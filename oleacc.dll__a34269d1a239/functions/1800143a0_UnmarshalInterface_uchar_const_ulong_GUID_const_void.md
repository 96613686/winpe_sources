# UnmarshalInterface(uchar const *,ulong,_GUID const &,void * *)

- ea: `0x1800143a0`
- end: `0x180014470`
- name: `?UnmarshalInterface@@YAJPEBEKAEBU_GUID@@PEAPEAX@Z`
- size: `208`
- prototype: `__int64 __fastcall(const unsigned __int8 *Src, size_t Size, IID *riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d708`

## callees

- `0x1800143a0`
- `0x180047ff8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800143bd`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800143bd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180014456`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180014466`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180014456`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180014466`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800143ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800143ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800143ce`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800143ce`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18001441d`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18001441d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180014406`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180014406`

## pseudocode

```c
__int64 __fastcall UnmarshalInterface(const unsigned __int8 *Src, size_t Size, IID *riid, LPVOID *ppv)
{
  unsigned int v5; // edi
  HGLOBAL v8; // rax
  void *v9; // rbx
  void *v10; // rax
  HRESULT v11; // edi
  unsigned int v12; // ebx
  LPSTREAM ppstm; // [rsp+20h] [rbp-38h] BYREF

  v5 = Size;
  v8 = GlobalAlloc(2u, (unsigned int)Size);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v10 = GlobalLock(v8);
  if ( v10 )
  {
    memcpy_0(v10, Src, v5);
    GlobalUnlock(v9);
    ppstm = 0;
    v11 = CreateStreamOnHGlobal(v9, 1, &ppstm);
    if ( v11 < 0 )
    {
      GlobalFree(v9);
      return (unsigned int)v11;
    }
    else
    {
      v12 = CoUnmarshalInterface(ppstm, riid, ppv);
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      return v12;
    }
  }
  else
  {
    GlobalFree(v9);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x1800143a0  push    rbx
0x1800143a2  push    rbp
0x1800143a3  push    rsi
0x1800143a4  push    rdi
0x1800143a5  push    r14
0x1800143a7  sub     rsp, 30h
0x1800143ab  mov     r14, rcx
0x1800143ae  mov     edi, edx
0x1800143b0  mov     edx, edx; dwBytes
0x1800143b2  mov     ecx, 2; uFlags
0x1800143b7  mov     rsi, r9
0x1800143ba  mov     rbp, r8
0x1800143bd  call    cs:__imp_GlobalAlloc
0x1800143c3  mov     rbx, rax
0x1800143c6  test    rax, rax
0x1800143c9  jz      short loc_180014443
0x1800143cb  mov     rcx, rax; hMem
0x1800143ce  call    cs:__imp_GlobalLock
0x1800143d4  test    rax, rax
0x1800143d7  jz      short loc_180014453
0x1800143d9  mov     r8d, edi; Size
0x1800143dc  mov     rdx, r14; Src
0x1800143df  mov     rcx, rax; void *
0x1800143e2  call    memcpy_0
0x1800143e7  mov     rcx, rbx; hMem
0x1800143ea  call    cs:__imp_GlobalUnlock
0x1800143f0  lea     r8, [rsp+58h+ppstm]; ppstm
0x1800143f5  mov     [rsp+58h+ppstm], 0
0x1800143fe  mov     edx, 1; fDeleteOnRelease
0x180014403  mov     rcx, rbx; hGlobal
0x180014406  call    cs:__imp_CreateStreamOnHGlobal
0x18001440c  mov     edi, eax
0x18001440e  test    eax, eax
0x180014410  js      short loc_180014463
0x180014412  mov     rcx, [rsp+58h+ppstm]; pStm
0x180014417  mov     r8, rsi; ppv
0x18001441a  mov     rdx, rbp; riid
0x18001441d  call    cs:__imp_CoUnmarshalInterface
0x180014423  mov     rcx, [rsp+58h+ppstm]
0x180014428  mov     ebx, eax
0x18001442a  mov     rdx, [rcx]
0x18001442d  mov     rax, [rdx+10h]
0x180014431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014436  mov     eax, ebx
0x180014438  add     rsp, 30h
0x18001443c  pop     r14
0x18001443e  pop     rdi
0x18001443f  pop     rsi
0x180014440  pop     rbp
0x180014441  pop     rbx
0x180014442  retn
0x180014443  mov     eax, 8007000Eh
0x180014448  add     rsp, 30h
0x18001444c  pop     r14
0x18001444e  pop     rdi
0x18001444f  pop     rsi
0x180014450  pop     rbp
0x180014451  pop     rbx
0x180014452  retn
0x180014453  mov     rcx, rbx; hMem
0x180014456  call    cs:__imp_GlobalFree
0x18001445c  mov     eax, 80004005h
0x180014461  jmp     short loc_180014438
0x180014463  mov     rcx, rbx; hMem
0x180014466  call    cs:__imp_GlobalFree
0x18001446c  mov     eax, edi
0x18001446e  jmp     short loc_180014438
```
