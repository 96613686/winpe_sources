# WerpIsProcessInAeDebugExclusionList

- ea: `0x18005193c`
- end: `0x180051bba`
- name: `WerpIsProcessInAeDebugExclusionList`
- size: `638`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180051bc0`

## callees

- `0x18005193c`
- `0x180052114`
- `0x1800529d0`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180051a18`
- `ntdll!DbgPrintEx` at `0x180051b82`
- `ntdll!DbgPrintEx` at `0x180051a18`
- `ntdll!DbgPrintEx` at `0x180051b82`
- `ntdll!NtQueryValueKey` at `0x180051b3e`
- `ntdll!NtQueryValueKey` at `0x180051b3e`
- `ntdll!RtlInitUnicodeStringEx` at `0x180051ae7`
- `ntdll!RtlInitUnicodeStringEx` at `0x180051ae7`
- `ntdll!NtOpenKey` at `0x180051ac6`
- `ntdll!NtOpenKey` at `0x180051ac6`
- `ntdll!NtQueryInformationProcess` at `0x1800519d9`
- `ntdll!NtQueryInformationProcess` at `0x1800519d9`

## string_xrefs

- `0x180051b6c`: `WER/CrashAPI/%u:%u: ERROR WerpPathTail returned NULL\n`

## pseudocode

```c
__int64 __fastcall WerpIsProcessInAeDebugExclusionList(HANDLE ProcessHandle)
{
  unsigned int v2; // edi
  int IsProtectedProcess; // esi
  NTSTATUS v4; // ecx
  const CHAR *v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rax
  const WCHAR *v8; // rax
  const WCHAR *v9; // rbx
  void *v10; // rdx
  __int64 *v11; // rax
  NTSTATUS inited; // ecx
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  NTSTATUS ResultLength; // [rsp+28h] [rbp-D8h]
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int64 ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v21; // [rsp+88h] [rbp-78h]
  int KeyValueInformation; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v23; // [rsp+2A4h] [rbp+1A4h]

  KeyHandle = 0;
  LOWORD(ProcessInformation) = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0((char *)&ProcessInformation + 2, 0, 0x21Eu);
  KeyValueInformation = 0;
  LODWORD(v16) = 0;
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
    DbgPrintEx(
      0x96u,
      0,
      v5,
      NtCurrentTeb()->ClientId.UniqueProcess,
      ReturnLength,
      ResultLength,
      v16,
      KeyHandle,
      *(_QWORD *)&DestinationString.Length,
      DestinationString.Buffer,
      *(_QWORD *)&ObjectAttributes.Length,
      ObjectAttributes.RootDirectory,
      ObjectAttributes.ObjectName,
      *(_QWORD *)&ObjectAttributes.Attributes,
      ObjectAttributes.SecurityDescriptor,
      ObjectAttributes.SecurityQualityOfService,
      ProcessInformation);
    goto LABEL_24;
  }
  if ( !v21 )
    goto LABEL_23;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v21 + 2 * v7) );
  v8 = (const WCHAR *)(v21 + 2 * v7);
  do
  {
    v9 = v8;
    if ( (unsigned __int64)v8 <= v21 )
      break;
    if ( *--v8 == 92 )
      break;
  }
  while ( *v8 != 47 && *v8 != 58 );
  if ( !v9 )
  {
LABEL_23:
    DbgPrintEx(
      0x96u,
      0,
      "WER/CrashAPI/%u:%u: ERROR WerpPathTail returned NULL\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      4281);
    goto LABEL_24;
  }
  v10 = KeyHandle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  v11 = &qword_180086088;
  ObjectAttributes.Attributes = 64;
  if ( !IsProtectedProcess )
    v11 = &qword_180086098;
  KeyHandle = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  tlx::file_handle_traits::operator()(&qword_180086098, v10);
  if ( NtOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
  {
    LODWORD(v16) = 0;
    inited = RtlInitUnicodeStringEx(&DestinationString, v9);
    if ( (inited & 0xC0000000) == 0xC0000000 )
    {
      ResultLength = inited;
      v5 = "WER/CrashAPI/%u:%u: ERROR RtlInitUnicodeStringEx returned 0x%x\n";
      LODWORD(ReturnLength) = 4307;
      goto LABEL_3;
    }
    if ( NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x14u,
           (PULONG)&v16) >= 0
      && (_DWORD)v23 == 4
      && DWORD2(v23) )
    {
      v2 = 1;
    }
  }
LABEL_24:
  tlx::file_handle_traits::operator()(v6, KeyHandle);
  return v2;
}

```

## disassembly

```asm
0x18005193c  push    rbp
0x18005193e  push    rbx
0x18005193f  push    rsi
0x180051940  push    rdi
0x180051941  push    r14
0x180051943  push    r15
0x180051945  lea     rbp, [rsp-1C8h]
0x18005194d  sub     rsp, 2C8h
0x180051954  mov     rax, cs:__security_cookie
0x18005195b  xor     rax, rsp
0x18005195e  mov     [rbp+1F0h+var_38], rax
0x180051965  xorps   xmm0, xmm0
0x180051968  mov     rbx, rcx
0x18005196b  xor     r14d, r14d
0x18005196e  lea     rcx, [rbp+1F0h+var_26E]; void *
0x180051972  xor     edx, edx; Val
0x180051974  mov     [rsp+2F0h+KeyHandle], r14
0x180051979  mov     r8d, 21Eh; Size
0x18005197f  mov     [rbp+1F0h+ProcessInformation], r14w
0x180051984  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x180051989  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm0
0x18005198e  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180051993  call    memset_0
0x180051998  xorps   xmm0, xmm0
0x18005199b  mov     [rbp+1F0h+KeyValueInformation], r14d
0x1800519a2  xorps   xmm1, xmm1
0x1800519a5  mov     dword ptr [rsp+2F0h+var_2C0], r14d
0x1800519aa  mov     rcx, rbx; ProcessHandle
0x1800519ad  mov     edi, r14d
0x1800519b0  movups  [rbp+1F0h+var_4C], xmm0
0x1800519b7  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm1
0x1800519bc  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x1800519c1  mov     r9d, 218h; ProcessInformationLength
0x1800519c7  mov     [rsp+2F0h+ReturnLength], r14; ReturnLength
0x1800519cc  lea     r8, [rbp+1F0h+ProcessInformation]; ProcessInformation
0x1800519d0  mov     rcx, rbx; ProcessHandle
0x1800519d3  lea     edx, [r14+2Bh]; ProcessInformationClass
0x1800519d7  mov     esi, eax
0x1800519d9  call    cs:__imp_NtQueryInformationProcess
0x1800519e0  nop     dword ptr [rax+rax+00h]
0x1800519e5  mov     r15d, 0C0000000h
0x1800519eb  mov     ecx, eax
0x1800519ed  and     eax, r15d
0x1800519f0  cmp     eax, r15d
0x1800519f3  jnz     short loc_180051A29
0x1800519f5  mov     dword ptr [rsp+2F0h+ResultLength], ecx
0x1800519f9  lea     r8, aWerCrashapiUUE_47; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x180051a00  mov     dword ptr [rsp+2F0h+ReturnLength], 10B1h
0x180051a08  mov     r9, gs:40h
0x180051a11  xor     edx, edx; Level
0x180051a13  mov     ecx, 96h; ComponentId
0x180051a18  call    cs:__imp_DbgPrintEx
0x180051a1f  nop     dword ptr [rax+rax+00h]
0x180051a24  jmp     loc_180051B8E
0x180051a29  mov     rcx, [rbp+1F0h+var_268]
0x180051a2d  test    rcx, rcx
0x180051a30  jz      loc_180051B63
0x180051a36  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051a3a  inc     rax
0x180051a3d  cmp     [rcx+rax*2], r14w
0x180051a42  jnz     short loc_180051A3A
0x180051a44  lea     rax, [rcx+rax*2]
0x180051a48  mov     rbx, rax
0x180051a4b  cmp     rax, rcx
0x180051a4e  jbe     short loc_180051A66
0x180051a50  sub     rax, 2
0x180051a54  cmp     word ptr [rax], 5Ch ; '\'
0x180051a58  jz      short loc_180051A66
0x180051a5a  cmp     word ptr [rax], 2Fh ; '/'
0x180051a5e  jz      short loc_180051A66
0x180051a60  cmp     word ptr [rax], 3Ah ; ':'
0x180051a64  jnz     short loc_180051A48
0x180051a66  test    rbx, rbx
0x180051a69  jz      loc_180051B63
0x180051a6f  mov     rdx, [rsp+2F0h+KeyHandle]
0x180051a74  lea     rcx, qword_180086098
0x180051a7b  xorps   xmm0, xmm0
0x180051a7e  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x180051a86  test    esi, esi
0x180051a88  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], r14
0x180051a8d  lea     rax, qword_180086088
0x180051a94  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x180051a9c  cmovz   rax, rcx
0x180051aa0  mov     [rsp+2F0h+KeyHandle], r14
0x180051aa5  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x180051aaa  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180051ab0  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x180051ab5  mov     esi, 1
0x180051aba  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x180051abf  mov     edx, esi; DesiredAccess
0x180051ac1  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x180051ac6  call    cs:__imp_NtOpenKey
0x180051acd  nop     dword ptr [rax+rax+00h]
0x180051ad2  test    eax, eax
0x180051ad4  js      loc_180051B8E
0x180051ada  mov     rdx, rbx; SourceString
0x180051add  mov     dword ptr [rsp+2F0h+var_2C0], r14d
0x180051ae2  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x180051ae7  call    cs:__imp_RtlInitUnicodeStringEx
0x180051aee  nop     dword ptr [rax+rax+00h]
0x180051af3  mov     ecx, eax
0x180051af5  and     eax, r15d
0x180051af8  cmp     eax, r15d
0x180051afb  jnz     short loc_180051B15
0x180051afd  mov     dword ptr [rsp+2F0h+ResultLength], ecx
0x180051b01  lea     r8, aWerCrashapiUUE_27; "WER/CrashAPI/%u:%u: ERROR RtlInitUnicod"...
0x180051b08  mov     dword ptr [rsp+2F0h+ReturnLength], 10D3h
0x180051b10  jmp     loc_180051A08
0x180051b15  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x180051b1a  lea     rax, [rsp+2F0h+var_2C0]
0x180051b1f  mov     [rsp+2F0h+ResultLength], rax; ResultLength
0x180051b24  lea     r9, [rbp+1F0h+KeyValueInformation]; KeyValueInformation
0x180051b2b  mov     r8d, 2; KeyValueInformationClass
0x180051b31  mov     dword ptr [rsp+2F0h+ReturnLength], 14h; Length
0x180051b39  lea     rdx, [rsp+2F0h+DestinationString]; ValueName
0x180051b3e  call    cs:__imp_NtQueryValueKey
0x180051b45  nop     dword ptr [rax+rax+00h]
0x180051b4a  test    eax, eax
0x180051b4c  js      short loc_180051B8E
0x180051b4e  cmp     dword ptr [rbp+1F0h+var_4C], 4
0x180051b55  jnz     short loc_180051B8E
0x180051b57  cmp     dword ptr [rbp+1F0h+var_4C+8], r14d
0x180051b5e  cmovnz  edi, esi
0x180051b61  jmp     short loc_180051B8E
0x180051b63  mov     r9, gs:40h
0x180051b6c  lea     r8, aWerCrashapiUUE_38; "WER/CrashAPI/%u:%u: ERROR WerpPathTail "...
0x180051b73  xor     edx, edx; Level
0x180051b75  mov     dword ptr [rsp+2F0h+ReturnLength], 10B9h
0x180051b7d  mov     ecx, 96h; ComponentId
0x180051b82  call    cs:__imp_DbgPrintEx
0x180051b89  nop     dword ptr [rax+rax+00h]
0x180051b8e  mov     rdx, [rsp+2F0h+KeyHandle]
0x180051b93  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x180051b98  mov     eax, edi
0x180051b9a  mov     rcx, [rbp+1F0h+var_38]
0x180051ba1  xor     rcx, rsp; StackCookie
0x180051ba4  call    __security_check_cookie
0x180051ba9  add     rsp, 2C8h
0x180051bb0  pop     r15
0x180051bb2  pop     r14
0x180051bb4  pop     rdi
0x180051bb5  pop     rsi
0x180051bb6  pop     rbx
0x180051bb7  pop     rbp
0x180051bb8  retn
```
