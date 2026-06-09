# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CDeliveryOptimizationCleanup,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x18000b260`
- end: `0x18000b334`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCDeliveryOptimizationCleanup@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800022cc`
- `0x18000b260`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CDeliveryOptimizationCleanup,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi

  v7 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v7[3] = 1;
  v7[5] = 4;
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CDeliveryOptimizationCleanup,0>::`vftable';
  ((void (__fastcall *)(_DWORD *))Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef)(v7);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  v8[5] = *a1;
  v9 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v8)(v8, a3, a4);
  v10 = v9;
  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    if ( v9 < 0 )
    {
      v8[5] &= 0xFFFFFFFA;
    }
    else if ( (*(_BYTE *)a1 & 4) != 0 )
    {
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    }
    else
    {
      v8 = 0;
    }
  }
  if ( v8 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v10;
}

```

## disassembly

```asm
0x18000b260  push    rbx
0x18000b262  push    rbp
0x18000b263  push    rsi
0x18000b264  push    rdi
0x18000b265  sub     rsp, 28h
0x18000b269  mov     rdi, r9
0x18000b26c  mov     rbp, r8
0x18000b26f  mov     rsi, rcx
0x18000b272  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b279  mov     ecx, 18h; unsigned __int64
0x18000b27e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b283  mov     rbx, rax
0x18000b286  test    rax, rax
0x18000b289  jz      loc_18000B326
0x18000b28f  mov     dword ptr [rax+0Ch], 1
0x18000b296  mov     dword ptr [rax+14h], 4
0x18000b29d  lea     rax, ??_7?$SimpleClassFactory@VCDeliveryOptimizationCleanup@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CDeliveryOptimizationCleanup,0>::`vftable'
0x18000b2a4  mov     [rbx], rax
0x18000b2a7  mov     rcx, rbx
0x18000b2aa  mov     rax, cs:off_18000F490
0x18000b2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2b6  nop
0x18000b2b7  mov     rax, [rbx]
0x18000b2ba  mov     rcx, rbx
0x18000b2bd  mov     rax, [rax+10h]
0x18000b2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c6  nop
0x18000b2c7  mov     eax, [rsi]
0x18000b2c9  mov     [rbx+14h], eax
0x18000b2cc  mov     rax, [rbx]
0x18000b2cf  mov     r8, rdi
0x18000b2d2  mov     rdx, rbp
0x18000b2d5  mov     rcx, rbx
0x18000b2d8  mov     rax, [rax]
0x18000b2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2e0  mov     edi, eax
0x18000b2e2  test    byte ptr [rsi], 1
0x18000b2e5  jz      short loc_18000B30D
0x18000b2e7  test    eax, eax
0x18000b2e9  js      short loc_18000B309
0x18000b2eb  test    byte ptr [rsi], 4
0x18000b2ee  jz      short loc_18000B305
0x18000b2f0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b2f7  mov     rax, [rcx]
0x18000b2fa  mov     rax, [rax+8]
0x18000b2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b303  jmp     short loc_18000B30D
0x18000b305  xor     ebx, ebx
0x18000b307  jmp     short loc_18000B30D
0x18000b309  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x18000b30d  test    rbx, rbx
0x18000b310  jz      short loc_18000B322
0x18000b312  mov     rax, [rbx]
0x18000b315  mov     rcx, rbx
0x18000b318  mov     rax, [rax+10h]
0x18000b31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b321  nop
0x18000b322  mov     eax, edi
0x18000b324  jmp     short loc_18000B32B
0x18000b326  mov     eax, 8007000Eh
0x18000b32b  add     rsp, 28h
0x18000b32f  pop     rdi
0x18000b330  pop     rsi
0x18000b331  pop     rbp
0x18000b332  pop     rbx
0x18000b333  retn
```
