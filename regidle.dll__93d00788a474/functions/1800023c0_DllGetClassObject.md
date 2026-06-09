# DllGetClassObject

- ea: `0x1800023c0`
- end: `0x180002470`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x1800023c0`
- `0x180003010`

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
  if ( *(_OWORD *)&CLSID_RegIdleTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CRegIdleHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x1800023c0  mov     [rsp+arg_0], rbx
0x1800023c5  mov     [rsp+arg_8], rsi
0x1800023ca  push    rdi
0x1800023cb  sub     rsp, 20h
0x1800023cf  mov     rbx, r8
0x1800023d2  mov     rsi, rdx
0x1800023d5  test    r8, r8
0x1800023d8  jnz     short loc_1800023E1
0x1800023da  mov     ebx, 80070057h
0x1800023df  jmp     short loc_18000245E
0x1800023e1  mov     qword ptr [r8], 0
0x1800023e8  mov     rax, qword ptr cs:CLSID_RegIdleTask.Data1
0x1800023ef  cmp     rax, [rcx]
0x1800023f2  jnz     short loc_180002459
0x1800023f4  mov     rax, qword ptr cs:CLSID_RegIdleTask.Data4
0x1800023fb  cmp     rax, [rcx+8]
0x1800023ff  jnz     short loc_180002459
0x180002401  mov     ecx, 10h; Size
0x180002406  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000240b  mov     rdi, rax
0x18000240e  test    rax, rax
0x180002411  jz      short loc_180002452
0x180002413  lea     rax, ??_7?$CWinTaskClassFactoryT@VCRegIdleHandler@@$00@@6B@; const CWinTaskClassFactoryT<CRegIdleHandler,1>::`vftable'
0x18000241a  mov     [rdi], rax
0x18000241d  mov     dword ptr [rdi+8], 1
0x180002424  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000242b  mov     rax, [rdi]
0x18000242e  mov     r8, rbx
0x180002431  mov     rdx, rsi
0x180002434  mov     rcx, rdi
0x180002437  mov     rax, [rax]
0x18000243a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000243f  mov     ebx, eax
0x180002441  mov     rax, [rdi]
0x180002444  mov     rcx, rdi
0x180002447  mov     rax, [rax+10h]
0x18000244b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002450  jmp     short loc_18000245E
0x180002452  mov     ebx, 8007000Eh
0x180002457  jmp     short loc_18000245E
0x180002459  mov     ebx, 80040111h
0x18000245e  mov     rsi, [rsp+28h+arg_8]
0x180002463  mov     eax, ebx
0x180002465  mov     rbx, [rsp+28h+arg_0]
0x18000246a  add     rsp, 20h
0x18000246e  pop     rdi
0x18000246f  retn
```
