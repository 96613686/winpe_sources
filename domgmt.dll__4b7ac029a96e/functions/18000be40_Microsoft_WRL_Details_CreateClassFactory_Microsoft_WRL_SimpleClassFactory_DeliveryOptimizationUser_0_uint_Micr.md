# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<DeliveryOptimizationUser,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x18000be40`
- end: `0x18000bf14`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VDeliveryOptimizationUser@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800022cc`
- `0x18000be40`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<DeliveryOptimizationUser,0>>(
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
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<DeliveryOptimizationUser,0>::`vftable';
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
0x18000be40  push    rbx
0x18000be42  push    rbp
0x18000be43  push    rsi
0x18000be44  push    rdi
0x18000be45  sub     rsp, 28h
0x18000be49  mov     rdi, r9
0x18000be4c  mov     rbp, r8
0x18000be4f  mov     rsi, rcx
0x18000be52  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000be59  mov     ecx, 18h; unsigned __int64
0x18000be5e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000be63  mov     rbx, rax
0x18000be66  test    rax, rax
0x18000be69  jz      loc_18000BF06
0x18000be6f  mov     dword ptr [rax+0Ch], 1
0x18000be76  mov     dword ptr [rax+14h], 4
0x18000be7d  lea     rax, ??_7?$SimpleClassFactory@VDeliveryOptimizationUser@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<DeliveryOptimizationUser,0>::`vftable'
0x18000be84  mov     [rbx], rax
0x18000be87  mov     rcx, rbx
0x18000be8a  mov     rax, cs:off_18000F560
0x18000be91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be96  nop
0x18000be97  mov     rax, [rbx]
0x18000be9a  mov     rcx, rbx
0x18000be9d  mov     rax, [rax+10h]
0x18000bea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bea6  nop
0x18000bea7  mov     eax, [rsi]
0x18000bea9  mov     [rbx+14h], eax
0x18000beac  mov     rax, [rbx]
0x18000beaf  mov     r8, rdi
0x18000beb2  mov     rdx, rbp
0x18000beb5  mov     rcx, rbx
0x18000beb8  mov     rax, [rax]
0x18000bebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bec0  mov     edi, eax
0x18000bec2  test    byte ptr [rsi], 1
0x18000bec5  jz      short loc_18000BEED
0x18000bec7  test    eax, eax
0x18000bec9  js      short loc_18000BEE9
0x18000becb  test    byte ptr [rsi], 4
0x18000bece  jz      short loc_18000BEE5
0x18000bed0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000bed7  mov     rax, [rcx]
0x18000beda  mov     rax, [rax+8]
0x18000bede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee3  jmp     short loc_18000BEED
0x18000bee5  xor     ebx, ebx
0x18000bee7  jmp     short loc_18000BEED
0x18000bee9  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x18000beed  test    rbx, rbx
0x18000bef0  jz      short loc_18000BF02
0x18000bef2  mov     rax, [rbx]
0x18000bef5  mov     rcx, rbx
0x18000bef8  mov     rax, [rax+10h]
0x18000befc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf01  nop
0x18000bf02  mov     eax, edi
0x18000bf04  jmp     short loc_18000BF0B
0x18000bf06  mov     eax, 8007000Eh
0x18000bf0b  add     rsp, 28h
0x18000bf0f  pop     rdi
0x18000bf10  pop     rsi
0x18000bf11  pop     rbp
0x18000bf12  pop     rbx
0x18000bf13  retn
```
