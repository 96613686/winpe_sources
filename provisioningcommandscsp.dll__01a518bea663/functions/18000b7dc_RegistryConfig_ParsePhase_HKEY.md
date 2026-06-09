# RegistryConfig::ParsePhase(HKEY__ *)

- ea: `0x18000b7dc`
- end: `0x18000ba12`
- name: `?ParsePhase@RegistryConfig@@AEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEAUHKEY__@@@Z`
- size: `566`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, HKEY)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b1c8`

## callees

- `0x180001340`
- `0x18000a010`
- `0x18000a330`
- `0x18000b660`
- `0x18000b7dc`
- `0x18000ba18`
- `0x18000ba6c`
- `0x18000c144`
- `0x18000c600`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ba0b`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ba0b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b9cc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b9cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b990`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b990`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000b9b6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000b9b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b8d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b8d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b878`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b878`

## pseudocode

```c
_QWORD *__fastcall RegistryConfig::ParsePhase(__int64 a1, _QWORD *a2, HKEY a3)
{
  DWORD v6; // esi
  WCHAR *v7; // rbx
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
  WCHAR *v22; // [rsp+78h] [rbp-41h] BYREF
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
    v7 = (WCHAR *)lpSubKey[0];
    for ( i = 0; !RegEnumKeyExW(a3, i, v7, cchName, 0, 0, 0, 0); i = v6 )
    {
      phkResult = 0;
      if ( RegOpenKeyExW(a3, v7, 0, 0x20019u, &phkResult) )
      {
        if ( (unsigned int)dword_180014230 > 2 )
        {
          v22 = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v9,
            (unsigned int)word_180010B3A,
            v10,
            v11,
            (__int64)&v22);
        }
      }
      else
      {
        if ( (unsigned int)dword_180014230 > 4 )
        {
          v22 = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v9,
            (unsigned int)byte_180010B7B,
            v10,
            v11,
            (__int64)&v22);
        }
        v12 = RegistryConfig::ParseCommandSet(a1, v26, phkResult, v7);
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
0x18000b7dc  mov     [rsp-8+arg_18], rbx
0x18000b7e1  push    rbp
0x18000b7e2  push    rsi
0x18000b7e3  push    rdi
0x18000b7e4  push    r12
0x18000b7e6  push    r13
0x18000b7e8  push    r14
0x18000b7ea  push    r15
0x18000b7ec  lea     rbp, [rsp-27h]
0x18000b7f1  sub     rsp, 0E0h
0x18000b7f8  mov     rax, cs:__security_cookie
0x18000b7ff  xor     rax, rsp
0x18000b802  mov     [rbp+57h+var_38], rax
0x18000b806  mov     r14, r8
0x18000b809  mov     rdi, rdx
0x18000b80c  mov     r12, rcx
0x18000b80f  mov     [rbp+57h+var_78], rdx
0x18000b813  xor     r13d, r13d
0x18000b816  mov     [rbp+57h+var_A8], r13d
0x18000b81a  mov     [rdx], r13
0x18000b81d  mov     [rdx+8], r13
0x18000b821  xor     r8d, r8d
0x18000b824  xor     edx, edx
0x18000b826  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000b82b  mov     [rdi], rax
0x18000b82e  mov     [rbp+57h+var_A8], 1
0x18000b835  mov     [rbp+57h+cSubKeys], r13d
0x18000b839  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18000b83d  mov     [rsp+110h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000b842  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000b847  mov     [rsp+110h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000b84c  mov     [rsp+110h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18000b851  mov     [rsp+110h+lpcValues], r13; lpcValues
0x18000b856  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000b85b  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18000b85f  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000b864  lea     rax, [rbp+57h+cSubKeys]
0x18000b868  mov     [rsp+110h+lpcSubKeys], rax; lpcSubKeys
0x18000b86d  xor     r9d, r9d; lpReserved
0x18000b870  xor     r8d, r8d; lpcchClass
0x18000b873  xor     edx, edx; lpClass
0x18000b875  mov     rcx, r14; hKey
0x18000b878  call    cs:__imp_RegQueryInfoKeyW
0x18000b87e  test    eax, eax
0x18000b880  jnz     loc_18000B9D2
0x18000b886  xorps   xmm0, xmm0
0x18000b889  movdqu  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18000b88e  mov     [rbp+57h+var_80], r13
0x18000b892  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000b895  add     eax, 1
0x18000b898  mov     [rbp+57h+cchName], eax
0x18000b89b  mov     edx, eax
0x18000b89d  jz      short loc_18000B8A8
0x18000b89f  lea     rcx, [rbp+57h+lpSubKey]
0x18000b8a3  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18000b8a8  mov     esi, r13d
0x18000b8ab  mov     rbx, [rbp+57h+lpSubKey]
0x18000b8af  xor     edx, edx
0x18000b8b1  jmp     loc_18000B998
0x18000b8b6  mov     [rbp+57h+phkResult], r13
0x18000b8ba  lea     rax, [rbp+57h+phkResult]
0x18000b8be  mov     [rsp+110h+lpcSubKeys], rax; phkResult
0x18000b8c3  mov     r9d, 20019h; samDesired
0x18000b8c9  xor     r8d, r8d; ulOptions
0x18000b8cc  mov     rdx, rbx; lpSubKey
0x18000b8cf  mov     rcx, r14; hKey
0x18000b8d2  call    cs:__imp_RegOpenKeyExW
0x18000b8d8  test    eax, eax
0x18000b8da  mov     eax, cs:dword_180014230
0x18000b8e0  jnz     short loc_18000B95F
0x18000b8e2  cmp     eax, 4
0x18000b8e5  jbe     short loc_18000B900
0x18000b8e7  mov     [rbp+57h+var_98], rbx
0x18000b8eb  lea     rax, [rbp+57h+var_98]
0x18000b8ef  mov     [rsp+110h+lpcSubKeys], rax
0x18000b8f4  lea     rdx, byte_180010B7B
0x18000b8fb  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000b900  mov     r9, rbx
0x18000b903  mov     r8, [rbp+57h+phkResult]
0x18000b907  lea     rdx, [rbp+57h+var_70]
0x18000b90b  mov     rcx, r12
0x18000b90e  call    ?ParseCommandSet@RegistryConfig@@AEAA?AUCommandSet@@PEAUHKEY__@@PEBG@Z; RegistryConfig::ParseCommandSet(HKEY__ *,ushort const *)
0x18000b913  nop
0x18000b914  mov     r15, [rdi]
0x18000b917  mov     r9, rax
0x18000b91a  mov     r8, [r15+8]
0x18000b91e  mov     rdx, r15
0x18000b921  call    ??$_Buynode@UCommandSet@@@?$_List_buy@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@1@PEAU21@0$$QEAUCommandSet@@@Z; std::_List_buy<CommandSet>::_Buynode<CommandSet>(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *,CommandSet &&)
0x18000b926  mov     rdx, [rdi+8]
0x18000b92a  mov     rcx, 38E38E38E38E38Dh
0x18000b934  sub     rcx, rdx
0x18000b937  cmp     rcx, 1
0x18000b93b  jb      loc_18000BA04
0x18000b941  lea     rcx, [rdx+1]
0x18000b945  mov     [rdi+8], rcx
0x18000b949  mov     [r15+8], rax
0x18000b94d  mov     rcx, [rax+8]
0x18000b951  mov     [rcx], rax
0x18000b954  lea     rcx, [rbp+57h+var_70]; this
0x18000b958  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x18000b95d  jmp     short loc_18000B97D
0x18000b95f  cmp     eax, 2
0x18000b962  jbe     short loc_18000B97D
0x18000b964  mov     [rbp+57h+var_98], rbx
0x18000b968  lea     rax, [rbp+57h+var_98]
0x18000b96c  mov     [rsp+110h+lpcSubKeys], rax
0x18000b971  lea     rdx, word_180010B3A
0x18000b978  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000b97d  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000b980  inc     eax
0x18000b982  mov     [rbp+57h+cchName], eax
0x18000b985  inc     esi
0x18000b987  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000b98b  test    rcx, rcx
0x18000b98e  jz      short loc_18000B996
0x18000b990  call    cs:__imp_RegCloseKey
0x18000b996  mov     edx, esi; dwIndex
0x18000b998  mov     [rsp+110h+lpcValues], r13; lpftLastWriteTime
0x18000b99d  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcchClass
0x18000b9a2  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpClass
0x18000b9a7  mov     [rsp+110h+lpcSubKeys], r13; lpReserved
0x18000b9ac  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000b9b0  mov     r8, rbx; lpName
0x18000b9b3  mov     rcx, r14; hKey
0x18000b9b6  call    cs:__imp_RegEnumKeyExW
0x18000b9bc  test    eax, eax
0x18000b9be  jz      loc_18000B8B6
0x18000b9c4  test    rbx, rbx
0x18000b9c7  jz      short loc_18000B9D2
0x18000b9c9  mov     rcx, rbx
0x18000b9cc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b9d2  mov     rcx, rdi
0x18000b9d5  call    ?sort@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXXZ; std::list<CommandSet>::sort(void)
0x18000b9da  mov     rax, rdi
0x18000b9dd  mov     rcx, [rbp+57h+var_38]
0x18000b9e1  xor     rcx, rsp; StackCookie
0x18000b9e4  call    __security_check_cookie
0x18000b9e9  mov     rbx, [rsp+110h+arg_18]
0x18000b9f1  add     rsp, 0E0h
0x18000b9f8  pop     r15
0x18000b9fa  pop     r14
0x18000b9fc  pop     r13
0x18000b9fe  pop     r12
0x18000ba00  pop     rdi
0x18000ba01  pop     rsi
0x18000ba02  pop     rbp
0x18000ba03  retn
0x18000ba04  lea     rcx, aListTTooLong; "list<T> too long"
0x18000ba0b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
