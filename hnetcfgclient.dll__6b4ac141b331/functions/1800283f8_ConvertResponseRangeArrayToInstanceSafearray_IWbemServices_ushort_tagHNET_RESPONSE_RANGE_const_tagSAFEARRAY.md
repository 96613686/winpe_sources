# ConvertResponseRangeArrayToInstanceSafearray(IWbemServices *,ushort,tagHNET_RESPONSE_RANGE * const,tagSAFEARRAY * *)

- ea: `0x1800283f8`
- end: `0x18002859e`
- name: `?ConvertResponseRangeArrayToInstanceSafearray@@YAJPEAUIWbemServices@@GQEAUtagHNET_RESPONSE_RANGE@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(struct IWbemServices *, unsigned __int16, struct tagHNET_RESPONSE_RANGE *const, struct tagSAFEARRAY **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000ddf0`
- `0x180023550`

## callees

- `0x1800283f8`
- `0x18002878c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180028436`
- `OLEAUT32!__imp_SysAllocString` at `0x180028436`
- `OLEAUT32!__imp_SysFreeString` at `0x18002847f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002847f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002849e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002849e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002855c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002855c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180028525`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180028525`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConvertResponseRangeArrayToInstanceSafearray(
        struct IWbemServices *a1,
        unsigned __int16 a2,
        struct tagHNET_RESPONSE_RANGE *const a3,
        struct tagSAFEARRAY **a4)
{
  ULONG v5; // r14d
  OLECHAR *v8; // rdi
  HRESULT v9; // ebx
  SAFEARRAY *v10; // rsi
  HRESULT (__stdcall *GetObjectA)(IWbemServices *, const BSTR, int, IWbemContext *, IWbemClassObject **, IWbemCallResult **); // rax
  bool v12; // sf
  unsigned __int16 i; // di
  struct IWbemClassObjectVtbl *lpVtbl; // rax
  LONG rgIndices; // [rsp+40h] [rbp-30h] BYREF
  struct IWbemClassObject *v17; // [rsp+48h] [rbp-28h] BYREF
  __int64 v18; // [rsp+50h] [rbp-20h] BYREF
  void *pv; // [rsp+58h] [rbp-18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp-10h] BYREF

  v5 = a2;
  v18 = 0;
  v17 = 0;
  pv = 0;
  v8 = SysAllocString(L"HNet_ResponseRange");
  if ( !v8 )
    goto LABEL_2;
  v10 = 0;
  GetObjectA = a1->lpVtbl->GetObjectA;
  v18 = 0;
  v9 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, _QWORD, __int64 *, _QWORD))GetObjectA)(
         a1,
         v8,
         0,
         0,
         &v18,
         0);
  SysFreeString(v8);
  v12 = v9 < 0;
  if ( v9 )
  {
LABEL_14:
    if ( v12 )
      goto LABEL_16;
  }
  else
  {
    rgsabound.lLbound = 0;
    rgsabound.cElements = v5;
    v10 = SafeArrayCreate(0xDu, 1u, &rgsabound);
    if ( !v10 )
    {
LABEL_2:
      v9 = -2147024882;
      goto LABEL_16;
    }
    for ( i = 0; i < (unsigned __int16)v5; ++i )
    {
      v17 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWbemClassObject **))(*(_QWORD *)v18 + 120LL))(
             v18,
             0,
             &v17);
      if ( v9 )
      {
        v12 = v9 < 0;
        goto LABEL_14;
      }
      v9 = CopyStructToResponseInstance((struct tagHNET_RESPONSE_RANGE *const)((char *)a3 + 6 * i), v17);
      lpVtbl = v17->lpVtbl;
      if ( v9 < 0 )
      {
        ((void (*)(void))lpVtbl->Release)();
        goto LABEL_16;
      }
      ((void (__fastcall *)(struct IWbemClassObject *, GUID *, void **))lpVtbl->QueryInterface)(
        v17,
        &GUID_00000000_0000_0000_c000_000000000046,
        &pv);
      rgIndices = i;
      v9 = SafeArrayPutElement(v10, &rgIndices, pv);
      (*(void (__fastcall **)(void *))(*(_QWORD *)pv + 16LL))(pv);
      ((void (__fastcall *)(struct IWbemClassObject *))v17->lpVtbl->Release)(v17);
      if ( v9 < 0 )
      {
        SafeArrayDestroy(v10);
        goto LABEL_16;
      }
    }
  }
  *a4 = v10;
  v9 = 0;
LABEL_16:
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800283f8  push    rbp
0x1800283fa  push    rbx
0x1800283fb  push    rsi
0x1800283fc  push    rdi
0x1800283fd  push    r12
0x1800283ff  push    r14
0x180028401  push    r15
0x180028403  mov     rbp, rsp
0x180028406  sub     rsp, 70h
0x18002840a  mov     rbx, rcx
0x18002840d  movzx   r14d, dx
0x180028411  lea     rcx, ?c_wszHnetResponseRange@@3QBGB; "HNet_ResponseRange"
0x180028418  mov     [rbp+var_20], 0
0x180028420  mov     r15, r9
0x180028423  mov     [rbp+var_28], 0
0x18002842b  mov     r12, r8
0x18002842e  mov     [rbp+pv], 0
0x180028436  call    cs:__imp_SysAllocString
0x18002843c  mov     rdi, rax
0x18002843f  test    rax, rax
0x180028442  jnz     short loc_18002844E
0x180028444  mov     ebx, 8007000Eh
0x180028449  jmp     loc_180028578
0x18002844e  mov     rax, [rbx]
0x180028451  lea     rcx, [rbp+var_20]
0x180028455  xor     esi, esi
0x180028457  xor     r9d, r9d
0x18002845a  mov     [rsp+70h+var_48], rsi
0x18002845f  xor     r8d, r8d
0x180028462  mov     [rsp+70h+var_50], rcx
0x180028467  mov     rdx, rdi
0x18002846a  mov     rax, [rax+30h]
0x18002846e  mov     rcx, rbx
0x180028471  mov     [rbp+var_20], rsi
0x180028475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002847a  mov     rcx, rdi; bstrString
0x18002847d  mov     ebx, eax
0x18002847f  call    cs:__imp_SysFreeString
0x180028485  test    ebx, ebx
0x180028487  jnz     loc_180028571
0x18002848d  lea     ecx, [rsi+0Dh]; vt
0x180028490  mov     [rbp+rgsabound.lLbound], esi
0x180028493  lea     r8, [rbp+rgsabound]; rgsabound
0x180028497  mov     [rbp+rgsabound.cElements], r14d
0x18002849b  lea     edx, [rsi+1]; cDims
0x18002849e  call    cs:__imp_SafeArrayCreate
0x1800284a4  mov     rsi, rax
0x1800284a7  test    rax, rax
0x1800284aa  jz      short loc_180028444
0x1800284ac  xor     edi, edi
0x1800284ae  cmp     di, r14w
0x1800284b2  jnb     loc_180028573
0x1800284b8  mov     rcx, [rbp+var_20]
0x1800284bc  lea     r8, [rbp+var_28]
0x1800284c0  mov     [rbp+var_28], 0
0x1800284c8  xor     edx, edx
0x1800284ca  mov     rax, [rcx]
0x1800284cd  mov     rax, [rax+78h]
0x1800284d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284d6  mov     ebx, eax
0x1800284d8  test    eax, eax
0x1800284da  jnz     loc_18002856F
0x1800284e0  mov     rdx, [rbp+var_28]; struct IWbemClassObject *
0x1800284e4  movzx   eax, di
0x1800284e7  lea     rcx, [rax+rax*2]
0x1800284eb  lea     rcx, [r12+rcx*2]; struct tagHNET_RESPONSE_RANGE *
0x1800284ef  call    ?CopyStructToResponseInstance@@YAJPEAUtagHNET_RESPONSE_RANGE@@PEAUIWbemClassObject@@@Z; CopyStructToResponseInstance(tagHNET_RESPONSE_RANGE *,IWbemClassObject *)
0x1800284f4  mov     rcx, [rbp+var_28]
0x1800284f8  mov     ebx, eax
0x1800284fa  test    eax, eax
0x1800284fc  mov     rax, [rcx]
0x1800284ff  js      short loc_180028564
0x180028501  mov     rax, [rax]
0x180028504  lea     r8, [rbp+pv]
0x180028508  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002850f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028514  mov     r8, [rbp+pv]; pv
0x180028518  lea     rdx, [rbp+rgIndices]; rgIndices
0x18002851c  movzx   eax, di
0x18002851f  mov     rcx, rsi; psa
0x180028522  mov     [rbp+rgIndices], eax
0x180028525  call    cs:__imp_SafeArrayPutElement
0x18002852b  mov     rcx, [rbp+pv]
0x18002852f  mov     ebx, eax
0x180028531  mov     rax, [rcx]
0x180028534  mov     rax, [rax+10h]
0x180028538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002853d  mov     rcx, [rbp+var_28]
0x180028541  mov     rax, [rcx]
0x180028544  mov     rax, [rax+10h]
0x180028548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002854d  test    ebx, ebx
0x18002854f  js      short loc_180028559
0x180028551  inc     di
0x180028554  jmp     loc_1800284AE
0x180028559  mov     rcx, rsi; psa
0x18002855c  call    cs:__imp_SafeArrayDestroy
0x180028562  jmp     short loc_180028578
0x180028564  mov     rax, [rax+10h]
0x180028568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002856d  jmp     short loc_180028578
0x18002856f  test    ebx, ebx
0x180028571  js      short loc_180028578
0x180028573  mov     [r15], rsi
0x180028576  xor     ebx, ebx
0x180028578  mov     rcx, [rbp+var_20]
0x18002857c  test    rcx, rcx
0x18002857f  jz      short loc_18002858D
0x180028581  mov     rax, [rcx]
0x180028584  mov     rax, [rax+10h]
0x180028588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002858d  mov     eax, ebx
0x18002858f  add     rsp, 70h
0x180028593  pop     r15
0x180028595  pop     r14
0x180028597  pop     r12
0x180028599  pop     rdi
0x18002859a  pop     rsi
0x18002859b  pop     rbx
0x18002859c  pop     rbp
0x18002859d  retn
```
