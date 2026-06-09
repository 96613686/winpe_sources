# EfspValidateStreamTransitionMetadata

- ea: `0x140056b9c`
- end: `0x140056cc3`
- name: `EfspValidateStreamTransitionMetadata`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400568ac`

## callees

- `0x14005693c`
- `0x140056b9c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140056bdd`
- `ntoskrnl!RtlCompareMemory` at `0x140056c6c`
- `ntoskrnl!RtlCompareMemory` at `0x140056bdd`
- `ntoskrnl!RtlCompareMemory` at `0x140056c6c`

## pseudocode

```c
__int64 __fastcall EfspValidateStreamTransitionMetadata(__int64 a1, _DWORD *a2, unsigned int a3)
{
  unsigned __int16 v3; // r9
  unsigned __int64 v4; // rbp
  unsigned __int16 v6; // di
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // r8
  _DWORD *v11; // rbx

  v3 = *(_WORD *)(a1 + 28);
  v4 = a3;
  v6 = 0;
  if ( v3 >= 8u )
    v6 = v3 - 8;
  if ( RtlCompareMemory((const void *)a1, "EFSSTRAN", 8u) != 8
    || *(_DWORD *)(a1 + 8) != 1
    || *(_WORD *)(a1 + 30)
    || *(_DWORD *)(a1 + 32)
    || *(_DWORD *)(a1 + 36)
    || (v9 = *(_DWORD *)(a1 + 24), v9 < 0x30)
    || v9 != v4 - 24
    || (unsigned __int64)v6 + 72 > v4 )
  {
    v10 = 8021;
  }
  else if ( (*(_BYTE *)(a1 + 12) & 1) != 0 || !*(_WORD *)(a1 + 28) )
  {
    v11 = (_DWORD *)(v9 + a1);
    if ( v11 == a2 )
    {
      if ( RtlCompareMemory(v11, "EFSSTRFT", 8u) == 8 && v11[2] == 1 && !v11[4] && !v11[5] )
        return 0;
      v10 = 8056;
    }
    else
    {
      v10 = 8043;
    }
  }
  else
  {
    v10 = 8032;
  }
  EfspTraceLogAssert(v8, 6, v10, 3221227787LL);
  return 3221227787LL;
}

```

## disassembly

```asm
0x140056b9c  push    rbx
0x140056b9e  push    rbp
0x140056b9f  push    rsi
0x140056ba0  push    rdi
0x140056ba1  push    r14
0x140056ba3  push    r15
0x140056ba5  sub     rsp, 28h
0x140056ba9  movzx   r9d, word ptr [rcx+1Ch]
0x140056bae  mov     r15d, 8
0x140056bb4  movzx   eax, r9w
0x140056bb8  mov     ebp, r8d
0x140056bbb  sub     ax, r15w
0x140056bbf  xor     r14d, r14d
0x140056bc2  cmp     r9w, r15w
0x140056bc6  mov     rsi, rdx
0x140056bc9  mov     edi, r14d
0x140056bcc  lea     rdx, aEfsstran; "EFSSTRAN"
0x140056bd3  mov     r8d, r15d; Length
0x140056bd6  cmovnb  di, ax
0x140056bda  mov     rbx, rcx
0x140056bdd  call    cs:__imp_RtlCompareMemory
0x140056be4  nop     dword ptr [rax+rax+00h]
0x140056be9  cmp     rax, r15
0x140056bec  jnz     loc_140056C9B
0x140056bf2  cmp     dword ptr [rbx+8], 1
0x140056bf6  jnz     loc_140056C9B
0x140056bfc  cmp     [rbx+1Eh], r14w
0x140056c01  jnz     loc_140056C9B
0x140056c07  cmp     [rbx+20h], r14d
0x140056c0b  jnz     loc_140056C9B
0x140056c11  cmp     [rbx+24h], r14d
0x140056c15  jnz     loc_140056C9B
0x140056c1b  mov     eax, [rbx+18h]
0x140056c1e  cmp     eax, 30h ; '0'
0x140056c21  jb      short loc_140056C9B
0x140056c23  mov     edx, eax
0x140056c25  lea     rax, [rbp-18h]
0x140056c29  cmp     rdx, rax
0x140056c2c  jnz     short loc_140056C9B
0x140056c2e  movzx   eax, di
0x140056c31  add     rax, 48h ; 'H'
0x140056c35  cmp     rax, rbp
0x140056c38  ja      short loc_140056C9B
0x140056c3a  test    byte ptr [rbx+0Ch], 1
0x140056c3e  jnz     short loc_140056C4F
0x140056c40  cmp     [rbx+1Ch], r14w
0x140056c45  jz      short loc_140056C4F
0x140056c47  mov     r8d, 1F60h
0x140056c4d  jmp     short loc_140056CA1
0x140056c4f  add     rbx, rdx
0x140056c52  cmp     rbx, rsi
0x140056c55  jz      short loc_140056C5F
0x140056c57  mov     r8d, 1F6Bh
0x140056c5d  jmp     short loc_140056CA1
0x140056c5f  mov     r8, r15; Length
0x140056c62  lea     rdx, aEfsstrft; "EFSSTRFT"
0x140056c69  mov     rcx, rbx; Source1
0x140056c6c  call    cs:__imp_RtlCompareMemory
0x140056c73  nop     dword ptr [rax+rax+00h]
0x140056c78  cmp     rax, r15
0x140056c7b  jnz     short loc_140056C93
0x140056c7d  cmp     dword ptr [rbx+8], 1
0x140056c81  jnz     short loc_140056C93
0x140056c83  cmp     [rbx+10h], r14d
0x140056c87  jnz     short loc_140056C93
0x140056c89  cmp     [rbx+14h], r14d
0x140056c8d  jnz     short loc_140056C93
0x140056c8f  xor     eax, eax
0x140056c91  jmp     short loc_140056CB5
0x140056c93  mov     r8d, 1F78h
0x140056c99  jmp     short loc_140056CA1
0x140056c9b  mov     r8d, 1F55h
0x140056ca1  mov     ebx, 0C000090Bh
0x140056ca6  mov     edx, 6
0x140056cab  mov     r9d, ebx
0x140056cae  call    EfspTraceLogAssert
0x140056cb3  mov     eax, ebx
0x140056cb5  add     rsp, 28h
0x140056cb9  pop     r15
0x140056cbb  pop     r14
0x140056cbd  pop     rdi
0x140056cbe  pop     rsi
0x140056cbf  pop     rbp
0x140056cc0  pop     rbx
0x140056cc1  retn
```
