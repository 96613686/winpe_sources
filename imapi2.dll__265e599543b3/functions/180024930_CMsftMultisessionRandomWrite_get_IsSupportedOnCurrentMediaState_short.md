# CMsftMultisessionRandomWrite::get_IsSupportedOnCurrentMediaState(short *)

- ea: `0x180024930`
- end: `0x180024b48`
- name: `?get_IsSupportedOnCurrentMediaState@CMsftMultisessionRandomWrite@@UEAAJPEAF@Z`
- size: `536`
- prototype: `__int64 __fastcall(CMsftMultisessionRandomWrite *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ea20`
- `0x18001cb0c`
- `0x180024930`
- `0x18004a010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180024acd`
- `OLEAUT32!__imp_VariantClear` at `0x180024ae2`
- `OLEAUT32!__imp_VariantClear` at `0x180024acd`
- `OLEAUT32!__imp_VariantClear` at `0x180024ae2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180024a7c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180024a7c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180024a63`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180024a63`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180024aac`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180024aac`

## pseudocode

```c
__int64 __fastcall CMsftMultisessionRandomWrite::get_IsSupportedOnCurrentMediaState(
        CMsftMultisessionRandomWrite *this,
        __int16 *a2)
{
  HRESULT LBound; // ebx
  int v5; // edx
  __int64 i; // rcx
  __int64 v7; // rcx
  struct tagSAFEARRAY **v8; // rdx
  int v9; // eax
  __int64 v10; // rcx
  int v12; // [rsp+20h] [rbp-30h] BYREF
  SAFEARRAY *psa; // [rsp+28h] [rbp-28h] BYREF
  __int64 v14; // [rsp+30h] [rbp-20h] BYREF
  VARIANTARG pv; // [rsp+38h] [rbp-18h] BYREF
  LONG plLbound; // [rsp+88h] [rbp+38h] BYREF
  LONG rgIndices; // [rsp+90h] [rbp+40h] BYREF
  LONG plUbound; // [rsp+98h] [rbp+48h] BYREF

  v14 = 0;
  v12 = 0;
  if ( a2 )
  {
    LBound = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 8) + 104LL))(
               *((_QWORD *)this + 8),
               &v14);
    if ( LBound < 0 )
      goto LABEL_32;
    LBound = (*(__int64 (__fastcall **)(_QWORD, __int64, __int16 *))(**((_QWORD **)this + 8) + 64LL))(
               *((_QWORD *)this + 8),
               v14,
               a2);
    if ( LBound < 0 )
      goto LABEL_32;
    if ( *a2 == -1 )
    {
      LBound = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 8) + 232LL))(*((_QWORD *)this + 8), &v12);
      if ( LBound < 0 )
        goto LABEL_32;
    }
    v5 = v12;
    if ( *a2 == -1 )
    {
      *a2 = 0;
      for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
      {
        if ( v5 == *((_DWORD *)qword_18005A890 + i) )
        {
          *a2 = -1;
          break;
        }
      }
      if ( *a2 == -1 )
      {
        if ( v5 == 10 )
        {
          v7 = v14;
          psa = 0;
          *a2 = 0;
          plLbound = 0;
          plUbound = 0;
          rgIndices = 0;
          LBound = (*(__int64 (__fastcall **)(__int64, SAFEARRAY **))(*(_QWORD *)v7 + 200LL))(v7, &psa);
          plUbound = 0;
          v9 = 0;
          plLbound = 0;
          if ( LBound >= 0 )
          {
            LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
            if ( LBound >= 0 )
              LBound = SafeArrayGetUBound(psa, 1u, &plUbound);
            v9 = plLbound;
          }
          while ( 1 )
          {
            rgIndices = v9;
            if ( v9 > plUbound || LBound < 0 )
              break;
            memset(&pv, 0, sizeof(pv));
            LBound = SafeArrayGetElement(psa, &rgIndices, &pv);
            if ( LBound >= 0 )
            {
              if ( pv.vt == 3 && pv.lVal == 19 )
              {
                *a2 = -1;
                VariantClear(&pv);
                break;
              }
              VariantClear(&pv);
            }
            v9 = rgIndices + 1;
          }
          Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&psa, v8);
          if ( LBound < 0 )
            goto LABEL_32;
        }
        if ( *a2 == -1 )
        {
          v10 = *((_QWORD *)this + 8);
          plLbound = 0;
          LBound = (*(__int64 (__fastcall **)(__int64, LONG *))(*(_QWORD *)v10 + 144LL))(v10, &plLbound);
          if ( LBound < 0 || !plLbound || (plLbound & 0xFC00) != 0 )
LABEL_32:
            *a2 = 0;
        }
      }
    }
  }
  else
  {
    LBound = -2147467261;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x180024930  push    rbp
0x180024932  push    rbx
0x180024933  push    rsi
0x180024934  push    rdi
0x180024935  push    r15
0x180024937  mov     rbp, rsp
0x18002493a  sub     rsp, 50h
0x18002493e  mov     [rbp+var_20], 0
0x180024946  mov     rdi, rdx
0x180024949  mov     [rbp+var_30], 0
0x180024950  mov     rsi, rcx
0x180024953  test    rdx, rdx
0x180024956  jnz     short loc_180024962
0x180024958  mov     ebx, 80004003h
0x18002495d  jmp     loc_180024B32
0x180024962  mov     rcx, [rcx+40h]
0x180024966  lea     rdx, [rbp+var_20]
0x18002496a  mov     rax, [rcx]
0x18002496d  mov     rax, [rax+68h]
0x180024971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024976  mov     ebx, eax
0x180024978  test    eax, eax
0x18002497a  js      loc_180024B2D
0x180024980  mov     rcx, [rsi+40h]
0x180024984  mov     r8, rdi
0x180024987  mov     rdx, [rbp+var_20]
0x18002498b  mov     rax, [rcx]
0x18002498e  mov     rax, [rax+40h]
0x180024992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024997  mov     ebx, eax
0x180024999  test    eax, eax
0x18002499b  js      loc_180024B2D
0x1800249a1  or      r15d, 0FFFFFFFFh
0x1800249a5  cmp     [rdi], r15w
0x1800249a9  jnz     short loc_1800249CC
0x1800249ab  mov     rcx, [rsi+40h]
0x1800249af  lea     rdx, [rbp+var_30]
0x1800249b3  mov     rax, [rcx]
0x1800249b6  mov     rax, [rax+0E8h]
0x1800249bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249c2  mov     ebx, eax
0x1800249c4  test    eax, eax
0x1800249c6  js      loc_180024B2D
0x1800249cc  mov     edx, [rbp+var_30]
0x1800249cf  cmp     [rdi], r15w
0x1800249d3  jnz     loc_180024B32
0x1800249d9  xor     eax, eax
0x1800249db  mov     [rdi], ax
0x1800249de  xor     ecx, ecx
0x1800249e0  cmp     ecx, 5
0x1800249e3  jnb     short loc_1800249FA
0x1800249e5  lea     r8, qword_18005A890
0x1800249ec  cmp     edx, [r8+rcx*4]
0x1800249f0  jz      short loc_1800249F6
0x1800249f2  inc     ecx
0x1800249f4  jmp     short loc_1800249E0
0x1800249f6  mov     [rdi], r15w
0x1800249fa  cmp     [rdi], r15w
0x1800249fe  jnz     loc_180024B32
0x180024a04  cmp     edx, 0Ah
0x180024a07  jnz     loc_180024AF5
0x180024a0d  mov     rcx, [rbp+var_20]
0x180024a11  lea     rdx, [rbp+psa]
0x180024a15  xor     eax, eax
0x180024a17  mov     [rbp+psa], 0
0x180024a1f  mov     [rdi], ax
0x180024a22  mov     [rbp+plLbound], 0
0x180024a29  mov     [rbp+plUbound], 0
0x180024a30  mov     [rbp+rgIndices], 0
0x180024a37  mov     rax, [rcx]
0x180024a3a  mov     rax, [rax+0C8h]
0x180024a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a46  mov     ebx, eax
0x180024a48  mov     [rbp+plUbound], 0
0x180024a4f  xor     eax, eax
0x180024a51  mov     [rbp+plLbound], eax
0x180024a54  test    ebx, ebx
0x180024a56  js      short loc_180024A87
0x180024a58  mov     rcx, [rbp+psa]; psa
0x180024a5c  lea     r8, [rbp+plLbound]; plLbound
0x180024a60  lea     edx, [rax+1]; nDim
0x180024a63  call    cs:__imp_SafeArrayGetLBound
0x180024a69  mov     ebx, eax
0x180024a6b  test    eax, eax
0x180024a6d  js      short loc_180024A84
0x180024a6f  mov     rcx, [rbp+psa]; psa
0x180024a73  lea     r8, [rbp+plUbound]; plUbound
0x180024a77  mov     edx, 1; nDim
0x180024a7c  call    cs:__imp_SafeArrayGetUBound
0x180024a82  mov     ebx, eax
0x180024a84  mov     eax, [rbp+plLbound]
0x180024a87  mov     [rbp+rgIndices], eax
0x180024a8a  cmp     eax, [rbp+plUbound]
0x180024a8d  jg      short loc_180024AE8
0x180024a8f  test    ebx, ebx
0x180024a91  js      short loc_180024AE8
0x180024a93  mov     rcx, [rbp+psa]; psa
0x180024a97  lea     r8, [rbp+pv]; pv
0x180024a9b  xorps   xmm0, xmm0
0x180024a9e  lea     rdx, [rbp+rgIndices]; rgIndices
0x180024aa2  xor     eax, eax
0x180024aa4  movups  [rbp+pv], xmm0
0x180024aa8  mov     [rbp+var_8], rax
0x180024aac  call    cs:__imp_SafeArrayGetElement
0x180024ab2  mov     ebx, eax
0x180024ab4  test    eax, eax
0x180024ab6  js      short loc_180024AD3
0x180024ab8  mov     eax, 3
0x180024abd  cmp     ax, word ptr [rbp+pv]
0x180024ac1  jnz     short loc_180024AC9
0x180024ac3  cmp     dword ptr [rbp+pv+8], 13h
0x180024ac7  jz      short loc_180024ADA
0x180024ac9  lea     rcx, [rbp+pv]; pvarg
0x180024acd  call    cs:__imp_VariantClear
0x180024ad3  mov     eax, [rbp+rgIndices]
0x180024ad6  inc     eax
0x180024ad8  jmp     short loc_180024A87
0x180024ada  lea     rcx, [rbp+pv]; pvarg
0x180024ade  mov     [rdi], r15w
0x180024ae2  call    cs:__imp_VariantClear
0x180024ae8  lea     rcx, [rbp+psa]; this
0x180024aec  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x180024af1  test    ebx, ebx
0x180024af3  js      short loc_180024B2D
0x180024af5  cmp     [rdi], r15w
0x180024af9  jnz     short loc_180024B32
0x180024afb  mov     rcx, [rsi+40h]
0x180024aff  lea     rdx, [rbp+plLbound]
0x180024b03  mov     [rbp+plLbound], 0
0x180024b0a  mov     rax, [rcx]
0x180024b0d  mov     rax, [rax+90h]
0x180024b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b19  mov     ebx, eax
0x180024b1b  test    eax, eax
0x180024b1d  js      short loc_180024B2D
0x180024b1f  mov     eax, [rbp+plLbound]
0x180024b22  test    eax, eax
0x180024b24  jz      short loc_180024B2D
0x180024b26  test    eax, 0FC00h
0x180024b2b  jz      short loc_180024B32
0x180024b2d  xor     eax, eax
0x180024b2f  mov     [rdi], ax
0x180024b32  lea     rcx, [rbp+var_20]
0x180024b36  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180024b3b  mov     eax, ebx
0x180024b3d  add     rsp, 50h
0x180024b41  pop     r15
0x180024b43  pop     rdi
0x180024b44  pop     rsi
0x180024b45  pop     rbx
0x180024b46  pop     rbp
0x180024b47  retn
```
