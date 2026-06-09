# ConvertPrintTicketToDevModeThunk2

- ea: `0x180019c60`
- end: `0x180019d69`
- name: `ConvertPrintTicketToDevModeThunk2`
- size: `265`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, int, unsigned int, unsigned int, _QWORD *, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x1800197e4`
- `0x180019c60`
- `0x1800225b8`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019cf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019cf7`

## pseudocode

```c
__int64 __fastcall ConvertPrintTicketToDevModeThunk2(
        __int64 a1,
        unsigned __int8 *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        _QWORD *a6,
        _DWORD *a7,
        __int64 a8)
{
  int v12; // ebx
  void *v13; // rax
  void *v14; // rdi
  int v15; // eax
  SIZE_T cb; // [rsp+40h] [rbp-20h] BYREF
  struct IStream *v18; // [rsp+48h] [rbp-18h] BYREF
  void *Src; // [rsp+50h] [rbp-10h] BYREF

  v18 = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v18);
  v18 = 0;
  Src = 0;
  LODWORD(cb) = 0;
  v12 = BufferToIStream(a2, a3, &v18);
  if ( v12 >= 0 )
    v12 = ((__int64 (__fastcall *)(__int64, struct IStream *, _QWORD, _QWORD, SIZE_T *, void **, __int64))qword_1800321F0)(
            a1,
            v18,
            a4,
            a5,
            &cb,
            &Src,
            a8);
  if ( Src )
  {
    v13 = CoTaskMemAlloc((unsigned int)cb);
    v14 = v13;
    if ( v13 )
    {
      memcpy_0(v13, Src, (unsigned int)cb);
      *a7 = cb;
      *a6 = v14;
    }
    else
    {
      if ( v12 >= 0 )
        v12 = -2147024882;
      *a6 = 0;
      *a7 = 0;
    }
    v15 = ((__int64 (__fastcall *)(void *))qword_180032208)(Src);
    if ( v12 >= 0 )
      v12 = v15;
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v18);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180019c60  push    rbp
0x180019c62  push    rbx
0x180019c63  push    rsi
0x180019c64  push    rdi
0x180019c65  push    r14
0x180019c67  mov     rbp, rsp
0x180019c6a  sub     rsp, 60h
0x180019c6e  mov     r14, rcx
0x180019c71  mov     [rbp+var_18], 0
0x180019c79  lea     rcx, [rbp+var_18]
0x180019c7d  mov     esi, r9d
0x180019c80  mov     ebx, r8d
0x180019c83  mov     rdi, rdx
0x180019c86  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180019c8b  lea     r8, [rbp+var_18]; struct IStream **
0x180019c8f  mov     [rbp+var_18], 0
0x180019c97  mov     edx, ebx; int
0x180019c99  mov     [rbp+Src], 0
0x180019ca1  mov     rcx, rdi; unsigned __int8 *
0x180019ca4  mov     dword ptr [rbp+cb], 0
0x180019cab  call    ?BufferToIStream@@YAJPEAEHPEAPEAUIStream@@@Z; BufferToIStream(uchar *,int,IStream * *)
0x180019cb0  mov     ebx, eax
0x180019cb2  test    eax, eax
0x180019cb4  js      short loc_180019CED
0x180019cb6  mov     rcx, [rbp+arg_38]
0x180019cba  lea     rax, [rbp+Src]
0x180019cbe  mov     r9d, [rbp+arg_20]
0x180019cc2  mov     r8d, esi
0x180019cc5  mov     rdx, [rbp+var_18]
0x180019cc9  mov     [rsp+60h+var_30], rcx
0x180019cce  mov     rcx, r14
0x180019cd1  mov     [rsp+60h+var_38], rax
0x180019cd6  lea     rax, [rbp+cb]
0x180019cda  mov     [rsp+60h+var_40], rax
0x180019cdf  mov     rax, cs:qword_1800321F0
0x180019ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ceb  mov     ebx, eax
0x180019ced  cmp     [rbp+Src], 0
0x180019cf2  jz      short loc_180019D53
0x180019cf4  mov     ecx, dword ptr [rbp+cb]; cb
0x180019cf7  call    cs:__imp_CoTaskMemAlloc
0x180019cfd  mov     rdi, rax
0x180019d00  test    rax, rax
0x180019d03  jnz     short loc_180019D1E
0x180019d05  mov     eax, 8007000Eh
0x180019d0a  test    ebx, ebx
0x180019d0c  cmovns  ebx, eax
0x180019d0f  mov     rax, [rbp+arg_28]
0x180019d13  mov     [rax], rdi
0x180019d16  mov     rax, [rbp+arg_30]
0x180019d1a  mov     [rax], edi
0x180019d1c  jmp     short loc_180019D3E
0x180019d1e  mov     r8d, dword ptr [rbp+cb]; Size
0x180019d22  mov     rcx, rdi; void *
0x180019d25  mov     rdx, [rbp+Src]; Src
0x180019d29  call    memcpy_0
0x180019d2e  mov     eax, dword ptr [rbp+cb]
0x180019d31  mov     rcx, [rbp+arg_30]
0x180019d35  mov     [rcx], eax
0x180019d37  mov     rax, [rbp+arg_28]
0x180019d3b  mov     [rax], rdi
0x180019d3e  mov     rcx, [rbp+Src]
0x180019d42  mov     rax, cs:qword_180032208
0x180019d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d4e  test    ebx, ebx
0x180019d50  cmovns  ebx, eax
0x180019d53  lea     rcx, [rbp+var_18]
0x180019d57  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180019d5c  mov     eax, ebx
0x180019d5e  add     rsp, 60h
0x180019d62  pop     r14
0x180019d64  pop     rdi
0x180019d65  pop     rsi
0x180019d66  pop     rbx
0x180019d67  pop     rbp
0x180019d68  retn
```
