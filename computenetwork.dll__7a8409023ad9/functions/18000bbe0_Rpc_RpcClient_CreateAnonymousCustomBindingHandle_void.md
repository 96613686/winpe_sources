# Rpc::RpcClient::CreateAnonymousCustomBindingHandle(void)

- ea: `0x18000bbe0`
- end: `0x18000bd54`
- name: `?CreateAnonymousCustomBindingHandle@RpcClient@Rpc@@AEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `372`
- prototype: `unsigned __int16 *__fastcall(__int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bd5c`

## callees

- `0x18000bbe0`
- `0x18000c0bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bca9`
- `RPCRT4!RpcEpResolveBinding` at `0x18000bcf1`
- `RPCRT4!RpcEpResolveBinding` at `0x18000bcf1`
- `RPCRT4!RpcStringFreeW` at `0x18000bd14`
- `RPCRT4!RpcStringFreeW` at `0x18000bd14`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000bc8e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000bc8e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000bcd8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000bcd8`
- `RPCRT4!RpcBindingFree` at `0x18000bcbb`
- `RPCRT4!RpcBindingFree` at `0x18000bcbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall Rpc::RpcClient::CreateAnonymousCustomBindingHandle(__int64 a1, unsigned __int16 *a2)
{
  unsigned __int16 *v4; // r9
  unsigned __int16 *v5; // r8
  unsigned __int16 *v6; // rdx
  unsigned __int16 *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // r8d
  RPC_BINDING_HANDLE v10; // rbp
  DWORD LastError; // ebx
  unsigned int v12; // eax
  unsigned int v13; // r8d
  unsigned int v14; // eax
  unsigned int v15; // r8d
  unsigned int Options; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  RPC_WSTR StringBinding; // [rsp+60h] [rbp+8h] BYREF
  RPC_WSTR String; // [rsp+68h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+18h] BYREF

  String = a2;
  *(_QWORD *)a2 = 0;
  StringBinding = 0;
  v4 = (unsigned __int16 *)(a1 + 80);
  if ( *(_QWORD *)(a1 + 96) )
  {
    if ( *(_QWORD *)(a1 + 104) > 7u )
      v4 = *(unsigned __int16 **)v4;
  }
  else
  {
    v4 = 0;
  }
  v5 = (unsigned __int16 *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 32) )
  {
    if ( *(_QWORD *)(a1 + 40) > 7u )
      v5 = *(unsigned __int16 **)v5;
  }
  else
  {
    v5 = 0;
  }
  v6 = (unsigned __int16 *)(a1 + 48);
  if ( *(_QWORD *)(a1 + 64) )
  {
    if ( *(_QWORD *)(a1 + 72) > 7u )
      v6 = *(unsigned __int16 **)v6;
  }
  else
  {
    v6 = 0;
  }
  v7 = (unsigned __int16 *)(a1 + 112);
  if ( *((_QWORD *)v7 + 2) )
  {
    if ( *((_QWORD *)v7 + 3) > 7u )
      v7 = *(unsigned __int16 **)v7;
  }
  else
  {
    v7 = 0;
  }
  v8 = RpcStringBindingComposeW(v7, v6, v5, v4, 0, &StringBinding);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x8D, v9, (const char *)v8, Options);
  v10 = *(RPC_BINDING_HANDLE *)a2;
  if ( *(_QWORD *)a2 )
  {
    LastError = GetLastError();
    Binding = v10;
    RpcBindingFree(&Binding);
    SetLastError(LastError);
  }
  *(_QWORD *)a2 = 0;
  v12 = RpcBindingFromStringBindingW(StringBinding, (RPC_BINDING_HANDLE *)a2);
  if ( v12 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x91, v13, (const char *)v12, Options);
  v14 = RpcEpResolveBinding(*(RPC_BINDING_HANDLE *)a2, *(RPC_IF_HANDLE *)(a1 + 144));
  if ( v14 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x93, v15, (const char *)v14, Options);
  if ( StringBinding )
  {
    String = StringBinding;
    RpcStringFreeW(&String);
  }
  return a2;
}

```

## disassembly

```asm
0x18000bbe0  mov     rax, rsp
0x18000bbe3  mov     [rax+20h], rbx
0x18000bbe7  mov     [rax+10h], rdx
0x18000bbeb  push    rbp
0x18000bbec  push    rsi
0x18000bbed  push    rdi
0x18000bbee  sub     rsp, 40h
0x18000bbf2  mov     rdi, rdx
0x18000bbf5  mov     rsi, rcx
0x18000bbf8  mov     dword ptr [rax-28h], 0
0x18000bbff  mov     qword ptr [rdx], 0
0x18000bc06  mov     dword ptr [rax-28h], 1
0x18000bc0d  mov     qword ptr [rax+8], 0
0x18000bc15  lea     r9, [rcx+50h]
0x18000bc19  cmp     qword ptr [r9+10h], 0
0x18000bc1e  jnz     short loc_18000BC25
0x18000bc20  xor     r9d, r9d
0x18000bc23  jmp     short loc_18000BC2F
0x18000bc25  cmp     qword ptr [r9+18h], 7
0x18000bc2a  jbe     short loc_18000BC2F
0x18000bc2c  mov     r9, [r9]; Endpoint
0x18000bc2f  lea     r8, [rcx+10h]
0x18000bc33  cmp     qword ptr [r8+10h], 0
0x18000bc38  jnz     short loc_18000BC3F
0x18000bc3a  xor     r8d, r8d
0x18000bc3d  jmp     short loc_18000BC49
0x18000bc3f  cmp     qword ptr [r8+18h], 7
0x18000bc44  jbe     short loc_18000BC49
0x18000bc46  mov     r8, [r8]; NetworkAddr
0x18000bc49  lea     rdx, [rcx+30h]
0x18000bc4d  cmp     qword ptr [rdx+10h], 0
0x18000bc52  jnz     short loc_18000BC58
0x18000bc54  xor     edx, edx
0x18000bc56  jmp     short loc_18000BC62
0x18000bc58  cmp     qword ptr [rdx+18h], 7
0x18000bc5d  jbe     short loc_18000BC62
0x18000bc5f  mov     rdx, [rdx]; ProtSeq
0x18000bc62  add     rcx, 70h ; 'p'
0x18000bc66  cmp     qword ptr [rcx+10h], 0
0x18000bc6b  jnz     short loc_18000BC71
0x18000bc6d  xor     ecx, ecx
0x18000bc6f  jmp     short loc_18000BC7B
0x18000bc71  cmp     qword ptr [rcx+18h], 7
0x18000bc76  jbe     short loc_18000BC7B
0x18000bc78  mov     rcx, [rcx]; ObjUuid
0x18000bc7b  lea     rax, [rsp+58h+arg_0]
0x18000bc80  mov     [rsp+58h+StringBinding], rax; StringBinding
0x18000bc85  mov     [rsp+58h+Options], 0; unsigned int
0x18000bc8e  call    cs:__imp_RpcStringBindingComposeW
0x18000bc94  mov     rcx, [rsp+58h]; this
0x18000bc99  test    eax, eax
0x18000bc9b  jnz     loc_18000BD38
0x18000bca1  mov     rbp, [rdi]
0x18000bca4  test    rbp, rbp
0x18000bca7  jz      short loc_18000BCC9
0x18000bca9  call    cs:__imp_GetLastError
0x18000bcaf  mov     ebx, eax
0x18000bcb1  mov     [rsp+58h+Binding], rbp
0x18000bcb6  lea     rcx, [rsp+58h+Binding]; Binding
0x18000bcbb  call    cs:__imp_RpcBindingFree
0x18000bcc1  mov     ecx, ebx; dwErrCode
0x18000bcc3  call    cs:__imp_SetLastError
0x18000bcc9  mov     qword ptr [rdi], 0
0x18000bcd0  mov     rdx, rdi; Binding
0x18000bcd3  mov     rcx, [rsp+58h+arg_0]; StringBinding
0x18000bcd8  call    cs:__imp_RpcBindingFromStringBindingW
0x18000bcde  mov     rcx, [rsp+58h]; this
0x18000bce3  test    eax, eax
0x18000bce5  jnz     short loc_18000BD46
0x18000bce7  mov     rdx, [rsi+90h]; IfSpec
0x18000bcee  mov     rcx, [rdi]; Binding
0x18000bcf1  call    cs:__imp_RpcEpResolveBinding
0x18000bcf7  mov     rcx, [rsp+58h]; this
0x18000bcfc  test    eax, eax
0x18000bcfe  jnz     short loc_18000BD2A
0x18000bd00  mov     rax, [rsp+58h+arg_0]
0x18000bd05  test    rax, rax
0x18000bd08  jz      short loc_18000BD1A
0x18000bd0a  mov     [rsp+58h+String], rax
0x18000bd0f  lea     rcx, [rsp+58h+String]; String
0x18000bd14  call    cs:__imp_RpcStringFreeW
0x18000bd1a  mov     rax, rdi
0x18000bd1d  mov     rbx, [rsp+58h+arg_18]
0x18000bd22  add     rsp, 40h
0x18000bd26  pop     rdi
0x18000bd27  pop     rsi
0x18000bd28  pop     rbp
0x18000bd29  retn
0x18000bd2a  mov     r9d, eax; char *
0x18000bd2d  mov     edx, 93h; void *
0x18000bd32  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000bd38  mov     r9d, eax; char *
0x18000bd3b  mov     edx, 8Dh; void *
0x18000bd40  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000bd46  mov     r9d, eax; char *
0x18000bd49  mov     edx, 91h; void *
0x18000bd4e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
