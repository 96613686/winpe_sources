# CCscScope::Maintain(_CSC_SCOPE_MAINTAIN)

- ea: `0x18001a340`
- end: `0x18001a9c7`
- name: `?Maintain@CCscScope@@QEAAJW4_CSC_SCOPE_MAINTAIN@@@Z`
- size: `1671`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000a6f0`
- `0x18003ca70`

## callees

- `0x18000a6c8`
- `0x180010ac8`
- `0x18001a340`
- `0x18001b150`
- `0x18001b4e0`
- `0x180030df0`
- `0x1800355bc`
- `0x18003c488`
- `0x18003c4e8`
- `0x18003c560`
- `0x18005b208`
- `0x1800600bc`
- `0x180060160`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a38c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a38c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a46c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a46c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a484`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a484`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a8b0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a8b0`

## pseudocode

```c
__int64 __fastcall CCscScope::Maintain(__int64 a1, int a2)
{
  unsigned int v2; // ebp
  struct _LIST_ENTRY *v3; // rbx
  int v4; // r13d
  struct _LIST_ENTRY *v6; // rdx
  struct _LIST_ENTRY *Flink; // rbx
  __int64 v8; // rsi
  __int64 p_Blink; // r14
  __int64 v10; // r12
  __int64 v11; // r15
  struct _LIST_ENTRY **v12; // rax
  __int64 v13; // rbx
  int v14; // eax
  CObjectMonitor *v15; // r10
  unsigned int v16; // eax
  __int64 v17; // r10
  const unsigned __int16 *v18; // rax
  __int64 v19; // r10
  const unsigned __int16 *v20; // rax
  CCscScope *v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // r10
  const unsigned __int16 *v24; // rax
  const unsigned __int16 *v25; // rax
  int v26; // edx
  const unsigned __int16 *v27; // rax
  __int64 v28; // r10
  __int64 v29; // rdx
  const unsigned __int16 *v30; // rax
  __int64 v31; // r10
  const unsigned __int16 *v32; // rax
  CCscScope *v33; // rcx
  int v34; // ebx
  unsigned int v35; // eax
  __int64 v36; // r10
  bool v37; // zf
  unsigned int v38; // eax
  unsigned int v39; // eax
  __int64 v40; // r10
  const unsigned __int16 *v41; // rax
  __int64 v42; // r10
  const unsigned __int16 *v43; // rax
  CCscScope *v44; // rcx
  unsigned int v45; // eax
  __int64 v46; // r10
  const unsigned __int16 *v47; // rax
  int v48; // edx
  unsigned int v49; // eax
  __int64 v50; // r10
  char v51; // r8
  const unsigned __int16 *ConstBuffer; // rax
  __int64 v53; // r10
  unsigned int v54; // eax
  __int64 v55; // r10
  CRefCounted *v56; // rcx
  struct _LIST_ENTRY *v58; // [rsp+30h] [rbp-78h]
  __int64 v59; // [rsp+38h] [rbp-70h]
  __int64 v60; // [rsp+40h] [rbp-68h]
  struct _LIST_ENTRY *v61; // [rsp+48h] [rbp-60h]
  _QWORD v62[10]; // [rsp+58h] [rbp-50h] BYREF
  int v64; // [rsp+C0h] [rbp+18h]
  __int64 v65; // [rsp+C8h] [rbp+20h] BYREF

  v2 = 0;
  v3 = &stru_1800B6A90;
  v62[0] = &g_AgentAuthInfo;
  v58 = &stru_1800B6A90;
  v4 = 0;
  while ( g_AgentAuthInfo )
  {
    EnterCriticalSection(&stru_1800B6A68);
    v6 = v3;
    Flink = v3->Flink;
    if ( !Flink || Flink == &stru_1800B6A90 )
    {
      v8 = 32;
      v61 = 0;
      v64 = 1;
      v60 = 8;
      p_Blink = 40;
      v65 = 40;
      v10 = 40;
      v59 = 40;
      v11 = 40;
      v13 = 40;
    }
    else
    {
      v61 = Flink - 1;
      if ( Flink != (struct _LIST_ENTRY *)16 )
        _InterlockedIncrement((volatile signed __int32 *)&Flink[-1].Blink);
      v58 = Flink;
      v62[1] = Flink;
      if ( Flink != (struct _LIST_ENTRY *)16 )
        _InterlockedIncrement((volatile signed __int32 *)&Flink[-1].Blink);
      if ( v6 != &stru_1800B6A90 )
        CAuthInfoListIter::_ReleaseEntryReference((CAuthInfoListIter *)v62, v6);
      v8 = (__int64)&Flink[1];
      v64 = 0;
      p_Blink = (__int64)&Flink[1].Blink;
      v65 = (__int64)&Flink[1].Blink;
      v10 = (__int64)&Flink[1].Blink;
      v11 = (__int64)&Flink[1].Blink;
      v59 = (__int64)&Flink[1].Blink;
      v12 = &Flink[-1].Blink;
      v13 = (__int64)&Flink[1].Blink;
      v60 = (__int64)v12;
    }
    LeaveCriticalSection(&stru_1800B6A68);
    v14 = v64;
    if ( v64 )
    {
LABEL_85:
      if ( v14 == 1 )
      {
        v2 = -2147467259;
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          ConstBuffer = CPath::_GetConstBuffer((CPath *)a1);
          WPP_SF_S(*(_QWORD *)(v53 + 16), 37, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, ConstBuffer);
        }
      }
      goto LABEL_92;
    }
    if ( ImpersonateLoggedOnUser(*(HANDLE *)v8) )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        v16 = (unsigned int)CPath::_GetConstBuffer((CPath *)a1);
        WPP_SF_Sd(
          *(_QWORD *)(v17 + 16),
          24,
          (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
          v16,
          *(_DWORD *)p_Blink);
        v15 = WPP_GLOBAL_Control;
      }
      switch ( *(_DWORD *)(a1 + 576) )
      {
        case 1:
LABEL_24:
          if ( v15 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x400) != 0 )
          {
            v18 = CPath::_GetConstBuffer((CPath *)a1);
            WPP_SF_S(*(_QWORD *)(v19 + 16), 29, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, v18);
          }
          v20 = CPath::_GetConstBuffer((CPath *)a1);
          if ( (int)CCscScope::_TransitionSlowLinkOfflineIfRequired(
                      v21,
                      v20,
                      *(unsigned int *)(a1 + 592),
                      *(_QWORD *)(a1 + 584)) < 0 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              v49 = (unsigned int)CPath::_GetConstBuffer((CPath *)a1);
              WPP_SF_SdD(
                *(_QWORD *)(v50 + 16),
                31,
                (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
                v49,
                *(_DWORD *)v59,
                v51);
            }
          }
          else
          {
            LODWORD(v65) = 0;
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              v22 = (unsigned int)CPath::_GetConstBuffer((CPath *)a1);
              WPP_SF_Sd(
                *(_QWORD *)(v23 + 16),
                30,
                (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
                v22,
                *(_DWORD *)v13);
            }
            v2 = 0;
            v4 = 1;
            if ( a2 == 1 )
            {
              v24 = CPath::_GetConstBuffer((CPath *)a1);
              if ( (unsigned __int16)SlowLink_SecondsSinceTransitionToOnline(v24, (unsigned int *)&v65) == 2 )
              {
                v25 = CPath::_GetConstBuffer((CPath *)a1);
                SlowLink_RecordOnlineTransition(v25, v26);
              }
            }
          }
          goto LABEL_81;
        case 2:
          if ( v15 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x400) != 0 )
          {
            v27 = CPath::_GetConstBuffer((CPath *)a1);
            v29 = 36;
LABEL_37:
            WPP_SF_S(*(_QWORD *)(v28 + 16), v29, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, v27);
          }
LABEL_74:
          v4 = 1;
          goto LABEL_81;
        case 3:
          if ( v15 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x400) != 0 )
          {
            v41 = CPath::_GetConstBuffer((CPath *)a1);
            WPP_SF_S(*(_QWORD *)(v42 + 16), 32, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, v41);
          }
          v43 = CPath::_GetConstBuffer((CPath *)a1);
          if ( (int)CCscScope::_TransitionSlowLinkOnlineIfRequired(v44, v43) >= 0 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              v45 = (unsigned int)CPath::_GetConstBuffer((CPath *)a1);
              WPP_SF_Sd(
                *(_QWORD *)(v46 + 16),
                33,
                (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
                v45,
                *(_DWORD *)v11);
            }
            v47 = CPath::_GetConstBuffer((CPath *)a1);
            SlowLink_RecordOnlineTransition(v47, v48);
          }
          goto LABEL_74;
      }
      if ( *(_DWORD *)(a1 + 576) != 4 )
      {
        if ( *(_DWORD *)(a1 + 576) != 5 )
        {
          if ( *(_DWORD *)(a1 + 576) == 6 )
            goto LABEL_24;
LABEL_81:
          RevertToSelf();
          goto LABEL_82;
        }
        if ( v15 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x400) != 0 )
        {
          v27 = CPath::_GetConstBuffer((CPath *)a1);
          v29 = 35;
          goto LABEL_37;
        }
        goto LABEL_74;
      }
      if ( v15 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x400) != 0 )
      {
        v30 = CPath::_GetConstBuffer((CPath *)a1);
        WPP_SF_S(*(_QWORD *)(v31 + 16), 25, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, v30);
      }
      v32 = CPath::_GetConstBuffer((CPath *)a1);
      v34 = CCscScope::_ReconnectPath(v33, v32);
      if ( v34 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          v35 = (unsigned int)CPath::_GetConstBuffer((CPath *)a1);
          WPP_SF_Sd(
            *(_QWORD *)(v36 + 16),
            26,
            (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
            v35,
            *(_DWORD *)v10);
        }
        v2 = 0;
        goto LABEL_74;
      }
      if ( v34 > -1073741623 )
      {
        if ( v34 != -1073741620 && v34 != -1073741300 && v34 != -1073741299 && v34 != -1073741252 )
        {
          v37 = v34 == -1073741247;
          goto LABEL_58;
        }
      }
      else if ( v34 != -1073741623
             && v34 != -1073741816
             && v34 != -1073741643
             && v34 != -1073741636
             && v34 != -1073741634 )
      {
        v37 = v34 == -1073741628;
LABEL_58:
        if ( !v37 )
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            v38 = (unsigned int)CPath::_GetConstBuffer((CPath *)a1);
            WPP_SF_SdD(
              *(_QWORD *)(v50 + 16),
              28,
              (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
              v38,
              *(_DWORD *)v65,
              v34);
          }
          goto LABEL_81;
        }
      }
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        v39 = (unsigned int)CPath::_GetConstBuffer((CPath *)a1);
        WPP_SF_Sd(*(_QWORD *)(v40 + 16), 27, (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, v39, v34);
      }
      v4 = 1;
      v2 = ResultFromNtStatus(v34);
      goto LABEL_81;
    }
LABEL_82:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v60, 0xFFFFFFFF) == 1 )
      ((void (__fastcall *)(struct _LIST_ENTRY *, __int64))v61->Flink->Flink)(v61, 1);
    v14 = 0;
    v3 = v58;
    if ( v4 )
      goto LABEL_85;
  }
  v2 = -2147467259;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    v54 = (unsigned int)CPath::_GetConstBuffer((CPath *)a1);
    WPP_SF_Sd(*(_QWORD *)(v55 + 16), 38, (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, v54, 5);
  }
LABEL_92:
  if ( v58 != &stru_1800B6A90 )
  {
    v56 = (CRefCounted *)((unsigned __int64)&v58[-1] & -(__int64)(v58 != 0));
    if ( v56 )
      CRefCounted::ReleaseReference(v56);
  }
  return v2;
}

```

## disassembly

```asm
0x18001a340  mov     [rsp+arg_0], rbx
0x18001a345  mov     [rsp+arg_8], edx
0x18001a349  push    rbp
0x18001a34a  push    rsi
0x18001a34b  push    rdi
0x18001a34c  push    r12
0x18001a34e  push    r13
0x18001a350  push    r14
0x18001a352  push    r15
0x18001a354  sub     rsp, 70h
0x18001a358  xor     ebp, ebp
0x18001a35a  lea     rax, ?g_AgentAuthInfo@@3VCAuthInfoList@@A; CAuthInfoList g_AgentAuthInfo
0x18001a361  lea     rbx, stru_1800B6A90
0x18001a368  mov     [rsp+0A8h+var_50], rax
0x18001a36d  mov     [rsp+0A8h+var_78], rbx
0x18001a372  xor     r13d, r13d
0x18001a375  mov     rdi, rcx
0x18001a378  cmp     cs:?g_AgentAuthInfo@@3VCAuthInfoList@@A, 0; CAuthInfoList g_AgentAuthInfo
0x18001a37f  jz      loc_18001A93E
0x18001a385  lea     rcx, stru_1800B6A68; lpCriticalSection
0x18001a38c  call    cs:__imp_EnterCriticalSection
0x18001a392  mov     rdx, rbx; struct _LIST_ENTRY *
0x18001a395  mov     rbx, [rbx]
0x18001a398  test    rbx, rbx
0x18001a39b  jz      loc_18001A428
0x18001a3a1  lea     r8, stru_1800B6A90
0x18001a3a8  cmp     rbx, r8
0x18001a3ab  jz      short loc_18001A428
0x18001a3ad  lea     rcx, [rbx-10h]
0x18001a3b1  mov     [rsp+0A8h+var_60], rcx
0x18001a3b6  test    rcx, rcx
0x18001a3b9  jz      short loc_18001A3BF
0x18001a3bb  lock inc dword ptr [rbx-8]
0x18001a3bf  mov     [rsp+0A8h+var_78], rbx
0x18001a3c4  mov     [rsp+0A8h+var_48], rbx
0x18001a3c9  test    rcx, rcx
0x18001a3cc  jz      short loc_18001A3D2
0x18001a3ce  lock inc dword ptr [rbx-8]
0x18001a3d2  cmp     rdx, r8
0x18001a3d5  jz      short loc_18001A3E1
0x18001a3d7  lea     rcx, [rsp+0A8h+var_50]; this
0x18001a3dc  call    ?_ReleaseEntryReference@CAuthInfoListIter@@AEAAXPEAU_LIST_ENTRY@@@Z; CAuthInfoListIter::_ReleaseEntryReference(_LIST_ENTRY *)
0x18001a3e1  xor     eax, eax
0x18001a3e3  lea     rsi, [rbx+10h]
0x18001a3e7  mov     [rsp+0A8h+arg_10], eax
0x18001a3ee  lea     r14, [rbx+18h]
0x18001a3f2  lea     rax, [rbx+18h]
0x18001a3f6  mov     [rsp+0A8h+arg_18], rax
0x18001a3fe  lea     r12, [rbx+18h]
0x18001a402  lea     rax, [rbx+18h]
0x18001a406  mov     [rsp+0A8h+var_58], rax
0x18001a40b  lea     r15, [rbx+18h]
0x18001a40f  lea     rax, [rbx+18h]
0x18001a413  mov     [rsp+0A8h+var_70], rax
0x18001a418  lea     rax, [rbx-8]
0x18001a41c  mov     rbx, [rsp+0A8h+var_58]
0x18001a421  mov     [rsp+0A8h+var_68], rax
0x18001a426  jmp     short loc_18001A465
0x18001a428  mov     esi, 20h ; ' '
0x18001a42d  mov     [rsp+0A8h+var_60], 0
0x18001a436  mov     [rsp+0A8h+arg_10], 1
0x18001a441  mov     [rsp+0A8h+var_68], 8
0x18001a44a  lea     eax, [rsi+8]
0x18001a44d  mov     r14d, eax
0x18001a450  mov     [rsp+0A8h+arg_18], rax
0x18001a458  mov     r12d, eax
0x18001a45b  mov     [rsp+0A8h+var_70], rax
0x18001a460  mov     r15d, eax
0x18001a463  mov     ebx, eax
0x18001a465  lea     rcx, stru_1800B6A68; lpCriticalSection
0x18001a46c  call    cs:__imp_LeaveCriticalSection
0x18001a472  mov     eax, [rsp+0A8h+arg_10]
0x18001a479  test    eax, eax
0x18001a47b  jnz     loc_18001A8F1
0x18001a481  mov     rcx, [rsi]; hToken
0x18001a484  call    cs:__imp_ImpersonateLoggedOnUser
0x18001a48a  test    eax, eax
0x18001a48c  jz      loc_18001A8B6
0x18001a492  mov     r10, cs:WPP_GLOBAL_Control
0x18001a499  lea     rdx, WPP_GLOBAL_Control
0x18001a4a0  mov     esi, 400h
0x18001a4a5  cmp     r10, rdx
0x18001a4a8  jz      short loc_18001A4E6
0x18001a4aa  test    [r10+1Ch], esi
0x18001a4ae  jz      short loc_18001A4E6
0x18001a4b0  mov     rcx, rdi; this
0x18001a4b3  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a4b8  mov     r8d, [r14]
0x18001a4bb  mov     edx, 18h
0x18001a4c0  mov     rcx, [r10+10h]
0x18001a4c4  mov     r9, rax
0x18001a4c7  mov     [rsp+0A8h+var_88], r8d
0x18001a4cc  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18001a4d3  call    WPP_SF_Sd
0x18001a4d8  mov     r10, cs:WPP_GLOBAL_Control
0x18001a4df  lea     rdx, WPP_GLOBAL_Control
0x18001a4e6  mov     ecx, [rdi+240h]
0x18001a4ec  sub     ecx, 1
0x18001a4ef  jz      short loc_18001A51E
0x18001a4f1  sub     ecx, 1
0x18001a4f4  jz      loc_18001A84F
0x18001a4fa  sub     ecx, 1
0x18001a4fd  jz      loc_18001A7B7
0x18001a503  sub     ecx, 1
0x18001a506  jz      loc_18001A648
0x18001a50c  sub     ecx, 1
0x18001a50f  jz      loc_18001A609
0x18001a515  cmp     ecx, 1
0x18001a518  jnz     loc_18001A8B0
0x18001a51e  lea     r14, WPP_GLOBAL_Control
0x18001a525  cmp     r10, r14
0x18001a528  jz      short loc_18001A550
0x18001a52a  test    [r10+1Ch], esi
0x18001a52e  jz      short loc_18001A550
0x18001a530  mov     rcx, rdi; this
0x18001a533  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a538  mov     rcx, [r10+10h]
0x18001a53c  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18001a543  mov     r9, rax
0x18001a546  mov     edx, 1Dh
0x18001a54b  call    WPP_SF_S
0x18001a550  mov     rcx, rdi; this
0x18001a553  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a558  mov     r8d, [rdi+250h]; unsigned __int64
0x18001a55f  mov     rdx, rax; unsigned __int16 *
0x18001a562  mov     r9, [rdi+248h]; unsigned __int64
0x18001a569  call    ?_TransitionSlowLinkOfflineIfRequired@CCscScope@@AEAAJPEBG_K1@Z; CCscScope::_TransitionSlowLinkOfflineIfRequired(ushort const *,unsigned __int64,unsigned __int64)
0x18001a56e  mov     r8d, eax
0x18001a571  test    eax, eax
0x18001a573  js      loc_18001A86C
0x18001a579  mov     dword ptr [rsp+0A8h+arg_18], 0
0x18001a584  mov     r10, cs:WPP_GLOBAL_Control
0x18001a58b  cmp     r10, r14
0x18001a58e  jz      short loc_18001A5BE
0x18001a590  test    [r10+1Ch], esi
0x18001a594  jz      short loc_18001A5BE
0x18001a596  mov     rcx, rdi; this
0x18001a599  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a59e  mov     r8d, [rbx]
0x18001a5a1  mov     edx, 1Eh
0x18001a5a6  mov     rcx, [r10+10h]
0x18001a5aa  mov     r9, rax
0x18001a5ad  mov     [rsp+0A8h+var_88], r8d
0x18001a5b2  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18001a5b9  call    WPP_SF_Sd
0x18001a5be  xor     ebp, ebp
0x18001a5c0  lea     r13d, [rbp+1]
0x18001a5c4  cmp     [rsp+0A8h+arg_8], r13d
0x18001a5cc  jnz     loc_18001A8B0
0x18001a5d2  mov     rcx, rdi; this
0x18001a5d5  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a5da  mov     rcx, rax; unsigned __int16 *
0x18001a5dd  lea     rdx, [rsp+0A8h+arg_18]; unsigned int *
0x18001a5e5  call    ?SlowLink_SecondsSinceTransitionToOnline@@YAJPEBGPEAK@Z; SlowLink_SecondsSinceTransitionToOnline(ushort const *,ulong *)
0x18001a5ea  cmp     ax, 2
0x18001a5ee  jnz     loc_18001A8B0
0x18001a5f4  mov     rcx, rdi; this
0x18001a5f7  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a5fc  mov     rcx, rax; unsigned __int16 *
0x18001a5ff  call    ?SlowLink_RecordOnlineTransition@@YAJPEBGH@Z; SlowLink_RecordOnlineTransition(ushort const *,int)
0x18001a604  jmp     loc_18001A8B0
0x18001a609  lea     r14, WPP_GLOBAL_Control
0x18001a610  cmp     r10, r14
0x18001a613  jz      loc_18001A847
0x18001a619  test    [r10+1Ch], esi
0x18001a61d  jz      loc_18001A847
0x18001a623  mov     rcx, rdi; this
0x18001a626  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a62b  mov     edx, 23h ; '#'
0x18001a630  mov     rcx, [r10+10h]
0x18001a634  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18001a63b  mov     r9, rax
0x18001a63e  call    WPP_SF_S
0x18001a643  jmp     loc_18001A847
0x18001a648  lea     r14, WPP_GLOBAL_Control
0x18001a64f  cmp     r10, r14
0x18001a652  jz      short loc_18001A67A
0x18001a654  test    [r10+1Ch], esi
0x18001a658  jz      short loc_18001A67A
0x18001a65a  mov     rcx, rdi; this
0x18001a65d  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a662  mov     rcx, [r10+10h]
0x18001a666  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18001a66d  mov     r9, rax
0x18001a670  mov     edx, 19h
0x18001a675  call    WPP_SF_S
0x18001a67a  mov     rcx, rdi; this
0x18001a67d  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a682  mov     rdx, rax; unsigned __int16 *
0x18001a685  call    ?_ReconnectPath@CCscScope@@AEAAJPEBG@Z; CCscScope::_ReconnectPath(ushort const *)
0x18001a68a  mov     ebx, eax
0x18001a68c  test    eax, eax
0x18001a68e  js      short loc_18001A6D2
0x18001a690  mov     r10, cs:WPP_GLOBAL_Control
0x18001a697  cmp     r10, r14
0x18001a69a  jz      short loc_18001A6CB
0x18001a69c  test    [r10+1Ch], esi
0x18001a6a0  jz      short loc_18001A6CB
0x18001a6a2  mov     rcx, rdi; this
0x18001a6a5  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a6aa  mov     r8d, [r12]
0x18001a6ae  mov     edx, 1Ah
0x18001a6b3  mov     rcx, [r10+10h]
0x18001a6b7  mov     r9, rax
0x18001a6ba  mov     [rsp+0A8h+var_88], r8d
0x18001a6bf  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18001a6c6  call    WPP_SF_Sd
0x18001a6cb  xor     ebp, ebp
0x18001a6cd  jmp     loc_18001A847
0x18001a6d2  mov     eax, 0C00000C9h
0x18001a6d7  cmp     ebx, eax
0x18001a6d9  jg      short loc_18001A70D
0x18001a6db  jz      loc_18001A76D
0x18001a6e1  cmp     ebx, 0C0000008h
0x18001a6e7  jz      loc_18001A76D
0x18001a6ed  cmp     ebx, 0C00000B5h
0x18001a6f3  jz      short loc_18001A76D
0x18001a6f5  cmp     ebx, 0C00000BCh
0x18001a6fb  jz      short loc_18001A76D
0x18001a6fd  cmp     ebx, 0C00000BEh
0x18001a703  jz      short loc_18001A76D
0x18001a705  cmp     ebx, 0C00000C4h
0x18001a70b  jmp     short loc_18001A733
0x18001a70d  cmp     ebx, 0C00000CCh
0x18001a713  jz      short loc_18001A76D
0x18001a715  cmp     ebx, 0C000020Ch
0x18001a71b  jz      short loc_18001A76D
0x18001a71d  cmp     ebx, 0C000020Dh
0x18001a723  jz      short loc_18001A76D
0x18001a725  cmp     ebx, 0C000023Ch
0x18001a72b  jz      short loc_18001A76D
0x18001a72d  cmp     ebx, 0C0000241h
0x18001a733  jz      short loc_18001A76D
0x18001a735  mov     r10, cs:WPP_GLOBAL_Control
0x18001a73c  cmp     r10, r14
0x18001a73f  jz      loc_18001A8B0
0x18001a745  test    [r10+1Ch], esi
0x18001a749  jz      loc_18001A8B0
0x18001a74f  mov     rcx, rdi; this
0x18001a752  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a757  mov     r8, [rsp+0A8h+arg_18]
0x18001a75f  mov     edx, 1Ch
0x18001a764  mov     [rsp+0A8h+var_80], ebx
0x18001a768  jmp     loc_18001A895
0x18001a76d  mov     r10, cs:WPP_GLOBAL_Control
0x18001a774  cmp     r10, r14
0x18001a777  jz      short loc_18001A7A3
0x18001a779  test    [r10+1Ch], esi
0x18001a77d  jz      short loc_18001A7A3
0x18001a77f  mov     rcx, rdi; this
0x18001a782  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a787  mov     rcx, [r10+10h]
0x18001a78b  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18001a792  mov     r9, rax
0x18001a795  mov     [rsp+0A8h+var_88], ebx
0x18001a799  mov     edx, 1Bh
0x18001a79e  call    WPP_SF_Sd
0x18001a7a3  mov     ecx, ebx; int
0x18001a7a5  mov     r13d, 1
0x18001a7ab  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18001a7b0  mov     ebp, eax
0x18001a7b2  jmp     loc_18001A8B0
0x18001a7b7  lea     r14, WPP_GLOBAL_Control
0x18001a7be  cmp     r10, r14
0x18001a7c1  jz      short loc_18001A7E9
0x18001a7c3  test    [r10+1Ch], esi
0x18001a7c7  jz      short loc_18001A7E9
0x18001a7c9  mov     rcx, rdi; this
0x18001a7cc  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a7d1  mov     rcx, [r10+10h]
0x18001a7d5  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18001a7dc  mov     r9, rax
0x18001a7df  mov     edx, 20h ; ' '
0x18001a7e4  call    WPP_SF_S
0x18001a7e9  mov     rcx, rdi; this
0x18001a7ec  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a7f1  mov     rdx, rax; unsigned __int16 *
0x18001a7f4  call    ?_TransitionSlowLinkOnlineIfRequired@CCscScope@@AEAAJPEBG@Z; CCscScope::_TransitionSlowLinkOnlineIfRequired(ushort const *)
0x18001a7f9  test    eax, eax
0x18001a7fb  js      short loc_18001A847
0x18001a7fd  mov     r10, cs:WPP_GLOBAL_Control
0x18001a804  cmp     r10, r14
0x18001a807  jz      short loc_18001A837
0x18001a809  test    [r10+1Ch], esi
0x18001a80d  jz      short loc_18001A837
0x18001a80f  mov     rcx, rdi; this
0x18001a812  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a817  mov     r8d, [r15]
0x18001a81a  mov     edx, 21h ; '!'
0x18001a81f  mov     rcx, [r10+10h]
0x18001a823  mov     r9, rax
0x18001a826  mov     [rsp+0A8h+var_88], r8d
0x18001a82b  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x18001a832  call    WPP_SF_Sd
0x18001a837  mov     rcx, rdi; this
0x18001a83a  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001a83f  mov     rcx, rax; unsigned __int16 *
0x18001a842  call    ?SlowLink_RecordOnlineTransition@@YAJPEBGH@Z; SlowLink_RecordOnlineTransition(ushort const *,int)
0x18001a847  mov     r13d, 1
0x18001a84d  jmp     short loc_18001A8B0
  ... truncated ...
```
