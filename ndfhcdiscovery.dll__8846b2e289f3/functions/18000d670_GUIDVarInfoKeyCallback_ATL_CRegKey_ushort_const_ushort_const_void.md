# GUIDVarInfoKeyCallback(ATL::CRegKey &,ushort const *,ushort const *,void *)

- ea: `0x18000d670`
- end: `0x18000d80e`
- name: `?GUIDVarInfoKeyCallback@@YAJAEAVCRegKey@ATL@@PEBG1PEAX@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *, LPCOLESTR lpsz, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000a528`
- `0x18000ccc0`
- `0x18000d670`
- `0x1800113ac`
- `0x180011920`
- `0x180011cb4`
- `0x1800136b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d6cb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d6cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d767`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d7a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d767`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d7a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GUIDVarInfoKeyCallback(
        struct ATL::CRegKey *a1,
        LPCOLESTR lpsz,
        const unsigned __int16 *a3,
        void *a4)
{
  int v7; // ecx
  HRESULT StringWithAlloc; // esi
  void *v9; // rbx
  int v10; // eax
  int v11; // ecx
  void *v12; // rdi
  LPVOID pv[2]; // [rsp+30h] [rbp-49h] BYREF
  CLSID pclsid; // [rsp+40h] [rbp-39h] BYREF
  _WORD v16[8]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v17; // [rsp+60h] [rbp-19h]
  __int64 v18; // [rsp+68h] [rbp-11h]
  _WORD v19[8]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v20; // [rsp+80h] [rbp+7h]
  __int64 v21; // [rsp+88h] [rbp+Fh]

  v18 = 7;
  v17 = 0;
  v16[0] = 0;
  v21 = 7;
  v20 = 0;
  v19[0] = 0;
  StringWithAlloc = CLSIDFromString(lpsz, &pclsid);
  pv[0] = 0;
  if ( StringWithAlloc < 0 )
  {
    if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
      McTemplateU0qqzz_EventWriteTransfer(
        v7,
        (unsigned int)RegistryError,
        StringWithAlloc,
        1022,
        (__int64)a3,
        (__int64)L"Description");
  }
  else
  {
    StringWithAlloc = RegUtilLoadStringWithAlloc((unsigned __int16 **)pv, a1, L"Description");
    if ( StringWithAlloc >= 0 )
    {
      v9 = pv[0];
      pv[1] = pv[0];
      pv[0] = 0;
      v10 = RegUtilLoadStringWithAlloc((unsigned __int16 **)pv, a1, L"Symbol");
      StringWithAlloc = v10;
      if ( v10 < 0 )
      {
        if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
          McTemplateU0qqzz_EventWriteTransfer(
            v11,
            (unsigned int)RegistryError,
            v10,
            1042,
            (__int64)a3,
            (__int64)L"Symbol");
      }
      else
      {
        v12 = pv[0];
        std::wstring::assign(v19, v9);
        std::wstring::assign(v16, v12);
        std::vector<GUIDVarInfo>::push_back(a4, &pclsid);
        if ( v12 )
          CoTaskMemFree(v12);
      }
      if ( v9 )
        CoTaskMemFree(v9);
    }
  }
  GUIDVarInfo::~GUIDVarInfo((GUIDVarInfo *)&pclsid);
  return (unsigned int)StringWithAlloc;
}

```

## disassembly

```asm
0x18000d670  push    rbp
0x18000d672  push    rbx
0x18000d673  push    rsi
0x18000d674  push    rdi
0x18000d675  push    r13
0x18000d677  push    r14
0x18000d679  push    r15
0x18000d67b  lea     rbp, [rsp-27h]
0x18000d680  sub     rsp, 0A0h
0x18000d687  mov     rax, cs:__security_cookie
0x18000d68e  xor     rax, rsp
0x18000d691  mov     [rbp+57h+var_40], rax
0x18000d695  mov     r15, r9
0x18000d698  mov     rdi, r8
0x18000d69b  mov     r9, rdx
0x18000d69e  mov     r14, rcx
0x18000d6a1  mov     ecx, 7
0x18000d6a6  mov     [rbp+57h+var_68], rcx
0x18000d6aa  mov     [rbp+57h+var_70], 0
0x18000d6b2  xor     eax, eax
0x18000d6b4  mov     [rbp+57h+var_80], ax
0x18000d6b8  mov     [rbp+57h+var_48], rcx
0x18000d6bc  mov     [rbp+57h+var_50], rax
0x18000d6c0  mov     [rbp+57h+var_60], ax
0x18000d6c4  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18000d6c8  mov     rcx, r9; lpsz
0x18000d6cb  call    cs:__imp_CLSIDFromString
0x18000d6d2  nop     dword ptr [rax+rax+00h]
0x18000d6d7  mov     esi, eax
0x18000d6d9  mov     [rbp+57h+pv], 0
0x18000d6e1  test    eax, eax
0x18000d6e3  js      loc_18000D7B4
0x18000d6e9  lea     r8, aDescription; "Description"
0x18000d6f0  mov     rdx, r14; struct ATL::CRegKey *
0x18000d6f3  lea     rcx, [rbp+57h+pv]; unsigned __int16 **
0x18000d6f7  call    ?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z; RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)
0x18000d6fc  mov     esi, eax
0x18000d6fe  test    eax, eax
0x18000d700  js      loc_18000D7E4
0x18000d706  mov     rbx, [rbp+57h+pv]
0x18000d70a  mov     [rbp+57h+var_98], rbx
0x18000d70e  mov     [rbp+57h+pv], 0
0x18000d716  lea     r13, aSymbol; "Symbol"
0x18000d71d  mov     r8, r13; unsigned __int16 *
0x18000d720  mov     rdx, r14; struct ATL::CRegKey *
0x18000d723  lea     rcx, [rbp+57h+pv]; unsigned __int16 **
0x18000d727  call    ?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z; RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)
0x18000d72c  mov     esi, eax
0x18000d72e  test    eax, eax
0x18000d730  js      short loc_18000D775
0x18000d732  mov     rdi, [rbp+57h+pv]
0x18000d736  mov     [rbp+57h+pv], rdi
0x18000d73a  mov     rdx, rbx; Src
0x18000d73d  lea     rcx, [rbp+57h+var_60]; void *
0x18000d741  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000d746  mov     rdx, rdi; Src
0x18000d749  lea     rcx, [rbp+57h+var_80]; void *
0x18000d74d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000d752  lea     rdx, [rbp+57h+pclsid]
0x18000d756  mov     rcx, r15
0x18000d759  call    ?push_back@?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@QEAAXAEBUGUIDVarInfo@@@Z; std::vector<GUIDVarInfo>::push_back(GUIDVarInfo const &)
0x18000d75e  nop
0x18000d75f  test    rdi, rdi
0x18000d762  jz      short loc_18000D79E
0x18000d764  mov     rcx, rdi; pv
0x18000d767  call    cs:__imp_CoTaskMemFree
0x18000d76e  nop     dword ptr [rax+rax+00h]
0x18000d773  jmp     short loc_18000D79E
0x18000d775  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000d77c  jz      short loc_18000D79E
0x18000d77e  mov     [rsp+0D0h+var_A8], r13
0x18000d783  mov     [rsp+0D0h+var_B0], rdi
0x18000d788  mov     r9d, 412h
0x18000d78e  mov     r8d, eax
0x18000d791  lea     rdx, RegistryError
0x18000d798  call    McTemplateU0qqzz_EventWriteTransfer
0x18000d79d  nop
0x18000d79e  test    rbx, rbx
0x18000d7a1  jz      short loc_18000D7E4
0x18000d7a3  mov     rcx, rbx; pv
0x18000d7a6  call    cs:__imp_CoTaskMemFree
0x18000d7ad  nop     dword ptr [rax+rax+00h]
0x18000d7b2  jmp     short loc_18000D7E4
0x18000d7b4  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000d7bb  jz      short loc_18000D7E4
0x18000d7bd  lea     rax, aDescription; "Description"
0x18000d7c4  mov     [rsp+0D0h+var_A8], rax
0x18000d7c9  mov     [rsp+0D0h+var_B0], rdi
0x18000d7ce  mov     r9d, 3FEh
0x18000d7d4  mov     r8d, esi
0x18000d7d7  lea     rdx, RegistryError
0x18000d7de  call    McTemplateU0qqzz_EventWriteTransfer
0x18000d7e3  nop
0x18000d7e4  lea     rcx, [rbp+57h+pclsid]; this
0x18000d7e8  call    ??1GUIDVarInfo@@QEAA@XZ; GUIDVarInfo::~GUIDVarInfo(void)
0x18000d7ed  mov     eax, esi
0x18000d7ef  mov     rcx, [rbp+57h+var_40]
0x18000d7f3  xor     rcx, rsp; StackCookie
0x18000d7f6  call    __security_check_cookie
0x18000d7fb  add     rsp, 0A0h
0x18000d802  pop     r15
0x18000d804  pop     r14
0x18000d806  pop     r13
0x18000d808  pop     rdi
0x18000d809  pop     rsi
0x18000d80a  pop     rbx
0x18000d80b  pop     rbp
0x18000d80c  retn
```
