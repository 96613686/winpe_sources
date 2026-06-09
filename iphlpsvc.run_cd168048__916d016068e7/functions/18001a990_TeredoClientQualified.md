# TeredoClientQualified

- ea: `0x18001a990`
- end: `0x18001b1a7`
- name: `TeredoClientQualified`
- size: `2071`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005500`
- `0x180009200`
- `0x18001a420`

## callees

- `0x180007f34`
- `0x18000a6f4`
- `0x18000d7b0`
- `0x1800159c4`
- `0x180015a6c`
- `0x1800163d4`
- `0x180016ab0`
- `0x1800190e0`
- `0x18001a990`
- `0x18001b1b0`
- `0x18002a0ec`
- `0x18002b6dc`
- `0x18002b980`
- `0x18002ecac`
- `0x180035b1c`
- `0x180039acc`
- `0x18003b008`
- `0x18003bb54`
- `0x180041020`
- `0x1800426d0`
- `0x18004b630`
- `0x18004d2f8`
- `0x1800502b4`
- `0x18005b8b8`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001af72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001af72`
- `IPHLPAPI!InternalSetTeredoPort` at `0x18001ad8f`
- `IPHLPAPI!InternalSetTeredoPort` at `0x18001ad8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aa95`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aa95`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ab5c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ab5c`
- `WS2_32!__imp_ntohs` at `0x18001ad80`
- `WS2_32!__imp_ntohs` at `0x18001b089`
- `WS2_32!__imp_ntohs` at `0x18001b0d1`
- `WS2_32!__imp_ntohs` at `0x18001ad80`
- `WS2_32!__imp_ntohs` at `0x18001b089`
- `WS2_32!__imp_ntohs` at `0x18001b0d1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18001aafc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18001aafc`
- `ext-ms-win-networking-iphlpsvc-l1-1-0!IphlpsvcExtConfigureTeredoClientPort` at `0x18001b0b6`
- `ext-ms-win-networking-iphlpsvc-l1-1-0!IphlpsvcExtConfigureTeredoClientPort` at `0x18001b0b6`

## string_xrefs

- `0x18001abb3`: `Teredo Qualification completed successfully!`
- `0x18001ae4b`: `onecoreuap\net\netio\iphlpsvc\service\client.c`

## pseudocode

```c
__int64 __fastcall TeredoClientQualified(unsigned int *a1, __int64 a2, __int64 a3)
{
  _DWORD *v5; // r13
  unsigned int v6; // ebp
  unsigned int v7; // r12d
  int v8; // r14d
  __int64 v9; // r8
  char v10; // bp
  unsigned __int8 v11; // r12
  __int64 v12; // rcx
  signed __int64 v13; // rdx
  signed __int64 v14; // r9
  unsigned int v15; // edi
  DWORD v16; // r15d
  struct _TP_TIMER *v17; // rdi
  int v19; // ebp
  const wchar_t *v20; // r8
  __int64 v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // r8
  __int64 v24; // r14
  __int64 MaximumPreviousState; // rdi
  unsigned int started; // edi
  u_short v27; // ax
  __int64 v28; // rcx
  unsigned int v29; // ecx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  unsigned int v35; // eax
  u_short v36; // ax
  u_short v37; // ax
  const wchar_t *v38; // rax
  const wchar_t *v39; // r8
  __int64 v40; // [rsp+20h] [rbp-98h]
  __int64 v41; // [rsp+20h] [rbp-98h]
  __int64 v42; // [rsp+20h] [rbp-98h]
  __int64 v43; // [rsp+20h] [rbp-98h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v45[16]; // [rsp+58h] [rbp-60h] BYREF
  const wchar_t *v46; // [rsp+68h] [rbp-50h]
  __int64 v47; // [rsp+70h] [rbp-48h]

  v5 = (_DWORD *)*((_QWORD *)a1 + 988);
  v6 = ~*(_DWORD *)(a2 + 12);
  v7 = a1[2185];
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x100) != 0 )
  {
    v47 = 48;
    v46 = L"Teredo client qualified";
    McGenEventWrite_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED,
      a3,
      2,
      v45);
  }
  LODWORD(v40) = BYTE2(v6);
  EventWrite0(
    0x100000,
    L"Teredo client has qualified: Mapped-address is %d.%d.%d.%d, source address is %d.%d.%d.%d.",
    (unsigned __int8)v6,
    BYTE1(v6),
    v40,
    HIBYTE(v6),
    *((unsigned __int8 *)a1 + 7808),
    *((unsigned __int8 *)a1 + 7809),
    *((unsigned __int8 *)a1 + 7810),
    *((unsigned __int8 *)a1 + 7811));
  if ( *(_QWORD *)(a2 + 8) == *((_QWORD *)a1 + 1092) && *(_QWORD *)a2 == *((_QWORD *)a1 + 1091) )
  {
    v8 = 0;
  }
  else
  {
    if ( a1[2146] == 5 )
    {
      EventWrite0(0x100000, L"Restarting Teredo as the mappings have changed.");
      TeredoTraceAddress(L"Old Teredo Address", a1 + 2182);
      TeredoTraceAddress(L"New Teredo Address", a2);
      return TeredoClientProcessMappingChange(a1);
    }
    a1[2147] = (v6 == ~v7) + 4;
    EventWrite0(0x100000, L"Teredo client NAT state %u");
    v8 = 1;
  }
  v9 = a1[2146];
  v10 = 0;
  v11 = 0;
  if ( (_DWORD)v9 == 5 )
    goto LABEL_6;
  v19 = 5;
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
    McTemplateU0qq_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_STATE_CHANGE,
      v9,
      5);
  v20 = L"Relay";
  if ( *(_DWORD *)(*((_QWORD *)a1 + 988) + 2864LL) != 1 )
    v20 = L"Client";
  LODWORD(v41) = a1[2171];
  EventWrite0(0x100000, L"Current status: %ws Mode, Firewall enabled %d, Listening Apps %u", v20, a1[2172], v41);
  v21 = *((_QWORD *)a1 + 1052);
  a1[2146] = 5;
  v22 = TeredoEnableTunnelOffload(v21);
  if ( v22 )
    EventWriteError0(0x100000, L"Error %d when enabling teredo offload.", v22);
  v23 = a1[3599];
  if ( (int)v23 >= 7 )
  {
    v11 = 1;
    EventWrite0(0x100000, L"Changing Teredo client previous NAT state from %u to %u", v23, a1[2147]);
    a1[3599] = a1[2147];
  }
  else
  {
    a1[2147] = v23;
  }
  v24 = *((_QWORD *)a1 + 988);
  SystemTimeAsFileTime = (struct _FILETIME)-1LL;
  MaximumPreviousState = (unsigned int)TeredoGetMaximumPreviousState();
  EventWrite0(0x100000, L"Max previous state entries: %d", MaximumPreviousState);
  if ( (_DWORD)MaximumPreviousState )
  {
    if ( (unsigned int)TeredoCreateGatewayKey((PHKEY)&SystemTimeAsFileTime, 0) )
    {
      if ( (unsigned int)TeredoCheckIfNewEntryIsPossible((unsigned int)MaximumPreviousState) )
      {
        SystemTimeAsFileTime = (struct _FILETIME)-1LL;
        TeredoSetPreviousTeredoAddress(v24, -1, v11);
      }
    }
    else
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))TeredoSetPreviousTeredoAddress)(v24, SystemTimeAsFileTime, v11);
      RegCloseKey(*(HKEY *)&SystemTimeAsFileTime);
    }
  }
  LODWORD(v43) = v5[4832];
  EventWrite0(
    0x100000,
    L"TeredoResetBackOffStatemachine: old values are: In-Action: %u, Reset: %u, Failures: %u",
    (unsigned int)v5[4833],
    (unsigned int)v5[4834],
    v43);
  v5[4834] = 1;
  v5[4833] = 0;
  v5[4832] = 0;
  if ( !*((_BYTE *)a1 + 14392) )
  {
    v35 = TeredoSetMediaStateToConnected(*((_QWORD *)a1 + 1052));
    started = v35;
    if ( v35 )
    {
      EventWriteError0(0x100000, L"Error %d when setting media status to MediaConnected.", v35);
      goto LABEL_48;
    }
    *((_BYTE *)a1 + 14392) = 1;
  }
  started = TeredoClientStartTypeSpecificBehavior(a1);
  if ( started )
  {
    EventWriteError0(0x100000, L"Unable to enable weak host behavior");
    v19 = 14;
LABEL_48:
    v5[717] = v19;
    v5[719] = started;
    return TeredoStopClient(a1, v33, v34);
  }
  TeredoInitializeClientPortMappings(a1);
  v8 = 1;
  TeredoClientUpdateStateInNsi(a1);
  v27 = ntohs(*((_WORD *)a1 + 3903));
  if ( (unsigned int)InternalSetTeredoPort(v27) )
  {
    v36 = ntohs(*((_WORD *)a1 + 3903));
    EventWriteError0(0x100000, L"Unable to set Teredo port value (%d) in NSI", v36);
  }
  if ( (unsigned __int8)IsIphlpsvcExtConfigureTeredoClientPortPresent()
    && (unsigned int)IphlpsvcExtConfigureTeredoClientPort(*((unsigned __int16 *)a1 + 3903)) )
  {
    v37 = ntohs(*((_WORD *)a1 + 3903));
    EventWriteError0(0x100000, L"Unable to set Teredo port value (%d) in Xbox Virtual NIC", v37);
  }
  TeredoTraceAddress(L"Acquired Teredo address:", a1 + 2182);
  v10 = 1;
LABEL_6:
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v12 = *((_QWORD *)a1 + 1374);
  v13 = *(unsigned __int64 *)&SystemTimeAsFileTime / 0x989680;
  if ( v12 >= *((_QWORD *)a1 + 1375) )
    v12 = *((_QWORD *)a1 + 1375);
  v14 = v12 + a1[2200];
  if ( v13 >= v14 )
  {
    v38 = L"==";
    if ( v13 != v14 )
      v38 = L">";
    v39 = L"equal to";
    if ( v13 != v14 )
      v39 = L"greater than";
    v16 = 1000;
    EventWrite0(
      0x100000,
      L"Current time is %s client mapping expiration! %lld %s %lld",
      v39,
      *(unsigned __int64 *)&SystemTimeAsFileTime / 0x989680,
      v38,
      v12 + a1[2200]);
  }
  else
  {
    SystemTimeAsFileTime.dwLowDateTime = 0;
    v15 = 1000 * (v14 - v13);
    CryptGenRandom(hProv, 4u, (BYTE *)&SystemTimeAsFileTime);
    v16 = SystemTimeAsFileTime.dwLowDateTime % (v15 >> 2) + ((3 * v15) >> 2);
  }
  EventWrite0(0x100000, L"Qualified Timer interval is %d milliseconds", v16);
  v17 = *(struct _TP_TIMER **)(*((_QWORD *)a1 + 1369) + 16LL);
  SystemTimeAsFileTime = (struct _FILETIME)(-10000LL * v16);
  SetThreadpoolTimer(v17, &SystemTimeAsFileTime, 0, 0);
  LODWORD(v41) = 0;
  EventWrite0(
    0x8000000,
    L"%s has been set to: timeout = %d ms, period = %d ms, timer memory pointer = %p",
    L"Teredo Client Timer",
    v16,
    v41,
    v17);
  if ( v10 )
    TeredoClientProcessQueuedPackets(a1);
  if ( v8 || _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 2888, 0xFFFFFFFF) == 1 )
  {
    if ( _InterlockedExchange((volatile __int32 *)a1 + 3031, 1) )
    {
      a1[2888] = 1;
    }
    else
    {
      v28 = *((_QWORD *)a1 + 1798);
      a1[2888] = 10;
      if ( v28 == *((_QWORD *)a1 + 1099) )
      {
        a1[3031] = 0;
      }
      else
      {
        LODWORD(v42) = 4833;
        EventWrite0(
          0x100000,
          L"TeredoReferenceClient: ++%d @ %ls:%u",
          *a1,
          L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
          v42);
        v29 = *a1;
        v30 = 5LL * (_InterlockedExchangeAdd((volatile signed __int32 *)a1 + 2, 1u) & 0x3F);
        a1[2 * v30 + 4] = v29;
        a1[2 * v30 + 12] = 0;
        *(_QWORD *)&a1[2 * v30 + 10] = 0;
        a1[2 * v30 + 8] = 4833;
        *(_QWORD *)&a1[2 * v30 + 6] = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c";
        _InterlockedIncrement((volatile signed __int32 *)a1);
        *(_OWORD *)(a1 + 3022) = *(_OWORD *)(a1 + 2182);
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(
            MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
            EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_SEND_PACKET,
            6);
        if ( (unsigned __int8)RoReferenceEx(a1 + 2044) )
        {
          v31 = (*((__int64 (__fastcall **)(unsigned int *, unsigned int *))a1 + 1016))(a1 + 2014, a1 + 2892);
          if ( v31 )
            (*((void (__fastcall **)(unsigned int *, __int64))a1 + 1017))(a1 + 2014, v31);
        }
        else
        {
          (*((void (__fastcall **)(unsigned int *))a1 + 1450))(a1 + 2892);
        }
        v32 = *((_QWORD *)a1 + 1099);
        ++a1[2154];
        *((_QWORD *)a1 + 1798) = v32;
      }
    }
  }
  EventWrite0(0x100000, L"Teredo Qualification completed successfully!");
  if ( v10 )
    TeredoTelemetryWriteSuccessfulQualification(a1, v11);
  return TeredoRecordInterfaceConnectivity(a1);
}

```

## disassembly

```asm
0x18001a990  mov     [rsp+arg_10], rbx
0x18001a995  push    rbp
0x18001a996  push    rsi
0x18001a997  push    rdi
0x18001a998  push    r12
0x18001a99a  push    r13
0x18001a99c  push    r14
0x18001a99e  push    r15
0x18001a9a0  sub     rsp, 80h
0x18001a9a7  mov     rax, cs:__security_cookie
0x18001a9ae  xor     rax, rsp
0x18001a9b1  mov     [rsp+0B8h+var_40], rax
0x18001a9b6  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18001a9bd  mov     r14, rdx
0x18001a9c0  mov     ebp, [rdx+0Ch]
0x18001a9c3  mov     rbx, rcx
0x18001a9c6  mov     r13, [rcx+1EE0h]
0x18001a9cd  not     ebp
0x18001a9cf  mov     r12d, [rcx+2224h]
0x18001a9d6  jnz     loc_18001ABFE
0x18001a9dc  movzx   edx, byte ptr [rbx+1E80h]
0x18001a9e3  mov     eax, ebp
0x18001a9e5  movzx   r11d, byte ptr [rbx+1E83h]
0x18001a9ed  mov     r10d, ebp
0x18001a9f0  movzx   edi, byte ptr [rbx+1E82h]
0x18001a9f7  movzx   esi, byte ptr [rbx+1E81h]
0x18001a9fe  mov     [rsp+0B8h+var_70], r11d
0x18001aa03  shr     eax, 10h
0x18001aa06  movzx   ecx, al
0x18001aa09  mov     eax, ebp
0x18001aa0b  mov     [rsp+0B8h+var_78], edi
0x18001aa0f  mov     [rsp+0B8h+var_80], esi
0x18001aa13  mov     [rsp+0B8h+var_88], edx
0x18001aa17  lea     rdx, aTeredoClientHa; "Teredo client has qualified: Mapped-add"...
0x18001aa1e  shr     r10d, 18h
0x18001aa22  shr     eax, 8
0x18001aa25  mov     dword ptr [rsp+0B8h+var_90], r10d
0x18001aa2a  mov     dword ptr [rsp+0B8h+var_98], ecx
0x18001aa2e  mov     ecx, 100000h
0x18001aa33  movzx   r9d, al
0x18001aa37  movzx   r8d, bpl
0x18001aa3b  call    EventWrite0
0x18001aa40  mov     rax, [rbx+2220h]
0x18001aa47  cmp     [r14+8], rax
0x18001aa4b  jnz     loc_18001ADCC
0x18001aa51  mov     rax, [rbx+2218h]
0x18001aa58  cmp     [r14], rax
0x18001aa5b  jnz     loc_18001ADCC
0x18001aa61  xor     r14d, r14d
0x18001aa64  mov     r8d, [rbx+2188h]
0x18001aa6b  xor     bpl, bpl
0x18001aa6e  xor     r12b, r12b
0x18001aa71  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001aa78  cmp     r8d, 5
0x18001aa7c  jnz     loc_18001AC48
0x18001aa82  mov     r13d, 1
0x18001aa88  xor     r15d, r15d
0x18001aa8b  lea     rcx, [rsp+0B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001aa90  mov     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18001aa95  call    cs:__imp_GetSystemTimeAsFileTime
0x18001aa9c  nop     dword ptr [rax+rax+00h]
0x18001aaa1  mov     rcx, [rbx+2AF0h]
0x18001aaa8  mov     rax, 0D6BF94D5E57A42BDh
0x18001aab2  mul     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x18001aab7  mov     rax, [rbx+2AF8h]
0x18001aabe  mov     r9d, [rbx+2260h]
0x18001aac5  shr     rdx, 17h
0x18001aac9  cmp     rcx, rax
0x18001aacc  cmovge  rcx, rax
0x18001aad0  add     r9, rcx
0x18001aad3  cmp     rdx, r9
0x18001aad6  jge     loc_18001B0F7
0x18001aadc  mov     rcx, cs:hProv; hProv
0x18001aae3  lea     r8, [rsp+0B8h+SystemTimeAsFileTime]; pbBuffer
0x18001aae8  sub     r9d, edx
0x18001aaeb  mov     [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x18001aaf0  mov     edx, 4; dwLen
0x18001aaf5  imul    edi, r9d, 3E8h
0x18001aafc  call    cs:__imp_CryptGenRandom
0x18001ab03  nop     dword ptr [rax+rax+00h]
0x18001ab08  mov     eax, [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x18001ab0c  lea     r15d, [rdi+rdi*2]
0x18001ab10  xor     edx, edx
0x18001ab12  shr     r15d, 2
0x18001ab16  mov     ecx, edi
0x18001ab18  shr     ecx, 2
0x18001ab1b  div     ecx
0x18001ab1d  add     r15d, edx
0x18001ab20  mov     r8d, r15d
0x18001ab23  lea     rdx, aQualifiedTimer; "Qualified Timer interval is %d millisec"...
0x18001ab2a  mov     ecx, 100000h
0x18001ab2f  call    EventWrite0
0x18001ab34  mov     rax, [rbx+2AC8h]
0x18001ab3b  lea     rdx, [rsp+0B8h+SystemTimeAsFileTime]; pftDueTime
0x18001ab40  xor     r9d, r9d; msWindowLength
0x18001ab43  xor     r8d, r8d; msPeriod
0x18001ab46  mov     rdi, [rax+10h]
0x18001ab4a  mov     eax, r15d
0x18001ab4d  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18001ab54  mov     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18001ab59  mov     rcx, rdi; pti
0x18001ab5c  call    cs:__imp_SetThreadpoolTimer
0x18001ab63  nop     dword ptr [rax+rax+00h]
0x18001ab68  mov     r9d, r15d
0x18001ab6b  mov     [rsp+0B8h+var_90], rdi
0x18001ab70  lea     r8, aTeredoClientTi_1; "Teredo Client Timer"
0x18001ab77  mov     dword ptr [rsp+0B8h+var_98], 0
0x18001ab7f  lea     rdx, aSHasBeenSetToT; "%s has been set to: timeout = %d ms, pe"...
0x18001ab86  mov     ecx, 8000000h
0x18001ab8b  call    EventWrite0
0x18001ab90  test    bpl, bpl
0x18001ab93  jnz     loc_18001B144
0x18001ab99  test    r14d, r14d
0x18001ab9c  jnz     loc_18001AE19
0x18001aba2  lock xadd [rbx+2D20h], esi
0x18001abaa  cmp     esi, 1
0x18001abad  jz      loc_18001AE19
0x18001abb3  lea     rdx, aTeredoQualific; "Teredo Qualification completed successf"...
0x18001abba  mov     ecx, 100000h
0x18001abbf  call    EventWrite0
0x18001abc4  test    bpl, bpl
0x18001abc7  jnz     loc_18001B196
0x18001abcd  mov     rcx, rbx
0x18001abd0  call    TeredoRecordInterfaceConnectivity
0x18001abd5  mov     rcx, [rsp+0B8h+var_40]
0x18001abda  xor     rcx, rsp; StackCookie
0x18001abdd  call    __security_check_cookie
0x18001abe2  mov     rbx, [rsp+0B8h+arg_10]
0x18001abea  add     rsp, 80h
0x18001abf1  pop     r15
0x18001abf3  pop     r14
0x18001abf5  pop     r13
0x18001abf7  pop     r12
0x18001abf9  pop     rdi
0x18001abfa  pop     rsi
0x18001abfb  pop     rbp
0x18001abfc  retn
0x18001abfe  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 1
0x18001ac05  jz      loc_18001A9DC
0x18001ac0b  lea     rax, aTeredoClientQu; "Teredo client qualified"
0x18001ac12  mov     [rsp+0B8h+var_48], 30h ; '0'
0x18001ac1b  mov     [rsp+0B8h+var_50], rax
0x18001ac20  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED
0x18001ac27  lea     rax, [rsp+0B8h+var_60]
0x18001ac2c  mov     r9d, 2
0x18001ac32  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18001ac39  mov     [rsp+0B8h+var_98], rax
0x18001ac3e  call    McGenEventWrite_EventWriteTransfer
0x18001ac43  jmp     loc_18001A9DC
0x18001ac48  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001ac4f  mov     ebp, 5
0x18001ac54  jnz     loc_18001AFEF
0x18001ac5a  mov     rax, [rbx+1EE0h]
0x18001ac61  lea     rcx, aClient; "Client"
0x18001ac68  mov     r9d, [rbx+21F0h]
0x18001ac6f  lea     r8, aRelay; "Relay"
0x18001ac76  lea     rdx, aCurrentStatusW; "Current status: %ws Mode, Firewall enab"...
0x18001ac7d  cmp     dword ptr [rax+0B30h], 1
0x18001ac84  mov     eax, [rbx+21ECh]
0x18001ac8a  cmovnz  r8, rcx
0x18001ac8e  mov     dword ptr [rsp+0B8h+var_98], eax
0x18001ac92  mov     ecx, 100000h
0x18001ac97  call    EventWrite0
0x18001ac9c  mov     rcx, [rbx+20E0h]
0x18001aca3  mov     [rbx+2188h], ebp
0x18001aca9  call    TeredoEnableTunnelOffload
0x18001acae  test    eax, eax
0x18001acb0  jnz     loc_18001B00A
0x18001acb6  mov     r8d, [rbx+383Ch]
0x18001acbd  cmp     r8d, 7
0x18001acc1  jge     loc_18001AF1C
0x18001acc7  mov     [rbx+218Ch], r8d
0x18001acce  mov     r14, [rbx+1EE0h]
0x18001acd5  mov     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18001acda  call    TeredoGetMaximumPreviousState
0x18001acdf  mov     r8d, eax
0x18001ace2  lea     rdx, aMaxPreviousSta; "Max previous state entries: %d"
0x18001ace9  mov     ecx, 100000h
0x18001acee  mov     edi, eax
0x18001acf0  call    EventWrite0
0x18001acf5  test    edi, edi
0x18001acf7  jnz     loc_18001AF48
0x18001acfd  mov     eax, [r13+4B80h]
0x18001ad04  lea     rdx, aTeredoresetbac; "TeredoResetBackOffStatemachine: old val"...
0x18001ad0b  mov     r9d, [r13+4B88h]
0x18001ad12  mov     ecx, 100000h
0x18001ad17  mov     r8d, [r13+4B84h]
0x18001ad1e  mov     dword ptr [rsp+0B8h+var_98], eax
0x18001ad22  call    EventWrite0
0x18001ad27  xor     eax, eax
0x18001ad29  mov     dword ptr [r13+4B88h], 1
0x18001ad34  mov     [r13+4B84h], eax
0x18001ad3b  mov     [r13+4B80h], eax
0x18001ad42  cmp     [rbx+3838h], al
0x18001ad48  jz      loc_18001B04B
0x18001ad4e  mov     rcx, rbx
0x18001ad51  call    TeredoClientStartTypeSpecificBehavior
0x18001ad56  mov     edi, eax
0x18001ad58  test    eax, eax
0x18001ad5a  jnz     loc_18001AF83
0x18001ad60  mov     rcx, rbx
0x18001ad63  call    TeredoInitializeClientPortMappings
0x18001ad68  mov     r13d, 1
0x18001ad6e  mov     rcx, rbx
0x18001ad71  mov     r14d, r13d
0x18001ad74  call    TeredoClientUpdateStateInNsi
0x18001ad79  movzx   ecx, word ptr [rbx+1E7Eh]; netshort
0x18001ad80  call    cs:__imp_ntohs
0x18001ad87  nop     dword ptr [rax+rax+00h]
0x18001ad8c  movzx   ecx, ax
0x18001ad8f  call    cs:__imp_InternalSetTeredoPort
0x18001ad96  nop     dword ptr [rax+rax+00h]
0x18001ad9b  test    eax, eax
0x18001ad9d  jnz     loc_18001B082
0x18001ada3  call    IsIphlpsvcExtConfigureTeredoClientPortPresent
0x18001ada8  test    al, al
0x18001adaa  jnz     loc_18001B0AF
0x18001adb0  lea     rdx, [rbx+2218h]
0x18001adb7  lea     rcx, aAcquiredTeredo; "Acquired Teredo address:"
0x18001adbe  call    TeredoTraceAddress
0x18001adc3  movzx   ebp, r13b
0x18001adc7  jmp     loc_18001AA88
0x18001adcc  cmp     dword ptr [rbx+2188h], 5
0x18001add3  mov     ecx, 100000h
0x18001add8  jnz     loc_18001AFC0
0x18001adde  lea     rdx, aRestartingTere; "Restarting Teredo as the mappings have "...
0x18001ade5  call    EventWrite0
0x18001adea  lea     rdx, [rbx+2218h]
0x18001adf1  lea     rcx, aOldTeredoAddre; "Old Teredo Address"
0x18001adf8  call    TeredoTraceAddress
0x18001adfd  mov     rdx, r14
0x18001ae00  lea     rcx, aNewTeredoAddre_0; "New Teredo Address"
0x18001ae07  call    TeredoTraceAddress
0x18001ae0c  mov     rcx, rbx
0x18001ae0f  call    TeredoClientProcessMappingChange
0x18001ae14  jmp     loc_18001ABD5
0x18001ae19  mov     eax, r13d
0x18001ae1c  xchg    eax, [rbx+2F5Ch]
0x18001ae22  test    eax, eax
0x18001ae24  jnz     loc_18001AFB4
0x18001ae2a  mov     rcx, [rbx+3830h]
0x18001ae31  mov     dword ptr [rbx+2D20h], 0Ah
0x18001ae3b  cmp     rcx, [rbx+2258h]
0x18001ae42  jz      loc_18001B151
0x18001ae48  mov     r8d, [rbx]
0x18001ae4b  lea     rdi, aOnecoreuapNetN_27; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18001ae52  mov     r9, rdi
0x18001ae55  mov     dword ptr [rsp+0B8h+var_98], 12E1h
0x18001ae5d  lea     rdx, aTeredoreferenc_0; "TeredoReferenceClient: ++%d @ %ls:%u"
0x18001ae64  mov     ecx, 100000h
0x18001ae69  call    EventWrite0
0x18001ae6e  mov     ecx, [rbx]
0x18001ae70  lock xadd [rbx+8], r13d
0x18001ae76  mov     eax, r13d
0x18001ae79  and     eax, 3Fh
0x18001ae7c  lea     rax, [rax+rax*4]
0x18001ae80  mov     [rbx+rax*8+10h], ecx
0x18001ae84  xor     ecx, ecx
0x18001ae86  mov     [rbx+rax*8+30h], ecx
0x18001ae8a  mov     [rbx+rax*8+28h], rcx
0x18001ae8f  mov     dword ptr [rbx+rax*8+20h], 12E1h
0x18001ae97  mov     [rbx+rax*8+18h], rdi
0x18001ae9c  lock inc dword ptr [rbx]
0x18001ae9f  movups  xmm0, xmmword ptr [rbx+2218h]
0x18001aea6  movups  xmmword ptr [rbx+2F38h], xmm0
0x18001aead  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001aeb4  jnz     loc_18001B160
0x18001aeba  lea     rcx, [rbx+1FF0h]
0x18001aec1  call    RoReferenceEx
0x18001aec6  test    al, al
0x18001aec8  jz      loc_18001B17E
0x18001aece  mov     rax, [rbx+1FC0h]
0x18001aed5  lea     rdx, [rbx+2D30h]
0x18001aedc  lea     rcx, [rbx+1F78h]
0x18001aee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aee8  test    rax, rax
0x18001aeeb  jz      short loc_18001AF03
0x18001aeed  mov     rdx, rax
0x18001aef0  lea     rcx, [rbx+1F78h]
0x18001aef7  mov     rax, [rbx+1FC8h]
0x18001aefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af03  mov     rax, [rbx+2258h]
0x18001af0a  inc     dword ptr [rbx+21A8h]
0x18001af10  mov     [rbx+3830h], rax
0x18001af17  jmp     loc_18001ABB3
0x18001af1c  mov     r9d, [rbx+218Ch]
0x18001af23  lea     rdx, aChangingTeredo; "Changing Teredo client previous NAT sta"...
0x18001af2a  mov     ecx, 100000h
0x18001af2f  mov     r12b, 1
0x18001af32  call    EventWrite0
0x18001af37  mov     eax, [rbx+218Ch]
0x18001af3d  mov     [rbx+383Ch], eax
0x18001af43  jmp     loc_18001ACCE
0x18001af48  xor     edx, edx
0x18001af4a  lea     rcx, [rsp+0B8h+SystemTimeAsFileTime]; phkResult
0x18001af4f  call    TeredoCreateGatewayKey
0x18001af54  test    eax, eax
0x18001af56  jnz     loc_18001B023
0x18001af5c  mov     rdx, qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x18001af61  movzx   r8d, r12b
  ... truncated ...
```
