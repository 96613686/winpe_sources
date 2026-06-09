# ATL::CComAggObject<CAccClientDocMgr>::Release(void)

- ea: `0x1800119a0`
- end: `0x180011a19`
- name: `?Release@?$CComAggObject@VCAccClientDocMgr@@@ATL@@UEAAKXZ`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800119a0`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800119ff`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800119ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComAggObject<CAccClientDocMgr>::Release(_DWORD *a1)
{
  int v2; // edi
  unsigned int v3; // edi

  v2 = a1[2];
  if ( v2 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v2 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_180024B28);
      if ( a1 )
      {
        *(_QWORD *)a1 = &ATL::CComAggObject<CAccClientDocMgr>::`vftable';
        a1[2] = 1;
        _InterlockedDecrement(&dword_180024B28);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 4) + 16LL))(*((_QWORD *)a1 + 4));
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
0x1800119a0  mov     [rsp+arg_0], rbx
0x1800119a5  push    rdi
0x1800119a6  sub     rsp, 20h
0x1800119aa  mov     rbx, rcx
0x1800119ad  mov     edi, [rcx+8]
0x1800119b0  cmp     edi, 7FFFFFFFh
0x1800119b6  jnz     short loc_1800119BF
0x1800119b8  mov     edi, 7FFFFFFEh
0x1800119bd  jmp     short loc_180011A0C
0x1800119bf  sub     edi, 1
0x1800119c2  mov     [rcx+8], edi
0x1800119c5  jnz     short loc_180011A0C
0x1800119c7  lock inc cs:dword_180024B28
0x1800119ce  test    rbx, rbx
0x1800119d1  jz      short loc_180011A05
0x1800119d3  lea     rax, ??_7?$CComAggObject@VCAccClientDocMgr@@@ATL@@6B@; const ATL::CComAggObject<CAccClientDocMgr>::`vftable'
0x1800119da  mov     [rcx], rax
0x1800119dd  mov     dword ptr [rcx+8], 1
0x1800119e4  lock dec cs:dword_180024B28
0x1800119eb  mov     rcx, [rcx+20h]
0x1800119ef  mov     rdx, [rcx]
0x1800119f2  mov     rax, [rdx+10h]
0x1800119f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119fb  nop
0x1800119fc  mov     rcx, rbx
0x1800119ff  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011a05  lock dec cs:dword_180024B28
0x180011a0c  mov     eax, edi
0x180011a0e  mov     rbx, [rsp+28h+arg_0]
0x180011a13  add     rsp, 20h
0x180011a17  pop     rdi
0x180011a18  retn
```
