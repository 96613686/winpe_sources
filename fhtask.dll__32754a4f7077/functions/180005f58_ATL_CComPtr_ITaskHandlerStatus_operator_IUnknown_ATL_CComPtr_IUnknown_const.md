# ATL::CComPtr<ITaskHandlerStatus>::operator=<IUnknown>(ATL::CComPtr<IUnknown> const &)

- ea: `0x180005f58`
- end: `0x180006069`
- name: `??$?4UIUnknown@@@?$CComPtr@UITaskHandlerStatus@@@ATL@@QEAAPEAUITaskHandlerStatus@@AEBV?$CComPtr@UIUnknown@@@1@@Z`
- size: `273`
- prototype: `void (__fastcall ***__fastcall(_QWORD *, void (__fastcall ****)(_QWORD, GUID *, __int64)))(_QWORD, GUID *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006620`
- `0x180008600`

## callees

- `0x180005f58`
- `0x18000b010`

## pseudocode

```c
void (__fastcall ***__fastcall ATL::CComPtr<ITaskHandlerStatus>::operator=<IUnknown>(
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
      (**v8)(v8, &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a, (__int64)a1);
    if ( v9 )
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v9)[2])(v9);
  }
  return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
}

```

## disassembly

```asm
0x180005f58  mov     [rsp+arg_10], rbx
0x180005f5d  mov     [rsp+arg_18], rsi
0x180005f62  push    rdi
0x180005f63  sub     rsp, 20h
0x180005f67  mov     rsi, rdx
0x180005f6a  mov     rbx, rcx
0x180005f6d  mov     rdi, [rdx]
0x180005f70  mov     rcx, [rcx]
0x180005f73  test    rcx, rcx
0x180005f76  jnz     short loc_180005F89
0x180005f78  test    rdi, rdi
0x180005f7b  jnz     loc_180006013
0x180005f81  mov     dil, 1
0x180005f84  jmp     loc_180006016
0x180005f89  test    rdi, rdi
0x180005f8c  jz      loc_180006013
0x180005f92  mov     [rsp+28h+arg_0], 0
0x180005f9b  mov     [rsp+28h+arg_8], 0
0x180005fa4  mov     rax, [rcx]
0x180005fa7  lea     r8, [rsp+28h+arg_0]
0x180005fac  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005fb3  mov     rax, [rax]
0x180005fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fbb  mov     rax, [rdi]
0x180005fbe  lea     r8, [rsp+28h+arg_8]
0x180005fc3  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005fca  mov     rcx, rdi
0x180005fcd  mov     rax, [rax]
0x180005fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd5  mov     rcx, [rsp+28h+arg_0]
0x180005fda  mov     rdx, [rsp+28h+arg_8]
0x180005fdf  cmp     rcx, rdx
0x180005fe2  setz    dil
0x180005fe6  test    rdx, rdx
0x180005fe9  jz      short loc_180005FFF
0x180005feb  mov     rax, [rdx]
0x180005fee  mov     rcx, rdx
0x180005ff1  mov     rax, [rax+10h]
0x180005ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ffa  mov     rcx, [rsp+28h+arg_0]
0x180005fff  test    rcx, rcx
0x180006002  jz      short loc_180006011
0x180006004  mov     rax, [rcx]
0x180006007  mov     rax, [rax+10h]
0x18000600b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006010  nop
0x180006011  jmp     short loc_180006016
0x180006013  xor     dil, dil
0x180006016  test    dil, dil
0x180006019  jnz     short loc_180006056
0x18000601b  mov     rcx, [rsi]
0x18000601e  mov     rdi, [rbx]
0x180006021  mov     qword ptr [rbx], 0
0x180006028  test    rcx, rcx
0x18000602b  jz      short loc_180006042
0x18000602d  mov     rax, [rcx]
0x180006030  mov     r8, rbx
0x180006033  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000603a  mov     rax, [rax]
0x18000603d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006042  test    rdi, rdi
0x180006045  jz      short loc_180006056
0x180006047  mov     rax, [rdi]
0x18000604a  mov     rcx, rdi
0x18000604d  mov     rax, [rax+10h]
0x180006051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006056  mov     rax, [rbx]
0x180006059  mov     rbx, [rsp+28h+arg_10]
0x18000605e  mov     rsi, [rsp+28h+arg_18]
0x180006063  add     rsp, 20h
0x180006067  pop     rdi
0x180006068  retn
```
