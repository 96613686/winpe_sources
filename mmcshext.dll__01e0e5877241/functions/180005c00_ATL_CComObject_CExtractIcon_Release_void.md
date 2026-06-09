# ATL::CComObject<CExtractIcon>::Release(void)

- ea: `0x180005c00`
- end: `0x180005c86`
- name: `?Release@?$CComObject@VCExtractIcon@@@ATL@@UEAAKXZ`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005c90`

## callees

- `0x180005c00`
- `0x18000931c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005c6c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005c6c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CExtractIcon>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi
  CStr *v4; // rcx

  v1 = a1[4];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[4] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_180012EE8);
      if ( a1 )
      {
        a1[4] = 1;
        *(_QWORD *)a1 = &ATL::CComObject<CExtractIcon>::`vftable'{for `IExtractIconW'};
        *((_QWORD *)a1 + 1) = &ATL::CComObject<CExtractIcon>::`vftable'{for `IPersistFile'};
        v4 = (CStr *)(a1 + 6);
        _InterlockedDecrement(&dword_180012EE8);
        *(_QWORD *)v4 = &CStr::`vftable';
        CStr::Empty(v4);
        operator delete(a1);
      }
      _InterlockedDecrement(&dword_180012EE8);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180005c00  mov     [rsp+arg_0], rbx
0x180005c05  push    rdi
0x180005c06  sub     rsp, 20h
0x180005c0a  mov     edi, [rcx+10h]
0x180005c0d  mov     rbx, rcx
0x180005c10  cmp     edi, 7FFFFFFFh
0x180005c16  jnz     short loc_180005C1F
0x180005c18  mov     edi, 7FFFFFFEh
0x180005c1d  jmp     short loc_180005C79
0x180005c1f  sub     edi, 1
0x180005c22  mov     [rcx+10h], edi
0x180005c25  jnz     short loc_180005C79
0x180005c27  lock inc cs:dword_180012EE8
0x180005c2e  test    rbx, rbx
0x180005c31  jz      short loc_180005C72
0x180005c33  mov     dword ptr [rcx+10h], 1
0x180005c3a  lea     rax, ??_7?$CComObject@VCExtractIcon@@@ATL@@6BIExtractIconW@@@; const ATL::CComObject<CExtractIcon>::`vftable'{for `IExtractIconW'}
0x180005c41  mov     [rcx], rax
0x180005c44  lea     rax, ??_7?$CComObject@VCExtractIcon@@@ATL@@6BIPersistFile@@@; const ATL::CComObject<CExtractIcon>::`vftable'{for `IPersistFile'}
0x180005c4b  mov     [rcx+8], rax
0x180005c4f  add     rcx, 18h; this
0x180005c53  lock dec cs:dword_180012EE8
0x180005c5a  lea     rax, ??_7CStr@@6B@; const CStr::`vftable'
0x180005c61  mov     [rcx], rax
0x180005c64  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180005c69  mov     rcx, rbx
0x180005c6c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005c72  lock dec cs:dword_180012EE8
0x180005c79  mov     rbx, [rsp+28h+arg_0]
0x180005c7e  mov     eax, edi
0x180005c80  add     rsp, 20h
0x180005c84  pop     rdi
0x180005c85  retn
```
