# ATL::CComObject<CAccClientDocMgr>::Release(void)

- ea: `0x180011c70`
- end: `0x180011ce9`
- name: `?Release@?$CComObject@VCAccClientDocMgr@@@ATL@@UEAAKXZ`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180011c70`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011ccf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011ccf`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAccClientDocMgr>::Release(_DWORD *a1)
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
        *(_QWORD *)a1 = &ATL::CComObject<CAccClientDocMgr>::`vftable';
        a1[2] = 1;
        _InterlockedDecrement(&dword_180024B28);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 2) + 16LL))(*((_QWORD *)a1 + 2));
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
0x180011c70  mov     [rsp+arg_0], rbx
0x180011c75  push    rdi
0x180011c76  sub     rsp, 20h
0x180011c7a  mov     rbx, rcx
0x180011c7d  mov     edi, [rcx+8]
0x180011c80  cmp     edi, 7FFFFFFFh
0x180011c86  jnz     short loc_180011C8F
0x180011c88  mov     edi, 7FFFFFFEh
0x180011c8d  jmp     short loc_180011CDC
0x180011c8f  sub     edi, 1
0x180011c92  mov     [rcx+8], edi
0x180011c95  jnz     short loc_180011CDC
0x180011c97  lock inc cs:dword_180024B28
0x180011c9e  test    rbx, rbx
0x180011ca1  jz      short loc_180011CD5
0x180011ca3  lea     rax, ??_7?$CComObject@VCAccClientDocMgr@@@ATL@@6B@; const ATL::CComObject<CAccClientDocMgr>::`vftable'
0x180011caa  mov     [rcx], rax
0x180011cad  mov     dword ptr [rcx+8], 1
0x180011cb4  lock dec cs:dword_180024B28
0x180011cbb  mov     rcx, [rcx+10h]
0x180011cbf  mov     rdx, [rcx]
0x180011cc2  mov     rax, [rdx+10h]
0x180011cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ccb  nop
0x180011ccc  mov     rcx, rbx
0x180011ccf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011cd5  lock dec cs:dword_180024B28
0x180011cdc  mov     eax, edi
0x180011cde  mov     rbx, [rsp+28h+arg_0]
0x180011ce3  add     rsp, 20h
0x180011ce7  pop     rdi
0x180011ce8  retn
```
