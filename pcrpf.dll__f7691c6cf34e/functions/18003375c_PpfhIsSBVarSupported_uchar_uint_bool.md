# PpfhIsSBVarSupported(uchar *,uint,bool *)

- ea: `0x18003375c`
- end: `0x18003391d`
- name: `?PpfhIsSBVarSupported@@YAJPEAEIPEA_N@Z`
- size: `449`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180040350`
- `0x18004b710`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x18003375c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800338bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033903`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800338bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033903`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033872`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033872`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003381c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003381c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PpfhIsSBVarSupported(unsigned __int8 *a1, int a2, bool *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int ValueW; // eax
  __int64 v7; // rdx
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  HKEY hKey[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int pvData; // [rsp+78h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+30h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+38h] BYREF

  *a3 = 0;
  if ( a2 == 4 )
  {
    if ( *(_DWORD *)a1 == 4915280 )
    {
      *a3 = 1;
      return 0;
    }
    if ( *(_DWORD *)a1 != 6422628 )
      return 0;
  }
  else if ( a2 != 6
         || (*(_DWORD *)a1 != 4522059 || *((_WORD *)a1 + 2) != 75)
         && (*(_DWORD *)a1 != 6422628 || *((_WORD *)a1 + 2) != 120) )
  {
    return 0;
  }
  hKey[0] = 0;
  v4 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)hKey);
  v5 = v4;
  if ( v4 >= 0 )
  {
    hkey = 0;
    ValueW = RegOpenKeyExW(hKey[0], L"Control\\PCRPF", 0, 0x20019u, &hkey);
    if ( ValueW )
    {
      v7 = 1041;
      goto LABEL_24;
    }
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"AllowAllSBVars", 0x20000018u, 0, &pvData, &pcbData);
    if ( ValueW != 2 )
    {
      if ( ValueW )
      {
        v7 = 1052;
LABEL_24:
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v7,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
               (const char *)ValueW,
               phkResulta);
        if ( hkey )
          RegCloseKey(hkey);
        goto LABEL_26;
      }
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        0x41Au,
        "PpfhIsSBVarSupported",
        "AllowAllSBVars test override set: %u",
        pvData);
    }
    *a3 = pvData == 1;
    if ( hkey )
      RegCloseKey(hkey);
    PpfSystemCcsKey::~PpfSystemCcsKey(hKey);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x40F,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
    (const char *)(unsigned int)v4,
    phkResult);
LABEL_26:
  PpfSystemCcsKey::~PpfSystemCcsKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18003375c  push    rbp
0x18003375e  push    rbx
0x18003375f  push    rdi
0x180033760  mov     rbp, rsp
0x180033763  sub     rsp, 50h
0x180033767  mov     rdi, r8
0x18003376a  mov     byte ptr [r8], 0
0x18003376e  mov     eax, 620064h
0x180033773  cmp     edx, 4
0x180033776  jnz     short loc_1800337DD
0x180033778  cmp     dword ptr [rcx], 4B0050h
0x18003377e  jnz     short loc_180033789
0x180033780  mov     byte ptr [r8], 1
0x180033784  jmp     loc_1800338D5
0x180033789  cmp     [rcx], eax
0x18003378b  jz      short loc_1800337A9
0x18003378d  cmp     edx, 6
0x180033790  jnz     loc_1800338D5
0x180033796  cmp     [rcx], eax
0x180033798  jnz     loc_1800338D5
0x18003379e  cmp     word ptr [rcx+4], 78h ; 'x'
0x1800337a3  jnz     loc_1800338D5
0x1800337a9  mov     [rbp+hKey], 0
0x1800337b1  lea     rcx, [rbp+hKey]; this
0x1800337b5  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x1800337ba  mov     ebx, eax
0x1800337bc  test    eax, eax
0x1800337be  jns     short loc_1800337F7
0x1800337c0  mov     rcx, [rbp+18h]; this
0x1800337c4  mov     r9d, eax; char *
0x1800337c7  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800337ce  mov     edx, 40Fh; void *
0x1800337d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800337d8  jmp     loc_180033910
0x1800337dd  cmp     edx, 6
0x1800337e0  jnz     loc_1800338D5
0x1800337e6  cmp     dword ptr [rcx], 45004Bh
0x1800337ec  jnz     short loc_180033796
0x1800337ee  cmp     word ptr [rcx+4], 4Bh ; 'K'
0x1800337f3  jz      short loc_1800337A9
0x1800337f5  jmp     short loc_180033796
0x1800337f7  mov     [rbp+hkey], 0
0x1800337ff  lea     rax, [rbp+hkey]
0x180033803  mov     [rsp+50h+phkResult], rax; phkResult
0x180033808  mov     r9d, 20019h; samDesired
0x18003380e  xor     r8d, r8d; ulOptions
0x180033811  lea     rdx, aControlPcrpf; "Control\\PCRPF"
0x180033818  mov     rcx, [rbp+hKey]; hKey
0x18003381c  call    cs:__imp_RegOpenKeyExW
0x180033823  nop     dword ptr [rax+rax+00h]
0x180033828  test    eax, eax
0x18003382a  jz      short loc_180033836
0x18003382c  mov     edx, 411h
0x180033831  jmp     loc_1800338E5
0x180033836  mov     [rbp+arg_8], 0
0x18003383d  mov     [rbp+arg_10], 4
0x180033844  lea     rax, [rbp+arg_10]
0x180033848  mov     [rsp+50h+pcbData], rax; pcbData
0x18003384d  lea     rax, [rbp+arg_8]
0x180033851  mov     [rsp+50h+pvData], rax; pvData
0x180033856  mov     [rsp+50h+phkResult], 0; unsigned int
0x18003385f  mov     r9d, 20000018h; dwFlags
0x180033865  lea     r8, aAllowallsbvars; "AllowAllSBVars"
0x18003386c  xor     edx, edx; lpSubKey
0x18003386e  mov     rcx, [rbp+hkey]; hkey
0x180033872  call    cs:__imp_RegGetValueW
0x180033879  nop     dword ptr [rax+rax+00h]
0x18003387e  cmp     eax, 2
0x180033881  jz      short loc_1800338AD
0x180033883  test    eax, eax
0x180033885  jnz     short loc_1800338E0
0x180033887  mov     eax, [rbp+arg_8]
0x18003388a  mov     dword ptr [rsp+50h+phkResult], eax
0x18003388e  lea     r9, aAllowallsbvars_0; "AllowAllSBVars test override set: %u"
0x180033895  lea     r8, aPpfhissbvarsup; "PpfhIsSBVarSupported"
0x18003389c  mov     edx, 41Ah; unsigned int
0x1800338a1  lea     rcx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800338a8  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800338ad  cmp     [rbp+arg_8], 1
0x1800338b1  setz    al
0x1800338b4  mov     [rdi], al
0x1800338b6  mov     rcx, [rbp+hkey]; hKey
0x1800338ba  test    rcx, rcx
0x1800338bd  jz      short loc_1800338CC
0x1800338bf  call    cs:__imp_RegCloseKey
0x1800338c6  nop     dword ptr [rax+rax+00h]
0x1800338cb  nop
0x1800338cc  lea     rcx, [rbp+hKey]; this
0x1800338d0  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x1800338d5  xor     eax, eax
0x1800338d7  add     rsp, 50h
0x1800338db  pop     rdi
0x1800338dc  pop     rbx
0x1800338dd  pop     rbp
0x1800338de  retn
0x1800338e0  mov     edx, 41Ch; void *
0x1800338e5  mov     r9d, eax; char *
0x1800338e8  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800338ef  mov     rcx, [rbp+18h]; this
0x1800338f3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800338f8  mov     ebx, eax
0x1800338fa  mov     rcx, [rbp+hkey]; hKey
0x1800338fe  test    rcx, rcx
0x180033901  jz      short loc_180033910
0x180033903  call    cs:__imp_RegCloseKey
0x18003390a  nop     dword ptr [rax+rax+00h]
0x18003390f  nop
0x180033910  lea     rcx, [rbp+hKey]; this
0x180033914  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180033919  mov     eax, ebx
0x18003391b  jmp     short loc_1800338D7
```
