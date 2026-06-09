# ATL::CComModule::RegisterClassHelper(_GUID const &,ushort const *,ushort const *,uint,ulong)

- ea: `0x180004788`
- end: `0x1800049c1`
- name: `?RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1IK@Z`
- size: `569`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180007710`
- `0x180007750`
- `0x180007790`
- `0x1800077d0`
- `0x180007810`
- `0x180007850`

## callees

- `0x180004170`
- `0x180004228`
- `0x180004570`
- `0x180004788`
- `0x180004a1c`
- `0x180004a9c`
- `0x180008552`
- `0x180008580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004980`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004980`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004839`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000480d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000480d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004803`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004803`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000490f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000490f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800047d5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800047d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004975`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004975`

## string_xrefs

- `0x180004876`: `CLSID`
- `0x180004939`: `ThreadingModel`

## pseudocode

```c
int __fastcall ATL::CComModule::RegisterClassHelper(
        ATL::CComModule *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        UINT uID)
{
  int result; // eax
  unsigned __int16 *v9; // rsi
  int v10; // edi
  unsigned int v11; // r9d
  int v12; // ebx
  unsigned __int16 *v13; // r9
  const unsigned __int16 *v14; // r9
  WCHAR *v15; // r8
  const unsigned __int16 *v16; // rdx
  unsigned int v17; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v19; // [rsp+30h] [rbp-D0h]
  unsigned int *v20; // [rsp+38h] [rbp-C8h]
  HKEY hKey[3]; // [rsp+40h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[256]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+260h] [rbp+160h] BYREF

  LoadStringW(hModule, uID, Buffer, 256);
  memset_0(Filename, 0, 0x20Au);
  if ( GetModuleFileNameW(hModule, Filename, 0x104u) )
  {
    lpsz = 0;
    StringFromCLSID(a2, &lpsz);
    v9 = lpsz;
    v10 = ATL::AtlRegisterProgID(lpsz, a3, Buffer);
    if ( !v10 )
      v10 = ATL::AtlRegisterProgID(v9, a4, Buffer);
    v12 = 0;
    if ( !v10 )
    {
      memset(hKey, 0, sizeof(hKey));
      v12 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, L"CLSID", v11);
      if ( !v12 )
      {
        v12 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, hKey[0], v9, v13, v17, v18, v19, v20);
        if ( !v12 )
        {
          ATL::CRegKey::SetValue((ATL::CRegKey *)hKey, Buffer, 0);
          ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, L"ProgID", a3, 0);
          ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, L"VersionIndependentProgID", a4, 0);
          if ( !hModule || hModule == GetModuleHandleW(0) )
          {
            v14 = 0;
            v15 = Filename;
            v16 = L"LocalServer32";
          }
          else
          {
            ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, L"InprocServer32", Filename, 0);
            v14 = L"ThreadingModel";
            v15 = L"both";
            v16 = L"InprocServer32";
          }
          ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, v16, v15, v14);
        }
      }
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
    }
    CoTaskMemFree(lpsz);
    if ( v12 )
    {
      if ( v12 > 0 )
        return (unsigned __int16)v12 | 0x80070000;
      else
        return v12;
    }
    return v10;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180004788  mov     [rsp-8+arg_0], rbx
0x18000478d  push    rbp
0x18000478e  push    rsi
0x18000478f  push    rdi
0x180004790  push    r14
0x180004792  push    r15
0x180004794  lea     rbp, [rsp-380h]
0x18000479c  sub     rsp, 480h
0x1800047a3  mov     rax, cs:__security_cookie
0x1800047aa  xor     rax, rsp
0x1800047ad  mov     [rbp+3A0h+var_30], rax
0x1800047b4  mov     rcx, cs:hModule; hInstance
0x1800047bb  mov     r14, r9
0x1800047be  mov     r15, r8
0x1800047c1  mov     rbx, rdx
0x1800047c4  mov     edx, [rbp+3A0h+uID]; uID
0x1800047ca  lea     r8, [rsp+4A0h+Buffer]; lpBuffer
0x1800047cf  mov     r9d, 100h; cchBufferMax
0x1800047d5  call    cs:__imp_LoadStringW
0x1800047db  xor     edx, edx; Val
0x1800047dd  lea     rcx, [rbp+3A0h+Filename]; void *
0x1800047e4  mov     r8d, 20Ah; Size
0x1800047ea  call    memset_0
0x1800047ef  mov     rcx, cs:hModule; hModule
0x1800047f6  lea     rdx, [rbp+3A0h+Filename]; lpFilename
0x1800047fd  mov     r8d, 104h; nSize
0x180004803  call    cs:__imp_GetModuleFileNameW
0x180004809  test    eax, eax
0x18000480b  jnz     short loc_180004828
0x18000480d  call    cs:__imp_GetLastError
0x180004813  test    eax, eax
0x180004815  jle     loc_18000499B
0x18000481b  movzx   eax, ax
0x18000481e  or      eax, 80070000h
0x180004823  jmp     loc_18000499B
0x180004828  lea     rdx, [rsp+4A0h+lpsz]; lplpsz
0x18000482d  mov     [rsp+4A0h+lpsz], 0
0x180004836  mov     rcx, rbx; rclsid
0x180004839  call    cs:__imp_StringFromCLSID
0x18000483f  mov     rsi, [rsp+4A0h+lpsz]
0x180004844  lea     r8, [rsp+4A0h+Buffer]; unsigned __int16 *
0x180004849  mov     rcx, rsi; unsigned __int16 *
0x18000484c  mov     rdx, r15; unsigned __int16 *
0x18000484f  call    ATL__AtlRegisterProgID
0x180004854  mov     edi, eax
0x180004856  test    eax, eax
0x180004858  jnz     short loc_18000486C
0x18000485a  lea     r8, [rsp+4A0h+Buffer]; unsigned __int16 *
0x18000485f  mov     rdx, r14; unsigned __int16 *
0x180004862  mov     rcx, rsi; unsigned __int16 *
0x180004865  call    ATL__AtlRegisterProgID
0x18000486a  mov     edi, eax
0x18000486c  xor     ebx, ebx
0x18000486e  test    edi, edi
0x180004870  jnz     loc_18000497B
0x180004876  lea     r8, aClsid; "CLSID"
0x18000487d  mov     [rsp+4A0h+hKey], rbx
0x180004882  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x180004889  mov     [rsp+4A0h+var_458], rbx
0x18000488e  lea     rcx, [rsp+4A0h+hKey]; this
0x180004893  mov     [rsp+4A0h+var_450], rbx
0x180004898  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000489d  mov     ebx, eax
0x18000489f  test    eax, eax
0x1800048a1  jnz     loc_18000496B
0x1800048a7  mov     rdx, [rsp+4A0h+hKey]; HKEY
0x1800048ac  lea     rcx, [rsp+4A0h+hKey]; this
0x1800048b1  mov     r8, rsi; unsigned __int16 *
0x1800048b4  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800048b9  mov     ebx, eax
0x1800048bb  test    eax, eax
0x1800048bd  jnz     loc_18000496B
0x1800048c3  xor     r8d, r8d; unsigned __int16 *
0x1800048c6  lea     rdx, [rsp+4A0h+Buffer]; unsigned __int16 *
0x1800048cb  lea     rcx, [rsp+4A0h+hKey]; this
0x1800048d0  call    ?SetValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetValue(ushort const *,ushort const *)
0x1800048d5  xor     r9d, r9d; unsigned __int16 *
0x1800048d8  lea     rdx, aProgid; "ProgID"
0x1800048df  mov     r8, r15; unsigned __int16 *
0x1800048e2  lea     rcx, [rsp+4A0h+hKey]; this
0x1800048e7  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBG00@Z; ATL::CRegKey::SetKeyValue(ushort const *,ushort const *,ushort const *)
0x1800048ec  xor     r9d, r9d; unsigned __int16 *
0x1800048ef  lea     rdx, aVersionindepen; "VersionIndependentProgID"
0x1800048f6  mov     r8, r14; unsigned __int16 *
0x1800048f9  lea     rcx, [rsp+4A0h+hKey]; this
0x1800048fe  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBG00@Z; ATL::CRegKey::SetKeyValue(ushort const *,ushort const *,ushort const *)
0x180004903  cmp     cs:hModule, 0
0x18000490b  jz      short loc_180004950
0x18000490d  xor     ecx, ecx; lpModuleName
0x18000490f  call    cs:__imp_GetModuleHandleW
0x180004915  cmp     cs:hModule, rax
0x18000491c  jz      short loc_180004950
0x18000491e  xor     r9d, r9d; unsigned __int16 *
0x180004921  lea     r8, [rbp+3A0h+Filename]; unsigned __int16 *
0x180004928  lea     rdx, aInprocserver32; "InprocServer32"
0x18000492f  lea     rcx, [rsp+4A0h+hKey]; this
0x180004934  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBG00@Z; ATL::CRegKey::SetKeyValue(ushort const *,ushort const *,ushort const *)
0x180004939  lea     r9, aThreadingmodel; "ThreadingModel"
0x180004940  lea     r8, aBoth; "both"
0x180004947  lea     rdx, aInprocserver32; "InprocServer32"
0x18000494e  jmp     short loc_180004961
0x180004950  xor     r9d, r9d; unsigned __int16 *
0x180004953  lea     r8, [rbp+3A0h+Filename]; unsigned __int16 *
0x18000495a  lea     rdx, aLocalserver32; "LocalServer32"
0x180004961  lea     rcx, [rsp+4A0h+hKey]; this
0x180004966  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBG00@Z; ATL::CRegKey::SetKeyValue(ushort const *,ushort const *,ushort const *)
0x18000496b  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180004970  test    rcx, rcx
0x180004973  jz      short loc_18000497B
0x180004975  call    cs:__imp_RegCloseKey
0x18000497b  mov     rcx, [rsp+4A0h+lpsz]; pv
0x180004980  call    cs:__imp_CoTaskMemFree
0x180004986  test    ebx, ebx
0x180004988  jz      short loc_180004999
0x18000498a  jg      short loc_180004990
0x18000498c  mov     edi, ebx
0x18000498e  jmp     short loc_180004999
0x180004990  movzx   edi, bx
0x180004993  or      edi, 80070000h
0x180004999  mov     eax, edi
0x18000499b  mov     rcx, [rbp+3A0h+var_30]
0x1800049a2  xor     rcx, rsp; StackCookie
0x1800049a5  call    __security_check_cookie
0x1800049aa  mov     rbx, [rsp+4A0h+arg_0]
0x1800049b2  add     rsp, 480h
0x1800049b9  pop     r15
0x1800049bb  pop     r14
0x1800049bd  pop     rdi
0x1800049be  pop     rsi
0x1800049bf  pop     rbp
0x1800049c0  retn
```
