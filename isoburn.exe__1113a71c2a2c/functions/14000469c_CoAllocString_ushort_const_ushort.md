# CoAllocString(ushort const *,ushort * *)

- ea: `0x14000469c`
- end: `0x14000472c`
- name: `?CoAllocString@@YAJPEBGPEAPEAG@Z`
- size: `144`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140008890`
- `0x14000aac0`
- `0x14000be50`
- `0x14000e89c`

## callees

- `0x14000469c`
- `0x140008f78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400046e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400046e1`

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
0x14000469c  mov     [rsp+arg_0], rbx
0x1400046a1  mov     [rsp+arg_10], rbp
0x1400046a6  push    rsi
0x1400046a7  push    rdi
0x1400046a8  push    r14
0x1400046aa  sub     rsp, 40h
0x1400046ae  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400046b2  mov     rbx, rdx
0x1400046b5  xor     r14d, r14d
0x1400046b8  mov     rbp, rcx
0x1400046bb  inc     rdi
0x1400046be  cmp     [rcx+rdi*2], r14w
0x1400046c3  jnz     short loc_1400046BB
0x1400046c5  lea     rsi, [rdi+1]
0x1400046c9  mov     [rdx], r14
0x1400046cc  cmp     rsi, rdi
0x1400046cf  jb      short loc_140004712
0x1400046d1  mov     eax, 2
0x1400046d6  mul     rsi
0x1400046d9  test    rdx, rdx
0x1400046dc  jnz     short loc_140004712
0x1400046de  mov     rcx, rax; cb
0x1400046e1  call    cs:__imp_CoTaskMemAlloc
0x1400046e7  mov     [rbx], rax
0x1400046ea  mov     rcx, rax
0x1400046ed  neg     rcx
0x1400046f0  sbb     ebx, ebx
0x1400046f2  not     ebx
0x1400046f4  and     ebx, 8007000Eh
0x1400046fa  test    rax, rax
0x1400046fd  jz      short loc_140004717
0x1400046ff  mov     r9, rdi; unsigned __int64
0x140004702  mov     r8, rbp; unsigned __int16 *
0x140004705  mov     rdx, rsi; unsigned __int64
0x140004708  mov     rcx, rax; unsigned __int16 *
0x14000470b  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x140004710  jmp     short loc_140004717
0x140004712  mov     ebx, 80070216h
0x140004717  mov     rbp, [rsp+58h+arg_10]
0x14000471c  mov     eax, ebx
0x14000471e  mov     rbx, [rsp+58h+arg_0]
0x140004723  add     rsp, 40h
0x140004727  pop     r14
0x140004729  pop     rdi
0x14000472a  pop     rsi
0x14000472b  retn
```
