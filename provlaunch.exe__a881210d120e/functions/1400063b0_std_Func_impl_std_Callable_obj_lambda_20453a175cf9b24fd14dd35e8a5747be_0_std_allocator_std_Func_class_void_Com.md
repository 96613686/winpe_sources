# std::_Func_impl_std::_Callable_obj__lambda_20453a175cf9b24fd14dd35e8a5747be__0__std::allocator_std::_Func_class_void_CommandSet_const_&_Command_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const_&_Command_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call

- ea: `0x1400063b0`
- end: `0x14000642f`
- name: `std::_Func_impl_std::_Callable_obj__lambda_20453a175cf9b24fd14dd35e8a5747be__0__std::allocator_std::_Func_class_void_CommandSet_const_&_Command_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const_&_Command_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140003bd4`
- `0x1400063b0`
- `0x140008628`

## pseudocode

```c
void __fastcall std::_Func_impl_std::_Callable_obj__lambda_20453a175cf9b24fd14dd35e8a5747be__0__std::allocator_std::_Func_class_void_CommandSet_const___Command_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const___Command_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3)
{
  const WCHAR *v3; // rdi
  const unsigned __int16 *v5; // r9
  const unsigned __int16 *v6; // rbx
  const unsigned __int16 *v7; // r8

  v3 = a3;
  if ( *((_QWORD *)a3 + 3) < 8u )
    v5 = a3;
  else
    v5 = *(const unsigned __int16 **)a3;
  v6 = (const unsigned __int16 *)(a2 + 24);
  if ( *(_QWORD *)(a2 + 48) < 8u )
    v7 = (const unsigned __int16 *)(a2 + 24);
  else
    v7 = *(const unsigned __int16 **)v6;
  RegistryConfig::Delete(*(RegistryConfig **)(a1 + 8), **(const unsigned __int16 ***)(a1 + 16), v7, v5);
  if ( *((_QWORD *)v3 + 3) >= 8u )
    v3 = *(const WCHAR **)v3;
  if ( *((_QWORD *)v6 + 3) >= 8u )
    v6 = *(const unsigned __int16 **)v6;
  Add(**(LPCWSTR **)(a1 + 16), v6, v3, 1u);
}

```

## disassembly

```asm
0x1400063b0  mov     [rsp+arg_0], rbx
0x1400063b5  mov     [rsp+arg_8], rsi
0x1400063ba  push    rdi
0x1400063bb  sub     rsp, 20h
0x1400063bf  cmp     qword ptr [r8+18h], 8
0x1400063c4  mov     rdi, r8
0x1400063c7  mov     rsi, rcx
0x1400063ca  jb      short loc_1400063D1
0x1400063cc  mov     r9, [r8]
0x1400063cf  jmp     short loc_1400063D4
0x1400063d1  mov     r9, rdi; unsigned __int16 *
0x1400063d4  lea     rbx, [rdx+18h]
0x1400063d8  cmp     qword ptr [rbx+18h], 8
0x1400063dd  jb      short loc_1400063E4
0x1400063df  mov     r8, [rbx]
0x1400063e2  jmp     short loc_1400063E7
0x1400063e4  mov     r8, rbx; unsigned __int16 *
0x1400063e7  mov     rdx, [rcx+10h]
0x1400063eb  mov     rcx, [rcx+8]; this
0x1400063ef  mov     rdx, [rdx]; unsigned __int16 *
0x1400063f2  call    ?Delete@RegistryConfig@@QEAAXPEBG00@Z; RegistryConfig::Delete(ushort const *,ushort const *,ushort const *)
0x1400063f7  cmp     qword ptr [rdi+18h], 8
0x1400063fc  jb      short loc_140006401
0x1400063fe  mov     rdi, [rdi]
0x140006401  cmp     qword ptr [rbx+18h], 8
0x140006406  jb      short loc_14000640B
0x140006408  mov     rbx, [rbx]
0x14000640b  mov     rcx, [rsi+10h]
0x14000640f  mov     r9b, 1; bool
0x140006412  mov     r8, rdi; LPCWSTR
0x140006415  mov     rdx, rbx; LPCWSTR
0x140006418  mov     rcx, [rcx]; lpSubKey
0x14000641b  mov     rbx, [rsp+28h+arg_0]
0x140006420  mov     rsi, [rsp+28h+arg_8]
0x140006425  add     rsp, 20h
0x140006429  pop     rdi
0x14000642a  jmp     ?Add@@YAXPEBG00_N@Z; Add(ushort const *,ushort const *,ushort const *,bool)
```
