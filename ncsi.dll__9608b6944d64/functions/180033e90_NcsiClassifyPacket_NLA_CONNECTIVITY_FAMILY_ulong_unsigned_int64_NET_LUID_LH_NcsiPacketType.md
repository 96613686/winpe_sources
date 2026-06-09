# NcsiClassifyPacket(_NLA_CONNECTIVITY_FAMILY,ulong,unsigned __int64,_NET_LUID_LH,NcsiPacketType &)

- ea: `0x180033e90`
- end: `0x1800343bf`
- name: `?NcsiClassifyPacket@@YAKW4_NLA_CONNECTIVITY_FAMILY@@K_KT_NET_LUID_LH@@AEAW4NcsiPacketType@@@Z`
- size: `1327`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180010230`

## callees

- `0x180021470`
- `0x1800247ac`
- `0x180025078`
- `0x180033e90`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18003401d`
- `ntdll!EtwEventWriteTransfer` at `0x18003415a`
- `ntdll!EtwEventWriteTransfer` at `0x18003401d`
- `ntdll!EtwEventWriteTransfer` at `0x18003415a`

## pseudocode

```c
__int64 __fastcall NcsiClassifyPacket(
        unsigned int a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        _DWORD *a5)
{
  unsigned int v6; // r14d
  const char *v8; // rdx
  const char *v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rax
  bool v12; // zf
  const char *v14; // rsi
  unsigned int v15; // r13d
  const char *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  const char *v19; // rax
  unsigned __int8 *v20; // rdx
  unsigned int v21; // [rsp+50h] [rbp-91h] BYREF
  const char *v22; // [rsp+58h] [rbp-89h] BYREF
  const char *v23; // [rsp+60h] [rbp-81h] BYREF
  const char *v24; // [rsp+68h] [rbp-79h] BYREF
  const unsigned __int16 *v25[2]; // [rsp+70h] [rbp-71h] BYREF
  __int16 *v26; // [rsp+80h] [rbp-61h] BYREF
  int v27; // [rsp+88h] [rbp-59h]
  int v28; // [rsp+8Ch] [rbp-55h]
  __int16 *v29; // [rsp+90h] [rbp-51h]
  int v30; // [rsp+98h] [rbp-49h]
  int v31; // [rsp+9Ch] [rbp-45h]
  const char *v32; // [rsp+A0h] [rbp-41h]
  __int64 v33; // [rsp+A8h] [rbp-39h]
  const char *v34; // [rsp+B0h] [rbp-31h]
  __int64 v35; // [rsp+B8h] [rbp-29h]
  const char **v36; // [rsp+C0h] [rbp-21h]
  __int64 v37; // [rsp+C8h] [rbp-19h]
  const char **v38; // [rsp+D0h] [rbp-11h]
  __int64 v39; // [rsp+D8h] [rbp-9h]
  _DWORD v40[2]; // [rsp+E0h] [rbp-1h] BYREF
  __int64 v41; // [rsp+E8h] [rbp+7h]

  v25[0] = a3;
  v6 = a2;
  if ( a3 )
  {
    v14 = "UnknownConnectivityFamily";
    v15 = dword_18009B3BC;
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      LODWORD(v24) = dword_18009B3BC;
      LODWORD(v22) = a2;
      if ( a1 )
      {
        if ( a1 == 1 )
          v16 = "IPv6";
        else
          v16 = "UnknownConnectivityFamily";
      }
      else
      {
        v16 = "IPv4";
      }
      v23 = (const char *)a4;
      v38 = &v24;
      v36 = &v22;
      v17 = -1;
      v39 = 4;
      v37 = 4;
      do
        v12 = v16[++v17] == 0;
      while ( !v12 );
      v34 = v16;
      v35 = (unsigned int)(v17 + 1);
      v33 = 8;
      v32 = (const char *)&v23;
      v40[1] = 5;
      v26 = off_18009A050;
      v40[0] = 184549376;
      v41 = 0;
      v27 = (unsigned __int16)*off_18009A050;
      v29 = &word_180088DA6;
      v28 = 2;
      v30 = 80;
      v31 = 1;
      v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, v40, 0, 0, 6, &v26);
      a3 = v25[0];
    }
    v18 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_LDDIi(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), a2, a3, a1, v6, v15, a3, a4);
    }
    if ( v6 - 1 > 0x1A )
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        if ( a1 )
        {
          if ( a1 == 1 )
            v14 = "IPv6";
        }
        else
        {
          v14 = "IPv4";
        }
        v19 = "hopCount is greater than or equal to 28 or is 0";
        v20 = (unsigned __int8 *)&byte_180088DF7;
        goto LABEL_63;
      }
    }
    else
    {
      if ( v6 >= v15 )
      {
        if ( (unsigned int)dword_18009A080 > 5 )
        {
          if ( a1 )
          {
            if ( a1 == 1 )
              v14 = "IPv6";
          }
          else
          {
            v14 = "IPv4";
          }
          v25[0] = (const unsigned __int16 *)v14;
          v23 = "hopCount is greater than minimumInternetHopCount";
          v21 = v15;
          v24 = "Returning packetType is InternetPacket";
          LODWORD(v22) = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v18,
            (unsigned __int8 *)byte_180088CE3,
            (__int64)a3,
            (__int64)a4,
            (const unsigned __int16 **)&v24,
            (const unsigned __int16 **)&v23,
            (__int64)&v22,
            (__int64)&v21,
            v25);
        }
        *a5 = 0;
        return 0;
      }
      if ( v6 > 1 )
      {
        if ( (unsigned int)dword_18009A080 > 5 )
        {
          if ( a1 )
          {
            if ( a1 == 1 )
              v14 = "IPv6";
          }
          else
          {
            v14 = "IPv4";
          }
          v25[0] = (const unsigned __int16 *)v14;
          v23 = "hopCount is greater than 1 but less than minimumInternetHopCount";
          v21 = v15;
          v24 = "Returning packetType is LocalPacket";
          LODWORD(v22) = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v18,
            (unsigned __int8 *)byte_180088D3F,
            (__int64)a3,
            (__int64)a4,
            (const unsigned __int16 **)&v24,
            (const unsigned __int16 **)&v23,
            (__int64)&v22,
            (__int64)&v21,
            v25);
        }
        *a5 = 1;
        return 0;
      }
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        if ( a1 )
        {
          if ( a1 == 1 )
          {
            v14 = "IPv6";
            v19 = "hopCount is less than 1";
            v20 = (unsigned __int8 *)word_180088C52;
LABEL_63:
            v23 = v19;
            v22 = "Returning packetType is SubnetPacket";
            v25[0] = (const unsigned __int16 *)v14;
            v21 = v6;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v18,
              v20,
              (__int64)a3,
              (__int64)a4,
              (const unsigned __int16 **)&v22,
              (const unsigned __int16 **)&v23,
              (__int64)&v21,
              v25);
            goto LABEL_64;
          }
        }
        else
        {
          v14 = "IPv4";
        }
        v19 = "hopCount is less than 1";
        v20 = (unsigned __int8 *)word_180088C52;
        goto LABEL_63;
      }
    }
LABEL_64:
    *a5 = 2;
    return 0;
  }
  if ( (unsigned int)dword_18009A080 > 5 )
  {
    if ( *a5 )
    {
      if ( *a5 == 1 )
      {
        v8 = "LocalPacket";
      }
      else if ( *a5 == 2 )
      {
        v8 = "SubnetPacket";
      }
      else
      {
        v8 = "UnknownNcsiPacketType";
      }
    }
    else
    {
      v8 = "InternetPacket";
    }
    if ( a1 )
    {
      if ( a1 == 1 )
        v9 = "IPv6";
      else
        v9 = "UnknownConnectivityFamily";
    }
    else
    {
      v9 = "IPv4";
    }
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( v8[v11] );
    v38 = (const char **)v8;
    v39 = (unsigned int)(v11 + 1);
    do
      v12 = v9[++v10] == 0;
    while ( !v12 );
    v36 = (const char **)v9;
    v37 = (unsigned int)(v10 + 1);
    v34 = "receivedPacketsSinceLastPoll is 0";
    v35 = 34;
    v32 = "Skipping";
    v26 = (__int16 *)off_18009A088;
    v33 = 9;
    v25[0] = (const unsigned __int16 *)0x50B000000LL;
    v25[1] = 0;
    v27 = *(unsigned __int16 *)off_18009A088;
    v29 = (__int16 *)byte_180088E45;
    v28 = 2;
    v30 = 57;
    v31 = 1;
    LODWORD(v24) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_18009A0A0, v25, 0, 0, 6, &v26);
  }
  return 13;
}

```

## disassembly

```asm
0x180033e90  push    rbp
0x180033e92  push    rbx
0x180033e93  push    rsi
0x180033e94  push    rdi
0x180033e95  push    r12
0x180033e97  push    r14
0x180033e99  push    r15
0x180033e9b  lea     rbp, [rsp-1Fh]
0x180033ea0  sub     rsp, 100h
0x180033ea7  mov     rax, cs:__security_cookie
0x180033eae  xor     rax, rsp
0x180033eb1  mov     [rbp+4Fh+var_40], rax
0x180033eb5  mov     r12, [rbp+4Fh+arg_20]
0x180033eb9  mov     rbx, r9
0x180033ebc  mov     [rbp+4Fh+var_C0], r8
0x180033ec0  mov     r14d, edx
0x180033ec3  mov     edi, ecx
0x180033ec5  test    r8, r8
0x180033ec8  jnz     loc_18003402D
0x180033ece  mov     eax, cs:dword_18009A080
0x180033ed4  cmp     eax, 5
0x180033ed7  jbe     loc_180034023
0x180033edd  mov     ecx, [r12]
0x180033ee1  test    ecx, ecx
0x180033ee3  jz      short loc_180033F0A
0x180033ee5  sub     ecx, 1
0x180033ee8  jz      short loc_180033F01
0x180033eea  cmp     ecx, 1
0x180033eed  jz      short loc_180033EF8
0x180033eef  lea     rdx, aUnknownncsipac; "UnknownNcsiPacketType"
0x180033ef6  jmp     short loc_180033F11
0x180033ef8  lea     rdx, aSubnetpacket; "SubnetPacket"
0x180033eff  jmp     short loc_180033F11
0x180033f01  lea     rdx, aLocalpacket; "LocalPacket"
0x180033f08  jmp     short loc_180033F11
0x180033f0a  lea     rdx, aInternetpacket; "InternetPacket"
0x180033f11  test    edi, edi
0x180033f13  jz      short loc_180033F2C
0x180033f15  cmp     edi, 1
0x180033f18  jz      short loc_180033F23
0x180033f1a  lea     rsi, aUnknownconnect; "UnknownConnectivityFamily"
0x180033f21  jmp     short loc_180033F33
0x180033f23  lea     rsi, aIpv6; "IPv6"
0x180033f2a  jmp     short loc_180033F33
0x180033f2c  lea     rsi, aIpv4; "IPv4"
0x180033f33  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180033f3a  mov     rax, rcx
0x180033f3d  nop     dword ptr [rax]
0x180033f40  inc     rax
0x180033f43  cmp     byte ptr [rdx+rax], 0
0x180033f47  jnz     short loc_180033F40
0x180033f49  inc     eax
0x180033f4b  mov     [rbp+4Fh+var_60], rdx
0x180033f4f  xor     r15d, r15d
0x180033f52  mov     dword ptr [rbp+4Fh+var_58], eax
0x180033f55  mov     dword ptr [rbp+4Fh+var_58+4], r15d
0x180033f59  nop     dword ptr [rax+00000000h]
0x180033f60  cmp     [rsi+rcx+1], r15b
0x180033f65  lea     rcx, [rcx+1]
0x180033f69  jnz     short loc_180033F60
0x180033f6b  lea     eax, [rcx+1]
0x180033f6e  mov     [rbp+4Fh+var_70], rsi
0x180033f72  mov     dword ptr [rbp+4Fh+var_68], eax
0x180033f75  lea     rcx, _TraceLoggingMetadata
0x180033f7c  mov     dword ptr [rbp+4Fh+var_68+4], r15d
0x180033f80  lea     rax, aReceivedpacket; "receivedPacketsSinceLastPoll is 0"
0x180033f87  mov     [rbp+4Fh+var_80], rax
0x180033f8b  lea     rdx, [rbp+4Fh+var_C0]
0x180033f8f  lea     rax, aSkipping; "Skipping"
0x180033f96  mov     [rbp+4Fh+var_78], 22h ; '"'
0x180033f9e  mov     [rbp+4Fh+var_90], rax
0x180033fa2  xor     r9d, r9d
0x180033fa5  movzx   eax, cs:word_180088E3B
0x180033fac  xor     r8d, r8d
0x180033faf  mov     dword ptr [rbp+4Fh+var_C0+4], eax
0x180033fb2  mov     rax, cs:off_18009A088
0x180033fb9  mov     [rbp+4Fh+var_B0], rax
0x180033fbd  mov     [rbp+4Fh+var_88], 9
0x180033fc5  mov     dword ptr [rbp+4Fh+var_C0], 0B000000h
0x180033fcc  mov     [rbp+4Fh+var_B8], r15
0x180033fd0  movzx   eax, word ptr [rax]
0x180033fd3  mov     [rbp+4Fh+var_A8], eax
0x180033fd6  lea     rax, byte_180088E45
0x180033fdd  mov     [rbp+4Fh+var_A0], rax
0x180033fe1  lea     rax, _TraceLoggingMetadataEnd
0x180033fe8  sub     eax, ecx
0x180033fea  mov     [rbp+4Fh+var_A4], 2
0x180033ff1  mov     [rbp+4Fh+var_98], 39h ; '9'
0x180033ff8  mov     [rbp+4Fh+var_94], 1
0x180033fff  mov     dword ptr [rbp+4Fh+var_C8], eax
0x180034002  mov     eax, dword ptr [rbp+4Fh+var_C8]
0x180034005  mov     rcx, cs:qword_18009A0A0
0x18003400c  lea     rax, [rbp+4Fh+var_B0]
0x180034010  mov     [rsp+130h+var_108], rax
0x180034015  mov     dword ptr [rsp+130h+var_110], 6
0x18003401d  call    cs:__imp_EtwEventWriteTransfer
0x180034023  mov     eax, 0Dh
0x180034028  jmp     loc_1800343A1
0x18003402d  mov     [rsp+130h+arg_8], r13
0x180034035  lea     rsi, aUnknownconnect; "UnknownConnectivityFamily"
0x18003403c  mov     r13d, cs:dword_18009B3BC
0x180034043  xor     r15d, r15d
0x180034046  nop
0x180034047  mov     eax, cs:dword_18009A048
0x18003404d  cmp     eax, 5
0x180034050  jbe     loc_180034164
0x180034056  mov     dword ptr [rbp+4Fh+var_C8], r13d
0x18003405a  mov     dword ptr [rsp+130h+var_D8], r14d
0x18003405f  test    edi, edi
0x180034061  jz      short loc_180034076
0x180034063  cmp     edi, 1
0x180034066  jz      short loc_18003406D
0x180034068  mov     rax, rsi
0x18003406b  jmp     short loc_18003407D
0x18003406d  lea     rax, aIpv6; "IPv6"
0x180034074  jmp     short loc_18003407D
0x180034076  lea     rax, aIpv4; "IPv4"
0x18003407d  lea     rcx, [rbp+4Fh+var_C8]
0x180034081  mov     [rsp+130h+var_D0], rbx
0x180034086  mov     [rbp+4Fh+var_60], rcx
0x18003408a  lea     rcx, [rsp+130h+var_D8]
0x18003408f  mov     [rbp+4Fh+var_70], rcx
0x180034093  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003409a  mov     [rbp+4Fh+var_58], 4
0x1800340a2  mov     [rbp+4Fh+var_68], 4
0x1800340aa  nop     word ptr [rax+rax+00h]
0x1800340b0  cmp     [rax+rcx+1], r15b
0x1800340b5  lea     rcx, [rcx+1]
0x1800340b9  jnz     short loc_1800340B0
0x1800340bb  mov     [rbp+4Fh+var_80], rax
0x1800340bf  lea     rdx, [rbp+4Fh+var_50]
0x1800340c3  lea     eax, [rcx+1]
0x1800340c6  mov     dword ptr [rbp+4Fh+var_78+4], r15d
0x1800340ca  mov     dword ptr [rbp+4Fh+var_78], eax
0x1800340cd  lea     rcx, _TraceLoggingMetadata
0x1800340d4  lea     rax, [rsp+130h+var_D0]
0x1800340d9  mov     [rbp+4Fh+var_88], 8
0x1800340e1  mov     [rbp+4Fh+var_90], rax
0x1800340e5  xor     r9d, r9d
0x1800340e8  movzx   eax, cs:word_180088D9C
0x1800340ef  xor     r8d, r8d
0x1800340f2  mov     [rbp+4Fh+var_4C], eax
0x1800340f5  mov     rax, cs:off_18009A050
0x1800340fc  mov     [rbp+4Fh+var_B0], rax
0x180034100  mov     [rbp+4Fh+var_50], 0B000000h
0x180034107  mov     [rbp+4Fh+var_48], r15
0x18003410b  movzx   eax, word ptr [rax]
0x18003410e  mov     [rbp+4Fh+var_A8], eax
0x180034111  lea     rax, word_180088DA6
0x180034118  mov     [rbp+4Fh+var_A0], rax
0x18003411c  lea     rax, _TraceLoggingMetadataEnd
0x180034123  sub     eax, ecx
0x180034125  mov     [rbp+4Fh+var_A4], 2
0x18003412c  mov     [rbp+4Fh+var_98], 50h ; 'P'
0x180034133  mov     [rbp+4Fh+var_94], 1
0x18003413a  mov     [rsp+130h+var_E0], eax
0x18003413e  mov     eax, [rsp+130h+var_E0]
0x180034142  mov     rcx, cs:RegHandle
0x180034149  lea     rax, [rbp+4Fh+var_B0]
0x18003414d  mov     [rsp+130h+var_108], rax
0x180034152  mov     dword ptr [rsp+130h+var_110], 6
0x18003415a  call    cs:__imp_EtwEventWriteTransfer
0x180034160  mov     r8, [rbp+4Fh+var_C0]
0x180034164  mov     rcx, cs:WPP_GLOBAL_Control
0x18003416b  lea     rax, WPP_GLOBAL_Control
0x180034172  cmp     rcx, rax
0x180034175  jz      short loc_1800341A3
0x180034177  test    byte ptr [rcx+1Ch], 2
0x18003417b  jz      short loc_1800341A3
0x18003417d  cmp     byte ptr [rcx+19h], 5
0x180034181  jb      short loc_1800341A3
0x180034183  mov     rcx, [rcx+10h]
0x180034187  mov     r9d, edi
0x18003418a  mov     [rsp+130h+var_F8], rbx
0x18003418f  mov     [rsp+130h+var_100], r8
0x180034194  mov     dword ptr [rsp+130h+var_108], r13d
0x180034199  mov     dword ptr [rsp+130h+var_110], r14d
0x18003419e  call    WPP_SF_LDDIi
0x1800341a3  lea     eax, [r14-1]
0x1800341a7  cmp     eax, 1Ah
0x1800341aa  mov     eax, cs:dword_18009A080
0x1800341b0  ja      loc_18003431D
0x1800341b6  cmp     r14d, r13d
0x1800341b9  jb      loc_180034247
0x1800341bf  cmp     eax, 5
0x1800341c2  jbe     short loc_18003423E
0x1800341c4  test    edi, edi
0x1800341c6  jz      short loc_1800341D6
0x1800341c8  cmp     edi, 1
0x1800341cb  jnz     short loc_1800341DD
0x1800341cd  lea     rsi, aIpv6; "IPv6"
0x1800341d4  jmp     short loc_1800341DD
0x1800341d6  lea     rsi, aIpv4; "IPv4"
0x1800341dd  lea     rax, aHopcountIsGrea; "hopCount is greater than minimumInterne"...
0x1800341e4  mov     [rbp+4Fh+var_C0], rsi
0x1800341e8  mov     [rsp+130h+var_D0], rax
0x1800341ed  lea     rdx, byte_180088CE3
0x1800341f4  lea     rax, aReturningPacke; "Returning packetType is InternetPacket"
0x1800341fb  mov     [rsp+130h+var_E0], r13d
0x180034200  mov     [rbp+4Fh+var_C8], rax
0x180034204  lea     rax, [rbp+4Fh+var_C0]
0x180034208  mov     [rsp+130h+var_F0], rax
0x18003420d  lea     rax, [rsp+130h+var_E0]
0x180034212  mov     [rsp+130h+var_F8], rax
0x180034217  lea     rax, [rsp+130h+var_D8]
0x18003421c  mov     [rsp+130h+var_100], rax
0x180034221  lea     rax, [rsp+130h+var_D0]
0x180034226  mov     [rsp+130h+var_108], rax
0x18003422b  lea     rax, [rbp+4Fh+var_C8]
0x18003422f  mov     [rsp+130h+var_110], rax
0x180034234  mov     dword ptr [rsp+130h+var_D8], r14d
0x180034239  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003423e  mov     [r12], r15d
0x180034242  jmp     loc_180034397
0x180034247  cmp     r14d, 1
0x18003424b  jbe     loc_1800342DD
0x180034251  cmp     eax, 5
0x180034254  jbe     short loc_1800342D0
0x180034256  test    edi, edi
0x180034258  jz      short loc_180034268
0x18003425a  cmp     edi, 1
0x18003425d  jnz     short loc_18003426F
0x18003425f  lea     rsi, aIpv6; "IPv6"
0x180034266  jmp     short loc_18003426F
0x180034268  lea     rsi, aIpv4; "IPv4"
0x18003426f  lea     rax, aHopcountIsGrea_1; "hopCount is greater than 1 but less tha"...
0x180034276  mov     [rbp+4Fh+var_C0], rsi
0x18003427a  mov     [rsp+130h+var_D0], rax
0x18003427f  lea     rdx, byte_180088D3F
0x180034286  lea     rax, aReturningPacke_0; "Returning packetType is LocalPacket"
0x18003428d  mov     [rsp+130h+var_E0], r13d
0x180034292  mov     [rbp+4Fh+var_C8], rax
0x180034296  lea     rax, [rbp+4Fh+var_C0]
0x18003429a  mov     [rsp+130h+var_F0], rax
0x18003429f  lea     rax, [rsp+130h+var_E0]
0x1800342a4  mov     [rsp+130h+var_F8], rax
0x1800342a9  lea     rax, [rsp+130h+var_D8]
0x1800342ae  mov     [rsp+130h+var_100], rax
0x1800342b3  lea     rax, [rsp+130h+var_D0]
0x1800342b8  mov     [rsp+130h+var_108], rax
0x1800342bd  lea     rax, [rbp+4Fh+var_C8]
0x1800342c1  mov     [rsp+130h+var_110], rax
0x1800342c6  mov     dword ptr [rsp+130h+var_D8], r14d
0x1800342cb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800342d0  mov     dword ptr [r12], 1
0x1800342d8  jmp     loc_180034397
0x1800342dd  cmp     eax, 5
0x1800342e0  jbe     loc_18003438F
0x1800342e6  test    edi, edi
0x1800342e8  jz      short loc_180034306
0x1800342ea  cmp     edi, 1
0x1800342ed  jnz     short loc_18003430D
0x1800342ef  lea     rsi, aIpv6; "IPv6"
0x1800342f6  lea     rax, aHopcountIsLess; "hopCount is less than 1"
0x1800342fd  lea     rdx, word_180088C52
0x180034304  jmp     short loc_180034349
0x180034306  lea     rsi, aIpv4; "IPv4"
0x18003430d  lea     rax, aHopcountIsLess; "hopCount is less than 1"
0x180034314  lea     rdx, word_180088C52
0x18003431b  jmp     short loc_180034349
0x18003431d  cmp     eax, 5
0x180034320  jbe     short loc_18003438F
0x180034322  test    edi, edi
0x180034324  jz      short loc_180034334
0x180034326  cmp     edi, 1
0x180034329  jnz     short loc_18003433B
0x18003432b  lea     rsi, aIpv6; "IPv6"
0x180034332  jmp     short loc_18003433B
0x180034334  lea     rsi, aIpv4; "IPv4"
0x18003433b  lea     rax, aHopcountIsGrea_0; "hopCount is greater than or equal to 28"...
0x180034342  lea     rdx, byte_180088DF7
0x180034349  mov     [rsp+130h+var_D0], rax
0x18003434e  lea     rax, aReturningPacke_1; "Returning packetType is SubnetPacket"
0x180034355  mov     [rsp+130h+var_D8], rax
0x18003435a  lea     rax, [rbp+4Fh+var_C0]
0x18003435e  mov     [rsp+130h+var_F8], rax
0x180034363  lea     rax, [rsp+130h+var_E0]
0x180034368  mov     [rsp+130h+var_100], rax
0x18003436d  lea     rax, [rsp+130h+var_D0]
0x180034372  mov     [rsp+130h+var_108], rax
0x180034377  lea     rax, [rsp+130h+var_D8]
0x18003437c  mov     [rsp+130h+var_110], rax
0x180034381  mov     [rbp+4Fh+var_C0], rsi
0x180034385  mov     [rsp+130h+var_E0], r14d
0x18003438a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003438f  mov     dword ptr [r12], 2
0x180034397  mov     r13, [rsp+130h+arg_8]
0x18003439f  xor     eax, eax
0x1800343a1  mov     rcx, [rbp+4Fh+var_40]
0x1800343a5  xor     rcx, rsp; StackCookie
0x1800343a8  call    __security_check_cookie
0x1800343ad  add     rsp, 100h
0x1800343b4  pop     r15
0x1800343b6  pop     r14
0x1800343b8  pop     r12
0x1800343ba  pop     rdi
0x1800343bb  pop     rsi
0x1800343bc  pop     rbx
0x1800343bd  pop     rbp
0x1800343be  retn
  ... truncated ...
```
