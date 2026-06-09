# CContextMenuOverExplorerCommands::_PopulateSubMenu(HMENU__ *)

- ea: `0x180073c08`
- end: `0x180073d5f`
- name: `?_PopulateSubMenu@CContextMenuOverExplorerCommands@@AEAAJPEAUHMENU__@@@Z`
- size: `343`
- prototype: `int(CContextMenuOverExplorerCommands *__hidden this, HMENU)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180073af0`

## callees

- `0x180073c08`
- `0x180078010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x180073cb5`
- `SHCORE!IUnknown_SetSite` at `0x180073cb5`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180073c5f`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180073c5f`
- `USER32!DeleteMenu` at `0x180073c25`
- `USER32!DeleteMenu` at `0x180073c25`

## pseudocode

```c
__int64 __fastcall CContextMenuOverExplorerCommands::_PopulateSubMenu(CContextMenuOverExplorerCommands *this, HMENU a2)
{
  IUnknown **v4; // rsi
  HRESULT v5; // ebx
  IUnknown *v6; // rcx
  void *ppv; // [rsp+60h] [rbp+8h] BYREF
  __int64 v9; // [rsp+70h] [rbp+18h] BYREF

  DeleteMenu(a2, 0, 0x400u);
  v4 = (IUnknown **)((char *)this + 64);
  if ( *((_QWORD *)this + 8) )
    return ((unsigned int (__fastcall *)(IUnknown *, HMENU, _QWORD, _QWORD, _DWORD, _DWORD))(*v4)->lpVtbl[1].QueryInterface)(
             *v4,
             a2,
             0,
             *((unsigned int *)this + 29),
             *((_DWORD *)this + 30),
             0);
  ppv = 0;
  v5 = SHCoCreateInstance(0, &CLSID_EnumExplorerCommandOnMenu, 0, &GUID_974fc285_a627_490d_a293_0f5e8ab987fe, &ppv);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, *((_QWORD *)this + 7));
    if ( v5 >= 0 )
    {
      v5 = (**(__int64 (__fastcall ***)(void *, GUID *, char *))ppv)(
             ppv,
             &GUID_000214e4_0000_0000_c000_000000000046,
             (char *)this + 64);
      if ( v5 >= 0 )
      {
        IUnknown_SetSite(*v4, *((IUnknown **)this + 2));
        v6 = *v4;
        v9 = 0;
        v5 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))v6->lpVtbl->QueryInterface)(
               v6,
               &GUID_000214e8_0000_0000_c000_000000000046,
               &v9);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 24LL))(
                 v9,
                 0,
                 *((_QWORD *)this + 9),
                 0);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v5 >= 0 )
      return ((unsigned int (__fastcall *)(IUnknown *, HMENU, _QWORD, _QWORD, _DWORD, _DWORD))(*v4)->lpVtbl[1].QueryInterface)(
               *v4,
               a2,
               0,
               *((unsigned int *)this + 29),
               *((_DWORD *)this + 30),
               0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180073c08  mov     [rsp+arg_8], rbx
0x180073c0d  push    rbp
0x180073c0e  push    rsi
0x180073c0f  push    rdi
0x180073c10  sub     rsp, 40h
0x180073c14  mov     rbp, rdx
0x180073c17  mov     rdi, rcx
0x180073c1a  mov     rcx, rbp; hMenu
0x180073c1d  xor     edx, edx; uPosition
0x180073c1f  mov     r8d, 400h; uFlags
0x180073c25  call    cs:__imp_DeleteMenu
0x180073c2b  lea     rsi, [rdi+40h]
0x180073c2f  cmp     qword ptr [rsi], 0
0x180073c33  jnz     loc_180073D26
0x180073c39  lea     rax, [rsp+58h+arg_0]
0x180073c3e  mov     [rsp+58h+arg_0], 0
0x180073c47  lea     r9, _GUID_974fc285_a627_490d_a293_0f5e8ab987fe; riid
0x180073c4e  mov     [rsp+58h+ppv], rax; ppv
0x180073c53  xor     r8d, r8d; pUnkOuter
0x180073c56  lea     rdx, CLSID_EnumExplorerCommandOnMenu; pclsid
0x180073c5d  xor     ecx, ecx; pszCLSID
0x180073c5f  call    cs:__imp_SHCoCreateInstance
0x180073c65  mov     ebx, eax
0x180073c67  test    eax, eax
0x180073c69  js      loc_180073D50
0x180073c6f  mov     rcx, [rsp+58h+arg_0]
0x180073c74  mov     rdx, [rdi+38h]
0x180073c78  mov     rax, [rcx]
0x180073c7b  mov     rax, [rax+18h]
0x180073c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073c84  mov     ebx, eax
0x180073c86  test    eax, eax
0x180073c88  js      loc_180073D11
0x180073c8e  mov     rcx, [rsp+58h+arg_0]
0x180073c93  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046
0x180073c9a  mov     r8, rsi
0x180073c9d  mov     rax, [rcx]
0x180073ca0  mov     rax, [rax]
0x180073ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ca8  mov     ebx, eax
0x180073caa  test    eax, eax
0x180073cac  js      short loc_180073D11
0x180073cae  mov     rdx, [rdi+10h]; punkSite
0x180073cb2  mov     rcx, [rsi]; punk
0x180073cb5  call    cs:__imp_IUnknown_SetSite
0x180073cbb  mov     rcx, [rsi]
0x180073cbe  lea     r8, [rsp+58h+arg_10]
0x180073cc3  mov     [rsp+58h+arg_10], 0
0x180073ccc  lea     rdx, _GUID_000214e8_0000_0000_c000_000000000046
0x180073cd3  mov     rax, [rcx]
0x180073cd6  mov     rax, [rax]
0x180073cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073cde  mov     ebx, eax
0x180073ce0  test    eax, eax
0x180073ce2  js      short loc_180073D11
0x180073ce4  mov     rcx, [rsp+58h+arg_10]
0x180073ce9  xor     r9d, r9d
0x180073cec  mov     r8, [rdi+48h]
0x180073cf0  xor     edx, edx
0x180073cf2  mov     rax, [rcx]
0x180073cf5  mov     rax, [rax+18h]
0x180073cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073cfe  mov     rcx, [rsp+58h+arg_10]
0x180073d03  mov     ebx, eax
0x180073d05  mov     rax, [rcx]
0x180073d08  mov     rax, [rax+10h]
0x180073d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d11  mov     rcx, [rsp+58h+arg_0]
0x180073d16  mov     rax, [rcx]
0x180073d19  mov     rax, [rax+10h]
0x180073d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d22  test    ebx, ebx
0x180073d24  js      short loc_180073D50
0x180073d26  mov     edx, [rdi+78h]
0x180073d29  xor     r8d, r8d
0x180073d2c  mov     rcx, [rsi]
0x180073d2f  mov     r9d, [rdi+74h]
0x180073d33  mov     [rsp+58h+var_30], 0
0x180073d3b  mov     dword ptr [rsp+58h+ppv], edx
0x180073d3f  mov     rdx, rbp
0x180073d42  mov     rax, [rcx]
0x180073d45  mov     rax, [rax+18h]
0x180073d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d4e  mov     ebx, eax
0x180073d50  mov     eax, ebx
0x180073d52  mov     rbx, [rsp+58h+arg_8]
0x180073d57  add     rsp, 40h
0x180073d5b  pop     rdi
0x180073d5c  pop     rsi
0x180073d5d  pop     rbp
0x180073d5e  retn
```
