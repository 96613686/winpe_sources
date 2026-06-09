# DllGetClassObject

- ea: `0x180006c50`
- end: `0x180006cf4`
- name: `DllGetClassObject`
- size: `164`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800015d4`
- `0x180006c50`
- `0x18000a010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // edi
  _DWORD *v6; // rbx

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_MapsToastTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return v5;
}

```

## disassembly

```asm
0x180006c50  mov     [rsp+arg_0], rbx
0x180006c55  mov     [rsp+arg_8], rsi
0x180006c5a  push    rdi
0x180006c5b  sub     rsp, 20h
0x180006c5f  mov     rdi, r8
0x180006c62  mov     rsi, rdx
0x180006c65  test    r8, r8
0x180006c68  jnz     short loc_180006C71
0x180006c6a  mov     edi, 80070057h
0x180006c6f  jmp     short loc_180006CE2
0x180006c71  mov     qword ptr [r8], 0
0x180006c78  mov     rax, qword ptr cs:CLSID_MapsToastTask.Data1
0x180006c7f  cmp     rax, [rcx]
0x180006c82  jnz     short loc_180006CDD
0x180006c84  mov     rax, qword ptr cs:CLSID_MapsToastTask.Data4
0x180006c8b  cmp     rax, [rcx+8]
0x180006c8f  jnz     short loc_180006CDD
0x180006c91  mov     ecx, 10h; Size
0x180006c96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c9b  mov     rbx, rax
0x180006c9e  lea     rax, ??_7?$CWinTaskClassFactoryT@VCMapsToastTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::`vftable'
0x180006ca5  mov     [rbx], rax
0x180006ca8  mov     dword ptr [rbx+8], 1
0x180006caf  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180006cb6  mov     rax, [rbx]
0x180006cb9  mov     r8, rdi
0x180006cbc  mov     rdx, rsi
0x180006cbf  mov     rcx, rbx
0x180006cc2  mov     rax, [rax]
0x180006cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cca  mov     edi, eax
0x180006ccc  mov     rax, [rbx]
0x180006ccf  mov     rcx, rbx
0x180006cd2  mov     rax, [rax+10h]
0x180006cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cdb  jmp     short loc_180006CE2
0x180006cdd  mov     edi, 80040111h
0x180006ce2  mov     rbx, [rsp+28h+arg_0]
0x180006ce7  mov     eax, edi
0x180006ce9  mov     rsi, [rsp+28h+arg_8]
0x180006cee  add     rsp, 20h
0x180006cf2  pop     rdi
0x180006cf3  retn
```
