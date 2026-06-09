# Details::TestForFile(ushort const *,ushort * *)

- ea: `0x180045528`
- end: `0x1800455a6`
- name: `?TestForFile@Details@@YAJPEBGPEAPEAG@Z`
- size: `126`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800455ac`

## callees

- `0x18000d0bc`
- `0x180045528`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045593`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045565`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045565`

## pseudocode

```c
__int64 __fastcall Details::TestForFile(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r9
  void *v8; // rbp

  *a2 = 0;
  v3 = -2147467259;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v7 = -1;
  v8 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    do
      ++v7;
    while ( a1[v7] );
    v3 = _AllocStringWorker<CTCoAllocPolicy>(v6, v5, a1);
    CloseHandle(v8);
  }
  return v3;
}

```

## disassembly

```asm
0x180045528  push    rbx
0x18004552a  push    rbp
0x18004552b  push    rsi
0x18004552c  push    rdi
0x18004552d  push    r14
0x18004552f  sub     rsp, 40h
0x180045533  xor     r14d, r14d
0x180045536  mov     rsi, rdx
0x180045539  mov     [rdx], r14
0x18004553c  xor     r9d, r9d; lpSecurityAttributes
0x18004553f  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180045544  mov     edx, 80000000h; dwDesiredAccess
0x180045549  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180045551  mov     rdi, rcx
0x180045554  lea     r8d, [r14+1]; dwShareMode
0x180045558  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180045560  mov     ebx, 80004005h
0x180045565  call    cs:__imp_CreateFileW
0x18004556b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004556f  mov     rbp, rax
0x180045572  cmp     rax, r9
0x180045575  jz      short loc_180045599
0x180045577  inc     r9
0x18004557a  cmp     [rdi+r9*2], r14w
0x18004557f  jnz     short loc_180045577
0x180045581  mov     r8, rdi
0x180045584  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi
0x180045589  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18004558e  mov     rcx, rbp; hObject
0x180045591  mov     ebx, eax
0x180045593  call    cs:__imp_CloseHandle
0x180045599  mov     eax, ebx
0x18004559b  add     rsp, 40h
0x18004559f  pop     r14
0x1800455a1  pop     rdi
0x1800455a2  pop     rsi
0x1800455a3  pop     rbp
0x1800455a4  pop     rbx
0x1800455a5  retn
```
