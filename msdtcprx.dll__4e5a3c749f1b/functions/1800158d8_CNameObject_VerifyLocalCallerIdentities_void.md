# CNameObject::VerifyLocalCallerIdentities(void)

- ea: `0x1800158d8`
- end: `0x180015f08`
- name: `?VerifyLocalCallerIdentities@CNameObject@@AEAAJXZ`
- size: `1584`
- prototype: `__int64 __fastcall(CNameObject *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180050100`

## callees

- `0x180003cf0`
- `0x18000b210`
- `0x18000f8d0`
- `0x1800158d8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ea8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015eda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ea8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015eda`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015914`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015914`
- `MTXCLU!MtxCluCreateClusterTmInstance` at `0x180015ca6`
- `MTXCLU!MtxCluCreateClusterTmInstance` at `0x180015ca6`
- `MTXCLU!MtxCluEnumerateDtcResources` at `0x180015c39`
- `MTXCLU!MtxCluEnumerateDtcResources` at `0x180015c39`

## string_xrefs

- `0x180015944`: `com\complus\dtc\dtc\adme\namesvc.cpp`
- `0x18001596a`: `com\complus\dtc\dtc\adme\namesvc.cpp`
- `0x180015a07`: `Error getting TM instance service name`
- `0x180015a2b`: `It is service '%s'`
- `0x180015a68`: `Error getting PID for service '%s'`
- `0x180015acf`: `Not Verified! (Service pid %d)`
- `0x180015d1b`: `  Failed to get service name for '%s'`
- `0x180015d4f`: `Service '%s' does not exist - it is not online on this node.`
- `0x180015d7e`: `Error getting service PID for '%s'`

## pseudocode

```c
__int64 __fastcall CNameObject::VerifyLocalCallerIdentities(CNameObject *this)
{
  RPC_STATUS v2; // eax
  signed int ServiceProcessId; // edi
  const wchar_t *v4; // rax
  __int64 v5; // r9
  CNameObject *v6; // rcx
  __int64 v7; // r9
  const wchar_t *v8; // rax
  CNameObject *v9; // rcx
  CNameObject *v10; // rcx
  unsigned int i; // r13d
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  const wchar_t *v15; // rcx
  CNameObject *v16; // rcx
  int v17; // r12d
  LPVOID *v18; // rax
  unsigned int j; // esi
  __int64 v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+38h] [rbp-40h]
  const WCHAR *v24; // [rsp+38h] [rbp-40h]
  __int64 v25; // [rsp+40h] [rbp-38h]
  LPVOID pv; // [rsp+50h] [rbp-28h] BYREF
  LPVOID v27; // [rsp+58h] [rbp-20h] BYREF
  __int64 v28; // [rsp+60h] [rbp-18h] BYREF
  __int64 v29; // [rsp+68h] [rbp-10h]
  signed int v30; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v31; // [rsp+C8h] [rbp+50h] BYREF
  unsigned int Pid; // [rsp+D0h] [rbp+58h] BYREF
  unsigned int v33; // [rsp+D8h] [rbp+60h] BYREF

  *(_QWORD *)((char *)this + 100) = 0;
  Pid = 0;
  v31 = 0;
  pv = 0;
  v27 = 0;
  v33 = 0;
  v28 = 0;
  v2 = I_RpcBindingInqLocalClientPID(0, &Pid);
  ServiceProcessId = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      ServiceProcessId = (unsigned __int16)v2 | 0x80070000;
    v4 = L"Error asking for local PID";
    v5 = 2064;
LABEL_5:
    LODWORD(v21) = ServiceProcessId;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
      v5,
      L"CNameObject::VerifyLocalCallerIdentities",
      v21,
      v4);
    goto LABEL_49;
  }
  TraceStringInline(
    1,
    4,
    L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
    2071,
    L"CNameObject::VerifyLocalCallerIdentities",
    0,
    L"Trying to verify PID %d as MSDTC",
    Pid);
  if ( *((_QWORD *)this + 26) )
  {
    TraceStringInline(
      1,
      4,
      L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
      2079,
      L"CNameObject::VerifyLocalCallerIdentities",
      0,
      L"We have a TM instance for that, need to use it.");
    ServiceProcessId = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 26) + 56LL))(
                         *((_QWORD *)this + 26),
                         &pv);
    if ( ServiceProcessId < 0 )
    {
      v4 = L"Error getting TM instance service name";
      v5 = 2088;
      goto LABEL_5;
    }
    TraceStringInline(
      1,
      4,
      L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
      2092,
      L"CNameObject::VerifyLocalCallerIdentities",
      0,
      L"It is service '%s'",
      pv);
    ServiceProcessId = CNameObject::GetServiceProcessId(v6, (const unsigned __int16 *)pv, &v31);
    if ( ServiceProcessId < 0 )
    {
      v7 = 2100;
      v24 = (const WCHAR *)pv;
      v8 = L"Error getting PID for service '%s'";
      goto LABEL_11;
    }
    if ( v31 == Pid )
    {
      TraceStringInline(
        1,
        4,
        L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
        2106,
        L"CNameObject::VerifyLocalCallerIdentities",
        0,
        L"Verified!");
      *((_DWORD *)this + 25) = 1;
    }
    else
    {
      LODWORD(v23) = v31;
      TraceStringInline(
        1,
        4,
        L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
        2114,
        L"CNameObject::VerifyLocalCallerIdentities",
        0,
        L"Not Verified! (Service pid %d)",
        v23);
    }
    ServiceProcessId = 0;
    if ( !*((_DWORD *)this + 25) )
      goto LABEL_16;
    goto LABEL_49;
  }
  TraceStringInline(
    1,
    4,
    L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
    2137,
    L"CNameObject::VerifyLocalCallerIdentities",
    0,
    L"Checking local MSDTC...");
  ServiceProcessId = CNameObject::GetServiceProcessId(v10, L"MSDTC", &v31);
  if ( ServiceProcessId < 0 )
  {
    v7 = 2145;
    v24 = L"MSDTC";
    v8 = L"Error getting PID for %s";
LABEL_11:
    LODWORD(v22) = ServiceProcessId;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
      v7,
      L"CNameObject::VerifyLocalCallerIdentities",
      v22,
      v8,
      v24);
    goto LABEL_49;
  }
  if ( v31 == Pid )
  {
    LODWORD(v22) = ServiceProcessId;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
      2156,
      L"CNameObject::VerifyLocalCallerIdentities",
      v22,
      L"Verified as local MSDTC",
      L"MSDTC");
LABEL_22:
    *((_DWORD *)this + 25) = 1;
LABEL_48:
    ServiceProcessId = 0;
    goto LABEL_49;
  }
  LOBYTE(v30) = 0;
  MtxCluIsClusterPresentNonAdmin(0, (bool *)&v30);
  if ( !(_BYTE)v30 )
    goto LABEL_16;
  TraceStringInline(
    1,
    4,
    L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
    2170,
    L"CNameObject::VerifyLocalCallerIdentities",
    0,
    L"Cluster present, checking resources...");
  ServiceProcessId = MtxCluEnumerateDtcResources(0, &v33, &v27);
  if ( ServiceProcessId < 0 )
  {
    v4 = L"Failed to enumerate resources";
    v5 = 2175;
    goto LABEL_5;
  }
  ServiceProcessId = 0;
  for ( i = 0; i < v33; ++i )
  {
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v28 = 0;
    }
    CoTaskMemFree(pv);
    pv = 0;
    v29 = i;
    v12 = MtxCluCreateClusterTmInstance(0, *((_QWORD *)v27 + i), &v28);
    v30 = v12;
    if ( v12 < 0 )
    {
      v13 = 2210;
      v14 = *((_QWORD *)v27 + i);
      v15 = L"  Failed to get TM instance for '%s'";
LABEL_32:
      LODWORD(v21) = v12;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
        v13,
        L"CNameObject::VerifyLocalCallerIdentities",
        v21,
        v15,
        v14);
      ServiceProcessId = v30;
      continue;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v28 + 56LL))(v28, &pv);
    v30 = v12;
    if ( v12 < 0 )
    {
      v13 = 2221;
      v14 = *((_QWORD *)v27 + i);
      v15 = L"  Failed to get service name for '%s'";
      goto LABEL_32;
    }
    v17 = CNameObject::GetServiceProcessId(v16, (const unsigned __int16 *)pv, &v31);
    if ( v17 >= 0 )
    {
      if ( v31 == Pid )
      {
        TraceStringInline(
          1,
          4,
          L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
          2252,
          L"CNameObject::VerifyLocalCallerIdentities",
          0,
          L"Resource '%s' verified!",
          *((_QWORD *)v27 + v29));
        goto LABEL_22;
      }
      LODWORD(v25) = v31;
      TraceStringInline(
        1,
        4,
        L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
        2264,
        L"CNameObject::VerifyLocalCallerIdentities",
        0,
        L"  Resource '%s' found lacking. (pid %d)",
        *((_QWORD *)v27 + i),
        v25);
    }
    else
    {
      if ( v17 == -2147023836 )
      {
        TraceStringInline(
          1,
          3,
          L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
          2233,
          L"CNameObject::VerifyLocalCallerIdentities",
          0,
          L"Service '%s' does not exist - it is not online on this node.",
          pv);
        v17 = 0;
      }
      else
      {
        LODWORD(v21) = v17;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
          2241,
          L"CNameObject::VerifyLocalCallerIdentities",
          v21,
          L"Error getting service PID for '%s'",
          pv);
      }
      ServiceProcessId = v17;
    }
  }
  TraceStringInline(
    1,
    4,
    L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
    2268,
    L"CNameObject::VerifyLocalCallerIdentities",
    0,
    L"Done with resources");
  if ( ServiceProcessId < 0 )
  {
    v4 = L"Error somewhere in loop";
    v5 = 2272;
    goto LABEL_5;
  }
LABEL_16:
  TraceStringInline(
    1,
    4,
    L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
    2282,
    L"CNameObject::VerifyLocalCallerIdentities",
    0,
    L"Checking local KtmRm...");
  ServiceProcessId = CNameObject::GetServiceProcessId(v9, L"KtmRm", &v31);
  if ( ServiceProcessId < 0 )
  {
    v24 = L"KtmRm";
    v8 = L"Error getting PID for %s";
    v7 = 2290;
    goto LABEL_11;
  }
  if ( v31 == Pid )
  {
    LODWORD(v22) = ServiceProcessId;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
      2300,
      L"CNameObject::VerifyLocalCallerIdentities",
      v22,
      L"Verified as local KtmRm");
    *((_DWORD *)this + 26) = 1;
    goto LABEL_48;
  }
LABEL_49:
  CoTaskMemFree(pv);
  v18 = (LPVOID *)v27;
  if ( v27 )
  {
    for ( j = 0; j < v33; ++j )
    {
      CoTaskMemFree(v18[j]);
      v18 = (LPVOID *)v27;
    }
    CoTaskMemFree(v18);
  }
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  return (unsigned int)ServiceProcessId;
}

```

## disassembly

```asm
0x1800158d8  push    rbp
0x1800158da  push    rbx
0x1800158db  push    rsi
0x1800158dc  push    rdi
0x1800158dd  push    r12
0x1800158df  push    r13
0x1800158e1  push    r14
0x1800158e3  push    r15
0x1800158e5  mov     rbp, rsp
0x1800158e8  sub     rsp, 78h
0x1800158ec  xor     r12d, r12d
0x1800158ef  lea     rdx, [rbp+Pid]; Pid
0x1800158f3  mov     [rcx+64h], r12
0x1800158f7  mov     r15, rcx
0x1800158fa  xor     ecx, ecx; Binding
0x1800158fc  mov     [rbp+Pid], r12d
0x180015900  mov     [rbp+arg_8], r12d
0x180015904  mov     [rbp+pv], r12
0x180015908  mov     [rbp+var_20], r12
0x18001590c  mov     [rbp+arg_18], r12d
0x180015910  mov     [rbp+var_18], r12
0x180015914  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001591a  mov     edi, eax
0x18001591c  test    eax, eax
0x18001591e  jz      short loc_180015967
0x180015920  jle     short loc_18001592B
0x180015922  movzx   edi, ax
0x180015925  or      edi, 80070000h
0x18001592b  lea     rax, aErrorAskingFor; "Error asking for local PID"
0x180015932  mov     r9d, 810h
0x180015938  lea     r14, aCnameobjectVer; "CNameObject::VerifyLocalCallerIdentitie"...
0x18001593f  mov     ebx, 1
0x180015944  lea     r8, aComComplusDtcD_5; "com\\complus\\dtc\\dtc\\adme\\namesvc.c"...
0x18001594b  mov     ecx, ebx
0x18001594d  mov     [rsp+78h+var_48], rax
0x180015952  mov     edx, ebx
0x180015954  mov     dword ptr [rsp+78h+var_50], edi
0x180015958  mov     [rsp+78h+var_58], r14
0x18001595d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015962  jmp     loc_180015EA4
0x180015967  mov     eax, [rbp+Pid]
0x18001596a  lea     rsi, aComComplusDtcD_5; "com\\complus\\dtc\\dtc\\adme\\namesvc.c"...
0x180015971  mov     dword ptr [rsp+78h+var_40], eax
0x180015975  lea     r14, aCnameobjectVer; "CNameObject::VerifyLocalCallerIdentitie"...
0x18001597c  mov     r13d, 4
0x180015982  lea     rax, aTryingToVerify; "Trying to verify PID %d as MSDTC"
0x180015989  mov     [rsp+78h+var_48], rax
0x18001598e  mov     r9d, 817h
0x180015994  mov     [rsp+78h+var_50], r12
0x180015999  mov     r8, rsi
0x18001599c  mov     edx, r13d
0x18001599f  mov     [rsp+78h+var_58], r14
0x1800159a4  lea     ebx, [r13-3]
0x1800159a8  mov     ecx, ebx
0x1800159aa  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800159af  mov     r8, rsi
0x1800159b2  mov     edx, r13d
0x1800159b5  mov     ecx, ebx
0x1800159b7  cmp     [r15+0D0h], r12
0x1800159be  jz      loc_180015B54
0x1800159c4  lea     rax, aWeHaveATmInsta; "We have a TM instance for that, need to"...
0x1800159cb  mov     r9d, 81Fh
0x1800159d1  mov     [rsp+78h+var_48], rax
0x1800159d6  mov     [rsp+78h+var_50], r12
0x1800159db  mov     [rsp+78h+var_58], r14
0x1800159e0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800159e5  mov     rcx, [r15+0D0h]
0x1800159ec  lea     rdx, [rbp+pv]
0x1800159f0  mov     rax, [rcx]
0x1800159f3  mov     rax, [rax+38h]
0x1800159f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159fc  mov     edi, eax
0x1800159fe  mov     r8, rsi
0x180015a01  mov     ecx, ebx
0x180015a03  test    eax, eax
0x180015a05  jns     short loc_180015A19
0x180015a07  lea     rax, aErrorGettingTm; "Error getting TM instance service name"
0x180015a0e  mov     r9d, 828h
0x180015a14  jmp     loc_18001594D
0x180015a19  mov     rax, [rbp+pv]
0x180015a1d  mov     r9d, 82Ch
0x180015a23  mov     [rsp+78h+var_40], rax
0x180015a28  mov     edx, r13d
0x180015a2b  lea     rax, aItIsServiceS; "It is service '%s'"
0x180015a32  mov     [rsp+78h+var_48], rax
0x180015a37  mov     [rsp+78h+var_50], r12
0x180015a3c  mov     [rsp+78h+var_58], r14
0x180015a41  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015a46  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180015a4a  lea     r8, [rbp+arg_8]; unsigned int *
0x180015a4e  call    ?GetServiceProcessId@CNameObject@@AEAAJPEBGPEAK@Z; CNameObject::GetServiceProcessId(ushort const *,ulong *)
0x180015a53  mov     edi, eax
0x180015a55  test    eax, eax
0x180015a57  jns     short loc_180015A8E
0x180015a59  mov     rax, [rbp+pv]
0x180015a5d  mov     r9d, 834h
0x180015a63  mov     [rsp+78h+var_40], rax
0x180015a68  lea     rax, aErrorGettingPi_0; "Error getting PID for service '%s'"
0x180015a6f  mov     [rsp+78h+var_48], rax
0x180015a74  mov     r8, rsi
0x180015a77  mov     dword ptr [rsp+78h+var_50], edi
0x180015a7b  mov     edx, ebx
0x180015a7d  mov     ecx, ebx
0x180015a7f  mov     [rsp+78h+var_58], r14
0x180015a84  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015a89  jmp     loc_180015EA4
0x180015a8e  mov     eax, [rbp+arg_8]
0x180015a91  mov     r8, rsi
0x180015a94  mov     edx, r13d
0x180015a97  mov     ecx, ebx
0x180015a99  cmp     eax, [rbp+Pid]
0x180015a9c  jnz     short loc_180015AC5
0x180015a9e  lea     rax, aVerified; "Verified!"
0x180015aa5  mov     r9d, 83Ah
0x180015aab  mov     [rsp+78h+var_48], rax
0x180015ab0  mov     [rsp+78h+var_50], r12
0x180015ab5  mov     [rsp+78h+var_58], r14
0x180015aba  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015abf  mov     [r15+64h], ebx
0x180015ac3  jmp     short loc_180015AEA
0x180015ac5  mov     dword ptr [rsp+78h+var_40], eax
0x180015ac9  mov     r9d, 842h
0x180015acf  lea     rax, aNotVerifiedSer; "Not Verified! (Service pid %d)"
0x180015ad6  mov     [rsp+78h+var_48], rax
0x180015adb  mov     [rsp+78h+var_50], r12
0x180015ae0  mov     [rsp+78h+var_58], r14
0x180015ae5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015aea  mov     edi, r12d
0x180015aed  cmp     [r15+64h], r12d
0x180015af1  jnz     loc_180015EA4
0x180015af7  lea     rax, aCheckingLocalK; "Checking local KtmRm..."
0x180015afe  mov     r9d, 8EAh
0x180015b04  mov     [rsp+78h+var_48], rax
0x180015b09  mov     r8, rsi
0x180015b0c  mov     [rsp+78h+var_50], r12
0x180015b11  mov     edx, r13d
0x180015b14  mov     ecx, ebx
0x180015b16  mov     [rsp+78h+var_58], r14
0x180015b1b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015b20  lea     r13, ServiceName; "KtmRm"
0x180015b27  mov     rdx, r13; unsigned __int16 *
0x180015b2a  lea     r8, [rbp+arg_8]; unsigned int *
0x180015b2e  call    ?GetServiceProcessId@CNameObject@@AEAAJPEBGPEAK@Z; CNameObject::GetServiceProcessId(ushort const *,ulong *)
0x180015b33  mov     edi, eax
0x180015b35  test    eax, eax
0x180015b37  jns     loc_180015E6E
0x180015b3d  mov     [rsp+78h+var_40], r13
0x180015b42  lea     rax, aErrorGettingPi; "Error getting PID for %s"
0x180015b49  mov     r9d, 8F2h
0x180015b4f  jmp     loc_180015A6F
0x180015b54  lea     rax, aCheckingLocalM; "Checking local MSDTC..."
0x180015b5b  mov     r9d, 859h
0x180015b61  mov     [rsp+78h+var_48], rax
0x180015b66  mov     [rsp+78h+var_50], r12
0x180015b6b  mov     [rsp+78h+var_58], r14
0x180015b70  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015b75  lea     r8, [rbp+arg_8]; unsigned int *
0x180015b79  lea     rdx, aMsdtc; "MSDTC"
0x180015b80  call    ?GetServiceProcessId@CNameObject@@AEAAJPEBGPEAK@Z; CNameObject::GetServiceProcessId(ushort const *,ulong *)
0x180015b85  mov     edi, eax
0x180015b87  test    eax, eax
0x180015b89  jns     short loc_180015BA9
0x180015b8b  lea     rax, aMsdtc; "MSDTC"
0x180015b92  mov     r9d, 861h
0x180015b98  mov     [rsp+78h+var_40], rax
0x180015b9d  lea     rax, aErrorGettingPi; "Error getting PID for %s"
0x180015ba4  jmp     loc_180015A6F
0x180015ba9  mov     eax, [rbp+Pid]
0x180015bac  cmp     [rbp+arg_8], eax
0x180015baf  jnz     short loc_180015BED
0x180015bb1  lea     rax, aMsdtc; "MSDTC"
0x180015bb8  mov     r9d, 86Ch
0x180015bbe  mov     [rsp+78h+var_40], rax
0x180015bc3  mov     r8, rsi
0x180015bc6  lea     rax, aVerifiedAsLoca_0; "Verified as local MSDTC"
0x180015bcd  mov     edx, ebx
0x180015bcf  mov     [rsp+78h+var_48], rax
0x180015bd4  mov     dword ptr [rsp+78h+var_50], edi
0x180015bd8  mov     ecx, ebx
0x180015bda  mov     [rsp+78h+var_58], r14
0x180015bdf  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015be4  mov     [r15+64h], ebx
0x180015be8  jmp     loc_180015EA1
0x180015bed  lea     rdx, [rbp+arg_0]; bool *
0x180015bf1  mov     byte ptr [rbp+arg_0], r12b
0x180015bf5  xor     ecx, ecx; unsigned __int16 *
0x180015bf7  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x180015bfc  cmp     byte ptr [rbp+arg_0], r12b
0x180015c00  jz      loc_180015AF7
0x180015c06  lea     rax, aClusterPresent; "Cluster present, checking resources..."
0x180015c0d  mov     r9d, 87Ah
0x180015c13  mov     [rsp+78h+var_48], rax
0x180015c18  mov     r8, rsi
0x180015c1b  mov     [rsp+78h+var_50], r12
0x180015c20  mov     edx, r13d
0x180015c23  mov     ecx, ebx
0x180015c25  mov     [rsp+78h+var_58], r14
0x180015c2a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015c2f  lea     r8, [rbp+var_20]
0x180015c33  xor     ecx, ecx
0x180015c35  lea     rdx, [rbp+arg_18]
0x180015c39  call    cs:__imp_MtxCluEnumerateDtcResources
0x180015c3f  mov     edi, eax
0x180015c41  test    eax, eax
0x180015c43  jns     short loc_180015C5A
0x180015c45  lea     rax, aFailedToEnumer; "Failed to enumerate resources"
0x180015c4c  mov     r9d, 87Fh
0x180015c52  mov     r8, rsi
0x180015c55  jmp     loc_18001594B
0x180015c5a  mov     edi, r12d
0x180015c5d  mov     r13d, r12d
0x180015c60  cmp     r13d, [rbp+arg_18]
0x180015c64  jnb     loc_180015E25
0x180015c6a  mov     rcx, [rbp+var_18]
0x180015c6e  test    rcx, rcx
0x180015c71  jz      short loc_180015C83
0x180015c73  mov     rax, [rcx]
0x180015c76  mov     rax, [rax+10h]
0x180015c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c7f  mov     [rbp+var_18], r12
0x180015c83  mov     rcx, [rbp+pv]; pv
0x180015c87  call    cs:__imp_CoTaskMemFree
0x180015c8d  mov     rdx, [rbp+var_20]
0x180015c91  lea     r8, [rbp+var_18]
0x180015c95  mov     [rbp+pv], r12
0x180015c99  xor     ecx, ecx
0x180015c9b  mov     r12d, r13d
0x180015c9e  mov     [rbp+var_10], r12
0x180015ca2  mov     rdx, [rdx+r12*8]
0x180015ca6  call    cs:__imp_MtxCluCreateClusterTmInstance
0x180015cac  mov     [rbp+arg_0], eax
0x180015caf  test    eax, eax
0x180015cb1  jns     short loc_180015CF2
0x180015cb3  mov     rcx, [rbp+var_20]
0x180015cb7  mov     r9d, 8A2h
0x180015cbd  mov     rdx, [rcx+r12*8]
0x180015cc1  lea     rcx, aFailedToGetTmI; "  Failed to get TM instance for '%s'"
0x180015cc8  mov     [rsp+78h+var_40], rdx
0x180015ccd  mov     r8, rsi
0x180015cd0  mov     [rsp+78h+var_48], rcx
0x180015cd5  mov     edx, ebx
0x180015cd7  mov     dword ptr [rsp+78h+var_50], eax
0x180015cdb  mov     ecx, ebx
0x180015cdd  mov     [rsp+78h+var_58], r14
0x180015ce2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015ce7  mov     edi, [rbp+arg_0]
0x180015cea  xor     r12d, r12d
0x180015ced  jmp     loc_180015DF0
0x180015cf2  mov     rcx, [rbp+var_18]
0x180015cf6  lea     rdx, [rbp+pv]
0x180015cfa  mov     rax, [rcx]
0x180015cfd  mov     rax, [rax+38h]
0x180015d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d06  mov     [rbp+arg_0], eax
0x180015d09  test    eax, eax
0x180015d0b  jns     short loc_180015D24
0x180015d0d  mov     rcx, [rbp+var_20]
0x180015d11  mov     r9d, 8ADh
0x180015d17  mov     rdx, [rcx+r12*8]
0x180015d1b  lea     rcx, aFailedToGetSer; "  Failed to get service name for '%s'"
0x180015d22  jmp     short loc_180015CC8
0x180015d24  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180015d28  lea     r8, [rbp+arg_8]; unsigned int *
0x180015d2c  call    ?GetServiceProcessId@CNameObject@@AEAAJPEBGPEAK@Z; CNameObject::GetServiceProcessId(ushort const *,ulong *)
0x180015d31  mov     r12d, eax
0x180015d34  mov     r8, rsi
0x180015d37  test    eax, eax
0x180015d39  jns     short loc_180015DA9
0x180015d3b  mov     rax, [rbp+pv]
0x180015d3f  mov     ecx, ebx
0x180015d41  mov     [rsp+78h+var_40], rax
0x180015d46  cmp     r12d, 80070424h
0x180015d4d  jnz     short loc_180015D7E
0x180015d4f  lea     rax, aServiceSDoesNo; "Service '%s' does not exist - it is not"...
0x180015d56  mov     r9d, 8B9h
0x180015d5c  mov     [rsp+78h+var_48], rax
0x180015d61  mov     edx, 3
0x180015d66  mov     [rsp+78h+var_50], 0
0x180015d6f  mov     [rsp+78h+var_58], r14
0x180015d74  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015d79  xor     r12d, r12d
0x180015d7c  jmp     short loc_180015DA1
0x180015d7e  lea     rax, aErrorGettingSe; "Error getting service PID for '%s'"
0x180015d85  mov     r9d, 8C1h
0x180015d8b  mov     [rsp+78h+var_48], rax
0x180015d90  mov     edx, ebx
0x180015d92  mov     dword ptr [rsp+78h+var_50], r12d
0x180015d97  mov     [rsp+78h+var_58], r14
0x180015d9c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180015da1  mov     edi, r12d
0x180015da4  jmp     loc_180015CEA
0x180015da9  mov     eax, [rbp+arg_8]
0x180015dac  xor     r12d, r12d
0x180015daf  lea     edx, [r12+4]
0x180015db4  cmp     eax, [rbp+Pid]
0x180015db7  jz      short loc_180015DF8
0x180015db9  mov     [rsp+78h+var_38], eax
0x180015dbd  mov     r9d, 8D8h
0x180015dc3  mov     rax, [rbp+var_20]
0x180015dc7  mov     ecx, r13d
  ... truncated ...
```
