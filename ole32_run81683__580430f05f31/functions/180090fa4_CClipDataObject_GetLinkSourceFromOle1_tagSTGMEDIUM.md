# CClipDataObject::GetLinkSourceFromOle1(tagSTGMEDIUM *)

- ea: `0x180090fa4`
- end: `0x18009128b`
- name: `?GetLinkSourceFromOle1@CClipDataObject@@AEAAJPEAUtagSTGMEDIUM@@@Z`
- size: `743`
- prototype: `HRESULT __fastcall(CClipDataObject *this, tagSTGMEDIUM *pmedium)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800914dc`

## callees

- `0x1800078b0`
- `0x180008760`
- `0x180034760`
- `0x180052390`
- `0x18005b9ec`
- `0x180090608`
- `0x180090fa4`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x180091247`
- `KERNELBASE!GlobalFree` at `0x180091247`
- `USER32!IsClipboardFormatAvailable` at `0x180091010`
- `USER32!IsClipboardFormatAvailable` at `0x180091010`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800910fb`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800910fb`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18009116f`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18009123d`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18009116f`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18009123d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091200`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009121e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091200`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009121e`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x18009105c`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x18009105c`
- `api-ms-win-core-com-l2-1-1!WriteClassStm` at `0x180091140`
- `api-ms-win-core-com-l2-1-1!WriteClassStm` at `0x180091140`

## pseudocode

```c
__int64 __fastcall CClipDataObject::GetLinkSourceFromOle1(CClipDataObject *this, tagSTGMEDIUM *pmedium)
{
  CClipDataObject *v2; // r12
  BOOL v4; // esi
  IMoniker *v5; // rdi
  IMoniker *v6; // r14
  BOOL v7; // eax
  CClipDataObject *v8; // rcx
  unsigned int v9; // edx
  HRESULT v10; // eax
  OLECHAR *v11; // r15
  unsigned int v12; // ebx
  HRESULT v13; // eax
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // r12
  IStream *v15; // rcx
  CClipDataObject *v16; // rax
  HRESULT HGlobalFromStream; // eax
  IStream *v18; // rcx
  HBITMAP hBitmap; // rax
  IStream *pstm; // [rsp+30h] [rbp-39h] BYREF
  IMoniker *pmkFile; // [rsp+38h] [rbp-31h] BYREF
  void *hgFree; // [rsp+40h] [rbp-29h] BYREF
  IMoniker *pmkFinal; // [rsp+48h] [rbp-21h] BYREF
  wchar_t *pszClass; // [rsp+50h] [rbp-19h] BYREF
  wchar_t *pszFile; // [rsp+58h] [rbp-11h] BYREF
  IMoniker *pmkItem; // [rsp+60h] [rbp-9h] BYREF
  CClipDataObject *v28; // [rsp+68h] [rbp-1h]
  IPersistStream *pPersistStream; // [rsp+70h] [rbp+7h] BYREF
  _GUID clsid; // [rsp+78h] [rbp+Fh] BYREF

  v28 = this;
  v2 = this;
  pstm = 0;
  pmkFile = 0;
  v4 = 1;
  pmkFinal = 0;
  v5 = 0;
  pmkItem = 0;
  v6 = 0;
  pPersistStream = 0;
  pszClass = 0;
  pszFile = 0;
  hgFree = 0;
  clsid = 0;
  v7 = IsClipboardFormatAvailable(g_cfObjectLink);
  v9 = g_cfObjectLink;
  if ( !v7 )
    v9 = g_cfOwnerLink;
  v10 = CClipDataObject::GetAndTranslateOle1(v8, v9, &pszClass, &pszFile, (wchar_t **)&hgFree, 0);
  v11 = (OLECHAR *)hgFree;
  v12 = v10;
  if ( !v10 )
  {
    v12 = CLSIDFromOle1Class(pszClass, &clsid, 1);
    if ( !v12 )
    {
      v12 = CreateOle1FileMoniker(pszFile, &clsid, &pmkFile);
      if ( v12 )
      {
        v5 = pmkFile;
        goto $errRtn_130;
      }
      if ( v11 && *v11 )
      {
        v13 = CreateItemMoniker(L"!", v11, &pmkItem);
        v6 = pmkItem;
        v12 = v13;
        v5 = pmkFile;
        if ( v13 )
          goto $errRtn_130;
        v12 = CreateGenericComposite(pmkFile, pmkItem, &pmkFinal);
        if ( v12 )
          goto $errRtn_130;
      }
      else
      {
        v5 = pmkFile;
        pmkFinal = pmkFile;
        ((void (__fastcall *)(IMoniker *))pmkFile->lpVtbl->AddRef)(pmkFile);
      }
      v4 = pmedium->tymed != 1;
      v12 = CreateStreamOnHGlobal(0, v4, &pstm);
      if ( !v12 )
      {
        ((void (__fastcall *)(IMoniker *, GUID *, IPersistStream **))pmkFinal->lpVtbl->QueryInterface)(
          pmkFinal,
          &IID_IPersistStream,
          &pPersistStream);
        v12 = OleSaveToStream(pPersistStream, pstm);
        if ( !v12 )
        {
          v12 = WriteClassStm(pstm, &clsid);
          if ( !v12 )
          {
            p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&pmedium->hBitmap;
            v15 = pstm;
            if ( pmedium->tymed == 4 )
            {
              v16 = v28;
              v28->m_pUnkOle1 = (IUnknown *)pstm;
              p_hBitmap->hBitmap = (HBITMAP)v15;
              v2 = v16;
            }
            else
            {
              HGlobalFromStream = GetHGlobalFromStream(pstm, &pmedium->hMetaFilePict);
              v18 = pstm;
              v12 = HGlobalFromStream;
              hBitmap = p_hBitmap->hBitmap;
              v2 = v28;
              v28->m_hOle1 = hBitmap;
              ((void (__fastcall *)(IStream *))v18->lpVtbl->Release)(v18);
              pstm = 0;
            }
          }
        }
      }
    }
  }
$errRtn_130:
  if ( pPersistStream )
    ((void (__fastcall *)(IPersistStream *))pPersistStream->lpVtbl->Release)(pPersistStream);
  if ( v5 )
    ((void (__fastcall *)(IMoniker *))v5->lpVtbl->Release)(v5);
  if ( v6 )
    ((void (__fastcall *)(IMoniker *))v6->lpVtbl->Release)(v6);
  if ( pmkFinal )
    ((void (__fastcall *)(IMoniker *))pmkFinal->lpVtbl->Release)(pmkFinal);
  if ( pszClass )
    CoTaskMemFree(pszClass);
  if ( pszFile )
    CoTaskMemFree(pszFile);
  if ( v11 )
    CoTaskMemFree(v11);
  if ( v12 && pstm )
  {
    if ( !v4 )
    {
      hgFree = 0;
      GetHGlobalFromStream(pstm, &hgFree);
      GlobalFree(hgFree);
    }
    ((void (__fastcall *)(IStream *))pstm->lpVtbl->Release)(pstm);
    v2->m_pUnkOle1 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x180090fa4  mov     [rsp-8+arg_10], rbx
0x180090fa9  push    rbp
0x180090faa  push    rsi
0x180090fab  push    rdi
0x180090fac  push    r12
0x180090fae  push    r13
0x180090fb0  push    r14
0x180090fb2  push    r15
0x180090fb4  lea     rbp, [rsp-27h]
0x180090fb9  sub     rsp, 90h
0x180090fc0  mov     rax, cs:__security_cookie
0x180090fc7  xor     rax, rsp
0x180090fca  mov     [rbp+57h+var_38], rax
0x180090fce  xor     ebx, ebx
0x180090fd0  mov     [rbp+57h+var_58], this
0x180090fd4  mov     r12, this
0x180090fd7  mov     [rbp+57h+pstm], rbx
0x180090fdb  movzx   ecx, cs:?g_cfObjectLink@@3GA; format
0x180090fe2  xorps   xmm0, xmm0
0x180090fe5  mov     r13, pmedium
0x180090fe8  mov     [rbp+57h+pmkFile], rbx
0x180090fec  lea     esi, [rbx+1]
0x180090fef  mov     [rbp+57h+pmkFinal], rbx
0x180090ff3  mov     edi, ebx
0x180090ff5  mov     [rbp+57h+pmkItem], rbx
0x180090ff9  mov     r14d, ebx
0x180090ffc  mov     [rbp+57h+pPersistStream], rbx
0x180091000  mov     [rbp+57h+pszClass], rbx
0x180091004  mov     [rbp+57h+pszFile], rbx
0x180091008  mov     [rbp+57h+hgFree], rbx
0x18009100c  movups  xmmword ptr [rbp+57h+clsid.Data1], xmm0
0x180091010  call    cs:__imp_IsClipboardFormatAvailable
0x180091016  movzx   edx, cs:?g_cfObjectLink@@3GA; ushort g_cfObjectLink
0x18009101d  test    eax, eax
0x18009101f  jnz     short loc_180091028
0x180091021  movzx   edx, cs:?g_cfOwnerLink@@3GA; cf
0x180091028  lea     rax, [rbp+57h+hgFree]
0x18009102c  mov     [rsp+0C0h+ppszItemA], rbx; ppszItemA
0x180091031  lea     r9, [rbp+57h+pszFile]; ppszFile
0x180091035  mov     [rsp+0C0h+ppszItem], rax; ppszItem
0x18009103a  lea     r8, [rbp+57h+pszClass]; ppszClass
0x18009103e  call    ?GetAndTranslateOle1@CClipDataObject@@AEAAJIPEAPEAG00PEAPEAD@Z; CClipDataObject::GetAndTranslateOle1(uint,ushort * *,ushort * *,ushort * *,char * *)
0x180091043  mov     r15, [rbp+57h+hgFree]
0x180091047  mov     ebx, eax
0x180091049  test    eax, eax
0x18009104b  jnz     $errRtn_130
0x180091051  mov     this, [rbp+57h+pszClass]
0x180091055  lea     pmedium, [rbp+57h+clsid]
0x180091059  mov     r8d, esi
0x18009105c  call    cs:__imp_CLSIDFromOle1Class
0x180091062  mov     ebx, eax
0x180091064  test    eax, eax
0x180091066  jnz     $errRtn_130
0x18009106c  mov     this, [rbp+57h+pszFile]; lpszPathName
0x180091070  lea     r8, [rbp+57h+pmkFile]; ppmk
0x180091074  lea     pmedium, [rbp+57h+clsid]; rclsidOle1
0x180091078  call    CreateOle1FileMoniker
0x18009107d  mov     ebx, eax
0x18009107f  test    eax, eax
0x180091081  jnz     loc_18009119E
0x180091087  test    r15, r15
0x18009108a  jz      short loc_1800910D1
0x18009108c  cmp     [r15], di
0x180091090  jz      short loc_1800910D1
0x180091092  lea     r8, [rbp+57h+pmkItem]; ppmk
0x180091096  mov     pmedium, r15; lpszItem
0x180091099  lea     this, szDelim; "!"
0x1800910a0  call    CreateItemMoniker
0x1800910a5  mov     r14, [rbp+57h+pmkItem]
0x1800910a9  mov     ebx, eax
0x1800910ab  mov     rdi, [rbp+57h+pmkFile]
0x1800910af  test    eax, eax
0x1800910b1  jnz     $errRtn_130
0x1800910b7  lea     r8, [rbp+57h+pmkFinal]; ppmkComposite
0x1800910bb  mov     pmedium, r14; pmkRest
0x1800910be  mov     this, rdi; pmkFirst
0x1800910c1  call    CreateGenericComposite
0x1800910c6  mov     ebx, eax
0x1800910c8  test    eax, eax
0x1800910ca  jz      short loc_1800910E8
0x1800910cc  jmp     $errRtn_130
0x1800910d1  mov     rdi, [rbp+57h+pmkFile]
0x1800910d5  mov     [rbp+57h+pmkFinal], rdi
0x1800910d9  mov     this, rdi
0x1800910dc  mov     rax, [rdi]
0x1800910df  mov     rax, [rax+8]
0x1800910e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800910e8  xor     eax, eax
0x1800910ea  lea     r8, [rbp+57h+pstm]; ppstm
0x1800910ee  cmp     [r13+0], esi
0x1800910f2  setnz   al
0x1800910f5  xor     ecx, ecx; hGlobal
0x1800910f7  mov     edx, eax; fDeleteOnRelease
0x1800910f9  mov     esi, eax
0x1800910fb  call    cs:__imp_CreateStreamOnHGlobal
0x180091101  mov     ebx, eax
0x180091103  test    eax, eax
0x180091105  jnz     $errRtn_130
0x18009110b  mov     this, [rbp+57h+pmkFinal]
0x18009110f  lea     r8, [rbp+57h+pPersistStream]
0x180091113  lea     pmedium, IID_IPersistStream
0x18009111a  mov     rax, [this]
0x18009111d  mov     rax, [rax]
0x180091120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091125  mov     pmedium, [rbp+57h+pstm]; pStm
0x180091129  mov     this, [rbp+57h+pPersistStream]; pPStm
0x18009112d  call    OleSaveToStream
0x180091132  mov     ebx, eax
0x180091134  test    eax, eax
0x180091136  jnz     short $errRtn_130
0x180091138  mov     this, [rbp+57h+pstm]; pStm
0x18009113c  lea     pmedium, [rbp+57h+clsid]; rclsid
0x180091140  call    cs:__imp_WriteClassStm
0x180091146  mov     ebx, eax
0x180091148  test    eax, eax
0x18009114a  jnz     short $errRtn_130
0x18009114c  cmp     dword ptr [r13+0], 4
0x180091151  lea     r12, [r13+8]
0x180091155  mov     this, [rbp+57h+pstm]; pstm
0x180091159  jnz     short loc_18009116C
0x18009115b  mov     rax, [rbp+57h+var_58]
0x18009115f  mov     [rax+20h], this
0x180091163  mov     [r12], this
0x180091167  mov     r12, rax
0x18009116a  jmp     short $errRtn_130
0x18009116c  mov     pmedium, r12; phglobal
0x18009116f  call    cs:__imp_GetHGlobalFromStream
0x180091175  mov     this, [rbp+57h+pstm]
0x180091179  mov     ebx, eax
0x18009117b  mov     rax, [r12]
0x18009117f  mov     r12, [rbp+57h+var_58]
0x180091183  mov     [r12+18h], rax
0x180091188  mov     rax, [this]
0x18009118b  mov     rax, [rax+10h]
0x18009118f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091194  mov     [rbp+57h+pstm], 0
0x18009119c  jmp     short $errRtn_130
0x18009119e  mov     rdi, [rbp+57h+pmkFile]
0x1800911a2  mov     this, [rbp+57h+pPersistStream]
0x1800911a6  test    this, this
0x1800911a9  jz      short loc_1800911B7
0x1800911ab  mov     rax, [this]
0x1800911ae  mov     rax, [rax+10h]
0x1800911b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800911b7  test    rdi, rdi
0x1800911ba  jz      short loc_1800911CB
0x1800911bc  mov     rax, [rdi]
0x1800911bf  mov     this, rdi
0x1800911c2  mov     rax, [rax+10h]
0x1800911c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800911cb  xor     edi, edi
0x1800911cd  test    r14, r14
0x1800911d0  jz      short loc_1800911E1
0x1800911d2  mov     rax, [r14]
0x1800911d5  mov     this, r14
0x1800911d8  mov     rax, [rax+10h]
0x1800911dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800911e1  mov     this, [rbp+57h+pmkFinal]
0x1800911e5  test    this, this
0x1800911e8  jz      short loc_1800911F6
0x1800911ea  mov     rax, [this]
0x1800911ed  mov     rax, [rax+10h]
0x1800911f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800911f6  cmp     [rbp+57h+pszClass], rdi
0x1800911fa  jz      short loc_180091206
0x1800911fc  mov     this, [rbp+57h+pszClass]; pv
0x180091200  call    cs:__imp_CoTaskMemFree
0x180091206  cmp     [rbp+57h+pszFile], rdi
0x18009120a  jz      short loc_180091216
0x18009120c  mov     this, [rbp+57h+pszFile]; pv
0x180091210  call    cs:__imp_CoTaskMemFree
0x180091216  test    r15, r15
0x180091219  jz      short loc_180091224
0x18009121b  mov     this, r15; pv
0x18009121e  call    cs:__imp_CoTaskMemFree
0x180091224  test    ebx, ebx
0x180091226  jz      short loc_180091262
0x180091228  mov     this, [rbp+57h+pstm]; pstm
0x18009122c  test    this, this
0x18009122f  jz      short loc_180091262
0x180091231  test    esi, esi
0x180091233  jnz     short loc_18009124D
0x180091235  lea     pmedium, [rbp+57h+hgFree]; phglobal
0x180091239  mov     [rbp+57h+hgFree], rdi
0x18009123d  call    cs:__imp_GetHGlobalFromStream
0x180091243  mov     this, [rbp+57h+hgFree]; hMem
0x180091247  call    cs:__imp_GlobalFree
0x18009124d  mov     this, [rbp+57h+pstm]
0x180091251  mov     rax, [this]
0x180091254  mov     rax, [rax+10h]
0x180091258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009125d  mov     [r12+20h], rdi
0x180091262  mov     eax, ebx
0x180091264  mov     this, [rbp+57h+var_38]
0x180091268  xor     this, rsp; StackCookie
0x18009126b  call    __security_check_cookie
0x180091270  mov     rbx, [rsp+0C0h+arg_10]
0x180091278  add     rsp, 90h
0x18009127f  pop     r15
0x180091281  pop     r14
0x180091283  pop     r13
0x180091285  pop     r12
0x180091287  pop     rdi
0x180091288  pop     rsi
0x180091289  pop     rbp
0x18009128a  retn
```
