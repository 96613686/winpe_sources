# DllGetClassObject

- ea: `0x180001f30`
- end: `0x180001fde`
- name: `DllGetClassObject`
- size: `174`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180001f30`
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
  if ( *(_OWORD *)&CLSID_ReAgentTaskHandler != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CReAgentTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x180001f30  mov     [rsp+arg_0], rbx
0x180001f35  mov     [rsp+arg_8], rsi
0x180001f3a  push    rdi
0x180001f3b  sub     rsp, 20h
0x180001f3f  mov     rbx, r8
0x180001f42  mov     rsi, rdx
0x180001f45  test    r8, r8
0x180001f48  jnz     short loc_180001F51
0x180001f4a  mov     ebx, 80070057h
0x180001f4f  jmp     short loc_180001FCB
0x180001f51  and     qword ptr [r8], 0
0x180001f55  mov     rax, qword ptr cs:CLSID_ReAgentTaskHandler.Data1
0x180001f5c  cmp     rax, [rcx]
0x180001f5f  jnz     short loc_180001FC6
0x180001f61  mov     rax, qword ptr cs:CLSID_ReAgentTaskHandler.Data4
0x180001f68  cmp     rax, [rcx+8]
0x180001f6c  jnz     short loc_180001FC6
0x180001f6e  mov     ecx, 10h; Size
0x180001f73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001f78  mov     rdi, rax
0x180001f7b  test    rax, rax
0x180001f7e  jz      short loc_180001FBF
0x180001f80  lea     rax, ??_7?$CWinTaskClassFactoryT@VCReAgentTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CReAgentTaskHandler,1>::`vftable'
0x180001f87  mov     [rdi], rax
0x180001f8a  mov     dword ptr [rdi+8], 1
0x180001f91  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001f98  mov     rax, [rdi]
0x180001f9b  mov     r8, rbx
0x180001f9e  mov     rdx, rsi
0x180001fa1  mov     rcx, rdi
0x180001fa4  mov     rax, [rax]
0x180001fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fac  mov     ebx, eax
0x180001fae  mov     rax, [rdi]
0x180001fb1  mov     rcx, rdi
0x180001fb4  mov     rax, [rax+10h]
0x180001fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fbd  jmp     short loc_180001FCB
0x180001fbf  mov     ebx, 8007000Eh
0x180001fc4  jmp     short loc_180001FCB
0x180001fc6  mov     ebx, 80040111h
0x180001fcb  mov     rsi, [rsp+28h+arg_8]
0x180001fd0  mov     eax, ebx
0x180001fd2  mov     rbx, [rsp+28h+arg_0]
0x180001fd7  add     rsp, 20h
0x180001fdb  pop     rdi
0x180001fdc  retn
```
