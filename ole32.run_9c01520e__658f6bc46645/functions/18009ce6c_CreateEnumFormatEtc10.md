# CreateEnumFormatEtc10

- ea: `0x18009ce6c`
- end: `0x18009d01f`
- name: `CreateEnumFormatEtc10`
- size: `435`
- prototype: `HRESULT __fastcall(const _GUID *clsid, unsigned int dwDirection, IEnumFORMATETC **ppenum)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180022b70`
- `0x180072020`
- `0x180097650`
- `0x18009dd60`
- `0x1800a3560`
- `0x1800ad988`

## callees

- `0x18001d110`
- `0x18003a394`
- `0x180045468`
- `0x180093890`
- `0x18009cb10`
- `0x18009cc4c`
- `0x18009ce6c`
- `0x18009d140`
- `0x18009d3f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009cf5b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009cf5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009cf1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009cf1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009cf37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009cfcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009cf37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009cfcd`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009cebe`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009cebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ceec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cff0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ceec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009cff0`

## string_xrefs

- `0x18009cf18`: `Protocol\StdFileEditing\RequestDataFormats`

## pseudocode

```c
HRESULT __fastcall CreateEnumFormatEtc10(const _GUID *clsid, unsigned int dwDirection, IEnumFORMATETC **ppenum)
{
  const IID *v5; // r8
  HRESULT result; // eax
  LSTATUS v7; // r14d
  CEnumFmt10 *ptr; // rbx
  char *v9; // rax
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
      v9 = (char *)HeapAlloc(g_hHeap, 0, 0x28u);
      v16.buffer_ = v9;
      if ( v9 )
      {
        CEnumFmt10::CEnumFmt10((CEnumFmt10 *)v9, dwDirection, 0);
        Microsoft::WRL::ComPtr<CEnumFmt10>::Attach(&penum, v10);
        v16.buffer_ = 0;
        ptr = penum.ptr_;
      }
      Microsoft::WRL::Details::MakeAllocator<TypeLibRegistrationReader>::~MakeAllocator<TypeLibRegistrationReader>(&v16);
      v11 = -2147024882;
      if ( ptr )
      {
        v11 = 0;
        if ( v7 )
          CEnumFmt10::InitFromScratch(ptr);
        else
          CEnumFmt10::InitFromRegDb(ptr, hkey);
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
0x18009ce6c  mov     [rsp-18h+arg_0], rbx
0x18009ce71  mov     [rsp-18h+arg_8], rsi
0x18009ce76  push    rbp
0x18009ce77  push    rdi
0x18009ce78  push    r14
0x18009ce7a  mov     rbp, rsp
0x18009ce7d  sub     rsp, 50h
0x18009ce81  and     [rbp+szClsid], 0
0x18009ce86  mov     rsi, ppenum
0x18009ce89  and     [rbp+hkey], 0
0x18009ce8e  mov     ppenum, clsid
0x18009ce91  and     [rbp+hkeyFmts], 0
0x18009ce96  mov     edi, dwDirection
0x18009ce98  mov     clsid, rsi; pv
0x18009ce9b  mov     dwDirection, 8; cb
0x18009cea0  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x18009cea5  test    eax, eax
0x18009cea7  jnz     short loc_18009CEB3
0x18009cea9  mov     eax, 80070057h
0x18009ceae  jmp     loc_18009D00B
0x18009ceb3  and     qword ptr [rsi], 0
0x18009ceb7  lea     rdx, [rbp+szClsid]; lplpszProgID
0x18009cebb  mov     clsid, ppenum; clsid
0x18009cebe  call    cs:__imp_ProgIDFromCLSID
0x18009cec5  nop     dword ptr [rax+rax+00h]
0x18009ceca  test    eax, eax
0x18009cecc  jnz     loc_18009D00B
0x18009ced2  mov     clsid, [rbp+szClsid]; pszSubKey
0x18009ced6  lea     ppenum, [rbp+hkey]; phkResult
0x18009ceda  mov     dwDirection, 2000000h; samDesired
0x18009cedf  call    OpenClassesRootKeyExW
0x18009cee4  test    eax, eax
0x18009cee6  jz      short loc_18009CF02
0x18009cee8  mov     clsid, [rbp+szClsid]; pv
0x18009ceec  call    cs:__imp_CoTaskMemFree
0x18009cef3  nop     dword ptr [rax+rax+00h]
0x18009cef8  mov     eax, 80040154h
0x18009cefd  jmp     loc_18009D00B
0x18009cf02  mov     clsid, [rbp+hkey]; hKey
0x18009cf06  lea     rax, [rbp+hkeyFmts]
0x18009cf0a  mov     r9d, 20019h; samDesired
0x18009cf10  mov     [rsp+50h+phkResult], rax; phkResult
0x18009cf15  xor     r8d, r8d; ulOptions
0x18009cf18  lea     rdx, aProtocolStdfil; "Protocol\\StdFileEditing\\RequestDataFo"...
0x18009cf1f  call    cs:__imp_RegOpenKeyExW
0x18009cf26  nop     dword ptr [rax+rax+00h]
0x18009cf2b  mov     clsid, [rbp+hkeyFmts]; hKey
0x18009cf2f  mov     r14d, eax
0x18009cf32  test    clsid, clsid
0x18009cf35  jz      short loc_18009CF48
0x18009cf37  call    cs:__imp_RegCloseKey
0x18009cf3e  nop     dword ptr [rax+rax+00h]
0x18009cf43  and     [rbp+hkeyFmts], 0
0x18009cf48  mov     clsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009cf4f  xor     ebx, ebx
0x18009cf51  xor     dwDirection, dwDirection; dwFlags
0x18009cf53  mov     [rbp+penum.ptr_], rbx
0x18009cf57  lea     r8d, [rbx+28h]; dwBytes
0x18009cf5b  call    cs:__imp_HeapAlloc
0x18009cf62  nop     dword ptr [rax+rax+00h]
0x18009cf67  mov     [rbp+var_8.buffer_], rax
0x18009cf6b  test    rax, rax
0x18009cf6e  jz      short loc_18009CF91
0x18009cf70  xor     r8d, r8d; iKey
0x18009cf73  mov     dwDirection, edi; dwDirection
0x18009cf75  mov     clsid, rax; this
0x18009cf78  call    ??0CEnumFmt10@@QEAA@KK@Z; CEnumFmt10::CEnumFmt10(ulong,ulong)
0x18009cf7d  mov     rdx, rax; other
0x18009cf80  lea     clsid, [rbp+penum]; this
0x18009cf84  call    ?Attach@?$ComPtr@VCEnumFmt10@@@WRL@Microsoft@@QEAAXPEAVCEnumFmt10@@@Z; Microsoft::WRL::ComPtr<CEnumFmt10>::Attach(CEnumFmt10 *)
0x18009cf89  and     [rbp+var_8.buffer_], rbx
0x18009cf8d  mov     rbx, [rbp+penum.ptr_]
0x18009cf91  lea     clsid, [rbp+var_8]; this
0x18009cf95  call    ??1?$MakeAllocator@VTypeLibRegistrationReader@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<TypeLibRegistrationReader>::~MakeAllocator<TypeLibRegistrationReader>(void)
0x18009cf9a  mov     edi, 8007000Eh
0x18009cf9f  test    rbx, rbx
0x18009cfa2  jz      short $errRtn_130
0x18009cfa4  xor     eax, eax
0x18009cfa6  neg     al
0x18009cfa8  sbb     ecx, ecx
0x18009cfaa  and     edi, ecx
0x18009cfac  mov     clsid, rbx; this
0x18009cfaf  test    r14d, r14d
0x18009cfb2  jnz     short loc_18009CFBF
0x18009cfb4  mov     rdx, [rbp+hkey]; hkey
0x18009cfb8  call    ?InitFromRegDb@CEnumFmt10@@UEAAJPEAUHKEY__@@@Z; CEnumFmt10::InitFromRegDb(HKEY__ *)
0x18009cfbd  jmp     short $errRtn_130
0x18009cfbf  call    ?InitFromScratch@CEnumFmt10@@UEAAJXZ; CEnumFmt10::InitFromScratch(void)
0x18009cfc4  mov     clsid, [rbp+hkey]; hKey
0x18009cfc8  test    clsid, clsid
0x18009cfcb  jz      short loc_18009CFDE
0x18009cfcd  call    cs:__imp_RegCloseKey
0x18009cfd4  nop     dword ptr [rax+rax+00h]
0x18009cfd9  and     [rbp+hkey], 0
0x18009cfde  test    edi, edi
0x18009cfe0  jnz     short loc_18009CFEC
0x18009cfe2  mov     rax, rbx
0x18009cfe5  xor     ebx, ebx
0x18009cfe7  mov     [rsi], rax
0x18009cfea  jmp     short loc_18009CFFC
0x18009cfec  mov     clsid, [rbp+szClsid]; pv
0x18009cff0  call    cs:__imp_CoTaskMemFree
0x18009cff7  nop     dword ptr [rax+rax+00h]
0x18009cffc  test    rbx, rbx
0x18009cfff  jz      short loc_18009D009
0x18009d001  mov     clsid, rbx; this
0x18009d004  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDragOperationInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDragOperationInternal>::Release(void)
0x18009d009  mov     eax, edi
0x18009d00b  mov     rbx, [rsp+50h+arg_0]
0x18009d010  mov     rsi, [rsp+50h+arg_8]
0x18009d015  add     rsp, 50h
0x18009d019  pop     r14
0x18009d01b  pop     rdi
0x18009d01c  pop     rbp
0x18009d01d  retn
```
