# ServerClassFactoryT<CProvisioningWapDPURemote>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140006c30`
- end: `0x140006d22`
- name: `?CreateInstance@?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001844`
- `0x140006c30`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x140006c9c`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x140006c9c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006cc5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006cc5`

## pseudocode

```c
__int64 __fastcall ServerClassFactoryT<CProvisioningWapDPURemote>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  __int64 *v7; // rbx
  bool v8; // sf
  __int64 v9; // rax

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
      if ( v7 )
      {
        *((_DWORD *)v7 + 2) = 1;
        *v7 = (__int64)&CProvisioningWapDPURemote::`vftable';
        v7[2] = 0;
        CoAddRefServerProcess();
        v8 = CoCreateInstance(
               &GUID_f4477ad6_6b3a_411b_9ecc_7ce89b665401,
               0,
               1u,
               &GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd,
               (LPVOID *)v7 + 2) < 0;
        v9 = *v7;
        if ( !v8 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD *))v9)(v7, a3, a4);
          (*(void (__fastcall **)(__int64 *))(*v7 + 16))(v7);
          return v6;
        }
        (*(void (__fastcall **)(__int64 *, __int64))(v9 + 48))(v7, 1);
      }
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
}

```

## disassembly

```asm
0x140006c30  mov     [rsp+arg_0], rbx
0x140006c35  mov     [rsp+arg_8], rsi
0x140006c3a  push    rdi
0x140006c3b  sub     rsp, 30h
0x140006c3f  mov     rdi, r9
0x140006c42  mov     rsi, r8
0x140006c45  test    r9, r9
0x140006c48  jnz     short loc_140006C54
0x140006c4a  mov     edi, 80004003h
0x140006c4f  jmp     loc_140006CEE
0x140006c54  mov     qword ptr [r9], 0
0x140006c5b  test    rdx, rdx
0x140006c5e  jz      short loc_140006C6A
0x140006c60  mov     edi, 80040110h
0x140006c65  jmp     loc_140006CEE
0x140006c6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006c71  mov     ecx, 18h; unsigned __int64
0x140006c76  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140006c7b  mov     rbx, rax
0x140006c7e  test    rax, rax
0x140006c81  jz      short loc_140006CE9
0x140006c83  lea     rax, ??_7CProvisioningWapDPURemote@@6B@; const CProvisioningWapDPURemote::`vftable'
0x140006c8a  mov     dword ptr [rbx+8], 1
0x140006c91  mov     [rbx], rax
0x140006c94  mov     qword ptr [rbx+10h], 0
0x140006c9c  call    cs:__imp_CoAddRefServerProcess
0x140006ca3  nop     dword ptr [rax+rax+00h]
0x140006ca8  xor     edx, edx; pUnkOuter
0x140006caa  lea     rax, [rbx+10h]
0x140006cae  lea     r9, _GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd; riid
0x140006cb5  mov     [rsp+38h+ppv], rax; ppv
0x140006cba  lea     rcx, _GUID_f4477ad6_6b3a_411b_9ecc_7ce89b665401; rclsid
0x140006cc1  lea     r8d, [rdx+1]; dwClsContext
0x140006cc5  call    cs:__imp_CoCreateInstance
0x140006ccc  nop     dword ptr [rax+rax+00h]
0x140006cd1  test    eax, eax
0x140006cd3  mov     rcx, rbx
0x140006cd6  mov     rax, [rbx]
0x140006cd9  jns     short loc_140006D01
0x140006cdb  mov     rax, [rax+30h]
0x140006cdf  mov     edx, 1
0x140006ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ce9  mov     edi, 8007000Eh
0x140006cee  mov     rbx, [rsp+38h+arg_0]
0x140006cf3  mov     eax, edi
0x140006cf5  mov     rsi, [rsp+38h+arg_8]
0x140006cfa  add     rsp, 30h
0x140006cfe  pop     rdi
0x140006cff  retn
0x140006d01  mov     rax, [rax]
0x140006d04  mov     r8, rdi
0x140006d07  mov     rdx, rsi
0x140006d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d0f  mov     rcx, [rbx]
0x140006d12  mov     edi, eax
0x140006d14  mov     rax, [rcx+10h]
0x140006d18  mov     rcx, rbx
0x140006d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d20  jmp     short loc_140006CEE
```
