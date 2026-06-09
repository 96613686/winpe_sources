# Smb2AttemptToCacheShareRootHandle

- ea: `0x140016df0`
- end: `0x14001709d`
- name: `Smb2AttemptToCacheShareRootHandle`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140013210`

## callees

- `0x140016df0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140016fc1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140017085`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003b6ce`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140016fc1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140017085`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003b6ce`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140016eeb`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140016eeb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140016efe`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140016efe`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001702f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001702f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140016e82`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140016e82`

## pseudocode

```c
__int64 __fastcall Smb2AttemptToCacheShareRootHandle(__int64 a1)
{
  __int64 v2; // rbp
  unsigned int v3; // esi
  __int64 v4; // rdx
  __m128i *v5; // rdi
  __int64 v6; // r14
  int v7; // eax
  __int16 v9; // ax
  __int32 v10; // r13d
  __m128i v11; // xmm7
  __m128i si128; // xmm6
  unsigned __int64 v13; // xmm0_8
  unsigned __int64 v14; // r12
  __int32 v15; // r13d
  __int64 v16; // rax
  __int32 v17; // ecx
  __int32 v18; // [rsp+20h] [rbp-88h]
  __int32 v19; // [rsp+24h] [rbp-84h]
  __int32 v20; // [rsp+24h] [rbp-84h]
  __int32 v21; // [rsp+28h] [rbp-80h]
  __int32 v22; // [rsp+2Ch] [rbp-7Ch]
  __int64 v23; // [rsp+30h] [rbp-78h]
  KIRQL v24; // [rsp+B0h] [rbp+8h]
  __int32 v25; // [rsp+B8h] [rbp+10h]
  __int32 v26; // [rsp+C0h] [rbp+18h]
  __int32 v27; // [rsp+C8h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 48);
  v3 = -1073741802;
  v4 = *(_QWORD *)(a1 + 32);
  v5 = *(__m128i **)(*(_QWORD *)(a1 + 40) + 40LL);
  v6 = v5[1].m128i_i64[1];
  if ( dbgCacheShareRootHandle )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v5[26].m128i_i64[1] + 88) + 716LL) & 0x4000) == 0 )
    {
      v7 = *(_DWORD *)(v2 + 8);
      if ( (v7 & 0x80u) == 0 && (v7 & 8) != 0 )
      {
        v9 = *(_WORD *)(v4 + 360);
        if ( !v9 || v9 == 2 && **(_WORD **)(v4 + 368) == 92 )
        {
          ExAcquirePushLockExclusiveEx(v2 + 16, 0);
          if ( !*(_DWORD *)(v2 + 4) )
          {
            v25 = *(_DWORD *)(v2 + 44);
            v10 = *(_DWORD *)(v2 + 48);
            v26 = *(_DWORD *)(v2 + 52);
            v11 = *(__m128i *)(v2 + 28);
            v27 = *(_DWORD *)(a1 + 152);
            v18 = *(_DWORD *)(a1 + 156);
            v19 = v10;
            v24 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920));
            *(_DWORD *)(v6 + 2352) = (unsigned int)PsGetCurrentThreadId();
            si128 = v5[40];
            v21 = v5[41].m128i_i32[3];
            v22 = v5[42].m128i_i32[0];
            v13 = _mm_srli_si128(si128, 8).m128i_u64[0];
            v23 = v5[40].m128i_i64[0];
            v14 = v13;
            if ( si128.m128i_i64[0] == -1 && v13 == -1 || v5[41].m128i_i32[0] != v5[16].m128i_i32[2] )
            {
              v3 = 0;
              si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
              v5[41].m128i_i32[0] = v25;
              v5[41].m128i_i32[2] = v26;
              v5[41].m128i_i32[3] = v27;
              v5[41].m128i_i32[1] = v10;
              v15 = 0;
              v5[42].m128i_i32[0] = v18;
              v5[40] = v11;
              *(_DWORD *)(v6 + 2352) = -1;
              v20 = 0;
              ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920), v24);
              v16 = si128.m128i_i64[0];
              v14 = _mm_srli_si128(si128, 8).m128i_u64[0];
LABEL_13:
              *(_DWORD *)(v2 + 52) = v20;
              *(_DWORD *)(v2 + 48) = v15;
              *(__m128i *)(v2 + 28) = si128;
              *(_DWORD *)(a1 + 152) = v21;
              *(_DWORD *)(a1 + 156) = v22;
              if ( v16 == -1 && v14 == -1 )
                *(_DWORD *)(v2 + 4) = 6;
              goto LABEL_16;
            }
            v17 = v10;
            v15 = v5[41].m128i_i32[1];
            if ( (v19 | v15) == v19 && v15 != v19 )
            {
              v20 = v5[41].m128i_i32[2];
              v5[41].m128i_i32[0] = v25;
              v5[41].m128i_i32[2] = v26;
              v5[41].m128i_i32[3] = v27;
              v5[41].m128i_i32[1] = v17;
              v5[42].m128i_i32[0] = v18;
              v5[40] = v11;
              *(_DWORD *)(v6 + 2352) = -1;
              ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920), v24);
              v16 = v23;
              goto LABEL_13;
            }
            *(_DWORD *)(v6 + 2352) = -1;
            ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920), v24);
          }
LABEL_16:
          ExReleasePushLockExclusiveEx(v2 + 16, 0);
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140016df0  push    rbx
0x140016df2  push    rbp
0x140016df3  push    rsi
0x140016df4  push    rdi
0x140016df5  push    r14
0x140016df7  sub     rsp, 80h
0x140016dfe  mov     rax, [rcx+28h]
0x140016e02  mov     rbx, rcx
0x140016e05  mov     rbp, [rcx+30h]
0x140016e09  mov     esi, 0C0000016h
0x140016e0e  mov     rdx, [rcx+20h]
0x140016e12  mov     rdi, [rax+28h]
0x140016e16  movzx   eax, cs:dbgCacheShareRootHandle
0x140016e1d  mov     r14, [rdi+18h]
0x140016e21  test    al, al
0x140016e23  jz      short loc_140016E47
0x140016e25  mov     rax, [rdi+1A8h]
0x140016e2c  mov     rcx, [rax+58h]
0x140016e30  test    dword ptr [rcx+2CCh], 4000h
0x140016e3a  jnz     short loc_140016E47
0x140016e3c  mov     eax, [rbp+8]
0x140016e3f  test    al, al
0x140016e41  js      short loc_140016E47
0x140016e43  test    al, 8
0x140016e45  jnz     short loc_140016E58
0x140016e47  mov     eax, esi
0x140016e49  add     rsp, 80h
0x140016e50  pop     r14
0x140016e52  pop     rdi
0x140016e53  pop     rsi
0x140016e54  pop     rbp
0x140016e55  pop     rbx
0x140016e56  retn
0x140016e58  movzx   eax, word ptr [rdx+168h]
0x140016e5f  test    ax, ax
0x140016e62  jz      short loc_140016E77
0x140016e64  cmp     ax, 2
0x140016e68  jnz     short loc_140016E47
0x140016e6a  mov     rcx, [rdx+170h]
0x140016e71  cmp     word ptr [rcx], 5Ch ; '\'
0x140016e75  jnz     short loc_140016E47
0x140016e77  xor     edx, edx
0x140016e79  mov     [rsp+0A8h+var_40], r15
0x140016e7e  lea     rcx, [rbp+10h]
0x140016e82  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140016e89  nop     dword ptr [rax+rax+00h]
0x140016e8e  cmp     dword ptr [rbp+4], 0
0x140016e92  jnz     loc_140017029
0x140016e98  mov     eax, [rbp+2Ch]
0x140016e9b  lea     rcx, [r14+780h]; SpinLock
0x140016ea2  mov     [rsp+0A8h+arg_8], eax
0x140016ea9  mov     eax, [rbp+34h]
0x140016eac  mov     [rsp+0A8h+var_38], r13
0x140016eb1  mov     r13d, [rbp+30h]
0x140016eb5  mov     [rsp+0A8h+arg_10], eax
0x140016ebc  mov     eax, [rbx+98h]
0x140016ec2  movaps  [rsp+0A8h+var_58], xmm6
0x140016ec7  movaps  [rsp+0A8h+var_68], xmm7
0x140016ecc  movups  xmm7, xmmword ptr [rbp+1Ch]
0x140016ed0  mov     [rsp+0A8h+arg_18], eax
0x140016ed7  mov     eax, [rbx+9Ch]
0x140016edd  mov     [rsp+0A8h+var_88], eax
0x140016ee1  mov     [rsp+0A8h+var_30], r12
0x140016ee6  mov     [rsp+0A8h+var_84], r13d
0x140016eeb  call    cs:__imp_ExAcquireSpinLockExclusive
0x140016ef2  nop     dword ptr [rax+rax+00h]
0x140016ef7  mov     [rsp+0A8h+arg_0], al
0x140016efe  call    cs:__imp_PsGetCurrentThreadId
0x140016f05  nop     dword ptr [rax+rax+00h]
0x140016f0a  mov     [r14+930h], eax
0x140016f11  mov     eax, [rdi+29Ch]
0x140016f17  movups  xmm6, xmmword ptr [rdi+280h]
0x140016f1e  mov     [rsp+0A8h+var_80], eax
0x140016f22  mov     eax, [rdi+2A0h]
0x140016f28  movdqa  xmm0, xmm6
0x140016f2c  mov     [rsp+0A8h+var_7C], eax
0x140016f30  movq    rax, xmm6
0x140016f35  psrldq  xmm0, 8
0x140016f3a  mov     [rsp+0A8h+var_78], rax
0x140016f3f  movq    r12, xmm0
0x140016f44  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140016f48  jnz     loc_140017045
0x140016f4e  cmp     r12, rax
0x140016f51  jnz     loc_140017045
0x140016f57  mov     eax, [rsp+0A8h+arg_8]
0x140016f5e  lea     rcx, [r14+780h]; SpinLock
0x140016f65  movzx   edx, [rsp+0A8h+arg_0]; OldIrql
0x140016f6d  xor     esi, esi
0x140016f6f  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140016f77  mov     [rdi+290h], eax
0x140016f7d  mov     eax, [rsp+0A8h+arg_10]
0x140016f84  mov     [rdi+298h], eax
0x140016f8a  mov     eax, [rsp+0A8h+arg_18]
0x140016f91  mov     [rdi+29Ch], eax
0x140016f97  mov     eax, [rsp+0A8h+var_88]
0x140016f9b  mov     [rdi+294h], r13d
0x140016fa2  xor     r13d, r13d
0x140016fa5  mov     [rdi+2A0h], eax
0x140016fab  movups  xmmword ptr [rdi+280h], xmm7
0x140016fb2  mov     dword ptr [r14+930h], 0FFFFFFFFh
0x140016fbd  mov     [rsp+0A8h+var_84], esi
0x140016fc1  call    cs:__imp_ExReleaseSpinLockExclusive
0x140016fc8  nop     dword ptr [rax+rax+00h]
0x140016fcd  movdqa  xmm0, xmm6
0x140016fd1  movq    rax, xmm6
0x140016fd6  psrldq  xmm0, 8
0x140016fdb  movq    r12, xmm0
0x140016fe0  mov     ecx, [rsp+0A8h+var_84]
0x140016fe4  mov     [rbp+34h], ecx
0x140016fe7  mov     ecx, [rsp+0A8h+var_80]
0x140016feb  mov     [rbp+30h], r13d
0x140016fef  movups  xmmword ptr [rbp+1Ch], xmm6
0x140016ff3  mov     [rbx+98h], ecx
0x140016ff9  mov     ecx, [rsp+0A8h+var_7C]
0x140016ffd  mov     [rbx+9Ch], ecx
0x140017003  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140017007  jnz     short loc_140017015
0x140017009  cmp     r12, rax
0x14001700c  jnz     short loc_140017015
0x14001700e  mov     dword ptr [rbp+4], 6
0x140017015  mov     r12, [rsp+0A8h+var_30]
0x14001701a  mov     r13, [rsp+0A8h+var_38]
0x14001701f  movaps  xmm6, [rsp+0A8h+var_58]
0x140017024  movaps  xmm7, [rsp+0A8h+var_68]
0x140017029  xor     edx, edx
0x14001702b  lea     rcx, [rbp+10h]
0x14001702f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140017036  nop     dword ptr [rax+rax+00h]
0x14001703b  mov     r15, [rsp+0A8h+var_40]
0x140017040  jmp     loc_140016E47
0x140017045  mov     eax, [rdi+108h]
0x14001704b  cmp     [rdi+290h], eax
0x140017051  jnz     loc_140016F57
0x140017057  mov     ecx, [rsp+0A8h+var_84]
0x14001705b  mov     r13d, [rdi+294h]
0x140017062  mov     eax, r13d
0x140017065  or      eax, ecx
0x140017067  cmp     eax, ecx
0x140017069  jz      short loc_140017093
0x14001706b  movzx   edx, [rsp+0A8h+arg_0]; OldIrql
0x140017073  lea     rcx, [r14+780h]; SpinLock
0x14001707a  mov     dword ptr [r14+930h], 0FFFFFFFFh
0x140017085  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001708c  nop     dword ptr [rax+rax+00h]
0x140017091  jmp     short loc_140017015
0x140017093  cmp     r13d, ecx
0x140017096  jz      short loc_14001706B
0x140017098  jmp     loc_14003B66C
0x14003b66c  mov     eax, [rdi+298h]
0x14003b672  movzx   edx, [rsp+0A8h+arg_0]; OldIrql
0x14003b67a  mov     [rsp+0A8h+var_84], eax
0x14003b67e  mov     eax, [rsp+0A8h+arg_8]
0x14003b685  mov     [rdi+290h], eax
0x14003b68b  mov     eax, [rsp+0A8h+arg_10]
0x14003b692  mov     [rdi+298h], eax
0x14003b698  mov     eax, [rsp+0A8h+arg_18]
0x14003b69f  mov     [rdi+29Ch], eax
0x14003b6a5  mov     eax, [rsp+0A8h+var_88]
0x14003b6a9  mov     [rdi+294h], ecx
0x14003b6af  lea     rcx, [r14+780h]; SpinLock
0x14003b6b6  mov     [rdi+2A0h], eax
0x14003b6bc  movups  xmmword ptr [rdi+280h], xmm7
0x14003b6c3  mov     dword ptr [r14+930h], 0FFFFFFFFh
0x14003b6ce  call    cs:__imp_ExReleaseSpinLockExclusive
0x14003b6d5  nop     dword ptr [rax+rax+00h]
0x14003b6da  mov     rax, [rsp+0A8h+var_78]
0x14003b6df  jmp     loc_140016FE0
```
