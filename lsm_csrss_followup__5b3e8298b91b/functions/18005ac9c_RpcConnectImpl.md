# RpcConnectImpl

- ea: `0x18005ac9c`
- end: `0x18005b079`
- name: `RpcConnectImpl`
- size: `989`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18005bc30`
- `0x18005e810`
- `0x18005ecb0`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x18000d0a0`
- `0x180014c00`
- `0x180014f40`
- `0x180014ff0`
- `0x18001fd70`
- `0x180024344`
- `0x1800489c0`
- `0x1800496fc`
- `0x18004b460`
- `0x18005ac9c`
- `0x180097010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18005aed4`
- `RPCRT4!RpcImpersonateClient` at `0x18005aed4`
- `RPCRT4!RpcRevertToSelf` at `0x18005af3a`
- `RPCRT4!RpcRevertToSelf` at `0x18005af3a`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005ad77`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005ad77`

## string_xrefs

- `0x18005aeed`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18005af72`: `Source->AccessCheck( CONNECT ) failed: 0x%x in %s`
- `0x18005af87`: `Target->AccessCheck( DISCONNECT ) failed: 0x%x in %s`

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
0x18005ac9c  mov     [rsp-8+arg_18], rbx
0x18005aca1  push    rbp
0x18005aca2  push    rsi
0x18005aca3  push    rdi
0x18005aca4  push    r12
0x18005aca6  push    r13
0x18005aca8  push    r14
0x18005acaa  push    r15
0x18005acac  lea     rbp, [rsp-1C0h]
0x18005acb4  sub     rsp, 2C0h
0x18005acbb  mov     rax, cs:__security_cookie
0x18005acc2  xor     rax, rsp
0x18005acc5  mov     [rbp+1F0h+var_40], rax
0x18005accc  mov     r12d, r9d
0x18005accf  mov     rsi, r8
0x18005acd2  mov     r14d, edx
0x18005acd5  mov     rbx, rcx
0x18005acd8  xor     r13d, r13d
0x18005acdb  mov     [rsp+2F0h+var_2C0], r13
0x18005ace0  mov     [rsp+2F0h+var_2A8], r13
0x18005ace5  mov     [rsp+2F0h+var_2A0], r13
0x18005acea  mov     [rsp+2F0h+var_2B0], r13
0x18005acef  mov     dword ptr [rsp+2F0h+var_2D0], r13d
0x18005acf4  lea     r15, aRpcconnectimpl_0; "RpcConnectImpl"
0x18005acfb  mov     r8, r15; char *
0x18005acfe  lea     edx, [r13+1]; int
0x18005ad02  lea     rcx, [rsp+2F0h+var_290]; this
0x18005ad07  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005ad0c  nop
0x18005ad0d  test    rbx, rbx
0x18005ad10  jnz     short loc_18005AD35
0x18005ad12  mov     r9, r15
0x18005ad15  lea     r8, aHsession; "hSession"
0x18005ad1c  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005ad23  lea     ecx, [rbx+8]; int
0x18005ad26  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ad2b  mov     edi, 80070057h
0x18005ad30  jmp     loc_18005B017
0x18005ad35  mov     rdx, [rbx+638h]
0x18005ad3c  lea     rcx, [rsp+2F0h+var_2A8]
0x18005ad41  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x18005ad46  mov     rbx, [rsp+2F0h+var_2A8]
0x18005ad4b  mov     rax, [rbx]
0x18005ad4e  lea     rdx, [rsp+2F0h+var_2D0]
0x18005ad53  mov     rcx, rbx
0x18005ad56  mov     rax, [rax+50h]
0x18005ad5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad5f  mov     edi, eax
0x18005ad61  test    eax, eax
0x18005ad63  jns     short loc_18005AD77
0x18005ad65  mov     r9, r15
0x18005ad68  mov     r8d, eax
0x18005ad6b  lea     rdx, aPsourceGetidFa; "pSource->getId failed: 0x%x in %s"
0x18005ad72  jmp     loc_18005B00C
0x18005ad77  call    cs:__imp_WTSGetServiceSessionId
0x18005ad7d  mov     r15d, eax
0x18005ad80  test    r12d, r12d
0x18005ad83  jz      short loc_18005ADAE
0x18005ad85  cmp     dword ptr [rsp+2F0h+var_2D0], eax
0x18005ad89  jz      short loc_18005AD90
0x18005ad8b  cmp     r14d, eax
0x18005ad8e  jnz     short loc_18005ADAE
0x18005ad90  mov     edi, 80070005h
0x18005ad95  mov     r8d, edi
0x18005ad98  lea     rdx, aSomeoneTryingT; "Someone trying to Connect to Session 0:"...
0x18005ad9f  mov     ecx, 8; int
0x18005ada4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ada9  jmp     loc_18005B017
0x18005adae  mov     [rsp+2F0h+var_2C8], r13
0x18005adb3  lea     rcx, [rsp+2F0h+var_2C8]; struct ISessionManagerInternal **
0x18005adb8  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18005adbd  mov     rcx, [rsp+2F0h+var_2C8]
0x18005adc2  mov     [rsp+2F0h+var_2A0], rcx
0x18005adc7  mov     rax, [rcx]
0x18005adca  lea     rdx, [rsp+2F0h+var_2B0]
0x18005adcf  mov     rax, [rax+18h]
0x18005add3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005add8  mov     edi, eax
0x18005adda  test    eax, eax
0x18005addc  jns     short loc_18005ADF4
0x18005adde  lea     r9, aRpcconnectimpl_0; "RpcConnectImpl"
0x18005ade5  mov     r8d, eax
0x18005ade8  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x18005adef  jmp     loc_18005B00C
0x18005adf4  mov     rcx, [rsp+2F0h+var_2B0]
0x18005adf9  mov     rax, [rcx]
0x18005adfc  lea     r8, [rsp+2F0h+var_2C0]
0x18005ae01  mov     edx, r14d
0x18005ae04  mov     rax, [rax+18h]
0x18005ae08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae0d  mov     edi, eax
0x18005ae0f  test    eax, eax
0x18005ae11  jns     short loc_18005AE29
0x18005ae13  lea     r9, aRpcconnectimpl_0; "RpcConnectImpl"
0x18005ae1a  mov     r8d, eax
0x18005ae1d  lea     rdx, aFindsessionbyi_3; "FindSessionById failed: 0x%x in %s"
0x18005ae24  jmp     loc_18005B00C
0x18005ae29  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18005ae30  jz      short loc_18005AE4B
0x18005ae32  mov     r9d, r14d
0x18005ae35  mov     r8d, dword ptr [rsp+2F0h+var_2D0]
0x18005ae3a  lea     rdx, aConnectingSess; "Connecting session %d to terminal of se"...
0x18005ae41  mov     ecx, 2; int
0x18005ae46  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ae4b  mov     [rsp+2F0h+var_2B8], r13d
0x18005ae50  lea     rdx, [rsp+2F0h+var_2B8]; volatile unsigned int *
0x18005ae55  lea     r12, aRpcconnectimpl_0; "RpcConnectImpl"
0x18005ae5c  mov     rcx, r12; char *
0x18005ae5f  call    ?DumpRpcCaller@CRpcUtils@@SAXPEBDAECKAEBU_EVENT_DESCRIPTOR@@@Z; CRpcUtils::DumpRpcCaller(char const *,ulong volatile &,_EVENT_DESCRIPTOR const &)
0x18005ae64  mov     rcx, rbx; struct ITSSession *
0x18005ae67  call    ?CheckCallerCredibility@@YAJPEAUITSSession@@@Z; CheckCallerCredibility(ITSSession *)
0x18005ae6c  mov     edi, eax
0x18005ae6e  test    eax, eax
0x18005ae70  jns     short loc_18005AE81
0x18005ae72  mov     r8d, eax
0x18005ae75  lea     rdx, aCheckcallercre_1; "CheckCallerCredibility failed: 0x%x in "...
0x18005ae7c  jmp     loc_18005B009
0x18005ae81  cmp     eax, 1
0x18005ae84  jz      short loc_18005AE8E
0x18005ae86  mov     r14d, 1
0x18005ae8c  jmp     short loc_18005AE9E
0x18005ae8e  mov     rdx, rsi; unsigned __int16 *
0x18005ae91  mov     rcx, rbx; struct ITSSession *
0x18005ae94  call    ?CheckUserPassword@@YAJPEAUITSSession@@PEBG@Z; CheckUserPassword(ITSSession *,ushort const *)
0x18005ae99  mov     edi, eax
0x18005ae9b  mov     r14d, r13d
0x18005ae9e  test    rsi, rsi
0x18005aea1  jz      short loc_18005AEC2
0x18005aea3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005aea7  inc     rax
0x18005aeaa  cmp     [rsi+rax*2], r13w
0x18005aeaf  jnz     short loc_18005AEA7
0x18005aeb1  add     rax, rax
0x18005aeb4  jz      short loc_18005AEC2
0x18005aeb6  mov     [rsi], r13b
0x18005aeb9  inc     rsi
0x18005aebc  sub     rax, 1
0x18005aec0  jnz     short loc_18005AEB6
0x18005aec2  test    edi, edi
0x18005aec4  jns     short loc_18005AED2
0x18005aec6  lea     rdx, aCheckuserpassw; "CheckUserPassword failed: 0x%x in %s"
0x18005aecd  jmp     loc_18005B006
0x18005aed2  xor     ecx, ecx; BindingHandle
0x18005aed4  call    cs:__imp_RpcImpersonateClient
0x18005aeda  mov     edi, eax
0x18005aedc  test    eax, eax
0x18005aede  jle     short loc_18005AEE9
0x18005aee0  movzx   edi, ax
0x18005aee3  or      edi, 80070000h
0x18005aee9  test    edi, edi
0x18005aeeb  jns     short loc_18005AEF9
0x18005aeed  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18005aef4  jmp     loc_18005B006
0x18005aef9  mov     esi, r13d
0x18005aefc  mov     rax, [rbx]
0x18005aeff  xor     r8d, r8d
0x18005af02  mov     edx, 100h
0x18005af07  mov     rcx, rbx
0x18005af0a  mov     rax, [rax+88h]
0x18005af11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af16  mov     edi, eax
0x18005af18  test    eax, eax
0x18005af1a  js      short loc_18005AF3A
0x18005af1c  mov     rcx, [rsp+2F0h+var_2C0]
0x18005af21  mov     rax, [rcx]
0x18005af24  xor     r8d, r8d
0x18005af27  mov     edx, 200h
0x18005af2c  mov     rax, [rax+88h]
0x18005af33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af38  mov     esi, eax
0x18005af3a  call    cs:__imp_RpcRevertToSelf
0x18005af40  test    eax, eax
0x18005af42  jle     short loc_18005AF4E
0x18005af44  movzx   eax, ax
0x18005af47  or      eax, 80070000h
0x18005af4c  test    eax, eax
0x18005af4e  jns     short loc_18005AF6E
0x18005af50  mov     r8d, eax
0x18005af53  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x18005af5a  mov     ecx, 8; int
0x18005af5f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005af64  mov     edi, 80070005h
0x18005af69  jmp     loc_18005B017
0x18005af6e  test    edi, edi
0x18005af70  jns     short loc_18005AF7E
0x18005af72  lea     rdx, aSourceAccessch; "Source->AccessCheck( CONNECT ) failed: "...
0x18005af79  jmp     loc_18005B006
0x18005af7e  test    esi, esi
0x18005af80  jns     short loc_18005AF90
0x18005af82  mov     edi, esi
0x18005af84  mov     r8d, esi
0x18005af87  lea     rdx, aTargetAccessch_0; "Target->AccessCheck( DISCONNECT ) faile"...
0x18005af8e  jmp     short loc_18005B009
0x18005af90  mov     rcx, rbx
0x18005af93  cmp     dword ptr [rsp+2F0h+var_2D0], r15d
0x18005af98  jz      short loc_18005AFE5
0x18005af9a  mov     dword ptr [rsp+2F0h+var_2C8], r13d
0x18005af9f  mov     rax, [rbx]
0x18005afa2  lea     rdx, [rsp+2F0h+var_2C8]
0x18005afa7  mov     rax, [rax+58h]
0x18005afab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005afb0  mov     edi, eax
0x18005afb2  test    eax, eax
0x18005afb4  jns     short loc_18005AFC2
0x18005afb6  mov     r8d, eax
0x18005afb9  lea     rdx, aPsourceGetstat; "pSource->getState failed: 0x%x in %s"
0x18005afc0  jmp     short loc_18005B009
0x18005afc2  mov     ecx, dword ptr [rsp+2F0h+var_2C8]
0x18005afc6  call    IsLoggedOnState
0x18005afcb  test    eax, eax
0x18005afcd  jnz     short loc_18005AFDD
0x18005afcf  mov     edi, 8007139Fh
0x18005afd4  lea     rdx, aSourceSessionI; "Source session is not active. failed: 0"...
0x18005afdb  jmp     short loc_18005B006
0x18005afdd  mov     r8d, r14d
0x18005afe0  mov     rcx, rbx
0x18005afe3  jmp     short loc_18005AFE8
0x18005afe5  xor     r8d, r8d
0x18005afe8  mov     rax, [rbx]
0x18005afeb  mov     rdx, [rsp+2F0h+var_2C0]
0x18005aff0  mov     rax, [rax+28h]
0x18005aff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aff9  mov     edi, eax
0x18005affb  test    eax, eax
0x18005affd  jns     short loc_18005B017
0x18005afff  lea     rdx, aConnectFailed0; "Connect failed: 0x%x in %s"
0x18005b006  mov     r8d, edi
0x18005b009  mov     r9, r12
0x18005b00c  mov     ecx, 8; int
0x18005b011  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b016  nop
0x18005b017  lea     rcx, [rsp+2F0h+var_290]; this
0x18005b01c  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005b021  nop
0x18005b022  lea     rcx, [rsp+2F0h+var_2B0]
0x18005b027  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005b02c  nop
0x18005b02d  lea     rcx, [rsp+2F0h+var_2A0]
0x18005b032  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005b037  nop
0x18005b038  lea     rcx, [rsp+2F0h+var_2A8]
0x18005b03d  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005b042  nop
0x18005b043  lea     rcx, [rsp+2F0h+var_2C0]
0x18005b048  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005b04d  mov     eax, edi
0x18005b04f  mov     rcx, [rbp+1F0h+var_40]
0x18005b056  xor     rcx, rsp; StackCookie
0x18005b059  call    __security_check_cookie
0x18005b05e  mov     rbx, [rsp+2F0h+arg_18]
0x18005b066  add     rsp, 2C0h
0x18005b06d  pop     r15
0x18005b06f  pop     r14
0x18005b071  pop     r13
0x18005b073  pop     r12
0x18005b075  pop     rdi
0x18005b076  pop     rsi
0x18005b077  pop     rbp
0x18005b078  retn
```
