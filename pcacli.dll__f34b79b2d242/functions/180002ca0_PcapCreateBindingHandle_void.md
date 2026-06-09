# PcapCreateBindingHandle(void * *)

- ea: `0x180002ca0`
- end: `0x180002ee1`
- name: `?PcapCreateBindingHandle@@YAKPEAPEAX@Z`
- size: `577`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800012c0`
- `0x180001bd0`
- `0x180007040`
- `0x1800082c0`
- `0x180008480`

## callees

- `0x180002ca0`
- `0x180007738`
- `0x18000c030`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180002dad`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180002dad`
- `RPCRT4!RpcStringFreeW` at `0x180002e3c`
- `RPCRT4!RpcStringFreeW` at `0x180002e3c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180002dfd`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180002dfd`
- `RPCRT4!RpcStringBindingComposeW` at `0x180002d57`
- `RPCRT4!RpcStringBindingComposeW` at `0x180002d57`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180002d6f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180002d6f`
- `RPCRT4!RpcBindingSetOption` at `0x180002d8e`
- `RPCRT4!RpcBindingSetOption` at `0x180002d8e`
- `RPCRT4!RpcBindingFree` at `0x180002ec7`
- `RPCRT4!RpcBindingFree` at `0x180002ed6`
- `RPCRT4!RpcBindingFree` at `0x180002ec7`
- `RPCRT4!RpcBindingFree` at `0x180002ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e9d`

## string_xrefs

- `0x180002e68`: `PcapCreateBindingHandle`
- `0x180002e5b`: `RpcStringBindingCompose failed [%d]`
- `0x180002ea3`: `Failed to create sid [%d]`

## pseudocode

```c
__int64 __fastcall PcapCreateBindingHandle(void **a1)
{
  __int64 result; // rax
  DWORD LastError; // eax
  DWORD v4; // edi
  const char *v5; // r9
  __int64 v6; // r8
  RPC_WSTR Options; // [rsp+20h] [rbp-69h]
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-49h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-41h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-39h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+58h] [rbp-31h] BYREF
  __int128 v12; // [rsp+68h] [rbp-21h]
  _OWORD *v13; // [rsp+78h] [rbp-11h]
  _OWORD pSid[4]; // [rsp+80h] [rbp-9h] BYREF
  int v15; // [rsp+C0h] [rbp+37h]

  cbSid = 68;
  result = 0;
  String = 0;
  Binding = 0;
  v15 = 0;
  v13 = 0;
  memset(pSid, 0, sizeof(pSid));
  SecurityQOS = 0;
  v12 = 0;
  if ( qword_1800147E0 )
  {
    *a1 = (void *)qword_1800147E0;
    return result;
  }
  LastError = RpcStringBindingComposeW(
                (RPC_WSTR)L"0767A036-0D22-48aa-BA69-B619480F38CB",
                (RPC_WSTR)L"ncalrpc",
                0,
                0,
                0,
                &String);
  v4 = LastError;
  if ( LastError )
  {
    v5 = "RpcStringBindingCompose failed [%d]";
    v6 = 402;
  }
  else
  {
    LastError = RpcBindingFromStringBindingW(String, &Binding);
    v4 = LastError;
    if ( LastError )
    {
      v5 = "RpcBindingFromStringBinding failed [%d]";
      v6 = 409;
    }
    else
    {
      LastError = RpcBindingSetOption(Binding, 0xCu, 0xC8u);
      v4 = LastError;
      if ( LastError )
      {
        v5 = "RpcBindingSetOption failed [%d]";
        v6 = 418;
      }
      else if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
      {
        v13 = pSid;
        SecurityQOS.Version = 3;
        *(_QWORD *)&SecurityQOS.Capabilities = 1;
        SecurityQOS.ImpersonationType = 3;
        LastError = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
        v4 = LastError;
        if ( !LastError )
        {
          if ( _InterlockedCompareExchange64(&qword_1800147E0, (signed __int64)Binding, 0) )
            RpcBindingFree(&Binding);
          v4 = 0;
          *a1 = (void *)qword_1800147E0;
          Binding = 0;
          goto LABEL_11;
        }
        v5 = "RpcBindingSetAuthInfoEx failed [%d]";
        v6 = 455;
      }
      else
      {
        LastError = GetLastError();
        v5 = "Failed to create sid [%d]";
        v6 = 431;
        v4 = LastError;
      }
    }
  }
  LODWORD(Options) = LastError;
  AslLogCallPrintf(1, "PcapCreateBindingHandle", v6, v5, Options);
LABEL_11:
  if ( String )
    RpcStringFreeW(&String);
  if ( Binding )
    RpcBindingFree(&Binding);
  return v4;
}

```

## disassembly

```asm
0x180002ca0  mov     [rsp-8+arg_10], rbx
0x180002ca5  mov     [rsp-8+arg_18], rsi
0x180002caa  push    rbp
0x180002cab  lea     rbp, [rsp-57h]
0x180002cb0  sub     rsp, 0E0h
0x180002cb7  mov     rax, cs:__security_cookie
0x180002cbe  xor     rax, rsp
0x180002cc1  mov     [rbp+57h+var_10], rax
0x180002cc5  xorps   xmm0, xmm0
0x180002cc8  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180002ccf  xor     esi, esi
0x180002cd1  xor     eax, eax
0x180002cd3  mov     rbx, rcx
0x180002cd6  mov     [rbp+57h+String], rsi
0x180002cda  mov     rcx, cs:qword_1800147E0
0x180002ce1  mov     [rbp+57h+Binding], rsi
0x180002ce5  mov     [rbp+57h+var_20], eax
0x180002ce8  mov     [rbp+57h+var_68], rax
0x180002cec  movups  [rbp+57h+pSid], xmm0
0x180002cf0  movups  [rbp+57h+var_50], xmm0
0x180002cf4  movups  [rbp+57h+var_40], xmm0
0x180002cf8  movups  [rbp+57h+var_30], xmm0
0x180002cfc  movups  xmmword ptr [rbp+57h+var_88.Version], xmm0
0x180002d00  movups  [rbp+57h+var_78], xmm0
0x180002d04  test    rcx, rcx
0x180002d07  jz      short loc_180002D2D
0x180002d09  mov     [rbx], rcx
0x180002d0c  mov     rcx, [rbp+57h+var_10]
0x180002d10  xor     rcx, rsp; StackCookie
0x180002d13  call    __security_check_cookie
0x180002d18  lea     r11, [rsp+0E0h+var_s0]
0x180002d20  mov     rbx, [r11+20h]
0x180002d24  mov     rsi, [r11+28h]
0x180002d28  mov     rsp, r11
0x180002d2b  pop     rbp
0x180002d2c  retn
0x180002d2d  lea     rax, [rbp+57h+String]
0x180002d31  mov     [rsp+0E0h+arg_8], rdi
0x180002d39  mov     [rsp+0E0h+StringBinding], rax; StringBinding
0x180002d3e  lea     rdx, ProtSeq; "ncalrpc"
0x180002d45  xor     r9d, r9d; Endpoint
0x180002d48  mov     [rsp+0E0h+Options], rsi; Options
0x180002d4d  xor     r8d, r8d; NetworkAddr
0x180002d50  lea     rcx, ObjUuid; "0767A036-0D22-48aa-BA69-B619480F38CB"
0x180002d57  call    cs:__imp_RpcStringBindingComposeW
0x180002d5d  mov     edi, eax
0x180002d5f  test    eax, eax
0x180002d61  jnz     loc_180002E5B
0x180002d67  mov     rcx, [rbp+57h+String]; StringBinding
0x180002d6b  lea     rdx, [rbp+57h+Binding]; Binding
0x180002d6f  call    cs:__imp_RpcBindingFromStringBindingW
0x180002d75  mov     edi, eax
0x180002d77  test    eax, eax
0x180002d79  jnz     loc_180002E7F
0x180002d7f  mov     rcx, [rbp+57h+Binding]; hBinding
0x180002d83  mov     edx, 0Ch; option
0x180002d88  mov     r8d, 0C8h; optionValue
0x180002d8e  call    cs:__imp_RpcBindingSetOption
0x180002d94  mov     edi, eax
0x180002d96  test    eax, eax
0x180002d98  jnz     loc_180002E8E
0x180002d9e  lea     r9, [rbp+57h+cbSid]; cbSid
0x180002da2  xor     edx, edx; DomainSid
0x180002da4  lea     r8, [rbp+57h+pSid]; pSid
0x180002da8  mov     ecx, 16h; WellKnownSidType
0x180002dad  call    cs:__imp_CreateWellKnownSid
0x180002db3  test    eax, eax
0x180002db5  jz      loc_180002E9D
0x180002dbb  mov     rcx, [rbp+57h+Binding]; Binding
0x180002dbf  lea     rax, [rbp+57h+pSid]
0x180002dc3  mov     [rbp+57h+var_68], rax
0x180002dc7  xor     edx, edx; ServerPrincName
0x180002dc9  lea     rax, [rbp+57h+var_88]
0x180002dcd  mov     [rbp+57h+var_88.Version], 3
0x180002dd4  mov     [rsp+0E0h+SecurityQOS], rax; SecurityQOS
0x180002dd9  mov     r9d, 0Ah; AuthnSvc
0x180002ddf  mov     dword ptr [rsp+0E0h+StringBinding], esi; AuthzSvc
0x180002de3  mov     r8d, 6; AuthnLevel
0x180002de9  mov     [rsp+0E0h+Options], rsi; AuthIdentity
0x180002dee  mov     qword ptr [rbp+57h+var_88.Capabilities], 1
0x180002df6  mov     [rbp+57h+var_88.ImpersonationType], 3
0x180002dfd  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180002e03  mov     edi, eax
0x180002e05  test    eax, eax
0x180002e07  jnz     loc_180002EB4
0x180002e0d  mov     rcx, [rbp+57h+Binding]
0x180002e11  xor     eax, eax
0x180002e13  lock cmpxchg cs:qword_1800147E0, rcx
0x180002e1c  jnz     loc_180002EC3
0x180002e22  mov     rax, cs:qword_1800147E0
0x180002e29  mov     edi, esi
0x180002e2b  mov     [rbx], rax
0x180002e2e  mov     [rbp+57h+Binding], rsi
0x180002e32  cmp     [rbp+57h+String], rsi
0x180002e36  jz      short loc_180002E42
0x180002e38  lea     rcx, [rbp+57h+String]; String
0x180002e3c  call    cs:__imp_RpcStringFreeW
0x180002e42  cmp     [rbp+57h+Binding], rsi
0x180002e46  jnz     loc_180002ED2
0x180002e4c  mov     eax, edi
0x180002e4e  mov     rdi, [rsp+0E0h+arg_8]
0x180002e56  jmp     loc_180002D0C
0x180002e5b  lea     r9, aRpcstringbindi; "RpcStringBindingCompose failed [%d]"
0x180002e62  mov     r8d, 192h
0x180002e68  lea     rdx, aPcapcreatebind; "PcapCreateBindingHandle"
0x180002e6f  mov     dword ptr [rsp+0E0h+Options], eax
0x180002e73  mov     ecx, 1
0x180002e78  call    AslLogCallPrintf
0x180002e7d  jmp     short loc_180002E32
0x180002e7f  lea     r9, aRpcbindingfrom; "RpcBindingFromStringBinding failed [%d]"
0x180002e86  mov     r8d, 199h
0x180002e8c  jmp     short loc_180002E68
0x180002e8e  lea     r9, aRpcbindingseto; "RpcBindingSetOption failed [%d]"
0x180002e95  mov     r8d, 1A2h
0x180002e9b  jmp     short loc_180002E68
0x180002e9d  call    cs:__imp_GetLastError
0x180002ea3  lea     r9, aFailedToCreate; "Failed to create sid [%d]"
0x180002eaa  mov     r8d, 1AFh
0x180002eb0  mov     edi, eax
0x180002eb2  jmp     short loc_180002E68
0x180002eb4  lea     r9, aRpcbindingseta; "RpcBindingSetAuthInfoEx failed [%d]"
0x180002ebb  mov     r8d, 1C7h
0x180002ec1  jmp     short loc_180002E68
0x180002ec3  lea     rcx, [rbp+57h+Binding]; Binding
0x180002ec7  call    cs:__imp_RpcBindingFree
0x180002ecd  jmp     loc_180002E22
0x180002ed2  lea     rcx, [rbp+57h+Binding]; Binding
0x180002ed6  call    cs:__imp_RpcBindingFree
0x180002edc  jmp     loc_180002E4C
```
