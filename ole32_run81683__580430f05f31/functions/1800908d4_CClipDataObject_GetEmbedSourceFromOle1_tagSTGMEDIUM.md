# CClipDataObject::GetEmbedSourceFromOle1(tagSTGMEDIUM *)

- ea: `0x1800908d4`
- end: `0x180090bfb`
- name: `?GetEmbedSourceFromOle1@CClipDataObject@@AEAAJPEAUtagSTGMEDIUM@@@Z`
- size: `807`
- prototype: `HRESULT __fastcall(CClipDataObject *this, tagSTGMEDIUM *pmedium)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800914dc`

## callees

- `0x18002c4e4`
- `0x18002cbb0`
- `0x180052390`
- `0x180090608`
- `0x1800908d4`
- `0x1800a4afc`
- `0x1800a4b80`
- `0x1800a5550`
- `0x1800a6c2c`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x180090bce`
- `KERNELBASE!GlobalFree` at `0x180090bce`
- `USER32!RegisterClipboardFormatW` at `0x180090ab2`
- `USER32!RegisterClipboardFormatW` at `0x180090ab2`
- `USER32!GetClipboardData` at `0x180090992`
- `USER32!GetClipboardData` at `0x180090992`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090b64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090b72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090b64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090b72`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x180090972`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x180090972`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x1800909ae`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x1800909ae`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x180090b31`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x180090baf`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x180090b31`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x180090baf`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800909c5`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180090a27`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800909c5`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180090a27`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x1800909d9`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x1800909d9`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180090a59`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180090a59`

## pseudocode

```c
__int64 __fastcall CClipDataObject::GetEmbedSourceFromOle1(CClipDataObject *this, tagSTGMEDIUM *pmedium)
{
  BOOL v4; // edi
  HRESULT v5; // eax
  char *v6; // rsi
  int v7; // ebx
  HANDLE ClipboardData; // r14
  void *v9; // rcx
  HRESULT IsStorageILockBytes; // ebx
  IStorage *v11; // rdx
  int v12; // r8d
  unsigned int v13; // r9d
  CLIPFORMAT v14; // ax
  int v15; // r8d
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // r14
  IStorage *v17; // rcx
  HRESULT HGlobalFromILockBytes; // eax
  IStorage *v19; // rcx
  ILockBytes *v20; // rcx
  IStorage *pstg; // [rsp+30h] [rbp-40h] BYREF
  ILockBytes *plockbytes; // [rsp+38h] [rbp-38h] BYREF
  wchar_t *pszClass; // [rsp+40h] [rbp-30h] BYREF
  void *hCopy; // [rsp+48h] [rbp-28h] BYREF
  char *pszItemA; // [rsp+50h] [rbp-20h] BYREF
  _GUID clsid; // [rsp+58h] [rbp-18h] BYREF

  pstg = 0;
  hCopy = 0;
  pszClass = 0;
  pszItemA = 0;
  v4 = 1;
  clsid = 0;
  plockbytes = 0;
  v5 = CClipDataObject::GetAndTranslateOle1(this, g_cfOwnerLink, &pszClass, 0, 0, &pszItemA);
  v6 = pszItemA;
  v7 = v5;
  if ( v5 )
    goto $errRtn_128;
  v7 = CLSIDFromOle1Class(pszClass, &clsid, 1);
  if ( v7 )
    goto $errRtn_128;
  v4 = pmedium->tymed != 1;
  ClipboardData = GetClipboardData(g_cfNative);
  if ( !ClipboardData )
  {
    v7 = -2147221037;
    goto $errRtn_128;
  }
  if ( CoIsOle1Class(&clsid) )
    goto LABEL_13;
  v7 = CreateILockBytesOnHGlobal(ClipboardData, 0, &plockbytes);
  if ( v7 )
    goto $errRtn_128;
  IsStorageILockBytes = StgIsStorageILockBytes(plockbytes);
  ((void (__fastcall *)(ILockBytes *))plockbytes->lpVtbl->Release)(plockbytes);
  plockbytes = 0;
  if ( IsStorageILockBytes )
  {
LABEL_13:
    v7 = UtCreateStorageOnHGlobal(v9, v4, &pstg, &plockbytes);
    if ( v7 )
      goto $errRtn_128;
    v7 = ((__int64 (__fastcall *)(IStorage *, _GUID *))pstg->lpVtbl->SetClass)(pstg, &clsid);
    if ( v7 )
      goto $errRtn_128;
    v14 = RegisterClipboardFormatW(pszClass);
    v7 = WriteFmtUserTypeStg(pstg, v14, pszClass);
    if ( v7 )
      goto $errRtn_128;
    v7 = StSave10NativeData(pstg, ClipboardData, v15);
    if ( v7 )
      goto $errRtn_128;
    if ( v6 && *v6 )
      StSave10ItemName(pstg, v6);
    goto LABEL_20;
  }
  hCopy = UtDupGlobal(ClipboardData, 0x2002u);
  if ( !hCopy )
  {
    v7 = -2147024882;
    goto $errRtn_128;
  }
  v7 = CreateILockBytesOnHGlobal(hCopy, v4, &plockbytes);
  if ( !v7 )
  {
    hCopy = 0;
    v7 = StgOpenStorageOnILockBytes(plockbytes, 0, 0x12u, 0, 0, &pstg);
    if ( v7 >= 0 )
    {
      UtDoStreamOperation(pstg, v11, v12, v13);
LABEL_20:
      v7 = ((__int64 (__fastcall *)(IStorage *, _QWORD))pstg->lpVtbl->Commit)(pstg, 0);
      if ( !v7 )
      {
        p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&pmedium->hBitmap;
        if ( pmedium->tymed == 8 )
        {
          v17 = pstg;
          this->m_pUnkOle1 = (IUnknown *)pstg;
          p_hBitmap->hBitmap = (HBITMAP)v17;
        }
        else
        {
          HGlobalFromILockBytes = GetHGlobalFromILockBytes(plockbytes, &pmedium->hMetaFilePict);
          v19 = pstg;
          v7 = HGlobalFromILockBytes;
          this->m_hOle1 = p_hBitmap->hBitmap;
          ((void (__fastcall *)(IStorage *))v19->lpVtbl->Release)(v19);
          pstg = 0;
        }
      }
    }
  }
$errRtn_128:
  if ( pszClass )
    CoTaskMemFree(pszClass);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v7 && pstg )
  {
    ((void (__fastcall *)(IStorage *))pstg->lpVtbl->Release)(pstg);
    this->m_pUnkOle1 = 0;
  }
  v20 = plockbytes;
  if ( plockbytes )
  {
    if ( v7 < 0 && !v4 )
    {
      GetHGlobalFromILockBytes(plockbytes, &hCopy);
      v20 = plockbytes;
    }
    ((void (__fastcall *)(ILockBytes *))v20->lpVtbl->Release)(v20);
  }
  if ( hCopy )
    GlobalFree(hCopy);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800908d4  mov     r11, rsp
0x1800908d7  mov     [r11+18h], rbx
0x1800908db  mov     [r11+20h], rsi
0x1800908df  push    rbp
0x1800908e0  push    rdi
0x1800908e1  push    r12
0x1800908e3  push    r13
0x1800908e5  push    r14
0x1800908e7  mov     rbp, rsp
0x1800908ea  sub     rsp, 70h
0x1800908ee  mov     rax, cs:__security_cookie
0x1800908f5  xor     rax, rsp
0x1800908f8  mov     [rbp+var_8], rax
0x1800908fc  lea     rax, [rbp+pszItemA]
0x180090900  mov     [rbp+pstg], 0
0x180090908  mov     r13, pmedium
0x18009090b  mov     [r11-70h], rax
0x18009090f  movzx   edx, cs:?g_cfOwnerLink@@3GA; cf
0x180090916  lea     r8, [rbp+pszClass]; ppszClass
0x18009091a  xorps   xmm0, xmm0
0x18009091d  mov     qword ptr [r11-78h], 0
0x180090925  xor     r9d, r9d; ppszFile
0x180090928  mov     [rbp+hCopy], 0
0x180090930  mov     r12, this
0x180090933  mov     [rbp+pszClass], 0
0x18009093b  mov     [rbp+pszItemA], 0
0x180090943  mov     edi, 1
0x180090948  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x18009094c  mov     [rbp+plockbytes], 0
0x180090954  call    ?GetAndTranslateOle1@CClipDataObject@@AEAAJIPEAPEAG00PEAPEAD@Z; CClipDataObject::GetAndTranslateOle1(uint,ushort * *,ushort * *,ushort * *,char * *)
0x180090959  mov     rsi, [rbp+pszItemA]
0x18009095d  mov     ebx, eax
0x18009095f  test    eax, eax
0x180090961  jnz     $errRtn_128
0x180090967  mov     this, [rbp+pszClass]
0x18009096b  lea     pmedium, [rbp+clsid]
0x18009096f  mov     r8d, edi
0x180090972  call    cs:__imp_CLSIDFromOle1Class
0x180090978  mov     ebx, eax
0x18009097a  test    eax, eax
0x18009097c  jnz     $errRtn_128
0x180090982  cmp     [r13+0], edi
0x180090986  movzx   ecx, cs:?g_cfNative@@3GA; uFormat
0x18009098d  setnz   al
0x180090990  mov     edi, eax
0x180090992  call    cs:__imp_GetClipboardData
0x180090998  mov     r14, rax
0x18009099b  test    rax, rax
0x18009099e  jnz     short loc_1800909AA
0x1800909a0  mov     ebx, 800401D3h
0x1800909a5  jmp     $errRtn_128
0x1800909aa  lea     this, [rbp+clsid]; rclsid
0x1800909ae  call    cs:__imp_CoIsOle1Class
0x1800909b4  test    eax, eax
0x1800909b6  jnz     loc_180090A77
0x1800909bc  lea     r8, [rbp+plockbytes]; pplkbyt
0x1800909c0  xor     edx, edx; fDeleteOnRelease
0x1800909c2  mov     this, r14; hGlobal
0x1800909c5  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800909cb  mov     ebx, eax
0x1800909cd  test    eax, eax
0x1800909cf  jnz     $errRtn_128
0x1800909d5  mov     this, [rbp+plockbytes]; plkbyt
0x1800909d9  call    cs:__imp_StgIsStorageILockBytes
0x1800909df  mov     this, [rbp+plockbytes]
0x1800909e3  mov     ebx, eax
0x1800909e5  mov     pmedium, [this]
0x1800909e8  mov     rax, [pmedium+10h]
0x1800909ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800909f1  mov     [rbp+plockbytes], 0
0x1800909f9  test    ebx, ebx
0x1800909fb  jnz     short loc_180090A77
0x1800909fd  mov     edx, 2002h; uiFlags
0x180090a02  mov     this, r14; hsrc
0x180090a05  call    ?UtDupGlobal@@YAPEAXPEAXI@Z; UtDupGlobal(void *,uint)
0x180090a0a  mov     [rbp+hCopy], rax
0x180090a0e  test    rax, rax
0x180090a11  jnz     short loc_180090A1D
0x180090a13  mov     ebx, 8007000Eh
0x180090a18  jmp     $errRtn_128
0x180090a1d  mov     this, [rbp+hCopy]; hGlobal
0x180090a21  lea     r8, [rbp+plockbytes]; pplkbyt
0x180090a25  mov     edx, edi; fDeleteOnRelease
0x180090a27  call    cs:__imp_CreateILockBytesOnHGlobal
0x180090a2d  mov     ebx, eax
0x180090a2f  test    eax, eax
0x180090a31  jnz     $errRtn_128
0x180090a37  mov     this, [rbp+plockbytes]; plkbyt
0x180090a3b  lea     rax, [rbp+pstg]
0x180090a3f  mov     [rsp+70h+ppstgOpen], rax; ppstgOpen
0x180090a44  lea     r8d, [rbx+12h]; grfMode
0x180090a48  xor     r9d, r9d; snbExclude
0x180090a4b  mov     [rsp+70h+reserved], ebx; reserved
0x180090a4f  xor     edx, edx; pstgPriority
0x180090a51  mov     [rbp+hCopy], 0
0x180090a59  call    cs:__imp_StgOpenStorageOnILockBytes
0x180090a5f  mov     ebx, eax
0x180090a61  test    eax, eax
0x180090a63  js      $errRtn_128
0x180090a69  mov     this, [rbp+pstg]; pstgSrc
0x180090a6d  call    UtDoStreamOperation
0x180090a72  jmp     loc_180090AF9
0x180090a77  lea     r9, [rbp+plockbytes]; hGlobal
0x180090a7b  mov     edx, edi; ppStg
0x180090a7d  lea     r8, [rbp+pstg]; ppILockBytes
0x180090a81  call    ?UtCreateStorageOnHGlobal@@YAJPEAXHPEAPEAUIStorage@@PEAPEAUILockBytes@@@Z; UtCreateStorageOnHGlobal(void *,int,IStorage * *,ILockBytes * *)
0x180090a86  mov     ebx, eax
0x180090a88  test    eax, eax
0x180090a8a  jnz     $errRtn_128
0x180090a90  mov     this, [rbp+pstg]
0x180090a94  lea     pmedium, [rbp+clsid]
0x180090a98  mov     rax, [this]
0x180090a9b  mov     rax, [rax+78h]
0x180090a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090aa4  mov     ebx, eax
0x180090aa6  test    eax, eax
0x180090aa8  jnz     $errRtn_128
0x180090aae  mov     this, [rbp+pszClass]; lpszFormat
0x180090ab2  call    cs:__imp_RegisterClipboardFormatW
0x180090ab8  mov     r8, [rbp+pszClass]; lpszUserType
0x180090abc  movzx   edx, ax; cf
0x180090abf  mov     this, [rbp+pstg]; pstg
0x180090ac3  call    WriteFmtUserTypeStg
0x180090ac8  mov     ebx, eax
0x180090aca  test    eax, eax
0x180090acc  jnz     $errRtn_128
0x180090ad2  mov     this, [rbp+pstg]; pstgSave
0x180090ad6  mov     pmedium, r14; hNative
0x180090ad9  call    ?StSave10NativeData@@YAJPEAUIStorage@@PEAXH@Z; StSave10NativeData(IStorage *,void *,int)
0x180090ade  mov     ebx, eax
0x180090ae0  test    eax, eax
0x180090ae2  jnz     short $errRtn_128
0x180090ae4  test    rsi, rsi
0x180090ae7  jz      short loc_180090AF9
0x180090ae9  cmp     [rsi], al
0x180090aeb  jz      short loc_180090AF9
0x180090aed  mov     this, [rbp+pstg]; pstg
0x180090af1  mov     pmedium, rsi; szItemNameAnsi
0x180090af4  call    ?StSave10ItemName@@YAJPEAUIStorage@@PEBD@Z; StSave10ItemName(IStorage *,char const *)
0x180090af9  mov     this, [rbp+pstg]
0x180090afd  xor     edx, edx
0x180090aff  mov     rax, [this]
0x180090b02  mov     rax, [rax+48h]
0x180090b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090b0b  mov     ebx, eax
0x180090b0d  test    eax, eax
0x180090b0f  jnz     short $errRtn_128
0x180090b11  cmp     dword ptr [r13+0], 8
0x180090b16  lea     r14, [r13+8]
0x180090b1a  jnz     short loc_180090B2A
0x180090b1c  mov     this, [rbp+pstg]
0x180090b20  mov     [r12+20h], this
0x180090b25  mov     [r14], this
0x180090b28  jmp     short $errRtn_128
0x180090b2a  mov     this, [rbp+plockbytes]; plkbyt
0x180090b2e  mov     pmedium, r14; phglobal
0x180090b31  call    cs:__imp_GetHGlobalFromILockBytes
0x180090b37  mov     this, [rbp+pstg]
0x180090b3b  mov     ebx, eax
0x180090b3d  mov     rax, [r14]
0x180090b40  mov     [r12+18h], rax
0x180090b45  mov     rax, [this]
0x180090b48  mov     rax, [rax+10h]
0x180090b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090b51  mov     [rbp+pstg], 0
0x180090b59  cmp     [rbp+pszClass], 0
0x180090b5e  jz      short loc_180090B6A
0x180090b60  mov     this, [rbp+pszClass]; pv
0x180090b64  call    cs:__imp_CoTaskMemFree
0x180090b6a  test    rsi, rsi
0x180090b6d  jz      short loc_180090B78
0x180090b6f  mov     this, rsi; pv
0x180090b72  call    cs:__imp_CoTaskMemFree
0x180090b78  test    ebx, ebx
0x180090b7a  jz      short loc_180090B9A
0x180090b7c  mov     this, [rbp+pstg]
0x180090b80  test    this, this
0x180090b83  jz      short loc_180090B9A
0x180090b85  mov     rax, [this]
0x180090b88  mov     rax, [rax+10h]
0x180090b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090b91  mov     qword ptr [r12+20h], 0
0x180090b9a  mov     this, [rbp+plockbytes]; plkbyt
0x180090b9e  test    this, this
0x180090ba1  jz      short loc_180090BC5
0x180090ba3  test    ebx, ebx
0x180090ba5  jns     short loc_180090BB9
0x180090ba7  test    edi, edi
0x180090ba9  jnz     short loc_180090BB9
0x180090bab  lea     pmedium, [rbp+hCopy]; phglobal
0x180090baf  call    cs:__imp_GetHGlobalFromILockBytes
0x180090bb5  mov     this, [rbp+plockbytes]
0x180090bb9  mov     rax, [this]
0x180090bbc  mov     rax, [rax+10h]
0x180090bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090bc5  mov     this, [rbp+hCopy]; hMem
0x180090bc9  test    this, this
0x180090bcc  jz      short loc_180090BD4
0x180090bce  call    cs:__imp_GlobalFree
0x180090bd4  mov     eax, ebx
0x180090bd6  mov     this, [rbp+var_8]
0x180090bda  xor     this, rsp; StackCookie
0x180090bdd  call    __security_check_cookie
0x180090be2  lea     r11, [rsp+70h+var_s0]
0x180090be7  mov     rbx, [r11+40h]
0x180090beb  mov     rsi, [r11+48h]
0x180090bef  mov     rsp, r11
0x180090bf2  pop     r14
0x180090bf4  pop     r13
0x180090bf6  pop     r12
0x180090bf8  pop     rdi
0x180090bf9  pop     rbp
0x180090bfa  retn
```
