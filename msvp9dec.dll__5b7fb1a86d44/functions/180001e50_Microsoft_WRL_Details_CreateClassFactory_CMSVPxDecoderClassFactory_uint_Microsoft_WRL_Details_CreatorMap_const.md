# Microsoft::WRL::Details::CreateClassFactory<CMSVPxDecoderClassFactory>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180001e50`
- end: `0x180001f05`
- name: `??$CreateClassFactory@VCMSVPxDecoderClassFactory@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001d40`
- `0x180001e50`
- `0x180001f40`
- `0x180002090`
- `0x180002cd4`
- `0x180003974`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<CMSVPxDecoderClassFactory>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  CMSVPxDecoderClassFactory *v7; // rax
  CMSVPxDecoderClassFactory *v8; // rax
  CMSVPxDecoderClassFactory *v9; // rbp
  int v10; // edi

  v7 = (CMSVPxDecoderClassFactory *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  if ( v7 )
  {
    v8 = CMSVPxDecoderClassFactory::CMSVPxDecoderClassFactory(v7);
    v9 = v8;
    if ( v8 )
    {
      Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(v8);
      Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(v9);
    }
    *((_DWORD *)v9 + 7) = *a1;
    v10 = Microsoft::WRL::Details::RuntimeClassBaseT<6>::AsIID<Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>>(
            v9,
            a3,
            a4);
    if ( (*a1 & 1) != 0 )
    {
      if ( v10 < 0 )
      {
        *((_DWORD *)v9 + 7) &= 0xFFFFFFFA;
      }
      else
      {
        if ( (*a1 & 4) == 0 )
          return (unsigned int)v10;
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      }
    }
    Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(v9);
    return (unsigned int)v10;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180001e50  mov     [rsp+arg_8], rbx
0x180001e55  mov     [rsp+arg_10], rsi
0x180001e5a  push    rdi
0x180001e5b  sub     rsp, 20h
0x180001e5f  mov     rbx, rcx
0x180001e62  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001e69  mov     ecx, 20h ; ' '; unsigned __int64
0x180001e6e  mov     rdi, r9
0x180001e71  mov     rsi, r8
0x180001e74  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001e79  test    rax, rax
0x180001e7c  jz      short loc_180001EF0
0x180001e7e  mov     rcx, rax; this
0x180001e81  mov     [rsp+28h+arg_0], rbp
0x180001e86  call    ??0CMSVPxDecoderClassFactory@@QEAA@XZ; CMSVPxDecoderClassFactory::CMSVPxDecoderClassFactory(void)
0x180001e8b  mov     rbp, rax
0x180001e8e  test    rax, rax
0x180001e91  jz      short loc_180001EA3
0x180001e93  mov     rcx, rax
0x180001e96  call    ?AddRef@?$ClassFactory@UIClassFactory@@VNil@Details@WRL@Microsoft@@V2345@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)
0x180001e9b  mov     rcx, rbp
0x180001e9e  call    ?Release@?$ClassFactory@UIClassFactory@@VNil@Details@WRL@Microsoft@@V2345@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180001ea3  mov     ecx, [rbx]
0x180001ea5  mov     r8, rdi
0x180001ea8  mov     [rbp+1Ch], ecx
0x180001eab  mov     rdx, rsi
0x180001eae  mov     rcx, rbp
0x180001eb1  call    ??$AsIID@V?$ClassFactory@UIClassFactory@@VNil@Details@WRL@Microsoft@@V2345@$0A@@WRL@Microsoft@@@?$RuntimeClassBaseT@$05@Details@WRL@Microsoft@@KAJPEAV?$ClassFactory@UIClassFactory@@VNil@Details@WRL@Microsoft@@V2345@$0A@@23@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<6>::AsIID<Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>>(Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0> *,_GUID const &,void * *)
0x180001eb6  mov     edi, eax
0x180001eb8  mov     eax, [rbx]
0x180001eba  test    al, 1
0x180001ebc  jz      short loc_180001EDF
0x180001ebe  test    edi, edi
0x180001ec0  js      short loc_180001EDB
0x180001ec2  test    al, 4
0x180001ec4  jz      short loc_180001EE7
0x180001ec6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180001ecd  mov     rdx, [rcx]
0x180001ed0  mov     rax, [rdx+8]
0x180001ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ed9  jmp     short loc_180001EDF
0x180001edb  and     dword ptr [rbp+1Ch], 0FFFFFFFAh
0x180001edf  mov     rcx, rbp
0x180001ee2  call    ?Release@?$ClassFactory@UIClassFactory@@VNil@Details@WRL@Microsoft@@V2345@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180001ee7  mov     rbp, [rsp+28h+arg_0]
0x180001eec  mov     eax, edi
0x180001eee  jmp     short loc_180001EF5
0x180001ef0  mov     eax, 8007000Eh
0x180001ef5  mov     rbx, [rsp+28h+arg_8]
0x180001efa  mov     rsi, [rsp+28h+arg_10]
0x180001eff  add     rsp, 20h
0x180001f03  pop     rdi
0x180001f04  retn
```
