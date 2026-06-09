# RpcTerminateSession

- ea: `0x18005bab0`
- end: `0x18005bcde`
- name: `RpcTerminateSession`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800077a0`
- `0x18000c684`
- `0x18000e8b0`
- `0x18000f260`
- `0x18000f320`
- `0x18004e850`
- `0x18005bab0`
- `0x18009c010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18005bb9d`
- `RPCRT4!RpcImpersonateClient` at `0x18005bb9d`
- `RPCRT4!RpcRevertToSelf` at `0x18005bc00`
- `RPCRT4!RpcRevertToSelf` at `0x18005bc00`

## string_xrefs

- `0x18005bbed`: `AccessCheckEx failed: 0x%X`
- `0x18005bbb2`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18005bc19`: `AccessCheckEx failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcTerminateSession(__int64 a1, unsigned int a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  const char *v5; // rdx
  int v6; // eax
  int v7; // edi
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  struct ISessionManagerInternal *v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[592]; // [rsp+60h] [rbp-A0h] BYREF

  v12 = 0;
  v13 = 0;
  v9 = 0;
  v11 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v14, 1, "RpcTerminateSession");
  v10 = 0;
  ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v10);
  v3 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v10 + 24LL))(v10, &v12);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "GetSessionList failed: 0x%x in %s";
LABEL_18:
    _DbgPrintMessage(8, v5, (unsigned int)v3, "RpcTerminateSession");
    goto LABEL_19;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 24LL))(v12, a2, &v9);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "FindSessionById failed: 0x%x in %s";
    goto LABEL_18;
  }
  if ( v9 )
  {
    if ( RpcImpersonateClient(0) )
    {
      v4 = -2147024891;
      _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", 2147942405LL, "RpcTerminateSession");
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v9 + 144LL))(v9, 4, 0);
      v7 = v6;
      v4 = -2147024891;
      if ( v6 < 0 )
      {
        _DbgPrintMessage(8, "AccessCheckEx failed: 0x%X", v6);
        v7 = -2147024891;
      }
      if ( RpcRevertToSelf() || (v4 = v7, v7 < 0) )
      {
        _DbgPrintMessage(8, "AccessCheckEx failed: 0x%x in %s", v4, "RpcTerminateSession");
      }
      else
      {
        v3 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v9)(v9, qword_1800A7960, &v11);
        v4 = v3;
        if ( v3 < 0 )
        {
          v5 = "QI on IID_ITSSessionPrivate failed: 0x%x in %s";
          goto LABEL_18;
        }
        v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 576LL))(v11, 2);
        v4 = v3;
        if ( v3 < 0 )
        {
          v5 = "ptrPrivateSession->Logoff failed: 0x%x in %s";
          goto LABEL_18;
        }
      }
    }
  }
  else
  {
    v4 = -2147024894;
    _DbgPrintMessage(8, "NULL == ptrSession failed: 0x%x in %s", 2147942402LL, "RpcTerminateSession");
  }
LABEL_19:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v14);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v11);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v9);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v13);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v12);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v10);
  return v4;
}

```

## disassembly

```asm
0x18005bab0  push    rbp
0x18005bab2  push    rbx
0x18005bab3  push    rdi
0x18005bab4  push    r14
0x18005bab6  lea     rbp, [rsp-1C8h]
0x18005babe  sub     rsp, 2C8h
0x18005bac5  mov     rax, cs:__security_cookie
0x18005bacc  xor     rax, rsp
0x18005bacf  mov     [rbp+1E0h+var_30], rax
0x18005bad6  mov     edi, edx
0x18005bad8  mov     [rsp+2E0h+var_298], 0
0x18005bae1  lea     r14, aRpcterminatese; "RpcTerminateSession"
0x18005bae8  mov     [rsp+2E0h+var_290], 0
0x18005baf1  mov     r8, r14; char *
0x18005baf4  mov     [rsp+2E0h+var_2B0], 0
0x18005bafd  mov     edx, 1; int
0x18005bb02  mov     [rsp+2E0h+var_2A0], 0
0x18005bb0b  lea     rcx, [rsp+2E0h+var_280]; this
0x18005bb10  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005bb15  lea     rcx, [rsp+2E0h+var_2A8]; struct ISessionManagerInternal **
0x18005bb1a  mov     [rsp+2E0h+var_2A8], 0
0x18005bb23  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18005bb28  mov     rcx, [rsp+2E0h+var_2A8]
0x18005bb2d  lea     rdx, [rsp+2E0h+var_298]
0x18005bb32  mov     [rsp+2E0h+var_2A8], rcx
0x18005bb37  mov     rax, [rcx]
0x18005bb3a  mov     rax, [rax+18h]
0x18005bb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb43  mov     ebx, eax
0x18005bb45  test    eax, eax
0x18005bb47  jns     short loc_18005BB55
0x18005bb49  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x18005bb50  jmp     loc_18005BC73
0x18005bb55  mov     rcx, [rsp+2E0h+var_298]
0x18005bb5a  lea     r8, [rsp+2E0h+var_2B0]
0x18005bb5f  mov     edx, edi
0x18005bb61  mov     rax, [rcx]
0x18005bb64  mov     rax, [rax+18h]
0x18005bb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb6d  mov     ebx, eax
0x18005bb6f  test    eax, eax
0x18005bb71  jns     short loc_18005BB7F
0x18005bb73  lea     rdx, aFindsessionbyi_3; "FindSessionById failed: 0x%x in %s"
0x18005bb7a  jmp     loc_18005BC73
0x18005bb7f  cmp     [rsp+2E0h+var_2B0], 0
0x18005bb85  jnz     short loc_18005BB9B
0x18005bb87  mov     ebx, 80070002h
0x18005bb8c  lea     rdx, aNullPtrsession; "NULL == ptrSession failed: 0x%x in %s"
0x18005bb93  mov     r8d, ebx
0x18005bb96  jmp     loc_18005BC76
0x18005bb9b  xor     ecx, ecx; BindingHandle
0x18005bb9d  call    cs:__imp_RpcImpersonateClient
0x18005bba4  nop     dword ptr [rax+rax+00h]
0x18005bba9  test    eax, eax
0x18005bbab  jz      short loc_18005BBC1
0x18005bbad  mov     ebx, 80070005h
0x18005bbb2  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18005bbb9  mov     r8d, ebx
0x18005bbbc  jmp     loc_18005BC76
0x18005bbc1  mov     rcx, [rsp+2E0h+var_2B0]
0x18005bbc6  xor     r9d, r9d
0x18005bbc9  xor     r8d, r8d
0x18005bbcc  mov     rax, [rcx]
0x18005bbcf  lea     edx, [r9+4]
0x18005bbd3  mov     rax, [rax+90h]
0x18005bbda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bbdf  mov     edi, eax
0x18005bbe1  mov     ebx, 80070005h
0x18005bbe6  test    eax, eax
0x18005bbe8  jns     short loc_18005BC00
0x18005bbea  mov     r8d, eax
0x18005bbed  lea     rdx, aAccesscheckexF; "AccessCheckEx failed: 0x%X"
0x18005bbf4  mov     ecx, 8; int
0x18005bbf9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005bbfe  mov     edi, ebx
0x18005bc00  call    cs:__imp_RpcRevertToSelf
0x18005bc07  nop     dword ptr [rax+rax+00h]
0x18005bc0c  test    eax, eax
0x18005bc0e  jnz     short loc_18005BC16
0x18005bc10  mov     ebx, edi
0x18005bc12  test    edi, edi
0x18005bc14  jns     short loc_18005BC22
0x18005bc16  mov     r8d, ebx
0x18005bc19  lea     rdx, aAccesscheckexF_0; "AccessCheckEx failed: 0x%x in %s"
0x18005bc20  jmp     short loc_18005BC76
0x18005bc22  mov     rcx, [rsp+2E0h+var_2B0]
0x18005bc27  lea     r8, [rsp+2E0h+var_2A0]
0x18005bc2c  lea     rdx, qword_1800A7960
0x18005bc33  mov     rax, [rcx]
0x18005bc36  mov     rax, [rax]
0x18005bc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc3e  mov     ebx, eax
0x18005bc40  test    eax, eax
0x18005bc42  jns     short loc_18005BC4D
0x18005bc44  lea     rdx, aQiOnIidItssess; "QI on IID_ITSSessionPrivate failed: 0x%"...
0x18005bc4b  jmp     short loc_18005BC73
0x18005bc4d  mov     rcx, [rsp+2E0h+var_2A0]
0x18005bc52  mov     edx, 2
0x18005bc57  mov     rax, [rcx]
0x18005bc5a  mov     rax, [rax+240h]
0x18005bc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc66  mov     ebx, eax
0x18005bc68  test    eax, eax
0x18005bc6a  jns     short loc_18005BC83
0x18005bc6c  lea     rdx, aPtrprivatesess; "ptrPrivateSession->Logoff failed: 0x%x "...
0x18005bc73  mov     r8d, eax
0x18005bc76  mov     r9, r14
0x18005bc79  mov     ecx, 8; int
0x18005bc7e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005bc83  lea     rcx, [rsp+2E0h+var_280]; this
0x18005bc88  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005bc8d  lea     rcx, [rsp+2E0h+var_2A0]
0x18005bc92  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005bc97  lea     rcx, [rsp+2E0h+var_2B0]
0x18005bc9c  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005bca1  lea     rcx, [rsp+2E0h+var_290]
0x18005bca6  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005bcab  lea     rcx, [rsp+2E0h+var_298]
0x18005bcb0  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005bcb5  lea     rcx, [rsp+2E0h+var_2A8]
0x18005bcba  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005bcbf  mov     eax, ebx
0x18005bcc1  mov     rcx, [rbp+1E0h+var_30]
0x18005bcc8  xor     rcx, rsp; StackCookie
0x18005bccb  call    __security_check_cookie
0x18005bcd0  add     rsp, 2C8h
0x18005bcd7  pop     r14
0x18005bcd9  pop     rdi
0x18005bcda  pop     rbx
0x18005bcdb  pop     rbp
0x18005bcdc  retn
```
