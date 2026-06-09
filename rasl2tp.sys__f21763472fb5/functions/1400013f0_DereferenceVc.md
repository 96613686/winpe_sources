# DereferenceVc

- ea: `0x1400013f0`
- end: `0x14000143a`
- name: `DereferenceVc`
- size: `74`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1400021c0`
- `0x14000f008`
- `0x14000f2ec`
- `0x14000f898`
- `0x1400109d0`
- `0x140010f90`
- `0x140011518`
- `0x140015190`
- `0x1400154b8`
- `0x140015bbc`
- `0x140017010`
- `0x140019940`
- `0x140019a80`
- `0x14001a640`
- `0x14001ae40`

## callees

- `0x1400013f0`
- `0x140001870`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000141f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000141f`

## pseudocode

```c
__int64 __fastcall DereferenceVc(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rbx

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    *(_DWORD *)(a1 + 16) = 810824268;
    v2 = *(_QWORD *)(a1 + 24);
    ExFreePoolWithTag((PVOID)(a1 - 16), 0);
    return DereferenceAdapter(v2);
  }
  return result;
}

```

## disassembly

```asm
0x1400013f0  sub     rsp, 28h
0x1400013f4  mov     eax, 0FFFFFFFFh
0x1400013f9  lock xadd [rcx+14h], eax
0x1400013fe  cmp     eax, 1
0x140001401  jz      short loc_140001409
0x140001403  add     rsp, 28h
0x140001407  retn
0x140001409  mov     dword ptr [rcx+10h], 3054324Ch
0x140001410  xor     edx, edx; Tag
0x140001412  mov     [rsp+28h+var_8], rbx
0x140001417  mov     rbx, [rcx+18h]
0x14000141b  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14000141f  call    cs:__imp_ExFreePoolWithTag
0x140001426  nop     dword ptr [rax+rax+00h]
0x14000142b  mov     rcx, rbx
0x14000142e  call    DereferenceAdapter
0x140001433  mov     rbx, [rsp+28h+var_8]
0x140001438  jmp     short loc_140001403
```
