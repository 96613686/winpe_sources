# HvStatspUnmap

- ea: `0x140010458`
- end: `0x1400104e2`
- name: `HvStatspUnmap`
- size: `138`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fee8`
- `0x14001006c`
- `0x140010320`

## callees

- `0x1400101d0`
- `0x140010458`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400104a0`
- `ntoskrnl!IoFreeMdl` at `0x1400104a0`
- `winhvr!WinHvUnmapStatsPage` at `0x1400104bd`
- `winhvr!WinHvUnmapStatsPage` at `0x1400104bd`

## pseudocode

```c
void __fastcall HvStatspUnmap(__int64 a1)
{
  __int64 v1; // rbx
  _QWORD *i; // rsi
  struct _MDL *v4; // rcx

  v1 = a1 + 40;
  HvStatspClientBufferUnshare(a1 + 40, 0, (PRKPROCESS *)(a1 + 40));
  for ( i = (_QWORD *)(v1 + 40); (_QWORD *)*i != i; HvStatspClientBufferUnshare(v1, 0, (PRKPROCESS *)(*i - 8LL)) )
    ;
  v4 = *(struct _MDL **)(v1 + 56);
  if ( v4 )
  {
    IoFreeMdl(v4);
    *(_QWORD *)(v1 + 56) = 0;
  }
  if ( *(_QWORD *)(a1 + 32) )
  {
    WinHvUnmapStatsPage();
    *(_QWORD *)(a1 + 32) = 0;
  }
}

```

## disassembly

```asm
0x140010458  mov     [rsp+arg_0], rbx
0x14001045d  mov     [rsp+arg_8], rsi
0x140010462  push    rdi
0x140010463  sub     rsp, 20h
0x140010467  lea     rbx, [rcx+28h]
0x14001046b  mov     rdi, rcx
0x14001046e  mov     r8, rbx
0x140010471  mov     rcx, rbx
0x140010474  xor     edx, edx
0x140010476  call    HvStatspClientBufferUnshare
0x14001047b  lea     rsi, [rbx+28h]
0x14001047f  mov     r8, [rsi]
0x140010482  cmp     r8, rsi
0x140010485  jz      short loc_140010497
0x140010487  add     r8, 0FFFFFFFFFFFFFFF8h
0x14001048b  xor     edx, edx
0x14001048d  mov     rcx, rbx
0x140010490  call    HvStatspClientBufferUnshare
0x140010495  jmp     short loc_14001047F
0x140010497  mov     rcx, [rbx+38h]; Mdl
0x14001049b  test    rcx, rcx
0x14001049e  jz      short loc_1400104B4
0x1400104a0  call    cs:__imp_IoFreeMdl
0x1400104a7  nop     dword ptr [rax+rax+00h]
0x1400104ac  mov     qword ptr [rbx+38h], 0
0x1400104b4  mov     rcx, [rdi+20h]
0x1400104b8  test    rcx, rcx
0x1400104bb  jz      short loc_1400104D1
0x1400104bd  call    cs:__imp_WinHvUnmapStatsPage
0x1400104c4  nop     dword ptr [rax+rax+00h]
0x1400104c9  mov     qword ptr [rdi+20h], 0
0x1400104d1  mov     rbx, [rsp+28h+arg_0]
0x1400104d6  mov     rsi, [rsp+28h+arg_8]
0x1400104db  add     rsp, 20h
0x1400104df  pop     rdi
0x1400104e0  retn
```
