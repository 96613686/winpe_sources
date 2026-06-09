# PpfhGetVolatileRegBoolean(ushort const *,bool *)

- ea: `0x1800334d0`
- end: `0x180033667`
- name: `?PpfhGetVolatileRegBoolean@@YAJPEBGPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR lpValue, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800398b4`
- `0x180052728`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x1800334d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033597`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003363d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033597`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003363d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800335e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800335e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033560`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033560`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PpfhGetVolatileRegBoolean(LPCWSTR lpValue, bool *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int ValueW; // eax
  __int64 v7; // rdx
  int dwOptions; // [rsp+20h] [rbp-40h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-40h]
  REGSAM samDesired[2]; // [rsp+28h] [rbp-38h]
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int pvData; // [rsp+88h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+30h] BYREF
  HKEY hkey; // [rsp+98h] [rbp+38h] BYREF

  *a2 = 0;
  hKey[0] = 0;
  v4 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)hKey);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B5,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)(unsigned int)v4,
      dwOptions);
    goto LABEL_15;
  }
  hkey = 0;
  ValueW = RegCreateKeyExW(hKey[0], L"Control\\PCRPF\\Volatile", 0, 0, 1u, 0x20019u, 0, &hkey, 0);
  if ( ValueW )
  {
    v7 = 952;
    goto LABEL_5;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, lpValue, 0x20000010u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      v7 = 960;
LABEL_5:
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
             (const char *)ValueW,
             dwOptionsa);
      if ( hkey )
        RegCloseKey(hkey);
      goto LABEL_15;
    }
  }
  else if ( pvData == 1 )
  {
    *a2 = 1;
  }
  samDesired[0] = *a2;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
    0x3C7u,
    "PpfhGetVolatileRegBoolean",
    "Get volatile %ws: %u",
    lpValue,
    *(_QWORD *)samDesired);
  if ( hkey )
    RegCloseKey(hkey);
  v5 = 0;
LABEL_15:
  PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)hKey);
  return v5;
}

```

## disassembly

```asm
0x1800334d0  mov     [rsp-18h+arg_0], rbx
0x1800334d5  push    rbp
0x1800334d6  push    rsi
0x1800334d7  push    rdi
0x1800334d8  mov     rbp, rsp
0x1800334db  sub     rsp, 60h
0x1800334df  mov     rdi, rdx
0x1800334e2  mov     rsi, rcx
0x1800334e5  mov     byte ptr [rdx], 0
0x1800334e8  mov     [rbp+hKey], 0
0x1800334f0  lea     rcx, [rbp+hKey]; this
0x1800334f4  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x1800334f9  mov     ebx, eax
0x1800334fb  test    eax, eax
0x1800334fd  jns     short loc_18003351C
0x1800334ff  mov     rcx, [rbp+18h]; this
0x180033503  mov     r9d, eax; char *
0x180033506  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003350d  mov     edx, 3B5h; void *
0x180033512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033517  jmp     loc_18003364B
0x18003351c  mov     [rbp+hkey], 0
0x180033524  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18003352d  lea     rax, [rbp+hkey]
0x180033531  mov     [rsp+60h+phkResult], rax; phkResult
0x180033536  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003353f  mov     [rsp+60h+samDesired], 20019h; samDesired
0x180033547  mov     [rsp+60h+dwOptions], 1; unsigned int
0x18003354f  xor     r9d, r9d; lpClass
0x180033552  xor     r8d, r8d; Reserved
0x180033555  lea     rdx, aControlPcrpfVo; "Control\\PCRPF\\Volatile"
0x18003355c  mov     rcx, [rbp+hKey]; hKey
0x180033560  call    cs:__imp_RegCreateKeyExW
0x180033567  nop     dword ptr [rax+rax+00h]
0x18003356c  test    eax, eax
0x18003356e  jz      short loc_1800335A8
0x180033570  mov     edx, 3B8h; void *
0x180033575  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003357c  mov     r9d, eax; char *
0x18003357f  mov     rcx, [rbp+18h]; this
0x180033583  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033588  mov     ebx, eax
0x18003358a  mov     rcx, [rbp+hkey]; hKey
0x18003358e  test    rcx, rcx
0x180033591  jz      loc_18003364B
0x180033597  call    cs:__imp_RegCloseKey
0x18003359e  nop     dword ptr [rax+rax+00h]
0x1800335a3  jmp     loc_18003364B
0x1800335a8  mov     [rbp+pvData], 0
0x1800335af  mov     [rbp+pcbData], 4
0x1800335b6  lea     rax, [rbp+pcbData]
0x1800335ba  mov     [rsp+60h+lpSecurityAttributes], rax; pcbData
0x1800335bf  lea     rax, [rbp+pvData]
0x1800335c3  mov     qword ptr [rsp+60h+samDesired], rax; pvData
0x1800335c8  mov     qword ptr [rsp+60h+dwOptions], 0; pdwType
0x1800335d1  mov     r9d, 20000010h; dwFlags
0x1800335d7  mov     r8, rsi; lpValue
0x1800335da  xor     edx, edx; lpSubKey
0x1800335dc  mov     rcx, [rbp+hkey]; hkey
0x1800335e0  call    cs:__imp_RegGetValueW
0x1800335e7  nop     dword ptr [rax+rax+00h]
0x1800335ec  test    eax, eax
0x1800335ee  jz      short loc_1800335FF
0x1800335f0  cmp     eax, 2
0x1800335f3  jz      short loc_180033608
0x1800335f5  mov     edx, 3C0h
0x1800335fa  jmp     loc_180033575
0x1800335ff  cmp     [rbp+pvData], 1
0x180033603  jnz     short loc_180033608
0x180033605  mov     byte ptr [rdi], 1
0x180033608  movzx   eax, byte ptr [rdi]
0x18003360b  mov     [rsp+60h+samDesired], eax
0x18003360f  mov     qword ptr [rsp+60h+dwOptions], rsi
0x180033614  lea     r9, aGetVolatileWsU; "Get volatile %ws: %u"
0x18003361b  lea     r8, aPpfhgetvolatil; "PpfhGetVolatileRegBoolean"
0x180033622  mov     edx, 3C7h; unsigned int
0x180033627  lea     rcx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003362e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180033633  nop
0x180033634  mov     rcx, [rbp+hkey]; hKey
0x180033638  test    rcx, rcx
0x18003363b  jz      short loc_180033649
0x18003363d  call    cs:__imp_RegCloseKey
0x180033644  nop     dword ptr [rax+rax+00h]
0x180033649  xor     ebx, ebx
0x18003364b  lea     rcx, [rbp+hKey]; this
0x18003364f  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180033654  mov     eax, ebx
0x180033656  mov     rbx, [rsp+60h+arg_0]
0x18003365e  add     rsp, 60h
0x180033662  pop     rdi
0x180033663  pop     rsi
0x180033664  pop     rbp
0x180033665  retn
```
