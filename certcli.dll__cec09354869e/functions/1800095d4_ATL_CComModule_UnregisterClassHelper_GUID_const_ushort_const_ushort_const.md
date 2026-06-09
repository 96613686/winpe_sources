# ATL::CComModule::UnregisterClassHelper(_GUID const &,ushort const *,ushort const *)

- ea: `0x1800095d4`
- end: `0x1800096e8`
- name: `?UnregisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1@Z`
- size: `276`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009828`

## callees

- `0x180004e8c`
- `0x18000602c`
- `0x1800063c4`
- `0x180007da0`
- `0x180008198`
- `0x1800095d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096bc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180009667`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180009667`

## string_xrefs

- `0x18000967d`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComModule::UnregisterClassHelper(
        OLECHAR *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int v6; // eax
  HRESULT v7; // ebx
  const unsigned __int16 *v8; // rdi
  unsigned int v9; // ecx
  HKEY hKey[4]; // [rsp+20h] [rbp-20h] BYREF
  LPOLESTR lpsz; // [rsp+60h] [rbp+20h] BYREF
  _QWORD *v13; // [rsp+70h] [rbp+30h] BYREF

  lpsz = this;
  v13 = 0;
  hKey[1] = 0;
  hKey[2] = 0;
  hKey[0] = HKEY_CLASSES_ROOT;
  if ( a3 && *a3 && ((v6 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, a3), (v6 & 0xFFFFFFFC) != 0) || v6 == 1)
    || a4 && *a4 && ((v6 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, a4), (v6 & 0xFFFFFFFC) != 0) || v6 == 1) )
  {
    hKey[0] = 0;
    v7 = ATL::AtlHresultFromWin32(v6);
  }
  else
  {
    lpsz = 0;
    v7 = StringFromCLSID(a2, &lpsz);
    if ( v7 >= 0 )
    {
      v8 = lpsz;
      v9 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, hKey[0], L"CLSID", 0x2001Fu);
      if ( (v9 || (v9 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, v8)) != 0) && v9 - 2 > 1 )
        v7 = ATL::AtlHresultFromWin32(v9);
      CoTaskMemFree(lpsz);
    }
    hKey[0] = 0;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800095d4  mov     [rsp-18h+arg_8], rbx
0x1800095d9  mov     [rsp-18h+lpsz], rcx
0x1800095de  push    rbp
0x1800095df  push    rsi
0x1800095e0  push    rdi
0x1800095e1  mov     rbp, rsp
0x1800095e4  sub     rsp, 40h
0x1800095e8  mov     rbx, r9
0x1800095eb  mov     rdi, rdx
0x1800095ee  xor     esi, esi
0x1800095f0  mov     [rbp+arg_10], rsi
0x1800095f4  mov     [rbp+hKey], rsi
0x1800095f8  mov     [rbp+var_18], rsi
0x1800095fc  mov     [rbp+var_10], rsi
0x180009600  mov     [rbp+hKey], 0FFFFFFFF80000000h
0x180009608  test    r8, r8
0x18000960b  jz      short loc_18000962B
0x18000960d  cmp     [r8], si
0x180009611  jz      short loc_18000962B
0x180009613  mov     rdx, r8; unsigned __int16 *
0x180009616  lea     rcx, [rbp+hKey]; this
0x18000961a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000961f  test    eax, 0FFFFFFFCh
0x180009624  jnz     short loc_18000964D
0x180009626  cmp     eax, 1
0x180009629  jz      short loc_18000964D
0x18000962b  test    rbx, rbx
0x18000962e  jz      short loc_18000965C
0x180009630  cmp     [rbx], si
0x180009633  jz      short loc_18000965C
0x180009635  mov     rdx, rbx; unsigned __int16 *
0x180009638  lea     rcx, [rbp+hKey]; this
0x18000963c  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180009641  test    eax, 0FFFFFFFCh
0x180009646  jnz     short loc_18000964D
0x180009648  cmp     eax, 1
0x18000964b  jnz     short loc_18000965C
0x18000964d  mov     [rbp+hKey], rsi
0x180009651  mov     ecx, eax; unsigned int
0x180009653  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180009658  mov     ebx, eax
0x18000965a  jmp     short loc_1800096C6
0x18000965c  mov     [rbp+lpsz], rsi
0x180009660  lea     rdx, [rbp+lpsz]; lplpsz
0x180009664  mov     rcx, rdi; rclsid
0x180009667  call    cs:__imp_StringFromCLSID
0x18000966d  mov     ebx, eax
0x18000966f  test    eax, eax
0x180009671  js      short loc_1800096C2
0x180009673  mov     rdi, [rbp+lpsz]
0x180009677  mov     r9d, 2001Fh; unsigned int
0x18000967d  lea     r8, aClsid; "CLSID"
0x180009684  mov     rdx, [rbp+hKey]; hKey
0x180009688  lea     rcx, [rbp+hKey]; this
0x18000968c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180009691  mov     ecx, eax
0x180009693  test    eax, eax
0x180009695  jnz     short loc_1800096A9
0x180009697  mov     rdx, rdi; unsigned __int16 *
0x18000969a  lea     rcx, [rbp+hKey]; this
0x18000969e  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800096a3  mov     ecx, eax; unsigned int
0x1800096a5  test    eax, eax
0x1800096a7  jz      short loc_1800096B8
0x1800096a9  lea     eax, [rcx-2]
0x1800096ac  cmp     eax, 1
0x1800096af  jbe     short loc_1800096B8
0x1800096b1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800096b6  mov     ebx, eax
0x1800096b8  mov     rcx, [rbp+lpsz]; pv
0x1800096bc  call    cs:__imp_CoTaskMemFree
0x1800096c2  mov     [rbp+hKey], rsi
0x1800096c6  lea     rcx, [rbp+hKey]; this
0x1800096ca  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800096cf  nop
0x1800096d0  lea     rcx, [rbp+arg_10]
0x1800096d4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800096d9  mov     eax, ebx
0x1800096db  mov     rbx, [rsp+40h+arg_8]
0x1800096e0  add     rsp, 40h
0x1800096e4  pop     rdi
0x1800096e5  pop     rsi
0x1800096e6  pop     rbp
0x1800096e7  retn
```
