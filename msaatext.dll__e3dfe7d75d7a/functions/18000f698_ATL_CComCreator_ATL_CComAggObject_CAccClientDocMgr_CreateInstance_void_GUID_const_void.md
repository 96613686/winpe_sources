# ATL::CComCreator<ATL::CComAggObject<CAccClientDocMgr>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f698`
- end: `0x18000f7e0`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCAccClientDocMgr@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000f2d0`

## callees

- `0x180001370`
- `0x18000f698`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f7c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f7c1`
- `KERNEL32!Sleep` at `0x18000f779`
- `KERNEL32!Sleep` at `0x18000f779`
- `KERNEL32!CloseHandle` at `0x18000f744`
- `KERNEL32!CloseHandle` at `0x18000f744`
- `KERNEL32!OpenEventW` at `0x18000f733`
- `KERNEL32!OpenEventW` at `0x18000f733`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f767`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f767`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CAccClientDocMgr>>::CreateInstance(
        void *a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int Instance; // edi
  LPVOID *v8; // rax
  LPVOID *v9; // rbx
  HANDLE v10; // rax
  HANDLE v11; // rsi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  Instance = -2147024882;
  v8 = (LPVOID *)operator new(0x28u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CAccClientDocMgr>::`vftable';
    v8[4] = 0;
    v8[2] = &ATL::CComContainedObject<CAccClientDocMgr>::`vftable';
    v8[3] = a1;
    _InterlockedIncrement(&dword_180024B28);
    v10 = OpenEventW(0x100000u, 0, L"MSAA_STORE_EVENT");
    v11 = v10;
    if ( v10 )
      CloseHandle(v10);
    Instance = CoCreateInstance(&CLSID_AccStore, 0, 4u, &IID_IAccStore, v9 + 4);
    if ( !v11 )
      Sleep(0x1F4u);
    if ( Instance || (Instance = (*(__int64 (__fastcall **)(LPVOID *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
    {
      *v9 = &ATL::CComAggObject<CAccClientDocMgr>::`vftable';
      *((_DWORD *)v9 + 2) = 1;
      _InterlockedDecrement(&dword_180024B28);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9[4] + 16LL))(v9[4]);
      operator delete(v9);
    }
  }
  return Instance;
}

```

## disassembly

```asm
0x18000f698  mov     [rsp+arg_0], rbx
0x18000f69d  mov     [rsp+arg_8], rbp
0x18000f6a2  push    rsi
0x18000f6a3  push    rdi
0x18000f6a4  push    r13
0x18000f6a6  push    r14
0x18000f6a8  push    r15
0x18000f6aa  sub     rsp, 30h
0x18000f6ae  mov     r14, r8
0x18000f6b1  mov     rbp, rdx
0x18000f6b4  mov     rsi, rcx
0x18000f6b7  test    r8, r8
0x18000f6ba  jnz     short loc_18000F6C6
0x18000f6bc  mov     eax, 80004003h
0x18000f6c1  jmp     loc_18000F7C9
0x18000f6c6  mov     qword ptr [r8], 0
0x18000f6cd  mov     edi, 8007000Eh
0x18000f6d2  mov     ecx, 28h ; '('; Size
0x18000f6d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f6dc  mov     rbx, rax
0x18000f6df  mov     [rsp+58h+arg_10], rax
0x18000f6e4  test    rax, rax
0x18000f6e7  jz      loc_18000F7C7
0x18000f6ed  mov     dword ptr [rax+8], 0
0x18000f6f4  lea     r13, ??_7?$CComAggObject@VCAccClientDocMgr@@@ATL@@6B@; const ATL::CComAggObject<CAccClientDocMgr>::`vftable'
0x18000f6fb  mov     [rax], r13
0x18000f6fe  mov     qword ptr [rax+20h], 0
0x18000f706  lea     rax, ??_7?$CComContainedObject@VCAccClientDocMgr@@@ATL@@6B@; const ATL::CComContainedObject<CAccClientDocMgr>::`vftable'
0x18000f70d  mov     [rbx+10h], rax
0x18000f711  mov     [rbx+18h], rsi
0x18000f715  lock inc cs:dword_180024B28
0x18000f71c  test    rbx, rbx
0x18000f71f  jz      loc_18000F7C7
0x18000f725  lea     r8, aMsaaStoreEvent; "MSAA_STORE_EVENT"
0x18000f72c  xor     edx, edx; bInheritHandle
0x18000f72e  mov     ecx, 100000h; dwDesiredAccess
0x18000f733  call    cs:__imp_OpenEventW
0x18000f739  mov     rsi, rax
0x18000f73c  test    rax, rax
0x18000f73f  jz      short loc_18000F74A
0x18000f741  mov     rcx, rax; hObject
0x18000f744  call    cs:__imp_CloseHandle
0x18000f74a  lea     r15, [rbx+20h]
0x18000f74e  mov     [rsp+58h+ppv], r15; ppv
0x18000f753  lea     r9, IID_IAccStore; riid
0x18000f75a  xor     edx, edx; pUnkOuter
0x18000f75c  lea     r8d, [rdx+4]; dwClsContext
0x18000f760  lea     rcx, CLSID_AccStore; rclsid
0x18000f767  call    cs:__imp_CoCreateInstance
0x18000f76d  mov     edi, eax
0x18000f76f  test    rsi, rsi
0x18000f772  jnz     short loc_18000F77F
0x18000f774  mov     ecx, 1F4h; dwMilliseconds
0x18000f779  call    cs:__imp_Sleep
0x18000f77f  test    edi, edi
0x18000f781  jnz     short loc_18000F79D
0x18000f783  mov     rax, [rbx]
0x18000f786  mov     r8, r14
0x18000f789  mov     rdx, rbp
0x18000f78c  mov     rcx, rbx
0x18000f78f  mov     rax, [rax]
0x18000f792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f797  mov     edi, eax
0x18000f799  test    eax, eax
0x18000f79b  jz      short loc_18000F7C7
0x18000f79d  mov     [rbx], r13
0x18000f7a0  mov     dword ptr [rbx+8], 1
0x18000f7a7  lock dec cs:dword_180024B28
0x18000f7ae  mov     rcx, [r15]
0x18000f7b1  mov     rax, [rcx]
0x18000f7b4  mov     rax, [rax+10h]
0x18000f7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7bd  nop
0x18000f7be  mov     rcx, rbx
0x18000f7c1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f7c7  mov     eax, edi
0x18000f7c9  mov     rbx, [rsp+58h+arg_0]
0x18000f7ce  mov     rbp, [rsp+58h+arg_8]
0x18000f7d3  add     rsp, 30h
0x18000f7d7  pop     r15
0x18000f7d9  pop     r14
0x18000f7db  pop     r13
0x18000f7dd  pop     rdi
0x18000f7de  pop     rsi
0x18000f7df  retn
```
