# FormatPathsAsLinks(IShellItem * *,ulong,ushort * *)

- ea: `0x180072bb8`
- end: `0x180072e5a`
- name: `?FormatPathsAsLinks@@YAJPEAPEAUIShellItem@@KPEAPEAG@Z`
- size: `674`
- prototype: `__int64 __fastcall(struct IShellItem **, unsigned int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180064774`
- `0x18006488c`
- `0x1800678a0`

## callees

- `0x1800095a0`
- `0x1800098dc`
- `0x18001c4a8`
- `0x180024e44`
- `0x1800254e0`
- `0x180050d90`
- `0x180066250`
- `0x180072600`
- `0x180072bb8`
- `0x180073528`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180072c09`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180072c09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072d30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072dc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072d30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072dc3`
- `SHELL32!SHCreateItemFromParsingName` at `0x180072cf1`
- `SHELL32!SHCreateItemFromParsingName` at `0x180072cf1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FormatPathsAsLinks(struct IShellItem **a1, unsigned int a2, unsigned __int16 **a3)
{
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  HRESULT Related; // ebx
  unsigned int v10; // edi
  unsigned __int16 *v11; // rax
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPath; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v17; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v18; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v19; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+78h] [rbp-88h]
  __int64 v21; // [rsp+80h] [rbp-80h]
  WCHAR Buffer[36]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v23[1040]; // [rsp+D0h] [rbp-30h] BYREF

  if ( LoadStringW(g_hInstance, 0xEB8u, Buffer, 30) )
  {
    Related = 0;
LABEL_4:
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v10 = 0;
    do
    {
      if ( v10 >= a2 )
        break;
      v13 = 0;
      Related = GetRelatedItem<IIdentityName>((unsigned int)a1[v10], v6, v7, v8, (__int64)&v13);
      if ( Related >= 0 )
      {
        v18 = 0;
        Related = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v13 + 40LL))(
                    v13,
                    2147581953LL,
                    &v18);
        if ( Related >= 0 )
        {
          v17 = 0;
          Related = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 **))(*(_QWORD *)v13 + 40LL))(
                      v13,
                      2147844096LL,
                      &v17);
          if ( Related >= 0 )
          {
            pv = 0;
            pszPath = 0;
            if ( (int)PathMapLocalToUNC(v17, (unsigned __int16 **)&pszPath) < 0 )
            {
              Related = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v13 + 40LL))(
                          v13,
                          2147909632LL,
                          &pv);
            }
            else
            {
              ppv = 0;
              Related = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
              if ( Related >= 0 )
              {
                Related = (*(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)ppv + 40LL))(
                            ppv,
                            2147909632LL,
                            &pv);
                (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
              }
              CoTaskMemFree((LPVOID)pszPath);
            }
            if ( Related >= 0 )
            {
              Related = SHFormatMessageArg(1024, (unsigned int)Buffer, 0, 0, (__int64)v23);
              if ( Related >= 0 )
                Related = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                            &v19,
                            v23);
            }
            CoTaskMemFree(pv);
            CoTaskMemFree(v17);
          }
          CoTaskMemFree(v18);
        }
      }
      ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v13);
      ++v10;
    }
    while ( Related >= 0 );
    if ( Related < 0 )
      goto LABEL_25;
    *a3 = 0;
    Related = 0;
    v11 = v19;
    if ( !v19 )
    {
      Related = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  &v19,
                  &WindowName,
                  -1);
      if ( Related < 0 )
      {
LABEL_25:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
        return (unsigned int)Related;
      }
      v11 = v19;
    }
    v19 = 0;
    v21 = 0;
    v20 = 0;
    *a3 = v11;
    goto LABEL_25;
  }
  Related = ResultFromKnownLastError();
  if ( Related >= 0 )
    goto LABEL_4;
  return (unsigned int)Related;
}

```

## disassembly

```asm
0x180072bb8  mov     [rsp-8+arg_8], rbx
0x180072bbd  mov     [rsp-8+arg_18], rsi
0x180072bc2  push    rbp
0x180072bc3  push    rdi
0x180072bc4  push    r12
0x180072bc6  push    r14
0x180072bc8  push    r15
0x180072bca  lea     rbp, [rsp-3F0h]
0x180072bd2  sub     rsp, 4F0h
0x180072bd9  mov     rax, cs:__security_cookie
0x180072be0  xor     rax, rsp
0x180072be3  mov     [rbp+410h+var_30], rax
0x180072bea  mov     rsi, r8
0x180072bed  mov     r14d, edx
0x180072bf0  mov     r15, rcx
0x180072bf3  mov     r9d, 1Eh; cchBufferMax
0x180072bf9  lea     r8, [rbp+410h+Buffer]; lpBuffer
0x180072bfd  mov     edx, 0EB8h; uID
0x180072c02  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180072c09  call    cs:__imp_LoadStringW
0x180072c0f  xor     r12d, r12d
0x180072c12  test    eax, eax
0x180072c14  jz      short loc_180072C1B
0x180072c16  mov     ebx, r12d
0x180072c19  jmp     short loc_180072C2A
0x180072c1b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180072c20  mov     ebx, eax
0x180072c22  test    eax, eax
0x180072c24  js      loc_180072E2D
0x180072c2a  mov     [rsp+510h+var_4A0], r12
0x180072c2f  mov     [rsp+510h+var_498], r12
0x180072c34  mov     [rbp+410h+var_490], r12
0x180072c38  mov     edi, r12d
0x180072c3b  cmp     edi, r14d
0x180072c3e  jnb     loc_180072DDE
0x180072c44  mov     eax, edi
0x180072c46  mov     [rsp+510h+var_4D0], r12
0x180072c4b  lea     rcx, [rsp+510h+var_4D0]
0x180072c50  mov     [rsp+510h+var_4F0], rcx
0x180072c55  mov     rcx, [r15+rax*8]
0x180072c59  call    ??$GetRelatedItem@UIIdentityName@@@@YAJPEAUIShellItem@@PEAUIBindCtx@@_NAEBU_GUID@@PEAPEAX@Z; GetRelatedItem<IIdentityName>(IShellItem *,IBindCtx *,bool,_GUID const &,void * *)
0x180072c5e  mov     ebx, eax
0x180072c60  test    eax, eax
0x180072c62  js      loc_180072DCA
0x180072c68  mov     [rsp+510h+var_4A8], r12
0x180072c6d  mov     rcx, [rsp+510h+var_4D0]
0x180072c72  mov     rax, [rcx]
0x180072c75  lea     r8, [rsp+510h+var_4A8]
0x180072c7a  mov     edx, 80018001h
0x180072c7f  mov     rax, [rax+28h]
0x180072c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c88  mov     ebx, eax
0x180072c8a  test    eax, eax
0x180072c8c  js      loc_180072DCA
0x180072c92  mov     [rsp+510h+var_4B0], r12
0x180072c97  mov     rcx, [rsp+510h+var_4D0]
0x180072c9c  mov     rax, [rcx]
0x180072c9f  lea     r8, [rsp+510h+var_4B0]
0x180072ca4  mov     edx, 80058000h
0x180072ca9  mov     rax, [rax+28h]
0x180072cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072cb2  mov     ebx, eax
0x180072cb4  test    eax, eax
0x180072cb6  js      loc_180072DBE
0x180072cbc  mov     [rsp+510h+pv], r12
0x180072cc1  mov     [rsp+510h+pszPath], r12
0x180072cc6  lea     rdx, [rsp+510h+pszPath]; unsigned __int16 **
0x180072ccb  mov     rcx, [rsp+510h+var_4B0]; unsigned __int16 *
0x180072cd0  call    ?PathMapLocalToUNC@@YAJPEBGPEAPEAG@Z; PathMapLocalToUNC(ushort const *,ushort * *)
0x180072cd5  test    eax, eax
0x180072cd7  js      short loc_180072D38
0x180072cd9  mov     [rsp+510h+ppv], r12
0x180072cde  lea     r9, [rsp+510h+ppv]; ppv
0x180072ce3  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180072cea  xor     edx, edx; pbc
0x180072cec  mov     rcx, [rsp+510h+pszPath]; pszPath
0x180072cf1  call    cs:__imp_SHCreateItemFromParsingName
0x180072cf7  mov     ebx, eax
0x180072cf9  test    eax, eax
0x180072cfb  js      short loc_180072D2B
0x180072cfd  mov     rcx, [rsp+510h+ppv]
0x180072d02  mov     rax, [rcx]
0x180072d05  lea     r8, [rsp+510h+pv]
0x180072d0a  mov     edx, 80068000h
0x180072d0f  mov     rax, [rax+28h]
0x180072d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072d18  mov     ebx, eax
0x180072d1a  mov     rcx, [rsp+510h+ppv]
0x180072d1f  mov     rax, [rcx]
0x180072d22  mov     rax, [rax+10h]
0x180072d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072d2b  mov     rcx, [rsp+510h+pszPath]; pv
0x180072d30  call    cs:__imp_CoTaskMemFree
0x180072d36  jmp     short loc_180072D55
0x180072d38  mov     rcx, [rsp+510h+var_4D0]
0x180072d3d  mov     rax, [rcx]
0x180072d40  lea     r8, [rsp+510h+pv]
0x180072d45  mov     edx, 80068000h
0x180072d4a  mov     rax, [rax+28h]
0x180072d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072d53  mov     ebx, eax
0x180072d55  test    ebx, ebx
0x180072d57  js      short loc_180072DA8
0x180072d59  mov     rax, [rsp+510h+pv]
0x180072d5e  mov     [rsp+510h+var_4D8], rax
0x180072d63  mov     rax, [rsp+510h+var_4A8]
0x180072d68  mov     [rsp+510h+var_4E0], rax
0x180072d6d  mov     [rsp+510h+var_4E8], 208h
0x180072d75  lea     rax, [rbp+410h+var_440]
0x180072d79  mov     [rsp+510h+var_4F0], rax
0x180072d7e  xor     r9d, r9d
0x180072d81  xor     r8d, r8d
0x180072d84  lea     rdx, [rbp+410h+Buffer]
0x180072d88  mov     ecx, 400h
0x180072d8d  call    SHFormatMessageArg
0x180072d92  mov     ebx, eax
0x180072d94  test    eax, eax
0x180072d96  js      short loc_180072DA8
0x180072d98  lea     rdx, [rbp+410h+var_440]
0x180072d9c  lea     rcx, [rsp+510h+var_4A0]
0x180072da1  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x180072da6  mov     ebx, eax
0x180072da8  mov     rcx, [rsp+510h+pv]; pv
0x180072dad  call    cs:__imp_CoTaskMemFree
0x180072db3  mov     rcx, [rsp+510h+var_4B0]; pv
0x180072db8  call    cs:__imp_CoTaskMemFree
0x180072dbe  mov     rcx, [rsp+510h+var_4A8]; pv
0x180072dc3  call    cs:__imp_CoTaskMemFree
0x180072dc9  nop
0x180072dca  lea     rcx, [rsp+510h+var_4D0]
0x180072dcf  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180072dd4  inc     edi
0x180072dd6  test    ebx, ebx
0x180072dd8  jns     loc_180072C3B
0x180072dde  test    ebx, ebx
0x180072de0  js      short loc_180072E23
0x180072de2  mov     [rsi], r12
0x180072de5  mov     ebx, r12d
0x180072de8  mov     rax, [rsp+510h+var_4A0]
0x180072ded  test    rax, rax
0x180072df0  jnz     short loc_180072E12
0x180072df2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180072df6  lea     rdx, WindowName
0x180072dfd  lea     rcx, [rsp+510h+var_4A0]
0x180072e02  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180072e07  mov     ebx, eax
0x180072e09  test    eax, eax
0x180072e0b  js      short loc_180072E23
0x180072e0d  mov     rax, [rsp+510h+var_4A0]
0x180072e12  mov     [rsp+510h+var_4A0], r12
0x180072e17  mov     [rbp+410h+var_490], r12
0x180072e1b  mov     [rsp+510h+var_498], r12
0x180072e20  mov     [rsi], rax
0x180072e23  lea     rcx, [rsp+510h+var_4A0]
0x180072e28  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180072e2d  mov     eax, ebx
0x180072e2f  mov     rcx, [rbp+410h+var_30]
0x180072e36  xor     rcx, rsp; StackCookie
0x180072e39  call    __security_check_cookie
0x180072e3e  lea     r11, [rsp+510h+var_20]
0x180072e46  mov     rbx, [r11+38h]
0x180072e4a  mov     rsi, [r11+48h]
0x180072e4e  mov     rsp, r11
0x180072e51  pop     r15
0x180072e53  pop     r14
0x180072e55  pop     r12
0x180072e57  pop     rdi
0x180072e58  pop     rbp
0x180072e59  retn
```
