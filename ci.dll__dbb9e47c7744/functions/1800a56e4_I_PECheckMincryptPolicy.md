# I_PECheckMincryptPolicy

- ea: `0x1800a56e4`
- end: `0x1800a59dd`
- name: `I_PECheckMincryptPolicy`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009a1d0`
- `0x1800a5320`

## callees

- `0x18000ce08`
- `0x180093528`
- `0x1800a56e4`
- `0x1800a59e4`
- `0x1800a5aa4`
- `0x1800a5ad8`
- `0x1800a5db0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a57dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a5928`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a57dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a5928`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5897`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5989`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5897`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5989`
- `ntoskrnl!RtlCompareMemory` at `0x1800a5854`
- `ntoskrnl!RtlCompareMemory` at `0x1800a5854`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a57f2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a593d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a57f2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a593d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a588b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a597d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a588b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a597d`

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
  if ( _InterlockedCompareExchange64(&qword_180049410, 0, 0) )
  {
    *(_OWORD *)v5 = 0;
    v5[4] = 0;
    MinCryptHashMemory(32772, 1, v11, (_DWORD)v5, (__int64)&v22);
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
    if ( (unsigned int)MFIsHashInGRL(qword_180049410, v5, 3) )
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
      if ( _InterlockedCompareExchange64(&qword_180049410, 0, 0) )
      {
        while ( 1 )
        {
          *(_OWORD *)v5 = 0;
          v5[4] = 0;
          MinCryptHashMemory(32772, 1, *(_DWORD *)(*(_QWORD *)(a1 + 16) + 8LL) + 16 * v14, (_DWORD)v5, (__int64)&v22);
          KeEnterCriticalRegion();
          ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
          v15 = qword_180049410;
          if ( qword_180049410 )
          {
            v16 = *(_DWORD **)qword_180049410;
            if ( *(_QWORD *)qword_180049410 )
            {
              if ( *(_QWORD *)(qword_180049410 + 8) )
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
0x1800a56e4  mov     rax, rsp
0x1800a56e7  mov     [rax+20h], rbx
0x1800a56eb  mov     [rax+18h], r8
0x1800a56ef  mov     [rax+10h], edx
0x1800a56f2  push    rbp
0x1800a56f3  push    rsi
0x1800a56f4  push    rdi
0x1800a56f5  push    r12
0x1800a56f7  push    r13
0x1800a56f9  push    r14
0x1800a56fb  push    r15
0x1800a56fd  sub     rsp, 50h
0x1800a5701  movups  xmm0, xmmword ptr cs:a1361413111053; "1.3.6.1.4.1.311.10.5.3"
0x1800a5708  mov     r14, r8
0x1800a570b  mov     rdi, r9
0x1800a570e  movsd   xmm1, qword ptr cs:a1361413111053+0Fh; ".10.5.3"
0x1800a5716  mov     r8d, edx
0x1800a5719  mov     dword ptr [r9], 0
0x1800a5720  mov     rsi, rcx
0x1800a5723  cmp     dword ptr [rcx], 0
0x1800a5726  movups  xmmword ptr [rax-58h], xmm0
0x1800a572a  movsd   qword ptr [rax-49h], xmm1
0x1800a572f  jz      loc_1800A58E1
0x1800a5735  cmp     qword ptr [rcx+10h], 0
0x1800a573a  jz      loc_1800A58E1
0x1800a5740  test    dword ptr [rcx+8], 0FFFF0000h
0x1800a5747  jnz     loc_1800A58E1
0x1800a574d  call    MincryptGetRootKeyFromPolicy
0x1800a5752  mov     rbp, rax
0x1800a5755  test    rax, rax
0x1800a5758  jz      loc_1800A58E1
0x1800a575e  mov     r15, [rsp+88h+arg_20]
0x1800a5766  xor     ebx, ebx
0x1800a5768  test    r8d, r8d
0x1800a576b  mov     rdx, r15
0x1800a576e  mov     rcx, rax
0x1800a5771  setnz   r8b
0x1800a5775  call    MFKeyIsTrustedRootKey
0x1800a577a  test    al, al
0x1800a577c  jz      loc_1800A58E8
0x1800a5782  mov     eax, [r15]
0x1800a5785  test    al, 2
0x1800a5787  jnz     loc_1800A59B0
0x1800a578d  xor     ebp, ebp
0x1800a578f  xor     ecx, ecx
0x1800a5791  xor     eax, eax
0x1800a5793  lock cmpxchg cs:qword_180049410, rcx
0x1800a579c  jz      loc_1800A59D4
0x1800a57a2  xor     eax, eax
0x1800a57a4  mov     r8d, ebp
0x1800a57a7  xorps   xmm0, xmm0
0x1800a57aa  shl     r8, 4
0x1800a57ae  movups  xmmword ptr [r14], xmm0
0x1800a57b2  mov     [r14+10h], eax
0x1800a57b6  mov     r9, r14
0x1800a57b9  mov     rax, [rsi+10h]
0x1800a57bd  mov     edx, 1
0x1800a57c2  mov     ecx, 8004h
0x1800a57c7  add     r8, [rax+8]
0x1800a57cb  lea     rax, [rsp+88h+arg_0]
0x1800a57d3  mov     [rsp+88h+var_68], rax
0x1800a57d8  call    MinCryptHashMemory
0x1800a57dd  call    cs:__imp_KeEnterCriticalRegion
0x1800a57e4  nop     dword ptr [rax+rax+00h]
0x1800a57e9  mov     dl, 1; Wait
0x1800a57eb  lea     rcx, g_GRLContextLock; Resource
0x1800a57f2  call    cs:__imp_ExAcquireResourceSharedLite
0x1800a57f9  nop     dword ptr [rax+rax+00h]
0x1800a57fe  mov     r12, cs:qword_180049410
0x1800a5805  test    r12, r12
0x1800a5808  jz      short loc_1800A5884
0x1800a580a  mov     rax, [r12]
0x1800a580e  test    rax, rax
0x1800a5811  jz      short loc_1800A5884
0x1800a5813  cmp     qword ptr [r12+8], 0
0x1800a5819  jz      short loc_1800A5884
0x1800a581b  mov     r13d, [rax+2Ch]
0x1800a581f  add     r13d, [rax+28h]
0x1800a5823  mov     eax, [rax+30h]
0x1800a5826  xor     r14d, r14d
0x1800a5829  mov     [rsp+88h+arg_0], eax
0x1800a5830  cmp     r14d, eax
0x1800a5833  jnb     short loc_1800A587C
0x1800a5835  mov     rcx, [rsp+88h+Source1]; Source1
0x1800a583d  lea     eax, [r14+r13]
0x1800a5841  lea     rdx, [rax+rax*4]
0x1800a5845  mov     r8d, 14h; Length
0x1800a584b  mov     rax, [r12+8]
0x1800a5850  lea     rdx, [rax+rdx*4]; Source2
0x1800a5854  call    cs:__imp_RtlCompareMemory
0x1800a585b  nop     dword ptr [rax+rax+00h]
0x1800a5860  cmp     rax, 14h
0x1800a5864  jz      short loc_1800A5872
0x1800a5866  mov     eax, [rsp+88h+arg_0]
0x1800a586d  inc     r14d
0x1800a5870  jmp     short loc_1800A5830
0x1800a5872  bts     ebx, 0Fh
0x1800a5876  mov     dword ptr [rdi], 1
0x1800a587c  mov     r14, [rsp+88h+Source1]
0x1800a5884  lea     rcx, g_GRLContextLock; Resource
0x1800a588b  call    cs:__imp_ExReleaseResourceLite
0x1800a5892  nop     dword ptr [rax+rax+00h]
0x1800a5897  call    cs:__imp_KeLeaveCriticalRegion
0x1800a589e  nop     dword ptr [rax+rax+00h]
0x1800a58a3  cmp     dword ptr [rdi], 0
0x1800a58a6  jnz     short loc_1800A58C6
0x1800a58a8  mov     rax, [rsi+10h]
0x1800a58ac  inc     ebp
0x1800a58ae  cmp     ebp, [rax+10h]
0x1800a58b1  jnz     loc_1800A57A2
0x1800a58b7  mov     edx, [r15]
0x1800a58ba  mov     ecx, [rsp+88h+arg_8]
0x1800a58c1  call    I_PESetTrustState
0x1800a58c6  mov     eax, ebx
0x1800a58c8  mov     rbx, [rsp+88h+arg_18]
0x1800a58d0  add     rsp, 50h
0x1800a58d4  pop     r15
0x1800a58d6  pop     r14
0x1800a58d8  pop     r13
0x1800a58da  pop     r12
0x1800a58dc  pop     rdi
0x1800a58dd  pop     rsi
0x1800a58de  pop     rbp
0x1800a58df  retn
0x1800a58e1  mov     eax, 10000000h
0x1800a58e6  jmp     short loc_1800A58C8
0x1800a58e8  xor     ecx, ecx
0x1800a58ea  xor     eax, eax
0x1800a58ec  lock cmpxchg cs:qword_180049410, rcx
0x1800a58f5  jz      loc_1800A5997
0x1800a58fb  xor     eax, eax
0x1800a58fd  lea     edx, [rcx+1]
0x1800a5900  xorps   xmm0, xmm0
0x1800a5903  mov     r9, r14
0x1800a5906  movups  xmmword ptr [r14], xmm0
0x1800a590a  mov     [r14+10h], eax
0x1800a590e  mov     r8, rbp
0x1800a5911  lea     rax, [rsp+88h+arg_0]
0x1800a5919  mov     ecx, 8004h
0x1800a591e  mov     [rsp+88h+var_68], rax
0x1800a5923  call    MinCryptHashMemory
0x1800a5928  call    cs:__imp_KeEnterCriticalRegion
0x1800a592f  nop     dword ptr [rax+rax+00h]
0x1800a5934  mov     dl, 1; Wait
0x1800a5936  lea     rcx, g_GRLContextLock; Resource
0x1800a593d  call    cs:__imp_ExAcquireResourceSharedLite
0x1800a5944  nop     dword ptr [rax+rax+00h]
0x1800a5949  mov     rcx, cs:qword_180049410
0x1800a5950  mov     r8d, 3
0x1800a5956  mov     rdx, r14
0x1800a5959  call    MFIsHashInGRL
0x1800a595e  test    eax, eax
0x1800a5960  jnz     short loc_1800A596F
0x1800a5962  mov     ebx, 10000h
0x1800a5967  mov     dword ptr [rdi], 1
0x1800a596d  jmp     short loc_1800A5976
0x1800a596f  mov     dword ptr [r15], 2
0x1800a5976  lea     rcx, g_GRLContextLock; Resource
0x1800a597d  call    cs:__imp_ExReleaseResourceLite
0x1800a5984  nop     dword ptr [rax+rax+00h]
0x1800a5989  call    cs:__imp_KeLeaveCriticalRegion
0x1800a5990  nop     dword ptr [rax+rax+00h]
0x1800a5995  jmp     short loc_1800A59A2
0x1800a5997  mov     ebx, 11000h
0x1800a599c  mov     dword ptr [rdi], 1
0x1800a59a2  cmp     dword ptr [rdi], 0
0x1800a59a5  jz      loc_1800A5782
0x1800a59ab  jmp     loc_1800A58C6
0x1800a59b0  lea     rdx, [rsp+88h+var_58]
0x1800a59b5  mov     rcx, rsi
0x1800a59b8  call    MincryptIsEKUInPolicy
0x1800a59bd  test    al, al
0x1800a59bf  jnz     loc_1800A578D
0x1800a59c5  bts     ebx, 0Eh
0x1800a59c9  mov     dword ptr [rdi], 1
0x1800a59cf  jmp     loc_1800A58C6
0x1800a59d4  bts     ebx, 0Ch
0x1800a59d8  jmp     loc_1800A58B7
```
