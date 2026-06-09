# CProvisioningCommandsClassFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x1800049f0`
- end: `0x180004a4b`
- name: `?QueryInterface@CProvisioningCommandsClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `91`
- prototype: `__int64 __fastcall(CProvisioningCommandsClassFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800049f0`
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
0x1800049f0  sub     rsp, 28h
0x1800049f4  mov     rax, [rdx]
0x1800049f7  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x1800049fe  jnz     short loc_180004A0D
0x180004a00  mov     rax, [rdx+8]
0x180004a04  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180004a0b  jz      short loc_180004A26
0x180004a0d  mov     rax, [rdx]
0x180004a10  cmp     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data1
0x180004a17  jnz     short loc_180004A39
0x180004a19  mov     rax, [rdx+8]
0x180004a1d  cmp     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4
0x180004a24  jnz     short loc_180004A39
0x180004a26  mov     [r8], rcx
0x180004a29  mov     rax, [rcx]
0x180004a2c  mov     rax, [rax+8]
0x180004a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a35  xor     eax, eax
0x180004a37  jmp     short loc_180004A45
0x180004a39  mov     qword ptr [r8], 0
0x180004a40  mov     eax, 80004002h
0x180004a45  add     rsp, 28h
0x180004a49  retn
```
