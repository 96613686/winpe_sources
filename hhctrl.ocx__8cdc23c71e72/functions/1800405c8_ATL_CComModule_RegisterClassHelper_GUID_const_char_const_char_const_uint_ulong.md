# ATL::CComModule::RegisterClassHelper(_GUID const &,char const *,char const *,uint,ulong)

- ea: `0x1800405c8`
- end: `0x1800408d8`
- name: `?RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBD1IK@Z`
- size: `784`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const char *, const char *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800415b0`
- `0x1800415f0`

## callees

- `0x1800020b8`
- `0x18003eaf0`
- `0x18003ee44`
- `0x18003ee80`
- `0x18003f9d4`
- `0x18003fa00`
- `0x180040090`
- `0x1800405c8`
- `0x180040bbc`
- `0x180040ebc`
- `0x180040f78`
- `0x180041628`
- `0x180075c90`
- `0x180075d50`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x1800407f5`
- `KERNEL32!GetModuleHandleA` at `0x1800407f5`
- `KERNEL32!GetModuleFileNameA` at `0x180040636`
- `KERNEL32!GetModuleFileNameA` at `0x180040636`
- `KERNEL32!WideCharToMultiByte` at `0x180040714`
- `KERNEL32!WideCharToMultiByte` at `0x180040714`
- `USER32!LoadStringA` at `0x18004061d`
- `USER32!LoadStringA` at `0x18004061d`
- `ole32!CoTaskMemFree` at `0x180040871`
- `ole32!CoTaskMemFree` at `0x180040899`
- `ole32!CoTaskMemFree` at `0x180040871`
- `ole32!CoTaskMemFree` at `0x180040899`
- `ole32!StringFromCLSID` at `0x180040669`
- `ole32!StringFromCLSID` at `0x180040669`

## string_xrefs

- `0x18004081b`: `ThreadingModel`
- `0x18004075c`: `CLSID`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::RegisterClassHelper(
        ATL::CComModule *this,
        const struct _GUID *a2,
        const char *a3,
        const char *a4)
{
  signed int ModuleFileNameA; // eax
  __int64 v8; // r15
  int Error; // ebx
  unsigned __int64 v10; // rdx
  LPOLESTR v11; // rbx
  __int64 v12; // rax
  int cbMultiByte; // r14d
  unsigned __int64 v14; // rax
  void *v15; // rsp
  CHAR *p_lpsz; // rsi
  unsigned int v17; // r9d
  int v18; // edi
  char *v19; // r9
  const char *v20; // r9
  char *v21; // r8
  const char *v22; // rdx
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-20h]
  unsigned int lpMultiByteStra; // [rsp+20h] [rbp-20h]
  struct _SECURITY_ATTRIBUTES *lpDefaultChar; // [rsp+30h] [rbp-10h]
  unsigned int *lpUsedDefaultChar; // [rsp+38h] [rbp-8h]
  LPOLESTR lpsz; // [rsp+40h] [rbp+0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp+8h] BYREF
  _QWORD v30[2]; // [rsp+60h] [rbp+20h] BYREF
  char v31; // [rsp+70h] [rbp+30h] BYREF
  CHAR Filename[271]; // [rsp+71h] [rbp+31h] BYREF
  CHAR Buffer[256]; // [rsp+180h] [rbp+140h] BYREF

  v30[0] = 0;
  LoadStringA(hInstance, 0, Buffer, 256);
  ModuleFileNameA = GetModuleFileNameA(hInstance, Filename, 0x104u);
  v8 = ModuleFileNameA;
  if ( ModuleFileNameA == 260 )
  {
    Error = -2147024785;
    goto LABEL_36;
  }
  if ( !ModuleFileNameA )
  {
    Error = ATL::AtlHresultFromLastError();
    goto LABEL_36;
  }
  lpsz = 0;
  Error = StringFromCLSID(a2, &lpsz);
  if ( Error < 0 )
    goto LABEL_36;
  v11 = lpsz;
  if ( !lpsz )
  {
LABEL_35:
    CoTaskMemFree(v11);
    Error = -2147024882;
    goto LABEL_36;
  }
  v12 = -1;
  do
    ++v12;
  while ( lpsz[v12] );
  cbMultiByte = 2 * v12 + 2;
  if ( cbMultiByte <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)cbMultiByte, v10) )
  {
    v14 = cbMultiByte + 15LL;
    if ( v14 < cbMultiByte )
      v14 = 0xFFFFFFFFFFFFFF0LL;
    v15 = alloca(v14 & 0xFFFFFFFFFFFFFFF0uLL);
    p_lpsz = (CHAR *)&lpsz;
  }
  else
  {
    p_lpsz = (CHAR *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                       v30,
                       cbMultiByte);
  }
  if ( !p_lpsz || (*p_lpsz = 0, !WideCharToMultiByte(0, 0, v11, -1, p_lpsz, cbMultiByte, 0, 0)) )
  {
    v11 = lpsz;
    goto LABEL_35;
  }
  Error = ATL::CComModule::RegisterProgID(p_lpsz, a3, Buffer);
  if ( !Error )
    Error = ATL::CComModule::RegisterProgID(p_lpsz, a4, Buffer);
  v18 = 0;
  if ( !Error )
  {
    memset(hKey, 0, sizeof(hKey));
    v18 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, "CLSID", v17, lpMultiByteStr);
    if ( !v18 )
    {
      v18 = ATL::CRegKey::Create(
              (ATL::CRegKey *)hKey,
              hKey[0],
              p_lpsz,
              v19,
              lpMultiByteStra,
              0x2001Fu,
              lpDefaultChar,
              lpUsedDefaultChar);
      if ( !v18 )
      {
        ATL::CRegKey::SetValue((ATL::CRegKey *)hKey, Buffer, 0);
        ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, "ProgID", a3, 0);
        ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, "VersionIndependentProgID", a4, 0);
        if ( !hInstance || hInstance == GetModuleHandleA(0) )
        {
          v31 = 34;
          Filename[v8] = 34;
          if ( (unsigned __int64)(v8 + 2) >= 0x106 )
            _report_rangecheckfailure();
          Filename[v8 + 1] = 0;
          v21 = &v31;
          v20 = 0;
          v22 = "LocalServer32";
        }
        else
        {
          ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, "InprocServer32", Filename, 0);
          v20 = "ThreadingModel";
          v21 = "both";
          v22 = "InprocServer32";
        }
        ATL::CRegKey::SetKeyValue((ATL::CRegKey *)hKey, v22, v21, v20);
      }
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  }
  CoTaskMemFree(lpsz);
  if ( v18 )
  {
    if ( v18 > 0 )
      Error = (unsigned __int16)v18 | 0x80070000;
    else
      Error = v18;
  }
LABEL_36:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(v30);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800405c8  push    rbp
0x1800405ca  push    rsi
0x1800405cb  push    rdi
0x1800405cc  push    r12
0x1800405ce  push    r13
0x1800405d0  push    r14
0x1800405d2  push    r15
0x1800405d4  sub     rsp, 290h
0x1800405db  lea     rbp, [rsp+40h]
0x1800405e0  mov     [rbp+280h+arg_0], rbx
0x1800405e7  mov     rax, cs:__security_cookie
0x1800405ee  xor     rax, rbp
0x1800405f1  mov     [rbp+280h+var_40], rax
0x1800405f8  mov     rcx, cs:hInstance; hInstance
0x1800405ff  mov     r13, r9
0x180040602  mov     r12, r8
0x180040605  mov     rbx, rdx
0x180040608  xor     esi, esi
0x18004060a  lea     r8, [rbp+280h+Buffer]; lpBuffer
0x180040611  mov     r9d, 100h; cchBufferMax
0x180040617  mov     [rbp+280h+var_260], rsi
0x18004061b  xor     edx, edx; uID
0x18004061d  call    cs:__imp_LoadStringA
0x180040623  mov     rcx, cs:hInstance; hModule
0x18004062a  lea     rdx, [rbp+280h+Filename]; lpFilename
0x18004062e  mov     edi, 104h
0x180040633  mov     r8d, edi; nSize
0x180040636  call    cs:__imp_GetModuleFileNameA
0x18004063c  movsxd  r15, eax
0x18004063f  cmp     r15d, edi
0x180040642  jnz     short loc_18004064E
0x180040644  mov     ebx, 8007006Fh
0x180040649  jmp     loc_1800408A4
0x18004064e  test    eax, eax
0x180040650  jnz     short loc_18004065E
0x180040652  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180040657  mov     ebx, eax
0x180040659  jmp     loc_1800408A4
0x18004065e  lea     rdx, [rbp+280h+lpsz]; lplpsz
0x180040662  mov     [rbp+280h+lpsz], rsi
0x180040666  mov     rcx, rbx; rclsid
0x180040669  call    cs:__imp_StringFromCLSID
0x18004066f  mov     ebx, eax
0x180040671  test    eax, eax
0x180040673  js      loc_1800408A4
0x180040679  mov     rbx, [rbp+280h+lpsz]
0x18004067d  test    rbx, rbx
0x180040680  jz      loc_180040896
0x180040686  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004068a  inc     rax
0x18004068d  cmp     [rbx+rax*2], si
0x180040691  jnz     short loc_18004068A
0x180040693  lea     r14d, ds:2[rax*2]
0x18004069b  movsxd  rdi, r14d
0x18004069e  cmp     r14d, 400h
0x1800406a5  jg      short loc_1800406D9
0x1800406a7  mov     rcx, rdi; this
0x1800406aa  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x1800406af  test    al, al
0x1800406b1  jz      short loc_1800406D9
0x1800406b3  lea     rax, [rdi+0Fh]
0x1800406b7  cmp     rax, rdi
0x1800406ba  ja      short loc_1800406C6
0x1800406bc  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800406c6  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800406ca  call    _alloca_probe
0x1800406cf  sub     rsp, rax
0x1800406d2  lea     rsi, [rsp+2C0h+lpsz]
0x1800406d7  jmp     short loc_1800406E8
0x1800406d9  mov     rdx, rdi
0x1800406dc  lea     rcx, [rbp+280h+var_260]
0x1800406e0  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x1800406e5  mov     rsi, rax
0x1800406e8  xor     eax, eax
0x1800406ea  test    rsi, rsi
0x1800406ed  jz      loc_180040892
0x1800406f3  mov     [rsp+2C0h+lpUsedDefaultChar], rax; unsigned int *
0x1800406f8  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800406fc  mov     [rsp+2C0h+lpDefaultChar], rax; struct _SECURITY_ATTRIBUTES *
0x180040701  mov     r8, rbx; lpWideCharStr
0x180040704  mov     [rsp+2C0h+cbMultiByte], r14d; cbMultiByte
0x180040709  xor     edx, edx; dwFlags
0x18004070b  xor     ecx, ecx; CodePage
0x18004070d  mov     [rsp+2C0h+lpMultiByteStr], rsi; unsigned int
0x180040712  mov     [rsi], al
0x180040714  call    cs:__imp_WideCharToMultiByte
0x18004071a  xor     r14d, r14d
0x18004071d  test    eax, eax
0x18004071f  jz      loc_180040892
0x180040725  lea     r8, [rbp+280h+Buffer]; char *
0x18004072c  mov     rdx, r12; lpSubKey
0x18004072f  mov     rcx, rsi; char *
0x180040732  call    ?RegisterProgID@CComModule@ATL@@SAJPEBD00@Z; ATL::CComModule::RegisterProgID(char const *,char const *,char const *)
0x180040737  mov     ebx, eax
0x180040739  test    eax, eax
0x18004073b  jnz     short loc_180040751
0x18004073d  lea     r8, [rbp+280h+Buffer]; char *
0x180040744  mov     rdx, r13; lpSubKey
0x180040747  mov     rcx, rsi; char *
0x18004074a  call    ?RegisterProgID@CComModule@ATL@@SAJPEBD00@Z; ATL::CComModule::RegisterProgID(char const *,char const *,char const *)
0x18004074f  mov     ebx, eax
0x180040751  mov     edi, r14d
0x180040754  test    ebx, ebx
0x180040756  jnz     loc_18004086D
0x18004075c  lea     r8, aClsid; "CLSID"
0x180040763  mov     [rbp+280h+hKey], r14
0x180040767  mov     rdx, 0FFFFFFFF80000000h; hKey
0x18004076e  mov     [rbp+280h+var_270], r14
0x180040772  lea     rcx, [rbp+280h+hKey]; this
0x180040776  mov     [rbp+280h+var_268], r14
0x18004077a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBDKK@Z; ATL::CRegKey::Open(HKEY__ *,char const *,ulong,ulong)
0x18004077f  mov     edi, eax
0x180040781  test    eax, eax
0x180040783  jnz     loc_180040864
0x180040789  mov     rdx, [rbp+280h+hKey]; hKey
0x18004078d  lea     rcx, [rbp+280h+hKey]; this
0x180040791  mov     r8, rsi; lpSubKey
0x180040794  mov     [rsp+2C0h+cbMultiByte], 2001Fh; unsigned int
0x18004079c  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBDPEADKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,char const *,char *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800407a1  mov     edi, eax
0x1800407a3  test    eax, eax
0x1800407a5  jnz     loc_180040864
0x1800407ab  xor     r8d, r8d; char *
0x1800407ae  lea     rdx, [rbp+280h+Buffer]; char *
0x1800407b5  lea     rcx, [rbp+280h+hKey]; this
0x1800407b9  call    ?SetValue@CRegKey@ATL@@QEAAJPEBD0@Z; ATL::CRegKey::SetValue(char const *,char const *)
0x1800407be  xor     r9d, r9d; char *
0x1800407c1  lea     rdx, ?szProgID@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBD1IK@Z@4QBDB; "ProgID"
0x1800407c8  mov     r8, r12; char *
0x1800407cb  lea     rcx, [rbp+280h+hKey]; this
0x1800407cf  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBD00@Z; ATL::CRegKey::SetKeyValue(char const *,char const *,char const *)
0x1800407d4  xor     r9d, r9d; char *
0x1800407d7  lea     rdx, ?szVIProgID@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBD1IK@Z@4QBDB; "VersionIndependentProgID"
0x1800407de  mov     r8, r13; char *
0x1800407e1  lea     rcx, [rbp+280h+hKey]; this
0x1800407e5  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBD00@Z; ATL::CRegKey::SetKeyValue(char const *,char const *,char const *)
0x1800407ea  cmp     cs:hInstance, r14
0x1800407f1  jz      short loc_180040832
0x1800407f3  xor     ecx, ecx; lpModuleName
0x1800407f5  call    cs:__imp_GetModuleHandleA
0x1800407fb  cmp     cs:hInstance, rax
0x180040802  jz      short loc_180040832
0x180040804  xor     r9d, r9d; char *
0x180040807  lea     r8, [rbp+280h+Filename]; char *
0x18004080b  lea     rdx, ?szIPS32@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBD1IK@Z@4QBDB; "InprocServer32"
0x180040812  lea     rcx, [rbp+280h+hKey]; this
0x180040816  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBD00@Z; ATL::CRegKey::SetKeyValue(char const *,char const *,char const *)
0x18004081b  lea     r9, ?szThreadingModel@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBD1IK@Z@4QBDB; "ThreadingModel"
0x180040822  lea     r8, ?szBoth@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBD1IK@Z@4QBDB; "both"
0x180040829  lea     rdx, ?szIPS32@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBD1IK@Z@4QBDB; "InprocServer32"
0x180040830  jmp     short loc_18004085B
0x180040832  lea     rax, [r15+2]
0x180040836  mov     [rbp+280h+var_250], 22h ; '"'
0x18004083a  mov     [rbp+r15+280h+Filename], 22h ; '"'
0x180040840  cmp     rax, 106h
0x180040846  jnb     short loc_180040881
0x180040848  mov     [rbp+rax+280h+var_250], r14b
0x18004084d  lea     r8, [rbp+280h+var_250]; char *
0x180040851  xor     r9d, r9d; char *
0x180040854  lea     rdx, ?szLS32@?1??RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBD1IK@Z@4QBDB; "LocalServer32"
0x18004085b  lea     rcx, [rbp+280h+hKey]; this
0x18004085f  call    ?SetKeyValue@CRegKey@ATL@@QEAAJPEBD00@Z; ATL::CRegKey::SetKeyValue(char const *,char const *,char const *)
0x180040864  lea     rcx, [rbp+280h+hKey]; this
0x180040868  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18004086d  mov     rcx, [rbp+280h+lpsz]; pv
0x180040871  call    cs:__imp_CoTaskMemFree
0x180040877  test    edi, edi
0x180040879  jz      short loc_1800408A4
0x18004087b  jg      short loc_180040887
0x18004087d  mov     ebx, edi
0x18004087f  jmp     short loc_1800408A4
0x180040881  call    __report_rangecheckfailure
0x180040887  movzx   ebx, di
0x18004088a  or      ebx, 80070000h
0x180040890  jmp     short loc_1800408A4
0x180040892  mov     rbx, [rbp+280h+lpsz]
0x180040896  mov     rcx, rbx; pv
0x180040899  call    cs:__imp_CoTaskMemFree
0x18004089f  mov     ebx, 8007000Eh
0x1800408a4  lea     rcx, [rbp+280h+var_260]
0x1800408a8  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800408ad  mov     eax, ebx
0x1800408af  mov     rcx, [rbp+280h+var_40]
0x1800408b6  xor     rcx, rbp; StackCookie
0x1800408b9  call    __security_check_cookie
0x1800408be  mov     rbx, [rbp+280h+arg_0]
0x1800408c5  lea     rsp, [rbp+250h]
0x1800408cc  pop     r15
0x1800408ce  pop     r14
0x1800408d0  pop     r13
0x1800408d2  pop     r12
0x1800408d4  pop     rdi
0x1800408d5  pop     rsi
0x1800408d6  pop     rbp
0x1800408d7  retn
```
