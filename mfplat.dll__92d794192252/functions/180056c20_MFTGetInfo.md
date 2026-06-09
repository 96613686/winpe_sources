# MFTGetInfo

- ea: `0x180056c20`
- end: `0x180056e69`
- name: `MFTGetInfo`
- size: `585`
- prototype: `HRESULT __stdcall(CLSID *__struct_ptr clsidMFT, LPWSTR *pszName, MFT_REGISTER_TYPE_INFO **ppInputTypes, UINT32 *pcInputTypes, MFT_REGISTER_TYPE_INFO **ppOutputTypes, UINT32 *pcOutputTypes, IMFAttributes **ppAttributes)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180056c20`
- `0x1800571bc`
- `0x180057d78`
- `0x180057e90`
- `0x180058894`
- `0x1800aacc8`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056e53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056e5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056e53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056e5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056cb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056d5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056d70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056d5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056d70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056d87`

## pseudocode

```c
HRESULT __stdcall MFTGetInfo(
        CLSID *clsidMFT,
        LPWSTR *pszName,
        MFT_REGISTER_TYPE_INFO **ppInputTypes,
        UINT32 *pcInputTypes,
        MFT_REGISTER_TYPE_INFO **ppOutputTypes,
        UINT32 *pcOutputTypes,
        IMFAttributes **ppAttributes)
{
  IMFAttributes **v10; // rdi
  UINT32 *v11; // r12
  LPVOID *v12; // rsi
  LSTATUS v13; // eax
  HRESULT AttributesFromRegistry; // ebx
  struct _GUID v16; // [rsp+30h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+50h] BYREF

  hkey = 0;
  hKey = 0;
  if ( pszName )
    *pszName = 0;
  v10 = ppAttributes;
  v11 = pcOutputTypes;
  v12 = (LPVOID *)ppOutputTypes;
  if ( ppInputTypes )
  {
    *ppInputTypes = 0;
    if ( !pcInputTypes )
      goto LABEL_22;
  }
  else if ( !pcInputTypes )
  {
    goto LABEL_5;
  }
  *pcInputTypes = 0;
LABEL_5:
  if ( !v12 )
  {
    if ( !v11 )
      goto LABEL_7;
    goto LABEL_34;
  }
  *v12 = 0;
  if ( !v11 )
  {
LABEL_22:
    AttributesFromRegistry = -2147467261;
LABEL_23:
    if ( pszName )
    {
      CoTaskMemFree(*pszName);
      *pszName = 0;
    }
    if ( ppInputTypes )
    {
      CoTaskMemFree(*ppInputTypes);
      *ppInputTypes = 0;
      *pcInputTypes = 0;
    }
    if ( v12 )
    {
      CoTaskMemFree(*v12);
      *v12 = 0;
      *v11 = 0;
    }
    if ( v10 && *v10 )
    {
      (*v10)->Release(*v10);
      *v10 = 0;
    }
    return AttributesFromRegistry;
  }
LABEL_34:
  *v11 = 0;
LABEL_7:
  if ( v10 )
    *v10 = 0;
  v13 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"MediaFoundation\\Transforms", 0, 0x20019u, &hKey);
  AttributesFromRegistry = v13;
  if ( v13 > 0 )
    AttributesFromRegistry = (unsigned __int16)v13 | 0x80070000;
  if ( AttributesFromRegistry >= 0 )
  {
    v16 = *clsidMFT;
    AttributesFromRegistry = OpenMFTKey(hKey, &v16, &hkey);
    if ( AttributesFromRegistry >= 0 )
    {
      if ( !pszName || (AttributesFromRegistry = GetNameFromRegistry(hkey, pszName), AttributesFromRegistry >= 0) )
      {
        if ( !ppInputTypes
          || (AttributesFromRegistry = GetTypesFromRegistry(hkey, 0, (LPVOID *)ppInputTypes, pcInputTypes),
              AttributesFromRegistry >= 0) )
        {
          if ( !v12 || (AttributesFromRegistry = GetTypesFromRegistry(hkey, 1, v12, v11), AttributesFromRegistry >= 0) )
          {
            if ( v10 )
            {
              AttributesFromRegistry = MFCreateAttributes(v10, 0);
              if ( AttributesFromRegistry >= 0 )
                AttributesFromRegistry = GetAttributesFromRegistry(hkey, *v10);
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( hkey )
    RegCloseKey(hkey);
  if ( AttributesFromRegistry < 0 )
    goto LABEL_23;
  return AttributesFromRegistry;
}

```

## disassembly

```asm
0x180056c20  mov     [rsp-38h+arg_18], rbx
0x180056c25  mov     [rsp-38h+arg_0], rcx
0x180056c2a  push    rbp
0x180056c2b  push    rsi
0x180056c2c  push    rdi
0x180056c2d  push    r12
0x180056c2f  push    r13
0x180056c31  push    r14
0x180056c33  push    r15
0x180056c35  mov     rbp, rsp
0x180056c38  sub     rsp, 40h
0x180056c3c  xor     ecx, ecx
0x180056c3e  mov     r13, r9
0x180056c41  mov     [rbp+hkey], rcx
0x180056c45  mov     r15, r8
0x180056c48  mov     [rbp+hKey], rcx
0x180056c4c  mov     r14, rdx
0x180056c4f  test    rdx, rdx
0x180056c52  jz      short loc_180056C57
0x180056c54  mov     [rdx], rcx
0x180056c57  mov     rdi, [rbp+ppAttributes]
0x180056c5b  mov     r12, [rbp+pcOutputTypes]
0x180056c5f  mov     rsi, [rbp+ppOutputTypes]
0x180056c63  test    r15, r15
0x180056c66  jnz     loc_180056D48
0x180056c6c  test    r13, r13
0x180056c6f  jnz     loc_180056DBF
0x180056c75  test    rsi, rsi
0x180056c78  jnz     loc_180056DC7
0x180056c7e  test    r12, r12
0x180056c81  jnz     loc_180056DCF
0x180056c87  test    rdi, rdi
0x180056c8a  jnz     loc_180056DD8
0x180056c90  lea     rax, [rbp+hKey]
0x180056c94  mov     r9d, 20019h; samDesired
0x180056c9a  xor     r8d, r8d; ulOptions
0x180056c9d  mov     [rsp+40h+phkResult], rax; phkResult
0x180056ca2  lea     rdx, SubKey; "MediaFoundation\\Transforms"
0x180056ca9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180056cb0  call    cs:__imp_RegOpenKeyExW
0x180056cb6  mov     ebx, eax
0x180056cb8  test    eax, eax
0x180056cba  jg      short loc_180056D3A
0x180056cbc  test    ebx, ebx
0x180056cbe  js      short loc_180056D02
0x180056cc0  mov     rax, [rbp+arg_0]
0x180056cc4  lea     r8, [rbp+hkey]; HKEY *
0x180056cc8  mov     rcx, [rbp+hKey]; hKey
0x180056ccc  lea     rdx, [rbp+var_10]; struct _GUID
0x180056cd0  movups  xmm0, xmmword ptr [rax]
0x180056cd3  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x180056cd8  call    ?OpenMFTKey@@YAJPEAUHKEY__@@U_GUID@@PEAPEAU1@@Z; OpenMFTKey(HKEY__ *,_GUID,HKEY__ * *)
0x180056cdd  mov     ebx, eax
0x180056cdf  test    eax, eax
0x180056ce1  js      short loc_180056D02
0x180056ce3  test    r14, r14
0x180056ce6  jz      loc_180056DE0
0x180056cec  mov     rcx, [rbp+hkey]; hkey
0x180056cf0  mov     rdx, r14; unsigned __int16 **
0x180056cf3  call    ?GetNameFromRegistry@@YAJPEAUHKEY__@@PEAPEAG@Z; GetNameFromRegistry(HKEY__ *,ushort * *)
0x180056cf8  mov     ebx, eax
0x180056cfa  test    eax, eax
0x180056cfc  jns     loc_180056DE0
0x180056d02  mov     rcx, [rbp+hKey]; hKey
0x180056d06  test    rcx, rcx
0x180056d09  jnz     loc_180056E53
0x180056d0f  mov     rcx, [rbp+hkey]; hKey
0x180056d13  test    rcx, rcx
0x180056d16  jnz     loc_180056E5E
0x180056d1c  test    ebx, ebx
0x180056d1e  js      short loc_180056D55
0x180056d20  mov     eax, ebx
0x180056d22  mov     rbx, [rsp+40h+arg_18]
0x180056d2a  add     rsp, 40h
0x180056d2e  pop     r15
0x180056d30  pop     r14
0x180056d32  pop     r13
0x180056d34  pop     r12
0x180056d36  pop     rdi
0x180056d37  pop     rsi
0x180056d38  pop     rbp
0x180056d39  retn
0x180056d3a  movzx   ebx, ax
0x180056d3d  or      ebx, 80070000h
0x180056d43  jmp     loc_180056CBC
0x180056d48  mov     [r8], rcx
0x180056d4b  test    r13, r13
0x180056d4e  jnz     short loc_180056DBF
0x180056d50  mov     ebx, 80004003h
0x180056d55  test    r14, r14
0x180056d58  jz      short loc_180056D68
0x180056d5a  mov     rcx, [r14]; pv
0x180056d5d  call    cs:__imp_CoTaskMemFree
0x180056d63  xor     ecx, ecx
0x180056d65  mov     [r14], rcx
0x180056d68  test    r15, r15
0x180056d6b  jz      short loc_180056D7F
0x180056d6d  mov     rcx, [r15]; pv
0x180056d70  call    cs:__imp_CoTaskMemFree
0x180056d76  xor     ecx, ecx
0x180056d78  mov     [r15], rcx
0x180056d7b  mov     [r13+0], ecx
0x180056d7f  test    rsi, rsi
0x180056d82  jz      short loc_180056D96
0x180056d84  mov     rcx, [rsi]; pv
0x180056d87  call    cs:__imp_CoTaskMemFree
0x180056d8d  xor     ecx, ecx
0x180056d8f  mov     [rsi], rcx
0x180056d92  mov     [r12], ecx
0x180056d96  test    rdi, rdi
0x180056d99  jz      short loc_180056D20
0x180056d9b  mov     rcx, [rdi]
0x180056d9e  test    rcx, rcx
0x180056da1  jz      loc_180056D20
0x180056da7  mov     rax, [rcx]
0x180056daa  mov     rax, [rax+10h]
0x180056dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056db3  mov     qword ptr [rdi], 0
0x180056dba  jmp     loc_180056D20
0x180056dbf  mov     [r9], ecx
0x180056dc2  jmp     loc_180056C75
0x180056dc7  mov     [rsi], rcx
0x180056dca  test    r12, r12
0x180056dcd  jz      short loc_180056D50
0x180056dcf  mov     [r12], ecx
0x180056dd3  jmp     loc_180056C87
0x180056dd8  mov     [rdi], rcx
0x180056ddb  jmp     loc_180056C90
0x180056de0  test    r15, r15
0x180056de3  jz      short loc_180056E00
0x180056de5  mov     rcx, [rbp+hkey]
0x180056de9  mov     r9, r13
0x180056dec  mov     r8, r15
0x180056def  xor     edx, edx
0x180056df1  call    ?GetTypesFromRegistry@@YAJPEAUHKEY__@@W4_MEDIA_TYPES_INOUT@@PEAPEAU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAI@Z; GetTypesFromRegistry(HKEY__ *,_MEDIA_TYPES_INOUT,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 * *,uint *)
0x180056df6  mov     ebx, eax
0x180056df8  test    eax, eax
0x180056dfa  js      loc_180056D02
0x180056e00  test    rsi, rsi
0x180056e03  jz      short loc_180056E23
0x180056e05  mov     rcx, [rbp+hkey]
0x180056e09  mov     r9, r12
0x180056e0c  mov     r8, rsi
0x180056e0f  mov     edx, 1
0x180056e14  call    ?GetTypesFromRegistry@@YAJPEAUHKEY__@@W4_MEDIA_TYPES_INOUT@@PEAPEAU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAI@Z; GetTypesFromRegistry(HKEY__ *,_MEDIA_TYPES_INOUT,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 * *,uint *)
0x180056e19  mov     ebx, eax
0x180056e1b  test    eax, eax
0x180056e1d  js      loc_180056D02
0x180056e23  test    rdi, rdi
0x180056e26  jz      loc_180056D02
0x180056e2c  xor     edx, edx; cInitialSize
0x180056e2e  mov     rcx, rdi; ppMFAttributes
0x180056e31  call    MFCreateAttributes
0x180056e36  mov     ebx, eax
0x180056e38  test    eax, eax
0x180056e3a  js      loc_180056D02
0x180056e40  mov     rdx, [rdi]; pAttributes
0x180056e43  mov     rcx, [rbp+hkey]; hKey
0x180056e47  call    ?GetAttributesFromRegistry@@YAJPEAUHKEY__@@PEAUIMFAttributes@@@Z; GetAttributesFromRegistry(HKEY__ *,IMFAttributes *)
0x180056e4c  mov     ebx, eax
0x180056e4e  jmp     loc_180056D02
0x180056e53  call    cs:__imp_RegCloseKey
0x180056e59  jmp     loc_180056D0F
0x180056e5e  call    cs:__imp_RegCloseKey
0x180056e64  jmp     loc_180056D1C
```
