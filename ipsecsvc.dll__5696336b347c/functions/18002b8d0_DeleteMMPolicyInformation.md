# DeleteMMPolicyInformation

- ea: `0x18002b8d0`
- end: `0x18002b9a0`
- name: `DeleteMMPolicyInformation`
- size: `208`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180001710`
- `0x18000acb4`
- `0x18000b29c`

## callees

- `0x18000e510`
- `0x1800277f8`
- `0x1800281dc`
- `0x1800293a4`
- `0x18002b8d0`

## pseudocode

```c
__int64 __fastcall DeleteMMPolicyInformation(__int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // r14
  __int64 i; // rbx
  unsigned int v5; // eax
  unsigned int v6; // eax
  _OWORD v8[3]; // [rsp+20h] [rbp-38h] BYREF

  PADeleteMMFilters(a1, *(_QWORD *)(a1 + 32), *(unsigned int *)(a1 + 40));
  v2 = *(_DWORD *)(a1 + 40);
  v3 = *(_QWORD *)(a1 + 32);
  for ( i = 0; (unsigned int)i < v2; i = (unsigned int)(i + 1) )
  {
    v8[0] = *(_OWORD *)(*(_QWORD *)(v3 + 8 * i) + 8LL);
    v5 = PADeleteMMAuthMethod(v8);
    if ( v5
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_3886d72ed9b13ccdc9fcf8afdec51da0_Traceguids, v5);
    }
  }
  _mm_lfence();
  v8[0] = *(_OWORD *)*(_QWORD *)(a1 + 24);
  v6 = PADeleteMMPolicy(v8);
  if ( v6 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids, v6);
  return 0;
}

```

## disassembly

```asm
0x18002b8d0  push    rbx
0x18002b8d2  push    rbp
0x18002b8d3  push    rsi
0x18002b8d4  push    rdi
0x18002b8d5  push    r14
0x18002b8d7  sub     rsp, 30h
0x18002b8db  mov     r8d, [rcx+28h]
0x18002b8df  mov     rdi, rcx
0x18002b8e2  mov     rdx, [rcx+20h]
0x18002b8e6  call    PADeleteMMFilters
0x18002b8eb  mov     esi, [rdi+28h]
0x18002b8ee  lea     rbp, WPP_GLOBAL_Control
0x18002b8f5  mov     r14, [rdi+20h]
0x18002b8f9  xor     ebx, ebx
0x18002b8fb  test    esi, esi
0x18002b8fd  jz      short loc_18002B94B
0x18002b8ff  mov     rcx, [r14+rbx*8]
0x18002b903  movups  xmm0, xmmword ptr [rcx+8]
0x18002b907  lea     rcx, [rsp+58h+var_38]
0x18002b90c  movdqu  [rsp+58h+var_38], xmm0
0x18002b912  call    PADeleteMMAuthMethod
0x18002b917  test    eax, eax
0x18002b919  jz      short loc_18002B945
0x18002b91b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b922  cmp     rcx, rbp
0x18002b925  jz      short loc_18002B945
0x18002b927  test    byte ptr [rcx+1Ch], 10h
0x18002b92b  jz      short loc_18002B945
0x18002b92d  mov     rcx, [rcx+10h]
0x18002b931  lea     r8, WPP_3886d72ed9b13ccdc9fcf8afdec51da0_Traceguids
0x18002b938  mov     edx, 1Dh
0x18002b93d  mov     r9d, eax
0x18002b940  call    WPP_SF_d
0x18002b945  inc     ebx
0x18002b947  cmp     ebx, esi
0x18002b949  jb      short loc_18002B8FF
0x18002b94b  lfence
0x18002b94e  mov     rax, [rdi+18h]
0x18002b952  lea     rcx, [rsp+58h+var_38]
0x18002b957  movups  xmm0, xmmword ptr [rax]
0x18002b95a  movdqu  [rsp+58h+var_38], xmm0
0x18002b960  call    PADeleteMMPolicy
0x18002b965  test    eax, eax
0x18002b967  jz      short loc_18002B993
0x18002b969  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b970  cmp     rcx, rbp
0x18002b973  jz      short loc_18002B993
0x18002b975  test    byte ptr [rcx+1Ch], 10h
0x18002b979  jz      short loc_18002B993
0x18002b97b  mov     rcx, [rcx+10h]
0x18002b97f  lea     r8, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids
0x18002b986  mov     edx, 17h
0x18002b98b  mov     r9d, eax
0x18002b98e  call    WPP_SF_d
0x18002b993  xor     eax, eax
0x18002b995  add     rsp, 30h
0x18002b999  pop     r14
0x18002b99b  pop     rdi
0x18002b99c  pop     rsi
0x18002b99d  pop     rbp
0x18002b99e  pop     rbx
0x18002b99f  retn
```
