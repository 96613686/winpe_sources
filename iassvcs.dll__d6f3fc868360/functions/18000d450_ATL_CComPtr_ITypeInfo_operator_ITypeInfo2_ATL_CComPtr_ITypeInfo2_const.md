# ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)

- ea: `0x18000d450`
- end: `0x18000d561`
- name: `??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z`
- size: `273`
- prototype: `void (__fastcall ***__fastcall(_QWORD *, void (__fastcall ****)(_QWORD, GUID *, __int64)))(_QWORD, GUID *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010020`

## callees

- `0x18000d450`
- `0x180019010`

## pseudocode

```c
void (__fastcall ***__fastcall ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(
        _QWORD *a1,
        void (__fastcall ****a2)(_QWORD, GUID *, __int64)))(_QWORD, GUID *, __int64 *)
{
  void (__fastcall ***v4)(_QWORD, GUID *, __int64); // rdi
  void (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  bool v6; // di
  __int64 v7; // rcx
  void (__fastcall ***v8)(_QWORD, GUID *, __int64); // rcx
  void (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF
  __int64 v12; // [rsp+38h] [rbp+10h] BYREF

  v4 = *a2;
  v5 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
  if ( !v5 )
  {
    if ( !v4 )
    {
      v6 = 1;
      goto LABEL_11;
    }
    goto LABEL_10;
  }
  if ( !v4 )
  {
LABEL_10:
    v6 = 0;
    goto LABEL_11;
  }
  v11 = 0;
  v12 = 0;
  (**v5)(v5, &GUID_00000000_0000_0000_c000_000000000046, &v11);
  (**v4)(v4, &GUID_00000000_0000_0000_c000_000000000046, (__int64)&v12);
  v7 = v11;
  v6 = v11 == v12;
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v7 = v11;
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_11:
  if ( !v6 )
  {
    v8 = *a2;
    v9 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
    *a1 = 0;
    if ( v8 )
      (**v8)(v8, &GUID_00020401_0000_0000_c000_000000000046, (__int64)a1);
    if ( v9 )
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v9)[2])(v9);
  }
  return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
}

```

## disassembly

```asm
0x18000d450  mov     [rsp+arg_10], rbx
0x18000d455  mov     [rsp+arg_18], rsi
0x18000d45a  push    rdi
0x18000d45b  sub     rsp, 20h
0x18000d45f  mov     rsi, rdx
0x18000d462  mov     rbx, rcx
0x18000d465  mov     rdi, [rdx]
0x18000d468  mov     rcx, [rcx]
0x18000d46b  test    rcx, rcx
0x18000d46e  jnz     short loc_18000D481
0x18000d470  test    rdi, rdi
0x18000d473  jnz     loc_18000D50B
0x18000d479  mov     dil, 1
0x18000d47c  jmp     loc_18000D50E
0x18000d481  test    rdi, rdi
0x18000d484  jz      loc_18000D50B
0x18000d48a  mov     [rsp+28h+arg_0], 0
0x18000d493  mov     [rsp+28h+arg_8], 0
0x18000d49c  mov     rax, [rcx]
0x18000d49f  lea     r8, [rsp+28h+arg_0]
0x18000d4a4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000d4ab  mov     rax, [rax]
0x18000d4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4b3  mov     rax, [rdi]
0x18000d4b6  lea     r8, [rsp+28h+arg_8]
0x18000d4bb  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000d4c2  mov     rcx, rdi
0x18000d4c5  mov     rax, [rax]
0x18000d4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4cd  mov     rcx, [rsp+28h+arg_0]
0x18000d4d2  mov     rdx, [rsp+28h+arg_8]
0x18000d4d7  cmp     rcx, rdx
0x18000d4da  setz    dil
0x18000d4de  test    rdx, rdx
0x18000d4e1  jz      short loc_18000D4F7
0x18000d4e3  mov     rax, [rdx]
0x18000d4e6  mov     rcx, rdx
0x18000d4e9  mov     rax, [rax+10h]
0x18000d4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4f2  mov     rcx, [rsp+28h+arg_0]
0x18000d4f7  test    rcx, rcx
0x18000d4fa  jz      short loc_18000D509
0x18000d4fc  mov     rax, [rcx]
0x18000d4ff  mov     rax, [rax+10h]
0x18000d503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d508  nop
0x18000d509  jmp     short loc_18000D50E
0x18000d50b  xor     dil, dil
0x18000d50e  test    dil, dil
0x18000d511  jnz     short loc_18000D54E
0x18000d513  mov     rcx, [rsi]
0x18000d516  mov     rdi, [rbx]
0x18000d519  mov     qword ptr [rbx], 0
0x18000d520  test    rcx, rcx
0x18000d523  jz      short loc_18000D53A
0x18000d525  mov     rax, [rcx]
0x18000d528  mov     r8, rbx
0x18000d52b  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x18000d532  mov     rax, [rax]
0x18000d535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53a  test    rdi, rdi
0x18000d53d  jz      short loc_18000D54E
0x18000d53f  mov     rax, [rdi]
0x18000d542  mov     rcx, rdi
0x18000d545  mov     rax, [rax+10h]
0x18000d549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d54e  mov     rax, [rbx]
0x18000d551  mov     rbx, [rsp+28h+arg_10]
0x18000d556  mov     rsi, [rsp+28h+arg_18]
0x18000d55b  add     rsp, 20h
0x18000d55f  pop     rdi
0x18000d560  retn
```
