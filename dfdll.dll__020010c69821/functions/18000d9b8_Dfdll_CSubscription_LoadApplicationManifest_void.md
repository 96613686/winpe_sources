# Dfdll::CSubscription::LoadApplicationManifest(void)

- ea: `0x18000d9b8`
- end: `0x18000dada`
- name: `?LoadApplicationManifest@CSubscription@Dfdll@@IEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a2ac`
- `0x18000ab8c`
- `0x18000cac8`

## callees

- `0x1800093b0`
- `0x18000a040`
- `0x18000d9b8`
- `0x180010f34`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CSubscription::LoadApplicationManifest(Dfdll::CSubscription *this)
{
  int Identities; // ebx
  __int64 v4; // [rsp+38h] [rbp-10h] BYREF

  if ( *((_QWORD *)this + 8) )
  {
    Identities = Dfdll::CSubscription::EnsureInitialization(this);
    if ( Identities >= 0 )
    {
      if ( *((_QWORD *)this + 14) || (Identities = Dfdll::CSubscription::LoadIdentities(this), Identities >= 0) )
      {
        v4 = 0;
        Identities = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, GUID *, __int64 *))(**((_QWORD **)this + 16)
                                                                                          + 56LL))(
                       *((_QWORD *)this + 16),
                       0,
                       *((_QWORD *)this + 14),
                       &GUID_a504e5b0_8ccf_4cb4_9902_c9d1b9abd033,
                       &v4);
        if ( Identities >= 0 )
        {
          Identities = Dfdll::CInterfacePointer<IUnknown>::Attach((char *)this + 168, v4, 0);
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
0x18000d9b8  mov     [rsp+arg_0], rbx
0x18000d9bd  push    rdi
0x18000d9be  sub     rsp, 40h
0x18000d9c2  mov     rdi, rcx
0x18000d9c5  cmp     qword ptr [rcx+40h], 0
0x18000d9ca  jnz     short loc_18000D9D6
0x18000d9cc  mov     ebx, 800703EBh
0x18000d9d1  jmp     loc_18000DACD
0x18000d9d6  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x18000d9db  mov     ebx, eax
0x18000d9dd  test    eax, eax
0x18000d9df  js      loc_18000DACD
0x18000d9e5  cmp     qword ptr [rdi+70h], 0
0x18000d9ea  jnz     short loc_18000D9FE
0x18000d9ec  mov     rcx, rdi; this
0x18000d9ef  call    ?LoadIdentities@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::LoadIdentities(void)
0x18000d9f4  mov     ebx, eax
0x18000d9f6  test    eax, eax
0x18000d9f8  js      loc_18000DACD
0x18000d9fe  and     [rsp+48h+var_10], 0
0x18000da04  lea     rax, ??_7?$CIUnknownBasedPointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IUnknown>::`vftable'
0x18000da0b  mov     [rsp+48h+var_18], rax
0x18000da10  mov     rcx, [rdi+80h]
0x18000da17  mov     rax, [rcx]
0x18000da1a  lea     rdx, [rsp+48h+var_10]
0x18000da1f  mov     [rsp+48h+var_28], rdx
0x18000da24  lea     r9, _GUID_a504e5b0_8ccf_4cb4_9902_c9d1b9abd033
0x18000da2b  mov     r8, [rdi+70h]
0x18000da2f  xor     edx, edx
0x18000da31  mov     rax, [rax+38h]
0x18000da35  call    cs:__guard_dispatch_icall_fptr
0x18000da3b  mov     ebx, eax
0x18000da3d  test    eax, eax
0x18000da3f  jns     short loc_18000DA67
0x18000da41  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000da48  mov     [rsp+48h+var_18], rax
0x18000da4d  mov     rcx, [rsp+48h+var_10]
0x18000da52  test    rcx, rcx
0x18000da55  jz      short loc_18000DA65
0x18000da57  mov     rax, [rcx]
0x18000da5a  mov     rax, [rax+10h]
0x18000da5e  call    cs:__guard_dispatch_icall_fptr
0x18000da64  nop
0x18000da65  jmp     short loc_18000DACD
0x18000da67  lea     rcx, [rdi+0A8h]
0x18000da6e  xor     r8d, r8d
0x18000da71  mov     rdx, [rsp+48h+var_10]
0x18000da76  call    ?Attach@?$CInterfacePointer@UIUnknown@@@Dfdll@@QEAAJPEAUIUnknown@@_N@Z; Dfdll::CInterfacePointer<IUnknown>::Attach(IUnknown *,bool)
0x18000da7b  mov     ebx, eax
0x18000da7d  test    eax, eax
0x18000da7f  jns     short loc_18000DAA7
0x18000da81  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000da88  mov     [rsp+48h+var_18], rax
0x18000da8d  mov     rcx, [rsp+48h+var_10]
0x18000da92  test    rcx, rcx
0x18000da95  jz      short loc_18000DAA5
0x18000da97  mov     rax, [rcx]
0x18000da9a  mov     rax, [rax+10h]
0x18000da9e  call    cs:__guard_dispatch_icall_fptr
0x18000daa4  nop
0x18000daa5  jmp     short loc_18000DACD
0x18000daa7  xor     ebx, ebx
0x18000daa9  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000dab0  mov     [rsp+48h+var_18], rax
0x18000dab5  mov     rcx, [rsp+48h+var_10]
0x18000daba  test    rcx, rcx
0x18000dabd  jz      short loc_18000DACD
0x18000dabf  mov     rax, [rcx]
0x18000dac2  mov     rax, [rax+10h]
0x18000dac6  call    cs:__guard_dispatch_icall_fptr
0x18000dacc  nop
0x18000dacd  mov     eax, ebx
0x18000dacf  mov     rbx, [rsp+48h+arg_0]
0x18000dad4  add     rsp, 40h
0x18000dad8  pop     rdi
0x18000dad9  retn
```
