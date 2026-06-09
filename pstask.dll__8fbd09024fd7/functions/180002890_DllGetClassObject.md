# DllGetClassObject

- ea: `0x180002890`
- end: `0x180002940`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180002890`
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
  if ( *(_OWORD *)&CLSID_pstask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CsvtaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x180002890  mov     [rsp+arg_0], rbx
0x180002895  mov     [rsp+arg_8], rsi
0x18000289a  push    rdi
0x18000289b  sub     rsp, 20h
0x18000289f  mov     rbx, r8
0x1800028a2  mov     rsi, rdx
0x1800028a5  test    r8, r8
0x1800028a8  jnz     short loc_1800028B1
0x1800028aa  mov     ebx, 80070057h
0x1800028af  jmp     short loc_18000292E
0x1800028b1  mov     qword ptr [r8], 0
0x1800028b8  mov     rax, qword ptr cs:CLSID_pstask.Data1
0x1800028bf  cmp     rax, [rcx]
0x1800028c2  jnz     short loc_180002929
0x1800028c4  mov     rax, qword ptr cs:CLSID_pstask.Data4
0x1800028cb  cmp     rax, [rcx+8]
0x1800028cf  jnz     short loc_180002929
0x1800028d1  mov     ecx, 10h; Size
0x1800028d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800028db  mov     rdi, rax
0x1800028de  test    rax, rax
0x1800028e1  jz      short loc_180002922
0x1800028e3  lea     rax, ??_7?$CWinTaskClassFactoryT@VCsvtaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CsvtaskHandler,1>::`vftable'
0x1800028ea  mov     [rdi], rax
0x1800028ed  mov     dword ptr [rdi+8], 1
0x1800028f4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800028fb  mov     rax, [rdi]
0x1800028fe  mov     r8, rbx
0x180002901  mov     rdx, rsi
0x180002904  mov     rcx, rdi
0x180002907  mov     rax, [rax]
0x18000290a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000290f  mov     ebx, eax
0x180002911  mov     rax, [rdi]
0x180002914  mov     rcx, rdi
0x180002917  mov     rax, [rax+10h]
0x18000291b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002920  jmp     short loc_18000292E
0x180002922  mov     ebx, 8007000Eh
0x180002927  jmp     short loc_18000292E
0x180002929  mov     ebx, 80040111h
0x18000292e  mov     rsi, [rsp+28h+arg_8]
0x180002933  mov     eax, ebx
0x180002935  mov     rbx, [rsp+28h+arg_0]
0x18000293a  add     rsp, 20h
0x18000293e  pop     rdi
0x18000293f  retn
```
