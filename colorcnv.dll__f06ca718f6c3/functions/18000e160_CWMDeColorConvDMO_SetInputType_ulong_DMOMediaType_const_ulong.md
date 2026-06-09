# CWMDeColorConvDMO::SetInputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x18000e160`
- end: `0x18000e423`
- name: `?SetInputType@CWMDeColorConvDMO@@MEAAJKPEBU_DMOMediaType@@K@Z`
- size: `707`
- prototype: `HRESULT __fastcall(CWMDeColorConvDMO *this, int, const struct _DMOMediaType *, char)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180004414`
- `0x180004a68`
- `0x1800087f8`
- `0x18000a360`
- `0x18000cb10`
- `0x18000d6ec`
- `0x18000e160`
- `0x18000e514`
- `0x18000e5b8`
- `0x18000e8a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e390`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e390`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e408`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e408`
- `msdmo!MoCopyMediaType` at `0x18000e3be`
- `msdmo!MoCopyMediaType` at `0x18000e3be`
- `msdmo!MoFreeMediaType` at `0x18000e1a5`
- `msdmo!MoFreeMediaType` at `0x18000e3aa`
- `msdmo!MoFreeMediaType` at `0x18000e1a5`
- `msdmo!MoFreeMediaType` at `0x18000e3aa`

## pseudocode

```c
HRESULT __fastcall CWMDeColorConvDMO::SetInputType(
        CWMDeColorConvDMO *this,
        int a2,
        const struct _DMOMediaType *a3,
        char a4)
{
  HRESULT result; // eax
  CWMDeColorConvDMO *v7; // rcx
  const struct _DMOMediaType *v8; // rdx
  CWMDeColorConvDMO *v9; // rcx
  CWMDeColorConvDMO *v10; // rcx
  const struct tagBITMAPINFOHEADER *v11; // rbp
  CWMDeColorConvDMO *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  char *v16; // r14
  __int64 v17; // rdx
  int v18; // ecx
  int biHeight; // eax
  unsigned __int8 SubTypeIndex; // al
  bool v21; // zf
  __int64 v22; // rcx
  HRESULT v23; // esi
  struct _GUID Buf1; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 )
    return -2147220991;
  if ( (a4 & 2) != 0 )
  {
    if ( !*((_DWORD *)this + 2) )
      return 1;
    if ( (a4 & 1) == 0 )
    {
      *((_DWORD *)this + 2) = 0;
      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
    }
    return 0;
  }
  if ( !a3 )
    return -2147467261;
  Buf1 = *(struct _GUID *)((char *)a3 + 44);
  if ( (int)prvValidateMediaTypeSize(&Buf1) < 0 )
    return -2147220987;
  result = CWMDeColorConvDMO::CheckType1(v7, a3, (const struct _GUID *const *)&off_18002C080, 0x14u);
  if ( result < 0 )
    return result;
  result = CWMDeColorConvDMO::getVIH(
             v9,
             v8,
             *((struct tagVIDEOINFOHEADER **)this + 142),
             *((_DWORD *)this + 286),
             (struct tagVIDEOINFOHEADER **)this + 141);
  if ( result < 0 )
    return result;
  result = CWMDeColorConvDMO::setBIH(
             v10,
             *((const struct tagVIDEOINFOHEADER **)this + 141),
             (struct tagBITMAPINFOHEADER **)this + 147);
  if ( result < 0 )
    return result;
  v11 = (const struct tagBITMAPINFOHEADER *)*((_QWORD *)this + 147);
  if ( !(unsigned int)IsValidBitmapInfoHeader(v11) )
    return -2147024809;
  if ( (unsigned int)biCompressionFromSubtype((char *)a3 + 16) != v11->biCompression
    || !(unsigned int)ValidImageSizeForFOURCC(v11->biCompression, v11->biWidth, v11->biHeight) )
  {
    return -2147220987;
  }
  v13 = *(_QWORD *)((char *)a3 + 44) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
  if ( !v13 )
    v13 = *(_QWORD *)((char *)a3 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
  if ( v13 )
  {
    v14 = *(_QWORD *)((char *)a3 + 44) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    if ( !v14 )
      v14 = *(_QWORD *)((char *)a3 + 52) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
    if ( v14 )
    {
      v15 = *(_QWORD *)((char *)a3 + 44) - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
      if ( !v15 )
        v15 = *(_QWORD *)((char *)a3 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
      if ( v15 || *(_DWORD *)(*((_QWORD *)a3 + 10) + 28LL) == 2 )
        goto LABEL_32;
    }
    else if ( *(_DWORD *)(*((_QWORD *)a3 + 10) + 48LL) != 1 )
    {
      goto LABEL_32;
    }
    *((_DWORD *)this + 146) = 2;
  }
LABEL_32:
  if ( *((_DWORD *)this + 3) )
  {
    v16 = (char *)this + 1152;
    result = CWMDeColorConvDMO::getVIH(
               v12,
               (CWMDeColorConvDMO *)((char *)this + 104),
               *((struct tagVIDEOINFOHEADER **)this + 145),
               *((_DWORD *)this + 292),
               (struct tagVIDEOINFOHEADER **)this + 144);
    if ( result < 0 )
      return result;
    v17 = *(_QWORD *)v16;
    v18 = -*(_DWORD *)(*(_QWORD *)v16 + 56LL);
    if ( *(int *)(*(_QWORD *)v16 + 56LL) > 0 )
      v18 = *(_DWORD *)(v17 + 56);
    biHeight = -v11->biHeight;
    if ( v11->biHeight > 0 )
      biHeight = v11->biHeight;
    if ( biHeight != v18 || v11->biWidth != *(_DWORD *)(v17 + 52) )
      return -2147220987;
  }
  Buf1 = (struct _GUID)*((_OWORD *)a3 + 1);
  SubTypeIndex = GetSubTypeIndex(&Buf1);
  *((_DWORD *)this + 123) = SubTypeIndex;
  if ( SubTypeIndex == 255 )
    return -2147220987;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v21 = *((_DWORD *)this + 2) == 0;
  *((_DWORD *)this + 122) = 1;
  if ( !v21 )
  {
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
    *((_DWORD *)this + 2) = 0;
  }
  v23 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 16), (const DMO_MEDIA_TYPE *)a3);
  if ( v23 >= 0 )
  {
    *((_DWORD *)this + 2) = 1;
    if ( *((_QWORD *)this + 50) )
      CWMDeColorConvDMO::GenVideoCCDestroy(v22, (char *)this + 400, *((unsigned int *)this + 108));
    if ( *((_QWORD *)this + 52) )
      CWMDeColorConvDMO::GenVideoCCDestroy(v22, (char *)this + 416, *((unsigned int *)this + 109));
    v23 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  return v23;
}

```

## disassembly

```asm
0x18000e160  push    rbx
0x18000e162  push    rbp
0x18000e163  push    rsi
0x18000e164  push    r14
0x18000e166  push    r15
0x18000e168  sub     rsp, 40h
0x18000e16c  mov     rsi, r8
0x18000e16f  mov     rbx, rcx
0x18000e172  cmp     edx, 1
0x18000e175  jb      short loc_18000E181
0x18000e177  mov     eax, 80040201h
0x18000e17c  jmp     loc_18000E417
0x18000e181  test    r9b, 2
0x18000e185  jz      short loc_18000E1B7
0x18000e187  cmp     dword ptr [rcx+8], 0
0x18000e18b  jz      short loc_18000E1AD
0x18000e18d  test    r9b, 1
0x18000e191  jz      short loc_18000E19A
0x18000e193  xor     eax, eax
0x18000e195  jmp     loc_18000E417
0x18000e19a  mov     dword ptr [rcx+8], 0
0x18000e1a1  add     rcx, 10h; pmt
0x18000e1a5  call    cs:__imp_MoFreeMediaType
0x18000e1ab  jmp     short loc_18000E193
0x18000e1ad  mov     eax, 1
0x18000e1b2  jmp     loc_18000E417
0x18000e1b7  test    rsi, rsi
0x18000e1ba  jnz     short loc_18000E1C6
0x18000e1bc  mov     eax, 80004003h
0x18000e1c1  jmp     loc_18000E417
0x18000e1c6  movups  xmm0, xmmword ptr [r8+2Ch]
0x18000e1cb  mov     r8d, [r8+48h]
0x18000e1cf  lea     rcx, [rsp+68h+Buf1]; Buf1
0x18000e1d4  mov     rdx, [rsi+50h]
0x18000e1d8  movdqu  xmmword ptr [rsp+68h+Buf1.Data1], xmm0
0x18000e1de  call    prvValidateMediaTypeSize
0x18000e1e3  test    eax, eax
0x18000e1e5  js      loc_18000E412
0x18000e1eb  mov     r9d, 14h; unsigned int
0x18000e1f1  lea     r8, off_18002C080; struct _GUID **
0x18000e1f8  mov     rdx, rsi; struct _DMOMediaType *
0x18000e1fb  call    ?CheckType1@CWMDeColorConvDMO@@AEAAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z; CWMDeColorConvDMO::CheckType1(_DMOMediaType const *,_GUID const * const *,uint)
0x18000e200  test    eax, eax
0x18000e202  js      loc_18000E417
0x18000e208  mov     r9d, [rbx+478h]; unsigned int
0x18000e20f  lea     r14, [rbx+468h]
0x18000e216  mov     r8, [rbx+470h]; struct tagVIDEOINFOHEADER *
0x18000e21d  mov     [rsp+68h+var_48], r14; struct tagVIDEOINFOHEADER **
0x18000e222  call    ?getVIH@CWMDeColorConvDMO@@AEAAJPEBU_DMOMediaType@@PEAUtagVIDEOINFOHEADER@@KPEAPEAU3@@Z; CWMDeColorConvDMO::getVIH(_DMOMediaType const *,tagVIDEOINFOHEADER *,ulong,tagVIDEOINFOHEADER * *)
0x18000e227  test    eax, eax
0x18000e229  js      loc_18000E417
0x18000e22f  mov     rdx, [r14]; struct tagVIDEOINFOHEADER *
0x18000e232  lea     rbp, [rbx+498h]
0x18000e239  mov     r8, rbp; struct tagBITMAPINFOHEADER **
0x18000e23c  call    ?setBIH@CWMDeColorConvDMO@@AEAAJPEBUtagVIDEOINFOHEADER@@PEAPEAUtagBITMAPINFOHEADER@@@Z; CWMDeColorConvDMO::setBIH(tagVIDEOINFOHEADER const *,tagBITMAPINFOHEADER * *)
0x18000e241  test    eax, eax
0x18000e243  js      loc_18000E417
0x18000e249  mov     rbp, [rbp+0]
0x18000e24d  mov     rcx, rbp; struct tagBITMAPINFOHEADER *
0x18000e250  call    ?IsValidBitmapInfoHeader@@YAHPEBUtagBITMAPINFOHEADER@@@Z; IsValidBitmapInfoHeader(tagBITMAPINFOHEADER const *)
0x18000e255  test    eax, eax
0x18000e257  jnz     short loc_18000E263
0x18000e259  mov     eax, 80070057h
0x18000e25e  jmp     loc_18000E417
0x18000e263  lea     rcx, [rsi+10h]
0x18000e267  call    biCompressionFromSubtype
0x18000e26c  cmp     eax, [rbp+10h]
0x18000e26f  jnz     loc_18000E412
0x18000e275  mov     edx, [rbp+4]; int
0x18000e278  mov     r8d, [rbp+8]; int
0x18000e27c  mov     ecx, [rbp+10h]; unsigned int
0x18000e27f  call    ?ValidImageSizeForFOURCC@@YAHKJJ@Z; ValidImageSizeForFOURCC(ulong,long,long)
0x18000e284  test    eax, eax
0x18000e286  jz      loc_18000E412
0x18000e28c  mov     rax, [rsi+2Ch]
0x18000e290  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x18000e297  jnz     short loc_18000E2A4
0x18000e299  mov     rax, [rsi+34h]
0x18000e29d  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18000e2a4  test    rax, rax
0x18000e2a7  jz      short loc_18000E303
0x18000e2a9  mov     rax, [rsi+2Ch]
0x18000e2ad  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18000e2b4  jnz     short loc_18000E2C1
0x18000e2b6  mov     rax, [rsi+34h]
0x18000e2ba  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18000e2c1  test    rax, rax
0x18000e2c4  jz      short loc_18000E2EF
0x18000e2c6  mov     rax, [rsi+2Ch]
0x18000e2ca  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000e2d1  jnz     short loc_18000E2DE
0x18000e2d3  mov     rax, [rsi+34h]
0x18000e2d7  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18000e2de  test    rax, rax
0x18000e2e1  jnz     short loc_18000E303
0x18000e2e3  mov     rax, [rsi+50h]
0x18000e2e7  cmp     dword ptr [rax+1Ch], 2
0x18000e2eb  jnz     short loc_18000E2F9
0x18000e2ed  jmp     short loc_18000E303
0x18000e2ef  mov     rax, [rsi+50h]
0x18000e2f3  cmp     dword ptr [rax+30h], 1
0x18000e2f7  jnz     short loc_18000E303
0x18000e2f9  mov     dword ptr [rbx+248h], 2
0x18000e303  cmp     dword ptr [rbx+0Ch], 0
0x18000e307  jz      short loc_18000E35D
0x18000e309  mov     r9d, [rbx+490h]; unsigned int
0x18000e310  lea     r14, [rbx+480h]
0x18000e317  mov     r8, [rbx+488h]; struct tagVIDEOINFOHEADER *
0x18000e31e  lea     rdx, [rbx+68h]; struct _DMOMediaType *
0x18000e322  mov     [rsp+68h+var_48], r14; struct tagVIDEOINFOHEADER **
0x18000e327  call    ?getVIH@CWMDeColorConvDMO@@AEAAJPEBU_DMOMediaType@@PEAUtagVIDEOINFOHEADER@@KPEAPEAU3@@Z; CWMDeColorConvDMO::getVIH(_DMOMediaType const *,tagVIDEOINFOHEADER *,ulong,tagVIDEOINFOHEADER * *)
0x18000e32c  test    eax, eax
0x18000e32e  js      loc_18000E417
0x18000e334  mov     rdx, [r14]
0x18000e337  mov     eax, [rbp+8]
0x18000e33a  mov     ecx, [rdx+38h]
0x18000e33d  neg     ecx
0x18000e33f  cmovs   ecx, [rdx+38h]
0x18000e343  neg     eax
0x18000e345  cmovs   eax, [rbp+8]
0x18000e349  cmp     eax, ecx
0x18000e34b  jnz     loc_18000E412
0x18000e351  mov     eax, [rdx+34h]
0x18000e354  cmp     [rbp+4], eax
0x18000e357  jnz     loc_18000E412
0x18000e35d  movups  xmm0, xmmword ptr [rsi+10h]
0x18000e361  lea     rcx, [rsp+68h+Buf1]; struct _GUID
0x18000e366  movdqu  xmmword ptr [rsp+68h+Buf1.Data1], xmm0
0x18000e36c  call    ?GetSubTypeIndex@@YAEU_GUID@@@Z; GetSubTypeIndex(_GUID)
0x18000e371  movzx   ecx, al
0x18000e374  mov     [rbx+1ECh], ecx
0x18000e37a  cmp     ecx, 0FFh
0x18000e380  jz      loc_18000E412
0x18000e386  lea     rbp, [rbx+0D8h]
0x18000e38d  mov     rcx, rbp; lpCriticalSection
0x18000e390  call    cs:__imp_EnterCriticalSection
0x18000e396  cmp     dword ptr [rbx+8], 0
0x18000e39a  mov     dword ptr [rbx+1E8h], 1
0x18000e3a4  jz      short loc_18000E3B7
0x18000e3a6  lea     rcx, [rbx+10h]; pmt
0x18000e3aa  call    cs:__imp_MoFreeMediaType
0x18000e3b0  mov     dword ptr [rbx+8], 0
0x18000e3b7  mov     rdx, rsi; pmtSrc
0x18000e3ba  lea     rcx, [rbx+10h]; pmtDest
0x18000e3be  call    cs:__imp_MoCopyMediaType
0x18000e3c4  mov     esi, eax
0x18000e3c6  test    eax, eax
0x18000e3c8  js      short loc_18000E405
0x18000e3ca  lea     rdx, [rbx+190h]
0x18000e3d1  mov     dword ptr [rbx+8], 1
0x18000e3d8  cmp     qword ptr [rdx], 0
0x18000e3dc  jz      short loc_18000E3EA
0x18000e3de  mov     r8d, [rbx+1B0h]
0x18000e3e5  call    ?GenVideoCCDestroy@CWMDeColorConvDMO@@IEAAJPEAPEAXW4CC_OPS@@@Z; CWMDeColorConvDMO::GenVideoCCDestroy(void * *,CC_OPS)
0x18000e3ea  lea     rdx, [rbx+1A0h]
0x18000e3f1  cmp     qword ptr [rdx], 0
0x18000e3f5  jz      short loc_18000E403
0x18000e3f7  mov     r8d, [rbx+1B4h]
0x18000e3fe  call    ?GenVideoCCDestroy@CWMDeColorConvDMO@@IEAAJPEAPEAXW4CC_OPS@@@Z; CWMDeColorConvDMO::GenVideoCCDestroy(void * *,CC_OPS)
0x18000e403  xor     esi, esi
0x18000e405  mov     rcx, rbp; lpCriticalSection
0x18000e408  call    cs:__imp_LeaveCriticalSection
0x18000e40e  mov     eax, esi
0x18000e410  jmp     short loc_18000E417
0x18000e412  mov     eax, 80040205h
0x18000e417  add     rsp, 40h
0x18000e41b  pop     r15
0x18000e41d  pop     r14
0x18000e41f  pop     rsi
0x18000e420  pop     rbp
0x18000e421  pop     rbx
0x18000e422  retn
```
