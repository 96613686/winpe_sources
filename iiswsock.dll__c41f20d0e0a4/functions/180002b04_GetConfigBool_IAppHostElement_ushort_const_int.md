# GetConfigBool(IAppHostElement *,ushort const *,int *)

- ea: `0x180002b04`
- end: `0x180002bec`
- name: `?GetConfigBool@@YAJPEAUIAppHostElement@@PEBGPEAH@Z`
- size: `232`
- prototype: `__int64 __fastcall(struct IAppHostElement *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002e44`

## callees

- `0x180002b04`
- `0x180009010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002b40`
- `OLEAUT32!__imp_SysAllocString` at `0x180002b40`
- `OLEAUT32!__imp_SysFreeString` at `0x180002bc6`
- `OLEAUT32!__imp_SysFreeString` at `0x180002bc6`
- `OLEAUT32!__imp_VariantInit` at `0x180002b33`
- `OLEAUT32!__imp_VariantInit` at `0x180002b33`
- `OLEAUT32!__imp_VariantClear` at `0x180002bb8`
- `OLEAUT32!__imp_VariantClear` at `0x180002bb8`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002b9c`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002b9c`

## pseudocode

```c
__int64 __fastcall GetConfigBool(struct IAppHostElement *a1, const unsigned __int16 *a2, int *a3)
{
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  HRESULT v7; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+78h] [rbp+30h] BYREF

  v10 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v5 = SysAllocString(L"enabled");
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
        v7 = VariantChangeType(&pvarg, &pvarg, 0, 0xBu);
        if ( v7 >= 0 )
          *a3 = pvarg.iVal == -1;
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
0x180002b04  mov     [rsp-20h+arg_8], rdx
0x180002b09  push    rbp
0x180002b0a  push    rbx
0x180002b0b  push    rsi
0x180002b0c  push    rdi
0x180002b0d  mov     rbp, rsp
0x180002b10  sub     rsp, 48h
0x180002b14  mov     rbx, rcx
0x180002b17  mov     [rbp+arg_8], 0
0x180002b1f  xorps   xmm0, xmm0
0x180002b22  lea     rcx, [rbp+pvarg]; pvarg
0x180002b26  xor     eax, eax
0x180002b28  mov     rsi, r8
0x180002b2b  movups  xmmword ptr [rbp+pvarg], xmm0
0x180002b2f  mov     qword ptr [rbp+pvarg+10h], rax
0x180002b33  call    cs:__imp_VariantInit
0x180002b39  lea     rcx, psz; "enabled"
0x180002b40  call    cs:__imp_SysAllocString
0x180002b46  mov     rdi, rax
0x180002b49  test    rax, rax
0x180002b4c  jnz     short loc_180002B55
0x180002b4e  mov     ebx, 8007000Eh
0x180002b53  jmp     short loc_180002BB4
0x180002b55  mov     rax, [rbx]
0x180002b58  lea     r8, [rbp+arg_8]
0x180002b5c  mov     rdx, rdi
0x180002b5f  mov     rcx, rbx
0x180002b62  mov     rax, [rax+58h]
0x180002b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b6b  mov     ebx, eax
0x180002b6d  test    eax, eax
0x180002b6f  js      short loc_180002BB4
0x180002b71  mov     rcx, [rbp+arg_8]
0x180002b75  lea     rdx, [rbp+pvarg]
0x180002b79  mov     rax, [rcx]
0x180002b7c  mov     rax, [rax+20h]
0x180002b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b85  mov     ebx, eax
0x180002b87  test    eax, eax
0x180002b89  js      short loc_180002BB4
0x180002b8b  mov     r9d, 0Bh; vt
0x180002b91  lea     rdx, [rbp+pvarg]; pvarSrc
0x180002b95  xor     r8d, r8d; wFlags
0x180002b98  lea     rcx, [rbp+pvarg]; pvargDest
0x180002b9c  call    cs:__imp_VariantChangeType
0x180002ba2  mov     ebx, eax
0x180002ba4  test    eax, eax
0x180002ba6  js      short loc_180002BB4
0x180002ba8  xor     eax, eax
0x180002baa  cmp     word ptr [rbp+pvarg+8], 0FFFFh
0x180002baf  setz    al
0x180002bb2  mov     [rsi], eax
0x180002bb4  lea     rcx, [rbp+pvarg]; pvarg
0x180002bb8  call    cs:__imp_VariantClear
0x180002bbe  test    rdi, rdi
0x180002bc1  jz      short loc_180002BCC
0x180002bc3  mov     rcx, rdi; bstrString
0x180002bc6  call    cs:__imp_SysFreeString
0x180002bcc  mov     rcx, [rbp+arg_8]
0x180002bd0  test    rcx, rcx
0x180002bd3  jz      short loc_180002BE1
0x180002bd5  mov     rax, [rcx]
0x180002bd8  mov     rax, [rax+10h]
0x180002bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be1  mov     eax, ebx
0x180002be3  add     rsp, 48h
0x180002be7  pop     rdi
0x180002be8  pop     rsi
0x180002be9  pop     rbx
0x180002bea  pop     rbp
0x180002beb  retn
```
