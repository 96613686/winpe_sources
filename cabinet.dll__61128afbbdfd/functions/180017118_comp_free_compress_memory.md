# comp_free_compress_memory

- ea: `0x180017118`
- end: `0x180017273`
- name: `comp_free_compress_memory`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016db8`
- `0x180016eac`

## callees

- `0x180017118`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall comp_free_compress_memory(__int64 a1)
{
  __int64 (**v2)(void); // rdi
  __int64 result; // rax
  __int64 (**v4)(void); // rsi
  __int64 (**v5)(void); // rdi

  v2 = (__int64 (**)(void))(a1 + 17320);
  if ( *(_QWORD *)(a1 + 16) )
  {
    result = (*v2)();
    *(_QWORD *)(a1 + 16) = 0;
  }
  if ( *(_QWORD *)(a1 + 17280) )
  {
    result = (*v2)();
    *(_QWORD *)(a1 + 17280) = 0;
  }
  if ( *(_QWORD *)(a1 + 17288) )
  {
    result = (*v2)();
    *(_QWORD *)(a1 + 17288) = 0;
  }
  v4 = (__int64 (**)(void))(a1 + 17320);
  if ( *(_QWORD *)(a1 + 17272) )
  {
    result = (*v2)();
    *(_QWORD *)(a1 + 17272) = 0;
    *(_QWORD *)a1 = 0;
  }
  else
  {
    v4 = (__int64 (**)(void))(a1 + 17320);
  }
  if ( *(_QWORD *)(a1 + 72) )
  {
    result = (*v4)();
    *(_QWORD *)(a1 + 72) = 0;
  }
  if ( *(_QWORD *)(a1 + 64) )
  {
    result = (*v4)();
    *(_QWORD *)(a1 + 64) = 0;
    v5 = (__int64 (**)(void))(a1 + 17320);
  }
  else
  {
    v5 = v4;
  }
  if ( *(_QWORD *)(a1 + 80) )
  {
    result = (*v4)();
    *(_QWORD *)(a1 + 80) = 0;
  }
  else
  {
    v5 = v4;
  }
  if ( *(_QWORD *)(a1 + 9600) )
  {
    result = (*v5)();
    *(_QWORD *)(a1 + 9600) = 0;
  }
  if ( *(_QWORD *)(a1 + 2176) )
  {
    result = (*v5)();
    *(_QWORD *)(a1 + 2176) = 0;
  }
  *(_DWORD *)(a1 + 2220) = 0;
  return result;
}

```

## disassembly

```asm
0x180017118  mov     [rsp+arg_0], rbx
0x18001711d  mov     [rsp+arg_8], rsi
0x180017122  push    rdi
0x180017123  sub     rsp, 20h
0x180017127  mov     rbx, rcx
0x18001712a  mov     rcx, [rcx+10h]
0x18001712e  lea     rdi, [rbx+43A8h]
0x180017135  test    rcx, rcx
0x180017138  jz      short loc_18001714A
0x18001713a  mov     rax, [rdi]
0x18001713d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017142  mov     qword ptr [rbx+10h], 0
0x18001714a  mov     rcx, [rbx+4380h]
0x180017151  test    rcx, rcx
0x180017154  jz      short loc_180017169
0x180017156  mov     rax, [rdi]
0x180017159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001715e  mov     qword ptr [rbx+4380h], 0
0x180017169  mov     rcx, [rbx+4388h]
0x180017170  test    rcx, rcx
0x180017173  jz      short loc_180017191
0x180017175  mov     rax, [rdi]
0x180017178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001717d  mov     qword ptr [rbx+4388h], 0
0x180017188  lea     rsi, [rbx+43A8h]
0x18001718f  jmp     short loc_180017194
0x180017191  mov     rsi, rdi
0x180017194  mov     rcx, [rbx+4378h]
0x18001719b  test    rcx, rcx
0x18001719e  jz      short loc_1800171BC
0x1800171a0  mov     rax, [rdi]
0x1800171a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171a8  mov     qword ptr [rbx+4378h], 0
0x1800171b3  mov     qword ptr [rbx], 0
0x1800171ba  jmp     short loc_1800171BF
0x1800171bc  mov     rsi, rdi
0x1800171bf  mov     rcx, [rbx+48h]
0x1800171c3  test    rcx, rcx
0x1800171c6  jz      short loc_1800171D8
0x1800171c8  mov     rax, [rsi]
0x1800171cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171d0  mov     qword ptr [rbx+48h], 0
0x1800171d8  mov     rcx, [rbx+40h]
0x1800171dc  test    rcx, rcx
0x1800171df  jz      short loc_1800171FA
0x1800171e1  mov     rax, [rsi]
0x1800171e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e9  mov     qword ptr [rbx+40h], 0
0x1800171f1  lea     rdi, [rbx+43A8h]
0x1800171f8  jmp     short loc_1800171FD
0x1800171fa  mov     rdi, rsi
0x1800171fd  mov     rcx, [rbx+50h]
0x180017201  test    rcx, rcx
0x180017204  jz      short loc_180017218
0x180017206  mov     rax, [rsi]
0x180017209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001720e  mov     qword ptr [rbx+50h], 0
0x180017216  jmp     short loc_18001721B
0x180017218  mov     rdi, rsi
0x18001721b  mov     rcx, [rbx+2580h]
0x180017222  test    rcx, rcx
0x180017225  jz      short loc_18001723A
0x180017227  mov     rax, [rdi]
0x18001722a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001722f  mov     qword ptr [rbx+2580h], 0
0x18001723a  mov     rcx, [rbx+880h]
0x180017241  test    rcx, rcx
0x180017244  jz      short loc_180017259
0x180017246  mov     rax, [rdi]
0x180017249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001724e  mov     qword ptr [rbx+880h], 0
0x180017259  mov     rsi, [rsp+28h+arg_8]
0x18001725e  mov     dword ptr [rbx+8ACh], 0
0x180017268  mov     rbx, [rsp+28h+arg_0]
0x18001726d  add     rsp, 20h
0x180017271  pop     rdi
0x180017272  retn
```
