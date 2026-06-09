# LdrGetProcedureAddressForCaller

- ea: `0x180052930`
- end: `0x18005313b`
- name: `LdrGetProcedureAddressForCaller`
- size: `2059`
- prototype: ``
- caller_count: `7`
- callee_count: `24`
- tags: `loader_planting, installer_update`

## callers

- `0x18001d4b0`
- `0x18002631c`
- `0x1800400b0`
- `0x180050f70`
- `0x1800bcb70`
- `0x1800bd96c`
- `0x1800db408`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x1800254e0`
- `0x1800259fc`
- `0x180052930`
- `0x180053150`
- `0x180053390`
- `0x1800535c0`
- `0x180053ab0`
- `0x180053dd0`
- `0x180053fa0`
- `0x180054000`
- `0x180066cf0`
- `0x180068e04`
- `0x180068eac`
- `0x1800d4320`
- `0x1800e5fcc`
- `0x1800e9448`
- `0x1800ea810`
- `0x180136578`
- `0x1801365a0`
- `0x180162000`
- `0x180163a80`
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
  if ( v11 || (v13 = 6, (void *)qword_1801C4900 != NtCurrentTeb()->ClientId.UniqueThread) )
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
        RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
        v26 = LdrpModuleBaseAddressIndex;
        if ( (qword_1801CA478 & 1) != 0 )
        {
          if ( !LdrpModuleBaseAddressIndex )
            goto LABEL_99;
          v26 = (unsigned __int64)&LdrpModuleBaseAddressIndex ^ LdrpModuleBaseAddressIndex;
        }
        v25 = qword_1801CA478 & 1;
        if ( !v26 )
          goto LABEL_99;
        while ( a1 > *(_QWORD *)(v26 - 152) )
        {
          v36 = *(_QWORD *)(v26 + 8);
          if ( (qword_1801CA478 & 1) == 0 || !v36 )
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
          RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v25);
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
      if ( (qword_1801CA478 & 1) != 0 && v36 )
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
  RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
  v30 = LdrpModuleBaseAddressIndex;
  if ( (qword_1801CA478 & 1) != 0 )
  {
    if ( LdrpModuleBaseAddressIndex )
    {
      v30 = (unsigned __int64)&LdrpModuleBaseAddressIndex ^ LdrpModuleBaseAddressIndex;
      goto LABEL_62;
    }
LABEL_75:
    RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v29);
LABEL_76:
    v34 = v45;
    v22 = LdrpResolveProcedureAddress(0, v7, (_DWORD)Heap_0, v45, v24, (__int64)&v42);
    goto LABEL_77;
  }
LABEL_62:
  v31 = 0;
  v29 = qword_1801CA478 & 1;
  if ( !v30 )
    goto LABEL_66;
  while ( 2 )
  {
    v32 = *(_QWORD *)(v30 - 152);
    if ( a6 < v32 )
    {
      v35 = *(_QWORD *)v30;
      if ( (qword_1801CA478 & 1) != 0 && v35 )
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
    if ( (qword_1801CA478 & 1) != 0 && v35 )
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
  RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v29);
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
    || (void *)qword_1801C4900 == NtCurrentTeb()->ClientId.UniqueThread
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
0x180052930  push    rbx
0x180052932  push    rbp
0x180052933  push    rsi
0x180052934  push    rdi
0x180052935  push    r13
0x180052937  push    r14
0x180052939  sub     rsp, 118h
0x180052940  mov     rax, cs:__security_cookie
0x180052947  xor     rax, rsp
0x18005294a  mov     [rsp+148h+var_48], rax
0x180052952  mov     rdi, [rsp+148h+arg_28]
0x18005295a  mov     ebx, r8d
0x18005295d  xor     r13d, r13d
0x180052960  mov     [rsp+148h+var_EC], ebx
0x180052964  mov     [rsp+148h+var_E8], r13d
0x180052969  mov     r14, r9
0x18005296c  mov     [rsp+148h+var_E0], r13
0x180052971  mov     rsi, rdx
0x180052974  mov     [rsp+148h+var_D0], r9
0x180052979  mov     rbp, rcx
0x18005297c  call    ExecuteHotpatchTestRuntimeFunction
0x180052981  call    GetHotpatchTestRuntimeFunctionState
0x180052986  test    eax, eax
0x180052988  jnz     loc_1800530C0
0x18005298e  and     [rsp+148h+arg_20], 1
0x180052996  mov     edx, 9
0x18005299b  mov     [rsp+148h+var_108], edx
0x18005299f  mov     r14, r13
0x1800529a2  mov     [rsp+148h+var_38], r15
0x1800529aa  mov     [rsp+148h+var_100], r13
0x1800529af  mov     [rsp+148h+var_118], r13b
0x1800529b4  jnz     loc_180052AA3
0x1800529ba  mov     r15d, edx
0x1800529bd  mov     [rsp+148h+arg_0], r12
0x1800529c5  test    rsi, rsi
0x1800529c8  jz      short loc_180052A2F
0x1800529ca  movzx   ebx, word ptr [rsi]
0x1800529cd  movzx   eax, word ptr [rsi+2]
0x1800529d1  lea     ecx, [rbx+1]
0x1800529d4  cmp     eax, ecx
0x1800529d6  jb      short loc_1800529E7
0x1800529d8  mov     r12, [rsi+8]
0x1800529dc  mov     [rsp+148h+var_110], r12
0x1800529e1  cmp     [rbx+r12], r13b
0x1800529e5  jz      short loc_180052A34
0x1800529e7  cmp     ecx, 80h
0x1800529ed  jbe     loc_1800530FE
0x1800529f3  mov     edx, cs:NtdllBaseTag
0x1800529f9  mov     r8d, ecx
0x1800529fc  add     edx, 180000h
0x180052a02  mov     rcx, gs:60h
0x180052a0b  mov     rcx, [rcx+30h]
0x180052a0f  call    RtlAllocateHeap_0
0x180052a14  mov     [rsp+148h+var_110], rax
0x180052a19  mov     r12, rax
0x180052a1c  test    rax, rax
0x180052a1f  jnz     loc_18005312D
0x180052a25  mov     eax, 0C000009Ah
0x180052a2a  jmp     loc_180052B41
0x180052a2f  mov     [rsp+148h+var_110], r13
0x180052a34  mov     rsi, r13
0x180052a37  mov     [rsp+148h+var_F8], r13
0x180052a3c  lea     r12, LdrpEnclaveList
0x180052a43  lea     rcx, LdrpEnclaveListLock
0x180052a4a  call    RtlEnterCriticalSection
0x180052a4f  mov     rax, cs:LdrpEnclaveList
0x180052a56  cmp     rax, r12
0x180052a59  jnz     loc_180052BF0
0x180052a5f  lea     rcx, LdrpEnclaveListLock
0x180052a66  test    rsi, rsi
0x180052a69  jz      loc_180052C11
0x180052a6f  lock inc dword ptr [rsi+3Ch]
0x180052a73  call    RtlLeaveCriticalSection
0x180052a78  lea     rcx, [rsi+10h]
0x180052a7c  call    RtlEnterCriticalSection
0x180052a81  cmp     [rsi+48h], r13
0x180052a85  jnz     loc_180052D14
0x180052a8b  lea     rcx, [rsi+10h]
0x180052a8f  call    RtlLeaveCriticalSection
0x180052a94  mov     rcx, rsi
0x180052a97  call    LdrpDereferenceEnclave
0x180052a9c  mov     [rsp+148h+var_F8], rsi
0x180052aa1  jmp     short loc_180052A43
0x180052aa3  mov     rax, gs:30h
0x180052aac  mov     r15d, 6
0x180052ab2  mov     rcx, [rax+48h]
0x180052ab6  cmp     cs:qword_1801C4900, rcx
0x180052abd  jz      loc_1800529BD
0x180052ac3  jmp     loc_1800529BA
0x180052ac8  mov     r14, [rsp+148h+var_100]
0x180052acd  mov     rsi, [rsp+148h+var_F8]
0x180052ad2  cmp     ebx, 0C0000135h
0x180052ad8  jz      loc_1800530B6
0x180052ade  cmp     ebx, 0C0000142h
0x180052ae4  jz      loc_1800530B6
0x180052aea  test    rsi, rsi
0x180052aed  jnz     loc_180052CED
0x180052af3  mov     rcx, r15
0x180052af6  call    LdrpDereferenceModule
0x180052afb  cmp     ebx, 0C000007Ah
0x180052b01  jz      loc_180052CBE
0x180052b07  mov     rdi, [rsp+148h+var_110]
0x180052b0c  cmp     [rsp+148h+var_118], 0
0x180052b11  jz      short loc_180052B2A
0x180052b13  mov     rcx, gs:60h
0x180052b1c  mov     r8, rdi
0x180052b1f  xor     edx, edx
0x180052b21  mov     rcx, [rcx+30h]
0x180052b25  call    RtlFreeHeap_0
0x180052b2a  cmp     cs:UseWOW64, 0
0x180052b31  jnz     short loc_180052B37
0x180052b33  test    ebx, ebx
0x180052b35  jns     short loc_180052B72
0x180052b37  mov     rax, [rsp+148h+var_D0]
0x180052b3c  mov     [rax], r14
0x180052b3f  mov     eax, ebx
0x180052b41  mov     r12, [rsp+148h+arg_0]
0x180052b49  mov     r15, [rsp+148h+var_38]
0x180052b51  mov     rcx, [rsp+148h+var_48]
0x180052b59  xor     rcx, rsp; StackCookie
0x180052b5c  call    __security_check_cookie
0x180052b61  add     rsp, 118h
0x180052b68  pop     r14
0x180052b6a  pop     r13
0x180052b6c  pop     rdi
0x180052b6d  pop     rsi
0x180052b6e  pop     rbp
0x180052b6f  pop     rbx
0x180052b70  retn
0x180052b72  cmp     cs:qword_1801E3518, 0
0x180052b7a  jz      short loc_180052B37
0x180052b7c  test    byte ptr cs:dword_1801E34FC, 1
0x180052b83  jnz     short loc_180052B37
0x180052b85  mov     rax, cs:qword_1801E3500
0x180052b8c  shr     rax, 28h
0x180052b90  and     al, 3
0x180052b92  cmp     al, 3
0x180052b94  jnz     short loc_180052B37
0x180052b96  lea     rdx, [rsp+148h+var_E8]
0x180052b9b  mov     rcx, r14
0x180052b9e  call    RtlValidateUserCallTarget
0x180052ba3  cmp     eax, 1
0x180052ba6  jz      short loc_180052B37
0x180052ba8  test    byte ptr [rsp+148h+var_E8], 10h
0x180052bad  jz      short loc_180052B37
0x180052baf  call    LdrControlFlowGuardEnforced
0x180052bb4  test    eax, eax
0x180052bb6  jz      loc_180053134
0x180052bbc  mov     rcx, r14
0x180052bbf  call    RtlGuardIsExportSuppressedAddress
0x180052bc4  cmp     al, 1
0x180052bc6  jnz     short loc_180052BDF
0x180052bc8  mov     edx, 4
0x180052bcd  mov     rcx, r14
0x180052bd0  call    RtlpGuardGrantSuppressedCallAccess
0x180052bd5  mov     ebx, eax
0x180052bd7  test    eax, eax
0x180052bd9  jns     loc_180052B37
0x180052bdf  mov     ecx, 2Eh ; '.'
0x180052be4  int     29h; Win8: RtlFailFast(ecx)
0x180052bf0  mov     rsi, rax
0x180052bf3  mov     [rsp+148h+var_F8], rax
0x180052bf8  cmp     rbp, [rax+48h]
0x180052bfc  jz      loc_180052A5F
0x180052c02  mov     rax, [rax]
0x180052c05  cmp     rax, r12
0x180052c08  jnz     short loc_180052BF0
0x180052c0a  lea     rcx, LdrpEnclaveListLock
0x180052c11  call    RtlLeaveCriticalSection
0x180052c16  mov     [rsp+148h+var_F8], r13
0x180052c1b  mov     ebx, r13d
0x180052c1e  mov     [rsp+148h+var_108], ebx
0x180052c22  mov     r12d, 1
0x180052c28  mov     [rsp+148h+var_F0], r12d
0x180052c2d  test    rbp, rbp
0x180052c30  jz      loc_180052FB8
0x180052c36  lea     rsi, LdrpModuleBaseAddressIndex
0x180052c3d  cmp     rbp, cs:LdrpSystemDllBase
0x180052c44  mov     ecx, 1000h
0x180052c49  jz      loc_180052FC2
0x180052c4f  lea     rcx, LdrpModuleDatatableLock
0x180052c56  call    RtlAcquireSRWLockShared
0x180052c5b  mov     rcx, cs:qword_1801CA478
0x180052c62  mov     rax, cs:LdrpModuleBaseAddressIndex
0x180052c69  test    r12b, cl
0x180052c6c  jnz     loc_180052FF5
0x180052c72  movzx   edx, cl
0x180052c75  and     edx, r12d
0x180052c78  test    rax, rax
0x180052c7b  jz      loc_180052F79
0x180052c81  cmp     rbp, [rax-98h]
0x180052c88  ja      loc_180052F54
0x180052c8e  jb      loc_180052F66
0x180052c94  mov     rcx, [rax-30h]
0x180052c98  lea     r13, [rax-0C8h]
0x180052c9f  mov     eax, [rcx+18h]
0x180052ca2  cmp     eax, 0FFFFFFFFh
0x180052ca5  jnz     loc_180052FD9
0x180052cab  mov     rax, [r13+98h]
0x180052cb2  mov     ebx, [rax+38h]
0x180052cb5  mov     [rsp+148h+var_108], ebx
0x180052cb9  jmp     loc_180052F79
0x180052cbe  mov     rdi, [rsp+148h+var_110]
0x180052cc3  mov     rax, rdi
0x180052cc6  test    rdi, rdi
0x180052cc9  jnz     short loc_180052CCD
0x180052ccb  mov     edi, ebp
0x180052ccd  xor     ebx, ebx
0x180052ccf  mov     rdx, rdi
0x180052cd2  test    rax, rax
0x180052cd5  setnz   bl
0x180052cd8  xor     ecx, ecx
0x180052cda  add     ebx, 0C0000138h
0x180052ce0  mov     r8d, ebx
0x180052ce3  call    LdrpReportError
0x180052ce8  jmp     loc_180052B0C
0x180052ced  mov     rcx, rsi
0x180052cf0  call    LdrpDereferenceEnclave
0x180052cf5  test    ebx, ebx
0x180052cf7  js      loc_180052AFB
0x180052cfd  jmp     short loc_180052D01
0x180052cff  xor     ebx, ebx
0x180052d01  mov     rax, [r15+0B8h]
0x180052d08  sub     rax, [r15+30h]
0x180052d0c  add     r14, rax
0x180052d0f  jmp     loc_180052B07
0x180052d14  cmp     dword ptr [rsi+38h], 10h
0x180052d18  jnz     loc_180052F3E
0x180052d1e  cmp     dword ptr [rsi+40h], 2
0x180052d22  jnz     loc_180052F3E
0x180052d28  lea     rcx, [rsi+10h]
0x180052d2c  call    RtlLeaveCriticalSection
0x180052d31  mov     r13, [rsi+70h]
0x180052d35  mov     r15, r13
0x180052d38  test    r13, r13
0x180052d3b  jz      short loc_180052CFF
0x180052d3d  mov     r12d, 3
0x180052d43  lea     rsi, LdrpModuleBaseAddressIndex
0x180052d4a  mov     [rsp+148h+var_F0], r12d
0x180052d4f  lea     rcx, LdrpModuleDatatableLock
0x180052d56  mov     r14d, 1000h
0x180052d5c  call    RtlAcquireSRWLockShared
0x180052d61  mov     rax, cs:qword_1801CA478
0x180052d68  mov     rbx, cs:LdrpModuleBaseAddressIndex
0x180052d6f  test    al, 1
0x180052d71  jnz     loc_180052F2D
0x180052d77  movzx   edx, al
0x180052d7a  xor     esi, esi
0x180052d7c  and     edx, 1
0x180052d7f  test    rbx, rbx
0x180052d82  jz      short loc_180052DC5
0x180052d84  nop     dword ptr [rax+00h]
0x180052d88  nop     dword ptr [rax+rax+00000000h]
0x180052d90  mov     rcx, [rbx-98h]
0x180052d97  cmp     rdi, rcx
0x180052d9a  jb      loc_180052E22
0x180052da0  mov     eax, [rbx-88h]
0x180052da6  add     rax, rcx
0x180052da9  cmp     rdi, rax
0x180052dac  jnb     short loc_180052E10
0x180052dae  mov     rcx, [rbx-30h]
0x180052db2  lea     rsi, [rbx-0C8h]
0x180052db9  mov     eax, [rcx+18h]
0x180052dbc  cmp     eax, 0FFFFFFFFh
0x180052dbf  jnz     loc_180052EB6
0x180052dc5  lea     rcx, LdrpModuleDatatableLock
0x180052dcc  call    RtlReleaseSRWLockShared
0x180052dd1  test    rbx, rbx
0x180052dd4  jz      short loc_180052E41
0x180052dd6  mov     ebp, [rsp+148h+var_EC]
0x180052dda  lea     rax, [rsp+148h+var_100]
0x180052ddf  mov     r8, [rsp+148h+var_110]
0x180052de4  mov     r9d, ebp
0x180052de7  mov     [rsp+148h+var_120], rax
0x180052dec  mov     rdx, r15
0x180052def  mov     eax, [rsp+148h+var_F0]
0x180052df3  mov     rcx, rsi
0x180052df6  mov     dword ptr [rsp+148h+var_128], eax
0x180052dfa  call    LdrpResolveProcedureAddress
0x180052dff  mov     ebx, eax
0x180052e01  test    rsi, rsi
0x180052e04  jz      short loc_180052E68
0x180052e06  mov     rcx, rsi
0x180052e09  call    LdrpDereferenceModule
0x180052e0e  jmp     short loc_180052E68
0x180052e10  mov     rax, [rbx+8]
0x180052e14  test    edx, edx
0x180052e16  jz      short loc_180052E29
0x180052e18  test    rax, rax
0x180052e1b  jz      short loc_180052E29
0x180052e1d  xor     rbx, rax
0x180052e20  jmp     short loc_180052E2C
0x180052e22  mov     rax, [rbx]
0x180052e25  test    edx, edx
0x180052e27  jnz     short loc_180052EA5
0x180052e29  mov     rbx, rax
0x180052e2c  test    rbx, rbx
0x180052e2f  jnz     loc_180052D90
0x180052e35  lea     rcx, LdrpModuleDatatableLock
0x180052e3c  call    RtlReleaseSRWLockShared
  ... truncated ...
```
