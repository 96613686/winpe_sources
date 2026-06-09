# RegisterForRoutingDomainChangeNotifications(int)

- ea: `0x180016790`
- end: `0x18001687e`
- name: `?RegisterForRoutingDomainChangeNotifications@@YAKH@Z`
- size: `238`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800115c8`
- `0x180011eb0`

## callees

- `0x18000def0`
- `0x180016790`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `IPHLPAPI!CancelMibChangeNotify2` at `0x180016812`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180016812`
- `IPHLPAPI!NotifyCompartmentChange` at `0x1800167dc`
- `IPHLPAPI!NotifyCompartmentChange` at `0x1800167dc`

## string_xrefs

- `0x1800167f3`: `RegisterForRoutingDomainChangeNotifications: NotifyCompartmentChange failed with error %d.`

## pseudocode

```c
__int64 __fastcall RegisterForRoutingDomainChangeNotifications(int a1)
{
  __int64 v2; // r8
  unsigned int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v7[2044]; // [rsp+24h] [rbp-814h] BYREF

  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  if ( a1 )
  {
    LOBYTE(v2) = 1;
    v3 = NotifyCompartmentChange(RoutingDomainChangeCallback, 0, v2, &gblhRdChangeNotif, v6);
    v4 = v3;
    if ( !v3 || (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      return v4;
    LOWORD(v6) = 0;
    FormatRRASErrorString(
      &v6,
      L"RegisterForRoutingDomainChangeNotifications: NotifyCompartmentChange failed with error %d.",
      v3);
  }
  else
  {
    v4 = 0;
    if ( !gblhRdChangeNotif )
      return v4;
    v4 = CancelMibChangeNotify2(gblhRdChangeNotif);
    if ( !v4 || (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      return v4;
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"RegisterForRoutingDomainChangeNotifications: CancelMibChangeNotify2 failed: %d.", v4);
  }
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v6);
  return v4;
}

```

## disassembly

```asm
0x180016790  push    rbx
0x180016792  sub     rsp, 830h
0x180016799  mov     rax, cs:__security_cookie
0x1800167a0  xor     rax, rsp
0x1800167a3  mov     [rsp+838h+var_18], rax
0x1800167ab  mov     ebx, ecx
0x1800167ad  xor     eax, eax
0x1800167af  lea     rcx, [rsp+838h+var_814]; void *
0x1800167b4  mov     [rsp+838h+var_818], eax
0x1800167b8  xor     edx, edx; Val
0x1800167ba  mov     r8d, 7FCh; Size
0x1800167c0  call    memset_0
0x1800167c5  test    ebx, ebx
0x1800167c7  jz      short loc_180016804
0x1800167c9  lea     r9, ?gblhRdChangeNotif@@3PEAXEA; void * gblhRdChangeNotif
0x1800167d0  mov     r8b, 1
0x1800167d3  xor     edx, edx
0x1800167d5  lea     rcx, ?RoutingDomainChangeCallback@@YAXPEAXPEAU_MIB_COMPARTMENT_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z; RoutingDomainChangeCallback(void *,_MIB_COMPARTMENT_ROW *,_MIB_NOTIFICATION_TYPE)
0x1800167dc  call    cs:__imp_NotifyCompartmentChange
0x1800167e2  mov     ebx, eax
0x1800167e4  test    eax, eax
0x1800167e6  jz      short loc_180016863
0x1800167e8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800167ef  jz      short loc_180016863
0x1800167f1  xor     ecx, ecx
0x1800167f3  lea     rdx, aRegisterforrou_0; "RegisterForRoutingDomainChangeNotificat"...
0x1800167fa  mov     word ptr [rsp+838h+var_818], cx
0x1800167ff  mov     r8d, eax
0x180016802  jmp     short loc_180016838
0x180016804  mov     rcx, cs:?gblhRdChangeNotif@@3PEAXEA; NotificationHandle
0x18001680b  xor     ebx, ebx
0x18001680d  test    rcx, rcx
0x180016810  jz      short loc_180016863
0x180016812  call    cs:__imp_CancelMibChangeNotify2
0x180016818  mov     ebx, eax
0x18001681a  test    eax, eax
0x18001681c  jz      short loc_180016863
0x18001681e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180016825  jz      short loc_180016863
0x180016827  xor     eax, eax
0x180016829  lea     rdx, aRegisterforrou; "RegisterForRoutingDomainChangeNotificat"...
0x180016830  mov     word ptr [rsp+838h+var_818], ax
0x180016835  mov     r8d, ebx
0x180016838  lea     rcx, [rsp+838h+var_818]
0x18001683d  call    FormatRRASErrorString
0x180016842  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180016849  jz      short loc_180016863
0x18001684b  lea     r8, [rsp+838h+var_818]
0x180016850  lea     rdx, RasDimTraceError
0x180016857  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001685e  call    McTemplateU0z_EventWriteTransfer
0x180016863  mov     eax, ebx
0x180016865  mov     rcx, [rsp+838h+var_18]
0x18001686d  xor     rcx, rsp; StackCookie
0x180016870  call    __security_check_cookie
0x180016875  add     rsp, 830h
0x18001687c  pop     rbx
0x18001687d  retn
```
