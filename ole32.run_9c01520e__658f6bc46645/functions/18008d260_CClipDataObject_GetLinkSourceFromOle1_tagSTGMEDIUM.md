# CClipDataObject::GetLinkSourceFromOle1(tagSTGMEDIUM *)

- ea: `0x18008d260`
- end: `0x18008d584`
- name: `?GetLinkSourceFromOle1@CClipDataObject@@AEAAJPEAUtagSTGMEDIUM@@@Z`
- size: `804`
- prototype: `HRESULT __fastcall(CClipDataObject *this, tagSTGMEDIUM *pmedium)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008d7fc`

## callees

- `0x180006b80`
- `0x180009000`
- `0x1800383d0`
- `0x180046460`
- `0x18004d694`
- `0x18008c7c8`
- `0x18008d260`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x18008d539`
- `KERNELBASE!GlobalFree` at `0x18008d539`
- `USER32!IsClipboardFormatAvailable` at `0x18008d2cc`
- `USER32!IsClipboardFormatAvailable` at `0x18008d2cc`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18008d3c2`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18008d3c2`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18008d445`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18008d529`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18008d445`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18008d529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d4d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d4ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d4d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d4ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d502`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x18008d31e`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x18008d31e`
- `api-ms-win-core-com-l2-1-1!WriteClassStm` at `0x18008d410`
- `api-ms-win-core-com-l2-1-1!WriteClassStm` at `0x18008d410`

## pseudocode

```c
__int64 __fastcall CClipDataObject::GetLinkSourceFromOle1(CClipDataObject *this, tagSTGMEDIUM *pmedium)
{
  BOOL v2; // r14d
  IMoniker *v4; // rdi
  int v5; // r12d
  IMoniker *v6; // rsi
  BOOL v7; // eax
  CClipDataObject *v8; // rcx
  unsigned int v9; // edx
  HRESULT v10; // eax
  OLECHAR *v11; // r15
  unsigned int v12; // ebx
  HRESULT v13; // eax
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // r12
  IStream *v15; // rcx
  CClipDataObject *v16; // r13
  HRESULT HGlobalFromStream; // eax
  IStream *v18; // rcx
  IStream *pstm; // [rsp+30h] [rbp-39h] BYREF
  CClipDataObject *v21; // [rsp+38h] [rbp-31h]
  IMoniker *pmkFile; // [rsp+40h] [rbp-29h] BYREF
  void *hgFree; // [rsp+48h] [rbp-21h] BYREF
  IMoniker *pmkFinal; // [rsp+50h] [rbp-19h] BYREF
  IMoniker *pmkItem; // [rsp+58h] [rbp-11h] BYREF
  IPersistStream *pPersistStream; // [rsp+60h] [rbp-9h] BYREF
  wchar_t *pszClass; // [rsp+68h] [rbp-1h] BYREF
  wchar_t *pszFile; // [rsp+70h] [rbp+7h] BYREF
  _GUID clsid; // [rsp+78h] [rbp+Fh] BYREF

  v2 = 0;
  v21 = this;
  pstm = 0;
  v4 = 0;
  pmkFile = 0;
  v5 = 1;
  pmkFinal = 0;
  v6 = 0;
  pmkItem = 0;
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
  if ( v10 )
    goto LABEL_20;
  v12 = CLSIDFromOle1Class(pszClass, &clsid, 1);
  if ( v12 )
    goto LABEL_20;
  v12 = CreateOle1FileMoniker(pszFile, &clsid, &pmkFile);
  if ( v12 )
  {
    v4 = pmkFile;
    goto LABEL_20;
  }
  if ( v11 && *v11 )
  {
    v13 = CreateItemMoniker(L"!", v11, &pmkItem);
    v6 = pmkItem;
    v12 = v13;
    v4 = pmkFile;
    if ( v13 )
      goto LABEL_20;
    v12 = CreateGenericComposite(pmkFile, pmkItem, &pmkFinal);
    if ( v12 )
      goto LABEL_20;
  }
  else
  {
    v4 = pmkFile;
    pmkFinal = pmkFile;
    ((void (__fastcall *)(IMoniker *))pmkFile->lpVtbl->AddRef)(pmkFile);
  }
  LOBYTE(v2) = pmedium->tymed != 1;
  v12 = CreateStreamOnHGlobal(0, v2, &pstm);
  v5 = v2;
  if ( v12
    || (((void (__fastcall *)(IMoniker *, GUID *, IPersistStream **))pmkFinal->lpVtbl->QueryInterface)(
          pmkFinal,
          &IID_IPersistStream,
          &pPersistStream),
        (v12 = OleSaveToStream(pPersistStream, pstm)) != 0)
    || (v12 = WriteClassStm(pstm, &clsid)) != 0 )
  {
LABEL_20:
    v16 = v21;
    goto $errRtn_103;
  }
  p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&pmedium->hBitmap;
  v15 = pstm;
  if ( pmedium->tymed == 4 )
  {
    v16 = v21;
    v21->m_pUnkOle1 = (IUnknown *)pstm;
    p_hBitmap->hBitmap = (HBITMAP)v15;
  }
  else
  {
    HGlobalFromStream = GetHGlobalFromStream(pstm, &pmedium->hMetaFilePict);
    v18 = pstm;
    v12 = HGlobalFromStream;
    v16 = v21;
    v21->m_hOle1 = p_hBitmap->hBitmap;
    ((void (__fastcall *)(IStream *))v18->lpVtbl->Release)(v18);
    pstm = 0;
  }
  v5 = v2;
$errRtn_103:
  if ( pPersistStream )
    ((void (__fastcall *)(IPersistStream *))pPersistStream->lpVtbl->Release)(pPersistStream);
  if ( v4 )
    ((void (__fastcall *)(IMoniker *))v4->lpVtbl->Release)(v4);
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
    if ( !v5 )
    {
      hgFree = 0;
      GetHGlobalFromStream(pstm, &hgFree);
      GlobalFree(hgFree);
    }
    ((void (__fastcall *)(IStream *))pstm->lpVtbl->Release)(pstm);
    v16->m_pUnkOle1 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x18008d260  mov     [rsp-8+arg_10], rbx
0x18008d265  push    rbp
0x18008d266  push    rsi
0x18008d267  push    rdi
0x18008d268  push    r12
0x18008d26a  push    r13
0x18008d26c  push    r14
0x18008d26e  push    r15
0x18008d270  lea     rbp, [rsp-27h]
0x18008d275  sub     rsp, 90h
0x18008d27c  mov     rax, cs:__security_cookie
0x18008d283  xor     rax, rsp
0x18008d286  mov     [rbp+57h+var_38], rax
0x18008d28a  xor     r14d, r14d
0x18008d28d  mov     [rbp+57h+var_88], this
0x18008d291  movzx   ecx, cs:?g_cfObjectLink@@3GA; format
0x18008d298  xorps   xmm0, xmm0
0x18008d29b  mov     r13, pmedium
0x18008d29e  mov     [rbp+57h+pstm], r14
0x18008d2a2  mov     edi, r14d
0x18008d2a5  mov     [rbp+57h+pmkFile], r14
0x18008d2a9  lea     r12d, [r14+1]
0x18008d2ad  mov     [rbp+57h+pmkFinal], r14
0x18008d2b1  mov     esi, r14d
0x18008d2b4  mov     [rbp+57h+pmkItem], r14
0x18008d2b8  mov     [rbp+57h+pPersistStream], r14
0x18008d2bc  mov     [rbp+57h+pszClass], r14
0x18008d2c0  mov     [rbp+57h+pszFile], r14
0x18008d2c4  mov     [rbp+57h+hgFree], r14
0x18008d2c8  movups  xmmword ptr [rbp+57h+clsid.Data1], xmm0
0x18008d2cc  call    cs:__imp_IsClipboardFormatAvailable
0x18008d2d3  nop     dword ptr [rax+rax+00h]
0x18008d2d8  movzx   edx, cs:?g_cfObjectLink@@3GA; ushort g_cfObjectLink
0x18008d2df  test    eax, eax
0x18008d2e1  jnz     short loc_18008D2EA
0x18008d2e3  movzx   edx, cs:?g_cfOwnerLink@@3GA; cf
0x18008d2ea  lea     rax, [rbp+57h+hgFree]
0x18008d2ee  mov     [rsp+0C0h+ppszItemA], r14; ppszItemA
0x18008d2f3  lea     r9, [rbp+57h+pszFile]; ppszFile
0x18008d2f7  mov     [rsp+0C0h+ppszItem], rax; ppszItem
0x18008d2fc  lea     r8, [rbp+57h+pszClass]; ppszClass
0x18008d300  call    ?GetAndTranslateOle1@CClipDataObject@@AEAAJIPEAPEAG00PEAPEAD@Z; CClipDataObject::GetAndTranslateOle1(uint,ushort * *,ushort * *,ushort * *,char * *)
0x18008d305  mov     r15, [rbp+57h+hgFree]
0x18008d309  mov     ebx, eax
0x18008d30b  test    eax, eax
0x18008d30d  jnz     loc_18008D47A
0x18008d313  mov     this, [rbp+57h+pszClass]
0x18008d317  lea     pmedium, [rbp+57h+clsid]
0x18008d31b  mov     r8d, r12d
0x18008d31e  call    cs:__imp_CLSIDFromOle1Class
0x18008d325  nop     dword ptr [rax+rax+00h]
0x18008d32a  mov     ebx, eax
0x18008d32c  test    eax, eax
0x18008d32e  jnz     loc_18008D47A
0x18008d334  mov     this, [rbp+57h+pszFile]; lpszPathName
0x18008d338  lea     r8, [rbp+57h+pmkFile]; ppmk
0x18008d33c  lea     pmedium, [rbp+57h+clsid]; rclsidOle1
0x18008d340  call    CreateOle1FileMoniker
0x18008d345  mov     ebx, eax
0x18008d347  test    eax, eax
0x18008d349  jnz     loc_18008D476
0x18008d34f  test    r15, r15
0x18008d352  jz      short loc_18008D39A
0x18008d354  cmp     [r15], r14w
0x18008d358  jz      short loc_18008D39A
0x18008d35a  lea     r8, [rbp+57h+pmkItem]; ppmk
0x18008d35e  mov     pmedium, r15; lpszItem
0x18008d361  lea     this, szDelim; "!"
0x18008d368  call    CreateItemMoniker
0x18008d36d  mov     rsi, [rbp+57h+pmkItem]
0x18008d371  mov     ebx, eax
0x18008d373  mov     rdi, [rbp+57h+pmkFile]
0x18008d377  test    eax, eax
0x18008d379  jnz     loc_18008D47A
0x18008d37f  lea     r8, [rbp+57h+pmkFinal]; ppmkComposite
0x18008d383  mov     pmedium, rsi; pmkRest
0x18008d386  mov     this, rdi; pmkFirst
0x18008d389  call    CreateGenericComposite
0x18008d38e  mov     ebx, eax
0x18008d390  test    eax, eax
0x18008d392  jnz     loc_18008D47A
0x18008d398  jmp     short loc_18008D3B1
0x18008d39a  mov     rdi, [rbp+57h+pmkFile]
0x18008d39e  mov     [rbp+57h+pmkFinal], rdi
0x18008d3a2  mov     this, rdi
0x18008d3a5  mov     rax, [rdi]
0x18008d3a8  mov     rax, [rax+8]
0x18008d3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d3b1  cmp     [r13+0], r12d
0x18008d3b5  lea     r8, [rbp+57h+pstm]; ppstm
0x18008d3b9  setnz   r14b
0x18008d3bd  xor     ecx, ecx; hGlobal
0x18008d3bf  mov     edx, r14d; fDeleteOnRelease
0x18008d3c2  call    cs:__imp_CreateStreamOnHGlobal
0x18008d3c9  nop     dword ptr [rax+rax+00h]
0x18008d3ce  mov     ebx, eax
0x18008d3d0  mov     r12d, r14d
0x18008d3d3  test    eax, eax
0x18008d3d5  jnz     loc_18008D47A
0x18008d3db  mov     this, [rbp+57h+pmkFinal]
0x18008d3df  lea     r8, [rbp+57h+pPersistStream]
0x18008d3e3  lea     pmedium, IID_IPersistStream
0x18008d3ea  mov     rax, [this]
0x18008d3ed  mov     rax, [rax]
0x18008d3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d3f5  mov     pmedium, [rbp+57h+pstm]; pStm
0x18008d3f9  mov     this, [rbp+57h+pPersistStream]; pPStm
0x18008d3fd  call    OleSaveToStream
0x18008d402  mov     ebx, eax
0x18008d404  test    eax, eax
0x18008d406  jnz     short loc_18008D47A
0x18008d408  mov     this, [rbp+57h+pstm]; pStm
0x18008d40c  lea     pmedium, [rbp+57h+clsid]; rclsid
0x18008d410  call    cs:__imp_WriteClassStm
0x18008d417  nop     dword ptr [rax+rax+00h]
0x18008d41c  mov     ebx, eax
0x18008d41e  test    eax, eax
0x18008d420  jnz     short loc_18008D47A
0x18008d422  cmp     dword ptr [r13+0], 4
0x18008d427  lea     r12, [r13+8]
0x18008d42b  mov     this, [rbp+57h+pstm]; pstm
0x18008d42f  jnz     short loc_18008D442
0x18008d431  mov     r13, [rbp+57h+var_88]
0x18008d435  mov     [r13+20h], this
0x18008d439  mov     [r12], this
0x18008d43d  mov     r12d, r14d
0x18008d440  jmp     short $errRtn_103
0x18008d442  mov     pmedium, r12; phglobal
0x18008d445  call    cs:__imp_GetHGlobalFromStream
0x18008d44c  nop     dword ptr [rax+rax+00h]
0x18008d451  mov     this, [rbp+57h+pstm]
0x18008d455  mov     ebx, eax
0x18008d457  mov     rax, [r12]
0x18008d45b  mov     r13, [rbp+57h+var_88]
0x18008d45f  mov     [r13+18h], rax
0x18008d463  mov     rax, [this]
0x18008d466  mov     rax, [rax+10h]
0x18008d46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d46f  and     [rbp+57h+pstm], 0
0x18008d474  jmp     short loc_18008D43D
0x18008d476  mov     rdi, [rbp+57h+pmkFile]
0x18008d47a  mov     r13, [rbp+57h+var_88]
0x18008d47e  mov     this, [rbp+57h+pPersistStream]
0x18008d482  test    this, this
0x18008d485  jz      short loc_18008D493
0x18008d487  mov     rax, [this]
0x18008d48a  mov     rax, [rax+10h]
0x18008d48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d493  test    rdi, rdi
0x18008d496  jz      short loc_18008D4A7
0x18008d498  mov     rax, [rdi]
0x18008d49b  mov     this, rdi
0x18008d49e  mov     rax, [rax+10h]
0x18008d4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d4a7  test    rsi, rsi
0x18008d4aa  jz      short loc_18008D4BB
0x18008d4ac  mov     rax, [rsi]
0x18008d4af  mov     this, rsi
0x18008d4b2  mov     rax, [rax+10h]
0x18008d4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d4bb  mov     this, [rbp+57h+pmkFinal]
0x18008d4bf  test    this, this
0x18008d4c2  jz      short loc_18008D4D0
0x18008d4c4  mov     rax, [this]
0x18008d4c7  mov     rax, [rax+10h]
0x18008d4cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d4d0  mov     this, [rbp+57h+pszClass]; pv
0x18008d4d4  test    this, this
0x18008d4d7  jz      short loc_18008D4E5
0x18008d4d9  call    cs:__imp_CoTaskMemFree
0x18008d4e0  nop     dword ptr [rax+rax+00h]
0x18008d4e5  mov     this, [rbp+57h+pszFile]; pv
0x18008d4e9  test    this, this
0x18008d4ec  jz      short loc_18008D4FA
0x18008d4ee  call    cs:__imp_CoTaskMemFree
0x18008d4f5  nop     dword ptr [rax+rax+00h]
0x18008d4fa  test    r15, r15
0x18008d4fd  jz      short loc_18008D50E
0x18008d4ff  mov     this, r15; pv
0x18008d502  call    cs:__imp_CoTaskMemFree
0x18008d509  nop     dword ptr [rax+rax+00h]
0x18008d50e  test    ebx, ebx
0x18008d510  jz      short loc_18008D55A
0x18008d512  mov     this, [rbp+57h+pstm]; pstm
0x18008d516  test    this, this
0x18008d519  jz      short loc_18008D55A
0x18008d51b  test    r12d, r12d
0x18008d51e  jnz     short loc_18008D545
0x18008d520  and     [rbp+57h+hgFree], 0
0x18008d525  lea     pmedium, [rbp+57h+hgFree]; phglobal
0x18008d529  call    cs:__imp_GetHGlobalFromStream
0x18008d530  nop     dword ptr [rax+rax+00h]
0x18008d535  mov     this, [rbp+57h+hgFree]; hMem
0x18008d539  call    cs:__imp_GlobalFree
0x18008d540  nop     dword ptr [rax+rax+00h]
0x18008d545  mov     this, [rbp+57h+pstm]
0x18008d549  mov     rax, [this]
0x18008d54c  mov     rax, [rax+10h]
0x18008d550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d555  and     qword ptr [r13+20h], 0
0x18008d55a  mov     eax, ebx
0x18008d55c  mov     this, [rbp+57h+var_38]
0x18008d560  xor     this, rsp; StackCookie
0x18008d563  call    __security_check_cookie
0x18008d568  mov     rbx, [rsp+0C0h+arg_10]
0x18008d570  add     rsp, 90h
0x18008d577  pop     r15
0x18008d579  pop     r14
0x18008d57b  pop     r13
0x18008d57d  pop     r12
0x18008d57f  pop     rdi
0x18008d580  pop     rsi
0x18008d581  pop     rbp
0x18008d582  retn
```
