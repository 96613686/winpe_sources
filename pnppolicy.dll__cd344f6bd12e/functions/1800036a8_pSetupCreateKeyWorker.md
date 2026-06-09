# pSetupCreateKeyWorker

- ea: `0x1800036a8`
- end: `0x1800037c6`
- name: `pSetupCreateKeyWorker`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000355c`

## callees

- `0x1800036a8`
- `0x180003904`

## import_xrefs

- `ntdll!NtCreateKey` at `0x18000377f`
- `ntdll!NtCreateKey` at `0x18000377f`
- `ntdll!RtlInitUnicodeString` at `0x18000371b`
- `ntdll!RtlInitUnicodeString` at `0x18000371b`
- `ntdll!NtClose` at `0x1800037a7`
- `ntdll!NtClose` at `0x1800037a7`
- `ntdll!RtlNtStatusToDosError` at `0x18000378b`
- `ntdll!RtlNtStatusToDosError` at `0x18000378b`

## pseudocode

```c
__int64 __fastcall pSetupCreateKeyWorker(
        void *a1,
        const WCHAR *a2,
        __int64 a3,
        ULONG a4,
        ACCESS_MASK DesiredAccess,
        __int64 a6,
        _QWORD *a7)
{
  HANDLE v7; // rbx
  void *v10; // rsi
  ULONG v11; // edi
  ULONG v12; // eax
  int v13; // eax
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+C0h] [rbp+40h] BYREF

  KeyHandle = 0;
  v7 = 0;
  Handle = 0;
  v10 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned __int64)a1 + 0x80000000 <= 7 )
  {
    v12 = pSetupOpenPredefinedKey(a1, &Handle);
    v7 = Handle;
    v11 = v12;
    if ( v12 )
      goto LABEL_9;
  }
  else
  {
    v11 = 0;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  if ( v7 )
    v10 = v7;
  ObjectAttributes.RootDirectory = v10;
  ObjectAttributes.Attributes = (a4 & 8) != 0 ? 448 : 192;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = NtCreateKey(&KeyHandle, DesiredAccess, &ObjectAttributes, 0, 0, a4, 0);
  if ( v13 >= 0 )
    *a7 = (int)KeyHandle;
  else
    v11 = RtlNtStatusToDosError(v13);
LABEL_9:
  if ( v7 )
    NtClose((HANDLE)(unsigned int)v7);
  return v11;
}

```

## disassembly

```asm
0x1800036a8  mov     [rsp-28h+arg_8], rbx
0x1800036ad  mov     [rsp-28h+Handle], r8
0x1800036b2  push    rbp
0x1800036b3  push    rsi
0x1800036b4  push    rdi
0x1800036b5  push    r14
0x1800036b7  push    r15
0x1800036b9  mov     rbp, rsp
0x1800036bc  sub     rsp, 80h
0x1800036c3  xor     eax, eax
0x1800036c5  xorps   xmm0, xmm0
0x1800036c8  mov     [rbp+KeyHandle], rax
0x1800036cc  xor     ebx, ebx
0x1800036ce  mov     eax, 80000000h
0x1800036d3  mov     [rbp+Handle], rbx
0x1800036d7  add     rax, rcx
0x1800036da  mov     r14d, r9d
0x1800036dd  mov     r15, rdx
0x1800036e0  mov     rsi, rcx
0x1800036e3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800036e7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800036eb  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800036ef  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800036f3  cmp     rax, 7
0x1800036f7  jbe     short loc_1800036FD
0x1800036f9  xor     edi, edi
0x1800036fb  jmp     short loc_180003714
0x1800036fd  lea     rdx, [rbp+Handle]
0x180003701  call    pSetupOpenPredefinedKey
0x180003706  mov     rbx, [rbp+Handle]
0x18000370a  mov     edi, eax
0x18000370c  test    eax, eax
0x18000370e  jnz     loc_1800037A0
0x180003714  mov     rdx, r15; SourceString
0x180003717  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000371b  call    cs:__imp_RtlInitUnicodeString
0x180003721  mov     edx, [rbp+DesiredAccess]; DesiredAccess
0x180003724  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180003728  mov     ecx, r14d
0x18000372b  mov     [rsp+80h+Disposition], 0; Disposition
0x180003734  and     ecx, 8
0x180003737  mov     [rsp+80h+CreateOptions], r14d; CreateOptions
0x18000373c  test    rbx, rbx
0x18000373f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180003746  xorps   xmm0, xmm0
0x180003749  mov     [rsp+80h+Class], 0; Class
0x180003752  cmovnz  rsi, rbx
0x180003756  neg     ecx
0x180003758  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18000375c  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180003760  sbb     eax, eax
0x180003762  xor     r9d, r9d; TitleIndex
0x180003765  and     eax, 100h
0x18000376a  add     eax, 0C0h
0x18000376f  mov     [rbp+ObjectAttributes.Attributes], eax
0x180003772  lea     rax, [rbp+DestinationString]
0x180003776  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000377a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000377f  call    cs:__imp_NtCreateKey
0x180003785  test    eax, eax
0x180003787  jns     short loc_180003795
0x180003789  mov     ecx, eax; Status
0x18000378b  call    cs:__imp_RtlNtStatusToDosError
0x180003791  mov     edi, eax
0x180003793  jmp     short loc_1800037A0
0x180003795  mov     rax, [rbp+arg_30]
0x180003799  movsxd  rcx, dword ptr [rbp+KeyHandle]
0x18000379d  mov     [rax], rcx
0x1800037a0  test    rbx, rbx
0x1800037a3  jz      short loc_1800037AD
0x1800037a5  mov     ecx, ebx; Handle
0x1800037a7  call    cs:__imp_NtClose
0x1800037ad  mov     rbx, [rsp+80h+arg_8]
0x1800037b5  mov     eax, edi
0x1800037b7  add     rsp, 80h
0x1800037be  pop     r15
0x1800037c0  pop     r14
0x1800037c2  pop     rdi
0x1800037c3  pop     rsi
0x1800037c4  pop     rbp
0x1800037c5  retn
```
