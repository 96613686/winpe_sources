# RegisterInterfaceChangeNotifications(_GUID *,int)

- ea: `0x180016884`
- end: `0x180016b76`
- name: `?RegisterInterfaceChangeNotifications@@YAKPEAU_GUID@@H@Z`
- size: `754`
- prototype: `unsigned int __fastcall(struct _GUID *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014244`
- `0x180014fcc`

## callees

- `0x18000df70`
- `0x180016884`
- `0x180035d10`
- `0x1800379b0`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `IPHLPAPI!CancelMibChangeNotify2` at `0x180016a8d`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180016a8d`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180016a00`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180016b4f`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180016a00`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180016b4f`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800168b2`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800168b2`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180016a55`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180016a55`

## string_xrefs

- `0x180016944`: `RegisterInterfaceChangeNotifications: Failed to retrieve the compartment ID for routing domain: %d.`
- `0x1800169e4`: `RegisterInterfaceChangeNotifications: GetRoutingDomainConfiguration failed: %d.`
- `0x180016a1b`: `RegisterInterfaceChangeNotifications: SetCurrentThreadCompartmentId failed: %d.`
- `0x180016aef`: `RegisterInterfaceChangeNotifications: SetRoutingDomainConfiguration failed: %d.`

## pseudocode

```c
__int64 __fastcall RegisterInterfaceChangeNotifications(struct _GUID *a1, int a2)
{
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r14d
  unsigned int RoutingDomainConfiguration; // eax
  unsigned int v6; // ebx
  __int128 *v7; // r9
  const wchar_t *v8; // rdx
  __int128 *v9; // r9
  NET_IF_COMPARTMENT_ID CompartmentId; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE NotificationHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v13[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v16; // [rsp+64h] [rbp-9Ch]
  __int128 v17; // [rsp+74h] [rbp-8Ch]
  int v18; // [rsp+84h] [rbp-7Ch]
  int v19; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v20[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  CompartmentId = 0;
  v19 = 0;
  NotificationHandle = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  *(_OWORD *)v13 = 0;
  memset_0(v20, 0, sizeof(v20));
  v15 = 0;
  v18 = 0;
  v16 = 0;
  v17 = 0;
  v14 = 0;
  RoutingDomainConfiguration = GetRoutingDomainConfiguration(a1, (__int64)&CompartmentId);
  v6 = RoutingDomainConfiguration;
  if ( !RoutingDomainConfiguration )
  {
    v6 = GetRoutingDomainConfiguration(a1, (__int64)v13);
    if ( v6 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        return v6;
      LOWORD(v19) = 0;
      LOWORD(v15) = 0;
      FormatRRASErrorString(
        &v19,
        L"RegisterInterfaceChangeNotifications: GetRoutingDomainConfiguration failed: %d.",
        v6);
      goto LABEL_4;
    }
    v6 = SetCurrentThreadCompartmentId(CompartmentId);
    if ( v6 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        return v6;
      LOWORD(v19) = 0;
      LOWORD(v15) = 0;
      FormatRRASErrorString(
        &v19,
        L"RegisterInterfaceChangeNotifications: SetCurrentThreadCompartmentId failed: %d.",
        v6);
      goto LABEL_4;
    }
    if ( a2 )
    {
      v6 = NotifyIpInterfaceChange(2u, InterfaceChangeCallback, (PVOID)CompartmentId, 1u, &NotificationHandle);
      if ( v6 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v8 = L"RegisterInterfaceChangeNotifications: NotifyIpInterfaceChange failed: %d.";
          goto LABEL_27;
        }
LABEL_31:
        SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
        return v6;
      }
      v13[0] = NotificationHandle;
    }
    else if ( v13[0] )
    {
      v6 = CancelMibChangeNotify2(v13[0]);
      if ( v6 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
          goto LABEL_31;
        v8 = L"RegisterInterfaceChangeNotifications: CancelMibChangeNotify2 failed: %d.";
LABEL_27:
        LOWORD(v19) = 0;
        LOWORD(v15) = 0;
        FormatRRASErrorString(&v19, v8, v6);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v9 = &v14;
          if ( a1 )
            LODWORD(v9) = (_DWORD)a1;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v19,
            (_DWORD)v9,
            0,
            (__int64)&v15);
        }
        goto LABEL_31;
      }
      v13[0] = 0;
    }
    v6 = SetRoutingDomainConfiguration(a1, (__int64)v13);
    if ( !v6 || (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_31;
    v8 = L"RegisterInterfaceChangeNotifications: SetRoutingDomainConfiguration failed: %d.";
    goto LABEL_27;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
    return v6;
  LOWORD(v19) = 0;
  LOWORD(v15) = 0;
  FormatRRASErrorString(
    &v19,
    L"RegisterInterfaceChangeNotifications: Failed to retrieve the compartment ID for routing domain: %d.",
    RoutingDomainConfiguration);
LABEL_4:
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
  {
    v7 = &v14;
    if ( a1 )
      LODWORD(v7) = (_DWORD)a1;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDimParamTraceError,
      (unsigned int)&v19,
      (_DWORD)v7,
      0,
      (__int64)&v15);
  }
  return v6;
}

```

## disassembly

```asm
0x180016884  push    rbp
0x180016886  push    rbx
0x180016887  push    rsi
0x180016888  push    rdi
0x180016889  push    r12
0x18001688b  push    r14
0x18001688d  lea     rbp, [rsp-7A8h]
0x180016895  sub     rsp, 8A8h
0x18001689c  mov     rax, cs:__security_cookie
0x1800168a3  xor     rax, rsp
0x1800168a6  mov     [rbp+7D0h+var_40], rax
0x1800168ad  mov     esi, edx
0x1800168af  mov     rdi, rcx
0x1800168b2  call    cs:__imp_GetCurrentThreadCompartmentId
0x1800168b8  xor     ecx, ecx
0x1800168ba  mov     [rsp+8D0h+CompartmentId], 0
0x1800168c2  mov     [rbp+7D0h+var_840], ecx
0x1800168c5  xorps   xmm0, xmm0
0x1800168c8  lea     rcx, [rbp+7D0h+var_83C]; void *
0x1800168cc  mov     [rsp+8D0h+var_898], 0
0x1800168d5  xor     edx, edx; Val
0x1800168d7  mov     r8d, 7FCh; Size
0x1800168dd  mov     r14d, eax
0x1800168e0  movups  xmmword ptr [rsp+8D0h+var_890], xmm0
0x1800168e5  call    memset_0
0x1800168ea  xor     ecx, ecx
0x1800168ec  lea     r9, [rsp+8D0h+var_8A0]
0x1800168f1  xorps   xmm0, xmm0
0x1800168f4  mov     [rsp+8D0h+var_870], ecx
0x1800168f8  xor     eax, eax
0x1800168fa  xor     r8d, r8d
0x1800168fd  mov     [rbp+7D0h+var_84C], eax
0x180016900  mov     edx, 100h
0x180016905  lea     r12d, [rcx+4]
0x180016909  mov     rcx, rdi; struct _GUID *
0x18001690c  lea     rax, [rsp+8D0h+CompartmentId]
0x180016911  mov     [rsp+8D0h+var_8A0], r12d
0x180016916  movups  [rsp+8D0h+var_86C], xmm0
0x18001691b  mov     [rsp+8D0h+NotificationHandle], rax; __int64
0x180016920  movups  [rsp+8D0h+var_85C], xmm0
0x180016925  movups  [rsp+8D0h+var_880], xmm0
0x18001692a  call    GetRoutingDomainConfiguration
0x18001692f  mov     ebx, eax
0x180016931  test    eax, eax
0x180016933  jz      short loc_1800169A8
0x180016935  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18001693c  jz      loc_180016B55
0x180016942  xor     ecx, ecx
0x180016944  lea     rdx, aRegisterinterf_2; "RegisterInterfaceChangeNotifications: F"...
0x18001694b  mov     word ptr [rbp+7D0h+var_840], cx
0x18001694f  mov     r8d, eax
0x180016952  mov     word ptr [rsp+8D0h+var_870], cx
0x180016957  lea     rcx, [rbp+7D0h+var_840]
0x18001695b  call    FormatRRASErrorString
0x180016960  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180016967  jz      loc_180016B55
0x18001696d  test    rdi, rdi
0x180016970  lea     rax, [rsp+8D0h+var_870]
0x180016975  mov     [rsp+8D0h+var_8A8], rax
0x18001697a  lea     r9, [rsp+8D0h+var_880]
0x18001697f  cmovnz  r9, rdi
0x180016983  mov     [rsp+8D0h+NotificationHandle], 0
0x18001698c  lea     r8, [rbp+7D0h+var_840]
0x180016990  lea     rdx, RasDimParamTraceError
0x180016997  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001699e  call    McTemplateU0zjzz_EventWriteTransfer
0x1800169a3  jmp     loc_180016B55
0x1800169a8  lea     rax, [rsp+8D0h+var_890]
0x1800169ad  mov     [rsp+8D0h+var_8A0], 10h
0x1800169b5  lea     r9, [rsp+8D0h+var_8A0]
0x1800169ba  mov     [rsp+8D0h+NotificationHandle], rax; __int64
0x1800169bf  xor     r8d, r8d
0x1800169c2  mov     edx, 10000h
0x1800169c7  mov     rcx, rdi; struct _GUID *
0x1800169ca  call    GetRoutingDomainConfiguration
0x1800169cf  mov     ebx, eax
0x1800169d1  test    eax, eax
0x1800169d3  jz      short loc_1800169FC
0x1800169d5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800169dc  jz      loc_180016B55
0x1800169e2  xor     eax, eax
0x1800169e4  lea     rdx, aRegisterinterf_0; "RegisterInterfaceChangeNotifications: G"...
0x1800169eb  mov     word ptr [rbp+7D0h+var_840], ax
0x1800169ef  mov     r8d, ebx
0x1800169f2  mov     word ptr [rsp+8D0h+var_870], ax
0x1800169f7  jmp     loc_180016957
0x1800169fc  mov     ecx, [rsp+8D0h+CompartmentId]; CompartmentId
0x180016a00  call    cs:__imp_SetCurrentThreadCompartmentId
0x180016a06  mov     ebx, eax
0x180016a08  test    eax, eax
0x180016a0a  jz      short loc_180016A33
0x180016a0c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180016a13  jz      loc_180016B55
0x180016a19  xor     eax, eax
0x180016a1b  lea     rdx, aRegisterinterf; "RegisterInterfaceChangeNotifications: S"...
0x180016a22  mov     word ptr [rbp+7D0h+var_840], ax
0x180016a26  mov     r8d, ebx
0x180016a29  mov     word ptr [rsp+8D0h+var_870], ax
0x180016a2e  jmp     loc_180016957
0x180016a33  test    esi, esi
0x180016a35  jz      short loc_180016A83
0x180016a37  mov     r8d, [rsp+8D0h+CompartmentId]; CallerContext
0x180016a3c  lea     rax, [rsp+8D0h+var_898]
0x180016a41  mov     ecx, 2; Family
0x180016a46  mov     [rsp+8D0h+NotificationHandle], rax; NotificationHandle
0x180016a4b  mov     r9b, 1; InitialNotification
0x180016a4e  lea     rdx, ?InterfaceChangeCallback@@YAXPEAXPEAU_MIB_IPINTERFACE_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x180016a55  call    cs:__imp_NotifyIpInterfaceChange
0x180016a5b  mov     ebx, eax
0x180016a5d  test    eax, eax
0x180016a5f  jz      short loc_180016A77
0x180016a61  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180016a68  jz      loc_180016B4C
0x180016a6e  lea     rdx, aRegisterinterf_4; "RegisterInterfaceChangeNotifications: N"...
0x180016a75  jmp     short loc_180016AF6
0x180016a77  mov     rax, [rsp+8D0h+var_898]
0x180016a7c  mov     [rsp+8D0h+var_890], rax
0x180016a81  jmp     short loc_180016AB8
0x180016a83  mov     rcx, [rsp+8D0h+var_890]; NotificationHandle
0x180016a88  test    rcx, rcx
0x180016a8b  jz      short loc_180016AB8
0x180016a8d  call    cs:__imp_CancelMibChangeNotify2
0x180016a93  mov     ebx, eax
0x180016a95  test    eax, eax
0x180016a97  jz      short loc_180016AAF
0x180016a99  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180016aa0  jz      loc_180016B4C
0x180016aa6  lea     rdx, aRegisterinterf_3; "RegisterInterfaceChangeNotifications: C"...
0x180016aad  jmp     short loc_180016AF6
0x180016aaf  mov     [rsp+8D0h+var_890], 0
0x180016ab8  lea     rax, [rsp+8D0h+var_890]
0x180016abd  mov     [rsp+8D0h+var_8A0], 10h
0x180016ac5  mov     r9d, 10h
0x180016acb  mov     [rsp+8D0h+NotificationHandle], rax; __int64
0x180016ad0  xor     r8d, r8d
0x180016ad3  mov     edx, 10000h
0x180016ad8  mov     rcx, rdi; struct _GUID *
0x180016adb  call    SetRoutingDomainConfiguration
0x180016ae0  mov     ebx, eax
0x180016ae2  test    eax, eax
0x180016ae4  jz      short loc_180016B4C
0x180016ae6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180016aed  jz      short loc_180016B4C
0x180016aef  lea     rdx, aRegisterinterf_1; "RegisterInterfaceChangeNotifications: S"...
0x180016af6  xor     eax, eax
0x180016af8  lea     rcx, [rbp+7D0h+var_840]
0x180016afc  mov     r8d, ebx
0x180016aff  mov     word ptr [rbp+7D0h+var_840], ax
0x180016b03  mov     word ptr [rsp+8D0h+var_870], ax
0x180016b08  call    FormatRRASErrorString
0x180016b0d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180016b14  jz      short loc_180016B4C
0x180016b16  test    rdi, rdi
0x180016b19  lea     rax, [rsp+8D0h+var_870]
0x180016b1e  mov     [rsp+8D0h+var_8A8], rax
0x180016b23  lea     r9, [rsp+8D0h+var_880]
0x180016b28  cmovnz  r9, rdi
0x180016b2c  mov     [rsp+8D0h+NotificationHandle], 0
0x180016b35  lea     r8, [rbp+7D0h+var_840]
0x180016b39  lea     rdx, RasDimParamTraceError
0x180016b40  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016b47  call    McTemplateU0zjzz_EventWriteTransfer
0x180016b4c  mov     ecx, r14d; CompartmentId
0x180016b4f  call    cs:__imp_SetCurrentThreadCompartmentId
0x180016b55  mov     eax, ebx
0x180016b57  mov     rcx, [rbp+7D0h+var_40]
0x180016b5e  xor     rcx, rsp; StackCookie
0x180016b61  call    __security_check_cookie
0x180016b66  add     rsp, 8A8h
0x180016b6d  pop     r14
0x180016b6f  pop     r12
0x180016b71  pop     rdi
0x180016b72  pop     rsi
0x180016b73  pop     rbx
0x180016b74  pop     rbp
0x180016b75  retn
```
