# CreateEnumFormatEtc10

- ea: `0x18009ab30`
- end: `0x18009acc6`
- name: `CreateEnumFormatEtc10`
- size: `406`
- prototype: `HRESULT __fastcall(const _GUID *clsid, unsigned int dwDirection, IEnumFORMATETC **ppenum)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001bf18`
- `0x1800445d0`
- `0x180046840`
- `0x180079550`
- `0x18009b8b0`
- `0x1800a67d8`

## callees

- `0x18001c1d0`
- `0x180036488`
- `0x1800470d4`
- `0x180094b30`
- `0x18009a7f0`
- `0x18009a93c`
- `0x18009ab30`
- `0x18009adc0`
- `0x18009b030`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ac16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ac16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009abf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ac7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009abf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ac7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009abe4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009abe4`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009ab8f`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009ab8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009abb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ac9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009abb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ac9e`

## string_xrefs

- `0x18009abdd`: `Protocol\StdFileEditing\RequestDataFormats`

## pseudocode

```c
HRESULT __fastcall CreateEnumFormatEtc10(const _GUID *clsid, unsigned int dwDirection, IEnumFORMATETC **ppenum)
{
  const IID *v5; // r8
  HRESULT result; // eax
  LSTATUS v7; // edi
  CEnumFmt10 *ptr; // rbx
  CEnumFmt10 *v9; // rax
  CEnumFmt10 *v10; // rax
  int v11; // edi
  IEnumFORMATETC *v12; // rax
  wchar_t *szClsid; // [rsp+30h] [rbp-20h] BYREF
  HKEY__ *hkeyFmts; // [rsp+38h] [rbp-18h] BYREF
  Microsoft::WRL::ComPtr<CEnumFmt10> penum; // [rsp+40h] [rbp-10h] BYREF
  Microsoft::WRL::Details::MakeAllocator<CFormatOnlyDataObject> v16; // [rsp+48h] [rbp-8h] BYREF
  HKEY__ *hkey; // [rsp+88h] [rbp+38h] BYREF

  szClsid = 0;
  hkey = 0;
  hkeyFmts = 0;
  if ( !IsValidPtrOut(ppenum, 8u) )
    return -2147024809;
  *ppenum = 0;
  result = ProgIDFromCLSID(v5, &szClsid);
  if ( !result )
  {
    if ( (unsigned int)OpenClassesRootKeyExW(szClsid, 0x2000000u, &hkey) )
    {
      CoTaskMemFree(szClsid);
      return -2147221164;
    }
    else
    {
      v7 = RegOpenKeyExW(hkey, L"Protocol\\StdFileEditing\\RequestDataFormats", 0, 0x20019u, &hkeyFmts);
      if ( hkeyFmts )
      {
        RegCloseKey(hkeyFmts);
        hkeyFmts = 0;
      }
      ptr = 0;
      penum.ptr_ = 0;
      v9 = (CEnumFmt10 *)HeapAlloc(g_hHeap, 0, 0x28u);
      v16.buffer_ = v9;
      if ( v9 )
      {
        CEnumFmt10::CEnumFmt10(v9, dwDirection, 0);
        Microsoft::WRL::ComPtr<CEnumFmt10>::Attach(&penum, v10);
        v16.buffer_ = 0;
        ptr = penum.ptr_;
      }
      Microsoft::WRL::Details::MakeAllocator<TypeLibRegistrationReader>::~MakeAllocator<TypeLibRegistrationReader>(&v16);
      if ( ptr )
      {
        if ( v7 )
          CEnumFmt10::InitFromScratch(ptr);
        else
          CEnumFmt10::InitFromRegDb(ptr, hkey);
        v11 = 0;
      }
      else
      {
        v11 = -2147024882;
      }
      if ( hkey )
      {
        RegCloseKey(hkey);
        hkey = 0;
      }
      if ( v11 )
      {
        CoTaskMemFree(szClsid);
      }
      else
      {
        v12 = ptr;
        ptr = 0;
        *ppenum = v12;
      }
      if ( ptr )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDragOperationInternal>::Release((Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IOleVerb> *)ptr);
      return v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18009ab30  mov     [rsp-18h+arg_0], rbx
0x18009ab35  mov     [rsp-18h+arg_8], rsi
0x18009ab3a  push    rbp
0x18009ab3b  push    rdi
0x18009ab3c  push    r14
0x18009ab3e  mov     rbp, rsp
0x18009ab41  sub     rsp, 50h
0x18009ab45  mov     rsi, ppenum
0x18009ab48  mov     [rbp+szClsid], 0
0x18009ab50  mov     ppenum, clsid
0x18009ab53  mov     [rbp+hkey], 0
0x18009ab5b  mov     r14d, dwDirection
0x18009ab5e  mov     [rbp+hkeyFmts], 0
0x18009ab66  mov     clsid, rsi; pv
0x18009ab69  mov     dwDirection, 8; cb
0x18009ab6e  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x18009ab73  test    eax, eax
0x18009ab75  jnz     short loc_18009AB81
0x18009ab77  mov     eax, 80070057h
0x18009ab7c  jmp     loc_18009ACB3
0x18009ab81  lea     rdx, [rbp+szClsid]; lplpszProgID
0x18009ab85  mov     qword ptr [rsi], 0
0x18009ab8c  mov     clsid, ppenum; clsid
0x18009ab8f  call    cs:__imp_ProgIDFromCLSID
0x18009ab95  test    eax, eax
0x18009ab97  jnz     loc_18009ACB3
0x18009ab9d  mov     clsid, [rbp+szClsid]; pszSubKey
0x18009aba1  lea     ppenum, [rbp+hkey]; phkResult
0x18009aba5  mov     dwDirection, 2000000h; samDesired
0x18009abaa  call    OpenClassesRootKeyExW
0x18009abaf  test    eax, eax
0x18009abb1  jz      short loc_18009ABC7
0x18009abb3  mov     clsid, [rbp+szClsid]; pv
0x18009abb7  call    cs:__imp_CoTaskMemFree
0x18009abbd  mov     eax, 80040154h
0x18009abc2  jmp     loc_18009ACB3
0x18009abc7  mov     clsid, [rbp+hkey]; hKey
0x18009abcb  lea     rax, [rbp+hkeyFmts]
0x18009abcf  mov     r9d, 20019h; samDesired
0x18009abd5  mov     [rsp+50h+phkResult], rax; phkResult
0x18009abda  xor     r8d, r8d; ulOptions
0x18009abdd  lea     rdx, aProtocolStdfil; "Protocol\\StdFileEditing\\RequestDataFo"...
0x18009abe4  call    cs:__imp_RegOpenKeyExW
0x18009abea  mov     clsid, [rbp+hkeyFmts]; hKey
0x18009abee  mov     edi, eax
0x18009abf0  test    clsid, clsid
0x18009abf3  jz      short loc_18009AC03
0x18009abf5  call    cs:__imp_RegCloseKey
0x18009abfb  mov     [rbp+hkeyFmts], 0
0x18009ac03  mov     clsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009ac0a  xor     ebx, ebx
0x18009ac0c  xor     dwDirection, dwDirection; dwFlags
0x18009ac0e  mov     [rbp+penum.ptr_], rbx
0x18009ac12  lea     r8d, [rbx+28h]; dwBytes
0x18009ac16  call    cs:__imp_HeapAlloc
0x18009ac1c  mov     [rbp+var_8.buffer_], rax
0x18009ac20  test    rax, rax
0x18009ac23  jz      short loc_18009AC47
0x18009ac25  xor     r8d, r8d; iKey
0x18009ac28  mov     dwDirection, r14d; dwDirection
0x18009ac2b  mov     clsid, rax; this
0x18009ac2e  call    ??0CEnumFmt10@@QEAA@KK@Z; CEnumFmt10::CEnumFmt10(ulong,ulong)
0x18009ac33  mov     rdx, rax; other
0x18009ac36  lea     clsid, [rbp+penum]; this
0x18009ac3a  call    ?Attach@?$ComPtr@VCEnumFmt10@@@WRL@Microsoft@@QEAAXPEAVCEnumFmt10@@@Z; Microsoft::WRL::ComPtr<CEnumFmt10>::Attach(CEnumFmt10 *)
0x18009ac3f  mov     [rbp+var_8.buffer_], rbx
0x18009ac43  mov     rbx, [rbp+penum.ptr_]
0x18009ac47  lea     clsid, [rbp+var_8]; this
0x18009ac4b  call    ??1?$MakeAllocator@VTypeLibRegistrationReader@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<TypeLibRegistrationReader>::~MakeAllocator<TypeLibRegistrationReader>(void)
0x18009ac50  test    rbx, rbx
0x18009ac53  jnz     short loc_18009AC5C
0x18009ac55  mov     edi, 8007000Eh
0x18009ac5a  jmp     short $errRtn_146
0x18009ac5c  mov     clsid, rbx; this
0x18009ac5f  test    edi, edi
0x18009ac61  jnz     short loc_18009AC6E
0x18009ac63  mov     rdx, [rbp+hkey]; hkey
0x18009ac67  call    ?InitFromRegDb@CEnumFmt10@@UEAAJPEAUHKEY__@@@Z; CEnumFmt10::InitFromRegDb(HKEY__ *)
0x18009ac6c  jmp     short loc_18009AC73
0x18009ac6e  call    ?InitFromScratch@CEnumFmt10@@UEAAJXZ; CEnumFmt10::InitFromScratch(void)
0x18009ac73  xor     edi, edi
0x18009ac75  mov     clsid, [rbp+hkey]; hKey
0x18009ac79  test    clsid, clsid
0x18009ac7c  jz      short loc_18009AC8C
0x18009ac7e  call    cs:__imp_RegCloseKey
0x18009ac84  mov     [rbp+hkey], 0
0x18009ac8c  test    edi, edi
0x18009ac8e  jnz     short loc_18009AC9A
0x18009ac90  mov     rax, rbx
0x18009ac93  xor     ebx, ebx
0x18009ac95  mov     [rsi], rax
0x18009ac98  jmp     short loc_18009ACA4
0x18009ac9a  mov     clsid, [rbp+szClsid]; pv
0x18009ac9e  call    cs:__imp_CoTaskMemFree
0x18009aca4  test    rbx, rbx
0x18009aca7  jz      short loc_18009ACB1
0x18009aca9  mov     clsid, rbx; this
0x18009acac  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDragOperationInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDragOperationInternal>::Release(void)
0x18009acb1  mov     eax, edi
0x18009acb3  mov     rbx, [rsp+50h+arg_0]
0x18009acb8  mov     rsi, [rsp+50h+arg_8]
0x18009acbd  add     rsp, 50h
0x18009acc1  pop     r14
0x18009acc3  pop     rdi
0x18009acc4  pop     rbp
0x18009acc5  retn
```
