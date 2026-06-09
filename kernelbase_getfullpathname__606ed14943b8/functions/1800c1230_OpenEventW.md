# OpenEventW

- ea: `0x1800c1230`
- end: `0x1800c14c1`
- name: `OpenEventW`
- size: `657`
- prototype: `HANDLE __stdcall(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c1160`

## callees

- `0x18004b9d0`
- `0x1800731a0`
- `0x1800c1230`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800c127b`
- `ntdll!RtlInitUnicodeString` at `0x1800c127b`
- `ntdll!NtClose` at `0x1800c13ea`
- `ntdll!NtClose` at `0x1800c13ff`
- `ntdll!NtClose` at `0x1800c14b0`
- `ntdll!NtClose` at `0x1800c13ea`
- `ntdll!NtClose` at `0x1800c13ff`
- `ntdll!NtClose` at `0x1800c14b0`
- `ntdll!NtOpenProcessToken` at `0x1800c1376`
- `ntdll!NtOpenProcessToken` at `0x1800c1376`
- `ntdll!NtOpenThreadToken` at `0x1800c1436`
- `ntdll!NtOpenThreadToken` at `0x1800c1436`
- `ntdll!NtSetInformationThread` at `0x1800c1463`
- `ntdll!NtSetInformationThread` at `0x1800c14a0`
- `ntdll!NtSetInformationThread` at `0x1800c1463`
- `ntdll!NtSetInformationThread` at `0x1800c14a0`
- `ntdll!NtOpenEvent` at `0x1800c12eb`
- `ntdll!NtOpenEvent` at `0x1800c12eb`

## pseudocode

```c
HANDLE __stdcall OpenEventW(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)
{
  void *v5; // rbx
  NTSTATUS v6; // eax
  int v8; // r15d
  int NamedObjectDirectoryForToken; // r14d
  HANDLE v10; // rcx
  HANDLE TokenHandle; // [rsp+38h] [rbp-29h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp-21h] BYREF
  HANDLE EventHandle; // [rsp+48h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-1h] BYREF
  HANDLE v16; // [rsp+D8h] [rbp+77h] BYREF
  HANDLE Handle; // [rsp+E0h] [rbp+7Fh] BYREF

  EventHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( !lpName )
  {
    BaseSetLastNTError(3221225485LL);
    return 0;
  }
  RtlInitUnicodeString(&DestinationString, lpName);
  v5 = (void *)BaseNamedObjectDirectory;
  v16 = 0;
  TokenHandle = 0;
  ThreadInformation = 0;
  Handle = 0;
  if ( BaseNamedObjectDirectory )
    goto LABEL_3;
  v5 = 0;
  v8 = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    NamedObjectDirectoryForToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &v16);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_15;
    ThreadInformation = 0;
    NamedObjectDirectoryForToken = NtSetInformationThread(
                                     (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                     ThreadImpersonationToken,
                                     &ThreadInformation,
                                     8u);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_15;
    v8 = 1;
  }
  NamedObjectDirectoryForToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( NamedObjectDirectoryForToken >= 0 )
  {
    NamedObjectDirectoryForToken = BasepGetNamedObjectDirectoryForToken(TokenHandle, 0, 1, 15, &Handle);
    if ( NamedObjectDirectoryForToken >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&BaseNamedObjectDirectory, (signed __int64)Handle, 0) )
        Handle = 0;
      v5 = (void *)BaseNamedObjectDirectory;
    }
  }
LABEL_15:
  v10 = v16;
  if ( v16 )
  {
    if ( v8 )
    {
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v16, 8u);
      v10 = v16;
    }
    NtClose(v10);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  if ( NamedObjectDirectoryForToken < 0 )
  {
    BaseSetLastNTError((unsigned int)NamedObjectDirectoryForToken);
    return 0;
  }
LABEL_3:
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v5;
  ObjectAttributes.Attributes = bInheritHandle ? 2 : 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( pfnAdjustObjectAttributesForPrivateNamespace )
    pfnAdjustObjectAttributesForPrivateNamespace(&ObjectAttributes);
  v6 = NtOpenEvent(&EventHandle, dwDesiredAccess, &ObjectAttributes);
  if ( v6 >= 0 )
    return EventHandle;
  BaseSetLastNTError((unsigned int)v6);
  return 0;
}

```

## disassembly

```asm
0x1800c1230  mov     r11, rsp
0x1800c1233  push    rbp
0x1800c1234  push    rsi
0x1800c1235  push    rdi
0x1800c1236  push    r12
0x1800c1238  lea     rbp, [r11-5Fh]
0x1800c123c  sub     rsp, 98h
0x1800c1243  xorps   xmm0, xmm0
0x1800c1246  xor     r12d, r12d
0x1800c1249  xor     eax, eax
0x1800c124b  mov     [rbp+57h+EventHandle], r12
0x1800c124f  mov     edi, edx
0x1800c1251  mov     esi, ecx
0x1800c1253  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800c1257  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800c125b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800c125f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800c1263  test    r8, r8
0x1800c1266  jz      loc_1800C1328
0x1800c126c  mov     [r11+8], rbx
0x1800c1270  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c1274  mov     rdx, r8; SourceString
0x1800c1277  mov     [r11+10h], r14
0x1800c127b  call    cs:__imp_RtlInitUnicodeString
0x1800c1282  nop     dword ptr [rax+rax+00h]
0x1800c1287  mov     rbx, cs:BaseNamedObjectDirectory
0x1800c128e  mov     [rbp+57h+arg_10], r12
0x1800c1292  mov     [rbp+57h+TokenHandle], r12
0x1800c1296  mov     [rbp+57h+ThreadInformation], r12
0x1800c129a  mov     [rbp+57h+Handle], r12
0x1800c129e  test    rbx, rbx
0x1800c12a1  jz      loc_1800C1342
0x1800c12a7  neg     edi
0x1800c12a9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800c12b0  xorps   xmm0, xmm0
0x1800c12b3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1800c12b7  sbb     eax, eax
0x1800c12b9  and     eax, 2
0x1800c12bc  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x1800c12bf  lea     rax, [rbp+57h+DestinationString]
0x1800c12c3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800c12c7  mov     rax, cs:pfnAdjustObjectAttributesForPrivateNamespace
0x1800c12ce  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c12d3  test    rax, rax
0x1800c12d6  jz      short loc_1800C12E1
0x1800c12d8  lea     rcx, [rbp+57h+ObjectAttributes]
0x1800c12dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c12e1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800c12e5  mov     edx, esi; DesiredAccess
0x1800c12e7  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x1800c12eb  call    cs:__imp_NtOpenEvent
0x1800c12f2  nop     dword ptr [rax+rax+00h]
0x1800c12f7  test    eax, eax
0x1800c12f9  js      short loc_1800C131D
0x1800c12fb  mov     rax, [rbp+57h+EventHandle]
0x1800c12ff  mov     rbx, [rsp+0B0h+arg_0]
0x1800c1307  mov     r14, [rsp+0B0h+arg_8]
0x1800c130f  add     rsp, 98h
0x1800c1316  pop     r12
0x1800c1318  pop     rdi
0x1800c1319  pop     rsi
0x1800c131a  pop     rbp
0x1800c131b  retn
0x1800c131d  mov     ecx, eax
0x1800c131f  call    BaseSetLastNTError
0x1800c1324  xor     eax, eax
0x1800c1326  jmp     short loc_1800C12FF
0x1800c1328  mov     ecx, 0C000000Dh
0x1800c132d  call    BaseSetLastNTError
0x1800c1332  xor     eax, eax
0x1800c1334  add     rsp, 98h
0x1800c133b  pop     r12
0x1800c133d  pop     rdi
0x1800c133e  pop     rsi
0x1800c133f  pop     rbp
0x1800c1340  retn
0x1800c1342  mov     rax, gs:30h
0x1800c134b  mov     rbx, r12
0x1800c134e  mov     [rsp+90h], r15
0x1800c1356  mov     r15d, r12d
0x1800c1359  cmp     [rax+179Ch], r12d
0x1800c1360  jnz     loc_1800C1423
0x1800c1366  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800c136a  mov     edx, 8; DesiredAccess
0x1800c136f  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800c1376  call    cs:__imp_NtOpenProcessToken
0x1800c137d  nop     dword ptr [rax+rax+00h]
0x1800c1382  mov     r14d, eax
0x1800c1385  test    eax, eax
0x1800c1387  js      short loc_1800C13CC
0x1800c1389  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800c138d  lea     rax, [rbp+57h+Handle]
0x1800c1391  xor     edx, edx
0x1800c1393  mov     [rsp+20h], rax; __int64
0x1800c1398  mov     r9d, 0Fh
0x1800c139e  mov     r8d, 1
0x1800c13a4  call    BasepGetNamedObjectDirectoryForToken
0x1800c13a9  mov     r14d, eax
0x1800c13ac  test    eax, eax
0x1800c13ae  js      short loc_1800C13CC
0x1800c13b0  mov     rcx, [rbp+57h+Handle]
0x1800c13b4  xor     eax, eax
0x1800c13b6  lock cmpxchg cs:BaseNamedObjectDirectory, rcx
0x1800c13bf  jnz     short loc_1800C13C5
0x1800c13c1  mov     [rbp+57h+Handle], r12
0x1800c13c5  mov     rbx, cs:BaseNamedObjectDirectory
0x1800c13cc  mov     rcx, [rbp+57h+arg_10]
0x1800c13d0  test    rcx, rcx
0x1800c13d3  jnz     loc_1800C1485
0x1800c13d9  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800c13dd  mov     r15, [rsp+90h]
0x1800c13e5  test    rcx, rcx
0x1800c13e8  jz      short loc_1800C13F6
0x1800c13ea  call    cs:__imp_NtClose
0x1800c13f1  nop     dword ptr [rax+rax+00h]
0x1800c13f6  mov     rcx, [rbp+57h+Handle]; Handle
0x1800c13fa  test    rcx, rcx
0x1800c13fd  jz      short loc_1800C140B
0x1800c13ff  call    cs:__imp_NtClose
0x1800c1406  nop     dword ptr [rax+rax+00h]
0x1800c140b  test    r14d, r14d
0x1800c140e  jns     loc_1800C12A7
0x1800c1414  mov     ecx, r14d
0x1800c1417  call    BaseSetLastNTError
0x1800c141c  xor     eax, eax
0x1800c141e  jmp     loc_1800C12FF
0x1800c1423  lea     r9, [rbp+57h+arg_10]; TokenHandle
0x1800c1427  mov     r8b, 1; OpenAsSelf
0x1800c142a  mov     edx, 4; DesiredAccess
0x1800c142f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c1436  call    cs:__imp_NtOpenThreadToken
0x1800c143d  nop     dword ptr [rax+rax+00h]
0x1800c1442  mov     r14d, eax
0x1800c1445  test    eax, eax
0x1800c1447  js      short loc_1800C13CC
0x1800c1449  mov     r9d, 8; ThreadInformationLength
0x1800c144f  mov     [rbp+57h+ThreadInformation], r12
0x1800c1453  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x1800c1457  mov     edx, 5; ThreadInformationClass
0x1800c145c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c1463  call    cs:__imp_NtSetInformationThread
0x1800c146a  nop     dword ptr [rax+rax+00h]
0x1800c146f  mov     r14d, eax
0x1800c1472  test    eax, eax
0x1800c1474  js      loc_1800C13CC
0x1800c147a  mov     r15d, 1
0x1800c1480  jmp     loc_1800C1366
0x1800c1485  test    r15d, r15d
0x1800c1488  jz      short loc_1800C14B0
0x1800c148a  mov     r9d, 8; ThreadInformationLength
0x1800c1490  lea     r8, [rbp+57h+arg_10]; ThreadInformation
0x1800c1494  mov     edx, 5; ThreadInformationClass
0x1800c1499  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c14a0  call    cs:__imp_NtSetInformationThread
0x1800c14a7  nop     dword ptr [rax+rax+00h]
0x1800c14ac  mov     rcx, [rbp+57h+arg_10]; Handle
0x1800c14b0  call    cs:__imp_NtClose
0x1800c14b7  nop     dword ptr [rax+rax+00h]
0x1800c14bc  jmp     loc_1800C13D9
```
