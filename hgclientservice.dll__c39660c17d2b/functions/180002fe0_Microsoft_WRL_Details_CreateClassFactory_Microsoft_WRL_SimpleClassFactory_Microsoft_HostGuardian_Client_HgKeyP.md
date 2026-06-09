# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgKeyProtection,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002fe0`
- end: `0x1800030b4`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VHgKeyProtection@Client@HostGuardian@Microsoft@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800017d8`
- `0x180002fe0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgKeyProtection,0>>(
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
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgKeyProtection,0>::`vftable';
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
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
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
0x180002fe0  push    rbx
0x180002fe2  push    rbp
0x180002fe3  push    rsi
0x180002fe4  push    rdi
0x180002fe5  sub     rsp, 28h
0x180002fe9  mov     rdi, r9
0x180002fec  mov     rbp, r8
0x180002fef  mov     rsi, rcx
0x180002ff2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002ff9  mov     ecx, 18h; unsigned __int64
0x180002ffe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003003  mov     rbx, rax
0x180003006  test    rax, rax
0x180003009  jz      loc_1800030A6
0x18000300f  mov     dword ptr [rax+0Ch], 1
0x180003016  mov     dword ptr [rax+14h], 4
0x18000301d  lea     rax, ??_7?$SimpleClassFactory@VHgKeyProtection@Client@HostGuardian@Microsoft@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgKeyProtection,0>::`vftable'
0x180003024  mov     [rbx], rax
0x180003027  mov     rcx, rbx
0x18000302a  mov     rax, cs:off_180018060
0x180003031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003036  nop
0x180003037  mov     rax, [rbx]
0x18000303a  mov     rcx, rbx
0x18000303d  mov     rax, [rax+10h]
0x180003041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003046  nop
0x180003047  mov     eax, [rsi]
0x180003049  mov     [rbx+14h], eax
0x18000304c  mov     rax, [rbx]
0x18000304f  mov     r8, rdi
0x180003052  mov     rdx, rbp
0x180003055  mov     rcx, rbx
0x180003058  mov     rax, [rax]
0x18000305b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003060  mov     edi, eax
0x180003062  test    byte ptr [rsi], 1
0x180003065  jz      short loc_18000308D
0x180003067  test    eax, eax
0x180003069  js      short loc_180003089
0x18000306b  test    byte ptr [rsi], 4
0x18000306e  jz      short loc_180003085
0x180003070  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003077  mov     rax, [rcx]
0x18000307a  mov     rax, [rax+8]
0x18000307e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003083  jmp     short loc_18000308D
0x180003085  xor     ebx, ebx
0x180003087  jmp     short loc_18000308D
0x180003089  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x18000308d  test    rbx, rbx
0x180003090  jz      short loc_1800030A2
0x180003092  mov     rax, [rbx]
0x180003095  mov     rcx, rbx
0x180003098  mov     rax, [rax+10h]
0x18000309c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a1  nop
0x1800030a2  mov     eax, edi
0x1800030a4  jmp     short loc_1800030AB
0x1800030a6  mov     eax, 8007000Eh
0x1800030ab  add     rsp, 28h
0x1800030af  pop     rdi
0x1800030b0  pop     rsi
0x1800030b1  pop     rbp
0x1800030b2  pop     rbx
0x1800030b3  retn
```
