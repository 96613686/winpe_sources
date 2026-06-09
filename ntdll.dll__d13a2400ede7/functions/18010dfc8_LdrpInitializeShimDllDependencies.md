# LdrpInitializeShimDllDependencies

- ea: `0x18010dfc8`
- end: `0x18010e158`
- name: `LdrpInitializeShimDllDependencies`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800c19c0`

## callees

- `0x18001eb80`
- `0x18004eb70`
- `0x1800e634c`
- `0x18010dfc8`
- `0x18015f060`
- `0x18016f030`

## string_xrefs

- `0x18010e105`: `LdrpInitializeShimDllDependencies`

## pseudocode

```c
__int64 *LdrpInitializeShimDllDependencies()
{
  __int64 v0; // rbx
  char v1; // r14
  __int64 v2; // rax
  __int64 *v3; // rsi
  __int64 *v4; // rdi
  __int64 v5; // rcx
  int v6; // eax
  __int64 *result; // rax
  _BYTE v8[32]; // [rsp+40h] [rbp-C0h] BYREF
  int v9; // [rsp+60h] [rbp-A0h]
  int *v10; // [rsp+68h] [rbp-98h]
  char v11; // [rsp+140h] [rbp+40h] BYREF
  int v12; // [rsp+148h] [rbp+48h] BYREF

  v12 = 0;
  memset_thunk_772440563353939046(v8, 0, 0xD0u);
  v0 = qword_1801CA8D0;
  v9 = 0x80000;
  v10 = &v12;
  if ( (__int64 *)qword_1801CA8D0 != &qword_1801CA8D0 )
  {
    do
    {
      if ( *(_DWORD *)(*(_QWORD *)(v0 + 152) + 56LL) == 7 && !*(_QWORD *)(v0 + 176) )
        *(_QWORD *)(v0 + 176) = v8;
      v0 = *(_QWORD *)v0;
    }
    while ( (__int64 *)v0 != &qword_1801CA8D0 );
    v0 = qword_1801CA8D0;
  }
  v12 = 0;
  v1 = 0;
  while ( (__int64 *)v0 != &qword_1801CA8D0 )
  {
    v1 = v0;
    if ( (*(_DWORD *)(v0 + 104) & 0x100) != 0 )
    {
      v2 = *(_QWORD *)(v0 + 152);
      v3 = *(__int64 **)(v2 + 40);
      if ( v3 )
      {
        v4 = *(__int64 **)(v2 + 40);
        do
        {
          v4 = (__int64 *)*v4;
          if ( (v4[3] & 1) == 0 )
          {
            v5 = v4[1];
            v6 = *(_DWORD *)(v5 + 56);
            if ( v6 == 7 )
            {
              v11 = 0;
              v12 = LdrpInitializeGraphRecurse(v5, &v12, &v11);
              if ( v12 < 0 )
                goto LABEL_20;
            }
            else if ( v6 == -4 )
            {
              v12 = -1073741502;
              goto LABEL_20;
            }
          }
        }
        while ( v4 != v3 );
      }
    }
    v0 = *(_QWORD *)v0;
  }
LABEL_20:
  for ( result = (__int64 *)qword_1801CA8D0; result != &qword_1801CA8D0; result = (__int64 *)*result )
  {
    v1 = (char)result;
    if ( (_BYTE *)result[22] == v8 )
      result[22] = 0;
  }
  if ( v12 < 0 )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      3666,
      (int)"LdrpInitializeShimDllDependencies",
      0,
      "Initializing a shim dependency \"%wZ\" failed with status 0x%08lx\n",
      v1 + 72);
    LdrpInitializationFailure((unsigned int)v12);
    return (__int64 *)ZwTerminateProcess(-1, (unsigned int)v12);
  }
  return result;
}

```

## disassembly

```asm
0x18010dfc8  mov     [rsp-8+arg_10], rbx
0x18010dfcd  push    rbp
0x18010dfce  push    rsi
0x18010dfcf  push    rdi
0x18010dfd0  push    r12
0x18010dfd2  push    r14
0x18010dfd4  lea     rbp, [rsp-10h]
0x18010dfd9  sub     rsp, 110h
0x18010dfe0  xor     edx, edx; Val
0x18010dfe2  mov     [rbp+30h+arg_8], 0
0x18010dfe9  mov     r8d, 0D0h; Size
0x18010dfef  lea     rcx, [rsp+130h+var_F0]; void *
0x18010dff4  call    memset$thunk$772440563353939046
0x18010dff9  mov     rbx, cs:qword_1801CA8D0
0x18010e000  lea     r12, qword_1801CA8D0
0x18010e007  mov     [rsp+130h+var_D0], 80000h
0x18010e00f  lea     rax, [rbp+30h+arg_8]
0x18010e013  mov     [rsp+130h+var_C8], rax
0x18010e018  cmp     rbx, r12
0x18010e01b  jz      short loc_18010E051
0x18010e01d  mov     rax, [rbx+98h]
0x18010e024  mov     ecx, [rax+38h]
0x18010e027  cmp     ecx, 7
0x18010e02a  jnz     short loc_18010E042
0x18010e02c  cmp     qword ptr [rbx+0B0h], 0
0x18010e034  jnz     short loc_18010E042
0x18010e036  lea     rax, [rsp+130h+var_F0]
0x18010e03b  mov     [rbx+0B0h], rax
0x18010e042  mov     rbx, [rbx]
0x18010e045  cmp     rbx, r12
0x18010e048  jnz     short loc_18010E01D
0x18010e04a  mov     rbx, cs:qword_1801CA8D0
0x18010e051  mov     [rbp+30h+arg_8], 0
0x18010e058  xor     r14d, r14d
0x18010e05b  cmp     rbx, r12
0x18010e05e  jz      short loc_18010E0C4
0x18010e060  mov     eax, [rbx+68h]
0x18010e063  mov     r14, rbx
0x18010e066  bt      eax, 8
0x18010e06a  jnb     short loc_18010E0B8
0x18010e06c  mov     rax, [rbx+98h]
0x18010e073  mov     rsi, [rax+28h]
0x18010e077  test    rsi, rsi
0x18010e07a  jz      short loc_18010E0B8
0x18010e07c  mov     rdi, rsi
0x18010e07f  mov     rdi, [rdi]
0x18010e082  test    byte ptr [rdi+18h], 1
0x18010e086  jnz     short loc_18010E0B3
0x18010e088  mov     rcx, [rdi+8]
0x18010e08c  mov     eax, [rcx+38h]
0x18010e08f  cmp     eax, 7
0x18010e092  jnz     short loc_18010E0AE
0x18010e094  lea     r8, [rbp+30h+arg_0]
0x18010e098  mov     [rbp+30h+arg_0], 0
0x18010e09c  lea     rdx, [rbp+30h+arg_8]
0x18010e0a0  call    LdrpInitializeGraphRecurse
0x18010e0a5  mov     [rbp+30h+arg_8], eax
0x18010e0a8  test    eax, eax
0x18010e0aa  jns     short loc_18010E0B3
0x18010e0ac  jmp     short loc_18010E0C4
0x18010e0ae  cmp     eax, 0FFFFFFFCh
0x18010e0b1  jz      short loc_18010E0BD
0x18010e0b3  cmp     rdi, rsi
0x18010e0b6  jnz     short loc_18010E07F
0x18010e0b8  mov     rbx, [rbx]
0x18010e0bb  jmp     short loc_18010E05B
0x18010e0bd  mov     [rbp+30h+arg_8], 0C0000142h
0x18010e0c4  mov     rax, cs:qword_1801CA8D0
0x18010e0cb  jmp     short loc_18010E0EC
0x18010e0cd  lea     rcx, [rsp+130h+var_F0]
0x18010e0d2  mov     r14, rax
0x18010e0d5  cmp     [rax+0B0h], rcx
0x18010e0dc  jnz     short loc_18010E0E9
0x18010e0de  mov     qword ptr [rax+0B0h], 0
0x18010e0e9  mov     rax, [rax]
0x18010e0ec  cmp     rax, r12
0x18010e0ef  jnz     short loc_18010E0CD
0x18010e0f1  mov     ecx, [rbp+30h+arg_8]
0x18010e0f4  test    ecx, ecx
0x18010e0f6  jns     short loc_18010E140
0x18010e0f8  mov     [rsp+130h+var_100], ecx
0x18010e0fc  lea     rax, [r14+48h]
0x18010e100  mov     qword ptr [rsp+130h+ArgList], rax; ArgList
0x18010e105  lea     r8, aLdrpinitialize_11; "LdrpInitializeShimDllDependencies"
0x18010e10c  lea     rax, aInitializingAS; "Initializing a shim dependency \"%wZ\" "...
0x18010e113  xor     r9d, r9d; int
0x18010e116  mov     edx, 0E52h; int
0x18010e11b  mov     [rsp+130h+Format], rax; Format
0x18010e120  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18010e127  call    LdrpLogInternal
0x18010e12c  mov     ecx, [rbp+30h+arg_8]
0x18010e12f  call    LdrpInitializationFailure
0x18010e134  mov     edx, [rbp+30h+arg_8]
0x18010e137  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18010e13b  call    ZwTerminateProcess
0x18010e140  mov     rbx, [rsp+130h+arg_10]
0x18010e148  add     rsp, 110h
0x18010e14f  pop     r14
0x18010e151  pop     r12
0x18010e153  pop     rdi
0x18010e154  pop     rsi
0x18010e155  pop     rbp
0x18010e156  retn
```
