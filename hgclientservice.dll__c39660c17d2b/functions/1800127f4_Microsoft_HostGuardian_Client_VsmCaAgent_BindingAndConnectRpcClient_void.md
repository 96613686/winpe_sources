# Microsoft::HostGuardian::Client::VsmCaAgent::BindingAndConnectRpcClient(void)

- ea: `0x1800127f4`
- end: `0x180012883`
- name: `?BindingAndConnectRpcClient@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ`
- size: `143`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013954`

## callees

- `0x180008760`
- `0x1800127f4`
- `0x180013438`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001283e`
- `RPCRT4!NdrClientCall3` at `0x18001283e`

## string_xrefs

- `0x180012871`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::BindingAndConnectRpcClient(void **this)
{
  Microsoft::HostGuardian::Client::VsmCaAgent *v2; // rcx
  int Pointer; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Microsoft::HostGuardian::Client::VsmCaAgent::InitializeRpcClient(
    (Microsoft::HostGuardian::Client::VsmCaAgent *)this,
    qword_1800189A0,
    this);
  Microsoft::HostGuardian::Client::VsmCaAgent::InitializeRpcClient(v2, qword_180018B30, this + 1);
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, *this, this + 2).Pointer;
  if ( Pointer < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D2,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)(unsigned int)Pointer,
      v4);
}

```

## disassembly

```asm
0x1800127f4  push    rbx
0x1800127f6  sub     rsp, 40h
0x1800127fa  mov     rbx, rcx
0x1800127fd  mov     r8, rcx; void **
0x180012800  lea     rdx, qword_1800189A0; void *
0x180012807  call    ?InitializeRpcClient@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXPEAXPEAPEAX@Z; Microsoft::HostGuardian::Client::VsmCaAgent::InitializeRpcClient(void *,void * *)
0x18001280c  lea     r8, [rbx+8]; void **
0x180012810  lea     rdx, qword_180018B30; void *
0x180012817  call    ?InitializeRpcClient@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXPEAXPEAPEAX@Z; Microsoft::HostGuardian::Client::VsmCaAgent::InitializeRpcClient(void *,void * *)
0x18001281c  nop
0x18001281d  mov     r9, [rbx]
0x180012820  mov     [rsp+48h+arg_0], 0
0x180012829  lea     rax, [rbx+10h]
0x18001282d  mov     qword ptr [rsp+48h+var_28], rax
0x180012832  xor     r8d, r8d; pReturnValue
0x180012835  xor     edx, edx; nProcNum
0x180012837  lea     rcx, pProxyInfo; pProxyInfo
0x18001283e  call    cs:__imp_NdrClientCall3
0x180012844  mov     [rsp+48h+arg_0], rax
0x180012849  mov     [rsp+48h+var_18], eax
0x18001284d  jmp     short loc_18001285F
0x18001284f  test    eax, eax
0x180012851  jle     short loc_18001285B
0x180012853  movzx   eax, ax
0x180012856  or      eax, 80070000h
0x18001285b  mov     [rsp+48h+var_18], eax
0x18001285f  test    eax, eax
0x180012861  js      short loc_180012869
0x180012863  add     rsp, 40h
0x180012867  pop     rbx
0x180012868  retn
0x180012869  mov     rcx, [rsp+48h]; this
0x18001286e  mov     r9d, eax; char *
0x180012871  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012878  mov     edx, 1D2h; void *
0x18001287d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
