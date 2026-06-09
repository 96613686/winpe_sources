# RtrMgrMIBEntryCreate

- ea: `0x180026794`
- end: `0x180026c15`
- name: `RtrMgrMIBEntryCreate`
- size: `1153`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003db00`
- `0x18003db20`

## callees

- `0x180005db0`
- `0x1800061e8`
- `0x180006730`
- `0x180008740`
- `0x18000ac60`
- `0x180026794`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180026b5d`
- `ntdll!RtlReleaseResource` at `0x180026b5d`
- `ntdll!RtlAcquireResourceShared` at `0x180026b03`
- `ntdll!RtlAcquireResourceShared` at `0x180026b03`
- `KERNEL32!LeaveCriticalSection` at `0x18002680f`
- `KERNEL32!LeaveCriticalSection` at `0x1800268ba`
- `KERNEL32!LeaveCriticalSection` at `0x180026b9c`
- `KERNEL32!LeaveCriticalSection` at `0x180026ba6`
- `KERNEL32!LeaveCriticalSection` at `0x18002680f`
- `KERNEL32!LeaveCriticalSection` at `0x1800268ba`
- `KERNEL32!LeaveCriticalSection` at `0x180026b9c`
- `KERNEL32!LeaveCriticalSection` at `0x180026ba6`
- `KERNEL32!EnterCriticalSection` at `0x1800267f4`
- `KERNEL32!EnterCriticalSection` at `0x1800268a7`
- `KERNEL32!EnterCriticalSection` at `0x180026b89`
- `KERNEL32!EnterCriticalSection` at `0x1800267f4`
- `KERNEL32!EnterCriticalSection` at `0x1800268a7`
- `KERNEL32!EnterCriticalSection` at `0x180026b89`

## string_xrefs

- `0x180026824`: `RtrMgrMIBEntryCreate`
- `0x18002686b`: `RtrMgrMIBEntryCreate: Called with invalid lpEntry`
- `0x18002688a`: `Leaving: RtrMgrMIBEntryCreate`
- `0x180026b6c`: `Leaving: RtrMgrMIBEntryCreate`
- `0x180026ac2`: `RtrMgrMIBEntryCreate: Called with invalid buffer size %d for MIB_IPFORWARDROW`
- `0x180026a09`: `RtrMgrMIBEntryCreate: Called with invalid buffer size %d for MIB_IPNETROW`
- `0x18002699f`: `RtrMgrMIBEntryCreate: Called with invalid buffer size %d for MIB_PROXYARP`

## pseudocode

```c
__int64 __fastcall RtrMgrMIBEntryCreate(int a1, unsigned int a2, _DWORD *a3, int a4)
{
  unsigned int v9; // ebx
  unsigned int v10; // eax
  int v11; // eax
  const wchar_t *v12; // rdx
  int v13; // eax
  __int64 *v14; // rax
  __int64 *v15; // rcx
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v17[3]; // [rsp+44h] [rbp-BCh] BYREF
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+54h] [rbp-ACh]
  int v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+5Ch] [rbp-A4h]
  int v22; // [rsp+60h] [rbp-A0h]
  int v23; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v16 = 0;
  v17[0] = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  EnterCriticalSection(&RouterStateLock);
  if ( !(_DWORD)RouterState )
  {
    ++HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Entered: %ws", L"RtrMgrMIBEntryCreate");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v23);
    }
    if ( !a3 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"RtrMgrMIBEntryCreate: Called with invalid lpEntry");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: RtrMgrMIBEntryCreate");
      }
      EnterCriticalSection(&RouterStateLock);
      --HIDWORD(RouterState);
      LeaveCriticalSection(&RouterStateLock);
      return 87;
    }
    if ( a1 != 10000 )
    {
      RtlAcquireResourceShared(&stru_18008C4A0, 1u);
      v14 = (__int64 *)g_leProtoCbListV6;
      v15 = (__int64 *)&g_leProtoCbListV4;
      v9 = 1003;
      if ( a4 == 33 )
        v14 = (__int64 *)g_leProtoCbListV4;
      else
        v15 = &g_leProtoCbListV6;
      while ( v14 != v15 )
      {
        if ( a1 == *((_DWORD *)v14 + 15) )
        {
          v9 = ((__int64 (__fastcall *)(_QWORD, _DWORD *))v14[27])(a2, a3);
          break;
        }
        v14 = (__int64 *)*v14;
      }
      RtlReleaseResource(&stru_18008C4A0);
      goto LABEL_44;
    }
    switch ( *a3 )
    {
      case 8:
        if ( a2 < 8 || a2 - 8 < 0x38 )
        {
          v9 = 87;
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v23) = 0;
            FormatRRASErrorString(
              &v23,
              L"RtrMgrMIBEntryCreate: Called with invalid buffer size %d for MIB_IPFORWARDROW",
              a2);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v23);
          }
          goto LABEL_44;
        }
        v19 = a3[2];
        v20 = a3[8];
        v21 = a3[4];
        v22 = a3[5];
        v18 = 8;
        v16 = a2;
        v10 = AccessIpForwardRow(7, 20, (unsigned int)&v18, (unsigned int)&v16, (__int64)a3, (__int64)v17, a4);
        goto LABEL_32;
      case 0xA:
        if ( a2 >= 8 && a2 - 8 >= 0x18 )
        {
          v19 = a3[2];
          v13 = a3[6];
          v18 = 10;
          v20 = v13;
          v16 = a2;
          v10 = AccessIpNetRow(7, 12, (unsigned int)&v18, (unsigned int)&v16, (__int64)a3, (__int64)v17, a4);
          goto LABEL_32;
        }
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_15;
        v12 = L"RtrMgrMIBEntryCreate: Called with invalid buffer size %d for MIB_IPNETROW";
        break;
      case 0x16:
        if ( a2 >= 8 && a2 - 8 >= 0xC )
        {
          v19 = a3[2];
          v20 = a3[3];
          v11 = a3[4];
          v18 = 10;
          v21 = v11;
          v16 = a2;
          v10 = AccessProxyArp(7, 0x10u, (__int64)&v18, &v16, a3, (int)v17, a4);
          goto LABEL_32;
        }
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_15;
        v12 = L"RtrMgrMIBEntryCreate: Called with invalid buffer size %d for MIB_PROXYARP";
        break;
      case 0x1F:
        v16 = a2;
        v10 = AccessIpMatchingRoute(7, 0, 0, &v16, a3, (int)v17, a4);
LABEL_32:
        v9 = v10;
        goto LABEL_44;
      default:
LABEL_15:
        v9 = 87;
LABEL_44:
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: RtrMgrMIBEntryCreate");
        EnterCriticalSection(&RouterStateLock);
        --HIDWORD(RouterState);
        LeaveCriticalSection(&RouterStateLock);
        return v9;
    }
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, v12, a2);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v23);
    goto LABEL_15;
  }
  LeaveCriticalSection(&RouterStateLock);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"error %d on RM API", 900);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v23);
  }
  return 900;
}

```

## disassembly

```asm
0x180026794  push    rbp
0x180026796  push    rbx
0x180026797  push    rsi
0x180026798  push    rdi
0x180026799  push    r12
0x18002679b  push    r13
0x18002679d  push    r14
0x18002679f  lea     rbp, [rsp-780h]
0x1800267a7  sub     rsp, 880h
0x1800267ae  mov     rax, cs:__security_cookie
0x1800267b5  xor     rax, rsp
0x1800267b8  mov     [rbp+7B0h+var_40], rax
0x1800267bf  xor     ebx, ebx
0x1800267c1  mov     r14, r8
0x1800267c4  mov     edi, edx
0x1800267c6  mov     [rsp+8B0h+var_870], ebx
0x1800267ca  mov     r12d, ecx
0x1800267cd  mov     [rsp+8B0h+var_86C], ebx
0x1800267d1  xor     edx, edx; Val
0x1800267d3  mov     [rsp+8B0h+var_840], ebx
0x1800267d7  mov     r8d, 7FCh; Size
0x1800267dd  lea     rcx, [rsp+8B0h+var_83C]; void *
0x1800267e2  mov     r13d, r9d
0x1800267e5  call    memset_0
0x1800267ea  lea     rsi, RouterStateLock
0x1800267f1  mov     rcx, rsi; lpCriticalSection
0x1800267f4  call    cs:__imp_EnterCriticalSection
0x1800267fa  cmp     dword ptr cs:RouterState, ebx
0x180026800  mov     rcx, rsi; lpCriticalSection
0x180026803  jnz     loc_180026BA6
0x180026809  inc     dword ptr cs:RouterState+4
0x18002680f  call    cs:__imp_LeaveCriticalSection
0x180026815  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18002681b  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026822  jge     short loc_18002685D
0x180026824  lea     r8, aRtrmgrmibentry_12; "RtrMgrMIBEntryCreate"
0x18002682b  mov     word ptr [rsp+8B0h+var_840], bx
0x180026830  lea     rdx, aEnteredWs; "Entered: %ws"
0x180026837  lea     rcx, [rsp+8B0h+var_840]
0x18002683c  call    FormatRRASErrorString
0x180026841  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026847  jge     short loc_18002685D
0x180026849  lea     r8, [rsp+8B0h+var_840]
0x18002684e  mov     rcx, rsi
0x180026851  lea     rdx, RasRtrmgrTraceInfo
0x180026858  call    McTemplateU0z_EventWriteTransfer
0x18002685d  test    r14, r14
0x180026860  jnz     short loc_1800268CA
0x180026862  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180026869  jz      short loc_1800268A0
0x18002686b  lea     r8, aRtrmgrmibentry_0; "RtrMgrMIBEntryCreate: Called with inval"...
0x180026872  mov     rcx, rsi
0x180026875  lea     rdx, RasRtrmgrTraceInfo
0x18002687c  call    McTemplateU0z_EventWriteTransfer
0x180026881  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180026888  jz      short loc_1800268A0
0x18002688a  lea     r8, aLeavingRtrmgrm_4; "Leaving: RtrMgrMIBEntryCreate"
0x180026891  mov     rcx, rsi
0x180026894  lea     rdx, RasRtrmgrTraceInfo
0x18002689b  call    McTemplateU0z_EventWriteTransfer
0x1800268a0  lea     rcx, RouterStateLock; lpCriticalSection
0x1800268a7  call    cs:__imp_EnterCriticalSection
0x1800268ad  dec     dword ptr cs:RouterState+4
0x1800268b3  lea     rcx, RouterStateLock; lpCriticalSection
0x1800268ba  call    cs:__imp_LeaveCriticalSection
0x1800268c0  mov     eax, 57h ; 'W'
0x1800268c5  jmp     loc_180026BF4
0x1800268ca  cmp     r12d, 2710h
0x1800268d1  jnz     loc_180026AFA
0x1800268d7  mov     ecx, 8
0x1800268dc  cmp     [r14], ecx
0x1800268df  jz      loc_180026A48
0x1800268e5  lea     edx, [rcx+2]
0x1800268e8  cmp     [r14], edx
0x1800268eb  jz      loc_1800269A8
0x1800268f1  cmp     dword ptr [r14], 16h
0x1800268f5  jz      short loc_180026936
0x1800268f7  cmp     dword ptr [r14], 1Fh
0x1800268fb  jz      short loc_180026907
0x1800268fd  mov     ebx, 57h ; 'W'
0x180026902  jmp     loc_180026B63
0x180026907  xor     edx, edx
0x180026909  mov     [rsp+8B0h+var_880], r13d
0x18002690e  lea     rax, [rsp+8B0h+var_86C]
0x180026913  mov     [rsp+8B0h+var_870], edi
0x180026917  mov     [rsp+8B0h+var_888], rax
0x18002691c  lea     r9, [rsp+8B0h+var_870]
0x180026921  xor     r8d, r8d
0x180026924  mov     [rsp+8B0h+var_890], r14
0x180026929  lea     ecx, [rdx+7]
0x18002692c  call    AccessIpMatchingRoute
0x180026931  jmp     loc_180026AA7
0x180026936  cmp     edi, ecx
0x180026938  jb      short loc_180026992
0x18002693a  lea     eax, [rdi-8]
0x18002693d  cmp     eax, 0Ch
0x180026940  jb      short loc_180026992
0x180026942  mov     eax, [r14+8]
0x180026946  lea     r9, [rsp+8B0h+var_870]
0x18002694b  mov     [rsp+8B0h+var_85C], eax
0x18002694f  lea     r8, [rsp+8B0h+var_860]
0x180026954  mov     eax, [r14+0Ch]
0x180026958  mov     [rsp+8B0h+var_858], eax
0x18002695c  mov     eax, [r14+10h]
0x180026960  mov     [rsp+8B0h+var_860], edx
0x180026964  mov     edx, 10h
0x180026969  mov     [rsp+8B0h+var_854], eax
0x18002696d  lea     rax, [rsp+8B0h+var_86C]
0x180026972  mov     [rsp+8B0h+var_880], r13d
0x180026977  mov     [rsp+8B0h+var_888], rax
0x18002697c  lea     ecx, [rdx-9]
0x18002697f  mov     [rsp+8B0h+var_890], r14
0x180026984  mov     [rsp+8B0h+var_870], edi
0x180026988  call    AccessProxyArp
0x18002698d  jmp     loc_180026AA7
0x180026992  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180026999  jz      loc_1800268FD
0x18002699f  lea     rdx, aRtrmgrmibentry_10; "RtrMgrMIBEntryCreate: Called with inval"...
0x1800269a6  jmp     short loc_180026A10
0x1800269a8  cmp     edi, ecx
0x1800269aa  jb      short loc_1800269FC
0x1800269ac  lea     eax, [rdi-8]
0x1800269af  cmp     eax, 18h
0x1800269b2  jb      short loc_1800269FC
0x1800269b4  mov     eax, [r14+8]
0x1800269b8  lea     r9, [rsp+8B0h+var_870]
0x1800269bd  mov     [rsp+8B0h+var_85C], eax
0x1800269c1  lea     r8, [rsp+8B0h+var_860]
0x1800269c6  mov     eax, [r14+18h]
0x1800269ca  mov     [rsp+8B0h+var_860], edx
0x1800269ce  mov     edx, 0Ch
0x1800269d3  mov     [rsp+8B0h+var_858], eax
0x1800269d7  lea     rax, [rsp+8B0h+var_86C]
0x1800269dc  mov     [rsp+8B0h+var_880], r13d
0x1800269e1  mov     [rsp+8B0h+var_888], rax
0x1800269e6  lea     ecx, [rdx-5]
0x1800269e9  mov     [rsp+8B0h+var_890], r14
0x1800269ee  mov     [rsp+8B0h+var_870], edi
0x1800269f2  call    AccessIpNetRow
0x1800269f7  jmp     loc_180026AA7
0x1800269fc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180026a03  jz      loc_1800268FD
0x180026a09  lea     rdx, aRtrmgrmibentry_15; "RtrMgrMIBEntryCreate: Called with inval"...
0x180026a10  mov     r8d, edi
0x180026a13  mov     word ptr [rsp+8B0h+var_840], bx
0x180026a18  lea     rcx, [rsp+8B0h+var_840]
0x180026a1d  call    FormatRRASErrorString
0x180026a22  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180026a29  jz      loc_1800268FD
0x180026a2f  lea     r8, [rsp+8B0h+var_840]
0x180026a34  mov     rcx, rsi
0x180026a37  lea     rdx, RasRtrMgrTraceError
0x180026a3e  call    McTemplateU0z_EventWriteTransfer
0x180026a43  jmp     loc_1800268FD
0x180026a48  cmp     edi, ecx
0x180026a4a  jb      short loc_180026AAE
0x180026a4c  lea     eax, [rdi-8]
0x180026a4f  cmp     eax, 38h ; '8'
0x180026a52  jb      short loc_180026AAE
0x180026a54  mov     eax, [r14+8]
0x180026a58  lea     r9, [rsp+8B0h+var_870]
0x180026a5d  mov     [rsp+8B0h+var_85C], eax
0x180026a61  lea     r8, [rsp+8B0h+var_860]
0x180026a66  mov     eax, [r14+20h]
0x180026a6a  mov     edx, 14h
0x180026a6f  mov     [rsp+8B0h+var_858], eax
0x180026a73  mov     eax, [r14+10h]
0x180026a77  mov     [rsp+8B0h+var_854], eax
0x180026a7b  mov     eax, [r14+14h]
0x180026a7f  mov     [rsp+8B0h+var_850], eax
0x180026a83  lea     rax, [rsp+8B0h+var_86C]
0x180026a88  mov     [rsp+8B0h+var_860], ecx
0x180026a8c  lea     ecx, [rdx-0Dh]
0x180026a8f  mov     [rsp+8B0h+var_880], r13d
0x180026a94  mov     [rsp+8B0h+var_888], rax
0x180026a99  mov     [rsp+8B0h+var_890], r14
0x180026a9e  mov     [rsp+8B0h+var_870], edi
0x180026aa2  call    AccessIpForwardRow
0x180026aa7  mov     ebx, eax
0x180026aa9  jmp     loc_180026B63
0x180026aae  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180026ab5  mov     ebx, 57h ; 'W'
0x180026aba  jz      loc_180026B63
0x180026ac0  xor     eax, eax
0x180026ac2  lea     rdx, aRtrmgrmibentry_6; "RtrMgrMIBEntryCreate: Called with inval"...
0x180026ac9  mov     r8d, edi
0x180026acc  mov     word ptr [rsp+8B0h+var_840], ax
0x180026ad1  lea     rcx, [rsp+8B0h+var_840]
0x180026ad6  call    FormatRRASErrorString
0x180026adb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180026ae2  jz      short loc_180026B63
0x180026ae4  lea     r8, [rsp+8B0h+var_840]
0x180026ae9  mov     rcx, rsi
0x180026aec  lea     rdx, RasRtrMgrTraceError
0x180026af3  call    McTemplateU0z_EventWriteTransfer
0x180026af8  jmp     short loc_180026B63
0x180026afa  mov     dl, 1; Wait
0x180026afc  lea     rcx, stru_18008C4A0; Resource
0x180026b03  call    cs:__imp_RtlAcquireResourceShared
0x180026b09  mov     rax, cs:g_leProtoCbListV6
0x180026b10  lea     rdx, g_leProtoCbListV6
0x180026b17  cmp     r13d, 21h ; '!'
0x180026b1b  lea     rcx, g_leProtoCbListV4
0x180026b22  mov     ebx, 3EBh
0x180026b27  cmovz   rax, cs:g_leProtoCbListV4
0x180026b2f  cmovnz  rcx, rdx
0x180026b33  cmp     rax, rcx
0x180026b36  jz      short loc_180026B56
0x180026b38  cmp     r12d, [rax+3Ch]
0x180026b3c  jz      short loc_180026B43
0x180026b3e  mov     rax, [rax]
0x180026b41  jmp     short loc_180026B33
0x180026b43  mov     rax, [rax+0D8h]
0x180026b4a  mov     rdx, r14
0x180026b4d  mov     ecx, edi
0x180026b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b54  mov     ebx, eax
0x180026b56  lea     rcx, stru_18008C4A0; Resource
0x180026b5d  call    cs:__imp_RtlReleaseResource
0x180026b63  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180026b6a  jz      short loc_180026B82
0x180026b6c  lea     r8, aLeavingRtrmgrm_4; "Leaving: RtrMgrMIBEntryCreate"
0x180026b73  mov     rcx, rsi
0x180026b76  lea     rdx, RasRtrmgrTraceInfo
0x180026b7d  call    McTemplateU0z_EventWriteTransfer
0x180026b82  lea     rcx, RouterStateLock; lpCriticalSection
0x180026b89  call    cs:__imp_EnterCriticalSection
0x180026b8f  dec     dword ptr cs:RouterState+4
0x180026b95  lea     rcx, RouterStateLock; lpCriticalSection
0x180026b9c  call    cs:__imp_LeaveCriticalSection
0x180026ba2  mov     eax, ebx
0x180026ba4  jmp     short loc_180026BF4
0x180026ba6  call    cs:__imp_LeaveCriticalSection
0x180026bac  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026bb2  mov     edi, 384h
0x180026bb7  jge     short loc_180026BF2
0x180026bb9  mov     r8d, edi
0x180026bbc  mov     word ptr [rsp+8B0h+var_840], bx
0x180026bc1  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x180026bc8  lea     rcx, [rsp+8B0h+var_840]
0x180026bcd  call    FormatRRASErrorString
0x180026bd2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180026bd8  jge     short loc_180026BF2
0x180026bda  lea     r8, [rsp+8B0h+var_840]
0x180026bdf  lea     rdx, RasRtrmgrTraceInfo
0x180026be6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026bed  call    McTemplateU0z_EventWriteTransfer
0x180026bf2  mov     eax, edi
0x180026bf4  mov     rcx, [rbp+7B0h+var_40]
0x180026bfb  xor     rcx, rsp; StackCookie
0x180026bfe  call    __security_check_cookie
0x180026c03  add     rsp, 880h
0x180026c0a  pop     r14
0x180026c0c  pop     r13
0x180026c0e  pop     r12
0x180026c10  pop     rdi
0x180026c11  pop     rsi
0x180026c12  pop     rbx
0x180026c13  pop     rbp
0x180026c14  retn
```
