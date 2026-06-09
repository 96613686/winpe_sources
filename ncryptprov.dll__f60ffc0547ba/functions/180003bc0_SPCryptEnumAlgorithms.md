# SPCryptEnumAlgorithms

- ea: `0x180003bc0`
- end: `0x180003e8b`
- name: `SPCryptEnumAlgorithms`
- size: `715`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003bc0`
- `0x180004350`
- `0x18000af80`
- `0x18000b250`
- `0x18000def0`
- `0x1800398b0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180003c94`
- `ntdll!RtlReleaseResource` at `0x180003c94`
- `ntdll!RtlAcquireResourceShared` at `0x180003bf9`
- `ntdll!RtlAcquireResourceShared` at `0x180003bf9`

## string_xrefs

- `0x180003cf8`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180003d4b`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180003e1f`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180003e73`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`

## pseudocode

```c
__int64 __fastcall SPCryptEnumAlgorithms(__int64 a1, int a2, _DWORD *a3, __int64 *a4, int a5)
{
  __int64 *v5; // r12
  __int64 v8; // rax
  int v9; // edx
  int v10; // r8d
  __int64 v11; // r14
  __int64 v12; // rdx
  __int64 v13; // rbx
  unsigned __int64 i; // rcx
  __int64 v15; // rax
  unsigned int v16; // ebx
  __int64 v18; // rdi
  __int64 v19; // rax
  int v20; // edx
  int v21; // r8d
  char *v22; // r13
  __int64 v23; // r15
  unsigned __int64 v24; // rsi
  __int64 v25; // r14
  int v26; // eax
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // [rsp+40h] [rbp-58h]

  v5 = a4;
  v8 = KspValidateProvHandle();
  v29 = v8;
  v11 = v8;
  if ( v8 )
  {
    RtlAcquireResourceShared((PRTL_RESOURCE)(v8 + 64), 1u);
    if ( a3 && v5 )
    {
      *a3 = 0;
      *v5 = 0;
      if ( (a5 & 0xFFFFFFBF) == 0 )
      {
        v12 = 0;
        v13 = 0;
        for ( i = 0; i < 0x18; ++i )
        {
          v15 = 13 * i;
          if ( !a2 || (a2 & *((_DWORD *)&off_180064030 + 2 * v15 + 3)) != 0 )
          {
            v12 += (__int64)(*(&off_180064030 + v15 + 3) + 12);
            v13 = (unsigned int)(v13 + 1);
          }
        }
        if ( !a2 || (_DWORD)v13 )
        {
          v18 = 0;
          if ( (_DWORD)v13 )
          {
            v19 = SafeAllocaAllocateFromHeap(v12);
            v18 = v19;
            if ( !v19 )
            {
              v16 = -2146893810;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v20,
                  v21,
                  (unsigned int)"Status",
                  14,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c",
                  52);
              goto LABEL_15;
            }
            *a3 = v13;
            v22 = (char *)(v19 + 24 * v13);
            v23 = v19;
            v24 = 0;
            do
            {
              if ( v24 >= 0x18 )
                break;
              if ( !a2 || (a2 & *((_DWORD *)&off_180064030 + 26 * v24 + 3)) != 0 )
              {
                v25 = 13 * v24;
                *(_DWORD *)(v23 + 16) = (&off_180064030)[13 * v24 + 1];
                *(_DWORD *)(v23 + 8) = *((_DWORD *)&off_180064030 + 26 * v24 + 2);
                v26 = *((_DWORD *)&off_180064030 + 26 * v24 + 3);
                *(_DWORD *)(v23 + 12) = v26;
                if ( *((_DWORD *)&off_180064030 + 26 * v24 + 3) == 8 && LODWORD((&off_180064030)[v25 + 2]) != 196610 )
                  *(_DWORD *)(v23 + 12) = v26 | 0x10;
                *(_QWORD *)v23 = v22;
                memcpy_0(v22, (&off_180064030)[v25], (size_t)*(&off_180064030 + v25 + 3));
                v22 = &v22[(_QWORD)*(&off_180064030 + v25 + 3)];
                v23 += 24;
                LODWORD(v13) = v13 - 1;
              }
              ++v24;
            }
            while ( (_DWORD)v13 );
            v5 = a4;
            v11 = v29;
          }
          *v5 = v18;
          v16 = 0;
        }
        else
        {
          v16 = -2146893783;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v12,
              (unsigned int)&off_180064030,
              (unsigned int)"Status",
              41,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c",
              37);
        }
LABEL_15:
        RtlReleaseResource((PRTL_RESOURCE)(v11 + 64));
        return v16;
      }
      v16 = -2146893815;
      v27 = 768;
      v28 = 2148073481LL;
    }
    else
    {
      v16 = -2146893785;
      v27 = 758;
      v28 = 2148073511LL;
    }
    DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", v27);
    goto LABEL_15;
  }
  v16 = -2146893786;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v10,
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c",
      239);
  return v16;
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp+arg_18], r9
0x180003bc5  push    rbx
0x180003bc6  push    rbp
0x180003bc7  push    rsi
0x180003bc8  push    rdi
0x180003bc9  push    r12
0x180003bcb  push    r13
0x180003bcd  push    r14
0x180003bcf  push    r15
0x180003bd1  sub     rsp, 58h
0x180003bd5  mov     r12, r9
0x180003bd8  mov     rsi, r8
0x180003bdb  mov     ebp, edx
0x180003bdd  call    KspValidateProvHandle
0x180003be2  mov     [rsp+98h+var_58], rax
0x180003be7  mov     r14, rax
0x180003bea  test    rax, rax
0x180003bed  jz      loc_180003D21
0x180003bf3  lea     rcx, [rax+40h]; Resource
0x180003bf7  mov     dl, 1; Wait
0x180003bf9  call    cs:__imp_RtlAcquireResourceShared
0x180003c00  nop     dword ptr [rax+rax+00h]
0x180003c05  test    rsi, rsi
0x180003c08  jz      loc_180003E63
0x180003c0e  test    r12, r12
0x180003c11  jz      loc_180003E63
0x180003c17  test    [rsp+98h+arg_20], 0FFFFFFBFh
0x180003c22  mov     dword ptr [rsi], 0
0x180003c28  mov     qword ptr [r12], 0
0x180003c30  jnz     loc_180003E05
0x180003c36  xor     edx, edx
0x180003c38  lea     r8, off_180064030; "RSA"
0x180003c3f  xor     ebx, ebx
0x180003c41  xor     ecx, ecx
0x180003c43  imul    rax, rcx, 68h ; 'h'
0x180003c47  test    ebp, ebp
0x180003c49  jz      short loc_180003C52
0x180003c4b  test    [rax+r8+0Ch], ebp
0x180003c50  jz      short loc_180003C5D
0x180003c52  add     rdx, 18h
0x180003c56  add     rdx, [rax+r8+18h]
0x180003c5b  inc     ebx
0x180003c5d  inc     rcx
0x180003c60  cmp     rcx, 18h
0x180003c64  jb      short loc_180003C43
0x180003c66  test    ebp, ebp
0x180003c68  jz      short loc_180003CB4
0x180003c6a  test    ebx, ebx
0x180003c6c  jnz     short loc_180003CB4
0x180003c6e  mov     ebx, 80090029h
0x180003c73  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c7a  lea     rax, WPP_GLOBAL_Control
0x180003c81  cmp     rcx, rax
0x180003c84  jz      short loc_180003C90
0x180003c86  test    byte ptr [rcx+1Ch], 1
0x180003c8a  jnz     loc_180003E17
0x180003c90  lea     rcx, [r14+40h]; Resource
0x180003c94  call    cs:__imp_RtlReleaseResource
0x180003c9b  nop     dword ptr [rax+rax+00h]
0x180003ca0  mov     eax, ebx
0x180003ca2  add     rsp, 58h
0x180003ca6  pop     r15
0x180003ca8  pop     r14
0x180003caa  pop     r13
0x180003cac  pop     r12
0x180003cae  pop     rdi
0x180003caf  pop     rsi
0x180003cb0  pop     rbp
0x180003cb1  pop     rbx
0x180003cb2  retn
0x180003cb4  xor     edi, edi
0x180003cb6  test    ebx, ebx
0x180003cb8  jz      loc_180003DFA
0x180003cbe  mov     rcx, rdx
0x180003cc1  call    SafeAllocaAllocateFromHeap
0x180003cc6  mov     rdi, rax
0x180003cc9  test    rax, rax
0x180003ccc  jnz     loc_180003D78
0x180003cd2  mov     ebx, 8009000Eh
0x180003cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cde  lea     rax, WPP_GLOBAL_Control
0x180003ce5  cmp     rcx, rax
0x180003ce8  jz      short loc_180003C90
0x180003cea  test    byte ptr [rcx+1Ch], 1
0x180003cee  jz      short loc_180003C90
0x180003cf0  mov     [rsp+98h+var_68], 334h
0x180003cf8  lea     rax, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003cff  mov     [rsp+98h+var_70], rax
0x180003d04  mov     [rsp+98h+var_78], 8009000Eh
0x180003d0c  mov     rcx, [rcx+10h]
0x180003d10  lea     r9, aStatus; "Status"
0x180003d17  call    WPP_SF_sDsd
0x180003d1c  jmp     loc_180003C90
0x180003d21  mov     ebx, 80090026h
0x180003d26  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d2d  lea     rax, WPP_GLOBAL_Control
0x180003d34  cmp     rcx, rax
0x180003d37  jz      loc_180003CA0
0x180003d3d  test    byte ptr [rcx+1Ch], 1
0x180003d41  jz      loc_180003CA0
0x180003d47  mov     rcx, [rcx+10h]
0x180003d4b  lea     rax, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003d52  mov     [rsp+98h+var_68], 2EFh
0x180003d5a  lea     r9, aStatus; "Status"
0x180003d61  mov     [rsp+98h+var_70], rax
0x180003d66  mov     [rsp+98h+var_78], 80090026h
0x180003d6e  call    WPP_SF_sDsd
0x180003d73  jmp     loc_180003CA0
0x180003d78  lea     rcx, [rbx+rbx*2]
0x180003d7c  mov     [rsi], ebx
0x180003d7e  lea     r13, [rax+rcx*8]
0x180003d82  mov     r15, rax
0x180003d85  xor     esi, esi
0x180003d87  lea     r12, off_180064030; "RSA"
0x180003d8e  cmp     rsi, 18h
0x180003d92  jnb     short loc_180003DED
0x180003d94  test    ebp, ebp
0x180003d96  jnz     loc_180003E38
0x180003d9c  imul    r14, rsi, 68h ; 'h'
0x180003da0  mov     eax, [r14+r12+10h]
0x180003da5  mov     [r15+10h], eax
0x180003da9  mov     eax, [r14+r12+8]
0x180003dae  mov     [r15+8], eax
0x180003db2  mov     eax, [r14+r12+0Ch]
0x180003db7  mov     [r15+0Ch], eax
0x180003dbb  cmp     dword ptr [r14+r12+0Ch], 8
0x180003dc1  jz      loc_180003E48
0x180003dc7  mov     [r15], r13
0x180003dca  mov     rcx, r13; void *
0x180003dcd  mov     r8, [r14+r12+18h]; Size
0x180003dd2  mov     rdx, [r14+r12]; Src
0x180003dd6  call    memcpy_0
0x180003ddb  add     r13, [r14+r12+18h]
0x180003de0  add     r15, 18h
0x180003de4  dec     ebx
0x180003de6  inc     rsi
0x180003de9  test    ebx, ebx
0x180003deb  jnz     short loc_180003D8E
0x180003ded  mov     r12, [rsp+98h+arg_18]
0x180003df5  mov     r14, [rsp+98h+var_58]
0x180003dfa  mov     [r12], rdi
0x180003dfe  xor     ebx, ebx
0x180003e00  jmp     loc_180003C90
0x180003e05  mov     ebx, 80090009h
0x180003e0a  mov     r9d, 300h
0x180003e10  mov     ecx, 80090009h
0x180003e15  jmp     short loc_180003E73
0x180003e17  mov     [rsp+98h+var_68], 325h
0x180003e1f  lea     rax, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003e26  mov     [rsp+98h+var_70], rax
0x180003e2b  mov     [rsp+98h+var_78], 80090029h
0x180003e33  jmp     loc_180003D0C
0x180003e38  imul    rax, rsi, 68h ; 'h'
0x180003e3c  test    [rax+r12+0Ch], ebp
0x180003e41  jz      short loc_180003DE6
0x180003e43  jmp     loc_180003D9C
0x180003e48  cmp     dword ptr [r14+r12+20h], 30002h
0x180003e51  jz      loc_180003DC7
0x180003e57  or      eax, 10h
0x180003e5a  mov     [r15+0Ch], eax
0x180003e5e  jmp     loc_180003DC7
0x180003e63  mov     ebx, 80090027h
0x180003e68  mov     r9d, 2F6h
0x180003e6e  mov     ecx, 80090027h
0x180003e73  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003e7a  lea     rdx, aStatus; "Status"
0x180003e81  call    DebugTraceError
0x180003e86  jmp     loc_180003C90
```
