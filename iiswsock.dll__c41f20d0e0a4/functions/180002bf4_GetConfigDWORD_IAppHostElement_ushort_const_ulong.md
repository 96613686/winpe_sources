# GetConfigDWORD(IAppHostElement *,ushort const *,ulong *)

- ea: `0x180002bf4`
- end: `0x180002ce4`
- name: `?GetConfigDWORD@@YAJPEAUIAppHostElement@@PEBGPEAK@Z`
- size: `240`
- prototype: `int(struct IAppHostElement *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002e44`

## callees

- `0x180002bf4`
- `0x180009010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002c34`
- `OLEAUT32!__imp_SysAllocString` at `0x180002c34`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cb4`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cb4`
- `OLEAUT32!__imp_VariantInit` at `0x180002c2b`
- `OLEAUT32!__imp_VariantInit` at `0x180002c2b`
- `OLEAUT32!__imp_VariantClear` at `0x180002ca6`
- `OLEAUT32!__imp_VariantClear` at `0x180002ca6`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002c90`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002c90`

## pseudocode

```c
__int64 __fastcall GetConfigDWORD(struct IAppHostElement *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  BSTR v6; // rax
  OLECHAR *v7; // rdi
  HRESULT v8; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  __int64 v11; // [rsp+78h] [rbp+38h] BYREF

  v11 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
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
0x180002bf4  mov     [rsp-18h+arg_0], rbx
0x180002bf9  mov     [rsp-18h+arg_8], rsi
0x180002bfe  push    rbp
0x180002bff  push    rdi
0x180002c00  push    r14
0x180002c02  mov     rbp, rsp
0x180002c05  sub     rsp, 40h
0x180002c09  mov     rsi, rcx
0x180002c0c  mov     [rbp+arg_18], 0
0x180002c14  xorps   xmm0, xmm0
0x180002c17  lea     rcx, [rbp+pvarg]; pvarg
0x180002c1b  xor     eax, eax
0x180002c1d  mov     r14, r8
0x180002c20  movups  xmmword ptr [rbp+pvarg], xmm0
0x180002c24  mov     qword ptr [rbp+pvarg+10h], rax
0x180002c28  mov     rbx, rdx
0x180002c2b  call    cs:__imp_VariantInit
0x180002c31  mov     rcx, rbx; psz
0x180002c34  call    cs:__imp_SysAllocString
0x180002c3a  mov     rdi, rax
0x180002c3d  test    rax, rax
0x180002c40  jnz     short loc_180002C49
0x180002c42  mov     ebx, 8007000Eh
0x180002c47  jmp     short loc_180002CA2
0x180002c49  mov     rax, [rsi]
0x180002c4c  lea     r8, [rbp+arg_18]
0x180002c50  mov     rdx, rdi
0x180002c53  mov     rcx, rsi
0x180002c56  mov     rax, [rax+58h]
0x180002c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c5f  mov     ebx, eax
0x180002c61  test    eax, eax
0x180002c63  js      short loc_180002CA2
0x180002c65  mov     rcx, [rbp+arg_18]
0x180002c69  lea     rdx, [rbp+pvarg]
0x180002c6d  mov     rax, [rcx]
0x180002c70  mov     rax, [rax+20h]
0x180002c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c79  mov     ebx, eax
0x180002c7b  test    eax, eax
0x180002c7d  js      short loc_180002CA2
0x180002c7f  mov     r9d, 13h; vt
0x180002c85  lea     rdx, [rbp+pvarg]; pvarSrc
0x180002c89  xor     r8d, r8d; wFlags
0x180002c8c  lea     rcx, [rbp+pvarg]; pvargDest
0x180002c90  call    cs:__imp_VariantChangeType
0x180002c96  mov     ebx, eax
0x180002c98  test    eax, eax
0x180002c9a  js      short loc_180002CA2
0x180002c9c  mov     eax, dword ptr [rbp+pvarg+8]
0x180002c9f  mov     [r14], eax
0x180002ca2  lea     rcx, [rbp+pvarg]; pvarg
0x180002ca6  call    cs:__imp_VariantClear
0x180002cac  test    rdi, rdi
0x180002caf  jz      short loc_180002CBA
0x180002cb1  mov     rcx, rdi; bstrString
0x180002cb4  call    cs:__imp_SysFreeString
0x180002cba  mov     rcx, [rbp+arg_18]
0x180002cbe  test    rcx, rcx
0x180002cc1  jz      short loc_180002CCF
0x180002cc3  mov     rax, [rcx]
0x180002cc6  mov     rax, [rax+10h]
0x180002cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ccf  mov     rsi, [rsp+40h+arg_8]
0x180002cd4  mov     eax, ebx
0x180002cd6  mov     rbx, [rsp+40h+arg_0]
0x180002cdb  add     rsp, 40h
0x180002cdf  pop     r14
0x180002ce1  pop     rdi
0x180002ce2  pop     rbp
0x180002ce3  retn
```
