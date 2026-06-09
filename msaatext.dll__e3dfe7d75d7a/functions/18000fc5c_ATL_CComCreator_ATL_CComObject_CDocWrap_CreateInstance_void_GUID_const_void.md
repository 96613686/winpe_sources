# ATL::CComCreator<ATL::CComObject<CDocWrap>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000fc5c`
- end: `0x18000fd45`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDocWrap@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f5b0`

## callees

- `0x180001370`
- `0x18000c200`
- `0x18000fc5c`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fd2a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fd2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDocWrap>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v6; // esi
  CDocWrap *v7; // rax
  CDocWrap *v8; // rbx
  int v9; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CDocWrap *)operator new(0x30u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 5) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CDocWrap>::`vftable';
    _InterlockedIncrement(&dword_180024B28);
    v9 = *((_DWORD *)v7 + 2);
    if ( v9 != 0x7FFFFFFF )
    {
      *((_DWORD *)v7 + 2) = v9 + 1;
      if ( v9 != 2147483646 )
        *((_DWORD *)v7 + 2) = v9;
    }
    v6 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, a2, a3);
    if ( v6 )
    {
      *(_QWORD *)v8 = &ATL::CComObject<CDocWrap>::`vftable';
      *((_DWORD *)v8 + 2) = 1;
      _InterlockedDecrement(&dword_180024B28);
      CDocWrap::_Clear(v8);
      operator delete(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000fc5c  mov     [rsp+arg_8], rbx
0x18000fc61  mov     [rsp+arg_10], rbp
0x18000fc66  push    rsi
0x18000fc67  push    rdi
0x18000fc68  push    r15
0x18000fc6a  sub     rsp, 20h
0x18000fc6e  mov     rdi, r8
0x18000fc71  mov     rbp, rdx
0x18000fc74  test    r8, r8
0x18000fc77  jnz     short loc_18000FC83
0x18000fc79  mov     eax, 80004003h
0x18000fc7e  jmp     loc_18000FD32
0x18000fc83  mov     qword ptr [r8], 0
0x18000fc8a  mov     esi, 8007000Eh
0x18000fc8f  mov     ecx, 30h ; '0'; Size
0x18000fc94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fc99  mov     rbx, rax
0x18000fc9c  mov     [rsp+38h+arg_0], rax
0x18000fca1  test    rax, rax
0x18000fca4  jz      loc_18000FD30
0x18000fcaa  mov     dword ptr [rax+8], 0
0x18000fcb1  mov     qword ptr [rax+20h], 0
0x18000fcb9  mov     qword ptr [rax+28h], 0
0x18000fcc1  lea     r15, ??_7?$CComObject@VCDocWrap@@@ATL@@6B@; const ATL::CComObject<CDocWrap>::`vftable'
0x18000fcc8  mov     [rax], r15
0x18000fccb  lock inc cs:dword_180024B28
0x18000fcd2  test    rax, rax
0x18000fcd5  jz      short loc_18000FD30
0x18000fcd7  mov     ecx, [rax+8]
0x18000fcda  cmp     ecx, 7FFFFFFFh
0x18000fce0  jz      short loc_18000FCF3
0x18000fce2  lea     eax, [rcx+1]
0x18000fce5  mov     [rbx+8], eax
0x18000fce8  cmp     ecx, 7FFFFFFEh
0x18000fcee  jz      short loc_18000FCF3
0x18000fcf0  mov     [rbx+8], ecx
0x18000fcf3  mov     rax, [rbx]
0x18000fcf6  mov     r8, rdi
0x18000fcf9  mov     rdx, rbp
0x18000fcfc  mov     rcx, rbx
0x18000fcff  mov     rax, [rax]
0x18000fd02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd07  mov     esi, eax
0x18000fd09  test    eax, eax
0x18000fd0b  jz      short loc_18000FD30
0x18000fd0d  mov     [rbx], r15
0x18000fd10  mov     dword ptr [rbx+8], 1
0x18000fd17  lock dec cs:dword_180024B28
0x18000fd1e  mov     rcx, rbx; this
0x18000fd21  call    ?_Clear@CDocWrap@@AEAAXXZ; CDocWrap::_Clear(void)
0x18000fd26  nop
0x18000fd27  mov     rcx, rbx
0x18000fd2a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fd30  mov     eax, esi
0x18000fd32  mov     rbx, [rsp+38h+arg_8]
0x18000fd37  mov     rbp, [rsp+38h+arg_10]
0x18000fd3c  add     rsp, 20h
0x18000fd40  pop     r15
0x18000fd42  pop     rdi
0x18000fd43  pop     rsi
0x18000fd44  retn
```
