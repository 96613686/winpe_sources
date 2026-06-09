# CITransaction::GetKtmCookie(_GUID *)

- ea: `0x180028d40`
- end: `0x180028fb8`
- name: `?GetKtmCookie@CITransaction@@AEAAJPEAU_GUID@@@Z`
- size: `632`
- prototype: `int(CITransaction *__hidden this, struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002847c`
- `0x180042ca0`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x180028d40`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028f2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028f2c`
- `RPCRT4!UuidFromStringW` at `0x180028e71`
- `RPCRT4!UuidFromStringW` at `0x180028e71`
- `RPCRT4!UuidToStringW` at `0x180028f55`
- `RPCRT4!UuidToStringW` at `0x180028f55`
- `RPCRT4!RpcStringFreeW` at `0x180028f9f`
- `RPCRT4!RpcStringFreeW` at `0x180028f9f`

## string_xrefs

- `0x180028dbe`: `com\complus\dtc\dtc\msdtcprx\src\dtcprxtx.cpp`
- `0x180028df7`: `com\complus\dtc\dtc\msdtcprx\src\dtcprxtx.cpp`
- `0x180028e92`: `com\complus\dtc\dtc\msdtcprx\src\dtcprxtx.cpp`
- `0x180028ecb`: `com\complus\dtc\dtc\msdtcprx\src\dtcprxtx.cpp`
- `0x180028f6a`: `com\complus\dtc\dtc\msdtcprx\src\dtcprxtx.cpp`
- `0x180028d63`: `CITransaction::GetKtmCookie (com\complus\dtc\dtc\msdtcprx\src\dtcprxtx.cpp@3665): pTmResourceId != NULL`

## pseudocode

```c
__int64 __fastcall CITransaction::GetKtmCookie(CITransaction *this, struct _GUID *a2)
{
  int v4; // r14d
  const wchar_t *v5; // rax
  __int64 v6; // r9
  __int64 v8; // [rsp+28h] [rbp-30h]
  RPC_WSTR StringUuid; // [rsp+68h] [rbp+10h] BYREF
  RPC_WSTR String; // [rsp+70h] [rbp+18h] BYREF

  StringUuid = 0;
  if ( !a2 )
    DtcInternalErrorW(L"CITransaction::GetKtmCookie (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp@3665): pTmResourceId != NULL");
  *a2 = GUID_NULL;
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 29) + 3472LL) + 24LL))(*(_QWORD *)(*((_QWORD *)this + 29) + 3472LL)) )
  {
    TraceStringInline(
      15,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp",
      3671,
      L"CITransaction::GetKtmCookie",
      0,
      L"Its Clustered TM Instance!!\n");
    v4 = (*(__int64 (__fastcall **)(_QWORD, RPC_WSTR *))(**(_QWORD **)(*((_QWORD *)this + 29) + 3472LL) + 64LL))(
           *(_QWORD *)(*((_QWORD *)this + 29) + 3472LL),
           &StringUuid);
    if ( v4 >= 0 )
    {
      TraceStringInline(
        15,
        4,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp",
        3680,
        L"CITransaction::GetKtmCookie",
        0,
        L"Clustered TM resource Id -%s\n",
        StringUuid);
      if ( !UuidFromStringW(StringUuid, a2) )
        goto LABEL_13;
      v4 = -2147467259;
      v5 = L"UuidFromStringW failed!\n";
      v6 = 3685;
    }
    else
    {
      v5 = L"getting resource name failed!\n";
      v6 = 3676;
    }
    LODWORD(v8) = v4;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp",
      v6,
      L"CITransaction::GetKtmCookie",
      v8,
      v5);
  }
  else
  {
    v4 = 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 29) + 3472LL) + 32LL))(*(_QWORD *)(*((_QWORD *)this + 29) + 3472LL)) )
    {
      TraceStringInline(
        15,
        4,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp",
        3691,
        L"CITransaction::GetKtmCookie",
        0,
        L"Its Remote Proxy!!\n");
    }
    else
    {
      TraceStringInline(
        15,
        4,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp",
        3699,
        L"CITransaction::GetKtmCookie",
        0,
        L"Using local DTC instance\n");
      *a2 = (struct _GUID)LOCAL_DTC_TM_RESOURCE_ID;
    }
  }
LABEL_13:
  if ( StringUuid )
  {
    CoTaskMemFree(StringUuid);
    StringUuid = 0;
  }
  if ( (unsigned int)dword_1800D51B8 >= 4 )
  {
    String = 0;
    UuidToStringW(a2, &String);
    if ( String )
    {
      LODWORD(v8) = v4;
      TraceStringInline(
        15,
        4,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp",
        3718,
        L"CITransaction::GetKtmCookie",
        v8,
        L"Get Ktm Cookie TmIdentity is %s",
        String);
      RpcStringFreeW(&String);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180028d40  mov     [rsp+arg_0], rsi
0x180028d45  push    r13
0x180028d47  push    r14
0x180028d49  push    r15
0x180028d4b  sub     rsp, 40h
0x180028d4f  mov     [rsp+58h+StringUuid], 0
0x180028d58  mov     r15, rdx
0x180028d5b  mov     r13, rcx
0x180028d5e  test    rdx, rdx
0x180028d61  jnz     short loc_180028D70
0x180028d63  lea     rcx, aCitransactionG_4; "CITransaction::GetKtmCookie (com\\compl"...
0x180028d6a  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180028d70  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180028d77  movdqu  xmmword ptr [rdx], xmm0
0x180028d7b  mov     rax, [rcx+0E8h]
0x180028d82  mov     rcx, [rax+0D90h]
0x180028d89  mov     rax, [rcx]
0x180028d8c  mov     rax, [rax+18h]
0x180028d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d95  test    eax, eax
0x180028d97  jz      loc_180028EA3
0x180028d9d  mov     edx, 4
0x180028da2  lea     rax, aItsClusteredTm; "Its Clustered TM Instance!!\n"
0x180028da9  mov     [rsp+58h+var_28], rax
0x180028dae  lea     rsi, aCitransactionG_2; "CITransaction::GetKtmCookie"
0x180028db5  mov     [rsp+58h+var_30], 0
0x180028dbe  lea     r8, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180028dc5  mov     r9d, 0E57h
0x180028dcb  mov     [rsp+58h+var_38], rsi
0x180028dd0  lea     ecx, [rdx+0Bh]
0x180028dd3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180028dd8  mov     rax, [r13+0E8h]
0x180028ddf  lea     rdx, [rsp+58h+StringUuid]
0x180028de4  mov     rcx, [rax+0D90h]
0x180028deb  mov     rax, [rcx]
0x180028dee  mov     rax, [rax+40h]
0x180028df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028df7  lea     r8, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180028dfe  mov     r14d, eax
0x180028e01  mov     ecx, 0Fh
0x180028e06  test    eax, eax
0x180028e08  jns     short loc_180028E35
0x180028e0a  lea     rax, aGettingResourc; "getting resource name failed!\n"
0x180028e11  mov     r9d, 0E5Ch
0x180028e17  mov     [rsp+58h+var_28], rax
0x180028e1c  mov     edx, 1
0x180028e21  mov     dword ptr [rsp+58h+var_30], r14d
0x180028e26  mov     [rsp+58h+var_38], rsi
0x180028e2b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180028e30  jmp     loc_180028F22
0x180028e35  mov     rax, [rsp+58h+StringUuid]
0x180028e3a  mov     r9d, 0E60h
0x180028e40  mov     [rsp+58h+var_20], rax
0x180028e45  mov     edx, 4
0x180028e4a  lea     rax, aClusteredTmRes; "Clustered TM resource Id -%s\n"
0x180028e51  mov     [rsp+58h+var_28], rax
0x180028e56  mov     [rsp+58h+var_30], 0
0x180028e5f  mov     [rsp+58h+var_38], rsi
0x180028e64  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180028e69  mov     rcx, [rsp+58h+StringUuid]; StringUuid
0x180028e6e  mov     rdx, r15; Uuid
0x180028e71  call    cs:__imp_UuidFromStringW
0x180028e77  test    eax, eax
0x180028e79  jz      loc_180028F22
0x180028e7f  mov     r14d, 80004005h
0x180028e85  lea     rax, aUuidfromstring_0; "UuidFromStringW failed!\n"
0x180028e8c  mov     r9d, 0E65h
0x180028e92  lea     r8, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180028e99  mov     ecx, 0Fh
0x180028e9e  jmp     loc_180028E17
0x180028ea3  mov     rax, [r13+0E8h]
0x180028eaa  xor     r14d, r14d
0x180028ead  mov     rcx, [rax+0D90h]
0x180028eb4  mov     rax, [rcx]
0x180028eb7  mov     rax, [rax+20h]
0x180028ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ec0  lea     edx, [r14+4]
0x180028ec4  lea     rsi, aCitransactionG_2; "CITransaction::GetKtmCookie"
0x180028ecb  lea     r8, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180028ed2  lea     ecx, [rdx+0Bh]
0x180028ed5  test    eax, eax
0x180028ed7  jz      short loc_180028EF5
0x180028ed9  lea     rax, aItsRemoteProxy; "Its Remote Proxy!!\n"
0x180028ee0  mov     r9d, 0E6Bh
0x180028ee6  mov     [rsp+58h+var_28], rax
0x180028eeb  mov     [rsp+58h+var_30], r14
0x180028ef0  jmp     loc_180028E26
0x180028ef5  lea     rax, aUsingLocalDtcI; "Using local DTC instance\n"
0x180028efc  mov     r9d, 0E73h
0x180028f02  mov     [rsp+58h+var_28], rax
0x180028f07  mov     [rsp+58h+var_30], r14
0x180028f0c  mov     [rsp+58h+var_38], rsi
0x180028f11  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180028f16  movups  xmm0, cs:LOCAL_DTC_TM_RESOURCE_ID
0x180028f1d  movdqu  xmmword ptr [r15], xmm0
0x180028f22  mov     rcx, [rsp+58h+StringUuid]; pv
0x180028f27  test    rcx, rcx
0x180028f2a  jz      short loc_180028F3B
0x180028f2c  call    cs:__imp_CoTaskMemFree
0x180028f32  mov     [rsp+58h+StringUuid], 0
0x180028f3b  cmp     cs:dword_1800D51B8, 4
0x180028f42  jb      short loc_180028FA5
0x180028f44  lea     rdx, [rsp+58h+String]; StringUuid
0x180028f49  mov     [rsp+58h+String], 0
0x180028f52  mov     rcx, r15; Uuid
0x180028f55  call    cs:__imp_UuidToStringW
0x180028f5b  mov     rax, [rsp+58h+String]
0x180028f60  test    rax, rax
0x180028f63  jz      short loc_180028FA5
0x180028f65  mov     [rsp+58h+var_20], rax
0x180028f6a  lea     r8, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180028f71  mov     edx, 4
0x180028f76  lea     rax, aGetKtmCookieTm; "Get Ktm Cookie TmIdentity is %s"
0x180028f7d  mov     [rsp+58h+var_28], rax
0x180028f82  mov     r9d, 0E86h
0x180028f88  mov     dword ptr [rsp+58h+var_30], r14d
0x180028f8d  mov     [rsp+58h+var_38], rsi
0x180028f92  lea     ecx, [rdx+0Bh]
0x180028f95  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180028f9a  lea     rcx, [rsp+58h+String]; String
0x180028f9f  call    cs:__imp_RpcStringFreeW
0x180028fa5  mov     rsi, [rsp+58h+arg_0]
0x180028faa  mov     eax, r14d
0x180028fad  add     rsp, 40h
0x180028fb1  pop     r15
0x180028fb3  pop     r14
0x180028fb5  pop     r13
0x180028fb7  retn
```
