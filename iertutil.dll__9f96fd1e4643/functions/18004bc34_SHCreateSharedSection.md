# SHCreateSharedSection

- ea: `0x18004bc34`
- end: `0x18004bd15`
- name: `SHCreateSharedSection`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004bb90`

## callees

- `0x180018410`
- `0x18004bc34`
- `0x180053f78`
- `0x1800637bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004bc90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004bc99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004bc90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004bc99`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004bcc5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004bcc5`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18004bc57`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18004bcf3`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18004bc57`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18004bcf3`

## pseudocode

```c
__int64 __fastcall SHCreateSharedSection(__int64 a1, __int64 a2, void *a3, _QWORD *a4)
{
  HANDLE v5; // rax
  void *NamedSection; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v8; // rax
  HANDLE TargetHandle; // [rsp+60h] [rbp+18h] BYREF

  TargetHandle = a3;
  v5 = OpenFileMappingW(6u, 0, L"Local\\windows_ie_global_counters");
  TargetHandle = v5;
  if ( v5 )
    goto LABEL_7;
  if ( !(unsigned __int8)IEConfiguration_GetBool(536870913) && (unsigned __int8)IEConfiguration_GetBool(536870916) )
    goto LABEL_6;
  NamedSection = (void *)CreateNamedSection();
  if ( NamedSection )
  {
    CurrentProcess = GetCurrentProcess();
    v8 = GetCurrentProcess();
    DuplicateHandle(v8, NamedSection, CurrentProcess, &TargetHandle, 6u, 0, 1u);
LABEL_6:
    v5 = TargetHandle;
    goto LABEL_7;
  }
  if ( GetLastError() != 5 )
    goto LABEL_6;
  v5 = OpenFileMappingW(6u, 0, L"Local\\windows_ie_global_counters");
  TargetHandle = v5;
LABEL_7:
  *a4 = v5;
  if ( v5 )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x18004bc34  mov     [rsp+arg_0], rbx
0x18004bc39  mov     [rsp+arg_8], rsi
0x18004bc3e  mov     [rsp+TargetHandle], r8
0x18004bc43  push    rdi
0x18004bc44  sub     rsp, 40h
0x18004bc48  xor     edx, edx; bInheritHandle
0x18004bc4a  lea     r8, aLocalWindowsIe; "Local\\windows_ie_global_counters"
0x18004bc51  mov     rsi, r9
0x18004bc54  lea     ecx, [rdx+6]; dwDesiredAccess
0x18004bc57  call    cs:__imp_OpenFileMappingW
0x18004bc5d  mov     [rsp+48h+TargetHandle], rax
0x18004bc62  test    rax, rax
0x18004bc65  jnz     short loc_18004BCD0
0x18004bc67  mov     ecx, 20000001h
0x18004bc6c  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004bc71  test    al, al
0x18004bc73  jnz     short loc_18004BC83
0x18004bc75  mov     ecx, 20000004h
0x18004bc7a  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004bc7f  test    al, al
0x18004bc81  jnz     short loc_18004BCCB
0x18004bc83  call    _CreateNamedSection
0x18004bc88  mov     rdi, rax
0x18004bc8b  test    rax, rax
0x18004bc8e  jz      short loc_18004BCDC
0x18004bc90  call    cs:__imp_GetCurrentProcess
0x18004bc96  mov     rbx, rax
0x18004bc99  call    cs:__imp_GetCurrentProcess
0x18004bc9f  mov     [rsp+48h+dwOptions], 1; dwOptions
0x18004bca7  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x18004bcac  mov     rcx, rax; hSourceProcessHandle
0x18004bcaf  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x18004bcb7  mov     r8, rbx; hTargetProcessHandle
0x18004bcba  mov     [rsp+48h+dwDesiredAccess], 6; dwDesiredAccess
0x18004bcc2  mov     rdx, rdi; hSourceHandle
0x18004bcc5  call    cs:__imp_DuplicateHandle
0x18004bccb  mov     rax, [rsp+48h+TargetHandle]
0x18004bcd0  mov     [rsi], rax
0x18004bcd3  test    rax, rax
0x18004bcd6  jz      short loc_18004BD00
0x18004bcd8  xor     eax, eax
0x18004bcda  jmp     short loc_18004BD05
0x18004bcdc  call    cs:__imp_GetLastError
0x18004bce2  cmp     eax, 5
0x18004bce5  jnz     short loc_18004BCCB
0x18004bce7  lea     r8, aLocalWindowsIe; "Local\\windows_ie_global_counters"
0x18004bcee  xor     edx, edx; bInheritHandle
0x18004bcf0  lea     ecx, [rax+1]; dwDesiredAccess
0x18004bcf3  call    cs:__imp_OpenFileMappingW
0x18004bcf9  mov     [rsp+48h+TargetHandle], rax
0x18004bcfe  jmp     short loc_18004BCD0
0x18004bd00  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004bd05  mov     rbx, [rsp+48h+arg_0]
0x18004bd0a  mov     rsi, [rsp+48h+arg_8]
0x18004bd0f  add     rsp, 40h
0x18004bd13  pop     rdi
0x18004bd14  retn
```
