# RemoteProviderQueryWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180016220`
- end: `0x1800166b0`
- name: `?RemoteProviderQueryWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `1168`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180005924`
- `0x180007500`
- `0x180009590`
- `0x1800153e0`
- `0x180016220`
- `0x1800529dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800162fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001654b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001667f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800162fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001654b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001667f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001641b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001657b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800166a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001641b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001657b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800166a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001627a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001627a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180016455`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180016455`
- `RPCRT4!MesHandleFree` at `0x1800165a3`
- `RPCRT4!MesHandleFree` at `0x1800165a3`
- `RPCRT4!NdrMesTypeDecode3` at `0x1800164d7`
- `RPCRT4!NdrMesTypeDecode3` at `0x1800164d7`
- `RPCRT4!NdrClientCall3` at `0x180016347`
- `RPCRT4!NdrClientCall3` at `0x180016347`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18001647b`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18001647b`

## pseudocode

```c
void __fastcall RemoteProviderQueryWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  signed int Pointer; // ebx
  _DWORD *v6; // rcx
  signed int LastError; // eax
  int v8; // r8d
  _DWORD *v9; // rsi
  RTL_SRWLOCK *v10; // r12
  CLIENT_CALL_RETURN v11; // rax
  int v12; // edx
  int v13; // r8d
  int v14; // eax
  int v15; // r8d
  int v16; // r8d
  signed int ResultUpdateStub; // eax
  void *v18; // rdx
  wil::details *pObject; // [rsp+30h] [rbp-98h] BYREF
  int v20; // [rsp+38h] [rbp-90h]
  handle_t pHandle[3]; // [rsp+40h] [rbp-88h] BYREF
  __int128 UserState; // [rsp+58h] [rbp-70h] BYREF
  __int64 v23; // [rsp+68h] [rbp-60h]
  char *v24; // [rsp+70h] [rbp-58h]
  char *v25; // [rsp+78h] [rbp-50h]
  _DWORD *v26; // [rsp+80h] [rbp-48h]
  _DWORD *v27; // [rsp+D8h] [rbp+10h]

  Pointer = 0;
  pHandle[1] = Context;
  v6 = (_DWORD *)*((_QWORD *)Context + 2);
  v27 = v6;
  pHandle[2] = v6;
  UserState = 0;
  v23 = 0;
  pHandle[0] = 0;
  v26 = v6 + 2;
  if ( v6[2] )
  {
    if ( WaitResult )
    {
      LastError = GetLastError();
      Pointer = LastError;
      if ( LastError > 0 )
        Pointer = (unsigned __int16)LastError | 0x80070000;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)Context,
          v8,
          49,
          &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
          Pointer);
    }
    else
    {
      v10 = (RTL_SRWLOCK *)(Context + 168);
      v24 = Context + 168;
      AcquireSRWLockShared((PSRWLOCK)Context + 21);
      v25 = Context + 176;
      if ( *((_DWORD *)Context + 44) )
      {
        v11.Pointer = NdrClientCall3(
                        (MIDL_STUBLESS_PROXY_INFO *)&stru_180083280,
                        6u,
                        0,
                        Context + 80,
                        &UserState,
                        (char *)&UserState + 8,
                        0).Pointer;
        Pointer = (signed int)v11.Pointer;
        pObject = (wil::details *)v11.Simple;
        v20 = (int)v11.Pointer;
        if ( SLODWORD(v11.Simple) < 0 && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v12,
            v13,
            50,
            &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
            v11.Simple);
      }
      ReleaseSRWLockShared(v10);
      if ( Pointer >= 0 )
      {
        v14 = MesDecodeIncrementalHandleCreate(&UserState, SerializationRead, pHandle);
        if ( v14 >= 1 )
          v14 = (unsigned __int16)v14 | 0x80010000;
        Pointer = v14;
        if ( v14 )
        {
          if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              (int)Context,
              v15,
              52,
              &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
              v14);
        }
        else
        {
          while ( (unsigned int)UserState > (unsigned int)v23 )
          {
            pObject = 0;
            NdrMesTypeDecode3(
              pHandle[0],
              &pPicklingInfo,
              &pProxyInfo,
              (const unsigned int **)&ArrTypeOffset,
              0,
              &pObject);
            if ( !pObject )
            {
              Pointer = -2147418113;
              if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_D(
                  *((_QWORD *)WPP_GLOBAL_Control + 5),
                  (int)Context,
                  v16,
                  54,
                  &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
                  255);
              goto LABEL_7;
            }
            AcquireSRWLockShared(v10);
            if ( *((_DWORD *)Context + 44) )
            {
              if ( *(_DWORD *)pObject )
                ResultUpdateStub = OnQueryResultUpdateStub(
                                     *(unsigned int *)pObject,
                                     *((_QWORD *)pObject + 2),
                                     *((unsigned int *)pObject + 6),
                                     *((_QWORD *)pObject + 4),
                                     Context);
              else
                ResultUpdateStub = OnQueryStateUpdateStub(*((unsigned int *)pObject + 2), 2, Context);
              Pointer = ResultUpdateStub;
            }
            ReleaseSRWLockShared(v10);
            wil::details::FreeProcessHeap(pObject, v18);
          }
        }
      }
    }
    goto LABEL_7;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)Context,
      (int)Wait,
      48,
      &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids);
LABEL_7:
    v9 = v27;
    goto LABEL_8;
  }
  v9 = v6;
LABEL_8:
  if ( Pointer < 0 )
  {
    AcquireSRWLockShared((PSRWLOCK)Context + 21);
    if ( *((_DWORD *)Context + 44) )
      OnQueryStateUpdateStub(2, 2, *((_QWORD *)v9 + 49));
    ReleaseSRWLockShared((PSRWLOCK)Context + 21);
  }
  if ( *((_QWORD *)&UserState + 1) )
    wil::details::FreeProcessHeap(*((wil::details **)&UserState + 1), Context);
  if ( pHandle[0] )
    MesHandleFree(pHandle[0]);
  if ( *v26 )
    SetThreadpoolWait(*((PTP_WAIT *)Context + 19), *((HANDLE *)Context + 9), 0);
}

```

## disassembly

```asm
0x180016220  push    rbx
0x180016222  push    rsi
0x180016223  push    r12
0x180016225  push    r13
0x180016227  push    r14
0x180016229  push    r15
0x18001622b  sub     rsp, 98h
0x180016232  mov     r14, rdx
0x180016235  xor     ebx, ebx
0x180016237  mov     [rsp+0C8h+var_80], rdx
0x18001623c  mov     rcx, [rdx+10h]
0x180016240  mov     [rsp+0C8h+arg_8], rcx
0x180016248  mov     [rsp+0C8h+var_78], rcx
0x18001624d  xorps   xmm0, xmm0
0x180016250  xor     eax, eax
0x180016252  movups  [rsp+0C8h+UserState], xmm0
0x180016257  mov     [rsp+0C8h+var_60], rax
0x18001625c  mov     [rsp+0C8h+pHandle], rax
0x180016261  lea     rax, [rcx+8]
0x180016265  mov     [rsp+0C8h+var_48], rax
0x18001626d  cmp     [rax], ebx
0x18001626f  jz      loc_18001642B
0x180016275  test    r9d, r9d
0x180016278  jz      short loc_1800162ED
0x18001627a  call    cs:__imp_GetLastError
0x180016280  mov     ebx, eax
0x180016282  test    eax, eax
0x180016284  jg      loc_1800165D5
0x18001628a  lea     rsi, WPP_RECORDER_INITIALIZED
0x180016291  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180016298  jnz     loc_1800165E3
0x18001629e  mov     rsi, [rsp+0C8h+arg_8]
0x1800162a6  test    ebx, ebx
0x1800162a8  js      loc_180016675
0x1800162ae  mov     rcx, qword ptr [rsp+0C8h+UserState+8]; this
0x1800162b3  test    rcx, rcx
0x1800162b6  jnz     loc_180016460
0x1800162bc  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x1800162c1  test    rcx, rcx
0x1800162c4  jnz     loc_1800165A3
0x1800162ca  mov     rax, [rsp+0C8h+var_48]
0x1800162d2  cmp     dword ptr [rax], 0
0x1800162d5  jnz     loc_180016447
0x1800162db  add     rsp, 98h
0x1800162e2  pop     r15
0x1800162e4  pop     r14
0x1800162e6  pop     r13
0x1800162e8  pop     r12
0x1800162ea  pop     rsi
0x1800162eb  pop     rbx
0x1800162ec  retn
0x1800162ed  lea     r12, [rdx+0A8h]
0x1800162f4  mov     [rsp+0C8h+var_58], r12
0x1800162f9  mov     rcx, r12; SRWLock
0x1800162fc  call    cs:__imp_AcquireSRWLockShared
0x180016302  lea     r13, [r14+0B0h]
0x180016309  mov     [rsp+0C8h+var_50], r13
0x18001630e  cmp     [r13+0], ebx
0x180016312  jz      loc_180016590
0x180016318  mov     [rsp+0C8h+var_98], 0
0x180016321  lea     r9, [r14+50h]
0x180016325  lea     rax, [rsp+0C8h+UserState+8]
0x18001632a  mov     [rsp+0C8h+pObject], rax
0x18001632f  lea     rax, [rsp+0C8h+UserState]
0x180016334  mov     qword ptr [rsp+0C8h+nTypeIndex], rax
0x180016339  xor     r8d, r8d; pReturnValue
0x18001633c  lea     edx, [r8+6]; nProcNum
0x180016340  lea     rcx, stru_180083280; pProxyInfo
0x180016347  call    cs:__imp_NdrClientCall3
0x18001634d  mov     rbx, rax
0x180016350  mov     [rsp+0C8h+var_98], rax
0x180016355  mov     [rsp+0C8h+var_90], eax
0x180016359  test    eax, eax
0x18001635b  js      short loc_18001636D
0x18001635d  lea     rsi, WPP_RECORDER_INITIALIZED
0x180016364  lea     r15, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x18001636b  jmp     short loc_1800163A3
0x18001636d  lea     rsi, WPP_RECORDER_INITIALIZED
0x180016374  lea     r15, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x18001637b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180016382  jz      short loc_1800163A3
0x180016384  mov     r9d, 32h ; '2'; int
0x18001638a  mov     dword ptr [rsp+0C8h+pObject], eax; char
0x18001638e  mov     qword ptr [rsp+0C8h+nTypeIndex], r15; MessageGuid
0x180016393  mov     rcx, cs:WPP_GLOBAL_Control
0x18001639a  mov     rcx, [rcx+28h]; int
0x18001639e  call    WPP_RECORDER_SF_D
0x1800163a3  jmp     short loc_180016418
0x1800163a5  cmp     eax, 1
0x1800163a8  jl      short loc_1800163B2
0x1800163aa  movzx   eax, ax
0x1800163ad  or      eax, 80010000h
0x1800163b2  mov     ebx, eax
0x1800163b4  mov     [rsp+0C8h+var_90], eax
0x1800163b8  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800163bf  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800163c6  jz      short loc_1800163EE
0x1800163c8  mov     r9d, 33h ; '3'; int
0x1800163ce  mov     dword ptr [rsp+0C8h+pObject], eax; char
0x1800163d2  lea     rax, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x1800163d9  mov     qword ptr [rsp+0C8h+nTypeIndex], rax; MessageGuid
0x1800163de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163e5  mov     rcx, [rcx+28h]; int
0x1800163e9  call    WPP_RECORDER_SF_D
0x1800163ee  lea     rsi, WPP_RECORDER_INITIALIZED
0x1800163f5  lea     r15, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x1800163fc  mov     r14, [rsp+0C8h+var_80]
0x180016401  mov     rax, [rsp+0C8h+var_78]
0x180016406  mov     [rsp+0C8h+arg_8], rax
0x18001640e  mov     r12, [rsp+0C8h+var_58]
0x180016413  mov     r13, [rsp+0C8h+var_50]
0x180016418  mov     rcx, r12; SRWLock
0x18001641b  call    cs:__imp_ReleaseSRWLockShared
0x180016421  test    ebx, ebx
0x180016423  js      loc_18001629E
0x180016429  jmp     short loc_18001646A
0x18001642b  lea     rsi, WPP_RECORDER_INITIALIZED
0x180016432  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180016439  jnz     loc_1800165AE
0x18001643f  mov     rsi, rcx
0x180016442  jmp     loc_1800162A6
0x180016447  xor     r8d, r8d; pftTimeout
0x18001644a  mov     rdx, [r14+48h]; h
0x18001644e  mov     rcx, [r14+98h]; pwa
0x180016455  call    cs:__imp_SetThreadpoolWait
0x18001645b  jmp     loc_1800162DB
0x180016460  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180016465  jmp     loc_1800162BC
0x18001646a  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x18001646f  lea     rdx, ?SerializationRead@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x180016476  lea     rcx, [rsp+0C8h+UserState]; UserState
0x18001647b  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x180016481  cmp     eax, 1
0x180016484  jge     loc_18001661E
0x18001648a  mov     ebx, eax
0x18001648c  test    eax, eax
0x18001648e  jnz     loc_18001662B
0x180016494  mov     eax, dword ptr [rsp+0C8h+UserState]
0x180016498  cmp     eax, dword ptr [rsp+0C8h+var_60]
0x18001649c  jbe     loc_18001629E
0x1800164a2  mov     [rsp+0C8h+var_98], 0
0x1800164ab  lea     rax, [rsp+0C8h+var_98]
0x1800164b0  mov     [rsp+0C8h+pObject], rax; pObject
0x1800164b5  mov     [rsp+0C8h+nTypeIndex], 0; nTypeIndex
0x1800164bd  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800164c4  lea     r8, pProxyInfo; pProxyInfo
0x1800164cb  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800164d2  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x1800164d7  call    cs:__imp_NdrMesTypeDecode3
0x1800164dd  jmp     short loc_18001653C
0x1800164df  mov     [rsp+0C8h+var_98], 0
0x1800164e8  cmp     eax, 1
0x1800164eb  jl      short loc_1800164F5
0x1800164ed  movzx   eax, ax
0x1800164f0  or      eax, 80010000h
0x1800164f5  mov     ebx, eax
0x1800164f7  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800164fe  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180016505  jz      short loc_18001652D
0x180016507  mov     r9d, 35h ; '5'; int
0x18001650d  mov     dword ptr [rsp+0C8h+pObject], eax; char
0x180016511  lea     rax, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x180016518  mov     qword ptr [rsp+0C8h+nTypeIndex], rax; MessageGuid
0x18001651d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016524  mov     rcx, [rcx+28h]; int
0x180016528  call    WPP_RECORDER_SF_D
0x18001652d  mov     r14, [rsp+0C8h+var_80]
0x180016532  mov     rsi, [rsp+0C8h+var_78]
0x180016537  jmp     loc_1800162A6
0x18001653c  cmp     [rsp+0C8h+var_98], 0
0x180016542  jz      loc_180016644
0x180016548  mov     rcx, r12; SRWLock
0x18001654b  call    cs:__imp_AcquireSRWLockShared
0x180016551  cmp     dword ptr [r13+0], 0
0x180016556  jz      short loc_180016578
0x180016558  mov     rax, [rsp+0C8h+var_98]
0x18001655d  cmp     dword ptr [rax], 0
0x180016560  jnz     loc_180016658
0x180016566  mov     r8, r14
0x180016569  mov     edx, 2
0x18001656e  mov     ecx, [rax+8]
0x180016571  call    ?OnQueryStateUpdateStub@@YAJW4_DEV_QUERY_STATE@@W4_DAF_SECONDARY_QUERY_STATE@@PEAX@Z; OnQueryStateUpdateStub(_DEV_QUERY_STATE,_DAF_SECONDARY_QUERY_STATE,void *)
0x180016576  mov     ebx, eax
0x180016578  mov     rcx, r12; SRWLock
0x18001657b  call    cs:__imp_ReleaseSRWLockShared
0x180016581  mov     rcx, [rsp+0C8h+var_98]; this
0x180016586  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001658b  jmp     loc_180016494
0x180016590  lea     rsi, WPP_RECORDER_INITIALIZED
0x180016597  lea     r15, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x18001659e  jmp     loc_180016418
0x1800165a3  call    cs:__imp_MesHandleFree
0x1800165a9  jmp     loc_1800162CA
0x1800165ae  mov     r9d, 30h ; '0'; int
0x1800165b4  lea     r15, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x1800165bb  mov     qword ptr [rsp+0C8h+nTypeIndex], r15; MessageGuid
0x1800165c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165c7  mov     rcx, [rcx+28h]; int
0x1800165cb  call    WPP_RECORDER_SF_
0x1800165d0  jmp     loc_18001629E
0x1800165d5  movzx   ebx, ax
0x1800165d8  or      ebx, 80070000h
0x1800165de  jmp     loc_18001628A
0x1800165e3  mov     r9d, 31h ; '1'
0x1800165e9  mov     dword ptr [rsp+0C8h+pObject], ebx
0x1800165ed  lea     r15, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x1800165f4  jmp     short loc_180016604
0x1800165f6  mov     r9d, 36h ; '6'; int
0x1800165fc  mov     dword ptr [rsp+0C8h+pObject], 8000FFFFh; char
0x180016604  mov     qword ptr [rsp+0C8h+nTypeIndex], r15; MessageGuid
0x180016609  mov     rcx, cs:WPP_GLOBAL_Control
0x180016610  mov     rcx, [rcx+28h]; int
0x180016614  call    WPP_RECORDER_SF_D
0x180016619  jmp     loc_18001629E
0x18001661e  movzx   eax, ax
0x180016621  or      eax, 80010000h
0x180016626  jmp     loc_18001648A
0x18001662b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180016632  jz      loc_18001629E
0x180016638  mov     r9d, 34h ; '4'
0x18001663e  mov     dword ptr [rsp+0C8h+pObject], eax
0x180016642  jmp     short loc_180016604
0x180016644  mov     ebx, 8000FFFFh
0x180016649  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180016650  jz      loc_18001629E
0x180016656  jmp     short loc_1800165F6
0x180016658  mov     qword ptr [rsp+0C8h+nTypeIndex], r14
0x18001665d  mov     r9, [rax+20h]
0x180016661  mov     r8d, [rax+18h]
0x180016665  mov     rdx, [rax+10h]
0x180016669  mov     ecx, [rax]
0x18001666b  call    ?OnQueryResultUpdateStub@@YAJW4_DEV_QUERY_RESULT_ACTION@@PEBGKQEAU_DEVPROPERTY@@PEAX@Z; OnQueryResultUpdateStub(_DEV_QUERY_RESULT_ACTION,ushort const *,ulong,_DEVPROPERTY * const,void *)
0x180016670  jmp     loc_180016576
0x180016675  lea     rbx, [r14+0A8h]
0x18001667c  mov     rcx, rbx; SRWLock
0x18001667f  call    cs:__imp_AcquireSRWLockShared
0x180016685  cmp     dword ptr [r14+0B0h], 0
0x18001668d  jz      short loc_1800166A2
0x18001668f  mov     r8, [rsi+188h]
0x180016696  mov     edx, 2
0x18001669b  mov     ecx, edx
0x18001669d  call    ?OnQueryStateUpdateStub@@YAJW4_DEV_QUERY_STATE@@W4_DAF_SECONDARY_QUERY_STATE@@PEAX@Z; OnQueryStateUpdateStub(_DEV_QUERY_STATE,_DAF_SECONDARY_QUERY_STATE,void *)
0x1800166a2  mov     rcx, rbx; SRWLock
0x1800166a5  call    cs:__imp_ReleaseSRWLockShared
0x1800166ab  jmp     loc_1800162AE
```
