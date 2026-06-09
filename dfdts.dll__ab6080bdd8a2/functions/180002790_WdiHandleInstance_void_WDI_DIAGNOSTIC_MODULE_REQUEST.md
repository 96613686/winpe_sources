# WdiHandleInstance(void *,WDI_DIAGNOSTIC_MODULE_REQUEST)

- ea: `0x180002790`
- end: `0x180002b43`
- name: `?WdiHandleInstance@@YAJPEAXW4WDI_DIAGNOSTIC_MODULE_REQUEST@@@Z`
- size: `947`
- prototype: `__int64 __fastcall(__int64, int, struct _DISK_INFO *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002790`
- `0x180002c68`
- `0x180002cd0`
- `0x180002d24`
- `0x180002d64`
- `0x180002ed8`
- `0x1800034a4`
- `0x18000357c`
- `0x180005d68`
- `0x180006b10`
- `0x180008370`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x1800029d9`
- `ntdll!WinSqmSetDWORD` at `0x180002a03`
- `ntdll!WinSqmSetDWORD` at `0x180002a22`
- `ntdll!WinSqmSetDWORD` at `0x1800029d9`
- `ntdll!WinSqmSetDWORD` at `0x180002a03`
- `ntdll!WinSqmSetDWORD` at `0x180002a22`
- `ADVAPI32!EventWrite` at `0x1800028b4`
- `ADVAPI32!EventWrite` at `0x180002a6c`
- `ADVAPI32!EventWrite` at `0x1800028b4`
- `ADVAPI32!EventWrite` at `0x180002a6c`
- `wdi!WdiSetResolution` at `0x18000295b`
- `wdi!WdiSetResolution` at `0x18000295b`
- `wdi!WdiSetProblemDetectionResult` at `0x180002aca`
- `wdi!WdiSetProblemDetectionResult` at `0x180002aca`

## pseudocode

```c
__int64 __fastcall WdiHandleInstance(__int64 a1, int a2, struct _DISK_INFO *a3)
{
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  int v7; // ebx
  int v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  signed int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 *v14; // rdx
  struct _EVENT_DATA_DESCRIPTOR *p_UserData; // r9
  ULONG v16; // r8d
  char v17; // bl
  unsigned int v18; // r14d
  int v19; // eax
  DfdManager *v20; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // ebx
  DfdTSSqm *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  unsigned int v29; // [rsp+30h] [rbp-38h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-30h] BYREF
  unsigned int WDIPolicy; // [rsp+48h] [rbp-20h]
  __int64 v32; // [rsp+50h] [rbp-18h]

  v5 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids, a1, a2);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = a2 - 2;
  if ( !v7 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
      WPP_SF_(v6[2], 14, &WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids);
    v19 = WdiSetProblemDetectionResult(a1, 1);
    v5 = v19;
    if ( v19 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v5;
      v22 = 15;
LABEL_58:
      WPP_SF_qD(v21[2], v22, &WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids, a1, v19);
      return v5;
    }
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return v5;
    v27 = 16;
LABEL_62:
    WPP_SF_q(v26[2], v27, &WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids, a1);
    return v5;
  }
  v8 = v7 - 1;
  if ( v8 )
  {
    if ( v8 == 1 )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
        WPP_SF_q(v6[2], 21, &WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids, a1);
      v29 = 0;
      v9 = IsTSAppCompatEnabled((int *)&v29);
      v10 = v29;
      if ( v9 )
        v10 = 0;
      v11 = SetDFDTask(L"Microsoft-Windows-DiskDiagnosticResolver", v10 != 0);
      v5 = v11;
      v29 = v11;
      if ( g_RegHandle )
      {
        if ( v11 < 0 )
        {
          *(_QWORD *)&UserData.Size = 4;
          UserData.Ptr = (ULONGLONG)&v29;
          v14 = DFD_TS_ETW_EVENT_DISABLE_FAILURE;
          p_UserData = &UserData;
          v16 = 1;
          if ( !v10 )
            v14 = (__int64 *)&DFD_TS_ETW_EVENT_SCHEDULE_FAILURE;
        }
        else
        {
          v14 = DFD_TS_ETW_EVENT_DISABLE_SUCCESS;
          if ( !v10 )
            v14 = DFD_TS_ETW_EVENT_SCHEDULE_SUCCESS;
          p_UserData = 0;
          v16 = 0;
        }
        EventWrite(g_RegHandle, (PCEVENT_DESCRIPTOR)v14, v16, p_UserData);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, v10 != 0, v5);
    }
    return v5;
  }
  v17 = 0;
  v29 = 0;
  if ( pDfdTSSqm )
    v17 = *((_BYTE *)pDfdTSSqm + 20);
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
    WPP_SF_(v6[2], 17, &WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids);
  if ( !CheckDiskHealth((unsigned __int64)v6, &v29, a3, v17) )
  {
    v18 = v29;
    if ( v29 )
    {
      v19 = WdiSetResolution(a1, &DFDResolverDiagGuid, 0, 0, 0, 0);
      v5 = v19;
      if ( v19 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v5;
        v22 = 18;
        goto LABEL_58;
      }
      if ( !pDfdTSSqm )
        goto LABEL_43;
      v32 = 0;
      WDIPolicy = DfdManager::GetWDIPolicy(v20);
      v23 = WDIPolicy;
      DfdManager::~DfdManager((DfdManager *)&UserData);
      if ( v23 <= 4 )
      {
        if ( !*((_BYTE *)pDfdTSSqm + 20) )
          goto LABEL_43;
        WinSqmSetDWORD(*((_QWORD *)pDfdTSSqm + 1), 918, v18);
        v24 = pDfdTSSqm;
        if ( !*((_BYTE *)pDfdTSSqm + 20) )
          goto LABEL_43;
        v25 = 0;
      }
      else
      {
        if ( !*((_BYTE *)pDfdTSSqm + 20) )
          goto LABEL_43;
        WinSqmSetDWORD(*((_QWORD *)pDfdTSSqm + 1), 918, 0);
        v24 = pDfdTSSqm;
        if ( !*((_BYTE *)pDfdTSSqm + 20) )
          goto LABEL_43;
        v25 = v18;
      }
      WinSqmSetDWORD(*((_QWORD *)v24 + 1), 917, v25);
LABEL_43:
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return v5;
      v27 = 19;
      goto LABEL_62;
    }
    if ( g_RegHandle )
      EventWrite(g_RegHandle, &DFD_TS_ETW_EVENT_SMART_FAILURE_IGNORE, 0, 0);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids);
  }
  return v5;
}

```

## disassembly

```asm
0x180002790  push    rbp
0x180002792  push    rbx
0x180002793  push    rsi
0x180002794  push    rdi
0x180002795  push    r12
0x180002797  push    r14
0x180002799  mov     rbp, rsp
0x18000279c  sub     rsp, 68h
0x1800027a0  mov     rax, cs:__security_cookie
0x1800027a7  xor     rax, rsp
0x1800027aa  mov     [rbp+var_10], rax
0x1800027ae  mov     ebx, edx
0x1800027b0  mov     rsi, rcx
0x1800027b3  xor     edi, edi
0x1800027b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027bc  lea     r12, WPP_GLOBAL_Control
0x1800027c3  lea     r14, WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids
0x1800027ca  cmp     rcx, r12
0x1800027cd  jz      short loc_1800027F2
0x1800027cf  test    byte ptr [rcx+1Ch], 4
0x1800027d3  jz      short loc_1800027F2
0x1800027d5  mov     rcx, [rcx+10h]
0x1800027d9  lea     edx, [rdi+0Dh]
0x1800027dc  mov     r9, rsi
0x1800027df  mov     [rsp+68h+var_48], ebx
0x1800027e3  mov     r8, r14
0x1800027e6  call    WPP_SF_qD
0x1800027eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027f2  sub     ebx, 2
0x1800027f5  jz      loc_180002AA6
0x1800027fb  sub     ebx, 1
0x1800027fe  jz      loc_1800028EF
0x180002804  cmp     ebx, 1
0x180002807  jnz     loc_180002B28
0x18000280d  cmp     rcx, r12
0x180002810  jz      short loc_18000282A
0x180002812  test    byte ptr [rcx+1Ch], 4
0x180002816  jz      short loc_18000282A
0x180002818  mov     rcx, [rcx+10h]
0x18000281c  lea     edx, [rbx+14h]
0x18000281f  mov     r9, rsi
0x180002822  mov     r8, r14
0x180002825  call    WPP_SF_q
0x18000282a  lea     rcx, [rbp+var_38]; int *
0x18000282e  mov     [rbp+var_38], edi
0x180002831  call    ?IsTSAppCompatEnabled@@YAKPEAH@Z; IsTSAppCompatEnabled(int *)
0x180002836  mov     ebx, [rbp+var_38]
0x180002839  mov     ecx, eax
0x18000283b  xor     eax, eax
0x18000283d  test    ecx, ecx
0x18000283f  lea     rcx, aMicrosoftWindo; "Microsoft-Windows-DiskDiagnosticResolve"...
0x180002846  cmovnz  ebx, eax
0x180002849  xor     edx, edx
0x18000284b  test    ebx, ebx
0x18000284d  setnz   dl
0x180002850  call    ?SetDFDTask@@YAJPEBGW4DFD_JOB_ACTION@@@Z; SetDFDTask(ushort const *,DFD_JOB_ACTION)
0x180002855  mov     rcx, cs:?g_RegHandle@@3_KA; RegHandle
0x18000285c  mov     edi, eax
0x18000285e  mov     [rbp+var_38], eax
0x180002861  test    rcx, rcx
0x180002864  jz      short loc_1800028BA
0x180002866  test    eax, eax
0x180002868  js      short loc_180002886
0x18000286a  test    ebx, ebx
0x18000286c  lea     rax, DFD_TS_ETW_EVENT_SCHEDULE_SUCCESS
0x180002873  lea     rdx, DFD_TS_ETW_EVENT_DISABLE_SUCCESS
0x18000287a  cmovz   rdx, rax
0x18000287e  xor     r9d, r9d
0x180002881  xor     r8d, r8d
0x180002884  jmp     short loc_1800028B4
0x180002886  lea     rax, [rbp+var_38]
0x18000288a  mov     qword ptr [rbp+UserData.Size], 4
0x180002892  mov     [rbp+UserData.Ptr], rax
0x180002896  lea     rdx, DFD_TS_ETW_EVENT_DISABLE_FAILURE
0x18000289d  test    ebx, ebx
0x18000289f  lea     rax, DFD_TS_ETW_EVENT_SCHEDULE_FAILURE
0x1800028a6  lea     r9, [rbp+UserData]; UserData
0x1800028aa  mov     r8d, 1; UserDataCount
0x1800028b0  cmovz   rdx, rax; EventDescriptor
0x1800028b4  call    cs:__imp_EventWrite
0x1800028ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028c1  cmp     rcx, r12
0x1800028c4  jz      loc_180002B28
0x1800028ca  test    byte ptr [rcx+1Ch], 1
0x1800028ce  jz      loc_180002B28
0x1800028d4  mov     rcx, [rcx+10h]
0x1800028d8  xor     r9d, r9d
0x1800028db  test    ebx, ebx
0x1800028dd  mov     [rsp+68h+var_48], edi
0x1800028e1  setnz   r9b
0x1800028e5  call    WPP_SF_dD
0x1800028ea  jmp     loc_180002B28
0x1800028ef  mov     rax, cs:?pDfdTSSqm@@3PEAVDfdTSSqm@@EA; DfdTSSqm * pDfdTSSqm
0x1800028f6  xor     bl, bl
0x1800028f8  mov     [rbp+var_38], edi
0x1800028fb  test    rax, rax
0x1800028fe  jz      short loc_180002903
0x180002900  mov     bl, [rax+14h]
0x180002903  cmp     rcx, r12
0x180002906  jz      short loc_18000291F
0x180002908  test    byte ptr [rcx+1Ch], 4
0x18000290c  jz      short loc_18000291F
0x18000290e  mov     rcx, [rcx+10h]
0x180002912  mov     edx, 11h
0x180002917  mov     r8, r14
0x18000291a  call    WPP_SF_
0x18000291f  mov     r9b, bl; bool
0x180002922  lea     rdx, [rbp+var_38]; unsigned int *
0x180002926  call    ?CheckDiskHealth@@YAK_KPEAKPEAU_DISK_INFO@@_N@Z; CheckDiskHealth(unsigned __int64,ulong *,_DISK_INFO *,bool)
0x18000292b  test    eax, eax
0x18000292d  jnz     loc_180002B28
0x180002933  mov     r14d, [rbp+var_38]
0x180002937  test    r14d, r14d
0x18000293a  jz      loc_180002A53
0x180002940  xor     eax, eax
0x180002942  lea     rdx, ?DFDResolverDiagGuid@@3U_GUID@@A; _GUID DFDResolverDiagGuid
0x180002949  mov     [rsp+68h+var_40], rax
0x18000294e  xor     r9d, r9d
0x180002951  xor     r8d, r8d
0x180002954  mov     [rsp+68h+var_48], eax
0x180002958  mov     rcx, rsi
0x18000295b  call    cs:__imp_WdiSetResolution
0x180002961  mov     edi, eax
0x180002963  test    eax, eax
0x180002965  jns     short loc_180002992
0x180002967  mov     rcx, cs:WPP_GLOBAL_Control
0x18000296e  cmp     rcx, r12
0x180002971  jz      loc_180002B28
0x180002977  test    byte ptr [rcx+1Ch], 1
0x18000297b  jz      loc_180002B28
0x180002981  mov     edx, 12h
0x180002986  lea     r8, WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids
0x18000298d  jmp     loc_180002AF0
0x180002992  cmp     cs:?pDfdTSSqm@@3PEAVDfdTSSqm@@EA, 0; DfdTSSqm * pDfdTSSqm
0x18000299a  jz      loc_180002A28
0x1800029a0  mov     [rbp+var_18], 0
0x1800029a8  call    ?GetWDIPolicy@DfdManager@@AEAAKXZ; DfdManager::GetWDIPolicy(void)
0x1800029ad  lea     rcx, [rbp+UserData]; this
0x1800029b1  mov     [rbp+var_20], eax
0x1800029b4  mov     ebx, eax
0x1800029b6  call    ??1DfdManager@@QEAA@XZ; DfdManager::~DfdManager(void)
0x1800029bb  mov     rcx, cs:?pDfdTSSqm@@3PEAVDfdTSSqm@@EA; DfdTSSqm * pDfdTSSqm
0x1800029c2  cmp     ebx, 4
0x1800029c5  jbe     short loc_1800029F1
0x1800029c7  cmp     byte ptr [rcx+14h], 0
0x1800029cb  jz      short loc_180002A28
0x1800029cd  mov     rcx, [rcx+8]
0x1800029d1  xor     r8d, r8d
0x1800029d4  mov     edx, 396h
0x1800029d9  call    cs:__imp_WinSqmSetDWORD
0x1800029df  mov     rcx, cs:?pDfdTSSqm@@3PEAVDfdTSSqm@@EA; DfdTSSqm * pDfdTSSqm
0x1800029e6  cmp     byte ptr [rcx+14h], 0
0x1800029ea  jz      short loc_180002A28
0x1800029ec  mov     r8d, r14d
0x1800029ef  jmp     short loc_180002A19
0x1800029f1  cmp     byte ptr [rcx+14h], 0
0x1800029f5  jz      short loc_180002A28
0x1800029f7  mov     rcx, [rcx+8]
0x1800029fb  mov     r8d, r14d
0x1800029fe  mov     edx, 396h
0x180002a03  call    cs:__imp_WinSqmSetDWORD
0x180002a09  mov     rcx, cs:?pDfdTSSqm@@3PEAVDfdTSSqm@@EA; DfdTSSqm * pDfdTSSqm
0x180002a10  cmp     byte ptr [rcx+14h], 0
0x180002a14  jz      short loc_180002A28
0x180002a16  xor     r8d, r8d
0x180002a19  mov     rcx, [rcx+8]
0x180002a1d  mov     edx, 395h
0x180002a22  call    cs:__imp_WinSqmSetDWORD
0x180002a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a2f  cmp     rcx, r12
0x180002a32  jz      loc_180002B28
0x180002a38  test    byte ptr [rcx+1Ch], 4
0x180002a3c  jz      loc_180002B28
0x180002a42  mov     edx, 13h
0x180002a47  lea     r8, WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids
0x180002a4e  jmp     loc_180002B1C
0x180002a53  mov     rcx, cs:?g_RegHandle@@3_KA; RegHandle
0x180002a5a  test    rcx, rcx
0x180002a5d  jz      short loc_180002A72
0x180002a5f  xor     r9d, r9d; UserData
0x180002a62  lea     rdx, DFD_TS_ETW_EVENT_SMART_FAILURE_IGNORE; EventDescriptor
0x180002a69  xor     r8d, r8d; UserDataCount
0x180002a6c  call    cs:__imp_EventWrite
0x180002a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a79  cmp     rcx, r12
0x180002a7c  jz      loc_180002B28
0x180002a82  test    byte ptr [rcx+1Ch], 4
0x180002a86  jz      loc_180002B28
0x180002a8c  mov     rcx, [rcx+10h]
0x180002a90  lea     r8, WPP_450947b02e9e3dda52562310e2bb9e16_Traceguids
0x180002a97  mov     edx, 14h
0x180002a9c  call    WPP_SF_
0x180002aa1  jmp     loc_180002B28
0x180002aa6  cmp     rcx, r12
0x180002aa9  jz      short loc_180002AC2
0x180002aab  test    byte ptr [rcx+1Ch], 4
0x180002aaf  jz      short loc_180002AC2
0x180002ab1  mov     rcx, [rcx+10h]
0x180002ab5  mov     edx, 0Eh
0x180002aba  mov     r8, r14
0x180002abd  call    WPP_SF_
0x180002ac2  mov     edx, 1
0x180002ac7  mov     rcx, rsi
0x180002aca  call    cs:__imp_WdiSetProblemDetectionResult
0x180002ad0  mov     edi, eax
0x180002ad2  test    eax, eax
0x180002ad4  jns     short loc_180002B02
0x180002ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x180002add  cmp     rcx, r12
0x180002ae0  jz      short loc_180002B28
0x180002ae2  test    byte ptr [rcx+1Ch], 1
0x180002ae6  jz      short loc_180002B28
0x180002ae8  mov     edx, 0Fh
0x180002aed  mov     r8, r14
0x180002af0  mov     rcx, [rcx+10h]
0x180002af4  mov     r9, rsi
0x180002af7  mov     [rsp+68h+var_48], eax
0x180002afb  call    WPP_SF_qD
0x180002b00  jmp     short loc_180002B28
0x180002b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b09  cmp     rcx, r12
0x180002b0c  jz      short loc_180002B28
0x180002b0e  test    byte ptr [rcx+1Ch], 4
0x180002b12  jz      short loc_180002B28
0x180002b14  mov     edx, 10h
0x180002b19  mov     r8, r14
0x180002b1c  mov     rcx, [rcx+10h]
0x180002b20  mov     r9, rsi
0x180002b23  call    WPP_SF_q
0x180002b28  mov     eax, edi
0x180002b2a  mov     rcx, [rbp+var_10]
0x180002b2e  xor     rcx, rsp; StackCookie
0x180002b31  call    __security_check_cookie
0x180002b36  add     rsp, 68h
0x180002b3a  pop     r14
0x180002b3c  pop     r12
0x180002b3e  pop     rdi
0x180002b3f  pop     rsi
0x180002b40  pop     rbx
0x180002b41  pop     rbp
0x180002b42  retn
```
