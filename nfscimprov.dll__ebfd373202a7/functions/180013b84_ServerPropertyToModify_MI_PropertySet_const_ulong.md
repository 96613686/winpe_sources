# ServerPropertyToModify(_MI_PropertySet const *,ulong *)

- ea: `0x180013b84`
- end: `0x18001415f`
- name: `?ServerPropertyToModify@@YA?AW4_MI_Result@@PEBU_MI_PropertySet@@PEAK@Z`
- size: `1499`
- prototype: `enum _MI_Result __fastcall(const struct _MI_PropertySet *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180012690`

## callees

- `0x180009704`
- `0x180009744`
- `0x1800097d0`
- `0x18000994c`
- `0x18000eae4`
- `0x180013b84`
- `0x180035b40`
- `0x180037010`

## string_xrefs

- `0x180013c22`: `DirectoryCacheSize`
- `0x180013ede`: `MapsvrProtocol`
- `0x180013e16`: `MountProtocol`
- `0x180013e48`: `NfsProtocol`
- `0x180013f10`: `NisProtocol`
- `0x180013e7a`: `NlmProtocol`
- `0x180013eac`: `NsmProtocol`
- `0x180013de4`: `PortmapProtocol`
- `0x180013f74`: `NetgroupCacheTimeout`
- `0x18001400a`: `AlwaysOpenByName`
- `0x1800140a0`: `ClearMappingCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServerPropertyToModify(const struct _MI_PropertySet *a1, unsigned int *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 *v31; // rbx
  _QWORD *v32; // rdx
  unsigned int v33; // eax
  _BYTE v35[16]; // [rsp+20h] [rbp-39h] BYREF
  _QWORD v36[8]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v37[32]; // [rsp+70h] [rbp+17h] BYREF

  stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>(v36);
  v4 = 0;
  std::wstring::wstring(v37, L"LogActivity");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 2;
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(v37, v5, 0);
  std::wstring::wstring(v37, L"CharacterTranslationFile");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 8;
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v37, v6, 0);
  std::wstring::wstring(v37, L"DirectoryCacheSize");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 16;
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(v37, v7, 0);
  std::wstring::wstring(v37, L"EnableAuthRenewal");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 32;
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(v37, v8, 0);
  std::wstring::wstring(v37, L"AuthRenewalInterval");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 64;
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v37, v9, 0);
  std::wstring::wstring(v37, L"EnableNFSV2");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 128;
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v37, v10, 0);
  std::wstring::wstring(v37, L"EnableNFSV3");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 256;
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v37, v11, 0);
  std::wstring::wstring(v37, L"EnableNFSV4");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 512;
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(v37, v12, 0);
  std::wstring::wstring(v37, L"HideFilesBeginningInDot");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 1024;
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(v37, v13, 0);
  std::wstring::wstring(v37, L"NlmGracePeriod");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 4096;
  LOBYTE(v14) = 1;
  std::wstring::_Tidy(v37, v14, 0);
  std::wstring::wstring(v37, L"GracePeriod");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x10000000;
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(v37, v15, 0);
  std::wstring::wstring(v37, L"PortmapProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x2000;
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(v37, v16, 0);
  std::wstring::wstring(v37, L"MountProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x4000;
  LOBYTE(v17) = 1;
  std::wstring::_Tidy(v37, v17, 0);
  std::wstring::wstring(v37, L"NfsProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x8000;
  LOBYTE(v18) = 1;
  std::wstring::_Tidy(v37, v18, 0);
  std::wstring::wstring(v37, L"NlmProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x10000;
  LOBYTE(v19) = 1;
  std::wstring::_Tidy(v37, v19, 0);
  std::wstring::wstring(v37, L"NsmProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x20000;
  LOBYTE(v20) = 1;
  std::wstring::_Tidy(v37, v20, 0);
  std::wstring::wstring(v37, L"MapsvrProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x40000;
  LOBYTE(v21) = 1;
  std::wstring::_Tidy(v37, v21, 0);
  std::wstring::wstring(v37, L"NisProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x80000;
  LOBYTE(v22) = 1;
  std::wstring::_Tidy(v37, v22, 0);
  std::wstring::wstring(v37, L"PreserveInheritance");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x100000;
  LOBYTE(v23) = 1;
  std::wstring::_Tidy(v37, v23, 0);
  std::wstring::wstring(v37, L"NetgroupCacheTimeout");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x200000;
  LOBYTE(v24) = 1;
  std::wstring::_Tidy(v37, v24, 0);
  std::wstring::wstring(v37, L"UnmappedUserAccount");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x400000;
  LOBYTE(v25) = 1;
  std::wstring::_Tidy(v37, v25, 0);
  std::wstring::wstring(v37, L"WorldAccount");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x800000;
  LOBYTE(v26) = 1;
  std::wstring::_Tidy(v37, v26, 0);
  std::wstring::wstring(v37, L"AlwaysOpenByName");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x1000000;
  LOBYTE(v27) = 1;
  std::wstring::_Tidy(v37, v27, 0);
  std::wstring::wstring(v37, L"LeasePeriod");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x2000000;
  LOBYTE(v28) = 1;
  std::wstring::_Tidy(v37, v28, 0);
  std::wstring::wstring(v37, L"OnlineTimeoutInSeconds");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x8000000;
  LOBYTE(v29) = 1;
  std::wstring::_Tidy(v37, v29, 0);
  std::wstring::wstring(v37, L"ClearMappingCache");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v36,
               v37) = 0x4000000;
  LOBYTE(v30) = 1;
  std::wstring::_Tidy(v37, v30, 0);
  v31 = (__int64 *)v36[0];
LABEL_2:
  v31 = (__int64 *)*v31;
  while ( v31 != (__int64 *)v36[0] )
  {
    v35[0] = 0;
    v32 = v31 + 2;
    if ( (unsigned __int64)v31[5] >= 8 )
      v32 = (_QWORD *)*v32;
    if ( !a1 || !a1->ft )
    {
      v4 = 4;
      break;
    }
    v33 = ((__int64 (__fastcall *)(const struct _MI_PropertySet *, _QWORD *, _BYTE *))a1->ft->ContainsElement)(
            a1,
            v32,
            v35);
    v4 = v33;
    if ( !v33 && v35[0] == 1 )
    {
      *a2 |= *((_DWORD *)v31 + 12);
      goto LABEL_2;
    }
    v31 = (__int64 *)*v31;
    if ( v33 )
      break;
  }
  std::_Hash<stdext::_Hmap_traits<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v36);
  return v4;
}

```

## disassembly

```asm
0x180013b84  mov     [rsp-8+arg_10], rbx
0x180013b89  mov     [rsp-8+arg_18], rsi
0x180013b8e  push    rbp
0x180013b8f  push    rdi
0x180013b90  push    r14
0x180013b92  lea     rbp, [rsp-47h]
0x180013b97  sub     rsp, 0A0h
0x180013b9e  mov     rax, cs:__security_cookie
0x180013ba5  xor     rax, rsp
0x180013ba8  mov     [rbp+57h+var_20], rax
0x180013bac  mov     r14, rdx
0x180013baf  mov     rsi, rcx
0x180013bb2  lea     rcx, [rbp+57h+var_80]
0x180013bb6  call    ??0?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAA@XZ; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>(void)
0x180013bbb  nop
0x180013bbc  xor     edi, edi
0x180013bbe  lea     rdx, aLogactivity; "LogActivity"
0x180013bc5  lea     rcx, [rbp+57h+var_40]
0x180013bc9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013bce  nop
0x180013bcf  lea     rdx, [rbp+57h+var_40]
0x180013bd3  lea     rcx, [rbp+57h+var_80]
0x180013bd7  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013bdc  mov     dword ptr [rax], 2
0x180013be2  xor     r8d, r8d
0x180013be5  mov     dl, 1
0x180013be7  lea     rcx, [rbp+57h+var_40]
0x180013beb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013bf0  lea     rdx, aCharactertrans; "CharacterTranslationFile"
0x180013bf7  lea     rcx, [rbp+57h+var_40]
0x180013bfb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013c00  nop
0x180013c01  lea     rdx, [rbp+57h+var_40]
0x180013c05  lea     rcx, [rbp+57h+var_80]
0x180013c09  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013c0e  mov     dword ptr [rax], 8
0x180013c14  xor     r8d, r8d
0x180013c17  mov     dl, 1
0x180013c19  lea     rcx, [rbp+57h+var_40]
0x180013c1d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013c22  lea     rdx, aDirectorycache; "DirectoryCacheSize"
0x180013c29  lea     rcx, [rbp+57h+var_40]
0x180013c2d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013c32  nop
0x180013c33  lea     rdx, [rbp+57h+var_40]
0x180013c37  lea     rcx, [rbp+57h+var_80]
0x180013c3b  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013c40  mov     dword ptr [rax], 10h
0x180013c46  xor     r8d, r8d
0x180013c49  mov     dl, 1
0x180013c4b  lea     rcx, [rbp+57h+var_40]
0x180013c4f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013c54  lea     rdx, aEnableauthrene; "EnableAuthRenewal"
0x180013c5b  lea     rcx, [rbp+57h+var_40]
0x180013c5f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013c64  nop
0x180013c65  lea     rdx, [rbp+57h+var_40]
0x180013c69  lea     rcx, [rbp+57h+var_80]
0x180013c6d  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013c72  mov     dword ptr [rax], 20h ; ' '
0x180013c78  xor     r8d, r8d
0x180013c7b  mov     dl, 1
0x180013c7d  lea     rcx, [rbp+57h+var_40]
0x180013c81  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013c86  lea     rdx, aAuthrenewalint; "AuthRenewalInterval"
0x180013c8d  lea     rcx, [rbp+57h+var_40]
0x180013c91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013c96  nop
0x180013c97  lea     rdx, [rbp+57h+var_40]
0x180013c9b  lea     rcx, [rbp+57h+var_80]
0x180013c9f  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013ca4  mov     dword ptr [rax], 40h ; '@'
0x180013caa  xor     r8d, r8d
0x180013cad  mov     dl, 1
0x180013caf  lea     rcx, [rbp+57h+var_40]
0x180013cb3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013cb8  lea     rdx, aEnablenfsv2; "EnableNFSV2"
0x180013cbf  lea     rcx, [rbp+57h+var_40]
0x180013cc3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013cc8  nop
0x180013cc9  lea     rdx, [rbp+57h+var_40]
0x180013ccd  lea     rcx, [rbp+57h+var_80]
0x180013cd1  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013cd6  mov     dword ptr [rax], 80h
0x180013cdc  xor     r8d, r8d
0x180013cdf  mov     dl, 1
0x180013ce1  lea     rcx, [rbp+57h+var_40]
0x180013ce5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013cea  lea     rdx, aEnablenfsv3; "EnableNFSV3"
0x180013cf1  lea     rcx, [rbp+57h+var_40]
0x180013cf5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013cfa  nop
0x180013cfb  lea     rdx, [rbp+57h+var_40]
0x180013cff  lea     rcx, [rbp+57h+var_80]
0x180013d03  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013d08  mov     dword ptr [rax], 100h
0x180013d0e  xor     r8d, r8d
0x180013d11  mov     dl, 1
0x180013d13  lea     rcx, [rbp+57h+var_40]
0x180013d17  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013d1c  lea     rdx, aEnablenfsv4; "EnableNFSV4"
0x180013d23  lea     rcx, [rbp+57h+var_40]
0x180013d27  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013d2c  nop
0x180013d2d  lea     rdx, [rbp+57h+var_40]
0x180013d31  lea     rcx, [rbp+57h+var_80]
0x180013d35  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013d3a  mov     dword ptr [rax], 200h
0x180013d40  xor     r8d, r8d
0x180013d43  mov     dl, 1
0x180013d45  lea     rcx, [rbp+57h+var_40]
0x180013d49  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013d4e  lea     rdx, aHidefilesbegin; "HideFilesBeginningInDot"
0x180013d55  lea     rcx, [rbp+57h+var_40]
0x180013d59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013d5e  nop
0x180013d5f  lea     rdx, [rbp+57h+var_40]
0x180013d63  lea     rcx, [rbp+57h+var_80]
0x180013d67  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013d6c  mov     dword ptr [rax], 400h
0x180013d72  xor     r8d, r8d
0x180013d75  mov     dl, 1
0x180013d77  lea     rcx, [rbp+57h+var_40]
0x180013d7b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013d80  lea     rdx, aNlmgraceperiod; "NlmGracePeriod"
0x180013d87  lea     rcx, [rbp+57h+var_40]
0x180013d8b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013d90  nop
0x180013d91  lea     rdx, [rbp+57h+var_40]
0x180013d95  lea     rcx, [rbp+57h+var_80]
0x180013d99  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013d9e  mov     dword ptr [rax], 1000h
0x180013da4  xor     r8d, r8d
0x180013da7  mov     dl, 1
0x180013da9  lea     rcx, [rbp+57h+var_40]
0x180013dad  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013db2  lea     rdx, aGraceperiod; "GracePeriod"
0x180013db9  lea     rcx, [rbp+57h+var_40]
0x180013dbd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013dc2  nop
0x180013dc3  lea     rdx, [rbp+57h+var_40]
0x180013dc7  lea     rcx, [rbp+57h+var_80]
0x180013dcb  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013dd0  mov     dword ptr [rax], 10000000h
0x180013dd6  xor     r8d, r8d
0x180013dd9  mov     dl, 1
0x180013ddb  lea     rcx, [rbp+57h+var_40]
0x180013ddf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013de4  lea     rdx, aPortmapprotoco; "PortmapProtocol"
0x180013deb  lea     rcx, [rbp+57h+var_40]
0x180013def  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013df4  nop
0x180013df5  lea     rdx, [rbp+57h+var_40]
0x180013df9  lea     rcx, [rbp+57h+var_80]
0x180013dfd  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013e02  mov     dword ptr [rax], 2000h
0x180013e08  xor     r8d, r8d
0x180013e0b  mov     dl, 1
0x180013e0d  lea     rcx, [rbp+57h+var_40]
0x180013e11  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013e16  lea     rdx, aMountprotocol; "MountProtocol"
0x180013e1d  lea     rcx, [rbp+57h+var_40]
0x180013e21  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013e26  nop
0x180013e27  lea     rdx, [rbp+57h+var_40]
0x180013e2b  lea     rcx, [rbp+57h+var_80]
0x180013e2f  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013e34  mov     dword ptr [rax], 4000h
0x180013e3a  xor     r8d, r8d
0x180013e3d  mov     dl, 1
0x180013e3f  lea     rcx, [rbp+57h+var_40]
0x180013e43  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013e48  lea     rdx, aNfsprotocol; "NfsProtocol"
0x180013e4f  lea     rcx, [rbp+57h+var_40]
0x180013e53  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013e58  nop
0x180013e59  lea     rdx, [rbp+57h+var_40]
0x180013e5d  lea     rcx, [rbp+57h+var_80]
0x180013e61  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013e66  mov     dword ptr [rax], 8000h
0x180013e6c  xor     r8d, r8d
0x180013e6f  mov     dl, 1
0x180013e71  lea     rcx, [rbp+57h+var_40]
0x180013e75  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013e7a  lea     rdx, aNlmprotocol; "NlmProtocol"
0x180013e81  lea     rcx, [rbp+57h+var_40]
0x180013e85  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013e8a  nop
0x180013e8b  lea     rdx, [rbp+57h+var_40]
0x180013e8f  lea     rcx, [rbp+57h+var_80]
0x180013e93  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013e98  mov     dword ptr [rax], 10000h
0x180013e9e  xor     r8d, r8d
0x180013ea1  mov     dl, 1
0x180013ea3  lea     rcx, [rbp+57h+var_40]
0x180013ea7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013eac  lea     rdx, aNsmprotocol; "NsmProtocol"
0x180013eb3  lea     rcx, [rbp+57h+var_40]
0x180013eb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013ebc  nop
0x180013ebd  lea     rdx, [rbp+57h+var_40]
0x180013ec1  lea     rcx, [rbp+57h+var_80]
0x180013ec5  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013eca  mov     dword ptr [rax], 20000h
0x180013ed0  xor     r8d, r8d
0x180013ed3  mov     dl, 1
0x180013ed5  lea     rcx, [rbp+57h+var_40]
0x180013ed9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013ede  lea     rdx, aMapsvrprotocol; "MapsvrProtocol"
0x180013ee5  lea     rcx, [rbp+57h+var_40]
0x180013ee9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013eee  nop
0x180013eef  lea     rdx, [rbp+57h+var_40]
0x180013ef3  lea     rcx, [rbp+57h+var_80]
0x180013ef7  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013efc  mov     dword ptr [rax], 40000h
0x180013f02  xor     r8d, r8d
0x180013f05  mov     dl, 1
0x180013f07  lea     rcx, [rbp+57h+var_40]
0x180013f0b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013f10  lea     rdx, aNisprotocol; "NisProtocol"
0x180013f17  lea     rcx, [rbp+57h+var_40]
0x180013f1b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013f20  nop
0x180013f21  lea     rdx, [rbp+57h+var_40]
0x180013f25  lea     rcx, [rbp+57h+var_80]
0x180013f29  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013f2e  mov     dword ptr [rax], 80000h
0x180013f34  xor     r8d, r8d
0x180013f37  mov     dl, 1
0x180013f39  lea     rcx, [rbp+57h+var_40]
0x180013f3d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013f42  lea     rdx, aPreserveinheri; "PreserveInheritance"
0x180013f49  lea     rcx, [rbp+57h+var_40]
0x180013f4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013f52  nop
0x180013f53  lea     rdx, [rbp+57h+var_40]
0x180013f57  lea     rcx, [rbp+57h+var_80]
0x180013f5b  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013f60  mov     dword ptr [rax], 100000h
0x180013f66  xor     r8d, r8d
0x180013f69  mov     dl, 1
0x180013f6b  lea     rcx, [rbp+57h+var_40]
0x180013f6f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013f74  lea     rdx, aNetgroupcachet; "NetgroupCacheTimeout"
0x180013f7b  lea     rcx, [rbp+57h+var_40]
0x180013f7f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013f84  nop
0x180013f85  lea     rdx, [rbp+57h+var_40]
0x180013f89  lea     rcx, [rbp+57h+var_80]
0x180013f8d  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013f92  mov     dword ptr [rax], 200000h
0x180013f98  xor     r8d, r8d
0x180013f9b  mov     dl, 1
0x180013f9d  lea     rcx, [rbp+57h+var_40]
0x180013fa1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013fa6  lea     rdx, aUnmappeduserac; "UnmappedUserAccount"
0x180013fad  lea     rcx, [rbp+57h+var_40]
0x180013fb1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013fb6  nop
0x180013fb7  lea     rdx, [rbp+57h+var_40]
0x180013fbb  lea     rcx, [rbp+57h+var_80]
0x180013fbf  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013fc4  mov     dword ptr [rax], 400000h
0x180013fca  xor     r8d, r8d
0x180013fcd  mov     dl, 1
0x180013fcf  lea     rcx, [rbp+57h+var_40]
0x180013fd3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013fd8  lea     rdx, aWorldaccount; "WorldAccount"
0x180013fdf  lea     rcx, [rbp+57h+var_40]
0x180013fe3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013fe8  nop
0x180013fe9  lea     rdx, [rbp+57h+var_40]
0x180013fed  lea     rcx, [rbp+57h+var_80]
0x180013ff1  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180013ff6  mov     dword ptr [rax], 800000h
0x180013ffc  xor     r8d, r8d
0x180013fff  mov     dl, 1
0x180014001  lea     rcx, [rbp+57h+var_40]
0x180014005  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001400a  lea     rdx, aAlwaysopenbyna; "AlwaysOpenByName"
0x180014011  lea     rcx, [rbp+57h+var_40]
0x180014015  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001401a  nop
0x18001401b  lea     rdx, [rbp+57h+var_40]
0x18001401f  lea     rcx, [rbp+57h+var_80]
0x180014023  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180014028  mov     dword ptr [rax], 1000000h
0x18001402e  xor     r8d, r8d
0x180014031  mov     dl, 1
0x180014033  lea     rcx, [rbp+57h+var_40]
0x180014037  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001403c  lea     rdx, aLeaseperiod; "LeasePeriod"
0x180014043  lea     rcx, [rbp+57h+var_40]
0x180014047  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001404c  nop
0x18001404d  lea     rdx, [rbp+57h+var_40]
0x180014051  lea     rcx, [rbp+57h+var_80]
0x180014055  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18001405a  mov     dword ptr [rax], 2000000h
  ... truncated ...
```
