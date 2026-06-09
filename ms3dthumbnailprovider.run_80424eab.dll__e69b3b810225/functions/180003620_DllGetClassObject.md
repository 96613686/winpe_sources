# DllGetClassObject

- ea: `0x180003620`
- end: `0x18000376a`
- name: `DllGetClassObject`
- size: `330`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001f14`
- `0x180002a8c`
- `0x180003620`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  HRESULT v7; // edi
  _QWORD *v8; // rax
  _QWORD *v9; // rbx

  if ( *(_OWORD *)rclsid == __PAIR128__(0xBCA4B3C213A4EFBAuLL, 0x4C501AE0E64164EBLL) )
  {
    v5 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v5;
    if ( v5 )
    {
      Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>((__int64)v5);
      *v6 = &ThumbnailClassFactory::`vftable';
      v6[1] = &ThumbnailClassFactory::`vftable'{for `IClassFactory'};
      v6[2] = &Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
      v7 = ((__int64 (__fastcall *)(_QWORD *, const IID *const, LPVOID *))ThumbnailClassFactory::`vftable')(
             v6,
             riid,
             ppv);
    }
    else
    {
      v7 = -2147024882;
      v6 = 0;
    }
    if ( v6 )
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  }
  else
  {
    v7 = -2147221231;
    if ( *(_QWORD *)&rclsid->Data1 == 4981954505213530000LL && *(_QWORD *)rclsid->Data4 == 0xFF6EBCB4CA40A4A4uLL )
    {
      v8 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      v9 = v8;
      if ( v8 )
      {
        Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>((__int64)v8);
        *v9 = &Shell3DPrintClassFactory::`vftable';
        v9[1] = &Shell3DPrintClassFactory::`vftable'{for `IClassFactory'};
        v9[2] = &Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
        v7 = ((__int64 (__fastcall *)(_QWORD *, const IID *const, LPVOID *))Shell3DPrintClassFactory::`vftable')(
               v9,
               riid,
               ppv);
      }
      else
      {
        v7 = -2147024882;
        v9 = 0;
      }
      if ( v9 )
        (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180003620  push    rbx
0x180003622  push    rbp
0x180003623  push    rsi
0x180003624  push    rdi
0x180003625  sub     rsp, 28h
0x180003629  mov     rsi, r8
0x18000362c  mov     rbp, rdx
0x18000362f  mov     rax, cs:qword_18000CEE0
0x180003636  cmp     rax, [rcx]
0x180003639  jnz     loc_1800036C7
0x18000363f  mov     rax, cs:qword_18000CEE8
0x180003646  cmp     rax, [rcx+8]
0x18000364a  jnz     short loc_1800036C7
0x18000364c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003653  mov     ecx, 40h ; '@'; unsigned __int64
0x180003658  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000365d  mov     rbx, rax
0x180003660  test    rax, rax
0x180003663  jz      short loc_1800036A6
0x180003665  mov     rcx, rax
0x180003668  call    ??0?$ClassFactory@UIClassFactory@@VFtmBase@WRL@Microsoft@@VNil@Details@34@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>(void)
0x18000366d  lea     rax, ??_7ThumbnailClassFactory@@6B@; const ThumbnailClassFactory::`vftable'
0x180003674  mov     [rbx], rax
0x180003677  lea     rax, ??_7ThumbnailClassFactory@@6BIClassFactory@@@; const ThumbnailClassFactory::`vftable'{for `IClassFactory'}
0x18000367e  mov     [rbx+8], rax
0x180003682  lea     rax, ??_7?$ClassFactory@UIClassFactory@@VFtmBase@WRL@Microsoft@@VNil@Details@34@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$05@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@VNil@523@V6523@@Details@12@@; const Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180003689  mov     [rbx+10h], rax
0x18000368d  mov     r8, rsi
0x180003690  mov     rdx, rbp
0x180003693  mov     rcx, rbx
0x180003696  mov     rax, cs:??_7ThumbnailClassFactory@@6B@; const ThumbnailClassFactory::`vftable'
0x18000369d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036a2  mov     edi, eax
0x1800036a4  jmp     short loc_1800036AD
0x1800036a6  mov     edi, 8007000Eh
0x1800036ab  xor     ebx, ebx
0x1800036ad  test    rbx, rbx
0x1800036b0  jz      short loc_1800036C2
0x1800036b2  mov     rax, [rbx]
0x1800036b5  mov     rcx, rbx
0x1800036b8  mov     rax, [rax+10h]
0x1800036bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c1  nop
0x1800036c2  jmp     loc_18000375F
0x1800036c7  mov     edi, 80040111h
0x1800036cc  mov     rax, cs:qword_18000CED0
0x1800036d3  cmp     rax, [rcx]
0x1800036d6  jnz     loc_18000375F
0x1800036dc  mov     rax, cs:qword_18000CED8
0x1800036e3  cmp     rax, [rcx+8]
0x1800036e7  jnz     short loc_18000375F
0x1800036e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800036f0  mov     ecx, 40h ; '@'; unsigned __int64
0x1800036f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800036fa  mov     rbx, rax
0x1800036fd  test    rax, rax
0x180003700  jz      short loc_180003743
0x180003702  mov     rcx, rax
0x180003705  call    ??0?$ClassFactory@UIClassFactory@@VFtmBase@WRL@Microsoft@@VNil@Details@34@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>(void)
0x18000370a  lea     rax, ??_7Shell3DPrintClassFactory@@6B@; const Shell3DPrintClassFactory::`vftable'
0x180003711  mov     [rbx], rax
0x180003714  lea     rax, ??_7Shell3DPrintClassFactory@@6BIClassFactory@@@; const Shell3DPrintClassFactory::`vftable'{for `IClassFactory'}
0x18000371b  mov     [rbx+8], rax
0x18000371f  lea     rax, ??_7?$ClassFactory@UIClassFactory@@VFtmBase@WRL@Microsoft@@VNil@Details@34@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$05@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@VNil@523@V6523@@Details@12@@; const Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180003726  mov     [rbx+10h], rax
0x18000372a  mov     r8, rsi
0x18000372d  mov     rdx, rbp
0x180003730  mov     rcx, rbx
0x180003733  mov     rax, cs:??_7Shell3DPrintClassFactory@@6B@; const Shell3DPrintClassFactory::`vftable'
0x18000373a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000373f  mov     edi, eax
0x180003741  jmp     short loc_18000374A
0x180003743  mov     edi, 8007000Eh
0x180003748  xor     ebx, ebx
0x18000374a  test    rbx, rbx
0x18000374d  jz      short loc_18000375F
0x18000374f  mov     rcx, [rbx]
0x180003752  mov     rax, [rcx+10h]
0x180003756  mov     rcx, rbx
0x180003759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000375e  nop
0x18000375f  mov     eax, edi
0x180003761  add     rsp, 28h
0x180003765  pop     rdi
0x180003766  pop     rsi
0x180003767  pop     rbp
0x180003768  pop     rbx
0x180003769  retn
```
