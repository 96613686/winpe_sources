# FID_Create(ulong,ulong,ushort const *,ushort const *,ushort const *,FID_FILEINFO &,uint,ushort const * *,_ITEMIDLIST * *)

- ea: `0x1800220b4`
- end: `0x180022348`
- name: `?FID_Create@@YAJKKPEBG00AEAUFID_FILEINFO@@IPEAPEBGPEAPEFAU_ITEMIDLIST@@@Z`
- size: `660`
- prototype: `__int64 __fastcall(unsigned int, __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, const FILETIME *, unsigned int cElems, const unsigned __int16 **prgsz)`
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800224ec`
- `0x180022d00`
- `0x180022e1c`
- `0x180022f20`

## callees

- `0x180006624`
- `0x1800139f4`
- `0x180021c00`
- `0x1800220b4`
- `0x18002a16c`
- `0x18002ce50`
- `0x18002ce90`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `PROPSYS!InitPropVariantFromFileTime` at `0x180022277`
- `PROPSYS!InitPropVariantFromFileTime` at `0x180022277`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800221b2`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800221b2`
- `PROPSYS!InitPropVariantFromStringVector` at `0x1800221e1`
- `PROPSYS!InitPropVariantFromStringVector` at `0x1800221e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002220d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800222a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002220d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800222a3`

## pseudocode

```c
__int64 __fastcall FID_Create(
        unsigned int a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        const FILETIME *a6,
        unsigned int cElems,
        const unsigned __int16 **prgsz)
{
  unsigned __int64 v11; // r11
  HRESULT v12; // ebx
  __int64 v13; // rdx
  unsigned int v14; // r8d
  __int64 i; // rbx
  bool v16; // al
  void *ppv; // [rsp+20h] [rbp-E0h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h]
  unsigned int Src; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v24[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[1040]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v26[384]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v27[384]; // [rsp+7A0h] [rbp+6A0h] BYREF
  _BYTE v28[144]; // [rsp+AA0h] [rbp+9A0h] BYREF
  unsigned __int16 v29[32]; // [rsp+B30h] [rbp+A30h] BYREF

  v20 = 0;
  *(_OWORD *)ppropvar = 0;
  memset_0(&Src, 0, 0xAECu);
  Src = a1;
  ppv = 0;
  v23 = 0;
  memset_0(v25, 0, sizeof(v25));
  memset_0(v28, 0, 0x80u);
  StringCchCopyW(v26, 0x180u, a3);
  if ( a5 )
    StringCchCopyW(v24, 0x20u, a5);
  if ( a4 )
    StringCchCopyW(v27, v11, a4);
  v12 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( v12 >= 0 )
  {
    v20 = 0;
    *(_OWORD *)ppropvar = 0;
    if ( InitPropVariantFromStringVector(prgsz, cElems, ppropvar) >= 0 )
    {
      (*(void (__fastcall **)(void *, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
        ppv,
        &PKEY_Fonts_FileNames,
        ppropvar);
      PropVariantClear(ppropvar);
    }
    IPropertyStore_SetUInt64(ppv, v13, a6->dwLowDateTime + ((unsigned __int64)a6->dwHighDateTime << 32));
    v29[0] = 0;
    FontTypeStringFromFontType(a1, v29, v14);
    IPropertyStore_SetString(ppv, &PKEY_Fonts_Type, v29);
    IPropertyStore_SetString(ppv, &PKEY_ItemNameDisplay, a3);
    if ( InitPropVariantFromFileTime(a6 + 1, ppropvar) >= 0 )
    {
      (*(void (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
        ppv,
        &PKEY_DateModified,
        ppropvar);
      PropVariantClear(ppropvar);
    }
    for ( i = 0; (unsigned int)i < cElems; i = (unsigned int)(i + 1) )
    {
      if ( !PathIsInFontsDirectory(0, prgsz[i]) )
      {
        v16 = PathIsInFontsDirectory(1, prgsz[i]);
        v22 = 1;
        if ( !v16 )
          continue;
      }
      v22 = 0;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 56LL))(ppv);
    v12 = CItemIDFactory<FID,156830041>::s_CreateItemID(&Src);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800220b4  mov     [rsp-8+arg_8], rbx
0x1800220b9  push    rbp
0x1800220ba  push    rsi
0x1800220bb  push    rdi
0x1800220bc  push    r12
0x1800220be  push    r13
0x1800220c0  push    r14
0x1800220c2  push    r15
0x1800220c4  lea     rbp, [rsp-0A80h]
0x1800220cc  sub     rsp, 0B80h
0x1800220d3  mov     rax, cs:__security_cookie
0x1800220da  xor     rax, rsp
0x1800220dd  mov     [rbp+0AB0h+var_40], rax
0x1800220e4  mov     rsi, [rbp+0AB0h+arg_28]
0x1800220eb  mov     r12, r8
0x1800220ee  mov     rdi, [rbp+0AB0h+arg_20]
0x1800220f5  mov     r15d, ecx
0x1800220f8  mov     r14, [rbp+0AB0h+prgsz]
0x1800220ff  lea     rcx, [rsp+0BB0h+Src]; void *
0x180022104  mov     r13, [rbp+0AB0h+arg_40]
0x18002210b  xorps   xmm0, xmm0
0x18002210e  xor     eax, eax
0x180022110  mov     r8d, 0AECh; Size
0x180022116  xor     edx, edx; Val
0x180022118  mov     [rsp+0BB0h+var_B78], rax
0x18002211d  movups  xmmword ptr [rsp+0BB0h+ppropvar], xmm0
0x180022122  mov     rbx, r9
0x180022125  call    memset_0
0x18002212a  xor     eax, eax
0x18002212c  mov     [rsp+0BB0h+Src], r15d
0x180022131  xor     edx, edx; Val
0x180022133  mov     [rsp+0BB0h+ppv], rax
0x180022138  mov     r8d, 410h; Size
0x18002213e  mov     [rsp+0BB0h+var_B68], rax
0x180022143  lea     rcx, [rbp+0AB0h+var_B20]; void *
0x180022147  call    memset_0
0x18002214c  xor     edx, edx; Val
0x18002214e  lea     rcx, [rbp+0AB0h+var_110]; void *
0x180022155  mov     r8d, 80h; Size
0x18002215b  call    memset_0
0x180022160  mov     r11d, 180h
0x180022166  lea     rcx, [rbp+0AB0h+var_710]; unsigned __int16 *
0x18002216d  mov     edx, r11d; unsigned __int64
0x180022170  mov     r8, r12; unsigned __int16 *
0x180022173  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022178  test    rdi, rdi
0x18002217b  jz      short loc_18002218F
0x18002217d  mov     r8, rdi; unsigned __int16 *
0x180022180  lea     rcx, [rsp+0BB0h+var_B60]; unsigned __int16 *
0x180022185  mov     edx, 20h ; ' '; unsigned __int64
0x18002218a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002218f  test    rbx, rbx
0x180022192  jz      short loc_1800221A6
0x180022194  mov     r8, rbx; unsigned __int16 *
0x180022197  lea     rcx, [rbp+0AB0h+var_410]; unsigned __int16 *
0x18002219e  mov     rdx, r11; unsigned __int64
0x1800221a1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800221a6  lea     rdx, [rsp+0BB0h+ppv]; ppv
0x1800221ab  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800221b2  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800221b8  mov     ebx, eax
0x1800221ba  test    eax, eax
0x1800221bc  js      loc_18002231C
0x1800221c2  mov     edi, [rbp+0AB0h+cElems]
0x1800221c8  lea     r8, [rsp+0BB0h+ppropvar]; ppropvar
0x1800221cd  xorps   xmm0, xmm0
0x1800221d0  xor     eax, eax
0x1800221d2  mov     edx, edi; cElems
0x1800221d4  mov     [rsp+0BB0h+var_B78], rax
0x1800221d9  mov     rcx, r14; prgsz
0x1800221dc  movups  xmmword ptr [rsp+0BB0h+ppropvar], xmm0
0x1800221e1  call    cs:__imp_InitPropVariantFromStringVector
0x1800221e7  test    eax, eax
0x1800221e9  js      short loc_180022213
0x1800221eb  mov     rcx, [rsp+0BB0h+ppv]
0x1800221f0  lea     r8, [rsp+0BB0h+ppropvar]
0x1800221f5  lea     rdx, PKEY_Fonts_FileNames
0x1800221fc  mov     rax, [rcx]
0x1800221ff  mov     rax, [rax+30h]
0x180022203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022208  lea     rcx, [rsp+0BB0h+ppropvar]; pvar
0x18002220d  call    cs:__imp_PropVariantClear
0x180022213  mov     r8d, [rsi+4]
0x180022217  mov     eax, [rsi]
0x180022219  mov     rcx, [rsp+0BB0h+ppv]
0x18002221e  shl     r8, 20h
0x180022222  add     r8, rax
0x180022225  call    IPropertyStore_SetUInt64
0x18002222a  xor     eax, eax
0x18002222c  lea     rdx, [rbp+0AB0h+var_80]; unsigned __int16 *
0x180022233  mov     ecx, r15d; unsigned int
0x180022236  mov     [rbp+0AB0h+var_80], ax
0x18002223d  call    ?FontTypeStringFromFontType@@YAXKPEAGK@Z; FontTypeStringFromFontType(ulong,ushort *,ulong)
0x180022242  mov     rcx, [rsp+0BB0h+ppv]
0x180022247  lea     r8, [rbp+0AB0h+var_80]
0x18002224e  lea     rdx, PKEY_Fonts_Type
0x180022255  call    IPropertyStore_SetString
0x18002225a  mov     rcx, [rsp+0BB0h+ppv]
0x18002225f  lea     rdx, PKEY_ItemNameDisplay
0x180022266  mov     r8, r12
0x180022269  call    IPropertyStore_SetString
0x18002226e  lea     rcx, [rsi+8]; pftIn
0x180022272  lea     rdx, [rsp+0BB0h+ppropvar]; ppropvar
0x180022277  call    cs:__imp_InitPropVariantFromFileTime
0x18002227d  test    eax, eax
0x18002227f  js      short loc_1800222A9
0x180022281  mov     rcx, [rsp+0BB0h+ppv]
0x180022286  lea     r8, [rsp+0BB0h+ppropvar]
0x18002228b  lea     rdx, PKEY_DateModified
0x180022292  mov     rax, [rcx]
0x180022295  mov     rax, [rax+30h]
0x180022299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002229e  lea     rcx, [rsp+0BB0h+ppropvar]; pvar
0x1800222a3  call    cs:__imp_PropVariantClear
0x1800222a9  xor     ebx, ebx
0x1800222ab  test    edi, edi
0x1800222ad  jz      short loc_1800222E6
0x1800222af  lea     r15d, [rbx+1]
0x1800222b3  mov     rdx, [r14+rbx*8]; unsigned __int16 *
0x1800222b7  xor     ecx, ecx; int
0x1800222b9  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x1800222be  test    al, al
0x1800222c0  jnz     short loc_1800222D7
0x1800222c2  mov     rdx, [r14+rbx*8]; unsigned __int16 *
0x1800222c6  mov     ecx, r15d; int
0x1800222c9  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x1800222ce  mov     [rsp+0BB0h+var_B6C], r15d
0x1800222d3  test    al, al
0x1800222d5  jz      short loc_1800222DF
0x1800222d7  mov     [rsp+0BB0h+var_B6C], 0
0x1800222df  add     ebx, r15d
0x1800222e2  cmp     ebx, edi
0x1800222e4  jb      short loc_1800222B3
0x1800222e6  mov     rcx, [rsp+0BB0h+ppv]
0x1800222eb  mov     rax, [rcx]
0x1800222ee  mov     rax, [rax+38h]
0x1800222f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222f7  mov     rdx, [rsp+0BB0h+ppv]
0x1800222fc  lea     rcx, [rsp+0BB0h+Src]; Src
0x180022301  mov     r8, r13
0x180022304  call    ?s_CreateItemID@?$CItemIDFactory@UFID@@$0JFJAJFJ@@@SAJPEFBUFID@@PEAUIPropertyStore@@PEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@@Z; CItemIDFactory<FID,156830041>::s_CreateItemID(FID const *,IPropertyStore *,_ITEMIDLIST * *,IMalloc *)
0x180022309  mov     rcx, [rsp+0BB0h+ppv]
0x18002230e  mov     ebx, eax
0x180022310  mov     rax, [rcx]
0x180022313  mov     rax, [rax+10h]
0x180022317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002231c  mov     eax, ebx
0x18002231e  mov     rcx, [rbp+0AB0h+var_40]
0x180022325  xor     rcx, rsp; StackCookie
0x180022328  call    __security_check_cookie
0x18002232d  mov     rbx, [rsp+0BB0h+arg_8]
0x180022335  add     rsp, 0B80h
0x18002233c  pop     r15
0x18002233e  pop     r14
0x180022340  pop     r13
0x180022342  pop     r12
0x180022344  pop     rdi
0x180022345  pop     rsi
0x180022346  pop     rbp
0x180022347  retn
```
