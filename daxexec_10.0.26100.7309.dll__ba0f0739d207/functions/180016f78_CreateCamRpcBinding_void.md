# CreateCamRpcBinding(void * *)

- ea: `0x180016f78`
- end: `0x180017177`
- name: `?CreateCamRpcBinding@@YAJPEAPEAX@Z`
- size: `511`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016bcc`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x180016f78`
- `0x18001e32c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017090`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800170b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800170b6`
- `RPCRT4!RpcBindingBind` at `0x180017130`
- `RPCRT4!RpcBindingBind` at `0x180017130`
- `RPCRT4!RpcBindingCreateW` at `0x1800170d4`
- `RPCRT4!RpcBindingCreateW` at `0x1800170d4`
- `RPCRT4!RpcBindingFree` at `0x1800170a8`
- `RPCRT4!RpcBindingFree` at `0x180017112`
- `RPCRT4!RpcBindingFree` at `0x1800170a8`
- `RPCRT4!RpcBindingFree` at `0x180017112`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001703f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001703f`

## string_xrefs

- `0x1800170ed`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
__int64 __fastcall CreateCamRpcBinding(void **a1)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  RPC_BINDING_HANDLE v6; // [rsp+28h] [rbp-E0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-D8h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-D0h] BYREF
  _DWORD Security[11]; // [rsp+3Ch] [rbp-CCh] BYREF
  _DWORD v10[2]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v11[4]; // [rsp+70h] [rbp-98h]
  __int128 v12; // [rsp+90h] [rbp-78h]
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+A0h] [rbp-68h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE pSid[80]; // [rsp+E8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  *a1 = 0;
  v6 = 0;
  Options.CallTimeout = 0;
  *(_QWORD *)&Security[2] = 0;
  Security[4] = 0;
  *(_QWORD *)&Security[7] = 0;
  v11[0] = 0x300000000LL;
  memset(&Template.ProtocolSequence + 1, 0, 28);
  Template.Version = 1;
  *(_OWORD *)&v11[1] = 0;
  Template.Flags = 1;
  Template.ProtocolSequence = 3;
  v12 = 0;
  v10[0] = 5;
  Template.ObjectUuid = (UUID)xmmword_1800D0414;
  v10[1] = 17;
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid);
  Options.ComTimeout = 5;
  v11[3] = pSid;
  *(_QWORD *)&Security[9] = v10;
  Security[1] = 1;
  Security[5] = 6;
  Security[6] = 20;
  Options.Version = 1;
  Options.Flags = 2;
  v2 = RpcBindingCreateW(&Template, (RPC_BINDING_HANDLE_SECURITY_V1_W *)&Security[1], &Options, &v6);
  if ( v2 )
  {
    v3 = 427;
  }
  else
  {
    v2 = RpcBindingBind(0, v6, &unk_1800D0410);
    if ( !v2 )
    {
      *a1 = v6;
      return 0;
    }
    v3 = 432;
  }
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v3,
         (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
         (const char *)v2,
         (unsigned int)v6);
  if ( v6 )
  {
    Binding = v6;
    RpcBindingFree(&Binding);
  }
  return v4;
}

```

## disassembly

```asm
0x180016f78  mov     rax, rsp
0x180016f7b  mov     [rax+10h], rbx
0x180016f7f  mov     [rax+18h], rsi
0x180016f83  mov     [rax+20h], rdi
0x180016f87  push    rbp
0x180016f88  lea     rbp, [rax-48h]
0x180016f8c  sub     rsp, 140h
0x180016f93  mov     rax, cs:__security_cookie
0x180016f9a  xor     rax, rsp
0x180016f9d  mov     [rbp+40h+var_10], rax
0x180016fa1  and     qword ptr [rcx], 0
0x180016fa5  mov     eax, 3
0x180016faa  and     [rsp+140h+var_120], 0
0x180016fb0  xorps   xmm0, xmm0
0x180016fb3  and     [rbp+40h+Template.StringEndpoint+4], 0
0x180016fb8  mov     rdi, rcx
0x180016fbb  and     dword ptr [rbp+40h+Template.u1+4], 0
0x180016fbf  lea     rcx, [rbp+40h+pSid]; void *
0x180016fc3  and     [rbp+40h+Options.CallTimeout], 0
0x180016fc7  lea     ebx, [rax+41h]
0x180016fca  and     qword ptr [rsp+140h+Security+8], 0
0x180016fd0  lea     esi, [rax+2]
0x180016fd3  and     dword ptr [rsp+140h+Security+10h], 0
0x180016fd8  xorps   xmm1, xmm1
0x180016fdb  and     qword ptr [rsp+140h+Security+1Ch], 0
0x180016fe1  mov     r8d, ebx; Size
0x180016fe4  and     dword ptr [rsp+140h+var_D8], 0
0x180016fe9  xor     edx, edx; Val
0x180016feb  movdqu  xmmword ptr [rbp+40h+Template+0Ch], xmm0
0x180016ff0  mov     [rbp+40h+Template.Version], 1
0x180016ff7  movdqu  xmmword ptr [rsp+140h+var_D8+8], xmm0
0x180016ffd  mov     [rbp+40h+Template.Flags], 1
0x180017004  movups  xmm0, cs:xmmword_1800D0414
0x18001700b  mov     [rbp+40h+Template.ProtocolSequence], eax
0x18001700e  movdqu  [rbp+40h+var_B8], xmm1
0x180017013  mov     [rsp+140h+var_E0], esi
0x180017017  movdqu  xmmword ptr [rbp+40h+Template.ObjectUuid.Data1], xmm0
0x18001701c  mov     dword ptr [rsp+140h+var_D8+4], eax
0x180017020  mov     [rsp+140h+var_DC], 11h
0x180017028  call    memset_0
0x18001702d  lea     r9, [rsp+140h+cbSid]; cbSid
0x180017032  mov     [rsp+140h+cbSid], ebx
0x180017036  lea     r8, [rbp+40h+pSid]; pSid
0x18001703a  xor     edx, edx; DomainSid
0x18001703c  lea     ecx, [rsi+11h]; WellKnownSidType
0x18001703f  call    cs:__imp_CreateWellKnownSid
0x180017046  nop     dword ptr [rax+rax+00h]
0x18001704b  lea     rax, [rbp+40h+pSid]
0x18001704f  mov     [rbp+40h+Options.ComTimeout], esi
0x180017052  mov     rsi, [rsp+140h+var_120]
0x180017057  mov     [rbp+40h+var_C0], rax
0x18001705b  lea     rax, [rsp+140h+var_E0]
0x180017060  mov     qword ptr [rsp+140h+Security+24h], rax
0x180017065  mov     dword ptr [rsp+140h+Security+4], 1
0x18001706d  mov     dword ptr [rsp+140h+Security+14h], 6
0x180017075  mov     dword ptr [rsp+140h+Security+18h], 14h
0x18001707d  mov     [rbp+40h+Options.Version], 1
0x180017084  mov     [rbp+40h+Options.Flags], 2
0x18001708b  test    rsi, rsi
0x18001708e  jz      short loc_1800170C2
0x180017090  call    cs:__imp_GetLastError
0x180017097  nop     dword ptr [rax+rax+00h]
0x18001709c  lea     rcx, [rsp+140h+Binding]; Binding
0x1800170a1  mov     [rsp+140h+Binding], rsi
0x1800170a6  mov     ebx, eax
0x1800170a8  call    cs:__imp_RpcBindingFree
0x1800170af  nop     dword ptr [rax+rax+00h]
0x1800170b4  mov     ecx, ebx; dwErrCode
0x1800170b6  call    cs:__imp_SetLastError
0x1800170bd  nop     dword ptr [rax+rax+00h]
0x1800170c2  lea     r9, [rsp+140h+var_120]; Binding
0x1800170c7  lea     r8, [rbp+40h+Options]; Options
0x1800170cb  lea     rdx, [rsp+140h+Security+4]; Security
0x1800170d0  lea     rcx, [rbp+40h+Template]; Template
0x1800170d4  call    cs:__imp_RpcBindingCreateW
0x1800170db  nop     dword ptr [rax+rax+00h]
0x1800170e0  test    eax, eax
0x1800170e2  jz      short loc_180017122
0x1800170e4  mov     edx, 1ABh; void *
0x1800170e9  mov     rcx, [rbp+48h]; this
0x1800170ed  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800170f4  mov     r9d, eax; char *
0x1800170f7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800170fc  mov     rcx, [rsp+140h+var_120]
0x180017101  mov     ebx, eax
0x180017103  test    rcx, rcx
0x180017106  jz      short loc_18001711E
0x180017108  mov     [rsp+140h+Binding], rcx
0x18001710d  lea     rcx, [rsp+140h+Binding]; Binding
0x180017112  call    cs:__imp_RpcBindingFree
0x180017119  nop     dword ptr [rax+rax+00h]
0x18001711e  mov     eax, ebx
0x180017120  jmp     short loc_180017151
0x180017122  mov     rdx, [rsp+140h+var_120]; Binding
0x180017127  lea     r8, unk_1800D0410; IfSpec
0x18001712e  xor     ecx, ecx; pAsync
0x180017130  call    cs:__imp_RpcBindingBind
0x180017137  nop     dword ptr [rax+rax+00h]
0x18001713c  test    eax, eax
0x18001713e  jz      short loc_180017147
0x180017140  mov     edx, 1B0h
0x180017145  jmp     short loc_1800170E9
0x180017147  mov     rax, [rsp+140h+var_120]
0x18001714c  mov     [rdi], rax
0x18001714f  xor     eax, eax
0x180017151  mov     rcx, [rbp+40h+var_10]
0x180017155  xor     rcx, rsp; StackCookie
0x180017158  call    __security_check_cookie
0x18001715d  lea     r11, [rsp+140h+var_s0]
0x180017165  mov     rbx, [r11+18h]
0x180017169  mov     rsi, [r11+20h]
0x18001716d  mov     rdi, [r11+28h]
0x180017171  mov     rsp, r11
0x180017174  pop     rbp
0x180017175  retn
```
