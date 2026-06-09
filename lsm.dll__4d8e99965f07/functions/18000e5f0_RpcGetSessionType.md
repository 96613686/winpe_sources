# RpcGetSessionType

- ea: `0x18000e5f0`
- end: `0x18000e8a7`
- name: `RpcGetSessionType`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000db70`

## callees

- `0x1800077a0`
- `0x18000e5f0`
- `0x18000e8b0`
- `0x18000f260`
- `0x18000f320`
- `0x18000f6e8`
- `0x18004e850`
- `0x18009c010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000e751`
- `RPCRT4!RpcImpersonateClient` at `0x18000e751`
- `RPCRT4!RpcRevertToSelf` at `0x18000e792`
- `RPCRT4!RpcRevertToSelf` at `0x18000e792`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000e651`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000e651`

## string_xrefs

- `0x18000e816`: `AccessCheckEx failed: 0x%X`
- `0x18000e89b`: `CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s`
- `0x18000e843`: `CheckAccessToSession`
- `0x18000e86c`: `Cannot impersonate client: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetSessionType(__int64 a1, int a2, unsigned int *a3)
{
  struct ISessionManagerInternal *v5; // rbx
  unsigned int v6; // edi
  int v8; // eax
  struct ITSSession *v9; // rdi
  RPC_STATUS v10; // eax
  int v11; // eax
  int v12; // r14d
  RPC_STATUS v13; // eax
  const char *v14; // rdx
  struct ITSSession *v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  struct ISessionManagerInternal *v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[592]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = 0;
  v16 = 0;
  v15 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v18, 0, "RpcGetSessionType");
  if ( !a3 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "pSessionType", "RpcGetSessionType");
    v6 = -2147024809;
    goto LABEL_4;
  }
  v6 = 0;
  *a3 = 0;
  if ( a2 == (unsigned int)WTSGetServiceSessionId() )
  {
    *a3 = 1;
    goto LABEL_4;
  }
  if ( a2 >= 0x10000 )
  {
    *a3 = 2;
    goto LABEL_4;
  }
  v17 = 0;
  ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v17);
  v5 = v17;
  v8 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v17 + 24LL))(v17, &v16);
  v6 = v8;
  if ( v8 < 0 )
  {
    v14 = "GetSessionList failed: 0x%x in %s";
LABEL_24:
    _DbgPrintMessage(8, v14, (unsigned int)v8, "RpcGetSessionType");
    goto LABEL_4;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ITSSession **))(*(_QWORD *)v16 + 24LL))(
         v16,
         (unsigned int)a2,
         &v15);
  v6 = v8;
  if ( v8 < 0 )
  {
    v14 = "FindSessionById failed: 0x%x in %s";
    goto LABEL_24;
  }
  v9 = v15;
  if ( v15 )
  {
    v10 = RpcImpersonateClient(0);
    if ( v10 )
    {
      _DbgPrintMessage(8, "Cannot impersonate client: %d", v10);
      v6 = -2147024891;
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(struct ITSSession *, __int64, _QWORD, __int64))(*(_QWORD *)v9 + 144LL))(
              v9,
              1,
              0,
              1);
      v12 = v11;
      v6 = -2147024891;
      if ( v11 < 0 )
      {
        _DbgPrintMessage(8, "AccessCheckEx failed: 0x%X", v11);
        v12 = -2147024891;
      }
      v13 = RpcRevertToSelf();
      if ( v13 )
      {
        _DbgPrintMessage(8, "RpcRevertToSelf failed: %d", v13);
      }
      else
      {
        v6 = v12;
        if ( v12 >= 0 )
        {
          v8 = PrivateSessionTypeToPublicSessionType(v15, a3);
          v6 = v8;
          if ( v8 >= 0 )
            goto LABEL_4;
          v14 = "PrivateSessionTypeToPublicSessionType failed: 0x%x in %s";
          goto LABEL_24;
        }
      }
    }
  }
  else
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "pSession", "CheckAccessToSession");
    v6 = -2147024809;
  }
  _DbgPrintMessage(8, "CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s", v6, "RpcGetSessionType");
LABEL_4:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v18);
  if ( v15 )
    (*(void (__fastcall **)(struct ITSSession *))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v5 )
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v5 + 16LL))(v5);
  return v6;
}

```

## disassembly

```asm
0x18000e5f0  mov     [rsp-8+arg_0], rbx
0x18000e5f5  push    rbp
0x18000e5f6  push    rsi
0x18000e5f7  push    rdi
0x18000e5f8  push    r12
0x18000e5fa  push    r14
0x18000e5fc  lea     rbp, [rsp-1B0h]
0x18000e604  sub     rsp, 2B0h
0x18000e60b  mov     rax, cs:__security_cookie
0x18000e612  xor     rax, rsp
0x18000e615  mov     [rbp+1D0h+var_30], rax
0x18000e61c  mov     rsi, r8
0x18000e61f  mov     r14d, edx
0x18000e622  xor     ebx, ebx
0x18000e624  mov     [rsp+2D0h+var_298], rbx
0x18000e629  mov     [rsp+2D0h+var_2A0], rbx
0x18000e62e  lea     r12, aRpcgetsessiont; "RpcGetSessionType"
0x18000e635  mov     r8, r12; char *
0x18000e638  xor     edx, edx; int
0x18000e63a  lea     rcx, [rsp+2D0h+var_280]; this
0x18000e63f  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18000e644  test    rsi, rsi
0x18000e647  jz      loc_18000E7D2
0x18000e64d  xor     edi, edi
0x18000e64f  mov     [rsi], ebx
0x18000e651  call    cs:__imp_WTSGetServiceSessionId
0x18000e658  nop     dword ptr [rax+rax+00h]
0x18000e65d  cmp     r14d, eax
0x18000e660  jnz     short loc_18000E6DF
0x18000e662  mov     dword ptr [rsi], 1
0x18000e668  lea     rcx, [rsp+2D0h+var_280]; this
0x18000e66d  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18000e672  nop
0x18000e673  mov     rcx, [rsp+2D0h+var_2A0]
0x18000e678  test    rcx, rcx
0x18000e67b  jz      short loc_18000E68A
0x18000e67d  mov     rax, [rcx]
0x18000e680  mov     rax, [rax+10h]
0x18000e684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e689  nop
0x18000e68a  mov     rcx, [rsp+2D0h+var_298]
0x18000e68f  test    rcx, rcx
0x18000e692  jz      short loc_18000E6A1
0x18000e694  mov     rax, [rcx]
0x18000e697  mov     rax, [rax+10h]
0x18000e69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6a0  nop
0x18000e6a1  test    rbx, rbx
0x18000e6a4  jz      short loc_18000E6B6
0x18000e6a6  mov     rax, [rbx]
0x18000e6a9  mov     rcx, rbx
0x18000e6ac  mov     rax, [rax+10h]
0x18000e6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6b5  nop
0x18000e6b6  mov     eax, edi
0x18000e6b8  mov     rcx, [rbp+1D0h+var_30]
0x18000e6bf  xor     rcx, rsp; StackCookie
0x18000e6c2  call    __security_check_cookie
0x18000e6c7  mov     rbx, [rsp+2D0h+arg_0]
0x18000e6cf  add     rsp, 2B0h
0x18000e6d6  pop     r14
0x18000e6d8  pop     r12
0x18000e6da  pop     rdi
0x18000e6db  pop     rsi
0x18000e6dc  pop     rbp
0x18000e6dd  retn
0x18000e6df  cmp     r14d, 10000h
0x18000e6e6  jge     loc_18000E82F
0x18000e6ec  mov     [rsp+2D0h+var_290], rbx
0x18000e6f1  lea     rcx, [rsp+2D0h+var_290]; struct ISessionManagerInternal **
0x18000e6f6  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18000e6fb  mov     rbx, [rsp+2D0h+var_290]
0x18000e700  mov     rax, [rbx]
0x18000e703  lea     rdx, [rsp+2D0h+var_298]
0x18000e708  mov     rcx, rbx
0x18000e70b  mov     rax, [rax+18h]
0x18000e70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e714  mov     edi, eax
0x18000e716  test    eax, eax
0x18000e718  js      loc_18000E7F7
0x18000e71e  mov     rcx, [rsp+2D0h+var_298]
0x18000e723  mov     rax, [rcx]
0x18000e726  lea     r8, [rsp+2D0h+var_2A0]
0x18000e72b  mov     edx, r14d
0x18000e72e  mov     rax, [rax+18h]
0x18000e732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e737  mov     edi, eax
0x18000e739  test    eax, eax
0x18000e73b  js      loc_18000E83A
0x18000e741  mov     rdi, [rsp+2D0h+var_2A0]
0x18000e746  test    rdi, rdi
0x18000e749  jz      loc_18000E843
0x18000e74f  xor     ecx, ecx; BindingHandle
0x18000e751  call    cs:__imp_RpcImpersonateClient
0x18000e758  nop     dword ptr [rax+rax+00h]
0x18000e75d  test    eax, eax
0x18000e75f  jnz     loc_18000E869
0x18000e765  mov     rax, [rdi]
0x18000e768  mov     edx, 1
0x18000e76d  mov     r9d, edx
0x18000e770  xor     r8d, r8d
0x18000e773  mov     rcx, rdi
0x18000e776  mov     rax, [rax+90h]
0x18000e77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e782  mov     r14d, eax
0x18000e785  mov     edi, 80070005h
0x18000e78a  test    eax, eax
0x18000e78c  js      loc_18000E813
0x18000e792  call    cs:__imp_RpcRevertToSelf
0x18000e799  nop     dword ptr [rax+rax+00h]
0x18000e79e  test    eax, eax
0x18000e7a0  jnz     loc_18000E884
0x18000e7a6  mov     edi, r14d
0x18000e7a9  test    r14d, r14d
0x18000e7ac  js      loc_18000E898
0x18000e7b2  mov     rdx, rsi; unsigned int *
0x18000e7b5  mov     rcx, [rsp+2D0h+var_2A0]; struct ITSSession *
0x18000e7ba  call    ?PrivateSessionTypeToPublicSessionType@@YAJPEAUITSSession@@PEAK@Z; PrivateSessionTypeToPublicSessionType(ITSSession *,ulong *)
0x18000e7bf  mov     edi, eax
0x18000e7c1  test    eax, eax
0x18000e7c3  jns     loc_18000E668
0x18000e7c9  lea     rdx, aPrivatesession_0; "PrivateSessionTypeToPublicSessionType f"...
0x18000e7d0  jmp     short loc_18000E7FE
0x18000e7d2  mov     r9, r12
0x18000e7d5  lea     r8, aPsessiontype; "pSessionType"
0x18000e7dc  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000e7e3  mov     ecx, 8; int
0x18000e7e8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e7ed  mov     edi, 80070057h
0x18000e7f2  jmp     loc_18000E668
0x18000e7f7  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x18000e7fe  mov     r8d, eax
0x18000e801  mov     r9, r12
0x18000e804  mov     ecx, 8; int
0x18000e809  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e80e  jmp     loc_18000E668
0x18000e813  mov     r8d, eax
0x18000e816  lea     rdx, aAccesscheckexF; "AccessCheckEx failed: 0x%X"
0x18000e81d  mov     ecx, 8; int
0x18000e822  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e827  mov     r14d, edi
0x18000e82a  jmp     loc_18000E792
0x18000e82f  mov     dword ptr [rsi], 2
0x18000e835  jmp     loc_18000E668
0x18000e83a  lea     rdx, aFindsessionbyi_3; "FindSessionById failed: 0x%x in %s"
0x18000e841  jmp     short loc_18000E7FE
0x18000e843  lea     r9, aCheckaccesstos_3; "CheckAccessToSession"
0x18000e84a  lea     r8, aPsession; "pSession"
0x18000e851  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000e858  mov     ecx, 8; int
0x18000e85d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e862  mov     edi, 80070057h
0x18000e867  jmp     short loc_18000E898
0x18000e869  mov     r8d, eax
0x18000e86c  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x18000e873  mov     ecx, 8; int
0x18000e878  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e87d  mov     edi, 80070005h
0x18000e882  jmp     short loc_18000E898
0x18000e884  mov     r8d, eax
0x18000e887  lea     rdx, aRpcreverttosel_0; "RpcRevertToSelf failed: %d"
0x18000e88e  mov     ecx, 8; int
0x18000e893  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e898  mov     r8d, edi
0x18000e89b  lea     rdx, aCheckaccesstos_5; "CheckAccessToSession(WINSTATION_QUERY) "...
0x18000e8a2  jmp     loc_18000E801
```
