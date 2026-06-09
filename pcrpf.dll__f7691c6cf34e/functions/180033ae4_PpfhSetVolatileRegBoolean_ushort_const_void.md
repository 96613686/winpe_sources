# PpfhSetVolatileRegBoolean(ushort const *,void *)

- ea: `0x180033ae4`
- end: `0x180033c92`
- name: `?PpfhSetVolatileRegBoolean@@YAJPEBGPEAX@Z`
- size: `430`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, HANDLE hTransaction)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003796c`
- `0x180052728`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x180033ae4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033bb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033c68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033bb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033c68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033c1c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033c1c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033be4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033be4`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180033b79`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180033b79`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall PpfhSetVolatileRegBoolean(LPCWSTR lpValueName, HANDLE hTransaction)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  int dwOptions; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-50h]
  __int64 samDesired; // [rsp+28h] [rbp-48h]
  HKEY hKey[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int Data; // [rsp+A0h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp+38h] BYREF

  hKey[0] = 0;
  v4 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)hKey);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D1,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)(unsigned int)v4,
      dwOptions);
    goto LABEL_15;
  }
  phkResult = 0;
  if ( hTransaction )
  {
    v6 = RegCreateKeyTransactedW(hKey[0], L"Control\\PCRPF\\Volatile", 0, 0, 1u, 2u, 0, &phkResult, 0, hTransaction, 0);
    if ( v6 )
    {
      v7 = 982;
      goto LABEL_6;
    }
  }
  else
  {
    v6 = RegCreateKeyExW(hKey[0], L"Control\\PCRPF\\Volatile", 0, 0, 1u, 2u, 0, &phkResult, 0);
    if ( v6 )
    {
      v7 = 987;
      goto LABEL_6;
    }
  }
  Data = 1;
  v6 = RegSetValueExW(phkResult, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
  if ( v6 )
  {
    v7 = 992;
LABEL_6:
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v7,
           (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
           (const char *)v6,
           dwOptionsa);
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_15;
  }
  LODWORD(samDesired) = 1;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
    0x3E2u,
    "PpfhSetVolatileRegBoolean",
    "Set volatile %ws: %u",
    lpValueName,
    samDesired);
  if ( phkResult )
    RegCloseKey(phkResult);
  v5 = 0;
LABEL_15:
  PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)hKey);
  return v5;
}

```

## disassembly

```asm
0x180033ae4  mov     [rsp-18h+arg_0], rbx
0x180033ae9  push    rbp
0x180033aea  push    rsi
0x180033aeb  push    rdi
0x180033aec  mov     rbp, rsp
0x180033aef  sub     rsp, 70h
0x180033af3  mov     rdi, rdx
0x180033af6  mov     rsi, rcx
0x180033af9  mov     [rbp+hKey], 0
0x180033b01  lea     rcx, [rbp+hKey]; this
0x180033b05  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x180033b0a  mov     ebx, eax
0x180033b0c  test    eax, eax
0x180033b0e  jns     short loc_180033B2D
0x180033b10  mov     rcx, [rbp+18h]; this
0x180033b14  mov     r9d, eax; char *
0x180033b17  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180033b1e  mov     edx, 3D1h; void *
0x180033b23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033b28  jmp     loc_180033C76
0x180033b2d  mov     [rbp+arg_18], 0
0x180033b35  lea     rax, [rbp+arg_18]
0x180033b39  mov     ebx, 1
0x180033b3e  xor     r9d, r9d; lpClass
0x180033b41  xor     r8d, r8d; Reserved
0x180033b44  lea     rdx, aControlPcrpfVo; "Control\\PCRPF\\Volatile"
0x180033b4b  mov     rcx, [rbp+hKey]; hKey
0x180033b4f  test    rdi, rdi
0x180033b52  jz      short loc_180033BC1
0x180033b54  mov     [rsp+70h+pExtendedParemeter], r8; pExtendedParemeter
0x180033b59  mov     [rsp+70h+hTransaction], rdi; hTransaction
0x180033b5e  mov     [rsp+70h+lpdwDisposition], r8; lpdwDisposition
0x180033b63  mov     [rsp+70h+phkResult], rax; phkResult
0x180033b68  mov     [rsp+70h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180033b6d  mov     dword ptr [rsp+70h+samDesired], 2; samDesired
0x180033b75  mov     [rsp+70h+dwOptions], ebx; unsigned int
0x180033b79  call    cs:__imp_RegCreateKeyTransactedW
0x180033b80  nop     dword ptr [rax+rax+00h]
0x180033b85  test    eax, eax
0x180033b87  jz      short loc_180033BFB
0x180033b89  mov     edx, 3D6h; void *
0x180033b8e  mov     rcx, [rbp+18h]; this
0x180033b92  mov     r9d, eax; char *
0x180033b95  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180033b9c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033ba1  mov     ebx, eax
0x180033ba3  mov     rcx, [rbp+arg_18]; hKey
0x180033ba7  test    rcx, rcx
0x180033baa  jz      loc_180033C76
0x180033bb0  call    cs:__imp_RegCloseKey
0x180033bb7  nop     dword ptr [rax+rax+00h]
0x180033bbc  jmp     loc_180033C76
0x180033bc1  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180033bca  mov     [rsp+70h+phkResult], rax; phkResult
0x180033bcf  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180033bd8  mov     dword ptr [rsp+70h+samDesired], 2; samDesired
0x180033be0  mov     [rsp+70h+dwOptions], ebx; dwOptions
0x180033be4  call    cs:__imp_RegCreateKeyExW
0x180033beb  nop     dword ptr [rax+rax+00h]
0x180033bf0  test    eax, eax
0x180033bf2  jz      short loc_180033BFB
0x180033bf4  mov     edx, 3DBh
0x180033bf9  jmp     short loc_180033B8E
0x180033bfb  mov     [rbp+Data], ebx
0x180033bfe  mov     r9d, 4; dwType
0x180033c04  mov     dword ptr [rsp+70h+samDesired], r9d; cbData
0x180033c09  lea     rax, [rbp+Data]
0x180033c0d  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x180033c12  xor     r8d, r8d; Reserved
0x180033c15  mov     rdx, rsi; lpValueName
0x180033c18  mov     rcx, [rbp+arg_18]; hKey
0x180033c1c  call    cs:__imp_RegSetValueExW
0x180033c23  nop     dword ptr [rax+rax+00h]
0x180033c28  test    eax, eax
0x180033c2a  jz      short loc_180033C36
0x180033c2c  mov     edx, 3E0h
0x180033c31  jmp     loc_180033B8E
0x180033c36  mov     dword ptr [rsp+70h+samDesired], ebx
0x180033c3a  mov     qword ptr [rsp+70h+dwOptions], rsi
0x180033c3f  lea     r9, aSetVolatileWsU; "Set volatile %ws: %u"
0x180033c46  lea     r8, aPpfhsetvolatil; "PpfhSetVolatileRegBoolean"
0x180033c4d  mov     edx, 3E2h; unsigned int
0x180033c52  lea     rcx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180033c59  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180033c5e  nop
0x180033c5f  mov     rcx, [rbp+arg_18]; hKey
0x180033c63  test    rcx, rcx
0x180033c66  jz      short loc_180033C74
0x180033c68  call    cs:__imp_RegCloseKey
0x180033c6f  nop     dword ptr [rax+rax+00h]
0x180033c74  xor     ebx, ebx
0x180033c76  lea     rcx, [rbp+hKey]; this
0x180033c7a  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180033c7f  mov     eax, ebx
0x180033c81  mov     rbx, [rsp+70h+arg_0]
0x180033c89  add     rsp, 70h
0x180033c8d  pop     rdi
0x180033c8e  pop     rsi
0x180033c8f  pop     rbp
0x180033c90  retn
```
