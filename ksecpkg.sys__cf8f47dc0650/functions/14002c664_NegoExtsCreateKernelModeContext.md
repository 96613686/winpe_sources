# NegoExtsCreateKernelModeContext

- ea: `0x14002c664`
- end: `0x14002c739`
- name: `NegoExtsCreateKernelModeContext`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140022280`
- `0x140022510`

## callees

- `0x140007008`
- `0x14000e344`
- `0x140010240`
- `0x14002c664`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002c6c9`
- `ntoskrnl!ExAllocatePool2` at `0x14002c6c9`

## pseudocode

```c
__int64 __fastcall NegoExtsCreateKernelModeContext(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rsi
  __int64 v7; // rcx
  unsigned int v8; // ebx
  _QWORD *Pool2; // rdi
  __int64 v10; // rax

  if ( *(_DWORD *)a2 >= 0x14u )
  {
    v6 = *(_QWORD *)(a2 + 8);
    v7 = 64;
    if ( NegoExtsPoolType == 1 )
      v7 = 256;
    v8 = 0;
    Pool2 = (_QWORD *)ExAllocatePool2(v7, 40, 1952675918);
    if ( Pool2 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD))(NegoExtsKernelFunctions + 64))(*(unsigned int *)(v6 + 8));
      Pool2[3] = v10;
      if ( v10 )
      {
        *((_DWORD *)Pool2 + 4) = *(_DWORD *)(v6 + 8);
        *Pool2 = 0x4F47454E5458544BLL;
        Pool2[1] = a1;
        *a3 = Pool2;
      }
      else
      {
        NegoExtsFreeContext(Pool2);
        return (unsigned int)-1073741570;
      }
    }
    else
    {
      return (unsigned int)-1073741801;
    }
    return v8;
  }
  else
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Invalid buffer size for marshalled context: was %#x, needed %#x\n", *(_DWORD *)a2, 20);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14002c664  push    rbx
0x14002c666  push    rbp
0x14002c667  push    rsi
0x14002c668  push    rdi
0x14002c669  push    r14
0x14002c66b  sub     rsp, 20h
0x14002c66f  mov     r14, r8
0x14002c672  mov     r9d, 14h
0x14002c678  mov     r8d, [rdx]
0x14002c67b  mov     rbp, rcx
0x14002c67e  cmp     r8d, r9d
0x14002c681  jnb     short loc_14002C6A6
0x14002c683  xor     ebx, ebx
0x14002c685  cmp     cs:KsecInfoLevel, ebx
0x14002c68b  jz      short loc_14002C69C
0x14002c68d  lea     rdx, aInvalidBufferS; "Invalid buffer size for marshalled cont"...
0x14002c694  lea     ecx, [rbx+1]
0x14002c697  call    KsecDebugOut
0x14002c69c  mov     eax, 0C000000Dh
0x14002c6a1  jmp     loc_14002C72D
0x14002c6a6  cmp     cs:NegoExtsPoolType, 1
0x14002c6ad  mov     eax, 100h
0x14002c6b2  mov     rsi, [rdx+8]
0x14002c6b6  mov     ecx, 40h ; '@'
0x14002c6bb  cmovz   ecx, eax
0x14002c6be  mov     edx, 28h ; '('
0x14002c6c3  mov     r8d, 7463784Eh
0x14002c6c9  call    cs:__imp_ExAllocatePool2
0x14002c6d0  nop     dword ptr [rax+rax+00h]
0x14002c6d5  xor     ebx, ebx
0x14002c6d7  mov     rdi, rax
0x14002c6da  test    rax, rax
0x14002c6dd  jnz     short loc_14002C6E6
0x14002c6df  mov     ebx, 0C0000017h
0x14002c6e4  jmp     short loc_14002C72B
0x14002c6e6  mov     rax, cs:NegoExtsKernelFunctions
0x14002c6ed  mov     ecx, [rsi+8]
0x14002c6f0  mov     rax, [rax+40h]
0x14002c6f4  call    _guard_dispatch_icall
0x14002c6f9  mov     [rdi+18h], rax
0x14002c6fd  test    rax, rax
0x14002c700  jz      short loc_14002C71E
0x14002c702  mov     eax, [rsi+8]
0x14002c705  mov     [rdi+10h], eax
0x14002c708  mov     rax, 4F47454E5458544Bh
0x14002c712  mov     [rdi], rax
0x14002c715  mov     [rdi+8], rbp
0x14002c719  mov     [r14], rdi
0x14002c71c  jmp     short loc_14002C72B
0x14002c71e  mov     rcx, rdi; P
0x14002c721  call    NegoExtsFreeContext
0x14002c726  mov     ebx, 0C00000FEh
0x14002c72b  mov     eax, ebx
0x14002c72d  add     rsp, 20h
0x14002c731  pop     r14
0x14002c733  pop     rdi
0x14002c734  pop     rsi
0x14002c735  pop     rbp
0x14002c736  pop     rbx
0x14002c737  retn
```
