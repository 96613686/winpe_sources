# WcRemoveFilesInDirectory

- ea: `0x14000e4c0`
- end: `0x14000e5a2`
- name: `WcRemoveFilesInDirectory`
- size: `226`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x14000aca8`

## callees

- `0x14000dfb8`
- `0x14000e1c8`
- `0x14000e4c0`
- `0x14000e5a8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e530`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e530`
- `ntdll!RtlFreeHeap` at `0x14000e559`
- `ntdll!RtlFreeHeap` at `0x14000e585`
- `ntdll!RtlFreeHeap` at `0x14000e559`
- `ntdll!RtlFreeHeap` at `0x14000e585`

## pseudocode

```c
__int64 __fastcall WcRemoveFilesInDirectory(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PVOID v4; // rbx
  int v5; // edi
  int FinalPath; // eax
  int v7; // eax
  int v8; // eax
  void *v10; // [rsp+20h] [rbp-30h]
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF
  PVOID P; // [rsp+48h] [rbp-8h] BYREF
  DWORD v13; // [rsp+78h] [rbp+28h] BYREF
  int v14; // [rsp+80h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+38h] BYREF

  v4 = 0;
  hObject = (HANDLE)-1LL;
  v11 = 0;
  v13 = 0;
  P = 0;
  v14 = 0;
  v5 = WcCreateFile(&hObject, a1, a3, a4, v10);
  if ( v5 >= 0 )
  {
    FinalPath = GetFinalPath(hObject, (PVOID *)&v11, &v13);
    v4 = (PVOID)v11;
    v5 = FinalPath;
    if ( FinalPath >= 0 )
      v5 = WcRemoveFilesInDirectoryInternal(v11, (__int64)&P, (__int64)&v14);
  }
  if ( hObject != (HANDLE)-1LL && !CloseHandle(hObject) )
    __int2c();
  if ( v4 )
  {
    LOBYTE(v7) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    if ( !v7 )
      __int2c();
  }
  if ( P )
  {
    LOBYTE(v8) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    if ( !v8 )
      __int2c();
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000e4c0  mov     [rsp-18h+arg_8], edx
0x14000e4c4  push    rbp
0x14000e4c5  push    rbx
0x14000e4c6  push    rdi
0x14000e4c7  mov     rbp, rsp
0x14000e4ca  sub     rsp, 50h
0x14000e4ce  xor     ebx, ebx
0x14000e4d0  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x14000e4d8  mov     rdx, rcx; int
0x14000e4db  mov     [rbp+var_10], rbx
0x14000e4df  lea     rcx, [rbp+hObject]; int
0x14000e4e3  mov     [rbp+arg_8], ebx
0x14000e4e6  mov     [rbp+P], rbx
0x14000e4ea  mov     [rbp+arg_10], ebx
0x14000e4ed  call    WcCreateFile
0x14000e4f2  mov     edi, eax
0x14000e4f4  test    eax, eax
0x14000e4f6  js      short loc_14000E525
0x14000e4f8  mov     rcx, [rbp+hObject]; hFile
0x14000e4fc  lea     r8, [rbp+arg_8]
0x14000e500  lea     rdx, [rbp+var_10]
0x14000e504  call    GetFinalPath
0x14000e509  mov     rbx, [rbp+var_10]
0x14000e50d  mov     edi, eax
0x14000e50f  test    eax, eax
0x14000e511  js      short loc_14000E525
0x14000e513  lea     r8, [rbp+arg_10]
0x14000e517  mov     rcx, rbx
0x14000e51a  lea     rdx, [rbp+P]
0x14000e51e  call    WcRemoveFilesInDirectoryInternal
0x14000e523  mov     edi, eax
0x14000e525  cmp     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x14000e52a  jz      short loc_14000E542
0x14000e52c  mov     rcx, [rbp+hObject]; hObject
0x14000e530  call    cs:__imp_CloseHandle
0x14000e537  nop     dword ptr [rax+rax+00h]
0x14000e53c  test    eax, eax
0x14000e53e  jnz     short loc_14000E542
0x14000e540  int     2Ch; Windows NT - assertion failure
0x14000e542  test    rbx, rbx
0x14000e545  jz      short loc_14000E56B
0x14000e547  mov     rcx, gs:60h
0x14000e550  mov     r8, rbx; P
0x14000e553  xor     edx, edx; Flags
0x14000e555  mov     rcx, [rcx+30h]; HeapHandle
0x14000e559  call    cs:__imp_RtlFreeHeap
0x14000e560  nop     dword ptr [rax+rax+00h]
0x14000e565  test    eax, eax
0x14000e567  jnz     short loc_14000E56B
0x14000e569  int     2Ch; Windows NT - assertion failure
0x14000e56b  cmp     [rbp+P], 0
0x14000e570  jz      short loc_14000E597
0x14000e572  mov     rcx, gs:60h
0x14000e57b  xor     edx, edx; Flags
0x14000e57d  mov     r8, [rbp+P]; P
0x14000e581  mov     rcx, [rcx+30h]; HeapHandle
0x14000e585  call    cs:__imp_RtlFreeHeap
0x14000e58c  nop     dword ptr [rax+rax+00h]
0x14000e591  test    eax, eax
0x14000e593  jnz     short loc_14000E597
0x14000e595  int     2Ch; Windows NT - assertion failure
0x14000e597  mov     eax, edi
0x14000e599  add     rsp, 50h
0x14000e59d  pop     rdi
0x14000e59e  pop     rbx
0x14000e59f  pop     rbp
0x14000e5a0  retn
```
