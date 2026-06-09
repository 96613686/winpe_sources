# PMCIWrapper::EnsureTypeLib(void)

- ea: `0x18008bfc4`
- end: `0x18008c0f7`
- name: `?EnsureTypeLib@PMCIWrapper@@AEAAJXZ`
- size: `307`
- prototype: `__int64 __fastcall(PMCIWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18008b9b4`

## callees

- `0x18008bfc4`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x18008bff9`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x18008bff9`

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
0x18008bfc4  mov     [rsp+arg_8], rbx
0x18008bfc9  push    rdi
0x18008bfca  sub     rsp, 20h
0x18008bfce  cmp     qword ptr [rcx+18h], 0
0x18008bfd3  mov     rdi, rcx
0x18008bfd6  jz      short loc_18008BFDF
0x18008bfd8  xor     eax, eax
0x18008bfda  jmp     loc_18008C0EC
0x18008bfdf  lea     r8, [rsp+28h+ppctlib]; ppctlib
0x18008bfe4  mov     [rsp+28h+ppctlib], 0
0x18008bfed  lea     rdx, szFile; "JSSig.tlb"
0x18008bff4  mov     ecx, 1; syskind
0x18008bff9  call    cs:__imp_CreateTypeLib2
0x18008bfff  mov     ebx, eax
0x18008c001  test    eax, eax
0x18008c003  js      loc_18008C0D4
0x18008c009  mov     rcx, [rsp+28h+ppctlib]
0x18008c00e  mov     edx, 400h
0x18008c013  mov     rax, [rcx]
0x18008c016  mov     rax, [rax+50h]
0x18008c01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c01f  mov     ebx, eax
0x18008c021  test    eax, eax
0x18008c023  js      loc_18008C0D4
0x18008c029  mov     rcx, [rsp+28h+ppctlib]
0x18008c02e  lea     rdx, aScrglobtlib; "ScrGlobTlib"
0x18008c035  mov     rax, [rcx]
0x18008c038  mov     rax, [rax+20h]
0x18008c03c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c041  mov     ebx, eax
0x18008c043  test    eax, eax
0x18008c045  js      loc_18008C0D4
0x18008c04b  mov     rcx, [rsp+28h+ppctlib]
0x18008c050  lea     rdx, aScriptingGloba_0; "Scripting Global Type Library"
0x18008c057  mov     rax, [rcx]
0x18008c05a  mov     rax, [rax+38h]
0x18008c05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c063  mov     ebx, eax
0x18008c065  test    eax, eax
0x18008c067  js      short loc_18008C0D4
0x18008c069  mov     rcx, [rsp+28h+ppctlib]
0x18008c06e  mov     edx, 0Ah
0x18008c073  mov     rax, [rcx]
0x18008c076  lea     r8d, [rdx-2]
0x18008c07a  mov     rax, [rax+28h]
0x18008c07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c083  mov     ebx, eax
0x18008c085  test    eax, eax
0x18008c087  js      short loc_18008C0D4
0x18008c089  mov     rcx, [rsp+28h+ppctlib]
0x18008c08e  lea     rdx, IID_IScriptTypeLib
0x18008c095  mov     rax, [rcx]
0x18008c098  mov     rax, [rax+30h]
0x18008c09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c0a1  mov     ebx, eax
0x18008c0a3  test    eax, eax
0x18008c0a5  js      short loc_18008C0D4
0x18008c0a7  mov     rcx, [rsp+28h+ppctlib]
0x18008c0ac  xor     edx, edx
0x18008c0ae  mov     rax, [rcx]
0x18008c0b1  mov     rax, [rax+58h]
0x18008c0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c0ba  mov     ebx, eax
0x18008c0bc  test    eax, eax
0x18008c0be  js      short loc_18008C0D4
0x18008c0c0  mov     rax, [rsp+28h+ppctlib]
0x18008c0c5  xor     ecx, ecx
0x18008c0c7  mov     [rdi+18h], rax
0x18008c0cb  xor     ebx, ebx
0x18008c0cd  mov     [rsp+28h+ppctlib], rcx
0x18008c0d2  jmp     short loc_18008C0D9
0x18008c0d4  mov     rcx, [rsp+28h+ppctlib]
0x18008c0d9  test    rcx, rcx
0x18008c0dc  jz      short loc_18008C0EA
0x18008c0de  mov     rax, [rcx]
0x18008c0e1  mov     rax, [rax+10h]
0x18008c0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c0ea  mov     eax, ebx
0x18008c0ec  mov     rbx, [rsp+28h+arg_8]
0x18008c0f1  add     rsp, 20h
0x18008c0f5  pop     rdi
0x18008c0f6  retn
```
