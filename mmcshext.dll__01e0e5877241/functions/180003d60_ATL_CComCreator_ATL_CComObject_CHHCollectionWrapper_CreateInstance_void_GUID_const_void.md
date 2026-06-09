# ATL::CComCreator<ATL::CComObject<CHHCollectionWrapper>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003d60`
- end: `0x180003e49`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCHHCollectionWrapper@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180003a40`

## callees

- `0x180001140`
- `0x180003d60`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003e2e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003e2e`
- `hhsetup!??0CCollection@@QEAA@XZ` at `0x180003dc1`
- `hhsetup!??0CCollection@@QEAA@XZ` at `0x180003dc1`
- `hhsetup!??1CCollection@@QEAA@XZ` at `0x180003e25`
- `hhsetup!??1CCollection@@QEAA@XZ` at `0x180003e25`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CHHCollectionWrapper>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  char *v7; // rax
  _DWORD *v8; // rbx
  int v9; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (char *)operator new(0x400u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 0;
    CCollection::CCollection((CCollection *)(v7 + 16));
    *(_QWORD *)v8 = &ATL::CComObject<CHHCollectionWrapper>::`vftable';
    _InterlockedIncrement(&dword_180012EE8);
  }
  else
  {
    v8 = 0;
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
    v6 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v8)(v8, a2, a3);
    if ( v6 )
    {
      *(_QWORD *)v8 = &ATL::CComObject<CHHCollectionWrapper>::`vftable';
      v8[2] = 1;
      _InterlockedDecrement(&dword_180012EE8);
      CCollection::~CCollection((CCollection *)(v8 + 4));
      operator delete(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180003d60  mov     [rsp+arg_8], rbx
0x180003d65  mov     [rsp+arg_10], rbp
0x180003d6a  mov     [rsp+arg_0], rcx
0x180003d6f  push    rsi
0x180003d70  push    rdi
0x180003d71  push    r14
0x180003d73  sub     rsp, 20h
0x180003d77  mov     rdi, r8
0x180003d7a  mov     rbp, rdx
0x180003d7d  test    r8, r8
0x180003d80  jnz     short loc_180003D8C
0x180003d82  mov     eax, 80004003h
0x180003d87  jmp     loc_180003E36
0x180003d8c  mov     qword ptr [r8], 0
0x180003d93  mov     esi, 8007000Eh
0x180003d98  mov     ecx, 400h; Size
0x180003d9d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003da2  mov     rbx, rax
0x180003da5  mov     [rsp+38h+arg_0], rax
0x180003daa  lea     r14, ??_7?$CComObject@VCHHCollectionWrapper@@@ATL@@6B@; const ATL::CComObject<CHHCollectionWrapper>::`vftable'
0x180003db1  test    rax, rax
0x180003db4  jz      short loc_180003DD3
0x180003db6  mov     dword ptr [rax+8], 0
0x180003dbd  lea     rcx, [rax+10h]
0x180003dc1  call    cs:__imp_??0CCollection@@QEAA@XZ; CCollection::CCollection(void)
0x180003dc7  mov     [rbx], r14
0x180003dca  lock inc cs:dword_180012EE8
0x180003dd1  jmp     short loc_180003DD5
0x180003dd3  xor     ebx, ebx
0x180003dd5  test    rbx, rbx
0x180003dd8  jz      short loc_180003E34
0x180003dda  mov     ecx, [rbx+8]
0x180003ddd  cmp     ecx, 7FFFFFFFh
0x180003de3  jz      short loc_180003DF6
0x180003de5  lea     eax, [rcx+1]
0x180003de8  mov     [rbx+8], eax
0x180003deb  cmp     ecx, 7FFFFFFEh
0x180003df1  jz      short loc_180003DF6
0x180003df3  mov     [rbx+8], ecx
0x180003df6  mov     rax, [rbx]
0x180003df9  mov     r8, rdi
0x180003dfc  mov     rdx, rbp
0x180003dff  mov     rcx, rbx
0x180003e02  mov     rax, [rax]
0x180003e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0a  mov     esi, eax
0x180003e0c  test    eax, eax
0x180003e0e  jz      short loc_180003E34
0x180003e10  mov     [rbx], r14
0x180003e13  mov     dword ptr [rbx+8], 1
0x180003e1a  lock dec cs:dword_180012EE8
0x180003e21  lea     rcx, [rbx+10h]
0x180003e25  call    cs:__imp_??1CCollection@@QEAA@XZ; CCollection::~CCollection(void)
0x180003e2b  mov     rcx, rbx
0x180003e2e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003e34  mov     eax, esi
0x180003e36  mov     rbx, [rsp+38h+arg_8]
0x180003e3b  mov     rbp, [rsp+38h+arg_10]
0x180003e40  add     rsp, 20h
0x180003e44  pop     r14
0x180003e46  pop     rdi
0x180003e47  pop     rsi
0x180003e48  retn
```
