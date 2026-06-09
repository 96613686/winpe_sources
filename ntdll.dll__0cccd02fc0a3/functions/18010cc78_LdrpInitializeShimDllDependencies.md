# LdrpInitializeShimDllDependencies

- ea: `0x18010cc78`
- end: `0x18010ce08`
- name: `LdrpInitializeShimDllDependencies`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800bd6e0`

## callees

- `0x18001eb80`
- `0x1800414e0`
- `0x1800e5fcc`
- `0x18010cc78`
- `0x18015e850`
- `0x18016f030`

## string_xrefs

- `0x18010cdb5`: `LdrpInitializeShimDllDependencies`

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
0x18010cc78  mov     [rsp-8+arg_10], rbx
0x18010cc7d  push    rbp
0x18010cc7e  push    rsi
0x18010cc7f  push    rdi
0x18010cc80  push    r12
0x18010cc82  push    r14
0x18010cc84  lea     rbp, [rsp-10h]
0x18010cc89  sub     rsp, 110h
0x18010cc90  xor     edx, edx; Val
0x18010cc92  mov     [rbp+30h+arg_8], 0
0x18010cc99  mov     r8d, 0D0h; Size
0x18010cc9f  lea     rcx, [rsp+130h+var_F0]; void *
0x18010cca4  call    memset$thunk$772440563353939046
0x18010cca9  mov     rbx, cs:qword_1801CA8D0
0x18010ccb0  lea     r12, qword_1801CA8D0
0x18010ccb7  mov     [rsp+130h+var_D0], 80000h
0x18010ccbf  lea     rax, [rbp+30h+arg_8]
0x18010ccc3  mov     [rsp+130h+var_C8], rax
0x18010ccc8  cmp     rbx, r12
0x18010cccb  jz      short loc_18010CD01
0x18010cccd  mov     rax, [rbx+98h]
0x18010ccd4  mov     ecx, [rax+38h]
0x18010ccd7  cmp     ecx, 7
0x18010ccda  jnz     short loc_18010CCF2
0x18010ccdc  cmp     qword ptr [rbx+0B0h], 0
0x18010cce4  jnz     short loc_18010CCF2
0x18010cce6  lea     rax, [rsp+130h+var_F0]
0x18010cceb  mov     [rbx+0B0h], rax
0x18010ccf2  mov     rbx, [rbx]
0x18010ccf5  cmp     rbx, r12
0x18010ccf8  jnz     short loc_18010CCCD
0x18010ccfa  mov     rbx, cs:qword_1801CA8D0
0x18010cd01  mov     [rbp+30h+arg_8], 0
0x18010cd08  xor     r14d, r14d
0x18010cd0b  cmp     rbx, r12
0x18010cd0e  jz      short loc_18010CD74
0x18010cd10  mov     eax, [rbx+68h]
0x18010cd13  mov     r14, rbx
0x18010cd16  bt      eax, 8
0x18010cd1a  jnb     short loc_18010CD68
0x18010cd1c  mov     rax, [rbx+98h]
0x18010cd23  mov     rsi, [rax+28h]
0x18010cd27  test    rsi, rsi
0x18010cd2a  jz      short loc_18010CD68
0x18010cd2c  mov     rdi, rsi
0x18010cd2f  mov     rdi, [rdi]
0x18010cd32  test    byte ptr [rdi+18h], 1
0x18010cd36  jnz     short loc_18010CD63
0x18010cd38  mov     rcx, [rdi+8]
0x18010cd3c  mov     eax, [rcx+38h]
0x18010cd3f  cmp     eax, 7
0x18010cd42  jnz     short loc_18010CD5E
0x18010cd44  lea     r8, [rbp+30h+arg_0]
0x18010cd48  mov     [rbp+30h+arg_0], 0
0x18010cd4c  lea     rdx, [rbp+30h+arg_8]
0x18010cd50  call    LdrpInitializeGraphRecurse
0x18010cd55  mov     [rbp+30h+arg_8], eax
0x18010cd58  test    eax, eax
0x18010cd5a  jns     short loc_18010CD63
0x18010cd5c  jmp     short loc_18010CD74
0x18010cd5e  cmp     eax, 0FFFFFFFCh
0x18010cd61  jz      short loc_18010CD6D
0x18010cd63  cmp     rdi, rsi
0x18010cd66  jnz     short loc_18010CD2F
0x18010cd68  mov     rbx, [rbx]
0x18010cd6b  jmp     short loc_18010CD0B
0x18010cd6d  mov     [rbp+30h+arg_8], 0C0000142h
0x18010cd74  mov     rax, cs:qword_1801CA8D0
0x18010cd7b  jmp     short loc_18010CD9C
0x18010cd7d  lea     rcx, [rsp+130h+var_F0]
0x18010cd82  mov     r14, rax
0x18010cd85  cmp     [rax+0B0h], rcx
0x18010cd8c  jnz     short loc_18010CD99
0x18010cd8e  mov     qword ptr [rax+0B0h], 0
0x18010cd99  mov     rax, [rax]
0x18010cd9c  cmp     rax, r12
0x18010cd9f  jnz     short loc_18010CD7D
0x18010cda1  mov     ecx, [rbp+30h+arg_8]
0x18010cda4  test    ecx, ecx
0x18010cda6  jns     short loc_18010CDF0
0x18010cda8  mov     [rsp+130h+var_100], ecx
0x18010cdac  lea     rax, [r14+48h]
0x18010cdb0  mov     qword ptr [rsp+130h+ArgList], rax; ArgList
0x18010cdb5  lea     r8, aLdrpinitialize_11; "LdrpInitializeShimDllDependencies"
0x18010cdbc  lea     rax, aInitializingAS; "Initializing a shim dependency \"%wZ\" "...
0x18010cdc3  xor     r9d, r9d; int
0x18010cdc6  mov     edx, 0E52h; int
0x18010cdcb  mov     [rsp+130h+Format], rax; Format
0x18010cdd0  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18010cdd7  call    LdrpLogInternal
0x18010cddc  mov     ecx, [rbp+30h+arg_8]
0x18010cddf  call    LdrpInitializationFailure
0x18010cde4  mov     edx, [rbp+30h+arg_8]
0x18010cde7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18010cdeb  call    ZwTerminateProcess
0x18010cdf0  mov     rbx, [rsp+130h+arg_10]
0x18010cdf8  add     rsp, 110h
0x18010cdff  pop     r14
0x18010ce01  pop     r12
0x18010ce03  pop     rdi
0x18010ce04  pop     rsi
0x18010ce05  pop     rbp
0x18010ce06  retn
```
