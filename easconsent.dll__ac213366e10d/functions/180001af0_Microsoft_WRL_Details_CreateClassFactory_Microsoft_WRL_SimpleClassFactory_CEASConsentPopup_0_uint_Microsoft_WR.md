# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CEASConsentPopup,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180001af0`
- end: `0x180001bc1`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCEASConsentPopup@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001548`
- `0x180001af0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CEASConsentPopup,0>>(
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
  if ( v7 )
  {
    v7[3] = 1;
    v7[5] = 4;
    *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CEASConsentPopup,0>::`vftable';
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
      else
      {
        if ( (*(_BYTE *)a1 & 4) != 0 )
          (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                               + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
        else
          v8 = 0;
        if ( !v8 )
          return v10;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    return v10;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180001af0  push    rbx
0x180001af2  push    rbp
0x180001af3  push    rsi
0x180001af4  push    rdi
0x180001af5  sub     rsp, 28h
0x180001af9  mov     rsi, rcx
0x180001afc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001b03  mov     ecx, 18h; unsigned __int64
0x180001b08  mov     rdi, r9
0x180001b0b  mov     rbp, r8
0x180001b0e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001b13  mov     rbx, rax
0x180001b16  test    rax, rax
0x180001b19  jz      loc_180001BB3
0x180001b1f  mov     dword ptr [rax+0Ch], 1
0x180001b26  mov     rcx, rbx
0x180001b29  mov     dword ptr [rax+14h], 4
0x180001b30  lea     rax, ??_7?$SimpleClassFactory@VCEASConsentPopup@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CEASConsentPopup,0>::`vftable'
0x180001b37  mov     [rbx], rax
0x180001b3a  mov     rax, cs:off_1800050B0
0x180001b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b46  mov     rax, [rbx]
0x180001b49  mov     rcx, rbx
0x180001b4c  mov     rax, [rax+10h]
0x180001b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b55  mov     eax, [rsi]
0x180001b57  mov     r8, rdi
0x180001b5a  mov     [rbx+14h], eax
0x180001b5d  mov     rdx, rbp
0x180001b60  mov     rax, [rbx]
0x180001b63  mov     rcx, rbx
0x180001b66  mov     rax, [rax]
0x180001b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b6e  test    byte ptr [rsi], 1
0x180001b71  mov     edi, eax
0x180001b73  jz      short loc_180001BA0
0x180001b75  test    eax, eax
0x180001b77  js      short loc_180001B9C
0x180001b79  test    byte ptr [rsi], 4
0x180001b7c  jz      short loc_180001B93
0x180001b7e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180001b85  mov     rdx, [rcx]
0x180001b88  mov     rax, [rdx+8]
0x180001b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b91  jmp     short loc_180001B95
0x180001b93  xor     ebx, ebx
0x180001b95  test    rbx, rbx
0x180001b98  jz      short loc_180001BAF
0x180001b9a  jmp     short loc_180001BA0
0x180001b9c  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180001ba0  mov     rax, [rbx]
0x180001ba3  mov     rcx, rbx
0x180001ba6  mov     rax, [rax+10h]
0x180001baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001baf  mov     eax, edi
0x180001bb1  jmp     short loc_180001BB8
0x180001bb3  mov     eax, 8007000Eh
0x180001bb8  add     rsp, 28h
0x180001bbc  pop     rdi
0x180001bbd  pop     rsi
0x180001bbe  pop     rbp
0x180001bbf  pop     rbx
0x180001bc0  retn
```
