# UlAiStartTrackingAddressInformation

- ea: `0x1400cb5a4`
- end: `0x1400cb78b`
- name: `UlAiStartTrackingAddressInformation`
- size: `487`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400cb1b8`
- `0x1400cb314`

## callees

- `0x14009f1f4`
- `0x1400cb5a4`
- `0x1401c3f58`
- `0x1401da5a4`

## import_xrefs

- `NETIO!NotifyUnicastIpAddressChange` at `0x1400cb6a7`
- `NETIO!NotifyUnicastIpAddressChange` at `0x1400cb6a7`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400cb71c`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400cb73d`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400cb71c`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400cb73d`
- `NETIO!CancelMibChangeNotify2` at `0x1400cb752`
- `NETIO!CancelMibChangeNotify2` at `0x1400cb752`
- `NETIO!NsiRegisterChangeNotification` at `0x1400cb61e`
- `NETIO!NsiRegisterChangeNotification` at `0x1400cb668`
- `NETIO!NsiRegisterChangeNotification` at `0x1400cb61e`
- `NETIO!NsiRegisterChangeNotification` at `0x1400cb668`

## pseudocode

```c
__int64 UlAiStartTrackingAddressInformation()
{
  NTSTATUS v0; // ebx
  HANDLE NotificationHandle; // [rsp+60h] [rbp+30h] BYREF

  NotificationHandle = 0;
  if ( SBYTE2(xmmword_1401A2CA0) < 0 )
    WPP_SF_(1047, 16, WPP_8a82f71bae7e3fbe145cef66ca25cf13_Traceguids);
  if ( (unsigned __int8)UxPodIsCurrentRoot() )
  {
    v0 = 0;
    if ( UlAiNlIpv4NotificationHandle
      || (v0 = NsiRegisterChangeNotification(&NPI_MS_IPV4_MODULEID, 7, UlpAiNlChangeCallback), v0 >= 0) )
    {
      if ( UlAiNlIpv6NotificationHandle
        || (v0 = NsiRegisterChangeNotification(&NPI_MS_IPV6_MODULEID, 7, UlpAiNlChangeCallback), v0 >= 0) )
      {
        if ( !UlAiIpChangeNotificationHandle
          && (v0 = NotifyUnicastIpAddressChange(0, UlpAiIpAddressChangeCallback, 0, 1u, &NotificationHandle), v0 < 0)
          || NotificationHandle
          && !_InterlockedCompareExchange64(
                (volatile signed __int64 *)&UlAiIpChangeNotificationHandle,
                (signed __int64)NotificationHandle,
                0) )
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
  if ( SBYTE2(xmmword_1401A2CA0) < 0 )
    WPP_SF_d(1047, 17, WPP_8a82f71bae7e3fbe145cef66ca25cf13_Traceguids, (unsigned int)v0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400cb5a4  push    rbp
0x1400cb5a6  push    rbx
0x1400cb5a7  push    rdi
0x1400cb5a8  mov     rbp, rsp
0x1400cb5ab  sub     rsp, 30h
0x1400cb5af  xor     edi, edi
0x1400cb5b1  mov     [rbp+arg_0], rdi
0x1400cb5b5  mov     [rbp+arg_8], rdi
0x1400cb5b9  mov     [rbp+arg_10], rdi
0x1400cb5bd  cmp     byte ptr cs:xmmword_1401A2CA0+2, dil
0x1400cb5c4  jge     short loc_1400CB5DA
0x1400cb5c6  lea     edx, [rdi+10h]
0x1400cb5c9  mov     ecx, 417h
0x1400cb5ce  lea     r8, WPP_8a82f71bae7e3fbe145cef66ca25cf13_Traceguids
0x1400cb5d5  call    WPP_SF_
0x1400cb5da  call    UxPodIsCurrentRoot
0x1400cb5df  test    al, al
0x1400cb5e1  jnz     short loc_1400CB5ED
0x1400cb5e3  mov     ebx, 0C00000BBh
0x1400cb5e8  jmp     loc_1400CB707
0x1400cb5ed  mov     rax, cs:UlAiNlIpv4NotificationHandle
0x1400cb5f4  mov     ebx, edi
0x1400cb5f6  test    rax, rax
0x1400cb5f9  jnz     short loc_1400CB639
0x1400cb5fb  xor     r9d, r9d
0x1400cb5fe  lea     rax, [rbp+arg_0]
0x1400cb602  mov     [rsp+30h+var_8], rax
0x1400cb607  lea     r8, UlpAiNlChangeCallback
0x1400cb60e  lea     rcx, NPI_MS_IPV4_MODULEID
0x1400cb615  mov     [rsp+30h+NotificationHandle], rdi
0x1400cb61a  lea     edx, [r9+7]
0x1400cb61e  call    cs:__imp_NsiRegisterChangeNotification
0x1400cb625  nop     dword ptr [rax+rax+00h]
0x1400cb62a  mov     ebx, eax
0x1400cb62c  test    eax, eax
0x1400cb62e  jns     short loc_1400CB639
0x1400cb630  mov     [rbp+arg_0], rdi
0x1400cb634  jmp     loc_1400CB728
0x1400cb639  mov     rax, cs:UlAiNlIpv6NotificationHandle
0x1400cb640  test    rax, rax
0x1400cb643  jnz     short loc_1400CB683
0x1400cb645  xor     r9d, r9d
0x1400cb648  lea     rax, [rbp+arg_8]
0x1400cb64c  mov     [rsp+30h+var_8], rax
0x1400cb651  lea     r8, UlpAiNlChangeCallback
0x1400cb658  lea     rcx, NPI_MS_IPV6_MODULEID
0x1400cb65f  mov     [rsp+30h+NotificationHandle], rdi
0x1400cb664  lea     edx, [r9+7]
0x1400cb668  call    cs:__imp_NsiRegisterChangeNotification
0x1400cb66f  nop     dword ptr [rax+rax+00h]
0x1400cb674  mov     ebx, eax
0x1400cb676  test    eax, eax
0x1400cb678  jns     short loc_1400CB683
0x1400cb67a  mov     [rbp+arg_8], rdi
0x1400cb67e  jmp     loc_1400CB707
0x1400cb683  mov     rax, cs:UlAiIpChangeNotificationHandle
0x1400cb68a  test    rax, rax
0x1400cb68d  jnz     short loc_1400CB6B9
0x1400cb68f  lea     rax, [rbp+arg_10]
0x1400cb693  xor     ecx, ecx; Family
0x1400cb695  mov     r9b, 1; InitialNotification
0x1400cb698  mov     [rsp+30h+NotificationHandle], rax; NotificationHandle
0x1400cb69d  xor     r8d, r8d; CallerContext
0x1400cb6a0  lea     rdx, UlpAiIpAddressChangeCallback; Callback
0x1400cb6a7  call    cs:__imp_NotifyUnicastIpAddressChange
0x1400cb6ae  nop     dword ptr [rax+rax+00h]
0x1400cb6b3  mov     ebx, eax
0x1400cb6b5  test    eax, eax
0x1400cb6b7  js      short loc_1400CB703
0x1400cb6b9  mov     r8, [rbp+arg_0]
0x1400cb6bd  test    r8, r8
0x1400cb6c0  jz      short loc_1400CB6D3
0x1400cb6c2  xor     eax, eax
0x1400cb6c4  lock cmpxchg cs:UlAiNlIpv4NotificationHandle, r8
0x1400cb6cd  jnz     short loc_1400CB6D3
0x1400cb6cf  mov     [rbp+arg_0], rdi
0x1400cb6d3  mov     r8, [rbp+arg_8]
0x1400cb6d7  test    r8, r8
0x1400cb6da  jz      short loc_1400CB6ED
0x1400cb6dc  xor     eax, eax
0x1400cb6de  lock cmpxchg cs:UlAiNlIpv6NotificationHandle, r8
0x1400cb6e7  jnz     short loc_1400CB6ED
0x1400cb6e9  mov     [rbp+arg_8], rdi
0x1400cb6ed  mov     rcx, [rbp+arg_10]
0x1400cb6f1  test    rcx, rcx
0x1400cb6f4  jz      short loc_1400CB707
0x1400cb6f6  xor     eax, eax
0x1400cb6f8  lock cmpxchg cs:UlAiIpChangeNotificationHandle, rcx
0x1400cb701  jnz     short loc_1400CB707
0x1400cb703  mov     [rbp+arg_10], rdi
0x1400cb707  mov     r8, [rbp+arg_0]
0x1400cb70b  test    r8, r8
0x1400cb70e  jz      short loc_1400CB728
0x1400cb710  mov     edx, 7
0x1400cb715  lea     rcx, NPI_MS_IPV4_MODULEID
0x1400cb71c  call    cs:__imp_NsiDeregisterChangeNotification
0x1400cb723  nop     dword ptr [rax+rax+00h]
0x1400cb728  mov     r8, [rbp+arg_8]
0x1400cb72c  test    r8, r8
0x1400cb72f  jz      short loc_1400CB749
0x1400cb731  mov     edx, 7
0x1400cb736  lea     rcx, NPI_MS_IPV6_MODULEID
0x1400cb73d  call    cs:__imp_NsiDeregisterChangeNotification
0x1400cb744  nop     dword ptr [rax+rax+00h]
0x1400cb749  mov     rcx, [rbp+arg_10]; NotificationHandle
0x1400cb74d  test    rcx, rcx
0x1400cb750  jz      short loc_1400CB75E
0x1400cb752  call    cs:__imp_CancelMibChangeNotify2
0x1400cb759  nop     dword ptr [rax+rax+00h]
0x1400cb75e  cmp     byte ptr cs:xmmword_1401A2CA0+2, dil
0x1400cb765  jge     short loc_1400CB780
0x1400cb767  mov     edx, 11h
0x1400cb76c  lea     r8, WPP_8a82f71bae7e3fbe145cef66ca25cf13_Traceguids
0x1400cb773  mov     ecx, 417h
0x1400cb778  mov     r9d, ebx
0x1400cb77b  call    WPP_SF_d
0x1400cb780  mov     eax, ebx
0x1400cb782  add     rsp, 30h
0x1400cb786  pop     rdi
0x1400cb787  pop     rbx
0x1400cb788  pop     rbp
0x1400cb789  retn
```
