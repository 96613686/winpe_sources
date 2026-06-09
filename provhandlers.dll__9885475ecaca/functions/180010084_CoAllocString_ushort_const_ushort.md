# CoAllocString(ushort const *,ushort * *)

- ea: `0x180010084`
- end: `0x180010114`
- name: `?CoAllocString@@YAJPEBGPEAPEAG@Z`
- size: `144`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010820`
- `0x1800109a0`
- `0x180027220`
- `0x180027880`
- `0x18002e580`
- `0x18002e8f0`
- `0x18002eae0`

## callees

- `0x180010084`
- `0x180012004`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800100c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800100c9`

## pseudocode

```c
__int64 __fastcall CoAllocString(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v5; // rsi
  unsigned __int16 *v6; // rax
  unsigned int v7; // ebx
  unsigned __int16 **v9; // [rsp+20h] [rbp-38h]
  unsigned __int64 *v10; // [rsp+28h] [rbp-30h]
  unsigned int v11; // [rsp+30h] [rbp-28h]

  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  v5 = v2 + 1;
  *a2 = 0;
  if ( v2 + 1 >= v2 && is_mul_ok(v5, 2u) )
  {
    v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5);
    *a2 = v6;
    v7 = v6 == 0 ? 0x8007000E : 0;
    if ( v6 )
      StringCchCopyNExW(v6, v2 + 1, a1, v2, v9, v10, v11);
  }
  else
  {
    return (unsigned int)-2147024362;
  }
  return v7;
}

```

## disassembly

```asm
0x180010084  mov     [rsp+arg_0], rbx
0x180010089  mov     [rsp+arg_10], rbp
0x18001008e  push    rsi
0x18001008f  push    rdi
0x180010090  push    r14
0x180010092  sub     rsp, 40h
0x180010096  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001009a  mov     rbx, rdx
0x18001009d  xor     r14d, r14d
0x1800100a0  mov     rbp, rcx
0x1800100a3  inc     rdi
0x1800100a6  cmp     [rcx+rdi*2], r14w
0x1800100ab  jnz     short loc_1800100A3
0x1800100ad  lea     rsi, [rdi+1]
0x1800100b1  mov     [rdx], r14
0x1800100b4  cmp     rsi, rdi
0x1800100b7  jb      short loc_1800100FA
0x1800100b9  mov     eax, 2
0x1800100be  mul     rsi
0x1800100c1  test    rdx, rdx
0x1800100c4  jnz     short loc_1800100FA
0x1800100c6  mov     rcx, rax; cb
0x1800100c9  call    cs:__imp_CoTaskMemAlloc
0x1800100cf  mov     [rbx], rax
0x1800100d2  mov     rcx, rax
0x1800100d5  neg     rcx
0x1800100d8  sbb     ebx, ebx
0x1800100da  not     ebx
0x1800100dc  and     ebx, 8007000Eh
0x1800100e2  test    rax, rax
0x1800100e5  jz      short loc_1800100FF
0x1800100e7  mov     r9, rdi; unsigned __int64
0x1800100ea  mov     r8, rbp; unsigned __int16 *
0x1800100ed  mov     rdx, rsi; unsigned __int64
0x1800100f0  mov     rcx, rax; unsigned __int16 *
0x1800100f3  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800100f8  jmp     short loc_1800100FF
0x1800100fa  mov     ebx, 80070216h
0x1800100ff  mov     rbp, [rsp+58h+arg_10]
0x180010104  mov     eax, ebx
0x180010106  mov     rbx, [rsp+58h+arg_0]
0x18001010b  add     rsp, 40h
0x18001010f  pop     r14
0x180010111  pop     rdi
0x180010112  pop     rsi
0x180010113  retn
```
