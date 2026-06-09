# CJob::GetComment(ushort * *)

- ea: `0x18000da50`
- end: `0x18000dac1`
- name: `?GetComment@CJob@@UEAAJPEAPEAG@Z`
- size: `113`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001840`
- `0x18000da50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da8b`

## pseudocode

```c
__int64 __fastcall CJob::GetComment(CJob *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax

  v2 = (const unsigned __int16 *)&wszEmpty;
  if ( *((_QWORD *)this + 18) )
    v2 = (const unsigned __int16 *)*((_QWORD *)this + 18);
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( v2[v5] );
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5 + 2);
  *a2 = v6;
  if ( !v6 )
    return 2147942414LL;
  do
    ++v4;
  while ( v2[v4] );
  return StringCchCopyW(v6, v4 + 1, v2);
}

```

## disassembly

```asm
0x18000da50  push    rbx
0x18000da52  push    rbp
0x18000da53  push    rsi
0x18000da54  push    rdi
0x18000da55  sub     rsp, 28h
0x18000da59  mov     rax, [rcx+90h]
0x18000da60  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x18000da67  xor     ebp, ebp
0x18000da69  mov     rsi, rdx
0x18000da6c  test    rax, rax
0x18000da6f  cmovnz  rdi, rax
0x18000da73  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000da77  mov     rcx, rbx
0x18000da7a  inc     rcx
0x18000da7d  cmp     [rdi+rcx*2], bp
0x18000da81  jnz     short loc_18000DA7A
0x18000da83  lea     rcx, ds:2[rcx*2]; cb
0x18000da8b  call    cs:__imp_CoTaskMemAlloc
0x18000da91  mov     [rsi], rax
0x18000da94  test    rax, rax
0x18000da97  jnz     short loc_18000DAA0
0x18000da99  mov     eax, 8007000Eh
0x18000da9e  jmp     short loc_18000DAB8
0x18000daa0  inc     rbx
0x18000daa3  cmp     [rdi+rbx*2], bp
0x18000daa7  jnz     short loc_18000DAA0
0x18000daa9  lea     rdx, [rbx+1]; unsigned __int64
0x18000daad  mov     r8, rdi; unsigned __int16 *
0x18000dab0  mov     rcx, rax; unsigned __int16 *
0x18000dab3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dab8  add     rsp, 28h
0x18000dabc  pop     rdi
0x18000dabd  pop     rsi
0x18000dabe  pop     rbp
0x18000dabf  pop     rbx
0x18000dac0  retn
```
