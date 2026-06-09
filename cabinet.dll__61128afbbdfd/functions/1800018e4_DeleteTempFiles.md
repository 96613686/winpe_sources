# DeleteTempFiles

- ea: `0x1800018e4`
- end: `0x1800019c7`
- name: `DeleteTempFiles`
- size: `227`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001008`
- `0x1800014b4`
- `0x180001bd8`
- `0x1800039b8`

## callees

- `0x1800018e4`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall DeleteTempFiles(
        __int64 a1,
        int a2,
        unsigned int (__fastcall *a3)(__int64, int *, __int64),
        unsigned int (__fastcall *a4)(__int64, int *, __int64),
        _DWORD *a5,
        __int64 a6)
{
  _DWORD *v6; // rbx
  unsigned int v7; // edi
  unsigned int i; // esi
  __int64 v13; // r14
  __int64 v14; // rcx
  __int64 v15; // r8
  int v17; // [rsp+78h] [rbp+10h] BYREF

  v6 = a5;
  v7 = 0;
  for ( i = 1; (int)v7 < a2; ++v7 )
  {
    v13 = 272LL * v7;
    v14 = *(_QWORD *)(v13 + a1 + 8);
    if ( v14 != -1 )
    {
      v17 = 0;
      if ( a3(v14, &v17, a6) )
      {
        i = 0;
        v6[1] = v17;
        *v6 = 4;
        v6[2] = 1;
      }
      v15 = a6;
      *(_QWORD *)(v13 + a1 + 8) = -1;
      v17 = 0;
      if ( a4(v13 + a1 + 16, &v17, v15) == -1 )
      {
        i = 0;
        v6[1] = v17;
        *v6 = 4;
        v6[2] = 1;
      }
    }
  }
  return i;
}

```

## disassembly

```asm
0x1800018e4  push    rbx
0x1800018e6  push    rbp
0x1800018e7  push    rsi
0x1800018e8  push    rdi
0x1800018e9  push    r12
0x1800018eb  push    r13
0x1800018ed  push    r14
0x1800018ef  push    r15
0x1800018f1  sub     rsp, 28h
0x1800018f5  mov     rbx, [rsp+68h+arg_20]
0x1800018fd  xor     edi, edi
0x1800018ff  mov     r13, r9
0x180001902  mov     r12, r8
0x180001905  mov     ebp, edx
0x180001907  mov     r15, rcx
0x18000190a  mov     esi, 1
0x18000190f  test    edx, edx
0x180001911  jle     loc_1800019B4
0x180001917  mov     eax, edi
0x180001919  imul    r14, rax, 110h
0x180001920  mov     rcx, [r14+r15+8]
0x180001925  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180001929  jz      short loc_1800019AA
0x18000192b  mov     r8, [rsp+68h+arg_28]
0x180001933  lea     rdx, [rsp+68h+arg_8]
0x180001938  mov     rax, r12
0x18000193b  mov     [rsp+68h+arg_8], 0
0x180001943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001948  test    eax, eax
0x18000194a  jz      short loc_180001962
0x18000194c  mov     eax, [rsp+68h+arg_8]
0x180001950  xor     esi, esi
0x180001952  mov     [rbx+4], eax
0x180001955  mov     dword ptr [rbx], 4
0x18000195b  mov     dword ptr [rbx+8], 1
0x180001962  mov     r8, [rsp+68h+arg_28]
0x18000196a  lea     rcx, [r15+10h]
0x18000196e  add     rcx, r14
0x180001971  mov     qword ptr [r14+r15+8], 0FFFFFFFFFFFFFFFFh
0x18000197a  lea     rdx, [rsp+68h+arg_8]
0x18000197f  mov     [rsp+68h+arg_8], 0
0x180001987  mov     rax, r13
0x18000198a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000198f  cmp     eax, 0FFFFFFFFh
0x180001992  jnz     short loc_1800019AA
0x180001994  mov     eax, [rsp+68h+arg_8]
0x180001998  xor     esi, esi
0x18000199a  mov     [rbx+4], eax
0x18000199d  mov     dword ptr [rbx], 4
0x1800019a3  mov     dword ptr [rbx+8], 1
0x1800019aa  inc     edi
0x1800019ac  cmp     edi, ebp
0x1800019ae  jl      loc_180001917
0x1800019b4  mov     eax, esi
0x1800019b6  add     rsp, 28h
0x1800019ba  pop     r15
0x1800019bc  pop     r14
0x1800019be  pop     r13
0x1800019c0  pop     r12
0x1800019c2  pop     rdi
0x1800019c3  pop     rsi
0x1800019c4  pop     rbp
0x1800019c5  pop     rbx
0x1800019c6  retn
```
