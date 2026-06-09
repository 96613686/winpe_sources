# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180012f30`
- end: `0x180012fe2`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VConsolePropertySheetHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012f30`
- `0x180012fe8`
- `0x18001a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // ebx
  _DWORD *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  _DWORD *v12; // [rsp+20h] [rbp-38h] BYREF

  v12 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>,Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>,>(&v12);
  if ( v7 >= 0 )
  {
    v9 = v12;
    v12[5] = *a1;
    v10 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v9)(v9, a3, a4);
    v11 = v10;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      if ( v10 < 0 )
      {
        v9[5] &= 0xFFFFFFFA;
      }
      else if ( (*(_BYTE *)a1 & 4) != 0 )
      {
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      }
      else
      {
        v9 = 0;
      }
    }
    if ( v9 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    return v11;
  }
  else
  {
    if ( v12 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 16LL))(v12);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180012f30  push    rbx
0x180012f32  push    rbp
0x180012f33  push    rsi
0x180012f34  push    rdi
0x180012f35  sub     rsp, 38h
0x180012f39  mov     rdi, r9
0x180012f3c  mov     rbp, r8
0x180012f3f  mov     rsi, rcx
0x180012f42  mov     [rsp+58h+var_38], 0
0x180012f4b  lea     rcx, [rsp+58h+var_38]
0x180012f50  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VConsolePropertySheetHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VConsolePropertySheetHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>,Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>,>(Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0> * *)
0x180012f55  mov     ebx, eax
0x180012f57  test    eax, eax
0x180012f59  jns     short loc_180012F76
0x180012f5b  mov     rcx, [rsp+58h+var_38]
0x180012f60  test    rcx, rcx
0x180012f63  jz      short loc_180012F72
0x180012f65  mov     rdx, [rcx]
0x180012f68  mov     rax, [rdx+10h]
0x180012f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f71  nop
0x180012f72  mov     eax, ebx
0x180012f74  jmp     short loc_180012FD8
0x180012f76  mov     rbx, [rsp+58h+var_38]
0x180012f7b  mov     eax, [rsi]
0x180012f7d  mov     [rbx+14h], eax
0x180012f80  mov     rax, [rbx]
0x180012f83  mov     r8, rdi
0x180012f86  mov     rdx, rbp
0x180012f89  mov     rcx, rbx
0x180012f8c  mov     rax, [rax]
0x180012f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f94  mov     edi, eax
0x180012f96  test    byte ptr [rsi], 1
0x180012f99  jz      short loc_180012FC1
0x180012f9b  test    eax, eax
0x180012f9d  js      short loc_180012FBD
0x180012f9f  test    byte ptr [rsi], 4
0x180012fa2  jz      short loc_180012FB9
0x180012fa4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180012fab  mov     rax, [rcx]
0x180012fae  mov     rax, [rax+8]
0x180012fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fb7  jmp     short loc_180012FC1
0x180012fb9  xor     ebx, ebx
0x180012fbb  jmp     short loc_180012FC1
0x180012fbd  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180012fc1  test    rbx, rbx
0x180012fc4  jz      short loc_180012FD6
0x180012fc6  mov     rax, [rbx]
0x180012fc9  mov     rcx, rbx
0x180012fcc  mov     rax, [rax+10h]
0x180012fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fd5  nop
0x180012fd6  mov     eax, edi
0x180012fd8  add     rsp, 38h
0x180012fdc  pop     rdi
0x180012fdd  pop     rsi
0x180012fde  pop     rbp
0x180012fdf  pop     rbx
0x180012fe0  retn
```
