# GdiDeleteSpoolFileHandle

- ea: `0x18009a6c0`
- end: `0x18009a84d`
- name: `GdiDeleteSpoolFileHandle`
- size: `397`
- prototype: `BOOL __stdcall(HANDLE SpoolFileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18009a9e0`

## callees

- `0x180070a48`
- `0x18009a6c0`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a708`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a731`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a708`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a731`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a760`
- `GDI32!DeleteDC` at `0x18009a7ea`
- `GDI32!DeleteDC` at `0x18009a7ea`
- `GDI32!fpClosePrinter` at `0x18009a7f6`
- `ntdll!RtlFreeHeap` at `0x18009a78b`
- `ntdll!RtlFreeHeap` at `0x18009a7ce`
- `ntdll!RtlFreeHeap` at `0x18009a827`
- `ntdll!RtlFreeHeap` at `0x18009a78b`
- `ntdll!RtlFreeHeap` at `0x18009a7ce`
- `ntdll!RtlFreeHeap` at `0x18009a827`
- `ntdll!RtlDecodePointer` at `0x18009a800`
- `ntdll!RtlDecodePointer` at `0x18009a800`

## pseudocode

```c
BOOL __stdcall GdiDeleteSpoolFileHandle(HANDLE SpoolFileHandle)
{
  void *v3; // rcx
  unsigned int v4; // edx
  __int64 v5; // rdi
  int v6; // esi
  _QWORD *v7; // rdi
  void *v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  void (__fastcall *v12)(_QWORD); // rax

  if ( *(_DWORD *)SpoolFileHandle != 1397770324 )
    return 0;
  v3 = (void *)*((_QWORD *)SpoolFileHandle + 3);
  v4 = *((_DWORD *)SpoolFileHandle + 10);
  if ( v4 )
  {
    v5 = 0;
    do
    {
      if ( *(void **)(*((_QWORD *)SpoolFileHandle + 6) + 40 * v5 + 16) != v3 )
      {
        if ( v3 != *((void **)SpoolFileHandle + 3) && v3 )
        {
          LocalFree(v3);
          v4 = *((_DWORD *)SpoolFileHandle + 10);
        }
        v3 = *(void **)(*((_QWORD *)SpoolFileHandle + 6) + 40 * v5 + 16);
      }
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < v4 );
  }
  if ( v3 != *((void **)SpoolFileHandle + 3) && v3 )
    LocalFree(v3);
  if ( *((_QWORD *)SpoolFileHandle + 6) )
  {
    v6 = *((_DWORD *)SpoolFileHandle + 10);
    while ( v6 )
    {
      v7 = *(_QWORD **)(*((_QWORD *)SpoolFileHandle + 6) + 40LL * (unsigned int)--v6 + 32);
      while ( 1 )
      {
        v8 = v7;
        if ( !v7 )
          break;
        v7 = (_QWORD *)*v7;
        LocalFree(v8);
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)SpoolFileHandle + 6));
  }
  v9 = *((_QWORD *)SpoolFileHandle + 11);
  if ( v9 )
  {
    v10 = *((_QWORD *)SpoolFileHandle + 11);
    do
    {
      *((_QWORD *)SpoolFileHandle + 11) = *(_QWORD *)(v10 + 24);
      v11 = *(_QWORD *)(v9 + 8);
      if ( v11 )
        InternalDeleteEnhMetaFile(v11, *(unsigned int *)(v9 + 16));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v9);
      v9 = *((_QWORD *)SpoolFileHandle + 11);
      v10 = v9;
    }
    while ( v9 );
  }
  DeleteDC(*((HDC *)SpoolFileHandle + 1));
  v12 = (void (__fastcall *)(_QWORD))RtlDecodePointer(fpClosePrinter);
  v12(*((_QWORD *)SpoolFileHandle + 2));
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SpoolFileHandle);
  return 1;
}

```

## disassembly

```asm
0x18009a6c0  mov     [rsp+arg_0], rbx
0x18009a6c5  mov     [rsp+arg_8], rsi
0x18009a6ca  push    rdi
0x18009a6cb  sub     rsp, 20h
0x18009a6cf  mov     rbx, rcx
0x18009a6d2  cmp     dword ptr [rcx], 53504854h
0x18009a6d8  jz      short loc_18009A6E1
0x18009a6da  xor     eax, eax
0x18009a6dc  jmp     loc_18009A83C
0x18009a6e1  mov     rcx, [rcx+18h]; hMem
0x18009a6e5  mov     edx, [rbx+28h]
0x18009a6e8  test    edx, edx
0x18009a6ea  jz      short loc_18009A726
0x18009a6ec  xor     edi, edi
0x18009a6ee  lea     rsi, [rdi+rdi*4]
0x18009a6f2  mov     rax, [rbx+30h]
0x18009a6f6  cmp     [rax+rsi*8+10h], rcx
0x18009a6fb  jz      short loc_18009A720
0x18009a6fd  cmp     rcx, [rbx+18h]
0x18009a701  jz      short loc_18009A717
0x18009a703  test    rcx, rcx
0x18009a706  jz      short loc_18009A717
0x18009a708  call    cs:__imp_LocalFree
0x18009a70f  nop     dword ptr [rax+rax+00h]
0x18009a714  mov     edx, [rbx+28h]
0x18009a717  mov     rax, [rbx+30h]
0x18009a71b  mov     rcx, [rax+rsi*8+10h]; hMem
0x18009a720  inc     edi
0x18009a722  cmp     edi, edx
0x18009a724  jb      short loc_18009A6EE
0x18009a726  cmp     rcx, [rbx+18h]
0x18009a72a  jz      short loc_18009A73D
0x18009a72c  test    rcx, rcx
0x18009a72f  jz      short loc_18009A73D
0x18009a731  call    cs:__imp_LocalFree
0x18009a738  nop     dword ptr [rax+rax+00h]
0x18009a73d  cmp     qword ptr [rbx+30h], 0
0x18009a742  jz      short loc_18009A797
0x18009a744  mov     esi, [rbx+28h]
0x18009a747  jmp     short loc_18009A774
0x18009a749  lea     eax, [rsi-1]
0x18009a74c  mov     esi, eax
0x18009a74e  lea     rcx, [rax+rax*4]
0x18009a752  mov     rax, [rbx+30h]
0x18009a756  mov     rdi, [rax+rcx*8+20h]
0x18009a75b  jmp     short loc_18009A76C
0x18009a75d  mov     rdi, [rdi]
0x18009a760  call    cs:__imp_LocalFree
0x18009a767  nop     dword ptr [rax+rax+00h]
0x18009a76c  test    rdi, rdi
0x18009a76f  mov     rcx, rdi; hMem
0x18009a772  jnz     short loc_18009A75D
0x18009a774  test    esi, esi
0x18009a776  jnz     short loc_18009A749
0x18009a778  mov     rcx, gs:60h
0x18009a781  mov     r8, [rbx+30h]; P
0x18009a785  xor     edx, edx; Flags
0x18009a787  mov     rcx, [rcx+30h]; HeapHandle
0x18009a78b  call    cs:__imp_RtlFreeHeap
0x18009a792  nop     dword ptr [rax+rax+00h]
0x18009a797  mov     rdi, [rbx+58h]
0x18009a79b  test    rdi, rdi
0x18009a79e  jz      short loc_18009A7E6
0x18009a7a0  mov     rax, rdi
0x18009a7a3  mov     rax, [rax+18h]
0x18009a7a7  mov     [rbx+58h], rax
0x18009a7ab  mov     rcx, [rdi+8]
0x18009a7af  test    rcx, rcx
0x18009a7b2  jz      short loc_18009A7BC
0x18009a7b4  mov     edx, [rdi+10h]
0x18009a7b7  call    InternalDeleteEnhMetaFile
0x18009a7bc  mov     rcx, gs:60h
0x18009a7c5  mov     r8, rdi; P
0x18009a7c8  xor     edx, edx; Flags
0x18009a7ca  mov     rcx, [rcx+30h]; HeapHandle
0x18009a7ce  call    cs:__imp_RtlFreeHeap
0x18009a7d5  nop     dword ptr [rax+rax+00h]
0x18009a7da  mov     rdi, [rbx+58h]
0x18009a7de  mov     rax, rdi
0x18009a7e1  test    rdi, rdi
0x18009a7e4  jnz     short loc_18009A7A3
0x18009a7e6  mov     rcx, [rbx+8]; hdc
0x18009a7ea  call    cs:__imp_DeleteDC
0x18009a7f1  nop     dword ptr [rax+rax+00h]
0x18009a7f6  mov     rcx, cs:__imp_fpClosePrinter
0x18009a7fd  mov     rcx, [rcx]; Pointer
0x18009a800  call    cs:__imp_RtlDecodePointer
0x18009a807  nop     dword ptr [rax+rax+00h]
0x18009a80c  mov     rcx, [rbx+10h]
0x18009a810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a815  mov     rcx, gs:60h
0x18009a81e  mov     r8, rbx; P
0x18009a821  xor     edx, edx; Flags
0x18009a823  mov     rcx, [rcx+30h]; HeapHandle
0x18009a827  call    cs:__imp_RtlFreeHeap
0x18009a82e  nop     dword ptr [rax+rax+00h]
0x18009a833  mov     eax, 1
0x18009a838  jmp     short loc_18009A83C
0x18009a83a  xor     eax, eax
0x18009a83c  mov     rbx, [rsp+28h+arg_0]
0x18009a841  mov     rsi, [rsp+28h+arg_8]
0x18009a846  add     rsp, 20h
0x18009a84a  pop     rdi
0x18009a84b  retn
```
