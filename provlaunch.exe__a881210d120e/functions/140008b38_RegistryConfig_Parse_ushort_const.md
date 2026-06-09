# RegistryConfig::Parse(ushort const *)

- ea: `0x140008b38`
- end: `0x140008cdc`
- name: `?Parse@RegistryConfig@@QEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEBG@Z`
- size: `420`
- prototype: `__int64 *__fastcall(__int64, __int64 *, const WCHAR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000693c`

## callees

- `0x14000124c`
- `0x140001518`
- `0x140003560`
- `0x140008b38`
- `0x1400090ec`
- `0x140009328`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008b86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008bb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008b86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008bb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008bdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008c2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008cbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008bdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008c2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008cbe`

## pseudocode

```c
__int64 *__fastcall RegistryConfig::Parse(__int64 a1, __int64 *a2, const WCHAR *a3)
{
  HKEY v6; // rbx
  const WCHAR *v7; // rdx
  HKEY v8; // rcx
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  const WCHAR *v19; // [rsp+38h] [rbp-18h] BYREF
  __int64 v20; // [rsp+40h] [rbp-10h] BYREF
  __int64 v21; // [rsp+48h] [rbp-8h]
  HKEY phkResult; // [rsp+70h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  v6 = (HKEY)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) < 8u )
    v7 = (const WCHAR *)(a1 + 8);
  else
    v7 = *(const WCHAR **)v6;
  if ( RegOpenKeyExW(*(HKEY *)a1, v7, 0, 0x20019u, &hKey) )
  {
    if ( (unsigned int)dword_140010000 > 2 )
    {
      if ( *((_QWORD *)v6 + 3) >= 8u )
        v6 = *(HKEY *)v6;
      phkResult = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)byte_14000D58B,
        v9,
        v10,
        (__int64)&phkResult);
    }
    goto LABEL_18;
  }
  phkResult = 0;
  if ( RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult) )
  {
    if ( (unsigned int)dword_140010000 > 2 )
    {
      v19 = a3;
      if ( *((_QWORD *)v6 + 3) >= 8u )
        v6 = *(HKEY *)v6;
      v20 = (__int64)v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v11,
        (unsigned int)&unk_14000D648,
        v12,
        v13,
        (__int64)&v20,
        (__int64)&v19);
    }
    v8 = phkResult;
    if ( phkResult )
      RegCloseKey(phkResult);
LABEL_18:
    v21 = 0;
    v14 = std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(v8, 0, 0);
    v20 = v14;
    *a2 = 0;
    a2[1] = 0;
    v16 = std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(v15, 0, 0);
    *a2 = v14;
    v20 = v16;
    v17 = a2[1];
    a2[1] = 0;
    v21 = v17;
    std::list<CommandSet>::~list<CommandSet>(&v20);
    goto LABEL_19;
  }
  RegistryConfig::ParsePhase(a1, a2, phkResult);
  if ( phkResult )
    RegCloseKey(phkResult);
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  return a2;
}

```

## disassembly

```asm
0x140008b38  mov     [rsp-18h+arg_8], rbx
0x140008b3d  mov     [rsp-18h+arg_10], rsi
0x140008b42  push    rbp
0x140008b43  push    rdi
0x140008b44  push    r14
0x140008b46  mov     rbp, rsp
0x140008b49  sub     rsp, 50h
0x140008b4d  mov     r14, r8
0x140008b50  mov     rdi, rdx
0x140008b53  mov     rsi, rcx
0x140008b56  mov     [rbp+hKey], 0
0x140008b5e  lea     rbx, [rcx+8]
0x140008b62  cmp     qword ptr [rbx+18h], 8
0x140008b67  jb      short loc_140008B6E
0x140008b69  mov     rdx, [rbx]
0x140008b6c  jmp     short loc_140008B71
0x140008b6e  mov     rdx, rbx; lpSubKey
0x140008b71  lea     rax, [rbp+hKey]
0x140008b75  mov     [rsp+50h+phkResult], rax; phkResult
0x140008b7a  mov     r9d, 20019h; samDesired
0x140008b80  xor     r8d, r8d; ulOptions
0x140008b83  mov     rcx, [rcx]; hKey
0x140008b86  call    cs:__imp_RegOpenKeyExW
0x140008b8c  test    eax, eax
0x140008b8e  jnz     loc_140008C34
0x140008b94  mov     [rbp+arg_0], 0
0x140008b9c  lea     rax, [rbp+arg_0]
0x140008ba0  mov     [rsp+50h+phkResult], rax; phkResult
0x140008ba5  mov     r9d, 20019h; samDesired
0x140008bab  xor     r8d, r8d; ulOptions
0x140008bae  mov     rdx, r14; lpSubKey
0x140008bb1  mov     rcx, [rbp+hKey]; hKey
0x140008bb5  call    cs:__imp_RegOpenKeyExW
0x140008bbb  test    eax, eax
0x140008bbd  jnz     short loc_140008BE7
0x140008bbf  mov     r8, [rbp+arg_0]
0x140008bc3  mov     rdx, rdi
0x140008bc6  mov     rcx, rsi
0x140008bc9  call    ?ParsePhase@RegistryConfig@@AEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEAUHKEY__@@@Z; RegistryConfig::ParsePhase(HKEY__ *)
0x140008bce  nop
0x140008bcf  mov     rcx, [rbp+arg_0]; hKey
0x140008bd3  test    rcx, rcx
0x140008bd6  jz      loc_140008CB5
0x140008bdc  call    cs:__imp_RegCloseKey
0x140008be2  jmp     loc_140008CB5
0x140008be7  mov     eax, cs:dword_140010000
0x140008bed  cmp     eax, 2
0x140008bf0  jbe     short loc_140008C23
0x140008bf2  mov     [rbp+var_18], r14
0x140008bf6  cmp     qword ptr [rbx+18h], 8
0x140008bfb  jb      short loc_140008C00
0x140008bfd  mov     rbx, [rbx]
0x140008c00  mov     [rbp+var_10], rbx
0x140008c04  lea     rax, [rbp+var_18]
0x140008c08  mov     [rsp+50h+var_28], rax
0x140008c0d  lea     rax, [rbp+var_10]
0x140008c11  mov     [rsp+50h+phkResult], rax
0x140008c16  lea     rdx, unk_14000D648
0x140008c1d  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140008c22  nop
0x140008c23  mov     rcx, [rbp+arg_0]; hKey
0x140008c27  test    rcx, rcx
0x140008c2a  jz      short loc_140008C62
0x140008c2c  call    cs:__imp_RegCloseKey
0x140008c32  jmp     short loc_140008C62
0x140008c34  mov     eax, cs:dword_140010000
0x140008c3a  cmp     eax, 2
0x140008c3d  jbe     short loc_140008C62
0x140008c3f  cmp     qword ptr [rbx+18h], 8
0x140008c44  jb      short loc_140008C49
0x140008c46  mov     rbx, [rbx]
0x140008c49  mov     [rbp+arg_0], rbx
0x140008c4d  lea     rax, [rbp+arg_0]
0x140008c51  mov     [rsp+50h+phkResult], rax
0x140008c56  lea     rdx, byte_14000D58B
0x140008c5d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x140008c62  mov     [rbp+var_8], 0
0x140008c6a  xor     r8d, r8d
0x140008c6d  xor     edx, edx
0x140008c6f  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x140008c74  mov     rbx, rax
0x140008c77  mov     [rbp+var_10], rax
0x140008c7b  mov     qword ptr [rdi], 0
0x140008c82  mov     qword ptr [rdi+8], 0
0x140008c8a  xor     r8d, r8d
0x140008c8d  xor     edx, edx
0x140008c8f  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x140008c94  mov     [rdi], rbx
0x140008c97  mov     [rbp+var_10], rax
0x140008c9b  mov     rax, [rdi+8]
0x140008c9f  mov     qword ptr [rdi+8], 0
0x140008ca7  mov     [rbp+var_8], rax
0x140008cab  lea     rcx, [rbp+var_10]; void *
0x140008caf  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x140008cb4  nop
0x140008cb5  mov     rcx, [rbp+hKey]; hKey
0x140008cb9  test    rcx, rcx
0x140008cbc  jz      short loc_140008CC4
0x140008cbe  call    cs:__imp_RegCloseKey
0x140008cc4  mov     rax, rdi
0x140008cc7  lea     r11, [rsp+50h+var_s0]
0x140008ccc  mov     rbx, [r11+28h]
0x140008cd0  mov     rsi, [r11+30h]
0x140008cd4  mov     rsp, r11
0x140008cd7  pop     r14
0x140008cd9  pop     rdi
0x140008cda  pop     rbp
0x140008cdb  retn
```
