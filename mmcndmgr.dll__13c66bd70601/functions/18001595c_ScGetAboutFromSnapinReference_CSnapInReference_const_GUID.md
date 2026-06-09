# ScGetAboutFromSnapinReference(CSnapInReference const &,_GUID &)

- ea: `0x18001595c`
- end: `0x180015b92`
- name: `?ScGetAboutFromSnapinReference@@YA?AVSC@mmcerror@@AEBVCSnapInReference@@AEAU_GUID@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014fc8`
- `0x18005dfa4`
- `0x18006f070`
- `0x18006f360`
- `0x1800aa3e4`
- `0x1800ad1a0`

## callees

- `0x18001595c`
- `0x180026ac8`
- `0x180037cd4`
- `0x180044e84`
- `0x180134540`

## import_xrefs

- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180015998`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1800159bb`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180015998`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1800159bb`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180015a52`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180015af2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180015b14`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180015a52`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180015af2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180015b14`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180015a60`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180015acb`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180015b22`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180015b50`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180015a60`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180015acb`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180015b22`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180015b50`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800159aa`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800159ce`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800159aa`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800159ce`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180015ab8`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180015afd`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180015b3a`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180015ab8`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180015afd`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180015b3a`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180015ad6`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180015b2e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180015b5c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180015b67`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180015ad6`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180015b2e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180015b5c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180015b67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015a19`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015a19`
- `ole32!CLSIDFromString` at `0x180015ae5`
- `ole32!CLSIDFromString` at `0x180015ae5`

## string_xrefs

- `0x18001599f`: `ScGetAboutFromSnapinCLSID`
- `0x1800159c2`: `ScGetAboutFromSnapinCLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
mmcerror::SC *__fastcall ScGetAboutFromSnapinReference(mmcerror::SC *a1, __int64 a2, GUID *a3)
{
  const unsigned __int16 *v6; // rbx
  const struct mmcerror::SC *v7; // rax
  const struct mmcerror::SC *v8; // rdx
  unsigned int v9; // eax
  const struct mmcerror::SC *v10; // rax
  char v11; // al
  const struct mmcerror::SC *v12; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+34h] [rbp-CCh] BYREF
  int v16; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[24]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v21[24]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v22[32]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[104]; // [rsp+D0h] [rbp-30h] BYREF

  v17 = (HKEY)a1;
  mmcerror::SC::SC((mmcerror::SC *)v22, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v22, L"ScGetAboutFromSnapinCLSID");
  v6 = *(const unsigned __int16 **)(a2 + 24);
  mmcerror::SC::SC((mmcerror::SC *)v18, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v18, L"ScGetAboutFromSnapinCLSID");
  memset(v19, 0, sizeof(v19));
  v17 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MMC\\SnapIns", 0, 0x20019u, &v17) )
  {
    v10 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v18, 2147500037LL);
    mmcerror::SC::SC((mmcerror::SC *)v20, v10);
  }
  else
  {
    v19[0] = v17;
    if ( ATL::CRegKey::Open((ATL::CRegKey *)v19, v17, v6, 0x20019u, phkResult) )
    {
      v7 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v18, 2147500037LL);
      mmcerror::SC::SC((mmcerror::SC *)v20, v7);
    }
    else
    {
      v15 = 100;
      v16 = 1;
      CRegKeyEx::ScQueryValue(v19, v21, L"About", &v16, sz, &v15);
      if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
      {
        v8 = (const struct mmcerror::SC *)v21;
      }
      else
      {
        v9 = CLSIDFromString(sz, a3);
        mmcerror::SC::operator=(v18, v9);
        mmcerror::SC::operator bool(v18);
        v8 = (const struct mmcerror::SC *)v18;
      }
      mmcerror::SC::SC((mmcerror::SC *)v20, v8);
      mmcerror::SC::~SC((mmcerror::SC *)v21);
    }
    ATL::CRegKey::Close((ATL::CRegKey *)v19);
  }
  mmcerror::SC::~SC((mmcerror::SC *)v18);
  v11 = mmcerror::SC::operator bool(v20);
  v12 = (const struct mmcerror::SC *)v20;
  if ( !v11 )
    v12 = (const struct mmcerror::SC *)v22;
  mmcerror::SC::SC(a1, v12);
  mmcerror::SC::~SC((mmcerror::SC *)v20);
  mmcerror::SC::~SC((mmcerror::SC *)v22);
  return a1;
}

```

## disassembly

```asm
0x18001595c  mov     [rsp-8+arg_18], rbx
0x180015961  push    rbp
0x180015962  push    rsi
0x180015963  push    rdi
0x180015964  lea     rbp, [rsp-0B0h]
0x18001596c  sub     rsp, 1B0h
0x180015973  mov     rax, cs:__security_cookie
0x18001597a  xor     rax, rsp
0x18001597d  mov     [rbp+0C0h+var_20], rax
0x180015984  mov     rsi, r8
0x180015987  mov     rbx, rdx
0x18001598a  mov     rdi, rcx
0x18001598d  mov     [rsp+1C0h+var_180], rcx
0x180015992  xor     edx, edx
0x180015994  lea     rcx, [rbp+0C0h+var_110]
0x180015998  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18001599e  nop
0x18001599f  lea     rdx, aScgetaboutfrom; "ScGetAboutFromSnapinCLSID"
0x1800159a6  lea     rcx, [rbp+0C0h+var_110]
0x1800159aa  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1800159b0  mov     rbx, [rbx+18h]
0x1800159b4  xor     edx, edx
0x1800159b6  lea     rcx, [rsp+1C0h+var_178]
0x1800159bb  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1800159c1  nop
0x1800159c2  lea     rdx, aScgetaboutfrom; "ScGetAboutFromSnapinCLSID"
0x1800159c9  lea     rcx, [rsp+1C0h+var_178]
0x1800159ce  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1800159d4  mov     [rsp+1C0h+var_160], 0
0x1800159dd  mov     [rsp+1C0h+var_158], 0
0x1800159e6  mov     [rsp+1C0h+var_150], 0
0x1800159ef  mov     [rsp+1C0h+var_180], 0
0x1800159f8  lea     rax, [rsp+1C0h+var_180]
0x1800159fd  mov     [rsp+1C0h+phkResult], rax; unsigned int
0x180015a02  mov     r9d, 20019h; samDesired
0x180015a08  xor     r8d, r8d; ulOptions
0x180015a0b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\MMC\\SnapIns"
0x180015a12  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015a19  call    cs:__imp_RegOpenKeyExW
0x180015a1f  test    eax, eax
0x180015a21  jnz     loc_180015B0A
0x180015a27  mov     rdx, [rsp+1C0h+var_180]; HKEY
0x180015a2c  mov     [rsp+1C0h+var_160], rdx
0x180015a31  mov     r9d, 20019h; unsigned int
0x180015a37  mov     r8, rbx; unsigned __int16 *
0x180015a3a  lea     rcx, [rsp+1C0h+var_160]; this
0x180015a3f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x180015a44  test    eax, eax
0x180015a46  jz      short loc_180015A76
0x180015a48  mov     edx, 80004005h
0x180015a4d  lea     rcx, [rsp+1C0h+var_178]
0x180015a52  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180015a58  mov     rdx, rax
0x180015a5b  lea     rcx, [rsp+1C0h+var_148]
0x180015a60  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x180015a66  nop
0x180015a67  lea     rcx, [rsp+1C0h+var_160]; this
0x180015a6c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015a71  jmp     loc_180015B29
0x180015a76  mov     [rsp+1C0h+var_18C], 64h ; 'd'
0x180015a7e  mov     [rsp+1C0h+var_188], 1
0x180015a86  lea     rax, [rsp+1C0h+var_18C]
0x180015a8b  mov     [rsp+1C0h+var_198], rax
0x180015a90  lea     rax, [rbp+0C0h+sz]
0x180015a94  mov     [rsp+1C0h+phkResult], rax
0x180015a99  lea     r9, [rsp+1C0h+var_188]
0x180015a9e  lea     r8, aAbout; "About"
0x180015aa5  lea     rdx, [rbp+0C0h+var_128]
0x180015aa9  lea     rcx, [rsp+1C0h+var_160]
0x180015aae  call    ?ScQueryValue@CRegKeyEx@@QEAA?AVSC@mmcerror@@PEBGPEAKPEAX1@Z; CRegKeyEx::ScQueryValue(ushort const *,ulong *,void *,ulong *)
0x180015ab3  nop
0x180015ab4  lea     rcx, [rbp+0C0h+var_128]
0x180015ab8  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180015abe  test    al, al
0x180015ac0  jz      short loc_180015ADE
0x180015ac2  lea     rdx, [rbp+0C0h+var_128]
0x180015ac6  lea     rcx, [rsp+1C0h+var_148]
0x180015acb  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x180015ad1  nop
0x180015ad2  lea     rcx, [rbp+0C0h+var_128]
0x180015ad6  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180015adc  jmp     short loc_180015A67
0x180015ade  mov     rdx, rsi; pclsid
0x180015ae1  lea     rcx, [rbp+0C0h+sz]; lpsz
0x180015ae5  call    cs:__imp_CLSIDFromString
0x180015aeb  mov     edx, eax
0x180015aed  lea     rcx, [rsp+1C0h+var_178]
0x180015af2  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180015af8  lea     rcx, [rsp+1C0h+var_178]
0x180015afd  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180015b03  lea     rdx, [rsp+1C0h+var_178]
0x180015b08  jmp     short loc_180015AC6
0x180015b0a  mov     edx, 80004005h
0x180015b0f  lea     rcx, [rsp+1C0h+var_178]
0x180015b14  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180015b1a  mov     rdx, rax
0x180015b1d  lea     rcx, [rsp+1C0h+var_148]
0x180015b22  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x180015b28  nop
0x180015b29  lea     rcx, [rsp+1C0h+var_178]
0x180015b2e  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180015b34  nop
0x180015b35  lea     rcx, [rsp+1C0h+var_148]
0x180015b3a  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180015b40  mov     rcx, rdi
0x180015b43  test    al, al
0x180015b45  lea     rdx, [rsp+1C0h+var_148]
0x180015b4a  jnz     short loc_180015B50
0x180015b4c  lea     rdx, [rbp+0C0h+var_110]
0x180015b50  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x180015b56  nop
0x180015b57  lea     rcx, [rsp+1C0h+var_148]
0x180015b5c  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180015b62  nop
0x180015b63  lea     rcx, [rbp+0C0h+var_110]
0x180015b67  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180015b6d  mov     rax, rdi
0x180015b70  mov     rcx, [rbp+0C0h+var_20]
0x180015b77  xor     rcx, rsp; StackCookie
0x180015b7a  call    __security_check_cookie
0x180015b7f  mov     rbx, [rsp+1C0h+arg_18]
0x180015b87  add     rsp, 1B0h
0x180015b8e  pop     rdi
0x180015b8f  pop     rsi
0x180015b90  pop     rbp
0x180015b91  retn
```
