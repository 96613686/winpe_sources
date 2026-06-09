# ReadAllocCmapFormat4

- ea: `0x18000e4c8`
- end: `0x18000e611`
- name: `ReadAllocCmapFormat4`
- size: `329`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ec50`
- `0x1800143f0`

## callees

- `0x18000db8c`
- `0x18000dda0`
- `0x18000e4c8`
- `0x18000e618`
- `0x18000e754`
- `0x18000f198`
- `0x18001a3bc`

## pseudocode

```c
__int64 __fastcall ReadAllocCmapFormat4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _QWORD *a7,
        _WORD *a8)
{
  unsigned int CmapSubtable; // eax
  unsigned int v10; // r14d
  __int64 result; // rax
  unsigned int v12; // r14d
  unsigned __int16 v13; // r15
  unsigned __int16 AllocCmapFormat4Ids; // di
  __int64 v15; // r8
  _WORD v16[2]; // [rsp+40h] [rbp-18h] BYREF
  int v17; // [rsp+44h] [rbp-14h] BYREF
  int v18; // [rsp+48h] [rbp-10h] BYREF
  __int16 v19; // [rsp+4Ch] [rbp-Ch]

  v19 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  v16[0] = 0;
  v17 = 0;
  v18 = 0;
  CmapSubtable = FindCmapSubtable();
  v10 = CmapSubtable;
  if ( !CmapSubtable )
    return 1006;
  result = ReadCmapLength(a1, &v18, CmapSubtable, v16);
  if ( (_WORD)result )
    return result;
  if ( (_WORD)v18 != 4 )
    return 1006;
  result = ReadGeneric(a1, a5, 0xEu, (unsigned __int8 *)&CMAP_FORMAT4_CONTROL, v10, v16);
  if ( !(_WORD)result )
  {
    v12 = v16[0] + v10;
    v13 = *(_WORD *)(a5 + 6) >> 1;
    result = ReadAllocCmapFormat4Segs(a1, v13, (_DWORD)a6, v12, (__int64)&v17);
    if ( !(_WORD)result )
    {
      if ( v17
        && (AllocCmapFormat4Ids = ReadAllocCmapFormat4Ids(
                                    a1,
                                    v13,
                                    *a6,
                                    (_DWORD)a7,
                                    (__int64)a8,
                                    v12 + v17,
                                    (__int64)&v17)) != 0 )
      {
        FreeCmapFormat4(*a6, *a7, v15);
        result = AllocCmapFormat4Ids;
        *a6 = 0;
        *a7 = 0;
        *a8 = 0;
      }
      else
      {
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e4c8  push    rbp
0x18000e4ca  push    rbx
0x18000e4cb  push    rsi
0x18000e4cc  push    rdi
0x18000e4cd  push    r12
0x18000e4cf  push    r13
0x18000e4d1  push    r14
0x18000e4d3  push    r15
0x18000e4d5  mov     rbp, rsp
0x18000e4d8  sub     rsp, 58h
0x18000e4dc  mov     rbx, [rbp+arg_28]
0x18000e4e0  xor     r13d, r13d
0x18000e4e3  mov     rsi, [rbp+arg_30]
0x18000e4e7  xor     eax, eax
0x18000e4e9  mov     r12, [rbp+arg_38]
0x18000e4f0  mov     rdi, rcx
0x18000e4f3  mov     dword ptr [rbp+var_E], eax
0x18000e4f6  mov     [rbx], r13
0x18000e4f9  mov     [rsi], r13
0x18000e4fc  mov     [r12], r13w
0x18000e501  mov     [rbp+var_18], r13w
0x18000e506  mov     [rbp+var_14], r13d
0x18000e50a  mov     [rbp-10h], eax
0x18000e50d  call    FindCmapSubtable
0x18000e512  mov     r14d, eax
0x18000e515  test    eax, eax
0x18000e517  jz      loc_18000E5FB
0x18000e51d  lea     r9, [rbp+var_18]
0x18000e521  mov     r8d, eax
0x18000e524  lea     rdx, [rbp+var_10]
0x18000e528  mov     rcx, rdi
0x18000e52b  call    ReadCmapLength
0x18000e530  test    ax, ax
0x18000e533  jnz     loc_18000E600
0x18000e539  cmp     [rbp+var_10], 4
0x18000e53e  jnz     loc_18000E5FB
0x18000e544  mov     r15, [rbp+arg_20]
0x18000e548  lea     rax, [rbp+var_18]
0x18000e54c  mov     [rsp+58h+var_30], rax
0x18000e551  lea     r8d, [r13+0Eh]
0x18000e555  mov     rdx, r15
0x18000e558  mov     dword ptr [rsp+58h+var_38], r14d
0x18000e55d  lea     r9, CMAP_FORMAT4_CONTROL
0x18000e564  mov     rcx, rdi
0x18000e567  call    ReadGeneric
0x18000e56c  test    ax, ax
0x18000e56f  jnz     loc_18000E600
0x18000e575  movzx   r15d, word ptr [r15+6]
0x18000e57a  mov     r8, rbx
0x18000e57d  movzx   eax, [rbp+var_18]
0x18000e581  mov     rcx, rdi
0x18000e584  add     r14d, eax
0x18000e587  shr     r15w, 1
0x18000e58b  lea     rax, [rbp+var_14]
0x18000e58f  mov     r9d, r14d
0x18000e592  movzx   edx, r15w
0x18000e596  mov     [rsp+58h+var_38], rax
0x18000e59b  call    ReadAllocCmapFormat4Segs
0x18000e5a0  test    ax, ax
0x18000e5a3  jnz     short loc_18000E600
0x18000e5a5  mov     eax, [rbp+var_14]
0x18000e5a8  test    eax, eax
0x18000e5aa  jz      short loc_18000E5F6
0x18000e5ac  mov     r8, [rbx]
0x18000e5af  lea     rcx, [rbp+var_14]
0x18000e5b3  mov     [rsp+58h+var_28], rcx
0x18000e5b8  add     eax, r14d
0x18000e5bb  mov     dword ptr [rsp+58h+var_30], eax
0x18000e5bf  mov     rcx, rdi
0x18000e5c2  mov     r9, rsi
0x18000e5c5  mov     [rsp+58h+var_38], r12
0x18000e5ca  movzx   edx, r15w
0x18000e5ce  call    ReadAllocCmapFormat4Ids
0x18000e5d3  movzx   edi, ax
0x18000e5d6  test    ax, ax
0x18000e5d9  jz      short loc_18000E5F6
0x18000e5db  mov     rdx, [rsi]
0x18000e5de  mov     rcx, [rbx]
0x18000e5e1  call    FreeCmapFormat4
0x18000e5e6  movzx   eax, di
0x18000e5e9  mov     [rbx], r13
0x18000e5ec  mov     [rsi], r13
0x18000e5ef  mov     [r12], r13w
0x18000e5f4  jmp     short loc_18000E600
0x18000e5f6  mov     eax, r13d
0x18000e5f9  jmp     short loc_18000E600
0x18000e5fb  mov     eax, 3EEh
0x18000e600  add     rsp, 58h
0x18000e604  pop     r15
0x18000e606  pop     r14
0x18000e608  pop     r13
0x18000e60a  pop     r12
0x18000e60c  pop     rdi
0x18000e60d  pop     rsi
0x18000e60e  pop     rbx
0x18000e60f  pop     rbp
0x18000e610  retn
```
