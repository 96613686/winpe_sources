# AccessTcpRow

- ea: `0x1800096a0`
- end: `0x1800099a7`
- name: `AccessTcpRow`
- size: `775`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`
- `0x1800276bc`

## callees

- `0x1800096a0`
- `0x18000ac60`
- `0x18000baa8`
- `0x18002e944`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000981b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000981b`
- `ntdll!RtlReleaseResource` at `0x18000995b`
- `ntdll!RtlReleaseResource` at `0x18000995b`
- `ntdll!RtlAcquireResourceShared` at `0x180009823`
- `ntdll!RtlAcquireResourceShared` at `0x180009823`
- `IPHLPAPI!SetTcpEntry` at `0x180009911`
- `IPHLPAPI!SetTcpEntry` at `0x180009911`

## string_xrefs

- `0x180009708`: `AccessTcpRow`
- `0x180009775`: `Leaving: AccessTcpRow`
- `0x18000996a`: `Leaving: AccessTcpRow`
- `0x1800097c1`: `AccessTcpRow: Couldnt update Tcp Cache. Error %d`
- `0x1800098d0`: `AccessTcpRow: TCP State can only be set to delete. Tried to set to %d`
- `0x180009879`: `AccessTcpRow: Query type %d is wrong`

## pseudocode

```c
__int64 __fastcall AccessTcpRow(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  unsigned int v12; // eax
  DWORD updated; // eax
  DWORD TcpRow; // ebx
  char v15; // cl
  bool v16; // zf
  _OWORD *v17; // rdi
  __int64 v18; // rdx
  _DWORD *v19; // rax
  _DWORD v20[4]; // [rsp+20h] [rbp-858h] BYREF
  int v21; // [rsp+30h] [rbp-848h] BYREF
  _BYTE v22[2044]; // [rsp+34h] [rbp-844h] BYREF

  v20[0] = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v21) = 0;
    FormatRRASErrorString(&v21, L"Entered: %ws", L"AccessTcpRow");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v21);
  }
  if ( a7 == 87 )
    return 50;
  if ( a1 != 9 )
  {
    v12 = *a4;
    *a4 = 28;
    if ( v12 < 0x1C )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessTcpRow");
      return 122;
    }
    *(_DWORD *)a5 = 14;
  }
  updated = UpdateCache(4, a6);
  TcpRow = updated;
  if ( updated )
  {
    v15 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"AccessTcpRow: Couldnt update Tcp Cache. Error %d", updated);
      v15 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v21);
        v15 = Microsoft_Windows_RRASEnableBits;
      }
    }
    v16 = v15 >= 0;
  }
  else
  {
    if ( a1 == 5 )
      RtlAcquireResourceExclusive(&stru_18008C380, 1u);
    else
      RtlAcquireResourceShared(&stru_18008C380, 1u);
    TcpRow = LocateTcpRow(a1, (a2 >> 2) - 1, a3 + 4, v20);
    if ( !TcpRow )
    {
      v17 = (_OWORD *)(a5 + 8);
      if ( a1 == 1 || a1 == 2 || a1 == 4 )
      {
        TcpRow = 0;
        v18 = 5LL * v20[0];
        v19 = g_TcpInfo;
        *v17 = *(_OWORD *)((char *)g_TcpInfo + 20 * v20[0] + 4);
        *(_DWORD *)(a5 + 24) = v19[v18 + 5];
      }
      else if ( a1 == 5 )
      {
        if ( *(_DWORD *)v17 == 12 )
        {
          TcpRow = SetTcpEntry((PMIB_TCPROW)(a5 + 8));
          if ( !TcpRow )
            *((_DWORD *)g_TcpInfo + 5 * v20[0] + 1) = *(_DWORD *)v17;
        }
        else
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v21) = 0;
            FormatRRASErrorString(&v21, L"AccessTcpRow: TCP State can only be set to delete. Tried to set to %d");
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v21);
          }
          TcpRow = 13;
        }
      }
      else
      {
        if ( (char)Microsoft_Windows_RRASEnableBits < (char)TcpRow )
        {
          LOWORD(v21) = 0;
          FormatRRASErrorString(&v21, L"AccessTcpRow: Query type %d is wrong", a1);
          if ( (char)Microsoft_Windows_RRASEnableBits < (char)TcpRow )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v21);
        }
        TcpRow = 87;
      }
    }
    RtlReleaseResource(&stru_18008C380);
    v16 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
  }
  if ( !v16 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessTcpRow");
  return TcpRow;
}

```

## disassembly

```asm
0x1800096a0  push    rbx
0x1800096a2  push    rsi
0x1800096a3  push    rdi
0x1800096a4  push    r13
0x1800096a6  push    r14
0x1800096a8  push    r15
0x1800096aa  sub     rsp, 848h
0x1800096b1  mov     rax, cs:__security_cookie
0x1800096b8  xor     rax, rsp
0x1800096bb  mov     [rsp+878h+var_48], rax
0x1800096c3  mov     r14, [rsp+878h+arg_20]
0x1800096cb  mov     r13, r8
0x1800096ce  mov     r15, [rsp+878h+arg_28]
0x1800096d6  mov     edi, edx
0x1800096d8  mov     esi, ecx
0x1800096da  mov     [rsp+878h+var_858], 0
0x1800096e2  xor     eax, eax
0x1800096e4  lea     rcx, [rsp+878h+var_844]; void *
0x1800096e9  xor     edx, edx; Val
0x1800096eb  mov     [rsp+878h+var_848], eax
0x1800096ef  mov     r8d, 7FCh; Size
0x1800096f5  mov     rbx, r9
0x1800096f8  call    memset_0
0x1800096fd  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180009704  jge     short loc_180009746
0x180009706  xor     eax, eax
0x180009708  lea     r8, aAccesstcprow; "AccessTcpRow"
0x18000970f  lea     rdx, aEnteredWs; "Entered: %ws"
0x180009716  mov     word ptr [rsp+878h+var_848], ax
0x18000971b  lea     rcx, [rsp+878h+var_848]
0x180009720  call    FormatRRASErrorString
0x180009725  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000972c  jge     short loc_180009746
0x18000972e  lea     r8, [rsp+878h+var_848]
0x180009733  lea     rdx, RasRtrmgrTraceInfo
0x18000973a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009741  call    McTemplateU0z_EventWriteTransfer
0x180009746  cmp     [rsp+878h+arg_30], 57h ; 'W'
0x18000974e  jnz     short loc_18000975A
0x180009750  mov     eax, 32h ; '2'
0x180009755  jmp     loc_180009986
0x18000975a  cmp     esi, 9
0x18000975d  jz      short loc_1800097A0
0x18000975f  mov     eax, [rbx]
0x180009761  mov     dword ptr [rbx], 1Ch
0x180009767  cmp     eax, 1Ch
0x18000976a  jnb     short loc_180009799
0x18000976c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009773  jz      short loc_18000978F
0x180009775  lea     r8, aLeavingAccesst; "Leaving: AccessTcpRow"
0x18000977c  lea     rdx, RasRtrmgrTraceInfo
0x180009783  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000978a  call    McTemplateU0z_EventWriteTransfer
0x18000978f  mov     eax, 7Ah ; 'z'
0x180009794  jmp     loc_180009986
0x180009799  mov     dword ptr [r14], 0Eh
0x1800097a0  mov     rdx, r15
0x1800097a3  mov     ecx, 4
0x1800097a8  call    UpdateCache
0x1800097ad  mov     ebx, eax
0x1800097af  test    eax, eax
0x1800097b1  jz      short loc_18000980D
0x1800097b3  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800097ba  test    cl, 40h
0x1800097bd  jz      short loc_180009805
0x1800097bf  xor     ecx, ecx
0x1800097c1  lea     rdx, aAccesstcprowCo; "AccessTcpRow: Couldnt update Tcp Cache."...
0x1800097c8  mov     word ptr [rsp+878h+var_848], cx
0x1800097cd  mov     r8d, eax
0x1800097d0  lea     rcx, [rsp+878h+var_848]
0x1800097d5  call    FormatRRASErrorString
0x1800097da  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800097e1  test    cl, 40h
0x1800097e4  jz      short loc_180009805
0x1800097e6  lea     r8, [rsp+878h+var_848]
0x1800097eb  lea     rdx, RasRtrMgrTraceError
0x1800097f2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800097f9  call    McTemplateU0z_EventWriteTransfer
0x1800097fe  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180009805  test    cl, 80h
0x180009808  jmp     loc_180009968
0x18000980d  lea     rcx, stru_18008C380; Resource
0x180009814  mov     dl, 1; Wait
0x180009816  cmp     esi, 5
0x180009819  jnz     short loc_180009823
0x18000981b  call    cs:__imp_RtlAcquireResourceExclusive
0x180009821  jmp     short loc_180009829
0x180009823  call    cs:__imp_RtlAcquireResourceShared
0x180009829  shr     edi, 2
0x18000982c  lea     r8, [r13+4]
0x180009830  lea     r9, [rsp+878h+var_858]
0x180009835  mov     ecx, esi
0x180009837  lea     edx, [rdi-1]
0x18000983a  call    LocateTcpRow
0x18000983f  mov     ebx, eax
0x180009841  test    eax, eax
0x180009843  jnz     loc_180009954
0x180009849  mov     eax, esi
0x18000984b  lea     rdi, [r14+8]
0x18000984f  sub     eax, 1
0x180009852  jz      loc_180009934
0x180009858  sub     eax, 1
0x18000985b  jz      loc_180009934
0x180009861  sub     eax, 2
0x180009864  jz      loc_180009934
0x18000986a  cmp     eax, 1
0x18000986d  jz      short loc_1800098BC
0x18000986f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180009875  jge     short loc_1800098B2
0x180009877  xor     eax, eax
0x180009879  lea     rdx, aAccesstcprowQu; "AccessTcpRow: Query type %d is wrong"
0x180009880  mov     r8d, esi
0x180009883  mov     word ptr [rsp+878h+var_848], ax
0x180009888  lea     rcx, [rsp+878h+var_848]
0x18000988d  call    FormatRRASErrorString
0x180009892  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180009898  jge     short loc_1800098B2
0x18000989a  lea     r8, [rsp+878h+var_848]
0x18000989f  lea     rdx, RasRtrmgrTraceInfo
0x1800098a6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800098ad  call    McTemplateU0z_EventWriteTransfer
0x1800098b2  mov     ebx, 57h ; 'W'
0x1800098b7  jmp     loc_180009954
0x1800098bc  mov     r8d, [rdi]
0x1800098bf  cmp     r8d, 0Ch
0x1800098c3  jz      short loc_18000990E
0x1800098c5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800098cc  jge     short loc_180009907
0x1800098ce  xor     eax, eax
0x1800098d0  lea     rdx, aAccesstcprowTc; "AccessTcpRow: TCP State can only be set"...
0x1800098d7  lea     rcx, [rsp+878h+var_848]
0x1800098dc  mov     word ptr [rsp+878h+var_848], ax
0x1800098e1  call    FormatRRASErrorString
0x1800098e6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800098ed  jge     short loc_180009907
0x1800098ef  lea     r8, [rsp+878h+var_848]
0x1800098f4  lea     rdx, RasRtrmgrTraceInfo
0x1800098fb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009902  call    McTemplateU0z_EventWriteTransfer
0x180009907  mov     ebx, 0Dh
0x18000990c  jmp     short loc_180009954
0x18000990e  mov     rcx, rdi; pTcpRow
0x180009911  call    cs:__imp_SetTcpEntry
0x180009917  mov     ebx, eax
0x180009919  test    eax, eax
0x18000991b  jnz     short loc_180009954
0x18000991d  mov     eax, [rsp+878h+var_858]
0x180009921  mov     ecx, [rdi]
0x180009923  lea     rdx, [rax+rax*4]
0x180009927  mov     rax, cs:g_TcpInfo
0x18000992e  mov     [rax+rdx*4+4], ecx
0x180009932  jmp     short loc_180009954
0x180009934  mov     eax, [rsp+878h+var_858]
0x180009938  xor     ebx, ebx
0x18000993a  lea     rdx, [rax+rax*4]
0x18000993e  mov     rax, cs:g_TcpInfo
0x180009945  movups  xmm0, xmmword ptr [rax+rdx*4+4]
0x18000994a  movups  xmmword ptr [rdi], xmm0
0x18000994d  mov     eax, [rax+rdx*4+14h]
0x180009951  mov     [rdi+10h], eax
0x180009954  lea     rcx, stru_18008C380; Resource
0x18000995b  call    cs:__imp_RtlReleaseResource
0x180009961  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009968  jz      short loc_180009984
0x18000996a  lea     r8, aLeavingAccesst; "Leaving: AccessTcpRow"
0x180009971  lea     rdx, RasRtrmgrTraceInfo
0x180009978  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000997f  call    McTemplateU0z_EventWriteTransfer
0x180009984  mov     eax, ebx
0x180009986  mov     rcx, [rsp+878h+var_48]
0x18000998e  xor     rcx, rsp; StackCookie
0x180009991  call    __security_check_cookie
0x180009996  add     rsp, 848h
0x18000999d  pop     r15
0x18000999f  pop     r14
0x1800099a1  pop     r13
0x1800099a3  pop     rdi
0x1800099a4  pop     rsi
0x1800099a5  pop     rbx
0x1800099a6  retn
```
