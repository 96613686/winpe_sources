# DllGetClassObject

- ea: `0x180007820`
- end: `0x1800078c4`
- name: `DllGetClassObject`
- size: `164`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001c04`
- `0x180007820`
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
  if ( *(_OWORD *)&CLSID_MapUpdateTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return v5;
}

```

## disassembly

```asm
0x180007820  mov     [rsp+arg_0], rbx
0x180007825  mov     [rsp+arg_8], rsi
0x18000782a  push    rdi
0x18000782b  sub     rsp, 20h
0x18000782f  mov     rdi, r8
0x180007832  mov     rsi, rdx
0x180007835  test    r8, r8
0x180007838  jnz     short loc_180007841
0x18000783a  mov     edi, 80070057h
0x18000783f  jmp     short loc_1800078B2
0x180007841  mov     qword ptr [r8], 0
0x180007848  mov     rax, qword ptr cs:CLSID_MapUpdateTask.Data1
0x18000784f  cmp     rax, [rcx]
0x180007852  jnz     short loc_1800078AD
0x180007854  mov     rax, qword ptr cs:CLSID_MapUpdateTask.Data4
0x18000785b  cmp     rax, [rcx+8]
0x18000785f  jnz     short loc_1800078AD
0x180007861  mov     ecx, 10h; Size
0x180007866  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000786b  mov     rbx, rax
0x18000786e  lea     rax, ??_7?$CWinTaskClassFactoryT@VCMapsUpdateTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::`vftable'
0x180007875  mov     [rbx], rax
0x180007878  mov     dword ptr [rbx+8], 1
0x18000787f  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180007886  mov     rax, [rbx]
0x180007889  mov     r8, rdi
0x18000788c  mov     rdx, rsi
0x18000788f  mov     rcx, rbx
0x180007892  mov     rax, [rax]
0x180007895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000789a  mov     edi, eax
0x18000789c  mov     rax, [rbx]
0x18000789f  mov     rcx, rbx
0x1800078a2  mov     rax, [rax+10h]
0x1800078a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ab  jmp     short loc_1800078B2
0x1800078ad  mov     edi, 80040111h
0x1800078b2  mov     rbx, [rsp+28h+arg_0]
0x1800078b7  mov     eax, edi
0x1800078b9  mov     rsi, [rsp+28h+arg_8]
0x1800078be  add     rsp, 20h
0x1800078c2  pop     rdi
0x1800078c3  retn
```
