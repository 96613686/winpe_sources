# CNG_FindBCryptOidInfo

- ea: `0x180006be4`
- end: `0x180006c93`
- name: `CNG_FindBCryptOidInfo`
- size: `175`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003460`
- `0x180004454`
- `0x1800050d0`
- `0x180006090`
- `0x180006a70`
- `0x180016e90`

## callees

- `0x180006be4`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180006c48`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180006c48`

## pseudocode

```c
__int64 __fastcall CNG_FindBCryptOidInfo(const void *a1, unsigned int a2, unsigned int a3, _QWORD *a4)
{
  SIZE_T v4; // r13
  unsigned int v5; // r12d
  unsigned int i; // edi
  __int64 j; // rbp
  __int64 v9; // rdx
  __int64 v10; // r14
  const void *v12; // [rsp+70h] [rbp+8h]

  v12 = a1;
  v4 = a2;
  v5 = a3 + 1;
  *a4 = 0;
  for ( i = a3; i < v5; ++i )
  {
    for ( j = 0; (unsigned int)j < LODWORD(qword_180021040[2 * i]); j = (unsigned int)(j + 1) )
    {
      v9 = qword_180021040[2 * i + 1];
      v10 = 80 * j;
      if ( (_DWORD)v4 == *(_DWORD *)(v9 + 80 * j + 40) )
      {
        if ( v4 == RtlCompareMemory(a1, *(const void **)(v9 + v10 + 48), v4) )
        {
          *a4 = v10 + qword_180021040[2 * i + 1];
          return 0;
        }
        a1 = v12;
      }
    }
  }
  return 2148073480LL;
}

```

## disassembly

```asm
0x180006be4  mov     [rsp+arg_0], rcx
0x180006be9  push    rbx
0x180006bea  push    rbp
0x180006beb  push    rsi
0x180006bec  push    rdi
0x180006bed  push    r12
0x180006bef  push    r13
0x180006bf1  push    r14
0x180006bf3  push    r15
0x180006bf5  sub     rsp, 28h
0x180006bf9  mov     r13d, edx
0x180006bfc  lea     r12d, [r8+1]
0x180006c00  lea     rdx, qword_180021040
0x180006c07  mov     qword ptr [r9], 0
0x180006c0e  mov     r15, r9
0x180006c11  mov     edi, r8d
0x180006c14  cmp     edi, r12d
0x180006c17  jnb     short loc_180006C8C
0x180006c19  xor     ebp, ebp
0x180006c1b  mov     esi, edi
0x180006c1d  add     rsi, rsi
0x180006c20  cmp     ebp, [rdx+rsi*8]
0x180006c23  jnb     short loc_180006C88
0x180006c25  mov     rdx, [rdx+rsi*8+8]
0x180006c2a  lea     r14, ds:0[rbp*4]
0x180006c32  add     r14, rbp
0x180006c35  shl     r14, 4
0x180006c39  cmp     r13d, [rdx+r14+28h]
0x180006c3e  jnz     short loc_180006C7D
0x180006c40  mov     rdx, [rdx+r14+30h]; Source2
0x180006c45  mov     r8, r13; Length
0x180006c48  call    cs:__imp_RtlCompareMemory
0x180006c4e  cmp     r13, rax
0x180006c51  jnz     short loc_180006C78
0x180006c53  lea     rax, qword_180021040
0x180006c5a  mov     rcx, [rax+rsi*8+8]
0x180006c5f  add     rcx, r14
0x180006c62  mov     [r15], rcx
0x180006c65  xor     eax, eax
0x180006c67  add     rsp, 28h
0x180006c6b  pop     r15
0x180006c6d  pop     r14
0x180006c6f  pop     r13
0x180006c71  pop     r12
0x180006c73  pop     rdi
0x180006c74  pop     rsi
0x180006c75  pop     rbp
0x180006c76  pop     rbx
0x180006c77  retn
0x180006c78  mov     rcx, [rsp+68h+arg_0]
0x180006c7d  inc     ebp
0x180006c7f  lea     rdx, qword_180021040
0x180006c86  jmp     short loc_180006C20
0x180006c88  inc     edi
0x180006c8a  jmp     short loc_180006C14
0x180006c8c  mov     eax, 80090008h
0x180006c91  jmp     short loc_180006C67
```
