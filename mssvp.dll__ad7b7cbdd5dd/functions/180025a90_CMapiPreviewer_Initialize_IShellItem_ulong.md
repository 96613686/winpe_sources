# CMapiPreviewer::Initialize(IShellItem *,ulong)

- ea: `0x180025a90`
- end: `0x180025e4b`
- name: `?Initialize@CMapiPreviewer@@UEAAJPEAUIShellItem@@K@Z`
- size: `955`
- prototype: `__int64 __fastcall(CMapiPreviewer *__hidden this, struct IShellItem *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005210`
- `0x180005234`
- `0x18000557c`
- `0x180018808`
- `0x180018b34`
- `0x18001d404`
- `0x1800229b0`
- `0x180022fb4`
- `0x180025340`
- `0x180025780`
- `0x180025a90`
- `0x180025e80`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025c63`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025c63`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180025c07`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180025dfc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180025c07`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180025dfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiPreviewer::Initialize(CMapiPreviewer *this, struct IShellItem *a2)
{
  struct IMessage **v4; // rsi
  HRESULT MessageType; // edi
  CMapiPreviewer *v6; // rcx
  int IsMessageInJunkMail; // eax
  CMapiPreviewer *v8; // rcx
  CMapiPreviewer *v9; // rcx
  HWND v10; // rcx
  _QWORD *v11; // r14
  __int64 v12; // rdx
  int v13; // esi
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  HWND v18; // rcx
  _BYTE v20[144]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v21; // [rsp+D0h] [rbp+67h] BYREF
  LPVOID pv; // [rsp+E8h] [rbp+7Fh] BYREF

  CMapiPreviewer::DeactivateTooltip(this);
  v4 = (struct IMessage **)((char *)this + 216);
  ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 216);
  ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 256);
  *((_DWORD *)this + 309) = 0;
  pv = 0;
  MessageType = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a2->lpVtbl->GetDisplayName)(
                  a2,
                  2147647488LL,
                  &pv);
  if ( MessageType >= 0 )
  {
    CMapiUrl::CMapiUrl((CMapiUrl *)v20, (const wchar_t *)pv);
    if ( CMapiPreviewer::ConvertMapiUrlToMessage(
           v6,
           *((struct CMapiManager **)this + 36),
           (struct CMapiUrl *)v20,
           (struct IMessage **)this + 27) < 0 )
    {
      LODWORD(v21) = 0;
      MessageType = ((__int64 (__fastcall *)(struct IShellItem *, __int64, __int64 *))a2->lpVtbl->GetAttributes)(
                      a2,
                      0x40000000,
                      &v21);
      if ( MessageType < 0 )
      {
LABEL_9:
        CMapiUrl::~CMapiUrl((CMapiUrl *)v20);
        goto LABEL_10;
      }
      if ( !(_DWORD)v21 )
      {
        MessageType = -2147024809;
        goto LABEL_9;
      }
      IsMessageInJunkMail = CMapiPreviewer::ConvertFileToMessage(v8, (const wchar_t *)pv, (LPMESSAGE *)this + 27);
    }
    else
    {
      IsMessageInJunkMail = CMapiPreviewer::IsMessageInJunkMail(
                              *((struct CMapiManager **)this + 36),
                              *v4,
                              (struct CMapiUrl *)v20,
                              (int *)this + 309);
    }
    MessageType = IsMessageInJunkMail;
    goto LABEL_9;
  }
LABEL_10:
  CoTaskMemFree(pv);
  if ( MessageType >= 0 )
    MessageType = CMapiPreviewer::GetMessageType(this, *v4);
  LODWORD(v21) = 0;
  if ( MessageType < 0 )
    return (unsigned int)MessageType;
  if ( CMapiPreviewer::GetBodyFromMail(v9, *v4, (struct IStream **)this + 32, (unsigned int *)&v21) < 0 )
  {
    v16 = *((_QWORD *)this + 13);
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 48LL))(v16);
      ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 104);
    }
    v17 = *((_QWORD *)this + 14);
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 24LL))(v17, 0);
      ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 112);
    }
    if ( *((_QWORD *)this + 155) )
      ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 1240);
    v18 = (HWND)*((_QWORD *)this + 22);
    if ( v18 )
    {
      if ( DestroyWindow(v18) )
      {
        ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 1200);
        ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 1208);
        *((_QWORD *)this + 22) = 0;
      }
      else
      {
        return (unsigned int)ResultFromLastError();
      }
    }
    return (unsigned int)MessageType;
  }
  switch ( (_DWORD)v21 )
  {
    case 0x1000001E:
      v13 = 0;
      goto LABEL_37;
    case 0x1000001F:
      v13 = 1;
      goto LABEL_37;
    case 0x10090102:
      v13 = 2;
LABEL_37:
      v14 = *((_QWORD *)this + 13);
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 48LL))(v14);
        ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 104);
      }
      v15 = *((_QWORD *)this + 14);
      if ( v15 )
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, 0);
        ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 112);
      }
      if ( *((_QWORD *)this + 155) )
        ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 1240);
      goto LABEL_43;
  }
  if ( (_DWORD)v21 != 269680671 )
    return (unsigned int)-2147418113;
  v10 = (HWND)*((_QWORD *)this + 22);
  if ( v10 )
  {
    if ( DestroyWindow(v10) )
    {
      ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 1200);
      ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 1208);
      *((_QWORD *)this + 22) = 0;
    }
    else
    {
      MessageType = ResultFromLastError();
      if ( MessageType < 0 )
        return (unsigned int)MessageType;
    }
  }
  v11 = (_QWORD *)((char *)this + 104);
  if ( !*((_QWORD *)this + 13) )
  {
    MessageType = CoCreateInstance(
                    &CLSID_PreviewMime,
                    0,
                    0x17u,
                    &GUID_8895b1c6_b41f_4c1c_a562_0d564250836f,
                    (LPVOID *)this + 13);
    if ( MessageType < 0 )
      return (unsigned int)MessageType;
    if ( *((_QWORD *)this + 15)
      && (**(int (__fastcall ***)(_QWORD, GUID *, char *))*v11)(
           *v11,
           &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352,
           (char *)this + 112) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 14) + 24LL))(
        *((_QWORD *)this + 14),
        ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    }
  }
  v21 = 0;
  MessageType = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v11)(
                  *v11,
                  &GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f,
                  &v21);
  if ( MessageType >= 0 )
  {
    MessageType = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v21 + 24LL))(
                    v21,
                    *((_QWORD *)this + 32),
                    1);
    if ( MessageType >= 0 )
    {
      v12 = *((_QWORD *)this + 21);
      if ( v12 )
        MessageType = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v11 + 24LL))(
                        *v11,
                        v12,
                        (char *)this + 144);
    }
  }
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v21);
  v13 = 3;
  if ( MessageType >= 0 )
LABEL_43:
    *((_DWORD *)this + 52) = v13;
  return (unsigned int)MessageType;
}

```

## disassembly

```asm
0x180025a90  mov     [rsp-8+arg_8], rbx
0x180025a95  push    rbp
0x180025a96  push    rsi
0x180025a97  push    rdi
0x180025a98  push    r12
0x180025a9a  push    r13
0x180025a9c  push    r14
0x180025a9e  push    r15
0x180025aa0  lea     rbp, [rsp-27h]
0x180025aa5  sub     rsp, 90h
0x180025aac  mov     r14, rdx
0x180025aaf  mov     rbx, rcx
0x180025ab2  call    ?DeactivateTooltip@CMapiPreviewer@@AEAAXXZ; CMapiPreviewer::DeactivateTooltip(void)
0x180025ab7  lea     rsi, [rbx+0D8h]
0x180025abe  mov     rcx, rsi
0x180025ac1  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025ac6  lea     r12, [rbx+100h]
0x180025acd  mov     rcx, r12
0x180025ad0  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025ad5  lea     r15, [rbx+4D4h]
0x180025adc  xor     r13d, r13d
0x180025adf  mov     [r15], r13d
0x180025ae2  mov     [rbp+57h+pv], r13
0x180025ae6  mov     rax, [r14]
0x180025ae9  lea     r8, [rbp+57h+pv]
0x180025aed  mov     edx, 80028000h
0x180025af2  mov     rcx, r14
0x180025af5  mov     rax, [rax+28h]
0x180025af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025afe  mov     edi, eax
0x180025b00  test    eax, eax
0x180025b02  js      loc_180025B8A
0x180025b08  mov     rdx, [rbp+57h+pv]; wchar_t *
0x180025b0c  lea     rcx, [rbp+57h+var_90]; this
0x180025b10  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x180025b15  mov     r9, rsi; struct IMessage **
0x180025b18  lea     r8, [rbp+57h+var_90]; struct CMapiUrl *
0x180025b1c  mov     rdx, [rbx+120h]; struct CMapiManager *
0x180025b23  call    ?ConvertMapiUrlToMessage@CMapiPreviewer@@AEAAJPEAVCMapiManager@@AEAVCMapiUrl@@PEAPEAUIMessage@@@Z; CMapiPreviewer::ConvertMapiUrlToMessage(CMapiManager *,CMapiUrl &,IMessage * *)
0x180025b28  test    eax, eax
0x180025b2a  js      short loc_180025B44
0x180025b2c  mov     r9, r15; int *
0x180025b2f  lea     r8, [rbp+57h+var_90]; struct CMapiUrl *
0x180025b33  mov     rdx, [rsi]; struct IMessage *
0x180025b36  mov     rcx, [rbx+120h]; struct CMapiManager *
0x180025b3d  call    ?IsMessageInJunkMail@CMapiPreviewer@@CAJPEAVCMapiManager@@PEAUIMessage@@AEAVCMapiUrl@@PEAH@Z; CMapiPreviewer::IsMessageInJunkMail(CMapiManager *,IMessage *,CMapiUrl &,int *)
0x180025b42  jmp     short loc_180025B78
0x180025b44  mov     dword ptr [rbp+57h+arg_0], r13d
0x180025b48  mov     rax, [r14]
0x180025b4b  lea     r8, [rbp+57h+arg_0]
0x180025b4f  mov     edx, 40000000h
0x180025b54  mov     rcx, r14
0x180025b57  mov     rax, [rax+30h]
0x180025b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b60  mov     edi, eax
0x180025b62  test    eax, eax
0x180025b64  js      short loc_180025B81
0x180025b66  cmp     dword ptr [rbp+57h+arg_0], r13d
0x180025b6a  jz      short loc_180025B7C
0x180025b6c  mov     r8, rsi; struct IMessage **
0x180025b6f  mov     rdx, [rbp+57h+pv]; wchar_t *
0x180025b73  call    ?ConvertFileToMessage@CMapiPreviewer@@AEAAJPEB_WPEAPEAUIMessage@@@Z; CMapiPreviewer::ConvertFileToMessage(wchar_t const *,IMessage * *)
0x180025b78  mov     edi, eax
0x180025b7a  jmp     short loc_180025B81
0x180025b7c  mov     edi, 80070057h
0x180025b81  lea     rcx, [rbp+57h+var_90]; this
0x180025b85  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x180025b8a  mov     rcx, [rbp+57h+pv]; pv
0x180025b8e  call    cs:__imp_CoTaskMemFree
0x180025b94  test    edi, edi
0x180025b96  js      short loc_180025BA5
0x180025b98  mov     rdx, [rsi]; struct IMessage *
0x180025b9b  mov     rcx, rbx; this
0x180025b9e  call    ?GetMessageType@CMapiPreviewer@@AEAAJPEAUIMessage@@@Z; CMapiPreviewer::GetMessageType(IMessage *)
0x180025ba3  mov     edi, eax
0x180025ba5  mov     dword ptr [rbp+57h+arg_0], r13d
0x180025ba9  test    edi, edi
0x180025bab  js      loc_180025E2E
0x180025bb1  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180025bb5  mov     r8, r12; struct IStream **
0x180025bb8  mov     rdx, [rsi]; struct IMessage *
0x180025bbb  call    ?GetBodyFromMail@CMapiPreviewer@@AEAAJPEAUIMessage@@PEAPEAUIStream@@PEAK@Z; CMapiPreviewer::GetBodyFromMail(IMessage *,IStream * *,ulong *)
0x180025bc0  test    eax, eax
0x180025bc2  js      loc_180025DA1
0x180025bc8  mov     eax, dword ptr [rbp+57h+arg_0]
0x180025bcb  sub     eax, 1000001Eh
0x180025bd0  jz      loc_180025D44
0x180025bd6  sub     eax, 1
0x180025bd9  jz      loc_180025D3D
0x180025bdf  sub     eax, 900E3h
0x180025be4  jz      loc_180025D36
0x180025bea  cmp     eax, 9FF1Dh
0x180025bef  jz      short loc_180025BFB
0x180025bf1  mov     edi, 8000FFFFh
0x180025bf6  jmp     loc_180025E2E
0x180025bfb  mov     rcx, [rbx+0B0h]; hWnd
0x180025c02  test    rcx, rcx
0x180025c05  jz      short loc_180025C41
0x180025c07  call    cs:__imp_DestroyWindow
0x180025c0d  test    eax, eax
0x180025c0f  jz      short loc_180025C32
0x180025c11  lea     rcx, [rbx+4B0h]
0x180025c18  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025c1d  lea     rcx, [rbx+4B8h]
0x180025c24  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025c29  mov     [rbx+0B0h], r13
0x180025c30  jmp     short loc_180025C41
0x180025c32  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180025c37  mov     edi, eax
0x180025c39  test    eax, eax
0x180025c3b  js      loc_180025E2E
0x180025c41  lea     r14, [rbx+68h]
0x180025c45  cmp     [r14], r13
0x180025c48  jnz     short loc_180025CB7
0x180025c4a  mov     [rsp+0C0h+ppv], r14; ppv
0x180025c4f  lea     r9, _GUID_8895b1c6_b41f_4c1c_a562_0d564250836f; riid
0x180025c56  xor     edx, edx; pUnkOuter
0x180025c58  lea     r8d, [rdx+17h]; dwClsContext
0x180025c5c  lea     rcx, CLSID_PreviewMime; rclsid
0x180025c63  call    cs:__imp_CoCreateInstance
0x180025c69  mov     edi, eax
0x180025c6b  test    eax, eax
0x180025c6d  js      loc_180025E2E
0x180025c73  cmp     [rbx+78h], r13
0x180025c77  jz      short loc_180025CB7
0x180025c79  mov     rcx, [r14]
0x180025c7c  mov     rax, [rcx]
0x180025c7f  lea     r8, [rbx+70h]
0x180025c83  lea     rdx, _GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352
0x180025c8a  mov     rax, [rax]
0x180025c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c92  nop
0x180025c93  test    eax, eax
0x180025c95  js      short loc_180025CB7
0x180025c97  mov     rcx, [rbx+70h]
0x180025c9b  mov     r9, [rcx]
0x180025c9e  mov     rax, rbx
0x180025ca1  lea     r8, [rbx+8]
0x180025ca5  neg     rax
0x180025ca8  sbb     rdx, rdx
0x180025cab  and     rdx, r8
0x180025cae  mov     rax, [r9+18h]
0x180025cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cb7  mov     [rbp+57h+arg_0], r13
0x180025cbb  mov     rcx, [r14]
0x180025cbe  mov     rax, [rcx]
0x180025cc1  lea     r8, [rbp+57h+arg_0]
0x180025cc5  lea     rdx, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f
0x180025ccc  mov     rax, [rax]
0x180025ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cd4  mov     edi, eax
0x180025cd6  test    eax, eax
0x180025cd8  js      short loc_180025D1E
0x180025cda  mov     rcx, [rbp+57h+arg_0]
0x180025cde  mov     rax, [rcx]
0x180025ce1  mov     r8d, 1
0x180025ce7  mov     rdx, [r12]
0x180025ceb  mov     rax, [rax+18h]
0x180025cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cf4  mov     edi, eax
0x180025cf6  test    eax, eax
0x180025cf8  js      short loc_180025D1E
0x180025cfa  mov     rdx, [rbx+0A8h]
0x180025d01  test    rdx, rdx
0x180025d04  jz      short loc_180025D1E
0x180025d06  mov     rcx, [r14]
0x180025d09  mov     rax, [rcx]
0x180025d0c  lea     r8, [rbx+90h]
0x180025d13  mov     rax, [rax+18h]
0x180025d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d1c  mov     edi, eax
0x180025d1e  lea     rcx, [rbp+57h+arg_0]
0x180025d22  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180025d27  mov     esi, 3
0x180025d2c  test    edi, edi
0x180025d2e  js      loc_180025E2E
0x180025d34  jmp     short loc_180025D96
0x180025d36  mov     esi, 2
0x180025d3b  jmp     short loc_180025D47
0x180025d3d  mov     esi, 1
0x180025d42  jmp     short loc_180025D47
0x180025d44  mov     esi, r13d
0x180025d47  mov     rcx, [rbx+68h]
0x180025d4b  test    rcx, rcx
0x180025d4e  jz      short loc_180025D65
0x180025d50  mov     rax, [rcx]
0x180025d53  mov     rax, [rax+30h]
0x180025d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d5c  lea     rcx, [rbx+68h]
0x180025d60  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025d65  mov     rcx, [rbx+70h]
0x180025d69  test    rcx, rcx
0x180025d6c  jz      short loc_180025D85
0x180025d6e  mov     rax, [rcx]
0x180025d71  xor     edx, edx
0x180025d73  mov     rax, [rax+18h]
0x180025d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d7c  lea     rcx, [rbx+70h]
0x180025d80  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025d85  lea     rcx, [rbx+4D8h]
0x180025d8c  cmp     [rcx], r13
0x180025d8f  jz      short loc_180025D96
0x180025d91  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025d96  mov     [rbx+0D0h], esi
0x180025d9c  jmp     loc_180025E2E
0x180025da1  mov     rcx, [rbx+68h]
0x180025da5  test    rcx, rcx
0x180025da8  jz      short loc_180025DBF
0x180025daa  mov     rax, [rcx]
0x180025dad  mov     rax, [rax+30h]
0x180025db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025db6  lea     rcx, [rbx+68h]
0x180025dba  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025dbf  mov     rcx, [rbx+70h]
0x180025dc3  test    rcx, rcx
0x180025dc6  jz      short loc_180025DDF
0x180025dc8  mov     rax, [rcx]
0x180025dcb  xor     edx, edx
0x180025dcd  mov     rax, [rax+18h]
0x180025dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dd6  lea     rcx, [rbx+70h]
0x180025dda  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025ddf  lea     rcx, [rbx+4D8h]
0x180025de6  cmp     [rcx], r13
0x180025de9  jz      short loc_180025DF0
0x180025deb  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025df0  mov     rcx, [rbx+0B0h]; hWnd
0x180025df7  test    rcx, rcx
0x180025dfa  jz      short loc_180025E2E
0x180025dfc  call    cs:__imp_DestroyWindow
0x180025e02  test    eax, eax
0x180025e04  jz      short loc_180025E27
0x180025e06  lea     rcx, [rbx+4B0h]
0x180025e0d  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025e12  lea     rcx, [rbx+4B8h]
0x180025e19  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180025e1e  mov     [rbx+0B0h], r13
0x180025e25  jmp     short loc_180025E2E
0x180025e27  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180025e2c  mov     edi, eax
0x180025e2e  mov     eax, edi
0x180025e30  mov     rbx, [rsp+0C0h+arg_8]
0x180025e38  add     rsp, 90h
0x180025e3f  pop     r15
0x180025e41  pop     r14
0x180025e43  pop     r13
0x180025e45  pop     r12
0x180025e47  pop     rdi
0x180025e48  pop     rsi
0x180025e49  pop     rbp
0x180025e4a  retn
```
