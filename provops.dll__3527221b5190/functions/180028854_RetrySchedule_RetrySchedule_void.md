# RetrySchedule::RetrySchedule(void)

- ea: `0x180028854`
- end: `0x180028a3f`
- name: `??0RetrySchedule@@QEAA@XZ`
- size: `491`
- prototype: `RetrySchedule *__fastcall(RetrySchedule *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180013e9c`

## callees

- `0x18001434c`
- `0x1800210f0`
- `0x180027bfc`
- `0x180028854`
- `0x180028a48`
- `0x180028bfc`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180028934`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002897d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800289c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028a0f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028934`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002897d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800289c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028a0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800288c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800288c7`

## string_xrefs

- `0x1800288a1`: `OSData\SOFTWARE\Microsoft\Provisioning\Agent\RetrySchedule`
- `0x18002889a`: `SOFTWARE\Microsoft\Provisioning\Agent\RetrySchedule`

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
  *(_QWORD *)this = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,unsigned long>>>::_Buyheadnode();
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
0x180028854  push    rbp
0x180028856  push    rbx
0x180028857  push    rsi
0x180028858  push    r14
0x18002885a  mov     rbp, rsp
0x18002885d  sub     rsp, 78h
0x180028861  mov     rax, cs:__security_cookie
0x180028868  xor     rax, rsp
0x18002886b  mov     [rbp+var_18], rax
0x18002886f  mov     rbx, rcx
0x180028872  mov     [rbp+var_40], rcx
0x180028876  mov     qword ptr [rcx], 0
0x18002887d  mov     qword ptr [rcx+8], 0
0x180028885  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,ulong>>>::_Buyheadnode(void)
0x18002888a  mov     [rbx], rax
0x18002888d  mov     [rbp+hKey], 0
0x180028895  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x18002889a  lea     rcx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Provisioning\\Agen"...
0x1800288a1  lea     rdx, aOsdataSoftware_3; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800288a8  test    al, al
0x1800288aa  cmovz   rdx, rcx; lpSubKey
0x1800288ae  lea     rax, [rbp+hKey]
0x1800288b2  mov     [rsp+78h+phkResult], rax; phkResult
0x1800288b7  mov     r9d, 20019h; samDesired
0x1800288bd  xor     r8d, r8d; ulOptions
0x1800288c0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800288c7  call    cs:__imp_RegOpenKeyExW
0x1800288cd  test    eax, eax
0x1800288cf  jnz     short loc_1800288DD
0x1800288d1  mov     rdx, rbx
0x1800288d4  mov     rcx, [rbp+hKey]; hKey
0x1800288d8  call    ForEachRegValue__lambda_e405e640301f66b5d70cf538f601e620___; ForEachRegValue__lambda_e405e640301f66b5d70cf538f601e620_
0x1800288dd  cmp     qword ptr [rbx+8], 0
0x1800288e2  jnz     loc_180028A16
0x1800288e8  mov     esi, 7
0x1800288ed  mov     [rbp+var_20], rsi
0x1800288f1  mov     [rbp+var_28], 0
0x1800288f9  xor     eax, eax
0x1800288fb  mov     word ptr [rbp+var_38], ax
0x1800288ff  lea     r14d, [rsi-6]
0x180028903  mov     r8d, r14d
0x180028906  lea     rdx, a0; "0"
0x18002890d  lea     rcx, [rbp+var_38]; void *
0x180028911  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180028916  nop
0x180028917  lea     rdx, [rbp+var_38]
0x18002891b  mov     rcx, rbx
0x18002891e  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ulong>::operator[](std::wstring &&)
0x180028923  mov     dword ptr [rax], 78h ; 'x'
0x180028929  cmp     [rbp+var_20], 8
0x18002892e  jb      short loc_18002893A
0x180028930  mov     rcx, [rbp+var_38]
0x180028934  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002893a  mov     [rbp+var_20], rsi
0x18002893e  mov     [rbp+var_28], 0
0x180028946  xor     eax, eax
0x180028948  mov     word ptr [rbp+var_38], ax
0x18002894c  mov     r8, r14
0x18002894f  lea     rdx, a1; "1"
0x180028956  lea     rcx, [rbp+var_38]; void *
0x18002895a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002895f  nop
0x180028960  lea     rdx, [rbp+var_38]
0x180028964  mov     rcx, rbx
0x180028967  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ulong>::operator[](std::wstring &&)
0x18002896c  mov     dword ptr [rax], 384h
0x180028972  cmp     [rbp+var_20], 8
0x180028977  jb      short loc_180028983
0x180028979  mov     rcx, [rbp+var_38]
0x18002897d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028983  mov     [rbp+var_20], rsi
0x180028987  mov     [rbp+var_28], 0
0x18002898f  xor     eax, eax
0x180028991  mov     word ptr [rbp+var_38], ax
0x180028995  mov     r8, r14
0x180028998  lea     rdx, a2; "2"
0x18002899f  lea     rcx, [rbp+var_38]; void *
0x1800289a3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800289a8  nop
0x1800289a9  lea     rdx, [rbp+var_38]
0x1800289ad  mov     rcx, rbx
0x1800289b0  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ulong>::operator[](std::wstring &&)
0x1800289b5  mov     dword ptr [rax], 0E10h
0x1800289bb  cmp     [rbp+var_20], 8
0x1800289c0  jb      short loc_1800289CC
0x1800289c2  mov     rcx, [rbp+var_38]
0x1800289c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800289cc  mov     [rbp+var_20], rsi
0x1800289d0  mov     [rbp+var_28], 0
0x1800289d8  xor     eax, eax
0x1800289da  mov     word ptr [rbp+var_38], ax
0x1800289de  mov     r8, r14
0x1800289e1  lea     rdx, a3; "3"
0x1800289e8  lea     rcx, [rbp+var_38]; void *
0x1800289ec  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800289f1  nop
0x1800289f2  lea     rdx, [rbp+var_38]
0x1800289f6  mov     rcx, rbx
0x1800289f9  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ulong>::operator[](std::wstring &&)
0x1800289fe  mov     dword ptr [rax], 3840h
0x180028a04  cmp     [rbp+var_20], 8
0x180028a09  jb      short loc_180028A16
0x180028a0b  mov     rcx, [rbp+var_38]
0x180028a0f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028a15  nop
0x180028a16  mov     rcx, [rbp+hKey]; hKey
0x180028a1a  test    rcx, rcx
0x180028a1d  jz      short loc_180028A26
0x180028a1f  call    cs:__imp_RegCloseKey
0x180028a25  nop
0x180028a26  mov     rax, rbx
0x180028a29  mov     rcx, [rbp+var_18]
0x180028a2d  xor     rcx, rsp; StackCookie
0x180028a30  call    __security_check_cookie
0x180028a35  add     rsp, 78h
0x180028a39  pop     r14
0x180028a3b  pop     rsi
0x180028a3c  pop     rbx
0x180028a3d  pop     rbp
0x180028a3e  retn
```
