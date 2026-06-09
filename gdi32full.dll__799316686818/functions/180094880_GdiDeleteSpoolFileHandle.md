# GdiDeleteSpoolFileHandle

- ea: `0x180094880`
- end: `0x1800949dc`
- name: `GdiDeleteSpoolFileHandle`
- size: `348`
- prototype: `BOOL __stdcall(HANDLE SpoolFileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180094b70`

## callees

- `0x18006c0ec`
- `0x180094880`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800948c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800948eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094914`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800948c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800948eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094914`
- `GDI32!DeleteDC` at `0x18009498c`
- `GDI32!DeleteDC` at `0x18009498c`
- `GDI32!fpClosePrinter` at `0x180094992`
- `ntdll!RtlFreeHeap` at `0x180094939`
- `ntdll!RtlFreeHeap` at `0x180094976`
- `ntdll!RtlFreeHeap` at `0x1800949bd`
- `ntdll!RtlFreeHeap` at `0x180094939`
- `ntdll!RtlFreeHeap` at `0x180094976`
- `ntdll!RtlFreeHeap` at `0x1800949bd`
- `ntdll!RtlDecodePointer` at `0x18009499c`
- `ntdll!RtlDecodePointer` at `0x18009499c`

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
0x180094880  mov     [rsp+arg_0], rbx
0x180094885  mov     [rsp+arg_8], rsi
0x18009488a  push    rdi
0x18009488b  sub     rsp, 20h
0x18009488f  mov     rbx, rcx
0x180094892  cmp     dword ptr [rcx], 53504854h
0x180094898  jz      short loc_1800948A1
0x18009489a  xor     eax, eax
0x18009489c  jmp     loc_1800949CC
0x1800948a1  mov     rcx, [rcx+18h]; hMem
0x1800948a5  mov     edx, [rbx+28h]
0x1800948a8  test    edx, edx
0x1800948aa  jz      short loc_1800948E0
0x1800948ac  xor     edi, edi
0x1800948ae  lea     rsi, [rdi+rdi*4]
0x1800948b2  mov     rax, [rbx+30h]
0x1800948b6  cmp     [rax+rsi*8+10h], rcx
0x1800948bb  jz      short loc_1800948DA
0x1800948bd  cmp     rcx, [rbx+18h]
0x1800948c1  jz      short loc_1800948D1
0x1800948c3  test    rcx, rcx
0x1800948c6  jz      short loc_1800948D1
0x1800948c8  call    cs:__imp_LocalFree
0x1800948ce  mov     edx, [rbx+28h]
0x1800948d1  mov     rax, [rbx+30h]
0x1800948d5  mov     rcx, [rax+rsi*8+10h]; hMem
0x1800948da  inc     edi
0x1800948dc  cmp     edi, edx
0x1800948de  jb      short loc_1800948AE
0x1800948e0  cmp     rcx, [rbx+18h]
0x1800948e4  jz      short loc_1800948F1
0x1800948e6  test    rcx, rcx
0x1800948e9  jz      short loc_1800948F1
0x1800948eb  call    cs:__imp_LocalFree
0x1800948f1  cmp     qword ptr [rbx+30h], 0
0x1800948f6  jz      short loc_18009493F
0x1800948f8  mov     esi, [rbx+28h]
0x1800948fb  jmp     short loc_180094922
0x1800948fd  lea     eax, [rsi-1]
0x180094900  mov     esi, eax
0x180094902  lea     rcx, [rax+rax*4]
0x180094906  mov     rax, [rbx+30h]
0x18009490a  mov     rdi, [rax+rcx*8+20h]
0x18009490f  jmp     short loc_18009491A
0x180094911  mov     rdi, [rdi]
0x180094914  call    cs:__imp_LocalFree
0x18009491a  test    rdi, rdi
0x18009491d  mov     rcx, rdi; hMem
0x180094920  jnz     short loc_180094911
0x180094922  test    esi, esi
0x180094924  jnz     short loc_1800948FD
0x180094926  mov     rcx, gs:60h
0x18009492f  mov     r8, [rbx+30h]; P
0x180094933  xor     edx, edx; Flags
0x180094935  mov     rcx, [rcx+30h]; HeapHandle
0x180094939  call    cs:__imp_RtlFreeHeap
0x18009493f  mov     rdi, [rbx+58h]
0x180094943  test    rdi, rdi
0x180094946  jz      short loc_180094988
0x180094948  mov     rax, rdi
0x18009494b  mov     rax, [rax+18h]
0x18009494f  mov     [rbx+58h], rax
0x180094953  mov     rcx, [rdi+8]
0x180094957  test    rcx, rcx
0x18009495a  jz      short loc_180094964
0x18009495c  mov     edx, [rdi+10h]
0x18009495f  call    InternalDeleteEnhMetaFile
0x180094964  mov     rcx, gs:60h
0x18009496d  mov     r8, rdi; P
0x180094970  xor     edx, edx; Flags
0x180094972  mov     rcx, [rcx+30h]; HeapHandle
0x180094976  call    cs:__imp_RtlFreeHeap
0x18009497c  mov     rdi, [rbx+58h]
0x180094980  mov     rax, rdi
0x180094983  test    rdi, rdi
0x180094986  jnz     short loc_18009494B
0x180094988  mov     rcx, [rbx+8]; hdc
0x18009498c  call    cs:__imp_DeleteDC
0x180094992  mov     rcx, cs:__imp_fpClosePrinter
0x180094999  mov     rcx, [rcx]; Pointer
0x18009499c  call    cs:__imp_RtlDecodePointer
0x1800949a2  mov     rcx, [rbx+10h]
0x1800949a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800949ab  mov     rcx, gs:60h
0x1800949b4  mov     r8, rbx; P
0x1800949b7  xor     edx, edx; Flags
0x1800949b9  mov     rcx, [rcx+30h]; HeapHandle
0x1800949bd  call    cs:__imp_RtlFreeHeap
0x1800949c3  mov     eax, 1
0x1800949c8  jmp     short loc_1800949CC
0x1800949ca  xor     eax, eax
0x1800949cc  mov     rbx, [rsp+28h+arg_0]
0x1800949d1  mov     rsi, [rsp+28h+arg_8]
0x1800949d6  add     rsp, 20h
0x1800949da  pop     rdi
0x1800949db  retn
```
