# CProvisioningCommandsClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800034e0`
- end: `0x180003561`
- name: `?CreateInstance@CProvisioningCommandsClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `129`
- prototype: `__int64 __fastcall(CProvisioningCommandsClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800034e0`
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
0x1800034e0  mov     [rsp+arg_0], rbx
0x1800034e5  mov     [rsp+arg_8], rsi
0x1800034ea  push    rdi
0x1800034eb  sub     rsp, 20h
0x1800034ef  mov     rdi, r9
0x1800034f2  mov     rbx, r8
0x1800034f5  test    rdx, rdx
0x1800034f8  jz      short loc_18000350D
0x1800034fa  mov     ebx, 80040110h
0x1800034ff  test    r9, r9
0x180003502  jz      short loc_18000354E
0x180003504  mov     qword ptr [r9], 0
0x18000350b  jmp     short loc_18000354E
0x18000350d  mov     rax, [rcx+10h]
0x180003511  mov     rax, [rax+8]
0x180003515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351a  mov     rsi, rax
0x18000351d  test    rax, rax
0x180003520  jz      short loc_180003549
0x180003522  mov     rax, [rax]
0x180003525  mov     r8, rdi
0x180003528  mov     rdx, rbx
0x18000352b  mov     rcx, rsi
0x18000352e  mov     rax, [rax]
0x180003531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003536  mov     rcx, [rsi]
0x180003539  mov     ebx, eax
0x18000353b  mov     rax, [rcx+10h]
0x18000353f  mov     rcx, rsi
0x180003542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003547  jmp     short loc_18000354E
0x180003549  mov     ebx, 8007000Eh
0x18000354e  mov     rsi, [rsp+28h+arg_8]
0x180003553  mov     eax, ebx
0x180003555  mov     rbx, [rsp+28h+arg_0]
0x18000355a  add     rsp, 20h
0x18000355e  pop     rdi
0x18000355f  retn
```
