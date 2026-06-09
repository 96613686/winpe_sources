# RpcGetAllSessions

- ea: `0x180060530`
- end: `0x180060a52`
- name: `RpcGetAllSessions`
- size: `1314`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x18000bd30`
- `0x18000c684`
- `0x18000e8b0`
- `0x18000f260`
- `0x18000f320`
- `0x180013658`
- `0x18001e9d0`
- `0x180022030`
- `0x180022200`
- `0x180023984`
- `0x18004e850`
- `0x18004f354`
- `0x180060530`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800606b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800606b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060a37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060a37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060920`

## string_xrefs

- `0x180060679`: `Impersonate.ImpersonateRpcClient failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetAllSessions(__int64 a1, _DWORD *a2, _QWORD *a3, unsigned int *a4)
{
  unsigned int v7; // edi
  unsigned int v8; // ebx
  int v10; // eax
  volatile unsigned int v11; // r13d
  SIZE_T v12; // rdi
  char *v13; // r14
  int v14; // eax
  int v15; // eax
  unsigned __int64 v16; // rbx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  char *v20; // rdx
  unsigned __int16 *v21; // rax
  __int64 v22; // rcx
  __int16 v23; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  struct ISessionManagerInternal *v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v32; // [rsp+68h] [rbp-98h]
  struct ISessionManagerInternal *v33; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v34[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v35; // [rsp+90h] [rbp-70h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  _BYTE v37[28]; // [rsp+B0h] [rbp-50h]
  int v38; // [rsp+CCh] [rbp-34h]
  unsigned __int16 v39[33]; // [rsp+112h] [rbp+12h] BYREF
  unsigned __int16 v40[70]; // [rsp+154h] [rbp+54h] BYREF
  _BYTE v41[592]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v42[40]; // [rsp+430h] [rbp+330h] BYREF

  v7 = 0;
  v24 = 0;
  v30 = 0;
  v33 = 0;
  v31 = 0;
  v29 = 0;
  v23 = 0;
  v26 = 0;
  pv = 0;
  v28 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v41, 0, "RpcGetAllSessions");
  if ( !a2 || !a3 || !a4 )
    goto LABEL_6;
  *a3 = 0;
  *a4 = 0;
  if ( *a2 > 2u )
  {
    *a2 = 2;
LABEL_6:
    v8 = -2147024809;
    goto LABEL_7;
  }
  v10 = CImpersonate::ImpersonateRpcClient((CImpersonate *)&v23);
  v8 = v10;
  if ( v10 >= 0 )
  {
    v11 = CTSPerfProvider::TotalSessions;
    if ( !CTSPerfProvider::TotalSessions )
    {
      v8 = 0;
      goto LABEL_9;
    }
    v12 = (unsigned int)(348 * CTSPerfProvider::TotalSessions);
    v13 = (char *)LocalAlloc(0x40u, v12);
    if ( v13 )
    {
      v25 = 0;
      ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v25);
      v33 = v25;
      v14 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v25 + 24LL))(v25, &v31);
      v8 = v14;
      if ( v14 >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 32LL))(v31, &v29);
        v8 = v15;
        if ( v15 >= 0 )
        {
          v16 = v12 / 0x15C;
          v32 = v12 / 0x15C;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 88LL))(v29);
          v7 = 0;
          while ( v7 < v11 )
          {
            if ( v7 >= (unsigned int)v16 )
              break;
            SmartPtr<ITSSession>::operator=(&v24, 0);
            v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 80LL))(v29, &v24);
            v8 = v17;
            if ( v17 == -2147024637 )
              break;
            if ( v17 < 0 )
            {
              _DbgPrintMessage(8, "Enum failed: 0x%x in %s", (unsigned int)v17, "RpcGetAllSessions");
              goto LABEL_47;
            }
            v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 136LL))(v24, 1);
            LODWORD(v16) = v32;
            if ( v18 >= 0 )
            {
              memset_0(v34, 0, 0x158u);
              (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v24 + 80LL))(v24, v34);
              v38 = *(_DWORD *)v34;
              LODWORD(v25) = 0;
              (*(void (__fastcall **)(__int64, struct ISessionManagerInternal **))(*(_QWORD *)v24 + 88LL))(v24, &v25);
              *(_DWORD *)&v34[2] = PrivateToPublicState((unsigned int)v25);
              v42[0] = 0;
              (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 104LL))(v24, &v30);
              if ( v30 && (*(int (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v30 + 104LL))(v30, v42) >= 0 )
                StringCchCopyW(&v34[4], 0x21u, v42);
              SmartPtr<IUserName>::operator=(&v26, 0);
              if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 96LL))(v24, &v26) >= 0 )
              {
                if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v26 + 40LL))(v26, &pv) >= 0 )
                  StringCchCopyW(v39, 0x21u, (const unsigned __int16 *)pv);
                if ( (*(int (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v26 + 48LL))(v26, &v28) >= 0 )
                  StringCchCopyW(v40, 0x21u, v28);
                if ( pv )
                {
                  CoTaskMemFree(pv);
                  pv = 0;
                }
                if ( v28 )
                {
                  CoTaskMemFree(v28);
                  v28 = 0;
                }
              }
              v19 = 348LL * v7;
              *(_DWORD *)&v13[v19] = *a2;
              v20 = &v13[v19 + 4];
              if ( *a2 == 1 )
              {
                *(_OWORD *)v20 = *(_OWORD *)v34;
                *((_OWORD *)v20 + 1) = v35;
                *((_OWORD *)v20 + 2) = v36;
                *((_OWORD *)v20 + 3) = *(_OWORD *)v37;
                *(_OWORD *)(v20 + 60) = *(_OWORD *)&v37[12];
              }
              if ( *a2 == 2 )
              {
                v21 = v34;
                v22 = 2;
                do
                {
                  *(_OWORD *)v20 = *(_OWORD *)v21;
                  *((_OWORD *)v20 + 1) = *((_OWORD *)v21 + 1);
                  *((_OWORD *)v20 + 2) = *((_OWORD *)v21 + 2);
                  *((_OWORD *)v20 + 3) = *((_OWORD *)v21 + 3);
                  *((_OWORD *)v20 + 4) = *((_OWORD *)v21 + 4);
                  *((_OWORD *)v20 + 5) = *((_OWORD *)v21 + 5);
                  *((_OWORD *)v20 + 6) = *((_OWORD *)v21 + 6);
                  *((_OWORD *)v20 + 7) = *((_OWORD *)v21 + 7);
                  v20 += 128;
                  v21 += 64;
                  --v22;
                }
                while ( v22 );
                *(_OWORD *)v20 = *(_OWORD *)v21;
                *((_OWORD *)v20 + 1) = *((_OWORD *)v21 + 1);
                *((_OWORD *)v20 + 2) = *((_OWORD *)v21 + 2);
                *((_OWORD *)v20 + 3) = *((_OWORD *)v21 + 3);
                *((_OWORD *)v20 + 4) = *((_OWORD *)v21 + 4);
                *((_QWORD *)v20 + 10) = *((_QWORD *)v21 + 10);
              }
              SmartPtr<ITerminal>::operator=(&v30, 0);
              ++v7;
              LODWORD(v16) = v32;
            }
          }
          v8 = 0;
          *a3 = v13;
          goto LABEL_8;
        }
        _DbgPrintMessage(8, "GetInstanceOfEnum failed: 0x%x in %s", (unsigned int)v15, "RpcGetAllSessions");
      }
      else
      {
        _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", (unsigned int)v14, "RpcGetAllSessions");
      }
LABEL_47:
      LocalFree(v13);
    }
    else
    {
      v8 = -2147024882;
    }
    v7 = 0;
  }
  else
  {
    _DbgPrintMessage(8, "Impersonate.ImpersonateRpcClient failed: 0x%x in %s", v10, "RpcGetAllSessions");
  }
LABEL_7:
  *a3 = 0;
LABEL_8:
  *a4 = v7;
LABEL_9:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v41);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v26);
  CImpersonate::StopImpersonating((CImpersonate *)&v23);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v29);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v31);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v33);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v30);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v24);
  return v8;
}

```

## disassembly

```asm
0x180060530  mov     [rsp-8+arg_0], rbx
0x180060535  push    rbp
0x180060536  push    rsi
0x180060537  push    rdi
0x180060538  push    r12
0x18006053a  push    r13
0x18006053c  push    r14
0x18006053e  push    r15
0x180060540  lea     rbp, [rsp-390h]
0x180060548  sub     rsp, 490h
0x18006054f  mov     rax, cs:__security_cookie
0x180060556  xor     rax, rsp
0x180060559  mov     [rbp+3C0h+var_40], rax
0x180060560  mov     r12, r9
0x180060563  mov     r15, r8
0x180060566  mov     rsi, rdx
0x180060569  xor     edi, edi
0x18006056b  mov     [rsp+4C0h+var_498], rdi
0x180060570  mov     [rsp+4C0h+var_468], rdi
0x180060575  mov     [rsp+4C0h+var_450], rdi
0x18006057a  mov     [rsp+4C0h+var_460], rdi
0x18006057f  mov     [rsp+4C0h+var_470], rdi
0x180060584  mov     [rsp+4C0h+var_4A0], di
0x180060589  mov     [rsp+4C0h+var_488], rdi
0x18006058e  mov     [rsp+4C0h+pv], rdi
0x180060593  mov     [rsp+4C0h+var_478], rdi
0x180060598  lea     r8, aRpcgetallsessi_1; "RpcGetAllSessions"
0x18006059f  xor     edx, edx; int
0x1800605a1  lea     rcx, [rbp+3C0h+var_2E0]; this
0x1800605a8  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x1800605ad  test    rsi, rsi
0x1800605b0  jz      short loc_1800605D2
0x1800605b2  test    r15, r15
0x1800605b5  jz      short loc_1800605D2
0x1800605b7  test    r12, r12
0x1800605ba  jz      short loc_1800605D2
0x1800605bc  mov     [r15], rdi
0x1800605bf  mov     [r12], edi
0x1800605c3  cmp     dword ptr [rsi], 2
0x1800605c6  jbe     loc_18006065F
0x1800605cc  mov     dword ptr [rsi], 2
0x1800605d2  mov     ebx, 80070057h
0x1800605d7  mov     [r15], rdi
0x1800605da  mov     [r12], edi
0x1800605de  lea     rcx, [rbp+3C0h+var_2E0]; this
0x1800605e5  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x1800605ea  lea     rcx, [rsp+4C0h+var_488]
0x1800605ef  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800605f4  nop
0x1800605f5  lea     rcx, [rsp+4C0h+var_4A0]; this
0x1800605fa  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x1800605ff  nop
0x180060600  lea     rcx, [rsp+4C0h+var_470]
0x180060605  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006060a  lea     rcx, [rsp+4C0h+var_460]
0x18006060f  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180060614  lea     rcx, [rsp+4C0h+var_450]
0x180060619  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006061e  lea     rcx, [rsp+4C0h+var_468]
0x180060623  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180060628  lea     rcx, [rsp+4C0h+var_498]
0x18006062d  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180060632  mov     eax, ebx
0x180060634  mov     rcx, [rbp+3C0h+var_40]
0x18006063b  xor     rcx, rsp; StackCookie
0x18006063e  call    __security_check_cookie
0x180060643  mov     rbx, [rsp+4C0h+arg_0]
0x18006064b  add     rsp, 490h
0x180060652  pop     r15
0x180060654  pop     r14
0x180060656  pop     r13
0x180060658  pop     r12
0x18006065a  pop     rdi
0x18006065b  pop     rsi
0x18006065c  pop     rbp
0x18006065d  retn
0x18006065f  lea     rcx, [rsp+4C0h+var_4A0]; this
0x180060664  call    ?ImpersonateRpcClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateRpcClient(void)
0x180060669  mov     ebx, eax
0x18006066b  test    eax, eax
0x18006066d  jns     short loc_18006068F
0x18006066f  lea     r9, aRpcgetallsessi_1; "RpcGetAllSessions"
0x180060676  mov     r8d, eax
0x180060679  lea     rdx, aImpersonateImp_0; "Impersonate.ImpersonateRpcClient failed"...
0x180060680  mov     ecx, 8; int
0x180060685  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006068a  jmp     loc_1800605D7
0x18006068f  mov     r13d, cs:?TotalSessions@CTSPerfProvider@@0JC; long volatile CTSPerfProvider::TotalSessions
0x180060696  test    r13d, r13d
0x180060699  jnz     short loc_1800606A2
0x18006069b  mov     ebx, edi
0x18006069d  jmp     loc_1800605DE
0x1800606a2  imul    eax, r13d, 15Ch
0x1800606a9  mov     edi, eax
0x1800606ab  mov     edx, eax; uBytes
0x1800606ad  mov     ecx, 40h ; '@'; uFlags
0x1800606b2  call    cs:__imp_LocalAlloc
0x1800606b9  nop     dword ptr [rax+rax+00h]
0x1800606be  mov     r14, rax
0x1800606c1  test    rax, rax
0x1800606c4  jnz     short loc_1800606D2
0x1800606c6  mov     ebx, 8007000Eh
0x1800606cb  xor     edi, edi
0x1800606cd  jmp     loc_1800605D7
0x1800606d2  mov     [rsp+4C0h+var_490], 0
0x1800606db  lea     rcx, [rsp+4C0h+var_490]; struct ISessionManagerInternal **
0x1800606e0  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x1800606e5  mov     rcx, [rsp+4C0h+var_490]
0x1800606ea  mov     [rsp+4C0h+var_450], rcx
0x1800606ef  mov     rax, [rcx]
0x1800606f2  lea     rdx, [rsp+4C0h+var_460]
0x1800606f7  mov     rax, [rax+18h]
0x1800606fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060700  mov     ebx, eax
0x180060702  test    eax, eax
0x180060704  jns     short loc_180060712
0x180060706  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x18006070d  jmp     loc_180060A20
0x180060712  mov     rcx, [rsp+4C0h+var_460]
0x180060717  mov     rax, [rcx]
0x18006071a  lea     rdx, [rsp+4C0h+var_470]
0x18006071f  mov     rax, [rax+20h]
0x180060723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060728  mov     ebx, eax
0x18006072a  test    eax, eax
0x18006072c  jns     short loc_18006073A
0x18006072e  lea     rdx, aGetinstanceofe_1; "GetInstanceOfEnum failed: 0x%x in %s"
0x180060735  jmp     loc_180060A20
0x18006073a  mov     rax, 0BC52640BC52640BDh
0x180060744  mul     rdi
0x180060747  mov     rbx, rdx
0x18006074a  shr     rbx, 8
0x18006074e  mov     [rsp+4C0h+var_458], rbx
0x180060753  mov     rcx, [rsp+4C0h+var_470]
0x180060758  mov     rax, [rcx]
0x18006075b  mov     rax, [rax+58h]
0x18006075f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060764  xor     edi, edi
0x180060766  cmp     edi, r13d
0x180060769  jnb     loc_180060A48
0x18006076f  cmp     edi, ebx
0x180060771  jnb     loc_180060A48
0x180060777  xor     edx, edx
0x180060779  lea     rcx, [rsp+4C0h+var_498]
0x18006077e  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x180060783  mov     rcx, [rsp+4C0h+var_470]
0x180060788  mov     rax, [rcx]
0x18006078b  lea     rdx, [rsp+4C0h+var_498]
0x180060790  mov     rax, [rax+50h]
0x180060794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060799  mov     ebx, eax
0x18006079b  cmp     eax, 80070103h
0x1800607a0  jz      loc_180060A48
0x1800607a6  test    eax, eax
0x1800607a8  js      loc_180060A19
0x1800607ae  mov     rcx, [rsp+4C0h+var_498]
0x1800607b3  mov     rax, [rcx]
0x1800607b6  xor     r8d, r8d
0x1800607b9  lea     edx, [r8+1]
0x1800607bd  mov     rax, [rax+88h]
0x1800607c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607c9  test    eax, eax
0x1800607cb  mov     rbx, [rsp+4C0h+var_458]
0x1800607d0  js      short loc_180060766
0x1800607d2  xor     edx, edx; Val
0x1800607d4  mov     r8d, 158h; Size
0x1800607da  lea     rcx, [rbp+3C0h+var_440]; void *
0x1800607de  call    memset_0
0x1800607e3  mov     rcx, [rsp+4C0h+var_498]
0x1800607e8  mov     rax, [rcx]
0x1800607eb  lea     rdx, [rbp+3C0h+var_440]
0x1800607ef  mov     rax, [rax+50h]
0x1800607f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607f8  mov     eax, dword ptr [rbp+3C0h+var_440]
0x1800607fb  mov     [rbp+3C0h+var_3F4], eax
0x1800607fe  xor     ebx, ebx
0x180060800  mov     dword ptr [rsp+4C0h+var_490], ebx
0x180060804  mov     rcx, [rsp+4C0h+var_498]
0x180060809  mov     rax, [rcx]
0x18006080c  lea     rdx, [rsp+4C0h+var_490]
0x180060811  mov     rax, [rax+58h]
0x180060815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006081a  mov     ecx, dword ptr [rsp+4C0h+var_490]
0x18006081e  call    ?PrivateToPublicState@@YAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; PrivateToPublicState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x180060823  mov     dword ptr [rbp+3C0h+var_440+4], eax
0x180060826  mov     [rbp+3C0h+var_90], bx
0x18006082d  mov     rcx, [rsp+4C0h+var_498]
0x180060832  mov     rax, [rcx]
0x180060835  lea     rdx, [rsp+4C0h+var_468]
0x18006083a  mov     rax, [rax+68h]
0x18006083e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060843  mov     rcx, [rsp+4C0h+var_468]
0x180060848  test    rcx, rcx
0x18006084b  jz      short loc_180060877
0x18006084d  mov     rax, [rcx]
0x180060850  lea     rdx, [rbp+3C0h+var_90]
0x180060857  mov     rax, [rax+68h]
0x18006085b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060860  test    eax, eax
0x180060862  js      short loc_180060877
0x180060864  lea     r8, [rbp+3C0h+var_90]; unsigned __int16 *
0x18006086b  lea     edx, [rbx+21h]; unsigned __int64
0x18006086e  lea     rcx, [rbp+3C0h+var_440+8]; unsigned __int16 *
0x180060872  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180060877  xor     edx, edx
0x180060879  lea     rcx, [rsp+4C0h+var_488]
0x18006087e  call    ??4?$SmartPtr@UIUserName@@@@QEAAAEAV0@PEAUIUserName@@@Z; SmartPtr<IUserName>::operator=(IUserName *)
0x180060883  mov     rcx, [rsp+4C0h+var_498]
0x180060888  mov     rax, [rcx]
0x18006088b  lea     rdx, [rsp+4C0h+var_488]
0x180060890  mov     rax, [rax+60h]
0x180060894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060899  test    eax, eax
0x18006089b  js      loc_180060931
0x1800608a1  mov     rcx, [rsp+4C0h+var_488]
0x1800608a6  mov     rax, [rcx]
0x1800608a9  lea     rdx, [rsp+4C0h+pv]
0x1800608ae  mov     rax, [rax+28h]
0x1800608b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800608b7  test    eax, eax
0x1800608b9  js      short loc_1800608CE
0x1800608bb  mov     r8, [rsp+4C0h+pv]; unsigned __int16 *
0x1800608c0  mov     edx, 21h ; '!'; unsigned __int64
0x1800608c5  lea     rcx, [rbp+3C0h+var_3AE]; unsigned __int16 *
0x1800608c9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800608ce  mov     rcx, [rsp+4C0h+var_488]
0x1800608d3  mov     rax, [rcx]
0x1800608d6  lea     rdx, [rsp+4C0h+var_478]
0x1800608db  mov     rax, [rax+30h]
0x1800608df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800608e4  test    eax, eax
0x1800608e6  js      short loc_1800608FB
0x1800608e8  mov     r8, [rsp+4C0h+var_478]; unsigned __int16 *
0x1800608ed  mov     edx, 21h ; '!'; unsigned __int64
0x1800608f2  lea     rcx, [rbp+3C0h+var_36C]; unsigned __int16 *
0x1800608f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800608fb  mov     rcx, [rsp+4C0h+pv]; pv
0x180060900  test    rcx, rcx
0x180060903  jz      short loc_180060916
0x180060905  call    cs:__imp_CoTaskMemFree
0x18006090c  nop     dword ptr [rax+rax+00h]
0x180060911  mov     [rsp+4C0h+pv], rbx
0x180060916  mov     rcx, [rsp+4C0h+var_478]; pv
0x18006091b  test    rcx, rcx
0x18006091e  jz      short loc_180060931
0x180060920  call    cs:__imp_CoTaskMemFree
0x180060927  nop     dword ptr [rax+rax+00h]
0x18006092c  mov     [rsp+4C0h+var_478], rbx
0x180060931  mov     eax, edi
0x180060933  imul    rcx, rax, 15Ch
0x18006093a  mov     eax, [rsi]
0x18006093c  mov     [rcx+r14], eax
0x180060940  lea     rdx, [r14+4]
0x180060944  add     rdx, rcx
0x180060947  cmp     dword ptr [rsi], 1
0x18006094a  jnz     short loc_180060973
0x18006094c  movaps  xmm0, xmmword ptr [rbp+3C0h+var_440]
0x180060950  movups  xmmword ptr [rdx], xmm0
0x180060953  movaps  xmm1, [rbp+3C0h+var_430]
0x180060957  movups  xmmword ptr [rdx+10h], xmm1
0x18006095b  movaps  xmm0, [rbp+3C0h+var_420]
0x18006095f  movups  xmmword ptr [rdx+20h], xmm0
0x180060963  movaps  xmm1, xmmword ptr [rbp+3C0h+var_410]
0x180060967  movups  xmmword ptr [rdx+30h], xmm1
0x18006096b  movups  xmm0, xmmword ptr [rbp+3C0h+var_410+0Ch]
0x18006096f  movups  xmmword ptr [rdx+3Ch], xmm0
0x180060973  cmp     dword ptr [rsi], 2
0x180060976  jnz     loc_180060A01
0x18006097c  lea     rax, [rbp+3C0h+var_440]
0x180060980  mov     ecx, 2
0x180060985  lea     r8d, [rcx+7Eh]
0x180060989  movups  xmm0, xmmword ptr [rax]
0x18006098c  movups  xmmword ptr [rdx], xmm0
0x18006098f  movups  xmm1, xmmword ptr [rax+10h]
0x180060993  movups  xmmword ptr [rdx+10h], xmm1
0x180060997  movups  xmm0, xmmword ptr [rax+20h]
0x18006099b  movups  xmmword ptr [rdx+20h], xmm0
0x18006099f  movups  xmm1, xmmword ptr [rax+30h]
0x1800609a3  movups  xmmword ptr [rdx+30h], xmm1
0x1800609a7  movups  xmm0, xmmword ptr [rax+40h]
0x1800609ab  movups  xmmword ptr [rdx+40h], xmm0
0x1800609af  movups  xmm1, xmmword ptr [rax+50h]
0x1800609b3  movups  xmmword ptr [rdx+50h], xmm1
0x1800609b7  movups  xmm0, xmmword ptr [rax+60h]
0x1800609bb  movups  xmmword ptr [rdx+60h], xmm0
0x1800609bf  movups  xmm1, xmmword ptr [rax+70h]
0x1800609c3  movups  xmmword ptr [rdx+70h], xmm1
0x1800609c7  add     rdx, r8
0x1800609ca  add     rax, r8
0x1800609cd  sub     rcx, 1
0x1800609d1  jnz     short loc_180060989
0x1800609d3  movups  xmm0, xmmword ptr [rax]
0x1800609d6  movups  xmmword ptr [rdx], xmm0
0x1800609d9  movups  xmm1, xmmword ptr [rax+10h]
0x1800609dd  movups  xmmword ptr [rdx+10h], xmm1
0x1800609e1  movups  xmm0, xmmword ptr [rax+20h]
0x1800609e5  movups  xmmword ptr [rdx+20h], xmm0
0x1800609e9  movups  xmm1, xmmword ptr [rax+30h]
0x1800609ed  movups  xmmword ptr [rdx+30h], xmm1
0x1800609f1  movups  xmm0, xmmword ptr [rax+40h]
  ... truncated ...
```
