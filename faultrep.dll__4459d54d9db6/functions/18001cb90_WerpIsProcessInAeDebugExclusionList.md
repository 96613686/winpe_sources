# WerpIsProcessInAeDebugExclusionList

- ea: `0x18001cb90`
- end: `0x18001ce12`
- name: `WerpIsProcessInAeDebugExclusionList`
- size: `642`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c370`

## callees

- `0x180002890`
- `0x180003474`
- `0x180003617`
- `0x180007704`
- `0x18001bfb0`
- `0x18001cb90`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18001cd8d`
- `ntdll!NtQueryValueKey` at `0x18001cd8d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001cd37`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001cd37`
- `ntdll!NtOpenKey` at `0x18001cd1c`
- `ntdll!NtOpenKey` at `0x18001cd1c`
- `ntdll!NtQueryInformationProcess` at `0x18001cc36`
- `ntdll!NtQueryInformationProcess` at `0x18001cc36`
- `ntdll!DbgPrintEx` at `0x18001cc72`
- `ntdll!DbgPrintEx` at `0x18001cdcb`
- `ntdll!DbgPrintEx` at `0x18001cc72`
- `ntdll!DbgPrintEx` at `0x18001cdcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cddf`

## string_xrefs

- `0x18001cdbd`: `WER/CrashAPI/%u:%u: ERROR WerpPathTail returned NULL\n`

## pseudocode

```c
__int64 __fastcall WerpIsProcessInAeDebugExclusionList(HANDLE ProcessHandle)
{
  unsigned int v2; // edi
  int IsProtectedProcess; // esi
  NTSTATUS v4; // ebx
  DWORD CurrentProcessId_0; // eax
  __int64 v6; // rax
  const WCHAR *v7; // rcx
  unsigned __int64 v8; // rax
  __int64 v9; // r8
  const WCHAR *v10; // rbx
  __int64 *v11; // rax
  void **v12; // rax
  NTSTATUS inited; // ebx
  DWORD v14; // eax
  DWORD v15; // eax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int16 ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[6]; // [rsp+82h] [rbp-7Eh] BYREF
  unsigned __int64 v24; // [rsp+88h] [rbp-78h]
  int KeyValueInformation; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v26; // [rsp+2A4h] [rbp+1A4h]

  KeyHandle = 0;
  ProcessInformation = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(v23, 0, 0x21Eu);
  KeyValueInformation = 0;
  ResultLength = 0;
  v2 = 0;
  v26 = 0;
  DestinationString = 0;
  IsProtectedProcess = WerpIsProtectedProcess(ProcessHandle);
  v4 = NtQueryInformationProcess(ProcessHandle, ProcessImageFileNameWin32, &ProcessInformation, 0x218u, 0);
  if ( (v4 & 0xC0000000) == 0xC0000000 )
  {
    CurrentProcessId_0 = GetCurrentProcessId_0();
    LODWORD(ReturnLength) = 4273;
    DbgPrintEx(
      0x96u,
      0,
      "WER/CrashAPI/%u:%u: ERROR NtQueryInformationProcess failed 0x%x\n",
      CurrentProcessId_0,
      ReturnLength,
      v4);
  }
  else
  {
    if ( !v24 )
      goto LABEL_22;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v24 + 2 * v6) );
    v7 = (const WCHAR *)(v24 + 2 * v6);
    while ( 1 )
    {
      v10 = v7;
      if ( (unsigned __int64)v7 <= v24 )
        break;
      v8 = *--v7;
      LOWORD(v8) = v8 - 47;
      if ( (unsigned __int16)v8 <= 0x2Du )
      {
        v9 = 0x200000000801LL;
        if ( _bittest64(&v9, v8) )
          break;
      }
    }
    if ( v10 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      v11 = &qword_18004D8E8;
      if ( !IsProtectedProcess )
        v11 = &qword_18004D8F8;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v12 = tlx::replace<tlx::file_handle_traits>(&KeyHandle);
      if ( NtOpenKey(v12, 1u, &ObjectAttributes) >= 0 )
      {
        ResultLength = 0;
        inited = RtlInitUnicodeStringEx(&DestinationString, v10);
        if ( (inited & 0xC0000000) == 0xC0000000 )
        {
          v14 = GetCurrentProcessId_0();
          LODWORD(ReturnLength) = 4307;
          DbgPrintEx(
            0x96u,
            0,
            "WER/CrashAPI/%u:%u: ERROR RtlInitUnicodeStringEx returned 0x%x\n",
            v14,
            ReturnLength,
            inited);
        }
        else if ( NtQueryValueKey(
                    KeyHandle,
                    &DestinationString,
                    KeyValuePartialInformation,
                    &KeyValueInformation,
                    0x14u,
                    &ResultLength) >= 0
               && (_DWORD)v26 == 4
               && DWORD2(v26) )
        {
          v2 = 1;
        }
      }
    }
    else
    {
LABEL_22:
      v15 = GetCurrentProcessId_0();
      DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR WerpPathTail returned NULL\n", v15, 4281);
    }
  }
  if ( (unsigned __int64)KeyHandle + 1 > 1 )
    CloseHandle(KeyHandle);
  return v2;
}

```

## disassembly

```asm
0x18001cb90  mov     [rsp-8+arg_8], rbx
0x18001cb95  mov     [rsp-8+arg_10], rsi
0x18001cb9a  push    rbp
0x18001cb9b  push    rdi
0x18001cb9c  push    r12
0x18001cb9e  push    r14
0x18001cba0  push    r15
0x18001cba2  lea     rbp, [rsp-1C0h]
0x18001cbaa  sub     rsp, 2C0h
0x18001cbb1  mov     rax, cs:__security_cookie
0x18001cbb8  xor     rax, rsp
0x18001cbbb  mov     [rbp+1E0h+var_28], rax
0x18001cbc2  xorps   xmm0, xmm0
0x18001cbc5  mov     rbx, rcx
0x18001cbc8  xor     r14d, r14d
0x18001cbcb  lea     rcx, [rbp+1E0h+var_25E]; void *
0x18001cbcf  xor     edx, edx; Val
0x18001cbd1  mov     [rsp+2E0h+KeyHandle], r14
0x18001cbd6  mov     r8d, 21Eh; Size
0x18001cbdc  mov     [rbp+1E0h+ProcessInformation], r14w
0x18001cbe1  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x18001cbe6  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x18001cbeb  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001cbf0  call    memset_0
0x18001cbf5  xorps   xmm0, xmm0
0x18001cbf8  mov     [rbp+1E0h+KeyValueInformation], r14d
0x18001cbff  xorps   xmm1, xmm1
0x18001cc02  mov     [rsp+2E0h+var_2B0], r14d
0x18001cc07  mov     rcx, rbx; ProcessHandle
0x18001cc0a  mov     edi, r14d
0x18001cc0d  movups  [rbp+1E0h+var_3C], xmm0
0x18001cc14  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm1
0x18001cc19  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x18001cc1e  mov     r9d, 218h; ProcessInformationLength
0x18001cc24  mov     [rsp+2E0h+ReturnLength], r14; ReturnLength
0x18001cc29  lea     r8, [rbp+1E0h+ProcessInformation]; ProcessInformation
0x18001cc2d  mov     rcx, rbx; ProcessHandle
0x18001cc30  lea     edx, [r14+2Bh]; ProcessInformationClass
0x18001cc34  mov     esi, eax
0x18001cc36  call    cs:__imp_NtQueryInformationProcess
0x18001cc3c  mov     r12d, 0C0000000h
0x18001cc42  lea     r15d, [r14+1]
0x18001cc46  mov     ebx, eax
0x18001cc48  and     eax, r12d
0x18001cc4b  cmp     eax, r12d
0x18001cc4e  jnz     short loc_18001CC7D
0x18001cc50  call    GetCurrentProcessId_0
0x18001cc55  mov     dword ptr [rsp+2E0h+ResultLength], ebx
0x18001cc59  lea     r8, aWerCrashapiUUE_27; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x18001cc60  mov     dword ptr [rsp+2E0h+ReturnLength], 10B1h
0x18001cc68  mov     r9d, eax
0x18001cc6b  xor     edx, edx; Level
0x18001cc6d  mov     ecx, 96h; ComponentId
0x18001cc72  call    cs:__imp_DbgPrintEx
0x18001cc78  jmp     loc_18001CDD1
0x18001cc7d  mov     rdx, [rbp+1E0h+var_258]
0x18001cc81  test    rdx, rdx
0x18001cc84  jz      loc_18001CDAD
0x18001cc8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001cc8e  inc     rax
0x18001cc91  cmp     [rdx+rax*2], r14w
0x18001cc96  jnz     short loc_18001CC8E
0x18001cc98  lea     rcx, [rdx+rax*2]
0x18001cc9c  jmp     short loc_18001CCBF
0x18001cc9e  sub     rcx, 2
0x18001cca2  movzx   eax, word ptr [rcx]
0x18001cca5  sub     ax, 2Fh ; '/'
0x18001cca9  cmp     ax, 2Dh ; '-'
0x18001ccad  ja      short loc_18001CCBF
0x18001ccaf  mov     r8, 200000000801h
0x18001ccb9  bt      r8, rax
0x18001ccbd  jb      short loc_18001CCC7
0x18001ccbf  mov     rbx, rcx
0x18001ccc2  cmp     rcx, rdx
0x18001ccc5  ja      short loc_18001CC9E
0x18001ccc7  test    rbx, rbx
0x18001ccca  jz      loc_18001CDAD
0x18001ccd0  lea     rcx, qword_18004D8F8
0x18001ccd7  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x18001ccdf  xorps   xmm0, xmm0
0x18001cce2  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r14
0x18001cce7  test    esi, esi
0x18001cce9  mov     [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18001ccf1  lea     rax, qword_18004D8E8
0x18001ccf8  cmovz   rax, rcx
0x18001ccfc  lea     rcx, [rsp+2E0h+KeyHandle]
0x18001cd01  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x18001cd06  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001cd0c  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001cd11  mov     rcx, rax; KeyHandle
0x18001cd14  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18001cd19  mov     edx, r15d; DesiredAccess
0x18001cd1c  call    cs:__imp_NtOpenKey
0x18001cd22  test    eax, eax
0x18001cd24  js      loc_18001CDD1
0x18001cd2a  mov     rdx, rbx; SourceString
0x18001cd2d  mov     [rsp+2E0h+var_2B0], r14d
0x18001cd32  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x18001cd37  call    cs:__imp_RtlInitUnicodeStringEx
0x18001cd3d  mov     ebx, eax
0x18001cd3f  and     eax, r12d
0x18001cd42  cmp     eax, r12d
0x18001cd45  jnz     short loc_18001CD64
0x18001cd47  call    GetCurrentProcessId_0
0x18001cd4c  mov     dword ptr [rsp+2E0h+ResultLength], ebx
0x18001cd50  lea     r8, aWerCrashapiUUE_12; "WER/CrashAPI/%u:%u: ERROR RtlInitUnicod"...
0x18001cd57  mov     dword ptr [rsp+2E0h+ReturnLength], 10D3h
0x18001cd5f  jmp     loc_18001CC68
0x18001cd64  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x18001cd69  lea     rax, [rsp+2E0h+var_2B0]
0x18001cd6e  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18001cd73  lea     r9, [rbp+1E0h+KeyValueInformation]; KeyValueInformation
0x18001cd7a  mov     r8d, 2; KeyValueInformationClass
0x18001cd80  mov     dword ptr [rsp+2E0h+ReturnLength], 14h; Length
0x18001cd88  lea     rdx, [rsp+2E0h+DestinationString]; ValueName
0x18001cd8d  call    cs:__imp_NtQueryValueKey
0x18001cd93  test    eax, eax
0x18001cd95  js      short loc_18001CDD1
0x18001cd97  cmp     dword ptr [rbp+1E0h+var_3C], 4
0x18001cd9e  jnz     short loc_18001CDD1
0x18001cda0  cmp     dword ptr [rbp+1E0h+var_3C+8], r14d
0x18001cda7  cmovnz  edi, r15d
0x18001cdab  jmp     short loc_18001CDD1
0x18001cdad  call    GetCurrentProcessId_0
0x18001cdb2  mov     r9d, eax
0x18001cdb5  mov     dword ptr [rsp+2E0h+ReturnLength], 10B9h
0x18001cdbd  lea     r8, aWerCrashapiUUE_21; "WER/CrashAPI/%u:%u: ERROR WerpPathTail "...
0x18001cdc4  xor     edx, edx; Level
0x18001cdc6  mov     ecx, 96h; ComponentId
0x18001cdcb  call    cs:__imp_DbgPrintEx
0x18001cdd1  mov     rcx, [rsp+2E0h+KeyHandle]; hObject
0x18001cdd6  lea     rdx, [rcx+1]
0x18001cdda  cmp     rdx, r15
0x18001cddd  jbe     short loc_18001CDE5
0x18001cddf  call    cs:__imp_CloseHandle
0x18001cde5  mov     eax, edi
0x18001cde7  mov     rcx, [rbp+1E0h+var_28]
0x18001cdee  xor     rcx, rsp; StackCookie
0x18001cdf1  call    __security_check_cookie
0x18001cdf6  lea     r11, [rsp+2E0h+var_20]
0x18001cdfe  mov     rbx, [r11+38h]
0x18001ce02  mov     rsi, [r11+40h]
0x18001ce06  mov     rsp, r11
0x18001ce09  pop     r15
0x18001ce0b  pop     r14
0x18001ce0d  pop     r12
0x18001ce0f  pop     rdi
0x18001ce10  pop     rbp
0x18001ce11  retn
```
