# BasepGetComputerNameExWRtlAlloc

- ea: `0x18007a0bc`
- end: `0x18007a155`
- name: `BasepGetComputerNameExWRtlAlloc`
- size: `153`
- prototype: `__int64 __fastcall(COMPUTER_NAME_FORMAT NameType)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180046ce0`

## callees

- `0x18007a0bc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18007a13f`
- `ntdll!RtlFreeHeap` at `0x18007a13f`
- `ntdll!RtlAllocateHeap` at `0x18007a10b`
- `ntdll!RtlAllocateHeap` at `0x18007a10b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18007a0ee`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18007a0ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007a0d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007a123`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007a0d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007a123`

## pseudocode

```c
WCHAR *__fastcall BasepGetComputerNameExWRtlAlloc(COMPUTER_NAME_FORMAT NameType)
{
  WCHAR *v1; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  ULONG *GlobalData; // rax
  WCHAR *Heap; // rax
  DWORD nSize; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  nSize = 0;
  if ( !GetComputerNameExW(NameType, 0, &nSize) && NtCurrentTeb()->LastErrorValue == 234 )
  {
    GlobalData = (ULONG *)KernelBaseGetGlobalData(v4, v3, v5, v6);
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 2LL * nSize);
    v1 = Heap;
    if ( Heap )
    {
      if ( !GetComputerNameExW(NameType, Heap, &nSize) )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
        return 0;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18007a0bc  mov     [rsp+arg_0], rbx
0x18007a0c1  push    rdi
0x18007a0c2  sub     rsp, 20h
0x18007a0c6  xor     ebx, ebx
0x18007a0c8  lea     r8, [rsp+28h+nSize]; nSize
0x18007a0cd  xor     edx, edx; lpBuffer
0x18007a0cf  mov     [rsp+28h+nSize], ebx
0x18007a0d3  mov     edi, ecx
0x18007a0d5  call    cs:__imp_GetComputerNameExW
0x18007a0db  test    eax, eax
0x18007a0dd  jnz     short loc_18007A147
0x18007a0df  mov     eax, gs:68h
0x18007a0e7  cmp     eax, 0EAh
0x18007a0ec  jnz     short loc_18007A147
0x18007a0ee  call    cs:__imp_KernelBaseGetGlobalData
0x18007a0f4  mov     rcx, gs:60h
0x18007a0fd  mov     r8d, [rsp+28h+nSize]
0x18007a102  add     r8, r8; Size
0x18007a105  mov     edx, [rax]; Flags
0x18007a107  mov     rcx, [rcx+30h]; HeapHandle
0x18007a10b  call    cs:__imp_RtlAllocateHeap
0x18007a111  mov     rbx, rax
0x18007a114  test    rax, rax
0x18007a117  jz      short loc_18007A147
0x18007a119  lea     r8, [rsp+28h+nSize]; nSize
0x18007a11e  mov     rdx, rax; lpBuffer
0x18007a121  mov     ecx, edi; NameType
0x18007a123  call    cs:__imp_GetComputerNameExW
0x18007a129  test    eax, eax
0x18007a12b  jnz     short loc_18007A147
0x18007a12d  mov     rcx, gs:60h
0x18007a136  mov     r8, rbx; P
0x18007a139  xor     edx, edx; Flags
0x18007a13b  mov     rcx, [rcx+30h]; HeapHandle
0x18007a13f  call    cs:__imp_RtlFreeHeap
0x18007a145  xor     ebx, ebx
0x18007a147  mov     rax, rbx
0x18007a14a  mov     rbx, [rsp+28h+arg_0]
0x18007a14f  add     rsp, 20h
0x18007a153  pop     rdi
0x18007a154  retn
```
