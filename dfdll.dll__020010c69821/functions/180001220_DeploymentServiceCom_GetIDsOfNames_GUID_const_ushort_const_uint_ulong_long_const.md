# DeploymentServiceCom::GetIDsOfNames(_GUID const &,ushort * * const,uint,ulong,long * const)

- ea: `0x180001220`
- end: `0x18000126d`
- name: `?GetIDsOfNames@DeploymentServiceCom@@UEAAJAEBU_GUID@@QEAPEAGIKQEAJ@Z`
- size: `77`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this, const struct _GUID *, unsigned __int16 **const, unsigned int, unsigned int, int *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001270`

## callees

- `0x180001220`
- `0x1800013cc`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::GetIDsOfNames(
        DeploymentServiceCom *this,
        const struct _GUID *a2,
        unsigned __int16 **const a3,
        unsigned int a4,
        unsigned int a5,
        int *const a6)
{
  __int64 result; // rax

  result = DeploymentServiceCom::LoadTypeInfo(this);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **const, _QWORD, int *const))(**((_QWORD **)this + 3)
                                                                                           + 80LL))(
             *((_QWORD *)this + 3),
             a3,
             a4,
             a6);
  return result;
}

```

## disassembly

```asm
0x180001220  mov     [rsp+arg_0], rbx
0x180001225  mov     [rsp+arg_8], rsi
0x18000122a  push    rdi
0x18000122b  sub     rsp, 30h
0x18000122f  mov     edi, r9d
0x180001232  mov     rsi, r8
0x180001235  mov     rbx, rcx
0x180001238  call    ?LoadTypeInfo@DeploymentServiceCom@@QEAAJXZ; DeploymentServiceCom::LoadTypeInfo(void)
0x18000123d  test    eax, eax
0x18000123f  js      short loc_18000125D
0x180001241  mov     rcx, [rbx+18h]
0x180001245  mov     r8d, edi
0x180001248  mov     r9, [rsp+38h+arg_28]
0x18000124d  mov     rdx, rsi
0x180001250  mov     rax, [rcx]
0x180001253  mov     rax, [rax+50h]
0x180001257  call    cs:__guard_dispatch_icall_fptr
0x18000125d  mov     rbx, [rsp+38h+arg_0]
0x180001262  mov     rsi, [rsp+38h+arg_8]
0x180001267  add     rsp, 30h
0x18000126b  pop     rdi
0x18000126c  retn
```
