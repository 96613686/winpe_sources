# CSinkWrapAnchor::CreateRange(IAnchor *,IAnchor *,ITfRangeAnchor * *)

- ea: `0x180006ee0`
- end: `0x180006fcd`
- name: `?CreateRange@CSinkWrapAnchor@@UEAAJPEAUIAnchor@@0PEAPEAUITfRangeAnchor@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(CSinkWrapAnchor *__hidden this, struct IAnchor *, struct IAnchor *, struct ITfRangeAnchor **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800026d0`
- `0x180006ee0`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSinkWrapAnchor::CreateRange(
        CSinkWrapAnchor *this,
        struct IAnchor *a2,
        struct IAnchor *a3,
        struct ITfRangeAnchor **a4)
{
  __int64 **v7; // rbx
  __int64 i; // rbx
  unsigned int (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-48h]
  __int64 v13; // [rsp+70h] [rbp+8h] BYREF

  v7 = (__int64 **)((char *)this + 32);
  if ( !*((_QWORD *)this + 3) || !*v7 )
    InternalTrace(L"windows\\oleacc\\msaatext\\docwrap.cpp", 0x894u, 8u, 0, v12, 0, (wchar_t *)L"m_pMgr && m_pDocs");
  for ( i = **v7; ; i = *(_QWORD *)(i + 8) )
  {
    if ( !i )
      return 2147500037LL;
    v9 = *(unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *))(i + 24);
    if ( v9 )
      break;
LABEL_10:
    ;
  }
  v13 = 0;
  if ( (**v9)(v9, &GUID_aa80e9fe_2021_11d2_93e0_0060b067b86e, &v13) )
  {
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_10;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, struct IAnchor *, struct IAnchor *, struct ITfRangeAnchor **))(*(_QWORD *)v13 + 48LL))(
          v13,
          a2,
          a3,
          a4);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return v10;
}

```

## disassembly

```asm
0x180006ee0  push    rbx
0x180006ee2  push    rbp
0x180006ee3  push    rsi
0x180006ee4  push    rdi
0x180006ee5  sub     rsp, 48h
0x180006ee9  mov     rdi, r9
0x180006eec  mov     rsi, r8
0x180006eef  mov     rbp, rdx
0x180006ef2  lea     rbx, [rcx+20h]
0x180006ef6  cmp     qword ptr [rcx+18h], 0
0x180006efb  jz      short loc_180006F03
0x180006efd  cmp     qword ptr [rbx], 0
0x180006f01  jnz     short loc_180006F2F
0x180006f03  lea     rax, aMPmgrMPdocs; "m_pMgr && m_pDocs"
0x180006f0a  mov     [rsp+68h+var_38], rax; __int64
0x180006f0f  mov     [rsp+68h+var_40], 0; int
0x180006f17  xor     r9d, r9d
0x180006f1a  mov     edx, 894h; Value
0x180006f1f  lea     r8d, [r9+8]
0x180006f23  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180006f2a  call    InternalTrace
0x180006f2f  mov     rbx, [rbx]
0x180006f32  mov     rbx, [rbx]
0x180006f35  test    rbx, rbx
0x180006f38  jz      loc_180006FBF
0x180006f3e  mov     rcx, [rbx+18h]
0x180006f42  test    rcx, rcx
0x180006f45  jz      short loc_180006F82
0x180006f47  mov     [rsp+68h+arg_0], 0
0x180006f50  mov     rax, [rcx]
0x180006f53  lea     r8, [rsp+68h+arg_0]
0x180006f58  lea     rdx, _GUID_aa80e9fe_2021_11d2_93e0_0060b067b86e
0x180006f5f  mov     rax, [rax]
0x180006f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f67  test    eax, eax
0x180006f69  jz      short loc_180006F88
0x180006f6b  mov     rcx, [rsp+68h+arg_0]
0x180006f70  test    rcx, rcx
0x180006f73  jz      short loc_180006F82
0x180006f75  mov     rax, [rcx]
0x180006f78  mov     rax, [rax+10h]
0x180006f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f81  nop
0x180006f82  mov     rbx, [rbx+8]
0x180006f86  jmp     short loc_180006F35
0x180006f88  mov     rcx, [rsp+68h+arg_0]
0x180006f8d  mov     rax, [rcx]
0x180006f90  mov     r9, rdi
0x180006f93  mov     r8, rsi
0x180006f96  mov     rdx, rbp
0x180006f99  mov     rax, [rax+30h]
0x180006f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa2  mov     ebx, eax
0x180006fa4  mov     rcx, [rsp+68h+arg_0]
0x180006fa9  test    rcx, rcx
0x180006fac  jz      short loc_180006FBB
0x180006fae  mov     rdx, [rcx]
0x180006fb1  mov     rax, [rdx+10h]
0x180006fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fba  nop
0x180006fbb  mov     eax, ebx
0x180006fbd  jmp     short loc_180006FC4
0x180006fbf  mov     eax, 80004005h
0x180006fc4  add     rsp, 48h
0x180006fc8  pop     rdi
0x180006fc9  pop     rsi
0x180006fca  pop     rbp
0x180006fcb  pop     rbx
0x180006fcc  retn
```
