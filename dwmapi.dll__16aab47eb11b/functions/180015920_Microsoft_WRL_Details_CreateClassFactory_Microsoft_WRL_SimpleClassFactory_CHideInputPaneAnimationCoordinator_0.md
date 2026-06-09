# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180015920`
- end: `0x1800159cf`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCHideInputPaneAnimationCoordinator@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180015920`
- `0x180015ab8`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>,Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>,>(&v13);
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
0x180015920  push    rbx
0x180015922  push    rbp
0x180015923  push    rsi
0x180015924  push    rdi
0x180015925  sub     rsp, 38h
0x180015929  mov     rsi, rcx
0x18001592c  mov     [rsp+58h+var_38], 0
0x180015935  lea     rcx, [rsp+58h+var_38]
0x18001593a  mov     rdi, r9
0x18001593d  mov     rbp, r8
0x180015940  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VCHideInputPaneAnimationCoordinator@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VCHideInputPaneAnimationCoordinator@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>,Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>,>(Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0> * *)
0x180015945  mov     ebx, eax
0x180015947  test    eax, eax
0x180015949  jns     short loc_180015965
0x18001594b  mov     rcx, [rsp+58h+var_38]
0x180015950  test    rcx, rcx
0x180015953  jz      short loc_180015961
0x180015955  mov     rdx, [rcx]
0x180015958  mov     rax, [rdx+10h]
0x18001595c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015961  mov     eax, ebx
0x180015963  jmp     short loc_1800159C6
0x180015965  mov     rbx, [rsp+58h+var_38]
0x18001596a  mov     r8, rdi
0x18001596d  mov     eax, [rsi]
0x18001596f  mov     rdx, rbp
0x180015972  mov     rcx, rbx
0x180015975  mov     [rbx+14h], eax
0x180015978  mov     rax, [rbx]
0x18001597b  mov     rax, [rax]
0x18001597e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015983  test    byte ptr [rsi], 1
0x180015986  mov     edi, eax
0x180015988  jz      short loc_1800159B0
0x18001598a  test    eax, eax
0x18001598c  js      short loc_1800159AC
0x18001598e  test    byte ptr [rsi], 4
0x180015991  jz      short loc_1800159A8
0x180015993  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001599a  mov     rdx, [rcx]
0x18001599d  mov     rax, [rdx+8]
0x1800159a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159a6  jmp     short loc_1800159B0
0x1800159a8  xor     ebx, ebx
0x1800159aa  jmp     short loc_1800159B0
0x1800159ac  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x1800159b0  test    rbx, rbx
0x1800159b3  jz      short loc_1800159C4
0x1800159b5  mov     rax, [rbx]
0x1800159b8  mov     rcx, rbx
0x1800159bb  mov     rax, [rax+10h]
0x1800159bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159c4  mov     eax, edi
0x1800159c6  add     rsp, 38h
0x1800159ca  pop     rdi
0x1800159cb  pop     rsi
0x1800159cc  pop     rbp
0x1800159cd  pop     rbx
0x1800159ce  retn
```
