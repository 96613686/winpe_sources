# RpcConnectImpl

- ea: `0x18005e678`
- end: `0x18005ea68`
- name: `RpcConnectImpl`
- size: `1008`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18005f670`
- `0x180062300`
- `0x1800627a0`

## callees

- `0x1800077a0`
- `0x18000c684`
- `0x18000e8b0`
- `0x18000f260`
- `0x18000f320`
- `0x18001db60`
- `0x180022200`
- `0x180026178`
- `0x18004bc10`
- `0x18004c9ec`
- `0x18004e850`
- `0x18005e678`
- `0x18009c010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18005e8b6`
- `RPCRT4!RpcImpersonateClient` at `0x18005e8b6`
- `RPCRT4!RpcRevertToSelf` at `0x18005e922`
- `RPCRT4!RpcRevertToSelf` at `0x18005e922`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005e753`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005e753`

## string_xrefs

- `0x18005e8d5`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18005e960`: `Source->AccessCheck( CONNECT ) failed: 0x%x in %s`
- `0x18005e975`: `Target->AccessCheck( DISCONNECT ) failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RpcConnectImpl(__int64 a1, unsigned int a2, const unsigned __int16 *a3, int a4)
{
  signed int v8; // edi
  struct ITSSession *v9; // rbx
  int v10; // eax
  int v11; // eax
  int v12; // r15d
  int v13; // eax
  int v14; // eax
  const struct _EVENT_DESCRIPTOR *v15; // r8
  int v16; // eax
  __int64 v17; // r8
  const char *v18; // rdx
  unsigned int v19; // r14d
  __int64 v20; // rax
  __int64 i; // rax
  RPC_STATUS v22; // eax
  int v23; // esi
  int v24; // eax
  bool v25; // sf
  struct ITSSession *v26; // rcx
  int v27; // eax
  __int64 v28; // r8
  __int64 v30; // [rsp+20h] [rbp-E0h] BYREF
  struct ISessionManagerInternal *v31; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v32; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v33; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  struct ITSSession *v35; // [rsp+48h] [rbp-B8h] BYREF
  struct ISessionManagerInternal *v36; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v37[592]; // [rsp+60h] [rbp-A0h] BYREF

  v32 = 0;
  v35 = 0;
  v36 = 0;
  v34 = 0;
  LODWORD(v30) = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v37, 1, "RpcConnectImpl");
  if ( a1 )
  {
    SmartPtr<ITSSession>::operator=(&v35, *(_QWORD *)(a1 + 1592));
    v9 = v35;
    v10 = (*(__int64 (__fastcall **)(struct ITSSession *, __int64 *))(*(_QWORD *)v35 + 80LL))(v35, &v30);
    v8 = v10;
    if ( v10 < 0 )
    {
      _DbgPrintMessage(8, "pSource->getId failed: 0x%x in %s", (unsigned int)v10, "RpcConnectImpl");
      goto LABEL_52;
    }
    v11 = WTSGetServiceSessionId();
    v12 = v11;
    if ( a4 && ((_DWORD)v30 == v11 || a2 == v11) )
    {
      v8 = -2147024891;
      _DbgPrintMessage(8, "Someone trying to Connect to Session 0: 0x%x", -2147024891);
      goto LABEL_52;
    }
    v31 = 0;
    ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v31);
    v36 = v31;
    v13 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v31 + 24LL))(v31, &v34);
    v8 = v13;
    if ( v13 < 0 )
    {
      _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", (unsigned int)v13, "RpcConnectImpl");
      goto LABEL_52;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v34 + 24LL))(v34, a2, &v32);
    v8 = v14;
    if ( v14 < 0 )
    {
      _DbgPrintMessage(8, "FindSessionById failed: 0x%x in %s", (unsigned int)v14, "RpcConnectImpl");
      goto LABEL_52;
    }
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Connecting session %d to terminal of session %d", v30, a2);
    v33 = 0;
    CRpcUtils::DumpRpcCaller((DWORD *)"RpcConnectImpl", &v33, v15);
    v16 = CheckCallerCredibility(v9);
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = (unsigned int)v16;
      v18 = "CheckCallerCredibility failed: 0x%x in %s";
LABEL_51:
      _DbgPrintMessage(8, v18, v17, "RpcConnectImpl", v30);
      goto LABEL_52;
    }
    if ( v16 == 1 )
    {
      v8 = CheckUserPassword(v9, a3);
      v19 = 0;
    }
    else
    {
      v19 = 1;
    }
    if ( a3 )
    {
      v20 = -1;
      do
        ++v20;
      while ( a3[v20] );
      for ( i = 2 * v20; i; --i )
      {
        *(_BYTE *)a3 = 0;
        a3 = (const unsigned __int16 *)((char *)a3 + 1);
      }
    }
    if ( v8 >= 0 )
    {
      v22 = RpcImpersonateClient(0);
      v8 = v22;
      if ( v22 > 0 )
        v8 = (unsigned __int16)v22 | 0x80070000;
      if ( v8 >= 0 )
      {
        v23 = 0;
        v8 = (*(__int64 (__fastcall **)(struct ITSSession *, __int64, _QWORD))(*(_QWORD *)v9 + 136LL))(v9, 256, 0);
        if ( v8 >= 0 )
          v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v32 + 136LL))(v32, 512, 0);
        v24 = RpcRevertToSelf();
        v25 = v24 < 0;
        if ( v24 > 0 )
        {
          v24 = (unsigned __int16)v24 | 0x80070000;
          v25 = v24 < 0;
        }
        if ( v25 )
        {
          _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v24);
          v8 = -2147024891;
          goto LABEL_52;
        }
        if ( v8 >= 0 )
        {
          if ( v23 < 0 )
          {
            v8 = v23;
            v17 = (unsigned int)v23;
            v18 = "Target->AccessCheck( DISCONNECT ) failed: 0x%x in %s";
            goto LABEL_51;
          }
          v26 = v9;
          if ( (_DWORD)v30 == v12 )
          {
            v28 = 0;
          }
          else
          {
            LODWORD(v31) = 0;
            v27 = (*(__int64 (__fastcall **)(struct ITSSession *, struct ISessionManagerInternal **))(*(_QWORD *)v9 + 88LL))(
                    v9,
                    &v31);
            v8 = v27;
            if ( v27 < 0 )
            {
              v17 = (unsigned int)v27;
              v18 = "pSource->getState failed: 0x%x in %s";
              goto LABEL_51;
            }
            if ( !(unsigned int)IsLoggedOnState((unsigned int)v31) )
            {
              v8 = -2147019873;
              v18 = "Source session is not active. failed: 0x%x in %s";
              goto LABEL_50;
            }
            v28 = v19;
            v26 = v9;
          }
          v8 = (*(__int64 (__fastcall **)(struct ITSSession *, __int64, __int64))(*(_QWORD *)v9 + 40LL))(v26, v32, v28);
          if ( v8 >= 0 )
            goto LABEL_52;
          v18 = "Connect failed: 0x%x in %s";
          goto LABEL_50;
        }
        v18 = "Source->AccessCheck( CONNECT ) failed: 0x%x in %s";
      }
      else
      {
        v18 = "RpcImpersonateClient failed: 0x%x in %s";
      }
    }
    else
    {
      v18 = "CheckUserPassword failed: 0x%x in %s";
    }
LABEL_50:
    v17 = (unsigned int)v8;
    goto LABEL_51;
  }
  _DbgPrintMessage(8, "Missing paramter %s in %s", "hSession", "RpcConnectImpl");
  v8 = -2147024809;
LABEL_52:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v37);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v34);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v36);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v35);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v32);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005e678  mov     [rsp-8+arg_18], rbx
0x18005e67d  push    rbp
0x18005e67e  push    rsi
0x18005e67f  push    rdi
0x18005e680  push    r12
0x18005e682  push    r13
0x18005e684  push    r14
0x18005e686  push    r15
0x18005e688  lea     rbp, [rsp-1C0h]
0x18005e690  sub     rsp, 2C0h
0x18005e697  mov     rax, cs:__security_cookie
0x18005e69e  xor     rax, rsp
0x18005e6a1  mov     [rbp+1F0h+var_40], rax
0x18005e6a8  mov     r12d, r9d
0x18005e6ab  mov     rsi, r8
0x18005e6ae  mov     r14d, edx
0x18005e6b1  mov     rbx, rcx
0x18005e6b4  xor     r13d, r13d
0x18005e6b7  mov     [rsp+2F0h+var_2C0], r13
0x18005e6bc  mov     [rsp+2F0h+var_2A8], r13
0x18005e6c1  mov     [rsp+2F0h+var_2A0], r13
0x18005e6c6  mov     [rsp+2F0h+var_2B0], r13
0x18005e6cb  mov     dword ptr [rsp+2F0h+var_2D0], r13d
0x18005e6d0  lea     r15, aRpcconnectimpl_0; "RpcConnectImpl"
0x18005e6d7  mov     r8, r15; char *
0x18005e6da  lea     edx, [r13+1]; int
0x18005e6de  lea     rcx, [rsp+2F0h+var_290]; this
0x18005e6e3  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005e6e8  nop
0x18005e6e9  test    rbx, rbx
0x18005e6ec  jnz     short loc_18005E711
0x18005e6ee  mov     r9, r15
0x18005e6f1  lea     r8, aHsession; "hSession"
0x18005e6f8  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005e6ff  lea     ecx, [rbx+8]; int
0x18005e702  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e707  mov     edi, 80070057h
0x18005e70c  jmp     loc_18005EA05
0x18005e711  mov     rdx, [rbx+638h]
0x18005e718  lea     rcx, [rsp+2F0h+var_2A8]
0x18005e71d  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x18005e722  mov     rbx, [rsp+2F0h+var_2A8]
0x18005e727  mov     rax, [rbx]
0x18005e72a  lea     rdx, [rsp+2F0h+var_2D0]
0x18005e72f  mov     rcx, rbx
0x18005e732  mov     rax, [rax+50h]
0x18005e736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e73b  mov     edi, eax
0x18005e73d  test    eax, eax
0x18005e73f  jns     short loc_18005E753
0x18005e741  mov     r9, r15
0x18005e744  mov     r8d, eax
0x18005e747  lea     rdx, aPsourceGetidFa; "pSource->getId failed: 0x%x in %s"
0x18005e74e  jmp     loc_18005E9FA
0x18005e753  call    cs:__imp_WTSGetServiceSessionId
0x18005e75a  nop     dword ptr [rax+rax+00h]
0x18005e75f  mov     r15d, eax
0x18005e762  test    r12d, r12d
0x18005e765  jz      short loc_18005E790
0x18005e767  cmp     dword ptr [rsp+2F0h+var_2D0], eax
0x18005e76b  jz      short loc_18005E772
0x18005e76d  cmp     r14d, eax
0x18005e770  jnz     short loc_18005E790
0x18005e772  mov     edi, 80070005h
0x18005e777  mov     r8d, edi
0x18005e77a  lea     rdx, aSomeoneTryingT; "Someone trying to Connect to Session 0:"...
0x18005e781  mov     ecx, 8; int
0x18005e786  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e78b  jmp     loc_18005EA05
0x18005e790  mov     [rsp+2F0h+var_2C8], r13
0x18005e795  lea     rcx, [rsp+2F0h+var_2C8]; struct ISessionManagerInternal **
0x18005e79a  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18005e79f  mov     rcx, [rsp+2F0h+var_2C8]
0x18005e7a4  mov     [rsp+2F0h+var_2A0], rcx
0x18005e7a9  mov     rax, [rcx]
0x18005e7ac  lea     rdx, [rsp+2F0h+var_2B0]
0x18005e7b1  mov     rax, [rax+18h]
0x18005e7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7ba  mov     edi, eax
0x18005e7bc  test    eax, eax
0x18005e7be  jns     short loc_18005E7D6
0x18005e7c0  lea     r9, aRpcconnectimpl_0; "RpcConnectImpl"
0x18005e7c7  mov     r8d, eax
0x18005e7ca  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x18005e7d1  jmp     loc_18005E9FA
0x18005e7d6  mov     rcx, [rsp+2F0h+var_2B0]
0x18005e7db  mov     rax, [rcx]
0x18005e7de  lea     r8, [rsp+2F0h+var_2C0]
0x18005e7e3  mov     edx, r14d
0x18005e7e6  mov     rax, [rax+18h]
0x18005e7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7ef  mov     edi, eax
0x18005e7f1  test    eax, eax
0x18005e7f3  jns     short loc_18005E80B
0x18005e7f5  lea     r9, aRpcconnectimpl_0; "RpcConnectImpl"
0x18005e7fc  mov     r8d, eax
0x18005e7ff  lea     rdx, aFindsessionbyi_3; "FindSessionById failed: 0x%x in %s"
0x18005e806  jmp     loc_18005E9FA
0x18005e80b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18005e812  jz      short loc_18005E82D
0x18005e814  mov     r9d, r14d
0x18005e817  mov     r8d, dword ptr [rsp+2F0h+var_2D0]
0x18005e81c  lea     rdx, aConnectingSess; "Connecting session %d to terminal of se"...
0x18005e823  mov     ecx, 2; int
0x18005e828  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e82d  mov     [rsp+2F0h+var_2B8], r13d
0x18005e832  lea     rdx, [rsp+2F0h+var_2B8]; volatile unsigned int *
0x18005e837  lea     r12, aRpcconnectimpl_0; "RpcConnectImpl"
0x18005e83e  mov     rcx, r12; char *
0x18005e841  call    ?DumpRpcCaller@CRpcUtils@@SAXPEBDAECKAEBU_EVENT_DESCRIPTOR@@@Z; CRpcUtils::DumpRpcCaller(char const *,ulong volatile &,_EVENT_DESCRIPTOR const &)
0x18005e846  mov     rcx, rbx; struct ITSSession *
0x18005e849  call    ?CheckCallerCredibility@@YAJPEAUITSSession@@@Z; CheckCallerCredibility(ITSSession *)
0x18005e84e  mov     edi, eax
0x18005e850  test    eax, eax
0x18005e852  jns     short loc_18005E863
0x18005e854  mov     r8d, eax
0x18005e857  lea     rdx, aCheckcallercre_1; "CheckCallerCredibility failed: 0x%x in "...
0x18005e85e  jmp     loc_18005E9F7
0x18005e863  cmp     eax, 1
0x18005e866  jz      short loc_18005E870
0x18005e868  mov     r14d, 1
0x18005e86e  jmp     short loc_18005E880
0x18005e870  mov     rdx, rsi; unsigned __int16 *
0x18005e873  mov     rcx, rbx; struct ITSSession *
0x18005e876  call    ?CheckUserPassword@@YAJPEAUITSSession@@PEBG@Z; CheckUserPassword(ITSSession *,ushort const *)
0x18005e87b  mov     edi, eax
0x18005e87d  mov     r14d, r13d
0x18005e880  test    rsi, rsi
0x18005e883  jz      short loc_18005E8A4
0x18005e885  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005e889  inc     rax
0x18005e88c  cmp     [rsi+rax*2], r13w
0x18005e891  jnz     short loc_18005E889
0x18005e893  add     rax, rax
0x18005e896  jz      short loc_18005E8A4
0x18005e898  mov     [rsi], r13b
0x18005e89b  inc     rsi
0x18005e89e  sub     rax, 1
0x18005e8a2  jnz     short loc_18005E898
0x18005e8a4  test    edi, edi
0x18005e8a6  jns     short loc_18005E8B4
0x18005e8a8  lea     rdx, aCheckuserpassw; "CheckUserPassword failed: 0x%x in %s"
0x18005e8af  jmp     loc_18005E9F4
0x18005e8b4  xor     ecx, ecx; BindingHandle
0x18005e8b6  call    cs:__imp_RpcImpersonateClient
0x18005e8bd  nop     dword ptr [rax+rax+00h]
0x18005e8c2  mov     edi, eax
0x18005e8c4  test    eax, eax
0x18005e8c6  jle     short loc_18005E8D1
0x18005e8c8  movzx   edi, ax
0x18005e8cb  or      edi, 80070000h
0x18005e8d1  test    edi, edi
0x18005e8d3  jns     short loc_18005E8E1
0x18005e8d5  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18005e8dc  jmp     loc_18005E9F4
0x18005e8e1  mov     esi, r13d
0x18005e8e4  mov     rax, [rbx]
0x18005e8e7  xor     r8d, r8d
0x18005e8ea  mov     edx, 100h
0x18005e8ef  mov     rcx, rbx
0x18005e8f2  mov     rax, [rax+88h]
0x18005e8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8fe  mov     edi, eax
0x18005e900  test    eax, eax
0x18005e902  js      short loc_18005E922
0x18005e904  mov     rcx, [rsp+2F0h+var_2C0]
0x18005e909  mov     rax, [rcx]
0x18005e90c  xor     r8d, r8d
0x18005e90f  mov     edx, 200h
0x18005e914  mov     rax, [rax+88h]
0x18005e91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e920  mov     esi, eax
0x18005e922  call    cs:__imp_RpcRevertToSelf
0x18005e929  nop     dword ptr [rax+rax+00h]
0x18005e92e  test    eax, eax
0x18005e930  jle     short loc_18005E93C
0x18005e932  movzx   eax, ax
0x18005e935  or      eax, 80070000h
0x18005e93a  test    eax, eax
0x18005e93c  jns     short loc_18005E95C
0x18005e93e  mov     r8d, eax
0x18005e941  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x18005e948  mov     ecx, 8; int
0x18005e94d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e952  mov     edi, 80070005h
0x18005e957  jmp     loc_18005EA05
0x18005e95c  test    edi, edi
0x18005e95e  jns     short loc_18005E96C
0x18005e960  lea     rdx, aSourceAccessch; "Source->AccessCheck( CONNECT ) failed: "...
0x18005e967  jmp     loc_18005E9F4
0x18005e96c  test    esi, esi
0x18005e96e  jns     short loc_18005E97E
0x18005e970  mov     edi, esi
0x18005e972  mov     r8d, esi
0x18005e975  lea     rdx, aTargetAccessch_0; "Target->AccessCheck( DISCONNECT ) faile"...
0x18005e97c  jmp     short loc_18005E9F7
0x18005e97e  mov     rcx, rbx
0x18005e981  cmp     dword ptr [rsp+2F0h+var_2D0], r15d
0x18005e986  jz      short loc_18005E9D3
0x18005e988  mov     dword ptr [rsp+2F0h+var_2C8], r13d
0x18005e98d  mov     rax, [rbx]
0x18005e990  lea     rdx, [rsp+2F0h+var_2C8]
0x18005e995  mov     rax, [rax+58h]
0x18005e999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e99e  mov     edi, eax
0x18005e9a0  test    eax, eax
0x18005e9a2  jns     short loc_18005E9B0
0x18005e9a4  mov     r8d, eax
0x18005e9a7  lea     rdx, aPsourceGetstat; "pSource->getState failed: 0x%x in %s"
0x18005e9ae  jmp     short loc_18005E9F7
0x18005e9b0  mov     ecx, dword ptr [rsp+2F0h+var_2C8]
0x18005e9b4  call    IsLoggedOnState
0x18005e9b9  test    eax, eax
0x18005e9bb  jnz     short loc_18005E9CB
0x18005e9bd  mov     edi, 8007139Fh
0x18005e9c2  lea     rdx, aSourceSessionI; "Source session is not active. failed: 0"...
0x18005e9c9  jmp     short loc_18005E9F4
0x18005e9cb  mov     r8d, r14d
0x18005e9ce  mov     rcx, rbx
0x18005e9d1  jmp     short loc_18005E9D6
0x18005e9d3  xor     r8d, r8d
0x18005e9d6  mov     rax, [rbx]
0x18005e9d9  mov     rdx, [rsp+2F0h+var_2C0]
0x18005e9de  mov     rax, [rax+28h]
0x18005e9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9e7  mov     edi, eax
0x18005e9e9  test    eax, eax
0x18005e9eb  jns     short loc_18005EA05
0x18005e9ed  lea     rdx, aConnectFailed0; "Connect failed: 0x%x in %s"
0x18005e9f4  mov     r8d, edi
0x18005e9f7  mov     r9, r12
0x18005e9fa  mov     ecx, 8; int
0x18005e9ff  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ea04  nop
0x18005ea05  lea     rcx, [rsp+2F0h+var_290]; this
0x18005ea0a  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005ea0f  nop
0x18005ea10  lea     rcx, [rsp+2F0h+var_2B0]
0x18005ea15  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005ea1a  nop
0x18005ea1b  lea     rcx, [rsp+2F0h+var_2A0]
0x18005ea20  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005ea25  nop
0x18005ea26  lea     rcx, [rsp+2F0h+var_2A8]
0x18005ea2b  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005ea30  nop
0x18005ea31  lea     rcx, [rsp+2F0h+var_2C0]
0x18005ea36  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005ea3b  mov     eax, edi
0x18005ea3d  mov     rcx, [rbp+1F0h+var_40]
0x18005ea44  xor     rcx, rsp; StackCookie
0x18005ea47  call    __security_check_cookie
0x18005ea4c  mov     rbx, [rsp+2F0h+arg_18]
0x18005ea54  add     rsp, 2C0h
0x18005ea5b  pop     r15
0x18005ea5d  pop     r14
0x18005ea5f  pop     r13
0x18005ea61  pop     r12
0x18005ea63  pop     rdi
0x18005ea64  pop     rsi
0x18005ea65  pop     rbp
0x18005ea66  retn
```
