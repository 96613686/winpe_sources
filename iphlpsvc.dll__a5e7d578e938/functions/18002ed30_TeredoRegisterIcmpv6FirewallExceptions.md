# TeredoRegisterIcmpv6FirewallExceptions

- ea: `0x18002ed30`
- end: `0x18002f421`
- name: `TeredoRegisterIcmpv6FirewallExceptions`
- size: `1777`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001de74`
- `0x18002ecbc`

## callees

- `0x18000d7c0`
- `0x1800190f0`
- `0x18002ed30`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002f24a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002f24a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002edb9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ee18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ee58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002edb9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ee18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ee58`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002ed5b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002ed5b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee80`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee9f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eebe`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eedd`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eefc`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f044`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee80`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee9f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eebe`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eedd`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eefc`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f044`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f1f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f410`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f1f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f410`

## string_xrefs

- `0x18002ee79`: `@IpHlpSvc.dll,-502`
- `0x18002eeb7`: `@FirewallAPI.dll,-25000`
- `0x18002ee98`: `@FirewallAPI.dll,-28547`
- `0x18002f03d`: `@IpHlpSvc.dll,-503`
- `0x18002f2eb`: `Com initialization failed for registering ICMPV6 exemptions.`

## pseudocode

```c
void __fastcall TeredoRegisterIcmpv6FirewallExceptions(char a1)
{
  OLECHAR *v1; // r15
  OLECHAR *v3; // r14
  OLECHAR *v4; // rbx
  OLECHAR *v5; // r12
  OLECHAR *v6; // rsi
  OLECHAR *v7; // rdi
  int v8; // eax
  HRESULT v9; // eax
  HRESULT v10; // eax
  int v11; // eax
  BSTR v12; // rax
  __int64 v13; // r8
  LPVOID *ppv; // [rsp+20h] [rbp-40h]
  LPVOID v15; // [rsp+30h] [rbp-30h] BYREF
  LPVOID v16; // [rsp+88h] [rbp+28h] BYREF
  LPVOID v17; // [rsp+90h] [rbp+30h] BYREF
  __int64 v18; // [rsp+98h] [rbp+38h] BYREF

  v1 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( CoInitializeEx(0, 4u) < 0 )
  {
    EventWriteError0(0x100000, L"Com initialization failed for registering ICMPV6 exemptions.");
    return;
  }
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( CoCreateInstance(&CLSID_NetFwPolicy2, 0, 1u, &GUID_98325047_c671_4174_8d81_defcd3f03186, &v15) < 0 )
  {
    EventWriteError0(0x100000, L"Unable to find Firewall Policy manager.");
    goto LABEL_35;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v15 + 144LL))(v15, &v18);
  if ( v8 >= 0 && v18 )
  {
    v9 = CoCreateInstance(&CLSID_NetFwRule, 0, 1u, &GUID_af230d27_baba_4e42_aced_f524f22cfce2, &v16);
    if ( v9 < 0 || !v16 )
    {
      EventWriteError0(
        0x100000,
        L"stering ICMPV6 Exemptions: Rule (in) creation failed with Status(0x%d) and Ptr(0x%p)",
        (unsigned int)v9,
        v16);
      goto LABEL_35;
    }
    v10 = CoCreateInstance(&CLSID_NetFwRule, 0, 1u, &GUID_af230d27_baba_4e42_aced_f524f22cfce2, &v17);
    if ( v10 < 0 || !v17 )
    {
      EventWriteError0(
        0x100000,
        L"stering ICMPV6 Exemptions: Rule (out) creation failed with Status(0x%d) and Ptr(0x%p)",
        (unsigned int)v10,
        v17);
      goto LABEL_35;
    }
    v4 = SysAllocString(L"@IpHlpSvc.dll,-502");
    if ( !v4 )
      goto LABEL_35;
    v3 = SysAllocString(L"@FirewallAPI.dll,-28547");
    if ( !v3 )
      goto LABEL_35;
    v6 = SysAllocString(L"@FirewallAPI.dll,-25000");
    if ( !v6 )
      goto LABEL_35;
    v7 = SysAllocString(L"128:*");
    if ( !v7 )
      goto LABEL_35;
    v1 = SysAllocString(L"System");
    if ( !v1 )
      goto LABEL_35;
    (*(void (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v18 + 72LL))(v18, v4);
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v16 + 336LL))(v16, 1);
    if ( v11 < 0 )
    {
      v13 = 231;
      goto LABEL_60;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v16 + 64LL))(v16, v4);
    if ( v11 < 0 )
    {
      v13 = 232;
      goto LABEL_60;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v16 + 80LL))(v16, v3);
    if ( v11 < 0 )
    {
      v13 = 233;
      goto LABEL_60;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v16 + 224LL))(v16, 1);
    if ( v11 < 0 )
    {
      v13 = 234;
      goto LABEL_60;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v16 + 272LL))(v16, 0xFFFFFFFFLL);
    if ( v11 < 0 )
    {
      v13 = 235;
      goto LABEL_60;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v16 + 288LL))(v16, v6);
    if ( v11 < 0 )
    {
      v13 = 236;
      goto LABEL_60;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v16 + 128LL))(v16, 58);
    if ( v11 < 0 )
    {
      v13 = 237;
      goto LABEL_60;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v16 + 208LL))(v16, v7);
    if ( v11 < 0 )
    {
      v13 = 238;
      goto LABEL_60;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v16 + 96LL))(v16, v1);
    if ( v11 < 0 )
    {
      v13 = 239;
      goto LABEL_60;
    }
    if ( a1 )
    {
      v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v16 + 320LL))(v16, 0xFFFFFFFFLL);
      if ( v11 < 0 )
      {
        v13 = 243;
LABEL_60:
        LODWORD(ppv) = v11;
        EventWrite0(0x100000, L"Firewall op failed at line %d with error %d (0x%x)", v13, (unsigned int)v11, ppv);
        goto LABEL_35;
      }
    }
    v12 = SysAllocString(L"@IpHlpSvc.dll,-503");
    v5 = v12;
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64, BSTR))(*(_QWORD *)v18 + 72LL))(v18, v12);
      v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v17 + 336LL))(v17, 1);
      if ( v11 < 0 )
      {
        v13 = 255;
        goto LABEL_60;
      }
      v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v17 + 64LL))(v17, v5);
      if ( v11 < 0 )
      {
        v13 = 256;
        goto LABEL_60;
      }
      v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v17 + 80LL))(v17, v3);
      if ( v11 < 0 )
      {
        v13 = 257;
        goto LABEL_60;
      }
      v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v17 + 224LL))(v17, 2);
      if ( v11 < 0 )
      {
        v13 = 258;
        goto LABEL_60;
      }
      v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v17 + 272LL))(v17, 0xFFFFFFFFLL);
      if ( v11 < 0 )
      {
        v13 = 259;
        goto LABEL_60;
      }
      v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v17 + 288LL))(v17, v6);
      if ( v11 < 0 )
      {
        v13 = 260;
        goto LABEL_60;
      }
      v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v17 + 128LL))(v17, 58);
      if ( v11 < 0 )
      {
        v13 = 261;
        goto LABEL_60;
      }
      v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v17 + 208LL))(v17, v7);
      if ( v11 < 0 )
      {
        v13 = 262;
        goto LABEL_60;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v18 + 64LL))(v18, v16);
      if ( v11 < 0 )
      {
        v13 = 267;
        goto LABEL_60;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v18 + 64LL))(v18, v17);
      if ( v11 < 0 )
      {
        v13 = 268;
        goto LABEL_60;
      }
    }
  }
  else
  {
    EventWriteError0(
      0x100000,
      L"Registering ICMPV6 Exemptions: get_Rules failed with Status(0x%d) and Ptr(0x%p)",
      (unsigned int)v8,
      v18);
  }
LABEL_35:
  if ( v17 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v16 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v15 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v4 )
    SysFreeString(v4);
  if ( v5 )
    SysFreeString(v5);
  if ( v3 )
    SysFreeString(v3);
  if ( v6 )
    SysFreeString(v6);
  if ( v7 )
    SysFreeString(v7);
  if ( v1 )
    SysFreeString(v1);
  CoUninitialize();
}

```

## disassembly

```asm
0x18002ed30  push    rbp
0x18002ed32  push    r13
0x18002ed34  push    r15
0x18002ed36  mov     rbp, rsp
0x18002ed39  sub     rsp, 60h
0x18002ed3d  xor     r15d, r15d
0x18002ed40  movzx   r13d, cl
0x18002ed44  xor     ecx, ecx; pvReserved
0x18002ed46  mov     [rbp+var_30], r15
0x18002ed4a  mov     edx, 4; dwCoInit
0x18002ed4f  mov     [rbp+arg_8], r15
0x18002ed53  mov     [rbp+arg_10], r15
0x18002ed57  mov     [rbp+arg_18], r15
0x18002ed5b  call    cs:__imp_CoInitializeEx
0x18002ed62  nop     dword ptr [rax+rax+00h]
0x18002ed67  test    eax, eax
0x18002ed69  js      loc_18002F2EB
0x18002ed6f  mov     [rsp+60h+arg_0], rbx
0x18002ed77  lea     rax, [rbp+var_30]
0x18002ed7b  mov     [rsp+60h+var_8], rsi
0x18002ed80  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x18002ed87  mov     [rsp+60h+var_10], rdi
0x18002ed8c  lea     rcx, CLSID_NetFwPolicy2; rclsid
0x18002ed93  mov     [rsp+60h+var_18], r12
0x18002ed98  xor     edx, edx; pUnkOuter
0x18002ed9a  mov     [rsp+60h+var_20], r14
0x18002ed9f  mov     r8d, 1; dwClsContext
0x18002eda5  mov     r14d, r15d
0x18002eda8  mov     [rsp+60h+ppv], rax; ppv
0x18002edad  mov     ebx, r15d
0x18002edb0  mov     r12d, r15d
0x18002edb3  mov     esi, r15d
0x18002edb6  mov     edi, r15d
0x18002edb9  call    cs:__imp_CoCreateInstance
0x18002edc0  nop     dword ptr [rax+rax+00h]
0x18002edc5  test    eax, eax
0x18002edc7  js      loc_18002F2C5
0x18002edcd  mov     rcx, [rbp+var_30]
0x18002edd1  lea     rdx, [rbp+arg_18]
0x18002edd5  mov     rax, [rcx]
0x18002edd8  mov     rax, [rax+90h]
0x18002eddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ede4  mov     r9, [rbp+arg_18]
0x18002ede8  test    eax, eax
0x18002edea  js      loc_18002F261
0x18002edf0  test    r9, r9
0x18002edf3  jz      loc_18002F261
0x18002edf9  lea     rax, [rbp+arg_8]
0x18002edfd  xor     edx, edx; pUnkOuter
0x18002edff  lea     r9, _GUID_af230d27_baba_4e42_aced_f524f22cfce2; riid
0x18002ee06  mov     [rsp+60h+ppv], rax; ppv
0x18002ee0b  mov     r8d, 1; dwClsContext
0x18002ee11  lea     rcx, CLSID_NetFwRule; rclsid
0x18002ee18  call    cs:__imp_CoCreateInstance
0x18002ee1f  nop     dword ptr [rax+rax+00h]
0x18002ee24  mov     r9, [rbp+arg_8]
0x18002ee28  test    eax, eax
0x18002ee2a  js      loc_18002F3B1
0x18002ee30  test    r9, r9
0x18002ee33  jz      loc_18002F3B1
0x18002ee39  lea     rax, [rbp+arg_10]
0x18002ee3d  xor     edx, edx; pUnkOuter
0x18002ee3f  lea     r9, _GUID_af230d27_baba_4e42_aced_f524f22cfce2; riid
0x18002ee46  mov     [rsp+60h+ppv], rax; ppv
0x18002ee4b  mov     r8d, 1; dwClsContext
0x18002ee51  lea     rcx, CLSID_NetFwRule; rclsid
0x18002ee58  call    cs:__imp_CoCreateInstance
0x18002ee5f  nop     dword ptr [rax+rax+00h]
0x18002ee64  mov     r9, [rbp+arg_10]
0x18002ee68  test    eax, eax
0x18002ee6a  js      loc_18002F3A5
0x18002ee70  test    r9, r9
0x18002ee73  jz      loc_18002F3A5
0x18002ee79  lea     rcx, aIphlpsvcDll502; "@IpHlpSvc.dll,-502"
0x18002ee80  call    cs:__imp_SysAllocString
0x18002ee87  nop     dword ptr [rax+rax+00h]
0x18002ee8c  mov     rbx, rax
0x18002ee8f  test    rax, rax
0x18002ee92  jz      loc_18002F199
0x18002ee98  lea     rcx, aFirewallapiDll_0; "@FirewallAPI.dll,-28547"
0x18002ee9f  call    cs:__imp_SysAllocString
0x18002eea6  nop     dword ptr [rax+rax+00h]
0x18002eeab  mov     r14, rax
0x18002eeae  test    rax, rax
0x18002eeb1  jz      loc_18002F199
0x18002eeb7  lea     rcx, aFirewallapiDll_1; "@FirewallAPI.dll,-25000"
0x18002eebe  call    cs:__imp_SysAllocString
0x18002eec5  nop     dword ptr [rax+rax+00h]
0x18002eeca  mov     rsi, rax
0x18002eecd  test    rax, rax
0x18002eed0  jz      loc_18002F199
0x18002eed6  lea     rcx, a128; "128:*"
0x18002eedd  call    cs:__imp_SysAllocString
0x18002eee4  nop     dword ptr [rax+rax+00h]
0x18002eee9  mov     rdi, rax
0x18002eeec  test    rax, rax
0x18002eeef  jz      loc_18002F199
0x18002eef5  lea     rcx, aSystem_0; "System"
0x18002eefc  call    cs:__imp_SysAllocString
0x18002ef03  nop     dword ptr [rax+rax+00h]
0x18002ef08  mov     r15, rax
0x18002ef0b  test    rax, rax
0x18002ef0e  jz      loc_18002F199
0x18002ef14  mov     rcx, [rbp+arg_18]
0x18002ef18  mov     rdx, [rcx]
0x18002ef1b  mov     rax, [rdx+48h]
0x18002ef1f  mov     rdx, rbx
0x18002ef22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef27  mov     rcx, [rbp+arg_8]
0x18002ef2b  mov     rdx, [rcx]
0x18002ef2e  mov     rax, [rdx+150h]
0x18002ef35  mov     edx, 1
0x18002ef3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef3f  test    eax, eax
0x18002ef41  js      loc_18002F2E3
0x18002ef47  mov     rcx, [rbp+arg_8]
0x18002ef4b  mov     rdx, rbx
0x18002ef4e  mov     rax, [rcx]
0x18002ef51  mov     rax, [rax+40h]
0x18002ef55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef5a  test    eax, eax
0x18002ef5c  js      loc_18002F301
0x18002ef62  mov     rcx, [rbp+arg_8]
0x18002ef66  mov     rdx, r14
0x18002ef69  mov     rax, [rcx]
0x18002ef6c  mov     rax, [rax+50h]
0x18002ef70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef75  test    eax, eax
0x18002ef77  js      loc_18002F309
0x18002ef7d  mov     rcx, [rbp+arg_8]
0x18002ef81  mov     edx, 1
0x18002ef86  mov     rax, [rcx]
0x18002ef89  mov     rax, [rax+0E0h]
0x18002ef90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef95  test    eax, eax
0x18002ef97  js      loc_18002F311
0x18002ef9d  mov     rcx, [rbp+arg_8]
0x18002efa1  mov     edx, 0FFFFFFFFh
0x18002efa6  mov     rax, [rcx]
0x18002efa9  mov     rax, [rax+110h]
0x18002efb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efb5  test    eax, eax
0x18002efb7  js      loc_18002F319
0x18002efbd  mov     rcx, [rbp+arg_8]
0x18002efc1  mov     rdx, rsi
0x18002efc4  mov     rax, [rcx]
0x18002efc7  mov     rax, [rax+120h]
0x18002efce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efd3  test    eax, eax
0x18002efd5  js      loc_18002F321
0x18002efdb  mov     rcx, [rbp+arg_8]
0x18002efdf  mov     edx, 3Ah ; ':'
0x18002efe4  mov     rax, [rcx]
0x18002efe7  mov     rax, [rax+80h]
0x18002efee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eff3  test    eax, eax
0x18002eff5  js      loc_18002F32C
0x18002effb  mov     rcx, [rbp+arg_8]
0x18002efff  mov     rdx, rdi
0x18002f002  mov     rax, [rcx]
0x18002f005  mov     rax, [rax+0D0h]
0x18002f00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f011  test    eax, eax
0x18002f013  js      loc_18002F337
0x18002f019  mov     rcx, [rbp+arg_8]
0x18002f01d  mov     rdx, r15
0x18002f020  mov     rax, [rcx]
0x18002f023  mov     rax, [rax+60h]
0x18002f027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f02c  test    eax, eax
0x18002f02e  js      loc_18002F342
0x18002f034  test    r13b, r13b
0x18002f037  jnz     loc_18002F27A
0x18002f03d  lea     rcx, aIphlpsvcDll503; "@IpHlpSvc.dll,-503"
0x18002f044  call    cs:__imp_SysAllocString
0x18002f04b  nop     dword ptr [rax+rax+00h]
0x18002f050  mov     r12, rax
0x18002f053  test    rax, rax
0x18002f056  jz      loc_18002F199
0x18002f05c  mov     rcx, [rbp+arg_18]
0x18002f060  mov     rdx, rax
0x18002f063  mov     r8, [rcx]
0x18002f066  mov     rax, [r8+48h]
0x18002f06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f06f  mov     rcx, [rbp+arg_10]
0x18002f073  mov     edx, 1
0x18002f078  mov     r8, [rcx]
0x18002f07b  mov     rax, [r8+150h]
0x18002f082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f087  test    eax, eax
0x18002f089  js      loc_18002F2A2
0x18002f08f  mov     rcx, [rbp+arg_10]
0x18002f093  mov     rdx, r12
0x18002f096  mov     rax, [rcx]
0x18002f099  mov     rax, [rax+40h]
0x18002f09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0a2  test    eax, eax
0x18002f0a4  js      loc_18002F34D
0x18002f0aa  mov     rcx, [rbp+arg_10]
0x18002f0ae  mov     rdx, r14
0x18002f0b1  mov     rax, [rcx]
0x18002f0b4  mov     rax, [rax+50h]
0x18002f0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0bd  test    eax, eax
0x18002f0bf  js      loc_18002F358
0x18002f0c5  mov     rcx, [rbp+arg_10]
0x18002f0c9  mov     edx, 2
0x18002f0ce  mov     rax, [rcx]
0x18002f0d1  mov     rax, [rax+0E0h]
0x18002f0d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0dd  test    eax, eax
0x18002f0df  js      loc_18002F363
0x18002f0e5  mov     rcx, [rbp+arg_10]
0x18002f0e9  mov     edx, 0FFFFFFFFh
0x18002f0ee  mov     rax, [rcx]
0x18002f0f1  mov     rax, [rax+110h]
0x18002f0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0fd  test    eax, eax
0x18002f0ff  js      loc_18002F2DB
0x18002f105  mov     rcx, [rbp+arg_10]
0x18002f109  mov     rdx, rsi
0x18002f10c  mov     rax, [rcx]
0x18002f10f  mov     rax, [rax+120h]
0x18002f116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f11b  test    eax, eax
0x18002f11d  js      loc_18002F36E
0x18002f123  mov     rcx, [rbp+arg_10]
0x18002f127  mov     edx, 3Ah ; ':'
0x18002f12c  mov     rax, [rcx]
0x18002f12f  mov     rax, [rax+80h]
0x18002f136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f13b  test    eax, eax
0x18002f13d  js      loc_18002F379
0x18002f143  mov     rcx, [rbp+arg_10]
0x18002f147  mov     rdx, rdi
0x18002f14a  mov     rax, [rcx]
0x18002f14d  mov     rax, [rax+0D0h]
0x18002f154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f159  test    eax, eax
0x18002f15b  js      loc_18002F384
0x18002f161  mov     rcx, [rbp+arg_18]
0x18002f165  mov     rdx, [rbp+arg_8]
0x18002f169  mov     rax, [rcx]
0x18002f16c  mov     rax, [rax+40h]
0x18002f170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f175  test    eax, eax
0x18002f177  js      loc_18002F38F
0x18002f17d  mov     rcx, [rbp+arg_18]
0x18002f181  mov     rdx, [rbp+arg_10]
0x18002f185  mov     rax, [rcx]
0x18002f188  mov     rax, [rax+40h]
0x18002f18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f191  test    eax, eax
0x18002f193  js      loc_18002F39A
0x18002f199  mov     rcx, [rbp+arg_10]
0x18002f19d  test    rcx, rcx
0x18002f1a0  jz      short loc_18002F1AE
0x18002f1a2  mov     rax, [rcx]
0x18002f1a5  mov     rax, [rax+10h]
0x18002f1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1ae  mov     rcx, [rbp+arg_8]
0x18002f1b2  test    rcx, rcx
0x18002f1b5  jz      short loc_18002F1C3
0x18002f1b7  mov     rax, [rcx]
0x18002f1ba  mov     rax, [rax+10h]
0x18002f1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1c3  mov     rcx, [rbp+arg_18]
0x18002f1c7  test    rcx, rcx
0x18002f1ca  jz      short loc_18002F1D8
0x18002f1cc  mov     rax, [rcx]
0x18002f1cf  mov     rax, [rax+10h]
0x18002f1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1d8  mov     rcx, [rbp+var_30]
0x18002f1dc  test    rcx, rcx
0x18002f1df  jz      short loc_18002F1ED
0x18002f1e1  mov     rax, [rcx]
0x18002f1e4  mov     rax, [rax+10h]
0x18002f1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1ed  test    rbx, rbx
0x18002f1f0  jz      short loc_18002F201
0x18002f1f2  mov     rcx, rbx; bstrString
0x18002f1f5  call    cs:__imp_SysFreeString
0x18002f1fc  nop     dword ptr [rax+rax+00h]
0x18002f201  mov     rbx, [rsp+60h+arg_0]
0x18002f209  test    r12, r12
0x18002f20c  jnz     loc_18002F3BD
0x18002f212  mov     r12, [rsp+60h+var_18]
0x18002f217  test    r14, r14
0x18002f21a  jnz     loc_18002F3D1
0x18002f220  mov     r14, [rsp+60h+var_20]
0x18002f225  test    rsi, rsi
0x18002f228  jnz     loc_18002F3E5
0x18002f22e  mov     rsi, [rsp+60h+var_8]
0x18002f233  test    rdi, rdi
0x18002f236  jnz     loc_18002F3F9
0x18002f23c  mov     rdi, [rsp+60h+var_10]
0x18002f241  test    r15, r15
0x18002f244  jnz     loc_18002F40D
0x18002f24a  call    cs:__imp_CoUninitialize
0x18002f251  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
