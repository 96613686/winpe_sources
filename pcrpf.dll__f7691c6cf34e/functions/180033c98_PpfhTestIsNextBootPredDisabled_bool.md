# PpfhTestIsNextBootPredDisabled(bool *)

- ea: `0x180033c98`
- end: `0x180033dfd`
- name: `?PpfhTestIsNextBootPredDisabled@@YAJPEA_N@Z`
- size: `357`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800107e8`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x180033c98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033d36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033dd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033d36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033dd0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033d83`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033d83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033cff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033cff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PpfhTestIsNextBootPredDisabled(bool *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  unsigned int ValueW; // eax
  __int64 v5; // rdx
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  HKEY hKey[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int pvData; // [rsp+78h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+30h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+38h] BYREF

  hKey[0] = 0;
  v2 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)hKey);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67A,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)(unsigned int)v2,
      phkResult);
    goto LABEL_13;
  }
  hkey = 0;
  ValueW = RegOpenKeyExW(hKey[0], L"Control\\PCRPF", 0, 0x20019u, &hkey);
  if ( ValueW )
  {
    v5 = 1660;
    goto LABEL_5;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"DisableNextBootPred", 0x20000018u, 0, &pvData, &pcbData);
  if ( ValueW != 2 )
  {
    if ( ValueW )
    {
      v5 = 1671;
LABEL_5:
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
             (const char *)ValueW,
             phkResulta);
      if ( hkey )
        RegCloseKey(hkey);
      goto LABEL_13;
    }
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x685u,
      "PpfhTestIsNextBootPredDisabled",
      "DisableNextBootPred test override set: %u",
      pvData);
  }
  *a1 = pvData == 1;
  if ( hkey )
    RegCloseKey(hkey);
  v3 = 0;
LABEL_13:
  PpfSystemCcsKey::~PpfSystemCcsKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180033c98  push    rbp
0x180033c9a  push    rbx
0x180033c9b  push    rdi
0x180033c9c  mov     rbp, rsp
0x180033c9f  sub     rsp, 50h
0x180033ca3  mov     rdi, rcx
0x180033ca6  mov     [rbp+hKey], 0
0x180033cae  lea     rcx, [rbp+hKey]; this
0x180033cb2  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x180033cb7  mov     ebx, eax
0x180033cb9  test    eax, eax
0x180033cbb  jns     short loc_180033CDA
0x180033cbd  mov     rcx, [rbp+18h]; this
0x180033cc1  mov     r9d, eax; char *
0x180033cc4  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180033ccb  mov     edx, 67Ah; void *
0x180033cd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033cd5  jmp     loc_180033DDE
0x180033cda  mov     [rbp+hkey], 0
0x180033ce2  lea     rax, [rbp+hkey]
0x180033ce6  mov     [rsp+50h+phkResult], rax; unsigned int
0x180033ceb  mov     r9d, 20019h; samDesired
0x180033cf1  xor     r8d, r8d; ulOptions
0x180033cf4  lea     rdx, aControlPcrpf; "Control\\PCRPF"
0x180033cfb  mov     rcx, [rbp+hKey]; hKey
0x180033cff  call    cs:__imp_RegOpenKeyExW
0x180033d06  nop     dword ptr [rax+rax+00h]
0x180033d0b  test    eax, eax
0x180033d0d  jz      short loc_180033D47
0x180033d0f  mov     edx, 67Ch; void *
0x180033d14  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180033d1b  mov     r9d, eax; char *
0x180033d1e  mov     rcx, [rbp+18h]; this
0x180033d22  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033d27  mov     ebx, eax
0x180033d29  mov     rcx, [rbp+hkey]; hKey
0x180033d2d  test    rcx, rcx
0x180033d30  jz      loc_180033DDE
0x180033d36  call    cs:__imp_RegCloseKey
0x180033d3d  nop     dword ptr [rax+rax+00h]
0x180033d42  jmp     loc_180033DDE
0x180033d47  mov     [rbp+arg_8], 0
0x180033d4e  mov     [rbp+arg_10], 4
0x180033d55  lea     rax, [rbp+arg_10]
0x180033d59  mov     [rsp+50h+pcbData], rax; pcbData
0x180033d5e  lea     rax, [rbp+arg_8]
0x180033d62  mov     [rsp+50h+pvData], rax; pvData
0x180033d67  mov     [rsp+50h+phkResult], 0; pdwType
0x180033d70  mov     r9d, 20000018h; dwFlags
0x180033d76  lea     r8, aDisablenextboo; "DisableNextBootPred"
0x180033d7d  xor     edx, edx; lpSubKey
0x180033d7f  mov     rcx, [rbp+hkey]; hkey
0x180033d83  call    cs:__imp_RegGetValueW
0x180033d8a  nop     dword ptr [rax+rax+00h]
0x180033d8f  cmp     eax, 2
0x180033d92  jz      short loc_180033DBE
0x180033d94  test    eax, eax
0x180033d96  jnz     short loc_180033DF2
0x180033d98  mov     eax, [rbp+arg_8]
0x180033d9b  mov     dword ptr [rsp+50h+phkResult], eax
0x180033d9f  lea     r9, aDisablenextboo_0; "DisableNextBootPred test override set: "...
0x180033da6  lea     r8, aPpfhtestisnext; "PpfhTestIsNextBootPredDisabled"
0x180033dad  mov     edx, 685h; unsigned int
0x180033db2  lea     rcx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180033db9  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180033dbe  cmp     [rbp+arg_8], 1
0x180033dc2  setz    al
0x180033dc5  mov     [rdi], al
0x180033dc7  mov     rcx, [rbp+hkey]; hKey
0x180033dcb  test    rcx, rcx
0x180033dce  jz      short loc_180033DDC
0x180033dd0  call    cs:__imp_RegCloseKey
0x180033dd7  nop     dword ptr [rax+rax+00h]
0x180033ddc  xor     ebx, ebx
0x180033dde  lea     rcx, [rbp+hKey]; this
0x180033de2  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180033de7  mov     eax, ebx
0x180033de9  add     rsp, 50h
0x180033ded  pop     rdi
0x180033dee  pop     rbx
0x180033def  pop     rbp
0x180033df0  retn
0x180033df2  mov     edx, 687h
0x180033df7  jmp     loc_180033D14
```
