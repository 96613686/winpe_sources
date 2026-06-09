# ATL::CComModule::UnregisterClassHelper(_GUID const &,char const *,char const *)

- ea: `0x18004132c`
- end: `0x1800414de`
- name: `?UnregisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBD1@Z`
- size: `434`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const char *, const char *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800415b0`
- `0x1800415f0`

## callees

- `0x18003eaf0`
- `0x18003ee44`
- `0x18003f9d4`
- `0x180040090`
- `0x180040308`
- `0x18004132c`
- `0x180041628`
- `0x180075c90`
- `0x180075d50`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x180041379`
- `KERNEL32!lstrcmpiA` at `0x18004139e`
- `KERNEL32!lstrcmpiA` at `0x180041379`
- `KERNEL32!lstrcmpiA` at `0x18004139e`
- `KERNEL32!WideCharToMultiByte` at `0x180041463`
- `KERNEL32!WideCharToMultiByte` at `0x180041463`
- `ole32!CoTaskMemFree` at `0x180041495`
- `ole32!CoTaskMemFree` at `0x1800414a7`
- `ole32!CoTaskMemFree` at `0x180041495`
- `ole32!CoTaskMemFree` at `0x1800414a7`
- `ole32!StringFromCLSID` at `0x1800413bf`
- `ole32!StringFromCLSID` at `0x1800413bf`

## string_xrefs

- `0x18004146d`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComModule::UnregisterClassHelper(
        ATL::CComModule *this,
        const struct _GUID *a2,
        const char *a3,
        const char *a4)
{
  unsigned __int64 v7; // rdx
  HRESULT v8; // ebx
  WCHAR *v9; // rbx
  __int64 v10; // rax
  int cbMultiByte; // esi
  unsigned __int64 v12; // rax
  void *v13; // rsp
  char *p_lpsz; // rdi
  unsigned int v15; // r9d
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-20h]
  LPOLESTR lpsz; // [rsp+40h] [rbp+0h] BYREF
  __int64 v19; // [rsp+48h] [rbp+8h] BYREF
  HKEY hKey[3]; // [rsp+50h] [rbp+10h] BYREF

  v19 = 0;
  hKey[1] = 0;
  hKey[2] = 0;
  hKey[0] = HKEY_CLASSES_ROOT;
  if ( a3 && lstrcmpiA(a3, Class) )
    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, a3);
  if ( a4 && lstrcmpiA(a4, Class) )
    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, a4);
  lpsz = 0;
  v8 = StringFromCLSID(a2, &lpsz);
  if ( v8 >= 0 )
  {
    v9 = lpsz;
    if ( lpsz )
    {
      v10 = -1;
      do
        ++v10;
      while ( lpsz[v10] );
      cbMultiByte = 2 * v10 + 2;
      if ( cbMultiByte <= 1024
        && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)cbMultiByte, v7) )
      {
        v12 = cbMultiByte + 15LL;
        if ( v12 < cbMultiByte )
          v12 = 0xFFFFFFFFFFFFFF0LL;
        v13 = alloca(v12 & 0xFFFFFFFFFFFFFFF0uLL);
        p_lpsz = (char *)&lpsz;
      }
      else
      {
        p_lpsz = (char *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                           &v19,
                           cbMultiByte);
      }
      if ( p_lpsz )
      {
        *p_lpsz = 0;
        if ( WideCharToMultiByte(0, 0, v9, -1, p_lpsz, cbMultiByte, 0, 0) )
        {
          if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, hKey[0], "CLSID", v15, lpMultiByteStr) )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, p_lpsz);
          CoTaskMemFree(lpsz);
          v8 = 0;
          goto LABEL_24;
        }
      }
      v9 = lpsz;
    }
    CoTaskMemFree(v9);
    v8 = -2147024882;
  }
LABEL_24:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v19);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004132c  push    rbp
0x18004132e  push    rbx
0x18004132f  push    rsi
0x180041330  push    rdi
0x180041331  push    r14
0x180041333  sub     rsp, 70h
0x180041337  lea     rbp, [rsp+40h]
0x18004133c  mov     rax, cs:__security_cookie
0x180041343  xor     rax, rbp
0x180041346  mov     [rbp+50h+var_28], rax
0x18004134a  mov     rbx, r9
0x18004134d  mov     rdi, r8
0x180041350  mov     rsi, rdx
0x180041353  xor     r14d, r14d
0x180041356  mov     [rbp+50h+var_48], r14
0x18004135a  mov     [rbp+50h+var_38], r14
0x18004135e  mov     [rbp+50h+var_30], r14
0x180041362  mov     [rbp+50h+hKey], 0FFFFFFFF80000000h
0x18004136a  test    r8, r8
0x18004136d  jz      short loc_18004138F
0x18004136f  lea     rdx, Class; lpString2
0x180041376  mov     rcx, r8; lpString1
0x180041379  call    cs:__imp_lstrcmpiA
0x18004137f  test    eax, eax
0x180041381  jz      short loc_18004138F
0x180041383  mov     rdx, rdi; char *
0x180041386  lea     rcx, [rbp+50h+hKey]; this
0x18004138a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBD@Z; ATL::CRegKey::RecurseDeleteKey(char const *)
0x18004138f  test    rbx, rbx
0x180041392  jz      short loc_1800413B4
0x180041394  lea     rdx, Class; lpString2
0x18004139b  mov     rcx, rbx; lpString1
0x18004139e  call    cs:__imp_lstrcmpiA
0x1800413a4  test    eax, eax
0x1800413a6  jz      short loc_1800413B4
0x1800413a8  mov     rdx, rbx; char *
0x1800413ab  lea     rcx, [rbp+50h+hKey]; this
0x1800413af  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBD@Z; ATL::CRegKey::RecurseDeleteKey(char const *)
0x1800413b4  mov     [rbp+50h+lpsz], r14
0x1800413b8  lea     rdx, [rbp+50h+lpsz]; lplpsz
0x1800413bc  mov     rcx, rsi; rclsid
0x1800413bf  call    cs:__imp_StringFromCLSID
0x1800413c5  mov     ebx, eax
0x1800413c7  test    eax, eax
0x1800413c9  js      loc_1800414B2
0x1800413cf  mov     rbx, [rbp+50h+lpsz]
0x1800413d3  test    rbx, rbx
0x1800413d6  jz      loc_1800414A4
0x1800413dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800413e0  inc     rax
0x1800413e3  cmp     [rbx+rax*2], r14w
0x1800413e8  jnz     short loc_1800413E0
0x1800413ea  lea     esi, ds:2[rax*2]
0x1800413f1  movsxd  rdi, esi
0x1800413f4  cmp     esi, 400h
0x1800413fa  jg      short loc_18004142E
0x1800413fc  mov     rcx, rdi; this
0x1800413ff  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180041404  test    al, al
0x180041406  jz      short loc_18004142E
0x180041408  lea     rax, [rdi+0Fh]
0x18004140c  cmp     rax, rdi
0x18004140f  ja      short loc_18004141B
0x180041411  mov     rax, 0FFFFFFFFFFFFFF0h
0x18004141b  and     rax, 0FFFFFFFFFFFFFFF0h
0x18004141f  call    _alloca_probe
0x180041424  sub     rsp, rax
0x180041427  lea     rdi, [rsp+90h+lpsz]
0x18004142c  jmp     short loc_18004143D
0x18004142e  mov     rdx, rdi
0x180041431  lea     rcx, [rbp+50h+var_48]
0x180041435  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x18004143a  mov     rdi, rax
0x18004143d  test    rdi, rdi
0x180041440  jz      short loc_1800414A0
0x180041442  mov     [rdi], r14b
0x180041445  mov     [rsp+90h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18004144a  mov     [rsp+90h+lpDefaultChar], r14; lpDefaultChar
0x18004144f  mov     [rsp+90h+cbMultiByte], esi; cbMultiByte
0x180041453  mov     [rsp+90h+lpMultiByteStr], rdi; unsigned int
0x180041458  or      r9d, 0FFFFFFFFh; cchWideChar
0x18004145c  mov     r8, rbx; lpWideCharStr
0x18004145f  xor     edx, edx; dwFlags
0x180041461  xor     ecx, ecx; CodePage
0x180041463  call    cs:__imp_WideCharToMultiByte
0x180041469  test    eax, eax
0x18004146b  jz      short loc_1800414A0
0x18004146d  lea     r8, aClsid; "CLSID"
0x180041474  mov     rdx, [rbp+50h+hKey]; hKey
0x180041478  lea     rcx, [rbp+50h+hKey]; this
0x18004147c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBDKK@Z; ATL::CRegKey::Open(HKEY__ *,char const *,ulong,ulong)
0x180041481  test    eax, eax
0x180041483  jnz     short loc_180041491
0x180041485  mov     rdx, rdi; char *
0x180041488  lea     rcx, [rbp+50h+hKey]; this
0x18004148c  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBD@Z; ATL::CRegKey::RecurseDeleteKey(char const *)
0x180041491  mov     rcx, [rbp+50h+lpsz]; pv
0x180041495  call    cs:__imp_CoTaskMemFree
0x18004149b  mov     ebx, r14d
0x18004149e  jmp     short loc_1800414B2
0x1800414a0  mov     rbx, [rbp+50h+lpsz]
0x1800414a4  mov     rcx, rbx; pv
0x1800414a7  call    cs:__imp_CoTaskMemFree
0x1800414ad  mov     ebx, 8007000Eh
0x1800414b2  lea     rcx, [rbp+50h+hKey]; this
0x1800414b6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800414bb  nop
0x1800414bc  lea     rcx, [rbp+50h+var_48]
0x1800414c0  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800414c5  mov     eax, ebx
0x1800414c7  mov     rcx, [rbp+50h+var_28]
0x1800414cb  xor     rcx, rbp; StackCookie
0x1800414ce  call    __security_check_cookie
0x1800414d3  lea     rsp, [rbp+30h]
0x1800414d7  pop     r14
0x1800414d9  pop     rdi
0x1800414da  pop     rsi
0x1800414db  pop     rbx
0x1800414dc  pop     rbp
0x1800414dd  retn
```
