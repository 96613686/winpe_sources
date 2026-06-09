# CertEnrollHttp::CopyResponse(uchar *,ulong,_CERTTRANSBLOB *)

- ea: `0x180014994`
- end: `0x1800149f2`
- name: `?CopyResponse@CertEnrollHttp@@YAJPEAEKPEAU_CERTTRANSBLOB@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(CertEnrollHttp *this, size_t Size, __int64, struct _CERTTRANSBLOB *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800149f8`

## callees

- `0x180002306`
- `0x180014994`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800149b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800149b2`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800149cd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800149cd`

## pseudocode

```c
__int64 __fastcall CertEnrollHttp::CopyResponse(
        CertEnrollHttp *this,
        size_t Size,
        __int64 a3,
        struct _CERTTRANSBLOB *a4)
{
  size_t v5; // rsi
  unsigned int v6; // ebx
  void *v8; // rax

  v5 = (unsigned int)Size;
  v6 = 0;
  *(_DWORD *)a3 = 0;
  *(_QWORD *)(a3 + 8) = 0;
  v8 = CoTaskMemAlloc((unsigned int)Size);
  *(_QWORD *)(a3 + 8) = v8;
  if ( v8 )
  {
    *(_DWORD *)a3 = v5;
    memcpy_0(v8, this, v5);
  }
  else
  {
    v6 = -2147024882;
    CSPrintErrorLineFile(0x1D0BB9u, -2147024882);
  }
  return v6;
}

```

## disassembly

```asm
0x180014994  push    rbx
0x180014996  push    rbp
0x180014997  push    rsi
0x180014998  push    rdi
0x180014999  push    r14
0x18001499b  sub     rsp, 20h
0x18001499f  mov     r14, rcx
0x1800149a2  mov     esi, edx
0x1800149a4  xor     ebx, ebx
0x1800149a6  mov     ecx, edx; cb
0x1800149a8  mov     [r8], ebx
0x1800149ab  mov     rdi, r8
0x1800149ae  mov     [r8+8], rbx
0x1800149b2  call    cs:__imp_CoTaskMemAlloc
0x1800149b8  mov     [rdi+8], rax
0x1800149bc  test    rax, rax
0x1800149bf  jnz     short loc_1800149D5
0x1800149c1  mov     ebx, 8007000Eh
0x1800149c6  mov     ecx, 1D0BB9h
0x1800149cb  mov     edx, ebx
0x1800149cd  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800149d3  jmp     short loc_1800149E5
0x1800149d5  mov     r8, rsi; Size
0x1800149d8  mov     [rdi], esi
0x1800149da  mov     rdx, r14; Src
0x1800149dd  mov     rcx, rax; void *
0x1800149e0  call    memcpy_0
0x1800149e5  mov     eax, ebx
0x1800149e7  add     rsp, 20h
0x1800149eb  pop     r14
0x1800149ed  pop     rdi
0x1800149ee  pop     rsi
0x1800149ef  pop     rbp
0x1800149f0  pop     rbx
0x1800149f1  retn
```
