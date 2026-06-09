# Microsoft::WRL::SimpleClassFactory<DeliveryOptimizationUser,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000c2d0`
- end: `0x18000c3f4`
- name: `?CreateInstance@?$SimpleClassFactory@VDeliveryOptimizationUser@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `292`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800022cc`
- `0x18000c2d0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000c2f4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000c2f4`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<DeliveryOptimizationUser,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // edi
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v13)(_QWORD, __int64, _QWORD *); // [rsp+58h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
    return v6;
  }
  v13 = 0;
  v7 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    v7[3] = 1;
    *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDeliveryOptimizationUser>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v8 = &DeliveryOptimizationUser::`vftable';
    v9 = ((__int64 (__fastcall *)(_DWORD *, GUID *, _QWORD))DeliveryOptimizationUser::`vftable')(
           v8,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v13);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v9 >= 0 )
    {
      v6 = (**v13)(v13, a3, a4);
      v12 = v13;
      if ( v13 )
      {
        v13 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v12)[2])(v12);
      }
      return v6;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  v10 = v13;
  if ( v13 )
  {
    v13 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v10)[2])(v10);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c2d0  push    rbx
0x18000c2d2  push    rbp
0x18000c2d3  push    rsi
0x18000c2d4  push    rdi
0x18000c2d5  sub     rsp, 28h
0x18000c2d9  mov     rsi, r9
0x18000c2dc  mov     rbp, r8
0x18000c2df  mov     qword ptr [r9], 0
0x18000c2e6  test    rdx, rdx
0x18000c2e9  jz      short loc_18000C2FF
0x18000c2eb  xor     edx, edx
0x18000c2ed  mov     ebx, 80040110h
0x18000c2f2  mov     ecx, ebx
0x18000c2f4  call    cs:__imp_RoOriginateError
0x18000c2fa  jmp     loc_18000C3E9
0x18000c2ff  mov     [rsp+48h+arg_8], 0
0x18000c308  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c30f  mov     ecx, 10h; unsigned __int64
0x18000c314  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c319  mov     rbx, rax
0x18000c31c  test    rax, rax
0x18000c31f  jnz     short loc_18000C328
0x18000c321  mov     edi, 8007000Eh
0x18000c326  jmp     short loc_18000C38D
0x18000c328  mov     dword ptr [rax+0Ch], 1
0x18000c32f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDeliveryOptimizationUser@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDeliveryOptimizationUser>::`vftable'
0x18000c336  mov     [rbx], rax
0x18000c339  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000c340  test    rcx, rcx
0x18000c343  jz      short loc_18000C352
0x18000c345  mov     rax, [rcx]
0x18000c348  mov     rax, [rax+8]
0x18000c34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c351  nop
0x18000c352  lea     rax, ??_7DeliveryOptimizationUser@@6B@; const DeliveryOptimizationUser::`vftable'
0x18000c359  mov     [rbx], rax
0x18000c35c  lea     r8, [rsp+48h+arg_8]
0x18000c361  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000c368  mov     rcx, rbx
0x18000c36b  mov     rax, cs:??_7DeliveryOptimizationUser@@6B@; const DeliveryOptimizationUser::`vftable'
0x18000c372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c377  mov     edi, eax
0x18000c379  mov     rax, [rbx]
0x18000c37c  mov     rcx, rbx
0x18000c37f  mov     rax, [rax+10h]
0x18000c383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c388  nop
0x18000c389  test    edi, edi
0x18000c38b  jns     short loc_18000C3B1
0x18000c38d  mov     rcx, [rsp+48h+arg_8]
0x18000c392  test    rcx, rcx
0x18000c395  jz      short loc_18000C3AD
0x18000c397  mov     [rsp+48h+arg_8], 0
0x18000c3a0  mov     rdx, [rcx]
0x18000c3a3  mov     rax, [rdx+10h]
0x18000c3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ac  nop
0x18000c3ad  mov     eax, edi
0x18000c3af  jmp     short loc_18000C3EB
0x18000c3b1  mov     rcx, [rsp+48h+arg_8]
0x18000c3b6  mov     rax, [rcx]
0x18000c3b9  mov     r8, rsi
0x18000c3bc  mov     rdx, rbp
0x18000c3bf  mov     rax, [rax]
0x18000c3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c7  mov     ebx, eax
0x18000c3c9  mov     rcx, [rsp+48h+arg_8]
0x18000c3ce  test    rcx, rcx
0x18000c3d1  jz      short loc_18000C3E9
0x18000c3d3  mov     [rsp+48h+arg_8], 0
0x18000c3dc  mov     rdx, [rcx]
0x18000c3df  mov     rax, [rdx+10h]
0x18000c3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e8  nop
0x18000c3e9  mov     eax, ebx
0x18000c3eb  add     rsp, 28h
0x18000c3ef  pop     rdi
0x18000c3f0  pop     rsi
0x18000c3f1  pop     rbp
0x18000c3f2  pop     rbx
0x18000c3f3  retn
```
