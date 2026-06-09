# CSharingConfiguration::CanShareItems(IShellItemArray *)

- ea: `0x18001b180`
- end: `0x18001b382`
- name: `?CanShareItems@CSharingConfiguration@@UEAAJPEAUIShellItemArray@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(CSharingConfiguration *__hidden this, struct IShellItemArray *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18001b180`
- `0x18001d370`
- `0x180078010`

## import_xrefs

- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x18001b247`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x18001b247`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001b25c`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001b25c`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x18001b2af`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x18001b2af`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18001b28e`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18001b28e`

## pseudocode

```c
__int64 __fastcall CSharingConfiguration::CanShareItems(CSharingConfiguration *this, struct IShellItemArray *a2)
{
  HRESULT v3; // ebx
  struct IShellItemArrayVtbl *lpVtbl; // rax
  int v5; // ebx
  struct IShellItemArrayVtbl *v6; // rax
  BOOL v7; // edi
  int v9; // eax
  void *v10; // [rsp+30h] [rbp-10h] BYREF
  int v11; // [rsp+68h] [rbp+28h] BYREF
  void *ppv; // [rsp+70h] [rbp+30h] BYREF
  IShellItem *psi; // [rsp+78h] [rbp+38h] BYREF

  v3 = -2147467261;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    v11 = 0;
    ppv = 0;
    if ( ((int (__fastcall *)(struct IShellItemArray *, GUID *, void **))lpVtbl->QueryInterface)(
           a2,
           &GUID_d4c5a1a7_e152_4a59_b3f6_0190a5a6d385,
           &ppv) < 0 )
    {
      v5 = ((__int64 (__fastcall *)(struct IShellItemArray *, int *))a2->lpVtbl->GetCount)(a2, &v11);
    }
    else
    {
      v5 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppv + 24LL))(ppv, &v11);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v5 < 0 || !v11 )
      return (unsigned int)-2147024809;
    v6 = a2->lpVtbl;
    psi = 0;
    v3 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, IShellItem **))v6->GetItemAt)(a2, 0, &psi);
    if ( v3 >= 0 )
    {
      if ( SHRegGetBoolValueFromHKCUHKLM(
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
             L"SharingWizardOn",
             1)
        && !(unsigned int)SHWindowsPolicy(POLID_NoInplaceSharing) )
      {
        ppv = 0;
        v3 = SHCoCreateInstance(0, &CLSID_InplaceShareEngine, 0, &GUID_559b1911_d3af_486e_b8bc_242b24df0114, &ppv);
        if ( v3 < 0 )
          goto LABEL_12;
        v7 = 0;
        v10 = 0;
        v3 = SHCreateShellItemArrayFromShellItem(psi, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &v10);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(void *, void *))(*(_QWORD *)ppv + 32LL))(ppv, v10);
          if ( v3 >= 0 )
            v7 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppv + 96LL))(ppv) == 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( v3 < 0 )
          goto LABEL_12;
        if ( v7 )
          goto LABEL_22;
      }
      if ( v11 == 1 )
      {
        v9 = CanShareSMB(psi);
        v3 = v9;
        if ( v9 < 0 )
        {
LABEL_12:
          ((void (__fastcall *)(IShellItem *))psi->lpVtbl->Release)(psi);
          return (unsigned int)v3;
        }
        if ( !v9 )
        {
LABEL_22:
          v3 = 0;
          goto LABEL_12;
        }
      }
      v3 = 1;
      goto LABEL_12;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001b180  mov     [rsp-18h+arg_0], rbx
0x18001b185  push    rbp
0x18001b186  push    rdi
0x18001b187  push    r14
0x18001b189  mov     rbp, rsp
0x18001b18c  sub     rsp, 40h
0x18001b190  mov     rdi, rdx
0x18001b193  mov     ebx, 80004003h
0x18001b198  test    rdx, rdx
0x18001b19b  jz      loc_18001B2DF
0x18001b1a1  mov     rax, [rdx]
0x18001b1a4  lea     r8, [rbp+arg_10]
0x18001b1a8  lea     rdx, _GUID_d4c5a1a7_e152_4a59_b3f6_0190a5a6d385
0x18001b1af  mov     [rbp+arg_8], 0
0x18001b1b6  mov     rcx, rdi
0x18001b1b9  mov     [rbp+arg_10], 0
0x18001b1c1  mov     rax, [rax]
0x18001b1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1c9  lea     rdx, [rbp+arg_8]
0x18001b1cd  test    eax, eax
0x18001b1cf  js      loc_18001B2EF
0x18001b1d5  mov     rcx, [rbp+arg_10]
0x18001b1d9  mov     rax, [rcx]
0x18001b1dc  mov     rax, [rax+18h]
0x18001b1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1e5  mov     rcx, [rbp+arg_10]
0x18001b1e9  mov     ebx, eax
0x18001b1eb  mov     rax, [rcx]
0x18001b1ee  mov     rax, [rax+10h]
0x18001b1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1f7  test    ebx, ebx
0x18001b1f9  js      loc_18001B378
0x18001b1ff  cmp     [rbp+arg_8], 0
0x18001b203  jbe     loc_18001B378
0x18001b209  mov     rax, [rdi]
0x18001b20c  lea     r8, [rbp+psi]
0x18001b210  xor     edx, edx
0x18001b212  mov     [rbp+psi], 0
0x18001b21a  mov     rcx, rdi
0x18001b21d  mov     rax, [rax+40h]
0x18001b221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b226  mov     ebx, eax
0x18001b228  test    eax, eax
0x18001b22a  js      loc_18001B2DF
0x18001b230  mov     r14d, 1
0x18001b236  lea     rdx, pszValue; "SharingWizardOn"
0x18001b23d  mov     r8d, r14d; fDefault
0x18001b240  lea     rcx, pszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001b247  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x18001b24d  test    eax, eax
0x18001b24f  jz      loc_18001B34E
0x18001b255  lea     rcx, POLID_NoInplaceSharing
0x18001b25c  call    cs:__imp_SHWindowsPolicy
0x18001b262  test    eax, eax
0x18001b264  jnz     loc_18001B34E
0x18001b26a  lea     rax, [rbp+arg_10]
0x18001b26e  mov     [rbp+arg_10], 0
0x18001b276  lea     r9, _GUID_559b1911_d3af_486e_b8bc_242b24df0114; riid
0x18001b27d  mov     [rsp+40h+ppv], rax; ppv
0x18001b282  xor     r8d, r8d; pUnkOuter
0x18001b285  lea     rdx, CLSID_InplaceShareEngine; pclsid
0x18001b28c  xor     ecx, ecx; pszCLSID
0x18001b28e  call    cs:__imp_SHCoCreateInstance
0x18001b294  mov     ebx, eax
0x18001b296  test    eax, eax
0x18001b298  js      short loc_18001B2CF
0x18001b29a  mov     rcx, [rbp+psi]; psi
0x18001b29e  lea     r8, [rbp+var_10]; ppv
0x18001b2a2  xor     edi, edi
0x18001b2a4  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x18001b2ab  mov     [rbp+var_10], rdi
0x18001b2af  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x18001b2b5  mov     ebx, eax
0x18001b2b7  test    eax, eax
0x18001b2b9  jns     short loc_18001B305
0x18001b2bb  mov     rcx, [rbp+arg_10]
0x18001b2bf  mov     rax, [rcx]
0x18001b2c2  mov     rax, [rax+10h]
0x18001b2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2cb  test    ebx, ebx
0x18001b2cd  jns     short loc_18001B34A
0x18001b2cf  mov     rcx, [rbp+psi]
0x18001b2d3  mov     rax, [rcx]
0x18001b2d6  mov     rax, [rax+10h]
0x18001b2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2df  mov     eax, ebx
0x18001b2e1  mov     rbx, [rsp+40h+arg_0]
0x18001b2e6  add     rsp, 40h
0x18001b2ea  pop     r14
0x18001b2ec  pop     rdi
0x18001b2ed  pop     rbp
0x18001b2ee  retn
0x18001b2ef  mov     rax, [rdi]
0x18001b2f2  mov     rcx, rdi
0x18001b2f5  mov     rax, [rax+38h]
0x18001b2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2fe  mov     ebx, eax
0x18001b300  jmp     loc_18001B1F7
0x18001b305  mov     rcx, [rbp+arg_10]
0x18001b309  mov     rdx, [rbp+var_10]
0x18001b30d  mov     rax, [rcx]
0x18001b310  mov     rax, [rax+20h]
0x18001b314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b319  mov     ebx, eax
0x18001b31b  test    eax, eax
0x18001b31d  js      short loc_18001B335
0x18001b31f  mov     rcx, [rbp+arg_10]
0x18001b323  mov     rax, [rcx]
0x18001b326  mov     rax, [rax+60h]
0x18001b32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b32f  test    eax, eax
0x18001b331  cmovz   edi, r14d
0x18001b335  mov     rcx, [rbp+var_10]
0x18001b339  mov     rax, [rcx]
0x18001b33c  mov     rax, [rax+10h]
0x18001b340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b345  jmp     loc_18001B2BB
0x18001b34a  test    edi, edi
0x18001b34c  jnz     short loc_18001B369
0x18001b34e  cmp     [rbp+arg_8], r14d
0x18001b352  jnz     short loc_18001B370
0x18001b354  mov     rcx, [rbp+psi]; struct IShellItem *
0x18001b358  call    ?CanShareSMB@@YAJPEAUIShellItem@@@Z; CanShareSMB(IShellItem *)
0x18001b35d  mov     ebx, eax
0x18001b35f  test    eax, eax
0x18001b361  js      loc_18001B2CF
0x18001b367  jnz     short loc_18001B370
0x18001b369  xor     ebx, ebx
0x18001b36b  jmp     loc_18001B2CF
0x18001b370  mov     ebx, r14d
0x18001b373  jmp     loc_18001B2CF
0x18001b378  mov     ebx, 80070057h
0x18001b37d  jmp     loc_18001B2DF
```
