# ATL::CComCreator<ATL::CComObject<CAccClientDocMgr>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f8fc`
- end: `0x18000fa44`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCAccClientDocMgr@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000f2d0`

## callees

- `0x180001370`
- `0x18000f8fc`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fa2f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fa2f`
- `KERNEL32!Sleep` at `0x18000f9d1`
- `KERNEL32!Sleep` at `0x18000f9d1`
- `KERNEL32!CloseHandle` at `0x18000f99c`
- `KERNEL32!CloseHandle` at `0x18000f99c`
- `KERNEL32!OpenEventW` at `0x18000f98b`
- `KERNEL32!OpenEventW` at `0x18000f98b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f9bf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f9bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CAccClientDocMgr>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int Instance; // edi
  _QWORD *v7; // rax
  void *v8; // rbx
  int v9; // eax
  HANDLE v10; // rax
  HANDLE v11; // rbp
  int v12; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  Instance = -2147024882;
  v7 = operator new(0x18u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 0;
    v7[2] = 0;
    *v7 = &ATL::CComObject<CAccClientDocMgr>::`vftable';
    _InterlockedIncrement(&dword_180024B28);
    v9 = *((_DWORD *)v7 + 2);
    if ( v9 != 0x7FFFFFFF )
      *((_DWORD *)v8 + 2) = v9 + 1;
    v10 = OpenEventW(0x100000u, 0, L"MSAA_STORE_EVENT");
    v11 = v10;
    if ( v10 )
      CloseHandle(v10);
    Instance = CoCreateInstance(&CLSID_AccStore, 0, 4u, &IID_IAccStore, (LPVOID *)v8 + 2);
    if ( !v11 )
      Sleep(0x1F4u);
    v12 = *((_DWORD *)v8 + 2);
    if ( v12 != 0x7FFFFFFF )
      *((_DWORD *)v8 + 2) = v12 - 1;
    if ( Instance || (Instance = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
    {
      *(_QWORD *)v8 = &ATL::CComObject<CAccClientDocMgr>::`vftable';
      *((_DWORD *)v8 + 2) = 1;
      _InterlockedDecrement(&dword_180024B28);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 2) + 16LL))(*((_QWORD *)v8 + 2));
      operator delete(v8);
    }
  }
  return Instance;
}

```

## disassembly

```asm
0x18000f8fc  push    rbx
0x18000f8fe  push    rbp
0x18000f8ff  push    rsi
0x18000f900  push    rdi
0x18000f901  push    r14
0x18000f903  push    r15
0x18000f905  sub     rsp, 38h
0x18000f909  mov     rsi, r8
0x18000f90c  mov     r15, rdx
0x18000f90f  test    r8, r8
0x18000f912  jnz     short loc_18000F91E
0x18000f914  mov     eax, 80004003h
0x18000f919  jmp     loc_18000FA37
0x18000f91e  mov     qword ptr [r8], 0
0x18000f925  mov     edi, 8007000Eh
0x18000f92a  mov     ecx, 18h; Size
0x18000f92f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f934  mov     rbx, rax
0x18000f937  mov     [rsp+68h+arg_0], rax
0x18000f93c  test    rax, rax
0x18000f93f  jz      loc_18000FA35
0x18000f945  mov     dword ptr [rax+8], 0
0x18000f94c  mov     qword ptr [rax+10h], 0
0x18000f954  lea     rax, ??_7?$CComObject@VCAccClientDocMgr@@@ATL@@6B@; const ATL::CComObject<CAccClientDocMgr>::`vftable'
0x18000f95b  mov     [rbx], rax
0x18000f95e  lock inc cs:dword_180024B28
0x18000f965  test    rbx, rbx
0x18000f968  jz      loc_18000FA35
0x18000f96e  mov     eax, [rbx+8]
0x18000f971  cmp     eax, 7FFFFFFFh
0x18000f976  jz      short loc_18000F97D
0x18000f978  inc     eax
0x18000f97a  mov     [rbx+8], eax
0x18000f97d  lea     r8, aMsaaStoreEvent; "MSAA_STORE_EVENT"
0x18000f984  xor     edx, edx; bInheritHandle
0x18000f986  mov     ecx, 100000h; dwDesiredAccess
0x18000f98b  call    cs:__imp_OpenEventW
0x18000f991  mov     rbp, rax
0x18000f994  test    rax, rax
0x18000f997  jz      short loc_18000F9A2
0x18000f999  mov     rcx, rax; hObject
0x18000f99c  call    cs:__imp_CloseHandle
0x18000f9a2  lea     r14, [rbx+10h]
0x18000f9a6  mov     [rsp+68h+ppv], r14; ppv
0x18000f9ab  lea     r9, IID_IAccStore; riid
0x18000f9b2  xor     edx, edx; pUnkOuter
0x18000f9b4  lea     r8d, [rdx+4]; dwClsContext
0x18000f9b8  lea     rcx, CLSID_AccStore; rclsid
0x18000f9bf  call    cs:__imp_CoCreateInstance
0x18000f9c5  mov     edi, eax
0x18000f9c7  test    rbp, rbp
0x18000f9ca  jnz     short loc_18000F9D7
0x18000f9cc  mov     ecx, 1F4h; dwMilliseconds
0x18000f9d1  call    cs:__imp_Sleep
0x18000f9d7  mov     eax, [rbx+8]
0x18000f9da  cmp     eax, 7FFFFFFFh
0x18000f9df  jz      short loc_18000F9E6
0x18000f9e1  dec     eax
0x18000f9e3  mov     [rbx+8], eax
0x18000f9e6  test    edi, edi
0x18000f9e8  jnz     short loc_18000FA04
0x18000f9ea  mov     rax, [rbx]
0x18000f9ed  mov     r8, rsi
0x18000f9f0  mov     rdx, r15
0x18000f9f3  mov     rcx, rbx
0x18000f9f6  mov     rax, [rax]
0x18000f9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9fe  mov     edi, eax
0x18000fa00  test    eax, eax
0x18000fa02  jz      short loc_18000FA35
0x18000fa04  lea     rax, ??_7?$CComObject@VCAccClientDocMgr@@@ATL@@6B@; const ATL::CComObject<CAccClientDocMgr>::`vftable'
0x18000fa0b  mov     [rbx], rax
0x18000fa0e  mov     dword ptr [rbx+8], 1
0x18000fa15  lock dec cs:dword_180024B28
0x18000fa1c  mov     rcx, [r14]
0x18000fa1f  mov     rdx, [rcx]
0x18000fa22  mov     rax, [rdx+10h]
0x18000fa26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa2b  nop
0x18000fa2c  mov     rcx, rbx
0x18000fa2f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fa35  mov     eax, edi
0x18000fa37  add     rsp, 38h
0x18000fa3b  pop     r15
0x18000fa3d  pop     r14
0x18000fa3f  pop     rdi
0x18000fa40  pop     rsi
0x18000fa41  pop     rbp
0x18000fa42  pop     rbx
0x18000fa43  retn
```
