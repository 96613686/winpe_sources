# RegistryConfig::Parse(ushort const *)

- ea: `0x18000b1c8`
- end: `0x18000b3e7`
- name: `?Parse@RegistryConfig@@QEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEBG@Z`
- size: `543`
- prototype: `HKEY *__fastcall(__int64, HKEY *, const WCHAR *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007360`
- `0x180009290`

## callees

- `0x18000108c`
- `0x180001340`
- `0x180006a00`
- `0x18000b1c8`
- `0x18000b7dc`
- `0x18000ba18`
- `0x18000c600`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b27c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b335`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b27c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b335`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b22a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b255`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b22a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b255`

## pseudocode

```c
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
  HKEY hKey[7]; // [rsp+40h] [rbp-29h] BYREF
  int v23; // [rsp+78h] [rbp+Fh]
  int v24; // [rsp+7Ch] [rbp+13h]
  const WCHAR *v25; // [rsp+80h] [rbp+17h]
  int v26; // [rsp+88h] [rbp+1Fh]
  int v27; // [rsp+8Ch] [rbp+23h]

  hKey[0] = 0;
  v6 = (HKEY)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) < 8u )
    v7 = (const WCHAR *)(a1 + 8);
  else
    v7 = *(const WCHAR **)v6;
  if ( RegOpenKeyExW(*(HKEY *)a1, v7, 0, 0x20019u, hKey) )
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
  if ( RegOpenKeyExW(hKey[0], a3, 0, 0x20019u, &phkResult) )
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
      v25 = a3;
      v26 = v13;
      v27 = 0;
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
      hKey[6] = v6;
      v23 = v10;
      v24 = 0;
      tlgWriteTransfer_EventWriteTransfer(&dword_180014230, &dword_180010BBC, 0, 0);
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
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return a2;
}

```

## disassembly

```asm
0x18000b1c8  mov     [rsp-8+arg_18], rbx
0x18000b1cd  push    rbp
0x18000b1ce  push    rsi
0x18000b1cf  push    rdi
0x18000b1d0  push    r14
0x18000b1d2  push    r15
0x18000b1d4  lea     rbp, [rsp-37h]
0x18000b1d9  sub     rsp, 0A0h
0x18000b1e0  mov     rax, cs:__security_cookie
0x18000b1e7  xor     rax, rsp
0x18000b1ea  mov     [rbp+57h+var_30], rax
0x18000b1ee  mov     rsi, r8
0x18000b1f1  mov     rdi, rdx
0x18000b1f4  mov     r14, rcx
0x18000b1f7  mov     [rbp+57h+hKey], rdx
0x18000b1fb  xor     r15d, r15d
0x18000b1fe  mov     [rbp+57h+hKey], r15
0x18000b202  lea     rbx, [rcx+8]
0x18000b206  cmp     qword ptr [rbx+18h], 8
0x18000b20b  jb      short loc_18000B212
0x18000b20d  mov     rdx, [rbx]
0x18000b210  jmp     short loc_18000B215
0x18000b212  mov     rdx, rbx; lpSubKey
0x18000b215  lea     rax, [rbp+57h+hKey]
0x18000b219  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000b21e  mov     r9d, 20019h; samDesired
0x18000b224  xor     r8d, r8d; ulOptions
0x18000b227  mov     rcx, [rcx]; hKey
0x18000b22a  call    cs:__imp_RegOpenKeyExW
0x18000b230  test    eax, eax
0x18000b232  jnz     loc_18000B33D
0x18000b238  mov     [rbp+57h+var_90], r15
0x18000b23c  lea     rax, [rbp+57h+var_90]
0x18000b240  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000b245  mov     r9d, 20019h; samDesired
0x18000b24b  xor     r8d, r8d; ulOptions
0x18000b24e  mov     rdx, rsi; lpSubKey
0x18000b251  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b255  call    cs:__imp_RegOpenKeyExW
0x18000b25b  test    eax, eax
0x18000b25d  jnz     short loc_18000B287
0x18000b25f  mov     r8, [rbp+57h+var_90]
0x18000b263  mov     rdx, rdi
0x18000b266  mov     rcx, r14
0x18000b269  call    ?ParsePhase@RegistryConfig@@AEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEAUHKEY__@@@Z; RegistryConfig::ParsePhase(HKEY__ *)
0x18000b26e  nop
0x18000b26f  mov     rcx, [rbp+57h+var_90]; hKey
0x18000b273  test    rcx, rcx
0x18000b276  jz      loc_18000B3B2
0x18000b27c  call    cs:__imp_RegCloseKey
0x18000b282  jmp     loc_18000B3B2
0x18000b287  mov     eax, cs:dword_180014230
0x18000b28d  mov     ecx, 2
0x18000b292  cmp     eax, ecx
0x18000b294  jbe     loc_18000B32C
0x18000b29a  cmp     qword ptr [rbx+18h], 8
0x18000b29f  jb      short loc_18000B2A4
0x18000b2a1  mov     rbx, [rbx]
0x18000b2a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b2a8  test    rsi, rsi
0x18000b2ab  jz      short loc_18000B2C3
0x18000b2ad  mov     rdx, rax
0x18000b2b0  inc     rdx
0x18000b2b3  cmp     [rsi+rdx*2], r15w
0x18000b2b8  jnz     short loc_18000B2B0
0x18000b2ba  lea     edx, ds:2[rdx*2]
0x18000b2c1  jmp     short loc_18000B2CC
0x18000b2c3  lea     rsi, qword_180010000
0x18000b2ca  mov     edx, ecx
0x18000b2cc  mov     [rbp+57h+var_40], rsi
0x18000b2d0  mov     [rbp+57h+var_38], edx
0x18000b2d3  mov     [rbp+57h+var_34], r15d
0x18000b2d7  test    rbx, rbx
0x18000b2da  jz      short loc_18000B2EF
0x18000b2dc  inc     rax
0x18000b2df  cmp     [rbx+rax*2], r15w
0x18000b2e4  jnz     short loc_18000B2DC
0x18000b2e6  lea     ecx, ds:2[rax*2]
0x18000b2ed  jmp     short loc_18000B2F6
0x18000b2ef  lea     rbx, qword_180010000
0x18000b2f6  mov     [rbp+57h+var_50], rbx
0x18000b2fa  mov     [rbp+57h+var_48], ecx
0x18000b2fd  mov     [rbp+57h+var_44], r15d
0x18000b301  lea     rax, [rbp+57h+var_70]
0x18000b305  mov     [rsp+0C0h+var_98], rax
0x18000b30a  mov     dword ptr [rsp+0C0h+phkResult], 4
0x18000b312  xor     r9d, r9d
0x18000b315  xor     r8d, r8d
0x18000b318  lea     rdx, dword_180010BBC
0x18000b31f  lea     rcx, dword_180014230
0x18000b326  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b32b  nop
0x18000b32c  mov     rcx, [rbp+57h+var_90]; hKey
0x18000b330  test    rcx, rcx
0x18000b333  jz      short loc_18000B36F
0x18000b335  call    cs:__imp_RegCloseKey
0x18000b33b  jmp     short loc_18000B36F
0x18000b33d  mov     eax, cs:dword_180014230
0x18000b343  mov     ecx, 2
0x18000b348  cmp     eax, ecx
0x18000b34a  jbe     short loc_18000B36F
0x18000b34c  cmp     qword ptr [rbx+18h], 8
0x18000b351  jb      short loc_18000B356
0x18000b353  mov     rbx, [rbx]
0x18000b356  mov     [rbp+57h+var_90], rbx
0x18000b35a  lea     rax, [rbp+57h+var_90]
0x18000b35e  mov     [rsp+0C0h+phkResult], rax
0x18000b363  lea     rdx, byte_180010AFF
0x18000b36a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000b36f  mov     [rbp+57h+var_88], r15
0x18000b373  xor     r8d, r8d
0x18000b376  xor     edx, edx
0x18000b378  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000b37d  mov     rbx, rax
0x18000b380  mov     [rbp+57h+var_90], rax
0x18000b384  mov     [rdi], r15
0x18000b387  mov     [rdi+8], r15
0x18000b38b  xor     r8d, r8d
0x18000b38e  xor     edx, edx
0x18000b390  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000b395  mov     [rdi], rbx
0x18000b398  mov     [rbp+57h+var_90], rax
0x18000b39c  mov     rcx, [rdi+8]
0x18000b3a0  mov     [rdi+8], r15
0x18000b3a4  mov     [rbp+57h+var_88], rcx
0x18000b3a8  lea     rcx, [rbp+57h+var_90]; void *
0x18000b3ac  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x18000b3b1  nop
0x18000b3b2  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b3b6  test    rcx, rcx
0x18000b3b9  jz      short loc_18000B3C1
0x18000b3bb  call    cs:__imp_RegCloseKey
0x18000b3c1  mov     rax, rdi
0x18000b3c4  mov     rcx, [rbp+57h+var_30]
0x18000b3c8  xor     rcx, rsp; StackCookie
0x18000b3cb  call    __security_check_cookie
0x18000b3d0  mov     rbx, [rsp+0C0h+arg_18]
0x18000b3d8  add     rsp, 0A0h
0x18000b3df  pop     r15
0x18000b3e1  pop     r14
0x18000b3e3  pop     rdi
0x18000b3e4  pop     rsi
0x18000b3e5  pop     rbp
0x18000b3e6  retn
```
