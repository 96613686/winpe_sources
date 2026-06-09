# DllGetClassObject

- ea: `0x180007b00`
- end: `0x180007ba4`
- name: `DllGetClassObject`
- size: `164`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001534`
- `0x180007b00`
- `0x180009010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // edi
  _DWORD *v6; // rbx

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_CmCleanup != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CmCleanupWim,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return v5;
}

```

## disassembly

```asm
0x180007b00  mov     [rsp+arg_0], rbx
0x180007b05  mov     [rsp+arg_8], rsi
0x180007b0a  push    rdi
0x180007b0b  sub     rsp, 20h
0x180007b0f  mov     rdi, r8
0x180007b12  mov     rsi, rdx
0x180007b15  test    r8, r8
0x180007b18  jnz     short loc_180007B21
0x180007b1a  mov     edi, 80070057h
0x180007b1f  jmp     short loc_180007B92
0x180007b21  mov     qword ptr [r8], 0
0x180007b28  mov     rax, qword ptr cs:CLSID_CmCleanup.Data1
0x180007b2f  cmp     rax, [rcx]
0x180007b32  jnz     short loc_180007B8D
0x180007b34  mov     rax, qword ptr cs:CLSID_CmCleanup.Data4
0x180007b3b  cmp     rax, [rcx+8]
0x180007b3f  jnz     short loc_180007B8D
0x180007b41  mov     ecx, 10h; Size
0x180007b46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b4b  mov     rbx, rax
0x180007b4e  lea     rax, ??_7?$CWinTaskClassFactoryT@VCmCleanupWim@@$00@@6B@; const CWinTaskClassFactoryT<CmCleanupWim,1>::`vftable'
0x180007b55  mov     [rbx], rax
0x180007b58  mov     dword ptr [rbx+8], 1
0x180007b5f  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180007b66  mov     rax, [rbx]
0x180007b69  mov     r8, rdi
0x180007b6c  mov     rdx, rsi
0x180007b6f  mov     rcx, rbx
0x180007b72  mov     rax, [rax]
0x180007b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b7a  mov     edi, eax
0x180007b7c  mov     rax, [rbx]
0x180007b7f  mov     rcx, rbx
0x180007b82  mov     rax, [rax+10h]
0x180007b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b8b  jmp     short loc_180007B92
0x180007b8d  mov     edi, 80040111h
0x180007b92  mov     rbx, [rsp+28h+arg_0]
0x180007b97  mov     eax, edi
0x180007b99  mov     rsi, [rsp+28h+arg_8]
0x180007b9e  add     rsp, 20h
0x180007ba2  pop     rdi
0x180007ba3  retn
```
