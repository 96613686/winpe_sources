# ATL::CComObject<CDict>::Release(void)

- ea: `0x180011df0`
- end: `0x180011e5d`
- name: `?Release@?$CComObject@VCDict@@@ATL@@UEAAKXZ`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800047ec`
- `0x180011df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011e43`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011e43`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDict>::Release(CDict *a1)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = *((_DWORD *)a1 + 2);
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    *((_DWORD *)a1 + 2) = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_180024B28);
      if ( a1 )
      {
        *((_DWORD *)a1 + 2) = 1;
        *(_QWORD *)a1 = &ATL::CComObject<CDict>::`vftable';
        _InterlockedDecrement(&dword_180024B28);
        CDict::~CDict(a1);
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
0x180011df0  mov     [rsp+arg_0], rbx
0x180011df5  push    rdi
0x180011df6  sub     rsp, 20h
0x180011dfa  mov     edi, [rcx+8]
0x180011dfd  mov     rbx, rcx
0x180011e00  cmp     edi, 7FFFFFFFh
0x180011e06  jnz     short loc_180011E0F
0x180011e08  mov     edi, 7FFFFFFEh
0x180011e0d  jmp     short loc_180011E50
0x180011e0f  sub     edi, 1
0x180011e12  mov     [rcx+8], edi
0x180011e15  jnz     short loc_180011E50
0x180011e17  lock inc cs:dword_180024B28
0x180011e1e  test    rbx, rbx
0x180011e21  jz      short loc_180011E49
0x180011e23  lea     rax, ??_7?$CComObject@VCDict@@@ATL@@6B@; const ATL::CComObject<CDict>::`vftable'
0x180011e2a  mov     dword ptr [rcx+8], 1
0x180011e31  mov     [rcx], rax
0x180011e34  lock dec cs:dword_180024B28
0x180011e3b  call    ??1CDict@@QEAA@XZ; CDict::~CDict(void)
0x180011e40  mov     rcx, rbx
0x180011e43  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011e49  lock dec cs:dword_180024B28
0x180011e50  mov     rbx, [rsp+28h+arg_0]
0x180011e55  mov     eax, edi
0x180011e57  add     rsp, 20h
0x180011e5b  pop     rdi
0x180011e5c  retn
```
