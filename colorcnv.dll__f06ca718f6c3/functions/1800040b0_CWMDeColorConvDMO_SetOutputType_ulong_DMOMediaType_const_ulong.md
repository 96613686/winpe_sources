# CWMDeColorConvDMO::SetOutputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x1800040b0`
- end: `0x18000440b`
- name: `?SetOutputType@CWMDeColorConvDMO@@MEAAJKPEBU_DMOMediaType@@K@Z`
- size: `859`
- prototype: `HRESULT __fastcall(CWMDeColorConvDMO *this, int, const DMO_MEDIA_TYPE *, char)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800040b0`
- `0x180004414`
- `0x180004a68`
- `0x18000a360`
- `0x18000cb10`
- `0x18000d6ec`
- `0x18000e514`
- `0x18000e5b8`
- `0x18000e8a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004377`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004377`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043f0`
- `msdmo!MoCopyMediaType` at `0x18000439b`
- `msdmo!MoCopyMediaType` at `0x18000439b`
- `msdmo!MoFreeMediaType` at `0x1800040f3`
- `msdmo!MoFreeMediaType` at `0x180004387`
- `msdmo!MoFreeMediaType` at `0x1800040f3`
- `msdmo!MoFreeMediaType` at `0x180004387`

## pseudocode

```c
HRESULT __fastcall CWMDeColorConvDMO::SetOutputType(CWMDeColorConvDMO *this, int a2, const DMO_MEDIA_TYPE *a3, char a4)
{
  HRESULT result; // eax
  unsigned int cbFormat; // esi
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  CWMDeColorConvDMO *v15; // rcx
  struct _GUID *p_subtype; // rbp
  GUID *v17; // rdx
  __int64 v18; // rax
  CWMDeColorConvDMO *v19; // rcx
  const struct tagBITMAPINFOHEADER *v20; // rsi
  CWMDeColorConvDMO *v21; // rcx
  char *v22; // r14
  __int64 v23; // rdx
  int v24; // ecx
  int biHeight; // eax
  unsigned __int8 SubTypeIndex; // al
  __int64 v27; // rcx
  HRESULT v28; // edi
  struct _GUID Buf1; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 )
    return -2147220991;
  if ( (a4 & 2) != 0 )
  {
    if ( *((_DWORD *)this + 3) )
    {
      if ( (a4 & 1) == 0 )
      {
        *((_DWORD *)this + 3) = 0;
        MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
      }
      return 0;
    }
    return 1;
  }
  else
  {
    if ( !a3 )
      return -2147467261;
    cbFormat = a3->cbFormat;
    Buf1 = a3->formattype;
    if ( (int)prvValidateMediaTypeSize(&Buf1) < 0 )
      return -2147220987;
    v8 = *(_QWORD *)&a3->majortype.Data1 - *(_QWORD *)&MEDIATYPE_Video.Data1;
    if ( *(_QWORD *)&a3->majortype.Data1 == *(_QWORD *)&MEDIATYPE_Video.Data1 )
      v8 = *(_QWORD *)a3->majortype.Data4 - *(_QWORD *)MEDIATYPE_Video.Data4;
    if ( v8 )
      return -2147220987;
    v9 = *(_QWORD *)&a3->formattype.Data1 - *(_QWORD *)&FORMAT_VideoInfo.Data1;
    if ( !v9 )
      v9 = *(_QWORD *)a3->formattype.Data4 - *(_QWORD *)FORMAT_VideoInfo.Data4;
    if ( v9 )
    {
      v10 = *(_QWORD *)&a3->formattype.Data1 - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
      if ( !v10 )
        v10 = *(_QWORD *)a3->formattype.Data4 - *(_QWORD *)FORMAT_VideoInfo2.Data4;
      if ( v10 )
      {
        v11 = *(_QWORD *)&a3->formattype.Data1 - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
        if ( !v11 )
          v11 = *(_QWORD *)a3->formattype.Data4 - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
        if ( v11 )
          return -2147220987;
      }
    }
    v12 = *(_QWORD *)&a3->formattype.Data1 - *(_QWORD *)&FORMAT_VideoInfo.Data1;
    if ( !v12 )
      v12 = *(_QWORD *)a3->formattype.Data4 - *(_QWORD *)FORMAT_VideoInfo.Data4;
    if ( !v12 && cbFormat < 0x58 )
      return -2147220987;
    v13 = *(_QWORD *)&a3->formattype.Data1 - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    if ( !v13 )
      v13 = *(_QWORD *)a3->formattype.Data4 - *(_QWORD *)FORMAT_VideoInfo2.Data4;
    if ( !v13 && cbFormat < 0x70 )
      return -2147220987;
    v14 = *(_QWORD *)&a3->formattype.Data1 - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
    if ( !v14 )
      v14 = *(_QWORD *)a3->formattype.Data4 - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
    if ( !v14 && cbFormat < 0xB0 || !a3->pbFormat )
      return -2147220987;
    v15 = 0;
    p_subtype = &a3->subtype;
    while ( 1 )
    {
      v17 = off_18002C000[(_QWORD)v15];
      v18 = *(_QWORD *)&v17->Data1 - *(_QWORD *)&p_subtype->Data1;
      if ( *(_QWORD *)&v17->Data1 == *(_QWORD *)&p_subtype->Data1 )
        v18 = *(_QWORD *)v17->Data4 - *(_QWORD *)a3->subtype.Data4;
      if ( !v18 )
        break;
      v15 = (CWMDeColorConvDMO *)(unsigned int)((_DWORD)v15 + 1);
      if ( (unsigned int)v15 >= 0x10 )
      {
        if ( (_DWORD)v15 == 16 )
          return -2147220987;
        break;
      }
    }
    result = CWMDeColorConvDMO::getVIH(
               v15,
               (const struct _DMOMediaType *)a3,
               *((struct tagVIDEOINFOHEADER **)this + 145),
               *((_DWORD *)this + 292),
               (struct tagVIDEOINFOHEADER **)this + 144);
    if ( result < 0 )
      return result;
    result = CWMDeColorConvDMO::setBIH(
               v19,
               *((const struct tagVIDEOINFOHEADER **)this + 144),
               (struct tagBITMAPINFOHEADER **)this + 148);
    if ( result < 0 )
      return result;
    v20 = (const struct tagBITMAPINFOHEADER *)*((_QWORD *)this + 148);
    if ( !(unsigned int)IsValidBitmapInfoHeader(v20) )
      return -2147024809;
    if ( (unsigned int)biCompressionFromSubtype(&a3->subtype) != v20->biCompression
      || !(unsigned int)ValidImageSizeForFOURCC(v20->biCompression, v20->biWidth, v20->biHeight) )
    {
      return -2147220987;
    }
    if ( *((_DWORD *)this + 2) )
    {
      v22 = (char *)this + 1128;
      result = CWMDeColorConvDMO::getVIH(
                 v21,
                 (CWMDeColorConvDMO *)((char *)this + 16),
                 *((struct tagVIDEOINFOHEADER **)this + 142),
                 *((_DWORD *)this + 286),
                 (struct tagVIDEOINFOHEADER **)this + 141);
      if ( result < 0 )
        return result;
      v23 = *(_QWORD *)v22;
      v24 = -*(_DWORD *)(*(_QWORD *)v22 + 56LL);
      if ( *(int *)(*(_QWORD *)v22 + 56LL) > 0 )
        v24 = *(_DWORD *)(v23 + 56);
      biHeight = -v20->biHeight;
      if ( v20->biHeight > 0 )
        biHeight = v20->biHeight;
      if ( v24 != biHeight || *(_DWORD *)(v23 + 52) != v20->biWidth )
        return -2147220987;
    }
    Buf1 = *p_subtype;
    SubTypeIndex = GetSubTypeIndex(&Buf1);
    *((_DWORD *)this + 124) = SubTypeIndex;
    if ( SubTypeIndex == 255 )
      return -2147220987;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    if ( *((_DWORD *)this + 3) )
    {
      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
      *((_DWORD *)this + 3) = 0;
    }
    v28 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 104), a3);
    if ( v28 >= 0 )
    {
      *((_DWORD *)this + 3) = 1;
      if ( *((_QWORD *)this + 50) )
        CWMDeColorConvDMO::GenVideoCCDestroy(v27, (char *)this + 400, *((unsigned int *)this + 108));
      if ( *((_QWORD *)this + 52) )
        CWMDeColorConvDMO::GenVideoCCDestroy(v27, (char *)this + 416, *((unsigned int *)this + 109));
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
      return 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    return v28;
  }
}

```

## disassembly

```asm
0x1800040b0  push    rbx
0x1800040b2  push    rbp
0x1800040b3  push    rsi
0x1800040b4  push    rdi
0x1800040b5  push    r14
0x1800040b7  sub     rsp, 40h
0x1800040bb  mov     rdi, r8
0x1800040be  mov     rbx, rcx
0x1800040c1  test    edx, edx
0x1800040c3  jz      short loc_1800040CF
0x1800040c5  mov     eax, 80040201h
0x1800040ca  jmp     loc_180004400
0x1800040cf  test    r9b, 2
0x1800040d3  jz      short loc_180004105
0x1800040d5  cmp     dword ptr [rcx+0Ch], 0
0x1800040d9  jz      short loc_1800040FB
0x1800040db  test    r9b, 1
0x1800040df  jz      short loc_1800040E8
0x1800040e1  xor     eax, eax
0x1800040e3  jmp     loc_180004400
0x1800040e8  mov     dword ptr [rcx+0Ch], 0
0x1800040ef  add     rcx, 68h ; 'h'; pmt
0x1800040f3  call    cs:__imp_MoFreeMediaType
0x1800040f9  jmp     short loc_1800040E1
0x1800040fb  mov     eax, 1
0x180004100  jmp     loc_180004400
0x180004105  test    rdi, rdi
0x180004108  jnz     short loc_180004114
0x18000410a  mov     eax, 80004003h
0x18000410f  jmp     loc_180004400
0x180004114  movups  xmm0, xmmword ptr [r8+2Ch]
0x180004119  mov     esi, [r8+48h]
0x18000411d  lea     rcx, [rsp+68h+Buf1]; Buf1
0x180004122  mov     rdx, [rdi+50h]
0x180004126  mov     r8d, esi
0x180004129  movdqu  xmmword ptr [rsp+68h+Buf1.Data1], xmm0
0x18000412f  call    prvValidateMediaTypeSize
0x180004134  test    eax, eax
0x180004136  js      loc_1800043FB
0x18000413c  mov     rax, [rdi]
0x18000413f  sub     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x180004146  jnz     short loc_180004153
0x180004148  mov     rax, [rdi+8]
0x18000414c  sub     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x180004153  test    rax, rax
0x180004156  jnz     loc_1800043FB
0x18000415c  mov     rax, [rdi+2Ch]
0x180004160  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x180004167  mov     rcx, qword ptr cs:FORMAT_VideoInfo.Data4
0x18000416e  sub     rax, rdx
0x180004171  jnz     short loc_18000417A
0x180004173  mov     rax, [rdi+34h]
0x180004177  sub     rax, rcx
0x18000417a  mov     r9, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180004181  mov     r8, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180004188  mov     r10, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18000418f  mov     r11, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004196  test    rax, rax
0x180004199  jz      short loc_1800041C9
0x18000419b  mov     rax, [rdi+2Ch]
0x18000419f  sub     rax, r8
0x1800041a2  jnz     short loc_1800041AB
0x1800041a4  mov     rax, [rdi+34h]
0x1800041a8  sub     rax, r9
0x1800041ab  test    rax, rax
0x1800041ae  jz      short loc_1800041C9
0x1800041b0  mov     rax, [rdi+2Ch]
0x1800041b4  sub     rax, r11
0x1800041b7  jnz     short loc_1800041C0
0x1800041b9  mov     rax, [rdi+34h]
0x1800041bd  sub     rax, r10
0x1800041c0  test    rax, rax
0x1800041c3  jnz     loc_1800043FB
0x1800041c9  mov     rax, [rdi+2Ch]
0x1800041cd  sub     rax, rdx
0x1800041d0  jnz     short loc_1800041D9
0x1800041d2  mov     rax, [rdi+34h]
0x1800041d6  sub     rax, rcx
0x1800041d9  test    rax, rax
0x1800041dc  jnz     short loc_1800041E7
0x1800041de  cmp     esi, 58h ; 'X'
0x1800041e1  jb      loc_1800043FB
0x1800041e7  mov     rax, [rdi+2Ch]
0x1800041eb  sub     rax, r8
0x1800041ee  jnz     short loc_1800041F7
0x1800041f0  mov     rax, [rdi+34h]
0x1800041f4  sub     rax, r9
0x1800041f7  test    rax, rax
0x1800041fa  jnz     short loc_180004205
0x1800041fc  cmp     esi, 70h ; 'p'
0x1800041ff  jb      loc_1800043FB
0x180004205  mov     rax, [rdi+2Ch]
0x180004209  sub     rax, r11
0x18000420c  jnz     short loc_180004215
0x18000420e  mov     rax, [rdi+34h]
0x180004212  sub     rax, r10
0x180004215  test    rax, rax
0x180004218  jnz     short loc_180004226
0x18000421a  cmp     esi, 0B0h
0x180004220  jb      loc_1800043FB
0x180004226  cmp     qword ptr [rdi+50h], 0
0x18000422b  jz      loc_1800043FB
0x180004231  xor     ecx, ecx
0x180004233  lea     rbp, [rdi+10h]
0x180004237  lea     rdx, off_18002C000
0x18000423e  mov     rdx, [rdx+rcx*8]
0x180004242  mov     rax, [rdx]
0x180004245  sub     rax, [rbp+0]
0x180004249  jnz     short loc_180004253
0x18000424b  mov     rax, [rdx+8]
0x18000424f  sub     rax, [rbp+8]
0x180004253  test    rax, rax
0x180004256  jz      short loc_180004265
0x180004258  inc     ecx; this
0x18000425a  cmp     ecx, 10h
0x18000425d  jb      short loc_180004237
0x18000425f  jz      loc_1800043FB
0x180004265  mov     r9d, [rbx+490h]; unsigned int
0x18000426c  lea     r14, [rbx+480h]
0x180004273  mov     r8, [rbx+488h]; struct tagVIDEOINFOHEADER *
0x18000427a  mov     rdx, rdi; struct _DMOMediaType *
0x18000427d  mov     [rsp+68h+var_48], r14; struct tagVIDEOINFOHEADER **
0x180004282  call    ?getVIH@CWMDeColorConvDMO@@AEAAJPEBU_DMOMediaType@@PEAUtagVIDEOINFOHEADER@@KPEAPEAU3@@Z; CWMDeColorConvDMO::getVIH(_DMOMediaType const *,tagVIDEOINFOHEADER *,ulong,tagVIDEOINFOHEADER * *)
0x180004287  test    eax, eax
0x180004289  js      loc_180004400
0x18000428f  mov     rdx, [r14]; struct tagVIDEOINFOHEADER *
0x180004292  lea     rsi, [rbx+4A0h]
0x180004299  mov     r8, rsi; struct tagBITMAPINFOHEADER **
0x18000429c  call    ?setBIH@CWMDeColorConvDMO@@AEAAJPEBUtagVIDEOINFOHEADER@@PEAPEAUtagBITMAPINFOHEADER@@@Z; CWMDeColorConvDMO::setBIH(tagVIDEOINFOHEADER const *,tagBITMAPINFOHEADER * *)
0x1800042a1  test    eax, eax
0x1800042a3  js      loc_180004400
0x1800042a9  mov     rsi, [rsi]
0x1800042ac  mov     rcx, rsi; struct tagBITMAPINFOHEADER *
0x1800042af  call    ?IsValidBitmapInfoHeader@@YAHPEBUtagBITMAPINFOHEADER@@@Z; IsValidBitmapInfoHeader(tagBITMAPINFOHEADER const *)
0x1800042b4  test    eax, eax
0x1800042b6  jnz     short loc_1800042C2
0x1800042b8  mov     eax, 80070057h
0x1800042bd  jmp     loc_180004400
0x1800042c2  mov     rcx, rbp
0x1800042c5  call    biCompressionFromSubtype
0x1800042ca  cmp     eax, [rsi+10h]
0x1800042cd  jnz     loc_1800043FB
0x1800042d3  mov     edx, [rsi+4]; int
0x1800042d6  mov     r8d, [rsi+8]; int
0x1800042da  mov     ecx, [rsi+10h]; unsigned int
0x1800042dd  call    ?ValidImageSizeForFOURCC@@YAHKJJ@Z; ValidImageSizeForFOURCC(ulong,long,long)
0x1800042e2  test    eax, eax
0x1800042e4  jz      loc_1800043FB
0x1800042ea  cmp     dword ptr [rbx+8], 0
0x1800042ee  jz      short loc_180004344
0x1800042f0  mov     r9d, [rbx+478h]; unsigned int
0x1800042f7  lea     r14, [rbx+468h]
0x1800042fe  mov     r8, [rbx+470h]; struct tagVIDEOINFOHEADER *
0x180004305  lea     rdx, [rbx+10h]; struct _DMOMediaType *
0x180004309  mov     [rsp+68h+var_48], r14; struct tagVIDEOINFOHEADER **
0x18000430e  call    ?getVIH@CWMDeColorConvDMO@@AEAAJPEBU_DMOMediaType@@PEAUtagVIDEOINFOHEADER@@KPEAPEAU3@@Z; CWMDeColorConvDMO::getVIH(_DMOMediaType const *,tagVIDEOINFOHEADER *,ulong,tagVIDEOINFOHEADER * *)
0x180004313  test    eax, eax
0x180004315  js      loc_180004400
0x18000431b  mov     rdx, [r14]
0x18000431e  mov     eax, [rsi+8]
0x180004321  mov     ecx, [rdx+38h]
0x180004324  neg     ecx
0x180004326  cmovs   ecx, [rdx+38h]
0x18000432a  neg     eax
0x18000432c  cmovs   eax, [rsi+8]
0x180004330  cmp     ecx, eax
0x180004332  jnz     loc_1800043FB
0x180004338  mov     eax, [rsi+4]
0x18000433b  cmp     [rdx+34h], eax
0x18000433e  jnz     loc_1800043FB
0x180004344  movups  xmm0, xmmword ptr [rbp+0]
0x180004348  lea     rcx, [rsp+68h+Buf1]; struct _GUID
0x18000434d  movdqu  xmmword ptr [rsp+68h+Buf1.Data1], xmm0
0x180004353  call    ?GetSubTypeIndex@@YAEU_GUID@@@Z; GetSubTypeIndex(_GUID)
0x180004358  movzx   ecx, al
0x18000435b  mov     [rbx+1F0h], ecx
0x180004361  cmp     ecx, 0FFh
0x180004367  jz      loc_1800043FB
0x18000436d  lea     rsi, [rbx+0D8h]
0x180004374  mov     rcx, rsi; lpCriticalSection
0x180004377  call    cs:__imp_EnterCriticalSection
0x18000437d  cmp     dword ptr [rbx+0Ch], 0
0x180004381  jz      short loc_180004394
0x180004383  lea     rcx, [rbx+68h]; pmt
0x180004387  call    cs:__imp_MoFreeMediaType
0x18000438d  mov     dword ptr [rbx+0Ch], 0
0x180004394  mov     rdx, rdi; pmtSrc
0x180004397  lea     rcx, [rbx+68h]; pmtDest
0x18000439b  call    cs:__imp_MoCopyMediaType
0x1800043a1  mov     edi, eax
0x1800043a3  test    eax, eax
0x1800043a5  jns     short loc_1800043B4
0x1800043a7  mov     rcx, rsi; lpCriticalSection
0x1800043aa  call    cs:__imp_LeaveCriticalSection
0x1800043b0  mov     eax, edi
0x1800043b2  jmp     short loc_180004400
0x1800043b4  lea     rdx, [rbx+190h]
0x1800043bb  mov     dword ptr [rbx+0Ch], 1
0x1800043c2  cmp     qword ptr [rdx], 0
0x1800043c6  jz      short loc_1800043D4
0x1800043c8  mov     r8d, [rbx+1B0h]
0x1800043cf  call    ?GenVideoCCDestroy@CWMDeColorConvDMO@@IEAAJPEAPEAXW4CC_OPS@@@Z; CWMDeColorConvDMO::GenVideoCCDestroy(void * *,CC_OPS)
0x1800043d4  lea     rdx, [rbx+1A0h]
0x1800043db  cmp     qword ptr [rdx], 0
0x1800043df  jz      short loc_1800043ED
0x1800043e1  mov     r8d, [rbx+1B4h]
0x1800043e8  call    ?GenVideoCCDestroy@CWMDeColorConvDMO@@IEAAJPEAPEAXW4CC_OPS@@@Z; CWMDeColorConvDMO::GenVideoCCDestroy(void * *,CC_OPS)
0x1800043ed  mov     rcx, rsi; lpCriticalSection
0x1800043f0  call    cs:__imp_LeaveCriticalSection
0x1800043f6  jmp     loc_1800040E1
0x1800043fb  mov     eax, 80040205h
0x180004400  add     rsp, 40h
0x180004404  pop     r14
0x180004406  pop     rdi
0x180004407  pop     rsi
0x180004408  pop     rbp
0x180004409  pop     rbx
0x18000440a  retn
```
