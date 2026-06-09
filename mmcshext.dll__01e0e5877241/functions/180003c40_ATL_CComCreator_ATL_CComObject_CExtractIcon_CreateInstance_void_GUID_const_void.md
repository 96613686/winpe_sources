# ATL::CComCreator<ATL::CComObject<CExtractIcon>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003c40`
- end: `0x180003d58`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCExtractIcon@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003a20`

## callees

- `0x180001140`
- `0x180003c40`
- `0x18000931c`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003d39`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003d39`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CExtractIcon>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v6; // esi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  int v9; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x38u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 4) = 0;
    v7[3] = &CStr::`vftable';
    v7[5] = 0;
    v7[4] = &CStr::s_rgwchEmptyStringBuffer;
    *((_DWORD *)v7 + 12) = 0;
    *v7 = &ATL::CComObject<CExtractIcon>::`vftable'{for `IExtractIconW'};
    v7[1] = &ATL::CComObject<CExtractIcon>::`vftable'{for `IPersistFile'};
    _InterlockedIncrement(&dword_180012EE8);
    v9 = *((_DWORD *)v7 + 4);
    if ( v9 != 0x7FFFFFFF )
    {
      *((_DWORD *)v7 + 4) = v9 + 1;
      if ( v9 != 2147483646 )
        *((_DWORD *)v7 + 4) = v9;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v7)(v7, a2, a3);
    if ( v6 )
    {
      *v8 = &ATL::CComObject<CExtractIcon>::`vftable'{for `IExtractIconW'};
      v8[1] = &ATL::CComObject<CExtractIcon>::`vftable'{for `IPersistFile'};
      *((_DWORD *)v8 + 4) = 1;
      _InterlockedDecrement(&dword_180012EE8);
      v8[3] = &CStr::`vftable';
      CStr::Empty((CStr *)(v8 + 3));
      operator delete(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180003c40  mov     [rsp+arg_8], rbx
0x180003c45  mov     [rsp+arg_10], rbp
0x180003c4a  push    rsi
0x180003c4b  push    rdi
0x180003c4c  push    r12
0x180003c4e  push    r13
0x180003c50  push    r15
0x180003c52  sub     rsp, 20h
0x180003c56  mov     rdi, r8
0x180003c59  mov     rbp, rdx
0x180003c5c  test    r8, r8
0x180003c5f  jnz     short loc_180003C6B
0x180003c61  mov     eax, 80004003h
0x180003c66  jmp     loc_180003D41
0x180003c6b  mov     ecx, 38h ; '8'; Size
0x180003c70  mov     qword ptr [r8], 0
0x180003c77  mov     esi, 8007000Eh
0x180003c7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c81  mov     [rsp+48h+arg_0], rax
0x180003c86  mov     rbx, rax
0x180003c89  test    rax, rax
0x180003c8c  jz      loc_180003D3F
0x180003c92  mov     dword ptr [rax+10h], 0
0x180003c99  lea     r13, ??_7CStr@@6B@; const CStr::`vftable'
0x180003ca0  mov     [rax+18h], r13
0x180003ca4  lea     r15, ??_7?$CComObject@VCExtractIcon@@@ATL@@6BIExtractIconW@@@; const ATL::CComObject<CExtractIcon>::`vftable'{for `IExtractIconW'}
0x180003cab  mov     qword ptr [rbx+28h], 0
0x180003cb3  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180003cba  mov     [rbx+20h], rax
0x180003cbe  lea     r12, ??_7?$CComObject@VCExtractIcon@@@ATL@@6BIPersistFile@@@; const ATL::CComObject<CExtractIcon>::`vftable'{for `IPersistFile'}
0x180003cc5  mov     dword ptr [rbx+30h], 0
0x180003ccc  mov     [rbx], r15
0x180003ccf  mov     [rbx+8], r12
0x180003cd3  lock inc cs:dword_180012EE8
0x180003cda  test    rbx, rbx
0x180003cdd  jz      short loc_180003D3F
0x180003cdf  mov     ecx, [rbx+10h]
0x180003ce2  cmp     ecx, 7FFFFFFFh
0x180003ce8  jz      short loc_180003CFB
0x180003cea  lea     eax, [rcx+1]
0x180003ced  mov     [rbx+10h], eax
0x180003cf0  cmp     ecx, 7FFFFFFEh
0x180003cf6  jz      short loc_180003CFB
0x180003cf8  mov     [rbx+10h], ecx
0x180003cfb  mov     rax, [rbx]
0x180003cfe  mov     r8, rdi
0x180003d01  mov     rdx, rbp
0x180003d04  mov     rcx, rbx
0x180003d07  mov     rax, [rax]
0x180003d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d0f  mov     esi, eax
0x180003d11  test    eax, eax
0x180003d13  jz      short loc_180003D3F
0x180003d15  mov     [rbx], r15
0x180003d18  lea     rcx, [rbx+18h]; this
0x180003d1c  mov     [rbx+8], r12
0x180003d20  mov     dword ptr [rbx+10h], 1
0x180003d27  lock dec cs:dword_180012EE8
0x180003d2e  mov     [rcx], r13
0x180003d31  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180003d36  mov     rcx, rbx
0x180003d39  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003d3f  mov     eax, esi
0x180003d41  mov     rbx, [rsp+48h+arg_8]
0x180003d46  mov     rbp, [rsp+48h+arg_10]
0x180003d4b  add     rsp, 20h
0x180003d4f  pop     r15
0x180003d51  pop     r13
0x180003d53  pop     r12
0x180003d55  pop     rdi
0x180003d56  pop     rsi
0x180003d57  retn
```
