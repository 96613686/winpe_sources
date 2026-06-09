# DusmEthernet::NsiAdapterEnumCallback(NsiNotifications::NotificationTypes,_NET_LUID_LH const &,_NDIS_NSI_INTERFACE_ENUM_ROD const *,_NDIS_NSI_INTERFACE_ENUM_ROS const *)

- ea: `0x180034950`
- end: `0x180034cc7`
- name: `?NsiAdapterEnumCallback@DusmEthernet@@CAXW4NotificationTypes@NsiNotifications@@AEBT_NET_LUID_LH@@PEBU_NDIS_NSI_INTERFACE_ENUM_ROD@@PEBU_NDIS_NSI_INTERFACE_ENUM_ROS@@@Z`
- size: `887`
- prototype: `static void __high(enum NsiNotifications::NotificationTypes, const union _NET_LUID_LH *, const struct _NDIS_NSI_INTERFACE_ENUM_ROD *, const struct _NDIS_NSI_INTERFACE_ENUM_ROS *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001c20`
- `0x180005db0`
- `0x180005e2c`
- `0x180005ec0`
- `0x180007c90`
- `0x180013444`
- `0x18001db50`
- `0x18002f510`
- `0x1800344c0`
- `0x180034950`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034a4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034a4e`

## pseudocode

```c
int __fastcall DusmEthernet::NsiAdapterEnumCallback(__int64 a1, __int64 *a2, NsiNotifications *a3, __int64 a4)
{
  int v7; // ebx
  int *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int result; // eax
  const struct _NDIS_NSI_INTERFACE_ENUM_ROD *v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r15
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  const struct _NDIS_NSI_INTERFACE_ENUM_ROD *v18; // rdx
  _DWORD *v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  BOOL v22; // eax
  __int64 v23; // rdx
  _DWORD *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  bool IsInterfaceOperational; // bl
  _DWORD *v28; // r8
  __int64 v29; // r9
  int *v30; // r8
  __int64 v31; // r9
  int v32; // ecx
  bool v33; // zf
  int v34; // eax
  bool v35; // [rsp+70h] [rbp-90h] BYREF
  char v36; // [rsp+71h] [rbp-8Fh] BYREF
  bool v37; // [rsp+72h] [rbp-8Eh] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall **v41)(); // [rsp+90h] [rbp-70h] BYREF
  __int128 v42; // [rsp+98h] [rbp-68h]
  BOOL v43; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall ***v44)(); // [rsp+C8h] [rbp-38h]
  __int64 v45; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v46; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v48; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v49; // [rsp+101h] [rbp+1h]
  char v50; // [rsp+103h] [rbp+3h]

  v7 = a1;
  if ( !a4 )
  {
    v8 = *(int **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(a1, a2) + 8);
    result = *v8;
    if ( (unsigned int)*v8 > 5 )
    {
      v38 = *a2;
      LODWORD(v39) = v7;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
               (int)v8,
               (int)word_18005928A,
               v9,
               v10,
               (__int64)&v38,
               (__int64)&v39);
    }
    return result;
  }
  v12 = (const struct _NDIS_NSI_INTERFACE_ENUM_ROD *)*(unsigned int *)(a4 + 556);
  v13 = *(_DWORD *)(a4 + 556) & 2;
  if ( (*(_DWORD *)(a4 + 556) & 2) == 0 )
  {
    if ( *(_WORD *)(a4 + 520) == 281 )
      goto LABEL_14;
    result = *(_DWORD *)(a4 + 564);
    if ( !result || result == 19 )
    {
      if ( *(_DWORD *)(a4 + 560) )
        goto LABEL_14;
    }
    else if ( result != 14 )
    {
      goto LABEL_14;
    }
    if ( ((unsigned __int8)v12 & 1) == 0 )
      goto LABEL_15;
    if ( *(_BYTE *)(a4 + 552) )
      goto LABEL_17;
  }
  if ( (_DWORD)v13 )
  {
LABEL_35:
    v14 = a4 + 6;
    goto LABEL_36;
  }
LABEL_14:
  if ( ((unsigned __int8)v12 & 1) != 0 )
    goto LABEL_35;
LABEL_15:
  if ( *(_DWORD *)(a4 + 560) )
    goto LABEL_35;
  v14 = a4 + 6;
  result = CompareStringOrdinal(L"Microsoft Kernel Debug Network Adapter", -1, (LPCWCH)(a4 + 6), -1, 1);
  if ( result == 2 )
  {
LABEL_17:
    v48 = *(_OWORD *)(a4 + 536);
    v15 = v7 - 1;
    if ( !v15 )
    {
      IsInterfaceOperational = 0;
      if ( a3 )
        IsInterfaceOperational = NsiNotifications::IsInterfaceOperational(a3, v12);
      v28 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12) + 8);
      if ( *v28 > 5u )
      {
        v35 = IsInterfaceOperational;
        v38 = (__int64)&v48;
        v40 = *a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
          (int)v28,
          (int)byte_1800590F3,
          (__int64)v28,
          v29,
          (__int64)&v40,
          &v38,
          (__int64)&v35);
      }
      LOBYTE(v43) = IsInterfaceOperational;
      v41 = off_18004C780;
      *(_WORD *)((char *)&v43 + 1) = v49;
      HIBYTE(v43) = v50;
      goto LABEL_26;
    }
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 2;
      if ( !v17 )
      {
        v24 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12) + 8);
        if ( *v24 > 5u )
        {
          v38 = (__int64)&v48;
          v40 = *a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
            (int)v24,
            (int)byte_1800590A1,
            v25,
            v26,
            (__int64)&v40,
            &v38);
        }
        v41 = off_18004C7B0;
        goto LABEL_26;
      }
      if ( v17 != 4 )
        return result;
    }
    v19 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12) + 8);
    if ( *v19 > 5u )
    {
      v38 = (__int64)&v48;
      v40 = *a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
        (int)v19,
        (int)&unk_180059238,
        v20,
        v21,
        (__int64)&v40,
        &v38);
    }
    v22 = 0;
    if ( a3 )
      v22 = NsiNotifications::IsInterfaceOperational(a3, v18);
    v43 = v22;
    v41 = off_18004C840;
LABEL_26:
    v44 = &v41;
    v42 = v48;
    DusmAsync::SubmitOrderedWork(&v41);
    return std::function<long (void)>::~function<long (void)>((__int64)&v41, v23);
  }
LABEL_36:
  v30 = *(int **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12) + 8);
  result = *v30;
  if ( (unsigned int)*v30 > 5 )
  {
    v32 = *(_DWORD *)(a4 + 556);
    v33 = *(_BYTE *)(a4 + 552) == 0;
    LODWORD(v39) = *(_DWORD *)(a4 + 560);
    v34 = *(_DWORD *)(a4 + 564);
    v35 = !v33;
    LODWORD(v40) = v34;
    v36 = v32 & 1;
    v37 = (v32 & 2) != 0;
    v46 = a4 + 536;
    v47 = *a2;
    v45 = v14;
    LODWORD(v38) = v7;
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
             (int)v30,
             (int)&word_18005915E,
             (__int64)v30,
             v31,
             (__int64)&v47,
             (__int64)&v38,
             &v46,
             (const WCHAR **)&v45,
             (__int64)&v37,
             (__int64)&v36,
             (__int64)&v35,
             (__int64)&v40,
             (__int64)&v39);
  }
  return result;
}

```

## disassembly

```asm
0x180034950  push    rbp
0x180034952  push    rbx
0x180034953  push    rsi
0x180034954  push    rdi
0x180034955  push    r14
0x180034957  push    r15
0x180034959  lea     rbp, [rsp-28h]
0x18003495e  sub     rsp, 128h
0x180034965  mov     rax, cs:__security_cookie
0x18003496c  xor     rax, rsp
0x18003496f  mov     [rbp+50h+var_40], rax
0x180034973  mov     rdi, r9
0x180034976  mov     rsi, r8
0x180034979  mov     r14, rdx
0x18003497c  mov     ebx, ecx
0x18003497e  test    r9, r9
0x180034981  jnz     short loc_1800349C6
0x180034983  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180034988  mov     rcx, [rax+8]
0x18003498c  mov     eax, [rcx]
0x18003498e  cmp     eax, 5
0x180034991  jbe     loc_180034CAB
0x180034997  mov     rax, [r14]
0x18003499a  lea     rdx, word_18005928A
0x1800349a1  mov     [rsp+150h+var_D8], rax
0x1800349a6  lea     rax, [rbp+50h+var_D0]
0x1800349aa  mov     [rsp+150h+var_128], rax
0x1800349af  lea     rax, [rsp+150h+var_D8]
0x1800349b4  mov     qword ptr [rsp+150h+bIgnoreCase], rax
0x1800349b9  mov     dword ptr [rbp+50h+var_D0], ebx
0x1800349bc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800349c1  jmp     loc_180034CAB
0x1800349c6  mov     edx, [r9+22Ch]
0x1800349cd  mov     ecx, edx
0x1800349cf  and     ecx, 2
0x1800349d2  jnz     short loc_180034A13
0x1800349d4  mov     eax, 119h
0x1800349d9  cmp     [r9+208h], ax
0x1800349e1  jz      short loc_180034A1B
0x1800349e3  mov     eax, [r9+234h]
0x1800349ea  test    eax, eax
0x1800349ec  jz      short loc_1800349FA
0x1800349ee  cmp     eax, 13h
0x1800349f1  jz      short loc_1800349FA
0x1800349f3  cmp     eax, 0Eh
0x1800349f6  jz      short loc_180034A04
0x1800349f8  jmp     short loc_180034A1B
0x1800349fa  cmp     dword ptr [r9+230h], 0
0x180034a02  jnz     short loc_180034A1B
0x180034a04  test    dl, 1
0x180034a07  jz      short loc_180034A24
0x180034a09  cmp     byte ptr [r9+228h], 0
0x180034a11  jnz     short loc_180034A5D
0x180034a13  test    ecx, ecx
0x180034a15  jnz     loc_180034BDF
0x180034a1b  test    dl, 1
0x180034a1e  jnz     loc_180034BDF
0x180034a24  cmp     dword ptr [r9+230h], 0
0x180034a2c  jnz     loc_180034BDF
0x180034a32  lea     r15, [r9+6]
0x180034a36  mov     [rsp+150h+bIgnoreCase], 1; bIgnoreCase
0x180034a3e  or      edx, 0FFFFFFFFh; cchCount1
0x180034a41  lea     rcx, String1; "Microsoft Kernel Debug Network Adapter"
0x180034a48  mov     r9d, edx; cchCount2
0x180034a4b  mov     r8, r15; lpString2
0x180034a4e  call    cs:__imp_CompareStringOrdinal
0x180034a54  cmp     eax, 2
0x180034a57  jnz     loc_180034BE3
0x180034a5d  movups  xmm0, xmmword ptr [rdi+218h]
0x180034a64  movdqu  [rbp+50h+var_60], xmm0
0x180034a69  sub     ebx, 1
0x180034a6c  jz      loc_180034B5C
0x180034a72  sub     ebx, 1
0x180034a75  jz      short loc_180034A89
0x180034a77  sub     ebx, 2
0x180034a7a  jz      loc_180034B10
0x180034a80  cmp     ebx, 4
0x180034a83  jnz     loc_180034CAB
0x180034a89  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180034a8e  mov     rcx, [rax+8]
0x180034a92  mov     eax, [rcx]
0x180034a94  cmp     eax, 5
0x180034a97  jbe     short loc_180034AC8
0x180034a99  lea     rax, [rbp+50h+var_60]
0x180034a9d  mov     [rsp+150h+var_D8], rax
0x180034aa2  lea     rdx, unk_180059238
0x180034aa9  mov     rax, [r14]
0x180034aac  mov     [rbp+50h+var_C8], rax
0x180034ab0  lea     rax, [rsp+150h+var_D8]
0x180034ab5  mov     [rsp+150h+var_128], rax
0x180034aba  lea     rax, [rbp+50h+var_C8]
0x180034abe  mov     qword ptr [rsp+150h+bIgnoreCase], rax
0x180034ac3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x180034ac8  xor     eax, eax
0x180034aca  test    rsi, rsi
0x180034acd  jz      short loc_180034ADA
0x180034acf  mov     rcx, rsi; this
0x180034ad2  call    ?IsInterfaceOperational@NsiNotifications@@YA_NAEBU_NDIS_NSI_INTERFACE_ENUM_ROD@@@Z; NsiNotifications::IsInterfaceOperational(_NDIS_NSI_INTERFACE_ENUM_ROD const &)
0x180034ad7  movzx   eax, al
0x180034ada  lea     rcx, off_18004C840
0x180034ae1  mov     [rbp+50h+var_A8], eax
0x180034ae4  mov     [rbp+50h+var_C0], rcx
0x180034ae8  movaps  xmm0, [rbp+50h+var_60]
0x180034aec  lea     rax, [rbp+50h+var_C0]
0x180034af0  lea     rcx, [rbp+50h+var_C0]
0x180034af4  mov     [rbp+50h+var_88], rax
0x180034af8  movdqu  [rbp+50h+var_B8], xmm0
0x180034afd  call    ?SubmitOrderedWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitOrderedWork(std::function<void (void)> &&)
0x180034b02  lea     rcx, [rbp+50h+var_C0]
0x180034b06  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180034b0b  jmp     loc_180034CAB
0x180034b10  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180034b15  mov     rcx, [rax+8]
0x180034b19  mov     eax, [rcx]
0x180034b1b  cmp     eax, 5
0x180034b1e  jbe     short loc_180034B4F
0x180034b20  lea     rax, [rbp+50h+var_60]
0x180034b24  mov     [rsp+150h+var_D8], rax
0x180034b29  lea     rdx, byte_1800590A1
0x180034b30  mov     rax, [r14]
0x180034b33  mov     [rbp+50h+var_C8], rax
0x180034b37  lea     rax, [rsp+150h+var_D8]
0x180034b3c  mov     [rsp+150h+var_128], rax
0x180034b41  lea     rax, [rbp+50h+var_C8]
0x180034b45  mov     qword ptr [rsp+150h+bIgnoreCase], rax
0x180034b4a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x180034b4f  lea     rax, off_18004C7B0
0x180034b56  mov     [rbp+50h+var_C0], rax
0x180034b5a  jmp     short loc_180034AE8
0x180034b5c  xor     bl, bl
0x180034b5e  test    rsi, rsi
0x180034b61  jz      short loc_180034B6D
0x180034b63  mov     rcx, rsi; this
0x180034b66  call    ?IsInterfaceOperational@NsiNotifications@@YA_NAEBU_NDIS_NSI_INTERFACE_ENUM_ROD@@@Z; NsiNotifications::IsInterfaceOperational(_NDIS_NSI_INTERFACE_ENUM_ROD const &)
0x180034b6b  mov     bl, al
0x180034b6d  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180034b72  mov     r8, [rax+8]
0x180034b76  mov     ecx, [r8]
0x180034b79  cmp     ecx, 5
0x180034b7c  jbe     short loc_180034BBE
0x180034b7e  lea     rax, [rbp+50h+var_60]
0x180034b82  mov     byte ptr [rsp+150h+var_E0], bl
0x180034b86  mov     [rsp+150h+var_D8], rax
0x180034b8b  lea     rdx, byte_1800590F3
0x180034b92  mov     rax, [r14]
0x180034b95  mov     rcx, r8
0x180034b98  mov     [rbp+50h+var_C8], rax
0x180034b9c  lea     rax, [rsp+150h+var_E0]
0x180034ba1  mov     [rsp+150h+var_120], rax
0x180034ba6  lea     rax, [rsp+150h+var_D8]
0x180034bab  mov     [rsp+150h+var_128], rax
0x180034bb0  lea     rax, [rbp+50h+var_C8]
0x180034bb4  mov     qword ptr [rsp+150h+bIgnoreCase], rax
0x180034bb9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)
0x180034bbe  lea     rax, off_18004C780
0x180034bc5  mov     byte ptr [rbp+50h+var_A8], bl
0x180034bc8  mov     [rbp+50h+var_C0], rax
0x180034bcc  movzx   eax, [rbp+50h+var_4F]
0x180034bd0  mov     word ptr [rbp+50h+var_A8+1], ax
0x180034bd4  mov     al, [rbp+50h+var_4D]
0x180034bd7  mov     byte ptr [rbp+50h+var_A8+3], al
0x180034bda  jmp     loc_180034AE8
0x180034bdf  lea     r15, [r9+6]
0x180034be3  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180034be8  mov     r8, [rax+8]
0x180034bec  mov     eax, [r8]
0x180034bef  cmp     eax, 5
0x180034bf2  jbe     loc_180034CAB
0x180034bf8  mov     eax, [rdi+230h]
0x180034bfe  lea     rdx, word_18005915E
0x180034c05  mov     ecx, [rdi+22Ch]
0x180034c0b  cmp     byte ptr [rdi+228h], 0
0x180034c12  mov     dword ptr [rbp+50h+var_D0], eax
0x180034c15  mov     eax, [rdi+234h]
0x180034c1b  setnz   byte ptr [rsp+150h+var_E0]
0x180034c20  mov     dword ptr [rbp+50h+var_C8], eax
0x180034c23  mov     al, cl
0x180034c25  and     al, 1
0x180034c27  shr     ecx, 1
0x180034c29  mov     byte ptr [rsp+150h+var_E0+1], al
0x180034c2d  and     cl, 1
0x180034c30  lea     rax, [rdi+218h]
0x180034c37  mov     byte ptr [rsp+150h+var_E0+2], cl
0x180034c3b  mov     [rbp+50h+var_78], rax
0x180034c3f  mov     rcx, r8; int
0x180034c42  mov     rax, [r14]
0x180034c45  mov     [rbp+50h+var_70], rax
0x180034c49  lea     rax, [rbp+50h+var_D0]
0x180034c4d  mov     [rsp+150h+var_F0], rax; __int64
0x180034c52  lea     rax, [rbp+50h+var_C8]
0x180034c56  mov     [rsp+150h+var_F8], rax; __int64
0x180034c5b  lea     rax, [rsp+150h+var_E0]
0x180034c60  mov     [rsp+150h+var_100], rax; __int64
0x180034c65  lea     rax, [rsp+150h+var_E0+1]
0x180034c6a  mov     [rsp+150h+var_108], rax; __int64
0x180034c6f  lea     rax, [rsp+150h+var_E0+2]
0x180034c74  mov     [rsp+150h+var_110], rax; __int64
0x180034c79  lea     rax, [rbp+50h+var_80]
0x180034c7d  mov     [rsp+150h+var_118], rax; __int64
0x180034c82  lea     rax, [rbp+50h+var_78]
0x180034c86  mov     [rsp+150h+var_120], rax; __int64
0x180034c8b  lea     rax, [rsp+150h+var_D8]
0x180034c90  mov     [rsp+150h+var_128], rax; __int64
0x180034c95  lea     rax, [rbp+50h+var_70]
0x180034c99  mov     qword ptr [rsp+150h+bIgnoreCase], rax; __int64
0x180034c9e  mov     [rbp+50h+var_80], r15
0x180034ca2  mov     dword ptr [rsp+150h+var_D8], ebx
0x180034ca6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$00@@U5@U5@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$00@@7744@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180034cab  mov     rcx, [rbp+50h+var_40]
0x180034caf  xor     rcx, rsp; StackCookie
0x180034cb2  call    __security_check_cookie
0x180034cb7  add     rsp, 128h
0x180034cbe  pop     r15
0x180034cc0  pop     r14
0x180034cc2  pop     rdi
0x180034cc3  pop     rsi
0x180034cc4  pop     rbx
0x180034cc5  pop     rbp
0x180034cc6  retn
```
