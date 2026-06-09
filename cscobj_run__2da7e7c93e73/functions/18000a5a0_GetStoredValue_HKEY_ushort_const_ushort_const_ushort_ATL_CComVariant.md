# GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)

- ea: `0x18000a5a0`
- end: `0x18000a83a`
- name: `?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z`
- size: `666`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16@<r9w>, struct ATL::CComVariant *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ab6c`
- `0x1800281bc`

## callees

- `0x18000a5a0`
- `0x18000b1a8`
- `0x180027178`
- `0x180027fd0`
- `0x1800281bc`
- `0x180029458`
- `0x180029564`
- `0x180029c1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a5e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a5e8`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a713`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a713`
- `OLEAUT32!__imp_VariantClear` at `0x18000a64f`
- `OLEAUT32!__imp_VariantClear` at `0x18000a79a`
- `OLEAUT32!__imp_VariantClear` at `0x18000a7d8`
- `OLEAUT32!__imp_VariantClear` at `0x18000a815`
- `OLEAUT32!__imp_VariantClear` at `0x18000a64f`
- `OLEAUT32!__imp_VariantClear` at `0x18000a79a`
- `OLEAUT32!__imp_VariantClear` at `0x18000a7d8`
- `OLEAUT32!__imp_VariantClear` at `0x18000a815`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetStoredValue(HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *a3, __int16 a4, VARIANTARG *pvarg)
{
  LSTATUS v9; // eax
  const unsigned __int16 *v10; // rdx
  signed int Dword; // ebx
  __int16 v12; // si
  BSTR v13; // rax
  UINT v14; // eax
  struct tagVARIANT *v15; // r9
  BYTE v16; // si
  SHORT v17; // si
  LONG v18; // esi
  BSTR pbstr; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKeya[2]; // [rsp+38h] [rbp-10h] BYREF

  hKeya[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKeya,
    0);
  v9 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, hKeya);
  Dword = v9;
  if ( v9 > 0 )
    Dword = (unsigned __int16)v9 | 0x80070000;
  if ( Dword >= 0 )
  {
    if ( a4 == 11 )
    {
      LODWORD(pbstr) = 0;
      Dword = UstRegQueryDword(hKeya[0], a3, (unsigned int *)&pbstr);
      if ( Dword >= 0 )
      {
        if ( (_DWORD)pbstr )
          v12 = -1;
        else
          v12 = 0;
        if ( pvarg->vt != 11 )
        {
          VariantClear(pvarg);
          pvarg->vt = 11;
        }
        pvarg->iVal = v12;
      }
    }
    else if ( ((a4 - 3) & 0xFFEF) != 0 )
    {
      if ( ((a4 - 2) & 0xFFEF) != 0 )
      {
        if ( (unsigned __int16)(a4 - 16) > 1u )
        {
          if ( a4 == 8 )
          {
            pbstr = 0;
            Dword = UstRegQueryBSTRAlloc(hKeya[0], a3);
            if ( Dword >= 0 )
            {
              v13 = pbstr;
              pbstr = 0;
              pvarg->llVal = (LONGLONG)v13;
              pvarg->vt = 8;
            }
          }
          else
          {
            if ( a4 != 8200 )
            {
              if ( a4 == 8204 )
                Dword = GetMultiValueSetting(hKeya[0], v10, (struct ATL::CComVariant *)pvarg);
              else
                Dword = -2147024809;
              goto LABEL_38;
            }
            pbstr = 0;
            Dword = UstRegQueryBSTRAlloc(hKeya[0], a3);
            if ( Dword >= 0 )
            {
              v14 = SysStringLen(pbstr);
              Dword = UstVarLib::CscVarUtil_ConvertMULTISZToVariant(
                        pbstr,
                        (const unsigned __int16 *)(v14 + 1),
                        (unsigned int)pvarg,
                        v15);
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
          goto LABEL_38;
        }
        LODWORD(pbstr) = 0;
        Dword = UstRegQueryDword(hKeya[0], a3, (unsigned int *)&pbstr);
        if ( Dword >= 0 )
        {
          v16 = (unsigned __int8)pbstr;
          if ( pvarg->vt != 17 )
          {
            VariantClear(pvarg);
            pvarg->vt = 17;
          }
          pvarg->bVal = v16;
        }
      }
      else
      {
        LODWORD(pbstr) = 0;
        Dword = UstRegQueryDword(hKeya[0], a3, (unsigned int *)&pbstr);
        if ( Dword >= 0 )
        {
          v17 = (__int16)pbstr;
          if ( pvarg->vt != 2 )
          {
            VariantClear(pvarg);
            pvarg->vt = 2;
          }
          pvarg->iVal = v17;
        }
      }
    }
    else
    {
      LODWORD(pbstr) = 0;
      Dword = UstRegQueryDword(hKeya[0], a3, (unsigned int *)&pbstr);
      if ( Dword >= 0 )
      {
        v18 = (int)pbstr;
        if ( pvarg->vt != 3 )
        {
          VariantClear(pvarg);
          pvarg->vt = 3;
        }
        pvarg->lVal = v18;
      }
    }
  }
LABEL_38:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKeya);
  return (unsigned int)Dword;
}

```

## disassembly

```asm
0x18000a5a0  push    rbp
0x18000a5a2  push    rbx
0x18000a5a3  push    rsi
0x18000a5a4  push    rdi
0x18000a5a5  push    r12
0x18000a5a7  push    r14
0x18000a5a9  mov     rbp, rsp
0x18000a5ac  sub     rsp, 48h
0x18000a5b0  movzx   esi, r9w
0x18000a5b4  mov     r14, r8
0x18000a5b7  mov     rbx, rdx
0x18000a5ba  mov     rdi, rcx
0x18000a5bd  mov     [rbp+hKey], 0
0x18000a5c5  xor     edx, edx
0x18000a5c7  lea     rcx, [rbp+hKey]
0x18000a5cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000a5d0  lea     rax, [rbp+hKey]
0x18000a5d4  mov     [rsp+48h+phkResult], rax; phkResult
0x18000a5d9  mov     r9d, 20019h; samDesired
0x18000a5df  xor     r8d, r8d; ulOptions
0x18000a5e2  mov     rdx, rbx; lpSubKey
0x18000a5e5  mov     rcx, rdi; hKey
0x18000a5e8  call    cs:__imp_RegOpenKeyExW
0x18000a5ee  mov     ebx, eax
0x18000a5f0  test    eax, eax
0x18000a5f2  jle     short loc_18000A5FD
0x18000a5f4  movzx   ebx, ax
0x18000a5f7  or      ebx, 80070000h
0x18000a5fd  test    ebx, ebx
0x18000a5ff  js      loc_18000A822
0x18000a605  mov     r12d, 0Bh
0x18000a60b  cmp     si, r12w
0x18000a60f  jnz     short loc_18000A662
0x18000a611  mov     dword ptr [rbp+pbstr], 0
0x18000a618  lea     r8, [rbp+pbstr]; unsigned int *
0x18000a61c  mov     rdx, r14; unsigned __int16 *
0x18000a61f  mov     rcx, [rbp+hKey]; HKEY
0x18000a623  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x18000a628  mov     ebx, eax
0x18000a62a  test    eax, eax
0x18000a62c  js      loc_18000A822
0x18000a632  cmp     dword ptr [rbp+pbstr], 0
0x18000a636  jz      short loc_18000A63D
0x18000a638  or      esi, 0FFFFFFFFh
0x18000a63b  jmp     short loc_18000A642
0x18000a63d  xor     eax, eax
0x18000a63f  movzx   esi, ax
0x18000a642  mov     rdi, [rbp+pvarg]
0x18000a646  cmp     [rdi], r12w
0x18000a64a  jz      short loc_18000A659
0x18000a64c  mov     rcx, rdi; pvarg
0x18000a64f  call    cs:__imp_VariantClear
0x18000a655  mov     [rdi], r12w
0x18000a659  mov     [rdi+8], si
0x18000a65d  jmp     loc_18000A822
0x18000a662  movzx   eax, si
0x18000a665  mov     r12d, 3
0x18000a66b  sub     ax, r12w
0x18000a66f  mov     ecx, 0FFEFh
0x18000a674  test    cx, ax
0x18000a677  jz      loc_18000A7E8
0x18000a67d  movzx   eax, si
0x18000a680  mov     r12d, 2
0x18000a686  sub     ax, r12w
0x18000a68a  test    cx, ax
0x18000a68d  jz      loc_18000A7AA
0x18000a693  lea     eax, [rsi-10h]
0x18000a696  mov     r12d, 1
0x18000a69c  cmp     ax, r12w
0x18000a6a0  jbe     loc_18000A762
0x18000a6a6  lea     edi, [r12+7]
0x18000a6ab  cmp     si, di
0x18000a6ae  jnz     short loc_18000A6E7
0x18000a6b0  mov     [rbp+pbstr], 0
0x18000a6b8  lea     r8, [rbp+pbstr]
0x18000a6bc  mov     rdx, r14; unsigned __int16 *
0x18000a6bf  mov     rcx, [rbp+hKey]; HKEY
0x18000a6c3  call    ?UstRegQueryBSTRAlloc@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UstRegQueryBSTRAlloc(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18000a6c8  mov     ebx, eax
0x18000a6ca  test    eax, eax
0x18000a6cc  js      short loc_18000A6E5
0x18000a6ce  mov     rax, [rbp+pbstr]
0x18000a6d2  mov     [rbp+pbstr], 0
0x18000a6da  mov     rcx, [rbp+pvarg]
0x18000a6de  mov     [rcx+8], rax
0x18000a6e2  mov     [rcx], di
0x18000a6e5  jmp     short loc_18000A72C
0x18000a6e7  mov     eax, 2008h
0x18000a6ec  cmp     si, ax
0x18000a6ef  jnz     short loc_18000A73A
0x18000a6f1  mov     [rbp+pbstr], 0
0x18000a6f9  lea     r8, [rbp+pbstr]
0x18000a6fd  mov     rdx, r14; unsigned __int16 *
0x18000a700  mov     rcx, [rbp+hKey]; HKEY
0x18000a704  call    ?UstRegQueryBSTRAlloc@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UstRegQueryBSTRAlloc(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18000a709  mov     ebx, eax
0x18000a70b  test    eax, eax
0x18000a70d  js      short loc_18000A72C
0x18000a70f  mov     rcx, [rbp+pbstr]; pbstr
0x18000a713  call    cs:__imp_SysStringLen
0x18000a719  lea     edx, [r12+rax]; unsigned __int16 *
0x18000a71d  mov     r8, [rbp+pvarg]; unsigned int
0x18000a721  mov     rcx, [rbp+pbstr]; psz
0x18000a725  call    ?CscVarUtil_ConvertMULTISZToVariant@UstVarLib@@YAJPEBGKPEAUtagVARIANT@@@Z; UstVarLib::CscVarUtil_ConvertMULTISZToVariant(ushort const *,ulong,tagVARIANT *)
0x18000a72a  mov     ebx, eax
0x18000a72c  lea     rcx, [rbp+pbstr]
0x18000a730  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000a735  jmp     loc_18000A822
0x18000a73a  mov     eax, 200Ch
0x18000a73f  cmp     si, ax
0x18000a742  jnz     short loc_18000A758
0x18000a744  mov     r8, [rbp+pvarg]; struct ATL::CComVariant *
0x18000a748  mov     rcx, [rbp+hKey]; hKey
0x18000a74c  call    ?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z; GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)
0x18000a751  mov     ebx, eax
0x18000a753  jmp     loc_18000A822
0x18000a758  mov     ebx, 80070057h
0x18000a75d  jmp     loc_18000A822
0x18000a762  mov     dword ptr [rbp+pbstr], 0
0x18000a769  lea     r8, [rbp+pbstr]; unsigned int *
0x18000a76d  mov     rdx, r14; unsigned __int16 *
0x18000a770  mov     rcx, [rbp+hKey]; HKEY
0x18000a774  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x18000a779  mov     ebx, eax
0x18000a77b  test    eax, eax
0x18000a77d  js      loc_18000A822
0x18000a783  mov     sil, byte ptr [rbp+pbstr]
0x18000a787  mov     r14d, 11h
0x18000a78d  mov     rdi, [rbp+pvarg]
0x18000a791  cmp     [rdi], r14w
0x18000a795  jz      short loc_18000A7A4
0x18000a797  mov     rcx, rdi; pvarg
0x18000a79a  call    cs:__imp_VariantClear
0x18000a7a0  mov     [rdi], r14w
0x18000a7a4  mov     [rdi+8], sil
0x18000a7a8  jmp     short loc_18000A822
0x18000a7aa  mov     dword ptr [rbp+pbstr], 0
0x18000a7b1  lea     r8, [rbp+pbstr]; unsigned int *
0x18000a7b5  mov     rdx, r14; unsigned __int16 *
0x18000a7b8  mov     rcx, [rbp+hKey]; HKEY
0x18000a7bc  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x18000a7c1  mov     ebx, eax
0x18000a7c3  test    eax, eax
0x18000a7c5  js      short loc_18000A822
0x18000a7c7  movzx   esi, word ptr [rbp+pbstr]
0x18000a7cb  mov     rdi, [rbp+pvarg]
0x18000a7cf  cmp     [rdi], r12w
0x18000a7d3  jz      short loc_18000A7E2
0x18000a7d5  mov     rcx, rdi; pvarg
0x18000a7d8  call    cs:__imp_VariantClear
0x18000a7de  mov     [rdi], r12w
0x18000a7e2  mov     [rdi+8], si
0x18000a7e6  jmp     short loc_18000A822
0x18000a7e8  mov     dword ptr [rbp+pbstr], 0
0x18000a7ef  lea     r8, [rbp+pbstr]; unsigned int *
0x18000a7f3  mov     rdx, r14; unsigned __int16 *
0x18000a7f6  mov     rcx, [rbp+hKey]; HKEY
0x18000a7fa  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x18000a7ff  mov     ebx, eax
0x18000a801  test    eax, eax
0x18000a803  js      short loc_18000A822
0x18000a805  mov     esi, dword ptr [rbp+pbstr]
0x18000a808  mov     rdi, [rbp+pvarg]
0x18000a80c  cmp     [rdi], r12w
0x18000a810  jz      short loc_18000A81F
0x18000a812  mov     rcx, rdi; pvarg
0x18000a815  call    cs:__imp_VariantClear
0x18000a81b  mov     [rdi], r12w
0x18000a81f  mov     [rdi+8], esi
0x18000a822  lea     rcx, [rbp+hKey]
0x18000a826  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a82b  mov     eax, ebx
0x18000a82d  add     rsp, 48h
0x18000a831  pop     r14
0x18000a833  pop     r12
0x18000a835  pop     rdi
0x18000a836  pop     rsi
0x18000a837  pop     rbx
0x18000a838  pop     rbp
0x18000a839  retn
```
