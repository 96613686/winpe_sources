# CBody::Print(int,tagVARIANT *)

- ea: `0x18007c5d0`
- end: `0x18007c99d`
- name: `?Print@CBody@@AEAAJHPEAUtagVARIANT@@@Z`
- size: `973`
- prototype: `__int64 __fastcall(CBody *__hidden this, int, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180023d04`

## callees

- `0x180005748`
- `0x18002e0d0`
- `0x18006f720`
- `0x18007c5d0`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!__imp_IStream_Reset` at `0x18007c82b`
- `SHLWAPI!__imp_IStream_Reset` at `0x18007c82b`
- `USER32!LoadStringW` at `0x18007c70f`
- `USER32!LoadStringW` at `0x18007c77e`
- `USER32!LoadStringW` at `0x18007c70f`
- `USER32!LoadStringW` at `0x18007c77e`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c719`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c788`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c878`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c719`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c788`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c878`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c937`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c945`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c953`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c937`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c945`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c953`
- `OLEAUT32!__imp_VariantInit` at `0x18007c6c2`
- `OLEAUT32!__imp_VariantInit` at `0x18007c929`
- `OLEAUT32!__imp_VariantInit` at `0x18007c6c2`
- `OLEAUT32!__imp_VariantInit` at `0x18007c929`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18007c6a5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18007c6a5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18007c961`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18007c961`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c6db`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c752`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c7c9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c85c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c8b0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c8e3`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c6db`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c752`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c7c9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c85c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c8b0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007c8e3`

## pseudocode

```c
__int64 __fastcall CBody::Print(CBody *this, int a2, struct tagVARIANT *a3)
{
  OLECHAR *v3; // rsi
  __int64 v6; // rcx
  OLECHAR *v7; // r15
  OLECHAR *v8; // r12
  BOOL v9; // r13d
  SAFEARRAY *v10; // rdi
  HRESULT HeaderTable; // ebx
  unsigned int i; // ebx
  BSTR v13; // rax
  BSTR v14; // rax
  unsigned __int16 *bstrVal; // rdx
  unsigned int v16; // ebx
  BSTR v17; // rax
  __int64 v18; // rcx
  bool v19; // cf
  LONG rgIndices; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+60h] [rbp-A0h]
  SAFEARRAYBOUND rgsabound; // [rsp+68h] [rbp-98h] BYREF
  IStream *pstm; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h] BYREF
  struct tagVARIANT *v26; // [rsp+80h] [rbp-80h]
  __int128 v27; // [rsp+88h] [rbp-78h] BYREF
  __int64 v28; // [rsp+98h] [rbp-68h]
  WCHAR Buffer[512]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = 0;
  v26 = a3;
  v22 = a2;
  rgsabound = 0;
  v28 = 0;
  rgIndices = 0;
  pstm = 0;
  v27 = 0;
  v25 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( !*((_QWORD *)this + 12) )
    return 2147549183LL;
  v6 = *((_QWORD *)this + 35);
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( v6 && *((_QWORD *)this + 38) )
    v9 = MimeOleGetRelatedSection(v6, 0, &v25, 0) == 0;
  rgsabound = (SAFEARRAYBOUND)5LL;
  v10 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  if ( v10 )
  {
    VariantInit(&pvarg);
    for ( i = 0; i < 5; ++i )
    {
      rgIndices = i;
      SafeArrayPutElement(v10, &rgIndices, &pvarg);
    }
    *((_QWORD *)&v27 + 1) = v10;
    LOWORD(v27) = 24576;
    Buffer[0] = 0;
    LoadStringW(g_hLocRes, 0x47Fu, Buffer, 512);
    v13 = SysAllocString(Buffer);
    v3 = v13;
    if ( v13 )
    {
      pvarg.llVal = (LONGLONG)v13;
      pvarg.vt = 8;
      rgIndices = 0;
      HeaderTable = SafeArrayPutElement(v10, &rgIndices, &pvarg);
      if ( HeaderTable < 0 )
        goto LABEL_24;
      Buffer[0] = 0;
      LoadStringW(g_hLocRes, 0x480u, Buffer, 512);
      v14 = SysAllocString(Buffer);
      v7 = v14;
      if ( v14 )
      {
        pvarg.llVal = (LONGLONG)v14;
        pvarg.vt = 8;
        rgIndices = 1;
        HeaderTable = SafeArrayPutElement(v10, &rgIndices, &pvarg);
        if ( HeaderTable >= 0 )
        {
          if ( !*((_QWORD *)this + 35) )
            goto LABEL_22;
          bstrVal = 0;
          if ( v26 && v26->vt == 8 )
            bstrVal = v26->bstrVal;
          HeaderTable = GetHeaderTable(*((struct IMimeMessageW **)this + 36), bstrVal, 0x40000000u, &pstm);
          if ( HeaderTable >= 0 )
          {
            v16 = (unsigned int)pstm;
            IStream_Reset(pstm);
            pvarg.llVal = __PAIR64__(HIDWORD(pstm), v16);
            pvarg.vt = 13;
            rgIndices = 2;
            HeaderTable = SafeArrayPutElement(v10, &rgIndices, &pvarg);
            if ( HeaderTable >= 0 )
            {
              if ( !v9
                || (v17 = SysAllocString(*((const OLECHAR **)this + 38)),
                    rgIndices = 3,
                    v8 = v17,
                    pvarg.llVal = (LONGLONG)v17,
                    pvarg.vt = 8,
                    HeaderTable = SafeArrayPutElement(v10, &rgIndices, &pvarg),
                    HeaderTable >= 0) )
              {
LABEL_22:
                pvarg.vt = 3;
                pvarg.lVal = 2;
                rgIndices = 4;
                HeaderTable = SafeArrayPutElement(v10, &rgIndices, &pvarg);
                if ( HeaderTable >= 0 )
                {
                  v18 = *((_QWORD *)this + 12);
                  v19 = v22 != 0;
                  v22 = -v22;
                  HeaderTable = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int128 *, _QWORD))(*(_QWORD *)v18 + 32LL))(
                                  v18,
                                  0,
                                  6,
                                  2 - (unsigned int)v19,
                                  &v27,
                                  0);
                }
              }
            }
          }
        }
        goto LABEL_24;
      }
    }
  }
  HeaderTable = -2147024882;
LABEL_24:
  VariantInit(&pvarg);
  if ( v7 )
    SysFreeString(v7);
  if ( v3 )
    SysFreeString(v3);
  if ( v8 )
    SysFreeString(v8);
  if ( v10 )
    SafeArrayDestroy(v10);
  OE_SafeReleaseAndNullPtr<IStream>(&pstm);
  return (unsigned int)HeaderTable;
}

```

## disassembly

```asm
0x18007c5d0  mov     [rsp-8+arg_8], rbx
0x18007c5d5  push    rbp
0x18007c5d6  push    rsi
0x18007c5d7  push    rdi
0x18007c5d8  push    r12
0x18007c5da  push    r13
0x18007c5dc  push    r14
0x18007c5de  push    r15
0x18007c5e0  lea     rbp, [rsp-3B0h]
0x18007c5e8  sub     rsp, 4B0h
0x18007c5ef  mov     rax, cs:__security_cookie
0x18007c5f6  xor     rax, rsp
0x18007c5f9  mov     [rbp+3E0h+var_40], rax
0x18007c600  xor     esi, esi
0x18007c602  mov     [rbp+3E0h+var_460], r8
0x18007c606  xorps   xmm0, xmm0
0x18007c609  mov     [rsp+4E0h+var_480], edx
0x18007c60d  xor     eax, eax
0x18007c60f  mov     qword ptr [rsp+4E0h+rgsabound.cElements], rsi
0x18007c614  mov     r14, rcx
0x18007c617  mov     [rbp+3E0h+var_448], rax
0x18007c61b  xor     edx, edx; Val
0x18007c61d  mov     [rsp+4E0h+rgIndices], esi
0x18007c621  mov     r8d, 400h; Size
0x18007c627  mov     qword ptr [rsp+4E0h+pvarg+10h], rax
0x18007c62c  lea     rcx, [rbp+3E0h+Buffer]; void *
0x18007c630  mov     [rsp+4E0h+pstm], rsi
0x18007c635  movups  [rbp+3E0h+var_458], xmm0
0x18007c639  mov     [rsp+4E0h+var_468], rsi
0x18007c63e  movups  xmmword ptr [rsp+4E0h+pvarg], xmm0
0x18007c643  call    memset_0
0x18007c648  cmp     [r14+60h], rsi
0x18007c64c  jnz     short loc_18007C658
0x18007c64e  mov     eax, 8000FFFFh
0x18007c653  jmp     loc_18007C973
0x18007c658  mov     rcx, [r14+118h]
0x18007c65f  mov     r15, rsi
0x18007c662  mov     r12, rsi
0x18007c665  mov     r13d, esi
0x18007c668  mov     ebx, 1
0x18007c66d  test    rcx, rcx
0x18007c670  jz      short loc_18007C690
0x18007c672  cmp     [r14+130h], rsi
0x18007c679  jz      short loc_18007C690
0x18007c67b  xor     r9d, r9d
0x18007c67e  lea     r8, [rsp+4E0h+var_468]
0x18007c683  xor     edx, edx
0x18007c685  call    MimeOleGetRelatedSection
0x18007c68a  test    eax, eax
0x18007c68c  cmovz   r13d, ebx
0x18007c690  mov     ecx, 0Ch; vt
0x18007c695  mov     qword ptr [rsp+4E0h+rgsabound.cElements], 5
0x18007c69e  lea     r8, [rsp+4E0h+rgsabound]; rgsabound
0x18007c6a3  mov     edx, ebx; cDims
0x18007c6a5  call    cs:__imp_SafeArrayCreate
0x18007c6ab  mov     rdi, rax
0x18007c6ae  test    rax, rax
0x18007c6b1  jnz     short loc_18007C6BD
0x18007c6b3  mov     ebx, 8007000Eh
0x18007c6b8  jmp     loc_18007C924
0x18007c6bd  lea     rcx, [rsp+4E0h+pvarg]; pvarg
0x18007c6c2  call    cs:__imp_VariantInit
0x18007c6c8  mov     ebx, esi
0x18007c6ca  lea     r8, [rsp+4E0h+pvarg]; pv
0x18007c6cf  mov     [rsp+4E0h+rgIndices], ebx
0x18007c6d3  lea     rdx, [rsp+4E0h+rgIndices]; rgIndices
0x18007c6d8  mov     rcx, rdi; psa
0x18007c6db  call    cs:__imp_SafeArrayPutElement
0x18007c6e1  inc     ebx
0x18007c6e3  cmp     ebx, 5
0x18007c6e6  jb      short loc_18007C6CA
0x18007c6e8  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18007c6ef  lea     r8, [rbp+3E0h+Buffer]; lpBuffer
0x18007c6f3  mov     eax, 6000h
0x18007c6f8  mov     qword ptr [rbp+3E0h+var_458+8], rdi
0x18007c6fc  mov     r9d, 200h; cchBufferMax
0x18007c702  mov     word ptr [rbp+3E0h+var_458], ax
0x18007c706  mov     edx, 47Fh; uID
0x18007c70b  mov     [rbp+3E0h+Buffer], si
0x18007c70f  call    cs:__imp_LoadStringW
0x18007c715  lea     rcx, [rbp+3E0h+Buffer]; psz
0x18007c719  call    cs:__imp_SysAllocString
0x18007c71f  mov     rsi, rax
0x18007c722  test    rax, rax
0x18007c725  jz      short loc_18007C6B3
0x18007c727  mov     eax, 8
0x18007c72c  mov     dword ptr [rsp+4E0h+pvarg+8], esi
0x18007c730  mov     word ptr [rsp+4E0h+pvarg], ax
0x18007c735  lea     r8, [rsp+4E0h+pvarg]; pv
0x18007c73a  mov     rax, rsi
0x18007c73d  mov     [rsp+4E0h+rgIndices], r12d
0x18007c742  sar     rax, 20h
0x18007c746  lea     rdx, [rsp+4E0h+rgIndices]; rgIndices
0x18007c74b  mov     rcx, rdi; psa
0x18007c74e  mov     dword ptr [rsp+4E0h+pvarg+0Ch], eax
0x18007c752  call    cs:__imp_SafeArrayPutElement
0x18007c758  mov     ebx, eax
0x18007c75a  test    eax, eax
0x18007c75c  js      loc_18007C924
0x18007c762  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18007c769  lea     r8, [rbp+3E0h+Buffer]; lpBuffer
0x18007c76d  xor     eax, eax
0x18007c76f  mov     r9d, 200h; cchBufferMax
0x18007c775  mov     edx, 480h; uID
0x18007c77a  mov     [rbp+3E0h+Buffer], ax
0x18007c77e  call    cs:__imp_LoadStringW
0x18007c784  lea     rcx, [rbp+3E0h+Buffer]; psz
0x18007c788  call    cs:__imp_SysAllocString
0x18007c78e  mov     r15, rax
0x18007c791  test    rax, rax
0x18007c794  jz      loc_18007C6B3
0x18007c79a  mov     eax, 8
0x18007c79f  mov     dword ptr [rsp+4E0h+pvarg+8], r15d
0x18007c7a4  mov     word ptr [rsp+4E0h+pvarg], ax
0x18007c7a9  lea     r8, [rsp+4E0h+pvarg]; pv
0x18007c7ae  mov     rax, r15
0x18007c7b1  mov     [rsp+4E0h+rgIndices], 1
0x18007c7b9  sar     rax, 20h
0x18007c7bd  lea     rdx, [rsp+4E0h+rgIndices]; rgIndices
0x18007c7c2  mov     rcx, rdi; psa
0x18007c7c5  mov     dword ptr [rsp+4E0h+pvarg+0Ch], eax
0x18007c7c9  call    cs:__imp_SafeArrayPutElement
0x18007c7cf  mov     ebx, eax
0x18007c7d1  test    eax, eax
0x18007c7d3  js      loc_18007C924
0x18007c7d9  mov     eax, 3
0x18007c7de  cmp     [r14+118h], r12
0x18007c7e5  jz      loc_18007C8C1
0x18007c7eb  mov     rax, [rbp+3E0h+var_460]
0x18007c7ef  xor     edx, edx
0x18007c7f1  test    rax, rax
0x18007c7f4  jz      short loc_18007C802
0x18007c7f6  lea     ecx, [rdx+8]
0x18007c7f9  cmp     [rax], cx
0x18007c7fc  jnz     short loc_18007C802
0x18007c7fe  mov     rdx, [rax+8]; unsigned __int16 *
0x18007c802  mov     rcx, [r14+120h]; struct IMimeMessageW *
0x18007c809  lea     r9, [rsp+4E0h+pstm]; struct IStream **
0x18007c80e  mov     r8d, 40000000h; unsigned int
0x18007c814  call    ?GetHeaderTable@@YAJPEAUIMimeMessageW@@PEAGKPEAPEAUIStream@@@Z; GetHeaderTable(IMimeMessageW *,ushort *,ulong,IStream * *)
0x18007c819  mov     ebx, eax
0x18007c81b  test    eax, eax
0x18007c81d  js      loc_18007C924
0x18007c823  mov     rbx, [rsp+4E0h+pstm]
0x18007c828  mov     rcx, rbx; pstm
0x18007c82b  call    cs:__imp_IStream_Reset
0x18007c831  mov     eax, 0Dh
0x18007c836  mov     dword ptr [rsp+4E0h+pvarg+8], ebx
0x18007c83a  mov     word ptr [rsp+4E0h+pvarg], ax
0x18007c83f  lea     r8, [rsp+4E0h+pvarg]; pv
0x18007c844  mov     eax, dword ptr [rsp+4E0h+pstm+4]
0x18007c848  lea     rdx, [rsp+4E0h+rgIndices]; rgIndices
0x18007c84d  mov     rcx, rdi; psa
0x18007c850  mov     dword ptr [rsp+4E0h+pvarg+0Ch], eax
0x18007c854  mov     [rsp+4E0h+rgIndices], 2
0x18007c85c  call    cs:__imp_SafeArrayPutElement
0x18007c862  mov     ebx, eax
0x18007c864  test    eax, eax
0x18007c866  js      loc_18007C924
0x18007c86c  test    r13d, r13d
0x18007c86f  jz      short loc_18007C8BC
0x18007c871  mov     rcx, [r14+130h]; psz
0x18007c878  call    cs:__imp_SysAllocString
0x18007c87e  lea     r8, [rsp+4E0h+pvarg]; pv
0x18007c883  mov     [rsp+4E0h+rgIndices], 3
0x18007c88b  mov     r12, rax
0x18007c88e  lea     rdx, [rsp+4E0h+rgIndices]; rgIndices
0x18007c893  mov     eax, 8
0x18007c898  mov     dword ptr [rsp+4E0h+pvarg+8], r12d
0x18007c89d  mov     rcx, r12
0x18007c8a0  mov     word ptr [rsp+4E0h+pvarg], ax
0x18007c8a5  sar     rcx, 20h
0x18007c8a9  mov     dword ptr [rsp+4E0h+pvarg+0Ch], ecx
0x18007c8ad  mov     rcx, rdi; psa
0x18007c8b0  call    cs:__imp_SafeArrayPutElement
0x18007c8b6  mov     ebx, eax
0x18007c8b8  test    eax, eax
0x18007c8ba  js      short loc_18007C924
0x18007c8bc  mov     eax, 3
0x18007c8c1  lea     r8, [rsp+4E0h+pvarg]; pv
0x18007c8c6  mov     word ptr [rsp+4E0h+pvarg], ax
0x18007c8cb  lea     rdx, [rsp+4E0h+rgIndices]; rgIndices
0x18007c8d0  mov     dword ptr [rsp+4E0h+pvarg+8], 2
0x18007c8d8  mov     rcx, rdi; psa
0x18007c8db  mov     [rsp+4E0h+rgIndices], 4
0x18007c8e3  call    cs:__imp_SafeArrayPutElement
0x18007c8e9  mov     ebx, eax
0x18007c8eb  test    eax, eax
0x18007c8ed  js      short loc_18007C924
0x18007c8ef  mov     rcx, [r14+60h]
0x18007c8f3  lea     rdx, [rbp+3E0h+var_458]
0x18007c8f7  neg     [rsp+4E0h+var_480]
0x18007c8fb  mov     [rsp+4E0h+var_4B8], 0
0x18007c904  sbb     r9d, r9d
0x18007c907  mov     [rsp+4E0h+var_4C0], rdx
0x18007c90c  mov     rax, [rcx]
0x18007c90f  xor     edx, edx
0x18007c911  add     r9d, 2
0x18007c915  mov     rax, [rax+20h]
0x18007c919  lea     r8d, [rdx+6]
0x18007c91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c922  mov     ebx, eax
0x18007c924  lea     rcx, [rsp+4E0h+pvarg]; pvarg
0x18007c929  call    cs:__imp_VariantInit
0x18007c92f  test    r15, r15
0x18007c932  jz      short loc_18007C93D
0x18007c934  mov     rcx, r15; bstrString
0x18007c937  call    cs:__imp_SysFreeString
0x18007c93d  test    rsi, rsi
0x18007c940  jz      short loc_18007C94B
0x18007c942  mov     rcx, rsi; bstrString
0x18007c945  call    cs:__imp_SysFreeString
0x18007c94b  test    r12, r12
0x18007c94e  jz      short loc_18007C959
0x18007c950  mov     rcx, r12; bstrString
0x18007c953  call    cs:__imp_SysFreeString
0x18007c959  test    rdi, rdi
0x18007c95c  jz      short loc_18007C967
0x18007c95e  mov     rcx, rdi; psa
0x18007c961  call    cs:__imp_SafeArrayDestroy
0x18007c967  lea     rcx, [rsp+4E0h+pstm]
0x18007c96c  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x18007c971  mov     eax, ebx
0x18007c973  mov     rcx, [rbp+3E0h+var_40]
0x18007c97a  xor     rcx, rsp; StackCookie
0x18007c97d  call    __security_check_cookie
0x18007c982  mov     rbx, [rsp+4E0h+arg_8]
0x18007c98a  add     rsp, 4B0h
0x18007c991  pop     r15
0x18007c993  pop     r14
0x18007c995  pop     r13
0x18007c997  pop     r12
0x18007c999  pop     rdi
0x18007c99a  pop     rsi
0x18007c99b  pop     rbp
0x18007c99c  retn
```
