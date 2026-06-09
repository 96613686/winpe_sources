# TeredoRegisterIcmpv6FirewallExceptions

- ea: `0x18002ed20`
- end: `0x18002f411`
- name: `TeredoRegisterIcmpv6FirewallExceptions`
- size: `1777`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001de64`
- `0x18002ecac`

## callees

- `0x18000d7b0`
- `0x1800190e0`
- `0x18002ed20`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002f23a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002f23a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002eda9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ee08`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ee48`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002eda9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ee08`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ee48`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002ed4b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002ed4b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee70`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee8f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eeae`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eecd`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eeec`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f034`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee70`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee8f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eeae`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eecd`
- `OLEAUT32!__imp_SysAllocString` at `0x18002eeec`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f034`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f1e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3ec`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f400`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f1e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f3ec`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f400`

## string_xrefs

- `0x18002ee69`: `@IpHlpSvc.dll,-502`
- `0x18002eea7`: `@FirewallAPI.dll,-25000`
- `0x18002ee88`: `@FirewallAPI.dll,-28547`
- `0x18002f02d`: `@IpHlpSvc.dll,-503`
- `0x18002f2db`: `Com initialization failed for registering ICMPV6 exemptions.`

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
0x18002ed20  push    rbp
0x18002ed22  push    r13
0x18002ed24  push    r15
0x18002ed26  mov     rbp, rsp
0x18002ed29  sub     rsp, 60h
0x18002ed2d  xor     r15d, r15d
0x18002ed30  movzx   r13d, cl
0x18002ed34  xor     ecx, ecx; pvReserved
0x18002ed36  mov     [rbp+var_30], r15
0x18002ed3a  mov     edx, 4; dwCoInit
0x18002ed3f  mov     [rbp+arg_8], r15
0x18002ed43  mov     [rbp+arg_10], r15
0x18002ed47  mov     [rbp+arg_18], r15
0x18002ed4b  call    cs:__imp_CoInitializeEx
0x18002ed52  nop     dword ptr [rax+rax+00h]
0x18002ed57  test    eax, eax
0x18002ed59  js      loc_18002F2DB
0x18002ed5f  mov     [rsp+60h+arg_0], rbx
0x18002ed67  lea     rax, [rbp+var_30]
0x18002ed6b  mov     [rsp+60h+var_8], rsi
0x18002ed70  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x18002ed77  mov     [rsp+60h+var_10], rdi
0x18002ed7c  lea     rcx, CLSID_NetFwPolicy2; rclsid
0x18002ed83  mov     [rsp+60h+var_18], r12
0x18002ed88  xor     edx, edx; pUnkOuter
0x18002ed8a  mov     [rsp+60h+var_20], r14
0x18002ed8f  mov     r8d, 1; dwClsContext
0x18002ed95  mov     r14d, r15d
0x18002ed98  mov     [rsp+60h+ppv], rax; ppv
0x18002ed9d  mov     ebx, r15d
0x18002eda0  mov     r12d, r15d
0x18002eda3  mov     esi, r15d
0x18002eda6  mov     edi, r15d
0x18002eda9  call    cs:__imp_CoCreateInstance
0x18002edb0  nop     dword ptr [rax+rax+00h]
0x18002edb5  test    eax, eax
0x18002edb7  js      loc_18002F2B5
0x18002edbd  mov     rcx, [rbp+var_30]
0x18002edc1  lea     rdx, [rbp+arg_18]
0x18002edc5  mov     rax, [rcx]
0x18002edc8  mov     rax, [rax+90h]
0x18002edcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002edd4  mov     r9, [rbp+arg_18]
0x18002edd8  test    eax, eax
0x18002edda  js      loc_18002F251
0x18002ede0  test    r9, r9
0x18002ede3  jz      loc_18002F251
0x18002ede9  lea     rax, [rbp+arg_8]
0x18002eded  xor     edx, edx; pUnkOuter
0x18002edef  lea     r9, _GUID_af230d27_baba_4e42_aced_f524f22cfce2; riid
0x18002edf6  mov     [rsp+60h+ppv], rax; ppv
0x18002edfb  mov     r8d, 1; dwClsContext
0x18002ee01  lea     rcx, CLSID_NetFwRule; rclsid
0x18002ee08  call    cs:__imp_CoCreateInstance
0x18002ee0f  nop     dword ptr [rax+rax+00h]
0x18002ee14  mov     r9, [rbp+arg_8]
0x18002ee18  test    eax, eax
0x18002ee1a  js      loc_18002F3A1
0x18002ee20  test    r9, r9
0x18002ee23  jz      loc_18002F3A1
0x18002ee29  lea     rax, [rbp+arg_10]
0x18002ee2d  xor     edx, edx; pUnkOuter
0x18002ee2f  lea     r9, _GUID_af230d27_baba_4e42_aced_f524f22cfce2; riid
0x18002ee36  mov     [rsp+60h+ppv], rax; ppv
0x18002ee3b  mov     r8d, 1; dwClsContext
0x18002ee41  lea     rcx, CLSID_NetFwRule; rclsid
0x18002ee48  call    cs:__imp_CoCreateInstance
0x18002ee4f  nop     dword ptr [rax+rax+00h]
0x18002ee54  mov     r9, [rbp+arg_10]
0x18002ee58  test    eax, eax
0x18002ee5a  js      loc_18002F395
0x18002ee60  test    r9, r9
0x18002ee63  jz      loc_18002F395
0x18002ee69  lea     rcx, aIphlpsvcDll502; "@IpHlpSvc.dll,-502"
0x18002ee70  call    cs:__imp_SysAllocString
0x18002ee77  nop     dword ptr [rax+rax+00h]
0x18002ee7c  mov     rbx, rax
0x18002ee7f  test    rax, rax
0x18002ee82  jz      loc_18002F189
0x18002ee88  lea     rcx, aFirewallapiDll_0; "@FirewallAPI.dll,-28547"
0x18002ee8f  call    cs:__imp_SysAllocString
0x18002ee96  nop     dword ptr [rax+rax+00h]
0x18002ee9b  mov     r14, rax
0x18002ee9e  test    rax, rax
0x18002eea1  jz      loc_18002F189
0x18002eea7  lea     rcx, aFirewallapiDll_1; "@FirewallAPI.dll,-25000"
0x18002eeae  call    cs:__imp_SysAllocString
0x18002eeb5  nop     dword ptr [rax+rax+00h]
0x18002eeba  mov     rsi, rax
0x18002eebd  test    rax, rax
0x18002eec0  jz      loc_18002F189
0x18002eec6  lea     rcx, a128; "128:*"
0x18002eecd  call    cs:__imp_SysAllocString
0x18002eed4  nop     dword ptr [rax+rax+00h]
0x18002eed9  mov     rdi, rax
0x18002eedc  test    rax, rax
0x18002eedf  jz      loc_18002F189
0x18002eee5  lea     rcx, aSystem_0; "System"
0x18002eeec  call    cs:__imp_SysAllocString
0x18002eef3  nop     dword ptr [rax+rax+00h]
0x18002eef8  mov     r15, rax
0x18002eefb  test    rax, rax
0x18002eefe  jz      loc_18002F189
0x18002ef04  mov     rcx, [rbp+arg_18]
0x18002ef08  mov     rdx, [rcx]
0x18002ef0b  mov     rax, [rdx+48h]
0x18002ef0f  mov     rdx, rbx
0x18002ef12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef17  mov     rcx, [rbp+arg_8]
0x18002ef1b  mov     rdx, [rcx]
0x18002ef1e  mov     rax, [rdx+150h]
0x18002ef25  mov     edx, 1
0x18002ef2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef2f  test    eax, eax
0x18002ef31  js      loc_18002F2D3
0x18002ef37  mov     rcx, [rbp+arg_8]
0x18002ef3b  mov     rdx, rbx
0x18002ef3e  mov     rax, [rcx]
0x18002ef41  mov     rax, [rax+40h]
0x18002ef45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef4a  test    eax, eax
0x18002ef4c  js      loc_18002F2F1
0x18002ef52  mov     rcx, [rbp+arg_8]
0x18002ef56  mov     rdx, r14
0x18002ef59  mov     rax, [rcx]
0x18002ef5c  mov     rax, [rax+50h]
0x18002ef60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef65  test    eax, eax
0x18002ef67  js      loc_18002F2F9
0x18002ef6d  mov     rcx, [rbp+arg_8]
0x18002ef71  mov     edx, 1
0x18002ef76  mov     rax, [rcx]
0x18002ef79  mov     rax, [rax+0E0h]
0x18002ef80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef85  test    eax, eax
0x18002ef87  js      loc_18002F301
0x18002ef8d  mov     rcx, [rbp+arg_8]
0x18002ef91  mov     edx, 0FFFFFFFFh
0x18002ef96  mov     rax, [rcx]
0x18002ef99  mov     rax, [rax+110h]
0x18002efa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efa5  test    eax, eax
0x18002efa7  js      loc_18002F309
0x18002efad  mov     rcx, [rbp+arg_8]
0x18002efb1  mov     rdx, rsi
0x18002efb4  mov     rax, [rcx]
0x18002efb7  mov     rax, [rax+120h]
0x18002efbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efc3  test    eax, eax
0x18002efc5  js      loc_18002F311
0x18002efcb  mov     rcx, [rbp+arg_8]
0x18002efcf  mov     edx, 3Ah ; ':'
0x18002efd4  mov     rax, [rcx]
0x18002efd7  mov     rax, [rax+80h]
0x18002efde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efe3  test    eax, eax
0x18002efe5  js      loc_18002F31C
0x18002efeb  mov     rcx, [rbp+arg_8]
0x18002efef  mov     rdx, rdi
0x18002eff2  mov     rax, [rcx]
0x18002eff5  mov     rax, [rax+0D0h]
0x18002effc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f001  test    eax, eax
0x18002f003  js      loc_18002F327
0x18002f009  mov     rcx, [rbp+arg_8]
0x18002f00d  mov     rdx, r15
0x18002f010  mov     rax, [rcx]
0x18002f013  mov     rax, [rax+60h]
0x18002f017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f01c  test    eax, eax
0x18002f01e  js      loc_18002F332
0x18002f024  test    r13b, r13b
0x18002f027  jnz     loc_18002F26A
0x18002f02d  lea     rcx, aIphlpsvcDll503; "@IpHlpSvc.dll,-503"
0x18002f034  call    cs:__imp_SysAllocString
0x18002f03b  nop     dword ptr [rax+rax+00h]
0x18002f040  mov     r12, rax
0x18002f043  test    rax, rax
0x18002f046  jz      loc_18002F189
0x18002f04c  mov     rcx, [rbp+arg_18]
0x18002f050  mov     rdx, rax
0x18002f053  mov     r8, [rcx]
0x18002f056  mov     rax, [r8+48h]
0x18002f05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f05f  mov     rcx, [rbp+arg_10]
0x18002f063  mov     edx, 1
0x18002f068  mov     r8, [rcx]
0x18002f06b  mov     rax, [r8+150h]
0x18002f072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f077  test    eax, eax
0x18002f079  js      loc_18002F292
0x18002f07f  mov     rcx, [rbp+arg_10]
0x18002f083  mov     rdx, r12
0x18002f086  mov     rax, [rcx]
0x18002f089  mov     rax, [rax+40h]
0x18002f08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f092  test    eax, eax
0x18002f094  js      loc_18002F33D
0x18002f09a  mov     rcx, [rbp+arg_10]
0x18002f09e  mov     rdx, r14
0x18002f0a1  mov     rax, [rcx]
0x18002f0a4  mov     rax, [rax+50h]
0x18002f0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0ad  test    eax, eax
0x18002f0af  js      loc_18002F348
0x18002f0b5  mov     rcx, [rbp+arg_10]
0x18002f0b9  mov     edx, 2
0x18002f0be  mov     rax, [rcx]
0x18002f0c1  mov     rax, [rax+0E0h]
0x18002f0c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0cd  test    eax, eax
0x18002f0cf  js      loc_18002F353
0x18002f0d5  mov     rcx, [rbp+arg_10]
0x18002f0d9  mov     edx, 0FFFFFFFFh
0x18002f0de  mov     rax, [rcx]
0x18002f0e1  mov     rax, [rax+110h]
0x18002f0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0ed  test    eax, eax
0x18002f0ef  js      loc_18002F2CB
0x18002f0f5  mov     rcx, [rbp+arg_10]
0x18002f0f9  mov     rdx, rsi
0x18002f0fc  mov     rax, [rcx]
0x18002f0ff  mov     rax, [rax+120h]
0x18002f106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f10b  test    eax, eax
0x18002f10d  js      loc_18002F35E
0x18002f113  mov     rcx, [rbp+arg_10]
0x18002f117  mov     edx, 3Ah ; ':'
0x18002f11c  mov     rax, [rcx]
0x18002f11f  mov     rax, [rax+80h]
0x18002f126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f12b  test    eax, eax
0x18002f12d  js      loc_18002F369
0x18002f133  mov     rcx, [rbp+arg_10]
0x18002f137  mov     rdx, rdi
0x18002f13a  mov     rax, [rcx]
0x18002f13d  mov     rax, [rax+0D0h]
0x18002f144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f149  test    eax, eax
0x18002f14b  js      loc_18002F374
0x18002f151  mov     rcx, [rbp+arg_18]
0x18002f155  mov     rdx, [rbp+arg_8]
0x18002f159  mov     rax, [rcx]
0x18002f15c  mov     rax, [rax+40h]
0x18002f160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f165  test    eax, eax
0x18002f167  js      loc_18002F37F
0x18002f16d  mov     rcx, [rbp+arg_18]
0x18002f171  mov     rdx, [rbp+arg_10]
0x18002f175  mov     rax, [rcx]
0x18002f178  mov     rax, [rax+40h]
0x18002f17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f181  test    eax, eax
0x18002f183  js      loc_18002F38A
0x18002f189  mov     rcx, [rbp+arg_10]
0x18002f18d  test    rcx, rcx
0x18002f190  jz      short loc_18002F19E
0x18002f192  mov     rax, [rcx]
0x18002f195  mov     rax, [rax+10h]
0x18002f199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f19e  mov     rcx, [rbp+arg_8]
0x18002f1a2  test    rcx, rcx
0x18002f1a5  jz      short loc_18002F1B3
0x18002f1a7  mov     rax, [rcx]
0x18002f1aa  mov     rax, [rax+10h]
0x18002f1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1b3  mov     rcx, [rbp+arg_18]
0x18002f1b7  test    rcx, rcx
0x18002f1ba  jz      short loc_18002F1C8
0x18002f1bc  mov     rax, [rcx]
0x18002f1bf  mov     rax, [rax+10h]
0x18002f1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1c8  mov     rcx, [rbp+var_30]
0x18002f1cc  test    rcx, rcx
0x18002f1cf  jz      short loc_18002F1DD
0x18002f1d1  mov     rax, [rcx]
0x18002f1d4  mov     rax, [rax+10h]
0x18002f1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1dd  test    rbx, rbx
0x18002f1e0  jz      short loc_18002F1F1
0x18002f1e2  mov     rcx, rbx; bstrString
0x18002f1e5  call    cs:__imp_SysFreeString
0x18002f1ec  nop     dword ptr [rax+rax+00h]
0x18002f1f1  mov     rbx, [rsp+60h+arg_0]
0x18002f1f9  test    r12, r12
0x18002f1fc  jnz     loc_18002F3AD
0x18002f202  mov     r12, [rsp+60h+var_18]
0x18002f207  test    r14, r14
0x18002f20a  jnz     loc_18002F3C1
0x18002f210  mov     r14, [rsp+60h+var_20]
0x18002f215  test    rsi, rsi
0x18002f218  jnz     loc_18002F3D5
0x18002f21e  mov     rsi, [rsp+60h+var_8]
0x18002f223  test    rdi, rdi
0x18002f226  jnz     loc_18002F3E9
0x18002f22c  mov     rdi, [rsp+60h+var_10]
0x18002f231  test    r15, r15
0x18002f234  jnz     loc_18002F3FD
0x18002f23a  call    cs:__imp_CoUninitialize
0x18002f241  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
