# wil::com_ptr_t<ILogonTrigger,wil::err_exception_policy>::reset(void)

- ea: `0x140013fe0`
- end: `0x140014008`
- name: `?reset@?$com_ptr_t@UILogonTrigger@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001376c`

## callees

- `0x140013fe0`
- `0x14001a010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<ILogonTrigger,wil::err_exception_policy>::reset(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x140013fe0  sub     rsp, 28h
0x140013fe4  mov     rdx, [rcx]
0x140013fe7  mov     qword ptr [rcx], 0
0x140013fee  test    rdx, rdx
0x140013ff1  jz      short loc_140014003
0x140013ff3  mov     rax, [rdx]
0x140013ff6  mov     rcx, rdx
0x140013ff9  mov     rax, [rax+10h]
0x140013ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014002  nop
0x140014003  add     rsp, 28h
0x140014007  retn
```
