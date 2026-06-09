# RpcTerminateSession

- ea: `0x180058180`
- end: `0x1800583a1`
- name: `RpcTerminateSession`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180014c00`
- `0x180014f40`
- `0x180014ff0`
- `0x18004b460`
- `0x180058180`
- `0x180097010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18005826d`
- `RPCRT4!RpcImpersonateClient` at `0x18005826d`
- `RPCRT4!RpcRevertToSelf` at `0x1800582ca`
- `RPCRT4!RpcRevertToSelf` at `0x1800582ca`

## string_xrefs

- `0x1800582b7`: `AccessCheckEx failed: 0x%X`
- `0x18005827c`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x1800582dd`: `AccessCheckEx failed: 0x%x in %s`

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
        v3 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v9)(v9, qword_1800A2D40, &v11);
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
0x180058180  push    rbp
0x180058182  push    rbx
0x180058183  push    rdi
0x180058184  push    r14
0x180058186  lea     rbp, [rsp-1C8h]
0x18005818e  sub     rsp, 2C8h
0x180058195  mov     rax, cs:__security_cookie
0x18005819c  xor     rax, rsp
0x18005819f  mov     [rbp+1E0h+var_30], rax
0x1800581a6  mov     edi, edx
0x1800581a8  mov     [rsp+2E0h+var_298], 0
0x1800581b1  lea     r14, aRpcterminatese; "RpcTerminateSession"
0x1800581b8  mov     [rsp+2E0h+var_290], 0
0x1800581c1  mov     r8, r14; char *
0x1800581c4  mov     [rsp+2E0h+var_2B0], 0
0x1800581cd  mov     edx, 1; int
0x1800581d2  mov     [rsp+2E0h+var_2A0], 0
0x1800581db  lea     rcx, [rsp+2E0h+var_280]; this
0x1800581e0  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x1800581e5  lea     rcx, [rsp+2E0h+var_2A8]; struct ISessionManagerInternal **
0x1800581ea  mov     [rsp+2E0h+var_2A8], 0
0x1800581f3  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x1800581f8  mov     rcx, [rsp+2E0h+var_2A8]
0x1800581fd  lea     rdx, [rsp+2E0h+var_298]
0x180058202  mov     [rsp+2E0h+var_2A8], rcx
0x180058207  mov     rax, [rcx]
0x18005820a  mov     rax, [rax+18h]
0x18005820e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058213  mov     ebx, eax
0x180058215  test    eax, eax
0x180058217  jns     short loc_180058225
0x180058219  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x180058220  jmp     loc_180058337
0x180058225  mov     rcx, [rsp+2E0h+var_298]
0x18005822a  lea     r8, [rsp+2E0h+var_2B0]
0x18005822f  mov     edx, edi
0x180058231  mov     rax, [rcx]
0x180058234  mov     rax, [rax+18h]
0x180058238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005823d  mov     ebx, eax
0x18005823f  test    eax, eax
0x180058241  jns     short loc_18005824F
0x180058243  lea     rdx, aFindsessionbyi_3; "FindSessionById failed: 0x%x in %s"
0x18005824a  jmp     loc_180058337
0x18005824f  cmp     [rsp+2E0h+var_2B0], 0
0x180058255  jnz     short loc_18005826B
0x180058257  mov     ebx, 80070002h
0x18005825c  lea     rdx, aNullPtrsession; "NULL == ptrSession failed: 0x%x in %s"
0x180058263  mov     r8d, ebx
0x180058266  jmp     loc_18005833A
0x18005826b  xor     ecx, ecx; BindingHandle
0x18005826d  call    cs:__imp_RpcImpersonateClient
0x180058273  test    eax, eax
0x180058275  jz      short loc_18005828B
0x180058277  mov     ebx, 80070005h
0x18005827c  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180058283  mov     r8d, ebx
0x180058286  jmp     loc_18005833A
0x18005828b  mov     rcx, [rsp+2E0h+var_2B0]
0x180058290  xor     r9d, r9d
0x180058293  xor     r8d, r8d
0x180058296  mov     rax, [rcx]
0x180058299  lea     edx, [r9+4]
0x18005829d  mov     rax, [rax+90h]
0x1800582a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582a9  mov     edi, eax
0x1800582ab  mov     ebx, 80070005h
0x1800582b0  test    eax, eax
0x1800582b2  jns     short loc_1800582CA
0x1800582b4  mov     r8d, eax
0x1800582b7  lea     rdx, aAccesscheckexF; "AccessCheckEx failed: 0x%X"
0x1800582be  mov     ecx, 8; int
0x1800582c3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800582c8  mov     edi, ebx
0x1800582ca  call    cs:__imp_RpcRevertToSelf
0x1800582d0  test    eax, eax
0x1800582d2  jnz     short loc_1800582DA
0x1800582d4  mov     ebx, edi
0x1800582d6  test    edi, edi
0x1800582d8  jns     short loc_1800582E6
0x1800582da  mov     r8d, ebx
0x1800582dd  lea     rdx, aAccesscheckexF_0; "AccessCheckEx failed: 0x%x in %s"
0x1800582e4  jmp     short loc_18005833A
0x1800582e6  mov     rcx, [rsp+2E0h+var_2B0]
0x1800582eb  lea     r8, [rsp+2E0h+var_2A0]
0x1800582f0  lea     rdx, qword_1800A2D40
0x1800582f7  mov     rax, [rcx]
0x1800582fa  mov     rax, [rax]
0x1800582fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058302  mov     ebx, eax
0x180058304  test    eax, eax
0x180058306  jns     short loc_180058311
0x180058308  lea     rdx, aQiOnIidItssess; "QI on IID_ITSSessionPrivate failed: 0x%"...
0x18005830f  jmp     short loc_180058337
0x180058311  mov     rcx, [rsp+2E0h+var_2A0]
0x180058316  mov     edx, 2
0x18005831b  mov     rax, [rcx]
0x18005831e  mov     rax, [rax+240h]
0x180058325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005832a  mov     ebx, eax
0x18005832c  test    eax, eax
0x18005832e  jns     short loc_180058347
0x180058330  lea     rdx, aPtrprivatesess; "ptrPrivateSession->Logoff failed: 0x%x "...
0x180058337  mov     r8d, eax
0x18005833a  mov     r9, r14
0x18005833d  mov     ecx, 8; int
0x180058342  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180058347  lea     rcx, [rsp+2E0h+var_280]; this
0x18005834c  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180058351  lea     rcx, [rsp+2E0h+var_2A0]
0x180058356  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005835b  lea     rcx, [rsp+2E0h+var_2B0]
0x180058360  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180058365  lea     rcx, [rsp+2E0h+var_290]
0x18005836a  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005836f  lea     rcx, [rsp+2E0h+var_298]
0x180058374  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180058379  lea     rcx, [rsp+2E0h+var_2A8]
0x18005837e  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180058383  mov     eax, ebx
0x180058385  mov     rcx, [rbp+1E0h+var_30]
0x18005838c  xor     rcx, rsp; StackCookie
0x18005838f  call    __security_check_cookie
0x180058394  add     rsp, 2C8h
0x18005839b  pop     r14
0x18005839d  pop     rdi
0x18005839e  pop     rbx
0x18005839f  pop     rbp
0x1800583a0  retn
```
