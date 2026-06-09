# ATL::CComAggObject<CDict>::Release(void)

- ea: `0x180011b20`
- end: `0x180011b91`
- name: `?Release@?$CComAggObject@VCDict@@@ATL@@UEAAKXZ`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800047ec`
- `0x180011b20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011b77`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011b77`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDict>::Release(_DWORD *a1)
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
        *(_QWORD *)a1 = &ATL::CComAggObject<CDict>::`vftable';
        _InterlockedDecrement(&dword_180024B28);
        CDict::~CDict((CDict *)(a1 + 4));
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
0x180011b20  mov     [rsp+arg_0], rbx
0x180011b25  push    rdi
0x180011b26  sub     rsp, 20h
0x180011b2a  mov     edi, [rcx+8]
0x180011b2d  mov     rbx, rcx
0x180011b30  cmp     edi, 7FFFFFFFh
0x180011b36  jnz     short loc_180011B3F
0x180011b38  mov     edi, 7FFFFFFEh
0x180011b3d  jmp     short loc_180011B84
0x180011b3f  sub     edi, 1
0x180011b42  mov     [rcx+8], edi
0x180011b45  jnz     short loc_180011B84
0x180011b47  lock inc cs:dword_180024B28
0x180011b4e  test    rbx, rbx
0x180011b51  jz      short loc_180011B7D
0x180011b53  mov     dword ptr [rcx+8], 1
0x180011b5a  lea     rax, ??_7?$CComAggObject@VCDict@@@ATL@@6B@; const ATL::CComAggObject<CDict>::`vftable'
0x180011b61  mov     [rcx], rax
0x180011b64  add     rcx, 10h; this
0x180011b68  lock dec cs:dword_180024B28
0x180011b6f  call    ??1CDict@@QEAA@XZ; CDict::~CDict(void)
0x180011b74  mov     rcx, rbx
0x180011b77  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011b7d  lock dec cs:dword_180024B28
0x180011b84  mov     rbx, [rsp+28h+arg_0]
0x180011b89  mov     eax, edi
0x180011b8b  add     rsp, 20h
0x180011b8f  pop     rdi
0x180011b90  retn
```
