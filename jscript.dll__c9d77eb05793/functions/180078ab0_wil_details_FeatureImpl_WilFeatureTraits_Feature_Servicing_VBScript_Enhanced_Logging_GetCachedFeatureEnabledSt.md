# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCachedFeatureEnabledState(void)

- ea: `0x180078ab0`
- end: `0x180078eb7`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `1031`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007cef0`
- `0x18007e100`

## callees

- `0x180059cd4`
- `0x180078ab0`
- `0x18007e140`
- `0x180096010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180078e18`
- `msvcrt!memcpy_s` at `0x180078e97`
- `msvcrt!memcpy_s` at `0x180078e18`
- `msvcrt!memcpy_s` at `0x180078e97`
- `KERNEL32!HeapFree` at `0x180078e3f`
- `KERNEL32!HeapFree` at `0x180078e3f`
- `KERNEL32!SetLastError` at `0x180078d90`
- `KERNEL32!SetLastError` at `0x180078e65`
- `KERNEL32!SetLastError` at `0x180078d90`
- `KERNEL32!SetLastError` at `0x180078e65`
- `KERNEL32!GetLastError` at `0x180078d6a`
- `KERNEL32!GetLastError` at `0x180078d6a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078b33`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078b8b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078b9c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078da2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078b33`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078b8b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078b9c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078da2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180078b16`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180078cf8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180078b16`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180078cf8`
- `KERNEL32!GetProcessHeap` at `0x180078e31`
- `KERNEL32!GetProcessHeap` at `0x180078e31`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCachedFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int16 v5; // di
  void (__fastcall *v6)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax
  __int64 (__fastcall *v7)(__int64, __int64, __int64 *); // rax
  int v8; // eax
  unsigned int v9; // r8d
  __int16 v10; // bx
  __int16 v11; // ax
  __int16 v12; // bx
  char v13; // r15
  char IsEnabled; // al
  signed __int32 v15; // eax
  unsigned __int16 v16; // di
  signed __int32 v17; // r8d
  int v18; // eax
  int v19; // edx
  signed __int32 v20; // ecx
  void *v21; // r10
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rbx
  DWORD LastError; // r12d
  unsigned __int64 v26; // r15
  void *v27; // rax
  void *v28; // rbx
  int v29; // ecx
  char *v31; // rbp
  void *v32; // r14
  HANDLE ProcessHeap; // rax
  rsize_t v34; // rdx
  _QWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v36; // [rsp+60h] [rbp+8h] BYREF

  v36 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = dword_1800B70DC;
  v5 = 1;
  if ( !dword_1800B70DC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800B7120 )
      {
        v4 = dword_1800B70DC;
        ReleaseSRWLockExclusive(&SRWLock);
        goto LABEL_12;
      }
      v6 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800B7120 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v6 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v6(
          &qword_1800B7120,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
        if ( qword_1800B7120 )
        {
          dword_1800B70DC = 1;
          ReleaseSRWLockExclusive(&SRWLock);
          v4 = 1;
          goto LABEL_12;
        }
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    v4 = 0;
  }
LABEL_12:
  v7 = (__int64 (__fastcall *)(__int64, __int64, __int64 *))g_wil_details_internalGetFeatureEnabledState;
  LODWORD(v36) = 0;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v7 = (__int64 (__fastcall *)(__int64, __int64, __int64 *))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      v10 = 0;
      goto LABEL_19;
    }
  }
  v8 = v7(57540041, 3, &v36);
  v9 = v8 & 0xFFFFFF3F;
  v10 = 8 * (v8 & 0x80 | (4 * (v8 & 0x40 | (4 * (v8 & 3)))));
  if ( (v8 & 0xFFFFFF3F) == 0 )
  {
LABEL_19:
    v11 = 64;
    goto LABEL_20;
  }
  v11 = 0;
  if ( v9 == 2 )
    v11 = 64;
LABEL_20:
  v12 = v11 | v10;
  if ( (v12 & 0xC00) == 0xC00 )
  {
    v13 = 1;
  }
  else
  {
    v13 = 0;
    if ( (v12 & 0x40) == 0 )
    {
      IsEnabled = 0;
      goto LABEL_27;
    }
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled();
  if ( v13 && !IsEnabled )
    v12 &= ~0x400u;
LABEL_27:
  if ( (v12 & 0x40) == 0 || !IsEnabled )
    v5 = 0;
  v15 = *(_DWORD *)a2;
  v16 = v12 | v5;
  do
  {
    v17 = v15;
    *(_DWORD *)a2 = v15;
    if ( !(_DWORD)v36 || (v15 & 2) != 0 )
    {
      v19 = v15;
    }
    else
    {
      v18 = v15
          ^ (v16
           ^ (unsigned __int16)v15)
          & 0x180
          ^ ((unsigned __int8)v16
           ^ (unsigned __int8)(v15 ^ (v16 ^ v15) & 0x80))
          & 0x40
          ^ ((unsigned __int8)(v15 ^ (v16 ^ v15) & 0x80 ^ (v16 ^ v15 ^ (v16 ^ v15) & 0x80) & 0x40)
           ^ (unsigned __int8)v16)
          & 1;
      v19 = v18 ^ ((unsigned __int16)v18 ^ v16) & 0x800 | 2;
      *(_DWORD *)a2 = v19;
    }
    if ( (v17 & 4) != 0 )
    {
      v20 = v19;
    }
    else
    {
      v20 = v19 ^ ((unsigned __int16)v19 ^ v16) & 0x400 | 4;
      *(_DWORD *)a2 = v20;
    }
    v15 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor,
            v20,
            v17);
  }
  while ( v17 != v15 );
  if ( (v17 & 4) != 0 || !wil::details::g_enabledStateManager )
    goto LABEL_51;
  AcquireSRWLockExclusive(&SRWLock);
  if ( !v4 || v4 != dword_1800B70DC )
    goto LABEL_49;
  v21 = Destination;
  v22 = qword_1800B7110;
  v23 = qword_1800B7110 - qword_1800B7100;
  Source[0] = 3;
  Source[1] = Feature_Servicing_VBScript_Enhanced_Logging__descriptor;
  if ( (unsigned __int64)Destination - qword_1800B7100 + 16 < qword_1800B7110 - qword_1800B7100 )
    goto LABEL_57;
  v24 = 16;
  if ( 2 * v23 > 0x10 )
    v24 = 2 * v23;
  if ( v23 >= v24 )
  {
LABEL_57:
    v34 = 0;
    if ( (unsigned __int64)v21 < v22 )
      v34 = v22 - (_QWORD)v21;
    memcpy_s(v21, v34, Source, 0x10u);
    Destination = (char *)Destination + 16;
    goto LABEL_50;
  }
  LastError = GetLastError();
  v26 = (v24 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
  v27 = wil::details::ProcessHeapAlloc(0, v26);
  v28 = v27;
  if ( v27 )
  {
    v31 = (char *)Destination - qword_1800B7100;
    memcpy_s(v27, v26, qword_1800B7100, (rsize_t)Destination - qword_1800B7100);
    v32 = lpMem;
    lpMem = v28;
    if ( v32 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v32);
    }
    qword_1800B7100 = v28;
    Destination = &v31[(_QWORD)v28];
    qword_1800B7110 = (__int64)v28 + v26;
    SetLastError(LastError);
    v22 = qword_1800B7110;
    v21 = Destination;
    goto LABEL_57;
  }
  SetLastError(LastError);
LABEL_49:
  _InterlockedAnd((volatile signed __int32 *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor, 0xFFFFFFFB);
LABEL_50:
  ReleaseSRWLockExclusive(&SRWLock);
LABEL_51:
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v29 = *(_DWORD *)a2
        ^ ((unsigned __int16)*(_DWORD *)a2
         ^ v16)
        & 0x180
        ^ ((unsigned __int8)(*(_DWORD *)a2 ^ (*(_DWORD *)a2 ^ v16) & 0x80)
         ^ (unsigned __int8)v16)
        & 0x40;
    *(_DWORD *)a2 = v29
                  ^ ((unsigned __int8)v29
                   ^ (unsigned __int8)v16)
                  & 1
                  ^ ((unsigned __int16)(v29 ^ ((unsigned __int8)v29 ^ (unsigned __int8)v16) & 1)
                   ^ v16)
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x180078ab0  mov     [rsp+arg_0], rcx
0x180078ab5  push    rsi
0x180078ab6  push    r13
0x180078ab8  push    r14
0x180078aba  sub     rsp, 40h
0x180078abe  mov     r14, cs:Feature_Servicing_VBScript_Enhanced_Logging__descriptor
0x180078ac5  xor     r13d, r13d
0x180078ac8  mov     [rdx], r13
0x180078acb  mov     rsi, rdx
0x180078ace  mov     eax, [r14]
0x180078ad1  mov     [rdx], eax
0x180078ad3  and     eax, 6
0x180078ad6  cmp     al, 6
0x180078ad8  jz      loc_180078EAA
0x180078ade  mov     [rsp+58h+arg_8], rbx
0x180078ae3  mov     [rsp+58h+arg_10], rbp
0x180078ae8  mov     ebp, cs:dword_1800B70DC
0x180078aee  nop
0x180078aef  mov     [rsp+58h+arg_18], rdi
0x180078af4  mov     edi, 1
0x180078af9  test    ebp, ebp
0x180078afb  jnz     loc_180078BA5
0x180078b01  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180078b07  test    eax, eax
0x180078b09  jz      loc_180078BA2
0x180078b0f  lea     rcx, SRWLock; SRWLock
0x180078b16  call    cs:__imp_AcquireSRWLockExclusive
0x180078b1c  cmp     cs:qword_1800B7120, r13
0x180078b23  jz      short loc_180078B3B
0x180078b25  mov     ebp, cs:dword_1800B70DC
0x180078b2b  lea     rcx, SRWLock; SRWLock
0x180078b32  nop
0x180078b33  call    cs:__imp_ReleaseSRWLockExclusive
0x180078b39  jmp     short loc_180078BA5
0x180078b3b  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180078b42  mov     cs:qword_1800B7120, r13
0x180078b49  test    rax, rax
0x180078b4c  jnz     short loc_180078B5A
0x180078b4e  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180078b55  test    rax, rax
0x180078b58  jz      short loc_180078B95
0x180078b5a  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180078b61  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180078b68  lea     rcx, qword_1800B7120
0x180078b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078b74  cmp     cs:qword_1800B7120, r13
0x180078b7b  jz      short loc_180078B95
0x180078b7d  nop
0x180078b7e  lea     rcx, SRWLock; SRWLock
0x180078b85  mov     cs:dword_1800B70DC, edi
0x180078b8b  call    cs:__imp_ReleaseSRWLockExclusive
0x180078b91  mov     ebp, edi
0x180078b93  jmp     short loc_180078BA5
0x180078b95  lea     rcx, SRWLock; SRWLock
0x180078b9c  call    cs:__imp_ReleaseSRWLockExclusive
0x180078ba2  mov     ebp, r13d
0x180078ba5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180078bac  mov     dword ptr [rsp+58h+arg_0], r13d
0x180078bb1  test    rax, rax
0x180078bb4  jnz     short loc_180078BC2
0x180078bb6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180078bbd  test    rax, rax
0x180078bc0  jz      short loc_180078C18
0x180078bc2  lea     r8, [rsp+58h+arg_0]
0x180078bc7  mov     edx, 3
0x180078bcc  mov     ecx, 36DFDC9h
0x180078bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078bd6  mov     r8d, eax
0x180078bd9  mov     edx, eax
0x180078bdb  and     r8d, 0FFFFFF3Fh
0x180078be2  and     eax, 40h
0x180078be5  and     edx, 80h
0x180078beb  mov     ecx, r8d
0x180078bee  and     ecx, 3
0x180078bf1  shl     ecx, 2
0x180078bf4  or      ecx, eax
0x180078bf6  shl     ecx, 2
0x180078bf9  or      ecx, edx
0x180078bfb  lea     ebx, ds:0[rcx*8]
0x180078c02  test    r8d, r8d
0x180078c05  jz      short loc_180078C1B
0x180078c07  cmp     r8d, 2
0x180078c0b  mov     eax, r13d
0x180078c0e  mov     ecx, 40h ; '@'
0x180078c13  cmovz   eax, ecx
0x180078c16  jmp     short loc_180078C20
0x180078c18  mov     ebx, r13d
0x180078c1b  mov     eax, 40h ; '@'
0x180078c20  or      ebx, eax
0x180078c22  mov     [rsp+58h+var_28], r15
0x180078c27  mov     eax, ebx
0x180078c29  and     eax, 0C00h
0x180078c2e  cmp     eax, 0C00h
0x180078c33  jnz     short loc_180078C3B
0x180078c35  movzx   r15d, dil
0x180078c39  jmp     short loc_180078C43
0x180078c3b  xor     r15b, r15b
0x180078c3e  test    bl, 40h
0x180078c41  jz      short loc_180078C57
0x180078c43  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x180078c48  test    r15b, r15b
0x180078c4b  jz      short loc_180078C59
0x180078c4d  test    al, al
0x180078c4f  jnz     short loc_180078C59
0x180078c51  btr     ebx, 0Ah
0x180078c55  jmp     short loc_180078C59
0x180078c57  xor     al, al
0x180078c59  test    bl, 40h
0x180078c5c  jz      short loc_180078C62
0x180078c5e  test    al, al
0x180078c60  jnz     short loc_180078C65
0x180078c62  mov     edi, r13d
0x180078c65  mov     eax, [rsi]
0x180078c67  or      edi, ebx
0x180078c69  mov     r8d, eax
0x180078c6c  mov     [rsi], eax
0x180078c6e  cmp     dword ptr [rsp+58h+arg_0], r13d
0x180078c73  jz      short loc_180078CAA
0x180078c75  test    r8b, 2
0x180078c79  jnz     short loc_180078CAA
0x180078c7b  xor     eax, edi
0x180078c7d  mov     edx, edi
0x180078c7f  and     eax, 180h
0x180078c84  xor     eax, r8d
0x180078c87  mov     ecx, eax
0x180078c89  xor     ecx, edi
0x180078c8b  and     ecx, 40h
0x180078c8e  xor     ecx, eax
0x180078c90  mov     eax, edi
0x180078c92  xor     eax, ecx
0x180078c94  and     eax, 1
0x180078c97  xor     eax, ecx
0x180078c99  xor     edx, eax
0x180078c9b  and     edx, 800h
0x180078ca1  xor     edx, eax
0x180078ca3  or      edx, 2
0x180078ca6  mov     [rsi], edx
0x180078ca8  jmp     short loc_180078CAD
0x180078caa  mov     edx, r8d
0x180078cad  mov     r9d, r8d
0x180078cb0  and     r9d, 4
0x180078cb4  jnz     short loc_180078CC9
0x180078cb6  mov     ecx, edi
0x180078cb8  xor     ecx, edx
0x180078cba  and     ecx, 400h
0x180078cc0  xor     ecx, edx
0x180078cc2  or      ecx, 4
0x180078cc5  mov     [rsi], ecx
0x180078cc7  jmp     short loc_180078CCB
0x180078cc9  mov     ecx, edx
0x180078ccb  mov     eax, r8d
0x180078cce  lock cmpxchg [r14], ecx
0x180078cd3  jnz     short loc_180078C69
0x180078cd5  test    r9d, r9d
0x180078cd8  jnz     loc_180078DAD
0x180078cde  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180078ce4  test    eax, eax
0x180078ce6  jz      loc_180078DAD
0x180078cec  lea     rcx, SRWLock; SRWLock
0x180078cf3  mov     [rsp+58h+var_20], r12
0x180078cf8  call    cs:__imp_AcquireSRWLockExclusive
0x180078cfe  mov     eax, cs:dword_1800B70DC
0x180078d04  test    ebp, ebp
0x180078d06  jz      loc_180078D96
0x180078d0c  cmp     ebp, eax
0x180078d0e  jnz     loc_180078D96
0x180078d14  mov     r10, cs:Destination
0x180078d1b  mov     r8, cs:qword_1800B7110
0x180078d22  mov     rax, r10
0x180078d25  sub     rax, cs:qword_1800B7100
0x180078d2c  mov     rdx, r8
0x180078d2f  sub     rdx, cs:qword_1800B7100
0x180078d36  add     rax, 10h
0x180078d3a  mov     [rsp+58h+Source], 3
0x180078d43  mov     [rsp+58h+var_30], r14
0x180078d48  cmp     rax, rdx
0x180078d4b  jb      loc_180078E79
0x180078d51  lea     rax, [rdx+rdx]
0x180078d55  mov     ebx, 10h
0x180078d5a  cmp     rax, rbx
0x180078d5d  cmova   rbx, rax
0x180078d61  cmp     rdx, rbx
0x180078d64  jnb     loc_180078E79
0x180078d6a  call    cs:__imp_GetLastError
0x180078d70  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180078d74  xor     ecx, ecx; dwFlags
0x180078d76  mov     r12d, eax
0x180078d79  lea     r15, [rbx+40h]
0x180078d7d  mov     rdx, r15; dwBytes
0x180078d80  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180078d85  mov     rbx, rax
0x180078d88  test    rax, rax
0x180078d8b  jnz     short loc_180078DFE
0x180078d8d  mov     ecx, r12d; dwErrCode
0x180078d90  call    cs:__imp_SetLastError
0x180078d96  lock and dword ptr [r14], 0FFFFFFFBh
0x180078d9b  lea     rcx, SRWLock; SRWLock
0x180078da2  call    cs:__imp_ReleaseSRWLockExclusive
0x180078da8  mov     r12, [rsp+58h+var_20]
0x180078dad  mov     ecx, [rsi]
0x180078daf  mov     r15, [rsp+58h+var_28]
0x180078db4  mov     rbp, [rsp+58h+arg_10]
0x180078db9  mov     rbx, [rsp+58h+arg_8]
0x180078dbe  test    cl, 2
0x180078dc1  jnz     short loc_180078DEC
0x180078dc3  mov     eax, edi
0x180078dc5  xor     eax, ecx
0x180078dc7  and     eax, 180h
0x180078dcc  xor     eax, ecx
0x180078dce  mov     ecx, edi
0x180078dd0  xor     ecx, eax
0x180078dd2  and     ecx, 40h
0x180078dd5  xor     ecx, eax
0x180078dd7  mov     eax, edi
0x180078dd9  xor     eax, ecx
0x180078ddb  and     eax, 1
0x180078dde  xor     eax, ecx
0x180078de0  xor     edi, eax
0x180078de2  and     edi, 800h
0x180078de8  xor     edi, eax
0x180078dea  mov     [rsi], edi
0x180078dec  mov     rdi, [rsp+58h+arg_18]
0x180078df1  mov     rax, rsi
0x180078df4  add     rsp, 40h
0x180078df8  pop     r14
0x180078dfa  pop     r13
0x180078dfc  pop     rsi
0x180078dfd  retn
0x180078dfe  mov     r8, cs:qword_1800B7100; Source
0x180078e05  mov     rdx, r15; DestinationSize
0x180078e08  mov     rbp, cs:Destination
0x180078e0f  mov     rcx, rbx; Destination
0x180078e12  sub     rbp, r8
0x180078e15  mov     r9, rbp; SourceSize
0x180078e18  call    cs:__imp_memcpy_s
0x180078e1e  mov     r14, cs:lpMem
0x180078e25  mov     cs:lpMem, rbx
0x180078e2c  test    r14, r14
0x180078e2f  jz      short loc_180078E45
0x180078e31  call    cs:__imp_GetProcessHeap
0x180078e37  mov     r8, r14; lpMem
0x180078e3a  xor     edx, edx; dwFlags
0x180078e3c  mov     rcx, rax; hHeap
0x180078e3f  call    cs:__imp_HeapFree
0x180078e45  lea     rax, [rbx+rbp]
0x180078e49  mov     cs:qword_1800B7100, rbx
0x180078e50  mov     cs:Destination, rax
0x180078e57  mov     ecx, r12d; dwErrCode
0x180078e5a  lea     rax, [rbx+r15]
0x180078e5e  mov     cs:qword_1800B7110, rax
0x180078e65  call    cs:__imp_SetLastError
0x180078e6b  mov     r8, cs:qword_1800B7110
0x180078e72  mov     r10, cs:Destination
0x180078e79  mov     rax, r8
0x180078e7c  mov     rdx, r13
0x180078e7f  sub     rax, r10
0x180078e82  mov     r9d, 10h; SourceSize
0x180078e88  cmp     r10, r8
0x180078e8b  mov     rcx, r10; Destination
0x180078e8e  lea     r8, [rsp+58h+Source]; Source
0x180078e93  cmovb   rdx, rax; DestinationSize
0x180078e97  call    cs:__imp_memcpy_s
0x180078e9d  add     cs:Destination, 10h
0x180078ea5  jmp     loc_180078D9B
0x180078eaa  mov     rax, rsi
0x180078ead  add     rsp, 40h
0x180078eb1  pop     r14
0x180078eb3  pop     r13
0x180078eb5  pop     rsi
0x180078eb6  retn
```
