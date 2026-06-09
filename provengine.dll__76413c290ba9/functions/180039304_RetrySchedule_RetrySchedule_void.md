# RetrySchedule::RetrySchedule(void)

- ea: `0x180039304`
- end: `0x1800394ef`
- name: `??0RetrySchedule@@QEAA@XZ`
- size: `491`
- prototype: `RetrySchedule *__fastcall(RetrySchedule *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000f6a0`

## callees

- `0x1800092dc`
- `0x18000b030`
- `0x180020b74`
- `0x180039010`
- `0x180039304`
- `0x1800394f8`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800393e4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003942d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039476`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800394bf`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800393e4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003942d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039476`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800394bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039377`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039377`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800394cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800394cf`

## string_xrefs

- `0x18003934a`: `SOFTWARE\Microsoft\Provisioning\Agent\RetrySchedule`
- `0x180039351`: `OSData\SOFTWARE\Microsoft\Provisioning\Agent\RetrySchedule`

## pseudocode

```c
RetrySchedule *__fastcall RetrySchedule::RetrySchedule(RetrySchedule *this)
{
  bool IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  HKEY hKey[2]; // [rsp+30h] [rbp-48h] BYREF
  void *v6[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v7; // [rsp+50h] [rbp-28h]
  unsigned __int64 v8; // [rsp+58h] [rbp-20h]

  hKey[1] = (HKEY)this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,long>>>::_Buyheadnode();
  hKey[0] = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v3 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Agent\\RetrySchedule";
  if ( !IsStateSeparationEnabled )
    v3 = L"SOFTWARE\\Microsoft\\Provisioning\\Agent\\RetrySchedule";
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, hKey) )
    ForEachRegValue__lambda_e405e640301f66b5d70cf538f601e620_(hKey[0]);
  if ( !*((_QWORD *)this + 1) )
  {
    v8 = 7;
    v7 = 0;
    LOWORD(v6[0]) = 0;
    std::wstring::assign(v6, L"0");
    *(_DWORD *)std::map<std::wstring,unsigned long>::operator[](this, v6) = 120;
    if ( v8 >= 8 )
      operator delete(v6[0]);
    v8 = 7;
    v7 = 0;
    LOWORD(v6[0]) = 0;
    std::wstring::assign(v6, L"1");
    *(_DWORD *)std::map<std::wstring,unsigned long>::operator[](this, v6) = 900;
    if ( v8 >= 8 )
      operator delete(v6[0]);
    v8 = 7;
    v7 = 0;
    LOWORD(v6[0]) = 0;
    std::wstring::assign(v6, L"2");
    *(_DWORD *)std::map<std::wstring,unsigned long>::operator[](this, v6) = 3600;
    if ( v8 >= 8 )
      operator delete(v6[0]);
    v8 = 7;
    v7 = 0;
    LOWORD(v6[0]) = 0;
    std::wstring::assign(v6, L"3");
    *(_DWORD *)std::map<std::wstring,unsigned long>::operator[](this, v6) = 14400;
    if ( v8 >= 8 )
      operator delete(v6[0]);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return this;
}

```

## disassembly

```asm
0x180039304  push    rbp
0x180039306  push    rbx
0x180039307  push    rsi
0x180039308  push    r14
0x18003930a  mov     rbp, rsp
0x18003930d  sub     rsp, 78h
0x180039311  mov     rax, cs:__security_cookie
0x180039318  xor     rax, rsp
0x18003931b  mov     [rbp+var_18], rax
0x18003931f  mov     rbx, rcx
0x180039322  mov     [rbp+var_40], rcx
0x180039326  mov     qword ptr [rcx], 0
0x18003932d  mov     qword ptr [rcx+8], 0
0x180039335  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,long>>>::_Buyheadnode(void)
0x18003933a  mov     [rbx], rax
0x18003933d  mov     [rbp+hKey], 0
0x180039345  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x18003934a  lea     rcx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Provisioning\\Agen"...
0x180039351  lea     rdx, aOsdataSoftware_5; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x180039358  test    al, al
0x18003935a  cmovz   rdx, rcx; lpSubKey
0x18003935e  lea     rax, [rbp+hKey]
0x180039362  mov     [rsp+78h+phkResult], rax; phkResult
0x180039367  mov     r9d, 20019h; samDesired
0x18003936d  xor     r8d, r8d; ulOptions
0x180039370  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039377  call    cs:__imp_RegOpenKeyExW
0x18003937d  test    eax, eax
0x18003937f  jnz     short loc_18003938D
0x180039381  mov     rdx, rbx
0x180039384  mov     rcx, [rbp+hKey]; hKey
0x180039388  call    ForEachRegValue__lambda_e405e640301f66b5d70cf538f601e620___; ForEachRegValue__lambda_e405e640301f66b5d70cf538f601e620_
0x18003938d  cmp     qword ptr [rbx+8], 0
0x180039392  jnz     loc_1800394C6
0x180039398  mov     esi, 7
0x18003939d  mov     [rbp+var_20], rsi
0x1800393a1  mov     [rbp+var_28], 0
0x1800393a9  xor     eax, eax
0x1800393ab  mov     word ptr [rbp+var_38], ax
0x1800393af  lea     r14d, [rsi-6]
0x1800393b3  mov     r8d, r14d
0x1800393b6  lea     rdx, a0; "0"
0x1800393bd  lea     rcx, [rbp+var_38]; void *
0x1800393c1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800393c6  nop
0x1800393c7  lea     rdx, [rbp+var_38]
0x1800393cb  mov     rcx, rbx
0x1800393ce  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ulong>::operator[](std::wstring &&)
0x1800393d3  mov     dword ptr [rax], 78h ; 'x'
0x1800393d9  cmp     [rbp+var_20], 8
0x1800393de  jb      short loc_1800393EA
0x1800393e0  mov     rcx, [rbp+var_38]
0x1800393e4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800393ea  mov     [rbp+var_20], rsi
0x1800393ee  mov     [rbp+var_28], 0
0x1800393f6  xor     eax, eax
0x1800393f8  mov     word ptr [rbp+var_38], ax
0x1800393fc  mov     r8, r14
0x1800393ff  lea     rdx, a1; "1"
0x180039406  lea     rcx, [rbp+var_38]; void *
0x18003940a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003940f  nop
0x180039410  lea     rdx, [rbp+var_38]
0x180039414  mov     rcx, rbx
0x180039417  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ulong>::operator[](std::wstring &&)
0x18003941c  mov     dword ptr [rax], 384h
0x180039422  cmp     [rbp+var_20], 8
0x180039427  jb      short loc_180039433
0x180039429  mov     rcx, [rbp+var_38]
0x18003942d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039433  mov     [rbp+var_20], rsi
0x180039437  mov     [rbp+var_28], 0
0x18003943f  xor     eax, eax
0x180039441  mov     word ptr [rbp+var_38], ax
0x180039445  mov     r8, r14
0x180039448  lea     rdx, a2; "2"
0x18003944f  lea     rcx, [rbp+var_38]; void *
0x180039453  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180039458  nop
0x180039459  lea     rdx, [rbp+var_38]
0x18003945d  mov     rcx, rbx
0x180039460  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ulong>::operator[](std::wstring &&)
0x180039465  mov     dword ptr [rax], 0E10h
0x18003946b  cmp     [rbp+var_20], 8
0x180039470  jb      short loc_18003947C
0x180039472  mov     rcx, [rbp+var_38]
0x180039476  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003947c  mov     [rbp+var_20], rsi
0x180039480  mov     [rbp+var_28], 0
0x180039488  xor     eax, eax
0x18003948a  mov     word ptr [rbp+var_38], ax
0x18003948e  mov     r8, r14
0x180039491  lea     rdx, a3; "3"
0x180039498  lea     rcx, [rbp+var_38]; void *
0x18003949c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800394a1  nop
0x1800394a2  lea     rdx, [rbp+var_38]
0x1800394a6  mov     rcx, rbx
0x1800394a9  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ulong>::operator[](std::wstring &&)
0x1800394ae  mov     dword ptr [rax], 3840h
0x1800394b4  cmp     [rbp+var_20], 8
0x1800394b9  jb      short loc_1800394C6
0x1800394bb  mov     rcx, [rbp+var_38]
0x1800394bf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800394c5  nop
0x1800394c6  mov     rcx, [rbp+hKey]; hKey
0x1800394ca  test    rcx, rcx
0x1800394cd  jz      short loc_1800394D6
0x1800394cf  call    cs:__imp_RegCloseKey
0x1800394d5  nop
0x1800394d6  mov     rax, rbx
0x1800394d9  mov     rcx, [rbp+var_18]
0x1800394dd  xor     rcx, rsp; StackCookie
0x1800394e0  call    __security_check_cookie
0x1800394e5  add     rsp, 78h
0x1800394e9  pop     r14
0x1800394eb  pop     rsi
0x1800394ec  pop     rbx
0x1800394ed  pop     rbp
0x1800394ee  retn
```
