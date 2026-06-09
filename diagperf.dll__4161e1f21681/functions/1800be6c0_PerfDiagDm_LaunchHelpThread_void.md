# PerfDiagDm::LaunchHelpThread(void *)

- ea: `0x1800be6c0`
- end: `0x1800be78c`
- name: `?LaunchHelpThread@PerfDiagDm@@YAKPEAX@Z`
- size: `204`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003268c`
- `0x1800be6c0`
- `0x1800cf080`
- `0x1800d6010`

## import_xrefs

- `USER32!LoadStringW` at `0x1800be704`
- `USER32!LoadStringW` at `0x1800be704`
- `ole32!CoInitialize` at `0x1800be6e4`
- `ole32!CoInitialize` at `0x1800be6e4`
- `ole32!CoCreateInstance` at `0x1800be735`
- `ole32!CoCreateInstance` at `0x1800be735`
- `ole32!CoUninitialize` at `0x1800be763`
- `ole32!CoUninitialize` at `0x1800be763`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall PerfDiagDm::LaunchHelpThread(PVOID Parameter)
{
  UINT v1; // edi
  HRESULT result; // eax
  HRESULT Instance; // ebx
  LPVOID ppv[2]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  v1 = (unsigned int)Parameter;
  result = CoInitialize(0);
  Instance = result;
  if ( result >= 0 )
  {
    if ( LoadStringW(hInstance, v1, Buffer, 260) )
    {
      ppv[0] = 0;
      Instance = CoCreateInstance(
                   &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
                   0,
                   0x17u,
                   &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
                   ppv);
      if ( Instance >= 0 )
        Instance = (*(__int64 (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv[0] + 24LL))(ppv[0], Buffer);
      ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(ppv);
    }
    CoUninitialize();
    return Instance;
  }
  return result;
}

```

## disassembly

```asm
0x1800be6c0  mov     [rsp+arg_8], rbx
0x1800be6c5  push    rdi
0x1800be6c6  sub     rsp, 260h
0x1800be6cd  mov     rax, cs:__security_cookie
0x1800be6d4  xor     rax, rsp
0x1800be6d7  mov     [rsp+268h+var_18], rax
0x1800be6df  mov     rdi, rcx
0x1800be6e2  xor     ecx, ecx; pvReserved
0x1800be6e4  call    cs:__imp_CoInitialize
0x1800be6ea  mov     ebx, eax
0x1800be6ec  test    eax, eax
0x1800be6ee  js      short loc_1800BE76B
0x1800be6f0  mov     edx, edi; uID
0x1800be6f2  mov     r9d, 104h; cchBufferMax
0x1800be6f8  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x1800be6fd  mov     rcx, cs:hInstance; hInstance
0x1800be704  call    cs:__imp_LoadStringW
0x1800be70a  test    eax, eax
0x1800be70c  jz      short loc_1800BE763
0x1800be70e  mov     [rsp+268h+var_238], 0
0x1800be717  lea     rax, [rsp+268h+var_238]
0x1800be71c  mov     [rsp+268h+ppv], rax; ppv
0x1800be721  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x1800be728  xor     edx, edx; pUnkOuter
0x1800be72a  lea     r8d, [rdx+17h]; dwClsContext
0x1800be72e  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x1800be735  call    cs:__imp_CoCreateInstance
0x1800be73b  mov     ebx, eax
0x1800be73d  test    eax, eax
0x1800be73f  js      short loc_1800BE759
0x1800be741  mov     rcx, [rsp+268h+var_238]
0x1800be746  mov     rax, [rcx]
0x1800be749  lea     rdx, [rsp+268h+Buffer]
0x1800be74e  mov     rax, [rax+18h]
0x1800be752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be757  mov     ebx, eax
0x1800be759  lea     rcx, [rsp+268h+var_238]
0x1800be75e  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x1800be763  call    cs:__imp_CoUninitialize
0x1800be769  mov     eax, ebx
0x1800be76b  mov     rcx, [rsp+268h+var_18]
0x1800be773  xor     rcx, rsp; StackCookie
0x1800be776  call    __security_check_cookie
0x1800be77b  mov     rbx, [rsp+268h+arg_8]
0x1800be783  add     rsp, 260h
0x1800be78a  pop     rdi
0x1800be78b  retn
```
