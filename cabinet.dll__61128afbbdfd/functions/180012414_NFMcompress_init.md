# NFMcompress_init

- ea: `0x180012414`
- end: `0x180012541`
- name: `NFMcompress_init`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800122c0`
- `0x1800142a8`

## callees

- `0x180012414`
- `0x180012548`
- `0x180012630`
- `0x18001562a`

## pseudocode

```c
__int64 __fastcall NFMcompress_init(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 Memory; // rax
  __int64 v11; // rax
  __int64 v12; // rcx

  a1[1526] = NFMcompress_PickAllocRoutineAndAllocateMemory(a2, a4, a6, 0x8000);
  a1[1527] = NFMcompress_PickAllocRoutineAndAllocateMemory(a2, a4, a6, 0x8000);
  a1[1528] = NFMcompress_PickAllocRoutineAndAllocateMemory(a2, a4, a6, 0x10000);
  a1[1529] = NFMcompress_PickAllocRoutineAndAllocateMemory(a2, a4, a6, 0x10000);
  Memory = NFMcompress_PickAllocRoutineAndAllocateMemory(a2, a4, a6, 65826);
  a1[1530] = Memory;
  if ( a1[1526] && a1[1527] && a1[1528] && a1[1529] && Memory )
  {
    memset_0((void *)(Memory + 0x10000), 0, 0x122u);
    v11 = a1[1526];
    v12 = a1[1527];
    *a1 = v11;
    a1[2] = v12;
    if ( v11 )
      return (unsigned int)(v12 != 0) - 1;
  }
  else
  {
    NFMcompress_uninit(a1, a3, a5, a6);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180012414  push    rbx
0x180012416  push    rsi
0x180012417  push    rdi
0x180012418  push    r14
0x18001241a  sub     rsp, 28h
0x18001241e  mov     rdi, r9
0x180012421  mov     rbx, rdx
0x180012424  mov     r14, r8
0x180012427  mov     rsi, rcx
0x18001242a  mov     r8, [rsp+48h+arg_28]
0x18001242f  mov     rdx, rdi
0x180012432  mov     rcx, rbx
0x180012435  mov     r9d, 8000h
0x18001243b  call    NFMcompress_PickAllocRoutineAndAllocateMemory
0x180012440  mov     r8, [rsp+48h+arg_28]
0x180012445  mov     r9d, 8000h
0x18001244b  mov     rdx, rdi
0x18001244e  mov     [rsi+2FB0h], rax
0x180012455  mov     rcx, rbx
0x180012458  call    NFMcompress_PickAllocRoutineAndAllocateMemory
0x18001245d  mov     r8, [rsp+48h+arg_28]
0x180012462  mov     r9d, 10000h
0x180012468  mov     rdx, rdi
0x18001246b  mov     [rsi+2FB8h], rax
0x180012472  mov     rcx, rbx
0x180012475  call    NFMcompress_PickAllocRoutineAndAllocateMemory
0x18001247a  mov     r8, [rsp+48h+arg_28]
0x18001247f  mov     r9d, 10000h
0x180012485  mov     rdx, rdi
0x180012488  mov     [rsi+2FC0h], rax
0x18001248f  mov     rcx, rbx
0x180012492  call    NFMcompress_PickAllocRoutineAndAllocateMemory
0x180012497  mov     r8, [rsp+48h+arg_28]
0x18001249c  mov     r9d, 10122h
0x1800124a2  mov     rdx, rdi
0x1800124a5  mov     [rsi+2FC8h], rax
0x1800124ac  mov     rcx, rbx
0x1800124af  call    NFMcompress_PickAllocRoutineAndAllocateMemory
0x1800124b4  xor     ebx, ebx
0x1800124b6  mov     [rsi+2FD0h], rax
0x1800124bd  cmp     [rsi+2FB0h], rbx
0x1800124c4  jz      short loc_180012527
0x1800124c6  cmp     [rsi+2FB8h], rbx
0x1800124cd  jz      short loc_180012527
0x1800124cf  cmp     [rsi+2FC0h], rbx
0x1800124d6  jz      short loc_180012527
0x1800124d8  cmp     [rsi+2FC8h], rbx
0x1800124df  jz      short loc_180012527
0x1800124e1  test    rax, rax
0x1800124e4  jz      short loc_180012527
0x1800124e6  lea     rcx, [rax+10000h]; void *
0x1800124ed  xor     edx, edx; Val
0x1800124ef  mov     r8d, 122h; Size
0x1800124f5  call    memset_0
0x1800124fa  mov     rax, [rsi+2FB0h]
0x180012501  mov     rcx, [rsi+2FB8h]
0x180012508  mov     [rsi], rax
0x18001250b  mov     [rsi+10h], rcx
0x18001250f  test    rax, rax
0x180012512  jz      short loc_18001253C
0x180012514  neg     rcx
0x180012517  sbb     eax, eax
0x180012519  neg     eax
0x18001251b  dec     eax
0x18001251d  add     rsp, 28h
0x180012521  pop     r14
0x180012523  pop     rdi
0x180012524  pop     rsi
0x180012525  pop     rbx
0x180012526  retn
0x180012527  mov     r9, [rsp+48h+arg_28]
0x18001252c  mov     rdx, r14
0x18001252f  mov     r8, [rsp+48h+arg_20]
0x180012534  mov     rcx, rsi
0x180012537  call    NFMcompress_uninit
0x18001253c  or      eax, 0FFFFFFFFh
0x18001253f  jmp     short loc_18001251D
```
