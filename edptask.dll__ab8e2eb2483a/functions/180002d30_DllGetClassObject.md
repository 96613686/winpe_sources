# DllGetClassObject

- ea: `0x180002d30`
- end: `0x180002de0`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001404`
- `0x180002d30`
- `0x180014010`

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
  if ( *(_OWORD *)&CLSID_EdpNotificationTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x180002d30  mov     [rsp+arg_0], rbx
0x180002d35  mov     [rsp+arg_8], rsi
0x180002d3a  push    rdi
0x180002d3b  sub     rsp, 20h
0x180002d3f  mov     rbx, r8
0x180002d42  mov     rsi, rdx
0x180002d45  test    r8, r8
0x180002d48  jnz     short loc_180002D51
0x180002d4a  mov     ebx, 80070057h
0x180002d4f  jmp     short loc_180002DCE
0x180002d51  mov     qword ptr [r8], 0
0x180002d58  mov     rax, qword ptr cs:CLSID_EdpNotificationTask.Data1
0x180002d5f  cmp     rax, [rcx]
0x180002d62  jnz     short loc_180002DC9
0x180002d64  mov     rax, qword ptr cs:CLSID_EdpNotificationTask.Data4
0x180002d6b  cmp     rax, [rcx+8]
0x180002d6f  jnz     short loc_180002DC9
0x180002d71  mov     ecx, 10h; Size
0x180002d76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d7b  mov     rdi, rax
0x180002d7e  test    rax, rax
0x180002d81  jz      short loc_180002DC2
0x180002d83  lea     rax, ??_7?$CWinTaskClassFactoryT@VCEdpNotificationTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::`vftable'
0x180002d8a  mov     [rdi], rax
0x180002d8d  mov     dword ptr [rdi+8], 1
0x180002d94  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002d9b  mov     rax, [rdi]
0x180002d9e  mov     r8, rbx
0x180002da1  mov     rdx, rsi
0x180002da4  mov     rcx, rdi
0x180002da7  mov     rax, [rax]
0x180002daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002daf  mov     ebx, eax
0x180002db1  mov     rcx, rdi
0x180002db4  mov     rax, [rdi]
0x180002db7  mov     rax, [rax+10h]
0x180002dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dc0  jmp     short loc_180002DCE
0x180002dc2  mov     ebx, 8007000Eh
0x180002dc7  jmp     short loc_180002DCE
0x180002dc9  mov     ebx, 80040111h
0x180002dce  mov     rsi, [rsp+28h+arg_8]
0x180002dd3  mov     eax, ebx
0x180002dd5  mov     rbx, [rsp+28h+arg_0]
0x180002dda  add     rsp, 20h
0x180002dde  pop     rdi
0x180002ddf  retn
```
