# CMultiplexPropertyStore::Load(IPropertyBag *,IErrorLog *)

- ea: `0x18006d1b0`
- end: `0x18006d3d7`
- name: `?Load@CMultiplexPropertyStore@@UEAAJPEAUIPropertyBag@@PEAUIErrorLog@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(CMultiplexPropertyStore *__hidden this, struct IPropertyBag *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003f94`
- `0x18001d080`
- `0x18002f840`
- `0x18006d1b0`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d3ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d3ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d28c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d28c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006d2da`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006d2da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d379`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d391`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d379`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d391`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006d32c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006d32c`
- `SHCORE!__imp_GUIDFromStringW` at `0x18006d2f7`
- `SHCORE!__imp_GUIDFromStringW` at `0x18006d2f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMultiplexPropertyStore::Load(
        CMultiplexPropertyStore *this,
        struct IPropertyBag *a2,
        struct IErrorLog *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // r14
  int v6; // esi
  HRESULT (__stdcall *QueryInterface)(IPropertyBag *, const IID *const, void **); // rbx
  int v8; // ebx
  LSTATUS v9; // eax
  DWORD i; // edi
  HKEY v11; // rcx
  HKEY v12; // rcx
  DWORD cchName; // [rsp+50h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-61h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  __int64 v18; // [rsp+70h] [rbp-49h] BYREF
  IID rclsid; // [rsp+78h] [rbp-41h] BYREF
  WCHAR Name[40]; // [rsp+90h] [rbp-29h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 16) & -(__int64)(this != (CMultiplexPropertyStore *)48));
  v6 = CObjectWithThreadUseDetection::TryEnterOnCurrentThread((__int64)v5);
  if ( v6 < 0 )
  {
    v8 = v6;
  }
  else
  {
    v18 = 0;
    QueryInterface = a2->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v18);
    v8 = ((__int64 (__fastcall *)(struct IPropertyBag *, GUID *, __int64 *))QueryInterface)(
           a2,
           &GUID_d960050c_f4e1_4294_ac4b_598913605923,
           &v18);
    if ( v8 >= 0 )
    {
      hKey = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, HKEY *))(*(_QWORD *)v18 + 32LL))(v18, 131097, &hKey);
      if ( v8 >= 0 )
      {
        phkResult = 0;
        v9 = RegOpenKeyExW(hKey, L"InitPropertyBag", 0, 0x20019u, &phkResult);
        v8 = v9;
        if ( v9 > 0 )
          v8 = (unsigned __int16)v9 | 0x80070000;
        for ( i = 0; ; ++i )
        {
          cchName = 39;
          if ( v8 < 0 || RegEnumKeyExW(phkResult, i, Name, &cchName, 0, 0, 0, 0) )
            break;
          rclsid = 0;
          if ( (unsigned int)GUIDFromStringW(Name, &rclsid) )
          {
            ppv = 0;
            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
            v8 = CoCreateInstance(&rclsid, 0, 1u, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
            if ( v8 >= 0 )
              v8 = CMultiplexPropertyStore::AddStore(
                     (CMultiplexPropertyStore *)((char *)this - 8),
                     (struct IUnknown *)ppv);
            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
          }
          else
          {
            v8 = -2147024809;
          }
        }
        v11 = phkResult;
        phkResult = 0;
        if ( v11 )
          RegCloseKey(v11);
      }
      v12 = hKey;
      hKey = 0;
      if ( v12 )
        RegCloseKey(v12);
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v18);
  }
  if ( v6 >= 0 )
    LeaveCriticalSection(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006d1b0  mov     [rsp-8+arg_10], rbx
0x18006d1b5  push    rbp
0x18006d1b6  push    rsi
0x18006d1b7  push    rdi
0x18006d1b8  push    r14
0x18006d1ba  push    r15
0x18006d1bc  lea     rbp, [rsp-37h]
0x18006d1c1  sub     rsp, 0F0h
0x18006d1c8  mov     rax, cs:__security_cookie
0x18006d1cf  xor     rax, rsp
0x18006d1d2  mov     [rbp+57h+var_30], rax
0x18006d1d6  mov     rdi, rdx
0x18006d1d9  mov     r15, rcx
0x18006d1dc  lea     rax, [rcx-30h]
0x18006d1e0  lea     rdx, [rcx+10h]
0x18006d1e4  neg     rax
0x18006d1e7  sbb     r14, r14
0x18006d1ea  and     r14, rdx
0x18006d1ed  mov     [rbp+57h+var_D0], r14
0x18006d1f1  mov     rcx, r14
0x18006d1f4  call    ?TryEnterOnCurrentThread@CObjectWithThreadUseDetection@@IEAAJW4ThreadUseFailureResponse@@@Z; CObjectWithThreadUseDetection::TryEnterOnCurrentThread(ThreadUseFailureResponse)
0x18006d1f9  mov     esi, eax
0x18006d1fb  mov     [rbp+57h+var_C8], eax
0x18006d1fe  test    eax, eax
0x18006d200  js      loc_18006D3A3
0x18006d206  mov     [rbp+57h+var_A0], 0
0x18006d20e  mov     rdx, [rdi]
0x18006d211  mov     rbx, [rdx]
0x18006d214  lea     rcx, [rbp+57h+var_A0]
0x18006d218  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18006d21d  lea     r8, [rbp+57h+var_A0]
0x18006d221  lea     rdx, _GUID_d960050c_f4e1_4294_ac4b_598913605923
0x18006d228  mov     rcx, rdi
0x18006d22b  mov     rax, rbx
0x18006d22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d233  mov     ebx, eax
0x18006d235  test    eax, eax
0x18006d237  js      loc_18006D398
0x18006d23d  mov     [rbp+57h+hKey], 0
0x18006d245  mov     rcx, [rbp+57h+var_A0]
0x18006d249  mov     rax, [rcx]
0x18006d24c  lea     r8, [rbp+57h+hKey]
0x18006d250  mov     edi, 20019h
0x18006d255  mov     edx, edi
0x18006d257  mov     rax, [rax+20h]
0x18006d25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d260  mov     ebx, eax
0x18006d262  test    eax, eax
0x18006d264  js      loc_18006D380
0x18006d26a  mov     [rbp+57h+var_B0], 0
0x18006d272  lea     rax, [rbp+57h+var_B0]
0x18006d276  mov     [rsp+110h+phkResult], rax; phkResult
0x18006d27b  mov     r9d, edi; samDesired
0x18006d27e  xor     r8d, r8d; ulOptions
0x18006d281  lea     rdx, aInitpropertyba; "InitPropertyBag"
0x18006d288  mov     rcx, [rbp+57h+hKey]; hKey
0x18006d28c  call    cs:__imp_RegOpenKeyExW
0x18006d292  mov     ebx, eax
0x18006d294  test    eax, eax
0x18006d296  jle     short loc_18006D2A1
0x18006d298  movzx   ebx, ax
0x18006d29b  or      ebx, 80070000h
0x18006d2a1  xor     edi, edi
0x18006d2a3  jmp     loc_18006D359
0x18006d2a8  mov     [rsp+110h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18006d2b1  mov     [rsp+110h+lpcchClass], 0; lpcchClass
0x18006d2ba  mov     [rsp+110h+lpClass], 0; lpClass
0x18006d2c3  mov     [rsp+110h+phkResult], 0; lpReserved
0x18006d2cc  lea     r9, [rbp+57h+cchName]; lpcchName
0x18006d2d0  lea     r8, [rbp+57h+Name]; lpName
0x18006d2d4  mov     edx, edi; dwIndex
0x18006d2d6  mov     rcx, [rbp+57h+var_B0]; hKey
0x18006d2da  call    cs:__imp_RegEnumKeyExW
0x18006d2e0  test    eax, eax
0x18006d2e2  jnz     loc_18006D368
0x18006d2e8  xorps   xmm0, xmm0
0x18006d2eb  movups  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x18006d2ef  lea     rdx, [rbp+57h+rclsid]
0x18006d2f3  lea     rcx, [rbp+57h+Name]
0x18006d2f7  call    cs:__imp_GUIDFromStringW
0x18006d2fd  test    eax, eax
0x18006d2ff  jz      short loc_18006D352
0x18006d301  mov     [rbp+57h+ppv], 0
0x18006d309  lea     rcx, [rbp+57h+ppv]
0x18006d30d  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18006d312  lea     rax, [rbp+57h+ppv]
0x18006d316  mov     [rsp+110h+phkResult], rax; ppv
0x18006d31b  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18006d322  xor     edx, edx; pUnkOuter
0x18006d324  lea     r8d, [rdx+1]; dwClsContext
0x18006d328  lea     rcx, [rbp+57h+rclsid]; rclsid
0x18006d32c  call    cs:__imp_CoCreateInstance
0x18006d332  mov     ebx, eax
0x18006d334  test    eax, eax
0x18006d336  js      short loc_18006D347
0x18006d338  lea     rcx, [r15-8]; this
0x18006d33c  mov     rdx, [rbp+57h+ppv]; struct IUnknown *
0x18006d340  call    ?AddStore@CMultiplexPropertyStore@@UEAAJPEAUIUnknown@@@Z; CMultiplexPropertyStore::AddStore(IUnknown *)
0x18006d345  mov     ebx, eax
0x18006d347  lea     rcx, [rbp+57h+ppv]
0x18006d34b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18006d350  jmp     short loc_18006D357
0x18006d352  mov     ebx, 80070057h
0x18006d357  inc     edi
0x18006d359  test    ebx, ebx
0x18006d35b  mov     [rbp+57h+cchName], 27h ; '''
0x18006d362  jns     loc_18006D2A8
0x18006d368  mov     rcx, [rbp+57h+var_B0]; hKey
0x18006d36c  mov     [rbp+57h+var_B0], 0
0x18006d374  test    rcx, rcx
0x18006d377  jz      short loc_18006D380
0x18006d379  call    cs:__imp_RegCloseKey
0x18006d37f  nop
0x18006d380  mov     rcx, [rbp+57h+hKey]; hKey
0x18006d384  mov     [rbp+57h+hKey], 0
0x18006d38c  test    rcx, rcx
0x18006d38f  jz      short loc_18006D398
0x18006d391  call    cs:__imp_RegCloseKey
0x18006d397  nop
0x18006d398  lea     rcx, [rbp+57h+var_A0]
0x18006d39c  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18006d3a1  jmp     short loc_18006D3A5
0x18006d3a3  mov     ebx, esi
0x18006d3a5  test    esi, esi
0x18006d3a7  js      short loc_18006D3B2
0x18006d3a9  mov     rcx, r14; lpCriticalSection
0x18006d3ac  call    cs:__imp_LeaveCriticalSection
0x18006d3b2  mov     eax, ebx
0x18006d3b4  mov     rcx, [rbp+57h+var_30]
0x18006d3b8  xor     rcx, rsp; StackCookie
0x18006d3bb  call    __security_check_cookie
0x18006d3c0  mov     rbx, [rsp+110h+arg_10]
0x18006d3c8  add     rsp, 0F0h
0x18006d3cf  pop     r15
0x18006d3d1  pop     r14
0x18006d3d3  pop     rdi
0x18006d3d4  pop     rsi
0x18006d3d5  pop     rbp
0x18006d3d6  retn
```
