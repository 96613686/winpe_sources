# EditShareAcl(HWND__ *,ushort const *,ushort const *,void *,int *,void * *)

- ea: `0x180033b18`
- end: `0x180033c53`
- name: `?EditShareAcl@@YAJPEAUHWND__@@PEBG1PEAXPEAHPEAPEAX@Z`
- size: `315`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *, void *, int *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180062d84`
- `0x180062e20`

## callees

- `0x1800259bc`
- `0x180033a38`
- `0x180033b18`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033b7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033b7c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180033be6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180033be6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180033b52`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180033b52`

## string_xrefs

- `0x180033b72`: `EditSecurity`
- `0x180033b4b`: `ACLUI.DLL`

## pseudocode

```c
__int64 __fastcall EditShareAcl(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4,
        int *a5,
        void **a6)
{
  HMODULE LibraryW; // rax
  CSecurityInformation *v10; // rax
  CSecurityInformation *v11; // rbx

  LibraryW = g_hlibACLUI;
  *a6 = 0;
  if ( LibraryW || (LibraryW = LoadLibraryW(L"ACLUI.DLL"), (g_hlibACLUI = LibraryW) != 0) )
  {
    if ( g_pfnEditSecurityProc
      || (g_pfnEditSecurityProc = (int (*)(HWND, struct ISecurityInformation *))GetProcAddress(LibraryW, "EditSecurity")) != 0 )
    {
      v10 = (CSecurityInformation *)operator new(0x1C0u, (const struct std::nothrow_t *)std::nothrow);
      v11 = v10;
      if ( v10 )
      {
        CSecurityInformation::CSecurityInformation(v10);
        *((_QWORD *)v11 + 2) = 0;
        *((_QWORD *)v11 + 3) = a3;
        *(_QWORD *)v11 = &CShareSecurityInformation::`vftable';
        LoadStringW(g_hInstance, 0x75u, (LPWSTR)v11 + 16, 200);
        *((_QWORD *)v11 + 54) = a4;
        *(_QWORD *)v11 = &CSMBSecurityInformation::`vftable';
        *((_QWORD *)v11 + 55) = a6;
        ((void (__fastcall *)(HWND, CSecurityInformation *))g_pfnEditSecurityProc)(a1, v11);
        if ( a5 )
          *a5 = *a6 != 0;
        (*(void (__fastcall **)(CSecurityInformation *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180033b18  mov     [rsp+arg_0], rbx
0x180033b1d  mov     [rsp+arg_10], rbp
0x180033b22  push    rsi
0x180033b23  push    rdi
0x180033b24  push    r14
0x180033b26  sub     rsp, 20h
0x180033b2a  mov     rdi, [rsp+38h+arg_28]
0x180033b2f  mov     rbp, r9
0x180033b32  mov     rax, cs:?g_hlibACLUI@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hlibACLUI
0x180033b39  mov     r14, r8
0x180033b3c  mov     rsi, rcx
0x180033b3f  mov     qword ptr [rdi], 0
0x180033b46  test    rax, rax
0x180033b49  jnz     short loc_180033B68
0x180033b4b  lea     rcx, aAcluiDll; "ACLUI.DLL"
0x180033b52  call    cs:__imp_LoadLibraryW
0x180033b58  mov     cs:?g_hlibACLUI@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hlibACLUI
0x180033b5f  test    rax, rax
0x180033b62  jz      loc_180033C3E
0x180033b68  cmp     cs:?g_pfnEditSecurityProc@@3P6AHPEAUHWND__@@PEAUISecurityInformation@@@ZEA, 0; int (*g_pfnEditSecurityProc)(HWND__ *,ISecurityInformation *)
0x180033b70  jnz     short loc_180033B92
0x180033b72  lea     rdx, aEditsecurity; "EditSecurity"
0x180033b79  mov     rcx, rax; hModule
0x180033b7c  call    cs:__imp_GetProcAddress
0x180033b82  mov     cs:?g_pfnEditSecurityProc@@3P6AHPEAUHWND__@@PEAUISecurityInformation@@@ZEA, rax; int (*g_pfnEditSecurityProc)(HWND__ *,ISecurityInformation *)
0x180033b89  test    rax, rax
0x180033b8c  jz      loc_180033C3E
0x180033b92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180033b99  mov     ecx, 1C0h; unsigned __int64
0x180033b9e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033ba3  mov     [rsp+38h+arg_8], rax
0x180033ba8  mov     rbx, rax
0x180033bab  test    rax, rax
0x180033bae  jz      loc_180033C3E
0x180033bb4  mov     rcx, rax; this
0x180033bb7  call    ??0CSecurityInformation@@QEAA@XZ; CSecurityInformation::CSecurityInformation(void)
0x180033bbc  mov     edx, 75h ; 'u'; uID
0x180033bc1  mov     qword ptr [rbx+10h], 0
0x180033bc9  lea     rcx, ??_7CShareSecurityInformation@@6B@; const CShareSecurityInformation::`vftable'
0x180033bd0  mov     [rbx+18h], r14
0x180033bd4  mov     [rbx], rcx
0x180033bd7  lea     r8, [rbx+20h]; lpBuffer
0x180033bdb  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180033be2  lea     r9d, [rdx+53h]; cchBufferMax
0x180033be6  call    cs:__imp_LoadStringW
0x180033bec  mov     [rbx+1B0h], rbp
0x180033bf3  lea     rax, ??_7CSMBSecurityInformation@@6B@; const CSMBSecurityInformation::`vftable'
0x180033bfa  mov     [rbx], rax
0x180033bfd  mov     [rbx+1B8h], rdi
0x180033c04  test    rbx, rbx
0x180033c07  jz      short loc_180033C3E
0x180033c09  mov     rax, cs:?g_pfnEditSecurityProc@@3P6AHPEAUHWND__@@PEAUISecurityInformation@@@ZEA; int (*g_pfnEditSecurityProc)(HWND__ *,ISecurityInformation *)
0x180033c10  mov     rdx, rbx
0x180033c13  mov     rcx, rsi
0x180033c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c1b  mov     rcx, [rsp+38h+arg_20]
0x180033c20  test    rcx, rcx
0x180033c23  jz      short loc_180033C2F
0x180033c25  xor     eax, eax
0x180033c27  cmp     [rdi], rax
0x180033c2a  setnz   al
0x180033c2d  mov     [rcx], eax
0x180033c2f  mov     rax, [rbx]
0x180033c32  mov     rcx, rbx
0x180033c35  mov     rax, [rax+10h]
0x180033c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c3e  mov     rbx, [rsp+38h+arg_0]
0x180033c43  xor     eax, eax
0x180033c45  mov     rbp, [rsp+38h+arg_10]
0x180033c4a  add     rsp, 20h
0x180033c4e  pop     r14
0x180033c50  pop     rdi
0x180033c51  pop     rsi
0x180033c52  retn
```
