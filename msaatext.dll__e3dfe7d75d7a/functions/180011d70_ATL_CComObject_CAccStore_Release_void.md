# ATL::CComObject<CAccStore>::Release(void)

- ea: `0x180011d70`
- end: `0x180011ddd`
- name: `?Release@?$CComObject@VCAccStore@@@ATL@@UEAAKXZ`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000d5a4`
- `0x180011d70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011dc3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011dc3`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAccStore>::Release(CAccStore *a1)
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
        *(_QWORD *)a1 = &ATL::CComObject<CAccStore>::`vftable';
        _InterlockedDecrement(&dword_180024B28);
        CAccStore::~CAccStore(a1);
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
0x180011d70  mov     [rsp+arg_0], rbx
0x180011d75  push    rdi
0x180011d76  sub     rsp, 20h
0x180011d7a  mov     edi, [rcx+8]
0x180011d7d  mov     rbx, rcx
0x180011d80  cmp     edi, 7FFFFFFFh
0x180011d86  jnz     short loc_180011D8F
0x180011d88  mov     edi, 7FFFFFFEh
0x180011d8d  jmp     short loc_180011DD0
0x180011d8f  sub     edi, 1
0x180011d92  mov     [rcx+8], edi
0x180011d95  jnz     short loc_180011DD0
0x180011d97  lock inc cs:dword_180024B28
0x180011d9e  test    rbx, rbx
0x180011da1  jz      short loc_180011DC9
0x180011da3  lea     rax, ??_7?$CComObject@VCAccStore@@@ATL@@6B@; const ATL::CComObject<CAccStore>::`vftable'
0x180011daa  mov     dword ptr [rcx+8], 1
0x180011db1  mov     [rcx], rax
0x180011db4  lock dec cs:dword_180024B28
0x180011dbb  call    ??1CAccStore@@QEAA@XZ; CAccStore::~CAccStore(void)
0x180011dc0  mov     rcx, rbx
0x180011dc3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011dc9  lock dec cs:dword_180024B28
0x180011dd0  mov     rbx, [rsp+28h+arg_0]
0x180011dd5  mov     eax, edi
0x180011dd7  add     rsp, 20h
0x180011ddb  pop     rdi
0x180011ddc  retn
```
