# ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)

- ea: `0x140001f68`
- end: `0x140002070`
- name: `??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400031f4`

## callees

- `0x140001f68`
- `0x140007010`

## pseudocode

```c
void (__fastcall ***__fastcall ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(
        __int64 *a1,
        void (__fastcall ****a2)(_QWORD, GUID *, __int64 *)))(_QWORD, GUID *, __int64 *)
{
  void (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rdi
  void (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v6; // rcx
  bool v7; // di
  void (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v9; // rdi
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF
  __int64 v12; // [rsp+38h] [rbp+10h] BYREF

  v2 = *a2;
  v4 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
  if ( !v4 )
  {
    if ( !v2 )
      return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
    goto LABEL_10;
  }
  if ( !v2 )
    goto LABEL_10;
  v11 = 0;
  v12 = 0;
  (**v4)(v4, &GUID_00000000_0000_0000_c000_000000000046, &v11);
  (**v2)(v2, &GUID_00000000_0000_0000_c000_000000000046, &v12);
  v6 = v11;
  v7 = v11 == v12;
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v6 = v11;
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( !v7 )
  {
LABEL_10:
    v8 = *a2;
    v9 = *a1;
    *a1 = 0;
    if ( v8 )
      (**v8)(v8, &GUID_00020401_0000_0000_c000_000000000046, a1);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
}

```

## disassembly

```asm
0x140001f68  mov     [rsp+arg_10], rbx
0x140001f6d  mov     [rsp+arg_18], rsi
0x140001f72  push    rdi
0x140001f73  sub     rsp, 20h
0x140001f77  mov     rdi, [rdx]
0x140001f7a  mov     rbx, rcx
0x140001f7d  mov     rcx, [rcx]
0x140001f80  mov     rsi, rdx
0x140001f83  test    rcx, rcx
0x140001f86  jnz     short loc_140001F96
0x140001f88  test    rdi, rdi
0x140001f8b  jnz     loc_140002022
0x140001f91  jmp     loc_14000205D
0x140001f96  test    rdi, rdi
0x140001f99  jz      loc_140002022
0x140001f9f  mov     [rsp+28h+arg_0], 0
0x140001fa8  lea     r8, [rsp+28h+arg_0]
0x140001fad  mov     [rsp+28h+arg_8], 0
0x140001fb6  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140001fbd  mov     rax, [rcx]
0x140001fc0  mov     rax, [rax]
0x140001fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fc8  mov     rax, [rdi]
0x140001fcb  lea     r8, [rsp+28h+arg_8]
0x140001fd0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140001fd7  mov     rcx, rdi
0x140001fda  mov     rax, [rax]
0x140001fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fe2  mov     rdx, [rsp+28h+arg_8]
0x140001fe7  mov     rcx, [rsp+28h+arg_0]
0x140001fec  cmp     rcx, rdx
0x140001fef  setz    dil
0x140001ff3  test    rdx, rdx
0x140001ff6  jz      short loc_14000200C
0x140001ff8  mov     rax, [rdx]
0x140001ffb  mov     rcx, rdx
0x140001ffe  mov     rax, [rax+10h]
0x140002002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002007  mov     rcx, [rsp+28h+arg_0]
0x14000200c  test    rcx, rcx
0x14000200f  jz      short loc_14000201D
0x140002011  mov     rax, [rcx]
0x140002014  mov     rax, [rax+10h]
0x140002018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000201d  test    dil, dil
0x140002020  jnz     short loc_14000205D
0x140002022  mov     rcx, [rsi]
0x140002025  mov     rdi, [rbx]
0x140002028  mov     qword ptr [rbx], 0
0x14000202f  test    rcx, rcx
0x140002032  jz      short loc_140002049
0x140002034  mov     rax, [rcx]
0x140002037  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x14000203e  mov     r8, rbx
0x140002041  mov     rax, [rax]
0x140002044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002049  test    rdi, rdi
0x14000204c  jz      short loc_14000205D
0x14000204e  mov     rax, [rdi]
0x140002051  mov     rcx, rdi
0x140002054  mov     rax, [rax+10h]
0x140002058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000205d  mov     rax, [rbx]
0x140002060  mov     rbx, [rsp+28h+arg_10]
0x140002065  mov     rsi, [rsp+28h+arg_18]
0x14000206a  add     rsp, 20h
0x14000206e  pop     rdi
0x14000206f  retn
```
