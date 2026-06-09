# ATL::CHeapPtrBase<_IASATTRIBUTE *,ATL::CComAllocator>::AllocateBytes(unsigned __int64)

- ea: `0x180012a04`
- end: `0x180012a31`
- name: `?AllocateBytes@?$CHeapPtrBase@PEAU_IASATTRIBUTE@@VCComAllocator@ATL@@@ATL@@QEAA_N_K@Z`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800133bc`

## callees

- `0x180012a04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012a1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012a1c`

## pseudocode

```c
bool __fastcall ATL::CHeapPtrBase<_IASATTRIBUTE *,ATL::CComAllocator>::AllocateBytes(_QWORD *a1, unsigned __int64 a2)
{
  LPVOID v3; // rax

  if ( a2 <= 0x7FFFFFFF )
    v3 = CoTaskMemAlloc((unsigned int)a2);
  else
    v3 = 0;
  *a1 = v3;
  return v3 != 0;
}

```

## disassembly

```asm
0x180012a04  push    rbx
0x180012a06  sub     rsp, 20h
0x180012a0a  mov     rbx, rcx
0x180012a0d  cmp     rdx, 7FFFFFFFh
0x180012a14  jbe     short loc_180012A1A
0x180012a16  xor     eax, eax
0x180012a18  jmp     short loc_180012A22
0x180012a1a  mov     ecx, edx; cb
0x180012a1c  call    cs:__imp_CoTaskMemAlloc
0x180012a22  test    rax, rax
0x180012a25  mov     [rbx], rax
0x180012a28  setnz   al
0x180012a2b  add     rsp, 20h
0x180012a2f  pop     rbx
0x180012a30  retn
```
