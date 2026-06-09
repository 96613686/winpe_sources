# HCAttributeKeyCallback(ATL::CRegKey &,ushort const *,ushort const *,void *)

- ea: `0x18000e2a0`
- end: `0x18000e5ef`
- name: `?HCAttributeKeyCallback@@YAJAEAVCRegKey@ATL@@PEBG1PEAX@Z`
- size: `847`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a528`
- `0x18000c79c`
- `0x18000cd30`
- `0x18000e2a0`
- `0x180011050`
- `0x180011920`
- `0x180011cb4`
- `0x1800136b0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000e353`
- `ADVAPI32!RegQueryValueExW` at `0x18000e353`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HCAttributeKeyCallback(HKEY *a1, unsigned __int16 *a2, const unsigned __int16 *a3, void *a4)
{
  LSTATUS Value; // eax
  int v8; // ecx
  signed int v9; // esi
  int StringWithAlloc; // eax
  int v11; // ecx
  void *v12; // rbx
  int v13; // eax
  int v14; // ecx
  void *v15; // rdi
  int v16; // eax
  int v17; // ecx
  char v18; // r15
  void *v19; // rbx
  __int64 v20; // r8
  __int64 v21; // rbx
  const struct StoredHelperAttributeInfo *v22; // rdx
  DWORD cbData[2]; // [rsp+30h] [rbp-99h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-91h] BYREF
  DWORD Type[4]; // [rsp+40h] [rbp-89h] BYREF
  BOOL v27; // [rsp+50h] [rbp-79h] BYREF
  _WORD v28[8]; // [rsp+58h] [rbp-71h] BYREF
  __int64 v29; // [rsp+68h] [rbp-61h]
  __int64 v30; // [rsp+70h] [rbp-59h]
  _WORD v31[8]; // [rsp+78h] [rbp-51h] BYREF
  __int64 v32; // [rsp+88h] [rbp-41h]
  __int64 v33; // [rsp+90h] [rbp-39h]
  _WORD v34[8]; // [rsp+98h] [rbp-31h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-21h]
  __int64 v36; // [rsp+B0h] [rbp-19h]
  _WORD v37[8]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-1h]
  __int64 v39; // [rsp+D0h] [rbp+7h]

  v30 = 7;
  v29 = 0;
  v28[0] = 0;
  v33 = 7;
  v32 = 0;
  v31[0] = 0;
  v36 = 7;
  v35 = 0;
  v34[0] = 0;
  v39 = 7;
  v38 = 0;
  v37[0] = 0;
  std::wstring::assign(v28, a2);
  *(_DWORD *)Data = 0;
  Type[0] = 0;
  cbData[0] = 4;
  Value = RegQueryValueExW(*a1, L"Required", 0, Type, Data, cbData);
  v9 = Value;
  if ( Value )
  {
    if ( Value <= 0 )
      goto LABEL_21;
    goto LABEL_20;
  }
  if ( Type[0] != 4 )
  {
    LOWORD(v9) = 13;
LABEL_20:
    v9 = (unsigned __int16)v9 | 0x80070000;
LABEL_21:
    v18 = 1;
    if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
      McTemplateU0qqzz_EventWriteTransfer(v8, (unsigned int)RegistryError, v9, 826, (__int64)a3, (__int64)L"Required");
LABEL_23:
    if ( v9 >= 0 )
    {
      if ( (unsigned __int64)&v27 >= *((_QWORD *)a4 + 1) || *(_QWORD *)a4 > (unsigned __int64)&v27 )
        v18 = 0;
      v20 = *((_QWORD *)a4 + 2);
      if ( v18 )
      {
        v21 = ((__int64)v28 - *(_QWORD *)a4) / 136;
        if ( *((_QWORD *)a4 + 1) == v20 )
          std::vector<StoredHelperAttributeInfo>::_Reserve(a4);
        v22 = (const struct StoredHelperAttributeInfo *)(*(_QWORD *)a4 + 136 * v21);
      }
      else
      {
        if ( *((_QWORD *)a4 + 1) == v20 )
          std::vector<StoredHelperAttributeInfo>::_Reserve(a4);
        v22 = (const struct StoredHelperAttributeInfo *)&v27;
      }
      StoredHelperAttributeInfo::StoredHelperAttributeInfo(*((StoredHelperAttributeInfo **)a4 + 1), v22);
      *((_QWORD *)a4 + 1) += 136LL;
    }
    goto LABEL_35;
  }
  v27 = *(_DWORD *)Data != 0;
  *(_QWORD *)cbData = 0;
  StringWithAlloc = RegUtilLoadStringWithAlloc((unsigned __int16 **)cbData, (struct ATL::CRegKey *)a1, L"DefaultValue");
  if ( StringWithAlloc < 0 )
  {
    if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
      McTemplateU0qqzz_EventWriteTransfer(
        v11,
        (unsigned int)RegistryWarning,
        StringWithAlloc,
        841,
        (__int64)a3,
        (__int64)L"DefaultValue");
  }
  else
  {
    v12 = *(void **)cbData;
    std::wstring::assign(v37, *(void **)cbData);
    if ( v12 )
      CoTaskMemFree(v12);
  }
  *(_QWORD *)cbData = 0;
  v13 = RegUtilLoadStringWithAlloc((unsigned __int16 **)cbData, (struct ATL::CRegKey *)a1, L"Description");
  v9 = v13;
  if ( v13 >= 0 )
  {
    v15 = *(void **)cbData;
    *(_QWORD *)Type = *(_QWORD *)cbData;
    std::wstring::assign(v34, *(void **)cbData);
    *(_QWORD *)cbData = 0;
    v16 = RegUtilLoadStringWithAlloc((unsigned __int16 **)cbData, (struct ATL::CRegKey *)a1, L"Type");
    v9 = v16;
    v18 = 1;
    if ( v16 < 0 )
    {
      if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
        McTemplateU0qqzz_EventWriteTransfer(v17, (unsigned int)RegistryError, v16, 860, (__int64)a3, (__int64)L"Type");
    }
    else
    {
      v19 = *(void **)cbData;
      std::wstring::assign(v31, *(void **)cbData);
      if ( v19 )
        CoTaskMemFree(v19);
    }
    if ( v15 )
      CoTaskMemFree(v15);
    goto LABEL_23;
  }
  if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
    McTemplateU0qqzz_EventWriteTransfer(
      v14,
      (unsigned int)RegistryError,
      v13,
      865,
      (__int64)a3,
      (__int64)L"Description");
LABEL_35:
  StoredHelperAttributeInfo::~StoredHelperAttributeInfo((StoredHelperAttributeInfo *)&v27);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e2a0  push    rbp
0x18000e2a2  push    rbx
0x18000e2a3  push    rsi
0x18000e2a4  push    rdi
0x18000e2a5  push    r12
0x18000e2a7  push    r14
0x18000e2a9  push    r15
0x18000e2ab  lea     rbp, [rsp-27h]
0x18000e2b0  sub     rsp, 0F0h
0x18000e2b7  mov     rax, cs:__security_cookie
0x18000e2be  xor     rax, rsp
0x18000e2c1  mov     [rbp+57h+var_40], rax
0x18000e2c5  mov     r14, r9
0x18000e2c8  mov     r12, r8
0x18000e2cb  mov     r15, rcx
0x18000e2ce  mov     ecx, 7
0x18000e2d3  mov     [rbp+57h+var_B0], rcx
0x18000e2d7  mov     [rbp+57h+var_B8], 0
0x18000e2df  xor     eax, eax
0x18000e2e1  mov     [rbp+57h+var_C8], ax
0x18000e2e5  mov     [rbp+57h+var_90], rcx
0x18000e2e9  mov     [rbp+57h+var_98], rax
0x18000e2ed  mov     [rbp+57h+var_A8], ax
0x18000e2f1  mov     [rbp+57h+var_70], rcx
0x18000e2f5  mov     [rbp+57h+var_78], rax
0x18000e2f9  mov     [rbp+57h+var_88], ax
0x18000e2fd  mov     [rbp+57h+var_50], rcx
0x18000e301  mov     [rbp+57h+var_58], rax
0x18000e305  mov     [rbp+57h+var_68], ax
0x18000e309  lea     rcx, [rbp+57h+var_C8]; void *
0x18000e30d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e312  mov     dword ptr [rsp+120h+Data], 0
0x18000e31a  mov     [rsp+120h+Type], 0
0x18000e322  mov     [rsp+120h+cbData], 4
0x18000e32a  lea     rax, [rsp+120h+cbData]
0x18000e32f  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18000e334  lea     rax, [rsp+120h+Data]
0x18000e339  mov     [rsp+120h+lpData], rax; lpData
0x18000e33e  lea     r9, [rsp+120h+Type]; lpType
0x18000e343  xor     r8d, r8d; lpReserved
0x18000e346  lea     rbx, ValueName; "Required"
0x18000e34d  mov     rdx, rbx; lpValueName
0x18000e350  mov     rcx, [r15]; hKey
0x18000e353  call    cs:__imp_RegQueryValueExW
0x18000e35a  nop     dword ptr [rax+rax+00h]
0x18000e35f  mov     esi, eax
0x18000e361  test    eax, eax
0x18000e363  jnz     loc_18000E506
0x18000e369  cmp     [rsp+120h+Type], 4
0x18000e36e  jz      short loc_18000E378
0x18000e370  lea     esi, [rax+0Dh]
0x18000e373  jmp     loc_18000E508
0x18000e378  xor     eax, eax
0x18000e37a  cmp     dword ptr [rsp+120h+Data], eax
0x18000e37e  setnz   al
0x18000e381  mov     [rbp+57h+var_D0], eax
0x18000e384  mov     qword ptr [rsp+120h+cbData], 0
0x18000e38d  lea     rbx, aDefaultvalue; "DefaultValue"
0x18000e394  mov     r8, rbx; unsigned __int16 *
0x18000e397  mov     rdx, r15; struct ATL::CRegKey *
0x18000e39a  lea     rcx, [rsp+120h+cbData]; unsigned __int16 **
0x18000e39f  call    ?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z; RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)
0x18000e3a4  test    eax, eax
0x18000e3a6  js      short loc_18000E3D5
0x18000e3a8  mov     rbx, qword ptr [rsp+120h+cbData]
0x18000e3ad  mov     qword ptr [rsp+120h+cbData], rbx
0x18000e3b2  mov     rdx, rbx; Src
0x18000e3b5  lea     rcx, [rbp+57h+var_68]; void *
0x18000e3b9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e3be  nop
0x18000e3bf  test    rbx, rbx
0x18000e3c2  jz      short loc_18000E3FD
0x18000e3c4  mov     rcx, rbx; pv
0x18000e3c7  call    cs:__imp_CoTaskMemFree
0x18000e3ce  nop     dword ptr [rax+rax+00h]
0x18000e3d3  jmp     short loc_18000E3FD
0x18000e3d5  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 2
0x18000e3dc  jz      short loc_18000E3FD
0x18000e3de  mov     [rsp+120h+lpcbData], rbx
0x18000e3e3  mov     [rsp+120h+lpData], r12
0x18000e3e8  mov     r9d, 349h
0x18000e3ee  mov     r8d, eax
0x18000e3f1  lea     rdx, RegistryWarning
0x18000e3f8  call    McTemplateU0qqzz_EventWriteTransfer
0x18000e3fd  mov     qword ptr [rsp+120h+cbData], 0
0x18000e406  lea     rbx, aDescription; "Description"
0x18000e40d  mov     r8, rbx; unsigned __int16 *
0x18000e410  mov     rdx, r15; struct ATL::CRegKey *
0x18000e413  lea     rcx, [rsp+120h+cbData]; unsigned __int16 **
0x18000e418  call    ?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z; RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)
0x18000e41d  mov     esi, eax
0x18000e41f  test    eax, eax
0x18000e421  js      loc_18000E4D2
0x18000e427  mov     rdi, qword ptr [rsp+120h+cbData]
0x18000e42c  mov     qword ptr [rsp+120h+Type], rdi
0x18000e431  mov     rdx, rdi; Src
0x18000e434  lea     rcx, [rbp+57h+var_88]; void *
0x18000e438  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e43d  mov     qword ptr [rsp+120h+cbData], 0
0x18000e446  lea     rbx, aType; "Type"
0x18000e44d  mov     r8, rbx; unsigned __int16 *
0x18000e450  mov     rdx, r15; struct ATL::CRegKey *
0x18000e453  lea     rcx, [rsp+120h+cbData]; unsigned __int16 **
0x18000e458  call    ?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z; RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)
0x18000e45d  mov     esi, eax
0x18000e45f  mov     r15b, 1
0x18000e462  test    eax, eax
0x18000e464  js      short loc_18000E493
0x18000e466  mov     rbx, qword ptr [rsp+120h+cbData]
0x18000e46b  mov     qword ptr [rsp+120h+cbData], rbx
0x18000e470  mov     rdx, rbx; Src
0x18000e473  lea     rcx, [rbp+57h+var_A8]; void *
0x18000e477  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e47c  nop
0x18000e47d  test    rbx, rbx
0x18000e480  jz      short loc_18000E4BC
0x18000e482  mov     rcx, rbx; pv
0x18000e485  call    cs:__imp_CoTaskMemFree
0x18000e48c  nop     dword ptr [rax+rax+00h]
0x18000e491  jmp     short loc_18000E4BC
0x18000e493  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, r15b
0x18000e49a  jz      short loc_18000E4BC
0x18000e49c  mov     [rsp+120h+lpcbData], rbx
0x18000e4a1  mov     [rsp+120h+lpData], r12
0x18000e4a6  mov     r9d, 35Ch
0x18000e4ac  mov     r8d, eax
0x18000e4af  lea     rdx, RegistryError
0x18000e4b6  call    McTemplateU0qqzz_EventWriteTransfer
0x18000e4bb  nop
0x18000e4bc  test    rdi, rdi
0x18000e4bf  jz      short loc_18000E53C
0x18000e4c1  mov     rcx, rdi; pv
0x18000e4c4  call    cs:__imp_CoTaskMemFree
0x18000e4cb  nop     dword ptr [rax+rax+00h]
0x18000e4d0  jmp     short loc_18000E53C
0x18000e4d2  mov     r15b, 1
0x18000e4d5  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, r15b
0x18000e4dc  jz      loc_18000E5C5
0x18000e4e2  mov     [rsp+120h+lpcbData], rbx
0x18000e4e7  mov     [rsp+120h+lpData], r12
0x18000e4ec  mov     r9d, 361h
0x18000e4f2  mov     r8d, eax
0x18000e4f5  lea     rdx, RegistryError
0x18000e4fc  call    McTemplateU0qqzz_EventWriteTransfer
0x18000e501  jmp     loc_18000E5C5
0x18000e506  jle     short loc_18000E511
0x18000e508  movzx   esi, si
0x18000e50b  or      esi, 80070000h
0x18000e511  mov     r15b, 1
0x18000e514  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, r15b
0x18000e51b  jz      short loc_18000E53C
0x18000e51d  mov     [rsp+120h+lpcbData], rbx
0x18000e522  mov     [rsp+120h+lpData], r12
0x18000e527  mov     r9d, 33Ah
0x18000e52d  mov     r8d, esi
0x18000e530  lea     rdx, RegistryError
0x18000e537  call    McTemplateU0qqzz_EventWriteTransfer
0x18000e53c  test    esi, esi
0x18000e53e  js      loc_18000E5C5
0x18000e544  lea     rax, [rbp+57h+var_D0]
0x18000e548  cmp     rax, [r14+8]
0x18000e54c  jnb     short loc_18000E557
0x18000e54e  lea     rax, [rbp+57h+var_D0]
0x18000e552  cmp     [r14], rax
0x18000e555  jbe     short loc_18000E55A
0x18000e557  xor     r15b, r15b
0x18000e55a  mov     r8, [r14+10h]
0x18000e55e  test    r15b, r15b
0x18000e561  jz      short loc_18000E5A2
0x18000e563  lea     rcx, [rbp+57h+var_D0]
0x18000e567  sub     rcx, [r14]
0x18000e56a  mov     rax, 7878787878787879h
0x18000e574  imul    rcx
0x18000e577  mov     rbx, rdx
0x18000e57a  sar     rbx, 6
0x18000e57e  mov     rax, rbx
0x18000e581  shr     rax, 3Fh
0x18000e585  add     rbx, rax
0x18000e588  cmp     [r14+8], r8
0x18000e58c  jnz     short loc_18000E596
0x18000e58e  mov     rcx, r14
0x18000e591  call    ?_Reserve@?$vector@UStoredHelperAttributeInfo@@V?$allocator@UStoredHelperAttributeInfo@@@std@@@std@@IEAAX_K@Z; std::vector<StoredHelperAttributeInfo>::_Reserve(unsigned __int64)
0x18000e596  imul    rdx, rbx, 88h
0x18000e59d  add     rdx, [r14]
0x18000e5a0  jmp     short loc_18000E5B4
0x18000e5a2  cmp     [r14+8], r8
0x18000e5a6  jnz     short loc_18000E5B0
0x18000e5a8  mov     rcx, r14
0x18000e5ab  call    ?_Reserve@?$vector@UStoredHelperAttributeInfo@@V?$allocator@UStoredHelperAttributeInfo@@@std@@@std@@IEAAX_K@Z; std::vector<StoredHelperAttributeInfo>::_Reserve(unsigned __int64)
0x18000e5b0  lea     rdx, [rbp+57h+var_D0]; struct StoredHelperAttributeInfo *
0x18000e5b4  mov     rcx, [r14+8]; this
0x18000e5b8  call    ??0StoredHelperAttributeInfo@@QEAA@AEBU0@@Z; StoredHelperAttributeInfo::StoredHelperAttributeInfo(StoredHelperAttributeInfo const &)
0x18000e5bd  add     qword ptr [r14+8], 88h
0x18000e5c5  lea     rcx, [rbp+57h+var_D0]; this
0x18000e5c9  call    ??1StoredHelperAttributeInfo@@QEAA@XZ; StoredHelperAttributeInfo::~StoredHelperAttributeInfo(void)
0x18000e5ce  mov     eax, esi
0x18000e5d0  mov     rcx, [rbp+57h+var_40]
0x18000e5d4  xor     rcx, rsp; StackCookie
0x18000e5d7  call    __security_check_cookie
0x18000e5dc  add     rsp, 0F0h
0x18000e5e3  pop     r15
0x18000e5e5  pop     r14
0x18000e5e7  pop     r12
0x18000e5e9  pop     rdi
0x18000e5ea  pop     rsi
0x18000e5eb  pop     rbx
0x18000e5ec  pop     rbp
0x18000e5ed  retn
```
