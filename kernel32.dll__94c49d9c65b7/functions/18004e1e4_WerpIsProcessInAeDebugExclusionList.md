# WerpIsProcessInAeDebugExclusionList

- ea: `0x18004e1e4`
- end: `0x18004e467`
- name: `WerpIsProcessInAeDebugExclusionList`
- size: `643`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180052a00`

## callees

- `0x18004e1e4`
- `0x18004ec94`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18004e2c7`
- `ntdll!DbgPrintEx` at `0x18004e420`
- `ntdll!DbgPrintEx` at `0x18004e2c7`
- `ntdll!DbgPrintEx` at `0x18004e420`
- `ntdll!NtQueryValueKey` at `0x18004e3e1`
- `ntdll!NtQueryValueKey` at `0x18004e3e1`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004e390`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004e390`
- `ntdll!NtOpenKey` at `0x18004e375`
- `ntdll!NtOpenKey` at `0x18004e375`
- `ntdll!NtQueryInformationProcess` at `0x18004e28a`
- `ntdll!NtQueryInformationProcess` at `0x18004e28a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e434`

## string_xrefs

- `0x18004e40a`: `WER/CrashAPI/%u:%u: ERROR WerpPathTail returned NULL\n`

## pseudocode

```c
__int64 __fastcall WerpIsProcessInAeDebugExclusionList(HANDLE ProcessHandle)
{
  unsigned int v2; // edi
  int IsProtectedProcess; // esi
  NTSTATUS v4; // ecx
  const CHAR *v5; // r8
  __int64 v6; // rax
  const WCHAR *v7; // rax
  const WCHAR *v8; // rbx
  __int64 *v9; // rax
  HANDLE v10; // rcx
  NTSTATUS inited; // ecx
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  NTSTATUS ResultLength; // [rsp+28h] [rbp-D8h]
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int16 ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v20[6]; // [rsp+82h] [rbp-7Eh] BYREF
  unsigned __int64 v21; // [rsp+88h] [rbp-78h]
  int KeyValueInformation; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v23; // [rsp+2A4h] [rbp+1A4h]

  hObject = 0;
  ProcessInformation = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(v20, 0, 0x21Eu);
  KeyValueInformation = 0;
  LODWORD(v15) = 0;
  v2 = 0;
  v23 = 0;
  DestinationString = 0;
  IsProtectedProcess = WerpIsProtectedProcess(ProcessHandle);
  v4 = NtQueryInformationProcess(ProcessHandle, ProcessImageFileNameWin32, &ProcessInformation, 0x218u, 0);
  if ( (v4 & 0xC0000000) == 0xC0000000 )
  {
    ResultLength = v4;
    v5 = "WER/CrashAPI/%u:%u: ERROR NtQueryInformationProcess failed 0x%x\n";
    LODWORD(ReturnLength) = 4273;
LABEL_3:
    DbgPrintEx(0x96u, 0, v5, NtCurrentTeb()->ClientId.UniqueProcess, ReturnLength, ResultLength, v15);
    goto LABEL_26;
  }
  if ( !v21 )
    goto LABEL_25;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v21 + 2 * v6) );
  v7 = (const WCHAR *)(v21 + 2 * v6);
  do
  {
    v8 = v7;
    if ( (unsigned __int64)v7 <= v21 )
      break;
    if ( *--v7 == 92 )
      break;
  }
  while ( *v7 != 47 && *v7 != 58 );
  if ( v8 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    v9 = &qword_18007E088;
    ObjectAttributes.Attributes = 64;
    if ( !IsProtectedProcess )
      v9 = &qword_18007E098;
    v10 = hObject;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v9;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    hObject = 0;
    if ( (unsigned __int64)v10 + 1 > 1 )
      CloseHandle(v10);
    if ( NtOpenKey(&hObject, 1u, &ObjectAttributes) >= 0 )
    {
      LODWORD(v15) = 0;
      inited = RtlInitUnicodeStringEx(&DestinationString, v8);
      if ( (inited & 0xC0000000) == 0xC0000000 )
      {
        ResultLength = inited;
        v5 = "WER/CrashAPI/%u:%u: ERROR RtlInitUnicodeStringEx returned 0x%x\n";
        LODWORD(ReturnLength) = 4307;
        goto LABEL_3;
      }
      if ( NtQueryValueKey(
             hObject,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x14u,
             (PULONG)&v15) >= 0
        && (_DWORD)v23 == 4
        && DWORD2(v23) )
      {
        v2 = 1;
      }
    }
  }
  else
  {
LABEL_25:
    DbgPrintEx(
      0x96u,
      0,
      "WER/CrashAPI/%u:%u: ERROR WerpPathTail returned NULL\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      4281);
  }
LABEL_26:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v2;
}

```

## disassembly

```asm
0x18004e1e4  mov     [rsp-8+arg_8], rbx
0x18004e1e9  mov     [rsp-8+arg_10], rsi
0x18004e1ee  push    rbp
0x18004e1ef  push    rdi
0x18004e1f0  push    r12
0x18004e1f2  push    r14
0x18004e1f4  push    r15
0x18004e1f6  lea     rbp, [rsp-1C0h]
0x18004e1fe  sub     rsp, 2C0h
0x18004e205  mov     rax, cs:__security_cookie
0x18004e20c  xor     rax, rsp
0x18004e20f  mov     [rbp+1E0h+var_28], rax
0x18004e216  xorps   xmm0, xmm0
0x18004e219  mov     rbx, rcx
0x18004e21c  xor     r14d, r14d
0x18004e21f  lea     rcx, [rbp+1E0h+var_25E]; void *
0x18004e223  xor     edx, edx; Val
0x18004e225  mov     [rsp+2E0h+hObject], r14
0x18004e22a  mov     r8d, 21Eh; Size
0x18004e230  mov     [rbp+1E0h+ProcessInformation], r14w
0x18004e235  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x18004e23a  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x18004e23f  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004e244  call    memset_0
0x18004e249  xorps   xmm0, xmm0
0x18004e24c  mov     [rbp+1E0h+KeyValueInformation], r14d
0x18004e253  xorps   xmm1, xmm1
0x18004e256  mov     dword ptr [rsp+2E0h+var_2B0], r14d
0x18004e25b  mov     rcx, rbx; ProcessHandle
0x18004e25e  mov     edi, r14d
0x18004e261  movups  [rbp+1E0h+var_3C], xmm0
0x18004e268  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm1
0x18004e26d  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x18004e272  mov     r9d, 218h; ProcessInformationLength
0x18004e278  mov     [rsp+2E0h+ReturnLength], r14; ReturnLength
0x18004e27d  lea     r8, [rbp+1E0h+ProcessInformation]; ProcessInformation
0x18004e281  mov     rcx, rbx; ProcessHandle
0x18004e284  lea     edx, [r14+2Bh]; ProcessInformationClass
0x18004e288  mov     esi, eax
0x18004e28a  call    cs:__imp_NtQueryInformationProcess
0x18004e290  mov     r12d, 0C0000000h
0x18004e296  lea     r15d, [r14+1]
0x18004e29a  mov     ecx, eax
0x18004e29c  and     eax, r12d
0x18004e29f  cmp     eax, r12d
0x18004e2a2  jnz     short loc_18004E2D2
0x18004e2a4  mov     dword ptr [rsp+2E0h+ResultLength], ecx
0x18004e2a8  lea     r8, aWerCrashapiUUE_47; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x18004e2af  mov     dword ptr [rsp+2E0h+ReturnLength], 10B1h
0x18004e2b7  mov     r9, gs:40h
0x18004e2c0  xor     edx, edx; Level
0x18004e2c2  mov     ecx, 96h; ComponentId
0x18004e2c7  call    cs:__imp_DbgPrintEx
0x18004e2cd  jmp     loc_18004E426
0x18004e2d2  mov     rcx, [rbp+1E0h+var_258]
0x18004e2d6  test    rcx, rcx
0x18004e2d9  jz      loc_18004E401
0x18004e2df  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004e2e3  inc     rax
0x18004e2e6  cmp     [rcx+rax*2], r14w
0x18004e2eb  jnz     short loc_18004E2E3
0x18004e2ed  lea     rax, [rcx+rax*2]
0x18004e2f1  mov     rbx, rax
0x18004e2f4  cmp     rax, rcx
0x18004e2f7  jbe     short loc_18004E30F
0x18004e2f9  sub     rax, 2
0x18004e2fd  cmp     word ptr [rax], 5Ch ; '\'
0x18004e301  jz      short loc_18004E30F
0x18004e303  cmp     word ptr [rax], 2Fh ; '/'
0x18004e307  jz      short loc_18004E30F
0x18004e309  cmp     word ptr [rax], 3Ah ; ':'
0x18004e30d  jnz     short loc_18004E2F1
0x18004e30f  test    rbx, rbx
0x18004e312  jz      loc_18004E401
0x18004e318  test    esi, esi
0x18004e31a  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x18004e322  lea     rcx, qword_18007E098
0x18004e329  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r14
0x18004e32e  lea     rax, qword_18007E088
0x18004e335  mov     [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18004e33d  cmovz   rax, rcx
0x18004e341  xorps   xmm0, xmm0
0x18004e344  mov     rcx, [rsp+2E0h+hObject]; hObject
0x18004e349  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x18004e34e  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004e354  mov     [rsp+2E0h+hObject], r14
0x18004e359  lea     rax, [rcx+1]
0x18004e35d  cmp     rax, r15
0x18004e360  jbe     short loc_18004E368
0x18004e362  call    cs:__imp_CloseHandle
0x18004e368  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18004e36d  mov     edx, r15d; DesiredAccess
0x18004e370  lea     rcx, [rsp+2E0h+hObject]; KeyHandle
0x18004e375  call    cs:__imp_NtOpenKey
0x18004e37b  test    eax, eax
0x18004e37d  js      loc_18004E426
0x18004e383  mov     rdx, rbx; SourceString
0x18004e386  mov     dword ptr [rsp+2E0h+var_2B0], r14d
0x18004e38b  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x18004e390  call    cs:__imp_RtlInitUnicodeStringEx
0x18004e396  mov     ecx, eax
0x18004e398  and     eax, r12d
0x18004e39b  cmp     eax, r12d
0x18004e39e  jnz     short loc_18004E3B8
0x18004e3a0  mov     dword ptr [rsp+2E0h+ResultLength], ecx
0x18004e3a4  lea     r8, aWerCrashapiUUE_27; "WER/CrashAPI/%u:%u: ERROR RtlInitUnicod"...
0x18004e3ab  mov     dword ptr [rsp+2E0h+ReturnLength], 10D3h
0x18004e3b3  jmp     loc_18004E2B7
0x18004e3b8  mov     rcx, [rsp+2E0h+hObject]; KeyHandle
0x18004e3bd  lea     rax, [rsp+2E0h+var_2B0]
0x18004e3c2  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18004e3c7  lea     r9, [rbp+1E0h+KeyValueInformation]; KeyValueInformation
0x18004e3ce  mov     r8d, 2; KeyValueInformationClass
0x18004e3d4  mov     dword ptr [rsp+2E0h+ReturnLength], 14h; Length
0x18004e3dc  lea     rdx, [rsp+2E0h+DestinationString]; ValueName
0x18004e3e1  call    cs:__imp_NtQueryValueKey
0x18004e3e7  test    eax, eax
0x18004e3e9  js      short loc_18004E426
0x18004e3eb  cmp     dword ptr [rbp+1E0h+var_3C], 4
0x18004e3f2  jnz     short loc_18004E426
0x18004e3f4  cmp     dword ptr [rbp+1E0h+var_3C+8], r14d
0x18004e3fb  cmovnz  edi, r15d
0x18004e3ff  jmp     short loc_18004E426
0x18004e401  mov     r9, gs:40h
0x18004e40a  lea     r8, aWerCrashapiUUE_38; "WER/CrashAPI/%u:%u: ERROR WerpPathTail "...
0x18004e411  xor     edx, edx; Level
0x18004e413  mov     dword ptr [rsp+2E0h+ReturnLength], 10B9h
0x18004e41b  mov     ecx, 96h; ComponentId
0x18004e420  call    cs:__imp_DbgPrintEx
0x18004e426  mov     rcx, [rsp+2E0h+hObject]; hObject
0x18004e42b  lea     rdx, [rcx+1]
0x18004e42f  cmp     rdx, r15
0x18004e432  jbe     short loc_18004E43A
0x18004e434  call    cs:__imp_CloseHandle
0x18004e43a  mov     eax, edi
0x18004e43c  mov     rcx, [rbp+1E0h+var_28]
0x18004e443  xor     rcx, rsp; StackCookie
0x18004e446  call    __security_check_cookie
0x18004e44b  lea     r11, [rsp+2E0h+var_20]
0x18004e453  mov     rbx, [r11+38h]
0x18004e457  mov     rsi, [r11+40h]
0x18004e45b  mov     rsp, r11
0x18004e45e  pop     r15
0x18004e460  pop     r14
0x18004e462  pop     r12
0x18004e464  pop     rdi
0x18004e465  pop     rbp
0x18004e466  retn
```
