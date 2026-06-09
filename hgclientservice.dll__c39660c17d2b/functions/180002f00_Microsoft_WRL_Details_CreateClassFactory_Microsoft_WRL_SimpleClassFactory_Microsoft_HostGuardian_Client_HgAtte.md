# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgAttestation,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002f00`
- end: `0x180002fd4`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VHgAttestation@Client@HostGuardian@Microsoft@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800017d8`
- `0x180002f00`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgAttestation,0>>(
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
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgAttestation,0>::`vftable';
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
0x180002f00  push    rbx
0x180002f02  push    rbp
0x180002f03  push    rsi
0x180002f04  push    rdi
0x180002f05  sub     rsp, 28h
0x180002f09  mov     rdi, r9
0x180002f0c  mov     rbp, r8
0x180002f0f  mov     rsi, rcx
0x180002f12  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002f19  mov     ecx, 18h; unsigned __int64
0x180002f1e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002f23  mov     rbx, rax
0x180002f26  test    rax, rax
0x180002f29  jz      loc_180002FC6
0x180002f2f  mov     dword ptr [rax+0Ch], 1
0x180002f36  mov     dword ptr [rax+14h], 4
0x180002f3d  lea     rax, ??_7?$SimpleClassFactory@VHgAttestation@Client@HostGuardian@Microsoft@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgAttestation,0>::`vftable'
0x180002f44  mov     [rbx], rax
0x180002f47  mov     rcx, rbx
0x180002f4a  mov     rax, cs:off_1800180B8
0x180002f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f56  nop
0x180002f57  mov     rax, [rbx]
0x180002f5a  mov     rcx, rbx
0x180002f5d  mov     rax, [rax+10h]
0x180002f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f66  nop
0x180002f67  mov     eax, [rsi]
0x180002f69  mov     [rbx+14h], eax
0x180002f6c  mov     rax, [rbx]
0x180002f6f  mov     r8, rdi
0x180002f72  mov     rdx, rbp
0x180002f75  mov     rcx, rbx
0x180002f78  mov     rax, [rax]
0x180002f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f80  mov     edi, eax
0x180002f82  test    byte ptr [rsi], 1
0x180002f85  jz      short loc_180002FAD
0x180002f87  test    eax, eax
0x180002f89  js      short loc_180002FA9
0x180002f8b  test    byte ptr [rsi], 4
0x180002f8e  jz      short loc_180002FA5
0x180002f90  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002f97  mov     rax, [rcx]
0x180002f9a  mov     rax, [rax+8]
0x180002f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa3  jmp     short loc_180002FAD
0x180002fa5  xor     ebx, ebx
0x180002fa7  jmp     short loc_180002FAD
0x180002fa9  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180002fad  test    rbx, rbx
0x180002fb0  jz      short loc_180002FC2
0x180002fb2  mov     rax, [rbx]
0x180002fb5  mov     rcx, rbx
0x180002fb8  mov     rax, [rax+10h]
0x180002fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc1  nop
0x180002fc2  mov     eax, edi
0x180002fc4  jmp     short loc_180002FCB
0x180002fc6  mov     eax, 8007000Eh
0x180002fcb  add     rsp, 28h
0x180002fcf  pop     rdi
0x180002fd0  pop     rsi
0x180002fd1  pop     rbp
0x180002fd2  pop     rbx
0x180002fd3  retn
```
