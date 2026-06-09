# RpcGetAllSessions

- ea: `0x18005caf0`
- end: `0x18005cff9`
- name: `RpcGetAllSessions`
- size: `1289`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x18000fa38`
- `0x180014c00`
- `0x180014f40`
- `0x180014ff0`
- `0x180017e00`
- `0x18001aa50`
- `0x18001ee40`
- `0x18001fd20`
- `0x18001fd70`
- `0x180021bc4`
- `0x18004b460`
- `0x18004bf44`
- `0x18005caf0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cc71`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cc71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cfe4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cfe4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ced3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ced3`

## string_xrefs

- `0x18005cc38`: `Impersonate.ImpersonateRpcClient failed: 0x%x in %s`

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
0x18005caf0  mov     [rsp-8+arg_0], rbx
0x18005caf5  push    rbp
0x18005caf6  push    rsi
0x18005caf7  push    rdi
0x18005caf8  push    r12
0x18005cafa  push    r13
0x18005cafc  push    r14
0x18005cafe  push    r15
0x18005cb00  lea     rbp, [rsp-390h]
0x18005cb08  sub     rsp, 490h
0x18005cb0f  mov     rax, cs:__security_cookie
0x18005cb16  xor     rax, rsp
0x18005cb19  mov     [rbp+3C0h+var_40], rax
0x18005cb20  mov     r12, r9
0x18005cb23  mov     r15, r8
0x18005cb26  mov     rsi, rdx
0x18005cb29  xor     edi, edi
0x18005cb2b  mov     [rsp+4C0h+var_498], rdi
0x18005cb30  mov     [rsp+4C0h+var_468], rdi
0x18005cb35  mov     [rsp+4C0h+var_450], rdi
0x18005cb3a  mov     [rsp+4C0h+var_460], rdi
0x18005cb3f  mov     [rsp+4C0h+var_470], rdi
0x18005cb44  mov     [rsp+4C0h+var_4A0], di
0x18005cb49  mov     [rsp+4C0h+var_488], rdi
0x18005cb4e  mov     [rsp+4C0h+pv], rdi
0x18005cb53  mov     [rsp+4C0h+var_478], rdi
0x18005cb58  lea     r8, aRpcgetallsessi_1; "RpcGetAllSessions"
0x18005cb5f  xor     edx, edx; int
0x18005cb61  lea     rcx, [rbp+3C0h+var_2E0]; this
0x18005cb68  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005cb6d  test    rsi, rsi
0x18005cb70  jz      short loc_18005CB92
0x18005cb72  test    r15, r15
0x18005cb75  jz      short loc_18005CB92
0x18005cb77  test    r12, r12
0x18005cb7a  jz      short loc_18005CB92
0x18005cb7c  mov     [r15], rdi
0x18005cb7f  mov     [r12], edi
0x18005cb83  cmp     dword ptr [rsi], 2
0x18005cb86  jbe     loc_18005CC1E
0x18005cb8c  mov     dword ptr [rsi], 2
0x18005cb92  mov     ebx, 80070057h
0x18005cb97  mov     [r15], rdi
0x18005cb9a  mov     [r12], edi
0x18005cb9e  lea     rcx, [rbp+3C0h+var_2E0]; this
0x18005cba5  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005cbaa  lea     rcx, [rsp+4C0h+var_488]
0x18005cbaf  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005cbb4  nop
0x18005cbb5  lea     rcx, [rsp+4C0h+var_4A0]; this
0x18005cbba  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x18005cbbf  nop
0x18005cbc0  lea     rcx, [rsp+4C0h+var_470]
0x18005cbc5  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005cbca  lea     rcx, [rsp+4C0h+var_460]
0x18005cbcf  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005cbd4  lea     rcx, [rsp+4C0h+var_450]
0x18005cbd9  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005cbde  lea     rcx, [rsp+4C0h+var_468]
0x18005cbe3  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005cbe8  lea     rcx, [rsp+4C0h+var_498]
0x18005cbed  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005cbf2  mov     eax, ebx
0x18005cbf4  mov     rcx, [rbp+3C0h+var_40]
0x18005cbfb  xor     rcx, rsp; StackCookie
0x18005cbfe  call    __security_check_cookie
0x18005cc03  mov     rbx, [rsp+4C0h+arg_0]
0x18005cc0b  add     rsp, 490h
0x18005cc12  pop     r15
0x18005cc14  pop     r14
0x18005cc16  pop     r13
0x18005cc18  pop     r12
0x18005cc1a  pop     rdi
0x18005cc1b  pop     rsi
0x18005cc1c  pop     rbp
0x18005cc1d  retn
0x18005cc1e  lea     rcx, [rsp+4C0h+var_4A0]; this
0x18005cc23  call    ?ImpersonateRpcClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateRpcClient(void)
0x18005cc28  mov     ebx, eax
0x18005cc2a  test    eax, eax
0x18005cc2c  jns     short loc_18005CC4E
0x18005cc2e  lea     r9, aRpcgetallsessi_1; "RpcGetAllSessions"
0x18005cc35  mov     r8d, eax
0x18005cc38  lea     rdx, aImpersonateImp_0; "Impersonate.ImpersonateRpcClient failed"...
0x18005cc3f  mov     ecx, 8; int
0x18005cc44  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005cc49  jmp     loc_18005CB97
0x18005cc4e  mov     r13d, cs:?TotalSessions@CTSPerfProvider@@0JC; long volatile CTSPerfProvider::TotalSessions
0x18005cc55  test    r13d, r13d
0x18005cc58  jnz     short loc_18005CC61
0x18005cc5a  mov     ebx, edi
0x18005cc5c  jmp     loc_18005CB9E
0x18005cc61  imul    eax, r13d, 15Ch
0x18005cc68  mov     edi, eax
0x18005cc6a  mov     edx, eax; uBytes
0x18005cc6c  mov     ecx, 40h ; '@'; uFlags
0x18005cc71  call    cs:__imp_LocalAlloc
0x18005cc77  mov     r14, rax
0x18005cc7a  test    rax, rax
0x18005cc7d  jnz     short loc_18005CC8B
0x18005cc7f  mov     ebx, 8007000Eh
0x18005cc84  xor     edi, edi
0x18005cc86  jmp     loc_18005CB97
0x18005cc8b  mov     [rsp+4C0h+var_490], 0
0x18005cc94  lea     rcx, [rsp+4C0h+var_490]; struct ISessionManagerInternal **
0x18005cc99  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18005cc9e  mov     rcx, [rsp+4C0h+var_490]
0x18005cca3  mov     [rsp+4C0h+var_450], rcx
0x18005cca8  mov     rax, [rcx]
0x18005ccab  lea     rdx, [rsp+4C0h+var_460]
0x18005ccb0  mov     rax, [rax+18h]
0x18005ccb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ccb9  mov     ebx, eax
0x18005ccbb  test    eax, eax
0x18005ccbd  jns     short loc_18005CCCB
0x18005ccbf  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x18005ccc6  jmp     loc_18005CFCD
0x18005cccb  mov     rcx, [rsp+4C0h+var_460]
0x18005ccd0  mov     rax, [rcx]
0x18005ccd3  lea     rdx, [rsp+4C0h+var_470]
0x18005ccd8  mov     rax, [rax+20h]
0x18005ccdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cce1  mov     ebx, eax
0x18005cce3  test    eax, eax
0x18005cce5  jns     short loc_18005CCF3
0x18005cce7  lea     rdx, aGetinstanceofe_1; "GetInstanceOfEnum failed: 0x%x in %s"
0x18005ccee  jmp     loc_18005CFCD
0x18005ccf3  mov     rax, 0BC52640BC52640BDh
0x18005ccfd  mul     rdi
0x18005cd00  mov     rbx, rdx
0x18005cd03  shr     rbx, 8
0x18005cd07  mov     [rsp+4C0h+var_458], rbx
0x18005cd0c  mov     rcx, [rsp+4C0h+var_470]
0x18005cd11  mov     rax, [rcx]
0x18005cd14  mov     rax, [rax+58h]
0x18005cd18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd1d  xor     edi, edi
0x18005cd1f  cmp     edi, r13d
0x18005cd22  jnb     loc_18005CFEF
0x18005cd28  cmp     edi, ebx
0x18005cd2a  jnb     loc_18005CFEF
0x18005cd30  xor     edx, edx
0x18005cd32  lea     rcx, [rsp+4C0h+var_498]
0x18005cd37  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x18005cd3c  mov     rcx, [rsp+4C0h+var_470]
0x18005cd41  mov     rax, [rcx]
0x18005cd44  lea     rdx, [rsp+4C0h+var_498]
0x18005cd49  mov     rax, [rax+50h]
0x18005cd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd52  mov     ebx, eax
0x18005cd54  cmp     eax, 80070103h
0x18005cd59  jz      loc_18005CFEF
0x18005cd5f  test    eax, eax
0x18005cd61  js      loc_18005CFC6
0x18005cd67  mov     rcx, [rsp+4C0h+var_498]
0x18005cd6c  mov     rax, [rcx]
0x18005cd6f  xor     r8d, r8d
0x18005cd72  lea     edx, [r8+1]
0x18005cd76  mov     rax, [rax+88h]
0x18005cd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd82  test    eax, eax
0x18005cd84  mov     rbx, [rsp+4C0h+var_458]
0x18005cd89  js      short loc_18005CD1F
0x18005cd8b  xor     edx, edx; Val
0x18005cd8d  mov     r8d, 158h; Size
0x18005cd93  lea     rcx, [rbp+3C0h+var_440]; void *
0x18005cd97  call    memset_0
0x18005cd9c  mov     rcx, [rsp+4C0h+var_498]
0x18005cda1  mov     rax, [rcx]
0x18005cda4  lea     rdx, [rbp+3C0h+var_440]
0x18005cda8  mov     rax, [rax+50h]
0x18005cdac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cdb1  mov     eax, dword ptr [rbp+3C0h+var_440]
0x18005cdb4  mov     [rbp+3C0h+var_3F4], eax
0x18005cdb7  xor     ebx, ebx
0x18005cdb9  mov     dword ptr [rsp+4C0h+var_490], ebx
0x18005cdbd  mov     rcx, [rsp+4C0h+var_498]
0x18005cdc2  mov     rax, [rcx]
0x18005cdc5  lea     rdx, [rsp+4C0h+var_490]
0x18005cdca  mov     rax, [rax+58h]
0x18005cdce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cdd3  mov     ecx, dword ptr [rsp+4C0h+var_490]
0x18005cdd7  call    ?PrivateToPublicState@@YAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; PrivateToPublicState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x18005cddc  mov     dword ptr [rbp+3C0h+var_440+4], eax
0x18005cddf  mov     [rbp+3C0h+var_90], bx
0x18005cde6  mov     rcx, [rsp+4C0h+var_498]
0x18005cdeb  mov     rax, [rcx]
0x18005cdee  lea     rdx, [rsp+4C0h+var_468]
0x18005cdf3  mov     rax, [rax+68h]
0x18005cdf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cdfc  mov     rcx, [rsp+4C0h+var_468]
0x18005ce01  test    rcx, rcx
0x18005ce04  jz      short loc_18005CE30
0x18005ce06  mov     rax, [rcx]
0x18005ce09  lea     rdx, [rbp+3C0h+var_90]
0x18005ce10  mov     rax, [rax+68h]
0x18005ce14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce19  test    eax, eax
0x18005ce1b  js      short loc_18005CE30
0x18005ce1d  lea     r8, [rbp+3C0h+var_90]; unsigned __int16 *
0x18005ce24  lea     edx, [rbx+21h]; unsigned __int64
0x18005ce27  lea     rcx, [rbp+3C0h+var_440+8]; unsigned __int16 *
0x18005ce2b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005ce30  xor     edx, edx
0x18005ce32  lea     rcx, [rsp+4C0h+var_488]
0x18005ce37  call    ??4?$SmartPtr@UIUserName@@@@QEAAAEAV0@PEAUIUserName@@@Z; SmartPtr<IUserName>::operator=(IUserName *)
0x18005ce3c  mov     rcx, [rsp+4C0h+var_498]
0x18005ce41  mov     rax, [rcx]
0x18005ce44  lea     rdx, [rsp+4C0h+var_488]
0x18005ce49  mov     rax, [rax+60h]
0x18005ce4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce52  test    eax, eax
0x18005ce54  js      loc_18005CEDE
0x18005ce5a  mov     rcx, [rsp+4C0h+var_488]
0x18005ce5f  mov     rax, [rcx]
0x18005ce62  lea     rdx, [rsp+4C0h+pv]
0x18005ce67  mov     rax, [rax+28h]
0x18005ce6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce70  test    eax, eax
0x18005ce72  js      short loc_18005CE87
0x18005ce74  mov     r8, [rsp+4C0h+pv]; unsigned __int16 *
0x18005ce79  mov     edx, 21h ; '!'; unsigned __int64
0x18005ce7e  lea     rcx, [rbp+3C0h+var_3AE]; unsigned __int16 *
0x18005ce82  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005ce87  mov     rcx, [rsp+4C0h+var_488]
0x18005ce8c  mov     rax, [rcx]
0x18005ce8f  lea     rdx, [rsp+4C0h+var_478]
0x18005ce94  mov     rax, [rax+30h]
0x18005ce98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce9d  test    eax, eax
0x18005ce9f  js      short loc_18005CEB4
0x18005cea1  mov     r8, [rsp+4C0h+var_478]; unsigned __int16 *
0x18005cea6  mov     edx, 21h ; '!'; unsigned __int64
0x18005ceab  lea     rcx, [rbp+3C0h+var_36C]; unsigned __int16 *
0x18005ceaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005ceb4  mov     rcx, [rsp+4C0h+pv]; pv
0x18005ceb9  test    rcx, rcx
0x18005cebc  jz      short loc_18005CEC9
0x18005cebe  call    cs:__imp_CoTaskMemFree
0x18005cec4  mov     [rsp+4C0h+pv], rbx
0x18005cec9  mov     rcx, [rsp+4C0h+var_478]; pv
0x18005cece  test    rcx, rcx
0x18005ced1  jz      short loc_18005CEDE
0x18005ced3  call    cs:__imp_CoTaskMemFree
0x18005ced9  mov     [rsp+4C0h+var_478], rbx
0x18005cede  mov     eax, edi
0x18005cee0  imul    rcx, rax, 15Ch
0x18005cee7  mov     eax, [rsi]
0x18005cee9  mov     [rcx+r14], eax
0x18005ceed  lea     rdx, [r14+4]
0x18005cef1  add     rdx, rcx
0x18005cef4  cmp     dword ptr [rsi], 1
0x18005cef7  jnz     short loc_18005CF20
0x18005cef9  movaps  xmm0, xmmword ptr [rbp+3C0h+var_440]
0x18005cefd  movups  xmmword ptr [rdx], xmm0
0x18005cf00  movaps  xmm1, [rbp+3C0h+var_430]
0x18005cf04  movups  xmmword ptr [rdx+10h], xmm1
0x18005cf08  movaps  xmm0, [rbp+3C0h+var_420]
0x18005cf0c  movups  xmmword ptr [rdx+20h], xmm0
0x18005cf10  movaps  xmm1, xmmword ptr [rbp+3C0h+var_410]
0x18005cf14  movups  xmmword ptr [rdx+30h], xmm1
0x18005cf18  movups  xmm0, xmmword ptr [rbp+3C0h+var_410+0Ch]
0x18005cf1c  movups  xmmword ptr [rdx+3Ch], xmm0
0x18005cf20  cmp     dword ptr [rsi], 2
0x18005cf23  jnz     loc_18005CFAE
0x18005cf29  lea     rax, [rbp+3C0h+var_440]
0x18005cf2d  mov     ecx, 2
0x18005cf32  lea     r8d, [rcx+7Eh]
0x18005cf36  movups  xmm0, xmmword ptr [rax]
0x18005cf39  movups  xmmword ptr [rdx], xmm0
0x18005cf3c  movups  xmm1, xmmword ptr [rax+10h]
0x18005cf40  movups  xmmword ptr [rdx+10h], xmm1
0x18005cf44  movups  xmm0, xmmword ptr [rax+20h]
0x18005cf48  movups  xmmword ptr [rdx+20h], xmm0
0x18005cf4c  movups  xmm1, xmmword ptr [rax+30h]
0x18005cf50  movups  xmmword ptr [rdx+30h], xmm1
0x18005cf54  movups  xmm0, xmmword ptr [rax+40h]
0x18005cf58  movups  xmmword ptr [rdx+40h], xmm0
0x18005cf5c  movups  xmm1, xmmword ptr [rax+50h]
0x18005cf60  movups  xmmword ptr [rdx+50h], xmm1
0x18005cf64  movups  xmm0, xmmword ptr [rax+60h]
0x18005cf68  movups  xmmword ptr [rdx+60h], xmm0
0x18005cf6c  movups  xmm1, xmmword ptr [rax+70h]
0x18005cf70  movups  xmmword ptr [rdx+70h], xmm1
0x18005cf74  add     rdx, r8
0x18005cf77  add     rax, r8
0x18005cf7a  sub     rcx, 1
0x18005cf7e  jnz     short loc_18005CF36
0x18005cf80  movups  xmm0, xmmword ptr [rax]
0x18005cf83  movups  xmmword ptr [rdx], xmm0
0x18005cf86  movups  xmm1, xmmword ptr [rax+10h]
0x18005cf8a  movups  xmmword ptr [rdx+10h], xmm1
0x18005cf8e  movups  xmm0, xmmword ptr [rax+20h]
0x18005cf92  movups  xmmword ptr [rdx+20h], xmm0
0x18005cf96  movups  xmm1, xmmword ptr [rax+30h]
0x18005cf9a  movups  xmmword ptr [rdx+30h], xmm1
0x18005cf9e  movups  xmm0, xmmword ptr [rax+40h]
0x18005cfa2  movups  xmmword ptr [rdx+40h], xmm0
0x18005cfa6  mov     rax, [rax+50h]
0x18005cfaa  mov     [rdx+50h], rax
  ... truncated ...
```
