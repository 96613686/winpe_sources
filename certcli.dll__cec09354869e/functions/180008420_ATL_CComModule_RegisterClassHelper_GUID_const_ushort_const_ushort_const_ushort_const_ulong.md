# ATL::CComModule::RegisterClassHelper(_GUID const &,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180008420`
- end: `0x1800086e8`
- name: `?RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG11K@Z`
- size: `712`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009828`

## callees

- `0x180002078`
- `0x180004e8c`
- `0x180006008`
- `0x18000602c`
- `0x1800061ec`
- `0x1800063c4`
- `0x1800063f0`
- `0x180007da0`
- `0x180008420`
- `0x18000889c`
- `0x18000927c`
- `0x1800092fc`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180008495`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180008495`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008600`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008600`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008699`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008699`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800084d6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800084d6`

## string_xrefs

- `0x18000862e`: `ThreadingModel`
- `0x180008549`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComModule::RegisterClassHelper(
        ATL::CComModule *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  const unsigned __int16 *v8; // r12
  DWORD ModuleFileNameW; // r13d
  HRESULT Error; // eax
  unsigned int v11; // ebx
  const unsigned __int16 *v13; // r15
  unsigned int v14; // edi
  unsigned int v15; // ebx
  unsigned __int16 *v16; // r9
  unsigned int v17; // r9d
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // r8
  const unsigned __int16 *v20; // rdx
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  HKEY hKey[3]; // [rsp+40h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v25; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Filename[263]; // [rsp+72h] [rbp-8Eh] BYREF

  v24[0] = 0;
  if ( a3 )
  {
    if ( a4 )
      goto LABEL_3;
LABEL_8:
    ATL::AtlThrowImpl(-2147467259);
  }
  if ( a4 )
    goto LABEL_8;
LABEL_3:
  v8 = &psz;
  if ( a5 )
    v8 = a5;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
    goto LABEL_12;
  }
  if ( ModuleFileNameW == 260 )
  {
    v11 = -2147024774;
LABEL_13:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v24);
    return v11;
  }
  lpsz = 0;
  Error = StringFromCLSID(a2, &lpsz);
  if ( Error < 0 )
  {
LABEL_12:
    v11 = Error;
    goto LABEL_13;
  }
  v13 = lpsz;
  if ( !a3 || (v14 = ATL::CComModule::RegisterProgID(lpsz, a3, v8)) == 0 )
  {
    if ( a4 )
      v14 = ATL::CComModule::RegisterProgID(v13, a4, v8);
    else
      v14 = 0;
  }
  v15 = 0;
  if ( !v14 )
  {
    memset(hKey, 0, sizeof(hKey));
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, L"CLSID", 0x2001Fu);
    if ( v15 )
      goto LABEL_34;
    v15 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, hKey[0], v13, v16, v21, 0x2001Fu);
    if ( v15 )
      goto LABEL_34;
    v15 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)hKey, 0, v8, v17);
    if ( v15 )
      goto LABEL_34;
    if ( a3 )
    {
      v15 = ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, L"ProgID", a3, 0);
      if ( v15 )
        goto LABEL_34;
    }
    if ( a4 )
    {
      v15 = ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, L"VersionIndependentProgID", a4, 0);
      if ( v15 )
        goto LABEL_34;
    }
    if ( !hModule || hModule == GetModuleHandleW(0) )
    {
      v25 = 34;
      Filename[ModuleFileNameW] = 34;
      if ( 2 * (unsigned __int64)(ModuleFileNameW + 2) >= 0x20C )
        _report_rangecheckfailure();
      Filename[ModuleFileNameW + 1] = 0;
      v18 = 0;
      v19 = &v25;
      v20 = L"LocalServer32";
    }
    else
    {
      v15 = ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, L"InprocServer32", Filename, 0);
      if ( v15 )
      {
LABEL_34:
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        goto LABEL_35;
      }
      v18 = L"ThreadingModel";
      v19 = L"both";
      v20 = L"InprocServer32";
    }
    v15 = ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, v20, v19, v18);
    goto LABEL_34;
  }
LABEL_35:
  CoTaskMemFree(lpsz);
  if ( v15 )
    v14 = ATL::AtlHresultFromWin32(v15);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v24);
  return v14;
}

```

## disassembly

```asm
0x180008420  mov     [rsp-8+arg_0], rbx
0x180008425  push    rbp
0x180008426  push    rsi
0x180008427  push    rdi
0x180008428  push    r12
0x18000842a  push    r13
0x18000842c  push    r14
0x18000842e  push    r15
0x180008430  lea     rbp, [rsp-190h]
0x180008438  sub     rsp, 290h
0x18000843f  mov     rax, cs:__security_cookie
0x180008446  xor     rax, rsp
0x180008449  mov     [rbp+1C0h+var_40], rax
0x180008450  mov     rsi, r9
0x180008453  mov     r14, r8
0x180008456  mov     rbx, rdx
0x180008459  mov     rax, [rbp+1C0h+arg_20]
0x180008460  mov     [rsp+2C0h+var_260], 0
0x180008469  test    r8, r8
0x18000846c  jz      short loc_1800084A9
0x18000846e  test    r9, r9
0x180008471  jz      short loc_1800084AE
0x180008473  lea     r12, psz
0x18000847a  test    rax, rax
0x18000847d  cmovnz  r12, rax
0x180008481  mov     edi, 104h
0x180008486  mov     r8d, edi; nSize
0x180008489  lea     rdx, [rsp+2C0h+Filename]; lpFilename
0x18000848e  mov     rcx, cs:hModule; hModule
0x180008495  call    cs:__imp_GetModuleFileNameW
0x18000849b  mov     r13d, eax
0x18000849e  test    eax, eax
0x1800084a0  jnz     short loc_1800084B9
0x1800084a2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800084a7  jmp     short loc_1800084E0
0x1800084a9  test    rsi, rsi
0x1800084ac  jz      short loc_180008473
0x1800084ae  mov     ecx, 80004005h; int
0x1800084b3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800084b9  cmp     r13d, edi
0x1800084bc  jnz     short loc_1800084C5
0x1800084be  mov     ebx, 8007007Ah
0x1800084c3  jmp     short loc_1800084E2
0x1800084c5  mov     [rsp+2C0h+lpsz], 0
0x1800084ce  lea     rdx, [rsp+2C0h+lpsz]; lplpsz
0x1800084d3  mov     rcx, rbx; rclsid
0x1800084d6  call    cs:__imp_StringFromCLSID
0x1800084dc  test    eax, eax
0x1800084de  jns     short loc_1800084F3
0x1800084e0  mov     ebx, eax
0x1800084e2  lea     rcx, [rsp+2C0h+var_260]
0x1800084e7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800084ec  mov     eax, ebx
0x1800084ee  jmp     loc_1800086B8
0x1800084f3  mov     r15, [rsp+2C0h+lpsz]
0x1800084f8  test    r14, r14
0x1800084fb  jz      short loc_180008511
0x1800084fd  mov     r8, r12; unsigned __int16 *
0x180008500  mov     rdx, r14; lpSubKey
0x180008503  mov     rcx, r15; unsigned __int16 *
0x180008506  call    ?RegisterProgID@CComModule@ATL@@SAJPEBG00@Z; ATL::CComModule::RegisterProgID(ushort const *,ushort const *,ushort const *)
0x18000850b  mov     edi, eax
0x18000850d  test    eax, eax
0x18000850f  jnz     short loc_18000852A
0x180008511  test    rsi, rsi
0x180008514  jz      short loc_180008528
0x180008516  mov     r8, r12; unsigned __int16 *
0x180008519  mov     rdx, rsi; lpSubKey
0x18000851c  mov     rcx, r15; unsigned __int16 *
0x18000851f  call    ?RegisterProgID@CComModule@ATL@@SAJPEBG00@Z; ATL::CComModule::RegisterProgID(ushort const *,ushort const *,ushort const *)
0x180008524  mov     edi, eax
0x180008526  jmp     short loc_18000852A
0x180008528  xor     edi, edi
0x18000852a  xor     ebx, ebx
0x18000852c  test    edi, edi
0x18000852e  jnz     loc_180008694
0x180008534  mov     [rsp+2C0h+hKey], rbx
0x180008539  mov     [rsp+2C0h+var_278], rbx
0x18000853e  mov     [rsp+2C0h+var_270], rbx
0x180008543  mov     r9d, 2001Fh; unsigned int
0x180008549  lea     r8, aClsid; "CLSID"
0x180008550  mov     rdx, 0FFFFFFFF80000000h; hKey
0x180008557  lea     rcx, [rsp+2C0h+hKey]; this
0x18000855c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008561  mov     ebx, eax
0x180008563  test    eax, eax
0x180008565  jnz     loc_18000868A
0x18000856b  mov     [rsp+2C0h+var_298], 2001Fh; unsigned int
0x180008573  mov     r8, r15; lpSubKey
0x180008576  mov     rdx, [rsp+2C0h+hKey]; hKey
0x18000857b  lea     rcx, [rsp+2C0h+hKey]; this
0x180008580  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180008585  mov     ebx, eax
0x180008587  test    eax, eax
0x180008589  jnz     loc_18000868A
0x18000858f  mov     r8, r12; unsigned __int16 *
0x180008592  xor     edx, edx; unsigned __int16 *
0x180008594  lea     rcx, [rsp+2C0h+hKey]; this
0x180008599  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18000859e  mov     ebx, eax
0x1800085a0  test    eax, eax
0x1800085a2  jnz     loc_18000868A
0x1800085a8  test    r14, r14
0x1800085ab  jz      short loc_1800085CE
0x1800085ad  xor     r9d, r9d; unsigned __int16 *
0x1800085b0  mov     r8, r14; unsigned __int16 *
0x1800085b3  lea     rdx, ?szProgID@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG11K@Z@4QBGB; "ProgID"
0x1800085ba  lea     rcx, [rsp+2C0h+hKey]; this
0x1800085bf  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBG00@Z; ATL::CRegKey::SetKeyValue(ushort const *,ushort const *,ushort const *)
0x1800085c4  mov     ebx, eax
0x1800085c6  test    eax, eax
0x1800085c8  jnz     loc_18000868A
0x1800085ce  test    rsi, rsi
0x1800085d1  jz      short loc_1800085F4
0x1800085d3  xor     r9d, r9d; unsigned __int16 *
0x1800085d6  mov     r8, rsi; unsigned __int16 *
0x1800085d9  lea     rdx, ?szVIProgID@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG11K@Z@4QBGB; "VersionIndependentProgID"
0x1800085e0  lea     rcx, [rsp+2C0h+hKey]; this
0x1800085e5  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBG00@Z; ATL::CRegKey::SetKeyValue(ushort const *,ushort const *,ushort const *)
0x1800085ea  mov     ebx, eax
0x1800085ec  test    eax, eax
0x1800085ee  jnz     loc_18000868A
0x1800085f4  cmp     cs:hModule, 0
0x1800085fc  jz      short loc_180008645
0x1800085fe  xor     ecx, ecx; lpModuleName
0x180008600  call    cs:__imp_GetModuleHandleW
0x180008606  cmp     cs:hModule, rax
0x18000860d  jz      short loc_180008645
0x18000860f  xor     r9d, r9d; unsigned __int16 *
0x180008612  lea     r8, [rsp+2C0h+Filename]; unsigned __int16 *
0x180008617  lea     rdx, ?szIPS32@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG11K@Z@4QBGB; "InprocServer32"
0x18000861e  lea     rcx, [rsp+2C0h+hKey]; this
0x180008623  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBG00@Z; ATL::CRegKey::SetKeyValue(ushort const *,ushort const *,ushort const *)
0x180008628  mov     ebx, eax
0x18000862a  test    eax, eax
0x18000862c  jnz     short loc_18000868A
0x18000862e  lea     r9, ?szThreadingModel@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG11K@Z@4QBGB; "ThreadingModel"
0x180008635  lea     r8, ?szBoth@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG11K@Z@4QBGB; "both"
0x18000863c  lea     rdx, ?szIPS32@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG11K@Z@4QBGB; "InprocServer32"
0x180008643  jmp     short loc_18000867E
0x180008645  mov     edx, 22h ; '"'
0x18000864a  mov     [rsp+2C0h+var_250], dx
0x18000864f  lea     eax, [r13+1]
0x180008653  mov     [rsp+rax*2+2C0h+var_250], dx
0x180008658  lea     ecx, [r13+2]
0x18000865c  add     rcx, rcx
0x18000865f  cmp     rcx, 20Ch
0x180008666  jnb     short loc_1800086E2
0x180008668  xor     eax, eax
0x18000866a  mov     [rsp+rcx+2C0h+var_250], ax
0x18000866f  xor     r9d, r9d; unsigned __int16 *
0x180008672  lea     r8, [rsp+2C0h+var_250]; unsigned __int16 *
0x180008677  lea     rdx, ?szLS32@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG11K@Z@4QBGB; "LocalServer32"
0x18000867e  lea     rcx, [rsp+2C0h+hKey]; this
0x180008683  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBG00@Z; ATL::CRegKey::SetKeyValue(ushort const *,ushort const *,ushort const *)
0x180008688  mov     ebx, eax
0x18000868a  lea     rcx, [rsp+2C0h+hKey]; this
0x18000868f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008694  mov     rcx, [rsp+2C0h+lpsz]; pv
0x180008699  call    cs:__imp_CoTaskMemFree
0x18000869f  test    ebx, ebx
0x1800086a1  jz      short loc_1800086AC
0x1800086a3  mov     ecx, ebx; unsigned int
0x1800086a5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800086aa  mov     edi, eax
0x1800086ac  lea     rcx, [rsp+2C0h+var_260]
0x1800086b1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800086b6  mov     eax, edi
0x1800086b8  mov     rcx, [rbp+1C0h+var_40]
0x1800086bf  xor     rcx, rsp; StackCookie
0x1800086c2  call    __security_check_cookie
0x1800086c7  mov     rbx, [rsp+2C0h+arg_0]
0x1800086cf  add     rsp, 290h
0x1800086d6  pop     r15
0x1800086d8  pop     r14
0x1800086da  pop     r13
0x1800086dc  pop     r12
0x1800086de  pop     rdi
0x1800086df  pop     rsi
0x1800086e0  pop     rbp
0x1800086e1  retn
0x1800086e2  call    __report_rangecheckfailure
```
