# CallerIdentity::VerifyWindowIsInSpecifiedApplication(HWND__ *,ushort const *,IUnknown *)

- ea: `0x180067668`
- end: `0x1800677d1`
- name: `?VerifyWindowIsInSpecifiedApplication@CallerIdentity@@YAJPEAUHWND__@@PEBGPEAUIUnknown@@@Z`
- size: `361`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, const wchar_t *pszAppId, IUnknown *pUnkApplicationResolver)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180067438`

## callees

- `0x1800037f7`
- `0x180003cf4`
- `0x1800668d8`
- `0x180066b68`
- `0x180066f14`
- `0x180067668`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800677a0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800677a0`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!GetWindowBand` at `0x1800676b7`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!GetWindowBand` at `0x1800676b7`

## pseudocode

```c
__int64 __fastcall CallerIdentity::VerifyWindowIsInSpecifiedApplication(
        HWND hwnd,
        const wchar_t *pszAppId,
        IUnknown *pUnkApplicationResolver)
{
  signed int Error; // ebx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT Instance_0; // eax
  IApplicationResolver *ptr; // rdi
  HRESULT (__fastcall *GetAppIDForWindow)(IApplicationResolver *, HWND__ *, wchar_t **, int *, int *, int *); // rbx
  Microsoft::WRL::ComPtr<IApplicationResolver> spApplicationResolver; // [rsp+40h] [rbp-10h] BYREF
  CMemString<CMemString_PolicyCoTaskMem> spszAppIdWindow; // [rsp+48h] [rbp-8h] BYREF
  ZBID zbid; // [rsp+88h] [rbp+38h] BYREF

  spszAppIdWindow._psz = 0;
  CoTaskMemFree_0(0);
  if ( CallerIdentity::GetImmersiveAppIdFromWindow(hwnd, &spszAppIdWindow._psz) >= 0 )
    goto LABEL_12;
  zbid = ZBID_DEFAULT;
  if ( (unsigned int)GetWindowBand(hwnd, &zbid) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    if ( zbid != ZBID_DESKTOP )
    {
      Error = -2147024809;
      goto LABEL_13;
    }
    spApplicationResolver.ptr_ = 0;
    if ( pUnkApplicationResolver )
    {
      QueryInterface = pUnkApplicationResolver->QueryInterface;
      Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(&spApplicationResolver);
      Instance_0 = QueryInterface(
                     pUnkApplicationResolver,
                     &GUID_de25675a_72de_44b4_9373_05170450c140,
                     (void **)&spApplicationResolver.ptr_);
    }
    else
    {
      Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(&spApplicationResolver);
      Instance_0 = CoCreateInstance_0(
                     &GUID_660b90c8_73a9_4b58_8cae_355b7f55341b,
                     0,
                     3u,
                     &GUID_de25675a_72de_44b4_9373_05170450c140,
                     (LPVOID *)&spApplicationResolver.ptr_);
    }
    Error = Instance_0;
    if ( Instance_0 >= 0 )
    {
      ptr = spApplicationResolver.ptr_;
      GetAppIDForWindow = spApplicationResolver.ptr_->GetAppIDForWindow;
      CoTaskMemFree_0(spszAppIdWindow._psz);
      Error = GetAppIDForWindow(ptr, hwnd, &spszAppIdWindow._psz, 0, 0, 0);
    }
    Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(&spApplicationResolver);
    if ( Error >= 0 )
LABEL_12:
      Error = CompareStringOrdinal(pszAppId, -1, spszAppIdWindow._psz, -1, 1) != 2 ? 0x80070005 : 0;
  }
LABEL_13:
  CoTaskMemFree_0(spszAppIdWindow._psz);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180067668  mov     [rsp-18h+arg_0], rbx
0x18006766d  mov     [rsp-18h+arg_8], rsi
0x180067672  push    rbp
0x180067673  push    rdi
0x180067674  push    r14
0x180067676  mov     rbp, rsp
0x180067679  sub     rsp, 50h
0x18006767d  mov     rsi, hwnd
0x180067680  mov     [rbp+spszAppIdWindow._psz], 0
0x180067688  xor     ecx, ecx; pv
0x18006768a  mov     rdi, pUnkApplicationResolver
0x18006768d  mov     r14, pszAppId
0x180067690  call    CoTaskMemFree_0
0x180067695  lea     pszAppId, [rbp+spszAppIdWindow]; result
0x180067699  mov     hwnd, rsi; hwnd
0x18006769c  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x1800676a1  test    eax, eax
0x1800676a3  jns     loc_18006778B
0x1800676a9  lea     pszAppId, [rbp+zbid]
0x1800676ad  mov     [rbp+zbid], 0
0x1800676b4  mov     hwnd, rsi
0x1800676b7  call    cs:__imp_GetWindowBand
0x1800676bd  test    eax, eax
0x1800676bf  jnz     short loc_1800676D0
0x1800676c1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800676c6  mov     ebx, eax
0x1800676c8  test    eax, eax
0x1800676ca  js      loc_1800677B3
0x1800676d0  cmp     [rbp+zbid], 1
0x1800676d4  jz      short loc_1800676E0
0x1800676d6  mov     ebx, 80070057h
0x1800676db  jmp     loc_1800677B3
0x1800676e0  mov     [rbp+spApplicationResolver.ptr_], 0
0x1800676e8  lea     hwnd, [rbp+spApplicationResolver]; this
0x1800676ec  test    rdi, rdi
0x1800676ef  jz      short loc_180067714
0x1800676f1  mov     rax, [rdi]
0x1800676f4  mov     rbx, [rax]
0x1800676f7  call    ?InternalRelease@?$ComPtr@UIImmersiveApplicationArrayService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(void)
0x1800676fc  lea     pUnkApplicationResolver, [rbp+spApplicationResolver]
0x180067700  mov     hwnd, rdi
0x180067703  lea     pszAppId, _GUID_de25675a_72de_44b4_9373_05170450c140
0x18006770a  mov     rax, rbx
0x18006770d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067712  jmp     short loc_18006773B
0x180067714  call    ?InternalRelease@?$ComPtr@UIImmersiveApplicationArrayService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(void)
0x180067719  xor     edx, edx; pUnkOuter
0x18006771b  lea     rax, [rbp+spApplicationResolver]
0x18006771f  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x180067726  mov     [rsp+50h+ppv], rax; ppv
0x18006772b  lea     hwnd, _GUID_660b90c8_73a9_4b58_8cae_355b7f55341b; rclsid
0x180067732  lea     r8d, [pszAppId+3]; dwClsContext
0x180067736  call    CoCreateInstance_0
0x18006773b  mov     ebx, eax
0x18006773d  test    eax, eax
0x18006773f  js      short loc_18006777E
0x180067741  mov     rdi, [rbp+spApplicationResolver.ptr_]
0x180067745  mov     hwnd, [rbp+spszAppIdWindow._psz]; pv
0x180067749  mov     rax, [rdi]
0x18006774c  mov     rbx, [rax+28h]
0x180067750  call    CoTaskMemFree_0
0x180067755  xor     r9d, r9d
0x180067758  mov     [rsp+50h+var_28], 0
0x180067761  lea     pUnkApplicationResolver, [rbp+spszAppIdWindow]
0x180067765  mov     [rsp+50h+ppv], 0
0x18006776e  mov     pszAppId, rsi
0x180067771  mov     hwnd, rdi
0x180067774  mov     rax, rbx
0x180067777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006777c  mov     ebx, eax
0x18006777e  lea     hwnd, [rbp+spApplicationResolver]; this
0x180067782  call    ?InternalRelease@?$ComPtr@UIImmersiveApplicationArrayService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(void)
0x180067787  test    ebx, ebx
0x180067789  js      short loc_1800677B3
0x18006778b  mov     pUnkApplicationResolver, [rbp+spszAppIdWindow._psz]; lpString2
0x18006778f  or      edx, 0FFFFFFFFh; cchCount1
0x180067792  mov     r9d, edx; cchCount2
0x180067795  mov     dword ptr [rsp+50h+ppv], 1; bIgnoreCase
0x18006779d  mov     hwnd, r14; lpString1
0x1800677a0  call    cs:__imp_CompareStringOrdinal
0x1800677a6  sub     eax, 2
0x1800677a9  neg     eax
0x1800677ab  sbb     ebx, ebx
0x1800677ad  and     ebx, 80070005h
0x1800677b3  mov     hwnd, [rbp+spszAppIdWindow._psz]; pv
0x1800677b7  call    CoTaskMemFree_0
0x1800677bc  mov     rsi, [rsp+50h+arg_8]
0x1800677c1  mov     eax, ebx
0x1800677c3  mov     rbx, [rsp+50h+arg_0]
0x1800677c8  add     rsp, 50h
0x1800677cc  pop     r14
0x1800677ce  pop     rdi
0x1800677cf  pop     rbp
0x1800677d0  retn
```
