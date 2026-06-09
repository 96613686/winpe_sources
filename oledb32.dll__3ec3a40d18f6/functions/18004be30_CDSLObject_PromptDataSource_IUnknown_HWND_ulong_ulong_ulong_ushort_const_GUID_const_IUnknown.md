# CDSLObject::PromptDataSource(IUnknown *,HWND__ *,ulong,ulong,ulong *,ushort const *,_GUID const &,IUnknown * *)

- ea: `0x18004be30`
- end: `0x18004c721`
- name: `?PromptDataSource@CDSLObject@@UEAAJPEAUIUnknown@@PEAUHWND__@@KKPEAKPEBGAEBU_GUID@@PEAPEAU2@@Z`
- size: `2289`
- prototype: `__int64 __usercall@<rax>(CDSLObject *__hidden this@<rcx>, struct IUnknown *@<rdx>, HWND@<r8>, unsigned int@<r9d>, unsigned int, unsigned int *, const unsigned __int16 *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013870`
- `0x180029c30`
- `0x18003c270`
- `0x18004af94`
- `0x18004b548`
- `0x18004b650`
- `0x18004baa0`
- `0x18004be30`
- `0x18004d950`
- `0x18004db90`
- `0x180055d3c`
- `0x180059100`
- `0x18005989c`
- `0x18007e6be`
- `0x18007e6ca`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18004c086`
- `KERNEL32!EnterCriticalSection` at `0x18004c086`
- `KERNEL32!LeaveCriticalSection` at `0x18004c0cb`
- `KERNEL32!LeaveCriticalSection` at `0x18004c0cb`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004bf0f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004bf0f`
- `USER32!SetCursor` at `0x18004bfca`
- `USER32!SetCursor` at `0x18004c6f6`
- `USER32!SetCursor` at `0x18004bfca`
- `USER32!SetCursor` at `0x18004c6f6`
- `USER32!LoadStringW` at `0x18004c391`
- `USER32!LoadStringW` at `0x18004c391`
- `ole32!CoTaskMemAlloc` at `0x18004c407`
- `ole32!CoTaskMemAlloc` at `0x18004c407`
- `ole32!CoTaskMemFree` at `0x18004c3f4`
- `ole32!CoTaskMemFree` at `0x18004c3f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDSLObject::PromptDataSource(
        CDSLObject *this,
        struct IUnknown *a2,
        struct _PSP **a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned __int16 *a7,
        struct _GUID *a8,
        struct IUnknown **a9)
{
  unsigned int BidID; // eax
  unsigned int v13; // edx
  int PropertyPages; // ebx
  bool v16; // zf
  const struct _GUID *v17; // rdx
  CDSLObject *v18; // rcx
  unsigned int v19; // r8d
  int v20; // ecx
  __int64 i; // rcx
  unsigned __int16 *v22; // r13
  HINSTANCE v23; // rbx
  bool v24; // bl
  void *v25; // rcx
  LPVOID v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  unsigned int v29; // r8d
  __int64 v30; // r9
  unsigned int v31; // r10d
  unsigned int j; // ecx
  __int64 v33; // rax
  struct IUnknown *v34; // rbx
  struct IUnknown *v35; // rcx
  int v36; // eax
  int v37; // eax
  __int64 v38; // rax
  struct IUnknown *v39; // rdi
  int v40; // eax
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v43; // [rsp+30h] [rbp-D0h]
  unsigned int v44[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  struct _PSP **v46; // [rsp+70h] [rbp-90h] BYREF
  void *Buf1; // [rsp+78h] [rbp-88h]
  HCURSOR hCursor; // [rsp+80h] [rbp-80h] BYREF
  char v49; // [rsp+88h] [rbp-78h]
  struct IUnknown *v50; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v51; // [rsp+98h] [rbp-68h]
  struct IUnknown *v52; // [rsp+A0h] [rbp-60h]
  int v53; // [rsp+B0h] [rbp-50h] BYREF
  int v54; // [rsp+B4h] [rbp-4Ch] BYREF
  struct _PSP **v55; // [rsp+B8h] [rbp-48h]
  HINSTANCE v56; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  WCHAR *p_Buffer; // [rsp+D0h] [rbp-30h]
  unsigned int v59; // [rsp+D8h] [rbp-28h]
  int v60; // [rsp+E0h] [rbp-20h]
  __int64 v61; // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v62)(HWND, unsigned int, __int64); // [rsp+F0h] [rbp-10h]
  WCHAR Buffer; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v64[1022]; // [rsp+112h] [rbp+12h] BYREF

  v46 = a3;
  v50 = a2;
  v51 = a7;
  Buf1 = a8;
  v45 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1800C9568[0] )
  {
    BidID = CDSLObject::GetBidID(this);
    LODWORD(v43) = a5;
    bidScopeEnterW(&v45, off_1800C9568[0], BidID, a2, (_DWORD)v46, a5);
  }
  DSLUtils::WaitCursor::WaitCursor((DSLUtils::WaitCursor *)&hCursor, 1);
  SetErrorInfo(0, 0);
  if ( !a9 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024809, L"<CDSLObject::PromptDataSource|OLEDB|ERR> ", 0x2BCu);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C9240[0] )
          bidTraceW(off_1800C83C8[0], 717824, off_1800C9240[0], 2147942487LL, 0, v42, v43);
      }
    }
    if ( (bidGblFlags & 4) != 0 && v45 != -1 && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v45);
    DSLUtils::SetErrorInfo(
      (DSLUtils *)0x32,
      v13,
      (unsigned int)&IID_IDBPromptInitialize,
      (const struct _GUID *)0x80070057LL,
      v41);
    if ( v49 )
      SetCursor(hCursor);
    return 2147942487LL;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 270, -1, 0) )
  {
    PropertyPages = -2147418113;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147418113, L"<CDSLObject::PromptDataSource|OLEDB|ERR> ", 0x2C5u);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C9238[0] )
          bidTraceW(off_1800C83C8[0], 727040, off_1800C9238[0], 2147549183LL, (_DWORD)a9, v42, v43);
      }
    }
    if ( (bidGblFlags & 4) != 0 && v45 != -1 && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v45);
    v16 = v49 == 0;
    goto LABEL_121;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( a2 )
  {
    if ( *a9 )
    {
      PropertyPages = -2147217886;
      if ( (bidGblFlags & 2) != 0 )
      {
        v19 = 725;
        goto LABEL_30;
      }
      goto LABEL_32;
    }
    if ( memcmp_0(Buf1, &IID_IUnknown, 0x10u) )
    {
      PropertyPages = -2147217886;
      if ( (bidGblFlags & 2) != 0 )
      {
        v19 = 732;
        goto LABEL_30;
      }
      goto LABEL_32;
    }
  }
  if ( !a4 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(-2147024809, L"<CDSLObject::PromptDataSource|OLEDB|ERR> ", 0x2EDu);
    PropertyPages = -2147024809;
    goto LABEL_32;
  }
  if ( (a4 & 0xFFFFFE8C) != 0 )
  {
    PropertyPages = -2147024809;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_32;
    v19 = 764;
LABEL_47:
    v20 = -2147024809;
    goto LABEL_31;
  }
  if ( (a4 & 0x10) != 0 && !*a9 )
  {
    DSLUtils::SetErrorInfo(
      (DSLUtils *)0x33,
      (unsigned int)v17,
      (unsigned int)&IID_IDBPromptInitialize,
      (const struct _GUID *)0x80070057LL,
      v41);
    PropertyPages = -2147024809;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_32;
    v19 = 772;
    goto LABEL_47;
  }
  if ( (a4 & 3) == 0 )
  {
    DSLUtils::SetErrorInfo(
      (DSLUtils *)0x34,
      (unsigned int)v17,
      (unsigned int)&IID_IDBPromptInitialize,
      (const struct _GUID *)0x80070057LL,
      v41);
    PropertyPages = -2147024809;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_32;
    v19 = 781;
    goto LABEL_47;
  }
  if ( a5 && !a6 )
  {
    DSLUtils::SetErrorInfo(
      (DSLUtils *)0x35,
      (unsigned int)v17,
      (unsigned int)&IID_IDBPromptInitialize,
      (const struct _GUID *)0x80070057LL,
      v41);
    PropertyPages = -2147024809;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_32;
    v19 = 789;
    goto LABEL_47;
  }
  *((_BYTE *)this + 1010) = (a4 & 0x20) == 0;
  if ( (a4 & 0x20) == 0 && (a4 & 0x40) != 0 )
  {
    if ( (unsigned int)CDSLObject::GetRegEntryForPassword(v18) )
      *((_BYTE *)this + 1010) = 0;
    else
      *((_BYTE *)this + 1011) = (a4 & 0x40) != 0;
  }
  *((_BYTE *)this + 1012) = BYTE1(a4) & 1;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a5 )
    {
      v52 = *a9;
      v22 = v51;
      PropertyPages = CDSLObject::PrePropertySheet(this, v17, a9, a4, a5, a6, v51, v50);
      if ( PropertyPages < 0 )
        goto LABEL_72;
      v53 = 96;
      memset_0(&v54, 0, 0x5Cu);
      v54 = 900;
      v55 = v46;
      v23 = hInstance;
      v56 = hInstance;
      v57 = 202;
      Buffer = 0;
      memset_0(v64, 0, sizeof(v64));
      LoadStringW(v23, 0x5Fu, &Buffer, 512);
      p_Buffer = &Buffer;
      v46 = 0;
      v44[0] = 0;
      PropertyPages = CDSLProviderInformation::GetPropertyPages(
                        (LPVOID *)(*((_QWORD *)this + 14) + 104LL * *((int *)this + 30)),
                        this,
                        &v46,
                        v44);
      if ( PropertyPages < 0 )
        goto LABEL_72;
      v24 = *((_DWORD *)this + 31) >= 0;
      v25 = (void *)*((_QWORD *)this + 32);
      if ( v25 )
        CoTaskMemFree(v25);
      v26 = CoTaskMemAlloc(8LL * (v44[0] + !v24));
      *((_QWORD *)this + 32) = v26;
      if ( !v26 )
      {
        PropertyPages = -2147024882;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_32;
        v29 = 890;
LABEL_78:
        OLEDBTraceErr(PropertyPages, L"<CDSLObject::PromptDataSource|OLEDB|ERR> ", v29);
        goto LABEL_32;
      }
      v30 = 0;
      if ( !v24 )
      {
        **((_QWORD **)this + 32) = IsolationAwareCreatePropertySheetPageW((char *)this + 136);
        if ( !**((_QWORD **)this + 32) )
        {
          CDSLObject::CleanUpProviderInformations(this);
          PropertyPages = -2147418113;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_32;
          v29 = 900;
          goto LABEL_78;
        }
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 6) + 8LL))((char *)this + 48);
        v30 = 1;
      }
      v31 = 0;
      for ( j = v44[0]; v31 < v44[0]; j = v44[0] )
      {
        v28 = (int)v30;
        v27 = *((_QWORD *)this + 32);
        *(_QWORD *)(v27 + 8LL * (int)v30) = v46[v31++];
        v30 = (unsigned int)(v30 + 1);
      }
      v61 = *((_QWORD *)this + 32);
      v59 = j;
      v60 = 0;
      if ( !v24 )
      {
        v59 = ++j;
        if ( *a9 )
          goto LABEL_92;
        if ( v22 )
        {
          v33 = -1;
          do
            ++v33;
          while ( v22[v33] );
          if ( !v22[v33 + 1] )
LABEL_92:
            v60 = 1;
        }
      }
      *((_DWORD *)this + 66) = j;
      v62 = CDSLObject::PropertySheetCallback;
      if ( (int)IsolationAwarePropertySheetW(&v53, v27, v28, v30) <= 0 )
      {
        PropertyPages = -2147217842;
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(-2147217842, L"<CDSLObject::PromptDataSource|OLEDB|ERR> ", 0x3AFu);
      }
      else
      {
        v34 = v50;
        if ( v50 )
        {
          v35 = *a9;
          if ( *a9 )
          {
            *(_QWORD *)v44 = 0;
            v36 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, unsigned int *))v35->lpVtbl->QueryInterface)(
                    v35,
                    &IID_IOuterUnknown,
                    v44);
            if ( v36 >= 0 )
            {
              CDSLObject::CleanUpProviderInformations(this);
              v37 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *))(**(_QWORD **)v44 + 40LL))(
                      *(_QWORD *)v44,
                      v34);
              PropertyPages = v37;
              if ( (bidGblFlags & 2) != 0 )
                OLEDBTraceErr(v37, L"<CDSLObject::PromptDataSource|OLEDB|ERR> ", 0x3D3u);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 16LL))(*(_QWORD *)v44);
              if ( *(_QWORD *)v44 )
                v38 = *(_QWORD *)v44 - 8LL;
              else
                v38 = 0;
              *(_BYTE *)(v38 + 176) = 1;
            }
            else
            {
              if ( (bidGblFlags & 2) != 0 )
                OLEDBTraceErr(v36, L"<CDSLObject::PromptDataSource|OLEDB|ERR> ", 0x3BFu);
              CDSLObject::CleanUpProviderInformations(this);
              PropertyPages = -2147418113;
            }
            goto LABEL_32;
          }
        }
        PropertyPages = 0;
        v39 = *a9;
        if ( *a9 )
        {
          v40 = ((__int64 (__fastcall *)(_QWORD, void *, struct IUnknown **))v39->lpVtbl->QueryInterface)(*a9, Buf1, a9);
          if ( v40 < 0 )
          {
            PropertyPages = v40;
            if ( (bidGblFlags & 2) != 0 )
              OLEDBTraceErr(v40, L"<CDSLObject::PromptDataSource|OLEDB|ERR> ", 0x3F4u);
            *a9 = v52;
          }
          else
          {
            ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
          }
        }
      }
LABEL_72:
      CDSLObject::CleanUpProviderInformations(this);
      goto LABEL_32;
    }
    if ( a6[i] == 2 )
      break;
  }
  PropertyPages = -2147217804;
  DSLUtils::SetErrorInfo(
    (DSLUtils *)0x36,
    (unsigned int)v17,
    (unsigned int)&IID_IDBPromptInitialize,
    (const struct _GUID *)0x80040E74LL,
    v41);
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_32;
  v19 = 837;
LABEL_30:
  v20 = PropertyPages;
LABEL_31:
  OLEDBTraceErr(v20, L"<CDSLObject::PromptDataSource|OLEDB|ERR> ", v19);
LABEL_32:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  _InterlockedExchange((volatile __int32 *)this + 270, 0);
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(PropertyPages, L"<CDSLObject::PromptDataSource|OLEDB|ERR> ", 0x411u);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( PropertyPages < 0 )
      {
        if ( off_1800C9228[0] )
          bidTraceW(off_1800C83C8[0], 1067008, off_1800C9228[0], (unsigned int)PropertyPages, (_DWORD)a9, v42, v43);
      }
      else if ( off_1800C9230[0] )
      {
        bidTraceW(off_1800C83C8[0], 1067008, off_1800C9230[0], (unsigned int)PropertyPages, (unsigned int)*a9, v42, v43);
      }
      if ( (bidGblFlags & 4) != 0 && v45 != -1 && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v45);
    }
  }
  v16 = v49 == 0;
LABEL_121:
  if ( !v16 )
    SetCursor(hCursor);
  return (unsigned int)PropertyPages;
}

```

## disassembly

```asm
0x18004be30  push    rbp
0x18004be32  push    rbx
0x18004be33  push    rsi
0x18004be34  push    rdi
0x18004be35  push    r12
0x18004be37  push    r13
0x18004be39  push    r14
0x18004be3b  push    r15
0x18004be3d  lea     rbp, [rsp-428h]
0x18004be45  sub     rsp, 528h
0x18004be4c  mov     rax, cs:__security_cookie
0x18004be53  xor     rax, rsp
0x18004be56  mov     [rbp+460h+var_50], rax
0x18004be5d  mov     ebx, r9d
0x18004be60  mov     [rsp+560h+var_4F0], r8
0x18004be65  mov     r13, rdx
0x18004be68  mov     [rbp+460h+var_4D0], rdx
0x18004be6c  mov     rsi, rcx
0x18004be6f  mov     r12, [rbp+460h+arg_28]
0x18004be76  mov     r14, [rbp+460h+arg_30]
0x18004be7d  mov     [rbp+460h+var_4C8], r14
0x18004be81  mov     rax, [rbp+460h+arg_38]
0x18004be88  mov     [rsp+560h+Buf1], rax
0x18004be8d  mov     r15, [rbp+460h+arg_40]
0x18004be94  mov     [rsp+560h+var_4F8], 0FFFFFFFFFFFFFFFFh
0x18004be9d  mov     edi, [rbp+460h+arg_20]
0x18004bea3  test    byte ptr cs:_bidGblFlags, 4
0x18004beaa  jz      short loc_18004BEFF
0x18004beac  mov     rax, cs:off_1800C9568; "<IDBPromptInitialize::PromptDataSource|"...
0x18004beb3  test    rax, rax
0x18004beb6  jz      short loc_18004BEFF
0x18004beb8  call    ?GetBidID@CDSLObject@@QEAAHXZ; CDSLObject::GetBidID(void)
0x18004bebd  mov     rdx, cs:off_1800C9568; "<IDBPromptInitialize::PromptDataSource|"...
0x18004bec4  mov     [rsp+560h+var_510], r15
0x18004bec9  mov     rcx, [rsp+560h+Buf1]
0x18004bece  mov     [rsp+560h+var_518], rcx
0x18004bed3  mov     [rsp+560h+var_520], r14
0x18004bed8  mov     [rsp+560h+var_528], r12
0x18004bedd  mov     dword ptr [rsp+560h+var_530], edi
0x18004bee1  mov     dword ptr [rsp+560h+var_538], edi
0x18004bee5  mov     rcx, [rsp+560h+var_4F0]
0x18004beea  mov     qword ptr [rsp+560h+var_540], rcx; int
0x18004beef  mov     r9, r13
0x18004bef2  mov     r8d, eax
0x18004bef5  lea     rcx, [rsp+560h+var_4F8]
0x18004befa  call    _bidScopeEnterW
0x18004beff  mov     dl, 1; bool
0x18004bf01  lea     rcx, [rbp+460h+hCursor]; this
0x18004bf05  call    ??0WaitCursor@DSLUtils@@QEAA@_N@Z; DSLUtils::WaitCursor::WaitCursor(bool)
0x18004bf0a  nop
0x18004bf0b  xor     edx, edx; perrinfo
0x18004bf0d  xor     ecx, ecx; dwReserved
0x18004bf0f  call    cs:__imp_SetErrorInfo
0x18004bf15  test    r15, r15
0x18004bf18  jnz     loc_18004BFD7
0x18004bf1e  mov     edi, 80070057h
0x18004bf23  test    byte ptr cs:_bidGblFlags, 2
0x18004bf2a  jz      short loc_18004BF75
0x18004bf2c  mov     r8d, 2BCh; unsigned int
0x18004bf32  lea     rdx, aCdslobjectProm_3; "<CDSLObject::PromptDataSource|OLEDB|ERR"...
0x18004bf39  mov     ecx, edi; int
0x18004bf3b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004bf40  test    byte ptr cs:_bidGblFlags, 2
0x18004bf47  jz      short loc_18004BF75
0x18004bf49  mov     rax, cs:off_1800C9240; "<IDBPromptInitialize::PromptDataSource|"...
0x18004bf50  test    rax, rax
0x18004bf53  jz      short loc_18004BF75
0x18004bf55  mov     qword ptr [rsp+560h+var_540], r15; int
0x18004bf5a  mov     r9d, edi
0x18004bf5d  mov     r8, cs:off_1800C9240; "<IDBPromptInitialize::PromptDataSource|"...
0x18004bf64  mov     edx, 0AF400h
0x18004bf69  mov     rcx, cs:off_1800C83C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004bf70  call    _bidTraceW
0x18004bf75  test    byte ptr cs:_bidGblFlags, 4
0x18004bf7c  jz      short loc_18004BFAB
0x18004bf7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004bf82  cmp     [rsp+560h+var_4F8], rax
0x18004bf87  jz      short loc_18004BFAB
0x18004bf89  mov     rcx, cs:_bidID
0x18004bf90  cmp     rcx, rax
0x18004bf93  jz      short loc_18004BFAB
0x18004bf95  lea     r9, [rsp+560h+var_4F8]
0x18004bf9a  xor     r8d, r8d
0x18004bf9d  xor     edx, edx
0x18004bf9f  mov     rax, cs:off_1800BC0E8
0x18004bfa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfab  mov     r9d, edi; struct _GUID *
0x18004bfae  lea     r8, IID_IDBPromptInitialize; unsigned int
0x18004bfb5  mov     ecx, 32h ; '2'; this
0x18004bfba  call    ?SetErrorInfo@DSLUtils@@YAXIIAEBU_GUID@@J@Z; DSLUtils::SetErrorInfo(uint,uint,_GUID const &,long)
0x18004bfbf  nop
0x18004bfc0  cmp     [rbp+460h+var_4D8], 0
0x18004bfc4  jz      short loc_18004BFD0
0x18004bfc6  mov     rcx, [rbp+460h+hCursor]; hCursor
0x18004bfca  call    cs:__imp_SetCursor
0x18004bfd0  mov     eax, edi
0x18004bfd2  jmp     loc_18004C6FE
0x18004bfd7  xor     eax, eax
0x18004bfd9  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004bfdd  lock cmpxchg [rsi+438h], r14d
0x18004bfe6  jz      loc_18004C082
0x18004bfec  mov     ebx, 8000FFFFh
0x18004bff1  test    byte ptr cs:_bidGblFlags, 2
0x18004bff8  jz      short loc_18004C046
0x18004bffa  mov     r8d, 2C5h; unsigned int
0x18004c000  lea     rdx, aCdslobjectProm_3; "<CDSLObject::PromptDataSource|OLEDB|ERR"...
0x18004c007  mov     ecx, ebx; int
0x18004c009  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004c00e  or      r14, r14
0x18004c011  test    byte ptr cs:_bidGblFlags, 2
0x18004c018  jz      short loc_18004C046
0x18004c01a  mov     rax, cs:off_1800C9238; "<IDBPromptInitialize::PromptDataSource|"...
0x18004c021  test    rax, rax
0x18004c024  jz      short loc_18004C046
0x18004c026  mov     qword ptr [rsp+560h+var_540], r15
0x18004c02b  mov     r9d, ebx
0x18004c02e  mov     r8, cs:off_1800C9238; "<IDBPromptInitialize::PromptDataSource|"...
0x18004c035  mov     edx, 0B1800h
0x18004c03a  mov     rcx, cs:off_1800C83C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004c041  call    _bidTraceW
0x18004c046  test    byte ptr cs:_bidGblFlags, 4
0x18004c04d  jz      short loc_18004C079
0x18004c04f  cmp     [rsp+560h+var_4F8], r14
0x18004c054  jz      short loc_18004C079
0x18004c056  mov     rcx, cs:_bidID
0x18004c05d  cmp     rcx, r14
0x18004c060  jz      short loc_18004C079
0x18004c062  lea     r9, [rsp+560h+var_4F8]
0x18004c067  xor     r8d, r8d
0x18004c06a  xor     edx, edx
0x18004c06c  mov     rax, cs:off_1800BC0E8
0x18004c073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c078  nop
0x18004c079  cmp     [rbp+460h+var_4D8], 0
0x18004c07d  jmp     loc_18004C6F0
0x18004c082  lea     rcx, [rsi+40h]; lpCriticalSection
0x18004c086  call    cs:__imp_EnterCriticalSection
0x18004c08c  lea     r14, aCdslobjectProm_3; "<CDSLObject::PromptDataSource|OLEDB|ERR"...
0x18004c093  test    r13, r13
0x18004c096  jz      loc_18004C16C
0x18004c09c  cmp     qword ptr [r15], 0
0x18004c0a0  jz      loc_18004C134
0x18004c0a6  mov     ebx, 80040E22h
0x18004c0ab  test    byte ptr cs:_bidGblFlags, 2
0x18004c0b2  jz      short loc_18004C0C4
0x18004c0b4  mov     r8d, 2D5h; unsigned int
0x18004c0ba  mov     ecx, ebx; int
0x18004c0bc  mov     rdx, r14; unsigned __int16 *
0x18004c0bf  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004c0c4  xor     r12d, r12d
0x18004c0c7  lea     rcx, [rsi+40h]; lpCriticalSection
0x18004c0cb  call    cs:__imp_LeaveCriticalSection
0x18004c0d1  mov     eax, r12d
0x18004c0d4  xchg    eax, [rsi+438h]
0x18004c0da  mov     ecx, cs:_bidGblFlags
0x18004c0e0  test    cl, 2
0x18004c0e3  jz      loc_18004C6EC
0x18004c0e9  mov     r8d, 411h; unsigned int
0x18004c0ef  mov     rdx, r14; unsigned __int16 *
0x18004c0f2  mov     ecx, ebx; int
0x18004c0f4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004c0f9  mov     ecx, cs:_bidGblFlags
0x18004c0ff  test    cl, 2
0x18004c102  jz      loc_18004C6EC
0x18004c108  test    ebx, ebx
0x18004c10a  js      loc_18004C689
0x18004c110  mov     rax, cs:off_1800C9230; "<IDBPromptInitialize::PromptDataSource|"...
0x18004c117  test    rax, rax
0x18004c11a  jz      loc_18004C6B5
0x18004c120  mov     rax, [r15]
0x18004c123  mov     qword ptr [rsp+560h+var_540], rax
0x18004c128  mov     r8, cs:off_1800C9230; "<IDBPromptInitialize::PromptDataSource|"...
0x18004c12f  jmp     loc_18004C6A1
0x18004c134  mov     r8d, 10h; Size
0x18004c13a  lea     rdx, IID_IUnknown; Buf2
0x18004c141  mov     rcx, [rsp+560h+Buf1]; Buf1
0x18004c146  call    memcmp_0
0x18004c14b  test    eax, eax
0x18004c14d  jz      short loc_18004C16C
0x18004c14f  mov     ebx, 80040E22h
0x18004c154  test    byte ptr cs:_bidGblFlags, 2
0x18004c15b  jz      loc_18004C0C4
0x18004c161  mov     r8d, 2DCh
0x18004c167  jmp     loc_18004C0BA
0x18004c16c  test    ebx, ebx
0x18004c16e  jnz     short loc_18004C195
0x18004c170  mov     edi, 80070057h
0x18004c175  test    byte ptr cs:_bidGblFlags, 2
0x18004c17c  jz      short loc_18004C18E
0x18004c17e  mov     r8d, 2EDh; unsigned int
0x18004c184  mov     rdx, r14; unsigned __int16 *
0x18004c187  mov     ecx, edi; int
0x18004c189  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004c18e  mov     ebx, edi
0x18004c190  jmp     loc_18004C0C4
0x18004c195  test    ebx, 0FFFFFE8Ch
0x18004c19b  jz      short loc_18004C1BE
0x18004c19d  mov     edi, 80070057h
0x18004c1a2  mov     ebx, edi
0x18004c1a4  test    byte ptr cs:_bidGblFlags, 2
0x18004c1ab  jz      loc_18004C0C4
0x18004c1b1  mov     r8d, 2FCh
0x18004c1b7  mov     ecx, edi
0x18004c1b9  jmp     loc_18004C0BC
0x18004c1be  test    bl, 10h
0x18004c1c1  jz      short loc_18004C1F9
0x18004c1c3  cmp     qword ptr [r15], 0
0x18004c1c7  jnz     short loc_18004C1F9
0x18004c1c9  mov     edi, 80070057h
0x18004c1ce  mov     r9d, edi; struct _GUID *
0x18004c1d1  lea     r8, IID_IDBPromptInitialize; unsigned int
0x18004c1d8  mov     ecx, 33h ; '3'; this
0x18004c1dd  call    ?SetErrorInfo@DSLUtils@@YAXIIAEBU_GUID@@J@Z; DSLUtils::SetErrorInfo(uint,uint,_GUID const &,long)
0x18004c1e2  mov     ebx, edi
0x18004c1e4  test    byte ptr cs:_bidGblFlags, 2
0x18004c1eb  jz      loc_18004C0C4
0x18004c1f1  mov     r8d, 304h
0x18004c1f7  jmp     short loc_18004C1B7
0x18004c1f9  test    bl, 3
0x18004c1fc  jnz     short loc_18004C22E
0x18004c1fe  mov     edi, 80070057h
0x18004c203  mov     r9d, edi; struct _GUID *
0x18004c206  lea     r8, IID_IDBPromptInitialize; unsigned int
0x18004c20d  mov     ecx, 34h ; '4'; this
0x18004c212  call    ?SetErrorInfo@DSLUtils@@YAXIIAEBU_GUID@@J@Z; DSLUtils::SetErrorInfo(uint,uint,_GUID const &,long)
0x18004c217  mov     ebx, edi
0x18004c219  test    byte ptr cs:_bidGblFlags, 2
0x18004c220  jz      loc_18004C0C4
0x18004c226  mov     r8d, 30Dh
0x18004c22c  jmp     short loc_18004C1B7
0x18004c22e  test    edi, edi
0x18004c230  jz      short loc_18004C26A
0x18004c232  test    r12, r12
0x18004c235  jnz     short loc_18004C26A
0x18004c237  mov     edi, 80070057h
0x18004c23c  mov     r9d, edi; struct _GUID *
0x18004c23f  lea     r8, IID_IDBPromptInitialize; unsigned int
0x18004c246  lea     ecx, [r12+35h]; this
0x18004c24b  call    ?SetErrorInfo@DSLUtils@@YAXIIAEBU_GUID@@J@Z; DSLUtils::SetErrorInfo(uint,uint,_GUID const &,long)
0x18004c250  mov     ebx, edi
0x18004c252  test    byte ptr cs:_bidGblFlags, 2
0x18004c259  jz      loc_18004C0C4
0x18004c25f  mov     r8d, 315h
0x18004c265  jmp     loc_18004C1B7
0x18004c26a  bt      ebx, 5
0x18004c26e  setnb   al
0x18004c271  mov     [rsi+3F2h], al
0x18004c277  mov     eax, ebx
0x18004c279  and     eax, 40h
0x18004c27c  setnz   r13b
0x18004c280  bt      ebx, 5
0x18004c284  jb      short loc_18004C2A3
0x18004c286  test    eax, eax
0x18004c288  jz      short loc_18004C2A3
0x18004c28a  call    ?GetRegEntryForPassword@CDSLObject@@QEAAKXZ; CDSLObject::GetRegEntryForPassword(void)
0x18004c28f  test    eax, eax
0x18004c291  jz      short loc_18004C29C
0x18004c293  mov     byte ptr [rsi+3F2h], 0
0x18004c29a  jmp     short loc_18004C2A3
0x18004c29c  mov     [rsi+3F3h], r13b
0x18004c2a3  mov     eax, ebx
0x18004c2a5  shr     eax, 8
0x18004c2a8  and     al, 1
0x18004c2aa  mov     [rsi+3F4h], al
0x18004c2b0  xor     ecx, ecx
0x18004c2b2  cmp     ecx, edi
0x18004c2b4  jnb     short loc_18004C2F2
0x18004c2b6  cmp     dword ptr [r12+rcx*4], 2
0x18004c2bb  jz      short loc_18004C2C1
0x18004c2bd  inc     ecx
0x18004c2bf  jmp     short loc_18004C2B2
0x18004c2c1  mov     ebx, 80040E74h
0x18004c2c6  mov     r9d, ebx; struct _GUID *
0x18004c2c9  lea     r8, IID_IDBPromptInitialize; unsigned int
0x18004c2d0  mov     ecx, 36h ; '6'; this
0x18004c2d5  call    ?SetErrorInfo@DSLUtils@@YAXIIAEBU_GUID@@J@Z; DSLUtils::SetErrorInfo(uint,uint,_GUID const &,long)
0x18004c2da  test    byte ptr cs:_bidGblFlags, 2
0x18004c2e1  jz      loc_18004C0C4
0x18004c2e7  mov     r8d, 345h
0x18004c2ed  jmp     loc_18004C0BA
0x18004c2f2  mov     rax, [r15]
0x18004c2f5  mov     [rbp+460h+var_4C0], rax
0x18004c2f9  mov     rax, [rbp+460h+var_4D0]
0x18004c2fd  mov     [rsp+560h+var_528], rax; struct IUnknown *
0x18004c302  mov     r13, [rbp+460h+var_4C8]
0x18004c306  mov     [rsp+560h+var_530], r13; unsigned __int16 *
0x18004c30b  mov     [rsp+560h+var_538], r12; unsigned int *
0x18004c310  mov     [rsp+560h+var_540], edi; unsigned int
0x18004c314  mov     r9d, ebx; unsigned int
0x18004c317  mov     r8, r15; struct IUnknown **
0x18004c31a  mov     rcx, rsi; this
0x18004c31d  call    ?PrePropertySheet@CDSLObject@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@KKPEAKPEBGPEAU3@@Z; CDSLObject::PrePropertySheet(_GUID const &,IUnknown * *,ulong,ulong,ulong *,ushort const *,IUnknown *)
0x18004c322  mov     ebx, eax
0x18004c324  xor     r12d, r12d
0x18004c327  test    eax, eax
0x18004c329  js      loc_18004C3CD
0x18004c32f  mov     [rbp+460h+var_4B0], 60h ; '`'
0x18004c336  xor     edx, edx; Val
0x18004c338  lea     r8d, [r12+5Ch]; Size
0x18004c33d  lea     rcx, [rbp+460h+var_4AC]; void *
  ... truncated ...
```
