# DllGetClassObject

- ea: `0x18000a930`
- end: `0x18000a9dd`
- name: `DllGetClassObject`
- size: `173`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a6ec`
- `0x18000a930`
- `0x18000e010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  char *v7; // rax
  char *v8; // rdi
  HRESULT v9; // ebx

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)rclsid != *(_OWORD *)&CLSID_CPackage )
    return -2147221231;
  v7 = (char *)operator new(0x20u);
  v8 = v7;
  if ( !v7 )
    return -2147024882;
  ++g_cRefThisDll;
  *(_QWORD *)v7 = &CMyClassFactory::`vftable';
  *((_DWORD *)v7 + 2) = 1;
  *(IID *)(v7 + 12) = *rclsid;
  v9 = ((__int64 (__fastcall *)(char *, const IID *const, LPVOID *))CMyClassFactory::`vftable')(v7, riid, ppv);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x18000a930  push    rbx
0x18000a932  push    rbp
0x18000a933  push    rsi
0x18000a934  push    rdi
0x18000a935  sub     rsp, 28h
0x18000a939  mov     rsi, r8
0x18000a93c  mov     rbp, rdx
0x18000a93f  mov     rbx, rcx
0x18000a942  test    r8, r8
0x18000a945  jnz     short loc_18000A951
0x18000a947  mov     eax, 80070057h
0x18000a94c  jmp     loc_18000A9D4
0x18000a951  mov     qword ptr [r8], 0
0x18000a958  mov     rax, [rcx]
0x18000a95b  cmp     rax, qword ptr cs:CLSID_CPackage.Data1
0x18000a962  jnz     short loc_18000A9CF
0x18000a964  mov     rax, [rcx+8]
0x18000a968  cmp     rax, qword ptr cs:CLSID_CPackage.Data4
0x18000a96f  jnz     short loc_18000A9CF
0x18000a971  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a976  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a97b  mov     rdi, rax
0x18000a97e  test    rax, rax
0x18000a981  jz      short loc_18000A9C8
0x18000a983  inc     cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000a989  lea     rax, ??_7CMyClassFactory@@6B@; const CMyClassFactory::`vftable'
0x18000a990  mov     [rdi], rax
0x18000a993  mov     r8, rsi
0x18000a996  mov     rax, [rax]
0x18000a999  mov     rdx, rbp
0x18000a99c  mov     dword ptr [rdi+8], 1
0x18000a9a3  mov     rcx, rdi
0x18000a9a6  movups  xmm0, xmmword ptr [rbx]
0x18000a9a9  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18000a9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9b3  mov     rcx, [rdi]
0x18000a9b6  mov     ebx, eax
0x18000a9b8  mov     rax, [rcx+10h]
0x18000a9bc  mov     rcx, rdi
0x18000a9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9c4  mov     eax, ebx
0x18000a9c6  jmp     short loc_18000A9D4
0x18000a9c8  mov     eax, 8007000Eh
0x18000a9cd  jmp     short loc_18000A9D4
0x18000a9cf  mov     eax, 80040111h
0x18000a9d4  add     rsp, 28h
0x18000a9d8  pop     rdi
0x18000a9d9  pop     rsi
0x18000a9da  pop     rbp
0x18000a9db  pop     rbx
0x18000a9dc  retn
```
