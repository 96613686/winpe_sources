# DllGetClassObject

- ea: `0x18000c4e0`
- end: `0x18000c590`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001254`
- `0x18000c4e0`
- `0x18000e010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // ebx
  _DWORD *v6; // rax
  _DWORD *v7; // rdi

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_PnpReboot != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CPnpRebootHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x18000c4e0  mov     [rsp+arg_0], rbx
0x18000c4e5  mov     [rsp+arg_8], rsi
0x18000c4ea  push    rdi
0x18000c4eb  sub     rsp, 20h
0x18000c4ef  mov     rbx, r8
0x18000c4f2  mov     rsi, rdx
0x18000c4f5  test    r8, r8
0x18000c4f8  jnz     short loc_18000C501
0x18000c4fa  mov     ebx, 80070057h
0x18000c4ff  jmp     short loc_18000C57E
0x18000c501  mov     qword ptr [r8], 0
0x18000c508  mov     rax, qword ptr cs:CLSID_PnpReboot.Data1
0x18000c50f  cmp     rax, [rcx]
0x18000c512  jnz     short loc_18000C579
0x18000c514  mov     rax, qword ptr cs:CLSID_PnpReboot.Data4
0x18000c51b  cmp     rax, [rcx+8]
0x18000c51f  jnz     short loc_18000C579
0x18000c521  mov     ecx, 10h; Size
0x18000c526  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c52b  mov     rdi, rax
0x18000c52e  test    rax, rax
0x18000c531  jz      short loc_18000C572
0x18000c533  lea     rax, ??_7?$CWinTaskClassFactoryT@VCPnpRebootHandler@@$00@@6B@; const CWinTaskClassFactoryT<CPnpRebootHandler,1>::`vftable'
0x18000c53a  mov     [rdi], rax
0x18000c53d  mov     dword ptr [rdi+8], 1
0x18000c544  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000c54b  mov     rax, [rdi]
0x18000c54e  mov     r8, rbx
0x18000c551  mov     rdx, rsi
0x18000c554  mov     rcx, rdi
0x18000c557  mov     rax, [rax]
0x18000c55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c55f  mov     ebx, eax
0x18000c561  mov     rax, [rdi]
0x18000c564  mov     rcx, rdi
0x18000c567  mov     rax, [rax+10h]
0x18000c56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c570  jmp     short loc_18000C57E
0x18000c572  mov     ebx, 8007000Eh
0x18000c577  jmp     short loc_18000C57E
0x18000c579  mov     ebx, 80040111h
0x18000c57e  mov     rsi, [rsp+28h+arg_8]
0x18000c583  mov     eax, ebx
0x18000c585  mov     rbx, [rsp+28h+arg_0]
0x18000c58a  add     rsp, 20h
0x18000c58e  pop     rdi
0x18000c58f  retn
```
