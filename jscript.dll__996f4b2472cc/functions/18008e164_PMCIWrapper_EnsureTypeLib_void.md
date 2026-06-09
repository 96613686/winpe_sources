# PMCIWrapper::EnsureTypeLib(void)

- ea: `0x18008e164`
- end: `0x18008e29e`
- name: `?EnsureTypeLib@PMCIWrapper@@AEAAJXZ`
- size: `314`
- prototype: `__int64 __fastcall(PMCIWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18008db40`

## callees

- `0x18008e164`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x18008e199`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x18008e199`

## pseudocode

```c
__int64 __fastcall PMCIWrapper::EnsureTypeLib(PMCIWrapper *this)
{
  HRESULT v3; // ebx
  ICreateTypeLib2 *v4; // rcx
  ICreateTypeLib2 *ppctlib; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 3) )
    return 0;
  ppctlib = 0;
  v3 = CreateTypeLib2(SYS_WIN32, L"JSSig.tlb", &ppctlib);
  if ( v3 < 0
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, __int64))ppctlib->lpVtbl->SetLcid)(ppctlib, 1024), v3 < 0)
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, const wchar_t *))ppctlib->lpVtbl->SetName)(
               ppctlib,
               L"ScrGlobTlib"),
        v3 < 0)
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, const wchar_t *))ppctlib->lpVtbl->SetDocString)(
               ppctlib,
               L"Scripting Global Type Library"),
        v3 < 0)
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, __int64, __int64))ppctlib->lpVtbl->SetVersion)(ppctlib, 10, 8),
        v3 < 0)
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, GUID *))ppctlib->lpVtbl->SetGuid)(ppctlib, &IID_IScriptTypeLib),
        v3 < 0)
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, _QWORD))ppctlib->lpVtbl->SetLibFlags)(ppctlib, 0), v3 < 0) )
  {
    v4 = ppctlib;
  }
  else
  {
    v4 = 0;
    *((_QWORD *)this + 3) = ppctlib;
    v3 = 0;
    ppctlib = 0;
  }
  if ( v4 )
    ((void (__fastcall *)(ICreateTypeLib2 *))v4->lpVtbl->Release)(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18008e164  mov     [rsp+arg_8], rbx
0x18008e169  push    rdi
0x18008e16a  sub     rsp, 20h
0x18008e16e  cmp     qword ptr [rcx+18h], 0
0x18008e173  mov     rdi, rcx
0x18008e176  jz      short loc_18008E17F
0x18008e178  xor     eax, eax
0x18008e17a  jmp     loc_18008E292
0x18008e17f  lea     r8, [rsp+28h+ppctlib]; ppctlib
0x18008e184  mov     [rsp+28h+ppctlib], 0
0x18008e18d  lea     rdx, szFile; "JSSig.tlb"
0x18008e194  mov     ecx, 1; syskind
0x18008e199  call    cs:__imp_CreateTypeLib2
0x18008e1a0  nop     dword ptr [rax+rax+00h]
0x18008e1a5  mov     ebx, eax
0x18008e1a7  test    eax, eax
0x18008e1a9  js      loc_18008E27A
0x18008e1af  mov     rcx, [rsp+28h+ppctlib]
0x18008e1b4  mov     edx, 400h
0x18008e1b9  mov     rax, [rcx]
0x18008e1bc  mov     rax, [rax+50h]
0x18008e1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e1c5  mov     ebx, eax
0x18008e1c7  test    eax, eax
0x18008e1c9  js      loc_18008E27A
0x18008e1cf  mov     rcx, [rsp+28h+ppctlib]
0x18008e1d4  lea     rdx, aScrglobtlib; "ScrGlobTlib"
0x18008e1db  mov     rax, [rcx]
0x18008e1de  mov     rax, [rax+20h]
0x18008e1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e1e7  mov     ebx, eax
0x18008e1e9  test    eax, eax
0x18008e1eb  js      loc_18008E27A
0x18008e1f1  mov     rcx, [rsp+28h+ppctlib]
0x18008e1f6  lea     rdx, aScriptingGloba_0; "Scripting Global Type Library"
0x18008e1fd  mov     rax, [rcx]
0x18008e200  mov     rax, [rax+38h]
0x18008e204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e209  mov     ebx, eax
0x18008e20b  test    eax, eax
0x18008e20d  js      short loc_18008E27A
0x18008e20f  mov     rcx, [rsp+28h+ppctlib]
0x18008e214  mov     edx, 0Ah
0x18008e219  mov     rax, [rcx]
0x18008e21c  lea     r8d, [rdx-2]
0x18008e220  mov     rax, [rax+28h]
0x18008e224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e229  mov     ebx, eax
0x18008e22b  test    eax, eax
0x18008e22d  js      short loc_18008E27A
0x18008e22f  mov     rcx, [rsp+28h+ppctlib]
0x18008e234  lea     rdx, IID_IScriptTypeLib
0x18008e23b  mov     rax, [rcx]
0x18008e23e  mov     rax, [rax+30h]
0x18008e242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e247  mov     ebx, eax
0x18008e249  test    eax, eax
0x18008e24b  js      short loc_18008E27A
0x18008e24d  mov     rcx, [rsp+28h+ppctlib]
0x18008e252  xor     edx, edx
0x18008e254  mov     rax, [rcx]
0x18008e257  mov     rax, [rax+58h]
0x18008e25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e260  mov     ebx, eax
0x18008e262  test    eax, eax
0x18008e264  js      short loc_18008E27A
0x18008e266  mov     rax, [rsp+28h+ppctlib]
0x18008e26b  xor     ecx, ecx
0x18008e26d  mov     [rdi+18h], rax
0x18008e271  xor     ebx, ebx
0x18008e273  mov     [rsp+28h+ppctlib], rcx
0x18008e278  jmp     short loc_18008E27F
0x18008e27a  mov     rcx, [rsp+28h+ppctlib]
0x18008e27f  test    rcx, rcx
0x18008e282  jz      short loc_18008E290
0x18008e284  mov     rax, [rcx]
0x18008e287  mov     rax, [rax+10h]
0x18008e28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e290  mov     eax, ebx
0x18008e292  mov     rbx, [rsp+28h+arg_8]
0x18008e297  add     rsp, 20h
0x18008e29b  pop     rdi
0x18008e29c  retn
```
