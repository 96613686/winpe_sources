# RegisterRouteChangeNotificationForAllRoutingDomains

- ea: `0x1800433a0`
- end: `0x1800435ad`
- name: `RegisterRouteChangeNotificationForAllRoutingDomains`
- size: `525`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180020238`
- `0x1800208c4`

## callees

- `0x180011790`
- `0x1800433a0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!NotifyRouteChange2` at `0x1800434b1`
- `IPHLPAPI!NotifyRouteChange2` at `0x1800434b1`
- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x180043426`
- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x180043426`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18004342f`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18004351e`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18004342f`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18004351e`

## string_xrefs

- `0x18004344b`: `ERROR:PostRouteChangeNotification: SetCurrentCompartmentId failed with error %d`
- `0x180043534`: `ERROR:PostRouteChangeNotification: SetCurrentThreadCompartmentScope 2 failed with error %d`

## pseudocode

```c
__int64 __fastcall RegisterRouteChangeNotificationForAllRoutingDomains(int a1)
{
  NTSTATUS v2; // eax
  unsigned int v3; // edi
  GUID *v4; // r9
  HANDLE *NotificationHandle; // rax
  ADDRESS_FAMILY v6; // cx
  NTSTATUS v7; // eax
  UINT32 CompartmentScope; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 CompartmentId; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v11; // [rsp+38h] [rbp-C8h] BYREF
  GUID v12; // [rsp+48h] [rbp-B8h] BYREF
  int v13; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v14; // [rsp+5Ch] [rbp-A4h]
  __int128 v15; // [rsp+6Ch] [rbp-94h]
  int v16; // [rsp+7Ch] [rbp-84h]
  int v17; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v18[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  CompartmentId = 1;
  CompartmentScope = 0;
  v17 = 0;
  v12 = GUID_NULL;
  memset_0(v18, 0, sizeof(v18));
  v13 = 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  v11 = 0;
  GetCurrentThreadCompartmentScope(&CompartmentScope, &CompartmentId);
  v2 = SetCurrentThreadCompartmentScope(0xFFFFFFFF);
  v3 = v2;
  if ( v2 >= 0 )
  {
    NotificationHandle = &g_hRouteChangeNotificationV4;
    if ( a1 != 33 )
      NotificationHandle = &g_hRouteChangeNotificationV6;
    v6 = 2;
    if ( a1 != 33 )
      v6 = 23;
    v7 = NotifyRouteChange2(v6, (PIPFORWARD_CHANGE_CALLBACK)OnRouteChange, (PVOID)1, 1u, NotificationHandle);
    if ( v7 < 0 && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v17) = 0;
      LOWORD(v13) = 0;
      FormatRRASErrorString(
        &v17,
        L"ERROR:PostRouteChangeNotification: NotifyRouteChange2 failed with error %d",
        (unsigned int)v7);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v17,
          (unsigned int)&v11,
          0,
          (__int64)&v13);
    }
    v3 = SetCurrentThreadCompartmentScope(CompartmentScope);
    if ( v3 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v17) = 0;
        LOWORD(v13) = 0;
        FormatRRASErrorString(
          &v17,
          L"ERROR:PostRouteChangeNotification: SetCurrentThreadCompartmentScope 2 failed with error %d",
          v3);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v4 = &v12;
          goto LABEL_17;
        }
      }
    }
  }
  else if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v17) = 0;
    LOWORD(v13) = 0;
    FormatRRASErrorString(
      &v17,
      L"ERROR:PostRouteChangeNotification: SetCurrentCompartmentId failed with error %d",
      (unsigned int)v2);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v4 = (GUID *)&v11;
LABEL_17:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v17,
        (_DWORD)v4,
        0,
        (__int64)&v13);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800433a0  mov     [rsp-8+arg_0], rbx
0x1800433a5  mov     [rsp-8+arg_8], rdi
0x1800433aa  push    rbp
0x1800433ab  lea     rbp, [rsp-790h]
0x1800433b3  sub     rsp, 890h
0x1800433ba  mov     rax, cs:__security_cookie
0x1800433c1  xor     rax, rsp
0x1800433c4  mov     [rbp+790h+var_10], rax
0x1800433cb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800433d2  mov     ebx, ecx
0x1800433d4  mov     [rsp+890h+CompartmentId], 1
0x1800433dc  xor     eax, eax
0x1800433de  mov     [rsp+890h+CompartmentScope], 0
0x1800433e6  xor     edx, edx; Val
0x1800433e8  mov     [rbp+790h+var_810], eax
0x1800433eb  mov     r8d, 7FCh; Size
0x1800433f1  lea     rcx, [rbp+790h+var_80C]; void *
0x1800433f5  movdqu  [rsp+890h+var_848], xmm0
0x1800433fb  call    memset_0
0x180043400  xorps   xmm0, xmm0
0x180043403  lea     rdx, [rsp+890h+CompartmentId]; CompartmentId
0x180043408  xor     eax, eax
0x18004340a  lea     rcx, [rsp+890h+CompartmentScope]; CompartmentScope
0x18004340f  mov     [rsp+890h+var_838], eax
0x180043413  movups  [rsp+890h+var_834], xmm0
0x180043418  mov     [rsp+890h+var_814], eax
0x18004341c  movups  [rsp+890h+var_824], xmm0
0x180043421  movups  [rsp+890h+var_858], xmm0
0x180043426  call    cs:__imp_GetCurrentThreadCompartmentScope
0x18004342c  or      ecx, 0FFFFFFFFh; CompartmentScope
0x18004342f  call    cs:__imp_SetCurrentThreadCompartmentScope
0x180043435  mov     edi, eax
0x180043437  test    eax, eax
0x180043439  jns     short loc_18004347D
0x18004343b  mov     bl, 40h ; '@'
0x18004343d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180043443  jz      loc_180043587
0x180043449  xor     ecx, ecx
0x18004344b  lea     rdx, aErrorPostroute; "ERROR:PostRouteChangeNotification: SetC"...
0x180043452  mov     word ptr [rbp+790h+var_810], cx
0x180043456  mov     r8d, eax
0x180043459  mov     word ptr [rsp+890h+var_838], cx
0x18004345e  lea     rcx, [rbp+790h+var_810]
0x180043462  call    FormatRRASErrorString
0x180043467  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004346d  jz      loc_180043587
0x180043473  lea     r9, [rsp+890h+var_858]
0x180043478  jmp     loc_18004355D
0x18004347d  lea     rcx, g_hRouteChangeNotificationV6
0x180043484  cmp     ebx, 21h ; '!'
0x180043487  lea     rax, g_hRouteChangeNotificationV4
0x18004348e  mov     r9b, 1; InitialNotification
0x180043491  cmovnz  rax, rcx
0x180043495  mov     ecx, 2
0x18004349a  mov     [rsp+890h+NotificationHandle], rax; NotificationHandle
0x18004349f  lea     edx, [rcx+15h]
0x1800434a2  cmovnz  cx, dx; AddressFamily
0x1800434a6  lea     r8d, [rdx-16h]; CallerContext
0x1800434aa  lea     rdx, OnRouteChange; Callback
0x1800434b1  call    cs:__imp_NotifyRouteChange2
0x1800434b7  mov     bl, 40h ; '@'
0x1800434b9  test    eax, eax
0x1800434bb  jns     short loc_18004351A
0x1800434bd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800434c3  jz      short loc_18004351A
0x1800434c5  xor     ecx, ecx
0x1800434c7  lea     rdx, aErrorPostroute_0; "ERROR:PostRouteChangeNotification: Noti"...
0x1800434ce  mov     word ptr [rbp+790h+var_810], cx
0x1800434d2  mov     r8d, eax
0x1800434d5  mov     word ptr [rsp+890h+var_838], cx
0x1800434da  lea     rcx, [rbp+790h+var_810]
0x1800434de  call    FormatRRASErrorString
0x1800434e3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800434e9  jz      short loc_18004351A
0x1800434eb  lea     rax, [rsp+890h+var_838]
0x1800434f0  mov     [rsp+890h+var_868], rax
0x1800434f5  lea     r9, [rsp+890h+var_858]
0x1800434fa  lea     r8, [rbp+790h+var_810]
0x1800434fe  mov     [rsp+890h+NotificationHandle], 0
0x180043507  lea     rdx, RasRtrMgrParamTraceError
0x18004350e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180043515  call    McTemplateU0zjzz_EventWriteTransfer
0x18004351a  mov     ecx, [rsp+890h+CompartmentScope]; CompartmentScope
0x18004351e  call    cs:__imp_SetCurrentThreadCompartmentScope
0x180043524  mov     edi, eax
0x180043526  test    eax, eax
0x180043528  jz      short loc_180043587
0x18004352a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180043530  jz      short loc_180043587
0x180043532  xor     eax, eax
0x180043534  lea     rdx, aErrorPostroute_1; "ERROR:PostRouteChangeNotification: SetC"...
0x18004353b  mov     r8d, edi
0x18004353e  mov     word ptr [rbp+790h+var_810], ax
0x180043542  lea     rcx, [rbp+790h+var_810]
0x180043546  mov     word ptr [rsp+890h+var_838], ax
0x18004354b  call    FormatRRASErrorString
0x180043550  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180043556  jz      short loc_180043587
0x180043558  lea     r9, [rsp+890h+var_848]
0x18004355d  lea     rax, [rsp+890h+var_838]
0x180043562  mov     [rsp+890h+var_868], rax
0x180043567  lea     r8, [rbp+790h+var_810]
0x18004356b  lea     rdx, RasRtrMgrParamTraceError
0x180043572  mov     [rsp+890h+NotificationHandle], 0
0x18004357b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180043582  call    McTemplateU0zjzz_EventWriteTransfer
0x180043587  mov     eax, edi
0x180043589  mov     rcx, [rbp+790h+var_10]
0x180043590  xor     rcx, rsp; StackCookie
0x180043593  call    __security_check_cookie
0x180043598  lea     r11, [rsp+890h+var_s0]
0x1800435a0  mov     rbx, [r11+10h]
0x1800435a4  mov     rdi, [r11+18h]
0x1800435a8  mov     rsp, r11
0x1800435ab  pop     rbp
0x1800435ac  retn
```
