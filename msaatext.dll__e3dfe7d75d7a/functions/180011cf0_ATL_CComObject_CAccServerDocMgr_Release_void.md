# ATL::CComObject<CAccServerDocMgr>::Release(void)

- ea: `0x180011cf0`
- end: `0x180011d5d`
- name: `?Release@?$CComObject@VCAccServerDocMgr@@@ATL@@UEAAKXZ`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000cac8`
- `0x180011cf0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011d43`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011d43`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAccServerDocMgr>::Release(CAccServerDocMgr *a1)
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
        *(_QWORD *)a1 = &ATL::CComObject<CAccServerDocMgr>::`vftable';
        _InterlockedDecrement(&dword_180024B28);
        CAccServerDocMgr::~CAccServerDocMgr(a1);
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
0x180011cf0  mov     [rsp+arg_0], rbx
0x180011cf5  push    rdi
0x180011cf6  sub     rsp, 20h
0x180011cfa  mov     edi, [rcx+8]
0x180011cfd  mov     rbx, rcx
0x180011d00  cmp     edi, 7FFFFFFFh
0x180011d06  jnz     short loc_180011D0F
0x180011d08  mov     edi, 7FFFFFFEh
0x180011d0d  jmp     short loc_180011D50
0x180011d0f  sub     edi, 1
0x180011d12  mov     [rcx+8], edi
0x180011d15  jnz     short loc_180011D50
0x180011d17  lock inc cs:dword_180024B28
0x180011d1e  test    rbx, rbx
0x180011d21  jz      short loc_180011D49
0x180011d23  lea     rax, ??_7?$CComObject@VCAccServerDocMgr@@@ATL@@6B@; const ATL::CComObject<CAccServerDocMgr>::`vftable'
0x180011d2a  mov     dword ptr [rcx+8], 1
0x180011d31  mov     [rcx], rax
0x180011d34  lock dec cs:dword_180024B28
0x180011d3b  call    ??1CAccServerDocMgr@@QEAA@XZ; CAccServerDocMgr::~CAccServerDocMgr(void)
0x180011d40  mov     rcx, rbx
0x180011d43  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011d49  lock dec cs:dword_180024B28
0x180011d50  mov     rbx, [rsp+28h+arg_0]
0x180011d55  mov     eax, edi
0x180011d57  add     rsp, 20h
0x180011d5b  pop     rdi
0x180011d5c  retn
```
