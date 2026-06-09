# ATL::CComAggObject<CAccServerDocMgr>::Release(void)

- ea: `0x180011a20`
- end: `0x180011a91`
- name: `?Release@?$CComAggObject@VCAccServerDocMgr@@@ATL@@UEAAKXZ`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000cac8`
- `0x180011a20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011a77`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011a77`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CAccServerDocMgr>::Release(_DWORD *a1)
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
        *(_QWORD *)a1 = &ATL::CComAggObject<CAccServerDocMgr>::`vftable';
        _InterlockedDecrement(&dword_180024B28);
        CAccServerDocMgr::~CAccServerDocMgr((CAccServerDocMgr *)(a1 + 4));
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
0x180011a20  mov     [rsp+arg_0], rbx
0x180011a25  push    rdi
0x180011a26  sub     rsp, 20h
0x180011a2a  mov     edi, [rcx+8]
0x180011a2d  mov     rbx, rcx
0x180011a30  cmp     edi, 7FFFFFFFh
0x180011a36  jnz     short loc_180011A3F
0x180011a38  mov     edi, 7FFFFFFEh
0x180011a3d  jmp     short loc_180011A84
0x180011a3f  sub     edi, 1
0x180011a42  mov     [rcx+8], edi
0x180011a45  jnz     short loc_180011A84
0x180011a47  lock inc cs:dword_180024B28
0x180011a4e  test    rbx, rbx
0x180011a51  jz      short loc_180011A7D
0x180011a53  mov     dword ptr [rcx+8], 1
0x180011a5a  lea     rax, ??_7?$CComAggObject@VCAccServerDocMgr@@@ATL@@6B@; const ATL::CComAggObject<CAccServerDocMgr>::`vftable'
0x180011a61  mov     [rcx], rax
0x180011a64  add     rcx, 10h; this
0x180011a68  lock dec cs:dword_180024B28
0x180011a6f  call    ??1CAccServerDocMgr@@QEAA@XZ; CAccServerDocMgr::~CAccServerDocMgr(void)
0x180011a74  mov     rcx, rbx
0x180011a77  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011a7d  lock dec cs:dword_180024B28
0x180011a84  mov     rbx, [rsp+28h+arg_0]
0x180011a89  mov     eax, edi
0x180011a8b  add     rsp, 20h
0x180011a8f  pop     rdi
0x180011a90  retn
```
