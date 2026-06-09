# CMSDiscMasterObj::Open(void)

- ea: `0x18000ce60`
- end: `0x18000d4c1`
- name: `?Open@CMSDiscMasterObj@@UEAAJXZ`
- size: `1633`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x180002ac4`
- `0x180004714`
- `0x180004784`
- `0x180007bac`
- `0x180007bd4`
- `0x180007d40`
- `0x180007d80`
- `0x18000b4b0`
- `0x18000c4a8`
- `0x18000c598`
- `0x18000c69c`
- `0x18000ce60`
- `0x18000e168`
- `0x1800184ce`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x18000d3c3`
- `ole32!CreateStreamOnHGlobal` at `0x18000d3c3`
- `ole32!CoCreateInstance` at `0x18000cfba`
- `ole32!CoCreateInstance` at `0x18000d0b7`
- `ole32!CoCreateInstance` at `0x18000d2ca`
- `ole32!CoCreateInstance` at `0x18000cfba`
- `ole32!CoCreateInstance` at `0x18000d0b7`
- `ole32!CoCreateInstance` at `0x18000d2ca`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d0ff`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d174`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d1d4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d256`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d31e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d0ff`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d174`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d1d4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d256`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d31e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d16a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d1b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d1ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d22b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d24d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d315`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d16a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d1b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d1ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d22b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d24d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d315`
- `KERNEL32!GlobalFree` at `0x18000d3d2`
- `KERNEL32!GlobalFree` at `0x18000d3d2`
- `KERNEL32!GlobalAlloc` at `0x18000d36c`
- `KERNEL32!GlobalAlloc` at `0x18000d36c`
- `KERNEL32!GetDateFormatW` at `0x18000d08c`
- `KERNEL32!GetDateFormatW` at `0x18000d14d`
- `KERNEL32!GetDateFormatW` at `0x18000d08c`
- `KERNEL32!GetDateFormatW` at `0x18000d14d`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000d02d`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000d02d`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::Open(CMSDiscMasterObj *this)
{
  int v2; // ebx
  CMSDiscMasterObj *v3; // rcx
  _QWORD *v4; // rcx
  HRESULT Instance; // eax
  WCHAR *v7; // rdx
  BSTR v8; // rax
  int DateFormatW; // eax
  OLECHAR *v10; // rdx
  BSTR v11; // rax
  int v12; // eax
  WCHAR *v13; // rcx
  BSTR v14; // rax
  WCHAR *v15; // rcx
  BSTR v16; // rax
  int v17; // ecx
  _QWORD *v18; // r14
  __int64 v19; // rcx
  HRESULT v20; // eax
  BSTR v21; // rax
  HGLOBAL v22; // rax
  void *v23; // rsi
  __int64 v24; // rdx
  LPSTREAM ppstm; // [rsp+30h] [rbp-79h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-71h] BYREF
  _QWORD v27[2]; // [rsp+40h] [rbp-69h] BYREF
  WCHAR DateStr[64]; // [rsp+50h] [rbp-59h] BYREF

  ppstm = 0;
  v27[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids, this);
  v2 = CMSDiscMasterObj::IsCallLegal(this, 2);
  if ( v2 < 0 )
    goto LABEL_9;
  CMSDiscMasterObj::InitializeSafeMembers(this);
  if ( !CMSDiscMasterObj::InitializeOnce(v3) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_10;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
LABEL_9:
    v4 = WPP_GLOBAL_Control;
LABEL_10:
    if ( !*((_BYTE *)this + 353) )
    {
      CMSDiscMasterObj::ReleaseAllResourcesFromOpen(this);
      CMSDiscMasterObj::InitializeSafeMembers(this);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 1) != 0 )
      WPP_SF_qD(v4[7], 19, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids, this, v2);
    goto LABEL_15;
  }
  Instance = CoCreateInstance(
               &GUID_2735412e_7f64_5b0f_8f00_5d77afbe261e,
               0,
               0x17u,
               &GUID_27354130_7f64_5b0f_8f00_5d77afbe261e,
               (LPVOID *)this + 57);
  v2 = Instance;
  if ( Instance < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_10;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      15,
      &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
      (unsigned int)Instance);
    goto LABEL_9;
  }
  if ( *((_DWORD *)this + 29) != -16843010 )
    ATL::AtlThrowImpl(-2147467259);
  ATL::AtlAdvise(
    *((struct IUnknown **)this + 57),
    (struct IUnknown *)this + 9,
    &IID_DDiscMaster2Events,
    (unsigned int *)this + 29);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 15, 0x80000000) )
  {
    v2 = -2147024882;
    goto LABEL_9;
  }
  *((_BYTE *)this + 596) = 1;
  ppv = 0;
  *((_BYTE *)this + 448) = 1;
  memset_0(DateStr, 0, sizeof(DateStr));
  if ( !GetDateFormatW(0x400u, 0x40u, 0, L"MMM dd yyyy", DateStr, 63) )
  {
    v10 = (OLECHAR *)*((_QWORD *)this + 55);
    if ( &word_18001BDF8 == v10 )
      goto LABEL_45;
    SysFreeString(*((BSTR *)this + 55));
    v15 = (WCHAR *)&word_18001BDF8;
    goto LABEL_44;
  }
  if ( CoCreateInstance(
         &GUID_2c941fc5_975b_59be_a960_9a2a262853a5,
         0,
         0x17u,
         &GUID_2c941fe1_975b_59be_a960_9a2a262853a5,
         &ppv) >= 0 )
  {
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 232LL))(ppv, 3);
    v7 = (WCHAR *)*((_QWORD *)this + 55);
    if ( DateStr != v7 )
    {
      SysFreeString(*((BSTR *)this + 55));
      v8 = SysAllocString(DateStr);
      *((_QWORD *)this + 55) = v8;
      v7 = v8;
      if ( !v8 )
        goto LABEL_76;
    }
    if ( (*(unsigned int (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 120LL))(ppv, v7) == -1062555388 )
    {
      DateFormatW = GetDateFormatW(0x400u, 0x41u, 0, 0, DateStr, 63);
      v10 = (OLECHAR *)*((_QWORD *)this + 55);
      if ( !DateFormatW )
        goto LABEL_32;
      if ( DateStr != v10 )
      {
        SysFreeString(*((BSTR *)this + 55));
        v11 = SysAllocString(DateStr);
        *((_QWORD *)this + 55) = v11;
        v10 = v11;
        if ( !v11 )
          goto LABEL_76;
      }
      v12 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 120LL))(ppv, v10);
      v10 = (OLECHAR *)*((_QWORD *)this + 55);
      if ( v12 == -1062555388 )
      {
LABEL_32:
        if ( &word_18001BDF8 != v10 )
        {
          SysFreeString(v10);
          v13 = (WCHAR *)&word_18001BDF8;
          goto LABEL_36;
        }
        goto LABEL_37;
      }
    }
    else
    {
      v10 = (OLECHAR *)*((_QWORD *)this + 55);
    }
    if ( DateStr != v10 )
    {
      SysFreeString(v10);
      v13 = DateStr;
LABEL_36:
      v14 = SysAllocString(v13);
      *((_QWORD *)this + 55) = v14;
      v10 = v14;
      if ( !v14 )
        goto LABEL_76;
    }
LABEL_37:
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 16LL))(ppv, v10);
      v10 = (OLECHAR *)*((_QWORD *)this + 55);
      ppv = 0;
    }
    goto LABEL_45;
  }
  v10 = (OLECHAR *)*((_QWORD *)this + 55);
  if ( DateStr != v10 )
  {
    SysFreeString(*((BSTR *)this + 55));
    v15 = DateStr;
LABEL_44:
    v16 = SysAllocString(v15);
    *((_QWORD *)this + 55) = v16;
    v10 = v16;
    if ( !v16 )
      goto LABEL_76;
  }
LABEL_45:
  v17 = 0;
  while ( 1 )
  {
    if ( !v10[v17] )
      goto LABEL_49;
    if ( v10[v17] > 0xFFu )
      break;
    if ( ++v17 >= 64 )
      goto LABEL_49;
  }
  if ( &word_18001BDF8 != v10 )
  {
    SysFreeString(v10);
    v21 = SysAllocString(&word_18001BDF8);
    *((_QWORD *)this + 55) = v21;
    if ( !v21 )
LABEL_76:
      ATL::AtlThrowImpl(-2147024882);
  }
LABEL_49:
  v18 = (_QWORD *)((char *)this + 496);
  v19 = *((_QWORD *)this + 62);
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    *v18 = 0;
  }
  v20 = CoCreateInstance(
          &GUID_2c941fce_975b_59be_a960_9a2a262853a5,
          0,
          0x17u,
          &GUID_2c941fd4_975b_59be_a960_9a2a262853a5,
          (LPVOID *)this + 62);
  v2 = v20;
  if ( v20 >= 0 )
  {
    _bstr_t::operator=(v27, &word_18001BDF8);
    (*(void (__fastcall **)(_QWORD, LPSTREAM *))(*(_QWORD *)*v18 + 56LL))(*v18, &ppstm);
    if ( !ppstm )
    {
      v22 = GlobalAlloc(0x2062u, 0x800u);
      v23 = v22;
      if ( v22 )
      {
        v2 = CreateStreamOnHGlobal(v22, 1, &ppstm);
        if ( v2 )
        {
          GlobalFree(v23);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              18,
              &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
              (unsigned int)v2);
        }
        else
        {
          (*(void (__fastcall **)(LPSTREAM, _QWORD))(*(_QWORD *)ppstm + 48LL))(ppstm, 0);
          v2 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
        }
        (*(void (__fastcall **)(_QWORD, LPSTREAM))(*(_QWORD *)*v18 + 120LL))(*v18, ppstm);
      }
      else
      {
        v2 = -2147024882;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            17,
            &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
            2147942414LL);
      }
    }
    if ( v27[0] )
      v24 = *(_QWORD *)v27[0];
    else
      v24 = 0;
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v18 + 72LL))(*v18, v24);
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v18 + 88LL))(*v18, 0);
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v18 + 104LL))(*v18, 0);
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    *((_BYTE *)this + 353) = 1;
    goto LABEL_9;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      16,
      &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
      (unsigned int)v20);
LABEL_15:
  _bstr_t::~_bstr_t((_bstr_t *)v27);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000ce60  mov     [rsp-8+arg_8], rbx
0x18000ce65  mov     [rsp-8+arg_10], rsi
0x18000ce6a  push    rbp
0x18000ce6b  push    rdi
0x18000ce6c  push    r13
0x18000ce6e  push    r14
0x18000ce70  push    r15
0x18000ce72  lea     rbp, [rsp-37h]
0x18000ce77  sub     rsp, 0E0h
0x18000ce7e  mov     rax, cs:__security_cookie
0x18000ce85  xor     rax, rsp
0x18000ce88  mov     [rbp+57h+var_30], rax
0x18000ce8c  xor     r15d, r15d
0x18000ce8f  mov     rdi, rcx
0x18000ce92  mov     [rbp+57h+ppstm], r15
0x18000ce96  mov     [rbp+57h+var_C0], r15
0x18000ce9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cea1  lea     r13, WPP_GLOBAL_Control
0x18000cea8  cmp     rcx, r13
0x18000ceab  jz      short loc_18000CECA
0x18000cead  test    byte ptr [rcx+44h], 1
0x18000ceb1  jz      short loc_18000CECA
0x18000ceb3  mov     rcx, [rcx+38h]
0x18000ceb7  lea     edx, [r15+0Dh]
0x18000cebb  mov     r9, rdi
0x18000cebe  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000cec5  call    WPP_SF_q
0x18000ceca  mov     edx, 2; unsigned int
0x18000cecf  mov     rcx, rdi; this
0x18000ced2  call    ?IsCallLegal@CMSDiscMasterObj@@AEAAJK@Z; CMSDiscMasterObj::IsCallLegal(ulong)
0x18000ced7  mov     ebx, eax
0x18000ced9  test    eax, eax
0x18000cedb  js      short loc_18000CF19
0x18000cedd  mov     rcx, rdi; this
0x18000cee0  call    ?InitializeSafeMembers@CMSDiscMasterObj@@AEAAXXZ; CMSDiscMasterObj::InitializeSafeMembers(void)
0x18000cee5  call    ?InitializeOnce@CMSDiscMasterObj@@AEAAEXZ; CMSDiscMasterObj::InitializeOnce(void)
0x18000ceea  test    al, al
0x18000ceec  jnz     loc_18000CF9A
0x18000cef2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cef9  cmp     rcx, r13
0x18000cefc  jz      short loc_18000CF20
0x18000cefe  test    byte ptr [rcx+44h], 1
0x18000cf02  jz      short loc_18000CF20
0x18000cf04  mov     rcx, [rcx+38h]
0x18000cf08  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000cf0f  mov     edx, 0Eh
0x18000cf14  call    WPP_SF_
0x18000cf19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf20  cmp     [rdi+161h], r15b
0x18000cf27  jnz     short loc_18000CF40
0x18000cf29  mov     rcx, rdi; this
0x18000cf2c  call    ?ReleaseAllResourcesFromOpen@CMSDiscMasterObj@@AEAAXXZ; CMSDiscMasterObj::ReleaseAllResourcesFromOpen(void)
0x18000cf31  mov     rcx, rdi; this
0x18000cf34  call    ?InitializeSafeMembers@CMSDiscMasterObj@@AEAAXXZ; CMSDiscMasterObj::InitializeSafeMembers(void)
0x18000cf39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf40  cmp     rcx, r13
0x18000cf43  jz      short loc_18000CF67
0x18000cf45  test    byte ptr [rcx+44h], 1
0x18000cf49  jz      short loc_18000CF67
0x18000cf4b  mov     rcx, [rcx+38h]
0x18000cf4f  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000cf56  mov     edx, 13h
0x18000cf5b  mov     dword ptr [rsp+100h+ppv], ebx
0x18000cf5f  mov     r9, rdi
0x18000cf62  call    WPP_SF_qD
0x18000cf67  lea     rcx, [rbp+57h+var_C0]; this
0x18000cf6b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000cf70  mov     eax, ebx
0x18000cf72  mov     rcx, [rbp+57h+var_30]
0x18000cf76  xor     rcx, rsp; StackCookie
0x18000cf79  call    __security_check_cookie
0x18000cf7e  lea     r11, [rsp+100h+var_20]
0x18000cf86  mov     rbx, [r11+38h]
0x18000cf8a  mov     rsi, [r11+40h]
0x18000cf8e  mov     rsp, r11
0x18000cf91  pop     r15
0x18000cf93  pop     r14
0x18000cf95  pop     r13
0x18000cf97  pop     rdi
0x18000cf98  pop     rbp
0x18000cf99  retn
0x18000cf9a  xor     edx, edx; pUnkOuter
0x18000cf9c  lea     rsi, [rdi+1C8h]
0x18000cfa3  lea     r9, _GUID_27354130_7f64_5b0f_8f00_5d77afbe261e; riid
0x18000cfaa  mov     [rsp+100h+ppv], rsi; ppv
0x18000cfaf  lea     rcx, _GUID_2735412e_7f64_5b0f_8f00_5d77afbe261e; rclsid
0x18000cfb6  lea     r8d, [rdx+17h]; dwClsContext
0x18000cfba  call    cs:__imp_CoCreateInstance
0x18000cfc0  mov     ebx, eax
0x18000cfc2  test    eax, eax
0x18000cfc4  jns     short loc_18000CFFD
0x18000cfc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfcd  cmp     rcx, r13
0x18000cfd0  jz      loc_18000CF20
0x18000cfd6  test    byte ptr [rcx+44h], 1
0x18000cfda  jz      loc_18000CF20
0x18000cfe0  mov     rcx, [rcx+38h]
0x18000cfe4  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000cfeb  mov     edx, 0Fh
0x18000cff0  mov     r9d, eax
0x18000cff3  call    WPP_SF_d
0x18000cff8  jmp     loc_18000CF19
0x18000cffd  lea     rdx, [rdi+48h]; struct IUnknown *
0x18000d001  lea     r9, [rdx+2Ch]; unsigned int *
0x18000d005  cmp     dword ptr [r9], 0FEFEFEFEh
0x18000d00c  jnz     loc_18000D4AB
0x18000d012  mov     rcx, [rsi]; struct IUnknown *
0x18000d015  lea     r8, IID_DDiscMaster2Events; struct _GUID *
0x18000d01c  call    ?AtlAdvise@ATL@@YAJPEAUIUnknown@@0AEBU_GUID@@PEAK@Z; ATL::AtlAdvise(IUnknown *,IUnknown *,_GUID const &,ulong *)
0x18000d021  lea     rcx, [rdi+258h]; lpCriticalSection
0x18000d028  mov     edx, 80000000h; dwSpinCount
0x18000d02d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d033  test    eax, eax
0x18000d035  jnz     short loc_18000D041
0x18000d037  mov     ebx, 8007000Eh
0x18000d03c  jmp     loc_18000CF19
0x18000d041  xor     edx, edx; Val
0x18000d043  mov     byte ptr [rdi+254h], 1
0x18000d04a  mov     r8d, 80h; Size
0x18000d050  mov     [rbp+57h+var_C8], r15
0x18000d054  lea     rcx, [rbp+57h+DateStr]; void *
0x18000d058  mov     byte ptr [rdi+1C0h], 1
0x18000d05f  call    memset_0
0x18000d064  mov     ebx, 3Fh ; '?'
0x18000d069  lea     rax, [rbp+57h+DateStr]
0x18000d06d  mov     r14d, 400h
0x18000d073  mov     [rsp+100h+cchDate], ebx; cchDate
0x18000d077  lea     r9, Format; "MMM dd yyyy"
0x18000d07e  mov     [rsp+100h+ppv], rax; lpDateStr
0x18000d083  xor     r8d, r8d; lpDate
0x18000d086  mov     ecx, r14d; Locale
0x18000d089  lea     edx, [rbx+1]; dwFlags
0x18000d08c  call    cs:__imp_GetDateFormatW
0x18000d092  test    eax, eax
0x18000d094  jz      loc_18000D237
0x18000d09a  lea     rax, [rbp+57h+var_C8]
0x18000d09e  xor     edx, edx; pUnkOuter
0x18000d0a0  lea     r9, _GUID_2c941fe1_975b_59be_a960_9a2a262853a5; riid
0x18000d0a7  mov     [rsp+100h+ppv], rax; ppv
0x18000d0ac  lea     r8d, [rbx-28h]; dwClsContext
0x18000d0b0  lea     rcx, _GUID_2c941fc5_975b_59be_a960_9a2a262853a5; rclsid
0x18000d0b7  call    cs:__imp_CoCreateInstance
0x18000d0bd  lea     rsi, word_18001BDF8
0x18000d0c4  test    eax, eax
0x18000d0c6  js      loc_18000D218
0x18000d0cc  mov     rcx, [rbp+57h+var_C8]
0x18000d0d0  lea     edx, [rbx-3Ch]
0x18000d0d3  mov     rax, [rcx]
0x18000d0d6  mov     rax, [rax+0E8h]
0x18000d0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0e2  mov     rdx, [rdi+1B8h]
0x18000d0e9  lea     rax, [rbp+57h+DateStr]
0x18000d0ed  cmp     rax, rdx
0x18000d0f0  jz      short loc_18000D118
0x18000d0f2  mov     rcx, rdx; bstrString
0x18000d0f5  call    cs:__imp_SysFreeString
0x18000d0fb  lea     rcx, [rbp+57h+DateStr]; psz
0x18000d0ff  call    cs:__imp_SysAllocString
0x18000d105  mov     [rdi+1B8h], rax
0x18000d10c  mov     rdx, rax
0x18000d10f  test    rax, rax
0x18000d112  jz      loc_18000D4B6
0x18000d118  mov     rcx, [rbp+57h+var_C8]
0x18000d11c  mov     rax, [rcx]
0x18000d11f  mov     rax, [rax+78h]
0x18000d123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d128  cmp     eax, 0C0AAB104h
0x18000d12d  lea     rax, [rbp+57h+DateStr]
0x18000d131  jnz     loc_18000D20F
0x18000d137  xor     r9d, r9d; lpFormat
0x18000d13a  mov     [rsp+100h+cchDate], ebx; cchDate
0x18000d13e  xor     r8d, r8d; lpDate
0x18000d141  mov     [rsp+100h+ppv], rax; lpDateStr
0x18000d146  mov     ecx, r14d; Locale
0x18000d149  lea     edx, [r9+41h]; dwFlags
0x18000d14d  call    cs:__imp_GetDateFormatW
0x18000d153  mov     rdx, [rdi+1B8h]
0x18000d15a  test    eax, eax
0x18000d15c  jz      short loc_18000D1AB
0x18000d15e  lea     rax, [rbp+57h+DateStr]
0x18000d162  cmp     rax, rdx
0x18000d165  jz      short loc_18000D18D
0x18000d167  mov     rcx, rdx; bstrString
0x18000d16a  call    cs:__imp_SysFreeString
0x18000d170  lea     rcx, [rbp+57h+DateStr]; psz
0x18000d174  call    cs:__imp_SysAllocString
0x18000d17a  mov     [rdi+1B8h], rax
0x18000d181  mov     rdx, rax
0x18000d184  test    rax, rax
0x18000d187  jz      loc_18000D4B6
0x18000d18d  mov     rcx, [rbp+57h+var_C8]
0x18000d191  mov     rax, [rcx]
0x18000d194  mov     rax, [rax+78h]
0x18000d198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d19d  mov     rdx, [rdi+1B8h]
0x18000d1a4  cmp     eax, 0C0AAB104h
0x18000d1a9  jnz     short loc_18000D1BE
0x18000d1ab  cmp     rsi, rdx
0x18000d1ae  jz      short loc_18000D1ED
0x18000d1b0  mov     rcx, rdx; bstrString
0x18000d1b3  call    cs:__imp_SysFreeString
0x18000d1b9  mov     rcx, rsi
0x18000d1bc  jmp     short loc_18000D1D4
0x18000d1be  lea     rax, [rbp+57h+DateStr]
0x18000d1c2  cmp     rax, rdx
0x18000d1c5  jz      short loc_18000D1ED
0x18000d1c7  mov     rcx, rdx; bstrString
0x18000d1ca  call    cs:__imp_SysFreeString
0x18000d1d0  lea     rcx, [rbp+57h+DateStr]; psz
0x18000d1d4  call    cs:__imp_SysAllocString
0x18000d1da  mov     [rdi+1B8h], rax
0x18000d1e1  mov     rdx, rax
0x18000d1e4  test    rax, rax
0x18000d1e7  jz      loc_18000D4B6
0x18000d1ed  mov     rcx, [rbp+57h+var_C8]
0x18000d1f1  test    rcx, rcx
0x18000d1f4  jz      short loc_18000D26F
0x18000d1f6  mov     rax, [rcx]
0x18000d1f9  mov     rax, [rax+10h]
0x18000d1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d202  mov     rdx, [rdi+1B8h]
0x18000d209  mov     [rbp+57h+var_C8], r15
0x18000d20d  jmp     short loc_18000D26F
0x18000d20f  mov     rdx, [rdi+1B8h]
0x18000d216  jmp     short loc_18000D1C2
0x18000d218  mov     rdx, [rdi+1B8h]
0x18000d21f  lea     rax, [rbp+57h+DateStr]
0x18000d223  cmp     rax, rdx
0x18000d226  jz      short loc_18000D26F
0x18000d228  mov     rcx, rdx; bstrString
0x18000d22b  call    cs:__imp_SysFreeString
0x18000d231  lea     rcx, [rbp+57h+DateStr]
0x18000d235  jmp     short loc_18000D256
0x18000d237  mov     rdx, [rdi+1B8h]
0x18000d23e  lea     rsi, word_18001BDF8
0x18000d245  cmp     rsi, rdx
0x18000d248  jz      short loc_18000D26F
0x18000d24a  mov     rcx, rdx; bstrString
0x18000d24d  call    cs:__imp_SysFreeString
0x18000d253  mov     rcx, rsi; psz
0x18000d256  call    cs:__imp_SysAllocString
0x18000d25c  mov     [rdi+1B8h], rax
0x18000d263  mov     rdx, rax
0x18000d266  test    rax, rax
0x18000d269  jz      loc_18000D4B6
0x18000d26f  mov     ecx, r15d
0x18000d272  mov     eax, ecx
0x18000d274  cmp     [rdx+rax*2], r15w
0x18000d279  jz      short loc_18000D293
0x18000d27b  mov     r8d, 0FFh
0x18000d281  cmp     [rdx+rax*2], r8w
0x18000d286  ja      loc_18000D30D
0x18000d28c  inc     ecx
0x18000d28e  cmp     ecx, 40h ; '@'
0x18000d291  jl      short loc_18000D272
0x18000d293  lea     r14, [rdi+1F0h]
0x18000d29a  mov     rcx, [r14]
0x18000d29d  test    rcx, rcx
0x18000d2a0  jz      short loc_18000D2B1
0x18000d2a2  mov     rax, [rcx]
0x18000d2a5  mov     rax, [rax+10h]
0x18000d2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2ae  mov     [r14], r15
0x18000d2b1  xor     edx, edx; pUnkOuter
0x18000d2b3  mov     [rsp+100h+ppv], r14; ppv
0x18000d2b8  lea     r9, _GUID_2c941fd4_975b_59be_a960_9a2a262853a5; riid
0x18000d2bf  lea     rcx, _GUID_2c941fce_975b_59be_a960_9a2a262853a5; rclsid
0x18000d2c6  lea     r8d, [rdx+17h]; dwClsContext
0x18000d2ca  call    cs:__imp_CoCreateInstance
0x18000d2d0  mov     ebx, eax
0x18000d2d2  test    eax, eax
0x18000d2d4  jns     short loc_18000D339
0x18000d2d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2dd  cmp     rcx, r13
0x18000d2e0  jz      loc_18000CF67
0x18000d2e6  test    byte ptr [rcx+44h], 1
0x18000d2ea  jz      loc_18000CF67
0x18000d2f0  mov     rcx, [rcx+38h]
0x18000d2f4  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000d2fb  mov     edx, 10h
0x18000d300  mov     r9d, eax
0x18000d303  call    WPP_SF_d
0x18000d308  jmp     loc_18000CF67
0x18000d30d  cmp     rsi, rdx
0x18000d310  jz      short loc_18000D293
0x18000d312  mov     rcx, rdx; bstrString
0x18000d315  call    cs:__imp_SysFreeString
0x18000d31b  mov     rcx, rsi; psz
0x18000d31e  call    cs:__imp_SysAllocString
0x18000d324  mov     [rdi+1B8h], rax
0x18000d32b  test    rax, rax
0x18000d32e  jz      loc_18000D4B6
0x18000d334  jmp     loc_18000D293
0x18000d339  mov     rdx, rsi
0x18000d33c  lea     rcx, [rbp+57h+var_C0]
0x18000d340  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18000d345  mov     rcx, [r14]
0x18000d348  lea     rdx, [rbp+57h+ppstm]
0x18000d34c  mov     rax, [rcx]
0x18000d34f  mov     rax, [rax+38h]
  ... truncated ...
```
