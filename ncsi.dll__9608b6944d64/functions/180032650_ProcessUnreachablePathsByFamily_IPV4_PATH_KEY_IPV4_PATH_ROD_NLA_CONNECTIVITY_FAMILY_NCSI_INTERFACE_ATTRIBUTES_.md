# ProcessUnreachablePathsByFamily<_IPV4_PATH_KEY,_IPV4_PATH_ROD>(_NLA_CONNECTIVITY_FAMILY,NCSI_INTERFACE_ATTRIBUTES *,ulong,Ncsi::Proxy::Info const &,TNcsiNsiTable<_IPV4_PATH_KEY,_IPV4_PATH_ROD> const &,NCSI_PASSIVE_POLL_DATA_IN const &,bool &)

- ea: `0x180032650`
- end: `0x18003300a`
- name: `??$ProcessUnreachablePathsByFamily@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@YAXW4_NLA_CONNECTIVITY_FAMILY@@PEAVNCSI_INTERFACE_ATTRIBUTES@@KAEBVInfo@Proxy@Ncsi@@AEBV?$TNcsiNsiTable@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@AEBUNCSI_PASSIVE_POLL_DATA_IN@@AEA_N@Z`
- size: `2490`
- prototype: `__int64 __fastcall(int, __int64, __int64, Ncsi::Proxy::Info *, int, int, _BYTE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180010870`

## callees

- `0x180009804`
- `0x1800099b8`
- `0x18000a6f8`
- `0x18000e350`
- `0x180017660`
- `0x18001e004`
- `0x18001fde0`
- `0x180024590`
- `0x180029b5c`
- `0x180031fac`
- `0x180032650`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800329d9`
- `ntdll!EtwEventWriteTransfer` at `0x180032abf`
- `ntdll!EtwEventWriteTransfer` at `0x180032cb0`
- `ntdll!EtwEventWriteTransfer` at `0x180032dbe`
- `ntdll!EtwEventWriteTransfer` at `0x180032eb3`
- `ntdll!EtwEventWriteTransfer` at `0x1800329d9`
- `ntdll!EtwEventWriteTransfer` at `0x180032abf`
- `ntdll!EtwEventWriteTransfer` at `0x180032cb0`
- `ntdll!EtwEventWriteTransfer` at `0x180032dbe`
- `ntdll!EtwEventWriteTransfer` at `0x180032eb3`

## string_xrefs

- `0x180032f6f`: `Found unreachable paths, network may be down`

## pseudocode

```c
__int64 __fastcall ProcessUnreachablePathsByFamily<_IPV4_PATH_KEY,_IPV4_PATH_ROD>(
        int a1,
        __int64 a2,
        __int64 a3,
        Ncsi::Proxy::Info *a4,
        int a5,
        int a6,
        _BYTE *a7)
{
  _BYTE *v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r11
  unsigned int v10; // r15d
  unsigned int v11; // esi
  int v12; // r10d
  unsigned int v13; // r9d
  unsigned int v14; // r13d
  __int64 v15; // r12
  __int64 v16; // rdi
  __int64 v17; // r14
  __int64 v18; // rsi
  char v19; // r15
  int v20; // r8d
  bool v21; // al
  const char *v22; // rcx
  __int64 result; // rax
  int v24; // edx
  int v25; // r8d
  bool IsProxyAddress; // al
  const char *v27; // rcx
  __int64 v28; // r8
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  __int64 v32; // rdx
  __int64 v33; // r8
  unsigned int v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-ACh]
  unsigned int v36; // [rsp+58h] [rbp-A8h]
  int v37; // [rsp+5Ch] [rbp-A4h] BYREF
  char v38; // [rsp+60h] [rbp-A0h] BYREF
  char v39; // [rsp+61h] [rbp-9Fh] BYREF
  unsigned int v40; // [rsp+64h] [rbp-9Ch] BYREF
  Ncsi::Proxy::Info *v41; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v42; // [rsp+70h] [rbp-90h] BYREF
  Ncsi::Proxy::Info *v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h]
  _QWORD v46[2]; // [rsp+90h] [rbp-70h] BYREF
  char *v47; // [rsp+A0h] [rbp-60h] BYREF
  int v48; // [rsp+A8h] [rbp-58h]
  int v49; // [rsp+ACh] [rbp-54h]
  char *v50; // [rsp+B0h] [rbp-50h]
  int v51; // [rsp+B8h] [rbp-48h]
  int v52; // [rsp+BCh] [rbp-44h]
  const char *v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+C8h] [rbp-38h]
  const char *v55; // [rsp+D0h] [rbp-30h]
  __int64 v56; // [rsp+D8h] [rbp-28h]
  __int64 *v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  const char *v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  unsigned int *v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  char *v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  unsigned int *v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+128h] [rbp+28h]
  char *v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]
  Ncsi::Proxy::Info **v69; // [rsp+140h] [rbp+40h]
  __int64 v70; // [rsp+148h] [rbp+48h]

  v7 = a7;
  v8 = a2;
  v9 = qword_18009DD48;
  v10 = 0;
  v11 = 0;
  LOBYTE(a2) = 0;
  v43 = a4;
  v12 = *(_DWORD *)(v8 + 4424);
  v13 = 0;
  v14 = a3;
  v37 = v12;
  LOBYTE(a3) = 0;
  v41 = (Ncsi::Proxy::Info *)a7;
  v15 = 0;
  v40 = 0;
  v34 = 0;
  v42 = a3;
  v35 = 0;
  v36 = a2;
  v46[0] = qword_18009DD48;
  v44 = qword_18009DD58;
  if ( g_nsiPathTablev4 )
  {
    v16 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      a1 = v15;
      v17 = v9 + 24 * v15;
      if ( *(_QWORD *)v8 == *(_QWORD *)(v17 + 8) )
      {
        v18 = v44 + 104LL * (unsigned int)v15;
        if ( !*(_BYTE *)(v18 + 20) || *(_BYTE *)(v18 + 21) )
        {
          if ( *(_DWORD *)(v18 + 16) > v14 )
            goto LABEL_28;
          if ( v12 < 2
            || !PathIsOnlink<_IPV4_PATH_KEY,_IPV4_PATH_ROD>(
                  (unsigned int)v15,
                  v8,
                  v9 + 24 * v15,
                  v44 + 104LL * (unsigned int)v15) )
          {
            v40 = ++v10;
          }
          if ( (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(v8, 0)
            && !(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot() )
          {
            v13 = v35;
          }
          else
          {
            IsProxyAddress = Ncsi::Proxy::Info::IsProxyAddress(v43, (const struct in_addr *)(v17 + 16));
            v13 = v35;
            v16 = WPP_GLOBAL_Control;
            if ( IsProxyAddress )
              v13 = ++v35;
          }
          if ( *(_BYTE *)(v16 + 25) < 5u || (_UNKNOWN *)v16 == &WPP_GLOBAL_Control || (*(_BYTE *)(v16 + 28) & 2) == 0 )
          {
            LOBYTE(a2) = v36;
          }
          else
          {
            v27 = "Can't connect ";
            if ( !*(_BYTE *)(v18 + 21) )
              v27 = "Unreachable";
            WPP_SF_sssDDd(
              *(_QWORD *)(v16 + 16),
              v24,
              v25,
              (unsigned int)"Remote ",
              (__int64)"path",
              (__int64)v27,
              *(_DWORD *)(v17 + 20),
              *(_DWORD *)(v17 + 16),
              *(_DWORD *)(v18 + 16));
            LOBYTE(a2) = v36;
            v16 = WPP_GLOBAL_Control;
LABEL_26:
            v13 = v35;
          }
          v9 = v46[0];
          v12 = v37;
          goto LABEL_28;
        }
        if ( *(_DWORD *)(v18 + 16) <= v14 )
        {
          v19 = PathIsOnlink<_IPV4_PATH_KEY,_IPV4_PATH_ROD>(
                  (unsigned int)v15,
                  v8,
                  v9 + 24 * v15,
                  v44 + 104LL * (unsigned int)v15);
          if ( !v19 )
            ++v34;
          if ( (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(v8, 0)
            && !(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot() )
          {
            a1 = 1;
          }
          else
          {
            v21 = Ncsi::Proxy::Info::IsProxyAddress(v43, (const struct in_addr *)(v17 + 16));
            v16 = WPP_GLOBAL_Control;
            a1 = 1;
            v20 = (unsigned __int8)v42;
            if ( v21 )
              v20 = 1;
            v42 = v20;
          }
          LODWORD(a2) = v36;
          if ( !v19 )
          {
            LODWORD(a2) = (unsigned __int8)v36;
            if ( !*(_WORD *)(v8 + 4360) )
              LODWORD(a2) = 1;
            v36 = a2;
          }
          if ( *(_BYTE *)(v16 + 25) >= 5u && (_UNKNOWN *)v16 != &WPP_GLOBAL_Control && (*(_BYTE *)(v16 + 28) & 2) != 0 )
          {
            v22 = "Can't connect ";
            if ( !*(_BYTE *)(v18 + 21) )
              v22 = "reachable";
            WPP_SF_sssDDd(
              *(_QWORD *)(v16 + 16),
              a2,
              v20,
              (unsigned int)"Remote ",
              (__int64)"path",
              (__int64)v22,
              *(_DWORD *)(v17 + 20),
              *(_DWORD *)(v17 + 16),
              *(_DWORD *)(v18 + 16));
            LOBYTE(a2) = v36;
            v16 = WPP_GLOBAL_Control;
          }
          v10 = v40;
          goto LABEL_26;
        }
      }
LABEL_28:
      v15 = (unsigned int)(v15 + 1);
      if ( (unsigned int)v15 >= g_nsiPathTablev4 )
      {
        a3 = v42;
        v11 = v34;
        v7 = v41;
        break;
      }
    }
  }
  result = (unsigned int)dword_18009A080;
  if ( (unsigned int)dword_18009A080 > 5 )
  {
    a1 = qword_18009A098;
    result = qword_18009A090;
    if ( (qword_18009A090 & 0x400000000000LL) != 0 )
    {
      result = qword_18009A098 & 0x400000000000LL;
      if ( (qword_18009A098 & 0x400000000000LL) == qword_18009A098 )
      {
        v44 = *(unsigned __int16 *)(v8 + 6);
        v43 = *(Ncsi::Proxy::Info **)v8;
        v69 = &v41;
        v67 = &v38;
        v65 = &v34;
        v63 = &v39;
        v61 = &v40;
        v59 = (const char *)&v37;
        v57 = &v44;
        v53 = (const char *)&v43;
        v47 = (char *)off_18009A088;
        v38 = a2;
        v34 = v13;
        v39 = a3;
        v68 = 1;
        v64 = 1;
        v41 = (Ncsi::Proxy::Info *)2048;
        v40 = v11;
        v37 = v10;
        v70 = 8;
        v66 = 4;
        v62 = 4;
        v60 = 4;
        v58 = 8;
        v55 = "IPv4";
        v56 = 5;
        v54 = 8;
        v46[0] = 0x50B000000LL;
        v46[1] = 0x400000000000LL;
        v48 = *(unsigned __int16 *)off_18009A088;
        v50 = byte_1800888E1;
        v52 = 1;
        v49 = 2;
        v51 = 182;
        v36 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        result = EtwEventWriteTransfer(qword_18009A0A0, v46, 0, 0, 11, &v47);
      }
    }
  }
  if ( (_BYTE)v42 )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v41 = *(Ncsi::Proxy::Info **)v8;
      v59 = "IPv4";
      v57 = (__int64 *)&v41;
      v60 = 5;
      v55 = "Successfully reached a proxy";
      v58 = 8;
      v53 = "SetProxiedInternetCapability to true";
      v47 = (char *)off_18009A088;
      v56 = 29;
      v54 = 37;
      v44 = 0x50B000000LL;
      v45 = 0;
      v48 = *(unsigned __int16 *)off_18009A088;
      v50 = byte_1800889A3;
      v49 = 2;
      v51 = 73;
      v52 = 1;
      v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(qword_18009A0A0, &v44, 0, 0, 6, &v47);
    }
    LOBYTE(a3) = 1;
    result = NCSI_INTERFACE_ATTRIBUTES::SetProxiedInternetCapability(v8, 0, a3, 13);
    if ( *(_BYTE *)(v8 + 8443) )
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        v41 = *(Ncsi::Proxy::Info **)v8;
        v60 = 5;
        v59 = "IPv6";
        v58 = 8;
        v57 = (__int64 *)&v41;
        v56 = 65;
        v55 = "Active probe over previous family was successful through a proxy";
        v53 = "SetProxiedInternetCapability to true on the other family";
        v47 = (char *)off_18009A088;
        v54 = 57;
        v44 = 0x50B000000LL;
        v45 = 0;
        v48 = *(unsigned __int16 *)off_18009A088;
        v50 = (char *)word_180088832;
        v49 = 2;
        v51 = 78;
        v52 = 1;
        v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(qword_18009A0A0, &v44, 0, 0, 6, &v47);
      }
      LOBYTE(v28) = 1;
      result = NCSI_INTERFACE_ATTRIBUTES::SetProxiedInternetCapability(v8, 1, v28, 13);
    }
    *v7 = 1;
    return result;
  }
  if ( v11 )
  {
    result = *(unsigned int *)(v8 + 4488);
    if ( (_DWORD)result == 1 || (_DWORD)result == 4 )
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        v41 = *(Ncsi::Proxy::Info **)v8;
        v45 = 0;
        v57 = (__int64 *)&v41;
        v59 = "IPv4";
        v55 = "Reached an host in a suspect state";
        v60 = 5;
        v53 = "CancelSuspectState";
        v47 = (char *)off_18009A088;
        v58 = 8;
        v56 = 35;
        v54 = 19;
        v44 = 0x50B000000LL;
        v48 = *(unsigned __int16 *)off_18009A088;
        v50 = (char *)&dword_18008888C;
        v49 = 2;
        v51 = 73;
        v52 = 1;
        v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(qword_18009A0A0, &v44, 0, 0, 6, &v47);
      }
      return NCSI_INTERFACE_ATTRIBUTES::CancelSuspectState(v8, 0, 4);
    }
    return result;
  }
  if ( !v35 )
  {
    if ( !v10 )
      return result;
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v44 = *(_QWORD *)v8;
      v43 = (Ncsi::Proxy::Info *)"Found unreachable paths, network may be down";
      v46[0] = "EnterSuspectState";
      v34 = 0;
      v42 = v10;
      v41 = (Ncsi::Proxy::Info *)"IPv4";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        a1,
        (unsigned int)&word_18008870E,
        a3,
        v13,
        (__int64)v46,
        (__int64)&v43,
        (__int64)&v44,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v34);
    }
    v32 = 0;
    v33 = 1;
    return NCSI_INTERFACE_ATTRIBUTES::EnterSuspectState(v8, v32, v33);
  }
  if ( (unsigned int)dword_18009A080 > 5 )
  {
    v41 = *(Ncsi::Proxy::Info **)v8;
    v45 = 0;
    v57 = (__int64 *)&v41;
    v59 = "IPv4";
    v55 = "Unreachable proxies";
    v60 = 5;
    v53 = "EnterSuspectState";
    v47 = (char *)off_18009A088;
    v58 = 8;
    v56 = 20;
    v54 = 18;
    v44 = 0x50B000000LL;
    v48 = *(unsigned __int16 *)off_18009A088;
    v50 = (char *)&unk_180088788;
    v49 = 2;
    v51 = 73;
    v52 = 1;
    v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_18009A0A0, &v44, 0, 0, 6, &v47);
  }
  result = NCSI_INTERFACE_ATTRIBUTES::EnterSuspectState(v8, 0, 2);
  if ( *(_BYTE *)(v8 + 8443) )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v41 = (Ncsi::Proxy::Info *)"IPv6";
      v44 = *(_QWORD *)v8;
      v43 = (Ncsi::Proxy::Info *)"Previous active probe was successful through a proxy but now fails";
      v46[0] = "EnterSuspectState on other family";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v29,
        (unsigned int)word_1800887D2,
        v30,
        v31,
        (__int64)v46,
        (__int64)&v43,
        (__int64)&v44,
        (__int64)&v41);
    }
    v32 = 1;
    v33 = 2;
    return NCSI_INTERFACE_ATTRIBUTES::EnterSuspectState(v8, v32, v33);
  }
  return result;
}

```

## disassembly

```asm
0x180032650  mov     [rsp-8+arg_0], rbx
0x180032655  push    rbp
0x180032656  push    rsi
0x180032657  push    rdi
0x180032658  push    r12
0x18003265a  push    r13
0x18003265c  push    r14
0x18003265e  push    r15
0x180032660  lea     rbp, [rsp-60h]
0x180032665  sub     rsp, 160h
0x18003266c  mov     rax, cs:__security_cookie
0x180032673  xor     rax, rsp
0x180032676  mov     [rbp+90h+var_40], rax
0x18003267a  mov     r14, [rbp+90h+arg_30]
0x180032681  mov     rbx, rdx
0x180032684  mov     r11, cs:qword_18009DD48
0x18003268b  xor     r15d, r15d
0x18003268e  mov     rax, cs:qword_18009DD58
0x180032695  xor     esi, esi
0x180032697  xor     dl, dl
0x180032699  mov     [rsp+190h+var_118], r9
0x18003269e  mov     r10d, [rbx+1148h]
0x1800326a5  xor     r9d, r9d
0x1800326a8  mov     r13d, r8d
0x1800326ab  mov     [rsp+190h+var_134], r10d
0x1800326b0  xor     r8b, r8b
0x1800326b3  mov     [rsp+190h+var_128], r14
0x1800326b8  xor     r12d, r12d
0x1800326bb  mov     [rsp+190h+var_12C], r15d
0x1800326c0  cmp     cs:?g_nsiPathTablev4@@3V?$TNcsiNsiTable@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@A, esi; TNcsiNsiTable<_IPV4_PATH_KEY,_IPV4_PATH_ROD> g_nsiPathTablev4
0x1800326c6  mov     [rsp+190h+var_140], esi
0x1800326ca  mov     [rsp+190h+var_120], r8d
0x1800326cf  mov     [rsp+190h+var_13C], r9d
0x1800326d4  mov     [rsp+190h+var_138], edx
0x1800326d8  mov     [rbp+90h+var_100], r11
0x1800326dc  mov     [rbp+90h+var_110], rax
0x1800326e0  jbe     loc_180032853
0x1800326e6  mov     rdi, cs:WPP_GLOBAL_Control
0x1800326ed  nop     dword ptr [rax]
0x1800326f0  lea     rax, [r12+r12*2]
0x1800326f4  mov     ecx, r12d
0x1800326f7  lea     r14, [r11+rax*8]
0x1800326fb  mov     rax, [r11+rax*8+8]
0x180032700  cmp     [rbx], rax
0x180032703  jnz     loc_180032835
0x180032709  imul    rsi, rcx, 68h ; 'h'
0x18003270d  add     rsi, [rbp+90h+var_110]
0x180032711  cmp     byte ptr [rsi+14h], 0
0x180032715  jz      loc_180032ACA
0x18003271b  cmp     byte ptr [rsi+15h], 0
0x18003271f  jnz     loc_180032ACA
0x180032725  cmp     [rsi+10h], r13d
0x180032729  ja      loc_180032835
0x18003272f  mov     r9, rsi
0x180032732  mov     r8, r14
0x180032735  mov     rdx, rbx
0x180032738  call    ??$PathIsOnlink@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@YA_NW4_NLA_CONNECTIVITY_FAMILY@@PEAVNCSI_INTERFACE_ATTRIBUTES@@PEAU_IPV4_PATH_KEY@@PEAU_IPV4_PATH_ROD@@@Z; PathIsOnlink<_IPV4_PATH_KEY,_IPV4_PATH_ROD>(_NLA_CONNECTIVITY_FAMILY,NCSI_INTERFACE_ATTRIBUTES *,_IPV4_PATH_KEY *,_IPV4_PATH_ROD *)
0x18003273d  movzx   r15d, al
0x180032741  test    al, al
0x180032743  jnz     short loc_180032749
0x180032745  inc     [rsp+190h+var_140]
0x180032749  xor     edx, edx
0x18003274b  mov     rcx, rbx
0x18003274e  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180032753  test    al, al
0x180032755  jz      short loc_180032760
0x180032757  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x18003275c  test    al, al
0x18003275e  jz      short loc_180032790
0x180032760  mov     rcx, [rsp+190h+var_118]; this
0x180032765  lea     rdx, [r14+10h]; struct in_addr *
0x180032769  call    ?IsProxyAddress@Info@Proxy@Ncsi@@QEBA_NAEBUin_addr@@@Z; Ncsi::Proxy::Info::IsProxyAddress(in_addr const &)
0x18003276e  mov     r8d, [rsp+190h+var_120]
0x180032773  test    al, al
0x180032775  mov     rdi, cs:WPP_GLOBAL_Control
0x18003277c  mov     ecx, 1
0x180032781  movzx   r8d, r8b
0x180032785  cmovnz  r8d, ecx
0x180032789  mov     [rsp+190h+var_120], r8d
0x18003278e  jmp     short loc_180032795
0x180032790  mov     ecx, 1
0x180032795  mov     edx, [rsp+190h+var_138]
0x180032799  test    r15b, r15b
0x18003279c  jnz     short loc_1800327B1
0x18003279e  xor     eax, eax
0x1800327a0  movzx   edx, dl
0x1800327a3  cmp     ax, [rbx+1108h]
0x1800327aa  cmovz   edx, ecx
0x1800327ad  mov     [rsp+190h+var_138], edx
0x1800327b1  cmp     byte ptr [rdi+19h], 5
0x1800327b5  jb      short loc_180032822
0x1800327b7  lea     rax, WPP_GLOBAL_Control
0x1800327be  cmp     rdi, rax
0x1800327c1  jz      short loc_180032822
0x1800327c3  test    byte ptr [rdi+1Ch], 2
0x1800327c7  jz      short loc_180032822
0x1800327c9  cmp     byte ptr [rsi+15h], 0
0x1800327cd  lea     rax, aReachable; "reachable"
0x1800327d4  lea     rcx, aCanTConnect; "Can't connect "
0x1800327db  cmovz   rcx, rax
0x1800327df  lea     r9, aRemote; "Remote "
0x1800327e6  mov     eax, [rsi+10h]
0x1800327e9  mov     dword ptr [rsp+190h+var_150], eax
0x1800327ed  mov     eax, [r14+10h]
0x1800327f1  mov     dword ptr [rsp+190h+var_158], eax
0x1800327f5  mov     eax, [r14+14h]
0x1800327f9  mov     dword ptr [rsp+190h+var_160], eax
0x1800327fd  lea     rax, aPath; "path"
0x180032804  mov     [rsp+190h+var_168], rcx
0x180032809  mov     rcx, [rdi+10h]
0x18003280d  mov     [rsp+190h+var_170], rax
0x180032812  call    WPP_SF_sssDDd
0x180032817  mov     edx, [rsp+190h+var_138]
0x18003281b  mov     rdi, cs:WPP_GLOBAL_Control
0x180032822  mov     r15d, [rsp+190h+var_12C]
0x180032827  mov     r9d, [rsp+190h+var_13C]
0x18003282c  mov     r11, [rbp+90h+var_100]
0x180032830  mov     r10d, [rsp+190h+var_134]
0x180032835  inc     r12d
0x180032838  cmp     r12d, cs:?g_nsiPathTablev4@@3V?$TNcsiNsiTable@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@A; TNcsiNsiTable<_IPV4_PATH_KEY,_IPV4_PATH_ROD> g_nsiPathTablev4
0x18003283f  jb      loc_1800326F0
0x180032845  mov     r8d, [rsp+190h+var_120]
0x18003284a  mov     esi, [rsp+190h+var_140]
0x18003284e  mov     r14, [rsp+190h+var_128]
0x180032853  mov     eax, cs:dword_18009A080
0x180032859  lea     r12, aIpv4; "IPv4"
0x180032860  lea     rdi, _TraceLoggingMetadataEnd
0x180032867  lea     r13, _TraceLoggingMetadata
0x18003286e  cmp     eax, 5
0x180032871  jbe     loc_1800329DF
0x180032877  mov     rcx, cs:qword_18009A098
0x18003287e  mov     r10, 400000000000h
0x180032888  mov     rax, cs:qword_18009A090
0x18003288f  test    r10, rax
0x180032892  jz      loc_1800329DF
0x180032898  mov     rax, rcx
0x18003289b  and     rax, r10
0x18003289e  cmp     rax, rcx
0x1800328a1  jnz     loc_1800329DF
0x1800328a7  movzx   eax, word ptr [rbx+6]
0x1800328ab  mov     [rbp+90h+var_110], rax
0x1800328af  mov     rax, [rbx]
0x1800328b2  mov     [rsp+190h+var_118], rax
0x1800328b7  lea     rax, [rsp+190h+var_128]
0x1800328bc  mov     [rbp+90h+var_50], rax
0x1800328c0  lea     rax, [rsp+190h+var_130]
0x1800328c5  mov     [rbp+90h+var_60], rax
0x1800328c9  lea     rax, [rsp+190h+var_140]
0x1800328ce  mov     [rbp+90h+var_70], rax
0x1800328d2  lea     rax, [rsp+190h+var_12F]
0x1800328d7  mov     [rbp+90h+var_80], rax
0x1800328db  lea     rax, [rsp+190h+var_12C]
0x1800328e0  mov     [rbp+90h+var_90], rax
0x1800328e4  lea     rax, [rsp+190h+var_134]
0x1800328e9  mov     [rbp+90h+var_A0], rax
0x1800328ed  lea     rax, [rbp+90h+var_110]
0x1800328f1  mov     [rbp+90h+var_B0], rax
0x1800328f5  lea     rax, [rsp+190h+var_118]
0x1800328fa  mov     [rbp+90h+var_D0], rax
0x1800328fe  movzx   eax, cs:word_1800888D7
0x180032905  mov     dword ptr [rbp+90h+var_100+4], eax
0x180032908  mov     rax, cs:off_18009A088
0x18003290f  mov     [rbp+90h+var_F0], rax
0x180032913  mov     [rsp+190h+var_130], dl
0x180032917  mov     edx, 1
0x18003291c  mov     [rsp+190h+var_140], r9d
0x180032921  xor     r9d, r9d
0x180032924  mov     [rsp+190h+var_12F], r8b
0x180032929  xor     r8d, r8d
0x18003292c  mov     [rbp+90h+var_58], rdx
0x180032930  mov     [rbp+90h+var_78], rdx
0x180032934  mov     [rsp+190h+var_128], 800h
0x18003293d  mov     [rsp+190h+var_12C], esi
0x180032941  mov     [rsp+190h+var_134], r15d
0x180032946  mov     [rbp+90h+var_48], 8
0x18003294e  mov     [rbp+90h+var_68], 4
0x180032956  mov     [rbp+90h+var_88], 4
0x18003295e  mov     [rbp+90h+var_98], 4
0x180032966  mov     [rbp+90h+var_A8], 8
0x18003296e  mov     [rbp+90h+var_C0], r12
0x180032972  mov     [rbp+90h+var_B8], 5
0x18003297a  mov     [rbp+90h+var_C8], 8
0x180032982  mov     dword ptr [rbp+90h+var_100], 0B000000h
0x180032989  mov     [rbp+90h+var_F8], r10
0x18003298d  movzx   eax, word ptr [rax]
0x180032990  mov     [rbp+90h+var_E8], eax
0x180032993  lea     rax, byte_1800888E1
0x18003299a  mov     [rbp+90h+var_E0], rax
0x18003299e  mov     rax, rdi
0x1800329a1  sub     eax, r13d
0x1800329a4  mov     [rbp+90h+var_D4], edx
0x1800329a7  mov     [rbp+90h+var_E4], 2
0x1800329ae  lea     rdx, [rbp+90h+var_100]
0x1800329b2  mov     [rbp+90h+var_D8], 0B6h
0x1800329b9  mov     [rsp+190h+var_138], eax
0x1800329bd  mov     eax, [rsp+190h+var_138]
0x1800329c1  mov     rcx, cs:qword_18009A0A0
0x1800329c8  lea     rax, [rbp+90h+var_F0]
0x1800329cc  mov     [rsp+190h+var_168], rax
0x1800329d1  mov     dword ptr [rsp+190h+var_170], 0Bh
0x1800329d9  call    cs:__imp_EtwEventWriteTransfer
0x1800329df  cmp     byte ptr [rsp+190h+var_120], 0
0x1800329e4  jz      loc_180032CD3
0x1800329ea  mov     eax, cs:dword_18009A080
0x1800329f0  cmp     eax, 5
0x1800329f3  jbe     loc_180032BB7
0x1800329f9  mov     rax, [rbx]
0x1800329fc  lea     rdx, [rbp+90h+var_110]
0x180032a00  mov     [rsp+190h+var_128], rax
0x180032a05  xor     esi, esi
0x180032a07  mov     [rbp+90h+var_A0], r12
0x180032a0b  lea     rax, [rsp+190h+var_128]
0x180032a10  mov     [rbp+90h+var_B0], rax
0x180032a14  mov     r15d, 1
0x180032a1a  mov     [rbp+90h+var_98], 5
0x180032a22  lea     rax, aSuccessfullyRe; "Successfully reached a proxy"
0x180032a29  mov     [rbp+90h+var_C0], rax
0x180032a2d  xor     r9d, r9d
0x180032a30  lea     rax, aSetproxiedinte; "SetProxiedInternetCapability to true"
0x180032a37  mov     [rbp+90h+var_A8], 8
0x180032a3f  mov     [rbp+90h+var_D0], rax
0x180032a43  xor     r8d, r8d
0x180032a46  movzx   eax, cs:word_180088999
0x180032a4d  mov     dword ptr [rbp+90h+var_110+4], eax
0x180032a50  mov     rax, cs:off_18009A088
0x180032a57  mov     [rbp+90h+var_F0], rax
0x180032a5b  mov     [rbp+90h+var_B8], 1Dh
0x180032a63  mov     [rbp+90h+var_C8], 25h ; '%'
0x180032a6b  mov     dword ptr [rbp+90h+var_110], 0B000000h
0x180032a72  mov     [rbp+90h+var_108], rsi
0x180032a76  movzx   eax, word ptr [rax]
0x180032a79  mov     [rbp+90h+var_E8], eax
0x180032a7c  lea     rax, byte_1800889A3
0x180032a83  mov     [rbp+90h+var_E0], rax
0x180032a87  mov     rax, rdi
0x180032a8a  sub     eax, r13d
0x180032a8d  mov     [rbp+90h+var_E4], 2
0x180032a94  mov     [rbp+90h+var_D8], 49h ; 'I'
0x180032a9b  mov     [rbp+90h+var_D4], r15d
0x180032a9f  mov     [rsp+190h+var_140], eax
0x180032aa3  mov     eax, [rsp+190h+var_140]
0x180032aa7  mov     rcx, cs:qword_18009A0A0
0x180032aae  lea     rax, [rbp+90h+var_F0]
0x180032ab2  mov     [rsp+190h+var_168], rax
0x180032ab7  mov     dword ptr [rsp+190h+var_170], 6
0x180032abf  call    cs:__imp_EtwEventWriteTransfer
0x180032ac5  jmp     loc_180032BBF
0x180032aca  cmp     [rsi+10h], r13d
0x180032ace  ja      loc_180032835
0x180032ad4  cmp     r10d, 2
0x180032ad8  jl      short loc_180032AEC
0x180032ada  mov     r9, rsi
0x180032add  mov     r8, r14
0x180032ae0  mov     rdx, rbx
0x180032ae3  call    ??$PathIsOnlink@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@YA_NW4_NLA_CONNECTIVITY_FAMILY@@PEAVNCSI_INTERFACE_ATTRIBUTES@@PEAU_IPV4_PATH_KEY@@PEAU_IPV4_PATH_ROD@@@Z; PathIsOnlink<_IPV4_PATH_KEY,_IPV4_PATH_ROD>(_NLA_CONNECTIVITY_FAMILY,NCSI_INTERFACE_ATTRIBUTES *,_IPV4_PATH_KEY *,_IPV4_PATH_ROD *)
0x180032ae8  test    al, al
0x180032aea  jnz     short loc_180032AF4
0x180032aec  inc     r15d
0x180032aef  mov     [rsp+190h+var_12C], r15d
0x180032af4  xor     edx, edx
0x180032af6  mov     rcx, rbx
0x180032af9  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180032afe  test    al, al
0x180032b00  jz      short loc_180032B0B
0x180032b02  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180032b07  test    al, al
0x180032b09  jz      short loc_180032B33
0x180032b0b  mov     rcx, [rsp+190h+var_118]; this
0x180032b10  lea     rdx, [r14+10h]; struct in_addr *
0x180032b14  call    ?IsProxyAddress@Info@Proxy@Ncsi@@QEBA_NAEBUin_addr@@@Z; Ncsi::Proxy::Info::IsProxyAddress(in_addr const &)
0x180032b19  mov     r9d, [rsp+190h+var_13C]
0x180032b1e  mov     rdi, cs:WPP_GLOBAL_Control
0x180032b25  test    al, al
0x180032b27  jz      short loc_180032B38
0x180032b29  inc     r9d
0x180032b2c  mov     [rsp+190h+var_13C], r9d
0x180032b31  jmp     short loc_180032B38
0x180032b33  mov     r9d, [rsp+190h+var_13C]
0x180032b38  cmp     byte ptr [rdi+19h], 5
0x180032b3c  jb      short loc_180032BAE
0x180032b3e  lea     rax, WPP_GLOBAL_Control
0x180032b45  cmp     rdi, rax
0x180032b48  jz      short loc_180032BAE
0x180032b4a  test    byte ptr [rdi+1Ch], 2
0x180032b4e  jz      short loc_180032BAE
0x180032b50  cmp     byte ptr [rsi+15h], 0
0x180032b54  lea     rax, aUnreachable; "Unreachable"
0x180032b5b  lea     rcx, aCanTConnect; "Can't connect "
0x180032b62  cmovz   rcx, rax
0x180032b66  lea     r9, aRemote; "Remote "
0x180032b6d  mov     eax, [rsi+10h]
0x180032b70  mov     dword ptr [rsp+190h+var_150], eax
0x180032b74  mov     eax, [r14+10h]
0x180032b78  mov     dword ptr [rsp+190h+var_158], eax
0x180032b7c  mov     eax, [r14+14h]
0x180032b80  mov     dword ptr [rsp+190h+var_160], eax
0x180032b84  lea     rax, aPath; "path"
0x180032b8b  mov     [rsp+190h+var_168], rcx
0x180032b90  mov     rcx, [rdi+10h]
0x180032b94  mov     [rsp+190h+var_170], rax
  ... truncated ...
```
