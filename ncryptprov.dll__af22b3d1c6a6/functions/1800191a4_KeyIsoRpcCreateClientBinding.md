# KeyIsoRpcCreateClientBinding

- ea: `0x1800191a4`
- end: `0x180019310`
- name: `KeyIsoRpcCreateClientBinding`
- size: `364`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018ea0`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x1800191a4`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x1800191dd`
- `RPCRT4!UuidFromStringW` at `0x1800191dd`
- `RPCRT4!RpcBindingFree` at `0x1800192f8`
- `RPCRT4!RpcBindingFree` at `0x1800192f8`
- `RPCRT4!RpcBindingCreateW` at `0x18001920d`
- `RPCRT4!RpcBindingCreateW` at `0x18001920d`
- `RPCRT4!RpcBindingBind` at `0x180019231`
- `RPCRT4!RpcBindingBind` at `0x180019231`

## string_xrefs

- `0x1800192aa`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\clibind.c`
- `0x1800192d6`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\clibind.c`

## pseudocode

```c
__int64 __fastcall KeyIsoRpcCreateClientBinding(__int64 a1, RPC_BINDING_HANDLE *a2)
{
  int v3; // edx
  unsigned int v4; // ebx
  unsigned int v5; // eax
  __int64 v7; // r9
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp+8h] BYREF

  Binding = 0;
  if ( a2 )
  {
    *a2 = 0;
    v4 = UuidFromStringW((RPC_WSTR)L"906B0CE0-C70B-1067-B317-00DD010662DA", &CALRPC_Template.ObjectUuid);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v3,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\clibind.c",
          (unsigned int)"rpcStatus",
          v4,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\clibind.c",
          122);
    }
    else
    {
      v5 = RpcBindingCreateW(&CALRPC_Template, &CALRPC_Security, &CALRPC_Options, &Binding);
      v4 = v5;
      if ( v5 )
      {
        v7 = 138;
      }
      else
      {
        v5 = RpcBindingBind(0, Binding, qword_180064F70);
        v4 = v5;
        if ( !v5 )
        {
          *a2 = Binding;
          return v4;
        }
        v7 = 153;
      }
      DebugTraceError(v5, "rpcStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\clibind.c", v7);
    }
  }
  else
  {
    v4 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\clibind.c",
        (unsigned int)"rpcStatus",
        87,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\clibind.c",
        109);
  }
  if ( *a2 )
  {
    RpcBindingFree(a2);
    *a2 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800191a4  mov     [rsp+arg_8], rbx
0x1800191a9  mov     [rsp+Binding], rcx
0x1800191ae  push    rdi
0x1800191af  sub     rsp, 40h
0x1800191b3  mov     [rsp+48h+Binding], 0
0x1800191bc  mov     rdi, rdx
0x1800191bf  test    rdx, rdx
0x1800191c2  jz      loc_18001925D
0x1800191c8  mov     qword ptr [rdx], 0
0x1800191cf  lea     rcx, StringUuid; "906B0CE0-C70B-1067-B317-00DD010662DA"
0x1800191d6  lea     rdx, CALRPC_Template.ObjectUuid; Uuid
0x1800191dd  call    cs:__imp_UuidFromStringW
0x1800191e4  nop     dword ptr [rax+rax+00h]
0x1800191e9  mov     ebx, eax
0x1800191eb  test    eax, eax
0x1800191ed  jnz     loc_180019285
0x1800191f3  lea     r9, [rsp+48h+Binding]; Binding
0x1800191f8  lea     r8, CALRPC_Options; Options
0x1800191ff  lea     rdx, CALRPC_Security; Security
0x180019206  lea     rcx, CALRPC_Template; Template
0x18001920d  call    cs:__imp_RpcBindingCreateW
0x180019214  nop     dword ptr [rax+rax+00h]
0x180019219  mov     ebx, eax
0x18001921b  test    eax, eax
0x18001921d  jnz     loc_1800192C8
0x180019223  mov     rdx, [rsp+48h+Binding]; Binding
0x180019228  lea     r8, qword_180064F70; IfSpec
0x18001922f  xor     ecx, ecx; pAsync
0x180019231  call    cs:__imp_RpcBindingBind
0x180019238  nop     dword ptr [rax+rax+00h]
0x18001923d  mov     ebx, eax
0x18001923f  test    eax, eax
0x180019241  jnz     loc_1800192D0
0x180019247  mov     rax, [rsp+48h+Binding]
0x18001924c  mov     [rdi], rax
0x18001924f  mov     eax, ebx
0x180019251  mov     rbx, [rsp+48h+arg_8]
0x180019256  add     rsp, 40h
0x18001925a  pop     rdi
0x18001925b  retn
0x18001925d  mov     ebx, 57h ; 'W'
0x180019262  mov     rcx, cs:WPP_GLOBAL_Control
0x180019269  lea     rax, WPP_GLOBAL_Control
0x180019270  cmp     rcx, rax
0x180019273  jz      short loc_1800192EB
0x180019275  test    byte ptr [rcx+1Ch], 1
0x180019279  jz      short loc_1800192EB
0x18001927b  mov     [rsp+48h+var_18], 6Dh ; 'm'
0x180019283  jmp     short loc_1800192A6
0x180019285  mov     rcx, cs:WPP_GLOBAL_Control
0x18001928c  lea     rax, WPP_GLOBAL_Control
0x180019293  cmp     rcx, rax
0x180019296  jz      short loc_1800192EB
0x180019298  test    byte ptr [rcx+1Ch], 1
0x18001929c  jz      short loc_1800192EB
0x18001929e  mov     [rsp+48h+var_18], 7Ah ; 'z'
0x1800192a6  mov     rcx, [rcx+10h]
0x1800192aa  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800192b1  mov     [rsp+48h+var_20], r8
0x1800192b6  lea     r9, aRpcstatus; "rpcStatus"
0x1800192bd  mov     [rsp+48h+var_28], ebx
0x1800192c1  call    WPP_SF_sDsd
0x1800192c6  jmp     short loc_1800192EB
0x1800192c8  mov     r9d, 8Ah
0x1800192ce  jmp     short loc_1800192D6
0x1800192d0  mov     r9d, 99h
0x1800192d6  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800192dd  mov     ecx, eax
0x1800192df  lea     rdx, aRpcstatus; "rpcStatus"
0x1800192e6  call    DebugTraceError
0x1800192eb  cmp     qword ptr [rdi], 0
0x1800192ef  jz      loc_18001924F
0x1800192f5  mov     rcx, rdi; Binding
0x1800192f8  call    cs:__imp_RpcBindingFree
0x1800192ff  nop     dword ptr [rax+rax+00h]
0x180019304  mov     qword ptr [rdi], 0
0x18001930b  jmp     loc_18001924F
```
