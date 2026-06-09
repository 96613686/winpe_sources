# BasepGetComputerNameExWRtlAlloc

- ea: `0x180081f6c`
- end: `0x180082028`
- name: `BasepGetComputerNameExWRtlAlloc`
- size: `188`
- prototype: `__int64 __fastcall(COMPUTER_NAME_FORMAT NameType)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004b35c`

## callees

- `0x180081f6c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18008200b`
- `ntdll!RtlFreeHeap` at `0x18008200b`
- `ntdll!RtlAllocateHeap` at `0x180081fcb`
- `ntdll!RtlAllocateHeap` at `0x180081fcb`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180081fa8`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180081fa8`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180081f85`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180081fe9`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180081f85`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180081fe9`

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
0x180081f6c  mov     [rsp+arg_0], rbx
0x180081f71  push    rdi
0x180081f72  sub     rsp, 20h
0x180081f76  xor     ebx, ebx
0x180081f78  lea     r8, [rsp+28h+nSize]; nSize
0x180081f7d  xor     edx, edx; lpBuffer
0x180081f7f  mov     [rsp+28h+nSize], ebx
0x180081f83  mov     edi, ecx
0x180081f85  call    cs:__imp_GetComputerNameExW
0x180081f8c  nop     dword ptr [rax+rax+00h]
0x180081f91  test    eax, eax
0x180081f93  jnz     loc_180082019
0x180081f99  mov     eax, gs:68h
0x180081fa1  cmp     eax, 0EAh
0x180081fa6  jnz     short loc_180082019
0x180081fa8  call    cs:__imp_KernelBaseGetGlobalData
0x180081faf  nop     dword ptr [rax+rax+00h]
0x180081fb4  mov     rcx, gs:60h
0x180081fbd  mov     r8d, [rsp+28h+nSize]
0x180081fc2  add     r8, r8; Size
0x180081fc5  mov     edx, [rax]; Flags
0x180081fc7  mov     rcx, [rcx+30h]; HeapHandle
0x180081fcb  call    cs:__imp_RtlAllocateHeap
0x180081fd2  nop     dword ptr [rax+rax+00h]
0x180081fd7  mov     rbx, rax
0x180081fda  test    rax, rax
0x180081fdd  jz      short loc_180082019
0x180081fdf  lea     r8, [rsp+28h+nSize]; nSize
0x180081fe4  mov     rdx, rax; lpBuffer
0x180081fe7  mov     ecx, edi; NameType
0x180081fe9  call    cs:__imp_GetComputerNameExW
0x180081ff0  nop     dword ptr [rax+rax+00h]
0x180081ff5  test    eax, eax
0x180081ff7  jnz     short loc_180082019
0x180081ff9  mov     rcx, gs:60h
0x180082002  mov     r8, rbx; P
0x180082005  xor     edx, edx; Flags
0x180082007  mov     rcx, [rcx+30h]; HeapHandle
0x18008200b  call    cs:__imp_RtlFreeHeap
0x180082012  nop     dword ptr [rax+rax+00h]
0x180082017  xor     ebx, ebx
0x180082019  mov     rax, rbx
0x18008201c  mov     rbx, [rsp+28h+arg_0]
0x180082021  add     rsp, 20h
0x180082025  pop     rdi
0x180082026  retn
```
