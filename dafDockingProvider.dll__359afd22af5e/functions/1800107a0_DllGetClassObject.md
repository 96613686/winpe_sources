# DllGetClassObject

- ea: `0x1800107a0`
- end: `0x180010844`
- name: `DllGetClassObject`
- size: `164`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001ef4`
- `0x1800107a0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800107f0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800107f0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  char *v7; // rbx
  HRESULT v8; // edi

  if ( !ppv )
    return -2147024809;
  v7 = (char *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v7 )
    return -2147024882;
  *((_DWORD *)v7 + 2) = 1;
  *(_QWORD *)v7 = &CClassFactory::`vftable';
  *((_QWORD *)v7 + 2) = rclsid;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v7 + 24));
  *((_QWORD *)v7 + 8) = 0;
  *((_QWORD *)v7 + 9) = 0;
  _InterlockedIncrement((volatile signed __int32 *)&g_cLockCount);
  v8 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v7)(v7, riid, ppv);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x1800107a0  push    rbx
0x1800107a2  push    rbp
0x1800107a3  push    rsi
0x1800107a4  push    rdi
0x1800107a5  sub     rsp, 28h
0x1800107a9  mov     rdi, r8
0x1800107ac  mov     rsi, rdx
0x1800107af  mov     rbp, rcx
0x1800107b2  test    r8, r8
0x1800107b5  jnz     short loc_1800107BE
0x1800107b7  mov     eax, 80070057h
0x1800107bc  jmp     short loc_18001083B
0x1800107be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800107c5  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800107ca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800107cf  mov     rbx, rax
0x1800107d2  test    rax, rax
0x1800107d5  jz      short loc_180010834
0x1800107d7  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x1800107de  mov     dword ptr [rbx+8], 1
0x1800107e5  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800107e9  mov     [rbx], rax
0x1800107ec  mov     [rbx+10h], rbp
0x1800107f0  call    cs:__imp_InitializeCriticalSection
0x1800107f6  mov     qword ptr [rbx+40h], 0
0x1800107fe  mov     qword ptr [rbx+48h], 0
0x180010806  lock inc cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18001080d  mov     rcx, [rbx]
0x180010810  mov     r8, rdi
0x180010813  mov     rdx, rsi
0x180010816  mov     rax, [rcx]
0x180010819  mov     rcx, rbx
0x18001081c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010821  mov     rcx, [rbx]
0x180010824  mov     edi, eax
0x180010826  mov     rax, [rcx+10h]
0x18001082a  mov     rcx, rbx
0x18001082d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010832  jmp     short loc_180010839
0x180010834  mov     edi, 8007000Eh
0x180010839  mov     eax, edi
0x18001083b  add     rsp, 28h
0x18001083f  pop     rdi
0x180010840  pop     rsi
0x180010841  pop     rbp
0x180010842  pop     rbx
0x180010843  retn
```
