# CreateStreamOnFile(ushort const *,uint)

- ea: `0x18000ab54`
- end: `0x18000ac29`
- name: `?CreateStreamOnFile@@YAPEAUIStream@@PEBGI@Z`
- size: `213`
- prototype: `struct IStream *__fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000adac`
- `0x18010c738`

## callees

- `0x18000ab54`
- `0x18011f804`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000abac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000abac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abc0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ab86`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ab86`

## pseudocode

```c
struct IStream *__fastcall CreateStreamOnFile(const unsigned __int16 *a1)
{
  char *FileW; // rdi
  FileStream *v3; // rax
  FileStream *v5; // rax
  FileStream *v6; // rbx

  FileW = (char *)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  v3 = (FileStream *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x60u);
  if ( !v3 || (v5 = FileStream::FileStream(v3), (v6 = v5) == 0) )
  {
    CloseHandle(FileW);
    return 0;
  }
  if ( (*(int (__fastcall **)(FileStream *, char *, __int64, const unsigned __int16 *))(*(_QWORD *)v5 + 120LL))(
         v5,
         FileW,
         16,
         a1) < 0 )
  {
    (*(void (__fastcall **)(FileStream *, __int64))(*(_QWORD *)v6 + 112LL))(v6, 1);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18000ab54  mov     rax, rsp
0x18000ab57  mov     [rax+8], rbx
0x18000ab5b  mov     [rax+10h], rsi
0x18000ab5f  push    rdi
0x18000ab60  sub     rsp, 40h
0x18000ab64  and     qword ptr [rax-18h], 0
0x18000ab69  xor     r9d, r9d; lpSecurityAttributes
0x18000ab6c  mov     dword ptr [rax-20h], 80h
0x18000ab73  mov     edx, 80000000h; dwDesiredAccess
0x18000ab78  mov     rsi, rcx
0x18000ab7b  mov     dword ptr [rax-28h], 3
0x18000ab82  lea     r8d, [r9+1]; dwShareMode
0x18000ab86  call    cs:__imp_CreateFileW
0x18000ab8d  nop     dword ptr [rax+rax+00h]
0x18000ab92  mov     rdi, rax
0x18000ab95  lea     rdx, [rax-1]
0x18000ab99  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000ab9d  ja      short loc_18000ABCC
0x18000ab9f  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18000aba6  xor     edx, edx; dwFlags
0x18000aba8  lea     r8d, [rdx+60h]; dwBytes
0x18000abac  call    cs:__imp_HeapAlloc
0x18000abb3  nop     dword ptr [rax+rax+00h]
0x18000abb8  test    rax, rax
0x18000abbb  jnz     short loc_18000ABDF
0x18000abbd  mov     rcx, rdi; hObject
0x18000abc0  call    cs:__imp_CloseHandle
0x18000abc7  nop     dword ptr [rax+rax+00h]
0x18000abcc  xor     eax, eax
0x18000abce  mov     rbx, [rsp+48h+arg_0]
0x18000abd3  mov     rsi, [rsp+48h+arg_8]
0x18000abd8  add     rsp, 40h
0x18000abdc  pop     rdi
0x18000abdd  retn
0x18000abdf  mov     rcx, rax; this
0x18000abe2  call    ??0FileStream@@QEAA@XZ; FileStream::FileStream(void)
0x18000abe7  mov     rbx, rax
0x18000abea  test    rax, rax
0x18000abed  jz      short loc_18000ABBD
0x18000abef  mov     rcx, [rax]
0x18000abf2  mov     r9, rsi
0x18000abf5  mov     r8d, 10h
0x18000abfb  mov     rdx, rdi
0x18000abfe  mov     rax, [rcx+78h]
0x18000ac02  mov     rcx, rbx
0x18000ac05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac0a  test    eax, eax
0x18000ac0c  js      short loc_18000AC13
0x18000ac0e  mov     rax, rbx
0x18000ac11  jmp     short loc_18000ABCE
0x18000ac13  mov     rax, [rbx]
0x18000ac16  mov     edx, 1
0x18000ac1b  mov     rcx, rbx
0x18000ac1e  mov     rax, [rax+70h]
0x18000ac22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac27  jmp     short loc_18000ABCC
```
