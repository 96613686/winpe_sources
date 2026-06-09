# RegistryConfig::ParsePhase(HKEY__ *)

- ea: `0x18000be6c`
- end: `0x18000c0c7`
- name: `?ParsePhase@RegistryConfig@@AEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEAUHKEY__@@@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b81c`

## callees

- `0x18000134c`
- `0x18000a50c`
- `0x18000a874`
- `0x18000bce8`
- `0x18000be6c`
- `0x18000c0d0`
- `0x18000c12c`
- `0x18000c744`
- `0x18000ccc0`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c0ba`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c0ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c074`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c074`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c02c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c02c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000c058`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000c058`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bf68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bf68`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000bf08`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000bf08`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall RegistryConfig::ParsePhase(__int64 a1, _QWORD *a2, HKEY a3)
{
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD v8; // esi
  WCHAR *v9; // rbx
  DWORD i; // edx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rax
  __int64 v15; // r15
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-59h] BYREF
  DWORD cchName[2]; // [rsp+64h] [rbp-55h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-4Dh] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-49h] BYREF
  WCHAR *v24; // [rsp+78h] [rbp-41h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+80h] [rbp-39h] BYREF
  __int64 v26; // [rsp+90h] [rbp-29h]
  _QWORD *v27; // [rsp+98h] [rbp-21h]
  _BYTE v28[56]; // [rsp+A0h] [rbp-19h] BYREF

  v27 = a2;
  *a2 = 0;
  a2[1] = 0;
  *a2 = std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(a1, 0, 0);
  cchName[1] = 1;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( !RegQueryInfoKeyW(a3, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    *(_OWORD *)lpSubKey = 0;
    v26 = 0;
    cchName[0] = cbMaxSubKeyLen + 1;
    if ( cbMaxSubKeyLen != -1 )
      std::vector<unsigned short>::_Reallocate(lpSubKey, cbMaxSubKeyLen + 1, v6, v7);
    v8 = 0;
    v9 = (WCHAR *)lpSubKey[0];
    for ( i = 0; !RegEnumKeyExW(a3, i, v9, cchName, 0, 0, 0, 0); i = v8 )
    {
      phkResult = 0;
      if ( RegOpenKeyExW(a3, v9, 0, 0x20019u, &phkResult) )
      {
        if ( (unsigned int)dword_180014230 > 2 )
        {
          v24 = v9;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v11,
            (unsigned int)word_180010B3A,
            v12,
            v13,
            (__int64)&v24);
        }
      }
      else
      {
        if ( (unsigned int)dword_180014230 > 4 )
        {
          v24 = v9;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v11,
            (unsigned int)byte_180010B7B,
            v12,
            v13,
            (__int64)&v24);
        }
        v14 = RegistryConfig::ParseCommandSet(a1, v28, phkResult, v9);
        v15 = *a2;
        v17 = std::_List_buy<CommandSet>::_Buynode<CommandSet>(v16, *a2, *(_QWORD *)(*a2 + 8LL), v14);
        v18 = a2[1];
        if ( v18 == 0x38E38E38E38E38DLL )
          std::_Xlength_error("list<T> too long");
        a2[1] = v18 + 1;
        *(_QWORD *)(v15 + 8) = v17;
        **(_QWORD **)(v17 + 8) = v17;
        CommandSet::~CommandSet((CommandSet *)v28);
      }
      cchName[0] = cbMaxSubKeyLen + 1;
      ++v8;
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    if ( v9 )
      operator delete(v9);
  }
  std::list<CommandSet>::sort(a2);
  return a2;
}

```

## disassembly

```asm
0x18000be6c  mov     [rsp-8+arg_18], rbx
0x18000be71  push    rbp
0x18000be72  push    rsi
0x18000be73  push    rdi
0x18000be74  push    r12
0x18000be76  push    r13
0x18000be78  push    r14
0x18000be7a  push    r15
0x18000be7c  lea     rbp, [rsp-27h]
0x18000be81  sub     rsp, 0E0h
0x18000be88  mov     rax, cs:__security_cookie
0x18000be8f  xor     rax, rsp
0x18000be92  mov     [rbp+57h+var_38], rax
0x18000be96  mov     r14, r8
0x18000be99  mov     rdi, rdx
0x18000be9c  mov     r12, rcx
0x18000be9f  mov     [rbp+57h+var_78], rdx
0x18000bea3  xor     r13d, r13d
0x18000bea6  mov     [rbp+57h+var_A8], r13d
0x18000beaa  mov     [rdx], r13
0x18000bead  mov     [rdx+8], r13
0x18000beb1  xor     r8d, r8d
0x18000beb4  xor     edx, edx
0x18000beb6  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000bebb  mov     [rdi], rax
0x18000bebe  mov     [rbp+57h+var_A8], 1
0x18000bec5  mov     [rbp+57h+cSubKeys], r13d
0x18000bec9  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18000becd  mov     [rsp+110h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000bed2  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000bed7  mov     [rsp+110h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000bedc  mov     [rsp+110h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18000bee1  mov     [rsp+110h+lpcValues], r13; lpcValues
0x18000bee6  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000beeb  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18000beef  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000bef4  lea     rax, [rbp+57h+cSubKeys]
0x18000bef8  mov     [rsp+110h+lpcSubKeys], rax; lpcSubKeys
0x18000befd  xor     r9d, r9d; lpReserved
0x18000bf00  xor     r8d, r8d; lpcchClass
0x18000bf03  xor     edx, edx; lpClass
0x18000bf05  mov     rcx, r14; hKey
0x18000bf08  call    cs:__imp_RegQueryInfoKeyW
0x18000bf0f  nop     dword ptr [rax+rax+00h]
0x18000bf14  test    eax, eax
0x18000bf16  jnz     loc_18000C080
0x18000bf1c  xorps   xmm0, xmm0
0x18000bf1f  movdqu  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18000bf24  mov     [rbp+57h+var_80], r13
0x18000bf28  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000bf2b  add     eax, 1
0x18000bf2e  mov     [rbp+57h+cchName], eax
0x18000bf31  mov     edx, eax
0x18000bf33  jz      short loc_18000BF3E
0x18000bf35  lea     rcx, [rbp+57h+lpSubKey]
0x18000bf39  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18000bf3e  mov     esi, r13d
0x18000bf41  mov     rbx, [rbp+57h+lpSubKey]
0x18000bf45  xor     edx, edx
0x18000bf47  jmp     loc_18000C03A
0x18000bf4c  mov     [rbp+57h+phkResult], r13
0x18000bf50  lea     rax, [rbp+57h+phkResult]
0x18000bf54  mov     [rsp+110h+lpcSubKeys], rax; phkResult
0x18000bf59  mov     r9d, 20019h; samDesired
0x18000bf5f  xor     r8d, r8d; ulOptions
0x18000bf62  mov     rdx, rbx; lpSubKey
0x18000bf65  mov     rcx, r14; hKey
0x18000bf68  call    cs:__imp_RegOpenKeyExW
0x18000bf6f  nop     dword ptr [rax+rax+00h]
0x18000bf74  test    eax, eax
0x18000bf76  mov     eax, cs:dword_180014230
0x18000bf7c  jnz     short loc_18000BFFB
0x18000bf7e  cmp     eax, 4
0x18000bf81  jbe     short loc_18000BF9C
0x18000bf83  mov     [rbp+57h+var_98], rbx
0x18000bf87  lea     rax, [rbp+57h+var_98]
0x18000bf8b  mov     [rsp+110h+lpcSubKeys], rax
0x18000bf90  lea     rdx, byte_180010B7B
0x18000bf97  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000bf9c  mov     r9, rbx
0x18000bf9f  mov     r8, [rbp+57h+phkResult]
0x18000bfa3  lea     rdx, [rbp+57h+var_70]
0x18000bfa7  mov     rcx, r12
0x18000bfaa  call    ?ParseCommandSet@RegistryConfig@@AEAA?AUCommandSet@@PEAUHKEY__@@PEBG@Z; RegistryConfig::ParseCommandSet(HKEY__ *,ushort const *)
0x18000bfaf  nop
0x18000bfb0  mov     r15, [rdi]
0x18000bfb3  mov     r9, rax
0x18000bfb6  mov     r8, [r15+8]
0x18000bfba  mov     rdx, r15
0x18000bfbd  call    ??$_Buynode@UCommandSet@@@?$_List_buy@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@1@PEAU21@0$$QEAUCommandSet@@@Z; std::_List_buy<CommandSet>::_Buynode<CommandSet>(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *,CommandSet &&)
0x18000bfc2  mov     rdx, [rdi+8]
0x18000bfc6  mov     rcx, 38E38E38E38E38Dh
0x18000bfd0  sub     rcx, rdx
0x18000bfd3  cmp     rcx, 1
0x18000bfd7  jb      loc_18000C0B3
0x18000bfdd  lea     rcx, [rdx+1]
0x18000bfe1  mov     [rdi+8], rcx
0x18000bfe5  mov     [r15+8], rax
0x18000bfe9  mov     rcx, [rax+8]
0x18000bfed  mov     [rcx], rax
0x18000bff0  lea     rcx, [rbp+57h+var_70]; this
0x18000bff4  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x18000bff9  jmp     short loc_18000C019
0x18000bffb  cmp     eax, 2
0x18000bffe  jbe     short loc_18000C019
0x18000c000  mov     [rbp+57h+var_98], rbx
0x18000c004  lea     rax, [rbp+57h+var_98]
0x18000c008  mov     [rsp+110h+lpcSubKeys], rax
0x18000c00d  lea     rdx, word_180010B3A
0x18000c014  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000c019  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000c01c  inc     eax
0x18000c01e  mov     [rbp+57h+cchName], eax
0x18000c021  inc     esi
0x18000c023  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000c027  test    rcx, rcx
0x18000c02a  jz      short loc_18000C038
0x18000c02c  call    cs:__imp_RegCloseKey
0x18000c033  nop     dword ptr [rax+rax+00h]
0x18000c038  mov     edx, esi; dwIndex
0x18000c03a  mov     [rsp+110h+lpcValues], r13; lpftLastWriteTime
0x18000c03f  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcchClass
0x18000c044  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpClass
0x18000c049  mov     [rsp+110h+lpcSubKeys], r13; lpReserved
0x18000c04e  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000c052  mov     r8, rbx; lpName
0x18000c055  mov     rcx, r14; hKey
0x18000c058  call    cs:__imp_RegEnumKeyExW
0x18000c05f  nop     dword ptr [rax+rax+00h]
0x18000c064  test    eax, eax
0x18000c066  jz      loc_18000BF4C
0x18000c06c  test    rbx, rbx
0x18000c06f  jz      short loc_18000C080
0x18000c071  mov     rcx, rbx
0x18000c074  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c07b  nop     dword ptr [rax+rax+00h]
0x18000c080  mov     rcx, rdi
0x18000c083  call    ?sort@?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAXXZ; std::list<CommandSet>::sort(void)
0x18000c088  mov     rax, rdi
0x18000c08b  mov     rcx, [rbp+57h+var_38]
0x18000c08f  xor     rcx, rsp; StackCookie
0x18000c092  call    __security_check_cookie
0x18000c097  mov     rbx, [rsp+110h+arg_18]
0x18000c09f  add     rsp, 0E0h
0x18000c0a6  pop     r15
0x18000c0a8  pop     r14
0x18000c0aa  pop     r13
0x18000c0ac  pop     r12
0x18000c0ae  pop     rdi
0x18000c0af  pop     rsi
0x18000c0b0  pop     rbp
0x18000c0b1  retn
0x18000c0b3  lea     rcx, aListTTooLong; "list<T> too long"
0x18000c0ba  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
