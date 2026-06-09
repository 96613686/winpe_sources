# GetConfigTimeSpan(IAppHostElement *,ushort const *,unsigned __int64 *)

- ea: `0x180002cec`
- end: `0x180002dcf`
- name: `?GetConfigTimeSpan@@YAJPEAUIAppHostElement@@PEBGPEA_K@Z`
- size: `227`
- prototype: `__int64 __fastcall(struct IAppHostElement *, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002e44`

## callees

- `0x180002cec`
- `0x180009010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002d28`
- `OLEAUT32!__imp_SysAllocString` at `0x180002d28`
- `OLEAUT32!__imp_SysFreeString` at `0x180002da9`
- `OLEAUT32!__imp_SysFreeString` at `0x180002da9`
- `OLEAUT32!__imp_VariantInit` at `0x180002d1b`
- `OLEAUT32!__imp_VariantInit` at `0x180002d1b`
- `OLEAUT32!__imp_VariantClear` at `0x180002d9b`
- `OLEAUT32!__imp_VariantClear` at `0x180002d9b`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002d84`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002d84`

## pseudocode

```c
__int64 __fastcall GetConfigTimeSpan(struct IAppHostElement *a1, const unsigned __int16 *a2, unsigned __int64 *a3)
{
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  HRESULT v7; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+78h] [rbp+30h] BYREF

  v10 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v5 = SysAllocString(L"pingInterval");
  v6 = v5;
  if ( v5 )
  {
    v7 = ((__int64 (__fastcall *)(struct IAppHostElement *, BSTR, __int64 *))a1->lpVtbl->GetPropertyByName)(
           a1,
           v5,
           &v10);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v10 + 32LL))(v10, &pvarg);
      if ( v7 >= 0 )
      {
        v7 = VariantChangeType(&pvarg, &pvarg, 0, 0x15u);
        if ( v7 >= 0 )
          *a3 = pvarg.ullVal;
      }
    }
  }
  else
  {
    v7 = -2147024882;
  }
  VariantClear(&pvarg);
  if ( v6 )
    SysFreeString(v6);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002cec  mov     [rsp-20h+arg_8], rdx
0x180002cf1  push    rbp
0x180002cf2  push    rbx
0x180002cf3  push    rsi
0x180002cf4  push    rdi
0x180002cf5  mov     rbp, rsp
0x180002cf8  sub     rsp, 48h
0x180002cfc  mov     rbx, rcx
0x180002cff  mov     [rbp+arg_8], 0
0x180002d07  xorps   xmm0, xmm0
0x180002d0a  lea     rcx, [rbp+pvarg]; pvarg
0x180002d0e  xor     eax, eax
0x180002d10  mov     rsi, r8
0x180002d13  movups  xmmword ptr [rbp+pvarg], xmm0
0x180002d17  mov     qword ptr [rbp+pvarg+10h], rax
0x180002d1b  call    cs:__imp_VariantInit
0x180002d21  lea     rcx, aPinginterval; "pingInterval"
0x180002d28  call    cs:__imp_SysAllocString
0x180002d2e  mov     rdi, rax
0x180002d31  test    rax, rax
0x180002d34  jnz     short loc_180002D3D
0x180002d36  mov     ebx, 8007000Eh
0x180002d3b  jmp     short loc_180002D97
0x180002d3d  mov     rax, [rbx]
0x180002d40  lea     r8, [rbp+arg_8]
0x180002d44  mov     rdx, rdi
0x180002d47  mov     rcx, rbx
0x180002d4a  mov     rax, [rax+58h]
0x180002d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d53  mov     ebx, eax
0x180002d55  test    eax, eax
0x180002d57  js      short loc_180002D97
0x180002d59  mov     rcx, [rbp+arg_8]
0x180002d5d  lea     rdx, [rbp+pvarg]
0x180002d61  mov     rax, [rcx]
0x180002d64  mov     rax, [rax+20h]
0x180002d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d6d  mov     ebx, eax
0x180002d6f  test    eax, eax
0x180002d71  js      short loc_180002D97
0x180002d73  mov     r9d, 15h; vt
0x180002d79  lea     rdx, [rbp+pvarg]; pvarSrc
0x180002d7d  xor     r8d, r8d; wFlags
0x180002d80  lea     rcx, [rbp+pvarg]; pvargDest
0x180002d84  call    cs:__imp_VariantChangeType
0x180002d8a  mov     ebx, eax
0x180002d8c  test    eax, eax
0x180002d8e  js      short loc_180002D97
0x180002d90  mov     rax, qword ptr [rbp+pvarg+8]
0x180002d94  mov     [rsi], rax
0x180002d97  lea     rcx, [rbp+pvarg]; pvarg
0x180002d9b  call    cs:__imp_VariantClear
0x180002da1  test    rdi, rdi
0x180002da4  jz      short loc_180002DAF
0x180002da6  mov     rcx, rdi; bstrString
0x180002da9  call    cs:__imp_SysFreeString
0x180002daf  mov     rcx, [rbp+arg_8]
0x180002db3  test    rcx, rcx
0x180002db6  jz      short loc_180002DC4
0x180002db8  mov     rax, [rcx]
0x180002dbb  mov     rax, [rax+10h]
0x180002dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dc4  mov     eax, ebx
0x180002dc6  add     rsp, 48h
0x180002dca  pop     rdi
0x180002dcb  pop     rsi
0x180002dcc  pop     rbx
0x180002dcd  pop     rbp
0x180002dce  retn
```
