# LdrGetProcedureAddressForCaller

- ea: `0x18006f310`
- end: `0x18006fb1b`
- name: `LdrGetProcedureAddressForCaller`
- size: `2059`
- prototype: ``
- caller_count: `7`
- callee_count: `24`
- tags: `loader_planting, installer_update`

## callers

- `0x18001d4b0`
- `0x18002630c`
- `0x18004d990`
- `0x18006d950`
- `0x1800c0e50`
- `0x1800c1c4c`
- `0x1800dbe88`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x1800254d0`
- `0x1800259ec`
- `0x1800376a0`
- `0x18006f310`
- `0x18006fb30`
- `0x18006fd70`
- `0x18006ffa0`
- `0x180070490`
- `0x1800707b0`
- `0x180070980`
- `0x1800709e0`
- `0x1800836d0`
- `0x1800857e4`
- `0x18008588c`
- `0x1800e634c`
- `0x1800e9aa8`
- `0x1800eae70`
- `0x180137068`
- `0x180137090`
- `0x180162810`
- `0x180164280`
- `0x18016f020`

## pseudocode

```c
__int64 __fastcall LdrGetProcedureAddressForCaller(
        unsigned __int64 a1,
        const void **a2,
        unsigned int a3,
        _QWORD *a4,
        char a5,
        unsigned __int64 a6)
{
  __int64 v7; // r13
  bool v11; // zf
  __int64 v12; // r14
  int v13; // r15d
  size_t v14; // rbx
  unsigned int v15; // ecx
  _BYTE *v16; // r12
  __int64 *v18; // rsi
  __int64 *v19; // rax
  __int64 *v20; // rsi
  char *v21; // rdi
  signed int v22; // ebx
  int v23; // ebx
  int v24; // r12d
  __int64 v25; // rdx
  unsigned __int64 v26; // rax
  __int64 v27; // rcx
  _QWORD *v28; // r15
  __int64 v29; // rdx
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // rsi
  unsigned __int64 v32; // rcx
  __int64 v33; // rcx
  unsigned int v34; // ebp
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rcx
  __int64 v37; // rcx
  char v38; // [rsp+30h] [rbp-118h]
  char v39[7]; // [rsp+31h] [rbp-117h] BYREF
  _BYTE *Heap_0; // [rsp+38h] [rbp-110h]
  int v41; // [rsp+40h] [rbp-108h]
  __int64 v42; // [rsp+48h] [rbp-100h] BYREF
  __int64 *i; // [rsp+50h] [rbp-F8h]
  int v44; // [rsp+58h] [rbp-F0h]
  unsigned int v45; // [rsp+5Ch] [rbp-ECh]
  int v46; // [rsp+60h] [rbp-E8h] BYREF
  __int64 v47; // [rsp+68h] [rbp-E0h] BYREF
  _QWORD *v48; // [rsp+78h] [rbp-D0h]
  _BYTE v49[128]; // [rsp+80h] [rbp-C8h] BYREF
  int v50; // [rsp+170h] [rbp+28h]

  v7 = 0;
  v45 = a3;
  v46 = 0;
  v47 = 0;
  v48 = a4;
  ExecuteHotpatchTestRuntimeFunction();
  if ( (unsigned int)GetHotpatchTestRuntimeFunctionState() && !a1 && !a2 && !a3 && !a6 && a4 )
  {
    *a4 = 4025479151LL;
    return 3221225485LL;
  }
  v11 = (a5 & 1) == 0;
  v50 = a5 & 1;
  v41 = 9;
  v12 = 0;
  v42 = 0;
  v38 = 0;
  if ( v11 || (v13 = 6, (void *)qword_1801C4930 != NtCurrentTeb()->ClientId.UniqueThread) )
    v13 = 9;
  if ( a2 )
  {
    v14 = *(unsigned __int16 *)a2;
    v15 = v14 + 1;
    if ( *((unsigned __int16 *)a2 + 1) < (unsigned int)(v14 + 1) || (Heap_0 = a2[1], Heap_0[v14]) )
    {
      if ( v15 <= 0x80 )
      {
        v16 = v49;
        Heap_0 = v49;
      }
      else
      {
        Heap_0 = (_BYTE *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, (unsigned int)(NtdllBaseTag + 1572864), v15);
        v16 = Heap_0;
        if ( !Heap_0 )
          return 3221225626LL;
        v38 = 1;
      }
      memmove(v16, a2[1], v14);
      v16[v14] = 0;
    }
  }
  else
  {
    Heap_0 = 0;
  }
  v18 = 0;
  for ( i = 0; ; i = v18 )
  {
    RtlEnterCriticalSection(LdrpEnclaveListLock);
    v19 = (__int64 *)LdrpEnclaveList;
    if ( (__int64 *)LdrpEnclaveList != &LdrpEnclaveList )
    {
      while ( 1 )
      {
        v18 = v19;
        i = v19;
        if ( a1 == v19[9] )
          break;
        v19 = (__int64 *)*v19;
        if ( v19 == &LdrpEnclaveList )
          goto LABEL_41;
      }
    }
    if ( !v18 )
    {
LABEL_41:
      RtlLeaveCriticalSection(LdrpEnclaveListLock);
LABEL_42:
      i = 0;
      v23 = 0;
      v41 = 0;
      v24 = 1;
      v44 = 1;
      if ( !a1 )
        goto LABEL_106;
      while ( 2 )
      {
        if ( a1 == LdrpSystemDllBase )
        {
          v7 = LdrpNtDllDataTableEntry;
          v23 = *(_DWORD *)(*(_QWORD *)(LdrpNtDllDataTableEntry + 152) + 56LL);
          v41 = v23;
          goto LABEL_100;
        }
        RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
        v26 = LdrpModuleBaseAddressIndex;
        if ( (qword_1801CA470 & 1) != 0 )
        {
          if ( !LdrpModuleBaseAddressIndex )
            goto LABEL_99;
          v26 = (unsigned __int64)&LdrpModuleBaseAddressIndex ^ LdrpModuleBaseAddressIndex;
        }
        v25 = qword_1801CA470 & 1;
        if ( !v26 )
          goto LABEL_99;
        while ( a1 > *(_QWORD *)(v26 - 152) )
        {
          v36 = *(_QWORD *)(v26 + 8);
          if ( (qword_1801CA470 & 1) == 0 || !v36 )
            goto LABEL_97;
          v26 ^= v36;
LABEL_98:
          if ( !v26 )
            goto LABEL_99;
        }
        if ( a1 >= *(_QWORD *)(v26 - 152) )
        {
          v27 = *(_QWORD *)(v26 - 48);
          v7 = v26 - 200;
          if ( *(_DWORD *)(v27 + 24) != -1 && (*(_DWORD *)(*(_QWORD *)v27 - 56LL) & 0x20) == 0 )
            _InterlockedIncrement((volatile signed __int32 *)(v7 + 276));
          v23 = *(_DWORD *)(*(_QWORD *)(v7 + 152) + 56LL);
          v41 = v23;
LABEL_99:
          RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v25);
LABEL_100:
          if ( v7 )
          {
            if ( (NtCurrentTeb()->SameTebFlags & 0x1000) != 0 || v23 >= v13 )
            {
              v28 = (_QWORD *)v7;
              goto LABEL_61;
            }
            LdrpDereferenceModule(v7);
            if ( v23 >= 0 )
            {
              LdrpDrainWorkQueue(0);
              LdrpDropLastInProgressCount();
              v7 = 0;
              continue;
            }
            v22 = -1073741811;
LABEL_24:
            v21 = Heap_0;
            goto LABEL_25;
          }
LABEL_106:
          v22 = -1073741515;
          goto LABEL_24;
        }
        break;
      }
      v36 = *(_QWORD *)v26;
      if ( (qword_1801CA470 & 1) != 0 && v36 )
      {
        v26 ^= v36;
        goto LABEL_98;
      }
LABEL_97:
      v26 = v36;
      goto LABEL_98;
    }
    _InterlockedIncrement((volatile signed __int32 *)v18 + 15);
    RtlLeaveCriticalSection(LdrpEnclaveListLock);
    RtlEnterCriticalSection(v18 + 2);
    if ( v18[9] )
      break;
    RtlLeaveCriticalSection(v18 + 2);
    LdrpDereferenceEnclave(v18);
  }
  if ( *((_DWORD *)v18 + 14) != 16 || *((_DWORD *)v18 + 16) != 2 )
  {
    RtlLeaveCriticalSection(v18 + 2);
    LdrpDereferenceEnclave(v18);
    goto LABEL_42;
  }
  RtlLeaveCriticalSection(v18 + 2);
  v7 = v18[14];
  v28 = (_QWORD *)v7;
  if ( !v7 )
  {
    v22 = 0;
    goto LABEL_56;
  }
  v24 = 3;
  v44 = 3;
LABEL_61:
  RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
  v30 = LdrpModuleBaseAddressIndex;
  if ( (qword_1801CA470 & 1) != 0 )
  {
    if ( LdrpModuleBaseAddressIndex )
    {
      v30 = (unsigned __int64)&LdrpModuleBaseAddressIndex ^ LdrpModuleBaseAddressIndex;
      goto LABEL_62;
    }
LABEL_75:
    RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v29);
LABEL_76:
    v34 = v45;
    v22 = LdrpResolveProcedureAddress(0, v7, (_DWORD)Heap_0, v45, v24, (__int64)&v42);
    goto LABEL_77;
  }
LABEL_62:
  v31 = 0;
  v29 = qword_1801CA470 & 1;
  if ( !v30 )
    goto LABEL_66;
  while ( 2 )
  {
    v32 = *(_QWORD *)(v30 - 152);
    if ( a6 < v32 )
    {
      v35 = *(_QWORD *)v30;
      if ( (qword_1801CA470 & 1) != 0 && v35 )
      {
        v30 ^= v35;
LABEL_74:
        if ( !v30 )
          goto LABEL_75;
        continue;
      }
LABEL_73:
      v30 = v35;
      goto LABEL_74;
    }
    break;
  }
  if ( a6 >= v32 + *(unsigned int *)(v30 - 136) )
  {
    v35 = *(_QWORD *)(v30 + 8);
    if ( (qword_1801CA470 & 1) != 0 && v35 )
    {
      v30 ^= v35;
      goto LABEL_74;
    }
    goto LABEL_73;
  }
  v33 = *(_QWORD *)(v30 - 48);
  v31 = v30 - 200;
  if ( *(_DWORD *)(v33 + 24) != -1 && (*(_DWORD *)(*(_QWORD *)v33 - 56LL) & 0x20) == 0 )
    _InterlockedIncrement((volatile signed __int32 *)(v31 + 276));
LABEL_66:
  RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v29);
  if ( !v30 )
    goto LABEL_76;
  v34 = v45;
  v22 = LdrpResolveProcedureAddress(v31, (_DWORD)v28, (_DWORD)Heap_0, v45, v44, (__int64)&v42);
  if ( v31 )
    LdrpDereferenceModule(v31);
LABEL_77:
  if ( v22 < 0 )
  {
    v12 = v42;
    goto LABEL_19;
  }
  if ( v41 != 7
    || v50
    || (NtCurrentTeb()->SameTebFlags & 0x1000) == 0
    || (void *)qword_1801C4930 == NtCurrentTeb()->ClientId.UniqueThread
    || (v37 = v28[19], v39[0] = 0, v22 = LdrpInitializeGraphRecurse(v37, 0, v39), v22 >= 0) )
  {
    v20 = i;
    if ( i )
      goto LABEL_83;
    if ( AvrfpAPILookupCallbacksEnabled )
      AVrfCallAPILookupCallback(a6, v28[6], v42, 0, (__int64)&v42);
    if ( g_ShimsEnabled )
    {
      v12 = v42;
      v47 = 0;
      ((void (__fastcall *)(__int64 *, _QWORD *, __int64, _QWORD, unsigned __int64))(__ROR8__(
                                                                                       g_pfnSE_GetProcAddressForCaller,
                                                                                       64 - (MEMORY[0x7FFE0330] & 0x3Fu))
                                                                                   ^ MEMORY[0x7FFE0330]))(
        &v47,
        v28,
        v42,
        0,
        a6);
      if ( v47 )
        v12 = v47;
    }
    else
    {
LABEL_83:
      v12 = v42;
    }
    goto LABEL_20;
  }
  v12 = 0;
LABEL_19:
  v20 = i;
  if ( v22 != -1073741515 )
  {
LABEL_20:
    if ( v22 != -1073741502 )
      goto LABEL_21;
  }
  v22 = -1073741702;
LABEL_21:
  if ( !v20 )
  {
    LdrpDereferenceModule(v28);
    goto LABEL_23;
  }
  LdrpDereferenceEnclave(v20);
  if ( v22 >= 0 )
  {
LABEL_56:
    v12 += v28[23] - v28[6];
    goto LABEL_24;
  }
LABEL_23:
  if ( v22 != -1073741702 )
    goto LABEL_24;
  v21 = Heap_0;
  if ( !Heap_0 )
    v21 = (char *)v34;
  v22 = (Heap_0 != 0) - 1073741512;
  LdrpReportError(0, v21, v22);
LABEL_25:
  if ( v38 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v21);
  if ( !UseWOW64
    && v22 >= 0
    && qword_1801E3518
    && (dword_1801E34FC & 1) == 0
    && (BYTE5(qword_1801E3500) & 3) == 3
    && (unsigned int)RtlValidateUserCallTarget(v12, &v46) != 1
    && (v46 & 0x10) != 0 )
  {
    if ( (unsigned int)LdrControlFlowGuardEnforced() )
    {
      if ( (unsigned __int8)RtlGuardIsExportSuppressedAddress(v12) != 1
        || (v22 = RtlpGuardGrantSuppressedCallAccess(v12, 4), v22 < 0) )
      {
        __fastfail(0x2Eu);
      }
    }
    else
    {
      v22 = 0;
    }
  }
  *v48 = v12;
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18006f310  push    rbx
0x18006f312  push    rbp
0x18006f313  push    rsi
0x18006f314  push    rdi
0x18006f315  push    r13
0x18006f317  push    r14
0x18006f319  sub     rsp, 118h
0x18006f320  mov     rax, cs:__security_cookie
0x18006f327  xor     rax, rsp
0x18006f32a  mov     [rsp+148h+var_48], rax
0x18006f332  mov     rdi, [rsp+148h+arg_28]
0x18006f33a  mov     ebx, r8d
0x18006f33d  xor     r13d, r13d
0x18006f340  mov     [rsp+148h+var_EC], ebx
0x18006f344  mov     [rsp+148h+var_E8], r13d
0x18006f349  mov     r14, r9
0x18006f34c  mov     [rsp+148h+var_E0], r13
0x18006f351  mov     rsi, rdx
0x18006f354  mov     [rsp+148h+var_D0], r9
0x18006f359  mov     rbp, rcx
0x18006f35c  call    ExecuteHotpatchTestRuntimeFunction
0x18006f361  call    GetHotpatchTestRuntimeFunctionState
0x18006f366  test    eax, eax
0x18006f368  jnz     loc_18006FAA0
0x18006f36e  and     [rsp+148h+arg_20], 1
0x18006f376  mov     edx, 9
0x18006f37b  mov     [rsp+148h+var_108], edx
0x18006f37f  mov     r14, r13
0x18006f382  mov     [rsp+148h+var_38], r15
0x18006f38a  mov     [rsp+148h+var_100], r13
0x18006f38f  mov     [rsp+148h+var_118], r13b
0x18006f394  jnz     loc_18006F483
0x18006f39a  mov     r15d, edx
0x18006f39d  mov     [rsp+148h+arg_0], r12
0x18006f3a5  test    rsi, rsi
0x18006f3a8  jz      short loc_18006F40F
0x18006f3aa  movzx   ebx, word ptr [rsi]
0x18006f3ad  movzx   eax, word ptr [rsi+2]
0x18006f3b1  lea     ecx, [rbx+1]
0x18006f3b4  cmp     eax, ecx
0x18006f3b6  jb      short loc_18006F3C7
0x18006f3b8  mov     r12, [rsi+8]
0x18006f3bc  mov     [rsp+148h+var_110], r12
0x18006f3c1  cmp     [rbx+r12], r13b
0x18006f3c5  jz      short loc_18006F414
0x18006f3c7  cmp     ecx, 80h
0x18006f3cd  jbe     loc_18006FADE
0x18006f3d3  mov     edx, cs:NtdllBaseTag
0x18006f3d9  mov     r8d, ecx
0x18006f3dc  add     edx, 180000h
0x18006f3e2  mov     rcx, gs:60h
0x18006f3eb  mov     rcx, [rcx+30h]
0x18006f3ef  call    RtlAllocateHeap_0
0x18006f3f4  mov     [rsp+148h+var_110], rax
0x18006f3f9  mov     r12, rax
0x18006f3fc  test    rax, rax
0x18006f3ff  jnz     loc_18006FB0D
0x18006f405  mov     eax, 0C000009Ah
0x18006f40a  jmp     loc_18006F521
0x18006f40f  mov     [rsp+148h+var_110], r13
0x18006f414  mov     rsi, r13
0x18006f417  mov     [rsp+148h+var_F8], r13
0x18006f41c  lea     r12, LdrpEnclaveList
0x18006f423  lea     rcx, LdrpEnclaveListLock
0x18006f42a  call    RtlEnterCriticalSection
0x18006f42f  mov     rax, cs:LdrpEnclaveList
0x18006f436  cmp     rax, r12
0x18006f439  jnz     loc_18006F5D0
0x18006f43f  lea     rcx, LdrpEnclaveListLock
0x18006f446  test    rsi, rsi
0x18006f449  jz      loc_18006F5F1
0x18006f44f  lock inc dword ptr [rsi+3Ch]
0x18006f453  call    RtlLeaveCriticalSection
0x18006f458  lea     rcx, [rsi+10h]
0x18006f45c  call    RtlEnterCriticalSection
0x18006f461  cmp     [rsi+48h], r13
0x18006f465  jnz     loc_18006F6F4
0x18006f46b  lea     rcx, [rsi+10h]
0x18006f46f  call    RtlLeaveCriticalSection
0x18006f474  mov     rcx, rsi
0x18006f477  call    LdrpDereferenceEnclave
0x18006f47c  mov     [rsp+148h+var_F8], rsi
0x18006f481  jmp     short loc_18006F423
0x18006f483  mov     rax, gs:30h
0x18006f48c  mov     r15d, 6
0x18006f492  mov     rcx, [rax+48h]
0x18006f496  cmp     cs:qword_1801C4930, rcx
0x18006f49d  jz      loc_18006F39D
0x18006f4a3  jmp     loc_18006F39A
0x18006f4a8  mov     r14, [rsp+148h+var_100]
0x18006f4ad  mov     rsi, [rsp+148h+var_F8]
0x18006f4b2  cmp     ebx, 0C0000135h
0x18006f4b8  jz      loc_18006FA96
0x18006f4be  cmp     ebx, 0C0000142h
0x18006f4c4  jz      loc_18006FA96
0x18006f4ca  test    rsi, rsi
0x18006f4cd  jnz     loc_18006F6CD
0x18006f4d3  mov     rcx, r15
0x18006f4d6  call    LdrpDereferenceModule
0x18006f4db  cmp     ebx, 0C000007Ah
0x18006f4e1  jz      loc_18006F69E
0x18006f4e7  mov     rdi, [rsp+148h+var_110]
0x18006f4ec  cmp     [rsp+148h+var_118], 0
0x18006f4f1  jz      short loc_18006F50A
0x18006f4f3  mov     rcx, gs:60h
0x18006f4fc  mov     r8, rdi
0x18006f4ff  xor     edx, edx
0x18006f501  mov     rcx, [rcx+30h]
0x18006f505  call    RtlFreeHeap_0
0x18006f50a  cmp     cs:UseWOW64, 0
0x18006f511  jnz     short loc_18006F517
0x18006f513  test    ebx, ebx
0x18006f515  jns     short loc_18006F552
0x18006f517  mov     rax, [rsp+148h+var_D0]
0x18006f51c  mov     [rax], r14
0x18006f51f  mov     eax, ebx
0x18006f521  mov     r12, [rsp+148h+arg_0]
0x18006f529  mov     r15, [rsp+148h+var_38]
0x18006f531  mov     rcx, [rsp+148h+var_48]
0x18006f539  xor     rcx, rsp; StackCookie
0x18006f53c  call    __security_check_cookie
0x18006f541  add     rsp, 118h
0x18006f548  pop     r14
0x18006f54a  pop     r13
0x18006f54c  pop     rdi
0x18006f54d  pop     rsi
0x18006f54e  pop     rbp
0x18006f54f  pop     rbx
0x18006f550  retn
0x18006f552  cmp     cs:qword_1801E3518, 0
0x18006f55a  jz      short loc_18006F517
0x18006f55c  test    byte ptr cs:dword_1801E34FC, 1
0x18006f563  jnz     short loc_18006F517
0x18006f565  mov     rax, cs:qword_1801E3500
0x18006f56c  shr     rax, 28h
0x18006f570  and     al, 3
0x18006f572  cmp     al, 3
0x18006f574  jnz     short loc_18006F517
0x18006f576  lea     rdx, [rsp+148h+var_E8]
0x18006f57b  mov     rcx, r14
0x18006f57e  call    RtlValidateUserCallTarget
0x18006f583  cmp     eax, 1
0x18006f586  jz      short loc_18006F517
0x18006f588  test    byte ptr [rsp+148h+var_E8], 10h
0x18006f58d  jz      short loc_18006F517
0x18006f58f  call    LdrControlFlowGuardEnforced
0x18006f594  test    eax, eax
0x18006f596  jz      loc_18006FB14
0x18006f59c  mov     rcx, r14
0x18006f59f  call    RtlGuardIsExportSuppressedAddress
0x18006f5a4  cmp     al, 1
0x18006f5a6  jnz     short loc_18006F5BF
0x18006f5a8  mov     edx, 4
0x18006f5ad  mov     rcx, r14
0x18006f5b0  call    RtlpGuardGrantSuppressedCallAccess
0x18006f5b5  mov     ebx, eax
0x18006f5b7  test    eax, eax
0x18006f5b9  jns     loc_18006F517
0x18006f5bf  mov     ecx, 2Eh ; '.'
0x18006f5c4  int     29h; Win8: RtlFailFast(ecx)
0x18006f5d0  mov     rsi, rax
0x18006f5d3  mov     [rsp+148h+var_F8], rax
0x18006f5d8  cmp     rbp, [rax+48h]
0x18006f5dc  jz      loc_18006F43F
0x18006f5e2  mov     rax, [rax]
0x18006f5e5  cmp     rax, r12
0x18006f5e8  jnz     short loc_18006F5D0
0x18006f5ea  lea     rcx, LdrpEnclaveListLock
0x18006f5f1  call    RtlLeaveCriticalSection
0x18006f5f6  mov     [rsp+148h+var_F8], r13
0x18006f5fb  mov     ebx, r13d
0x18006f5fe  mov     [rsp+148h+var_108], ebx
0x18006f602  mov     r12d, 1
0x18006f608  mov     [rsp+148h+var_F0], r12d
0x18006f60d  test    rbp, rbp
0x18006f610  jz      loc_18006F998
0x18006f616  lea     rsi, LdrpModuleBaseAddressIndex
0x18006f61d  cmp     rbp, cs:LdrpSystemDllBase
0x18006f624  mov     ecx, 1000h
0x18006f629  jz      loc_18006F9A2
0x18006f62f  lea     rcx, LdrpModuleDatatableLock
0x18006f636  call    RtlAcquireSRWLockShared
0x18006f63b  mov     rcx, cs:qword_1801CA470
0x18006f642  mov     rax, cs:LdrpModuleBaseAddressIndex
0x18006f649  test    r12b, cl
0x18006f64c  jnz     loc_18006F9D5
0x18006f652  movzx   edx, cl
0x18006f655  and     edx, r12d
0x18006f658  test    rax, rax
0x18006f65b  jz      loc_18006F959
0x18006f661  cmp     rbp, [rax-98h]
0x18006f668  ja      loc_18006F934
0x18006f66e  jb      loc_18006F946
0x18006f674  mov     rcx, [rax-30h]
0x18006f678  lea     r13, [rax-0C8h]
0x18006f67f  mov     eax, [rcx+18h]
0x18006f682  cmp     eax, 0FFFFFFFFh
0x18006f685  jnz     loc_18006F9B9
0x18006f68b  mov     rax, [r13+98h]
0x18006f692  mov     ebx, [rax+38h]
0x18006f695  mov     [rsp+148h+var_108], ebx
0x18006f699  jmp     loc_18006F959
0x18006f69e  mov     rdi, [rsp+148h+var_110]
0x18006f6a3  mov     rax, rdi
0x18006f6a6  test    rdi, rdi
0x18006f6a9  jnz     short loc_18006F6AD
0x18006f6ab  mov     edi, ebp
0x18006f6ad  xor     ebx, ebx
0x18006f6af  mov     rdx, rdi
0x18006f6b2  test    rax, rax
0x18006f6b5  setnz   bl
0x18006f6b8  xor     ecx, ecx
0x18006f6ba  add     ebx, 0C0000138h
0x18006f6c0  mov     r8d, ebx
0x18006f6c3  call    LdrpReportError
0x18006f6c8  jmp     loc_18006F4EC
0x18006f6cd  mov     rcx, rsi
0x18006f6d0  call    LdrpDereferenceEnclave
0x18006f6d5  test    ebx, ebx
0x18006f6d7  js      loc_18006F4DB
0x18006f6dd  jmp     short loc_18006F6E1
0x18006f6df  xor     ebx, ebx
0x18006f6e1  mov     rax, [r15+0B8h]
0x18006f6e8  sub     rax, [r15+30h]
0x18006f6ec  add     r14, rax
0x18006f6ef  jmp     loc_18006F4E7
0x18006f6f4  cmp     dword ptr [rsi+38h], 10h
0x18006f6f8  jnz     loc_18006F91E
0x18006f6fe  cmp     dword ptr [rsi+40h], 2
0x18006f702  jnz     loc_18006F91E
0x18006f708  lea     rcx, [rsi+10h]
0x18006f70c  call    RtlLeaveCriticalSection
0x18006f711  mov     r13, [rsi+70h]
0x18006f715  mov     r15, r13
0x18006f718  test    r13, r13
0x18006f71b  jz      short loc_18006F6DF
0x18006f71d  mov     r12d, 3
0x18006f723  lea     rsi, LdrpModuleBaseAddressIndex
0x18006f72a  mov     [rsp+148h+var_F0], r12d
0x18006f72f  lea     rcx, LdrpModuleDatatableLock
0x18006f736  mov     r14d, 1000h
0x18006f73c  call    RtlAcquireSRWLockShared
0x18006f741  mov     rax, cs:qword_1801CA470
0x18006f748  mov     rbx, cs:LdrpModuleBaseAddressIndex
0x18006f74f  test    al, 1
0x18006f751  jnz     loc_18006F90D
0x18006f757  movzx   edx, al
0x18006f75a  xor     esi, esi
0x18006f75c  and     edx, 1
0x18006f75f  test    rbx, rbx
0x18006f762  jz      short loc_18006F7A5
0x18006f764  nop     dword ptr [rax+00h]
0x18006f768  nop     dword ptr [rax+rax+00000000h]
0x18006f770  mov     rcx, [rbx-98h]
0x18006f777  cmp     rdi, rcx
0x18006f77a  jb      loc_18006F802
0x18006f780  mov     eax, [rbx-88h]
0x18006f786  add     rax, rcx
0x18006f789  cmp     rdi, rax
0x18006f78c  jnb     short loc_18006F7F0
0x18006f78e  mov     rcx, [rbx-30h]
0x18006f792  lea     rsi, [rbx-0C8h]
0x18006f799  mov     eax, [rcx+18h]
0x18006f79c  cmp     eax, 0FFFFFFFFh
0x18006f79f  jnz     loc_18006F896
0x18006f7a5  lea     rcx, LdrpModuleDatatableLock
0x18006f7ac  call    RtlReleaseSRWLockShared
0x18006f7b1  test    rbx, rbx
0x18006f7b4  jz      short loc_18006F821
0x18006f7b6  mov     ebp, [rsp+148h+var_EC]
0x18006f7ba  lea     rax, [rsp+148h+var_100]
0x18006f7bf  mov     r8, [rsp+148h+var_110]
0x18006f7c4  mov     r9d, ebp
0x18006f7c7  mov     [rsp+148h+var_120], rax
0x18006f7cc  mov     rdx, r15
0x18006f7cf  mov     eax, [rsp+148h+var_F0]
0x18006f7d3  mov     rcx, rsi
0x18006f7d6  mov     dword ptr [rsp+148h+var_128], eax
0x18006f7da  call    LdrpResolveProcedureAddress
0x18006f7df  mov     ebx, eax
0x18006f7e1  test    rsi, rsi
0x18006f7e4  jz      short loc_18006F848
0x18006f7e6  mov     rcx, rsi
0x18006f7e9  call    LdrpDereferenceModule
0x18006f7ee  jmp     short loc_18006F848
0x18006f7f0  mov     rax, [rbx+8]
0x18006f7f4  test    edx, edx
0x18006f7f6  jz      short loc_18006F809
0x18006f7f8  test    rax, rax
0x18006f7fb  jz      short loc_18006F809
0x18006f7fd  xor     rbx, rax
0x18006f800  jmp     short loc_18006F80C
0x18006f802  mov     rax, [rbx]
0x18006f805  test    edx, edx
0x18006f807  jnz     short loc_18006F885
0x18006f809  mov     rbx, rax
0x18006f80c  test    rbx, rbx
0x18006f80f  jnz     loc_18006F770
0x18006f815  lea     rcx, LdrpModuleDatatableLock
0x18006f81c  call    RtlReleaseSRWLockShared
  ... truncated ...
```
