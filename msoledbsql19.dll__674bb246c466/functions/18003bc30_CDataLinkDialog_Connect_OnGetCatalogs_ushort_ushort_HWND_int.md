# CDataLinkDialog_Connect::OnGetCatalogs(ushort,ushort,HWND__ *,int &)

- ea: `0x18003bc30`
- end: `0x18003c2f3`
- name: `?OnGetCatalogs@CDataLinkDialog_Connect@@AEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `1731`
- prototype: `__int64 __fastcall(CDataLinkDialog_Connect *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18003d0c0`

## callees

- `0x180003030`
- `0x180003488`
- `0x180003d20`
- `0x180003d80`
- `0x180036300`
- `0x180038b90`
- `0x180038d90`
- `0x18003a020`
- `0x18003bc30`
- `0x1801a65e1`
- `0x1801ad6a0`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18003bcad`
- `ole32!CoInitializeEx` at `0x18003bcad`
- `ole32!CoUninitialize` at `0x18003c147`
- `ole32!CoUninitialize` at `0x18003c147`
- `ole32!CoTaskMemFree` at `0x18003c0e4`
- `ole32!CoTaskMemFree` at `0x18003c0f6`
- `ole32!CoTaskMemFree` at `0x18003c0e4`
- `ole32!CoTaskMemFree` at `0x18003c0f6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18003c06b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18003c06b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18003c077`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18003c077`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18003bd8e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18003bd8e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003c163`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003c163`
- `USER32!LoadCursorW` at `0x18003bcea`
- `USER32!LoadCursorW` at `0x18003bcea`
- `USER32!SetCursor` at `0x18003bcf3`
- `USER32!SetCursor` at `0x18003c16d`
- `USER32!SetCursor` at `0x18003bcf3`
- `USER32!SetCursor` at `0x18003c16d`
- `USER32!GetWindowTextLengthW` at `0x18003bd0b`
- `USER32!GetWindowTextLengthW` at `0x18003bd0b`
- `USER32!GetWindowTextW` at `0x18003bdcd`
- `USER32!GetWindowTextW` at `0x18003bdcd`
- `USER32!SetWindowTextW` at `0x18003be65`
- `USER32!SetWindowTextW` at `0x18003c0b0`
- `USER32!SetWindowTextW` at `0x18003be65`
- `USER32!SetWindowTextW` at `0x18003c0b0`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c032`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c032`
- `OLEAUT32!__imp_VariantClear` at `0x18003be72`
- `OLEAUT32!__imp_VariantClear` at `0x18003be72`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDataLinkDialog_Connect::OnGetCatalogs(
        CDataLinkDialog_Connect *this,
        __int64 a2,
        __int64 a3,
        HWND a4)
{
  HWND v4; // r15
  CDataLinkDialog *v5; // rdi
  __int64 v6; // rsi
  int *v7; // rbx
  HCURSOR CursorW; // rax
  HCURSOR v9; // r12
  unsigned __int64 WindowTextLengthW; // r13
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rax
  size_t v13; // r14
  size_t v14; // rdx
  __int64 v15; // rax
  void *v16; // rsp
  int *v17; // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned int i; // ecx
  int v23; // eax
  int CatalogData; // eax
  BSTR v25; // r14
  __int64 v26; // rdx
  __int64 v28; // [rsp+0h] [rbp-50h] BYREF
  int v29; // [rsp+50h] [rbp+0h] BYREF
  unsigned int v30; // [rsp+54h] [rbp+4h] BYREF
  CDataLinkDialog *v31; // [rsp+58h] [rbp+8h]
  struct IDBInitialize *v32; // [rsp+60h] [rbp+10h] BYREF
  unsigned int v33; // [rsp+68h] [rbp+18h]
  HCURSOR v34; // [rsp+70h] [rbp+20h]
  HWND v35; // [rsp+78h] [rbp+28h]
  int *v36; // [rsp+80h] [rbp+30h]
  __int64 pExceptionObject; // [rsp+88h] [rbp+38h] BYREF
  __int64 v38; // [rsp+90h] [rbp+40h] BYREF
  __int64 v39; // [rsp+98h] [rbp+48h] BYREF
  __int64 v40; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v41; // [rsp+A8h] [rbp+58h] BYREF
  __int64 v42; // [rsp+B0h] [rbp+60h] BYREF
  __int128 v43; // [rsp+B8h] [rbp+68h]
  __int64 v44; // [rsp+C8h] [rbp+78h]
  struct IUnknown *v45; // [rsp+D0h] [rbp+80h] BYREF
  __int64 v46; // [rsp+D8h] [rbp+88h] BYREF
  LPVOID pv; // [rsp+E0h] [rbp+90h] BYREF
  struct IRowset *v48; // [rsp+E8h] [rbp+98h] BYREF
  __int64 v49; // [rsp+F0h] [rbp+A0h]
  LPVOID v50; // [rsp+F8h] [rbp+A8h] BYREF
  unsigned int v51; // [rsp+100h] [rbp+B0h] BYREF
  int *v52; // [rsp+108h] [rbp+B8h]

  v4 = a4;
  v5 = this;
  v31 = this;
  v35 = a4;
  v6 = *((_QWORD *)this + 146);
  v49 = v6;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v6 + 32) + 8LL))(v6 + 32);
  v44 = v6;
  v7 = 0;
  v29 = 0;
  v30 = 0;
  v32 = 0;
  v45 = 0;
  v33 = CoInitializeEx(0, 0);
  v51 = 0;
  pv = 0;
  v50 = 0;
  v48 = 0;
  v46 = 0;
  v43 = 0;
  BYTE8(v43) = 1;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v9 = SetCursor(CursorW);
  v34 = v9;
  *(_QWORD *)&v43 = v9;
  v36 = 0;
  WindowTextLengthW = (unsigned int)GetWindowTextLengthW(v4);
  v11 = WindowTextLengthW + 1;
  if ( WindowTextLengthW + 1 < WindowTextLengthW || (v52 = 0, v12 = 2 * v11, v13 = 2 * v11, !is_mul_ok(v11, 2u)) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_52;
    v26 = 2452489;
    goto LABEL_51;
  }
  v14 = 0;
  if ( v12 + 16 >= v12 )
    v14 = v12 + 16;
  if ( v14 )
  {
    if ( v14 > 0x400 )
    {
      _mm_lfence();
      v17 = (int *)malloc(v14);
      v7 = v17;
      if ( !v17 )
        goto LABEL_16;
      *v17 = 56797;
      goto LABEL_15;
    }
    v15 = v14 + 15;
    if ( v14 + 15 < v14 )
      v15 = 0xFFFFFFFFFFFFFF0LL;
    v16 = alloca(v15 & 0xFFFFFFFFFFFFFFF0uLL);
    v7 = &v29;
    if ( &v28 != (__int64 *)-80LL )
    {
      v29 = 52428;
LABEL_15:
      v7 += 4;
    }
  }
LABEL_16:
  v52 = v7;
  v36 = v7;
  memset_0(v7, 0, v13);
  if ( (_DWORD)WindowTextLengthW )
    GetWindowTextW(v4, (LPWSTR)v7, WindowTextLengthW + 1);
  (*(void (__fastcall **)(CDataLinkDialog *))(*(_QWORD *)v5 + 40LL))(v5);
  v18 = CDataLinkDialog_Connect::ConnectToDS(v5, &v29, &v30, 0, 0, &v32, &v45, 0);
  if ( v18 >= 0 )
  {
    v29 = 1;
    goto LABEL_86;
  }
  _mm_lfence();
  if ( (bidGblFlags & 2) != 0 )
    bidTraceHR(off_180260360[0], 2480137, (unsigned int)v18);
  CDataLinkDialog_Connect::DisconnectFromDS(v5, &v32, &v45);
  SetWindowTextW(v4, &Class);
  VariantClear((VARIANTARG *)v5 + 19);
  *((_QWORD *)v5 + 58) = 0;
  v19 = CDataLinkDialog_Connect::ConnectToDS(v5, &v29, &v30, 0, 0, &v32, &v45, 1);
  if ( v19 < 0 )
  {
    _mm_lfence();
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_180260360[0], 2500617, (unsigned int)v19);
    CDataLinkDialog::DataLinkMessageBoxInfo(v5, v30);
    v25 = SysAllocString((const OLECHAR *)v7);
    if ( v25 )
    {
      *((_QWORD *)v5 + 51) = 233;
      if ( v5 == (CDataLinkDialog *)-424LL )
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
      else
      {
        *(DBID *)((char *)v5 + 424) = DB_NULLID;
      }
      *((_WORD *)v5 + 228) = 8;
      *((_QWORD *)v5 + 58) = v25;
LABEL_47:
      if ( *(_WORD *)v7 )
        SetWindowTextW(v4, (LPCWSTR)v7);
      goto LABEL_52;
    }
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_52;
    v26 = 2509833;
LABEL_51:
    bidTraceHR(off_180260360[0], v26, 2147942414LL);
    goto LABEL_52;
  }
  v29 = 0;
LABEL_86:
  try
  {
    v20 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v45->lpVtbl->QueryInterface)(
            v45,
            &IID_IDBSchemaRowset,
            &v46);
    if ( v20 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180260360[0], 2528265, (unsigned int)v20);
      }
      pExceptionObject = 0;
      throw (__int64 *)&pExceptionObject;
    }
    v21 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *, LPVOID *))(*(_QWORD *)v46 + 32LL))(
            v46,
            &v51,
            &pv,
            &v50);
    if ( v21 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180260360[0], 2537481, (unsigned int)v21);
      }
      v38 = 0;
      throw (__int64 *)&v38;
    }
    if ( !pv && v51 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceHR(off_180260360[0], 2543625, 2147500037LL);
      v39 = 0;
      throw (__int64 *)&v39;
    }
    for ( i = 0; i < v51; ++i )
    {
      if ( *((_QWORD *)pv + 2 * i) == *(_QWORD *)&DBSCHEMA_CATALOGS.Data1
        && *((_QWORD *)pv + 2 * i + 1) == *(_QWORD *)DBSCHEMA_CATALOGS.Data4 )
      {
        break;
      }
    }
    if ( i == v51 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceHR(off_180260360[0], 2552841, 2147500037LL);
      v40 = 0;
      throw (__int64 *)&v40;
    }
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, _QWORD, _QWORD, GUID *, _DWORD, _QWORD, struct IRowset **))(*(_QWORD *)v46 + 24LL))(
            v46,
            0,
            &DBSCHEMA_CATALOGS,
            0,
            0,
            &IID_IRowset,
            0,
            0,
            &v48);
    if ( v23 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180260360[0], 2568201, (unsigned int)v23);
      }
      v41 = 0;
      throw (__int64 *)&v41;
    }
    CatalogData = CDataLinkDialog_Connect::GetCatalogData(v5, v48, v4);
    if ( CatalogData < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180260360[0], 2576393, (unsigned int)CatalogData);
      }
      v42 = 0;
      throw (__int64 *)&v42;
    }
  }
  catch ( __int64 )
  {
    CDataLinkDialog::DataLinkMessageBoxInfo(v31, 0x9C9Fu);
    v4 = v35;
    v5 = v31;
    v7 = v52;
    v9 = v34;
    v6 = v49;
  }
  catch ( ... )
  {
    CDataLinkDialog::DataLinkMessageBoxInfo(v31, 0x9C8Cu);
    v4 = v35;
    v5 = v31;
    v7 = v52;
    v9 = v34;
    v6 = v49;
  }
  if ( v29 )
    goto LABEL_47;
LABEL_52:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v50 )
    CoTaskMemFree(v50);
  if ( v48 )
    ((void (__fastcall *)(struct IRowset *))v48->lpVtbl->Release)(v48);
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  CDataLinkDialog_Connect::DisconnectFromDS(v5, &v32, &v45);
  if ( v33 <= 1 )
    CoUninitialize();
  if ( v36 && *(v36 - 4) == 56797 )
    free(v36 - 4);
  SetCursor(v9);
  if ( v6 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v6 + 32) + 24LL))(v6 + 32, *(_QWORD *)(v6 + 32));
  return 1;
}

```

## disassembly

```asm
0x18003bc30  push    rbp
0x18003bc32  push    rsi
0x18003bc33  push    rdi
0x18003bc34  push    r12
0x18003bc36  push    r13
0x18003bc38  push    r14
0x18003bc3a  push    r15
0x18003bc3c  sub     rsp, 120h
0x18003bc43  lea     rbp, [rsp+50h]
0x18003bc48  mov     [rbp+100h+arg_8], rbx
0x18003bc4f  mov     rax, cs:__security_cookie
0x18003bc56  xor     rax, rbp
0x18003bc59  mov     [rbp+100h+var_40], rax
0x18003bc60  mov     r15, r9
0x18003bc63  mov     rdi, rcx
0x18003bc66  mov     [rbp+100h+var_F8], rcx
0x18003bc6a  mov     [rbp+100h+var_D8], r9
0x18003bc6e  mov     rsi, [rcx+490h]
0x18003bc75  mov     [rbp+100h+var_60], rsi
0x18003bc7c  test    rsi, rsi
0x18003bc7f  jz      short loc_18003BC92
0x18003bc81  lea     rcx, [rsi+20h]
0x18003bc85  mov     rax, [rcx]
0x18003bc88  mov     rax, [rax+8]
0x18003bc8c  call    cs:__guard_dispatch_icall_fptr
0x18003bc92  mov     [rbp+100h+var_88], rsi
0x18003bc96  xor     ebx, ebx
0x18003bc98  mov     [rbp+100h+var_100], ebx
0x18003bc9b  mov     [rbp+100h+var_FC], ebx
0x18003bc9e  mov     [rbp+100h+var_F0], rbx
0x18003bca2  mov     [rbp+100h+var_80], rbx
0x18003bca9  xor     edx, edx; dwCoInit
0x18003bcab  xor     ecx, ecx; pvReserved
0x18003bcad  call    cs:__imp_CoInitializeEx
0x18003bcb3  mov     [rbp+100h+var_E8], eax
0x18003bcb6  mov     [rbp+100h+var_50], ebx
0x18003bcbc  mov     [rbp+100h+pv], rbx
0x18003bcc3  mov     [rbp+100h+var_58], rbx
0x18003bcca  mov     [rbp+100h+var_68], rbx
0x18003bcd1  mov     [rbp+100h+var_78], rbx
0x18003bcd8  xorps   xmm0, xmm0
0x18003bcdb  movups  [rbp+100h+var_98], xmm0
0x18003bcdf  mov     byte ptr [rbp+100h+var_98+8], 1
0x18003bce3  mov     edx, 7F02h; lpCursorName
0x18003bce8  xor     ecx, ecx; hInstance
0x18003bcea  call    cs:__imp_LoadCursorW
0x18003bcf0  mov     rcx, rax; hCursor
0x18003bcf3  call    cs:__imp_SetCursor
0x18003bcf9  mov     r12, rax
0x18003bcfc  mov     [rbp+100h+var_E0], rax
0x18003bd00  mov     qword ptr [rbp+100h+var_98], rax
0x18003bd04  mov     [rbp+100h+var_D0], rbx
0x18003bd08  mov     rcx, r15; hWnd
0x18003bd0b  call    cs:__imp_GetWindowTextLengthW
0x18003bd11  mov     r13d, eax
0x18003bd14  lea     rdx, [r13+1]
0x18003bd18  cmp     rdx, r13
0x18003bd1b  jb      loc_18003C0B8
0x18003bd21  mov     [rbp+100h+var_48], rbx
0x18003bd28  mov     eax, 2
0x18003bd2d  mul     rdx
0x18003bd30  mov     r14, rax
0x18003bd33  test    rdx, rdx
0x18003bd36  jnz     loc_18003C0B8
0x18003bd3c  lea     rcx, [rax+10h]
0x18003bd40  mov     edx, ebx
0x18003bd42  cmp     rcx, rax
0x18003bd45  cmova   rdx, rcx
0x18003bd49  test    rdx, rdx
0x18003bd4c  jz      short loc_18003BDA6
0x18003bd4e  cmp     rdx, 400h
0x18003bd55  ja      short loc_18003BD88
0x18003bd57  lea     rax, [rdx+0Fh]
0x18003bd5b  cmp     rax, rdx
0x18003bd5e  ja      short loc_18003BD6A
0x18003bd60  mov     rax, 0FFFFFFFFFFFFFF0h
0x18003bd6a  and     rax, 0FFFFFFFFFFFFFFF0h
0x18003bd6e  call    _alloca_probe
0x18003bd73  sub     rsp, rax
0x18003bd76  lea     rbx, [rsp+150h+var_100]
0x18003bd7b  test    rbx, rbx
0x18003bd7e  jz      short loc_18003BDA6
0x18003bd80  mov     dword ptr [rbx], 0CCCCh
0x18003bd86  jmp     short loc_18003BDA2
0x18003bd88  lfence
0x18003bd8b  mov     rcx, rdx; Size
0x18003bd8e  call    cs:__imp_malloc
0x18003bd94  mov     rbx, rax
0x18003bd97  test    rax, rax
0x18003bd9a  jz      short loc_18003BDA6
0x18003bd9c  mov     dword ptr [rax], 0DDDDh
0x18003bda2  add     rbx, 10h
0x18003bda6  mov     [rbp+100h+var_48], rbx
0x18003bdad  mov     [rbp+100h+var_D0], rbx
0x18003bdb1  mov     r8, r14; Size
0x18003bdb4  xor     edx, edx; Val
0x18003bdb6  mov     rcx, rbx; void *
0x18003bdb9  call    memset_0
0x18003bdbe  test    r13d, r13d
0x18003bdc1  jz      short loc_18003BDD3
0x18003bdc3  lea     r8d, [r13+1]; nMaxCount
0x18003bdc7  mov     rdx, rbx; lpString
0x18003bdca  mov     rcx, r15; hWnd
0x18003bdcd  call    cs:__imp_GetWindowTextW
0x18003bdd3  mov     rax, [rdi]
0x18003bdd6  mov     rcx, rdi
0x18003bdd9  mov     rax, [rax+28h]
0x18003bddd  call    cs:__guard_dispatch_icall_fptr
0x18003bde3  xor     r13d, r13d
0x18003bde6  mov     [rsp+150h+var_118], r13d; int
0x18003bdeb  lea     rax, [rbp+100h+var_80]
0x18003bdf2  mov     [rsp+150h+var_120], rax; struct IUnknown **
0x18003bdf7  lea     rax, [rbp+100h+var_F0]
0x18003bdfb  mov     [rsp+150h+var_128], rax; struct IDBInitialize **
0x18003be00  mov     [rsp+150h+var_130], r13d; unsigned int
0x18003be05  xor     r9d, r9d; wchar_t *
0x18003be08  lea     r8, [rbp+100h+var_FC]; unsigned int *
0x18003be0c  lea     rdx, [rbp+100h+var_100]; int *
0x18003be10  mov     rcx, rdi; this
0x18003be13  call    ?ConnectToDS@CDataLinkDialog_Connect@@AEAAJPEAHPEAKPEA_WKPEAPEAUIDBInitialize@@PEAPEAUIUnknown@@H@Z; CDataLinkDialog_Connect::ConnectToDS(int *,ulong *,wchar_t *,ulong,IDBInitialize * *,IUnknown * *,int)
0x18003be18  test    eax, eax
0x18003be1a  js      short loc_18003BE28
0x18003be1c  mov     [rbp+100h+var_100], 1
0x18003be23  jmp     loc_18003BEC0
0x18003be28  lfence
0x18003be2b  test    byte ptr cs:_bidGblFlags, 2
0x18003be32  jz      short loc_18003BE48
0x18003be34  mov     r8d, eax
0x18003be37  mov     edx, 25D809h
0x18003be3c  mov     rcx, cs:off_180260360; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18003be43  call    _bidTraceHR
0x18003be48  lea     r8, [rbp+100h+var_80]; struct IUnknown **
0x18003be4f  lea     rdx, [rbp+100h+var_F0]; struct IDBInitialize **
0x18003be53  mov     rcx, rdi; this
0x18003be56  call    ?DisconnectFromDS@CDataLinkDialog_Connect@@AEAAXPEAPEAUIDBInitialize@@PEAPEAUIUnknown@@@Z; CDataLinkDialog_Connect::DisconnectFromDS(IDBInitialize * *,IUnknown * *)
0x18003be5b  lea     rdx, Class; lpString
0x18003be62  mov     rcx, r15; hWnd
0x18003be65  call    cs:__imp_SetWindowTextW
0x18003be6b  lea     rcx, [rdi+1C8h]; pvarg
0x18003be72  call    cs:__imp_VariantClear
0x18003be78  mov     [rdi+1D0h], r13
0x18003be7f  mov     [rsp+150h+var_118], 1; int
0x18003be87  lea     rax, [rbp+100h+var_80]
0x18003be8e  mov     [rsp+150h+var_120], rax; struct IUnknown **
0x18003be93  lea     rax, [rbp+100h+var_F0]
0x18003be97  mov     [rsp+150h+var_128], rax; struct IDBInitialize **
0x18003be9c  mov     [rsp+150h+var_130], r13d; unsigned int
0x18003bea1  xor     r9d, r9d; wchar_t *
0x18003bea4  lea     r8, [rbp+100h+var_FC]; unsigned int *
0x18003bea8  lea     rdx, [rbp+100h+var_100]; int *
0x18003beac  mov     rcx, rdi; this
0x18003beaf  call    ?ConnectToDS@CDataLinkDialog_Connect@@AEAAJPEAHPEAKPEA_WKPEAPEAUIDBInitialize@@PEAPEAUIUnknown@@H@Z; CDataLinkDialog_Connect::ConnectToDS(int *,ulong *,wchar_t *,ulong,IDBInitialize * *,IUnknown * *,int)
0x18003beb4  test    eax, eax
0x18003beb6  js      loc_18003C004
0x18003bebc  mov     [rbp+100h+var_100], r13d
0x18003bec0  mov     rcx, [rbp+100h+var_80]
0x18003bec7  mov     rax, [rcx]
0x18003beca  lea     r8, [rbp+100h+var_78]
0x18003bed1  lea     rdx, IID_IDBSchemaRowset
0x18003bed8  mov     rax, [rax]
0x18003bedb  call    cs:__guard_dispatch_icall_fptr
0x18003bee1  test    eax, eax
0x18003bee3  js      loc_18003C1B9
0x18003bee9  mov     rcx, [rbp+100h+var_78]
0x18003bef0  mov     rax, [rcx]
0x18003bef3  lea     r9, [rbp+100h+var_58]
0x18003befa  lea     r8, [rbp+100h+pv]
0x18003bf01  lea     rdx, [rbp+100h+var_50]
0x18003bf08  mov     rax, [rax+20h]
0x18003bf0c  call    cs:__guard_dispatch_icall_fptr
0x18003bf12  test    eax, eax
0x18003bf14  js      loc_18003C1ED
0x18003bf1a  mov     r8, [rbp+100h+pv]
0x18003bf21  mov     edx, [rbp+100h+var_50]
0x18003bf27  test    r8, r8
0x18003bf2a  jnz     short loc_18003BF34
0x18003bf2c  test    edx, edx
0x18003bf2e  jnz     loc_18003C221
0x18003bf34  mov     ecx, r13d
0x18003bf37  test    edx, edx
0x18003bf39  jz      short loc_18003BF68
0x18003bf3b  mov     r9, qword ptr cs:DBSCHEMA_CATALOGS.Data4
0x18003bf42  mov     r10, qword ptr cs:DBSCHEMA_CATALOGS.Data1
0x18003bf49  nop     dword ptr [rax+00000000h]
0x18003bf50  mov     eax, ecx
0x18003bf52  add     rax, rax
0x18003bf55  cmp     [r8+rax*8], r10
0x18003bf59  jnz     short loc_18003BF62
0x18003bf5b  cmp     [r8+rax*8+8], r9
0x18003bf60  jz      short loc_18003BF68
0x18003bf62  inc     ecx
0x18003bf64  cmp     ecx, edx
0x18003bf66  jb      short loc_18003BF50
0x18003bf68  cmp     ecx, edx
0x18003bf6a  jz      loc_18003C255
0x18003bf70  mov     rcx, [rbp+100h+var_78]
0x18003bf77  mov     rax, [rcx]
0x18003bf7a  lea     rdx, [rbp+100h+var_68]
0x18003bf81  mov     [rsp+150h+var_110], rdx
0x18003bf86  mov     qword ptr [rsp+150h+var_118], r13
0x18003bf8b  mov     dword ptr [rsp+150h+var_120], r13d
0x18003bf90  lea     rdx, IID_IRowset
0x18003bf97  mov     [rsp+150h+var_128], rdx
0x18003bf9c  mov     qword ptr [rsp+150h+var_130], r13
0x18003bfa1  xor     r9d, r9d
0x18003bfa4  lea     r8, DBSCHEMA_CATALOGS
0x18003bfab  xor     edx, edx
0x18003bfad  mov     rax, [rax+18h]
0x18003bfb1  call    cs:__guard_dispatch_icall_fptr
0x18003bfb7  test    eax, eax
0x18003bfb9  js      loc_18003C289
0x18003bfbf  mov     r8, r15; HWND
0x18003bfc2  mov     rdx, [rbp+100h+var_68]; struct IRowset *
0x18003bfc9  mov     rcx, rdi; this
0x18003bfcc  call    ?GetCatalogData@CDataLinkDialog_Connect@@AEAAJPEAUIRowset@@PEAUHWND__@@@Z; CDataLinkDialog_Connect::GetCatalogData(IRowset *,HWND__ *)
0x18003bfd1  test    eax, eax
0x18003bfd3  js      loc_18003C2BD
0x18003bfd9  jmp     short loc_18003BFF5
0x18003bfdb  mov     r15, [rbp+100h+var_D8]
0x18003bfdf  mov     rdi, [rbp+100h+var_F8]
0x18003bfe3  mov     rbx, [rbp+100h+var_48]
0x18003bfea  mov     r12, [rbp+100h+var_E0]
0x18003bfee  mov     rsi, [rbp+100h+var_60]
0x18003bff5  cmp     [rbp+100h+var_100], 0
0x18003bff9  jz      loc_18003C0D8
0x18003bfff  jmp     loc_18003C0A4
0x18003c004  lfence
0x18003c007  test    byte ptr cs:_bidGblFlags, 2
0x18003c00e  jz      short loc_18003C024
0x18003c010  mov     r8d, eax
0x18003c013  mov     edx, 262809h
0x18003c018  mov     rcx, cs:off_180260360; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18003c01f  call    _bidTraceHR
0x18003c024  mov     edx, [rbp+100h+var_FC]; unsigned int
0x18003c027  mov     rcx, rdi; this
0x18003c02a  call    ?DataLinkMessageBoxInfo@CDataLinkDialog@@IEAAXK@Z; CDataLinkDialog::DataLinkMessageBoxInfo(ulong)
0x18003c02f  mov     rcx, rbx; psz
0x18003c032  call    cs:__imp_SysAllocString
0x18003c038  mov     r14, rax
0x18003c03b  test    rax, rax
0x18003c03e  jnz     short loc_18003C054
0x18003c040  test    byte ptr cs:_bidGblFlags, 2
0x18003c047  jz      loc_18003C0D8
0x18003c04d  mov     edx, 264C09h
0x18003c052  jmp     short loc_18003C0C6
0x18003c054  mov     qword ptr [rdi+198h], 0E9h
0x18003c05f  lea     rax, [rdi+1A8h]
0x18003c066  test    rax, rax
0x18003c069  jnz     short loc_18003C07F
0x18003c06b  call    cs:__imp__errno
0x18003c071  mov     dword ptr [rax], 16h
0x18003c077  call    cs:__imp__invalid_parameter_noinfo
0x18003c07d  jmp     short loc_18003C094
0x18003c07f  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x18003c086  movups  xmmword ptr [rax], xmm0
0x18003c089  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x18003c090  movups  xmmword ptr [rax+10h], xmm1
0x18003c094  mov     word ptr [rdi+1C8h], 8
0x18003c09d  mov     [rdi+1D0h], r14
0x18003c0a4  cmp     word ptr [rbx], 0
0x18003c0a8  jz      short loc_18003C0D8
0x18003c0aa  mov     rdx, rbx; lpString
0x18003c0ad  mov     rcx, r15; hWnd
0x18003c0b0  call    cs:__imp_SetWindowTextW
0x18003c0b6  jmp     short loc_18003C0D8
0x18003c0b8  test    byte ptr cs:_bidGblFlags, 2
0x18003c0bf  jz      short loc_18003C0D8
0x18003c0c1  mov     edx, 256C09h
0x18003c0c6  mov     r8d, 8007000Eh
0x18003c0cc  mov     rcx, cs:off_180260360; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18003c0d3  call    _bidTraceHR
0x18003c0d8  mov     rcx, [rbp+100h+pv]; pv
0x18003c0df  test    rcx, rcx
0x18003c0e2  jz      short loc_18003C0EA
0x18003c0e4  call    cs:__imp_CoTaskMemFree
0x18003c0ea  mov     rcx, [rbp+100h+var_58]; pv
0x18003c0f1  test    rcx, rcx
0x18003c0f4  jz      short loc_18003C0FC
0x18003c0f6  call    cs:__imp_CoTaskMemFree
0x18003c0fc  mov     rcx, [rbp+100h+var_68]
0x18003c103  test    rcx, rcx
0x18003c106  jz      short loc_18003C115
0x18003c108  mov     rax, [rcx]
0x18003c10b  mov     rax, [rax+10h]
0x18003c10f  call    cs:__guard_dispatch_icall_fptr
0x18003c115  mov     rcx, [rbp+100h+var_78]
0x18003c11c  test    rcx, rcx
0x18003c11f  jz      short loc_18003C12E
0x18003c121  mov     rax, [rcx]
0x18003c124  mov     rax, [rax+10h]
0x18003c128  call    cs:__guard_dispatch_icall_fptr
0x18003c12e  lea     r8, [rbp+100h+var_80]; struct IUnknown **
0x18003c135  lea     rdx, [rbp+100h+var_F0]; struct IDBInitialize **
0x18003c139  mov     rcx, rdi; this
0x18003c13c  call    ?DisconnectFromDS@CDataLinkDialog_Connect@@AEAAXPEAPEAUIDBInitialize@@PEAPEAUIUnknown@@@Z; CDataLinkDialog_Connect::DisconnectFromDS(IDBInitialize * *,IUnknown * *)
0x18003c141  cmp     [rbp+100h+var_E8], 1
0x18003c145  ja      short loc_18003C14E
0x18003c147  call    cs:__imp_CoUninitialize
0x18003c14d  nop
0x18003c14e  mov     rax, [rbp+100h+var_D0]
  ... truncated ...
```
