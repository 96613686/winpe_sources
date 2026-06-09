# CProvisioningCommandsClassFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x180004940`
- end: `0x18000499a`
- name: `?QueryInterface@CProvisioningCommandsClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(CProvisioningCommandsClassFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004940`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsClassFactory::QueryInterface(
        CProvisioningCommandsClassFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_00000001_0000_0000_c000_000000000046.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CProvisioningCommandsClassFactory *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180004940  sub     rsp, 28h
0x180004944  mov     rax, [rdx]
0x180004947  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x18000494e  jnz     short loc_18000495D
0x180004950  mov     rax, [rdx+8]
0x180004954  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000495b  jz      short loc_180004976
0x18000495d  mov     rax, [rdx]
0x180004960  cmp     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data1
0x180004967  jnz     short loc_180004989
0x180004969  mov     rax, [rdx+8]
0x18000496d  cmp     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4
0x180004974  jnz     short loc_180004989
0x180004976  mov     [r8], rcx
0x180004979  mov     rax, [rcx]
0x18000497c  mov     rax, [rax+8]
0x180004980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004985  xor     eax, eax
0x180004987  jmp     short loc_180004995
0x180004989  mov     qword ptr [r8], 0
0x180004990  mov     eax, 80004002h
0x180004995  add     rsp, 28h
0x180004999  retn
```
