# PpfhIsOSWinPEBased(bool *)

- ea: `0x180033670`
- end: `0x180033755`
- name: `?PpfhIsOSWinPEBased@@YAJPEA_N@Z`
- size: `229`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800107e8`
- `0x18002d1a8`
- `0x18003639c`
- `0x18003fb34`

## callees

- `0x18000dfe0`
- `0x18002d5ec`
- `0x180033670`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033704`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033740`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033704`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033740`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800336a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800336a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PpfhIsOSWinPEBased(bool *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey);
  if ( !v2 )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x21Fu,
      "PpfhIsOSWinPEBased",
      "Running in WinPE based OS");
    *a1 = 1;
LABEL_8:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( v2 - 2 <= 1 )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x225u,
      "PpfhIsOSWinPEBased",
      "Not running in WinPE based OS");
    *a1 = 0;
    goto LABEL_8;
  }
  v3 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x229,
         (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
         (const char *)v2,
         phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180033670  push    rbx
0x180033672  sub     rsp, 30h
0x180033676  mov     rbx, rcx
0x180033679  mov     [rsp+38h+hKey], 0
0x180033682  lea     rax, [rsp+38h+hKey]
0x180033687  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x18003368c  mov     r9d, 20019h; samDesired
0x180033692  xor     r8d, r8d; ulOptions
0x180033695  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x18003369c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800336a3  call    cs:__imp_RegOpenKeyExW
0x1800336aa  nop     dword ptr [rax+rax+00h]
0x1800336af  mov     r9d, eax; char *
0x1800336b2  test    eax, eax
0x1800336b4  jnz     short loc_1800336DA
0x1800336b6  lea     r9, aRunningInWinpe; "Running in WinPE based OS"
0x1800336bd  lea     r8, aPpfhisoswinpeb; "PpfhIsOSWinPEBased"
0x1800336c4  mov     edx, 21Fh; unsigned int
0x1800336c9  lea     rcx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800336d0  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800336d5  mov     byte ptr [rbx], 1
0x1800336d8  jmp     short loc_180033736
0x1800336da  add     eax, 0FFFFFFFEh
0x1800336dd  cmp     eax, 1
0x1800336e0  jbe     short loc_180033714
0x1800336e2  mov     rcx, [rsp+38h]; this
0x1800336e7  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800336ee  mov     edx, 229h; void *
0x1800336f3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800336f8  mov     ebx, eax
0x1800336fa  mov     rcx, [rsp+38h+hKey]; hKey
0x1800336ff  test    rcx, rcx
0x180033702  jz      short loc_180033710
0x180033704  call    cs:__imp_RegCloseKey
0x18003370b  nop     dword ptr [rax+rax+00h]
0x180033710  mov     eax, ebx
0x180033712  jmp     short loc_18003374E
0x180033714  lea     r9, aNotRunningInWi; "Not running in WinPE based OS"
0x18003371b  lea     r8, aPpfhisoswinpeb; "PpfhIsOSWinPEBased"
0x180033722  mov     edx, 225h; unsigned int
0x180033727  lea     rcx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003372e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180033733  mov     byte ptr [rbx], 0
0x180033736  mov     rcx, [rsp+38h+hKey]; hKey
0x18003373b  test    rcx, rcx
0x18003373e  jz      short loc_18003374C
0x180033740  call    cs:__imp_RegCloseKey
0x180033747  nop     dword ptr [rax+rax+00h]
0x18003374c  xor     eax, eax
0x18003374e  add     rsp, 30h
0x180033752  pop     rbx
0x180033753  retn
```
