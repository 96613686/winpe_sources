# GetPropertyDWORD(IAppHostElement *,ushort const *,ulong *)

- ea: `0x180002330`
- end: `0x180002422`
- name: `?GetPropertyDWORD@@YAJPEAUIAppHostElement@@PEBGPEAK@Z`
- size: `242`
- prototype: `int(struct IAppHostElement *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002604`

## callees

- `0x180002330`
- `0x180007010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002373`
- `OLEAUT32!__imp_SysAllocString` at `0x180002373`
- `OLEAUT32!__imp_SysFreeString` at `0x1800023f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800023f2`
- `OLEAUT32!__imp_VariantInit` at `0x18000236a`
- `OLEAUT32!__imp_VariantInit` at `0x18000236a`
- `OLEAUT32!__imp_VariantClear` at `0x1800023e4`
- `OLEAUT32!__imp_VariantClear` at `0x1800023e4`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800023cf`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800023cf`

## pseudocode

```c
__int64 __fastcall GetPropertyDWORD(struct IAppHostElement *a1, const unsigned __int16 *a2, unsigned int *a3)
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
        v8 = VariantChangeType(&pvarg, &pvarg, 0, 0x13u);
        if ( v8 >= 0 )
          *a3 = pvarg.cyVal.Lo;
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
0x180002330  mov     [rsp-18h+arg_0], rbx
0x180002335  mov     [rsp-18h+arg_8], rsi
0x18000233a  push    rbp
0x18000233b  push    rdi
0x18000233c  push    r14
0x18000233e  mov     rbp, rsp
0x180002341  sub     rsp, 40h
0x180002345  xor     eax, eax
0x180002347  mov     [rbp+arg_10], 0
0x18000234f  mov     r14, rcx
0x180002352  mov     qword ptr [rbp+pvarg+10h], rax
0x180002356  xorps   xmm0, xmm0
0x180002359  mov     [r8], eax
0x18000235c  lea     rcx, [rbp+pvarg]; pvarg
0x180002360  mov     rsi, r8
0x180002363  movups  xmmword ptr [rbp+pvarg], xmm0
0x180002367  mov     rbx, rdx
0x18000236a  call    cs:__imp_VariantInit
0x180002370  mov     rcx, rbx; psz
0x180002373  call    cs:__imp_SysAllocString
0x180002379  mov     rdi, rax
0x18000237c  test    rax, rax
0x18000237f  jnz     short loc_180002388
0x180002381  mov     ebx, 8007000Eh
0x180002386  jmp     short loc_1800023E0
0x180002388  mov     rax, [r14]
0x18000238b  lea     r8, [rbp+arg_10]
0x18000238f  mov     rdx, rdi
0x180002392  mov     rcx, r14
0x180002395  mov     rax, [rax+58h]
0x180002399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000239e  mov     ebx, eax
0x1800023a0  test    eax, eax
0x1800023a2  js      short loc_1800023E0
0x1800023a4  mov     rcx, [rbp+arg_10]
0x1800023a8  lea     rdx, [rbp+pvarg]
0x1800023ac  mov     rax, [rcx]
0x1800023af  mov     rax, [rax+20h]
0x1800023b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023b8  mov     ebx, eax
0x1800023ba  test    eax, eax
0x1800023bc  js      short loc_1800023E0
0x1800023be  mov     r9d, 13h; vt
0x1800023c4  lea     rdx, [rbp+pvarg]; pvarSrc
0x1800023c8  xor     r8d, r8d; wFlags
0x1800023cb  lea     rcx, [rbp+pvarg]; pvargDest
0x1800023cf  call    cs:__imp_VariantChangeType
0x1800023d5  mov     ebx, eax
0x1800023d7  test    eax, eax
0x1800023d9  js      short loc_1800023E0
0x1800023db  mov     eax, dword ptr [rbp+pvarg+8]
0x1800023de  mov     [rsi], eax
0x1800023e0  lea     rcx, [rbp+pvarg]; pvarg
0x1800023e4  call    cs:__imp_VariantClear
0x1800023ea  test    rdi, rdi
0x1800023ed  jz      short loc_1800023F8
0x1800023ef  mov     rcx, rdi; bstrString
0x1800023f2  call    cs:__imp_SysFreeString
0x1800023f8  mov     rcx, [rbp+arg_10]
0x1800023fc  test    rcx, rcx
0x1800023ff  jz      short loc_18000240D
0x180002401  mov     rax, [rcx]
0x180002404  mov     rax, [rax+10h]
0x180002408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240d  mov     rsi, [rsp+40h+arg_8]
0x180002412  mov     eax, ebx
0x180002414  mov     rbx, [rsp+40h+arg_0]
0x180002419  add     rsp, 40h
0x18000241d  pop     r14
0x18000241f  pop     rdi
0x180002420  pop     rbp
0x180002421  retn
```
