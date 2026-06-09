# DllGetClassObject

- ea: `0x180002b40`
- end: `0x180002bf0`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001030`
- `0x180002b40`
- `0x180004010`

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
  if ( *(_OWORD *)&CLSID_DsregTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CDsregTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x180002b40  mov     [rsp+arg_0], rbx
0x180002b45  mov     [rsp+arg_8], rsi
0x180002b4a  push    rdi
0x180002b4b  sub     rsp, 20h
0x180002b4f  mov     rbx, r8
0x180002b52  mov     rsi, rdx
0x180002b55  test    r8, r8
0x180002b58  jnz     short loc_180002B61
0x180002b5a  mov     ebx, 80070057h
0x180002b5f  jmp     short loc_180002BDE
0x180002b61  mov     qword ptr [r8], 0
0x180002b68  mov     rax, qword ptr cs:CLSID_DsregTask.Data1
0x180002b6f  cmp     rax, [rcx]
0x180002b72  jnz     short loc_180002BD9
0x180002b74  mov     rax, qword ptr cs:CLSID_DsregTask.Data4
0x180002b7b  cmp     rax, [rcx+8]
0x180002b7f  jnz     short loc_180002BD9
0x180002b81  mov     ecx, 10h; Size
0x180002b86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002b8b  mov     rdi, rax
0x180002b8e  test    rax, rax
0x180002b91  jz      short loc_180002BD2
0x180002b93  lea     rax, ??_7?$CWinTaskClassFactoryT@VCDsregTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CDsregTaskHandler,1>::`vftable'
0x180002b9a  mov     [rdi], rax
0x180002b9d  mov     dword ptr [rdi+8], 1
0x180002ba4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002bab  mov     rax, [rdi]
0x180002bae  mov     r8, rbx
0x180002bb1  mov     rdx, rsi
0x180002bb4  mov     rcx, rdi
0x180002bb7  mov     rax, [rax]
0x180002bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bbf  mov     ebx, eax
0x180002bc1  mov     rax, [rdi]
0x180002bc4  mov     rcx, rdi
0x180002bc7  mov     rax, [rax+10h]
0x180002bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd0  jmp     short loc_180002BDE
0x180002bd2  mov     ebx, 8007000Eh
0x180002bd7  jmp     short loc_180002BDE
0x180002bd9  mov     ebx, 80040111h
0x180002bde  mov     rsi, [rsp+28h+arg_8]
0x180002be3  mov     eax, ebx
0x180002be5  mov     rbx, [rsp+28h+arg_0]
0x180002bea  add     rsp, 20h
0x180002bee  pop     rdi
0x180002bef  retn
```
