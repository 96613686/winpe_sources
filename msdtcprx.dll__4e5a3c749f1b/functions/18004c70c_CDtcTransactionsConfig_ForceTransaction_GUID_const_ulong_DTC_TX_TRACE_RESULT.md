# CDtcTransactionsConfig::ForceTransaction(_GUID const &,ulong,_DTC_TX_TRACE_RESULT *)

- ea: `0x18004c70c`
- end: `0x18004cb28`
- name: `?ForceTransaction@CDtcTransactionsConfig@@AEAAJAEBU_GUID@@KPEAW4_DTC_TX_TRACE_RESULT@@@Z`
- size: `1052`
- prototype: `__int64 __fastcall(CDtcTransactionsConfig *__hidden this, const struct _GUID *, unsigned int, enum _DTC_TX_TRACE_RESULT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bc54`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x180048d50`
- `0x180049010`
- `0x18004c70c`
- `0x18007ee20`
- `0x18007f82c`
- `0x18007f8a0`
- `0x180081dd0`
- `0x180085010`

## string_xrefs

- `0x18004c74a`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004c833`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004c8cb`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004c9f0`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004ca2f`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004cae8`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004c76f`: `CDtcTransactionsConfig::ForceTransaction`
- `0x18004c7d5`: `CDtcTransactionsConfig::ForceTransaction`
- `0x18004c828`: `CDtcTransactionsConfig::ForceTransaction`
- `0x18004c8c0`: `CDtcTransactionsConfig::ForceTransaction`
- `0x18004c925`: `CDtcTransactionsConfig::ForceTransaction`
- `0x18004c97a`: `CDtcTransactionsConfig::ForceTransaction`
- `0x18004c9e0`: `CDtcTransactionsConfig::ForceTransaction`
- `0x18004ca0e`: `CDtcTransactionsConfig::ForceTransaction`
- `0x18004c795`: `CDtcTransactionsConfig::ForceTransaction (com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp@808): pResolveTx shouldn't be NULL`
- `0x18004ca1a`: `failed to create pCSendReceive.`

## pseudocode

```c
__int64 __fastcall CDtcTransactionsConfig::ForceTransaction(
        CDtcTransactionsConfig *this,
        const struct _GUID *a2,
        unsigned int a3,
        enum _DTC_TX_TRACE_RESULT *a4)
{
  struct INameObject *v7; // r15
  int v8; // esi
  CDtcConfig *v9; // rcx
  int ConnectionDispenser; // eax
  struct IConnectionDispenser *v11; // r12
  int v12; // ebx
  CIConnSink *v13; // rdi
  const wchar_t *v14; // rax
  __int64 v15; // r9
  struct CSendReceive *Instance; // rax
  int PartnerNamedObject; // eax
  __int64 v19; // [rsp+28h] [rbp-61h]
  __int64 v20; // [rsp+28h] [rbp-61h]
  __int64 v21; // [rsp+38h] [rbp-51h]
  int v22; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v23; // [rsp+54h] [rbp-35h]
  struct IConnectionDispenser *v24; // [rsp+58h] [rbp-31h] BYREF
  struct INameObject *v25; // [rsp+60h] [rbp-29h] BYREF
  __int64 v26; // [rsp+68h] [rbp-21h] BYREF
  CDtcConfig **v27; // [rsp+70h] [rbp-19h]
  enum _DTC_TX_TRACE_RESULT *v28; // [rsp+78h] [rbp-11h]
  __int128 v29; // [rsp+80h] [rbp-9h] BYREF

  v28 = a4;
  v23 = a3;
  v24 = 0;
  v25 = 0;
  v22 = 0;
  v26 = 0;
  v7 = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    807,
    L"CDtcTransactionsConfig::ForceTransaction",
    0,
    L"In");
  if ( !a4 )
    DtcInternalErrorW(
      L"CDtcTransactionsConfig::ForceTransaction (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp@808): pResolveTx "
       "shouldn't be NULL");
  v8 = 0;
  v9 = (CDtcConfig *)*((_QWORD *)this + 3);
  v29 = (__int128)*a2;
  v27 = (CDtcConfig **)((char *)this + 24);
  ConnectionDispenser = CDtcConfig::GetConnectionDispenser(v9, &v24);
  v11 = v24;
  v12 = ConnectionDispenser;
  if ( ConnectionDispenser < 0 )
  {
    v13 = 0;
    v14 = L"GetConnectionDispenser failed.";
    v15 = 816;
    goto LABEL_26;
  }
  Instance = CSendReceive::CreateInstance();
  v13 = Instance;
  if ( !Instance )
  {
LABEL_25:
    v12 = -2147024882;
    v14 = L"failed to create pCSendReceive.";
    v15 = 833;
    goto LABEL_26;
  }
  if ( !(*(unsigned int (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance + 32LL))(Instance) )
  {
    LODWORD(v19) = v12;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      825,
      L"CDtcTransactionsConfig::ForceTransaction",
      v19,
      L"Initilizing CSendReceive failed.");
    CIConnSink::DeleteObject(v13);
    v13 = 0;
    goto LABEL_25;
  }
  (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v13 + 160LL))(v13);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
  (*(void (__fastcall **)(CIConnSink *, unsigned __int64))(*(_QWORD *)v13 + 136LL))(
    v13,
    ((unsigned __int64)this + 8) & -(__int64)(this != 0));
  PartnerNamedObject = CDtcConfig::GetPartnerNamedObject(*v27, &v25);
  if ( PartnerNamedObject < 0 )
  {
    LODWORD(v19) = PartnerNamedObject;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      843,
      L"CDtcTransactionsConfig::ForceTransaction",
      v19,
      L"GetPartnerNamedObject failed.");
    return 0;
  }
  v7 = v25;
  v12 = (*(__int64 (__fastcall **)(CIConnSink *, struct IConnectionDispenser *, struct INameObject *, __int64, int))(*(_QWORD *)v13 + 248LL))(
          v13,
          v11,
          v25,
          1,
          7);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(CIConnSink *, _QWORD, __int64, __int128 *, int *, __int64 *, _DWORD, _QWORD))(*(_QWORD *)v13 + 96LL))(
            v13,
            v23,
            16,
            &v29,
            &v22,
            &v26,
            0,
            0);
    if ( !v12 )
    {
      if ( v22 != 4212 )
      {
        v12 = -2147467259;
        switch ( v22 )
        {
          case 4213:
            v8 = 1;
            break;
          case 4214:
            v8 = 2;
            break;
          case 4215:
            v8 = 3;
            break;
          case 4216:
            v8 = 4;
            break;
          default:
            v8 = 5;
            break;
        }
      }
      LODWORD(v21) = v22;
      TraceStringInline(
        15,
        3,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
        900,
        L"CDtcTransactionsConfig::ForceTransaction",
        0,
        L"Received MTAG: %d",
        v21);
      goto LABEL_27;
    }
    v8 = 5;
    v14 = L"SendReceive failed.";
    v15 = 865;
  }
  else
  {
    v14 = L"Failed to connect.";
    v15 = 853;
  }
LABEL_26:
  LODWORD(v19) = v12;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    v15,
    L"CDtcTransactionsConfig::ForceTransaction",
    v19,
    v14);
LABEL_27:
  if ( v26 )
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v13 + 120LL))(v13);
  if ( v12 < 0 )
    *(_DWORD *)v28 = v8;
  if ( v11 )
    (*(void (__fastcall **)(struct IConnectionDispenser *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v7 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v13 )
  {
    CSendReceive::Cancel(v13);
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v13 + 144LL))(v13);
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v13 + 272LL))(v13);
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v13 + 168LL))(v13);
  }
  LODWORD(v20) = v12;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    923,
    L"CDtcTransactionsConfig::ForceTransaction",
    v20,
    L"Out");
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004c70c  push    rbp
0x18004c70e  push    rbx
0x18004c70f  push    rsi
0x18004c710  push    rdi
0x18004c711  push    r12
0x18004c713  push    r13
0x18004c715  push    r14
0x18004c717  push    r15
0x18004c719  lea     rbp, [rsp-1Fh]
0x18004c71e  sub     rsp, 0A8h
0x18004c725  mov     rax, cs:__security_cookie
0x18004c72c  xor     rax, rsp
0x18004c72f  mov     [rbp+57h+var_50], rax
0x18004c733  xor     r14d, r14d
0x18004c736  mov     [rbp+57h+var_68], r9
0x18004c73a  lea     rax, aIn_0; "In"
0x18004c741  mov     [rbp+57h+var_8C], r8d
0x18004c745  mov     [rsp+0E0h+var_B0], rax
0x18004c74a  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004c751  mov     rbx, rdx
0x18004c754  mov     [rsp+0E0h+var_B8], r14
0x18004c759  lea     edx, [r14+6]
0x18004c75d  mov     [rbp+57h+var_88], r14
0x18004c761  mov     rdi, r9
0x18004c764  mov     [rbp+57h+var_80], r14
0x18004c768  mov     r13, rcx
0x18004c76b  mov     [rbp+57h+var_90], r14d
0x18004c76f  lea     rax, aCdtctransactio_5; "CDtcTransactionsConfig::ForceTransactio"...
0x18004c776  mov     [rbp+57h+var_78], r14
0x18004c77a  lea     ecx, [rdx+9]
0x18004c77d  mov     [rsp+0E0h+var_C0], rax
0x18004c782  mov     r9d, 327h
0x18004c788  mov     r15d, r14d
0x18004c78b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004c790  test    rdi, rdi
0x18004c793  jnz     short loc_18004C7A2
0x18004c795  lea     rcx, aCdtctransactio_8; "CDtcTransactionsConfig::ForceTransactio"...
0x18004c79c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18004c7a2  movups  xmm0, xmmword ptr [rbx]
0x18004c7a5  lea     rax, [r13+18h]
0x18004c7a9  mov     esi, r14d
0x18004c7ac  mov     rcx, [rax]; this
0x18004c7af  lea     rdx, [rbp+57h+var_88]; struct IConnectionDispenser **
0x18004c7b3  movdqu  [rbp+57h+var_60], xmm0
0x18004c7b8  mov     [rbp+57h+var_70], rax
0x18004c7bc  call    ?GetConnectionDispenser@CDtcConfig@@QEAAJPEAPEAUIConnectionDispenser@@@Z; CDtcConfig::GetConnectionDispenser(IConnectionDispenser * *)
0x18004c7c1  mov     r12, [rbp+57h+var_88]
0x18004c7c5  mov     ebx, eax
0x18004c7c7  test    eax, eax
0x18004c7c9  jns     short loc_18004C7EC
0x18004c7cb  mov     rdi, r14
0x18004c7ce  lea     rax, aGetconnectiond_0; "GetConnectionDispenser failed."
0x18004c7d5  lea     r13, aCdtctransactio_5; "CDtcTransactionsConfig::ForceTransactio"...
0x18004c7dc  mov     r9d, 330h
0x18004c7e2  mov     edx, 1
0x18004c7e7  jmp     loc_18004CA2A
0x18004c7ec  call    ?CreateInstance@CSendReceive@@SAPEAV1@XZ; CSendReceive::CreateInstance(void)
0x18004c7f1  mov     rdi, rax
0x18004c7f4  mov     r14d, 1
0x18004c7fa  test    rax, rax
0x18004c7fd  jz      loc_18004CA0E
0x18004c803  mov     rcx, [rax]
0x18004c806  mov     rax, [rcx+20h]
0x18004c80a  mov     rcx, rdi
0x18004c80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c812  test    eax, eax
0x18004c814  jnz     short loc_18004C85A
0x18004c816  lea     rax, aInitilizingCse; "Initilizing CSendReceive failed."
0x18004c81d  mov     r9d, 339h
0x18004c823  mov     [rsp+0E0h+var_B0], rax
0x18004c828  lea     r13, aCdtctransactio_5; "CDtcTransactionsConfig::ForceTransactio"...
0x18004c82f  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18004c833  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004c83a  mov     edx, r14d
0x18004c83d  mov     [rsp+0E0h+var_C0], r13
0x18004c842  lea     ecx, [r14+0Eh]
0x18004c846  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004c84b  mov     rcx, rdi; this
0x18004c84e  call    ?DeleteObject@CIConnSink@@UEAAXXZ; CIConnSink::DeleteObject(void)
0x18004c853  xor     edi, edi
0x18004c855  jmp     loc_18004CA15
0x18004c85a  mov     rax, [rdi]
0x18004c85d  mov     rcx, rdi
0x18004c860  mov     rax, [rax+0A0h]
0x18004c867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c86c  lea     rbx, [r13+8]
0x18004c870  mov     rax, [rbx]
0x18004c873  mov     rcx, rbx
0x18004c876  mov     rax, [rax+8]
0x18004c87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c87f  mov     rax, [rdi]
0x18004c882  neg     r13
0x18004c885  mov     rcx, rdi
0x18004c888  sbb     rdx, rdx
0x18004c88b  and     rdx, rbx
0x18004c88e  mov     rax, [rax+88h]
0x18004c895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c89a  mov     rcx, [rbp+57h+var_70]
0x18004c89e  lea     rdx, [rbp+57h+var_80]; struct INameObject **
0x18004c8a2  mov     rcx, [rcx]; this
0x18004c8a5  call    ?GetPartnerNamedObject@CDtcConfig@@QEAAJPEAPEAUINameObject@@@Z; CDtcConfig::GetPartnerNamedObject(INameObject * *)
0x18004c8aa  test    eax, eax
0x18004c8ac  jns     short loc_18004C8EB
0x18004c8ae  lea     rdx, aGetpartnername; "GetPartnerNamedObject failed."
0x18004c8b5  mov     r9d, 34Bh
0x18004c8bb  mov     [rsp+0E0h+var_B0], rdx
0x18004c8c0  lea     r13, aCdtctransactio_5; "CDtcTransactionsConfig::ForceTransactio"...
0x18004c8c7  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18004c8cb  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004c8d2  mov     edx, r14d
0x18004c8d5  mov     [rsp+0E0h+var_C0], r13
0x18004c8da  mov     ecx, 0Fh
0x18004c8df  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004c8e4  xor     eax, eax
0x18004c8e6  jmp     loc_18004CB08
0x18004c8eb  mov     rax, [rdi]
0x18004c8ee  mov     r9d, r14d
0x18004c8f1  mov     r15, [rbp+57h+var_80]
0x18004c8f5  mov     rdx, r12
0x18004c8f8  mov     r8, r15
0x18004c8fb  mov     dword ptr [rsp+0E0h+var_C0], 7
0x18004c903  mov     rcx, rdi
0x18004c906  mov     rax, [rax+0F8h]
0x18004c90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c912  mov     ebx, eax
0x18004c914  test    eax, eax
0x18004c916  jns     short loc_18004C931
0x18004c918  lea     rax, aFailedToConnec_0; "Failed to connect."
0x18004c91f  mov     r9d, 355h
0x18004c925  lea     r13, aCdtctransactio_5; "CDtcTransactionsConfig::ForceTransactio"...
0x18004c92c  jmp     loc_18004CA27
0x18004c931  mov     rax, [rdi]
0x18004c934  lea     rcx, [rbp+57h+var_78]
0x18004c938  mov     edx, [rbp+57h+var_8C]
0x18004c93b  lea     r9, [rbp+57h+var_60]
0x18004c93f  mov     [rsp+0E0h+var_A8], rsi
0x18004c944  mov     r8d, 10h
0x18004c94a  mov     dword ptr [rsp+0E0h+var_B0], esi
0x18004c94e  mov     rax, [rax+60h]
0x18004c952  mov     [rsp+0E0h+var_B8], rcx
0x18004c957  lea     rcx, [rbp+57h+var_90]
0x18004c95b  mov     [rsp+0E0h+var_C0], rcx
0x18004c960  mov     rcx, rdi
0x18004c963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c968  mov     ebx, eax
0x18004c96a  test    eax, eax
0x18004c96c  jz      short loc_18004C98C
0x18004c96e  mov     esi, 5
0x18004c973  lea     rax, aSendreceiveFai; "SendReceive failed."
0x18004c97a  lea     r13, aCdtctransactio_5; "CDtcTransactionsConfig::ForceTransactio"...
0x18004c981  mov     r9d, 361h
0x18004c987  jmp     loc_18004CA27
0x18004c98c  mov     ecx, [rbp+57h+var_90]
0x18004c98f  mov     edx, 3
0x18004c994  mov     eax, ecx
0x18004c996  sub     eax, 1074h
0x18004c99b  jz      short loc_18004C9D0
0x18004c99d  mov     ebx, 80004005h
0x18004c9a2  sub     eax, r14d
0x18004c9a5  jz      short loc_18004C9CD
0x18004c9a7  sub     eax, r14d
0x18004c9aa  jz      short loc_18004C9C6
0x18004c9ac  sub     eax, r14d
0x18004c9af  jz      short loc_18004C9C2
0x18004c9b1  cmp     eax, r14d
0x18004c9b4  jz      short loc_18004C9BB
0x18004c9b6  lea     esi, [rdx+2]
0x18004c9b9  jmp     short loc_18004C9D0
0x18004c9bb  mov     esi, 4
0x18004c9c0  jmp     short loc_18004C9D0
0x18004c9c2  mov     esi, edx
0x18004c9c4  jmp     short loc_18004C9D0
0x18004c9c6  mov     esi, 2
0x18004c9cb  jmp     short loc_18004C9D0
0x18004c9cd  mov     esi, r14d
0x18004c9d0  mov     dword ptr [rsp+0E0h+var_A8], ecx
0x18004c9d4  lea     rax, aReceivedMtagD; "Received MTAG: %d"
0x18004c9db  mov     [rsp+0E0h+var_B0], rax
0x18004c9e0  lea     r13, aCdtctransactio_5; "CDtcTransactionsConfig::ForceTransactio"...
0x18004c9e7  mov     [rsp+0E0h+var_B8], 0
0x18004c9f0  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004c9f7  mov     r9d, 384h
0x18004c9fd  mov     [rsp+0E0h+var_C0], r13
0x18004ca02  mov     ecx, 0Fh
0x18004ca07  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004ca0c  jmp     short loc_18004CA49
0x18004ca0e  lea     r13, aCdtctransactio_5; "CDtcTransactionsConfig::ForceTransactio"...
0x18004ca15  mov     ebx, 8007000Eh
0x18004ca1a  lea     rax, aFailedToCreate_0; "failed to create pCSendReceive."
0x18004ca21  mov     r9d, 341h
0x18004ca27  mov     edx, r14d
0x18004ca2a  mov     [rsp+0E0h+var_B0], rax
0x18004ca2f  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004ca36  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18004ca3a  mov     ecx, 0Fh
0x18004ca3f  mov     [rsp+0E0h+var_C0], r13
0x18004ca44  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004ca49  mov     rdx, [rbp+57h+var_78]
0x18004ca4d  test    rdx, rdx
0x18004ca50  jz      short loc_18004CA61
0x18004ca52  mov     rax, [rdi]
0x18004ca55  mov     rcx, rdi
0x18004ca58  mov     rax, [rax+78h]
0x18004ca5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca61  test    ebx, ebx
0x18004ca63  jns     short loc_18004CA6B
0x18004ca65  mov     rax, [rbp+57h+var_68]
0x18004ca69  mov     [rax], esi
0x18004ca6b  test    r12, r12
0x18004ca6e  jz      short loc_18004CA80
0x18004ca70  mov     rax, [r12]
0x18004ca74  mov     rcx, r12
0x18004ca77  mov     rax, [rax+10h]
0x18004ca7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca80  test    r15, r15
0x18004ca83  jz      short loc_18004CA94
0x18004ca85  mov     rax, [r15]
0x18004ca88  mov     rcx, r15
0x18004ca8b  mov     rax, [rax+10h]
0x18004ca8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca94  test    rdi, rdi
0x18004ca97  jz      short loc_18004CAD7
0x18004ca99  mov     rcx, rdi; this
0x18004ca9c  call    ?Cancel@CSendReceive@@QEAAJXZ; CSendReceive::Cancel(void)
0x18004caa1  mov     rax, [rdi]
0x18004caa4  mov     rcx, rdi
0x18004caa7  mov     rax, [rax+90h]
0x18004caae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cab3  mov     rax, [rdi]
0x18004cab6  mov     rcx, rdi
0x18004cab9  mov     rax, [rax+110h]
0x18004cac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cac5  mov     rax, [rdi]
0x18004cac8  mov     rcx, rdi
0x18004cacb  mov     rax, [rax+0A8h]
0x18004cad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cad7  mov     edx, 6
0x18004cadc  lea     rax, aOut; "Out"
0x18004cae3  mov     [rsp+0E0h+var_B0], rax
0x18004cae8  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004caef  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18004caf3  mov     r9d, 39Bh
0x18004caf9  mov     [rsp+0E0h+var_C0], r13
0x18004cafe  lea     ecx, [rdx+9]
0x18004cb01  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004cb06  mov     eax, ebx
0x18004cb08  mov     rcx, [rbp+57h+var_50]
0x18004cb0c  xor     rcx, rsp; StackCookie
0x18004cb0f  call    __security_check_cookie
0x18004cb14  add     rsp, 0A8h
0x18004cb1b  pop     r15
0x18004cb1d  pop     r14
0x18004cb1f  pop     r13
0x18004cb21  pop     r12
0x18004cb23  pop     rdi
0x18004cb24  pop     rsi
0x18004cb25  pop     rbx
0x18004cb26  pop     rbp
0x18004cb27  retn
```
