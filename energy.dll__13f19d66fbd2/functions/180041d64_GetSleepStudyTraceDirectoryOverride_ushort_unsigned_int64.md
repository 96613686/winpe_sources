# GetSleepStudyTraceDirectoryOverride(ushort *,unsigned __int64)

- ea: `0x180041d64`
- end: `0x180041e15`
- name: `?GetSleepStudyTraceDirectoryOverride@@YAHPEAG_K@Z`
- size: `177`
- prototype: `_BOOL8 __fastcall(LPWSTR lpDst)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180041c5c`

## callees

- `0x180041d64`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041dc9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041dc9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180041de1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180041de1`

## string_xrefs

- `0x180041d8e`: `SleepStudyTraceDirectory`

## pseudocode

```c
_BOOL8 __fastcall GetSleepStudyTraceDirectoryOverride(LPWSTR lpDst)
{
  DWORD v2; // ecx
  DWORD pcbData[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR Src[264]; // [rsp+50h] [rbp-228h] BYREF

  pcbData[0] = 520;
  Src[0] = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Power",
         L"SleepStudyTraceDirectory",
         2u,
         0,
         Src,
         pcbData) )
  {
    return 0;
  }
  v2 = ExpandEnvironmentStringsW(Src, lpDst, 0x104u);
  return v2 && v2 <= 0x104;
}

```

## disassembly

```asm
0x180041d64  push    rbx
0x180041d66  sub     rsp, 270h
0x180041d6d  mov     rax, cs:__security_cookie
0x180041d74  xor     rax, rsp
0x180041d77  mov     [rsp+278h+var_18], rax
0x180041d7f  xor     eax, eax
0x180041d81  mov     [rsp+278h+var_238], 208h
0x180041d89  mov     [rsp+278h+Src], ax
0x180041d8e  lea     r8, aSleepstudytrac; "SleepStudyTraceDirectory"
0x180041d95  lea     rax, [rsp+278h+var_238]
0x180041d9a  mov     rbx, rcx
0x180041d9d  mov     [rsp+278h+pcbData], rax; pcbData
0x180041da2  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x180041da9  lea     rax, [rsp+278h+Src]
0x180041dae  mov     r9d, 2; dwFlags
0x180041db4  mov     [rsp+278h+pvData], rax; pvData
0x180041db9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180041dc0  mov     [rsp+278h+pdwType], 0; pdwType
0x180041dc9  call    cs:__imp_RegGetValueW
0x180041dcf  test    eax, eax
0x180041dd1  jnz     short loc_180041DFA
0x180041dd3  mov     r8d, 104h; nSize
0x180041dd9  lea     rcx, [rsp+278h+Src]; lpSrc
0x180041dde  mov     rdx, rbx; lpDst
0x180041de1  call    cs:__imp_ExpandEnvironmentStringsW
0x180041de7  mov     ecx, eax
0x180041de9  test    eax, eax
0x180041deb  jz      short loc_180041DFA
0x180041ded  xor     eax, eax
0x180041def  cmp     ecx, 104h
0x180041df5  setbe   al
0x180041df8  jmp     short loc_180041DFC
0x180041dfa  xor     eax, eax
0x180041dfc  mov     rcx, [rsp+278h+var_18]
0x180041e04  xor     rcx, rsp; StackCookie
0x180041e07  call    __security_check_cookie
0x180041e0c  add     rsp, 270h
0x180041e13  pop     rbx
0x180041e14  retn
```
