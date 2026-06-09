# DfsDeletePrefixTable

- ea: `0x14005b03c`
- end: `0x14005b0be`
- name: `DfsDeletePrefixTable`
- size: `130`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a074`
- `0x14005b1b8`

## callees

- `0x14005b03c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14005b05c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14005b05c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005b07f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005b0a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005b07f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005b0a6`

## pseudocode

```c
void __fastcall DfsDeletePrefixTable(LPCRITICAL_SECTION *lpMem)
{
  int v1; // eax
  LPCRITICAL_SECTION *v2; // rdi

  if ( lpMem )
  {
    v1 = *((_DWORD *)lpMem + 2);
    v2 = lpMem + 3;
    if ( (v1 & 8) != 0 )
    {
      DeleteCriticalSection(*v2);
      *((_DWORD *)lpMem + 2) &= ~8u;
      v1 = *((_DWORD *)lpMem + 2);
    }
    if ( (v1 & 4) != 0 )
    {
      HeapFree(PrefixTableHeapHandle, 0, *v2);
      *v2 = 0;
      *((_DWORD *)lpMem + 2) &= ~4u;
      v1 = *((_DWORD *)lpMem + 2);
    }
    if ( (v1 & 2) != 0 )
      HeapFree(PrefixTableHeapHandle, 0, lpMem);
  }
}

```

## disassembly

```asm
0x14005b03c  test    rcx, rcx
0x14005b03f  jz      short locret_14005B0BC
0x14005b041  mov     [rsp+arg_0], rbx
0x14005b046  push    rdi
0x14005b047  sub     rsp, 20h
0x14005b04b  mov     eax, [rcx+8]
0x14005b04e  lea     rdi, [rcx+18h]
0x14005b052  mov     rbx, rcx
0x14005b055  test    al, 8
0x14005b057  jz      short loc_14005B06F
0x14005b059  mov     rcx, [rdi]; lpCriticalSection
0x14005b05c  call    cs:__imp_DeleteCriticalSection
0x14005b063  nop     dword ptr [rax+rax+00h]
0x14005b068  and     dword ptr [rbx+8], 0FFFFFFF7h
0x14005b06c  mov     eax, [rbx+8]
0x14005b06f  test    al, 4
0x14005b071  jz      short loc_14005B096
0x14005b073  mov     r8, [rdi]; lpMem
0x14005b076  xor     edx, edx; dwFlags
0x14005b078  mov     rcx, cs:PrefixTableHeapHandle; hHeap
0x14005b07f  call    cs:__imp_HeapFree
0x14005b086  nop     dword ptr [rax+rax+00h]
0x14005b08b  and     qword ptr [rdi], 0
0x14005b08f  and     dword ptr [rbx+8], 0FFFFFFFBh
0x14005b093  mov     eax, [rbx+8]
0x14005b096  test    al, 2
0x14005b098  jz      short loc_14005B0B2
0x14005b09a  mov     rcx, cs:PrefixTableHeapHandle; hHeap
0x14005b0a1  mov     r8, rbx; lpMem
0x14005b0a4  xor     edx, edx; dwFlags
0x14005b0a6  call    cs:__imp_HeapFree
0x14005b0ad  nop     dword ptr [rax+rax+00h]
0x14005b0b2  mov     rbx, [rsp+28h+arg_0]
0x14005b0b7  add     rsp, 20h
0x14005b0bb  pop     rdi
0x14005b0bc  retn
```
