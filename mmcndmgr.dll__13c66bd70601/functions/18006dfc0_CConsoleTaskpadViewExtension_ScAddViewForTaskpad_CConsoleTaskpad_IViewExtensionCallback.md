# CConsoleTaskpadViewExtension::ScAddViewForTaskpad(CConsoleTaskpad *,IViewExtensionCallback *)

- ea: `0x18006dfc0`
- end: `0x18006e1f0`
- name: `?ScAddViewForTaskpad@CConsoleTaskpadViewExtension@@CA?AVSC@mmcerror@@PEAVCConsoleTaskpad@@PEAUIViewExtensionCallback@@@Z`
- size: `560`
- prototype: `OLECHAR *__fastcall(OLECHAR *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180053804`

## callees

- `0x180013dac`
- `0x18002a710`
- `0x18002e700`
- `0x18003a698`
- `0x18003bf5c`
- `0x180040d94`
- `0x18006dfc0`
- `0x18006ebe4`
- `0x180134540`
- `0x18013f010`

## import_xrefs

- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18006e155`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18006e155`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18006dff6`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18006e160`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18006dff6`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18006e160`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006e099`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006e14c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006e18a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006e099`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006e14c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006e18a`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18006e055`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18006e0b6`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18006e198`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18006e055`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18006e0b6`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18006e198`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18006e02d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18006e02d`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18006e009`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18006e009`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006e043`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006e0a4`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006e043`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006e0a4`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006e038`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006e1cd`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006e038`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006e1cd`
- `ole32!StringFromCLSID` at `0x18006e08c`
- `ole32!StringFromCLSID` at `0x18006e08c`

## string_xrefs

- `0x18006dffd`: `CConsoleTaskpadViewExtension::ScAddViewForTaskpad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
OLECHAR *__fastcall CConsoleTaskpadViewExtension::ScAddViewForTaskpad(OLECHAR *a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  unsigned int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rax
  mmcerror::SC *v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rdx
  LPOLESTR lpsz; // [rsp+20h] [rbp-89h] BYREF
  _BYTE v18[32]; // [rsp+28h] [rbp-81h] BYREF
  _BYTE v19[24]; // [rsp+48h] [rbp-61h] BYREF
  _OWORD v20[3]; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v21[4]; // [rsp+90h] [rbp-19h] BYREF
  _QWORD v22[4]; // [rsp+B0h] [rbp+7h] BYREF

  lpsz = a1;
  mmcerror::SC::SC((mmcerror::SC *)v18, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v18, L"CConsoleTaskpadViewExtension::ScAddViewForTaskpad");
  v6 = ScCheckPointers(v19, a2, a3, 2147942487LL);
  mmcerror::SC::operator=(v18, v6);
  mmcerror::SC::~SC((mmcerror::SC *)v19);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v18) )
  {
    memset(v20, 0, sizeof(v20));
    lpsz = 0;
    v7 = StringFromCLSID((const IID *const)(a2 + 212), &lpsz);
    mmcerror::SC::operator=(v18, v7);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v18) )
    {
      mmcerror::SC::SC((mmcerror::SC *)a1, (const struct mmcerror::SC *)v18);
LABEL_13:
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpsz);
      goto LABEL_14;
    }
    std::wstring::wstring(v21, L"--mmc:");
    v8 = std::char_traits<unsigned short>::length(lpsz);
    std::wstring::append(v21, v9, v8);
    v10 = v21;
    if ( v21[3] >= 8u )
      v10 = (_QWORD *)v21[0];
    *(_QWORD *)&v20[1] = v10;
    DWORD2(v20[2]) = *(_BYTE *)(a2 + 296) != 0;
    v20[0] = *(_OWORD *)(a2 + 212);
    CStringTableStringBase::str(a2 + 16, v22);
    if ( v22[3] < 8u )
    {
      *((_QWORD *)&v20[1] + 1) = v22;
    }
    else
    {
      *((_QWORD *)&v20[1] + 1) = v22[0];
      if ( !v22[0] )
      {
        v11 = (mmcerror::SC *)mmcerror::SC::operator=(v18, 2147942414LL);
        v12 = mmcerror::SC::ToHr(v11);
        mmcerror::SC::SC((mmcerror::SC *)a1, v12);
LABEL_12:
        LOBYTE(v13) = 1;
        std::wstring::_Tidy(v22, v13, 0);
        LOBYTE(v15) = 1;
        std::wstring::_Tidy(v21, v15, 0);
        goto LABEL_13;
      }
    }
    v14 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)a3 + 24LL))(a3, v20);
    mmcerror::SC::operator=(v18, v14);
    mmcerror::SC::SC((mmcerror::SC *)a1, (const struct mmcerror::SC *)v18);
    goto LABEL_12;
  }
  mmcerror::SC::SC((mmcerror::SC *)a1, (const struct mmcerror::SC *)v18);
LABEL_14:
  mmcerror::SC::~SC((mmcerror::SC *)v18);
  return a1;
}

```

## disassembly

```asm
0x18006dfc0  push    rbp
0x18006dfc2  push    rbx
0x18006dfc3  push    rsi
0x18006dfc4  push    rdi
0x18006dfc5  push    r14
0x18006dfc7  lea     rbp, [rsp-37h]
0x18006dfcc  sub     rsp, 0E0h
0x18006dfd3  mov     rax, cs:__security_cookie
0x18006dfda  xor     rax, rsp
0x18006dfdd  mov     [rbp+57h+var_30], rax
0x18006dfe1  mov     r14, r8
0x18006dfe4  mov     rsi, rdx
0x18006dfe7  mov     rbx, rcx
0x18006dfea  mov     [rsp+100h+lpsz], rcx
0x18006dfef  xor     edx, edx
0x18006dff1  lea     rcx, [rsp+100h+var_D8]
0x18006dff6  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18006dffc  nop
0x18006dffd  lea     rdx, aCconsoletaskpa_0; "CConsoleTaskpadViewExtension::ScAddView"...
0x18006e004  lea     rcx, [rsp+100h+var_D8]
0x18006e009  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18006e00f  mov     r9d, 80070057h
0x18006e015  mov     r8, r14
0x18006e018  mov     rdx, rsi
0x18006e01b  lea     rcx, [rbp+57h+var_B8]
0x18006e01f  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBX0J@Z; ScCheckPointers(void const *,void const *,long)
0x18006e024  nop
0x18006e025  mov     rdx, rax
0x18006e028  lea     rcx, [rsp+100h+var_D8]
0x18006e02d  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18006e033  nop
0x18006e034  lea     rcx, [rbp+57h+var_B8]
0x18006e038  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18006e03e  lea     rcx, [rsp+100h+var_D8]
0x18006e043  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18006e049  test    al, al
0x18006e04b  jz      short loc_18006E060
0x18006e04d  lea     rdx, [rsp+100h+var_D8]
0x18006e052  mov     rcx, rbx
0x18006e055  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x18006e05b  jmp     loc_18006E1C8
0x18006e060  mov     [rbp+57h+var_A0], 0
0x18006e067  xorps   xmm0, xmm0
0x18006e06a  xor     eax, eax
0x18006e06c  movups  [rbp+57h+var_9C], xmm0
0x18006e070  movups  [rbp+57h+var_8C], xmm0
0x18006e074  movups  [rbp+57h+var_8C+0Ch], xmm0
0x18006e078  mov     [rsp+100h+lpsz], rax
0x18006e07d  lea     rdi, [rsi+0D4h]
0x18006e084  lea     rdx, [rsp+100h+lpsz]; lplpsz
0x18006e089  mov     rcx, rdi; rclsid
0x18006e08c  call    cs:__imp_StringFromCLSID
0x18006e092  mov     edx, eax
0x18006e094  lea     rcx, [rsp+100h+var_D8]
0x18006e099  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006e09f  lea     rcx, [rsp+100h+var_D8]
0x18006e0a4  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18006e0aa  test    al, al
0x18006e0ac  jz      short loc_18006E0C1
0x18006e0ae  lea     rdx, [rsp+100h+var_D8]
0x18006e0b3  mov     rcx, rbx
0x18006e0b6  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x18006e0bc  jmp     loc_18006E1BD
0x18006e0c1  lea     rdx, aMmc_1; "--mmc:"
0x18006e0c8  lea     rcx, [rbp+57h+var_70]
0x18006e0cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18006e0d1  nop
0x18006e0d2  mov     rcx, [rsp+100h+lpsz]
0x18006e0d7  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18006e0dc  mov     r8, rax
0x18006e0df  mov     rdx, rcx
0x18006e0e2  lea     rcx, [rbp+57h+var_70]
0x18006e0e6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18006e0eb  lea     rax, [rbp+57h+var_70]
0x18006e0ef  cmp     [rbp+57h+var_58], 8
0x18006e0f4  cmovnb  rax, [rbp+57h+var_70]
0x18006e0f9  mov     qword ptr [rbp+57h+var_9C+0Ch], rax
0x18006e0fd  xor     eax, eax
0x18006e0ff  cmp     [rsi+128h], al
0x18006e105  setnz   al
0x18006e108  mov     [rbp+57h+var_78], eax
0x18006e10b  mov     eax, [rdi]
0x18006e10d  mov     [rbp+57h+var_A0], eax
0x18006e110  movsd   xmm0, qword ptr [rdi+4]
0x18006e115  movsd   qword ptr [rbp+57h+var_9C], xmm0
0x18006e11a  mov     eax, [rdi+0Ch]
0x18006e11d  mov     dword ptr [rbp+57h+var_9C+8], eax
0x18006e120  lea     rcx, [rsi+10h]
0x18006e124  lea     rdx, [rbp+57h+var_50]
0x18006e128  call    ?str@CStringTableStringBase@@QEBA?AVtstring@@XZ; CStringTableStringBase::str(void)
0x18006e12d  nop
0x18006e12e  cmp     [rbp+57h+var_38], 8
0x18006e133  jb      short loc_18006E168
0x18006e135  mov     rax, [rbp+57h+var_50]
0x18006e139  mov     qword ptr [rbp+57h+var_8C+4], rax
0x18006e13d  test    rax, rax
0x18006e140  jnz     short loc_18006E170
0x18006e142  mov     edx, 8007000Eh
0x18006e147  lea     rcx, [rsp+100h+var_D8]
0x18006e14c  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006e152  mov     rcx, rax
0x18006e155  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18006e15b  mov     edx, eax
0x18006e15d  mov     rcx, rbx
0x18006e160  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18006e166  jmp     short loc_18006E19F
0x18006e168  lea     rax, [rbp+57h+var_50]
0x18006e16c  mov     qword ptr [rbp+57h+var_8C+4], rax
0x18006e170  mov     rax, [r14]
0x18006e173  lea     rdx, [rbp+57h+var_A0]
0x18006e177  mov     rcx, r14
0x18006e17a  mov     rax, [rax+18h]
0x18006e17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e183  mov     edx, eax
0x18006e185  lea     rcx, [rsp+100h+var_D8]
0x18006e18a  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006e190  lea     rdx, [rsp+100h+var_D8]
0x18006e195  mov     rcx, rbx
0x18006e198  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x18006e19e  nop
0x18006e19f  xor     r8d, r8d
0x18006e1a2  mov     dl, 1
0x18006e1a4  lea     rcx, [rbp+57h+var_50]
0x18006e1a8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18006e1ad  nop
0x18006e1ae  xor     r8d, r8d
0x18006e1b1  mov     dl, 1
0x18006e1b3  lea     rcx, [rbp+57h+var_70]
0x18006e1b7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18006e1bc  nop
0x18006e1bd  lea     rcx, [rsp+100h+lpsz]
0x18006e1c2  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18006e1c7  nop
0x18006e1c8  lea     rcx, [rsp+100h+var_D8]
0x18006e1cd  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18006e1d3  mov     rax, rbx
0x18006e1d6  mov     rcx, [rbp+57h+var_30]
0x18006e1da  xor     rcx, rsp; StackCookie
0x18006e1dd  call    __security_check_cookie
0x18006e1e2  add     rsp, 0E0h
0x18006e1e9  pop     r14
0x18006e1eb  pop     rdi
0x18006e1ec  pop     rsi
0x18006e1ed  pop     rbx
0x18006e1ee  pop     rbp
0x18006e1ef  retn
```
