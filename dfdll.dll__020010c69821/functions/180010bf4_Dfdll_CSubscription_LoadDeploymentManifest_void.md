# Dfdll::CSubscription::LoadDeploymentManifest(void)

- ea: `0x180010bf4`
- end: `0x180010d16`
- name: `?LoadDeploymentManifest@CSubscription@Dfdll@@IEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a2ac`

## callees

- `0x1800093b0`
- `0x18000a040`
- `0x180010bf4`
- `0x180010f34`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CSubscription::LoadDeploymentManifest(Dfdll::CSubscription *this)
{
  int Identities; // ebx
  __int64 v4; // [rsp+38h] [rbp-10h] BYREF

  if ( *((_QWORD *)this + 8) )
  {
    Identities = Dfdll::CSubscription::EnsureInitialization(this);
    if ( Identities >= 0 )
    {
      if ( *((_QWORD *)this + 12) || (Identities = Dfdll::CSubscription::LoadIdentities(this), Identities >= 0) )
      {
        v4 = 0;
        Identities = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, GUID *, __int64 *))(**((_QWORD **)this + 16)
                                                                                          + 56LL))(
                       *((_QWORD *)this + 16),
                       0,
                       *((_QWORD *)this + 12),
                       &GUID_a504e5b0_8ccf_4cb4_9902_c9d1b9abd033,
                       &v4);
        if ( Identities >= 0 )
        {
          Identities = Dfdll::CInterfacePointer<IUnknown>::Attach((char *)this + 184, v4, 0);
          if ( Identities >= 0 )
          {
            Identities = 0;
            if ( v4 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          }
          else if ( v4 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          }
        }
        else if ( v4 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147023893;
  }
  return (unsigned int)Identities;
}

```

## disassembly

```asm
0x180010bf4  mov     [rsp+arg_0], rbx
0x180010bf9  push    rdi
0x180010bfa  sub     rsp, 40h
0x180010bfe  mov     rdi, rcx
0x180010c01  cmp     qword ptr [rcx+40h], 0
0x180010c06  jnz     short loc_180010C12
0x180010c08  mov     ebx, 800703EBh
0x180010c0d  jmp     loc_180010D09
0x180010c12  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x180010c17  mov     ebx, eax
0x180010c19  test    eax, eax
0x180010c1b  js      loc_180010D09
0x180010c21  cmp     qword ptr [rdi+60h], 0
0x180010c26  jnz     short loc_180010C3A
0x180010c28  mov     rcx, rdi; this
0x180010c2b  call    ?LoadIdentities@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::LoadIdentities(void)
0x180010c30  mov     ebx, eax
0x180010c32  test    eax, eax
0x180010c34  js      loc_180010D09
0x180010c3a  and     [rsp+48h+var_10], 0
0x180010c40  lea     rax, ??_7?$CIUnknownBasedPointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IUnknown>::`vftable'
0x180010c47  mov     [rsp+48h+var_18], rax
0x180010c4c  mov     rcx, [rdi+80h]
0x180010c53  mov     rax, [rcx]
0x180010c56  lea     rdx, [rsp+48h+var_10]
0x180010c5b  mov     [rsp+48h+var_28], rdx
0x180010c60  lea     r9, _GUID_a504e5b0_8ccf_4cb4_9902_c9d1b9abd033
0x180010c67  mov     r8, [rdi+60h]
0x180010c6b  xor     edx, edx
0x180010c6d  mov     rax, [rax+38h]
0x180010c71  call    cs:__guard_dispatch_icall_fptr
0x180010c77  mov     ebx, eax
0x180010c79  test    eax, eax
0x180010c7b  jns     short loc_180010CA3
0x180010c7d  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180010c84  mov     [rsp+48h+var_18], rax
0x180010c89  mov     rcx, [rsp+48h+var_10]
0x180010c8e  test    rcx, rcx
0x180010c91  jz      short loc_180010CA1
0x180010c93  mov     rax, [rcx]
0x180010c96  mov     rax, [rax+10h]
0x180010c9a  call    cs:__guard_dispatch_icall_fptr
0x180010ca0  nop
0x180010ca1  jmp     short loc_180010D09
0x180010ca3  lea     rcx, [rdi+0B8h]
0x180010caa  xor     r8d, r8d
0x180010cad  mov     rdx, [rsp+48h+var_10]
0x180010cb2  call    ?Attach@?$CInterfacePointer@UIUnknown@@@Dfdll@@QEAAJPEAUIUnknown@@_N@Z; Dfdll::CInterfacePointer<IUnknown>::Attach(IUnknown *,bool)
0x180010cb7  mov     ebx, eax
0x180010cb9  test    eax, eax
0x180010cbb  jns     short loc_180010CE3
0x180010cbd  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180010cc4  mov     [rsp+48h+var_18], rax
0x180010cc9  mov     rcx, [rsp+48h+var_10]
0x180010cce  test    rcx, rcx
0x180010cd1  jz      short loc_180010CE1
0x180010cd3  mov     rax, [rcx]
0x180010cd6  mov     rax, [rax+10h]
0x180010cda  call    cs:__guard_dispatch_icall_fptr
0x180010ce0  nop
0x180010ce1  jmp     short loc_180010D09
0x180010ce3  xor     ebx, ebx
0x180010ce5  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180010cec  mov     [rsp+48h+var_18], rax
0x180010cf1  mov     rcx, [rsp+48h+var_10]
0x180010cf6  test    rcx, rcx
0x180010cf9  jz      short loc_180010D09
0x180010cfb  mov     rax, [rcx]
0x180010cfe  mov     rax, [rax+10h]
0x180010d02  call    cs:__guard_dispatch_icall_fptr
0x180010d08  nop
0x180010d09  mov     eax, ebx
0x180010d0b  mov     rbx, [rsp+48h+arg_0]
0x180010d10  add     rsp, 40h
0x180010d14  pop     rdi
0x180010d15  retn
```
