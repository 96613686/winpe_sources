# ATL::CComCreator<ATL::CComAggObject<CExtractIcon>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003b30`
- end: `0x180003c3a`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCExtractIcon@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003a20`

## callees

- `0x180001140`
- `0x180003b30`
- `0x18000931c`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003c1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003c1b`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CExtractIcon>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  _QWORD *v8; // rax
  _DWORD *v9; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0x48u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CExtractIcon>::`vftable';
    v8[5] = &CStr::`vftable';
    v8[6] = &CStr::s_rgwchEmptyStringBuffer;
    v8[2] = &ATL::CComContainedObject<CExtractIcon>::`vftable'{for `IExtractIconW'};
    v8[3] = &ATL::CComContainedObject<CExtractIcon>::`vftable'{for `IPersistFile'};
    v8[7] = 0;
    *((_DWORD *)v8 + 16) = 0;
    v8[4] = a1;
    _InterlockedIncrement(&dword_180012EE8);
    v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v8)(v8, a2, a3);
    if ( v7 )
    {
      *(_QWORD *)v9 = &ATL::CComAggObject<CExtractIcon>::`vftable';
      v9[2] = 1;
      _InterlockedDecrement(&dword_180012EE8);
      *((_QWORD *)v9 + 5) = &CStr::`vftable';
      CStr::Empty((CStr *)(v9 + 10));
      operator delete(v9);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180003b30  mov     [rsp+arg_0], rbx
0x180003b35  mov     [rsp+arg_8], rbp
0x180003b3a  push    rsi
0x180003b3b  push    rdi
0x180003b3c  push    r12
0x180003b3e  push    r13
0x180003b40  push    r14
0x180003b42  sub     rsp, 20h
0x180003b46  mov     rdi, r8
0x180003b49  mov     r14, rdx
0x180003b4c  mov     rbp, rcx
0x180003b4f  test    r8, r8
0x180003b52  jnz     short loc_180003B5E
0x180003b54  mov     eax, 80004003h
0x180003b59  jmp     loc_180003C23
0x180003b5e  mov     ecx, 48h ; 'H'; Size
0x180003b63  mov     qword ptr [r8], 0
0x180003b6a  mov     esi, 8007000Eh
0x180003b6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003b74  mov     [rsp+48h+arg_10], rax
0x180003b79  mov     rbx, rax
0x180003b7c  test    rax, rax
0x180003b7f  jz      loc_180003C21
0x180003b85  mov     dword ptr [rax+8], 0
0x180003b8c  lea     r12, ??_7?$CComAggObject@VCExtractIcon@@@ATL@@6B@; const ATL::CComAggObject<CExtractIcon>::`vftable'
0x180003b93  mov     [rax], r12
0x180003b96  lea     r13, ??_7CStr@@6B@; const CStr::`vftable'
0x180003b9d  mov     [rax+28h], r13
0x180003ba1  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180003ba8  mov     [rbx+30h], rax
0x180003bac  lea     rax, ??_7?$CComContainedObject@VCExtractIcon@@@ATL@@6BIExtractIconW@@@; const ATL::CComContainedObject<CExtractIcon>::`vftable'{for `IExtractIconW'}
0x180003bb3  mov     [rbx+10h], rax
0x180003bb7  lea     rax, ??_7?$CComContainedObject@VCExtractIcon@@@ATL@@6BIPersistFile@@@; const ATL::CComContainedObject<CExtractIcon>::`vftable'{for `IPersistFile'}
0x180003bbe  mov     [rbx+18h], rax
0x180003bc2  mov     qword ptr [rbx+38h], 0
0x180003bca  mov     dword ptr [rbx+40h], 0
0x180003bd1  mov     [rbx+20h], rbp
0x180003bd5  lock inc cs:dword_180012EE8
0x180003bdc  test    rbx, rbx
0x180003bdf  jz      short loc_180003C21
0x180003be1  mov     rax, [rbx]
0x180003be4  mov     r8, rdi
0x180003be7  mov     rdx, r14
0x180003bea  mov     rcx, rbx
0x180003bed  mov     rax, [rax]
0x180003bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bf5  mov     esi, eax
0x180003bf7  test    eax, eax
0x180003bf9  jz      short loc_180003C21
0x180003bfb  mov     [rbx], r12
0x180003bfe  lea     rcx, [rbx+28h]; this
0x180003c02  mov     dword ptr [rbx+8], 1
0x180003c09  lock dec cs:dword_180012EE8
0x180003c10  mov     [rcx], r13
0x180003c13  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180003c18  mov     rcx, rbx
0x180003c1b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003c21  mov     eax, esi
0x180003c23  mov     rbx, [rsp+48h+arg_0]
0x180003c28  mov     rbp, [rsp+48h+arg_8]
0x180003c2d  add     rsp, 20h
0x180003c31  pop     r14
0x180003c33  pop     r13
0x180003c35  pop     r12
0x180003c37  pop     rdi
0x180003c38  pop     rsi
0x180003c39  retn
```
