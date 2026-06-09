# ATL::CComAggObject<CDocWrap>::Release(void)

- ea: `0x180011ba0`
- end: `0x180011c12`
- name: `?Release@?$CComAggObject@VCDocWrap@@@ATL@@UEAAKXZ`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c200`
- `0x180011ba0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011bf8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011bf8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComAggObject<CDocWrap>::Release(_DWORD *a1)
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
        *(_QWORD *)a1 = &ATL::CComAggObject<CDocWrap>::`vftable';
        a1[2] = 1;
        _InterlockedDecrement(&dword_180024B28);
        CDocWrap::_Clear((CDocWrap *)(a1 + 4));
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
0x180011ba0  mov     [rsp+arg_0], rbx
0x180011ba5  push    rdi
0x180011ba6  sub     rsp, 20h
0x180011baa  mov     rbx, rcx
0x180011bad  mov     edi, [rcx+8]
0x180011bb0  cmp     edi, 7FFFFFFFh
0x180011bb6  jnz     short loc_180011BBF
0x180011bb8  mov     edi, 7FFFFFFEh
0x180011bbd  jmp     short loc_180011C05
0x180011bbf  sub     edi, 1
0x180011bc2  mov     [rcx+8], edi
0x180011bc5  jnz     short loc_180011C05
0x180011bc7  lock inc cs:dword_180024B28
0x180011bce  test    rbx, rbx
0x180011bd1  jz      short loc_180011BFE
0x180011bd3  lea     rax, ??_7?$CComAggObject@VCDocWrap@@@ATL@@6B@; const ATL::CComAggObject<CDocWrap>::`vftable'
0x180011bda  mov     [rcx], rax
0x180011bdd  mov     dword ptr [rcx+8], 1
0x180011be4  lock dec cs:dword_180024B28
0x180011beb  add     rcx, 10h; this
0x180011bef  call    ?_Clear@CDocWrap@@AEAAXXZ; CDocWrap::_Clear(void)
0x180011bf4  nop
0x180011bf5  mov     rcx, rbx
0x180011bf8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011bfe  lock dec cs:dword_180024B28
0x180011c05  mov     eax, edi
0x180011c07  mov     rbx, [rsp+28h+arg_0]
0x180011c0c  add     rsp, 20h
0x180011c10  pop     rdi
0x180011c11  retn
```
