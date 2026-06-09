# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x18000e7fc`
- end: `0x18000e919`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `285`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d91c`
- `0x18000dd44`
- `0x18000e2c4`

## callees

- `0x180004048`
- `0x18000e540`
- `0x18000e7fc`
- `0x180012010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000e8ce`
- `msvcrt!memmove_s` at `0x18000e8ce`
- `msvcrt!memcpy_s` at `0x18000e8e0`
- `msvcrt!memcpy_s` at `0x18000e8e0`

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

  v3 = a3;
  if ( a3 )
  {
    if ( !a2 )
      goto LABEL_20;
    v9 = *(unsigned int *)(*a1 - 16);
    v10 = ((__int64)a2 - *a1) >> 1;
    if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1);
    v11 = (char *)*a1;
    if ( v10 > v9 )
      memcpy_s(v11, 2 * v3, a2, 2 * v3);
    else
      memmove_s(v11, 2 * v3, &v11[2 * v10], 2 * v3);
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
0x18000e7fc  push    rbx
0x18000e7fe  push    rbp
0x18000e7ff  push    rsi
0x18000e800  push    rdi
0x18000e801  push    r14
0x18000e803  push    r15
0x18000e805  sub     rsp, 28h
0x18000e809  movsxd  rdi, r8d
0x18000e80c  mov     r14, rdx
0x18000e80f  mov     rbx, rcx
0x18000e812  test    r8d, r8d
0x18000e815  jnz     short loc_18000E884
0x18000e817  mov     rax, [rcx]
0x18000e81a  lea     rdx, [rax-18h]
0x18000e81e  cmp     [rdx+8], r8d
0x18000e822  jz      short loc_18000E877
0x18000e824  cmp     [rdx+10h], r8d
0x18000e828  jge     short loc_18000E842
0x18000e82a  cmp     [rax-0Ch], r8d
0x18000e82e  jl      loc_18000E903
0x18000e834  mov     [rax-10h], r8d
0x18000e838  mov     rcx, [rcx]
0x18000e83b  xor     eax, eax
0x18000e83d  mov     [rcx], ax
0x18000e840  jmp     short loc_18000E877
0x18000e842  mov     rdi, [rdx]
0x18000e845  or      eax, 0FFFFFFFFh
0x18000e848  lock xadd [rdx+10h], eax
0x18000e84d  sub     eax, 1
0x18000e850  jg      short loc_18000E861
0x18000e852  mov     rcx, [rdx]
0x18000e855  mov     rax, [rcx]
0x18000e858  mov     rax, [rax+8]
0x18000e85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e861  mov     rax, [rdi]
0x18000e864  mov     rcx, rdi
0x18000e867  mov     rax, [rax+18h]
0x18000e86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e870  add     rax, 18h
0x18000e874  mov     [rbx], rax
0x18000e877  add     rsp, 28h
0x18000e87b  pop     r15
0x18000e87d  pop     r14
0x18000e87f  pop     rdi
0x18000e880  pop     rsi
0x18000e881  pop     rbp
0x18000e882  pop     rbx
0x18000e883  retn
0x18000e884  test    r14, r14
0x18000e887  jz      loc_18000E90E
0x18000e88d  mov     rax, [rcx]
0x18000e890  mov     r15d, [rax-10h]
0x18000e894  mov     rbp, r14
0x18000e897  sub     rbp, rax
0x18000e89a  sar     rbp, 1
0x18000e89d  mov     ecx, 1
0x18000e8a2  sub     ecx, [rax-8]
0x18000e8a5  mov     eax, [rax-0Ch]
0x18000e8a8  sub     eax, edi
0x18000e8aa  or      ecx, eax
0x18000e8ac  jge     short loc_18000E8B8
0x18000e8ae  mov     edx, edi
0x18000e8b0  mov     rcx, rbx
0x18000e8b3  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000e8b8  mov     rcx, [rbx]; Destination
0x18000e8bb  lea     rsi, [rdi+rdi]
0x18000e8bf  cmp     rbp, r15
0x18000e8c2  ja      short loc_18000E8D7
0x18000e8c4  lea     r8, [rcx+rbp*2]; Source
0x18000e8c8  mov     r9, rsi; SourceSize
0x18000e8cb  mov     rdx, rsi; DestinationSize
0x18000e8ce  call    cs:__imp_memmove_s
0x18000e8d4  nop
0x18000e8d5  jmp     short loc_18000E8E6
0x18000e8d7  mov     r9, rsi; SourceSize
0x18000e8da  mov     r8, r14; Source
0x18000e8dd  mov     rdx, rsi; DestinationSize
0x18000e8e0  call    cs:__imp_memcpy_s
0x18000e8e6  test    edi, edi
0x18000e8e8  js      short loc_18000E90E
0x18000e8ea  mov     rax, [rbx]
0x18000e8ed  cmp     edi, [rax-0Ch]
0x18000e8f0  jg      short loc_18000E90E
0x18000e8f2  mov     [rax-10h], edi
0x18000e8f5  mov     rcx, [rbx]
0x18000e8f8  xor     eax, eax
0x18000e8fa  mov     [rsi+rcx], ax
0x18000e8fe  jmp     loc_18000E877
0x18000e903  mov     ecx, 80070057h; int
0x18000e908  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e90e  mov     ecx, 80070057h; int
0x18000e913  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
