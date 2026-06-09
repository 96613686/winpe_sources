# DeploymentServiceComClassFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x1800016d0`
- end: `0x180001734`
- name: `?QueryInterface@DeploymentServiceComClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: `__int64 __fastcall(DeploymentServiceComClassFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800016d0`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceComClassFactory::QueryInterface(
        DeploymentServiceComClassFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( !a3 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IClassFactory.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IClassFactory.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(DeploymentServiceComClassFactory *))(*(_QWORD *)this + 8LL))(this);
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
0x1800016d0  sub     rsp, 28h
0x1800016d4  test    r8, r8
0x1800016d7  jnz     short loc_1800016E0
0x1800016d9  mov     eax, 80004003h
0x1800016de  jmp     short loc_18000172F
0x1800016e0  mov     rax, [rdx]
0x1800016e3  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800016ea  jnz     short loc_1800016F9
0x1800016ec  mov     rax, [rdx+8]
0x1800016f0  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800016f7  jz      short loc_180001712
0x1800016f9  mov     rax, [rdx]
0x1800016fc  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x180001703  jnz     short loc_180001726
0x180001705  mov     rax, [rdx+8]
0x180001709  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180001710  jnz     short loc_180001726
0x180001712  mov     [r8], rcx
0x180001715  mov     rax, [rcx]
0x180001718  mov     rax, [rax+8]
0x18000171c  call    cs:__guard_dispatch_icall_fptr
0x180001722  xor     eax, eax
0x180001724  jmp     short loc_18000172F
0x180001726  and     qword ptr [r8], 0
0x18000172a  mov     eax, 80004002h
0x18000172f  add     rsp, 28h
0x180001733  retn
```
