# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ushort const *)

- ea: `0x18000ce9c`
- end: `0x18000cfdc`
- name: `??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d2f0`
- `0x180012144`

## callees

- `0x1800068ec`
- `0x18000ce9c`
- `0x1800104a8`
- `0x180015010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000cf1a`
- `msvcrt!memmove_s` at `0x18000cf1a`
- `msvcrt!memcpy_s` at `0x18000cf2b`
- `msvcrt!memcpy_s` at `0x18000cf2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int **__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        int **a1,
        char *a2)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // rbp
  char *v7; // rcx
  rsize_t v8; // r9
  int *v9; // rax
  volatile signed __int32 *v10; // rdx
  __int64 v11; // rbx

  if ( !a2 )
    goto LABEL_13;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&a2[2 * v4] );
  if ( (_DWORD)v4 )
  {
    v5 = (unsigned int)*(*a1 - 4);
    v6 = (a2 - (char *)*a1) >> 1;
    if ( (int)((*(*a1 - 3) - v4) | (1 - *(*a1 - 2))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v4);
    v7 = (char *)*a1;
    v8 = 2LL * (int)v4;
    if ( v6 > v5 )
      memcpy_s(v7, v8, a2, v8);
    else
      memmove_s(v7, v8, &v7[2 * v6], v8);
    if ( (int)v4 < 0 || (int)v4 > *(*a1 - 3) )
      ATL::AtlThrowImpl(-2147024809);
    *(*a1 - 4) = v4;
    *((_WORD *)*a1 + (int)v4) = 0;
  }
  else
  {
LABEL_13:
    v9 = *a1;
    v10 = *a1 - 6;
    if ( *((_DWORD *)v10 + 2) )
    {
      if ( *((int *)v10 + 4) >= 0 )
      {
        v11 = *(_QWORD *)v10;
        if ( _InterlockedDecrement(v10 + 4) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
        *a1 = (int *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11) + 24);
      }
      else
      {
        if ( *(v9 - 3) < 0 )
          ATL::AtlThrowImpl(-2147024809);
        *(v9 - 4) = 0;
        *(_WORD *)*a1 = 0;
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000ce9c  push    rbx
0x18000ce9e  push    rbp
0x18000ce9f  push    rsi
0x18000cea0  push    rdi
0x18000cea1  push    r12
0x18000cea3  push    r14
0x18000cea5  push    r15
0x18000cea7  sub     rsp, 20h
0x18000ceab  mov     r14, rdx
0x18000ceae  mov     rdi, rcx
0x18000ceb1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ceb5  xor     r12d, r12d
0x18000ceb8  test    rdx, rdx
0x18000cebb  jz      loc_18000CF58
0x18000cec1  mov     rbx, rcx
0x18000cec4  inc     rbx
0x18000cec7  cmp     [rdx+rbx*2], r12w
0x18000cecc  jnz     short loc_18000CEC4
0x18000cece  test    ebx, ebx
0x18000ced0  jz      loc_18000CF58
0x18000ced6  mov     rax, [rdi]
0x18000ced9  mov     r15d, [rax-10h]
0x18000cedd  mov     rbp, r14
0x18000cee0  sub     rbp, rax
0x18000cee3  sar     rbp, 1
0x18000cee6  mov     ecx, 1
0x18000ceeb  sub     ecx, [rax-8]
0x18000ceee  mov     eax, [rax-0Ch]
0x18000cef1  sub     eax, ebx
0x18000cef3  or      ecx, eax
0x18000cef5  jge     short loc_18000CF01
0x18000cef7  mov     edx, ebx
0x18000cef9  mov     rcx, rdi
0x18000cefc  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000cf01  mov     rcx, [rdi]; Destination
0x18000cf04  movsxd  rax, ebx
0x18000cf07  lea     rsi, [rax+rax]
0x18000cf0b  mov     r9, rsi; SourceSize
0x18000cf0e  mov     rdx, rsi; DestinationSize
0x18000cf11  cmp     rbp, r15
0x18000cf14  ja      short loc_18000CF28
0x18000cf16  lea     r8, [rcx+rbp*2]; Source
0x18000cf1a  call    cs:__imp_memmove_s
0x18000cf21  nop     dword ptr [rax+rax+00h]
0x18000cf26  jmp     short loc_18000CF37
0x18000cf28  mov     r8, r14; Source
0x18000cf2b  call    cs:__imp_memcpy_s
0x18000cf32  nop     dword ptr [rax+rax+00h]
0x18000cf37  test    ebx, ebx
0x18000cf39  js      loc_18000CFD1
0x18000cf3f  mov     rax, [rdi]
0x18000cf42  cmp     ebx, [rax-0Ch]
0x18000cf45  jg      loc_18000CFD1
0x18000cf4b  mov     [rax-10h], ebx
0x18000cf4e  mov     rcx, [rdi]
0x18000cf51  mov     [rsi+rcx], r12w
0x18000cf56  jmp     short loc_18000CFB3
0x18000cf58  mov     rax, [rdi]
0x18000cf5b  lea     rdx, [rax-18h]
0x18000cf5f  cmp     [rdx+8], r12d
0x18000cf63  jz      short loc_18000CFB3
0x18000cf65  cmp     [rdx+10h], r12d
0x18000cf69  jge     short loc_18000CF7E
0x18000cf6b  cmp     [rax-0Ch], r12d
0x18000cf6f  jl      short loc_18000CFC6
0x18000cf71  mov     [rax-10h], r12d
0x18000cf75  mov     rcx, [rdi]
0x18000cf78  mov     [rcx], r12w
0x18000cf7c  jmp     short loc_18000CFB3
0x18000cf7e  mov     rbx, [rdx]
0x18000cf81  mov     eax, ecx
0x18000cf83  lock xadd [rdx+10h], eax
0x18000cf88  add     eax, ecx
0x18000cf8a  test    eax, eax
0x18000cf8c  jg      short loc_18000CF9D
0x18000cf8e  mov     rcx, [rdx]
0x18000cf91  mov     rax, [rcx]
0x18000cf94  mov     rax, [rax+8]
0x18000cf98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf9d  mov     rax, [rbx]
0x18000cfa0  mov     rcx, rbx
0x18000cfa3  mov     rax, [rax+18h]
0x18000cfa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfac  add     rax, 18h
0x18000cfb0  mov     [rdi], rax
0x18000cfb3  mov     rax, rdi
0x18000cfb6  add     rsp, 20h
0x18000cfba  pop     r15
0x18000cfbc  pop     r14
0x18000cfbe  pop     r12
0x18000cfc0  pop     rdi
0x18000cfc1  pop     rsi
0x18000cfc2  pop     rbp
0x18000cfc3  pop     rbx
0x18000cfc4  retn
0x18000cfc6  mov     ecx, 80070057h; int
0x18000cfcb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000cfd1  mov     ecx, 80070057h; int
0x18000cfd6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
