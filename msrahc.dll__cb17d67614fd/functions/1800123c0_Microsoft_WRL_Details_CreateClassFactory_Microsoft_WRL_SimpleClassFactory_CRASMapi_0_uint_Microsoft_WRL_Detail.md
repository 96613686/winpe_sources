# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CRASMapi,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1800123c0`
- end: `0x180012471`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCRASMapi@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800123c0`
- `0x180012478`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CRASMapi,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CRASMapi,0>,Microsoft::WRL::SimpleClassFactory<CRASMapi,0>,>(&v12);
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
0x1800123c0  push    rbx
0x1800123c2  push    rbp
0x1800123c3  push    rsi
0x1800123c4  push    rdi
0x1800123c5  sub     rsp, 38h
0x1800123c9  mov     rdi, r9
0x1800123cc  mov     rbp, r8
0x1800123cf  mov     rsi, rcx
0x1800123d2  mov     [rsp+58h+var_38], 0
0x1800123db  lea     rcx, [rsp+58h+var_38]
0x1800123e0  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VCRASMapi@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VCRASMapi@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CRASMapi,0>,Microsoft::WRL::SimpleClassFactory<CRASMapi,0>,>(Microsoft::WRL::SimpleClassFactory<CRASMapi,0> * *)
0x1800123e5  mov     ebx, eax
0x1800123e7  test    eax, eax
0x1800123e9  jns     short loc_180012406
0x1800123eb  mov     rcx, [rsp+58h+var_38]
0x1800123f0  test    rcx, rcx
0x1800123f3  jz      short loc_180012402
0x1800123f5  mov     rdx, [rcx]
0x1800123f8  mov     rax, [rdx+10h]
0x1800123fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012401  nop
0x180012402  mov     eax, ebx
0x180012404  jmp     short loc_180012468
0x180012406  mov     rbx, [rsp+58h+var_38]
0x18001240b  mov     eax, [rsi]
0x18001240d  mov     [rbx+14h], eax
0x180012410  mov     rax, [rbx]
0x180012413  mov     r8, rdi
0x180012416  mov     rdx, rbp
0x180012419  mov     rcx, rbx
0x18001241c  mov     rax, [rax]
0x18001241f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012424  mov     edi, eax
0x180012426  test    byte ptr [rsi], 1
0x180012429  jz      short loc_180012451
0x18001242b  test    eax, eax
0x18001242d  js      short loc_18001244D
0x18001242f  test    byte ptr [rsi], 4
0x180012432  jz      short loc_180012449
0x180012434  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001243b  mov     rax, [rcx]
0x18001243e  mov     rax, [rax+8]
0x180012442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012447  jmp     short loc_180012451
0x180012449  xor     ebx, ebx
0x18001244b  jmp     short loc_180012451
0x18001244d  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180012451  test    rbx, rbx
0x180012454  jz      short loc_180012466
0x180012456  mov     rax, [rbx]
0x180012459  mov     rcx, rbx
0x18001245c  mov     rax, [rax+10h]
0x180012460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012465  nop
0x180012466  mov     eax, edi
0x180012468  add     rsp, 38h
0x18001246c  pop     rdi
0x18001246d  pop     rsi
0x18001246e  pop     rbp
0x18001246f  pop     rbx
0x180012470  retn
```
