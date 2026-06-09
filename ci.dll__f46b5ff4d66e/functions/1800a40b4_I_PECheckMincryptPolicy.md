# I_PECheckMincryptPolicy

- ea: `0x1800a40b4`
- end: `0x1800a43ad`
- name: `I_PECheckMincryptPolicy`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180098ba0`
- `0x1800a3cf0`

## callees

- `0x18000ce08`
- `0x180091ef8`
- `0x1800a40b4`
- `0x1800a43b4`
- `0x1800a4474`
- `0x1800a44a8`
- `0x1800a4780`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a41ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a42f8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a41ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a42f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a4267`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a4359`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a4267`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a4359`
- `ntoskrnl!RtlCompareMemory` at `0x1800a4224`
- `ntoskrnl!RtlCompareMemory` at `0x1800a4224`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a41c2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a430d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a41c2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a430d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a425b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a434d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a425b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a434d`

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
  if ( _InterlockedCompareExchange64(&qword_180048410, 0, 0) )
  {
    *(_OWORD *)v5 = 0;
    v5[4] = 0;
    MinCryptHashMemory(32772, 1, v11, (_DWORD)v5, (__int64)&v22);
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
    if ( (unsigned int)MFIsHashInGRL(qword_180048410, v5, 3) )
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
      if ( _InterlockedCompareExchange64(&qword_180048410, 0, 0) )
      {
        while ( 1 )
        {
          *(_OWORD *)v5 = 0;
          v5[4] = 0;
          MinCryptHashMemory(32772, 1, *(_DWORD *)(*(_QWORD *)(a1 + 16) + 8LL) + 16 * v14, (_DWORD)v5, (__int64)&v22);
          KeEnterCriticalRegion();
          ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
          v15 = qword_180048410;
          if ( qword_180048410 )
          {
            v16 = *(_DWORD **)qword_180048410;
            if ( *(_QWORD *)qword_180048410 )
            {
              if ( *(_QWORD *)(qword_180048410 + 8) )
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
0x1800a40b4  mov     rax, rsp
0x1800a40b7  mov     [rax+20h], rbx
0x1800a40bb  mov     [rax+18h], r8
0x1800a40bf  mov     [rax+10h], edx
0x1800a40c2  push    rbp
0x1800a40c3  push    rsi
0x1800a40c4  push    rdi
0x1800a40c5  push    r12
0x1800a40c7  push    r13
0x1800a40c9  push    r14
0x1800a40cb  push    r15
0x1800a40cd  sub     rsp, 50h
0x1800a40d1  movups  xmm0, xmmword ptr cs:a1361413111053; "1.3.6.1.4.1.311.10.5.3"
0x1800a40d8  mov     r14, r8
0x1800a40db  mov     rdi, r9
0x1800a40de  movsd   xmm1, qword ptr cs:a1361413111053+0Fh; ".10.5.3"
0x1800a40e6  mov     r8d, edx
0x1800a40e9  mov     dword ptr [r9], 0
0x1800a40f0  mov     rsi, rcx
0x1800a40f3  cmp     dword ptr [rcx], 0
0x1800a40f6  movups  xmmword ptr [rax-58h], xmm0
0x1800a40fa  movsd   qword ptr [rax-49h], xmm1
0x1800a40ff  jz      loc_1800A42B1
0x1800a4105  cmp     qword ptr [rcx+10h], 0
0x1800a410a  jz      loc_1800A42B1
0x1800a4110  test    dword ptr [rcx+8], 0FFFF0000h
0x1800a4117  jnz     loc_1800A42B1
0x1800a411d  call    MincryptGetRootKeyFromPolicy
0x1800a4122  mov     rbp, rax
0x1800a4125  test    rax, rax
0x1800a4128  jz      loc_1800A42B1
0x1800a412e  mov     r15, [rsp+88h+arg_20]
0x1800a4136  xor     ebx, ebx
0x1800a4138  test    r8d, r8d
0x1800a413b  mov     rdx, r15
0x1800a413e  mov     rcx, rax
0x1800a4141  setnz   r8b
0x1800a4145  call    MFKeyIsTrustedRootKey
0x1800a414a  test    al, al
0x1800a414c  jz      loc_1800A42B8
0x1800a4152  mov     eax, [r15]
0x1800a4155  test    al, 2
0x1800a4157  jnz     loc_1800A4380
0x1800a415d  xor     ebp, ebp
0x1800a415f  xor     ecx, ecx
0x1800a4161  xor     eax, eax
0x1800a4163  lock cmpxchg cs:qword_180048410, rcx
0x1800a416c  jz      loc_1800A43A4
0x1800a4172  xor     eax, eax
0x1800a4174  mov     r8d, ebp
0x1800a4177  xorps   xmm0, xmm0
0x1800a417a  shl     r8, 4
0x1800a417e  movups  xmmword ptr [r14], xmm0
0x1800a4182  mov     [r14+10h], eax
0x1800a4186  mov     r9, r14
0x1800a4189  mov     rax, [rsi+10h]
0x1800a418d  mov     edx, 1
0x1800a4192  mov     ecx, 8004h
0x1800a4197  add     r8, [rax+8]
0x1800a419b  lea     rax, [rsp+88h+arg_0]
0x1800a41a3  mov     [rsp+88h+var_68], rax
0x1800a41a8  call    MinCryptHashMemory
0x1800a41ad  call    cs:__imp_KeEnterCriticalRegion
0x1800a41b4  nop     dword ptr [rax+rax+00h]
0x1800a41b9  mov     dl, 1; Wait
0x1800a41bb  lea     rcx, g_GRLContextLock; Resource
0x1800a41c2  call    cs:__imp_ExAcquireResourceSharedLite
0x1800a41c9  nop     dword ptr [rax+rax+00h]
0x1800a41ce  mov     r12, cs:qword_180048410
0x1800a41d5  test    r12, r12
0x1800a41d8  jz      short loc_1800A4254
0x1800a41da  mov     rax, [r12]
0x1800a41de  test    rax, rax
0x1800a41e1  jz      short loc_1800A4254
0x1800a41e3  cmp     qword ptr [r12+8], 0
0x1800a41e9  jz      short loc_1800A4254
0x1800a41eb  mov     r13d, [rax+2Ch]
0x1800a41ef  add     r13d, [rax+28h]
0x1800a41f3  mov     eax, [rax+30h]
0x1800a41f6  xor     r14d, r14d
0x1800a41f9  mov     [rsp+88h+arg_0], eax
0x1800a4200  cmp     r14d, eax
0x1800a4203  jnb     short loc_1800A424C
0x1800a4205  mov     rcx, [rsp+88h+Source1]; Source1
0x1800a420d  lea     eax, [r14+r13]
0x1800a4211  lea     rdx, [rax+rax*4]
0x1800a4215  mov     r8d, 14h; Length
0x1800a421b  mov     rax, [r12+8]
0x1800a4220  lea     rdx, [rax+rdx*4]; Source2
0x1800a4224  call    cs:__imp_RtlCompareMemory
0x1800a422b  nop     dword ptr [rax+rax+00h]
0x1800a4230  cmp     rax, 14h
0x1800a4234  jz      short loc_1800A4242
0x1800a4236  mov     eax, [rsp+88h+arg_0]
0x1800a423d  inc     r14d
0x1800a4240  jmp     short loc_1800A4200
0x1800a4242  bts     ebx, 0Fh
0x1800a4246  mov     dword ptr [rdi], 1
0x1800a424c  mov     r14, [rsp+88h+Source1]
0x1800a4254  lea     rcx, g_GRLContextLock; Resource
0x1800a425b  call    cs:__imp_ExReleaseResourceLite
0x1800a4262  nop     dword ptr [rax+rax+00h]
0x1800a4267  call    cs:__imp_KeLeaveCriticalRegion
0x1800a426e  nop     dword ptr [rax+rax+00h]
0x1800a4273  cmp     dword ptr [rdi], 0
0x1800a4276  jnz     short loc_1800A4296
0x1800a4278  mov     rax, [rsi+10h]
0x1800a427c  inc     ebp
0x1800a427e  cmp     ebp, [rax+10h]
0x1800a4281  jnz     loc_1800A4172
0x1800a4287  mov     edx, [r15]
0x1800a428a  mov     ecx, [rsp+88h+arg_8]
0x1800a4291  call    I_PESetTrustState
0x1800a4296  mov     eax, ebx
0x1800a4298  mov     rbx, [rsp+88h+arg_18]
0x1800a42a0  add     rsp, 50h
0x1800a42a4  pop     r15
0x1800a42a6  pop     r14
0x1800a42a8  pop     r13
0x1800a42aa  pop     r12
0x1800a42ac  pop     rdi
0x1800a42ad  pop     rsi
0x1800a42ae  pop     rbp
0x1800a42af  retn
0x1800a42b1  mov     eax, 10000000h
0x1800a42b6  jmp     short loc_1800A4298
0x1800a42b8  xor     ecx, ecx
0x1800a42ba  xor     eax, eax
0x1800a42bc  lock cmpxchg cs:qword_180048410, rcx
0x1800a42c5  jz      loc_1800A4367
0x1800a42cb  xor     eax, eax
0x1800a42cd  lea     edx, [rcx+1]
0x1800a42d0  xorps   xmm0, xmm0
0x1800a42d3  mov     r9, r14
0x1800a42d6  movups  xmmword ptr [r14], xmm0
0x1800a42da  mov     [r14+10h], eax
0x1800a42de  mov     r8, rbp
0x1800a42e1  lea     rax, [rsp+88h+arg_0]
0x1800a42e9  mov     ecx, 8004h
0x1800a42ee  mov     [rsp+88h+var_68], rax
0x1800a42f3  call    MinCryptHashMemory
0x1800a42f8  call    cs:__imp_KeEnterCriticalRegion
0x1800a42ff  nop     dword ptr [rax+rax+00h]
0x1800a4304  mov     dl, 1; Wait
0x1800a4306  lea     rcx, g_GRLContextLock; Resource
0x1800a430d  call    cs:__imp_ExAcquireResourceSharedLite
0x1800a4314  nop     dword ptr [rax+rax+00h]
0x1800a4319  mov     rcx, cs:qword_180048410
0x1800a4320  mov     r8d, 3
0x1800a4326  mov     rdx, r14
0x1800a4329  call    MFIsHashInGRL
0x1800a432e  test    eax, eax
0x1800a4330  jnz     short loc_1800A433F
0x1800a4332  mov     ebx, 10000h
0x1800a4337  mov     dword ptr [rdi], 1
0x1800a433d  jmp     short loc_1800A4346
0x1800a433f  mov     dword ptr [r15], 2
0x1800a4346  lea     rcx, g_GRLContextLock; Resource
0x1800a434d  call    cs:__imp_ExReleaseResourceLite
0x1800a4354  nop     dword ptr [rax+rax+00h]
0x1800a4359  call    cs:__imp_KeLeaveCriticalRegion
0x1800a4360  nop     dword ptr [rax+rax+00h]
0x1800a4365  jmp     short loc_1800A4372
0x1800a4367  mov     ebx, 11000h
0x1800a436c  mov     dword ptr [rdi], 1
0x1800a4372  cmp     dword ptr [rdi], 0
0x1800a4375  jz      loc_1800A4152
0x1800a437b  jmp     loc_1800A4296
0x1800a4380  lea     rdx, [rsp+88h+var_58]
0x1800a4385  mov     rcx, rsi
0x1800a4388  call    MincryptIsEKUInPolicy
0x1800a438d  test    al, al
0x1800a438f  jnz     loc_1800A415D
0x1800a4395  bts     ebx, 0Eh
0x1800a4399  mov     dword ptr [rdi], 1
0x1800a439f  jmp     loc_1800A4296
0x1800a43a4  bts     ebx, 0Ch
0x1800a43a8  jmp     loc_1800A4287
```
