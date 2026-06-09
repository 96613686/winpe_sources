# DllGetClassObject

- ea: `0x180003410`
- end: `0x1800034c0`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180003410`
- `0x18000b010`

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
  if ( *(_OWORD *)&CLSID_pnppolicy != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CpnppolicyHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x180003410  mov     [rsp+arg_0], rbx
0x180003415  mov     [rsp+arg_8], rsi
0x18000341a  push    rdi
0x18000341b  sub     rsp, 20h
0x18000341f  mov     rbx, r8
0x180003422  mov     rsi, rdx
0x180003425  test    r8, r8
0x180003428  jnz     short loc_180003431
0x18000342a  mov     ebx, 80070057h
0x18000342f  jmp     short loc_1800034AE
0x180003431  mov     qword ptr [r8], 0
0x180003438  mov     rax, qword ptr cs:CLSID_pnppolicy.Data1
0x18000343f  cmp     rax, [rcx]
0x180003442  jnz     short loc_1800034A9
0x180003444  mov     rax, qword ptr cs:CLSID_pnppolicy.Data4
0x18000344b  cmp     rax, [rcx+8]
0x18000344f  jnz     short loc_1800034A9
0x180003451  mov     ecx, 10h; Size
0x180003456  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000345b  mov     rdi, rax
0x18000345e  test    rax, rax
0x180003461  jz      short loc_1800034A2
0x180003463  lea     rax, ??_7?$CWinTaskClassFactoryT@VCpnppolicyHandler@@$00@@6B@; const CWinTaskClassFactoryT<CpnppolicyHandler,1>::`vftable'
0x18000346a  mov     [rdi], rax
0x18000346d  mov     dword ptr [rdi+8], 1
0x180003474  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000347b  mov     rax, [rdi]
0x18000347e  mov     r8, rbx
0x180003481  mov     rdx, rsi
0x180003484  mov     rcx, rdi
0x180003487  mov     rax, [rax]
0x18000348a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000348f  mov     ebx, eax
0x180003491  mov     rax, [rdi]
0x180003494  mov     rcx, rdi
0x180003497  mov     rax, [rax+10h]
0x18000349b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034a0  jmp     short loc_1800034AE
0x1800034a2  mov     ebx, 8007000Eh
0x1800034a7  jmp     short loc_1800034AE
0x1800034a9  mov     ebx, 80040111h
0x1800034ae  mov     rsi, [rsp+28h+arg_8]
0x1800034b3  mov     eax, ebx
0x1800034b5  mov     rbx, [rsp+28h+arg_0]
0x1800034ba  add     rsp, 20h
0x1800034be  pop     rdi
0x1800034bf  retn
```
