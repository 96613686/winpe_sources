# ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)

- ea: `0x140002c9c`
- end: `0x140002da4`
- name: `??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400058e4`

## callees

- `0x140002c9c`
- `0x140010010`

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
0x140002c9c  mov     [rsp+arg_10], rbx
0x140002ca1  mov     [rsp+arg_18], rsi
0x140002ca6  push    rdi
0x140002ca7  sub     rsp, 20h
0x140002cab  mov     rdi, [rdx]
0x140002cae  mov     rbx, rcx
0x140002cb1  mov     rcx, [rcx]
0x140002cb4  mov     rsi, rdx
0x140002cb7  test    rcx, rcx
0x140002cba  jnz     short loc_140002CCA
0x140002cbc  test    rdi, rdi
0x140002cbf  jnz     loc_140002D56
0x140002cc5  jmp     loc_140002D91
0x140002cca  test    rdi, rdi
0x140002ccd  jz      loc_140002D56
0x140002cd3  mov     [rsp+28h+arg_0], 0
0x140002cdc  lea     r8, [rsp+28h+arg_0]
0x140002ce1  mov     [rsp+28h+arg_8], 0
0x140002cea  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140002cf1  mov     rax, [rcx]
0x140002cf4  mov     rax, [rax]
0x140002cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cfc  mov     rax, [rdi]
0x140002cff  lea     r8, [rsp+28h+arg_8]
0x140002d04  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140002d0b  mov     rcx, rdi
0x140002d0e  mov     rax, [rax]
0x140002d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d16  mov     rdx, [rsp+28h+arg_8]
0x140002d1b  mov     rcx, [rsp+28h+arg_0]
0x140002d20  cmp     rcx, rdx
0x140002d23  setz    dil
0x140002d27  test    rdx, rdx
0x140002d2a  jz      short loc_140002D40
0x140002d2c  mov     rax, [rdx]
0x140002d2f  mov     rcx, rdx
0x140002d32  mov     rax, [rax+10h]
0x140002d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d3b  mov     rcx, [rsp+28h+arg_0]
0x140002d40  test    rcx, rcx
0x140002d43  jz      short loc_140002D51
0x140002d45  mov     rax, [rcx]
0x140002d48  mov     rax, [rax+10h]
0x140002d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d51  test    dil, dil
0x140002d54  jnz     short loc_140002D91
0x140002d56  mov     rcx, [rsi]
0x140002d59  mov     rdi, [rbx]
0x140002d5c  mov     qword ptr [rbx], 0
0x140002d63  test    rcx, rcx
0x140002d66  jz      short loc_140002D7D
0x140002d68  mov     rax, [rcx]
0x140002d6b  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x140002d72  mov     r8, rbx
0x140002d75  mov     rax, [rax]
0x140002d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d7d  test    rdi, rdi
0x140002d80  jz      short loc_140002D91
0x140002d82  mov     rax, [rdi]
0x140002d85  mov     rcx, rdi
0x140002d88  mov     rax, [rax+10h]
0x140002d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d91  mov     rax, [rbx]
0x140002d94  mov     rbx, [rsp+28h+arg_10]
0x140002d99  mov     rsi, [rsp+28h+arg_18]
0x140002d9e  add     rsp, 20h
0x140002da2  pop     rdi
0x140002da3  retn
```
