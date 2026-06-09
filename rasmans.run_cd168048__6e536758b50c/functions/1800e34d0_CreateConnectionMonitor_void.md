# CreateConnectionMonitor(void)

- ea: `0x1800e34d0`
- end: `0x1800e3665`
- name: `?CreateConnectionMonitor@@YAJXZ`
- size: `405`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800c7af8`

## callees

- `0x180005bcc`
- `0x1800ab634`
- `0x1800e3480`
- `0x1800e34d0`
- `0x1800e3ca0`
- `0x1800e3cfc`
- `0x1800e3fac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3572`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e3610`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e3610`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e355e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e355e`

## string_xrefs

- `0x1800e3539`: `VpnAlloc for pTempMonitor`
- `0x1800e35df`: `VpnCriticalSectionCreate for pTempMonitor->connMonitorCs`
- `0x1800e3540`: `CreateConnectionMonitor`
- `0x1800e359d`: `CreateConnectionMonitor`
- `0x1800e35e6`: `CreateConnectionMonitor`
- `0x1800e3596`: `CreateThreadpoolTimer for pTimer`

## pseudocode

```c
__int64 CreateConnectionMonitor(void)
{
  char *v1; // rax
  char *v2; // rdi
  unsigned int v3; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax
  int v6; // eax
  int v7; // eax
  unsigned int v8; // ecx
  __int64 v9; // r8

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 15, WPP_7a80880b28e336a1e0ed3acb889178fc_Traceguids);
  if ( g_pMonitor )
    return 0;
  v1 = (char *)VpnAlloc(72);
  v2 = v1;
  if ( v1 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(LogConnectionDetails, v1, 0);
    *(_QWORD *)v2 = ThreadpoolTimer;
    if ( ThreadpoolTimer
      || ((LastError = GetLastError(), LastError > 0)
        ? (v3 = (unsigned __int16)LastError | 0x80070000)
        : (v3 = LastError),
          !LastError) )
    {
      v6 = VpnCriticalSectionCreate(&g_connMonitorCs);
      v3 = v6;
      if ( v6 < 0 )
      {
        v7 = (v6 >> 16) & 0x1FFF;
        v8 = (unsigned __int16)v3;
        if ( v7 != 7 )
          v8 = v3;
        if ( v8 )
        {
          v9 = (unsigned __int16)v3;
          if ( v7 != 7 )
            v9 = v3;
          VpnReportError("CreateConnectionMonitor", "VpnCriticalSectionCreate for pTempMonitor->connMonitorCs", v9);
          goto LABEL_23;
        }
      }
      CleanupConnectionDetails((struct _CONNECTION_DETAILS *)(v2 + 8));
      g_pMonitor = v2;
    }
    else
    {
      VpnReportError("CreateConnectionMonitor", "CreateThreadpoolTimer for pTimer", (unsigned int)LastError);
    }
    if ( (v3 & 0x80000000) == 0 )
      goto LABEL_26;
LABEL_23:
    if ( *(_QWORD *)v2 )
    {
      CloseThreadpoolTimer(*(PTP_TIMER *)v2);
      *(_QWORD *)v2 = 0;
    }
    MprCommonFree(v2);
    goto LABEL_26;
  }
  v3 = -2147024882;
  VpnReportError("CreateConnectionMonitor", "VpnAlloc for pTempMonitor", 14);
LABEL_26:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 16, WPP_7a80880b28e336a1e0ed3acb889178fc_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x1800e34d0  mov     [rsp+arg_0], rbx
0x1800e34d5  mov     [rsp+arg_8], rsi
0x1800e34da  push    rdi
0x1800e34db  sub     rsp, 20h
0x1800e34df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e34e6  lea     rsi, WPP_GLOBAL_Control
0x1800e34ed  cmp     rcx, rsi
0x1800e34f0  jz      short loc_1800E350D
0x1800e34f2  test    byte ptr [rcx+1Ch], 8
0x1800e34f6  jz      short loc_1800E350D
0x1800e34f8  mov     rcx, [rcx+10h]
0x1800e34fc  lea     r8, WPP_7a80880b28e336a1e0ed3acb889178fc_Traceguids
0x1800e3503  mov     edx, 0Fh
0x1800e3508  call    WPP_SF_
0x1800e350d  cmp     cs:?g_pMonitor@@3PEAU_CONNECTION_MONITOR@@EA, 0; _CONNECTION_MONITOR * g_pMonitor
0x1800e3515  jz      short loc_1800E351E
0x1800e3517  xor     eax, eax
0x1800e3519  jmp     loc_1800E3654
0x1800e351e  mov     ecx, 48h ; 'H'
0x1800e3523  call    VpnAlloc
0x1800e3528  mov     rdi, rax
0x1800e352b  test    rax, rax
0x1800e352e  jnz     short loc_1800E3551
0x1800e3530  lea     r8d, [rax+0Eh]
0x1800e3534  mov     ebx, 8007000Eh
0x1800e3539  lea     rdx, aVpnallocForPte; "VpnAlloc for pTempMonitor"
0x1800e3540  lea     rcx, aCreateconnecti; "CreateConnectionMonitor"
0x1800e3547  call    VpnReportError
0x1800e354c  jmp     loc_1800E362B
0x1800e3551  xor     r8d, r8d; pcbe
0x1800e3554  lea     rcx, ?LogConnectionDetails@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800e355b  mov     rdx, rdi; pv
0x1800e355e  call    cs:__imp_CreateThreadpoolTimer
0x1800e3565  nop     dword ptr [rax+rax+00h]
0x1800e356a  mov     [rdi], rax
0x1800e356d  test    rax, rax
0x1800e3570  jnz     short loc_1800E35AB
0x1800e3572  call    cs:__imp_GetLastError
0x1800e3579  nop     dword ptr [rax+rax+00h]
0x1800e357e  test    eax, eax
0x1800e3580  jg      short loc_1800E3586
0x1800e3582  mov     ebx, eax
0x1800e3584  jmp     short loc_1800E358F
0x1800e3586  movzx   ebx, ax
0x1800e3589  or      ebx, 80070000h
0x1800e358f  test    eax, eax
0x1800e3591  jz      short loc_1800E35AB
0x1800e3593  mov     r8d, eax
0x1800e3596  lea     rdx, aCreatethreadpo; "CreateThreadpoolTimer for pTimer"
0x1800e359d  lea     rcx, aCreateconnecti; "CreateConnectionMonitor"
0x1800e35a4  call    VpnReportError
0x1800e35a9  jmp     short loc_1800E3604
0x1800e35ab  lea     rcx, ?g_connMonitorCs@@3UVPN_CRITICAL_SECTION_@@A; lpCriticalSection
0x1800e35b2  call    VpnCriticalSectionCreate
0x1800e35b7  mov     ebx, eax
0x1800e35b9  test    eax, eax
0x1800e35bb  jns     short loc_1800E35F4
0x1800e35bd  sar     eax, 10h
0x1800e35c0  and     eax, 1FFFh
0x1800e35c5  movzx   ecx, bx
0x1800e35c8  cmp     eax, 7
0x1800e35cb  jz      short loc_1800E35CF
0x1800e35cd  mov     ecx, ebx
0x1800e35cf  test    ecx, ecx
0x1800e35d1  jz      short loc_1800E35F4
0x1800e35d3  movzx   r8d, bx
0x1800e35d7  cmp     eax, 7
0x1800e35da  jz      short loc_1800E35DF
0x1800e35dc  mov     r8d, ebx
0x1800e35df  lea     rdx, aVpncriticalsec_9; "VpnCriticalSectionCreate for pTempMonit"...
0x1800e35e6  lea     rcx, aCreateconnecti; "CreateConnectionMonitor"
0x1800e35ed  call    VpnReportError
0x1800e35f2  jmp     short loc_1800E3608
0x1800e35f4  lea     rcx, [rdi+8]; struct _CONNECTION_DETAILS *
0x1800e35f8  call    ?CleanupConnectionDetails@@YAXPEAU_CONNECTION_DETAILS@@@Z; CleanupConnectionDetails(_CONNECTION_DETAILS *)
0x1800e35fd  mov     cs:?g_pMonitor@@3PEAU_CONNECTION_MONITOR@@EA, rdi; _CONNECTION_MONITOR * g_pMonitor
0x1800e3604  test    ebx, ebx
0x1800e3606  jns     short loc_1800E362B
0x1800e3608  mov     rcx, [rdi]; pti
0x1800e360b  test    rcx, rcx
0x1800e360e  jz      short loc_1800E3623
0x1800e3610  call    cs:__imp_CloseThreadpoolTimer
0x1800e3617  nop     dword ptr [rax+rax+00h]
0x1800e361c  mov     qword ptr [rdi], 0
0x1800e3623  mov     rcx, rdi; lpMem
0x1800e3626  call    MprCommonFree
0x1800e362b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3632  cmp     rcx, rsi
0x1800e3635  jz      short loc_1800E3652
0x1800e3637  test    byte ptr [rcx+1Ch], 8
0x1800e363b  jz      short loc_1800E3652
0x1800e363d  mov     rcx, [rcx+10h]
0x1800e3641  lea     r8, WPP_7a80880b28e336a1e0ed3acb889178fc_Traceguids
0x1800e3648  mov     edx, 10h
0x1800e364d  call    WPP_SF_
0x1800e3652  mov     eax, ebx
0x1800e3654  mov     rbx, [rsp+28h+arg_0]
0x1800e3659  mov     rsi, [rsp+28h+arg_8]
0x1800e365e  add     rsp, 20h
0x1800e3662  pop     rdi
0x1800e3663  retn
```
