# PECheckComponentLoadEx

- ea: `0x1800a4f74`
- end: `0x1800a5232`
- name: `PECheckComponentLoadEx`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a4d6c`

## callees

- `0x18000ea54`
- `0x18000ec28`
- `0x18000ee14`
- `0x1800204b4`
- `0x18002c0d0`
- `0x180080e90`
- `0x1800a4f74`
- `0x1800a5238`
- `0x1800a5338`
- `0x1800a5638`
- `0x1800a57b0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a506a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a506a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a50cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a50cb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a507f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a507f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a50bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a50bf`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800a51e9`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800a51e9`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a4fe5`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a4fe5`

## pseudocode

```c
__int64 __fastcall PECheckComponentLoadEx(
        void *a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        unsigned int a4,
        int a5,
        _DWORD *a6)
{
  int v8; // esi
  int DPLForInterrupt; // ebx
  int v10; // eax
  unsigned int v11; // edi
  int v12; // r14d
  unsigned int v13; // ebx
  const UNICODE_STRING *v14; // r14
  unsigned int v15; // edi
  __int64 *v16; // rdx
  int v18; // esi
  char v19[4]; // [rsp+30h] [rbp-48h] BYREF
  __int16 SystemInformation; // [rsp+34h] [rbp-44h] BYREF
  char v21; // [rsp+36h] [rbp-42h]
  int v22; // [rsp+38h] [rbp-40h] BYREF
  int v23; // [rsp+3Ch] [rbp-3Ch] BYREF
  const UNICODE_STRING *v24; // [rsp+40h] [rbp-38h]
  void *Source2; // [rsp+48h] [rbp-30h]
  __int128 v26; // [rsp+50h] [rbp-28h] BYREF
  int v27; // [rsp+60h] [rbp-18h]

  v24 = a3;
  Source2 = a1;
  v27 = 0;
  v23 = 0;
  v26 = 0;
  v8 = 0;
  v22 = 0;
  v19[0] = 0;
  if ( g_PEAuthStateVariables )
  {
    SystemInformation = 0;
    v21 = 0;
    if ( ZwQuerySystemInformation(SystemFileCacheInformation|0x80, &SystemInformation, 3u, 0) < 0
      || (_BYTE)SystemInformation
      || (DPLForInterrupt = GetDPLForInterrupt(1), v10 = GetDPLForInterrupt(65), DPLForInterrupt)
      || v10
      || (unsigned __int8)GetDR7Value() )
    {
      PEAuthStoreParameter(1, 0);
      g_PEAuthStateVariables = 0;
    }
  }
  v11 = I_PELoadGRL(a1, a2, a3);
  v12 = 2;
  if ( a2 )
  {
    v13 = v11 | I_PECheckMincryptPolicy(a2, a4, (unsigned int)&v26, (unsigned int)&v23, (__int64)&v22);
    if ( v13 )
    {
      v8 = v22;
    }
    else
    {
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
      if ( qword_180049428 )
        v13 = (unsigned int)MFIsHashInGRL(qword_180049428, Source2, a4 == 0) != 0 ? 0x2000 : 0;
      else
        v13 |= 0x1000u;
      ExReleaseResourceLite(&g_GRLContextLock);
      KeLeaveCriticalRegion();
      v8 = v22;
      if ( v22 == 0x10002 )
      {
        if ( (int)PEAuthGetDebugCredentialsData(v19) < 0 )
        {
          PEAuthStoreParameter(1, 0);
          g_PEAuthStateVariables = 0;
          PEAuthStoreParameter(2, 0);
        }
        if ( !v19[0] )
          v13 |= 0x10000u;
      }
    }
  }
  else
  {
    v13 = v11;
  }
  if ( v13 )
  {
    v15 = -1073740760;
    v18 = 1;
    if ( (v13 & 0xFFFFEFCF) == 0 )
    {
      v15 = 0;
      v18 = 0;
      *a6 |= v13;
    }
    if ( a4 )
    {
      v15 = 0;
      PEAuthStoreParameter(1, 0);
      g_PEAuthStateVariables = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 |= v12;
    if ( PsIsCurrentThreadPrefetching() )
    {
      v18 = 0;
    }
    else if ( (g_PEAuthConfigOptions & 1) != 0 )
    {
      v14 = v24;
      I_PEWriteComponentLoadExEvents(v13, *(unsigned int *)(a2 + 8), v24, a4);
LABEL_24:
      if ( !v18 )
        return v15;
      goto LABEL_16;
    }
    v14 = v24;
    goto LABEL_24;
  }
  v14 = v24;
  v15 = 0;
  if ( (v8 & 0x10000) != 0 )
    *a6 |= 0x1000000u;
LABEL_16:
  if ( Source2 )
  {
    v16 = (__int64 *)&v26;
    if ( !v23 )
      v16 = g_rgEmptyHash;
    I_PEUpdateHashCache(Source2, (__int64)v16, v14, v13, a4, a5);
  }
  return v15;
}

```

## disassembly

```asm
0x1800a4f74  push    rbp
0x1800a4f76  push    rbx
0x1800a4f77  push    rsi
0x1800a4f78  push    rdi
0x1800a4f79  push    r12
0x1800a4f7b  push    r13
0x1800a4f7d  push    r14
0x1800a4f7f  push    r15
0x1800a4f81  mov     rbp, rsp
0x1800a4f84  sub     rsp, 78h
0x1800a4f88  mov     rax, cs:__security_cookie
0x1800a4f8f  xor     rax, rsp
0x1800a4f92  mov     [rbp+var_10], rax
0x1800a4f96  mov     r15, [rbp+arg_28]
0x1800a4f9a  xor     edi, edi
0x1800a4f9c  xor     eax, eax
0x1800a4f9e  mov     [rbp+var_38], r8
0x1800a4fa2  cmp     cs:g_PEAuthStateVariables, edi
0x1800a4fa8  xorps   xmm0, xmm0
0x1800a4fab  mov     r12d, r9d
0x1800a4fae  mov     [rbp+Source2], rcx
0x1800a4fb2  mov     r13, rdx
0x1800a4fb5  mov     [rbp+var_18], eax
0x1800a4fb8  lea     r14d, [rax+1]
0x1800a4fbc  mov     [rbp+var_3C], edi
0x1800a4fbf  movups  [rbp+var_28], xmm0
0x1800a4fc3  mov     esi, edi
0x1800a4fc5  mov     [rbp+var_40], edi
0x1800a4fc8  mov     [rbp+var_48], dil
0x1800a4fcc  jz      short loc_1800A502E
0x1800a4fce  xor     r9d, r9d; ReturnLength
0x1800a4fd1  mov     [rbp+SystemInformation], ax
0x1800a4fd5  lea     r8d, [rax+3]; SystemInformationLength
0x1800a4fd9  mov     [rbp+var_42], al
0x1800a4fdc  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x1800a4fe0  mov     ecx, 95h; SystemInformationClass
0x1800a4fe5  call    cs:__imp_ZwQuerySystemInformation
0x1800a4fec  nop     dword ptr [rax+rax+00h]
0x1800a4ff1  test    eax, eax
0x1800a4ff3  js      short loc_1800A501E
0x1800a4ff5  cmp     byte ptr [rbp+SystemInformation], dil
0x1800a4ff9  jnz     short loc_1800A501E
0x1800a4ffb  mov     ecx, r14d
0x1800a4ffe  call    GetDPLForInterrupt
0x1800a5003  lea     ecx, [rdi+41h]
0x1800a5006  mov     ebx, eax
0x1800a5008  call    GetDPLForInterrupt
0x1800a500d  test    ebx, ebx
0x1800a500f  jnz     short loc_1800A501E
0x1800a5011  test    eax, eax
0x1800a5013  jnz     short loc_1800A501E
0x1800a5015  call    GetDR7Value
0x1800a501a  test    al, al
0x1800a501c  jz      short loc_1800A502E
0x1800a501e  xor     edx, edx
0x1800a5020  mov     ecx, r14d
0x1800a5023  call    PEAuthStoreParameter
0x1800a5028  mov     cs:g_PEAuthStateVariables, edi
0x1800a502e  call    I_PELoadGRL
0x1800a5033  mov     edi, eax
0x1800a5035  mov     r14d, 2
0x1800a503b  test    r13, r13
0x1800a503e  jz      loc_1800A5157
0x1800a5044  lea     rax, [rbp+var_40]
0x1800a5048  mov     edx, r12d
0x1800a504b  lea     r9, [rbp+var_3C]
0x1800a504f  mov     qword ptr [rsp+78h+var_58], rax
0x1800a5054  lea     r8, [rbp+var_28]
0x1800a5058  mov     rcx, r13
0x1800a505b  call    I_PECheckMincryptPolicy
0x1800a5060  mov     ebx, eax
0x1800a5062  or      ebx, edi
0x1800a5064  jnz     loc_1800A5164
0x1800a506a  call    cs:__imp_KeEnterCriticalRegion
0x1800a5071  nop     dword ptr [rax+rax+00h]
0x1800a5076  mov     dl, 1; Wait
0x1800a5078  lea     rcx, g_GRLContextLock; Resource
0x1800a507f  call    cs:__imp_ExAcquireResourceSharedLite
0x1800a5086  nop     dword ptr [rax+rax+00h]
0x1800a508b  mov     rcx, cs:qword_180049428
0x1800a5092  test    rcx, rcx
0x1800a5095  jz      loc_1800A515B
0x1800a509b  mov     rdx, [rbp+Source2]
0x1800a509f  xor     r8d, r8d
0x1800a50a2  test    r12d, r12d
0x1800a50a5  setz    r8b
0x1800a50a9  call    MFIsHashInGRL
0x1800a50ae  neg     eax
0x1800a50b0  sbb     ebx, ebx
0x1800a50b2  and     ebx, 2000h
0x1800a50b8  lea     rcx, g_GRLContextLock; Resource
0x1800a50bf  call    cs:__imp_ExReleaseResourceLite
0x1800a50c6  nop     dword ptr [rax+rax+00h]
0x1800a50cb  call    cs:__imp_KeLeaveCriticalRegion
0x1800a50d2  nop     dword ptr [rax+rax+00h]
0x1800a50d7  mov     esi, [rbp+var_40]
0x1800a50da  mov     eax, esi
0x1800a50dc  xor     eax, 10002h
0x1800a50e1  jz      loc_1800A5172
0x1800a50e7  test    ebx, ebx
0x1800a50e9  jnz     loc_1800A51B0
0x1800a50ef  mov     r14, [rbp+var_38]
0x1800a50f3  xor     edi, edi
0x1800a50f5  bt      esi, 10h
0x1800a50f9  jb      loc_1800A5228
0x1800a50ff  mov     rax, [rbp+Source2]
0x1800a5103  test    rax, rax
0x1800a5106  jz      short loc_1800A5137
0x1800a5108  cmp     [rbp+var_3C], 0
0x1800a510c  lea     r8, g_rgEmptyHash
0x1800a5113  mov     r10d, [rbp+arg_20]
0x1800a5117  lea     rdx, [rbp+var_28]
0x1800a511b  cmovz   rdx, r8
0x1800a511f  mov     [rsp+78h+var_50], r10d; int
0x1800a5124  mov     r8, r14
0x1800a5127  mov     [rsp+78h+var_58], r12d; int
0x1800a512c  mov     r9d, ebx
0x1800a512f  mov     rcx, rax; Source2
0x1800a5132  call    I_PEUpdateHashCache
0x1800a5137  mov     eax, edi
0x1800a5139  mov     rcx, [rbp+var_10]
0x1800a513d  xor     rcx, rsp; StackCookie
0x1800a5140  call    __security_check_cookie
0x1800a5145  add     rsp, 78h
0x1800a5149  pop     r15
0x1800a514b  pop     r14
0x1800a514d  pop     r13
0x1800a514f  pop     r12
0x1800a5151  pop     rdi
0x1800a5152  pop     rsi
0x1800a5153  pop     rbx
0x1800a5154  pop     rbp
0x1800a5155  retn
0x1800a5157  mov     ebx, edi
0x1800a5159  jmp     short loc_1800A50E7
0x1800a515b  bts     ebx, 0Ch
0x1800a515f  jmp     loc_1800A50B8
0x1800a5164  mov     esi, [rbp+var_40]
0x1800a5167  jmp     loc_1800A50E7
0x1800a516c  test    esi, esi
0x1800a516e  jz      short loc_1800A5137
0x1800a5170  jmp     short loc_1800A50FF
0x1800a5172  lea     rcx, [rbp+var_48]
0x1800a5176  call    PEAuthGetDebugCredentialsData
0x1800a517b  test    eax, eax
0x1800a517d  jns     short loc_1800A519D
0x1800a517f  xor     edx, edx
0x1800a5181  lea     ecx, [rdx+1]
0x1800a5184  call    PEAuthStoreParameter
0x1800a5189  xor     edx, edx
0x1800a518b  mov     cs:g_PEAuthStateVariables, 0
0x1800a5195  mov     ecx, r14d
0x1800a5198  call    PEAuthStoreParameter
0x1800a519d  cmp     [rbp+var_48], 0
0x1800a51a1  ja      loc_1800A50E7
0x1800a51a7  bts     ebx, 10h
0x1800a51ab  jmp     loc_1800A50E7
0x1800a51b0  mov     eax, 1
0x1800a51b5  mov     edi, 0C0000428h
0x1800a51ba  mov     esi, eax
0x1800a51bc  test    ebx, 0FFFFEFCFh
0x1800a51c2  jnz     short loc_1800A51CB
0x1800a51c4  xor     edi, edi
0x1800a51c6  xor     esi, esi
0x1800a51c8  or      [r15], ebx
0x1800a51cb  test    r12d, r12d
0x1800a51ce  jz      short loc_1800A51E3
0x1800a51d0  xor     edi, edi
0x1800a51d2  xor     edx, edx
0x1800a51d4  mov     ecx, eax
0x1800a51d6  call    PEAuthStoreParameter
0x1800a51db  mov     cs:g_PEAuthStateVariables, edi
0x1800a51e1  jmp     short loc_1800A51E6
0x1800a51e3  mov     r14d, eax
0x1800a51e6  or      ebx, r14d
0x1800a51e9  call    cs:__imp_PsIsCurrentThreadPrefetching
0x1800a51f0  nop     dword ptr [rax+rax+00h]
0x1800a51f5  test    al, al
0x1800a51f7  jz      short loc_1800A5204
0x1800a51f9  xor     esi, esi
0x1800a51fb  mov     r14, [rbp+var_38]
0x1800a51ff  jmp     loc_1800A516C
0x1800a5204  mov     eax, cs:g_PEAuthConfigOptions
0x1800a520a  test    al, 1
0x1800a520c  jz      short loc_1800A51FB
0x1800a520e  mov     r14, [rbp+var_38]
0x1800a5212  mov     r9d, r12d
0x1800a5215  mov     edx, [r13+8]
0x1800a5219  mov     r8, r14
0x1800a521c  mov     ecx, ebx
0x1800a521e  call    I_PEWriteComponentLoadExEvents
0x1800a5223  jmp     loc_1800A516C
0x1800a5228  bts     dword ptr [r15], 18h
0x1800a522d  jmp     loc_1800A50FF
```
