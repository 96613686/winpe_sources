# ATL::CComObject<CWrapMgr<DocTraitsACP>>::Release(void)

- ea: `0x18000a5c0`
- end: `0x18000a62d`
- name: `?Release@?$CComObject@V?$CWrapMgr@VDocTraitsACP@@@@@ATL@@UEAAKXZ`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005944`
- `0x18000a5c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a613`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a613`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWrapMgr<DocTraitsACP>>::Release(_DWORD *a1)
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
        *(_QWORD *)a1 = &ATL::CComObject<CWrapMgr<DocTraitsACP>>::`vftable';
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
0x18000a5c0  mov     [rsp+arg_0], rbx
0x18000a5c5  push    rdi
0x18000a5c6  sub     rsp, 20h
0x18000a5ca  mov     edi, [rcx+8]
0x18000a5cd  mov     rbx, rcx
0x18000a5d0  cmp     edi, 7FFFFFFFh
0x18000a5d6  jnz     short loc_18000A5DF
0x18000a5d8  mov     edi, 7FFFFFFEh
0x18000a5dd  jmp     short loc_18000A620
0x18000a5df  sub     edi, 1
0x18000a5e2  mov     [rcx+8], edi
0x18000a5e5  jnz     short loc_18000A620
0x18000a5e7  lock inc cs:dword_180024B28
0x18000a5ee  test    rbx, rbx
0x18000a5f1  jz      short loc_18000A619
0x18000a5f3  lea     rax, ??_7?$CComObject@V?$CWrapMgr@VDocTraitsACP@@@@@ATL@@6B@; const ATL::CComObject<CWrapMgr<DocTraitsACP>>::`vftable'
0x18000a5fa  mov     dword ptr [rcx+8], 1
0x18000a601  mov     [rcx], rax
0x18000a604  lock dec cs:dword_180024B28
0x18000a60b  call    ??1?$CWrapMgr@VDocTraitsAnchor@@@@QEAA@XZ; CWrapMgr<DocTraitsAnchor>::~CWrapMgr<DocTraitsAnchor>(void)
0x18000a610  mov     rcx, rbx
0x18000a613  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a619  lock dec cs:dword_180024B28
0x18000a620  mov     rbx, [rsp+28h+arg_0]
0x18000a625  mov     eax, edi
0x18000a627  add     rsp, 20h
0x18000a62b  pop     rdi
0x18000a62c  retn
```
