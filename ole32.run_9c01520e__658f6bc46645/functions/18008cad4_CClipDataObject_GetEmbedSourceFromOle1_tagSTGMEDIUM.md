# CClipDataObject::GetEmbedSourceFromOle1(tagSTGMEDIUM *)

- ea: `0x18008cad4`
- end: `0x18008ce57`
- name: `?GetEmbedSourceFromOle1@CClipDataObject@@AEAAJPEAUtagSTGMEDIUM@@@Z`
- size: `899`
- prototype: `HRESULT __fastcall(CClipDataObject *this, tagSTGMEDIUM *pmedium)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008d7fc`

## callees

- `0x180017b84`
- `0x1800304d0`
- `0x180046460`
- `0x18008c7c8`
- `0x18008cad4`
- `0x1800ab800`
- `0x1800ab880`
- `0x1800ac328`
- `0x1800adda4`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x18008ce20`
- `KERNELBASE!GlobalFree` at `0x18008ce20`
- `USER32!RegisterClipboardFormatW` at `0x18008ccd5`
- `USER32!RegisterClipboardFormatW` at `0x18008ccd5`
- `USER32!GetClipboardData` at `0x18008cb8f`
- `USER32!GetClipboardData` at `0x18008cb8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008cda8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008cdbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008cda8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008cdbc`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x18008cb68`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x18008cb68`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18008cbb1`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18008cbb1`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x18008cd69`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x18008cdfb`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x18008cd69`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x18008cdfb`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18008cbce`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18008cc3f`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18008cbce`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18008cc3f`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x18008cbea`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x18008cbea`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x18008cc74`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x18008cc74`

## pseudocode

```c
__int64 __fastcall CClipDataObject::GetEmbedSourceFromOle1(CClipDataObject *this, tagSTGMEDIUM *pmedium)
{
  CClipDataObject *v3; // rsi
  int v4; // edi
  HRESULT v5; // eax
  char *v6; // r14
  HRESULT HGlobalFromILockBytes; // ebx
  BOOL v8; // esi
  HANDLE ClipboardData; // r15
  void *v10; // rcx
  HRESULT IsStorageILockBytes; // ebx
  IStorage *v12; // rdx
  int v13; // r8d
  unsigned int v14; // r9d
  CLIPFORMAT v15; // ax
  int v16; // r8d
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // rdi
  IStorage *v18; // rcx
  IStorage *v19; // rcx
  ILockBytes *v20; // rcx
  IStorage *pstg; // [rsp+38h] [rbp-48h] BYREF
  ILockBytes *plockbytes; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *pszClass; // [rsp+48h] [rbp-38h] BYREF
  void *hCopy; // [rsp+50h] [rbp-30h] BYREF
  char *pszItemA; // [rsp+58h] [rbp-28h] BYREF
  _GUID clsid; // [rsp+60h] [rbp-20h] BYREF

  pstg = 0;
  hCopy = 0;
  pszClass = 0;
  pszItemA = 0;
  plockbytes = 0;
  v3 = this;
  v4 = 1;
  clsid = 0;
  v5 = CClipDataObject::GetAndTranslateOle1(this, g_cfOwnerLink, &pszClass, 0, 0, &pszItemA);
  v6 = pszItemA;
  HGlobalFromILockBytes = v5;
  if ( !v5 )
  {
    HGlobalFromILockBytes = CLSIDFromOle1Class(pszClass, &clsid, 1);
    if ( !HGlobalFromILockBytes )
    {
      v8 = pmedium->tymed != 1;
      ClipboardData = GetClipboardData(g_cfNative);
      if ( !ClipboardData )
      {
        HGlobalFromILockBytes = -2147221037;
LABEL_24:
        v4 = v8;
        goto LABEL_25;
      }
      if ( CoIsOle1Class(&clsid) )
        goto LABEL_13;
      HGlobalFromILockBytes = CreateILockBytesOnHGlobal(ClipboardData, 0, &plockbytes);
      v4 = v8;
      if ( HGlobalFromILockBytes )
        goto LABEL_25;
      IsStorageILockBytes = StgIsStorageILockBytes(plockbytes);
      ((void (__fastcall *)(ILockBytes *))plockbytes->lpVtbl->Release)(plockbytes);
      plockbytes = 0;
      if ( IsStorageILockBytes )
      {
LABEL_13:
        HGlobalFromILockBytes = UtCreateStorageOnHGlobal(v10, v8, &pstg, &plockbytes);
        v4 = v8;
        if ( HGlobalFromILockBytes )
          goto LABEL_25;
        HGlobalFromILockBytes = ((__int64 (__fastcall *)(IStorage *, _GUID *))pstg->lpVtbl->SetClass)(pstg, &clsid);
        if ( HGlobalFromILockBytes )
          goto LABEL_25;
        v15 = RegisterClipboardFormatW(pszClass);
        HGlobalFromILockBytes = WriteFmtUserTypeStg(pstg, v15, pszClass);
        if ( HGlobalFromILockBytes )
          goto LABEL_25;
        HGlobalFromILockBytes = StSave10NativeData(pstg, ClipboardData, v16);
        if ( HGlobalFromILockBytes )
          goto LABEL_25;
        if ( v6 && *v6 )
          StSave10ItemName(pstg, v6);
      }
      else
      {
        hCopy = UtDupGlobal(ClipboardData, 0x2002u);
        if ( !hCopy )
        {
          HGlobalFromILockBytes = -2147024882;
          goto LABEL_25;
        }
        HGlobalFromILockBytes = CreateILockBytesOnHGlobal(hCopy, v8, &plockbytes);
        if ( HGlobalFromILockBytes )
          goto LABEL_25;
        hCopy = 0;
        HGlobalFromILockBytes = StgOpenStorageOnILockBytes(plockbytes, 0, 0x12u, 0, 0, &pstg);
        if ( HGlobalFromILockBytes < 0 )
          goto LABEL_25;
        UtDoStreamOperation(pstg, v12, v13, v14);
      }
      HGlobalFromILockBytes = ((__int64 (__fastcall *)(IStorage *, _QWORD))pstg->lpVtbl->Commit)(pstg, 0);
      v4 = v8;
      if ( !HGlobalFromILockBytes )
      {
        p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&pmedium->hBitmap;
        if ( pmedium->tymed == 8 )
        {
          v18 = pstg;
          this->m_pUnkOle1 = (IUnknown *)pstg;
          p_hBitmap->hBitmap = (HBITMAP)v18;
          v4 = v8;
          v3 = this;
          goto $errRtn_101;
        }
        HGlobalFromILockBytes = GetHGlobalFromILockBytes(plockbytes, &pmedium->hMetaFilePict);
        v19 = pstg;
        this->m_hOle1 = p_hBitmap->hBitmap;
        ((void (__fastcall *)(IStorage *))v19->lpVtbl->Release)(v19);
        pstg = 0;
        goto LABEL_24;
      }
LABEL_25:
      v3 = this;
    }
  }
$errRtn_101:
  if ( pszClass )
    CoTaskMemFree(pszClass);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( HGlobalFromILockBytes && pstg )
  {
    ((void (__fastcall *)(IStorage *))pstg->lpVtbl->Release)(pstg);
    v3->m_pUnkOle1 = 0;
  }
  v20 = plockbytes;
  if ( plockbytes )
  {
    if ( HGlobalFromILockBytes < 0 && !v4 )
    {
      GetHGlobalFromILockBytes(plockbytes, &hCopy);
      v20 = plockbytes;
    }
    ((void (__fastcall *)(ILockBytes *))v20->lpVtbl->Release)(v20);
  }
  if ( hCopy )
    GlobalFree(hCopy);
  return (unsigned int)HGlobalFromILockBytes;
}

```

## disassembly

```asm
0x18008cad4  mov     [rsp-28h+arg_10], rbx
0x18008cad9  mov     [rsp-28h+arg_18], rsi
0x18008cade  push    rbp
0x18008cadf  push    rdi
0x18008cae0  push    r13
0x18008cae2  push    r14
0x18008cae4  push    r15
0x18008cae6  mov     rbp, rsp
0x18008cae9  sub     rsp, 80h
0x18008caf0  mov     rax, cs:__security_cookie
0x18008caf7  xor     rax, rsp
0x18008cafa  mov     [rbp+var_10], rax
0x18008cafe  and     [rbp+pstg], 0
0x18008cb03  lea     rax, [rbp+pszItemA]
0x18008cb07  and     [rbp+hCopy], 0
0x18008cb0c  lea     r8, [rbp+pszClass]; ppszClass
0x18008cb10  and     [rbp+pszClass], 0
0x18008cb15  mov     r13, pmedium
0x18008cb18  movzx   edx, cs:?g_cfOwnerLink@@3GA; cf
0x18008cb1f  xorps   xmm0, xmm0
0x18008cb22  and     [rbp+pszItemA], 0
0x18008cb27  xor     r9d, r9d; ppszFile
0x18008cb2a  and     [rbp+plockbytes], 0
0x18008cb2f  mov     rsi, this
0x18008cb32  mov     [rsp+80h+ppszItemA], rax; ppszItemA
0x18008cb37  mov     edi, 1
0x18008cb3c  and     [rsp+80h+var_60], 0
0x18008cb42  mov     [rbp+var_50], this
0x18008cb46  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x18008cb4a  call    ?GetAndTranslateOle1@CClipDataObject@@AEAAJIPEAPEAG00PEAPEAD@Z; CClipDataObject::GetAndTranslateOle1(uint,ushort * *,ushort * *,ushort * *,char * *)
0x18008cb4f  mov     r14, [rbp+pszItemA]
0x18008cb53  mov     ebx, eax
0x18008cb55  test    eax, eax
0x18008cb57  jnz     $errRtn_101
0x18008cb5d  mov     this, [rbp+pszClass]
0x18008cb61  lea     pmedium, [rbp+clsid]
0x18008cb65  mov     r8d, edi
0x18008cb68  call    cs:__imp_CLSIDFromOle1Class
0x18008cb6f  nop     dword ptr [rax+rax+00h]
0x18008cb74  mov     ebx, eax
0x18008cb76  test    eax, eax
0x18008cb78  jnz     $errRtn_101
0x18008cb7e  movzx   ecx, cs:?g_cfNative@@3GA; uFormat
0x18008cb85  xor     esi, esi
0x18008cb87  cmp     [r13+0], edi
0x18008cb8b  setnz   sil
0x18008cb8f  call    cs:__imp_GetClipboardData
0x18008cb96  nop     dword ptr [rax+rax+00h]
0x18008cb9b  mov     r15, rax
0x18008cb9e  test    rax, rax
0x18008cba1  jnz     short loc_18008CBAD
0x18008cba3  mov     ebx, 800401D3h
0x18008cba8  jmp     loc_18008CD97
0x18008cbad  lea     this, [rbp+clsid]; rclsid
0x18008cbb1  call    cs:__imp_CoIsOle1Class
0x18008cbb8  nop     dword ptr [rax+rax+00h]
0x18008cbbd  test    eax, eax
0x18008cbbf  jnz     loc_18008CC98
0x18008cbc5  lea     r8, [rbp+plockbytes]; pplkbyt
0x18008cbc9  xor     edx, edx; fDeleteOnRelease
0x18008cbcb  mov     this, r15; hGlobal
0x18008cbce  call    cs:__imp_CreateILockBytesOnHGlobal
0x18008cbd5  nop     dword ptr [rax+rax+00h]
0x18008cbda  mov     ebx, eax
0x18008cbdc  mov     edi, esi
0x18008cbde  test    eax, eax
0x18008cbe0  jnz     loc_18008CD99
0x18008cbe6  mov     this, [rbp+plockbytes]; plkbyt
0x18008cbea  call    cs:__imp_StgIsStorageILockBytes
0x18008cbf1  nop     dword ptr [rax+rax+00h]
0x18008cbf6  mov     this, [rbp+plockbytes]
0x18008cbfa  mov     ebx, eax
0x18008cbfc  mov     pmedium, [this]
0x18008cbff  mov     rax, [pmedium+10h]
0x18008cc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc08  and     [rbp+plockbytes], 0
0x18008cc0d  test    ebx, ebx
0x18008cc0f  jnz     loc_18008CC98
0x18008cc15  mov     edx, 2002h; uiFlags
0x18008cc1a  mov     this, r15; hsrc
0x18008cc1d  call    ?UtDupGlobal@@YAPEAXPEAXI@Z; UtDupGlobal(void *,uint)
0x18008cc22  mov     [rbp+hCopy], rax
0x18008cc26  test    rax, rax
0x18008cc29  jnz     short loc_18008CC35
0x18008cc2b  mov     ebx, 8007000Eh
0x18008cc30  jmp     loc_18008CD99
0x18008cc35  mov     this, [rbp+hCopy]; hGlobal
0x18008cc39  lea     r8, [rbp+plockbytes]; pplkbyt
0x18008cc3d  mov     edx, esi; fDeleteOnRelease
0x18008cc3f  call    cs:__imp_CreateILockBytesOnHGlobal
0x18008cc46  nop     dword ptr [rax+rax+00h]
0x18008cc4b  mov     ebx, eax
0x18008cc4d  test    eax, eax
0x18008cc4f  jnz     loc_18008CD99
0x18008cc55  mov     this, [rbp+plockbytes]; plkbyt
0x18008cc59  lea     rax, [rbp+pstg]
0x18008cc5d  and     [rbp+hCopy], 0
0x18008cc62  lea     r8d, [rbx+12h]; grfMode
0x18008cc66  mov     [rsp+80h+ppszItemA], rax; ppstgOpen
0x18008cc6b  xor     r9d, r9d; snbExclude
0x18008cc6e  and     dword ptr [rsp+80h+var_60], ebx
0x18008cc72  xor     edx, edx; pstgPriority
0x18008cc74  call    cs:__imp_StgOpenStorageOnILockBytes
0x18008cc7b  nop     dword ptr [rax+rax+00h]
0x18008cc80  mov     ebx, eax
0x18008cc82  test    eax, eax
0x18008cc84  js      loc_18008CD99
0x18008cc8a  mov     this, [rbp+pstg]; pstgSrc
0x18008cc8e  call    UtDoStreamOperation
0x18008cc93  jmp     loc_18008CD27
0x18008cc98  lea     r9, [rbp+plockbytes]; hGlobal
0x18008cc9c  mov     edx, esi; ppStg
0x18008cc9e  lea     r8, [rbp+pstg]; ppILockBytes
0x18008cca2  call    ?UtCreateStorageOnHGlobal@@YAJPEAXHPEAPEAUIStorage@@PEAPEAUILockBytes@@@Z; UtCreateStorageOnHGlobal(void *,int,IStorage * *,ILockBytes * *)
0x18008cca7  mov     ebx, eax
0x18008cca9  mov     edi, esi
0x18008ccab  test    eax, eax
0x18008ccad  jnz     loc_18008CD99
0x18008ccb3  mov     this, [rbp+pstg]
0x18008ccb7  lea     pmedium, [rbp+clsid]
0x18008ccbb  mov     rax, [this]
0x18008ccbe  mov     rax, [rax+78h]
0x18008ccc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ccc7  mov     ebx, eax
0x18008ccc9  test    eax, eax
0x18008cccb  jnz     loc_18008CD99
0x18008ccd1  mov     this, [rbp+pszClass]; lpszFormat
0x18008ccd5  call    cs:__imp_RegisterClipboardFormatW
0x18008ccdc  nop     dword ptr [rax+rax+00h]
0x18008cce1  mov     r8, [rbp+pszClass]; lpszUserType
0x18008cce5  movzx   edx, ax; cf
0x18008cce8  mov     this, [rbp+pstg]; pstg
0x18008ccec  call    WriteFmtUserTypeStg
0x18008ccf1  mov     ebx, eax
0x18008ccf3  test    eax, eax
0x18008ccf5  jnz     loc_18008CD99
0x18008ccfb  mov     this, [rbp+pstg]; pstgSave
0x18008ccff  mov     pmedium, r15; hNative
0x18008cd02  call    ?StSave10NativeData@@YAJPEAUIStorage@@PEAXH@Z; StSave10NativeData(IStorage *,void *,int)
0x18008cd07  mov     ebx, eax
0x18008cd09  test    eax, eax
0x18008cd0b  jnz     loc_18008CD99
0x18008cd11  test    r14, r14
0x18008cd14  jz      short loc_18008CD27
0x18008cd16  cmp     [r14], al
0x18008cd19  jz      short loc_18008CD27
0x18008cd1b  mov     this, [rbp+pstg]; pstg
0x18008cd1f  mov     pmedium, r14; szItemNameAnsi
0x18008cd22  call    ?StSave10ItemName@@YAJPEAUIStorage@@PEBD@Z; StSave10ItemName(IStorage *,char const *)
0x18008cd27  mov     this, [rbp+pstg]
0x18008cd2b  xor     edx, edx
0x18008cd2d  mov     rax, [this]
0x18008cd30  mov     rax, [rax+48h]
0x18008cd34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cd39  mov     ebx, eax
0x18008cd3b  mov     edi, esi
0x18008cd3d  test    eax, eax
0x18008cd3f  jnz     short loc_18008CD99
0x18008cd41  cmp     dword ptr [r13+0], 8
0x18008cd46  lea     rdi, [r13+8]
0x18008cd4a  jnz     short loc_18008CD62
0x18008cd4c  mov     pmedium, [rbp+var_50]
0x18008cd50  mov     this, [rbp+pstg]
0x18008cd54  mov     [pmedium+20h], this
0x18008cd58  mov     [rdi], this
0x18008cd5b  mov     edi, esi
0x18008cd5d  mov     rsi, pmedium
0x18008cd60  jmp     short $errRtn_101
0x18008cd62  mov     this, [rbp+plockbytes]; plkbyt
0x18008cd66  mov     pmedium, rdi; phglobal
0x18008cd69  call    cs:__imp_GetHGlobalFromILockBytes
0x18008cd70  nop     dword ptr [rax+rax+00h]
0x18008cd75  mov     pmedium, [rbp+var_50]
0x18008cd79  mov     ebx, eax
0x18008cd7b  mov     rax, [rdi]
0x18008cd7e  mov     this, [rbp+pstg]
0x18008cd82  mov     [pmedium+18h], rax
0x18008cd86  mov     rax, [this]
0x18008cd89  mov     rax, [rax+10h]
0x18008cd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cd92  and     [rbp+pstg], 0
0x18008cd97  mov     edi, esi
0x18008cd99  mov     rsi, [rbp+var_50]
0x18008cd9d  cmp     [rbp+pszClass], 0
0x18008cda2  jz      short loc_18008CDB4
0x18008cda4  mov     this, [rbp+pszClass]; pv
0x18008cda8  call    cs:__imp_CoTaskMemFree
0x18008cdaf  nop     dword ptr [rax+rax+00h]
0x18008cdb4  test    r14, r14
0x18008cdb7  jz      short loc_18008CDC8
0x18008cdb9  mov     this, r14; pv
0x18008cdbc  call    cs:__imp_CoTaskMemFree
0x18008cdc3  nop     dword ptr [rax+rax+00h]
0x18008cdc8  test    ebx, ebx
0x18008cdca  jz      short loc_18008CDE6
0x18008cdcc  mov     this, [rbp+pstg]
0x18008cdd0  test    this, this
0x18008cdd3  jz      short loc_18008CDE6
0x18008cdd5  mov     rax, [this]
0x18008cdd8  mov     rax, [rax+10h]
0x18008cddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cde1  and     qword ptr [rsi+20h], 0
0x18008cde6  mov     this, [rbp+plockbytes]; plkbyt
0x18008cdea  test    this, this
0x18008cded  jz      short loc_18008CE17
0x18008cdef  test    ebx, ebx
0x18008cdf1  jns     short loc_18008CE0B
0x18008cdf3  test    edi, edi
0x18008cdf5  jnz     short loc_18008CE0B
0x18008cdf7  lea     pmedium, [rbp+hCopy]; phglobal
0x18008cdfb  call    cs:__imp_GetHGlobalFromILockBytes
0x18008ce02  nop     dword ptr [rax+rax+00h]
0x18008ce07  mov     this, [rbp+plockbytes]
0x18008ce0b  mov     rax, [this]
0x18008ce0e  mov     rax, [rax+10h]
0x18008ce12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ce17  mov     this, [rbp+hCopy]; hMem
0x18008ce1b  test    this, this
0x18008ce1e  jz      short loc_18008CE2C
0x18008ce20  call    cs:__imp_GlobalFree
0x18008ce27  nop     dword ptr [rax+rax+00h]
0x18008ce2c  mov     eax, ebx
0x18008ce2e  mov     this, [rbp+var_10]
0x18008ce32  xor     this, rsp; StackCookie
0x18008ce35  call    __security_check_cookie
0x18008ce3a  lea     r11, [rsp+80h+var_s0]
0x18008ce42  mov     rbx, [r11+40h]
0x18008ce46  mov     rsi, [r11+48h]
0x18008ce4a  mov     rsp, r11
0x18008ce4d  pop     r15
0x18008ce4f  pop     r14
0x18008ce51  pop     r13
0x18008ce53  pop     rdi
0x18008ce54  pop     rbp
0x18008ce55  retn
```
