# RegistryConfig::Parse(ushort const *)

- ea: `0x18000b81c`
- end: `0x18000ba5a`
- name: `?Parse@RegistryConfig@@QEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEBG@Z`
- size: `574`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800076ac`
- `0x1800096c0`

## callees

- `0x180001090`
- `0x18000134c`
- `0x180006d20`
- `0x18000b81c`
- `0x18000be6c`
- `0x18000c0d0`
- `0x18000ccc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b99b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ba27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b99b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ba27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b87e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b8af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b87e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b8af`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HKEY *__fastcall RegistryConfig::Parse(__int64 a1, HKEY *a2, const WCHAR *a3)
{
  HKEY v6; // rbx
  const WCHAR *v7; // rdx
  int v8; // r8d
  int v9; // r9d
  int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // edx
  __int64 v14; // rcx
  HKEY v15; // rbx
  __int64 v16; // rcx
  HKEY v17; // rax
  HKEY v18; // rcx
  HKEY phkResult; // [rsp+30h] [rbp-39h] BYREF
  HKEY v21; // [rsp+38h] [rbp-31h]
  HKEY hKey; // [rsp+40h] [rbp-29h] BYREF
  char v23[32]; // [rsp+50h] [rbp-19h] BYREF
  HKEY v24; // [rsp+70h] [rbp+7h]
  int v25; // [rsp+78h] [rbp+Fh]
  int v26; // [rsp+7Ch] [rbp+13h]
  const WCHAR *v27; // [rsp+80h] [rbp+17h]
  int v28; // [rsp+88h] [rbp+1Fh]
  int v29; // [rsp+8Ch] [rbp+23h]

  hKey = 0;
  v6 = (HKEY)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) < 8u )
    v7 = (const WCHAR *)(a1 + 8);
  else
    v7 = *(const WCHAR **)v6;
  if ( RegOpenKeyExW(*(HKEY *)a1, v7, 0, 0x20019u, &hKey) )
  {
    v14 = 2;
    if ( (unsigned int)dword_180014230 > 2 )
    {
      if ( *((_QWORD *)v6 + 3) >= 8u )
        v6 = *(HKEY *)v6;
      phkResult = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        2,
        (unsigned int)&byte_180010AFF,
        v8,
        v9,
        (__int64)&phkResult);
    }
    goto LABEL_27;
  }
  phkResult = 0;
  if ( RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult) )
  {
    v10 = 2;
    if ( (unsigned int)dword_180014230 > 2 )
    {
      if ( *((_QWORD *)v6 + 3) >= 8u )
        v6 = *(HKEY *)v6;
      v11 = -1;
      if ( a3 )
      {
        v12 = -1;
        do
          ++v12;
        while ( a3[v12] );
        v13 = 2 * v12 + 2;
      }
      else
      {
        a3 = (const WCHAR *)&qword_180010000;
        v13 = 2;
      }
      v27 = a3;
      v28 = v13;
      v29 = 0;
      if ( v6 )
      {
        do
          ++v11;
        while ( *((_WORD *)v6 + v11) );
        v10 = 2 * v11 + 2;
      }
      else
      {
        v6 = (HKEY)&qword_180010000;
      }
      v24 = v6;
      v25 = v10;
      v26 = 0;
      tlgWriteTransfer_EventWriteTransfer(&dword_180014230, &dword_180010BBC, 0, 0, 4, v23, (_DWORD)phkResult);
    }
    v14 = (__int64)phkResult;
    if ( phkResult )
      RegCloseKey(phkResult);
LABEL_27:
    v21 = 0;
    v15 = (HKEY)std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(v14, 0, 0);
    phkResult = v15;
    *a2 = 0;
    a2[1] = 0;
    v17 = (HKEY)std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(v16, 0, 0);
    *a2 = v15;
    phkResult = v17;
    v18 = a2[1];
    a2[1] = 0;
    v21 = v18;
    std::list<CommandSet>::~list<CommandSet>(&phkResult);
    goto LABEL_28;
  }
  RegistryConfig::ParsePhase(a1, a2, phkResult);
  if ( phkResult )
    RegCloseKey(phkResult);
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  return a2;
}

```

## disassembly

```asm
0x18000b81c  mov     [rsp-8+arg_18], rbx
0x18000b821  push    rbp
0x18000b822  push    rsi
0x18000b823  push    rdi
0x18000b824  push    r14
0x18000b826  push    r15
0x18000b828  lea     rbp, [rsp-37h]
0x18000b82d  sub     rsp, 0A0h
0x18000b834  mov     rax, cs:__security_cookie
0x18000b83b  xor     rax, rsp
0x18000b83e  mov     [rbp+57h+var_30], rax
0x18000b842  mov     rsi, r8
0x18000b845  mov     rdi, rdx
0x18000b848  mov     r14, rcx
0x18000b84b  mov     [rbp+57h+hKey], rdx
0x18000b84f  xor     r15d, r15d
0x18000b852  mov     [rbp+57h+hKey], r15
0x18000b856  lea     rbx, [rcx+8]
0x18000b85a  cmp     qword ptr [rbx+18h], 8
0x18000b85f  jb      short loc_18000B866
0x18000b861  mov     rdx, [rbx]
0x18000b864  jmp     short loc_18000B869
0x18000b866  mov     rdx, rbx; lpSubKey
0x18000b869  lea     rax, [rbp+57h+hKey]
0x18000b86d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000b872  mov     r9d, 20019h; samDesired
0x18000b878  xor     r8d, r8d; ulOptions
0x18000b87b  mov     rcx, [rcx]; hKey
0x18000b87e  call    cs:__imp_RegOpenKeyExW
0x18000b885  nop     dword ptr [rax+rax+00h]
0x18000b88a  test    eax, eax
0x18000b88c  jnz     loc_18000B9A9
0x18000b892  mov     [rbp+57h+var_90], r15
0x18000b896  lea     rax, [rbp+57h+var_90]
0x18000b89a  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000b89f  mov     r9d, 20019h; samDesired
0x18000b8a5  xor     r8d, r8d; ulOptions
0x18000b8a8  mov     rdx, rsi; lpSubKey
0x18000b8ab  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b8af  call    cs:__imp_RegOpenKeyExW
0x18000b8b6  nop     dword ptr [rax+rax+00h]
0x18000b8bb  test    eax, eax
0x18000b8bd  jnz     short loc_18000B8ED
0x18000b8bf  mov     r8, [rbp+57h+var_90]
0x18000b8c3  mov     rdx, rdi
0x18000b8c6  mov     rcx, r14
0x18000b8c9  call    ?ParsePhase@RegistryConfig@@AEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEAUHKEY__@@@Z; RegistryConfig::ParsePhase(HKEY__ *)
0x18000b8ce  nop
0x18000b8cf  mov     rcx, [rbp+57h+var_90]; hKey
0x18000b8d3  test    rcx, rcx
0x18000b8d6  jz      loc_18000BA1E
0x18000b8dc  call    cs:__imp_RegCloseKey
0x18000b8e3  nop     dword ptr [rax+rax+00h]
0x18000b8e8  jmp     loc_18000BA1E
0x18000b8ed  mov     eax, cs:dword_180014230
0x18000b8f3  mov     ecx, 2
0x18000b8f8  cmp     eax, ecx
0x18000b8fa  jbe     loc_18000B992
0x18000b900  cmp     qword ptr [rbx+18h], 8
0x18000b905  jb      short loc_18000B90A
0x18000b907  mov     rbx, [rbx]
0x18000b90a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b90e  test    rsi, rsi
0x18000b911  jz      short loc_18000B929
0x18000b913  mov     rdx, rax
0x18000b916  inc     rdx
0x18000b919  cmp     [rsi+rdx*2], r15w
0x18000b91e  jnz     short loc_18000B916
0x18000b920  lea     edx, ds:2[rdx*2]
0x18000b927  jmp     short loc_18000B932
0x18000b929  lea     rsi, qword_180010000
0x18000b930  mov     edx, ecx
0x18000b932  mov     [rbp+57h+var_40], rsi
0x18000b936  mov     [rbp+57h+var_38], edx
0x18000b939  mov     [rbp+57h+var_34], r15d
0x18000b93d  test    rbx, rbx
0x18000b940  jz      short loc_18000B955
0x18000b942  inc     rax
0x18000b945  cmp     [rbx+rax*2], r15w
0x18000b94a  jnz     short loc_18000B942
0x18000b94c  lea     ecx, ds:2[rax*2]
0x18000b953  jmp     short loc_18000B95C
0x18000b955  lea     rbx, qword_180010000
0x18000b95c  mov     [rbp+57h+var_50], rbx
0x18000b960  mov     [rbp+57h+var_48], ecx
0x18000b963  mov     [rbp+57h+var_44], r15d
0x18000b967  lea     rax, [rbp+57h+var_70]
0x18000b96b  mov     [rsp+0C0h+var_98], rax
0x18000b970  mov     dword ptr [rsp+0C0h+phkResult], 4
0x18000b978  xor     r9d, r9d
0x18000b97b  xor     r8d, r8d
0x18000b97e  lea     rdx, dword_180010BBC
0x18000b985  lea     rcx, dword_180014230
0x18000b98c  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b991  nop
0x18000b992  mov     rcx, [rbp+57h+var_90]; hKey
0x18000b996  test    rcx, rcx
0x18000b999  jz      short loc_18000B9DB
0x18000b99b  call    cs:__imp_RegCloseKey
0x18000b9a2  nop     dword ptr [rax+rax+00h]
0x18000b9a7  jmp     short loc_18000B9DB
0x18000b9a9  mov     eax, cs:dword_180014230
0x18000b9af  mov     ecx, 2
0x18000b9b4  cmp     eax, ecx
0x18000b9b6  jbe     short loc_18000B9DB
0x18000b9b8  cmp     qword ptr [rbx+18h], 8
0x18000b9bd  jb      short loc_18000B9C2
0x18000b9bf  mov     rbx, [rbx]
0x18000b9c2  mov     [rbp+57h+var_90], rbx
0x18000b9c6  lea     rax, [rbp+57h+var_90]
0x18000b9ca  mov     [rsp+0C0h+phkResult], rax
0x18000b9cf  lea     rdx, byte_180010AFF
0x18000b9d6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000b9db  mov     [rbp+57h+var_88], r15
0x18000b9df  xor     r8d, r8d
0x18000b9e2  xor     edx, edx
0x18000b9e4  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000b9e9  mov     rbx, rax
0x18000b9ec  mov     [rbp+57h+var_90], rax
0x18000b9f0  mov     [rdi], r15
0x18000b9f3  mov     [rdi+8], r15
0x18000b9f7  xor     r8d, r8d
0x18000b9fa  xor     edx, edx
0x18000b9fc  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000ba01  mov     [rdi], rbx
0x18000ba04  mov     [rbp+57h+var_90], rax
0x18000ba08  mov     rcx, [rdi+8]
0x18000ba0c  mov     [rdi+8], r15
0x18000ba10  mov     [rbp+57h+var_88], rcx
0x18000ba14  lea     rcx, [rbp+57h+var_90]; void *
0x18000ba18  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x18000ba1d  nop
0x18000ba1e  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ba22  test    rcx, rcx
0x18000ba25  jz      short loc_18000BA33
0x18000ba27  call    cs:__imp_RegCloseKey
0x18000ba2e  nop     dword ptr [rax+rax+00h]
0x18000ba33  mov     rax, rdi
0x18000ba36  mov     rcx, [rbp+57h+var_30]
0x18000ba3a  xor     rcx, rsp; StackCookie
0x18000ba3d  call    __security_check_cookie
0x18000ba42  mov     rbx, [rsp+0C0h+arg_18]
0x18000ba4a  add     rsp, 0A0h
0x18000ba51  pop     r15
0x18000ba53  pop     r14
0x18000ba55  pop     rdi
0x18000ba56  pop     rsi
0x18000ba57  pop     rbp
0x18000ba58  retn
```
