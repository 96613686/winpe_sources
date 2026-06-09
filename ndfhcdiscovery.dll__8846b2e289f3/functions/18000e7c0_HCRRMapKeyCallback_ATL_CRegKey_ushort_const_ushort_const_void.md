# HCRRMapKeyCallback(ATL::CRegKey &,ushort const *,ushort const *,void *)

- ea: `0x18000e7c0`
- end: `0x18000ea8f`
- name: `?HCRRMapKeyCallback@@YAJAEAVCRegKey@ATL@@PEBG1PEAX@Z`
- size: `719`
- prototype: `int(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000bf34`
- `0x18000c1f0`
- `0x18000d2f0`
- `0x18000e7c0`
- `0x180011920`
- `0x1800136b0`
- `0x180015010`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x18000e884`
- `ADVAPI32!RegEnumValueW` at `0x18000e884`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e810`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e8b3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e810`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e8b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall HCRRMapKeyCallback(HKEY *a1, const unsigned __int16 *a2, const unsigned __int16 *a3, _QWORD *a4)
{
  _QWORD *v4; // r13
  const unsigned __int16 *v5; // r14
  _QWORD **v8; // r15
  HRESULT v9; // eax
  int v10; // ecx
  int v11; // edi
  HKEY v12; // r12
  DWORD v13; // esi
  LSTATUS v14; // eax
  int v15; // ecx
  _QWORD *i; // rax
  __int64 v17; // rax
  int v18; // r8d
  int v19; // ecx
  __int64 v20; // rbx
  DWORD cchValueName; // [rsp+44h] [rbp-2D4h] BYREF
  int v23; // [rsp+48h] [rbp-2D0h]
  _QWORD *v24; // [rsp+50h] [rbp-2C8h]
  _QWORD **v25; // [rsp+58h] [rbp-2C0h]
  HKEY v26; // [rsp+60h] [rbp-2B8h]
  const unsigned __int16 *v27; // [rsp+68h] [rbp-2B0h]
  char v28; // [rsp+70h] [rbp-2A8h] BYREF
  CLSID v29; // [rsp+80h] [rbp-298h] BYREF
  CLSID pclsid; // [rsp+90h] [rbp-288h] BYREF
  CLSID v31; // [rsp+A0h] [rbp-278h] BYREF
  _QWORD *v32; // [rsp+B0h] [rbp-268h]
  WCHAR ValueName[264]; // [rsp+C0h] [rbp-258h] BYREF

  v4 = a4;
  v5 = a3;
  v27 = a3;
  v8 = (_QWORD **)a4[2];
  pclsid = 0;
  v9 = CLSIDFromString(a2, &pclsid);
  v11 = v9;
  if ( v9 < 0 )
  {
    if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
      McTemplateU0qqzz_EventWriteTransfer(v10, (unsigned int)RegistryError, v9, 1190, (__int64)v5, (__int64)a2);
  }
  else
  {
    v24 = v4;
    v25 = v8;
    v12 = *a1;
    v26 = *a1;
    v13 = 0;
    while ( v11 >= 0 )
    {
      cchValueName = 260;
      v14 = RegEnumValueW(v12, v13, ValueName, &cchValueName, 0, 0, 0, 0);
      if ( v14 )
      {
        if ( v14 == 259 )
          return (unsigned int)v11;
        if ( v14 > 0 )
          v11 = (unsigned __int16)v14 | 0x80070000;
        else
          v11 = v14;
        v23 = v11;
        try
        {
          *(_QWORD *)&v29.Data1 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v29,
            L"Enum Index: %d",
            v13);
          v20 = *(_QWORD *)&v29.Data1;
          if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
            McTemplateU0qqzz_EventWriteTransfer(
              v19,
              (unsigned int)RegistryError,
              v11,
              1180,
              (__int64)v5,
              *(__int64 *)&v29.Data1);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v20 - 24 + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v20 - 24) + 8LL))(*(_QWORD *)(v20 - 24));
        }
        catch ( ATL::CAtlException )
        {
          v4 = v24;
          v8 = v25;
          v11 = v23;
          v12 = v26;
          v5 = v27;
        }
      }
      else
      {
        v29 = 0;
        v11 = CLSIDFromString(ValueName, &v29);
        if ( v11 < 0 )
        {
          if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
            McTemplateU0qqzz_EventWriteTransfer(
              v15,
              (unsigned int)RegistryError,
              v11,
              1165,
              (__int64)v5,
              (__int64)ValueName);
        }
        else
        {
          for ( i = *v8; i != v8[1]; i += 10 )
          {
            if ( *i == *(_QWORD *)&v29.Data1 && i[1] == *(_QWORD *)v29.Data4 )
            {
              v31 = pclsid;
              v32 = i;
              v17 = std::_Tree_buy<std::pair<_GUID const,GUIDVarInfo const *>>::_Buynode<std::pair<_GUID,GUIDVarInfo const *>>(
                      v4,
                      &v31);
              std::_Tree<std::_Tmap_traits<_GUID,GUIDVarInfo const *,std::less<_GUID>,std::allocator<std::pair<_GUID const,GUIDVarInfo const *>>,1>>::_Insert_nohint<std::pair<_GUID const,GUIDVarInfo const *> &,std::_Tree_node<std::pair<_GUID const,GUIDVarInfo const *>,void *> *>(
                (_DWORD)v4,
                (unsigned int)&v28,
                v18,
                v17 + 32,
                v17);
              break;
            }
          }
        }
      }
      ++v13;
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000e7c0  push    rbx
0x18000e7c2  push    rsi
0x18000e7c3  push    rdi
0x18000e7c4  push    r12
0x18000e7c6  push    r13
0x18000e7c8  push    r14
0x18000e7ca  push    r15
0x18000e7cc  sub     rsp, 2E0h
0x18000e7d3  mov     rax, cs:__security_cookie
0x18000e7da  xor     rax, rsp
0x18000e7dd  mov     [rsp+318h+var_48], rax
0x18000e7e5  mov     r13, r9
0x18000e7e8  mov     r14, r8
0x18000e7eb  mov     rbx, rdx
0x18000e7ee  mov     rsi, rcx
0x18000e7f1  mov     [rsp+318h+var_2B0], r8
0x18000e7f6  mov     r15, [r9+10h]
0x18000e7fa  xorps   xmm0, xmm0
0x18000e7fd  movups  xmmword ptr [rsp+318h+pclsid.Data1], xmm0
0x18000e805  lea     rdx, [rsp+318h+pclsid]; pclsid
0x18000e80d  mov     rcx, rbx; lpsz
0x18000e810  call    cs:__imp_CLSIDFromString
0x18000e817  nop     dword ptr [rax+rax+00h]
0x18000e81c  mov     edi, eax
0x18000e81e  test    eax, eax
0x18000e820  js      loc_18000EA41
0x18000e826  mov     [rsp+318h+var_2C8], r13
0x18000e82b  mov     [rsp+318h+var_2C0], r15
0x18000e830  mov     r12, [rsi]
0x18000e833  mov     [rsp+318h+var_2B8], r12
0x18000e838  xor     esi, esi
0x18000e83a  mov     [rsp+318h+var_2D8], esi
0x18000e83e  test    edi, edi
0x18000e840  js      loc_18000EA69
0x18000e846  mov     [rsp+318h+cchValueName], 104h
0x18000e84e  mov     [rsp+318h+lpcbData], 0; lpcbData
0x18000e857  mov     [rsp+318h+lpData], 0; lpData
0x18000e860  mov     [rsp+318h+lpType], 0; lpType
0x18000e869  mov     [rsp+318h+lpReserved], 0; lpReserved
0x18000e872  lea     r9, [rsp+318h+cchValueName]; lpcchValueName
0x18000e877  lea     r8, [rsp+318h+ValueName]; lpValueName
0x18000e87f  mov     edx, esi; dwIndex
0x18000e881  mov     rcx, r12; hKey
0x18000e884  call    cs:__imp_RegEnumValueW
0x18000e88b  nop     dword ptr [rax+rax+00h]
0x18000e890  test    eax, eax
0x18000e892  jnz     loc_18000E970
0x18000e898  xorps   xmm0, xmm0
0x18000e89b  movups  xmmword ptr [rsp+318h+var_298.Data1], xmm0
0x18000e8a3  lea     rdx, [rsp+318h+var_298]; pclsid
0x18000e8ab  lea     rcx, [rsp+318h+ValueName]; lpsz
0x18000e8b3  call    cs:__imp_CLSIDFromString
0x18000e8ba  nop     dword ptr [rax+rax+00h]
0x18000e8bf  mov     edi, eax
0x18000e8c1  test    eax, eax
0x18000e8c3  js      short loc_18000E937
0x18000e8c5  mov     rax, [r15]
0x18000e8c8  mov     rcx, qword ptr [rsp+318h+var_298.Data4]
0x18000e8d0  mov     rdx, qword ptr [rsp+318h+var_298.Data1]
0x18000e8d8  cmp     rax, [r15+8]
0x18000e8dc  jz      loc_18000EA3A
0x18000e8e2  cmp     [rax], rdx
0x18000e8e5  jnz     short loc_18000E8ED
0x18000e8e7  cmp     [rax+8], rcx
0x18000e8eb  jz      short loc_18000E8F3
0x18000e8ed  add     rax, 50h ; 'P'
0x18000e8f1  jmp     short loc_18000E8D8
0x18000e8f3  movups  xmm0, xmmword ptr [rsp+318h+pclsid.Data1]
0x18000e8fb  movdqu  [rsp+318h+var_278], xmm0
0x18000e904  mov     [rsp+318h+var_268], rax
0x18000e90c  lea     rdx, [rsp+318h+var_278]
0x18000e914  mov     rcx, r13
0x18000e917  call    ??$_Buynode@U?$pair@U_GUID@@PEBUGUIDVarInfo@@@std@@@?$_Tree_buy@U?$pair@$$CBU_GUID@@PEBUGUIDVarInfo@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEBUGUIDVarInfo@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEBUGUIDVarInfo@@@std@@PEAX@1@$$QEAU?$pair@U_GUID@@PEBUGUIDVarInfo@@@1@@Z; std::_Tree_buy<std::pair<_GUID const,GUIDVarInfo const *>>::_Buynode<std::pair<_GUID,GUIDVarInfo const *>>(std::pair<_GUID,GUIDVarInfo const *> &&)
0x18000e91c  lea     r9, [rax+20h]
0x18000e920  mov     [rsp+318h+lpReserved], rax
0x18000e925  lea     rdx, [rsp+318h+var_2A8]
0x18000e92a  mov     rcx, r13
0x18000e92d  call    ??$_Insert_nohint@AEAU?$pair@$$CBU_GUID@@PEBUGUIDVarInfo@@@std@@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEBUGUIDVarInfo@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@U_GUID@@PEBUGUIDVarInfo@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEBUGUIDVarInfo@@@std@@@4@$00@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEBUGUIDVarInfo@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBU_GUID@@PEBUGUIDVarInfo@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEBUGUIDVarInfo@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,GUIDVarInfo const *,std::less<_GUID>,std::allocator<std::pair<_GUID const,GUIDVarInfo const *>>,1>>::_Insert_nohint<std::pair<_GUID const,GUIDVarInfo const *> &,std::_Tree_node<std::pair<_GUID const,GUIDVarInfo const *>,void *> *>(bool,std::pair<_GUID const,GUIDVarInfo const *> &,std::_Tree_node<std::pair<_GUID const,GUIDVarInfo const *>,void *> *)
0x18000e932  jmp     loc_18000EA3A
0x18000e937  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000e93e  jz      loc_18000EA3A
0x18000e944  lea     rax, [rsp+318h+ValueName]
0x18000e94c  mov     [rsp+318h+lpType], rax
0x18000e951  mov     [rsp+318h+lpReserved], r14
0x18000e956  mov     r9d, 48Dh
0x18000e95c  mov     r8d, edi
0x18000e95f  lea     rdx, RegistryError
0x18000e966  call    McTemplateU0qqzz_EventWriteTransfer
0x18000e96b  jmp     loc_18000EA3A
0x18000e970  cmp     eax, 103h
0x18000e975  jz      loc_18000EA69
0x18000e97b  test    eax, eax
0x18000e97d  jg      short loc_18000E983
0x18000e97f  mov     edi, eax
0x18000e981  jmp     short loc_18000E98C
0x18000e983  movzx   edi, ax
0x18000e986  or      edi, 80070000h
0x18000e98c  mov     [rsp+318h+var_2D0], edi
0x18000e990  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e997  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e99e  mov     rax, [rax+18h]
0x18000e9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9a7  add     rax, 18h
0x18000e9ab  mov     qword ptr [rsp+318h+var_298.Data1], rax
0x18000e9b3  mov     r8d, esi
0x18000e9b6  lea     rdx, aEnumIndexD; "Enum Index: %d"
0x18000e9bd  lea     rcx, [rsp+318h+var_298]
0x18000e9c5  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000e9ca  mov     rbx, qword ptr [rsp+318h+var_298.Data1]
0x18000e9d2  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000e9d9  jz      short loc_18000E9FB
0x18000e9db  mov     [rsp+318h+lpType], rbx
0x18000e9e0  mov     [rsp+318h+lpReserved], r14
0x18000e9e5  mov     r9d, 49Ch
0x18000e9eb  mov     r8d, edi
0x18000e9ee  lea     rdx, RegistryError
0x18000e9f5  call    McTemplateU0qqzz_EventWriteTransfer
0x18000e9fa  nop
0x18000e9fb  lea     rdx, [rbx-18h]
0x18000e9ff  or      eax, 0FFFFFFFFh
0x18000ea02  lock xadd [rdx+10h], eax
0x18000ea07  sub     eax, 1
0x18000ea0a  jg      short loc_18000EA1C
0x18000ea0c  mov     rcx, [rdx]
0x18000ea0f  mov     rax, [rcx]
0x18000ea12  mov     rax, [rax+8]
0x18000ea16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea1b  nop
0x18000ea1c  jmp     short loc_18000EA3A
0x18000ea1e  mov     r13, [rsp+318h+var_2C8]
0x18000ea23  mov     r15, [rsp+318h+var_2C0]
0x18000ea28  mov     edi, [rsp+318h+var_2D0]
0x18000ea2c  mov     r12, [rsp+318h+var_2B8]
0x18000ea31  mov     esi, [rsp+318h+var_2D8]
0x18000ea35  mov     r14, [rsp+318h+var_2B0]
0x18000ea3a  inc     esi
0x18000ea3c  jmp     loc_18000E83A
0x18000ea41  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000ea48  jz      short loc_18000EA69
0x18000ea4a  mov     [rsp+318h+lpType], rbx
0x18000ea4f  mov     [rsp+318h+lpReserved], r14
0x18000ea54  mov     r9d, 4A6h
0x18000ea5a  mov     r8d, eax
0x18000ea5d  lea     rdx, RegistryError
0x18000ea64  call    McTemplateU0qqzz_EventWriteTransfer
0x18000ea69  mov     eax, edi
0x18000ea6b  mov     rcx, [rsp+318h+var_48]
0x18000ea73  xor     rcx, rsp; StackCookie
0x18000ea76  call    __security_check_cookie
0x18000ea7b  add     rsp, 2E0h
0x18000ea82  pop     r15
0x18000ea84  pop     r14
0x18000ea86  pop     r13
0x18000ea88  pop     r12
0x18000ea8a  pop     rdi
0x18000ea8b  pop     rsi
0x18000ea8c  pop     rbx
0x18000ea8d  retn
```
