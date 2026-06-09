# AllocateWinsockThreadData

- ea: `0x180004558`
- end: `0x18000460d`
- name: `AllocateWinsockThreadData`
- size: `181`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800028b8`
- `0x180005f78`
- `0x18004a7bc`

## callees

- `0x180004558`
- `0x180022bd2`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180004571`
- `ntdll!RtlAllocateHeap` at `0x180004571`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800045ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800045ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800045b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800045b5`

## pseudocode

```c
_QWORD *AllocateWinsockThreadData()
{
  _QWORD *result; // rax
  _QWORD *v1; // rbx
  _QWORD *v2; // rax

  result = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x58u);
  v1 = result;
  if ( result )
  {
    memset_0(result, 0, 0x58u);
    v1[1] = v1;
    *v1 = v1;
    NtCurrentTeb()->WinSockData = 0;
    EnterCriticalSection(&WinsockTlsDataListLock);
    v2 = WinsockTlsDataList;
    if ( *((PVOID **)WinsockTlsDataList + 1) != &WinsockTlsDataList )
      __fastfail(3u);
    v1[1] = &WinsockTlsDataList;
    *v1 = v2;
    v2[1] = v1;
    WinsockTlsDataList = v1;
    LeaveCriticalSection(&WinsockTlsDataListLock);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x180004558  push    rbx
0x18000455a  sub     rsp, 20h
0x18000455e  mov     rcx, gs:60h
0x180004567  xor     edx, edx; Flags
0x180004569  mov     rcx, [rcx+30h]; HeapHandle
0x18000456d  lea     r8d, [rdx+58h]; Size
0x180004571  call    cs:__imp_RtlAllocateHeap
0x180004578  nop     dword ptr [rax+rax+00h]
0x18000457d  mov     rbx, rax
0x180004580  test    rax, rax
0x180004583  jz      short loc_180004604
0x180004585  xor     edx, edx; Val
0x180004587  mov     rcx, rax; void *
0x18000458a  lea     r8d, [rdx+58h]; Size
0x18000458e  call    memset_0
0x180004593  mov     [rbx+8], rbx
0x180004597  lea     rcx, WinsockTlsDataListLock; lpCriticalSection
0x18000459e  mov     [rbx], rbx
0x1800045a1  mov     rax, gs:30h
0x1800045aa  mov     qword ptr [rax+1738h], 0
0x1800045b5  call    cs:__imp_EnterCriticalSection
0x1800045bc  nop     dword ptr [rax+rax+00h]
0x1800045c1  mov     rax, cs:WinsockTlsDataList
0x1800045c8  lea     rcx, WinsockTlsDataList
0x1800045cf  cmp     [rax+8], rcx
0x1800045d3  jnz     short loc_180004606
0x1800045d5  mov     [rbx+8], rcx
0x1800045d9  lea     rcx, WinsockTlsDataListLock; lpCriticalSection
0x1800045e0  mov     [rbx], rax
0x1800045e3  mov     [rax+8], rbx
0x1800045e7  mov     cs:WinsockTlsDataList, rbx
0x1800045ee  call    cs:__imp_LeaveCriticalSection
0x1800045f5  nop     dword ptr [rax+rax+00h]
0x1800045fa  mov     rax, rbx
0x1800045fd  add     rsp, 20h
0x180004601  pop     rbx
0x180004602  retn
0x180004604  jmp     short loc_1800045FD
0x180004606  mov     ecx, 3
0x18000460b  int     29h; Win8: RtlFailFast(ecx)
```
