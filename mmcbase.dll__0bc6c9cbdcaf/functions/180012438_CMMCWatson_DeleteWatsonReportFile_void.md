# CMMCWatson::DeleteWatsonReportFile(void)

- ea: `0x180012438`
- end: `0x18001248f`
- name: `?DeleteWatsonReportFile@CMMCWatson@@AEAAXXZ`
- size: `87`
- prototype: `void __fastcall(CMMCWatson *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005ef0`

## callees

- `0x180012438`
- `0x18001b522`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180012470`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180012470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001244e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001244e`

## pseudocode

```c
void __fastcall CMMCWatson::DeleteWatsonReportFile(CMMCWatson *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 76);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 76) = -1;
  }
  if ( *((_WORD *)this + 308) )
    DeleteFileW((LPCWSTR)this + 308);
  memset_0((char *)this + 616, 0, 0x208u);
}

```

## disassembly

```asm
0x180012438  push    rbx
0x18001243a  sub     rsp, 20h
0x18001243e  mov     rbx, rcx
0x180012441  mov     rcx, [rcx+260h]; hObject
0x180012448  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001244c  jz      short loc_18001245F
0x18001244e  call    cs:__imp_CloseHandle
0x180012454  mov     qword ptr [rbx+260h], 0FFFFFFFFFFFFFFFFh
0x18001245f  cmp     word ptr [rbx+268h], 0
0x180012467  jz      short loc_180012476
0x180012469  lea     rcx, [rbx+268h]; lpFileName
0x180012470  call    cs:__imp_DeleteFileW
0x180012476  xor     edx, edx; Val
0x180012478  lea     rcx, [rbx+268h]; void *
0x18001247f  mov     r8d, 208h; Size
0x180012485  add     rsp, 20h
0x180012489  pop     rbx
0x18001248a  jmp     memset_0
```
