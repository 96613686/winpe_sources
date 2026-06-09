# ATL::CComCreator<ATL::CComObject<CPortableWorkspaceLauncher>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000bdb0`
- end: `0x18000bea1`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPortableWorkspaceLauncher@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bcb0`

## callees

- `0x1800016e4`
- `0x18000bdb0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPortableWorkspaceLauncher>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // ecx
  _DWORD *v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x10u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CPortableWorkspaceLauncher>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    v9 = v8[2];
    if ( v9 != 0x7FFFFFFF )
    {
      v8[2] = v9 + 1;
      if ( v9 != 2147483646 )
        v8[2] = v9;
    }
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 48LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000bdb0  mov     [rsp+arg_10], r8
0x18000bdb5  mov     [rsp+arg_8], rdx
0x18000bdba  mov     [rsp+arg_0], rcx
0x18000bdbf  push    rbx
0x18000bdc0  push    rsi
0x18000bdc1  push    rdi
0x18000bdc2  push    r14
0x18000bdc4  sub     rsp, 28h
0x18000bdc8  mov     rsi, r8
0x18000bdcb  mov     r14, rdx
0x18000bdce  test    r8, r8
0x18000bdd1  jnz     short loc_18000BDDD
0x18000bdd3  mov     eax, 80004003h
0x18000bdd8  jmp     loc_18000BE97
0x18000bddd  mov     qword ptr [r8], 0
0x18000bde4  mov     edi, 8007000Eh
0x18000bde9  mov     dword ptr [rsp+48h+arg_0], edi
0x18000bded  mov     [rsp+48h+arg_18], 0
0x18000bdf6  mov     ecx, 10h; Size
0x18000bdfb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000be00  mov     rbx, rax
0x18000be03  test    rbx, rbx
0x18000be06  jz      short loc_18000BE2C
0x18000be08  mov     dword ptr [rax+8], 0
0x18000be0f  lea     rax, ??_7?$CComObject@VCPortableWorkspaceLauncher@@@ATL@@6B@; const ATL::CComObject<CPortableWorkspaceLauncher>::`vftable'
0x18000be16  mov     [rbx], rax
0x18000be19  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000be20  mov     rax, [rcx]
0x18000be23  mov     rax, [rax+8]
0x18000be27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be2c  mov     [rsp+48h+arg_18], rbx
0x18000be31  jmp     short loc_18000BE46
0x18000be33  mov     rsi, [rsp+48h+arg_10]
0x18000be38  mov     r14, [rsp+48h+arg_8]
0x18000be3d  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000be41  mov     rbx, [rsp+48h+arg_18]
0x18000be46  test    rbx, rbx
0x18000be49  jz      short loc_18000BE95
0x18000be4b  mov     ecx, [rbx+8]
0x18000be4e  cmp     ecx, 7FFFFFFFh
0x18000be54  jz      short loc_18000BE67
0x18000be56  lea     eax, [rcx+1]
0x18000be59  mov     [rbx+8], eax
0x18000be5c  cmp     ecx, 7FFFFFFEh
0x18000be62  jz      short loc_18000BE67
0x18000be64  mov     [rbx+8], ecx
0x18000be67  mov     rax, [rbx]
0x18000be6a  mov     r8, rsi
0x18000be6d  mov     rdx, r14
0x18000be70  mov     rcx, rbx
0x18000be73  mov     rax, [rax]
0x18000be76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be7b  mov     edi, eax
0x18000be7d  test    eax, eax
0x18000be7f  jz      short loc_18000BE95
0x18000be81  mov     rdx, [rbx]
0x18000be84  mov     rax, [rdx+30h]
0x18000be88  mov     edx, 1
0x18000be8d  mov     rcx, rbx
0x18000be90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be95  mov     eax, edi
0x18000be97  add     rsp, 28h
0x18000be9b  pop     r14
0x18000be9d  pop     rdi
0x18000be9e  pop     rsi
0x18000be9f  pop     rbx
0x18000bea0  retn
```
