# Microsoft::HostGuardian::Client::VsmCaAgent::InitializeRpcClient(void *,void * *)

- ea: `0x180013438`
- end: `0x18001369b`
- name: `?InitializeRpcClient@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXPEAXPEAPEAX@Z`
- size: `611`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::VsmCaAgent *this, void *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800127f4`

## callees

- `0x180001770`
- `0x1800077a0`
- `0x180008760`
- `0x180013438`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800134cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800134cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134b5`
- `RPCRT4!RpcEpResolveBinding` at `0x180013556`
- `RPCRT4!RpcEpResolveBinding` at `0x180013556`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001352e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001352e`
- `RPCRT4!RpcBindingSetOption` at `0x180013584`
- `RPCRT4!RpcBindingSetOption` at `0x180013584`
- `RPCRT4!RpcStringFreeW` at `0x1800134c5`
- `RPCRT4!RpcStringFreeW` at `0x180013617`
- `RPCRT4!RpcStringFreeW` at `0x1800134c5`
- `RPCRT4!RpcStringFreeW` at `0x180013617`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800135e8`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800135e8`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013500`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013500`

## string_xrefs

- `0x180013641`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180013653`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180013665`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180013677`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180013689`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::InitializeRpcClient(
        Microsoft::HostGuardian::Client::VsmCaAgent *this,
        void *a2,
        void **a3)
{
  RPC_STATUS v5; // eax
  unsigned __int64 v6; // r9
  RPC_STATUS v7; // eax
  unsigned __int64 v8; // r9
  RPC_STATUS v9; // eax
  unsigned __int64 v10; // r9
  RPC_STATUS v11; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  RPC_SECURITY_QOS *p_SecurityQOS; // rax
  RPC_STATUS v15; // eax
  unsigned __int64 v16; // r9
  int Options; // [rsp+20h] [rbp-29h]
  int Optionsa; // [rsp+20h] [rbp-29h]
  RPC_WSTR StringBinding; // [rsp+40h] [rbp-9h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-1h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v22[16]; // [rsp+60h] [rbp+17h] BYREF
  const wchar_t *v23; // [rsp+70h] [rbp+27h]
  __int64 v24; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  StringBinding = 0;
  SecurityQOS = 0;
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v23 = L"InitializeRpcClient...";
    v24 = 46;
    McGenEventWrite_EventWriteTransfer(this, ServiceDebugInformational, a3, 2, v22);
  }
  StringBinding = 0;
  v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &StringBinding);
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  else
    v6 = (unsigned int)v5;
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)v6,
      Options);
  v7 = RpcBindingFromStringBindingW(StringBinding, a3);
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  else
    v8 = (unsigned int)v7;
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)v8,
      Options);
  v9 = RpcEpResolveBinding(*a3, a2);
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  else
    v10 = (unsigned int)v9;
  if ( v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)v10,
      Options);
  v11 = RpcBindingSetOption(*a3, 0xCu, 0x15F90u);
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  else
    v12 = (unsigned int)v11;
  if ( v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)v12,
      Options);
  v13 = 16;
  p_SecurityQOS = &SecurityQOS;
  do
  {
    LOBYTE(p_SecurityQOS->Version) = 0;
    p_SecurityQOS = (RPC_SECURITY_QOS *)((char *)p_SecurityQOS + 1);
    --v13;
  }
  while ( v13 );
  *(_QWORD *)&SecurityQOS.Version = 1;
  SecurityQOS.IdentityTracking = 0;
  SecurityQOS.ImpersonationType = 3;
  v15 = RpcBindingSetAuthInfoExW(*a3, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
  if ( v15 > 0 )
    v16 = (unsigned __int16)v15 | 0x80070000;
  else
    v16 = (unsigned int)v15;
  if ( v15 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)v16,
      Optionsa);
  if ( StringBinding )
  {
    String = StringBinding;
    RpcStringFreeW(&String);
  }
}

```

## disassembly

```asm
0x180013438  mov     [rsp-8+arg_0], rbx
0x18001343d  mov     [rsp-8+arg_18], rsi
0x180013442  push    rbp
0x180013443  push    rdi
0x180013444  push    r14
0x180013446  lea     rbp, [rsp-47h]
0x18001344b  sub     rsp, 90h
0x180013452  mov     rax, cs:__security_cookie
0x180013459  xor     rax, rsp
0x18001345c  mov     [rbp+57h+var_20], rax
0x180013460  mov     rsi, r8
0x180013463  mov     r14, rdx
0x180013466  mov     [rbp+57h+var_60], 0
0x18001346e  xorps   xmm0, xmm0
0x180013471  movups  xmmword ptr [rbp+57h+var_50.Version], xmm0
0x180013475  mov     r9d, 2
0x18001347b  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, r9b
0x180013482  jz      short loc_1800134D3
0x180013484  lea     rax, aInitializerpcc; "InitializeRpcClient..."
0x18001348b  mov     [rbp+57h+var_30], rax
0x18001348f  mov     [rbp+57h+var_28], 2Eh ; '.'
0x180013497  lea     rax, [rbp+57h+var_40]
0x18001349b  mov     [rsp+0A0h+Options], rax
0x1800134a0  lea     rdx, ServiceDebugInformational
0x1800134a7  call    McGenEventWrite_EventWriteTransfer
0x1800134ac  mov     rdi, [rbp+57h+var_60]
0x1800134b0  test    rdi, rdi
0x1800134b3  jz      short loc_1800134D3
0x1800134b5  call    cs:__imp_GetLastError
0x1800134bb  mov     ebx, eax
0x1800134bd  mov     [rbp+57h+String], rdi
0x1800134c1  lea     rcx, [rbp+57h+String]; String
0x1800134c5  call    cs:__imp_RpcStringFreeW
0x1800134cb  mov     ecx, ebx; dwErrCode
0x1800134cd  call    cs:__imp_SetLastError
0x1800134d3  mov     [rbp+57h+var_60], 0
0x1800134db  lea     rax, [rbp+57h+var_60]
0x1800134df  mov     [rsp+0A0h+StringBinding], rax; StringBinding
0x1800134e4  mov     [rsp+0A0h+Options], 0; int
0x1800134ed  lea     r9, Endpoint; "VMPLATFORMCA_RPC_SERVER"
0x1800134f4  xor     r8d, r8d; NetworkAddr
0x1800134f7  lea     rdx, ProtSeq; "ncalrpc"
0x1800134fe  xor     ecx, ecx; ObjUuid
0x180013500  call    cs:__imp_RpcStringBindingComposeW
0x180013506  mov     ebx, 80070000h
0x18001350b  test    eax, eax
0x18001350d  jg      short loc_180013514
0x18001350f  mov     r9d, eax
0x180013512  jmp     short loc_18001351B
0x180013514  movzx   r9d, ax
0x180013518  or      r9d, ebx; char *
0x18001351b  mov     rcx, [rbp+5Fh]; this
0x18001351f  test    eax, eax
0x180013521  jnz     loc_180013653
0x180013527  mov     rdx, rsi; Binding
0x18001352a  mov     rcx, [rbp+57h+var_60]; StringBinding
0x18001352e  call    cs:__imp_RpcBindingFromStringBindingW
0x180013534  test    eax, eax
0x180013536  jg      short loc_18001353D
0x180013538  mov     r9d, eax
0x18001353b  jmp     short loc_180013544
0x18001353d  movzx   r9d, ax
0x180013541  or      r9d, ebx; char *
0x180013544  mov     rcx, [rbp+5Fh]; this
0x180013548  test    eax, eax
0x18001354a  jnz     loc_180013665
0x180013550  mov     rdx, r14; IfSpec
0x180013553  mov     rcx, [rsi]; Binding
0x180013556  call    cs:__imp_RpcEpResolveBinding
0x18001355c  test    eax, eax
0x18001355e  jg      short loc_180013565
0x180013560  mov     r9d, eax
0x180013563  jmp     short loc_18001356C
0x180013565  movzx   r9d, ax
0x180013569  or      r9d, ebx; char *
0x18001356c  mov     rcx, [rbp+5Fh]; this
0x180013570  test    eax, eax
0x180013572  jnz     loc_180013677
0x180013578  lea     edx, [rax+0Ch]; option
0x18001357b  mov     r8d, 15F90h; optionValue
0x180013581  mov     rcx, [rsi]; hBinding
0x180013584  call    cs:__imp_RpcBindingSetOption
0x18001358a  test    eax, eax
0x18001358c  jg      short loc_180013593
0x18001358e  mov     r9d, eax
0x180013591  jmp     short loc_18001359A
0x180013593  movzx   r9d, ax
0x180013597  or      r9d, ebx; char *
0x18001359a  mov     rcx, [rbp+5Fh]; this
0x18001359e  test    eax, eax
0x1800135a0  jnz     loc_180013689
0x1800135a6  lea     edx, [rax+10h]
0x1800135a9  lea     rax, [rbp+57h+var_50]
0x1800135ad  mov     byte ptr [rax], 0
0x1800135b0  inc     rax
0x1800135b3  sub     rdx, 1; ServerPrincName
0x1800135b7  jnz     short loc_1800135AD
0x1800135b9  mov     qword ptr [rbp+57h+var_50.Version], 1
0x1800135c1  mov     [rbp+57h+var_50.IdentityTracking], edx
0x1800135c4  mov     [rbp+57h+var_50.ImpersonationType], 3
0x1800135cb  lea     rax, [rbp+57h+var_50]
0x1800135cf  mov     [rsp+0A0h+SecurityQOS], rax; SecurityQOS
0x1800135d4  mov     dword ptr [rsp+0A0h+StringBinding], edx; AuthzSvc
0x1800135d8  mov     [rsp+0A0h+Options], rdx; int
0x1800135dd  lea     r9d, [rdx+0Ah]; AuthnSvc
0x1800135e1  lea     r8d, [rdx+6]; AuthnLevel
0x1800135e5  mov     rcx, [rsi]; Binding
0x1800135e8  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800135ee  test    eax, eax
0x1800135f0  jg      short loc_1800135F7
0x1800135f2  mov     r9d, eax
0x1800135f5  jmp     short loc_1800135FE
0x1800135f7  movzx   r9d, ax
0x1800135fb  or      r9d, ebx; char *
0x1800135fe  mov     rcx, [rbp+5Fh]; this
0x180013602  test    eax, eax
0x180013604  jnz     short loc_180013641
0x180013606  mov     rax, [rbp+57h+var_60]
0x18001360a  test    rax, rax
0x18001360d  jz      short loc_18001361D
0x18001360f  mov     [rbp+57h+String], rax
0x180013613  lea     rcx, [rbp+57h+String]; String
0x180013617  call    cs:__imp_RpcStringFreeW
0x18001361d  mov     rcx, [rbp+57h+var_20]
0x180013621  xor     rcx, rsp; StackCookie
0x180013624  call    __security_check_cookie
0x180013629  lea     r11, [rsp+0A0h+var_10]
0x180013631  mov     rbx, [r11+20h]
0x180013635  mov     rsi, [r11+38h]
0x180013639  mov     rsp, r11
0x18001363c  pop     r14
0x18001363e  pop     rdi
0x18001363f  pop     rbp
0x180013640  retn
0x180013641  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180013648  mov     edx, 152h; void *
0x18001364d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013653  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x18001365a  mov     edx, 123h; void *
0x18001365f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013665  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x18001366c  mov     edx, 12Bh; void *
0x180013671  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013677  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x18001367e  mov     edx, 133h; void *
0x180013683  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013689  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180013690  mov     edx, 142h; void *
0x180013695  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
