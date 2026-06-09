# ATL::CComObject<CDocWrap>::Release(void)

- ea: `0x180011e70`
- end: `0x180011ede`
- name: `?Release@?$CComObject@VCDocWrap@@@ATL@@UEAAKXZ`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c200`
- `0x180011e70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011ec4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011ec4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CDocWrap>::Release(CDocWrap *a1)
{
  int v2; // edi
  unsigned int v3; // edi

  v2 = *((_DWORD *)a1 + 2);
  if ( v2 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v2 - 1;
    *((_DWORD *)a1 + 2) = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_180024B28);
      if ( a1 )
      {
        *(_QWORD *)a1 = &ATL::CComObject<CDocWrap>::`vftable';
        *((_DWORD *)a1 + 2) = 1;
        _InterlockedDecrement(&dword_180024B28);
        CDocWrap::_Clear(a1);
        operator delete(a1);
      }
      _InterlockedDecrement(&dword_180024B28);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180011e70  mov     [rsp+arg_0], rbx
0x180011e75  push    rdi
0x180011e76  sub     rsp, 20h
0x180011e7a  mov     rbx, rcx
0x180011e7d  mov     edi, [rcx+8]
0x180011e80  cmp     edi, 7FFFFFFFh
0x180011e86  jnz     short loc_180011E8F
0x180011e88  mov     edi, 7FFFFFFEh
0x180011e8d  jmp     short loc_180011ED1
0x180011e8f  sub     edi, 1
0x180011e92  mov     [rcx+8], edi
0x180011e95  jnz     short loc_180011ED1
0x180011e97  lock inc cs:dword_180024B28
0x180011e9e  test    rbx, rbx
0x180011ea1  jz      short loc_180011ECA
0x180011ea3  lea     rax, ??_7?$CComObject@VCDocWrap@@@ATL@@6B@; const ATL::CComObject<CDocWrap>::`vftable'
0x180011eaa  mov     [rcx], rax
0x180011ead  mov     dword ptr [rcx+8], 1
0x180011eb4  lock dec cs:dword_180024B28
0x180011ebb  call    ?_Clear@CDocWrap@@AEAAXXZ; CDocWrap::_Clear(void)
0x180011ec0  nop
0x180011ec1  mov     rcx, rbx
0x180011ec4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011eca  lock dec cs:dword_180024B28
0x180011ed1  mov     eax, edi
0x180011ed3  mov     rbx, [rsp+28h+arg_0]
0x180011ed8  add     rsp, 20h
0x180011edc  pop     rdi
0x180011edd  retn
```
