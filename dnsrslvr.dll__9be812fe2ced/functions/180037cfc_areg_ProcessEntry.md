# areg_ProcessEntry

- ea: `0x180037cfc`
- end: `0x18003841b`
- name: `areg_ProcessEntry`
- size: `1823`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180036b50`

## callees

- `0x180026134`
- `0x180026270`
- `0x1800264e4`
- `0x18002739c`
- `0x1800312e4`
- `0x180033f14`
- `0x180033fc4`
- `0x180035670`
- `0x180037cfc`
- `0x180038424`
- `0x180040cd4`
- `0x18004a860`
- `0x18004ab34`
- `0x18004ae00`
- `0x18004ae7c`
- `0x18006226c`
- `0x18007b4a4`
- `0x18007bc48`
- `0x180085fb8`
- `0x180086700`
- `0x180086b1c`
- `0x180086b70`
- `0x180086bd4`
- `0x180086f24`
- `0x18008841c`
- `0x180088578`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x180037d10`
- `DNSAPI!DnsGlobals` at `0x180037fd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038351`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038351`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038162`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800381e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038162`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800381e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180037d80`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180038069`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800383c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180037d80`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180038069`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800383c2`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180037dd9`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18003839b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180037dd9`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18003839b`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180037da0`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180037da0`

## pseudocode

```c
NTSTATUS __fastcall areg_ProcessEntry(unsigned int *a1)
{
  unsigned int v1; // r12d
  int v2; // r14d
  unsigned int *v3; // rbx
  unsigned int v4; // ebp
  ULONGLONG TickCount64; // rax
  __int64 v6; // rcx
  NET_IF_COMPARTMENT_ID v7; // edi
  ULONGLONG v8; // r15
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // eax
  NTSTATUS result; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  _QWORD *v13; // r13
  __int64 EntryFromRegistry; // rax
  unsigned int v15; // r15d
  unsigned int v16; // esi
  _WORD *i; // rdi
  unsigned int v18; // eax
  bool v19; // zf
  ULONGLONG v20; // rdi
  unsigned int v21; // r12d
  unsigned int v22; // esi
  unsigned int v23; // r14d
  int FailRetryInterval; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // r15d
  __int64 v29; // rcx
  __int64 v30; // rdx
  unsigned int v31; // r15d
  unsigned int v32; // eax
  NTSTATUS v33; // eax
  ULONGLONG v34; // rax
  ULONGLONG v35; // [rsp+30h] [rbp-58h]
  unsigned int v36; // [rsp+90h] [rbp+8h]
  int v37; // [rsp+98h] [rbp+10h]
  NET_IF_COMPARTMENT_ID CompartmentId; // [rsp+A0h] [rbp+18h]
  int v39; // [rsp+A8h] [rbp+20h]

  v1 = 0;
  v2 = g_fAregPurge;
  v3 = a1;
  v37 = g_fAregPurge;
  v4 = 0;
  CompartmentId = 0;
  v36 = DnsGlobals[64];
  v39 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qd(a1, 109, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, a1, g_fAregPurge);
  DnsPrint_AregEntry("Entering areg_ProcessEntry():", v3);
  TickCount64 = GetTickCount64();
  v7 = v3[58];
  v8 = TickCount64;
  v35 = TickCount64;
  if ( v7 )
  {
    if ( v7 != g_DefaultCompartmentId )
    {
      CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
      CompartmentId = CurrentThreadCompartmentId;
      if ( CurrentThreadCompartmentId != v7 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_dd(1035, 110, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, CurrentThreadCompartmentId, v7);
        result = SetCurrentThreadCompartmentId(v7);
        v4 = result;
        if ( result )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
            return result;
          v11 = 111;
          v12 = v7;
          return WPP_SF_d(1035, v11, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v12);
        }
        v39 = 1;
      }
    }
  }
  v13 = 0;
  if ( v3[65] )
  {
LABEL_25:
    v15 = 0;
    v16 = 0;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_Dd(v6, 113, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v3[67], v3[66]);
    if ( !v3[67] )
    {
      *((_QWORD *)v3 + 10) = *((_QWORD *)v3 + 9);
      v1 = areg_DoUpdate(v13, v3, 2);
    }
    if ( !v3[66] )
    {
      *((_QWORD *)v3 + 10) = *((_QWORD *)v3 + 8);
      v15 = areg_DoUpdate(v13, v3, 1);
    }
    if ( !v3[68] )
    {
      for ( i = (_WORD *)*((_QWORD *)v3 + 7); i; i = (_WORD *)MultiSz_NextString_W(i) )
      {
        if ( *i )
        {
          if ( SBYTE2(xmmword_1800AB5A0) < 0 )
            WPP_SF_S(1047, 114, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, i);
          *((_QWORD *)v3 + 10) = i;
          v18 = areg_DoUpdate(0, v3, 3);
          if ( v18 )
            v16 = v18;
        }
      }
      v3[68] = v16 == 0;
    }
    v19 = (v3[60] & 8) == 0;
    *((_QWORD *)v3 + 10) = 0;
    if ( !v19 && DnsGlobals[60] )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_(1035, 115, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
      areg_UpdatePtrRecords(v3, v3[65] == 0, 0);
    }
    if ( !v3[65] )
      areg_WriteEntryToRegistry((__int64)v3);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_DDD(v6, 116, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v15, v1, v16);
    if ( v15 )
    {
      v4 = v15;
    }
    else if ( v1 )
    {
      v4 = v1;
    }
    else if ( v16 )
    {
      v4 = v16;
    }
    v20 = GetTickCount64() / 0x3E8;
    if ( v4 )
    {
      if ( !v3[78] )
        v3[78] = v20;
      v23 = v3[75];
      FailRetryInterval = areg_GetFailRetryInterval(v23, v1, v15, v16, v3[65]);
      v28 = FailRetryInterval;
      LOBYTE(v29) = BYTE1(xmmword_1800AB5A0);
      v21 = v36;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        WPP_SF_ddd(1035, 117, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v36, v23, FailRetryInterval);
        LOBYTE(v29) = BYTE1(xmmword_1800AB5A0);
      }
      if ( v3[65] && v23 == 3 )
      {
        v22 = 0;
        if ( (v29 & 8) != 0 )
          WPP_SF_d(1035, 118, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, 3);
      }
      else
      {
        if ( !v3[78] )
          MicrosoftTelemetryAssertTriggeredNoArgs(v29, v25, v26, v27);
        v22 = v3[78];
        v31 = v20 + v28;
        if ( v31 - v22 < v36 )
        {
          if ( *((_QWORD *)v3 + 41) )
            areg_SignalUpdateStatus(v3 + 82, v4);
          EnterCriticalSection(&g_AregListCs);
          if ( v37 || g_fAregPurge )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_(1035, 123, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
            goto LABEL_98;
          }
          if ( !v23 )
            v3[77] = v20;
          if ( v3[77] + 86400 >= (unsigned int)v20 )
          {
            v32 = v23 + 1;
          }
          else
          {
            v3[77] = v20;
            v32 = 0;
          }
          v3[75] = v32;
          v3[76] = v31;
          v3[63] = 0;
          areg_EnqueueUpdateMaybe(v3);
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_q(1035, 124, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v3);
          goto LABEL_88;
        }
      }
      v2 = v37;
    }
    else
    {
      v21 = v36;
      v22 = v20;
    }
    if ( *((_QWORD *)v3 + 41) )
      areg_SignalUpdateStatus(v3 + 82, v4);
    EnterCriticalSection(&g_AregListCs);
    if ( v2 || g_fAregPurge )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v30 = 119;
        goto LABEL_97;
      }
LABEL_98:
      LeaveCriticalSection(&g_AregListCs);
      v8 = v35;
      goto LABEL_99;
    }
    if ( v3[65] )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v30 = 120;
LABEL_97:
        WPP_SF_d(1035, v30, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v4);
        goto LABEL_98;
      }
      goto LABEL_98;
    }
    v3[63] = 0;
    *((_QWORD *)v3 + 33) = 0;
    *((_QWORD *)v3 + 34) = 0;
    v3[70] = 0;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_ddd(1035, 121, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v22, v20, v21);
    v3[86] = v22;
    *(_QWORD *)(v3 + 75) = 0;
    *(_QWORD *)(v3 + 77) = 0;
    areg_EnqueueUpdate(v3);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_qD(1035, 122, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v3, v4);
LABEL_88:
    v3 = 0;
    goto LABEL_98;
  }
  if ( !v2 )
  {
    if ( (v3[60] & 0x2000) == 0 )
    {
      EntryFromRegistry = areg_ReadEntryFromRegistry(*((void **)v3 + 3));
      v13 = (_QWORD *)EntryFromRegistry;
      if ( EntryFromRegistry )
      {
        if ( !(unsigned int)Dns_NameCompare_W(*(PCNZWCH *)(EntryFromRegistry + 32), *((PCNZWCH *)v3 + 4)) )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_(1035, 112, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
          if ( *((_QWORD *)v3 + 7) && !(unsigned int)areg_IsAnotherUpdateName(v3, v13[9], 2) )
            areg_IsAnotherUpdateName(v3, v13[8], 1);
          areg_DeleteEntry(v13);
          v13 = 0;
        }
      }
    }
    goto LABEL_25;
  }
  if ( *((_QWORD *)v3 + 41) )
    areg_SignalUpdateStatus(v3 + 82, 1223);
LABEL_99:
  if ( v39 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 125, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, CompartmentId);
    v33 = SetCurrentThreadCompartmentId(CompartmentId);
    if ( v33 )
      __fastfail(v33);
  }
  areg_FreeEntry(v13);
  result = areg_FreeEntry(v3);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v34 = GetTickCount64();
    v11 = 126;
    v12 = (unsigned int)(v34 / 0x3E8) - (unsigned int)(v8 / 0x3E8);
    return WPP_SF_d(1035, v11, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v12);
  }
  return result;
}

```

## disassembly

```asm
0x180037cfc  mov     [rsp+arg_8], edx
0x180037d00  push    rbx
0x180037d01  push    rbp
0x180037d02  push    rsi
0x180037d03  push    rdi
0x180037d04  push    r12
0x180037d06  push    r13
0x180037d08  push    r14
0x180037d0a  push    r15
0x180037d0c  sub     rsp, 48h
0x180037d10  mov     rax, cs:__imp_DnsGlobals
0x180037d17  xor     r12d, r12d
0x180037d1a  mov     r14d, cs:g_fAregPurge
0x180037d21  mov     rbx, rcx
0x180037d24  mov     [rsp+88h+arg_8], r14d
0x180037d2c  mov     ebp, r12d
0x180037d2f  mov     [rsp+88h+CompartmentId], r12d
0x180037d37  mov     eax, [rax+100h]
0x180037d3d  mov     [rsp+88h+arg_0], eax
0x180037d44  mov     [rsp+88h+arg_18], r12d
0x180037d4c  mov     r13b, 8
0x180037d4f  test    byte ptr cs:xmmword_1800AB5A0+1, r13b
0x180037d56  jz      short loc_180037D71
0x180037d58  lea     edx, [r12+6Dh]
0x180037d5d  mov     [rsp+88h+var_68], r14d
0x180037d62  mov     r9, rcx
0x180037d65  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180037d6c  call    WPP_SF_qd
0x180037d71  mov     rdx, rbx
0x180037d74  lea     rcx, aEnteringAregPr; "Entering areg_ProcessEntry():"
0x180037d7b  call    DnsPrint_AregEntry
0x180037d80  call    cs:__imp_GetTickCount64
0x180037d86  mov     edi, [rbx+0E8h]
0x180037d8c  mov     r15, rax
0x180037d8f  mov     [rsp+88h+var_58], rax
0x180037d94  test    edi, edi
0x180037d96  jz      short loc_180037E0A
0x180037d98  cmp     edi, cs:g_DefaultCompartmentId
0x180037d9e  jz      short loc_180037E0A
0x180037da0  call    cs:__imp_GetCurrentThreadCompartmentId
0x180037da6  mov     [rsp+88h+CompartmentId], eax
0x180037dad  cmp     eax, edi
0x180037daf  jz      short loc_180037E0A
0x180037db1  test    byte ptr cs:xmmword_1800AB5A0+1, r13b
0x180037db8  jz      short loc_180037DD7
0x180037dba  mov     edx, 6Eh ; 'n'
0x180037dbf  mov     [rsp+88h+var_68], edi
0x180037dc3  mov     ecx, 40Bh
0x180037dc8  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180037dcf  mov     r9d, eax
0x180037dd2  call    WPP_SF_dd
0x180037dd7  mov     ecx, edi; CompartmentId
0x180037dd9  call    cs:__imp_SetCurrentThreadCompartmentId
0x180037ddf  mov     ebp, eax
0x180037de1  test    eax, eax
0x180037de3  jz      short loc_180037DFF
0x180037de5  test    byte ptr cs:xmmword_1800AB5A0+1, r13b
0x180037dec  jz      loc_18003840A
0x180037df2  mov     edx, 6Fh ; 'o'
0x180037df7  mov     r9d, edi
0x180037dfa  jmp     loc_1800383F9
0x180037dff  mov     [rsp+88h+arg_18], 1
0x180037e0a  mov     r13, r12
0x180037e0d  mov     rsi, 624DD2F1A9FBE77h
0x180037e17  cmp     [rbx+104h], r12d
0x180037e1e  jnz     loc_180037EE5
0x180037e24  test    r14d, r14d
0x180037e27  jz      short loc_180037E48
0x180037e29  lea     rcx, [rbx+148h]
0x180037e30  cmp     [rcx], r12
0x180037e33  jz      loc_180038366
0x180037e39  mov     edx, 4C7h
0x180037e3e  call    areg_SignalUpdateStatus
0x180037e43  jmp     loc_180038366
0x180037e48  test    dword ptr [rbx+0F0h], 2000h
0x180037e52  jnz     loc_180037EE5
0x180037e58  mov     rcx, [rbx+18h]; Src
0x180037e5c  xor     edx, edx
0x180037e5e  lea     r8d, [rdx+1]
0x180037e62  call    areg_ReadEntryFromRegistry
0x180037e67  mov     r13, rax
0x180037e6a  test    rax, rax
0x180037e6d  jz      short loc_180037EE5
0x180037e6f  mov     rdx, [rbx+20h]; lpString2
0x180037e73  mov     rcx, [rax+20h]; lpString1
0x180037e77  call    Dns_NameCompare_W
0x180037e7c  test    eax, eax
0x180037e7e  jnz     short loc_180037EE5
0x180037e80  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180037e87  jz      short loc_180037E9D
0x180037e89  lea     edx, [rax+70h]
0x180037e8c  mov     ecx, 40Bh
0x180037e91  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180037e98  call    WPP_SF_
0x180037e9d  cmp     [rbx+38h], r12
0x180037ea1  jz      short loc_180037ED2
0x180037ea3  mov     rdx, [r13+48h]
0x180037ea7  mov     r8d, 2
0x180037ead  mov     rcx, rbx
0x180037eb0  call    areg_IsAnotherUpdateName
0x180037eb5  test    eax, eax
0x180037eb7  jnz     short loc_180037ECD
0x180037eb9  mov     rdx, [r13+40h]
0x180037ebd  lea     r8d, [rax+1]
0x180037ec1  mov     rcx, rbx
0x180037ec4  call    areg_IsAnotherUpdateName
0x180037ec9  test    eax, eax
0x180037ecb  jz      short loc_180037ED2
0x180037ecd  mov     r8d, r12d
0x180037ed0  jmp     short loc_180037ED8
0x180037ed2  mov     r8d, 1
0x180037ed8  xor     edx, edx
0x180037eda  mov     rcx, r13; void *
0x180037edd  call    areg_DeleteEntry
0x180037ee2  mov     r13, r12
0x180037ee5  xor     edi, edi
0x180037ee7  mov     r15d, r12d
0x180037eea  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180037ef1  mov     esi, edi
0x180037ef3  jz      short loc_180037F15
0x180037ef5  mov     eax, [rbx+108h]
0x180037efb  lea     edx, [rdi+71h]
0x180037efe  mov     r9d, [rbx+10Ch]
0x180037f05  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180037f0c  mov     [rsp+88h+var_68], eax
0x180037f10  call    WPP_SF_Dd
0x180037f15  cmp     [rbx+10Ch], edi
0x180037f1b  jnz     short loc_180037F39
0x180037f1d  mov     rax, [rbx+48h]
0x180037f21  mov     r8d, 2
0x180037f27  mov     rdx, rbx
0x180037f2a  mov     [rbx+50h], rax
0x180037f2e  mov     rcx, r13
0x180037f31  call    areg_DoUpdate
0x180037f36  mov     r12d, eax
0x180037f39  cmp     [rbx+108h], edi
0x180037f3f  jnz     short loc_180037F5D
0x180037f41  mov     rax, [rbx+40h]
0x180037f45  mov     r8d, 1
0x180037f4b  mov     rdx, rbx
0x180037f4e  mov     [rbx+50h], rax
0x180037f52  mov     rcx, r13
0x180037f55  call    areg_DoUpdate
0x180037f5a  mov     r15d, eax
0x180037f5d  cmp     [rbx+110h], edi
0x180037f63  jnz     short loc_180037FC9
0x180037f65  mov     rdi, [rbx+38h]
0x180037f69  jmp     short loc_180037FB5
0x180037f6b  cmp     [rdi], ax
0x180037f6e  jz      short loc_180037FAA
0x180037f70  cmp     byte ptr cs:xmmword_1800AB5A0+2, al
0x180037f76  jge     short loc_180037F91
0x180037f78  mov     edx, 72h ; 'r'
0x180037f7d  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180037f84  mov     ecx, 417h
0x180037f89  mov     r9, rdi
0x180037f8c  call    WPP_SF_S
0x180037f91  mov     r8d, 3
0x180037f97  mov     [rbx+50h], rdi
0x180037f9b  mov     rdx, rbx
0x180037f9e  xor     ecx, ecx
0x180037fa0  call    areg_DoUpdate
0x180037fa5  test    eax, eax
0x180037fa7  cmovnz  esi, eax
0x180037faa  mov     rcx, rdi
0x180037fad  call    MultiSz_NextString_W
0x180037fb2  mov     rdi, rax
0x180037fb5  xor     eax, eax
0x180037fb7  test    rdi, rdi
0x180037fba  jnz     short loc_180037F6B
0x180037fbc  mov     eax, edi
0x180037fbe  test    esi, esi
0x180037fc0  setz    al
0x180037fc3  mov     [rbx+110h], eax
0x180037fc9  test    byte ptr [rbx+0F0h], 8
0x180037fd0  mov     [rbx+50h], rdi
0x180037fd4  jz      short loc_18003801A
0x180037fd6  mov     rax, cs:__imp_DnsGlobals
0x180037fdd  cmp     [rax+0F0h], edi
0x180037fe3  jz      short loc_18003801A
0x180037fe5  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180037fec  jz      short loc_180038004
0x180037fee  mov     edx, 73h ; 's'
0x180037ff3  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180037ffa  mov     ecx, 40Bh
0x180037fff  call    WPP_SF_
0x180038004  cmp     [rbx+104h], edi
0x18003800a  mov     edx, edi
0x18003800c  mov     rcx, rbx
0x18003800f  setz    dl
0x180038012  xor     r8d, r8d
0x180038015  call    areg_UpdatePtrRecords
0x18003801a  cmp     [rbx+104h], edi
0x180038020  jnz     short loc_18003802A
0x180038022  mov     rcx, rbx
0x180038025  call    areg_WriteEntryToRegistry
0x18003802a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038031  jz      short loc_180038050
0x180038033  mov     edx, 74h ; 't'
0x180038038  mov     [rsp+88h+var_60], esi
0x18003803c  mov     r9d, r15d
0x18003803f  mov     [rsp+88h+var_68], r12d
0x180038044  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x18003804b  call    WPP_SF_DDD
0x180038050  test    r15d, r15d
0x180038053  jz      short loc_18003805A
0x180038055  mov     ebp, r15d
0x180038058  jmp     short loc_180038069
0x18003805a  test    r12d, r12d
0x18003805d  jz      short loc_180038064
0x18003805f  mov     ebp, r12d
0x180038062  jmp     short loc_180038069
0x180038064  test    esi, esi
0x180038066  cmovnz  ebp, esi
0x180038069  call    cs:__imp_GetTickCount64
0x18003806f  mov     rdi, rax
0x180038072  mov     rax, 624DD2F1A9FBE77h
0x18003807c  mul     rdi
0x18003807f  sub     rdi, rdx
0x180038082  shr     rdi, 1
0x180038085  add     rdi, rdx
0x180038088  shr     rdi, 9
0x18003808c  test    ebp, ebp
0x18003808e  jnz     short loc_18003809F
0x180038090  mov     r12d, [rsp+88h+arg_0]
0x180038098  mov     esi, edi
0x18003809a  jmp     loc_180038147
0x18003809f  cmp     dword ptr [rbx+138h], 0
0x1800380a6  jnz     short loc_1800380AE
0x1800380a8  mov     [rbx+138h], edi
0x1800380ae  mov     eax, [rbx+104h]
0x1800380b4  mov     r9d, esi
0x1800380b7  mov     r14d, [rbx+12Ch]
0x1800380be  mov     r8d, r15d
0x1800380c1  mov     ecx, r14d
0x1800380c4  mov     [rsp+88h+var_68], eax
0x1800380c8  mov     edx, r12d
0x1800380cb  call    areg_GetFailRetryInterval
0x1800380d0  mov     r15d, eax
0x1800380d3  mov     cl, byte ptr cs:xmmword_1800AB5A0+1
0x1800380d9  mov     r12d, [rsp+88h+arg_0]
0x1800380e1  test    cl, 8
0x1800380e4  jz      short loc_18003810E
0x1800380e6  mov     [rsp+88h+var_60], eax
0x1800380ea  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x1800380f1  mov     edx, 75h ; 'u'
0x1800380f6  mov     [rsp+88h+var_68], r14d
0x1800380fb  mov     ecx, 40Bh
0x180038100  mov     r9d, r12d
0x180038103  call    WPP_SF_ddd
0x180038108  mov     cl, byte ptr cs:xmmword_1800AB5A0+1
0x18003810e  cmp     dword ptr [rbx+104h], 0
0x180038115  jz      loc_1800381A0
0x18003811b  cmp     r14d, 3
0x18003811f  jnz     short loc_1800381A0
0x180038121  xor     esi, esi
0x180038123  test    cl, 8
0x180038126  jz      short loc_18003813F
0x180038128  lea     edx, [rsi+76h]
0x18003812b  mov     ecx, 40Bh
0x180038130  mov     r9d, r14d
0x180038133  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x18003813a  call    WPP_SF_d
0x18003813f  mov     r14d, [rsp+88h+arg_8]
0x180038147  lea     rcx, [rbx+148h]
0x18003814e  cmp     qword ptr [rcx], 0
0x180038152  jz      short loc_18003815B
0x180038154  mov     edx, ebp
0x180038156  call    areg_SignalUpdateStatus
0x18003815b  lea     rcx, g_AregListCs; lpCriticalSection
0x180038162  call    cs:__imp_EnterCriticalSection
0x180038168  xor     eax, eax
0x18003816a  test    r14d, r14d
0x18003816d  jnz     loc_180038325
0x180038173  cmp     cs:g_fAregPurge, eax
0x180038179  jnz     loc_180038325
0x18003817f  cmp     [rbx+104h], eax
0x180038185  jz      loc_180038292
0x18003818b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180038192  jz      loc_180038347
0x180038198  lea     edx, [rax+78h]
0x18003819b  jmp     loc_180038333
0x1800381a0  cmp     dword ptr [rbx+138h], 0
0x1800381a7  jnz     short loc_1800381AE
0x1800381a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800381ae  mov     esi, [rbx+138h]
0x1800381b4  add     r15d, edi
0x1800381b7  mov     eax, r15d
0x1800381ba  sub     eax, esi
0x1800381bc  cmp     eax, r12d
0x1800381bf  jnb     loc_18003813F
0x1800381c5  lea     rcx, [rbx+148h]
0x1800381cc  xor     r12d, r12d
0x1800381cf  cmp     [rcx], r12
0x1800381d2  jz      short loc_1800381DB
0x1800381d4  mov     edx, ebp
0x1800381d6  call    areg_SignalUpdateStatus
0x1800381db  lea     rcx, g_AregListCs; lpCriticalSection
0x1800381e2  call    cs:__imp_EnterCriticalSection
0x1800381e8  cmp     [rsp+88h+arg_8], r12d
  ... truncated ...
```
