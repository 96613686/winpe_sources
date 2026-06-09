# RegistryConfig::ParsePhase(HKEY__ *)

- ea: `0x1400090ec`
- end: `0x140009322`
- name: `?ParsePhase@RegistryConfig@@AEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEAUHKEY__@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140008b38`

## callees

- `0x140001518`
- `0x140007b38`
- `0x140007ce0`
- `0x140008120`
- `0x140008f54`
- `0x1400090ec`
- `0x140009328`
- `0x140009ecc`
- `0x14000a370`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000931b`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000931b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400092dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400092dc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400092c6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400092c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400091e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400091e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140009188`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140009188`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400092a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400092a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall RegistryConfig::ParsePhase(__int64 a1, _QWORD *a2, HKEY a3)
{
  DWORD v6; // esi
  int *v7; // rbx
  DWORD i; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rax
  __int64 v13; // r15
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-59h] BYREF
  DWORD cchName[2]; // [rsp+64h] [rbp-55h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-4Dh] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-49h] BYREF
  int *v22; // [rsp+78h] [rbp-41h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+80h] [rbp-39h] BYREF
  __int64 v24; // [rsp+90h] [rbp-29h]
  _QWORD *v25; // [rsp+98h] [rbp-21h]
  _BYTE v26[56]; // [rsp+A0h] [rbp-19h] BYREF

  v25 = a2;
  *a2 = 0;
  a2[1] = 0;
  *a2 = std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(a1, 0, 0);
  cchName[1] = 1;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( !RegQueryInfoKeyW(a3, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    *(_OWORD *)lpSubKey = 0;
    v24 = 0;
    cchName[0] = cbMaxSubKeyLen + 1;
    if ( cbMaxSubKeyLen != -1 )
      std::vector<unsigned short>::_Reallocate(lpSubKey, cbMaxSubKeyLen + 1);
    v6 = 0;
    v7 = (int *)lpSubKey[0];
    for ( i = 0; !RegEnumKeyExW(a3, i, (LPWSTR)v7, cchName, 0, 0, 0, 0); i = v6 )
    {
      phkResult = 0;
      if ( RegOpenKeyExW(a3, (LPCWSTR)v7, 0, 0x20019u, &phkResult) )
      {
        if ( (unsigned int)dword_140010000 > 2 )
        {
          v22 = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v9,
            (unsigned int)&word_14000D5C6,
            v10,
            v11,
            (__int64)&v22);
        }
      }
      else
      {
        if ( (unsigned int)dword_140010000 > 4 )
        {
          v22 = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v9,
            (unsigned int)&byte_14000D607,
            v10,
            v11,
            (__int64)&v22);
        }
        v12 = RegistryConfig::ParseCommandSet(a1, (__int64)v26, phkResult, v7);
        v13 = *a2;
        v15 = std::_List_buy<CommandSet>::_Buynode<CommandSet>(v14, *a2, *(_QWORD *)(*a2 + 8LL), v12);
        v16 = a2[1];
        if ( v16 == 0x38E38E38E38E38DLL )
          std::_Xlength_error("list<T> too long");
        a2[1] = v16 + 1;
        *(_QWORD *)(v13 + 8) = v15;
        **(_QWORD **)(v15 + 8) = v15;
        CommandSet::~CommandSet((CommandSet *)v26);
      }
      cchName[0] = cbMaxSubKeyLen + 1;
      ++v6;
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    if ( v7 )
      operator delete(v7);
  }
  std::list<CommandSet>::sort(a2);
  return a2;
}

```

## disassembly

```asm
0x1400090ec  mov     [rsp-8+arg_18], rbx
0x1400090f1  push    rbp
0x1400090f2  push    rsi
0x1400090f3  push    rdi
0x1400090f4  push    r12
0x1400090f6  push    r13
0x1400090f8  push    r14
0x1400090fa  push    r15
0x1400090fc  lea     rbp, [rsp-27h]
0x140009101  sub     rsp, 0E0h
0x140009108  mov     rax, cs:__security_cookie
0x14000910f  xor     rax, rsp
0x140009112  mov     [rbp+57h+var_38], rax
0x140009116  mov     r14, r8
0x140009119  mov     rdi, rdx
0x14000911c  mov     r12, rcx
0x14000911f  mov     [rbp+57h+var_78], rdx
0x140009123  xor     r13d, r13d
0x140009126  mov     [rbp+57h+var_A8], r13d
0x14000912a  mov     [rdx], r13
0x14000912d  mov     [rdx+8], r13
0x140009131  xor     r8d, r8d
0x140009134  xor     edx, edx
0x140009136  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x14000913b  mov     [rdi], rax
0x14000913e  mov     [rbp+57h+var_A8], 1
0x140009145  mov     [rbp+57h+cSubKeys], r13d
0x140009149  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x14000914d  mov     [rsp+110h+lpftLastWriteTime], r13; lpftLastWriteTime
0x140009152  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x140009157  mov     [rsp+110h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x14000915c  mov     [rsp+110h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x140009161  mov     [rsp+110h+lpcValues], r13; lpcValues
0x140009166  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x14000916b  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14000916f  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140009174  lea     rax, [rbp+57h+cSubKeys]
0x140009178  mov     [rsp+110h+lpcSubKeys], rax; lpcSubKeys
0x14000917d  xor     r9d, r9d; lpReserved
0x140009180  xor     r8d, r8d; lpcchClass
0x140009183  xor     edx, edx; lpClass
0x140009185  mov     rcx, r14; hKey
0x140009188  call    cs:__imp_RegQueryInfoKeyW
0x14000918e  test    eax, eax
0x140009190  jnz     loc_1400092E2
0x140009196  xorps   xmm0, xmm0
0x140009199  movdqu  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x14000919e  mov     [rbp+57h+var_80], r13
0x1400091a2  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1400091a5  add     eax, 1
0x1400091a8  mov     [rbp+57h+cchName], eax
0x1400091ab  mov     edx, eax
0x1400091ad  jz      short loc_1400091B8
0x1400091af  lea     rcx, [rbp+57h+lpSubKey]
0x1400091b3  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x1400091b8  mov     esi, r13d
0x1400091bb  mov     rbx, [rbp+57h+lpSubKey]
0x1400091bf  xor     edx, edx
0x1400091c1  jmp     loc_1400092A8
0x1400091c6  mov     [rbp+57h+phkResult], r13
0x1400091ca  lea     rax, [rbp+57h+phkResult]
0x1400091ce  mov     [rsp+110h+lpcSubKeys], rax; phkResult
0x1400091d3  mov     r9d, 20019h; samDesired
0x1400091d9  xor     r8d, r8d; ulOptions
0x1400091dc  mov     rdx, rbx; lpSubKey
0x1400091df  mov     rcx, r14; hKey
0x1400091e2  call    cs:__imp_RegOpenKeyExW
0x1400091e8  test    eax, eax
0x1400091ea  mov     eax, cs:dword_140010000
0x1400091f0  jnz     short loc_14000926F
0x1400091f2  cmp     eax, 4
0x1400091f5  jbe     short loc_140009210
0x1400091f7  mov     [rbp+57h+var_98], rbx
0x1400091fb  lea     rax, [rbp+57h+var_98]
0x1400091ff  mov     [rsp+110h+lpcSubKeys], rax
0x140009204  lea     rdx, byte_14000D607
0x14000920b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x140009210  mov     r9, rbx
0x140009213  mov     r8, [rbp+57h+phkResult]
0x140009217  lea     rdx, [rbp+57h+var_70]
0x14000921b  mov     rcx, r12
0x14000921e  call    ?ParseCommandSet@RegistryConfig@@AEAA?AUCommandSet@@PEAUHKEY__@@PEBG@Z; RegistryConfig::ParseCommandSet(HKEY__ *,ushort const *)
0x140009223  nop
0x140009224  mov     r15, [rdi]
0x140009227  mov     r9, rax
0x14000922a  mov     r8, [r15+8]
0x14000922e  mov     rdx, r15
0x140009231  call    ??$_Buynode@UCommandSet@@@?$_List_buy@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@1@PEAU21@0$$QEAUCommandSet@@@Z; std::_List_buy<CommandSet>::_Buynode<CommandSet>(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *,CommandSet &&)
0x140009236  mov     rdx, [rdi+8]
0x14000923a  mov     rcx, 38E38E38E38E38Dh
0x140009244  sub     rcx, rdx
0x140009247  cmp     rcx, 1
0x14000924b  jb      loc_140009314
0x140009251  lea     rcx, [rdx+1]
0x140009255  mov     [rdi+8], rcx
0x140009259  mov     [r15+8], rax
0x14000925d  mov     rcx, [rax+8]
0x140009261  mov     [rcx], rax
0x140009264  lea     rcx, [rbp+57h+var_70]; this
0x140009268  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x14000926d  jmp     short loc_14000928D
0x14000926f  cmp     eax, 2
0x140009272  jbe     short loc_14000928D
0x140009274  mov     [rbp+57h+var_98], rbx
0x140009278  lea     rax, [rbp+57h+var_98]
0x14000927c  mov     [rsp+110h+lpcSubKeys], rax
0x140009281  lea     rdx, word_14000D5C6
0x140009288  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14000928d  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x140009290  inc     eax
0x140009292  mov     [rbp+57h+cchName], eax
0x140009295  inc     esi
0x140009297  mov     rcx, [rbp+57h+phkResult]; hKey
0x14000929b  test    rcx, rcx
0x14000929e  jz      short loc_1400092A6
0x1400092a0  call    cs:__imp_RegCloseKey
0x1400092a6  mov     edx, esi; dwIndex
0x1400092a8  mov     [rsp+110h+lpcValues], r13; lpftLastWriteTime
0x1400092ad  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcchClass
0x1400092b2  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpClass
0x1400092b7  mov     [rsp+110h+lpcSubKeys], r13; lpReserved
0x1400092bc  lea     r9, [rbp+57h+cchName]; lpcchName
0x1400092c0  mov     r8, rbx; lpName
0x1400092c3  mov     rcx, r14; hKey
0x1400092c6  call    cs:__imp_RegEnumKeyExW
0x1400092cc  test    eax, eax
0x1400092ce  jz      loc_1400091C6
0x1400092d4  test    rbx, rbx
0x1400092d7  jz      short loc_1400092E2
0x1400092d9  mov     rcx, rbx
0x1400092dc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400092e2  mov     rcx, rdi
0x1400092e5  call    ?sort@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXXZ; std::list<CommandSet>::sort(void)
0x1400092ea  mov     rax, rdi
0x1400092ed  mov     rcx, [rbp+57h+var_38]
0x1400092f1  xor     rcx, rsp; StackCookie
0x1400092f4  call    __security_check_cookie
0x1400092f9  mov     rbx, [rsp+110h+arg_18]
0x140009301  add     rsp, 0E0h
0x140009308  pop     r15
0x14000930a  pop     r14
0x14000930c  pop     r13
0x14000930e  pop     r12
0x140009310  pop     rdi
0x140009311  pop     rsi
0x140009312  pop     rbp
0x140009313  retn
0x140009314  lea     rcx, aListTTooLong; "list<T> too long"
0x14000931b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
