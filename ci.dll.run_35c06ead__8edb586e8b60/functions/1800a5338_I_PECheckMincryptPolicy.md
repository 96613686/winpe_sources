# I_PECheckMincryptPolicy

- ea: `0x1800a5338`
- end: `0x1800a5631`
- name: `I_PECheckMincryptPolicy`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009f510`
- `0x1800a4f74`

## callees

- `0x18000ce18`
- `0x180098e88`
- `0x1800a5338`
- `0x1800a5638`
- `0x1800a56f8`
- `0x1800a572c`
- `0x1800a5a04`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a5431`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a557c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a5431`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a557c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a54eb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a55dd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a54eb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a55dd`
- `ntoskrnl!RtlCompareMemory` at `0x1800a54a8`
- `ntoskrnl!RtlCompareMemory` at `0x1800a54a8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a5446`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a5591`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a5446`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a5591`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a54df`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a55d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a54df`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a55d1`

## pseudocode

```c
__int64 __fastcall I_PECheckMincryptPolicy(__int64 a1, __int64 a2, void *a3, _DWORD *a4, _DWORD *a5)
{
  _DWORD *v5; // r14
  bool v8; // zf
  __int64 RootKeyFromPolicy; // rax
  __int64 v10; // r8
  int v11; // ebp
  _DWORD *v12; // r15
  unsigned int v13; // ebx
  int v14; // ebp
  __int64 v15; // r12
  _DWORD *v16; // rax
  int v17; // r13d
  unsigned int v18; // eax
  unsigned int v19; // r14d
  char v21[88]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v22; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v23; // [rsp+98h] [rbp+10h]
  void *Source1; // [rsp+A0h] [rbp+18h]

  Source1 = a3;
  v23 = a2;
  v5 = a3;
  *a4 = 0;
  v8 = *(_DWORD *)a1 == 0;
  strcpy(v21, "1.3.6.1.4.1.311.10.5.3");
  if ( v8 )
    return 0x10000000;
  if ( !*(_QWORD *)(a1 + 16) )
    return 0x10000000;
  if ( (*(_DWORD *)(a1 + 8) & 0xFFFF0000) != 0 )
    return 0x10000000;
  RootKeyFromPolicy = MincryptGetRootKeyFromPolicy(a1, a2, (unsigned int)a2);
  v11 = RootKeyFromPolicy;
  if ( !RootKeyFromPolicy )
    return 0x10000000;
  v12 = a5;
  v13 = 0;
  LOBYTE(v10) = (_DWORD)v10 != 0;
  if ( (unsigned __int8)MFKeyIsTrustedRootKey(RootKeyFromPolicy, a5, v10) )
    goto LABEL_35;
  if ( _InterlockedCompareExchange64(&qword_180049428, 0, 0) )
  {
    *(_OWORD *)v5 = 0;
    v5[4] = 0;
    MinCryptHashMemory(32772, 1, v11, (_DWORD)v5, (__int64)&v22);
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
    if ( (unsigned int)MFIsHashInGRL(qword_180049428, v5, 3) )
    {
      *v12 = 2;
    }
    else
    {
      v13 = 0x10000;
      *a4 = 1;
    }
    ExReleaseResourceLite(&g_GRLContextLock);
    KeLeaveCriticalRegion();
  }
  else
  {
    v13 = 69632;
    *a4 = 1;
  }
  if ( !*a4 )
  {
LABEL_35:
    if ( (*v12 & 2) == 0 || (unsigned __int8)MincryptIsEKUInPolicy(a1, v21) )
    {
      v14 = 0;
      if ( _InterlockedCompareExchange64(&qword_180049428, 0, 0) )
      {
        while ( 1 )
        {
          *(_OWORD *)v5 = 0;
          v5[4] = 0;
          MinCryptHashMemory(32772, 1, *(_DWORD *)(*(_QWORD *)(a1 + 16) + 8LL) + 16 * v14, (_DWORD)v5, (__int64)&v22);
          KeEnterCriticalRegion();
          ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
          v15 = qword_180049428;
          if ( qword_180049428 )
          {
            v16 = *(_DWORD **)qword_180049428;
            if ( *(_QWORD *)qword_180049428 )
            {
              if ( *(_QWORD *)(qword_180049428 + 8) )
              {
                v17 = v16[10] + v16[11];
                v18 = v16[12];
                v19 = 0;
                v22 = v18;
                while ( v19 < v18 )
                {
                  if ( RtlCompareMemory(Source1, (const void *)(*(_QWORD *)(v15 + 8) + 20LL * (v19 + v17)), 0x14u) == 20 )
                  {
                    v13 |= 0x8000u;
                    *a4 = 1;
                    break;
                  }
                  v18 = v22;
                  ++v19;
                }
                v5 = Source1;
              }
            }
          }
          ExReleaseResourceLite(&g_GRLContextLock);
          KeLeaveCriticalRegion();
          if ( *a4 )
            break;
          if ( ++v14 == *(_DWORD *)(*(_QWORD *)(a1 + 16) + 16LL) )
            goto LABEL_19;
        }
      }
      else
      {
        v13 |= 0x1000u;
LABEL_19:
        I_PESetTrustState(v23, (unsigned int)*v12);
      }
    }
    else
    {
      v13 |= 0x4000u;
      *a4 = 1;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1800a5338  mov     rax, rsp
0x1800a533b  mov     [rax+20h], rbx
0x1800a533f  mov     [rax+18h], r8
0x1800a5343  mov     [rax+10h], edx
0x1800a5346  push    rbp
0x1800a5347  push    rsi
0x1800a5348  push    rdi
0x1800a5349  push    r12
0x1800a534b  push    r13
0x1800a534d  push    r14
0x1800a534f  push    r15
0x1800a5351  sub     rsp, 50h
0x1800a5355  movups  xmm0, xmmword ptr cs:a1361413111053; "1.3.6.1.4.1.311.10.5.3"
0x1800a535c  mov     r14, r8
0x1800a535f  mov     rdi, r9
0x1800a5362  movsd   xmm1, qword ptr cs:a1361413111053+0Fh; ".10.5.3"
0x1800a536a  mov     r8d, edx
0x1800a536d  mov     dword ptr [r9], 0
0x1800a5374  mov     rsi, rcx
0x1800a5377  cmp     dword ptr [rcx], 0
0x1800a537a  movups  xmmword ptr [rax-58h], xmm0
0x1800a537e  movsd   qword ptr [rax-49h], xmm1
0x1800a5383  jz      loc_1800A5535
0x1800a5389  cmp     qword ptr [rcx+10h], 0
0x1800a538e  jz      loc_1800A5535
0x1800a5394  test    dword ptr [rcx+8], 0FFFF0000h
0x1800a539b  jnz     loc_1800A5535
0x1800a53a1  call    MincryptGetRootKeyFromPolicy
0x1800a53a6  mov     rbp, rax
0x1800a53a9  test    rax, rax
0x1800a53ac  jz      loc_1800A5535
0x1800a53b2  mov     r15, [rsp+88h+arg_20]
0x1800a53ba  xor     ebx, ebx
0x1800a53bc  test    r8d, r8d
0x1800a53bf  mov     rdx, r15
0x1800a53c2  mov     rcx, rax
0x1800a53c5  setnz   r8b
0x1800a53c9  call    MFKeyIsTrustedRootKey
0x1800a53ce  test    al, al
0x1800a53d0  jz      loc_1800A553C
0x1800a53d6  mov     eax, [r15]
0x1800a53d9  test    al, 2
0x1800a53db  jnz     loc_1800A5604
0x1800a53e1  xor     ebp, ebp
0x1800a53e3  xor     ecx, ecx
0x1800a53e5  xor     eax, eax
0x1800a53e7  lock cmpxchg cs:qword_180049428, rcx
0x1800a53f0  jz      loc_1800A5628
0x1800a53f6  xor     eax, eax
0x1800a53f8  mov     r8d, ebp
0x1800a53fb  xorps   xmm0, xmm0
0x1800a53fe  shl     r8, 4
0x1800a5402  movups  xmmword ptr [r14], xmm0
0x1800a5406  mov     [r14+10h], eax
0x1800a540a  mov     r9, r14
0x1800a540d  mov     rax, [rsi+10h]
0x1800a5411  mov     edx, 1
0x1800a5416  mov     ecx, 8004h
0x1800a541b  add     r8, [rax+8]
0x1800a541f  lea     rax, [rsp+88h+arg_0]
0x1800a5427  mov     [rsp+88h+var_68], rax
0x1800a542c  call    MinCryptHashMemory
0x1800a5431  call    cs:__imp_KeEnterCriticalRegion
0x1800a5438  nop     dword ptr [rax+rax+00h]
0x1800a543d  mov     dl, 1; Wait
0x1800a543f  lea     rcx, g_GRLContextLock; Resource
0x1800a5446  call    cs:__imp_ExAcquireResourceSharedLite
0x1800a544d  nop     dword ptr [rax+rax+00h]
0x1800a5452  mov     r12, cs:qword_180049428
0x1800a5459  test    r12, r12
0x1800a545c  jz      short loc_1800A54D8
0x1800a545e  mov     rax, [r12]
0x1800a5462  test    rax, rax
0x1800a5465  jz      short loc_1800A54D8
0x1800a5467  cmp     qword ptr [r12+8], 0
0x1800a546d  jz      short loc_1800A54D8
0x1800a546f  mov     r13d, [rax+2Ch]
0x1800a5473  add     r13d, [rax+28h]
0x1800a5477  mov     eax, [rax+30h]
0x1800a547a  xor     r14d, r14d
0x1800a547d  mov     [rsp+88h+arg_0], eax
0x1800a5484  cmp     r14d, eax
0x1800a5487  jnb     short loc_1800A54D0
0x1800a5489  mov     rcx, [rsp+88h+Source1]; Source1
0x1800a5491  lea     eax, [r14+r13]
0x1800a5495  lea     rdx, [rax+rax*4]
0x1800a5499  mov     r8d, 14h; Length
0x1800a549f  mov     rax, [r12+8]
0x1800a54a4  lea     rdx, [rax+rdx*4]; Source2
0x1800a54a8  call    cs:__imp_RtlCompareMemory
0x1800a54af  nop     dword ptr [rax+rax+00h]
0x1800a54b4  cmp     rax, 14h
0x1800a54b8  jz      short loc_1800A54C6
0x1800a54ba  mov     eax, [rsp+88h+arg_0]
0x1800a54c1  inc     r14d
0x1800a54c4  jmp     short loc_1800A5484
0x1800a54c6  bts     ebx, 0Fh
0x1800a54ca  mov     dword ptr [rdi], 1
0x1800a54d0  mov     r14, [rsp+88h+Source1]
0x1800a54d8  lea     rcx, g_GRLContextLock; Resource
0x1800a54df  call    cs:__imp_ExReleaseResourceLite
0x1800a54e6  nop     dword ptr [rax+rax+00h]
0x1800a54eb  call    cs:__imp_KeLeaveCriticalRegion
0x1800a54f2  nop     dword ptr [rax+rax+00h]
0x1800a54f7  cmp     dword ptr [rdi], 0
0x1800a54fa  jnz     short loc_1800A551A
0x1800a54fc  mov     rax, [rsi+10h]
0x1800a5500  inc     ebp
0x1800a5502  cmp     ebp, [rax+10h]
0x1800a5505  jnz     loc_1800A53F6
0x1800a550b  mov     edx, [r15]
0x1800a550e  mov     ecx, [rsp+88h+arg_8]
0x1800a5515  call    I_PESetTrustState
0x1800a551a  mov     eax, ebx
0x1800a551c  mov     rbx, [rsp+88h+arg_18]
0x1800a5524  add     rsp, 50h
0x1800a5528  pop     r15
0x1800a552a  pop     r14
0x1800a552c  pop     r13
0x1800a552e  pop     r12
0x1800a5530  pop     rdi
0x1800a5531  pop     rsi
0x1800a5532  pop     rbp
0x1800a5533  retn
0x1800a5535  mov     eax, 10000000h
0x1800a553a  jmp     short loc_1800A551C
0x1800a553c  xor     ecx, ecx
0x1800a553e  xor     eax, eax
0x1800a5540  lock cmpxchg cs:qword_180049428, rcx
0x1800a5549  jz      loc_1800A55EB
0x1800a554f  xor     eax, eax
0x1800a5551  lea     edx, [rcx+1]
0x1800a5554  xorps   xmm0, xmm0
0x1800a5557  mov     r9, r14
0x1800a555a  movups  xmmword ptr [r14], xmm0
0x1800a555e  mov     [r14+10h], eax
0x1800a5562  mov     r8, rbp
0x1800a5565  lea     rax, [rsp+88h+arg_0]
0x1800a556d  mov     ecx, 8004h
0x1800a5572  mov     [rsp+88h+var_68], rax
0x1800a5577  call    MinCryptHashMemory
0x1800a557c  call    cs:__imp_KeEnterCriticalRegion
0x1800a5583  nop     dword ptr [rax+rax+00h]
0x1800a5588  mov     dl, 1; Wait
0x1800a558a  lea     rcx, g_GRLContextLock; Resource
0x1800a5591  call    cs:__imp_ExAcquireResourceSharedLite
0x1800a5598  nop     dword ptr [rax+rax+00h]
0x1800a559d  mov     rcx, cs:qword_180049428
0x1800a55a4  mov     r8d, 3
0x1800a55aa  mov     rdx, r14
0x1800a55ad  call    MFIsHashInGRL
0x1800a55b2  test    eax, eax
0x1800a55b4  jnz     short loc_1800A55C3
0x1800a55b6  mov     ebx, 10000h
0x1800a55bb  mov     dword ptr [rdi], 1
0x1800a55c1  jmp     short loc_1800A55CA
0x1800a55c3  mov     dword ptr [r15], 2
0x1800a55ca  lea     rcx, g_GRLContextLock; Resource
0x1800a55d1  call    cs:__imp_ExReleaseResourceLite
0x1800a55d8  nop     dword ptr [rax+rax+00h]
0x1800a55dd  call    cs:__imp_KeLeaveCriticalRegion
0x1800a55e4  nop     dword ptr [rax+rax+00h]
0x1800a55e9  jmp     short loc_1800A55F6
0x1800a55eb  mov     ebx, 11000h
0x1800a55f0  mov     dword ptr [rdi], 1
0x1800a55f6  cmp     dword ptr [rdi], 0
0x1800a55f9  jz      loc_1800A53D6
0x1800a55ff  jmp     loc_1800A551A
0x1800a5604  lea     rdx, [rsp+88h+var_58]
0x1800a5609  mov     rcx, rsi
0x1800a560c  call    MincryptIsEKUInPolicy
0x1800a5611  test    al, al
0x1800a5613  jnz     loc_1800A53E1
0x1800a5619  bts     ebx, 0Eh
0x1800a561d  mov     dword ptr [rdi], 1
0x1800a5623  jmp     loc_1800A551A
0x1800a5628  bts     ebx, 0Ch
0x1800a562c  jmp     loc_1800A550B
```
