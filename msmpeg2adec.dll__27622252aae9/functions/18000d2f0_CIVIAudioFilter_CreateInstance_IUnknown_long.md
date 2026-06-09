# CIVIAudioFilter::CreateInstance(IUnknown *,long *)

- ea: `0x18000d2f0`
- end: `0x18000d47c`
- name: `?CreateInstance@CIVIAudioFilter@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `396`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180001360`
- `0x18000a140`
- `0x18000d2f0`
- `0x180010c10`
- `0x180010cf0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d391`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d391`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d45f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d45f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d357`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d357`

## string_xrefs

- `0x18000d349`: `CLSID\{083863F1-70DE-11d0-BD40-00A0C911CE86}\Instance\{5261169D-9B6C-435F-B1D5-F79BAF700C71}`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct CUnknown *__fastcall CIVIAudioFilter::CreateInstance(struct IUnknown *a1, int *a2)
{
  struct IUnknown *v5; // rax
  CIVIAudioFilter *v6; // rbx
  LPVOID v7; // rcx
  void *v8; // rax
  unsigned __int16 *v9; // rdx
  const struct _AMOVIESETUP_FILTER *v10; // r9
  LPVOID ppv; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  if ( (unsigned int)IsLicensedComponentAAC_Internal() || (unsigned int)IsLicensedComponentDOLBY_Internal() )
  {
    hKey = 0;
    if ( RegOpenKeyExW(
           HKEY_CLASSES_ROOT,
           L"CLSID\\{083863F1-70DE-11d0-BD40-00A0C911CE86}\\Instance\\{5261169D-9B6C-435F-B1D5-F79BAF700C71}",
           0,
           0x20019u,
           &hKey) )
    {
      v8 = operator new(0x45B0u);
      ppv = v8;
      if ( v8 )
        v6 = CIVIAudioFilter::CIVIAudioFilter((CIVIAudioFilter *)v8, v9, a1, v10, a2);
      else
        v6 = 0;
    }
    else
    {
      ppv = 0;
      if ( CoCreateInstance(&CLSID_CMPEG2Ac3AudDecoderDS, a1, 1u, &IID_IBaseFilter, &ppv) < 0 )
      {
        v6 = 0;
        if ( a2 )
          *a2 = -2147467259;
      }
      else
      {
        if ( a2 )
          *a2 = 0;
        v5 = (struct IUnknown *)operator new(0x20u);
        v6 = (CIVIAudioFilter *)v5;
        if ( v5 )
        {
          v7 = ppv;
          _InterlockedIncrement(&CBaseObject::m_cObjects);
          if ( a1 )
            v5 = a1;
          *((_QWORD *)v6 + 1) = v5;
          *((_DWORD *)v6 + 4) = 0;
          *(_QWORD *)v6 = &CUnknownWrapper::`vftable';
          *((_QWORD *)v6 + 3) = v7;
          if ( v7 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 8LL))(v7);
        }
        else
        {
          v6 = 0;
        }
      }
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  else
  {
    if ( a2 )
      *a2 = -1073418223;
    return 0;
  }
}

```

## disassembly

```asm
0x18000d2f0  mov     [rsp+arg_0], rbx
0x18000d2f5  push    rbp
0x18000d2f6  push    rsi
0x18000d2f7  push    rdi
0x18000d2f8  sub     rsp, 40h
0x18000d2fc  mov     rdi, rdx
0x18000d2ff  mov     rsi, rcx
0x18000d302  call    ?IsLicensedComponentAAC_Internal@@YAHXZ; IsLicensedComponentAAC_Internal(void)
0x18000d307  test    eax, eax
0x18000d309  jnz     short loc_18000D32F
0x18000d30b  call    ?IsLicensedComponentDOLBY_Internal@@YAHXZ; IsLicensedComponentDOLBY_Internal(void)
0x18000d310  test    eax, eax
0x18000d312  jnz     short loc_18000D32F
0x18000d314  test    rdi, rdi
0x18000d317  jz      short loc_18000D31F
0x18000d319  mov     dword ptr [rdi], 0C004F011h
0x18000d31f  xor     eax, eax
0x18000d321  mov     rbx, [rsp+58h+arg_0]
0x18000d326  add     rsp, 40h
0x18000d32a  pop     rdi
0x18000d32b  pop     rsi
0x18000d32c  pop     rbp
0x18000d32d  retn
0x18000d32f  xor     ebp, ebp
0x18000d331  mov     [rsp+58h+hKey], rbp
0x18000d336  lea     rax, [rsp+58h+hKey]
0x18000d33b  mov     [rsp+58h+phkResult], rax; phkResult
0x18000d340  mov     r9d, 20019h; samDesired
0x18000d346  xor     r8d, r8d; ulOptions
0x18000d349  lea     rdx, SubKey; "CLSID\\{083863F1-70DE-11d0-BD40-00A0C91"...
0x18000d350  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000d357  call    cs:__imp_RegOpenKeyExW
0x18000d35e  nop     dword ptr [rax+rax+00h]
0x18000d363  test    eax, eax
0x18000d365  jnz     loc_18000D429
0x18000d36b  mov     [rsp+58h+ppv], rbp
0x18000d370  lea     rax, [rsp+58h+ppv]
0x18000d375  mov     [rsp+58h+phkResult], rax; ppv
0x18000d37a  lea     r9, IID_IBaseFilter; riid
0x18000d381  mov     r8d, 1; dwClsContext
0x18000d387  mov     rdx, rsi; pUnkOuter
0x18000d38a  lea     rcx, CLSID_CMPEG2Ac3AudDecoderDS; rclsid
0x18000d391  call    cs:__imp_CoCreateInstance
0x18000d398  nop     dword ptr [rax+rax+00h]
0x18000d39d  test    eax, eax
0x18000d39f  js      short loc_18000D401
0x18000d3a1  test    rdi, rdi
0x18000d3a4  jz      short loc_18000D3A8
0x18000d3a6  mov     [rdi], ebp
0x18000d3a8  mov     ecx, 20h ; ' '; Size
0x18000d3ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d3b2  mov     rbx, rax
0x18000d3b5  mov     [rsp+58h+var_28], rax
0x18000d3ba  test    rax, rax
0x18000d3bd  jz      short loc_18000D3FC
0x18000d3bf  mov     rcx, [rsp+58h+ppv]
0x18000d3c4  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18000d3cb  test    rsi, rsi
0x18000d3ce  cmovnz  rax, rsi
0x18000d3d2  mov     [rbx+8], rax
0x18000d3d6  mov     [rbx+10h], ebp
0x18000d3d9  lea     rax, ??_7CUnknownWrapper@@6B@; const CUnknownWrapper::`vftable'
0x18000d3e0  mov     [rbx], rax
0x18000d3e3  mov     [rbx+18h], rcx
0x18000d3e7  test    rcx, rcx
0x18000d3ea  jz      short loc_18000D3FA
0x18000d3ec  mov     rax, [rcx]
0x18000d3ef  mov     rax, [rax+8]
0x18000d3f3  call    cs:__guard_dispatch_icall_fptr
0x18000d3f9  nop
0x18000d3fa  jmp     short loc_18000D40F
0x18000d3fc  mov     rbx, rbp
0x18000d3ff  jmp     short loc_18000D40F
0x18000d401  mov     rbx, rbp
0x18000d404  test    rdi, rdi
0x18000d407  jz      short loc_18000D40F
0x18000d409  mov     dword ptr [rdi], 80004005h
0x18000d40f  mov     rcx, [rsp+58h+ppv]
0x18000d414  test    rcx, rcx
0x18000d417  jz      short loc_18000D427
0x18000d419  mov     rax, [rcx]
0x18000d41c  mov     rax, [rax+10h]
0x18000d420  call    cs:__guard_dispatch_icall_fptr
0x18000d426  nop
0x18000d427  jmp     short loc_18000D455
0x18000d429  mov     ecx, 45B0h; Size
0x18000d42e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d433  mov     [rsp+58h+ppv], rax
0x18000d438  test    rax, rax
0x18000d43b  jz      short loc_18000D452
0x18000d43d  mov     [rsp+58h+phkResult], rdi; int *
0x18000d442  mov     r8, rsi; struct IUnknown *
0x18000d445  mov     rcx, rax; this
0x18000d448  call    ??0CIVIAudioFilter@@QEAA@PEAGPEAUIUnknown@@PEBU_AMOVIESETUP_FILTER@@PEAJ@Z; CIVIAudioFilter::CIVIAudioFilter(ushort *,IUnknown *,_AMOVIESETUP_FILTER const *,long *)
0x18000d44d  mov     rbx, rax
0x18000d450  jmp     short loc_18000D455
0x18000d452  mov     rbx, rbp
0x18000d455  mov     rcx, [rsp+58h+hKey]; hKey
0x18000d45a  test    rcx, rcx
0x18000d45d  jz      short loc_18000D46B
0x18000d45f  call    cs:__imp_RegCloseKey
0x18000d466  nop     dword ptr [rax+rax+00h]
0x18000d46b  mov     rax, rbx
0x18000d46e  mov     rbx, [rsp+58h+arg_0]
0x18000d473  add     rsp, 40h
0x18000d477  pop     rdi
0x18000d478  pop     rsi
0x18000d479  pop     rbp
0x18000d47a  retn
```
