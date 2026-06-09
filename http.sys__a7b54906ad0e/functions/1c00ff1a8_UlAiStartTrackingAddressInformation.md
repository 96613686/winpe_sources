# UlAiStartTrackingAddressInformation

- ea: `0x1c00ff1a8`
- end: `0x1c00ff3a4`
- name: `UlAiStartTrackingAddressInformation`
- size: `508`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c00fee60`
- `0x1c00fefb4`

## callees

- `0x1c0036538`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c00ff1a8`

## import_xrefs

- `NETIO!NsiRegisterChangeNotification` at `0x1c00ff220`
- `NETIO!NsiRegisterChangeNotification` at `0x1c00ff26c`
- `NETIO!NsiRegisterChangeNotification` at `0x1c00ff220`
- `NETIO!NsiRegisterChangeNotification` at `0x1c00ff26c`
- `NETIO!CancelMibChangeNotify2` at `0x1c00ff36a`
- `NETIO!CancelMibChangeNotify2` at `0x1c00ff36a`
- `NETIO!NsiDeregisterChangeNotification` at `0x1c00ff334`
- `NETIO!NsiDeregisterChangeNotification` at `0x1c00ff355`
- `NETIO!NsiDeregisterChangeNotification` at `0x1c00ff334`
- `NETIO!NsiDeregisterChangeNotification` at `0x1c00ff355`
- `NETIO!NotifyUnicastIpAddressChange` at `0x1c00ff2ac`
- `NETIO!NotifyUnicastIpAddressChange` at `0x1c00ff2ac`

## pseudocode

```c
__int64 UlAiStartTrackingAddressInformation()
{
  NTSTATUS v0; // ebx
  HANDLE NotificationHandle; // [rsp+50h] [rbp+20h] BYREF

  v0 = 0;
  NotificationHandle = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x400000) != 0 )
    WPP_SF_(16, WPP_2d2e9e53eb3937d6fa5d0f266d0ba408_Traceguids);
  if ( (unsigned __int8)UxPodIsCurrentRoot() )
  {
    if ( UlAiNlIpv4NotificationHandle
      || (v0 = NsiRegisterChangeNotification(&NPI_MS_IPV4_MODULEID, 7, UlpAiNlChangeCallback), v0 >= 0) )
    {
      if ( UlAiNlIpv6NotificationHandle
        || (v0 = NsiRegisterChangeNotification(&NPI_MS_IPV6_MODULEID, 7, UlpAiNlChangeCallback), v0 >= 0) )
      {
        if ( UlAiIpChangeNotificationHandle
          || (v0 = NotifyUnicastIpAddressChange(0, UlpAiIpAddressChangeCallback, 0, 1u, &NotificationHandle), v0 >= 0) )
        {
          if ( NotificationHandle )
            NotificationHandle = (HANDLE)(-(__int64)(_InterlockedCompareExchange64(
                                                       (volatile signed __int64 *)&UlAiIpChangeNotificationHandle,
                                                       (signed __int64)NotificationHandle,
                                                       0) != 0)
                                        & (unsigned __int64)NotificationHandle);
        }
        else
        {
          NotificationHandle = 0;
        }
      }
    }
  }
  else
  {
    v0 = -1073741637;
  }
  if ( NotificationHandle )
    CancelMibChangeNotify2(NotificationHandle);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x400000) != 0 )
    WPP_SF_D(17, WPP_2d2e9e53eb3937d6fa5d0f266d0ba408_Traceguids);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1c00ff1a8  mov     [rsp-8+arg_18], rbx
0x1c00ff1ad  push    rbp
0x1c00ff1ae  mov     rbp, rsp
0x1c00ff1b1  sub     rsp, 30h
0x1c00ff1b5  xor     ebx, ebx
0x1c00ff1b7  and     [rbp+arg_0], rbx
0x1c00ff1bb  and     [rbp+arg_8], rbx
0x1c00ff1bf  and     [rbp+arg_10], rbx
0x1c00ff1c3  test    dword ptr cs:WPP_MAIN_CB.Queue, 400000h
0x1c00ff1cd  jz      short loc_1C00FF1DE
0x1c00ff1cf  lea     ecx, [rbx+10h]
0x1c00ff1d2  lea     rdx, WPP_2d2e9e53eb3937d6fa5d0f266d0ba408_Traceguids
0x1c00ff1d9  call    WPP_SF_
0x1c00ff1de  call    UxPodIsCurrentRoot
0x1c00ff1e3  test    al, al
0x1c00ff1e5  jnz     short loc_1C00FF1F1
0x1c00ff1e7  mov     ebx, 0C00000BBh
0x1c00ff1ec  jmp     loc_1C00FF31F
0x1c00ff1f1  mov     rax, cs:UlAiNlIpv4NotificationHandle
0x1c00ff1f8  test    rax, rax
0x1c00ff1fb  jnz     short loc_1C00FF23C
0x1c00ff1fd  xor     r9d, r9d
0x1c00ff200  lea     rax, [rbp+arg_0]
0x1c00ff204  mov     [rsp+30h+var_8], rax
0x1c00ff209  lea     r8, UlpAiNlChangeCallback
0x1c00ff210  and     [rsp+30h+NotificationHandle], rbx
0x1c00ff215  lea     rcx, NPI_MS_IPV4_MODULEID
0x1c00ff21c  lea     edx, [r9+7]
0x1c00ff220  call    cs:__imp_NsiRegisterChangeNotification
0x1c00ff227  nop     dword ptr [rax+rax+00h]
0x1c00ff22c  mov     ebx, eax
0x1c00ff22e  test    eax, eax
0x1c00ff230  jns     short loc_1C00FF23C
0x1c00ff232  and     [rbp+arg_0], 0
0x1c00ff237  jmp     loc_1C00FF340
0x1c00ff23c  mov     rax, cs:UlAiNlIpv6NotificationHandle
0x1c00ff243  test    rax, rax
0x1c00ff246  jnz     short loc_1C00FF288
0x1c00ff248  xor     r9d, r9d
0x1c00ff24b  lea     rax, [rbp+arg_8]
0x1c00ff24f  mov     [rsp+30h+var_8], rax
0x1c00ff254  lea     r8, UlpAiNlChangeCallback
0x1c00ff25b  and     [rsp+30h+NotificationHandle], 0
0x1c00ff261  lea     rcx, NPI_MS_IPV6_MODULEID
0x1c00ff268  lea     edx, [r9+7]
0x1c00ff26c  call    cs:__imp_NsiRegisterChangeNotification
0x1c00ff273  nop     dword ptr [rax+rax+00h]
0x1c00ff278  mov     ebx, eax
0x1c00ff27a  test    eax, eax
0x1c00ff27c  jns     short loc_1C00FF288
0x1c00ff27e  and     [rbp+arg_8], 0
0x1c00ff283  jmp     loc_1C00FF31F
0x1c00ff288  mov     rax, cs:UlAiIpChangeNotificationHandle
0x1c00ff28f  test    rax, rax
0x1c00ff292  jnz     short loc_1C00FF2C5
0x1c00ff294  lea     rax, [rbp+arg_10]
0x1c00ff298  xor     ecx, ecx; Family
0x1c00ff29a  mov     r9b, 1; InitialNotification
0x1c00ff29d  mov     [rsp+30h+NotificationHandle], rax; NotificationHandle
0x1c00ff2a2  xor     r8d, r8d; CallerContext
0x1c00ff2a5  lea     rdx, UlpAiIpAddressChangeCallback; Callback
0x1c00ff2ac  call    cs:__imp_NotifyUnicastIpAddressChange
0x1c00ff2b3  nop     dword ptr [rax+rax+00h]
0x1c00ff2b8  mov     ebx, eax
0x1c00ff2ba  test    eax, eax
0x1c00ff2bc  jns     short loc_1C00FF2C5
0x1c00ff2be  and     [rbp+arg_10], 0
0x1c00ff2c3  jmp     short loc_1C00FF31F
0x1c00ff2c5  mov     r8, [rbp+arg_0]
0x1c00ff2c9  test    r8, r8
0x1c00ff2cc  jz      short loc_1C00FF2E3
0x1c00ff2ce  xor     eax, eax
0x1c00ff2d0  lock cmpxchg cs:UlAiNlIpv4NotificationHandle, r8
0x1c00ff2d9  neg     rax
0x1c00ff2dc  sbb     rcx, rcx
0x1c00ff2df  and     [rbp+arg_0], rcx
0x1c00ff2e3  mov     r8, [rbp+arg_8]
0x1c00ff2e7  test    r8, r8
0x1c00ff2ea  jz      short loc_1C00FF301
0x1c00ff2ec  xor     eax, eax
0x1c00ff2ee  lock cmpxchg cs:UlAiNlIpv6NotificationHandle, r8
0x1c00ff2f7  neg     rax
0x1c00ff2fa  sbb     rcx, rcx
0x1c00ff2fd  and     [rbp+arg_8], rcx
0x1c00ff301  mov     rcx, [rbp+arg_10]
0x1c00ff305  test    rcx, rcx
0x1c00ff308  jz      short loc_1C00FF31F
0x1c00ff30a  xor     eax, eax
0x1c00ff30c  lock cmpxchg cs:UlAiIpChangeNotificationHandle, rcx
0x1c00ff315  neg     rax
0x1c00ff318  sbb     rcx, rcx
0x1c00ff31b  and     [rbp+arg_10], rcx
0x1c00ff31f  mov     r8, [rbp+arg_0]
0x1c00ff323  test    r8, r8
0x1c00ff326  jz      short loc_1C00FF340
0x1c00ff328  mov     edx, 7
0x1c00ff32d  lea     rcx, NPI_MS_IPV4_MODULEID
0x1c00ff334  call    cs:__imp_NsiDeregisterChangeNotification
0x1c00ff33b  nop     dword ptr [rax+rax+00h]
0x1c00ff340  mov     r8, [rbp+arg_8]
0x1c00ff344  test    r8, r8
0x1c00ff347  jz      short loc_1C00FF361
0x1c00ff349  mov     edx, 7
0x1c00ff34e  lea     rcx, NPI_MS_IPV6_MODULEID
0x1c00ff355  call    cs:__imp_NsiDeregisterChangeNotification
0x1c00ff35c  nop     dword ptr [rax+rax+00h]
0x1c00ff361  mov     rcx, [rbp+arg_10]; NotificationHandle
0x1c00ff365  test    rcx, rcx
0x1c00ff368  jz      short loc_1C00FF376
0x1c00ff36a  call    cs:__imp_CancelMibChangeNotify2
0x1c00ff371  nop     dword ptr [rax+rax+00h]
0x1c00ff376  test    dword ptr cs:WPP_MAIN_CB.Queue, 400000h
0x1c00ff380  jz      short loc_1C00FF396
0x1c00ff382  mov     ecx, 11h
0x1c00ff387  lea     rdx, WPP_2d2e9e53eb3937d6fa5d0f266d0ba408_Traceguids
0x1c00ff38e  mov     r8d, ebx
0x1c00ff391  call    WPP_SF_D
0x1c00ff396  mov     eax, ebx
0x1c00ff398  mov     rbx, [rsp+30h+arg_18]
0x1c00ff39d  add     rsp, 30h
0x1c00ff3a1  pop     rbp
0x1c00ff3a2  retn
```
