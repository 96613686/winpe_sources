# ATL::CComObject<CWrapMgr<DocTraitsAnchor>>::Release(void)

- ea: `0x18000a640`
- end: `0x18000a6ad`
- name: `?Release@?$CComObject@V?$CWrapMgr@VDocTraitsAnchor@@@@@ATL@@UEAAKXZ`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005944`
- `0x18000a640`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a693`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a693`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWrapMgr<DocTraitsAnchor>>::Release(_DWORD *a1)
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
        *(_QWORD *)a1 = &ATL::CComObject<CWrapMgr<DocTraitsAnchor>>::`vftable';
        _InterlockedDecrement(&dword_180024B28);
        CWrapMgr<DocTraitsAnchor>::~CWrapMgr<DocTraitsAnchor>();
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
0x18000a640  mov     [rsp+arg_0], rbx
0x18000a645  push    rdi
0x18000a646  sub     rsp, 20h
0x18000a64a  mov     edi, [rcx+8]
0x18000a64d  mov     rbx, rcx
0x18000a650  cmp     edi, 7FFFFFFFh
0x18000a656  jnz     short loc_18000A65F
0x18000a658  mov     edi, 7FFFFFFEh
0x18000a65d  jmp     short loc_18000A6A0
0x18000a65f  sub     edi, 1
0x18000a662  mov     [rcx+8], edi
0x18000a665  jnz     short loc_18000A6A0
0x18000a667  lock inc cs:dword_180024B28
0x18000a66e  test    rbx, rbx
0x18000a671  jz      short loc_18000A699
0x18000a673  lea     rax, ??_7?$CComObject@V?$CWrapMgr@VDocTraitsAnchor@@@@@ATL@@6B@; const ATL::CComObject<CWrapMgr<DocTraitsAnchor>>::`vftable'
0x18000a67a  mov     dword ptr [rcx+8], 1
0x18000a681  mov     [rcx], rax
0x18000a684  lock dec cs:dword_180024B28
0x18000a68b  call    ??1?$CWrapMgr@VDocTraitsAnchor@@@@QEAA@XZ; CWrapMgr<DocTraitsAnchor>::~CWrapMgr<DocTraitsAnchor>(void)
0x18000a690  mov     rcx, rbx
0x18000a693  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a699  lock dec cs:dword_180024B28
0x18000a6a0  mov     rbx, [rsp+28h+arg_0]
0x18000a6a5  mov     eax, edi
0x18000a6a7  add     rsp, 20h
0x18000a6ab  pop     rdi
0x18000a6ac  retn
```
