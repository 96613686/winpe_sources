# TeredoClientQualified

- ea: `0x18001a9a0`
- end: `0x18001b1b7`
- name: `TeredoClientQualified`
- size: `2071`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005510`
- `0x180009210`
- `0x18001a430`

## callees

- `0x180007f44`
- `0x18000a704`
- `0x18000d7c0`
- `0x1800159d4`
- `0x180015a7c`
- `0x1800163e4`
- `0x180016ac0`
- `0x1800190f0`
- `0x18001a9a0`
- `0x18001b1c0`
- `0x18002a0fc`
- `0x18002b6ec`
- `0x18002b990`
- `0x18002ecbc`
- `0x180035b2c`
- `0x180039adc`
- `0x18003b018`
- `0x18003bb64`
- `0x180040fe0`
- `0x180042690`
- `0x18004b5f0`
- `0x18004d2b8`
- `0x180050274`
- `0x18005b8d8`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001af82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001af82`
- `IPHLPAPI!InternalSetTeredoPort` at `0x18001ad9f`
- `IPHLPAPI!InternalSetTeredoPort` at `0x18001ad9f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aaa5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aaa5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ab6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ab6c`
- `WS2_32!__imp_ntohs` at `0x18001ad90`
- `WS2_32!__imp_ntohs` at `0x18001b099`
- `WS2_32!__imp_ntohs` at `0x18001b0e1`
- `WS2_32!__imp_ntohs` at `0x18001ad90`
- `WS2_32!__imp_ntohs` at `0x18001b099`
- `WS2_32!__imp_ntohs` at `0x18001b0e1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18001ab0c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18001ab0c`
- `ext-ms-win-networking-iphlpsvc-l1-1-0!IphlpsvcExtConfigureTeredoClientPort` at `0x18001b0c6`
- `ext-ms-win-networking-iphlpsvc-l1-1-0!IphlpsvcExtConfigureTeredoClientPort` at `0x18001b0c6`

## string_xrefs

- `0x18001abc3`: `Teredo Qualification completed successfully!`
- `0x18001ae5b`: `onecoreuap\net\netio\iphlpsvc\service\client.c`

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
0x18001a9a0  mov     [rsp+arg_10], rbx
0x18001a9a5  push    rbp
0x18001a9a6  push    rsi
0x18001a9a7  push    rdi
0x18001a9a8  push    r12
0x18001a9aa  push    r13
0x18001a9ac  push    r14
0x18001a9ae  push    r15
0x18001a9b0  sub     rsp, 80h
0x18001a9b7  mov     rax, cs:__security_cookie
0x18001a9be  xor     rax, rsp
0x18001a9c1  mov     [rsp+0B8h+var_40], rax
0x18001a9c6  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18001a9cd  mov     r14, rdx
0x18001a9d0  mov     ebp, [rdx+0Ch]
0x18001a9d3  mov     rbx, rcx
0x18001a9d6  mov     r13, [rcx+1EE0h]
0x18001a9dd  not     ebp
0x18001a9df  mov     r12d, [rcx+2224h]
0x18001a9e6  jnz     loc_18001AC0E
0x18001a9ec  movzx   edx, byte ptr [rbx+1E80h]
0x18001a9f3  mov     eax, ebp
0x18001a9f5  movzx   r11d, byte ptr [rbx+1E83h]
0x18001a9fd  mov     r10d, ebp
0x18001aa00  movzx   edi, byte ptr [rbx+1E82h]
0x18001aa07  movzx   esi, byte ptr [rbx+1E81h]
0x18001aa0e  mov     [rsp+0B8h+var_70], r11d
0x18001aa13  shr     eax, 10h
0x18001aa16  movzx   ecx, al
0x18001aa19  mov     eax, ebp
0x18001aa1b  mov     [rsp+0B8h+var_78], edi
0x18001aa1f  mov     [rsp+0B8h+var_80], esi
0x18001aa23  mov     [rsp+0B8h+var_88], edx
0x18001aa27  lea     rdx, aTeredoClientHa; "Teredo client has qualified: Mapped-add"...
0x18001aa2e  shr     r10d, 18h
0x18001aa32  shr     eax, 8
0x18001aa35  mov     dword ptr [rsp+0B8h+var_90], r10d
0x18001aa3a  mov     dword ptr [rsp+0B8h+var_98], ecx
0x18001aa3e  mov     ecx, 100000h
0x18001aa43  movzx   r9d, al
0x18001aa47  movzx   r8d, bpl
0x18001aa4b  call    EventWrite0
0x18001aa50  mov     rax, [rbx+2220h]
0x18001aa57  cmp     [r14+8], rax
0x18001aa5b  jnz     loc_18001ADDC
0x18001aa61  mov     rax, [rbx+2218h]
0x18001aa68  cmp     [r14], rax
0x18001aa6b  jnz     loc_18001ADDC
0x18001aa71  xor     r14d, r14d
0x18001aa74  mov     r8d, [rbx+2188h]
0x18001aa7b  xor     bpl, bpl
0x18001aa7e  xor     r12b, r12b
0x18001aa81  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001aa88  cmp     r8d, 5
0x18001aa8c  jnz     loc_18001AC58
0x18001aa92  mov     r13d, 1
0x18001aa98  xor     r15d, r15d
0x18001aa9b  lea     rcx, [rsp+0B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001aaa0  mov     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18001aaa5  call    cs:__imp_GetSystemTimeAsFileTime
0x18001aaac  nop     dword ptr [rax+rax+00h]
0x18001aab1  mov     rcx, [rbx+2AF0h]
0x18001aab8  mov     rax, 0D6BF94D5E57A42BDh
0x18001aac2  mul     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x18001aac7  mov     rax, [rbx+2AF8h]
0x18001aace  mov     r9d, [rbx+2260h]
0x18001aad5  shr     rdx, 17h
0x18001aad9  cmp     rcx, rax
0x18001aadc  cmovge  rcx, rax
0x18001aae0  add     r9, rcx
0x18001aae3  cmp     rdx, r9
0x18001aae6  jge     loc_18001B107
0x18001aaec  mov     rcx, cs:hProv; hProv
0x18001aaf3  lea     r8, [rsp+0B8h+SystemTimeAsFileTime]; pbBuffer
0x18001aaf8  sub     r9d, edx
0x18001aafb  mov     [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x18001ab00  mov     edx, 4; dwLen
0x18001ab05  imul    edi, r9d, 3E8h
0x18001ab0c  call    cs:__imp_CryptGenRandom
0x18001ab13  nop     dword ptr [rax+rax+00h]
0x18001ab18  mov     eax, [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x18001ab1c  lea     r15d, [rdi+rdi*2]
0x18001ab20  xor     edx, edx
0x18001ab22  shr     r15d, 2
0x18001ab26  mov     ecx, edi
0x18001ab28  shr     ecx, 2
0x18001ab2b  div     ecx
0x18001ab2d  add     r15d, edx
0x18001ab30  mov     r8d, r15d
0x18001ab33  lea     rdx, aQualifiedTimer; "Qualified Timer interval is %d millisec"...
0x18001ab3a  mov     ecx, 100000h
0x18001ab3f  call    EventWrite0
0x18001ab44  mov     rax, [rbx+2AC8h]
0x18001ab4b  lea     rdx, [rsp+0B8h+SystemTimeAsFileTime]; pftDueTime
0x18001ab50  xor     r9d, r9d; msWindowLength
0x18001ab53  xor     r8d, r8d; msPeriod
0x18001ab56  mov     rdi, [rax+10h]
0x18001ab5a  mov     eax, r15d
0x18001ab5d  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18001ab64  mov     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18001ab69  mov     rcx, rdi; pti
0x18001ab6c  call    cs:__imp_SetThreadpoolTimer
0x18001ab73  nop     dword ptr [rax+rax+00h]
0x18001ab78  mov     r9d, r15d
0x18001ab7b  mov     [rsp+0B8h+var_90], rdi
0x18001ab80  lea     r8, aTeredoClientTi_1; "Teredo Client Timer"
0x18001ab87  mov     dword ptr [rsp+0B8h+var_98], 0
0x18001ab8f  lea     rdx, aSHasBeenSetToT; "%s has been set to: timeout = %d ms, pe"...
0x18001ab96  mov     ecx, 8000000h
0x18001ab9b  call    EventWrite0
0x18001aba0  test    bpl, bpl
0x18001aba3  jnz     loc_18001B154
0x18001aba9  test    r14d, r14d
0x18001abac  jnz     loc_18001AE29
0x18001abb2  lock xadd [rbx+2D20h], esi
0x18001abba  cmp     esi, 1
0x18001abbd  jz      loc_18001AE29
0x18001abc3  lea     rdx, aTeredoQualific; "Teredo Qualification completed successf"...
0x18001abca  mov     ecx, 100000h
0x18001abcf  call    EventWrite0
0x18001abd4  test    bpl, bpl
0x18001abd7  jnz     loc_18001B1A6
0x18001abdd  mov     rcx, rbx
0x18001abe0  call    TeredoRecordInterfaceConnectivity
0x18001abe5  mov     rcx, [rsp+0B8h+var_40]
0x18001abea  xor     rcx, rsp; StackCookie
0x18001abed  call    __security_check_cookie
0x18001abf2  mov     rbx, [rsp+0B8h+arg_10]
0x18001abfa  add     rsp, 80h
0x18001ac01  pop     r15
0x18001ac03  pop     r14
0x18001ac05  pop     r13
0x18001ac07  pop     r12
0x18001ac09  pop     rdi
0x18001ac0a  pop     rsi
0x18001ac0b  pop     rbp
0x18001ac0c  retn
0x18001ac0e  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 1
0x18001ac15  jz      loc_18001A9EC
0x18001ac1b  lea     rax, aTeredoClientQu; "Teredo client qualified"
0x18001ac22  mov     [rsp+0B8h+var_48], 30h ; '0'
0x18001ac2b  mov     [rsp+0B8h+var_50], rax
0x18001ac30  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED
0x18001ac37  lea     rax, [rsp+0B8h+var_60]
0x18001ac3c  mov     r9d, 2
0x18001ac42  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18001ac49  mov     [rsp+0B8h+var_98], rax
0x18001ac4e  call    McGenEventWrite_EventWriteTransfer
0x18001ac53  jmp     loc_18001A9EC
0x18001ac58  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001ac5f  mov     ebp, 5
0x18001ac64  jnz     loc_18001AFFF
0x18001ac6a  mov     rax, [rbx+1EE0h]
0x18001ac71  lea     rcx, aClient; "Client"
0x18001ac78  mov     r9d, [rbx+21F0h]
0x18001ac7f  lea     r8, aRelay; "Relay"
0x18001ac86  lea     rdx, aCurrentStatusW; "Current status: %ws Mode, Firewall enab"...
0x18001ac8d  cmp     dword ptr [rax+0B30h], 1
0x18001ac94  mov     eax, [rbx+21ECh]
0x18001ac9a  cmovnz  r8, rcx
0x18001ac9e  mov     dword ptr [rsp+0B8h+var_98], eax
0x18001aca2  mov     ecx, 100000h
0x18001aca7  call    EventWrite0
0x18001acac  mov     rcx, [rbx+20E0h]
0x18001acb3  mov     [rbx+2188h], ebp
0x18001acb9  call    TeredoEnableTunnelOffload
0x18001acbe  test    eax, eax
0x18001acc0  jnz     loc_18001B01A
0x18001acc6  mov     r8d, [rbx+383Ch]
0x18001accd  cmp     r8d, 7
0x18001acd1  jge     loc_18001AF2C
0x18001acd7  mov     [rbx+218Ch], r8d
0x18001acde  mov     r14, [rbx+1EE0h]
0x18001ace5  mov     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18001acea  call    TeredoGetMaximumPreviousState
0x18001acef  mov     r8d, eax
0x18001acf2  lea     rdx, aMaxPreviousSta; "Max previous state entries: %d"
0x18001acf9  mov     ecx, 100000h
0x18001acfe  mov     edi, eax
0x18001ad00  call    EventWrite0
0x18001ad05  test    edi, edi
0x18001ad07  jnz     loc_18001AF58
0x18001ad0d  mov     eax, [r13+4B80h]
0x18001ad14  lea     rdx, aTeredoresetbac; "TeredoResetBackOffStatemachine: old val"...
0x18001ad1b  mov     r9d, [r13+4B88h]
0x18001ad22  mov     ecx, 100000h
0x18001ad27  mov     r8d, [r13+4B84h]
0x18001ad2e  mov     dword ptr [rsp+0B8h+var_98], eax
0x18001ad32  call    EventWrite0
0x18001ad37  xor     eax, eax
0x18001ad39  mov     dword ptr [r13+4B88h], 1
0x18001ad44  mov     [r13+4B84h], eax
0x18001ad4b  mov     [r13+4B80h], eax
0x18001ad52  cmp     [rbx+3838h], al
0x18001ad58  jz      loc_18001B05B
0x18001ad5e  mov     rcx, rbx
0x18001ad61  call    TeredoClientStartTypeSpecificBehavior
0x18001ad66  mov     edi, eax
0x18001ad68  test    eax, eax
0x18001ad6a  jnz     loc_18001AF93
0x18001ad70  mov     rcx, rbx
0x18001ad73  call    TeredoInitializeClientPortMappings
0x18001ad78  mov     r13d, 1
0x18001ad7e  mov     rcx, rbx
0x18001ad81  mov     r14d, r13d
0x18001ad84  call    TeredoClientUpdateStateInNsi
0x18001ad89  movzx   ecx, word ptr [rbx+1E7Eh]; netshort
0x18001ad90  call    cs:__imp_ntohs
0x18001ad97  nop     dword ptr [rax+rax+00h]
0x18001ad9c  movzx   ecx, ax
0x18001ad9f  call    cs:__imp_InternalSetTeredoPort
0x18001ada6  nop     dword ptr [rax+rax+00h]
0x18001adab  test    eax, eax
0x18001adad  jnz     loc_18001B092
0x18001adb3  call    IsIphlpsvcExtConfigureTeredoClientPortPresent
0x18001adb8  test    al, al
0x18001adba  jnz     loc_18001B0BF
0x18001adc0  lea     rdx, [rbx+2218h]
0x18001adc7  lea     rcx, aAcquiredTeredo; "Acquired Teredo address:"
0x18001adce  call    TeredoTraceAddress
0x18001add3  movzx   ebp, r13b
0x18001add7  jmp     loc_18001AA98
0x18001addc  cmp     dword ptr [rbx+2188h], 5
0x18001ade3  mov     ecx, 100000h
0x18001ade8  jnz     loc_18001AFD0
0x18001adee  lea     rdx, aRestartingTere; "Restarting Teredo as the mappings have "...
0x18001adf5  call    EventWrite0
0x18001adfa  lea     rdx, [rbx+2218h]
0x18001ae01  lea     rcx, aOldTeredoAddre; "Old Teredo Address"
0x18001ae08  call    TeredoTraceAddress
0x18001ae0d  mov     rdx, r14
0x18001ae10  lea     rcx, aNewTeredoAddre_0; "New Teredo Address"
0x18001ae17  call    TeredoTraceAddress
0x18001ae1c  mov     rcx, rbx
0x18001ae1f  call    TeredoClientProcessMappingChange
0x18001ae24  jmp     loc_18001ABE5
0x18001ae29  mov     eax, r13d
0x18001ae2c  xchg    eax, [rbx+2F5Ch]
0x18001ae32  test    eax, eax
0x18001ae34  jnz     loc_18001AFC4
0x18001ae3a  mov     rcx, [rbx+3830h]
0x18001ae41  mov     dword ptr [rbx+2D20h], 0Ah
0x18001ae4b  cmp     rcx, [rbx+2258h]
0x18001ae52  jz      loc_18001B161
0x18001ae58  mov     r8d, [rbx]
0x18001ae5b  lea     rdi, aOnecoreuapNetN_27; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18001ae62  mov     r9, rdi
0x18001ae65  mov     dword ptr [rsp+0B8h+var_98], 12E1h
0x18001ae6d  lea     rdx, aTeredoreferenc_0; "TeredoReferenceClient: ++%d @ %ls:%u"
0x18001ae74  mov     ecx, 100000h
0x18001ae79  call    EventWrite0
0x18001ae7e  mov     ecx, [rbx]
0x18001ae80  lock xadd [rbx+8], r13d
0x18001ae86  mov     eax, r13d
0x18001ae89  and     eax, 3Fh
0x18001ae8c  lea     rax, [rax+rax*4]
0x18001ae90  mov     [rbx+rax*8+10h], ecx
0x18001ae94  xor     ecx, ecx
0x18001ae96  mov     [rbx+rax*8+30h], ecx
0x18001ae9a  mov     [rbx+rax*8+28h], rcx
0x18001ae9f  mov     dword ptr [rbx+rax*8+20h], 12E1h
0x18001aea7  mov     [rbx+rax*8+18h], rdi
0x18001aeac  lock inc dword ptr [rbx]
0x18001aeaf  movups  xmm0, xmmword ptr [rbx+2218h]
0x18001aeb6  movups  xmmword ptr [rbx+2F38h], xmm0
0x18001aebd  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001aec4  jnz     loc_18001B170
0x18001aeca  lea     rcx, [rbx+1FF0h]
0x18001aed1  call    RoReferenceEx
0x18001aed6  test    al, al
0x18001aed8  jz      loc_18001B18E
0x18001aede  mov     rax, [rbx+1FC0h]
0x18001aee5  lea     rdx, [rbx+2D30h]
0x18001aeec  lea     rcx, [rbx+1F78h]
0x18001aef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aef8  test    rax, rax
0x18001aefb  jz      short loc_18001AF13
0x18001aefd  mov     rdx, rax
0x18001af00  lea     rcx, [rbx+1F78h]
0x18001af07  mov     rax, [rbx+1FC8h]
0x18001af0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af13  mov     rax, [rbx+2258h]
0x18001af1a  inc     dword ptr [rbx+21A8h]
0x18001af20  mov     [rbx+3830h], rax
0x18001af27  jmp     loc_18001ABC3
0x18001af2c  mov     r9d, [rbx+218Ch]
0x18001af33  lea     rdx, aChangingTeredo; "Changing Teredo client previous NAT sta"...
0x18001af3a  mov     ecx, 100000h
0x18001af3f  mov     r12b, 1
0x18001af42  call    EventWrite0
0x18001af47  mov     eax, [rbx+218Ch]
0x18001af4d  mov     [rbx+383Ch], eax
0x18001af53  jmp     loc_18001ACDE
0x18001af58  xor     edx, edx
0x18001af5a  lea     rcx, [rsp+0B8h+SystemTimeAsFileTime]; phkResult
0x18001af5f  call    TeredoCreateGatewayKey
0x18001af64  test    eax, eax
0x18001af66  jnz     loc_18001B033
0x18001af6c  mov     rdx, qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x18001af71  movzx   r8d, r12b
  ... truncated ...
```
