# CResultsList::SetItems(CResultItem * *,ulong)

- ea: `0x180066504`
- end: `0x180066b9c`
- name: `?SetItems@CResultsList@@QEAAJPEAPEAVCResultItem@@K@Z`
- size: `1688`
- prototype: `int(CResultsList *__hidden this, struct CResultItem **, unsigned int)`
- caller_count: `4`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180065460`
- `0x1800671b8`
- `0x18006939c`
- `0x180071038`

## callees

- `0x18000f720`
- `0x180010cf0`
- `0x180011e3c`
- `0x1800120e0`
- `0x180013220`
- `0x1800132f0`
- `0x18001b608`
- `0x18001c4a8`
- `0x1800254e0`
- `0x180026394`
- `0x1800645b0`
- `0x1800646ec`
- `0x1800661b0`
- `0x180066504`
- `0x180073528`
- `0x180074348`
- `0x1800744d0`
- `0x180074540`
- `0x1800745a8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800666b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800667ab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800666b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800667ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800666f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006688e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800668be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800669ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066a40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800666f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006688e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800668be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800669ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066a40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b2f`
- `GDI32!DeleteObject` at `0x180066af6`
- `GDI32!DeleteObject` at `0x180066af6`
- `USER32!SendMessageW` at `0x180066554`
- `USER32!SendMessageW` at `0x180066574`
- `USER32!SendMessageW` at `0x1800669d5`
- `USER32!SendMessageW` at `0x180066aa5`
- `USER32!SendMessageW` at `0x180066aeb`
- `USER32!SendMessageW` at `0x180066b58`
- `USER32!SendMessageW` at `0x180066554`
- `USER32!SendMessageW` at `0x180066574`
- `USER32!SendMessageW` at `0x1800669d5`
- `USER32!SendMessageW` at `0x180066aa5`
- `USER32!SendMessageW` at `0x180066aeb`
- `USER32!SendMessageW` at `0x180066b58`
- `USER32!GetWindowLongW` at `0x1800667d6`
- `USER32!GetWindowLongW` at `0x1800667d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CResultsList::SetItems(HWND *this, struct CResultItem **a2, unsigned int a3)
{
  unsigned int v3; // ebx
  int v6; // eax
  int v7; // r13d
  int v8; // r15d
  unsigned int v9; // esi
  struct _DPA *v10; // rdi
  void *v11; // rbx
  int v12; // eax
  int i; // r14d
  int v14; // eax
  PVOID Ptr; // rsi
  int (__fastcall *v16)(PVOID, _QWORD, LPVOID *); // rbx
  int v17; // eax
  LONG WindowLongW; // eax
  struct _IMAGELIST *v19; // rax
  unsigned int v20; // r14d
  void *v21; // rsi
  int (__fastcall *v22)(void *, _QWORD, LPVOID *); // rbx
  int (__fastcall *v23)(void *, __int64, LPVOID *); // rbx
  int v24; // ebx
  struct CResultItem **v25; // rbx
  void *v26; // rdx
  int v27; // eax
  int v28; // ecx
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, __int64, unsigned __int16 **); // rbx
  int v31; // eax
  const unsigned __int16 *v32; // rsi
  __int64 v33; // rax
  int v34; // r15d
  __int64 v35; // rcx
  int v36; // eax
  unsigned __int16 *v37; // rbx
  WPARAM v38; // rsi
  struct _IMAGELIST *v39; // rax
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v42; // [rsp+48h] [rbp-B8h]
  LPVOID v43; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h]
  struct CResultItem **v45; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v46; // [rsp+68h] [rbp-98h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v48; // [rsp+78h] [rbp-88h] BYREF
  HDPA hdpa; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v50; // [rsp+88h] [rbp-78h] BYREF
  WPARAM wParam; // [rsp+90h] [rbp-70h]
  HIMAGELIST himl; // [rsp+98h] [rbp-68h]
  LPARAM v53[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v54; // [rsp+C4h] [rbp-3Ch]
  void *v55; // [rsp+C8h] [rbp-38h]
  int v56; // [rsp+D4h] [rbp-2Ch]
  int v57; // [rsp+D8h] [rbp-28h]
  unsigned int near **v58; // [rsp+E0h] [rbp-20h]
  LPARAM v59; // [rsp+100h] [rbp+0h] BYREF
  int v60; // [rsp+108h] [rbp+8h]
  __int64 v61; // [rsp+118h] [rbp+18h]
  WCHAR Buffer[128]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR v63[256]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v64[392]; // [rsp+460h] [rbp+360h] BYREF

  v3 = a3;
  v42 = a3;
  v45 = a2;
  SendMessageW(*this, 0x1009u, 0, 0);
  CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>::Destroy(this + 2);
  SendMessageW(*this, 0x109Du, 1u, 0);
  v44 = 0x3000000030LL;
  v6 = *((_DWORD *)this + 2);
  v7 = 0;
  if ( v6 )
    v44 = 0x2000000020LL;
  v8 = v6 != 0 ? 32 : 48;
  LODWORD(pv) = v8;
  hdpa = 0;
  if ( (unsigned int)CDPA_Base<CShareItemResult,CTContainer_PolicyRelease<CShareItemResult>>::Create(this + 2)
    && (unsigned int)CDPA_Base<IUnknown,CTContainer_PolicyRelease<IUnknown>>::Create(&hdpa, 5) )
  {
    v9 = 0;
    v10 = hdpa;
    if ( v3 )
    {
      do
      {
        v11 = (void *)*((_QWORD *)a2[v9] + 1);
        v43 = v11;
        if ( v11 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 8LL))(v11);
          if ( DPA_Search(v10, v11, 0, _CompareLibraries, 0x10000000, 1u) == -1 )
          {
            v12 = DPA_Search(v10, v11, 0, _CompareLibraries, 0, 5u);
            if ( DPA_InsertPtr(v10, v12, v11) != -1 )
              v11 = 0;
            v43 = v11;
          }
        }
        ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v43);
        ++v9;
      }
      while ( v9 < v42 );
      v8 = (int)pv;
      v3 = v42;
    }
    if ( LoadStringW(g_hInstance, 0x852u, Buffer, 128) )
    {
      for ( i = 0; ; ++i )
      {
        v14 = v10 ? *(_DWORD *)v10 : 0;
        if ( i >= v14 )
          break;
        pv = 0;
        Ptr = DPA_GetPtr(v10, i);
        v16 = *(int (__fastcall **)(PVOID, _QWORD, LPVOID *))(*(_QWORD *)Ptr + 40LL);
        CoTaskMemFree(pv);
        if ( v16(Ptr, 0, &pv) >= 0 && (int)SHFormatMessageArg(1024, (unsigned int)Buffer, 0, 0, (__int64)v64) >= 0 )
        {
          if ( v10 )
            v17 = *(_DWORD *)v10;
          else
            v17 = 0;
          InsertListViewGroup(*this, i, v64, v17 > 1);
        }
        CoTaskMemFree(pv);
      }
      v3 = v42;
    }
    if ( v10 )
      v7 = *(_DWORD *)v10;
    if ( LoadStringW(g_hInstance, 0x851u, v63, 256) )
      InsertListViewGroup(*this, v7, v63, 0);
    WindowLongW = GetWindowLongW(*this, -20);
    v19 = ImageList_Create(v8, v8, (WindowLongW & 0x400000 | 0x2004000u) >> 9, v3, 2);
    himl = v19;
    if ( v19 )
    {
      v20 = 0;
      if ( v3 )
      {
        do
        {
          v21 = *(void **)v45[v20];
          if ( DPA_Search(v10, v21, 0, _CompareLibraries, 0x10000000, 1u) == -1
            && (int)CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(this + 2, v21) >= 0 )
          {
            (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 8LL))(v21);
            v43 = 0;
            v22 = *(int (__fastcall **)(void *, _QWORD, LPVOID *))(*(_QWORD *)v21 + 40LL);
            CoTaskMemFree(0);
            if ( v22(v21, 0, &v43) >= 0 )
            {
              v48 = 0;
              v23 = *(int (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)v21 + 40LL);
              CoTaskMemFree(0);
              if ( v23(v21, 2147844096LL, &v48) >= 0 )
              {
                v47 = 0;
                if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))v21)(
                       v21,
                       &GUID_bcc18b79_ba16_442f_80c4_8a59c30c463b,
                       &v47) >= 0 )
                {
                  pv = 0;
                  if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, LPVOID *))(*(_QWORD *)v47 + 24LL))(
                         v47,
                         v44,
                         0,
                         &pv) >= 0 )
                  {
                    v24 = ImageList_Add(himl, (HBITMAP)pv, 0);
                    memset_0(v53, 0, 0x58u);
                    LODWORD(v53[0]) = 775;
                    v53[3] = (LPARAM)v43;
                    v54 = v24;
                    v57 = 2;
                    v58 = &c_uTileColumns;
                    v55 = v21;
                    v56 = v7;
                    v25 = v45;
                    v26 = (void *)*((_QWORD *)v45[v20] + 1);
                    if ( v26 )
                    {
                      v27 = DPA_Search(v10, v26, 0, _CompareLibraries, 0x10000000, 1u);
                      v28 = v56;
                      if ( v27 != -1 )
                        v28 = v27;
                      v56 = v28;
                    }
                    wParam = (int)SendMessageW(*this, 0x104Du, 0, (LPARAM)v53);
                    v29 = *((_QWORD *)v25[v20] + 2);
                    v46 = 0;
                    if ( !v29
                      || (v30 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 **))(*(_QWORD *)v29 + 40LL),
                          CoTaskMemFree(0),
                          v31 = v30(v29, 2147844096LL, &v46),
                          v32 = v46,
                          v31 < 0) )
                    {
                      v32 = (const unsigned __int16 *)v48;
                    }
                    v50 = 0;
                    v33 = -1;
                    do
                      ++v33;
                    while ( v32[v33] );
                    v34 = v33 + 2;
                    CoTaskMemFree(0);
                    v36 = _AllocArray<unsigned short,CTCoAllocPolicy>(v35, 1, v34, &v50);
                    v37 = (unsigned __int16 *)v50;
                    if ( v36 < 0 )
                    {
                      v38 = wParam;
                    }
                    else
                    {
                      *(_WORD *)v50 = 8234;
                      StringCchCopyW(v37 + 1, v34 - 1, v32);
                      memset_0(&v59, 0, 0x58u);
                      v60 = 1;
                      v61 = (__int64)v37;
                      v38 = wParam;
                      SendMessageW(*this, 0x1074u, wParam, (LPARAM)&v59);
                    }
                    memset_0(&v59, 0, 0x58u);
                    v60 = 2;
                    v61 = (__int64)v45[v20] + 24;
                    SendMessageW(*this, 0x1074u, v38, (LPARAM)&v59);
                    DeleteObject(pv);
                    CoTaskMemFree(v37);
                    CoTaskMemFree(v46);
                  }
                }
                ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v47);
              }
              CoTaskMemFree(v48);
            }
            CoTaskMemFree(v43);
            v3 = v42;
          }
          ++v20;
        }
        while ( v20 < v3 );
        v19 = himl;
      }
      v39 = (struct _IMAGELIST *)SendMessageW(*this, 0x1003u, 0, (LPARAM)v19);
      ImageList_Destroy(v39);
    }
  }
  CDPA_Base<IShellItem,CTContainer_PolicyRelease<IShellItem>>::~CDPA_Base<IShellItem,CTContainer_PolicyRelease<IShellItem>>(&hdpa);
  return 0;
}

```

## disassembly

```asm
0x180066504  mov     [rsp-8+arg_18], rbx
0x180066509  push    rbp
0x18006650a  push    rsi
0x18006650b  push    rdi
0x18006650c  push    r12
0x18006650e  push    r13
0x180066510  push    r14
0x180066512  push    r15
0x180066514  lea     rbp, [rsp-680h]
0x18006651c  sub     rsp, 780h
0x180066523  mov     rax, cs:__security_cookie
0x18006652a  xor     rax, rsp
0x18006652d  mov     [rbp+6B0h+var_40], rax
0x180066534  mov     ebx, r8d
0x180066537  mov     [rsp+7B0h+var_768], ebx
0x18006653b  mov     r14, rdx
0x18006653e  mov     [rsp+7B0h+var_750], rdx
0x180066543  mov     r12, rcx
0x180066546  xor     r9d, r9d; lParam
0x180066549  xor     r8d, r8d; wParam
0x18006654c  mov     edx, 1009h; Msg
0x180066551  mov     rcx, [rcx]; hWnd
0x180066554  call    cs:__imp_SendMessageW
0x18006655a  lea     rcx, [r12+10h]
0x18006655f  call    ?Destroy@?$CDPA_Base@VCUserObject@@V?$CTContainer_PolicyUnOwned@VCUserObject@@@@@@QEAAHXZ; CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>::Destroy(void)
0x180066564  xor     r9d, r9d; lParam
0x180066567  mov     edx, 109Dh; Msg
0x18006656c  lea     r8d, [r9+1]; wParam
0x180066570  mov     rcx, [r12]; hWnd
0x180066574  call    cs:__imp_SendMessageW
0x18006657a  mov     edx, 30h ; '0'
0x18006657f  mov     dword ptr [rsp+7B0h+var_758], edx
0x180066583  mov     dword ptr [rsp+7B0h+var_758+4], edx
0x180066587  mov     eax, [r12+8]
0x18006658c  xor     r13d, r13d
0x18006658f  test    eax, eax
0x180066591  jz      short loc_18006659E
0x180066593  lea     ecx, [rdx-10h]
0x180066596  mov     dword ptr [rsp+7B0h+var_758], ecx
0x18006659a  mov     dword ptr [rsp+7B0h+var_758+4], ecx
0x18006659e  neg     eax
0x1800665a0  sbb     r15d, r15d
0x1800665a3  and     r15d, 0FFFFFFF0h
0x1800665a7  add     r15d, edx
0x1800665aa  mov     dword ptr [rsp+7B0h+pv], r15d
0x1800665af  mov     [rbp+6B0h+hdpa], r13
0x1800665b3  lea     rcx, [r12+10h]
0x1800665b8  call    ?Create@?$CDPA_Base@VCShareItemResult@@V?$CTContainer_PolicyRelease@VCShareItemResult@@@@@@QEAAHH@Z; CDPA_Base<CShareItemResult,CTContainer_PolicyRelease<CShareItemResult>>::Create(int)
0x1800665bd  test    eax, eax
0x1800665bf  jz      loc_180066B67
0x1800665c5  mov     edx, 5
0x1800665ca  lea     rcx, [rbp+6B0h+hdpa]
0x1800665ce  call    ?Create@?$CDPA_Base@UIUnknown@@V?$CTContainer_PolicyRelease@UIUnknown@@@@@@QEAAHH@Z; CDPA_Base<IUnknown,CTContainer_PolicyRelease<IUnknown>>::Create(int)
0x1800665d3  test    eax, eax
0x1800665d5  jz      loc_180066B67
0x1800665db  mov     esi, r13d
0x1800665de  mov     rdi, [rbp+6B0h+hdpa]
0x1800665e2  test    ebx, ebx
0x1800665e4  jz      loc_18006669C
0x1800665ea  mov     r15d, [rsp+7B0h+var_768]
0x1800665ef  mov     eax, esi
0x1800665f1  mov     rbx, [r14+rax*8]
0x1800665f5  mov     rbx, [rbx+8]
0x1800665f9  mov     [rsp+7B0h+var_760], rbx
0x1800665fe  test    rbx, rbx
0x180066601  jz      short loc_180066613
0x180066603  mov     rax, [rbx]
0x180066606  mov     rcx, rbx
0x180066609  mov     rax, [rax+8]
0x18006660d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066612  nop
0x180066613  test    rbx, rbx
0x180066616  jz      short loc_18006667E
0x180066618  mov     [rsp+7B0h+options], 1; options
0x180066620  mov     [rsp+7B0h+lParam], 10000000h; lParam
0x180066629  lea     r9, ?_CompareLibraries@@YAHPEBUIShellItem@@0_J@Z; pfnCompare
0x180066630  xor     r8d, r8d; iStart
0x180066633  mov     rdx, rbx; pFind
0x180066636  mov     rcx, rdi; hdpa
0x180066639  call    DPA_Search
0x18006663e  cmp     eax, 0FFFFFFFFh
0x180066641  jnz     short loc_18006667E
0x180066643  mov     [rsp+7B0h+options], 5; options
0x18006664b  mov     [rsp+7B0h+lParam], r13; lParam
0x180066650  lea     r9, ?_CompareLibraries@@YAHPEBUIShellItem@@0_J@Z; pfnCompare
0x180066657  xor     r8d, r8d; iStart
0x18006665a  mov     rdx, rbx; pFind
0x18006665d  mov     rcx, rdi; hdpa
0x180066660  call    DPA_Search
0x180066665  mov     r8, rbx; p
0x180066668  mov     edx, eax; i
0x18006666a  mov     rcx, rdi; hdpa
0x18006666d  call    DPA_InsertPtr
0x180066672  cmp     eax, 0FFFFFFFFh
0x180066675  cmovnz  rbx, r13
0x180066679  mov     [rsp+7B0h+var_760], rbx
0x18006667e  lea     rcx, [rsp+7B0h+var_760]
0x180066683  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180066688  inc     esi
0x18006668a  cmp     esi, r15d
0x18006668d  jb      loc_1800665EF
0x180066693  mov     r15d, dword ptr [rsp+7B0h+pv]
0x180066698  mov     ebx, [rsp+7B0h+var_768]
0x18006669c  mov     r9d, 80h; cchBufferMax
0x1800666a2  lea     r8, [rbp+6B0h+Buffer]; lpBuffer
0x1800666a6  mov     edx, 852h; uID
0x1800666ab  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800666b2  call    cs:__imp_LoadStringW
0x1800666b8  test    eax, eax
0x1800666ba  jz      loc_18006678A
0x1800666c0  mov     r14d, r13d
0x1800666c3  test    rdi, rdi
0x1800666c6  jz      short loc_1800666CC
0x1800666c8  mov     eax, [rdi]
0x1800666ca  jmp     short loc_1800666CF
0x1800666cc  mov     eax, r13d
0x1800666cf  cmp     r14d, eax
0x1800666d2  jge     loc_180066786
0x1800666d8  mov     [rsp+7B0h+pv], r13
0x1800666dd  movsxd  rdx, r14d; i
0x1800666e0  mov     rcx, rdi; hdpa
0x1800666e3  call    DPA_GetPtr
0x1800666e8  mov     rsi, rax
0x1800666eb  mov     rcx, [rax]
0x1800666ee  mov     rbx, [rcx+28h]
0x1800666f2  mov     rcx, [rsp+7B0h+pv]; pv
0x1800666f7  call    cs:__imp_CoTaskMemFree
0x1800666fd  lea     r8, [rsp+7B0h+pv]
0x180066702  xor     edx, edx
0x180066704  mov     rcx, rsi
0x180066707  mov     rax, rbx
0x18006670a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006670f  test    eax, eax
0x180066711  js      short loc_180066773
0x180066713  mov     rax, [rsp+7B0h+pv]
0x180066718  mov     [rsp+7B0h+var_780], rax
0x18006671d  mov     [rsp+7B0h+options], 184h
0x180066725  lea     rax, [rbp+6B0h+var_350]
0x18006672c  mov     [rsp+7B0h+lParam], rax
0x180066731  xor     r9d, r9d
0x180066734  xor     r8d, r8d
0x180066737  lea     rdx, [rbp+6B0h+Buffer]
0x18006673b  mov     ecx, 400h
0x180066740  call    SHFormatMessageArg
0x180066745  test    eax, eax
0x180066747  js      short loc_180066773
0x180066749  test    rdi, rdi
0x18006674c  jz      short loc_180066752
0x18006674e  mov     eax, [rdi]
0x180066750  jmp     short loc_180066755
0x180066752  mov     eax, r13d
0x180066755  mov     r9d, r13d
0x180066758  cmp     eax, 1
0x18006675b  setnle  r9b; int
0x18006675f  lea     r8, [rbp+6B0h+var_350]; unsigned __int16 *
0x180066766  mov     edx, r14d; int
0x180066769  mov     rcx, [r12]; hWnd
0x18006676d  call    ?InsertListViewGroup@@YAHPEAUHWND__@@HPEAGH@Z; InsertListViewGroup(HWND__ *,int,ushort *,int)
0x180066772  nop
0x180066773  mov     rcx, [rsp+7B0h+pv]; pv
0x180066778  call    cs:__imp_CoTaskMemFree
0x18006677e  inc     r14d
0x180066781  jmp     loc_1800666C3
0x180066786  mov     ebx, [rsp+7B0h+var_768]
0x18006678a  test    rdi, rdi
0x18006678d  jz      short loc_180066792
0x18006678f  mov     r13d, [rdi]
0x180066792  mov     r9d, 100h; cchBufferMax
0x180066798  lea     r8, [rbp+6B0h+var_550]; lpBuffer
0x18006679f  mov     edx, 851h; uID
0x1800667a4  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800667ab  call    cs:__imp_LoadStringW
0x1800667b1  xor     esi, esi
0x1800667b3  test    eax, eax
0x1800667b5  jz      short loc_1800667CD
0x1800667b7  xor     r9d, r9d; int
0x1800667ba  lea     r8, [rbp+6B0h+var_550]; unsigned __int16 *
0x1800667c1  mov     edx, r13d; int
0x1800667c4  mov     rcx, [r12]; hWnd
0x1800667c8  call    ?InsertListViewGroup@@YAHPEAUHWND__@@HPEAGH@Z; InsertListViewGroup(HWND__ *,int,ushort *,int)
0x1800667cd  mov     edx, 0FFFFFFECh; nIndex
0x1800667d2  mov     rcx, [r12]; hWnd
0x1800667d6  call    cs:__imp_GetWindowLongW
0x1800667dc  and     eax, 400000h
0x1800667e1  or      eax, 2004000h
0x1800667e6  shr     eax, 9
0x1800667e9  mov     dword ptr [rsp+7B0h+lParam], 2; cGrow
0x1800667f1  mov     r9d, ebx; cInitial
0x1800667f4  mov     r8d, eax; flags
0x1800667f7  mov     edx, r15d; cy
0x1800667fa  mov     ecx, r15d; cx
0x1800667fd  call    ImageList_Create
0x180066802  mov     [rbp+6B0h+himl], rax
0x180066806  test    rax, rax
0x180066809  jz      loc_180066B67
0x18006680f  mov     r14d, esi
0x180066812  test    ebx, ebx
0x180066814  jz      loc_180066B49
0x18006681a  mov     r15d, r14d
0x18006681d  mov     rax, [rsp+7B0h+var_750]
0x180066822  mov     rax, [rax+r15*8]
0x180066826  mov     rsi, [rax]
0x180066829  mov     [rsp+7B0h+options], 1; options
0x180066831  mov     [rsp+7B0h+lParam], 10000000h; lParam
0x18006683a  lea     r9, ?_CompareLibraries@@YAHPEBUIShellItem@@0_J@Z; pfnCompare
0x180066841  xor     r8d, r8d; iStart
0x180066844  mov     rdx, rsi; pFind
0x180066847  mov     rcx, rdi; hdpa
0x18006684a  call    DPA_Search
0x18006684f  cmp     eax, 0FFFFFFFFh
0x180066852  jnz     loc_180066B39
0x180066858  mov     rdx, rsi
0x18006685b  lea     rcx, [r12+10h]
0x180066860  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x180066865  test    eax, eax
0x180066867  js      loc_180066B39
0x18006686d  mov     rax, [rsi]
0x180066870  mov     rcx, rsi
0x180066873  mov     rax, [rax+8]
0x180066877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006687c  mov     [rsp+7B0h+var_760], 0
0x180066885  mov     rax, [rsi]
0x180066888  mov     rbx, [rax+28h]
0x18006688c  xor     ecx, ecx; pv
0x18006688e  call    cs:__imp_CoTaskMemFree
0x180066894  lea     r8, [rsp+7B0h+var_760]
0x180066899  xor     edx, edx
0x18006689b  mov     rcx, rsi
0x18006689e  mov     rax, rbx
0x1800668a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668a6  xor     ebx, ebx
0x1800668a8  test    eax, eax
0x1800668aa  js      loc_180066B2A
0x1800668b0  mov     [rsp+7B0h+var_738], rbx
0x1800668b5  mov     rax, [rsi]
0x1800668b8  mov     rbx, [rax+28h]
0x1800668bc  xor     ecx, ecx; pv
0x1800668be  call    cs:__imp_CoTaskMemFree
0x1800668c4  lea     r8, [rsp+7B0h+var_738]
0x1800668c9  mov     edx, 80058000h
0x1800668ce  mov     rcx, rsi
0x1800668d1  mov     rax, rbx
0x1800668d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668d9  xor     ebx, ebx
0x1800668db  test    eax, eax
0x1800668dd  js      loc_180066B1E
0x1800668e3  mov     [rsp+7B0h+var_740], rbx
0x1800668e8  mov     rax, [rsi]
0x1800668eb  lea     r8, [rsp+7B0h+var_740]
0x1800668f0  lea     rdx, _GUID_bcc18b79_ba16_442f_80c4_8a59c30c463b
0x1800668f7  mov     rcx, rsi
0x1800668fa  mov     rax, [rax]
0x1800668fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066902  test    eax, eax
0x180066904  js      loc_180066B13
0x18006690a  mov     [rsp+7B0h+pv], rbx
0x18006690f  mov     rcx, [rsp+7B0h+var_740]
0x180066914  mov     rax, [rcx]
0x180066917  lea     r9, [rsp+7B0h+pv]
0x18006691c  xor     r8d, r8d
0x18006691f  mov     rdx, [rsp+7B0h+var_758]
0x180066924  mov     rax, [rax+18h]
0x180066928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006692d  test    eax, eax
0x18006692f  js      loc_180066B13
0x180066935  xor     r8d, r8d; hbmMask
0x180066938  mov     rdx, [rsp+7B0h+pv]; hbmImage
0x18006693d  mov     rcx, [rbp+6B0h+himl]; himl
0x180066941  call    ImageList_Add
0x180066946  mov     ebx, eax
0x180066948  xor     edx, edx; Val
0x18006694a  lea     r8d, [rdx+58h]; Size
0x18006694e  lea     rcx, [rbp+6B0h+var_710]; void *
0x180066952  call    memset_0
0x180066957  mov     dword ptr [rbp+6B0h+var_710], 307h
0x18006695e  mov     rcx, [rsp+7B0h+var_760]
0x180066963  mov     [rbp+6B0h+var_6F8], rcx
0x180066967  mov     [rbp+6B0h+var_6EC], ebx
0x18006696a  mov     [rbp+6B0h+var_6D8], 2
0x180066971  lea     rax, ?c_uTileColumns@@3PAIA; uint near * c_uTileColumns
0x180066978  mov     [rbp+6B0h+var_6D0], rax
0x18006697c  mov     [rbp+6B0h+var_6E8], rsi
0x180066980  mov     [rbp+6B0h+var_6DC], r13d
0x180066984  mov     rbx, [rsp+7B0h+var_750]
0x180066989  mov     rax, [rbx+r15*8]
0x18006698d  mov     rdx, [rax+8]; pFind
0x180066991  test    rdx, rdx
0x180066994  jz      short loc_1800669C5
0x180066996  mov     [rsp+7B0h+options], 1; options
0x18006699e  mov     [rsp+7B0h+lParam], 10000000h; lParam
0x1800669a7  lea     r9, ?_CompareLibraries@@YAHPEBUIShellItem@@0_J@Z; pfnCompare
0x1800669ae  xor     r8d, r8d; iStart
0x1800669b1  mov     rcx, rdi; hdpa
0x1800669b4  call    DPA_Search
0x1800669b9  mov     ecx, [rbp+6B0h+var_6DC]
0x1800669bc  cmp     eax, 0FFFFFFFFh
0x1800669bf  cmovnz  ecx, eax
0x1800669c2  mov     [rbp+6B0h+var_6DC], ecx
0x1800669c5  lea     r9, [rbp+6B0h+var_710]; lParam
0x1800669c9  xor     r8d, r8d; wParam
  ... truncated ...
```
