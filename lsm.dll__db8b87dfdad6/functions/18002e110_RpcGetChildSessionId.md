# RpcGetChildSessionId

- ea: `0x18002e110`
- end: `0x18002e2ec`
- name: `RpcGetChildSessionId`
- size: `476`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800074c0`
- `0x180014c00`
- `0x180014f40`
- `0x180015ef8`
- `0x18002e110`
- `0x18004b460`
- `0x180097010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002e1ab`
- `RPCRT4!RpcImpersonateClient` at `0x18002e1ab`
- `RPCRT4!RpcRevertToSelf` at `0x18002e1ed`
- `RPCRT4!RpcRevertToSelf` at `0x18002e1ed`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18002e25c`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18002e25c`

## string_xrefs

- `0x18002e1c7`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18002e228`: `ptrSourceSession->AccessCheck( WINSTATION_QUERY ) failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RpcGetChildSessionId(__int64 a1, _DWORD *a2)
{
  signed int v3; // ebx
  int SessionFromRpcClientId; // eax
  const char *v5; // rdx
  RPC_STATUS v6; // eax
  int v7; // eax
  bool v8; // sf
  __int64 v10; // [rsp+20h] [rbp-E0h] BYREF
  struct ITSSession *v11; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v12[592]; // [rsp+30h] [rbp-D0h] BYREF

  v11 = 0;
  v10 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v12, 0, "RpcGetChildSessionId");
  if ( !a2 )
  {
    v3 = -2147024809;
    goto LABEL_26;
  }
  *a2 = -1;
  SessionFromRpcClientId = CRpcUtils::GetSessionFromRpcClientId(&v11);
  v3 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId < 0 )
  {
    v5 = "CRpcUtils::GetSessionFromRpcClientId failed: 0x%x in %s";
LABEL_5:
    _DbgPrintMessage(8, v5, (unsigned int)SessionFromRpcClientId, "RpcGetChildSessionId", v10);
    goto LABEL_26;
  }
  v6 = RpcImpersonateClient(0);
  v3 = v6;
  if ( v6 > 0 )
    v3 = (unsigned __int16)v6 | 0x80070000;
  if ( v3 < 0 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", (unsigned int)v3, "RpcGetChildSessionId");
    goto LABEL_26;
  }
  v3 = (*(__int64 (__fastcall **)(struct ITSSession *, __int64))(*(_QWORD *)v11 + 136LL))(v11, 1);
  v7 = RpcRevertToSelf();
  v8 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x80070000;
    v8 = v7 < 0;
  }
  if ( v8 )
  {
    _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v7);
    v3 = -2147024891;
    goto LABEL_26;
  }
  if ( v3 < 0 )
  {
    _DbgPrintMessage(
      8,
      "ptrSourceSession->AccessCheck( WINSTATION_QUERY ) failed: 0x%x in %s",
      (unsigned int)v3,
      "RpcGetChildSessionId");
    goto LABEL_26;
  }
  SessionFromRpcClientId = (*(__int64 (__fastcall **)(struct ITSSession *, __int64 *))(*(_QWORD *)v11 + 80LL))(
                             v11,
                             &v10);
  v3 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId < 0 )
  {
    v5 = "ptrSourceSession->getId failed: 0x%x in %s";
    goto LABEL_5;
  }
  if ( (_DWORD)v10 == (unsigned int)WTSGetServiceSessionId() )
  {
    v3 = -2147024846;
    goto LABEL_26;
  }
  SessionFromRpcClientId = (*(__int64 (__fastcall **)(struct ITSSession *, char *))(*(_QWORD *)v11 + 304LL))(
                             v11,
                             (char *)&v10 + 4);
  v3 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId < 0 )
  {
    v5 = "ptrSourceSession->getChildSessionId failed: 0x%x in %s";
    goto LABEL_5;
  }
  if ( HIDWORD(v10) == -1 )
    v3 = -2147023728;
  else
    *a2 = HIDWORD(v10);
LABEL_26:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v12);
  if ( v11 )
    (*(void (__fastcall **)(struct ITSSession *))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002e110  push    rbp
0x18002e112  push    rbx
0x18002e113  push    rdi
0x18002e114  push    r14
0x18002e116  lea     rbp, [rsp-198h]
0x18002e11e  sub     rsp, 298h
0x18002e125  mov     rax, cs:__security_cookie
0x18002e12c  xor     rax, rsp
0x18002e12f  mov     [rbp+1B0h+var_30], rax
0x18002e136  mov     rdi, rdx
0x18002e139  mov     [rsp+2B0h+var_288], 0
0x18002e142  mov     [rsp+2B0h+var_290], 0
0x18002e14a  mov     [rsp+2B0h+var_28C], 0
0x18002e152  lea     r14, aRpcgetchildses; "RpcGetChildSessionId"
0x18002e159  mov     r8, r14; char *
0x18002e15c  xor     edx, edx; int
0x18002e15e  lea     rcx, [rsp+2B0h+var_280]; this
0x18002e163  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18002e168  test    rdi, rdi
0x18002e16b  jnz     short loc_18002E177
0x18002e16d  mov     ebx, 80070057h
0x18002e172  jmp     loc_18002E2AC
0x18002e177  mov     dword ptr [rdi], 0FFFFFFFFh
0x18002e17d  lea     rcx, [rsp+2B0h+var_288]; struct ITSSession **
0x18002e182  call    ?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z; CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)
0x18002e187  mov     ebx, eax
0x18002e189  test    eax, eax
0x18002e18b  jns     short loc_18002E1A9
0x18002e18d  lea     rdx, aCrpcutilsGetse; "CRpcUtils::GetSessionFromRpcClientId fa"...
0x18002e194  mov     r8d, eax
0x18002e197  mov     r9, r14
0x18002e19a  mov     ecx, 8; int
0x18002e19f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e1a4  jmp     loc_18002E2AC
0x18002e1a9  xor     ecx, ecx; BindingHandle
0x18002e1ab  call    cs:__imp_RpcImpersonateClient
0x18002e1b1  mov     ebx, eax
0x18002e1b3  test    eax, eax
0x18002e1b5  jle     short loc_18002E1C0
0x18002e1b7  movzx   ebx, ax
0x18002e1ba  or      ebx, 80070000h
0x18002e1c0  test    ebx, ebx
0x18002e1c2  jns     short loc_18002E1D0
0x18002e1c4  mov     r8d, ebx
0x18002e1c7  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18002e1ce  jmp     short loc_18002E197
0x18002e1d0  mov     rcx, [rsp+2B0h+var_288]
0x18002e1d5  mov     rax, [rcx]
0x18002e1d8  xor     r8d, r8d
0x18002e1db  lea     edx, [r8+1]
0x18002e1df  mov     rax, [rax+88h]
0x18002e1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1eb  mov     ebx, eax
0x18002e1ed  call    cs:__imp_RpcRevertToSelf
0x18002e1f3  test    eax, eax
0x18002e1f5  jle     short loc_18002E201
0x18002e1f7  movzx   eax, ax
0x18002e1fa  or      eax, 80070000h
0x18002e1ff  test    eax, eax
0x18002e201  jns     short loc_18002E221
0x18002e203  mov     r8d, eax
0x18002e206  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x18002e20d  mov     ecx, 8; int
0x18002e212  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e217  mov     ebx, 80070005h
0x18002e21c  jmp     loc_18002E2AC
0x18002e221  test    ebx, ebx
0x18002e223  jns     short loc_18002E234
0x18002e225  mov     r8d, ebx
0x18002e228  lea     rdx, aPtrsourcesessi; "ptrSourceSession->AccessCheck( WINSTATI"...
0x18002e22f  jmp     loc_18002E197
0x18002e234  mov     rcx, [rsp+2B0h+var_288]
0x18002e239  mov     rax, [rcx]
0x18002e23c  lea     rdx, [rsp+2B0h+var_290]
0x18002e241  mov     rax, [rax+50h]
0x18002e245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e24a  mov     ebx, eax
0x18002e24c  test    eax, eax
0x18002e24e  jns     short loc_18002E25C
0x18002e250  lea     rdx, aPtrsourcesessi_2; "ptrSourceSession->getId failed: 0x%x in"...
0x18002e257  jmp     loc_18002E194
0x18002e25c  call    cs:__imp_WTSGetServiceSessionId
0x18002e262  cmp     [rsp+2B0h+var_290], eax
0x18002e266  jnz     short loc_18002E26F
0x18002e268  mov     ebx, 80070032h
0x18002e26d  jmp     short loc_18002E2AC
0x18002e26f  mov     rcx, [rsp+2B0h+var_288]
0x18002e274  mov     rax, [rcx]
0x18002e277  lea     rdx, [rsp+2B0h+var_28C]
0x18002e27c  mov     rax, [rax+130h]
0x18002e283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e288  mov     ebx, eax
0x18002e28a  test    eax, eax
0x18002e28c  jns     short loc_18002E29A
0x18002e28e  lea     rdx, aPtrsourcesessi_0; "ptrSourceSession->getChildSessionId fai"...
0x18002e295  jmp     loc_18002E194
0x18002e29a  mov     eax, [rsp+2B0h+var_28C]
0x18002e29e  cmp     eax, 0FFFFFFFFh
0x18002e2a1  jnz     short loc_18002E2AA
0x18002e2a3  mov     ebx, 80070490h
0x18002e2a8  jmp     short loc_18002E2AC
0x18002e2aa  mov     [rdi], eax
0x18002e2ac  lea     rcx, [rsp+2B0h+var_280]; this
0x18002e2b1  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18002e2b6  nop
0x18002e2b7  mov     rcx, [rsp+2B0h+var_288]
0x18002e2bc  test    rcx, rcx
0x18002e2bf  jz      short loc_18002E2CE
0x18002e2c1  mov     rax, [rcx]
0x18002e2c4  mov     rax, [rax+10h]
0x18002e2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2cd  nop
0x18002e2ce  mov     eax, ebx
0x18002e2d0  mov     rcx, [rbp+1B0h+var_30]
0x18002e2d7  xor     rcx, rsp; StackCookie
0x18002e2da  call    __security_check_cookie
0x18002e2df  add     rsp, 298h
0x18002e2e6  pop     r14
0x18002e2e8  pop     rdi
0x18002e2e9  pop     rbx
0x18002e2ea  pop     rbp
0x18002e2eb  retn
```
