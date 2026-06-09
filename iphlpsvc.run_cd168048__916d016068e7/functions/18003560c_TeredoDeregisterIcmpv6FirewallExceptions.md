# TeredoDeregisterIcmpv6FirewallExceptions

- ea: `0x18003560c`
- end: `0x1800357f3`
- name: `TeredoDeregisterIcmpv6FirewallExceptions`
- size: `487`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015d44`
- `0x180036ac4`

## callees

- `0x18000d7b0`
- `0x1800190e0`
- `0x18003560c`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800357d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800357d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003568b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003568b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180035646`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180035646`
- `OLEAUT32!__imp_SysAllocString` at `0x1800356e4`
- `OLEAUT32!__imp_SysAllocString` at `0x18003572f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800356e4`
- `OLEAUT32!__imp_SysAllocString` at `0x18003572f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800357b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800357ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800357b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800357ca`

## string_xrefs

- `0x1800356dd`: `@IpHlpSvc.dll,-502`
- `0x180035728`: `@IpHlpSvc.dll,-503`
- `0x180035656`: `Com initialization failed for de-registering ICMPV6 exemptions.`

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
0x18003560c  mov     rax, rsp
0x18003560f  mov     [rax+18h], rbx
0x180035613  mov     [rax+20h], rsi
0x180035617  push    rdi
0x180035618  sub     rsp, 30h
0x18003561c  mov     esi, 100000h
0x180035621  mov     qword ptr [rax+10h], 0
0x180035629  mov     ecx, esi
0x18003562b  mov     qword ptr [rax+8], 0
0x180035633  lea     rdx, aTeredoDeregist; "Teredo deregister Icmpv6 firewall excep"...
0x18003563a  call    EventWrite0
0x18003563f  mov     edx, 4; dwCoInit
0x180035644  xor     ecx, ecx; pvReserved
0x180035646  call    cs:__imp_CoInitializeEx
0x18003564d  nop     dword ptr [rax+rax+00h]
0x180035652  test    eax, eax
0x180035654  jns     short loc_180035669
0x180035656  lea     rdx, aComInitializat_1; "Com initialization failed for de-regist"...
0x18003565d  mov     ecx, esi
0x18003565f  call    EventWriteError0
0x180035664  jmp     loc_1800357E2
0x180035669  lea     rax, [rsp+38h+arg_8]
0x18003566e  xor     edi, edi
0x180035670  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x180035677  mov     [rsp+38h+ppv], rax; ppv
0x18003567c  xor     edx, edx; pUnkOuter
0x18003567e  lea     rcx, CLSID_NetFwPolicy2; rclsid
0x180035685  xor     ebx, ebx
0x180035687  lea     r8d, [rdi+1]; dwClsContext
0x18003568b  call    cs:__imp_CoCreateInstance
0x180035692  nop     dword ptr [rax+rax+00h]
0x180035697  test    eax, eax
0x180035699  jns     short loc_1800356AE
0x18003569b  lea     rdx, aUnableToFindFi_0; "%Unable to find Firewall Policy manager"...
0x1800356a2  mov     ecx, esi
0x1800356a4  call    EventWriteError0
0x1800356a9  jmp     loc_180035782
0x1800356ae  mov     rcx, [rsp+38h+arg_8]
0x1800356b3  lea     rdx, [rsp+38h+arg_0]
0x1800356b8  mov     rax, [rcx]
0x1800356bb  mov     rax, [rax+90h]
0x1800356c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356c7  mov     r9, [rsp+38h+arg_0]
0x1800356cc  test    eax, eax
0x1800356ce  js      loc_180035771
0x1800356d4  test    r9, r9
0x1800356d7  jz      loc_180035771
0x1800356dd  lea     rcx, aIphlpsvcDll502; "@IpHlpSvc.dll,-502"
0x1800356e4  call    cs:__imp_SysAllocString
0x1800356eb  nop     dword ptr [rax+rax+00h]
0x1800356f0  mov     rdi, rax
0x1800356f3  test    rax, rax
0x1800356f6  jz      loc_180035782
0x1800356fc  mov     rcx, [rsp+38h+arg_0]
0x180035701  mov     rdx, [rcx]
0x180035704  mov     rax, [rdx+48h]
0x180035708  mov     rdx, rdi
0x18003570b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035710  test    eax, eax
0x180035712  jns     short loc_180035728
0x180035714  mov     r9d, eax
0x180035717  lea     rdx, aDeRegisteringI; "De-registering ICMPV6 Exemptions: Firew"...
0x18003571e  mov     r8d, eax
0x180035721  mov     ecx, esi
0x180035723  call    EventWriteError0
0x180035728  lea     rcx, aIphlpsvcDll503; "@IpHlpSvc.dll,-503"
0x18003572f  call    cs:__imp_SysAllocString
0x180035736  nop     dword ptr [rax+rax+00h]
0x18003573b  mov     rbx, rax
0x18003573e  test    rax, rax
0x180035741  jz      short loc_180035782
0x180035743  mov     rcx, [rsp+38h+arg_0]
0x180035748  mov     rdx, rax
0x18003574b  mov     r8, [rcx]
0x18003574e  mov     rax, [r8+48h]
0x180035752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035757  test    eax, eax
0x180035759  jns     short loc_180035782
0x18003575b  mov     r9d, eax
0x18003575e  lea     rdx, aDeRegisteringI; "De-registering ICMPV6 Exemptions: Firew"...
0x180035765  mov     r8d, eax
0x180035768  mov     ecx, esi
0x18003576a  call    EventWriteError0
0x18003576f  jmp     short loc_180035782
0x180035771  mov     r8d, eax
0x180035774  lea     rdx, aDeRegisteringI_0; "De-registering ICMPV6 Exemptions: get_R"...
0x18003577b  mov     ecx, esi
0x18003577d  call    EventWriteError0
0x180035782  mov     rcx, [rsp+38h+arg_0]
0x180035787  test    rcx, rcx
0x18003578a  jz      short loc_180035798
0x18003578c  mov     rax, [rcx]
0x18003578f  mov     rax, [rax+10h]
0x180035793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035798  mov     rcx, [rsp+38h+arg_8]
0x18003579d  test    rcx, rcx
0x1800357a0  jz      short loc_1800357AE
0x1800357a2  mov     rax, [rcx]
0x1800357a5  mov     rax, [rax+10h]
0x1800357a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357ae  test    rdi, rdi
0x1800357b1  jz      short loc_1800357C2
0x1800357b3  mov     rcx, rdi; bstrString
0x1800357b6  call    cs:__imp_SysFreeString
0x1800357bd  nop     dword ptr [rax+rax+00h]
0x1800357c2  test    rbx, rbx
0x1800357c5  jz      short loc_1800357D6
0x1800357c7  mov     rcx, rbx; bstrString
0x1800357ca  call    cs:__imp_SysFreeString
0x1800357d1  nop     dword ptr [rax+rax+00h]
0x1800357d6  call    cs:__imp_CoUninitialize
0x1800357dd  nop     dword ptr [rax+rax+00h]
0x1800357e2  mov     rbx, [rsp+38h+arg_10]
0x1800357e7  mov     rsi, [rsp+38h+arg_18]
0x1800357ec  add     rsp, 30h
0x1800357f0  pop     rdi
0x1800357f1  retn
```
