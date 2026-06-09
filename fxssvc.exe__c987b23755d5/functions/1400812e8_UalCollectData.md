# UalCollectData

- ea: `0x1400812e8`
- end: `0x140081500`
- name: `UalCollectData`
- size: `536`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140016a60`

## callees

- `0x140002c43`
- `0x1400808d8`
- `0x140080ba8`
- `0x14008100c`
- `0x140081118`
- `0x1400812e8`
- `0x1400818b0`
- `0x140085010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400813df`
- `KERNEL32!GetLastError` at `0x1400813df`
- `RPCRT4!RpcRevertToSelfEx` at `0x140081384`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400814d9`
- `RPCRT4!RpcRevertToSelfEx` at `0x140081384`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400814d9`
- `RPCRT4!RpcImpersonateClient` at `0x140081341`
- `RPCRT4!RpcImpersonateClient` at `0x140081341`
- `ntdll!RtlIpv4StringToAddressExW` at `0x140081460`
- `ntdll!RtlIpv4StringToAddressExW` at `0x140081460`
- `ntdll!RtlIpv6StringToAddressExW` at `0x140081432`
- `ntdll!RtlIpv6StringToAddressExW` at `0x140081432`
- `Secur32!GetUserNameExW` at `0x1400813d5`
- `Secur32!GetUserNameExW` at `0x1400813d5`

## pseudocode

```c
__int64 __fastcall UalCollectData(void *a1)
{
  void *v3; // rdi
  char v4; // si
  RPC_STATUS v5; // eax
  bool v6; // sf
  unsigned int v7; // r8d
  signed int LastError; // eax
  int IpAddressFromRpc; // ebx
  int v10; // eax
  int v11; // eax
  ULONG nSize[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+34h] [rbp-CCh]
  _BYTE v15[20]; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v16; // [rsp+58h] [rbp-A8h]
  USHORT Port; // [rsp+5Ah] [rbp-A6h] BYREF
  in_addr v18; // [rsp+5Ch] [rbp-A4h] BYREF
  in6_addr Address; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ScopeId[26]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR NameBuffer[260]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR AddressString[72]; // [rsp+2E0h] [rbp+1E0h] BYREF

  if ( !fnUalInstrument )
    return 2147500037LL;
  v3 = 0;
  v4 = 0;
  if ( !a1 )
    goto LABEL_13;
  if ( !NtCurrentTeb()->IsImpersonating )
  {
    v5 = RpcImpersonateClient(a1);
    v6 = v5 < 0;
    if ( v5 > 0 )
      v6 = 1;
    if ( !v6 )
    {
      v3 = a1;
      v4 = 1;
    }
  }
  if ( IsLocalCall(a1) )
  {
    UalPrintTelemetry::WriteDbgTraceInfo("UalCollectData", L"Local client, no UAL collection");
    if ( v4 )
      RpcRevertToSelfEx(v3);
    return 1;
  }
  else
  {
LABEL_13:
    memset_0(v15, 0, 0x29Cu);
    v13 = 688;
    nSize[0] = 260;
    v14 = SumGuid_FAX;
    if ( !GetUserNameExW(NameSamCompatible, NameBuffer, nSize) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      UalPrintTelemetry::WriteDbgTraceError(
        "UalCollectData",
        L"Failed to collect username: hr: 0x%x",
        (unsigned int)LastError);
    }
    IpAddressFromRpc = GetIpAddressFromRpc(a1, AddressString, v7);
    if ( IpAddressFromRpc >= 0 )
    {
      v10 = RtlIpv6StringToAddressExW(AddressString, &Address, ScopeId, &Port) | 0x10000000;
      if ( v10 < 0 )
      {
        v10 = RtlIpv4StringToAddressExW(AddressString, 0, &v18, &Port) | 0x10000000;
        if ( v10 >= 0 )
          v16 = 2;
      }
      else
      {
        v16 = 23;
      }
      IpAddressFromRpc = 0;
      if ( v10 < 0 )
        IpAddressFromRpc = v10;
      if ( IpAddressFromRpc >= 0 )
        goto LABEL_26;
    }
    UalPrintTelemetry::WriteDbgTraceInfo(
      "UalCollectData",
      L"Failed to collect IP address: hr: 0x%x",
      (unsigned int)IpAddressFromRpc);
    v16 = 2;
    v18 = 0;
    if ( NameBuffer[0] )
    {
LABEL_26:
      v11 = ((__int64 (__fastcall *)(int *))fnUalInstrument)(&v13);
      IpAddressFromRpc = v11;
      if ( v11 < 0 )
        UalPrintTelemetry::WriteDbgTraceError("UalCollectData", L"Failed to log UAL data: hr: 0x%x", (unsigned int)v11);
    }
    if ( v4 )
      RpcRevertToSelfEx(v3);
    return (unsigned int)IpAddressFromRpc;
  }
}

```

## disassembly

```asm
0x1400812e8  push    rbp
0x1400812ea  push    rbx
0x1400812eb  push    rsi
0x1400812ec  push    rdi
0x1400812ed  push    r12
0x1400812ef  push    r14
0x1400812f1  lea     rbp, [rsp-288h]
0x1400812f9  sub     rsp, 388h
0x140081300  mov     rax, cs:__security_cookie
0x140081307  xor     rax, rsp
0x14008130a  mov     [rbp+2B0h+var_40], rax
0x140081311  xor     r14d, r14d
0x140081314  mov     rbx, rcx
0x140081317  cmp     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, r14; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x14008131e  jnz     short loc_14008132A
0x140081320  mov     eax, 80004005h
0x140081325  jmp     loc_1400814E1
0x14008132a  mov     rdi, r14
0x14008132d  mov     sil, r14b
0x140081330  test    rbx, rbx
0x140081333  jz      short loc_140081394
0x140081335  mov     eax, gs:179Ch
0x14008133d  test    eax, eax
0x14008133f  jnz     short loc_14008135D
0x140081341  call    cs:__imp_RpcImpersonateClient
0x140081347  test    eax, eax
0x140081349  jle     short loc_140081355
0x14008134b  movzx   eax, ax
0x14008134e  or      eax, 80070000h
0x140081353  test    eax, eax
0x140081355  js      short loc_14008135D
0x140081357  mov     rdi, rbx
0x14008135a  mov     sil, 1
0x14008135d  mov     rcx, rbx; void *
0x140081360  call    ?IsLocalCall@@YA_NPEAX@Z; IsLocalCall(void *)
0x140081365  test    al, al
0x140081367  jz      short loc_140081394
0x140081369  lea     rdx, aLocalClientNoU; "Local client, no UAL collection"
0x140081370  lea     rcx, aUalcollectdata; "UalCollectData"
0x140081377  call    ?WriteDbgTraceInfo@UalPrintTelemetry@@SAXPEADPEAGZZ; UalPrintTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14008137c  test    sil, sil
0x14008137f  jz      short loc_14008138A
0x140081381  mov     rcx, rdi; BindingHandle
0x140081384  call    cs:__imp_RpcRevertToSelfEx
0x14008138a  mov     eax, 1
0x14008138f  jmp     loc_1400814E1
0x140081394  xor     edx, edx; Val
0x140081396  lea     rcx, [rsp+3B0h+var_36C]; void *
0x14008139b  mov     r8d, 29Ch; Size
0x1400813a1  call    memset_0
0x1400813a6  movups  xmm0, cs:SumGuid_FAX
0x1400813ad  mov     r12d, 2
0x1400813b3  mov     [rsp+3B0h+var_380], 2B0h
0x1400813bb  lea     r8, [rsp+3B0h+nSize]; nSize
0x1400813c0  mov     [rsp+3B0h+nSize], 104h
0x1400813c8  lea     rdx, [rbp+2B0h+NameBuffer]; lpNameBuffer
0x1400813cc  mov     ecx, r12d; NameFormat
0x1400813cf  movdqu  [rsp+3B0h+var_37C], xmm0
0x1400813d5  call    cs:__imp_GetUserNameExW
0x1400813db  test    al, al
0x1400813dd  jnz     short loc_140081407
0x1400813df  call    cs:__imp_GetLastError
0x1400813e5  test    eax, eax
0x1400813e7  jle     short loc_1400813F1
0x1400813e9  movzx   eax, ax
0x1400813ec  or      eax, 80070000h
0x1400813f1  mov     r8d, eax
0x1400813f4  lea     rdx, aFailedToCollec_0; "Failed to collect username: hr: 0x%x"
0x1400813fb  lea     rcx, aUalcollectdata; "UalCollectData"
0x140081402  call    ?WriteDbgTraceError@UalPrintTelemetry@@SAXPEADPEAGZZ; UalPrintTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140081407  lea     rdx, [rbp+2B0h+AddressString]; unsigned __int16 *
0x14008140e  mov     rcx, rbx; void *
0x140081411  call    ?GetIpAddressFromRpc@@YAJPEAXPEAGK@Z; GetIpAddressFromRpc(void *,ushort *,ulong)
0x140081416  mov     ebx, eax
0x140081418  test    eax, eax
0x14008141a  js      short loc_14008147C
0x14008141c  lea     r9, [rsp+3B0h+Port]; Port
0x140081421  lea     r8, [rsp+3B0h+ScopeId]; ScopeId
0x140081426  lea     rdx, [rsp+3B0h+Address]; Address
0x14008142b  lea     rcx, [rbp+2B0h+AddressString]; AddressString
0x140081432  call    cs:__imp_RtlIpv6StringToAddressExW
0x140081438  mov     ebx, 10000000h
0x14008143d  or      eax, ebx
0x14008143f  jl      short loc_14008144D
0x140081441  mov     ecx, 17h
0x140081446  mov     [rsp+3B0h+var_358], cx
0x14008144b  jmp     short loc_140081470
0x14008144d  lea     r9, [rsp+3B0h+Port]; Port
0x140081452  xor     edx, edx; Strict
0x140081454  lea     r8, [rsp+3B0h+var_354]; Address
0x140081459  lea     rcx, [rbp+2B0h+AddressString]; AddressString
0x140081460  call    cs:__imp_RtlIpv4StringToAddressExW
0x140081466  or      eax, ebx
0x140081468  jl      short loc_140081470
0x14008146a  mov     [rsp+3B0h+var_358], r12w
0x140081470  test    eax, eax
0x140081472  mov     ebx, r14d
0x140081475  cmovs   ebx, eax
0x140081478  test    ebx, ebx
0x14008147a  jns     short loc_1400814A4
0x14008147c  mov     r8d, ebx
0x14008147f  lea     rdx, aFailedToCollec; "Failed to collect IP address: hr: 0x%x"
0x140081486  lea     rcx, aUalcollectdata; "UalCollectData"
0x14008148d  call    ?WriteDbgTraceInfo@UalPrintTelemetry@@SAXPEADPEAGZZ; UalPrintTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140081492  mov     [rsp+3B0h+var_358], r12w
0x140081498  mov     dword ptr [rsp+3B0h+var_354.S_un], r14d
0x14008149d  cmp     [rbp+2B0h+NameBuffer], r14w
0x1400814a2  jz      short loc_1400814D1
0x1400814a4  mov     rax, cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x1400814ab  lea     rcx, [rsp+3B0h+var_380]
0x1400814b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400814b5  mov     ebx, eax
0x1400814b7  test    eax, eax
0x1400814b9  jns     short loc_1400814D1
0x1400814bb  mov     r8d, eax
0x1400814be  lea     rdx, aFailedToLogUal; "Failed to log UAL data: hr: 0x%x"
0x1400814c5  lea     rcx, aUalcollectdata; "UalCollectData"
0x1400814cc  call    ?WriteDbgTraceError@UalPrintTelemetry@@SAXPEADPEAGZZ; UalPrintTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400814d1  test    sil, sil
0x1400814d4  jz      short loc_1400814DF
0x1400814d6  mov     rcx, rdi; BindingHandle
0x1400814d9  call    cs:__imp_RpcRevertToSelfEx
0x1400814df  mov     eax, ebx
0x1400814e1  mov     rcx, [rbp+2B0h+var_40]
0x1400814e8  xor     rcx, rsp; StackCookie
0x1400814eb  call    __security_check_cookie
0x1400814f0  add     rsp, 388h
0x1400814f7  pop     r14
0x1400814f9  pop     r12
0x1400814fb  pop     rdi
0x1400814fc  pop     rsi
0x1400814fd  pop     rbx
0x1400814fe  pop     rbp
0x1400814ff  retn
```
