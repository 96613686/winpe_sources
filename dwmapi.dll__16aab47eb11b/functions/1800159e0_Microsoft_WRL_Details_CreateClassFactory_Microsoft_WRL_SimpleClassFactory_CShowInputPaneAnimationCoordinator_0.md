# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CShowInputPaneAnimationCoordinator,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1800159e0`
- end: `0x180015a8f`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCShowInputPaneAnimationCoordinator@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800159e0`
- `0x180015b48`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CShowInputPaneAnimationCoordinator,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // ebx
  _DWORD *v9; // rbx
  __int64 (__fastcall ***v10)(_QWORD, __int64, __int64); // rcx
  int v11; // eax
  unsigned int v12; // edi
  _DWORD *v13; // [rsp+20h] [rbp-38h] BYREF

  v13 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CShowInputPaneAnimationCoordinator,0>,Microsoft::WRL::SimpleClassFactory<CShowInputPaneAnimationCoordinator,0>,>(&v13);
  if ( v7 >= 0 )
  {
    v9 = v13;
    v10 = (__int64 (__fastcall ***)(_QWORD, __int64, __int64))v13;
    v13[5] = *a1;
    v11 = (**v10)(v10, a3, a4);
    v12 = v11;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      if ( v11 < 0 )
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
    return v12;
  }
  else
  {
    if ( v13 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 16LL))(v13);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x1800159e0  push    rbx
0x1800159e2  push    rbp
0x1800159e3  push    rsi
0x1800159e4  push    rdi
0x1800159e5  sub     rsp, 38h
0x1800159e9  mov     rsi, rcx
0x1800159ec  mov     [rsp+58h+var_38], 0
0x1800159f5  lea     rcx, [rsp+58h+var_38]
0x1800159fa  mov     rdi, r9
0x1800159fd  mov     rbp, r8
0x180015a00  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VCShowInputPaneAnimationCoordinator@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VCShowInputPaneAnimationCoordinator@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CShowInputPaneAnimationCoordinator,0>,Microsoft::WRL::SimpleClassFactory<CShowInputPaneAnimationCoordinator,0>,>(Microsoft::WRL::SimpleClassFactory<CShowInputPaneAnimationCoordinator,0> * *)
0x180015a05  mov     ebx, eax
0x180015a07  test    eax, eax
0x180015a09  jns     short loc_180015A25
0x180015a0b  mov     rcx, [rsp+58h+var_38]
0x180015a10  test    rcx, rcx
0x180015a13  jz      short loc_180015A21
0x180015a15  mov     rdx, [rcx]
0x180015a18  mov     rax, [rdx+10h]
0x180015a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a21  mov     eax, ebx
0x180015a23  jmp     short loc_180015A86
0x180015a25  mov     rbx, [rsp+58h+var_38]
0x180015a2a  mov     r8, rdi
0x180015a2d  mov     eax, [rsi]
0x180015a2f  mov     rdx, rbp
0x180015a32  mov     rcx, rbx
0x180015a35  mov     [rbx+14h], eax
0x180015a38  mov     rax, [rbx]
0x180015a3b  mov     rax, [rax]
0x180015a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a43  test    byte ptr [rsi], 1
0x180015a46  mov     edi, eax
0x180015a48  jz      short loc_180015A70
0x180015a4a  test    eax, eax
0x180015a4c  js      short loc_180015A6C
0x180015a4e  test    byte ptr [rsi], 4
0x180015a51  jz      short loc_180015A68
0x180015a53  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180015a5a  mov     rdx, [rcx]
0x180015a5d  mov     rax, [rdx+8]
0x180015a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a66  jmp     short loc_180015A70
0x180015a68  xor     ebx, ebx
0x180015a6a  jmp     short loc_180015A70
0x180015a6c  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180015a70  test    rbx, rbx
0x180015a73  jz      short loc_180015A84
0x180015a75  mov     rax, [rbx]
0x180015a78  mov     rcx, rbx
0x180015a7b  mov     rax, [rax+10h]
0x180015a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a84  mov     eax, edi
0x180015a86  add     rsp, 38h
0x180015a8a  pop     rdi
0x180015a8b  pop     rsi
0x180015a8c  pop     rbp
0x180015a8d  pop     rbx
0x180015a8e  retn
```
