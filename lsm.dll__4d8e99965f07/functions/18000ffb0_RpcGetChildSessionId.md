# RpcGetChildSessionId

- ea: `0x18000ffb0`
- end: `0x18001019f`
- name: `RpcGetChildSessionId`
- size: `495`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800077a0`
- `0x18000da1c`
- `0x18000e8b0`
- `0x18000f260`
- `0x18000ffb0`
- `0x18004e850`
- `0x18009c010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18001004b`
- `RPCRT4!RpcImpersonateClient` at `0x18001004b`
- `RPCRT4!RpcRevertToSelf` at `0x180010093`
- `RPCRT4!RpcRevertToSelf` at `0x180010093`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180010108`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180010108`

## string_xrefs

- `0x18001006d`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x1800100d4`: `ptrSourceSession->AccessCheck( WINSTATION_QUERY ) failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000ffb0  push    rbp
0x18000ffb2  push    rbx
0x18000ffb3  push    rdi
0x18000ffb4  push    r14
0x18000ffb6  lea     rbp, [rsp-198h]
0x18000ffbe  sub     rsp, 298h
0x18000ffc5  mov     rax, cs:__security_cookie
0x18000ffcc  xor     rax, rsp
0x18000ffcf  mov     [rbp+1B0h+var_30], rax
0x18000ffd6  mov     rdi, rdx
0x18000ffd9  mov     [rsp+2B0h+var_288], 0
0x18000ffe2  mov     [rsp+2B0h+var_290], 0
0x18000ffea  mov     [rsp+2B0h+var_28C], 0
0x18000fff2  lea     r14, aRpcgetchildses; "RpcGetChildSessionId"
0x18000fff9  mov     r8, r14; char *
0x18000fffc  xor     edx, edx; int
0x18000fffe  lea     rcx, [rsp+2B0h+var_280]; this
0x180010003  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180010008  test    rdi, rdi
0x18001000b  jnz     short loc_180010017
0x18001000d  mov     ebx, 80070057h
0x180010012  jmp     loc_18001015E
0x180010017  mov     dword ptr [rdi], 0FFFFFFFFh
0x18001001d  lea     rcx, [rsp+2B0h+var_288]; struct ITSSession **
0x180010022  call    ?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z; CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)
0x180010027  mov     ebx, eax
0x180010029  test    eax, eax
0x18001002b  jns     short loc_180010049
0x18001002d  lea     rdx, aCrpcutilsGetse; "CRpcUtils::GetSessionFromRpcClientId fa"...
0x180010034  mov     r8d, eax
0x180010037  mov     r9, r14
0x18001003a  mov     ecx, 8; int
0x18001003f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010044  jmp     loc_18001015E
0x180010049  xor     ecx, ecx; BindingHandle
0x18001004b  call    cs:__imp_RpcImpersonateClient
0x180010052  nop     dword ptr [rax+rax+00h]
0x180010057  mov     ebx, eax
0x180010059  test    eax, eax
0x18001005b  jle     short loc_180010066
0x18001005d  movzx   ebx, ax
0x180010060  or      ebx, 80070000h
0x180010066  test    ebx, ebx
0x180010068  jns     short loc_180010076
0x18001006a  mov     r8d, ebx
0x18001006d  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180010074  jmp     short loc_180010037
0x180010076  mov     rcx, [rsp+2B0h+var_288]
0x18001007b  mov     rax, [rcx]
0x18001007e  xor     r8d, r8d
0x180010081  lea     edx, [r8+1]
0x180010085  mov     rax, [rax+88h]
0x18001008c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010091  mov     ebx, eax
0x180010093  call    cs:__imp_RpcRevertToSelf
0x18001009a  nop     dword ptr [rax+rax+00h]
0x18001009f  test    eax, eax
0x1800100a1  jle     short loc_1800100AD
0x1800100a3  movzx   eax, ax
0x1800100a6  or      eax, 80070000h
0x1800100ab  test    eax, eax
0x1800100ad  jns     short loc_1800100CD
0x1800100af  mov     r8d, eax
0x1800100b2  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x1800100b9  mov     ecx, 8; int
0x1800100be  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800100c3  mov     ebx, 80070005h
0x1800100c8  jmp     loc_18001015E
0x1800100cd  test    ebx, ebx
0x1800100cf  jns     short loc_1800100E0
0x1800100d1  mov     r8d, ebx
0x1800100d4  lea     rdx, aPtrsourcesessi; "ptrSourceSession->AccessCheck( WINSTATI"...
0x1800100db  jmp     loc_180010037
0x1800100e0  mov     rcx, [rsp+2B0h+var_288]
0x1800100e5  mov     rax, [rcx]
0x1800100e8  lea     rdx, [rsp+2B0h+var_290]
0x1800100ed  mov     rax, [rax+50h]
0x1800100f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100f6  mov     ebx, eax
0x1800100f8  test    eax, eax
0x1800100fa  jns     short loc_180010108
0x1800100fc  lea     rdx, aPtrsourcesessi_2; "ptrSourceSession->getId failed: 0x%x in"...
0x180010103  jmp     loc_180010034
0x180010108  call    cs:__imp_WTSGetServiceSessionId
0x18001010f  nop     dword ptr [rax+rax+00h]
0x180010114  cmp     [rsp+2B0h+var_290], eax
0x180010118  jnz     short loc_180010121
0x18001011a  mov     ebx, 80070032h
0x18001011f  jmp     short loc_18001015E
0x180010121  mov     rcx, [rsp+2B0h+var_288]
0x180010126  mov     rax, [rcx]
0x180010129  lea     rdx, [rsp+2B0h+var_28C]
0x18001012e  mov     rax, [rax+130h]
0x180010135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001013a  mov     ebx, eax
0x18001013c  test    eax, eax
0x18001013e  jns     short loc_18001014C
0x180010140  lea     rdx, aPtrsourcesessi_0; "ptrSourceSession->getChildSessionId fai"...
0x180010147  jmp     loc_180010034
0x18001014c  mov     eax, [rsp+2B0h+var_28C]
0x180010150  cmp     eax, 0FFFFFFFFh
0x180010153  jnz     short loc_18001015C
0x180010155  mov     ebx, 80070490h
0x18001015a  jmp     short loc_18001015E
0x18001015c  mov     [rdi], eax
0x18001015e  lea     rcx, [rsp+2B0h+var_280]; this
0x180010163  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180010168  nop
0x180010169  mov     rcx, [rsp+2B0h+var_288]
0x18001016e  test    rcx, rcx
0x180010171  jz      short loc_180010180
0x180010173  mov     rax, [rcx]
0x180010176  mov     rax, [rax+10h]
0x18001017a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001017f  nop
0x180010180  mov     eax, ebx
0x180010182  mov     rcx, [rbp+1B0h+var_30]
0x180010189  xor     rcx, rsp; StackCookie
0x18001018c  call    __security_check_cookie
0x180010191  add     rsp, 298h
0x180010198  pop     r14
0x18001019a  pop     rdi
0x18001019b  pop     rbx
0x18001019c  pop     rbp
0x18001019d  retn
```
