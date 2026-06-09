# TeredoDeregisterIcmpv6FirewallExceptions

- ea: `0x18003561c`
- end: `0x180035803`
- name: `TeredoDeregisterIcmpv6FirewallExceptions`
- size: `487`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015d54`
- `0x180036ad4`

## callees

- `0x18000d7c0`
- `0x1800190f0`
- `0x18003561c`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800357e6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800357e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003569b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003569b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180035656`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180035656`
- `OLEAUT32!__imp_SysAllocString` at `0x1800356f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18003573f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800356f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18003573f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800357c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800357da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800357c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800357da`

## string_xrefs

- `0x1800356ed`: `@IpHlpSvc.dll,-502`
- `0x180035738`: `@IpHlpSvc.dll,-503`
- `0x180035666`: `Com initialization failed for de-registering ICMPV6 exemptions.`

## pseudocode

```c
void TeredoDeregisterIcmpv6FirewallExceptions()
{
  OLECHAR *v0; // rdi
  OLECHAR *v1; // rbx
  int v2; // eax
  int v3; // eax
  BSTR v4; // rax
  int v5; // eax
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  v6 = 0;
  EventWrite0(0x100000, L"Teredo deregister Icmpv6 firewall exceptions");
  if ( CoInitializeEx(0, 4u) >= 0 )
  {
    v0 = 0;
    v1 = 0;
    if ( CoCreateInstance(&CLSID_NetFwPolicy2, 0, 1u, &GUID_98325047_c671_4174_8d81_defcd3f03186, &ppv) >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 144LL))(ppv, &v6);
      if ( v2 >= 0 && v6 )
      {
        v0 = SysAllocString(L"@IpHlpSvc.dll,-502");
        if ( v0 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v6 + 72LL))(v6, v0);
          if ( v3 < 0 )
            EventWriteError0(
              0x100000,
              L"De-registering ICMPV6 Exemptions: Firewall op failed with error %d (0x%x)",
              (unsigned int)v3,
              (unsigned int)v3);
          v4 = SysAllocString(L"@IpHlpSvc.dll,-503");
          v1 = v4;
          if ( v4 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v6 + 72LL))(v6, v4);
            if ( v5 < 0 )
              EventWriteError0(
                0x100000,
                L"De-registering ICMPV6 Exemptions: Firewall op failed with error %d (0x%x)",
                (unsigned int)v5,
                (unsigned int)v5);
          }
        }
      }
      else
      {
        EventWriteError0(
          0x100000,
          L"De-registering ICMPV6 Exemptions: get_Rules failed with Status(0x%d) and Ptr(0x%p)",
          (unsigned int)v2,
          v6);
      }
    }
    else
    {
      EventWriteError0(0x100000, L"%Unable to find Firewall Policy manager.");
    }
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v0 )
      SysFreeString(v0);
    if ( v1 )
      SysFreeString(v1);
    CoUninitialize();
  }
  else
  {
    EventWriteError0(0x100000, L"Com initialization failed for de-registering ICMPV6 exemptions.");
  }
}

```

## disassembly

```asm
0x18003561c  mov     rax, rsp
0x18003561f  mov     [rax+18h], rbx
0x180035623  mov     [rax+20h], rsi
0x180035627  push    rdi
0x180035628  sub     rsp, 30h
0x18003562c  mov     esi, 100000h
0x180035631  mov     qword ptr [rax+10h], 0
0x180035639  mov     ecx, esi
0x18003563b  mov     qword ptr [rax+8], 0
0x180035643  lea     rdx, aTeredoDeregist; "Teredo deregister Icmpv6 firewall excep"...
0x18003564a  call    EventWrite0
0x18003564f  mov     edx, 4; dwCoInit
0x180035654  xor     ecx, ecx; pvReserved
0x180035656  call    cs:__imp_CoInitializeEx
0x18003565d  nop     dword ptr [rax+rax+00h]
0x180035662  test    eax, eax
0x180035664  jns     short loc_180035679
0x180035666  lea     rdx, aComInitializat_1; "Com initialization failed for de-regist"...
0x18003566d  mov     ecx, esi
0x18003566f  call    EventWriteError0
0x180035674  jmp     loc_1800357F2
0x180035679  lea     rax, [rsp+38h+arg_8]
0x18003567e  xor     edi, edi
0x180035680  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x180035687  mov     [rsp+38h+ppv], rax; ppv
0x18003568c  xor     edx, edx; pUnkOuter
0x18003568e  lea     rcx, CLSID_NetFwPolicy2; rclsid
0x180035695  xor     ebx, ebx
0x180035697  lea     r8d, [rdi+1]; dwClsContext
0x18003569b  call    cs:__imp_CoCreateInstance
0x1800356a2  nop     dword ptr [rax+rax+00h]
0x1800356a7  test    eax, eax
0x1800356a9  jns     short loc_1800356BE
0x1800356ab  lea     rdx, aUnableToFindFi_0; "%Unable to find Firewall Policy manager"...
0x1800356b2  mov     ecx, esi
0x1800356b4  call    EventWriteError0
0x1800356b9  jmp     loc_180035792
0x1800356be  mov     rcx, [rsp+38h+arg_8]
0x1800356c3  lea     rdx, [rsp+38h+arg_0]
0x1800356c8  mov     rax, [rcx]
0x1800356cb  mov     rax, [rax+90h]
0x1800356d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356d7  mov     r9, [rsp+38h+arg_0]
0x1800356dc  test    eax, eax
0x1800356de  js      loc_180035781
0x1800356e4  test    r9, r9
0x1800356e7  jz      loc_180035781
0x1800356ed  lea     rcx, aIphlpsvcDll502; "@IpHlpSvc.dll,-502"
0x1800356f4  call    cs:__imp_SysAllocString
0x1800356fb  nop     dword ptr [rax+rax+00h]
0x180035700  mov     rdi, rax
0x180035703  test    rax, rax
0x180035706  jz      loc_180035792
0x18003570c  mov     rcx, [rsp+38h+arg_0]
0x180035711  mov     rdx, [rcx]
0x180035714  mov     rax, [rdx+48h]
0x180035718  mov     rdx, rdi
0x18003571b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035720  test    eax, eax
0x180035722  jns     short loc_180035738
0x180035724  mov     r9d, eax
0x180035727  lea     rdx, aDeRegisteringI; "De-registering ICMPV6 Exemptions: Firew"...
0x18003572e  mov     r8d, eax
0x180035731  mov     ecx, esi
0x180035733  call    EventWriteError0
0x180035738  lea     rcx, aIphlpsvcDll503; "@IpHlpSvc.dll,-503"
0x18003573f  call    cs:__imp_SysAllocString
0x180035746  nop     dword ptr [rax+rax+00h]
0x18003574b  mov     rbx, rax
0x18003574e  test    rax, rax
0x180035751  jz      short loc_180035792
0x180035753  mov     rcx, [rsp+38h+arg_0]
0x180035758  mov     rdx, rax
0x18003575b  mov     r8, [rcx]
0x18003575e  mov     rax, [r8+48h]
0x180035762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035767  test    eax, eax
0x180035769  jns     short loc_180035792
0x18003576b  mov     r9d, eax
0x18003576e  lea     rdx, aDeRegisteringI; "De-registering ICMPV6 Exemptions: Firew"...
0x180035775  mov     r8d, eax
0x180035778  mov     ecx, esi
0x18003577a  call    EventWriteError0
0x18003577f  jmp     short loc_180035792
0x180035781  mov     r8d, eax
0x180035784  lea     rdx, aDeRegisteringI_0; "De-registering ICMPV6 Exemptions: get_R"...
0x18003578b  mov     ecx, esi
0x18003578d  call    EventWriteError0
0x180035792  mov     rcx, [rsp+38h+arg_0]
0x180035797  test    rcx, rcx
0x18003579a  jz      short loc_1800357A8
0x18003579c  mov     rax, [rcx]
0x18003579f  mov     rax, [rax+10h]
0x1800357a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357a8  mov     rcx, [rsp+38h+arg_8]
0x1800357ad  test    rcx, rcx
0x1800357b0  jz      short loc_1800357BE
0x1800357b2  mov     rax, [rcx]
0x1800357b5  mov     rax, [rax+10h]
0x1800357b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357be  test    rdi, rdi
0x1800357c1  jz      short loc_1800357D2
0x1800357c3  mov     rcx, rdi; bstrString
0x1800357c6  call    cs:__imp_SysFreeString
0x1800357cd  nop     dword ptr [rax+rax+00h]
0x1800357d2  test    rbx, rbx
0x1800357d5  jz      short loc_1800357E6
0x1800357d7  mov     rcx, rbx; bstrString
0x1800357da  call    cs:__imp_SysFreeString
0x1800357e1  nop     dword ptr [rax+rax+00h]
0x1800357e6  call    cs:__imp_CoUninitialize
0x1800357ed  nop     dword ptr [rax+rax+00h]
0x1800357f2  mov     rbx, [rsp+38h+arg_10]
0x1800357f7  mov     rsi, [rsp+38h+arg_18]
0x1800357fc  add     rsp, 30h
0x180035800  pop     rdi
0x180035801  retn
```
