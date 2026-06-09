# RegisterIpAddressChangeNotifications

- ea: `0x1800523a8`
- end: `0x18005258d`
- name: `RegisterIpAddressChangeNotifications`
- size: `485`
- prototype: `__int64 __fastcall(unsigned int, struct _GUID *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180020238`
- `0x1800208c4`
- `0x1800236d4`

## callees

- `0x180011790`
- `0x1800523a8`
- `0x180057b34`
- `0x180057d8c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800523e2`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800523e2`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18005242e`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18005255f`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18005242e`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18005255f`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x1800524d6`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x1800524d6`

## string_xrefs

- `0x180052449`: `RegisterIpAddressChangeNotifications: SetCurrentCompartmentId failed with error %d`

## pseudocode

```c
__int64 __fastcall RegisterIpAddressChangeNotifications(unsigned int a1, struct _GUID *a2)
{
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r14d
  NET_IF_COMPARTMENT_ID CompartmentIdForRoutingDomain; // eax
  void *v6; // r15
  unsigned int v7; // eax
  unsigned int v8; // ebx
  __int128 *v9; // r9
  ADDRESS_FAMILY v10; // cx
  __int128 *v11; // r9
  HANDLE NotificationHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+4Ch] [rbp-B4h]
  __int128 v17; // [rsp+5Ch] [rbp-A4h]
  int v18; // [rsp+6Ch] [rbp-94h]
  int v19; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  NotificationHandle = 0;
  v19 = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  memset_0(v20, 0, sizeof(v20));
  v15 = 0;
  v18 = 0;
  v16 = 0;
  v17 = 0;
  v14 = 0;
  CompartmentIdForRoutingDomain = GetCompartmentIdForRoutingDomain(a2);
  v6 = (void *)CompartmentIdForRoutingDomain;
  v7 = SetCurrentThreadCompartmentId(CompartmentIdForRoutingDomain);
  v8 = v7;
  if ( v7 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v19) = 0;
      LOWORD(v15) = 0;
      FormatRRASErrorString(
        &v19,
        L"RegisterIpAddressChangeNotifications: SetCurrentCompartmentId failed with error %d",
        v7);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v9 = &v14;
        if ( a2 )
          LODWORD(v9) = (_DWORD)a2;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v19,
          (_DWORD)v9,
          0,
          (__int64)&v15);
      }
    }
  }
  else
  {
    v10 = 2;
    if ( a1 != 33 )
      v10 = 23;
    v8 = NotifyUnicastIpAddressChange(v10, OnAddressChange, v6, 1u, &NotificationHandle);
    if ( v8 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v19) = 0;
        LOWORD(v15) = 0;
        FormatRRASErrorString(
          &v19,
          L"RegisterIpAddressChangeNotifications: NotifyUnicastIpAddressChange failed with error %d",
          v8);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v11 = &v14;
          if ( a2 )
            LODWORD(v11) = (_DWORD)a2;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v19,
            (_DWORD)v11,
            0,
            (__int64)&v15);
        }
      }
    }
    else
    {
      SetIpChangeNotificationHandleForRoutingDomain(a2, a1, NotificationHandle);
    }
    SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
  }
  return v8;
}

```

## disassembly

```asm
0x1800523a8  mov     [rsp-8+arg_10], rbx
0x1800523ad  push    rbp
0x1800523ae  push    rsi
0x1800523af  push    rdi
0x1800523b0  push    r14
0x1800523b2  push    r15
0x1800523b4  lea     rbp, [rsp-780h]
0x1800523bc  sub     rsp, 880h
0x1800523c3  mov     rax, cs:__security_cookie
0x1800523ca  xor     rax, rsp
0x1800523cd  mov     [rbp+7A0h+var_30], rax
0x1800523d4  mov     rdi, rdx
0x1800523d7  mov     [rsp+8A0h+var_870], 0
0x1800523e0  mov     esi, ecx
0x1800523e2  call    cs:__imp_GetCurrentThreadCompartmentId
0x1800523e8  xor     ecx, ecx
0x1800523ea  xor     edx, edx; Val
0x1800523ec  mov     [rsp+8A0h+var_830], ecx
0x1800523f0  mov     r8d, 7FCh; Size
0x1800523f6  lea     rcx, [rsp+8A0h+var_82C]; void *
0x1800523fb  mov     r14d, eax
0x1800523fe  call    memset_0
0x180052403  xorps   xmm0, xmm0
0x180052406  xor     ecx, ecx
0x180052408  mov     [rsp+8A0h+var_858], ecx
0x18005240c  xor     eax, eax
0x18005240e  mov     rcx, rdi
0x180052411  mov     [rsp+8A0h+var_834], eax
0x180052415  movups  [rsp+8A0h+var_854], xmm0
0x18005241a  movups  [rsp+8A0h+var_844], xmm0
0x18005241f  movups  [rsp+8A0h+var_868], xmm0
0x180052424  call    GetCompartmentIdForRoutingDomain
0x180052429  mov     ecx, eax; CompartmentId
0x18005242b  mov     r15d, eax
0x18005242e  call    cs:__imp_SetCurrentThreadCompartmentId
0x180052434  mov     ebx, eax
0x180052436  test    eax, eax
0x180052438  jz      short loc_1800524B0
0x18005243a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180052441  jz      loc_180052565
0x180052447  xor     ecx, ecx
0x180052449  lea     rdx, aRegisteripaddr_0; "RegisterIpAddressChangeNotifications: S"...
0x180052450  mov     word ptr [rsp+8A0h+var_830], cx
0x180052455  mov     r8d, eax
0x180052458  mov     word ptr [rsp+8A0h+var_858], cx
0x18005245d  lea     rcx, [rsp+8A0h+var_830]
0x180052462  call    FormatRRASErrorString
0x180052467  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18005246e  jz      loc_180052565
0x180052474  test    rdi, rdi
0x180052477  lea     rax, [rsp+8A0h+var_858]
0x18005247c  mov     [rsp+8A0h+var_878], rax
0x180052481  lea     r9, [rsp+8A0h+var_868]
0x180052486  cmovnz  r9, rdi
0x18005248a  mov     [rsp+8A0h+NotificationHandle], 0
0x180052493  lea     r8, [rsp+8A0h+var_830]
0x180052498  lea     rdx, RasRtrMgrParamTraceError
0x18005249f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800524a6  call    McTemplateU0zjzz_EventWriteTransfer
0x1800524ab  jmp     loc_180052565
0x1800524b0  mov     ecx, 2
0x1800524b5  lea     rdx, OnAddressChange; Callback
0x1800524bc  cmp     esi, 21h ; '!'
0x1800524bf  mov     r8, r15; CallerContext
0x1800524c2  mov     r9b, 1; InitialNotification
0x1800524c5  lea     eax, [rcx+15h]
0x1800524c8  cmovnz  cx, ax; Family
0x1800524cc  lea     rax, [rsp+8A0h+var_870]
0x1800524d1  mov     [rsp+8A0h+NotificationHandle], rax; NotificationHandle
0x1800524d6  call    cs:__imp_NotifyUnicastIpAddressChange
0x1800524dc  mov     ebx, eax
0x1800524de  test    eax, eax
0x1800524e0  jz      short loc_18005254D
0x1800524e2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800524e9  jz      short loc_18005255C
0x1800524eb  xor     eax, eax
0x1800524ed  lea     rdx, aRegisteripaddr; "RegisterIpAddressChangeNotifications: N"...
0x1800524f4  mov     r8d, ebx
0x1800524f7  mov     word ptr [rsp+8A0h+var_830], ax
0x1800524fc  lea     rcx, [rsp+8A0h+var_830]
0x180052501  mov     word ptr [rsp+8A0h+var_858], ax
0x180052506  call    FormatRRASErrorString
0x18005250b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180052512  jz      short loc_18005255C
0x180052514  test    rdi, rdi
0x180052517  lea     rax, [rsp+8A0h+var_858]
0x18005251c  mov     [rsp+8A0h+var_878], rax
0x180052521  lea     r9, [rsp+8A0h+var_868]
0x180052526  cmovnz  r9, rdi
0x18005252a  mov     [rsp+8A0h+NotificationHandle], 0
0x180052533  lea     r8, [rsp+8A0h+var_830]
0x180052538  lea     rdx, RasRtrMgrParamTraceError
0x18005253f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180052546  call    McTemplateU0zjzz_EventWriteTransfer
0x18005254b  jmp     short loc_18005255C
0x18005254d  mov     r8, [rsp+8A0h+var_870]; void *
0x180052552  mov     edx, esi; unsigned int
0x180052554  mov     rcx, rdi; struct _GUID *
0x180052557  call    SetIpChangeNotificationHandleForRoutingDomain
0x18005255c  mov     ecx, r14d; CompartmentId
0x18005255f  call    cs:__imp_SetCurrentThreadCompartmentId
0x180052565  mov     eax, ebx
0x180052567  mov     rcx, [rbp+7A0h+var_30]
0x18005256e  xor     rcx, rsp; StackCookie
0x180052571  call    __security_check_cookie
0x180052576  mov     rbx, [rsp+8A0h+arg_10]
0x18005257e  add     rsp, 880h
0x180052585  pop     r15
0x180052587  pop     r14
0x180052589  pop     rdi
0x18005258a  pop     rsi
0x18005258b  pop     rbp
0x18005258c  retn
```
