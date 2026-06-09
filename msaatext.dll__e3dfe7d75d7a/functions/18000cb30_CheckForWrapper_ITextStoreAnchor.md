# CheckForWrapper(ITextStoreAnchor * *)

- ea: `0x18000cb30`
- end: `0x18000cc8e`
- name: `?CheckForWrapper@@YAHPEAPEAUITextStoreAnchor@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(struct ITextStoreAnchor **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cca0`

## callees

- `0x18000cb30`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cba7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cba7`

## pseudocode

```c
__int64 __fastcall CheckForWrapper(struct ITextStoreAnchor **a1)
{
  int v3; // eax
  LPVOID v4; // rcx
  int v5; // ebx
  LPVOID ppv; // [rsp+50h] [rbp+20h] BYREF
  __int64 v7; // [rsp+58h] [rbp+28h] BYREF
  struct ITextStoreAnchor *v8; // [rsp+60h] [rbp+30h] BYREF

  v7 = 0;
  if ( !((__int64 (__fastcall *)(_QWORD, GUID *, __int64 *))(*a1)->lpVtbl->QueryInterface)(
          *a1,
          &IID_IClonableWrapper,
          &v7)
    && v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    return 1;
  }
  ppv = 0;
  if ( !CoCreateInstance(&CLSID_DocWrap, 0, 0x15u, &IID_IDocWrap, &ppv) && ppv )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, GUID *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, &IID_ITextStoreAnchor, *a1);
    v4 = ppv;
    if ( !v3 )
    {
      v8 = 0;
      v5 = (*(__int64 (__fastcall **)(LPVOID, GUID *, struct ITextStoreAnchor **))(*(_QWORD *)ppv + 32LL))(
             ppv,
             &IID_ITextStoreAnchor,
             &v8);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v5 || !v8 )
        return 0;
      v7 = 0;
      if ( !((unsigned __int64 (__fastcall *)(struct ITextStoreAnchor *, GUID *, __int64 *))v8->lpVtbl->QueryInterface)(
              v8,
              &IID_IClonableWrapper,
              &v7)
        && v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        ((void (__fastcall *)(_QWORD))(*a1)->lpVtbl->Release)(*a1);
        *a1 = v8;
        return 1;
      }
      v4 = v8;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18000cb30  push    rbp
0x18000cb32  push    rbx
0x18000cb33  push    rdi
0x18000cb34  mov     rbp, rsp
0x18000cb37  sub     rsp, 30h
0x18000cb3b  mov     rdi, rcx
0x18000cb3e  mov     [rbp+arg_8], 0
0x18000cb46  mov     rcx, [rcx]
0x18000cb49  lea     r8, [rbp+arg_8]
0x18000cb4d  lea     rdx, IID_IClonableWrapper
0x18000cb54  mov     rax, [rcx]
0x18000cb57  mov     rax, [rax]
0x18000cb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb5f  test    eax, eax
0x18000cb61  jnz     short loc_18000CB82
0x18000cb63  mov     rcx, [rbp+arg_8]
0x18000cb67  test    rcx, rcx
0x18000cb6a  jz      short loc_18000CB82
0x18000cb6c  mov     rax, [rcx]
0x18000cb6f  mov     rax, [rax+10h]
0x18000cb73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb78  mov     eax, 1
0x18000cb7d  jmp     loc_18000CC86
0x18000cb82  xor     edx, edx; pUnkOuter
0x18000cb84  mov     [rbp+arg_0], 0
0x18000cb8c  lea     rax, [rbp+arg_0]
0x18000cb90  lea     r9, IID_IDocWrap; riid
0x18000cb97  mov     [rsp+30h+ppv], rax; ppv
0x18000cb9c  lea     rcx, CLSID_DocWrap; rclsid
0x18000cba3  lea     r8d, [rdx+15h]; dwClsContext
0x18000cba7  call    cs:__imp_CoCreateInstance
0x18000cbad  test    eax, eax
0x18000cbaf  jnz     loc_18000CC84
0x18000cbb5  mov     rcx, [rbp+arg_0]
0x18000cbb9  test    rcx, rcx
0x18000cbbc  jz      loc_18000CC84
0x18000cbc2  mov     rax, [rcx]
0x18000cbc5  lea     rdx, IID_ITextStoreAnchor
0x18000cbcc  mov     r8, [rdi]
0x18000cbcf  mov     rax, [rax+18h]
0x18000cbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbd8  mov     rcx, [rbp+arg_0]
0x18000cbdc  test    eax, eax
0x18000cbde  jnz     loc_18000CC78
0x18000cbe4  mov     [rbp+arg_10], 0
0x18000cbec  lea     r8, [rbp+arg_10]
0x18000cbf0  mov     rax, [rcx]
0x18000cbf3  lea     rdx, IID_ITextStoreAnchor
0x18000cbfa  mov     rax, [rax+20h]
0x18000cbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc03  mov     rcx, [rbp+arg_0]
0x18000cc07  mov     ebx, eax
0x18000cc09  mov     rdx, [rcx]
0x18000cc0c  mov     rax, [rdx+10h]
0x18000cc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc15  test    ebx, ebx
0x18000cc17  jnz     short loc_18000CC84
0x18000cc19  mov     rcx, [rbp+arg_10]
0x18000cc1d  test    rcx, rcx
0x18000cc20  jz      short loc_18000CC84
0x18000cc22  mov     [rbp+arg_8], 0
0x18000cc2a  lea     r8, [rbp+arg_8]
0x18000cc2e  mov     rax, [rcx]
0x18000cc31  lea     rdx, IID_IClonableWrapper
0x18000cc38  mov     rax, [rax]
0x18000cc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc40  test    eax, eax
0x18000cc42  jnz     short loc_18000CC74
0x18000cc44  mov     rcx, [rbp+arg_8]
0x18000cc48  test    rcx, rcx
0x18000cc4b  jz      short loc_18000CC74
0x18000cc4d  mov     rax, [rcx]
0x18000cc50  mov     rax, [rax+10h]
0x18000cc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc59  mov     rcx, [rdi]
0x18000cc5c  mov     rax, [rcx]
0x18000cc5f  mov     rax, [rax+10h]
0x18000cc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc68  mov     rax, [rbp+arg_10]
0x18000cc6c  mov     [rdi], rax
0x18000cc6f  jmp     loc_18000CB78
0x18000cc74  mov     rcx, [rbp+arg_10]
0x18000cc78  mov     rax, [rcx]
0x18000cc7b  mov     rax, [rax+10h]
0x18000cc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc84  xor     eax, eax
0x18000cc86  add     rsp, 30h
0x18000cc8a  pop     rdi
0x18000cc8b  pop     rbx
0x18000cc8c  pop     rbp
0x18000cc8d  retn
```
