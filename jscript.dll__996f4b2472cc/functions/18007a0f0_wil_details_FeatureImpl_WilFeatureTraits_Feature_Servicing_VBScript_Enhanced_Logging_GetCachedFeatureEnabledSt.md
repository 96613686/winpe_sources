# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCachedFeatureEnabledState(void)

- ea: `0x18007a0f0`
- end: `0x18007a547`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `1111`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007e770`
- `0x18007fa70`

## callees

- `0x18005ad2c`
- `0x18007a0f0`
- `0x18007fab0`
- `0x180098010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18007a489`
- `msvcrt!memcpy_s` at `0x18007a520`
- `msvcrt!memcpy_s` at `0x18007a489`
- `msvcrt!memcpy_s` at `0x18007a520`
- `KERNEL32!HeapFree` at `0x18007a4bc`
- `KERNEL32!HeapFree` at `0x18007a4bc`
- `KERNEL32!SetLastError` at `0x18007a3f4`
- `KERNEL32!SetLastError` at `0x18007a4e8`
- `KERNEL32!SetLastError` at `0x18007a3f4`
- `KERNEL32!SetLastError` at `0x18007a4e8`
- `KERNEL32!GetLastError` at `0x18007a3c8`
- `KERNEL32!GetLastError` at `0x18007a3c8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a179`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a1d7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a1ee`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a40c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a179`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a1d7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a1ee`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a40c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007a156`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007a350`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007a156`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007a350`
- `KERNEL32!GetProcessHeap` at `0x18007a4a8`
- `KERNEL32!GetProcessHeap` at `0x18007a4a8`

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
  v4 = dword_1800B90D4;
  v5 = 1;
  if ( !dword_1800B90D4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800B90D8 )
      {
        v4 = dword_1800B90D4;
        ReleaseSRWLockExclusive(&SRWLock);
        goto LABEL_12;
      }
      v6 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800B90D8 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v6 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v6(
          &qword_1800B90D8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
        if ( qword_1800B90D8 )
        {
          dword_1800B90D4 = 1;
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
  if ( !v4 || v4 != dword_1800B90D4 )
    goto LABEL_49;
  v21 = Destination;
  v22 = qword_1800B9118;
  v23 = qword_1800B9118 - qword_1800B9108;
  Source[0] = 3;
  Source[1] = Feature_Servicing_VBScript_Enhanced_Logging__descriptor;
  if ( (unsigned __int64)Destination - qword_1800B9108 + 16 < qword_1800B9118 - qword_1800B9108 )
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
    v31 = (char *)Destination - qword_1800B9108;
    memcpy_s(v27, v26, qword_1800B9108, (rsize_t)Destination - qword_1800B9108);
    v32 = lpMem;
    lpMem = v28;
    if ( v32 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v32);
    }
    qword_1800B9108 = v28;
    Destination = &v31[(_QWORD)v28];
    qword_1800B9118 = (__int64)v28 + v26;
    SetLastError(LastError);
    v22 = qword_1800B9118;
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
0x18007a0f0  mov     [rsp+arg_0], rcx
0x18007a0f5  push    rsi
0x18007a0f6  push    r13
0x18007a0f8  push    r14
0x18007a0fa  sub     rsp, 40h
0x18007a0fe  mov     r14, cs:Feature_Servicing_VBScript_Enhanced_Logging__descriptor
0x18007a105  xor     r13d, r13d
0x18007a108  mov     [rdx], r13
0x18007a10b  mov     rsi, rdx
0x18007a10e  mov     eax, [r14]
0x18007a111  mov     [rdx], eax
0x18007a113  and     eax, 6
0x18007a116  cmp     al, 6
0x18007a118  jz      loc_18007A539
0x18007a11e  mov     [rsp+58h+arg_8], rbx
0x18007a123  mov     [rsp+58h+arg_10], rbp
0x18007a128  mov     ebp, cs:dword_1800B90D4
0x18007a12e  nop
0x18007a12f  mov     [rsp+58h+arg_18], rdi
0x18007a134  mov     edi, 1
0x18007a139  test    ebp, ebp
0x18007a13b  jnz     loc_18007A1FD
0x18007a141  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007a147  test    eax, eax
0x18007a149  jz      loc_18007A1FA
0x18007a14f  lea     rcx, SRWLock; SRWLock
0x18007a156  call    cs:__imp_AcquireSRWLockExclusive
0x18007a15d  nop     dword ptr [rax+rax+00h]
0x18007a162  cmp     cs:qword_1800B90D8, r13
0x18007a169  jz      short loc_18007A187
0x18007a16b  mov     ebp, cs:dword_1800B90D4
0x18007a171  lea     rcx, SRWLock; SRWLock
0x18007a178  nop
0x18007a179  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a180  nop     dword ptr [rax+rax+00h]
0x18007a185  jmp     short loc_18007A1FD
0x18007a187  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18007a18e  mov     cs:qword_1800B90D8, r13
0x18007a195  test    rax, rax
0x18007a198  jnz     short loc_18007A1A6
0x18007a19a  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18007a1a1  test    rax, rax
0x18007a1a4  jz      short loc_18007A1E7
0x18007a1a6  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007a1ad  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18007a1b4  lea     rcx, qword_1800B90D8
0x18007a1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a1c0  cmp     cs:qword_1800B90D8, r13
0x18007a1c7  jz      short loc_18007A1E7
0x18007a1c9  nop
0x18007a1ca  lea     rcx, SRWLock; SRWLock
0x18007a1d1  mov     cs:dword_1800B90D4, edi
0x18007a1d7  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a1de  nop     dword ptr [rax+rax+00h]
0x18007a1e3  mov     ebp, edi
0x18007a1e5  jmp     short loc_18007A1FD
0x18007a1e7  lea     rcx, SRWLock; SRWLock
0x18007a1ee  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a1f5  nop     dword ptr [rax+rax+00h]
0x18007a1fa  mov     ebp, r13d
0x18007a1fd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18007a204  mov     dword ptr [rsp+58h+arg_0], r13d
0x18007a209  test    rax, rax
0x18007a20c  jnz     short loc_18007A21A
0x18007a20e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18007a215  test    rax, rax
0x18007a218  jz      short loc_18007A270
0x18007a21a  lea     r8, [rsp+58h+arg_0]
0x18007a21f  mov     edx, 3
0x18007a224  mov     ecx, 36DFDC9h
0x18007a229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a22e  mov     r8d, eax
0x18007a231  mov     edx, eax
0x18007a233  and     r8d, 0FFFFFF3Fh
0x18007a23a  and     eax, 40h
0x18007a23d  and     edx, 80h
0x18007a243  mov     ecx, r8d
0x18007a246  and     ecx, 3
0x18007a249  shl     ecx, 2
0x18007a24c  or      ecx, eax
0x18007a24e  shl     ecx, 2
0x18007a251  or      ecx, edx
0x18007a253  lea     ebx, ds:0[rcx*8]
0x18007a25a  test    r8d, r8d
0x18007a25d  jz      short loc_18007A273
0x18007a25f  cmp     r8d, 2
0x18007a263  mov     eax, r13d
0x18007a266  mov     ecx, 40h ; '@'
0x18007a26b  cmovz   eax, ecx
0x18007a26e  jmp     short loc_18007A278
0x18007a270  mov     ebx, r13d
0x18007a273  mov     eax, 40h ; '@'
0x18007a278  or      ebx, eax
0x18007a27a  mov     [rsp+58h+var_28], r15
0x18007a27f  mov     eax, ebx
0x18007a281  and     eax, 0C00h
0x18007a286  cmp     eax, 0C00h
0x18007a28b  jnz     short loc_18007A293
0x18007a28d  movzx   r15d, dil
0x18007a291  jmp     short loc_18007A29B
0x18007a293  xor     r15b, r15b
0x18007a296  test    bl, 40h
0x18007a299  jz      short loc_18007A2AF
0x18007a29b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18007a2a0  test    r15b, r15b
0x18007a2a3  jz      short loc_18007A2B1
0x18007a2a5  test    al, al
0x18007a2a7  jnz     short loc_18007A2B1
0x18007a2a9  btr     ebx, 0Ah
0x18007a2ad  jmp     short loc_18007A2B1
0x18007a2af  xor     al, al
0x18007a2b1  test    bl, 40h
0x18007a2b4  jz      short loc_18007A2BA
0x18007a2b6  test    al, al
0x18007a2b8  jnz     short loc_18007A2BD
0x18007a2ba  mov     edi, r13d
0x18007a2bd  mov     eax, [rsi]
0x18007a2bf  or      edi, ebx
0x18007a2c1  mov     r8d, eax
0x18007a2c4  mov     [rsi], eax
0x18007a2c6  cmp     dword ptr [rsp+58h+arg_0], r13d
0x18007a2cb  jz      short loc_18007A302
0x18007a2cd  test    r8b, 2
0x18007a2d1  jnz     short loc_18007A302
0x18007a2d3  xor     eax, edi
0x18007a2d5  mov     edx, edi
0x18007a2d7  and     eax, 180h
0x18007a2dc  xor     eax, r8d
0x18007a2df  mov     ecx, eax
0x18007a2e1  xor     ecx, edi
0x18007a2e3  and     ecx, 40h
0x18007a2e6  xor     ecx, eax
0x18007a2e8  mov     eax, edi
0x18007a2ea  xor     eax, ecx
0x18007a2ec  and     eax, 1
0x18007a2ef  xor     eax, ecx
0x18007a2f1  xor     edx, eax
0x18007a2f3  and     edx, 800h
0x18007a2f9  xor     edx, eax
0x18007a2fb  or      edx, 2
0x18007a2fe  mov     [rsi], edx
0x18007a300  jmp     short loc_18007A305
0x18007a302  mov     edx, r8d
0x18007a305  mov     r9d, r8d
0x18007a308  and     r9d, 4
0x18007a30c  jnz     short loc_18007A321
0x18007a30e  mov     ecx, edi
0x18007a310  xor     ecx, edx
0x18007a312  and     ecx, 400h
0x18007a318  xor     ecx, edx
0x18007a31a  or      ecx, 4
0x18007a31d  mov     [rsi], ecx
0x18007a31f  jmp     short loc_18007A323
0x18007a321  mov     ecx, edx
0x18007a323  mov     eax, r8d
0x18007a326  lock cmpxchg [r14], ecx
0x18007a32b  jnz     short loc_18007A2C1
0x18007a32d  test    r9d, r9d
0x18007a330  jnz     loc_18007A41D
0x18007a336  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007a33c  test    eax, eax
0x18007a33e  jz      loc_18007A41D
0x18007a344  lea     rcx, SRWLock; SRWLock
0x18007a34b  mov     [rsp+58h+var_20], r12
0x18007a350  call    cs:__imp_AcquireSRWLockExclusive
0x18007a357  nop     dword ptr [rax+rax+00h]
0x18007a35c  mov     eax, cs:dword_1800B90D4
0x18007a362  test    ebp, ebp
0x18007a364  jz      loc_18007A400
0x18007a36a  cmp     ebp, eax
0x18007a36c  jnz     loc_18007A400
0x18007a372  mov     r10, cs:Destination
0x18007a379  mov     r8, cs:qword_1800B9118
0x18007a380  mov     rax, r10
0x18007a383  sub     rax, cs:qword_1800B9108
0x18007a38a  mov     rdx, r8
0x18007a38d  sub     rdx, cs:qword_1800B9108
0x18007a394  add     rax, 10h
0x18007a398  mov     [rsp+58h+Source], 3
0x18007a3a1  mov     [rsp+58h+var_30], r14
0x18007a3a6  cmp     rax, rdx
0x18007a3a9  jb      loc_18007A502
0x18007a3af  lea     rax, [rdx+rdx]
0x18007a3b3  mov     ebx, 10h
0x18007a3b8  cmp     rax, rbx
0x18007a3bb  cmova   rbx, rax
0x18007a3bf  cmp     rdx, rbx
0x18007a3c2  jnb     loc_18007A502
0x18007a3c8  call    cs:__imp_GetLastError
0x18007a3cf  nop     dword ptr [rax+rax+00h]
0x18007a3d4  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18007a3d8  xor     ecx, ecx; dwFlags
0x18007a3da  mov     r12d, eax
0x18007a3dd  lea     r15, [rbx+40h]
0x18007a3e1  mov     rdx, r15; dwBytes
0x18007a3e4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18007a3e9  mov     rbx, rax
0x18007a3ec  test    rax, rax
0x18007a3ef  jnz     short loc_18007A46F
0x18007a3f1  mov     ecx, r12d; dwErrCode
0x18007a3f4  call    cs:__imp_SetLastError
0x18007a3fb  nop     dword ptr [rax+rax+00h]
0x18007a400  lock and dword ptr [r14], 0FFFFFFFBh
0x18007a405  lea     rcx, SRWLock; SRWLock
0x18007a40c  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a413  nop     dword ptr [rax+rax+00h]
0x18007a418  mov     r12, [rsp+58h+var_20]
0x18007a41d  mov     ecx, [rsi]
0x18007a41f  mov     r15, [rsp+58h+var_28]
0x18007a424  mov     rbp, [rsp+58h+arg_10]
0x18007a429  mov     rbx, [rsp+58h+arg_8]
0x18007a42e  test    cl, 2
0x18007a431  jnz     short loc_18007A45C
0x18007a433  mov     eax, edi
0x18007a435  xor     eax, ecx
0x18007a437  and     eax, 180h
0x18007a43c  xor     eax, ecx
0x18007a43e  mov     ecx, edi
0x18007a440  xor     ecx, eax
0x18007a442  and     ecx, 40h
0x18007a445  xor     ecx, eax
0x18007a447  mov     eax, edi
0x18007a449  xor     eax, ecx
0x18007a44b  and     eax, 1
0x18007a44e  xor     eax, ecx
0x18007a450  xor     edi, eax
0x18007a452  and     edi, 800h
0x18007a458  xor     edi, eax
0x18007a45a  mov     [rsi], edi
0x18007a45c  mov     rdi, [rsp+58h+arg_18]
0x18007a461  mov     rax, rsi
0x18007a464  add     rsp, 40h
0x18007a468  pop     r14
0x18007a46a  pop     r13
0x18007a46c  pop     rsi
0x18007a46d  retn
0x18007a46f  mov     r8, cs:qword_1800B9108; Source
0x18007a476  mov     rdx, r15; DestinationSize
0x18007a479  mov     rbp, cs:Destination
0x18007a480  mov     rcx, rbx; Destination
0x18007a483  sub     rbp, r8
0x18007a486  mov     r9, rbp; SourceSize
0x18007a489  call    cs:__imp_memcpy_s
0x18007a490  nop     dword ptr [rax+rax+00h]
0x18007a495  mov     r14, cs:lpMem
0x18007a49c  mov     cs:lpMem, rbx
0x18007a4a3  test    r14, r14
0x18007a4a6  jz      short loc_18007A4C8
0x18007a4a8  call    cs:__imp_GetProcessHeap
0x18007a4af  nop     dword ptr [rax+rax+00h]
0x18007a4b4  mov     r8, r14; lpMem
0x18007a4b7  xor     edx, edx; dwFlags
0x18007a4b9  mov     rcx, rax; hHeap
0x18007a4bc  call    cs:__imp_HeapFree
0x18007a4c3  nop     dword ptr [rax+rax+00h]
0x18007a4c8  lea     rax, [rbx+rbp]
0x18007a4cc  mov     cs:qword_1800B9108, rbx
0x18007a4d3  mov     cs:Destination, rax
0x18007a4da  mov     ecx, r12d; dwErrCode
0x18007a4dd  lea     rax, [rbx+r15]
0x18007a4e1  mov     cs:qword_1800B9118, rax
0x18007a4e8  call    cs:__imp_SetLastError
0x18007a4ef  nop     dword ptr [rax+rax+00h]
0x18007a4f4  mov     r8, cs:qword_1800B9118
0x18007a4fb  mov     r10, cs:Destination
0x18007a502  mov     rax, r8
0x18007a505  mov     rdx, r13
0x18007a508  sub     rax, r10
0x18007a50b  mov     r9d, 10h; SourceSize
0x18007a511  cmp     r10, r8
0x18007a514  mov     rcx, r10; Destination
0x18007a517  lea     r8, [rsp+58h+Source]; Source
0x18007a51c  cmovb   rdx, rax; DestinationSize
0x18007a520  call    cs:__imp_memcpy_s
0x18007a527  nop     dword ptr [rax+rax+00h]
0x18007a52c  add     cs:Destination, 10h
0x18007a534  jmp     loc_18007A405
0x18007a539  mov     rax, rsi
0x18007a53c  add     rsp, 40h
0x18007a540  pop     r14
0x18007a542  pop     r13
0x18007a544  pop     rsi
0x18007a545  retn
```
