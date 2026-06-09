# XLOLECellRead(x,x,x,x,x)

- ea: `0x10020780`
- end: `0x10020e61`
- name: `_XLOLECellRead@20`
- size: `1761`
- prototype: `int __userpurge@<eax>(DispatchDriver *@<edx>, int@<ecx>, int@<ebp>, unsigned int, __int16 *, char)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, installer_update`

## callers

- `0x1001bc80`

## callees

- `0x10006400`
- `0x100200c0`
- `0x10020780`
- `0x10021260`
- `0x10021330`
- `0x10021360`
- `0x10021fe0`
- `0x10022110`
- `0x10022240`
- `0x1002580a`
- `0x10025ab7`
- `0x1002ec67`
- `0x10035510`
- `0x100358c5`
- `0x10035e9f`
- `0x10035f40`
- `0x10036684`

## import_xrefs

- `OLEAUT32!__imp__SysFreeString@4` at `0x1002099d`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10020b06`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1002099d`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10020b06`
- `OLEAUT32!__imp__VariantInit@4` at `0x10020cf4`
- `OLEAUT32!__imp__VariantInit@4` at `0x10020cf4`
- `OLEAUT32!__imp__VariantClear@4` at `0x1002092e`
- `OLEAUT32!__imp__VariantClear@4` at `0x10020e31`
- `OLEAUT32!__imp__VariantClear@4` at `0x1002092e`
- `OLEAUT32!__imp__VariantClear@4` at `0x10020e31`
- `OLEAUT32!__imp__SafeArrayCreate@12` at `0x10020903`
- `OLEAUT32!__imp__SafeArrayCreate@12` at `0x10020903`
- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x10020846`
- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x10020846`
- `OLEAUT32!__imp__SafeArrayGetElement@12` at `0x10020d03`
- `OLEAUT32!__imp__SafeArrayGetElement@12` at `0x10020d03`
- `OLEAUT32!__imp__SafeArrayPutElement@12` at `0x1002091c`
- `OLEAUT32!__imp__SafeArrayPutElement@12` at `0x1002091c`
- `OLEAUT32!__imp__VarR8FromCy@12` at `0x10020e1f`
- `OLEAUT32!__imp__VarR8FromCy@12` at `0x10020e1f`

## pseudocode

```c
int __userpurge XLOLECellRead@<eax>(
        DispatchDriver *a1@<edx>,
        int a2@<ecx>,
        int a3@<ebp>,
        unsigned int a4,
        __int16 *a5,
        char a6)
{
  _DWORD *v6; // edx
  _BYTE *v7; // ecx
  int v8; // eax
  SAFEARRAY *v9; // eax
  ExcelRange *v10; // ecx
  DispatchDriver *v11; // eax
  _BYTE *v12; // ecx
  SAFEARRAY *v13; // edi
  OLECHAR *v14; // edi
  _DWORD *v15; // edi
  int Locked; // eax
  int j; // edi
  ExcelRange *v18; // ecx
  char v19; // al
  int i; // edi
  ExcelRange *v21; // ecx
  int k; // edi
  ExcelRange *v23; // ecx
  char v24; // al
  DispatchDriver *v25; // edi
  char v26; // al
  __int16 v27; // cx
  unsigned __int16 v28; // dx
  _DWORD *v29; // esi
  SAFEARRAY *v30; // esi
  int v31; // eax
  LONGLONG v32; // xmm0_8
  LONGLONG v33; // xmm0_8
  __int16 v34; // ax
  _WORD *v35; // ecx
  _WORD *v36; // edx
  unsigned int v38; // edi
  char *v39; // eax
  char *v40; // esi
  char *v42; // edx
  __int16 v43; // ax
  int v44; // [esp-88h] [ebp-94h] BYREF
  _WORD v45[8]; // [esp-78h] [ebp-84h] BYREF
  __m128i v46; // [esp-68h] [ebp-74h] BYREF
  __m128i v47; // [esp-58h] [ebp-64h] BYREF
  LONG v48[2]; // [esp-48h] [ebp-54h] BYREF
  LONG v49; // [esp-40h] [ebp-4Ch] BYREF
  __int32 v50; // [esp-3Ch] [ebp-48h] BYREF
  struct IDispatch *v51; // [esp-38h] [ebp-44h] BYREF
  struct IDispatch *v52; // [esp-34h] [ebp-40h] BYREF
  DispatchDriver *v53; // [esp-30h] [ebp-3Ch]
  DispatchDriver *v54; // [esp-2Ch] [ebp-38h]
  int v55; // [esp-28h] [ebp-34h] BYREF
  DispatchDriver *v56; // [esp-24h] [ebp-30h]
  _DWORD *v57; // [esp-20h] [ebp-2Ch]
  _DWORD *v58; // [esp-1Ch] [ebp-28h]
  int *v59; // [esp-14h] [ebp-20h]
  int *v60; // [esp-10h] [ebp-1Ch]
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // [esp-Ch] [ebp-18h]
  void *v62; // [esp-8h] [ebp-14h]
  int v63; // [esp-4h] [ebp-10h]
  int v64; // [esp+0h] [ebp-Ch]
  void *v65; // [esp+4h] [ebp-8h]
  int v66; // [esp+8h] [ebp-4h] BYREF
  void *retaddr; // [esp+Ch] [ebp+0h]

  v64 = a3;
  v65 = retaddr;
  v63 = -1;
  v62 = &loc_10036940;
  ExceptionList = NtCurrentTeb()->NtTib.ExceptionList;
  v59 = &v66;
  v60 = &v44;
  v54 = a1;
  v6 = (_DWORD *)a2;
  v58 = (_DWORD *)a2;
  v7 = (_BYTE *)(a2 + 20);
  v63 = 0;
  v48[1] = HIWORD(a4) + 1;
  v8 = v6[4];
  v48[0] = 1;
  v57 = v7;
  if ( (unsigned __int16)a4 == v8 )
  {
    if ( (a6 & 1) != 0 || (*v7 & 2) != 0 )
    {
      v57 = v7;
      if ( (a6 & 2) == 0 && (*v7 & 4) == 0 )
      {
LABEL_11:
        if ( (unsigned __int16)a4 == v8 )
          goto LABEL_14;
        goto LABEL_12;
      }
      if ( ((a6 & 4) != 0 || (*v7 & 8) != 0) && ((a6 & 8) != 0 || (*v7 & 1) != 0) )
      {
        v26 = a6;
        v55 = a6 & 4;
        goto LABEL_66;
      }
    }
    v57 = v7;
    goto LABEL_11;
  }
LABEL_12:
  v9 = (SAFEARRAY *)v6[6];
  v6[4] = -1;
  *(_DWORD *)v7 = 0;
  if ( v9 )
  {
    SafeArrayDestroy(v9);
    v58[6] = 0;
  }
LABEL_14:
  DispatchDriver::InvokeHelper(v54, 258, wInvokeMethod, 9u, (LPSTR)&v52, dword_1003A62C, (unsigned __int16)a4 + 1);
  v11 = ExcelRange::AttachToRange(v10, v52);
  v12 = v57;
  v56 = v11;
  if ( (a6 & 8) == 0 && (*(_BYTE *)v57 & 1) == 0 )
  {
    DispatchDriver::InvokeHelper(v11, 6, 2u, 0xCu, v46.m128i_i8, 0);
    v47 = v46;
    if ( (_mm_cvtsi128_si32(v46) & 0x2000) != 0 )
    {
      v58[6] = v46.m128i_i32[2];
    }
    else
    {
      v49 = 1;
      v50 = 1;
      v46.m128i_i64[0] = 0x100000001LL;
      v46.m128i_i64[1] = 0x100000001LL;
      v13 = SafeArrayCreate(0xCu, 2u, (SAFEARRAYBOUND *)&v46);
      if ( !v13 )
        _CxxThrowException(0, 0);
      if ( SafeArrayPutElement(v13, &v49, &v47) )
        _CxxThrowException(0, 0);
      VariantClear((VARIANTARG *)&v47);
      v58[6] = v13;
    }
    v12 = v57;
    v11 = v56;
    *v57 |= 1u;
  }
  if ( (a6 & 1) == 0 && (*v12 & 2) == 0 )
  {
    DispatchDriver::InvokeHelperWithLCID(v11, 193, 2u, 0x409u, 0xCu, v46.m128i_i8, 0);
    if ( v46.m128i_i16[0] == 1 || (v14 = (OLECHAR *)v46.m128i_i32[2]) == 0 )
    {
      for ( i = 1; i <= ExcelRange::GetColumnCount(v56); ++i )
      {
        DispatchDriver::InvokeHelper(
          v54,
          238,
          wInvokeMethod,
          9u,
          (LPSTR)&v51,
          dword_1003A628,
          (unsigned __int16)a4 + 1,
          i);
        v53 = ExcelRange::AttachToRange(v21, v51);
        v55 = 0;
        DispatchDriver::InvokeHelperWithLCID(v53, 193, 2u, 0x409u, 0xCu, v46.m128i_i8, 0);
        if ( v46.m128i_i16[0] != 1 )
        {
          v50 = v46.m128i_i32[2];
          if ( v46.m128i_i32[2] )
          {
            StoreFormat(&v55);
            SysFreeString((BSTR)v50);
          }
        }
        if ( v53 )
        {
          DispatchDriver::~DispatchDriver(v53);
          operator delete(v53, 8u);
        }
        *((_BYTE *)v58 + i + 27) = v55;
      }
    }
    else
    {
      v55 = 0;
      StoreFormat(&v55);
      SysFreeString(v14);
      memset(v58 + 7, (unsigned __int8)v55, 0x100u);
    }
    v12 = v57;
    *v57 |= 2u;
  }
  if ( (a6 & 2) != 0 || (*v12 & 4) != 0 )
    goto LABEL_51;
  v15 = v58;
  if ( v58[200] == 1 )
  {
    Locked = ExcelRange::GetLocked(v56);
    if ( Locked == 2 )
    {
      for ( j = 1; j <= ExcelRange::GetColumnCount(v56); ++j )
      {
        DispatchDriver::InvokeHelper(
          v54,
          238,
          wInvokeMethod,
          9u,
          (LPSTR)&v50,
          dword_1003A628,
          (unsigned __int16)a4 + 1,
          j);
        v53 = ExcelRange::AttachToRange(v18, (struct IDispatch *)v50);
        DispatchDriver::InvokeHelper(v53, 269, 2u, 0xCu, v46.m128i_i8, 0);
        if ( v46.m128i_i16[0] == 1 )
          v19 = 2;
        else
          v19 = v46.m128i_i16[4] != 0;
        *((_BYTE *)v58 + j + 283) = v19;
        if ( v53 )
        {
          DispatchDriver::~DispatchDriver(v53);
          operator delete(v53, 8u);
        }
      }
      goto LABEL_50;
    }
  }
  else
  {
    LOBYTE(Locked) = 0;
  }
  memset(v15 + 71, (unsigned __int8)Locked, 0x100u);
LABEL_50:
  v12 = v57;
  *v57 |= 4u;
LABEL_51:
  v55 = a6 & 4;
  if ( (a6 & 4) == 0 && (*v12 & 8) == 0 )
  {
    for ( k = 1; k <= ExcelRange::GetColumnCount(v56); ++k )
    {
      DispatchDriver::InvokeHelper(
        v54,
        238,
        wInvokeMethod,
        9u,
        (LPSTR)&v50,
        dword_1003A628,
        (unsigned __int16)a4 + 1,
        k);
      v53 = ExcelRange::AttachToRange(v23, (struct IDispatch *)v50);
      DispatchDriver::InvokeHelper(v53, 267, 2u, 0xCu, (LPSTR)v45, 0);
      if ( v45[0] == 1 )
        v24 = 2;
      else
        v24 = v45[4] != 0;
      *((_BYTE *)v58 + k + 539) = v24;
      if ( v53 )
      {
        DispatchDriver::~DispatchDriver(v53);
        operator delete(v53, 8u);
      }
    }
    *v57 |= 8u;
  }
  v25 = v56;
  if ( v56 )
  {
    DispatchDriver::~DispatchDriver(v56);
    operator delete(v25, 8u);
  }
  v6 = v58;
  v58[4] = (unsigned __int16)a4;
  v26 = a6;
LABEL_66:
  v27 = 0;
  *((_DWORD *)a5 + 1) = 0;
  *a5 = 0;
  if ( (v26 & 2) != 0 || v6[200] != 1 )
  {
    v28 = HIWORD(a4);
    v29 = v58;
  }
  else
  {
    v28 = HIWORD(a4);
    v29 = v58;
    if ( *((_BYTE *)v58 + HIWORD(a4) + 284) )
    {
      *a5 = 512;
      v27 = 512;
    }
  }
  if ( !v55 && *((_BYTE *)v29 + v28 + 540) )
    *a5 = v27 | 0x100;
  if ( (a6 & 1) == 0 )
    *((_DWORD *)a5 + 1) = *((unsigned __int8 *)v29 + v28 + 28);
  v30 = (SAFEARRAY *)v29[6];
  VariantInit((VARIANTARG *)&v47);
  if ( SafeArrayGetElement(v30, v48, &v47) >= 0 )
  {
    switch ( v47.m128i_i16[0] )
    {
      case 0xB:
        v31 = v47.m128i_i16[4];
        *a5 |= 4u;
        *((_DWORD *)a5 + 4) = v31;
        break;
      case 5:
        v32 = v47.m128i_i64[1];
        *a5 |= 2u;
        *((_QWORD *)a5 + 2) = v32;
        break;
      case 7:
        v33 = v47.m128i_i64[1];
        *a5 |= 0x42u;
        *((_QWORD *)a5 + 2) = v33;
        break;
      default:
        v34 = *a5;
        if ( v47.m128i_i16[0] == 8 )
        {
          v35 = (_WORD *)v47.m128i_i32[2];
          *a5 = v34 | 0x10;
          v36 = v35 + 1;
          while ( *v35++ )
            ;
          v38 = 2 * (v35 - v36) + 2;
          v39 = (char *)MemAllocate(v38);
          v40 = v39;
          if ( !v39 )
            return -1011;
          WCSCPY2(v39, (_WORD *)v47.m128i_i32[2], v38 >> 1);
          v42 = v40;
          do
          {
            v43 = *(_WORD *)v42;
            v42 += 2;
          }
          while ( v43 );
          *((_DWORD *)a5 + 4) = TextStoragePut(*(_DWORD *)(v58[201] + 16), v40, (v42 - (v40 + 2)) >> 1, 1);
          MemFree(v40);
        }
        else if ( v47.m128i_i16[0] == 6 )
        {
          *a5 = v34 | 0x22;
          VarR8FromCy((CY)v47.m128i_i64[1], (DOUBLE *)a5 + 2);
        }
        else
        {
          *a5 = v34 | 1;
        }
        break;
    }
    VariantClear((VARIANTARG *)&v47);
  }
  else
  {
    *a5 |= 1u;
  }
  return 0;
}

```

## disassembly

```asm
0x10020780  mov     edi, edi
0x10020782  push    ebx
0x10020783  mov     ebx, esp
0x10020785  sub     esp, 8
0x10020788  and     esp, 0FFFFFFF8h
0x1002078b  add     esp, 4
0x1002078e  push    ebp
0x1002078f  mov     ebp, [ebx+4]
0x10020792  mov     [esp+0Ch+var_8], ebp
0x10020796  mov     ebp, esp
0x10020798  push    0FFFFFFFFh
0x1002079a  push    offset loc_10036940
0x1002079f  mov     eax, large fs:0
0x100207a5  push    eax
0x100207a6  push    ecx
0x100207a7  push    ebx
0x100207a8  sub     esp, 68h
0x100207ab  push    esi
0x100207ac  push    edi
0x100207ad  mov     eax, ___security_cookie
0x100207b2  xor     eax, ebp
0x100207b4  push    eax
0x100207b5  lea     eax, [ebp-0Ch]
0x100207b8  mov     large fs:0, eax
0x100207be  mov     [ebp-10h], esp
0x100207c1  mov     [ebp-2Ch], edx
0x100207c4  mov     edx, ecx
0x100207c6  mov     [ebp-1Ch], edx
0x100207c9  mov     esi, [ebx+8]
0x100207cc  lea     ecx, [edx+14h]
0x100207cf  mov     eax, esi
0x100207d1  mov     dword ptr [ebp-4], 0
0x100207d8  shr     eax, 10h
0x100207db  inc     eax
0x100207dc  movzx   edi, si
0x100207df  mov     [ebp-44h], eax
0x100207e2  mov     eax, [edx+10h]
0x100207e5  mov     dword ptr [ebp-48h], 1
0x100207ec  mov     [ebp-20h], ecx
0x100207ef  cmp     edi, eax
0x100207f1  jnz     short loc_10020831
0x100207f3  test    byte ptr [ebx+10h], 1
0x100207f7  jnz     short loc_100207FE
0x100207f9  test    byte ptr [ecx], 2
0x100207fc  jz      short loc_1002082A
0x100207fe  test    byte ptr [ebx+10h], 2
0x10020802  mov     [ebp-20h], ecx
0x10020805  jnz     short loc_1002080C
0x10020807  test    byte ptr [ecx], 4
0x1002080a  jz      short loc_1002082D
0x1002080c  test    byte ptr [ebx+10h], 4
0x10020810  jnz     short loc_10020817
0x10020812  test    byte ptr [ecx], 8
0x10020815  jz      short loc_1002082A
0x10020817  test    byte ptr [ebx+10h], 8
0x1002081b  jnz     loc_10020C73
0x10020821  test    byte ptr [ecx], 1
0x10020824  jnz     loc_10020C73
0x1002082a  mov     [ebp-20h], ecx
0x1002082d  cmp     edi, eax
0x1002082f  jz      short loc_10020856
0x10020831  mov     eax, [edx+18h]
0x10020834  mov     dword ptr [edx+10h], 0FFFFFFFFh
0x1002083b  mov     dword ptr [ecx], 0
0x10020841  test    eax, eax
0x10020843  jz      short loc_10020856
0x10020845  push    eax; psa
0x10020846  call    ds:__imp__SafeArrayDestroy@4; SafeArrayDestroy(x)
0x1002084c  mov     eax, [ebp-1Ch]
0x1002084f  mov     dword ptr [eax+18h], 0
0x10020856  lea     eax, [edi+1]
0x10020859  push    eax
0x1002085a  push    offset dword_1003A62C; lpString
0x1002085f  lea     eax, [ebp-34h]
0x10020862  push    eax; LPSTR
0x10020863  movzx   eax, ?wInvokeMethod@@3GA; ushort wInvokeMethod
0x1002086a  push    9; unsigned __int16
0x1002086c  push    eax; unsigned __int16
0x1002086d  push    102h; int
0x10020872  push    dword ptr [ebp-2Ch]; this
0x10020875  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x1002087a  add     esp, 1Ch
0x1002087d  push    dword ptr [ebp-34h]; struct IDispatch *
0x10020880  call    ?AttachToRange@ExcelRange@@IAEPAV1@PAUIDispatch@@@Z; ExcelRange::AttachToRange(IDispatch *)
0x10020885  test    byte ptr [ebx+10h], 8
0x10020889  mov     ecx, [ebp-20h]
0x1002088c  mov     [ebp-24h], eax
0x1002088f  jnz     loc_10020943
0x10020895  test    byte ptr [ecx], 1
0x10020898  jnz     loc_10020943
0x1002089e  push    0; lpString
0x100208a0  lea     ecx, [ebp-68h]
0x100208a3  push    ecx; LPSTR
0x100208a4  push    0Ch; unsigned __int16
0x100208a6  push    2; unsigned __int16
0x100208a8  push    6; int
0x100208aa  push    eax; this
0x100208ab  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x100208b0  movups  xmm0, xmmword ptr [ebp-68h]
0x100208b4  add     esp, 18h
0x100208b7  movd    eax, xmm0
0x100208bb  movups  xmmword ptr [ebp-58h], xmm0
0x100208bf  test    eax, 2000h
0x100208c4  jz      short loc_100208D1
0x100208c6  mov     ecx, [ebp-1Ch]
0x100208c9  mov     eax, [ebp-60h]
0x100208cc  mov     [ecx+18h], eax
0x100208cf  jmp     short loc_1002093A
0x100208d1  lea     eax, [ebp-68h]
0x100208d4  mov     dword ptr [ebp-40h], 1
0x100208db  push    eax; rgsabound
0x100208dc  push    2; cDims
0x100208de  push    0Ch; vt
0x100208e0  mov     dword ptr [ebp-3Ch], 1
0x100208e7  mov     dword ptr [ebp-68h], 1
0x100208ee  mov     dword ptr [ebp-64h], 1
0x100208f5  mov     dword ptr [ebp-60h], 1
0x100208fc  mov     dword ptr [ebp-5Ch], 1
0x10020903  call    ds:__imp__SafeArrayCreate@12; SafeArrayCreate(x,x,x)
0x10020909  mov     edi, eax
0x1002090b  test    edi, edi
0x1002090d  jz      loc_10020E4F
0x10020913  lea     eax, [ebp-58h]
0x10020916  push    eax; pv
0x10020917  lea     eax, [ebp-40h]
0x1002091a  push    eax; rgIndices
0x1002091b  push    edi; psa
0x1002091c  call    ds:__imp__SafeArrayPutElement@12; SafeArrayPutElement(x,x,x)
0x10020922  test    eax, eax
0x10020924  jnz     loc_10020E58
0x1002092a  lea     eax, [ebp-58h]
0x1002092d  push    eax; pvarg
0x1002092e  call    ds:__imp__VariantClear@4; VariantClear(x)
0x10020934  mov     eax, [ebp-1Ch]
0x10020937  mov     [eax+18h], edi
0x1002093a  mov     ecx, [ebp-20h]
0x1002093d  mov     eax, [ebp-24h]
0x10020940  or      dword ptr [ecx], 1
0x10020943  test    byte ptr [ebx+10h], 1
0x10020947  jnz     short loc_100209C2
0x10020949  test    byte ptr [ecx], 2
0x1002094c  jnz     short loc_100209C2
0x1002094e  push    0; lpString
0x10020950  lea     ecx, [ebp-68h]
0x10020953  push    ecx; LPSTR
0x10020954  push    0Ch; unsigned __int16
0x10020956  push    409h; unsigned __int16
0x1002095b  push    2; unsigned __int16
0x1002095d  push    0C1h; int
0x10020962  push    eax; this
0x10020963  call    ?InvokeHelperWithLCID@DispatchDriver@@QAAHJGGGPAXPBEZZ; DispatchDriver::InvokeHelperWithLCID(long,ushort,ushort,ushort,void *,uchar const *,...)
0x10020968  add     esp, 1Ch
0x1002096b  cmp     word ptr [ebp-68h], 1
0x10020970  jz      loc_10020A71
0x10020976  mov     edi, [ebp-60h]
0x10020979  test    edi, edi
0x1002097b  jz      loc_10020A71
0x10020981  lea     eax, [ebp-28h]
0x10020984  mov     dword ptr [ebp-28h], 0
0x1002098b  push    eax
0x1002098c  mov     eax, [ebp-1Ch]
0x1002098f  mov     edx, edi
0x10020991  mov     ecx, [eax+324h]
0x10020997  call    StoreFormat
0x1002099c  push    edi; bstrString
0x1002099d  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x100209a3  movzx   eax, byte ptr [ebp-28h]
0x100209a7  push    100h; Size
0x100209ac  push    eax; Val
0x100209ad  mov     eax, [ebp-1Ch]
0x100209b0  add     eax, 1Ch
0x100209b3  push    eax; void *
0x100209b4  call    _memset
0x100209b9  add     esp, 0Ch
0x100209bc  mov     ecx, [ebp-20h]
0x100209bf  or      dword ptr [ecx], 2
0x100209c2  test    byte ptr [ebx+10h], 2
0x100209c6  jnz     loc_10020B8B
0x100209cc  test    byte ptr [ecx], 4
0x100209cf  jnz     loc_10020B8B
0x100209d5  mov     edi, [ebp-1Ch]
0x100209d8  cmp     dword ptr [edi+320h], 1
0x100209df  jnz     loc_10020B6B
0x100209e5  mov     ecx, [ebp-24h]; this
0x100209e8  call    ?GetLocked@ExcelRange@@QAEHXZ; ExcelRange::GetLocked(void)
0x100209ed  cmp     eax, 2
0x100209f0  jnz     loc_10020B6D
0x100209f6  lea     edi, [eax-1]
0x100209f9  nop     dword ptr [eax+00000000h]
0x10020a00  mov     ecx, [ebp-24h]; this
0x10020a03  call    ?GetColumnCount@ExcelRange@@QAEJXZ; ExcelRange::GetColumnCount(void)
0x10020a08  cmp     edi, eax
0x10020a0a  jg      loc_10020B85
0x10020a10  push    edi
0x10020a11  movzx   eax, si
0x10020a14  inc     eax
0x10020a15  push    eax
0x10020a16  push    offset dword_1003A628; lpString
0x10020a1b  lea     eax, [ebp-3Ch]
0x10020a1e  push    eax; LPSTR
0x10020a1f  movzx   eax, ?wInvokeMethod@@3GA; ushort wInvokeMethod
0x10020a26  push    9; unsigned __int16
0x10020a28  push    eax; unsigned __int16
0x10020a29  push    0EEh; int
0x10020a2e  push    dword ptr [ebp-2Ch]; this
0x10020a31  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x10020a36  add     esp, 20h
0x10020a39  push    dword ptr [ebp-3Ch]; struct IDispatch *
0x10020a3c  call    ?AttachToRange@ExcelRange@@IAEPAV1@PAUIDispatch@@@Z; ExcelRange::AttachToRange(IDispatch *)
0x10020a41  push    0; lpString
0x10020a43  lea     ecx, [ebp-68h]
0x10020a46  mov     [ebp-30h], eax
0x10020a49  push    ecx; LPSTR
0x10020a4a  push    0Ch; unsigned __int16
0x10020a4c  push    2; unsigned __int16
0x10020a4e  push    10Dh; int
0x10020a53  push    eax; this
0x10020a54  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x10020a59  add     esp, 18h
0x10020a5c  cmp     word ptr [ebp-68h], 1
0x10020a61  jnz     loc_10020B37
0x10020a67  mov     eax, 2
0x10020a6c  jmp     loc_10020B40
0x10020a71  mov     edi, 1
0x10020a76  mov     ecx, [ebp-24h]; this
0x10020a79  call    ?GetColumnCount@ExcelRange@@QAEJXZ; ExcelRange::GetColumnCount(void)
0x10020a7e  cmp     edi, eax
0x10020a80  jg      loc_100209BC
0x10020a86  push    edi
0x10020a87  movzx   eax, si
0x10020a8a  inc     eax
0x10020a8b  push    eax
0x10020a8c  push    offset dword_1003A628; lpString
0x10020a91  lea     eax, [ebp-38h]
0x10020a94  push    eax; LPSTR
0x10020a95  movzx   eax, ?wInvokeMethod@@3GA; ushort wInvokeMethod
0x10020a9c  push    9; unsigned __int16
0x10020a9e  push    eax; unsigned __int16
0x10020a9f  push    0EEh; int
0x10020aa4  push    dword ptr [ebp-2Ch]; this
0x10020aa7  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x10020aac  add     esp, 20h
0x10020aaf  push    dword ptr [ebp-38h]; struct IDispatch *
0x10020ab2  call    ?AttachToRange@ExcelRange@@IAEPAV1@PAUIDispatch@@@Z; ExcelRange::AttachToRange(IDispatch *)
0x10020ab7  push    0; lpString
0x10020ab9  lea     ecx, [ebp-68h]
0x10020abc  mov     [ebp-30h], eax
0x10020abf  push    ecx; LPSTR
0x10020ac0  push    0Ch; unsigned __int16
0x10020ac2  push    409h; unsigned __int16
0x10020ac7  push    2; unsigned __int16
0x10020ac9  push    0C1h; int
0x10020ace  push    eax; this
0x10020acf  mov     dword ptr [ebp-28h], 0
0x10020ad6  call    ?InvokeHelperWithLCID@DispatchDriver@@QAAHJGGGPAXPBEZZ; DispatchDriver::InvokeHelperWithLCID(long,ushort,ushort,ushort,void *,uchar const *,...)
0x10020adb  add     esp, 1Ch
0x10020ade  cmp     word ptr [ebp-68h], 1
0x10020ae3  jz      short loc_10020B0C
0x10020ae5  mov     eax, [ebp-60h]
0x10020ae8  mov     [ebp-3Ch], eax
0x10020aeb  test    eax, eax
0x10020aed  jz      short loc_10020B0C
0x10020aef  mov     edx, eax
0x10020af1  lea     ecx, [ebp-28h]
0x10020af4  mov     eax, [ebp-1Ch]
0x10020af7  push    ecx
0x10020af8  mov     ecx, [eax+324h]
0x10020afe  call    StoreFormat
0x10020b03  push    dword ptr [ebp-3Ch]; bstrString
0x10020b06  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10020b0c  mov     eax, [ebp-30h]
0x10020b0f  test    eax, eax
0x10020b11  jz      short loc_10020B27
0x10020b13  mov     ecx, eax; this
0x10020b15  call    ??1DispatchDriver@@QAE@XZ; DispatchDriver::~DispatchDriver(void)
0x10020b1a  push    8; unsigned int
0x10020b1c  push    dword ptr [ebp-30h]; void *
0x10020b1f  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10020b24  add     esp, 8
0x10020b27  mov     ecx, [ebp-1Ch]
0x10020b2a  mov     eax, [ebp-28h]
0x10020b2d  mov     [edi+ecx+1Bh], al
0x10020b31  inc     edi
0x10020b32  jmp     loc_10020A76
0x10020b37  xor     eax, eax
0x10020b39  cmp     [ebp-60h], ax
0x10020b3d  setnz   al
0x10020b40  mov     ecx, [ebp-1Ch]
0x10020b43  mov     [edi+ecx+11Bh], al
0x10020b4a  mov     eax, [ebp-30h]
0x10020b4d  test    eax, eax
0x10020b4f  jz      short loc_10020B65
0x10020b51  mov     ecx, eax; this
0x10020b53  call    ??1DispatchDriver@@QAE@XZ; DispatchDriver::~DispatchDriver(void)
0x10020b58  push    8; unsigned int
0x10020b5a  push    dword ptr [ebp-30h]; void *
0x10020b5d  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10020b62  add     esp, 8
0x10020b65  inc     edi
0x10020b66  jmp     loc_10020A00
  ... truncated ...
```
