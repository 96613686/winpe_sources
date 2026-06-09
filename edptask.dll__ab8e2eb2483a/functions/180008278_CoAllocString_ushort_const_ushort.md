# CoAllocString(ushort const *,ushort * *)

- ea: `0x180008278`
- end: `0x180008308`
- name: `?CoAllocString@@YAJPEBGPEAPEAG@Z`
- size: `144`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `10`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009f20`
- `0x18000a0b0`
- `0x18000a140`
- `0x18000a1d0`
- `0x18000a260`
- `0x18000a2f0`
- `0x18000a380`
- `0x18000a410`
- `0x18000a4a0`
- `0x18000a530`

## callees

- `0x180008278`
- `0x1800112a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800082bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800082bd`

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
0x180008278  mov     [rsp+arg_0], rbx
0x18000827d  mov     [rsp+arg_10], rbp
0x180008282  push    rsi
0x180008283  push    rdi
0x180008284  push    r14
0x180008286  sub     rsp, 40h
0x18000828a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000828e  mov     rbx, rdx
0x180008291  xor     r14d, r14d
0x180008294  mov     rbp, rcx
0x180008297  inc     rdi
0x18000829a  cmp     [rcx+rdi*2], r14w
0x18000829f  jnz     short loc_180008297
0x1800082a1  lea     rsi, [rdi+1]
0x1800082a5  mov     [rdx], r14
0x1800082a8  cmp     rsi, rdi
0x1800082ab  jb      short loc_1800082EE
0x1800082ad  mov     eax, 2
0x1800082b2  mul     rsi
0x1800082b5  test    rdx, rdx
0x1800082b8  jnz     short loc_1800082EE
0x1800082ba  mov     rcx, rax; cb
0x1800082bd  call    cs:__imp_CoTaskMemAlloc
0x1800082c3  mov     [rbx], rax
0x1800082c6  mov     rcx, rax
0x1800082c9  neg     rcx
0x1800082cc  sbb     ebx, ebx
0x1800082ce  not     ebx
0x1800082d0  and     ebx, 8007000Eh
0x1800082d6  test    rax, rax
0x1800082d9  jz      short loc_1800082F3
0x1800082db  mov     r9, rdi; unsigned __int64
0x1800082de  mov     r8, rbp; unsigned __int16 *
0x1800082e1  mov     rdx, rsi; unsigned __int64
0x1800082e4  mov     rcx, rax; unsigned __int16 *
0x1800082e7  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800082ec  jmp     short loc_1800082F3
0x1800082ee  mov     ebx, 80070216h
0x1800082f3  mov     rbp, [rsp+58h+arg_10]
0x1800082f8  mov     eax, ebx
0x1800082fa  mov     rbx, [rsp+58h+arg_0]
0x1800082ff  add     rsp, 40h
0x180008303  pop     r14
0x180008305  pop     rdi
0x180008306  pop     rsi
0x180008307  retn
```
