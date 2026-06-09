# RpcGetSessionType

- ea: `0x180014950`
- end: `0x180014bf0`
- name: `RpcGetSessionType`
- size: `672`
- prototype: `__int64 __fastcall(__int64, int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x180015750`

## callees

- `0x1800074c0`
- `0x180014950`
- `0x180014c00`
- `0x180014f40`
- `0x180014ff0`
- `0x180015d24`
- `0x18004b460`
- `0x180097010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180014aaa`
- `RPCRT4!RpcImpersonateClient` at `0x180014aaa`
- `RPCRT4!RpcRevertToSelf` at `0x180014ae1`
- `RPCRT4!RpcRevertToSelf` at `0x180014ae1`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800149b1`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800149b1`

## string_xrefs

- `0x180014b5f`: `AccessCheckEx failed: 0x%X`
- `0x180014bb5`: `Cannot impersonate client: %d`
- `0x180014be4`: `CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s`
- `0x180014b8c`: `CheckAccessToSession`

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
0x180014950  mov     [rsp-8+arg_0], rbx
0x180014955  push    rbp
0x180014956  push    rsi
0x180014957  push    rdi
0x180014958  push    r12
0x18001495a  push    r14
0x18001495c  lea     rbp, [rsp-1B0h]
0x180014964  sub     rsp, 2B0h
0x18001496b  mov     rax, cs:__security_cookie
0x180014972  xor     rax, rsp
0x180014975  mov     [rbp+1D0h+var_30], rax
0x18001497c  mov     rsi, r8
0x18001497f  mov     r14d, edx
0x180014982  xor     ebx, ebx
0x180014984  mov     [rsp+2D0h+var_298], rbx
0x180014989  mov     [rsp+2D0h+var_2A0], rbx
0x18001498e  lea     r12, aRpcgetsessiont; "RpcGetSessionType"
0x180014995  mov     r8, r12; char *
0x180014998  xor     edx, edx; int
0x18001499a  lea     rcx, [rsp+2D0h+var_280]; this
0x18001499f  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x1800149a4  test    rsi, rsi
0x1800149a7  jz      loc_180014B1B
0x1800149ad  xor     edi, edi
0x1800149af  mov     [rsi], ebx
0x1800149b1  call    cs:__imp_WTSGetServiceSessionId
0x1800149b7  cmp     r14d, eax
0x1800149ba  jnz     short loc_180014A38
0x1800149bc  mov     dword ptr [rsi], 1
0x1800149c2  lea     rcx, [rsp+2D0h+var_280]; this
0x1800149c7  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x1800149cc  nop
0x1800149cd  mov     rcx, [rsp+2D0h+var_2A0]
0x1800149d2  test    rcx, rcx
0x1800149d5  jz      short loc_1800149E4
0x1800149d7  mov     rax, [rcx]
0x1800149da  mov     rax, [rax+10h]
0x1800149de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149e3  nop
0x1800149e4  mov     rcx, [rsp+2D0h+var_298]
0x1800149e9  test    rcx, rcx
0x1800149ec  jz      short loc_1800149FB
0x1800149ee  mov     rax, [rcx]
0x1800149f1  mov     rax, [rax+10h]
0x1800149f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149fa  nop
0x1800149fb  test    rbx, rbx
0x1800149fe  jz      short loc_180014A10
0x180014a00  mov     rax, [rbx]
0x180014a03  mov     rcx, rbx
0x180014a06  mov     rax, [rax+10h]
0x180014a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a0f  nop
0x180014a10  mov     eax, edi
0x180014a12  mov     rcx, [rbp+1D0h+var_30]
0x180014a19  xor     rcx, rsp; StackCookie
0x180014a1c  call    __security_check_cookie
0x180014a21  mov     rbx, [rsp+2D0h+arg_0]
0x180014a29  add     rsp, 2B0h
0x180014a30  pop     r14
0x180014a32  pop     r12
0x180014a34  pop     rdi
0x180014a35  pop     rsi
0x180014a36  pop     rbp
0x180014a37  retn
0x180014a38  cmp     r14d, 10000h
0x180014a3f  jge     loc_180014B78
0x180014a45  mov     [rsp+2D0h+var_290], rbx
0x180014a4a  lea     rcx, [rsp+2D0h+var_290]; struct ISessionManagerInternal **
0x180014a4f  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x180014a54  mov     rbx, [rsp+2D0h+var_290]
0x180014a59  mov     rax, [rbx]
0x180014a5c  lea     rdx, [rsp+2D0h+var_298]
0x180014a61  mov     rcx, rbx
0x180014a64  mov     rax, [rax+18h]
0x180014a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a6d  mov     edi, eax
0x180014a6f  test    eax, eax
0x180014a71  js      loc_180014B40
0x180014a77  mov     rcx, [rsp+2D0h+var_298]
0x180014a7c  mov     rax, [rcx]
0x180014a7f  lea     r8, [rsp+2D0h+var_2A0]
0x180014a84  mov     edx, r14d
0x180014a87  mov     rax, [rax+18h]
0x180014a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a90  mov     edi, eax
0x180014a92  test    eax, eax
0x180014a94  js      loc_180014B83
0x180014a9a  mov     rdi, [rsp+2D0h+var_2A0]
0x180014a9f  test    rdi, rdi
0x180014aa2  jz      loc_180014B8C
0x180014aa8  xor     ecx, ecx; BindingHandle
0x180014aaa  call    cs:__imp_RpcImpersonateClient
0x180014ab0  test    eax, eax
0x180014ab2  jnz     loc_180014BB2
0x180014ab8  mov     rax, [rdi]
0x180014abb  mov     edx, 1
0x180014ac0  mov     r9d, edx
0x180014ac3  xor     r8d, r8d
0x180014ac6  mov     rcx, rdi
0x180014ac9  mov     rax, [rax+90h]
0x180014ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ad5  mov     r14d, eax
0x180014ad8  mov     edi, 80070005h
0x180014add  test    eax, eax
0x180014adf  js      short loc_180014B5C
0x180014ae1  call    cs:__imp_RpcRevertToSelf
0x180014ae7  test    eax, eax
0x180014ae9  jnz     loc_180014BCD
0x180014aef  mov     edi, r14d
0x180014af2  test    r14d, r14d
0x180014af5  js      loc_180014BE1
0x180014afb  mov     rdx, rsi; unsigned int *
0x180014afe  mov     rcx, [rsp+2D0h+var_2A0]; struct ITSSession *
0x180014b03  call    ?PrivateSessionTypeToPublicSessionType@@YAJPEAUITSSession@@PEAK@Z; PrivateSessionTypeToPublicSessionType(ITSSession *,ulong *)
0x180014b08  mov     edi, eax
0x180014b0a  test    eax, eax
0x180014b0c  jns     loc_1800149C2
0x180014b12  lea     rdx, aPrivatesession_0; "PrivateSessionTypeToPublicSessionType f"...
0x180014b19  jmp     short loc_180014B47
0x180014b1b  mov     r9, r12
0x180014b1e  lea     r8, aPsessiontype; "pSessionType"
0x180014b25  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180014b2c  mov     ecx, 8; int
0x180014b31  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014b36  mov     edi, 80070057h
0x180014b3b  jmp     loc_1800149C2
0x180014b40  lea     rdx, aGetsessionlist_1; "GetSessionList failed: 0x%x in %s"
0x180014b47  mov     r8d, eax
0x180014b4a  mov     r9, r12
0x180014b4d  mov     ecx, 8; int
0x180014b52  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014b57  jmp     loc_1800149C2
0x180014b5c  mov     r8d, eax
0x180014b5f  lea     rdx, aAccesscheckexF; "AccessCheckEx failed: 0x%X"
0x180014b66  mov     ecx, 8; int
0x180014b6b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014b70  mov     r14d, edi
0x180014b73  jmp     loc_180014AE1
0x180014b78  mov     dword ptr [rsi], 2
0x180014b7e  jmp     loc_1800149C2
0x180014b83  lea     rdx, aFindsessionbyi_3; "FindSessionById failed: 0x%x in %s"
0x180014b8a  jmp     short loc_180014B47
0x180014b8c  lea     r9, aCheckaccesstos_3; "CheckAccessToSession"
0x180014b93  lea     r8, aPsession; "pSession"
0x180014b9a  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180014ba1  mov     ecx, 8; int
0x180014ba6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014bab  mov     edi, 80070057h
0x180014bb0  jmp     short loc_180014BE1
0x180014bb2  mov     r8d, eax
0x180014bb5  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x180014bbc  mov     ecx, 8; int
0x180014bc1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014bc6  mov     edi, 80070005h
0x180014bcb  jmp     short loc_180014BE1
0x180014bcd  mov     r8d, eax
0x180014bd0  lea     rdx, aRpcreverttosel_0; "RpcRevertToSelf failed: %d"
0x180014bd7  mov     ecx, 8; int
0x180014bdc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014be1  mov     r8d, edi
0x180014be4  lea     rdx, aCheckaccesstos_5; "CheckAccessToSession(WINSTATION_QUERY) "...
0x180014beb  jmp     loc_180014B4A
```
