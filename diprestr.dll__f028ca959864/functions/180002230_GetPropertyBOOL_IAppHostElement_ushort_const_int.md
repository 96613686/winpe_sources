# GetPropertyBOOL(IAppHostElement *,ushort const *,int *)

- ea: `0x180002230`
- end: `0x180002329`
- name: `?GetPropertyBOOL@@YAJPEAUIAppHostElement@@PEBGPEAH@Z`
- size: `249`
- prototype: `int(struct IAppHostElement *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002604`

## callees

- `0x180002230`
- `0x180007010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002273`
- `OLEAUT32!__imp_SysAllocString` at `0x180002273`
- `OLEAUT32!__imp_SysFreeString` at `0x1800022f9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800022f9`
- `OLEAUT32!__imp_VariantInit` at `0x18000226a`
- `OLEAUT32!__imp_VariantInit` at `0x18000226a`
- `OLEAUT32!__imp_VariantClear` at `0x1800022eb`
- `OLEAUT32!__imp_VariantClear` at `0x1800022eb`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800022cf`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800022cf`

## pseudocode

```c
__int64 __fastcall GetPropertyBOOL(struct IAppHostElement *a1, const unsigned __int16 *a2, int *a3)
{
  BSTR v6; // rax
  OLECHAR *v7; // rdi
  HRESULT v8; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  __int64 v11; // [rsp+70h] [rbp+30h] BYREF

  v11 = 0;
  pvarg.pRecInfo = 0;
  *a3 = 0;
  *(_OWORD *)&pvarg.vt = 0;
  VariantInit(&pvarg);
  v6 = SysAllocString(a2);
  v7 = v6;
  if ( v6 )
  {
    v8 = ((__int64 (__fastcall *)(struct IAppHostElement *, BSTR, __int64 *))a1->lpVtbl->GetPropertyByName)(
           a1,
           v6,
           &v11);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v11 + 32LL))(v11, &pvarg);
      if ( v8 >= 0 )
      {
        v8 = VariantChangeType(&pvarg, &pvarg, 0, 0xBu);
        if ( v8 >= 0 )
          *a3 = pvarg.iVal == -1;
      }
    }
  }
  else
  {
    v8 = -2147024882;
  }
  VariantClear(&pvarg);
  if ( v7 )
    SysFreeString(v7);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002230  mov     [rsp-18h+arg_0], rbx
0x180002235  mov     [rsp-18h+arg_8], rsi
0x18000223a  push    rbp
0x18000223b  push    rdi
0x18000223c  push    r14
0x18000223e  mov     rbp, rsp
0x180002241  sub     rsp, 40h
0x180002245  xor     eax, eax
0x180002247  mov     [rbp+arg_10], 0
0x18000224f  mov     r14, rcx
0x180002252  mov     qword ptr [rbp+pvarg+10h], rax
0x180002256  xorps   xmm0, xmm0
0x180002259  mov     [r8], eax
0x18000225c  lea     rcx, [rbp+pvarg]; pvarg
0x180002260  mov     rsi, r8
0x180002263  movups  xmmword ptr [rbp+pvarg], xmm0
0x180002267  mov     rbx, rdx
0x18000226a  call    cs:__imp_VariantInit
0x180002270  mov     rcx, rbx; psz
0x180002273  call    cs:__imp_SysAllocString
0x180002279  mov     rdi, rax
0x18000227c  test    rax, rax
0x18000227f  jnz     short loc_180002288
0x180002281  mov     ebx, 8007000Eh
0x180002286  jmp     short loc_1800022E7
0x180002288  mov     rax, [r14]
0x18000228b  lea     r8, [rbp+arg_10]
0x18000228f  mov     rdx, rdi
0x180002292  mov     rcx, r14
0x180002295  mov     rax, [rax+58h]
0x180002299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000229e  mov     ebx, eax
0x1800022a0  test    eax, eax
0x1800022a2  js      short loc_1800022E7
0x1800022a4  mov     rcx, [rbp+arg_10]
0x1800022a8  lea     rdx, [rbp+pvarg]
0x1800022ac  mov     rax, [rcx]
0x1800022af  mov     rax, [rax+20h]
0x1800022b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022b8  mov     ebx, eax
0x1800022ba  test    eax, eax
0x1800022bc  js      short loc_1800022E7
0x1800022be  mov     r9d, 0Bh; vt
0x1800022c4  lea     rdx, [rbp+pvarg]; pvarSrc
0x1800022c8  xor     r8d, r8d; wFlags
0x1800022cb  lea     rcx, [rbp+pvarg]; pvargDest
0x1800022cf  call    cs:__imp_VariantChangeType
0x1800022d5  mov     ebx, eax
0x1800022d7  test    eax, eax
0x1800022d9  js      short loc_1800022E7
0x1800022db  xor     eax, eax
0x1800022dd  cmp     word ptr [rbp+pvarg+8], 0FFFFh
0x1800022e2  setz    al
0x1800022e5  mov     [rsi], eax
0x1800022e7  lea     rcx, [rbp+pvarg]; pvarg
0x1800022eb  call    cs:__imp_VariantClear
0x1800022f1  test    rdi, rdi
0x1800022f4  jz      short loc_1800022FF
0x1800022f6  mov     rcx, rdi; bstrString
0x1800022f9  call    cs:__imp_SysFreeString
0x1800022ff  mov     rcx, [rbp+arg_10]
0x180002303  test    rcx, rcx
0x180002306  jz      short loc_180002314
0x180002308  mov     rax, [rcx]
0x18000230b  mov     rax, [rax+10h]
0x18000230f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002314  mov     rsi, [rsp+40h+arg_8]
0x180002319  mov     eax, ebx
0x18000231b  mov     rbx, [rsp+40h+arg_0]
0x180002320  add     rsp, 40h
0x180002324  pop     r14
0x180002326  pop     rdi
0x180002327  pop     rbp
0x180002328  retn
```
