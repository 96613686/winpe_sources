# CProvisioningCommandsClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003760`
- end: `0x1800037e0`
- name: `?CreateInstance@CProvisioningCommandsClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(CProvisioningCommandsClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003760`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsClassFactory::CreateInstance(
        CProvisioningCommandsClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, const struct _GUID *, void **); // rax
  __int64 (__fastcall ***v8)(_QWORD, const struct _GUID *, void **); // rsi

  if ( a2 )
  {
    v6 = -2147221232;
    if ( a4 )
      *a4 = 0;
  }
  else
  {
    v7 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))(*(__int64 (**)(void))(*((_QWORD *)this + 2)
                                                                                               + 8LL))();
    v8 = v7;
    if ( v7 )
    {
      v6 = (**v7)(v7, a3, a4);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v8)[2])(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180003760  mov     [rsp+arg_0], rbx
0x180003765  mov     [rsp+arg_8], rsi
0x18000376a  push    rdi
0x18000376b  sub     rsp, 20h
0x18000376f  mov     rdi, r9
0x180003772  mov     rbx, r8
0x180003775  test    rdx, rdx
0x180003778  jz      short loc_18000378D
0x18000377a  mov     ebx, 80040110h
0x18000377f  test    r9, r9
0x180003782  jz      short loc_1800037CE
0x180003784  mov     qword ptr [r9], 0
0x18000378b  jmp     short loc_1800037CE
0x18000378d  mov     rax, [rcx+10h]
0x180003791  mov     rax, [rax+8]
0x180003795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000379a  mov     rsi, rax
0x18000379d  test    rax, rax
0x1800037a0  jz      short loc_1800037C9
0x1800037a2  mov     rax, [rax]
0x1800037a5  mov     r8, rdi
0x1800037a8  mov     rdx, rbx
0x1800037ab  mov     rcx, rsi
0x1800037ae  mov     rax, [rax]
0x1800037b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b6  mov     rcx, [rsi]
0x1800037b9  mov     ebx, eax
0x1800037bb  mov     rax, [rcx+10h]
0x1800037bf  mov     rcx, rsi
0x1800037c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c7  jmp     short loc_1800037CE
0x1800037c9  mov     ebx, 8007000Eh
0x1800037ce  mov     rsi, [rsp+28h+arg_8]
0x1800037d3  mov     eax, ebx
0x1800037d5  mov     rbx, [rsp+28h+arg_0]
0x1800037da  add     rsp, 20h
0x1800037de  pop     rdi
0x1800037df  retn
```
