# GetTmInstanceForHost

- ea: `0x180021f00`
- end: `0x1800221f3`
- name: `GetTmInstanceForHost`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023548`

## callees

- `0x180003cf0`
- `0x180006214`
- `0x18000d5f4`
- `0x18000f8d0`
- `0x180021f00`
- `0x180053720`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221c4`
- `RPCRT4!UuidFromStringW` at `0x1800220b9`
- `RPCRT4!UuidFromStringW` at `0x1800220b9`
- `MTXCLU!MtxCluCreateClusterProxyTmInstance` at `0x18002210d`
- `MTXCLU!MtxCluCreateClusterProxyTmInstance` at `0x18002210d`
- `MTXCLU!MtxCluGetDefaultClusterResourceNonAdmin` at `0x180021fee`
- `MTXCLU!MtxCluGetDefaultClusterResourceNonAdmin` at `0x180021fee`

## string_xrefs

- `0x180021fa1`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x180021f53`: `GetTmInstanceForHost (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@901): NULL != i_pwszLookupHost`
- `0x180021f65`: `GetTmInstanceForHost (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@902): NULL != o_ppTmInstance`
- `0x180021f77`: `GetTmInstanceForHost (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@903): NULL != o_ppLocalTmInstance`
- `0x180022119`: `Unable to create cluster proxy instance`
- `0x180022150`: `Unable to create remote TM instance`
- `0x18002217b`: `Unable to create local TM instance`

## pseudocode

```c
__int64 __fastcall GetTmInstanceForHost(const unsigned __int16 *a1, _QWORD *a2, struct ITmInstance **a3)
{
  unsigned __int16 *v6; // r15
  int DefaultClusterResourceNonAdmin; // ebx
  RPC_STATUS v8; // eax
  __int64 v10; // [rsp+28h] [rbp-51h]
  bool v11; // [rsp+50h] [rbp-29h] BYREF
  __int64 v12; // [rsp+58h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-19h] BYREF
  RPC_WSTR StringUuid; // [rsp+68h] [rbp-11h] BYREF
  UUID v15; // [rsp+70h] [rbp-9h] BYREF
  UUID Uuid; // [rsp+80h] [rbp+7h] BYREF

  v12 = 0;
  StringUuid = 0;
  pv = 0;
  Uuid = GUID_NULL;
  if ( !a1 )
    DtcInternalErrorW(L"GetTmInstanceForHost (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@901): NULL != i_pwszLookupHost");
  if ( !a2 )
    DtcInternalErrorW(L"GetTmInstanceForHost (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@902): NULL != o_ppTmInstance");
  if ( !a3 )
    DtcInternalErrorW(L"GetTmInstanceForHost (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@903): NULL != o_ppLocalTmInstance");
  *a2 = 0;
  v6 = (unsigned __int16 *)a1;
  *a3 = 0;
  v11 = 0;
  MtxCluIsClusterPresentNonAdmin(a1, &v11);
  if ( !v11 )
    goto LABEL_30;
  TraceStringInline(
    15,
    4,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
    929,
    L"GetTmInstanceForHost",
    0,
    L"Specified host name %s is in a cluster, using cluster default DTC",
    a1);
  DefaultClusterResourceNonAdmin = MtxCluGetDefaultClusterResourceNonAdmin(a1, &StringUuid, &pv);
  if ( DefaultClusterResourceNonAdmin < 0 )
  {
    LODWORD(v10) = DefaultClusterResourceNonAdmin;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
      936,
      L"GetTmInstanceForHost",
      v10,
      L"MtxCluGetDefaultClusterResourceNonAdmin failed for host name %s",
      a1);
    goto LABEL_25;
  }
  if ( pv && *(_WORD *)pv )
  {
    v6 = (unsigned __int16 *)pv;
    TraceStringInline(
      15,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
      946,
      L"GetTmInstanceForHost",
      0,
      L"Programmatic remote proxy to a cluster - using virtual server name %s instead of provided host name %s",
      pv,
      a1);
  }
  v11 = 0;
  MtxCluIsClusterPresentNonAdmin(0, &v11);
  if ( !v11 || !pv )
    goto LABEL_30;
  v8 = UuidFromStringW(StringUuid, &Uuid);
  if ( v8 )
  {
    DefaultClusterResourceNonAdmin = -2147467259;
    LODWORD(v10) = v8;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
      972,
      L"GetTmInstanceForHost",
      v10,
      L"UuidFromStringW failed");
    goto LABEL_25;
  }
  v15 = Uuid;
  DefaultClusterResourceNonAdmin = MtxCluCreateClusterProxyTmInstance(pv, &v15, &v12);
  if ( DefaultClusterResourceNonAdmin >= 0 )
  {
LABEL_30:
    if ( v12 || (DefaultClusterResourceNonAdmin = CreateLegacyTmInstance(v6), DefaultClusterResourceNonAdmin >= 0) )
    {
      DefaultClusterResourceNonAdmin = CreateLocalTmInstance(0, a3);
      if ( DefaultClusterResourceNonAdmin >= 0 )
      {
        *a2 = v12;
        v12 = 0;
      }
      else
      {
        LODWORD(v10) = DefaultClusterResourceNonAdmin;
        TraceStringInline(
          15,
          1,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
          1014,
          L"GetTmInstanceForHost",
          v10,
          L"Unable to create local TM instance");
      }
    }
    else
    {
      LODWORD(v10) = DefaultClusterResourceNonAdmin;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
        1001,
        L"GetTmInstanceForHost",
        v10,
        L"Unable to create remote TM instance");
    }
    goto LABEL_25;
  }
  LODWORD(v10) = DefaultClusterResourceNonAdmin;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
    981,
    L"GetTmInstanceForHost",
    v10,
    L"Unable to create cluster proxy instance");
LABEL_25:
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  CoTaskMemFree(StringUuid);
  CoTaskMemFree(pv);
  return (unsigned int)DefaultClusterResourceNonAdmin;
}

```

## disassembly

```asm
0x180021f00  mov     [rsp-8+arg_18], rbx
0x180021f05  push    rbp
0x180021f06  push    rsi
0x180021f07  push    rdi
0x180021f08  push    r12
0x180021f0a  push    r13
0x180021f0c  push    r14
0x180021f0e  push    r15
0x180021f10  lea     rbp, [rsp-27h]
0x180021f15  sub     rsp, 0A0h
0x180021f1c  mov     rax, cs:__security_cookie
0x180021f23  xor     rax, rsp
0x180021f26  mov     [rbp+57h+var_40], rax
0x180021f2a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180021f31  xor     r12d, r12d
0x180021f34  mov     r14, r8
0x180021f37  mov     [rbp+57h+var_78], r12
0x180021f3b  mov     rsi, rdx
0x180021f3e  mov     [rbp+57h+StringUuid], r12
0x180021f42  mov     rdi, rcx
0x180021f45  mov     [rbp+57h+pv], r12
0x180021f49  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180021f4e  test    rcx, rcx
0x180021f51  jnz     short loc_180021F60
0x180021f53  lea     rcx, aGettminstancef_14; "GetTmInstanceForHost (com\\complus\\dtc"...
0x180021f5a  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180021f60  test    rsi, rsi
0x180021f63  jnz     short loc_180021F72
0x180021f65  lea     rcx, aGettminstancef_15; "GetTmInstanceForHost (com\\complus\\dtc"...
0x180021f6c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180021f72  test    r14, r14
0x180021f75  jnz     short loc_180021F84
0x180021f77  lea     rcx, aGettminstancef_2; "GetTmInstanceForHost (com\\complus\\dtc"...
0x180021f7e  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180021f84  mov     [rdx], r12
0x180021f87  mov     r15, rdi
0x180021f8a  lea     rdx, [rbp+57h+var_80]; bool *
0x180021f8e  mov     [r8], r12
0x180021f91  mov     [rbp+57h+var_80], r12b
0x180021f95  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x180021f9a  lea     rcx, aGettminstancef_12; "GetTmInstanceForHost"
0x180021fa1  lea     r13, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180021fa8  cmp     [rbp+57h+var_80], r12b
0x180021fac  jz      loc_180022131
0x180021fb2  mov     [rsp+0D0h+var_98], rdi
0x180021fb7  lea     rax, aSpecifiedHostN; "Specified host name %s is in a cluster,"...
0x180021fbe  mov     [rsp+0D0h+var_A0], rax
0x180021fc3  mov     edx, 4
0x180021fc8  mov     [rsp+0D0h+var_A8], r12
0x180021fcd  mov     r9d, 3A1h
0x180021fd3  mov     [rsp+0D0h+var_B0], rcx
0x180021fd8  mov     r8, r13
0x180021fdb  lea     ecx, [rdx+0Bh]
0x180021fde  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180021fe3  lea     r8, [rbp+57h+pv]
0x180021fe7  mov     rcx, rdi
0x180021fea  lea     rdx, [rbp+57h+StringUuid]
0x180021fee  call    cs:__imp_MtxCluGetDefaultClusterResourceNonAdmin
0x180021ff4  mov     ebx, eax
0x180021ff6  test    eax, eax
0x180021ff8  jns     short loc_180022036
0x180021ffa  mov     [rsp+0D0h+var_98], rdi
0x180021fff  lea     rax, aMtxclugetdefau_1; "MtxCluGetDefaultClusterResourceNonAdmin"...
0x180022006  mov     [rsp+0D0h+var_A0], rax
0x18002200b  lea     rdi, aGettminstancef_12; "GetTmInstanceForHost"
0x180022012  mov     edx, 1
0x180022017  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x18002201b  mov     r9d, 3A8h
0x180022021  mov     [rsp+0D0h+var_B0], rdi
0x180022026  mov     r8, r13
0x180022029  lea     ecx, [rdx+0Eh]
0x18002202c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022031  jmp     loc_1800221A1
0x180022036  mov     rcx, [rbp+57h+pv]
0x18002203a  test    rcx, rcx
0x18002203d  jz      short loc_180022087
0x18002203f  cmp     r12w, [rcx]
0x180022043  jz      short loc_180022087
0x180022045  mov     [rsp+0D0h+var_90], rdi
0x18002204a  lea     rax, aProgrammaticRe; "Programmatic remote proxy to a cluster "...
0x180022051  mov     [rsp+0D0h+var_98], rcx
0x180022056  lea     rdi, aGettminstancef_12; "GetTmInstanceForHost"
0x18002205d  mov     [rsp+0D0h+var_A0], rax
0x180022062  mov     edx, 4
0x180022067  mov     r15, rcx
0x18002206a  mov     [rsp+0D0h+var_A8], r12
0x18002206f  mov     r9d, 3B2h
0x180022075  mov     [rsp+0D0h+var_B0], rdi
0x18002207a  mov     r8, r13
0x18002207d  lea     ecx, [rdx+0Bh]
0x180022080  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022085  jmp     short loc_18002208E
0x180022087  lea     rdi, aGettminstancef_12; "GetTmInstanceForHost"
0x18002208e  lea     rdx, [rbp+57h+var_80]; bool *
0x180022092  mov     [rbp+57h+var_80], r12b
0x180022096  xor     ecx, ecx; unsigned __int16 *
0x180022098  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x18002209d  cmp     [rbp+57h+var_80], r12b
0x1800220a1  jz      loc_180022138
0x1800220a7  cmp     [rbp+57h+pv], r12
0x1800220ab  jz      loc_180022138
0x1800220b1  mov     rcx, [rbp+57h+StringUuid]; StringUuid
0x1800220b5  lea     rdx, [rbp+57h+Uuid]; Uuid
0x1800220b9  call    cs:__imp_UuidFromStringW
0x1800220bf  test    eax, eax
0x1800220c1  jz      short loc_1800220F8
0x1800220c3  lea     rcx, aUuidfromstring_1; "UuidFromStringW failed"
0x1800220ca  mov     ebx, 80004005h
0x1800220cf  mov     [rsp+0D0h+var_A0], rcx
0x1800220d4  mov     r9d, 3CCh
0x1800220da  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800220de  mov     edx, 1
0x1800220e3  mov     [rsp+0D0h+var_B0], rdi
0x1800220e8  mov     r8, r13
0x1800220eb  lea     ecx, [rdx+0Eh]
0x1800220ee  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800220f3  jmp     loc_1800221A1
0x1800220f8  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x1800220fc  lea     r8, [rbp+57h+var_78]
0x180022100  mov     rcx, [rbp+57h+pv]
0x180022104  lea     rdx, [rbp+57h+var_60]
0x180022108  movdqa  [rbp+57h+var_60], xmm0
0x18002210d  call    cs:__imp_MtxCluCreateClusterProxyTmInstance
0x180022113  mov     ebx, eax
0x180022115  test    eax, eax
0x180022117  jns     short loc_180022138
0x180022119  lea     rax, aUnableToCreate_0; "Unable to create cluster proxy instance"
0x180022120  mov     r9d, 3D5h
0x180022126  mov     [rsp+0D0h+var_A0], rax
0x18002212b  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x18002212f  jmp     short loc_1800220DE
0x180022131  lea     rdi, aGettminstancef_12; "GetTmInstanceForHost"
0x180022138  cmp     [rbp+57h+var_78], r12
0x18002213c  jnz     short loc_18002216B
0x18002213e  lea     rdx, [rbp+57h+var_78]
0x180022142  mov     rcx, r15; unsigned __int16 *
0x180022145  call    CreateLegacyTmInstance
0x18002214a  mov     ebx, eax
0x18002214c  test    eax, eax
0x18002214e  jns     short loc_18002216B
0x180022150  lea     rax, aUnableToCreate_1; "Unable to create remote TM instance"
0x180022157  mov     r9d, 3E9h
0x18002215d  mov     [rsp+0D0h+var_A0], rax
0x180022162  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x180022166  jmp     loc_1800220DE
0x18002216b  mov     rdx, r14; struct ITmInstance **
0x18002216e  xor     ecx, ecx; unsigned __int16 *
0x180022170  call    ?CreateLocalTmInstance@@YAJPEBGPEAPEAUITmInstance@@@Z; CreateLocalTmInstance(ushort const *,ITmInstance * *)
0x180022175  mov     ebx, eax
0x180022177  test    eax, eax
0x180022179  jns     short loc_180022196
0x18002217b  lea     rax, aUnableToCreate; "Unable to create local TM instance"
0x180022182  mov     r9d, 3F6h
0x180022188  mov     [rsp+0D0h+var_A0], rax
0x18002218d  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x180022191  jmp     loc_1800220DE
0x180022196  mov     rax, [rbp+57h+var_78]
0x18002219a  mov     [rsi], rax
0x18002219d  mov     [rbp+57h+var_78], r12
0x1800221a1  mov     rcx, [rbp+57h+var_78]
0x1800221a5  test    rcx, rcx
0x1800221a8  jz      short loc_1800221B6
0x1800221aa  mov     rax, [rcx]
0x1800221ad  mov     rax, [rax+10h]
0x1800221b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221b6  mov     rcx, [rbp+57h+StringUuid]; pv
0x1800221ba  call    cs:__imp_CoTaskMemFree
0x1800221c0  mov     rcx, [rbp+57h+pv]; pv
0x1800221c4  call    cs:__imp_CoTaskMemFree
0x1800221ca  mov     eax, ebx
0x1800221cc  mov     rcx, [rbp+57h+var_40]
0x1800221d0  xor     rcx, rsp; StackCookie
0x1800221d3  call    __security_check_cookie
0x1800221d8  mov     rbx, [rsp+0D0h+arg_18]
0x1800221e0  add     rsp, 0A0h
0x1800221e7  pop     r15
0x1800221e9  pop     r14
0x1800221eb  pop     r13
0x1800221ed  pop     r12
0x1800221ef  pop     rdi
0x1800221f0  pop     rsi
0x1800221f1  pop     rbp
0x1800221f2  retn
```
