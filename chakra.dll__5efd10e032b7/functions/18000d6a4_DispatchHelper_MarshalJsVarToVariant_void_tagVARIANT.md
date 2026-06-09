# DispatchHelper::MarshalJsVarToVariant(void *,tagVARIANT *)

- ea: `0x18000d6a4`
- end: `0x18000d9fc`
- name: `?MarshalJsVarToVariant@DispatchHelper@@CAJPEAXPEAUtagVARIANT@@@Z`
- size: `856`
- prototype: `static int(void *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18000c218`
- `0x18000d670`

## callees

- `0x18000d6a4`
- `0x18001aa70`
- `0x1800822a0`
- `0x1800a3d24`
- `0x180187b50`
- `0x1801947a8`
- `0x1802408d4`
- `0x18039b2a0`
- `0x1803bbf58`
- `0x1803e64e0`
- `0x180447990`
- `0x18052dd68`
- `0x18052ee6c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000d86e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000d86e`
- `OLEAUT32!__imp_VariantInit` at `0x18000d6c7`
- `OLEAUT32!__imp_VariantInit` at `0x18000d6c7`
- `OLEAUT32!__imp_VariantCopy` at `0x18000d906`
- `OLEAUT32!__imp_VariantCopy` at `0x18000d906`

## pseudocode

```c
__int64 __fastcall DispatchHelper::MarshalJsVarToVariant(unsigned __int64 a1, struct tagVARIANT *a2)
{
  unsigned int v2; // ebp
  int v4; // ecx
  int v5; // ecx
  struct Js::JavascriptString *v7; // rax
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rcx
  double v14; // xmm0_8
  __int64 v15; // rax
  UINT v16; // ebx
  const OLECHAR *OriginalStringReference; // rax
  BSTR v18; // rax
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  bool v23; // zf
  int v24; // ecx
  struct Js::RecyclableObject *v25; // rbx
  struct IDispatch *Dispatch; // rax
  const VARIANTARG *v27; // rdx
  struct Js::JavascriptSymbol *v29; // rax
  int v30; // ecx
  int v31; // ecx
  bool v32; // zf
  int v33; // ecx
  bool v34; // zf
  int v35; // ecx
  bool v36; // zf
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  bool v41; // zf
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx

  v2 = 0;
  VariantInit(a2);
  if ( !a1 )
  {
    a2->vt = 1;
    return v2;
  }
  Js::JavascriptLibrary::CheckAndConvertCopyOnAccessNativeIntArray<void *>(a1);
  if ( HIWORD(a1) == 1 )
    goto LABEL_21;
  if ( a1 >= 0x4000000000000LL )
    goto LABEL_23;
  v4 = **(_DWORD **)(a1 + 8);
  if ( v4 > 43 )
  {
    if ( v4 > 59 )
    {
      if ( v4 > 66 )
      {
        v44 = v4 - 68;
        if ( !v44 )
          goto LABEL_85;
        v45 = v44 - 1;
        if ( !v45 )
          goto LABEL_85;
        v46 = v45 - 6;
        if ( !v46 )
          goto LABEL_85;
        v47 = v46 - 1;
        if ( !v47 )
          goto LABEL_85;
        v24 = v47 - 1;
        if ( !v24 )
          goto LABEL_24;
LABEL_84:
        if ( v24 == 1 )
          goto LABEL_85;
        goto LABEL_24;
      }
      if ( v4 == 66 )
        goto LABEL_85;
      v42 = v4 - 60;
      v41 = v42 == 0;
    }
    else
    {
      if ( v4 == 59 )
        goto LABEL_85;
      if ( v4 > 51 )
      {
        v37 = v4 - 52;
        v36 = v37 == 0;
        goto LABEL_63;
      }
      if ( v4 == 51 )
        goto LABEL_85;
      v40 = v4 - 44;
      if ( !v40 )
        goto LABEL_85;
      v42 = v40 - 1;
      v41 = v42 == 0;
    }
    if ( v41 )
      goto LABEL_85;
    v43 = v42 - 1;
    if ( !v43 )
      goto LABEL_85;
    v33 = v43 - 1;
    v32 = v33 == 0;
LABEL_57:
    if ( v32 )
      goto LABEL_85;
    v35 = v33 - 1;
    v34 = v35 == 0;
    goto LABEL_59;
  }
  if ( v4 == 43 )
    goto LABEL_85;
  if ( v4 > 27 )
  {
    if ( v4 <= 35 )
    {
      if ( v4 == 35 )
        goto LABEL_85;
      v30 = v4 - 28;
      if ( !v30 )
        goto LABEL_85;
      v31 = v30 - 1;
      if ( !v31 )
        goto LABEL_85;
      v33 = v31 - 2;
      v32 = v33 == 0;
      goto LABEL_57;
    }
    v37 = v4 - 36;
    v36 = v37 == 0;
LABEL_63:
    if ( v36 )
      goto LABEL_85;
    v38 = v37 - 1;
    if ( !v38 )
      goto LABEL_85;
    v39 = v38 - 1;
    if ( !v39 )
      goto LABEL_85;
    v35 = v39 - 2;
    v34 = v35 == 0;
LABEL_59:
    if ( v34 )
      goto LABEL_85;
    v24 = v35 - 1;
    v23 = v24 == 0;
    goto LABEL_42;
  }
  if ( v4 == 27 )
    goto LABEL_85;
  if ( v4 == 7 )
  {
    v7 = Js::JavascriptString::FromVar((void *)a1);
LABEL_16:
    if ( v7 == *(struct Js::JavascriptString **)(*(_QWORD *)(*((_QWORD *)v7 + 1) + 8LL) + 4528LL) )
    {
      a2->llVal = 0;
    }
    else
    {
      v16 = *((_DWORD *)v7 + 6);
      OriginalStringReference = (const OLECHAR *)Js::JavascriptString::GetOriginalStringReference(v7);
      v18 = SysAllocStringLen(OriginalStringReference, v16);
      a2->llVal = (LONGLONG)v18;
      if ( !v18 )
        v2 = -2147024882;
    }
    a2->vt = 8;
    return v2;
  }
  if ( v4 <= 7 )
  {
    if ( !v4 )
    {
      a2->vt = 0;
      return v2;
    }
    v5 = v4 - 1;
    if ( !v5 )
    {
      a2->vt = 1;
      return v2;
    }
    v8 = v5 - 1;
    if ( !v8 )
    {
      a2->vt = 11;
      a2->iVal = -(*((_DWORD *)Js::JavascriptBoolean::FromVar((void *)a1) + 4) != 0);
      return v2;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
LABEL_21:
      a2->vt = 3;
      a2->lVal = a1;
      return v2;
    }
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( !v11 )
      {
        a2->vt = 5;
        v14 = (double)(int)*(_QWORD *)(Js::JavascriptTypedNumber<__int64>::FromVar(a1) + 16);
LABEL_33:
        a2->dblVal = v14;
        return v2;
      }
      if ( v11 == 1 )
      {
        a2->vt = 5;
        v12 = Js::JavascriptTypedNumber<__int64>::FromVar(a1);
        v13 = *(_QWORD *)(v12 + 16);
        if ( v13 < 0 )
        {
          v15 = *(_QWORD *)(v12 + 16) & 1LL | (*(_QWORD *)(v12 + 16) >> 1);
          v14 = (double)(int)v15 + (double)(int)v15;
        }
        else
        {
          v14 = (double)(int)v13;
        }
        goto LABEL_33;
      }
      goto LABEL_24;
    }
LABEL_23:
    a2->vt = 5;
    a2->llVal = a1 ^ 0xFFFC000000000000uLL;
    return v2;
  }
  v19 = v4 - 8;
  if ( !v19 )
  {
    v29 = Js::JavascriptSymbol::FromVar((void *)a1);
    v7 = Js::JavascriptSymbol::ToString(
           *((const struct Js::PropertyRecord **)v29 + 2),
           *(struct Js::ScriptContext **)(*(_QWORD *)(*((_QWORD *)v29 + 1) + 8LL) + 1088LL));
    goto LABEL_16;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
LABEL_24:
    if ( (*(_BYTE *)(*((_QWORD *)Js::RecyclableObject::FromVar((void *)a1) + 1) + 4LL) & 8) == 0 )
      return (unsigned int)-2147467263;
LABEL_85:
    DispatchHelper::MarshalJsVarToDispatchVariant((void *)a1, a2);
    return v2;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
    a2->vt = 7;
    a2->llVal = *((_QWORD *)Js::JavascriptVariantDate::FromVar((void *)a1) + 2);
    return v2;
  }
  v22 = v21 - 12;
  if ( v22 )
  {
    v24 = v22 - 3;
    v23 = v24 == 0;
LABEL_42:
    if ( v23 )
      goto LABEL_85;
    goto LABEL_84;
  }
  v25 = Js::RecyclableObject::FromVar((void *)a1);
  Dispatch = HostDispatch::GetDispatch(v25);
  if ( Dispatch )
  {
    a2->vt = 9;
    a2->llVal = (LONGLONG)Dispatch;
  }
  else
  {
    v27 = (const VARIANTARG *)((*(_QWORD *)(*((_QWORD *)v25 + 3) + 16LL) + 16LL)
                             & -(__int64)(*(_QWORD *)(*((_QWORD *)v25 + 3) + 16LL) != 0));
    if ( v27 )
      return (unsigned int)VariantCopy(a2, v27);
    else
      return (unsigned int)MapHr(-2147024891, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d6a4  mov     rax, rsp
0x18000d6a7  mov     [rax+18h], rbx
0x18000d6ab  mov     [rax+20h], rbp
0x18000d6af  mov     [rax+10h], rdx
0x18000d6b3  mov     [rax+8], rcx
0x18000d6b7  push    rsi
0x18000d6b8  push    rdi
0x18000d6b9  push    r14
0x18000d6bb  sub     rsp, 20h
0x18000d6bf  mov     rcx, rdx; pvarg
0x18000d6c2  xor     ebp, ebp
0x18000d6c4  mov     rdi, rdx
0x18000d6c7  call    cs:__imp_VariantInit
0x18000d6ce  nop     dword ptr [rax+rax+00h]
0x18000d6d3  mov     rbx, [rsp+38h+arg_0]
0x18000d6d8  test    rbx, rbx
0x18000d6db  jz      loc_18000D9F2
0x18000d6e1  mov     rcx, rbx
0x18000d6e4  call    ??$CheckAndConvertCopyOnAccessNativeIntArray@PEAX@JavascriptLibrary@Js@@SAXQEAX@Z; Js::JavascriptLibrary::CheckAndConvertCopyOnAccessNativeIntArray<void *>(void * const)
0x18000d6e9  mov     rax, rbx
0x18000d6ec  lea     esi, [rbp+1]
0x18000d6ef  shr     rax, 30h
0x18000d6f3  cmp     rax, rsi
0x18000d6f6  jz      loc_18000D79B
0x18000d6fc  mov     rax, 4000000000000h
0x18000d706  cmp     rbx, rax
0x18000d709  jnb     loc_18000D7C0
0x18000d70f  mov     rax, [rbx+8]
0x18000d713  lea     r14d, [rbp+8]
0x18000d717  mov     ecx, [rax]
0x18000d719  cmp     ecx, 2Bh ; '+'
0x18000d71c  jg      loc_18000D995
0x18000d722  jz      loc_18000D9E2
0x18000d728  cmp     ecx, 1Bh
0x18000d72b  jg      loc_18000D956
0x18000d731  jz      loc_18000D9E2
0x18000d737  lea     edx, [rbp+7]
0x18000d73a  cmp     ecx, edx
0x18000d73c  jz      short loc_18000D76C
0x18000d73e  jg      loc_18000D88E
0x18000d744  test    ecx, ecx
0x18000d746  jz      short loc_18000D765
0x18000d748  sub     ecx, esi
0x18000d74a  jnz     short loc_18000D793
0x18000d74c  mov     [rdi], si
0x18000d74f  mov     rbx, [rsp+38h+arg_10]
0x18000d754  mov     eax, ebp
0x18000d756  mov     rbp, [rsp+38h+arg_18]
0x18000d75b  add     rsp, 20h
0x18000d75f  pop     r14
0x18000d761  pop     rdi
0x18000d762  pop     rsi
0x18000d763  retn
0x18000d765  xor     eax, eax
0x18000d767  mov     [rdi], ax
0x18000d76a  jmp     short loc_18000D74F
0x18000d76c  mov     rcx, rbx; void *
0x18000d76f  call    ?FromVar@JavascriptString@Js@@SAPEAV12@PEAX@Z; Js::JavascriptString::FromVar(void *)
0x18000d774  mov     rcx, [rax+8]
0x18000d778  mov     rdx, [rcx+8]
0x18000d77c  cmp     rax, [rdx+11B0h]
0x18000d783  jnz     loc_18000D85E
0x18000d789  mov     [rdi+8], rbp
0x18000d78d  mov     [rdi], r14w
0x18000d791  jmp     short loc_18000D74F
0x18000d793  sub     ecx, esi
0x18000d795  jz      short loc_18000D7A5
0x18000d797  sub     ecx, esi
0x18000d799  jnz     short loc_18000D7FB
0x18000d79b  mov     word ptr [rdi], 3
0x18000d7a0  mov     [rdi+8], ebx
0x18000d7a3  jmp     short loc_18000D74F
0x18000d7a5  mov     rcx, rbx; void *
0x18000d7a8  mov     word ptr [rdi], 0Bh
0x18000d7ad  call    ?FromVar@JavascriptBoolean@Js@@SAPEAV12@PEAX@Z; Js::JavascriptBoolean::FromVar(void *)
0x18000d7b2  mov     ecx, [rax+10h]
0x18000d7b5  neg     ecx
0x18000d7b7  sbb     ax, ax
0x18000d7ba  mov     [rdi+8], ax
0x18000d7be  jmp     short loc_18000D74F
0x18000d7c0  mov     rax, 0FFFC000000000000h
0x18000d7ca  mov     word ptr [rdi], 5
0x18000d7cf  xor     rbx, rax
0x18000d7d2  mov     [rdi+8], rbx
0x18000d7d6  jmp     loc_18000D74F
0x18000d7db  mov     rcx, rbx; void *
0x18000d7de  call    ?FromVar@RecyclableObject@Js@@SAPEAV12@PEAX@Z; Js::RecyclableObject::FromVar(void *)
0x18000d7e3  mov     rcx, [rax+8]
0x18000d7e7  test    [rcx+4], r14b
0x18000d7eb  jnz     loc_18000D9E2
0x18000d7f1  mov     ebp, 80004001h
0x18000d7f6  jmp     loc_18000D74F
0x18000d7fb  sub     ecx, esi
0x18000d7fd  jz      short loc_18000D7C0
0x18000d7ff  sub     ecx, esi
0x18000d801  jz      short loc_18000D83E
0x18000d803  cmp     ecx, esi
0x18000d805  jnz     short loc_18000D7DB
0x18000d807  mov     rcx, rbx
0x18000d80a  mov     word ptr [rdi], 5
0x18000d80f  call    ?FromVar@?$JavascriptTypedNumber@_J@Js@@SAPEAV12@PEAX@Z; Js::JavascriptTypedNumber<__int64>::FromVar(void *)
0x18000d814  xorps   xmm0, xmm0
0x18000d817  mov     rcx, [rax+10h]
0x18000d81b  test    rcx, rcx
0x18000d81e  js      short loc_18000D827
0x18000d820  cvtsi2sd xmm0, rcx
0x18000d825  jmp     short loc_18000D854
0x18000d827  mov     rax, rcx
0x18000d82a  and     rcx, rsi
0x18000d82d  shr     rax, 1
0x18000d830  or      rax, rcx
0x18000d833  cvtsi2sd xmm0, rax
0x18000d838  addsd   xmm0, xmm0
0x18000d83c  jmp     short loc_18000D854
0x18000d83e  mov     rcx, rbx
0x18000d841  mov     word ptr [rdi], 5
0x18000d846  call    ?FromVar@?$JavascriptTypedNumber@_J@Js@@SAPEAV12@PEAX@Z; Js::JavascriptTypedNumber<__int64>::FromVar(void *)
0x18000d84b  xorps   xmm0, xmm0
0x18000d84e  cvtsi2sd xmm0, qword ptr [rax+10h]
0x18000d854  movsd   qword ptr [rdi+8], xmm0
0x18000d859  jmp     loc_18000D74F
0x18000d85e  mov     ebx, [rax+18h]
0x18000d861  mov     rcx, rax; this
0x18000d864  call    ?GetOriginalStringReference@JavascriptString@Js@@UEAAPEBXXZ; Js::JavascriptString::GetOriginalStringReference(void)
0x18000d869  mov     edx, ebx; ui
0x18000d86b  mov     rcx, rax; strIn
0x18000d86e  call    cs:__imp_SysAllocStringLen
0x18000d875  nop     dword ptr [rax+rax+00h]
0x18000d87a  test    rax, rax
0x18000d87d  mov     [rdi+8], rax
0x18000d881  mov     ecx, 8007000Eh
0x18000d886  cmovz   ebp, ecx
0x18000d889  jmp     loc_18000D78D
0x18000d88e  sub     ecx, r14d
0x18000d891  jz      loc_18000D931
0x18000d897  sub     ecx, esi
0x18000d899  jz      loc_18000D7DB
0x18000d89f  sub     ecx, esi
0x18000d8a1  jz      short loc_18000D919
0x18000d8a3  sub     ecx, 0Ch
0x18000d8a6  jz      short loc_18000D8BA
0x18000d8a8  sub     ecx, 3
0x18000d8ab  jmp     short loc_18000D8AF
0x18000d8ad  sub     ecx, esi
0x18000d8af  jnz     loc_18000D9DA
0x18000d8b5  jmp     loc_18000D9E2
0x18000d8ba  mov     rcx, rbx; void *
0x18000d8bd  call    ?FromVar@RecyclableObject@Js@@SAPEAV12@PEAX@Z; Js::RecyclableObject::FromVar(void *)
0x18000d8c2  mov     rcx, rax; this
0x18000d8c5  mov     rbx, rax
0x18000d8c8  call    ?GetDispatch@HostDispatch@@QEAAPEAUIDispatch@@XZ; HostDispatch::GetDispatch(void)
0x18000d8cd  test    rax, rax
0x18000d8d0  jz      short loc_18000D8E0
0x18000d8d2  mov     word ptr [rdi], 9
0x18000d8d7  mov     [rdi+8], rax
0x18000d8db  jmp     loc_18000D74F
0x18000d8e0  mov     rax, [rbx+18h]
0x18000d8e4  mov     rcx, [rax+10h]
0x18000d8e8  lea     rax, [rcx+10h]
0x18000d8ec  neg     rcx
0x18000d8ef  sbb     rdx, rdx
0x18000d8f2  and     rdx, rax; enum ErrorTypeEnum *
0x18000d8f5  jnz     short loc_18000D903
0x18000d8f7  mov     ecx, 80070005h; int
0x18000d8fc  call    ?MapHr@@YAJJPEAW4ErrorTypeEnum@@@Z; MapHr(long,ErrorTypeEnum *)
0x18000d901  jmp     short loc_18000D912
0x18000d903  mov     rcx, rdi; pvargDest
0x18000d906  call    cs:__imp_VariantCopy
0x18000d90d  nop     dword ptr [rax+rax+00h]
0x18000d912  mov     ebp, eax
0x18000d914  jmp     loc_18000D74F
0x18000d919  mov     rcx, rbx; void *
0x18000d91c  mov     [rdi], dx
0x18000d91f  call    ?FromVar@JavascriptVariantDate@Js@@SAPEAV12@PEAX@Z; Js::JavascriptVariantDate::FromVar(void *)
0x18000d924  mov     rcx, [rax+10h]
0x18000d928  mov     [rdi+8], rcx
0x18000d92c  jmp     loc_18000D74F
0x18000d931  mov     rcx, rbx; void *
0x18000d934  call    ?FromVar@JavascriptSymbol@Js@@SAPEAV12@PEAX@Z; Js::JavascriptSymbol::FromVar(void *)
0x18000d939  mov     rcx, [rax+8]
0x18000d93d  mov     rdx, [rcx+8]
0x18000d941  mov     rcx, [rax+10h]; struct Js::PropertyRecord *
0x18000d945  mov     rdx, [rdx+440h]; struct Js::ScriptContext *
0x18000d94c  call    ?ToString@JavascriptSymbol@Js@@SAPEAVJavascriptString@2@PEBVPropertyRecord@2@PEAVScriptContext@2@@Z; Js::JavascriptSymbol::ToString(Js::PropertyRecord const *,Js::ScriptContext *)
0x18000d951  jmp     loc_18000D774
0x18000d956  cmp     ecx, 23h ; '#'
0x18000d959  jg      short loc_18000D981
0x18000d95b  jz      loc_18000D9E2
0x18000d961  sub     ecx, 1Ch
0x18000d964  jz      short loc_18000D9E2
0x18000d966  sub     ecx, esi
0x18000d968  jz      short loc_18000D9E2
0x18000d96a  sub     ecx, 2
0x18000d96d  jmp     short loc_18000D971
0x18000d96f  sub     ecx, esi
0x18000d971  jz      short loc_18000D9E2
0x18000d973  sub     ecx, esi
0x18000d975  jmp     short loc_18000D97A
0x18000d977  sub     ecx, 2
0x18000d97a  jz      short loc_18000D9E2
0x18000d97c  jmp     loc_18000D8AD
0x18000d981  sub     ecx, 24h ; '$'
0x18000d984  jmp     short loc_18000D989
0x18000d986  sub     ecx, 34h ; '4'
0x18000d989  jz      short loc_18000D9E2
0x18000d98b  sub     ecx, esi
0x18000d98d  jz      short loc_18000D9E2
0x18000d98f  sub     ecx, esi
0x18000d991  jz      short loc_18000D9E2
0x18000d993  jmp     short loc_18000D977
0x18000d995  cmp     ecx, 3Bh ; ';'
0x18000d998  jg      short loc_18000D9B7
0x18000d99a  jz      short loc_18000D9E2
0x18000d99c  cmp     ecx, 33h ; '3'
0x18000d99f  jg      short loc_18000D986
0x18000d9a1  jz      short loc_18000D9E2
0x18000d9a3  sub     ecx, 2Ch ; ','
0x18000d9a6  jz      short loc_18000D9E2
0x18000d9a8  sub     ecx, esi
0x18000d9aa  jmp     short loc_18000D9AF
0x18000d9ac  sub     ecx, 3Ch ; '<'
0x18000d9af  jz      short loc_18000D9E2
0x18000d9b1  sub     ecx, esi
0x18000d9b3  jz      short loc_18000D9E2
0x18000d9b5  jmp     short loc_18000D96F
0x18000d9b7  cmp     ecx, 42h ; 'B'
0x18000d9ba  jg      short loc_18000D9C0
0x18000d9bc  jz      short loc_18000D9E2
0x18000d9be  jmp     short loc_18000D9AC
0x18000d9c0  sub     ecx, 44h ; 'D'
0x18000d9c3  jz      short loc_18000D9E2
0x18000d9c5  sub     ecx, esi
0x18000d9c7  jz      short loc_18000D9E2
0x18000d9c9  sub     ecx, 6
0x18000d9cc  jz      short loc_18000D9E2
0x18000d9ce  sub     ecx, esi
0x18000d9d0  jz      short loc_18000D9E2
0x18000d9d2  sub     ecx, esi
0x18000d9d4  jz      loc_18000D7DB
0x18000d9da  cmp     ecx, esi
0x18000d9dc  jnz     loc_18000D7DB
0x18000d9e2  mov     rdx, rdi; struct tagVARIANT *
0x18000d9e5  mov     rcx, rbx; void *
0x18000d9e8  call    ?MarshalJsVarToDispatchVariant@DispatchHelper@@CAXPEAXPEAUtagVARIANT@@@Z; DispatchHelper::MarshalJsVarToDispatchVariant(void *,tagVARIANT *)
0x18000d9ed  jmp     loc_18000D74F
0x18000d9f2  mov     word ptr [rdi], 1
0x18000d9f7  jmp     loc_18000D74F
```
