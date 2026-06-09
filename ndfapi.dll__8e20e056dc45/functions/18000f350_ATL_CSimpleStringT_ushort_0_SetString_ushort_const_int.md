# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x18000f350`
- end: `0x18000f45f`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `271`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bae8`
- `0x18000cb28`
- `0x18000cbcc`
- `0x18000dd58`
- `0x18000f300`
- `0x180014e68`
- `0x1800150a0`
- `0x18001d790`
- `0x18001de8c`

## callees

- `0x180005688`
- `0x18000ebb4`
- `0x18000f350`
- `0x180021010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000f41e`
- `msvcrt!memmove_s` at `0x18000f41e`
- `msvcrt!memcpy_s` at `0x18000f429`
- `msvcrt!memcpy_s` at `0x18000f429`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  volatile signed __int32 *v7; // rdx
  __int64 v8; // rdi
  unsigned __int64 v9; // r15
  unsigned __int64 v10; // rbp
  char *v11; // rcx
  rsize_t v12; // r9
  rsize_t v13; // rdx

  v3 = a3;
  if ( a3 )
  {
    if ( !a2 )
      goto LABEL_20;
    v9 = *(unsigned int *)(*a1 - 16);
    v10 = ((__int64)a2 - *a1) >> 1;
    if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
    v11 = (char *)*a1;
    v12 = 2 * v3;
    v13 = 2 * v3;
    if ( v10 > v9 )
      memcpy_s(v11, v13, a2, v12);
    else
      memmove_s(v11, v13, &v11[2 * v10], v12);
    if ( (int)v3 < 0 || (int)v3 > *(_DWORD *)(*a1 - 12) )
LABEL_20:
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a1 - 16) = v3;
    result = 0;
    *(_WORD *)(2 * v3 + *a1) = 0;
  }
  else
  {
    result = *a1;
    v7 = (volatile signed __int32 *)(*a1 - 24);
    if ( *((_DWORD *)v7 + 2) )
    {
      if ( *((int *)v7 + 4) >= 0 )
      {
        v8 = *(_QWORD *)v7;
        if ( _InterlockedExchangeAdd(v7 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
        result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8) + 24;
        *a1 = result;
      }
      else
      {
        if ( *(int *)(result - 12) < 0 )
          ATL::AtlThrowImpl(-2147024809);
        *(_DWORD *)(result - 16) = 0;
        result = 0;
        *(_WORD *)*a1 = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f350  push    rbx
0x18000f352  push    rbp
0x18000f353  push    rsi
0x18000f354  push    rdi
0x18000f355  push    r14
0x18000f357  push    r15
0x18000f359  sub     rsp, 28h
0x18000f35d  movsxd  rdi, r8d
0x18000f360  mov     r14, rdx
0x18000f363  mov     rbx, rcx
0x18000f366  test    r8d, r8d
0x18000f369  jnz     short loc_18000F3D8
0x18000f36b  mov     rax, [rcx]
0x18000f36e  lea     rdx, [rax-18h]
0x18000f372  cmp     [rdx+8], r8d
0x18000f376  jz      short loc_18000F3CB
0x18000f378  cmp     [rdx+10h], r8d
0x18000f37c  jge     short loc_18000F396
0x18000f37e  cmp     [rax-0Ch], r8d
0x18000f382  jl      loc_18000F449
0x18000f388  mov     [rax-10h], r8d
0x18000f38c  mov     rcx, [rcx]
0x18000f38f  xor     eax, eax
0x18000f391  mov     [rcx], ax
0x18000f394  jmp     short loc_18000F3CB
0x18000f396  mov     rdi, [rdx]
0x18000f399  or      eax, 0FFFFFFFFh
0x18000f39c  lock xadd [rdx+10h], eax
0x18000f3a1  sub     eax, 1
0x18000f3a4  jg      short loc_18000F3B5
0x18000f3a6  mov     rcx, [rdx]
0x18000f3a9  mov     rax, [rcx]
0x18000f3ac  mov     rax, [rax+8]
0x18000f3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3b5  mov     rax, [rdi]
0x18000f3b8  mov     rcx, rdi
0x18000f3bb  mov     rax, [rax+18h]
0x18000f3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3c4  add     rax, 18h
0x18000f3c8  mov     [rbx], rax
0x18000f3cb  add     rsp, 28h
0x18000f3cf  pop     r15
0x18000f3d1  pop     r14
0x18000f3d3  pop     rdi
0x18000f3d4  pop     rsi
0x18000f3d5  pop     rbp
0x18000f3d6  pop     rbx
0x18000f3d7  retn
0x18000f3d8  test    r14, r14
0x18000f3db  jz      short loc_18000F454
0x18000f3dd  mov     rax, [rcx]
0x18000f3e0  mov     r15d, [rax-10h]
0x18000f3e4  mov     rbp, r14
0x18000f3e7  sub     rbp, rax
0x18000f3ea  sar     rbp, 1
0x18000f3ed  mov     ecx, 1
0x18000f3f2  sub     ecx, [rax-8]
0x18000f3f5  mov     eax, [rax-0Ch]
0x18000f3f8  sub     eax, edi
0x18000f3fa  or      ecx, eax
0x18000f3fc  jge     short loc_18000F408
0x18000f3fe  mov     edx, edi
0x18000f400  mov     rcx, rbx
0x18000f403  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000f408  mov     rcx, [rbx]; Destination
0x18000f40b  lea     rsi, [rdi+rdi]
0x18000f40f  mov     r9, rsi; SourceSize
0x18000f412  mov     rdx, rsi; DestinationSize
0x18000f415  cmp     rbp, r15
0x18000f418  ja      short loc_18000F426
0x18000f41a  lea     r8, [rcx+rbp*2]; Source
0x18000f41e  call    cs:__imp_memmove_s
0x18000f424  jmp     short loc_18000F42F
0x18000f426  mov     r8, r14; Source
0x18000f429  call    cs:__imp_memcpy_s
0x18000f42f  test    edi, edi
0x18000f431  js      short loc_18000F454
0x18000f433  mov     rax, [rbx]
0x18000f436  cmp     edi, [rax-0Ch]
0x18000f439  jg      short loc_18000F454
0x18000f43b  mov     [rax-10h], edi
0x18000f43e  mov     rcx, [rbx]
0x18000f441  xor     eax, eax
0x18000f443  mov     [rsi+rcx], ax
0x18000f447  jmp     short loc_18000F3CB
0x18000f449  mov     ecx, 80070057h; int
0x18000f44e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f454  mov     ecx, 80070057h; int
0x18000f459  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
