# ATL::CComAggObject<CAccStore>::Release(void)

- ea: `0x180011aa0`
- end: `0x180011b11`
- name: `?Release@?$CComAggObject@VCAccStore@@@ATL@@UEAAKXZ`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000d5a4`
- `0x180011aa0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011af7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011af7`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CAccStore>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_180024B28);
      if ( a1 )
      {
        a1[2] = 1;
        *(_QWORD *)a1 = &ATL::CComAggObject<CAccStore>::`vftable';
        _InterlockedDecrement(&dword_180024B28);
        CAccStore::~CAccStore((CAccStore *)(a1 + 4));
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
0x180011aa0  mov     [rsp+arg_0], rbx
0x180011aa5  push    rdi
0x180011aa6  sub     rsp, 20h
0x180011aaa  mov     edi, [rcx+8]
0x180011aad  mov     rbx, rcx
0x180011ab0  cmp     edi, 7FFFFFFFh
0x180011ab6  jnz     short loc_180011ABF
0x180011ab8  mov     edi, 7FFFFFFEh
0x180011abd  jmp     short loc_180011B04
0x180011abf  sub     edi, 1
0x180011ac2  mov     [rcx+8], edi
0x180011ac5  jnz     short loc_180011B04
0x180011ac7  lock inc cs:dword_180024B28
0x180011ace  test    rbx, rbx
0x180011ad1  jz      short loc_180011AFD
0x180011ad3  mov     dword ptr [rcx+8], 1
0x180011ada  lea     rax, ??_7?$CComAggObject@VCAccStore@@@ATL@@6B@; const ATL::CComAggObject<CAccStore>::`vftable'
0x180011ae1  mov     [rcx], rax
0x180011ae4  add     rcx, 10h; this
0x180011ae8  lock dec cs:dword_180024B28
0x180011aef  call    ??1CAccStore@@QEAA@XZ; CAccStore::~CAccStore(void)
0x180011af4  mov     rcx, rbx
0x180011af7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011afd  lock dec cs:dword_180024B28
0x180011b04  mov     rbx, [rsp+28h+arg_0]
0x180011b09  mov     eax, edi
0x180011b0b  add     rsp, 20h
0x180011b0f  pop     rdi
0x180011b10  retn
```
