# CReservedBlockManager::GetBlock(void)

- ea: `0x18013eae8`
- end: `0x18013eb6a`
- name: `?GetBlock@CReservedBlockManager@@QEAAPEAXXZ`
- size: `130`
- prototype: `void *__fastcall(CReservedBlockManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180138bc0`

## callees

- `0x18013eae8`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x18013eaf5`
- `KERNEL32!InterlockedPopEntrySList` at `0x18013eaf5`
- `KERNEL32!VirtualAlloc` at `0x18013eb0e`
- `KERNEL32!VirtualAlloc` at `0x18013eb40`
- `KERNEL32!VirtualAlloc` at `0x18013eb0e`
- `KERNEL32!VirtualAlloc` at `0x18013eb40`
- `KERNEL32!VirtualFree` at `0x18013eb5c`
- `KERNEL32!VirtualFree` at `0x18013eb5c`

## pseudocode

```c
void *__fastcall CReservedBlockManager::GetBlock(union _SLIST_HEADER *this)
{
  void *result; // rax
  unsigned __int64 v3; // rcx
  __int64 v4; // rbx

  result = InterlockedPopEntrySList(this + 1);
  if ( !result )
  {
    result = VirtualAlloc(0, LODWORD(this->Alignment), 0x2000u, 4u);
    if ( result )
    {
      v3 = 16LL * g_SystemInfo.dwPageSize;
      if ( v3 > 0xFFFFFFFF )
      {
        VirtualFree(result, 0, 0x8000u);
        return 0;
      }
      else
      {
        v4 = (unsigned int)v3;
        result = VirtualAlloc(result, (unsigned int)v3, 0x1000u, 4u);
        if ( result )
          *((_QWORD *)result + 2) = v4;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18013eae8  push    rbx
0x18013eaea  sub     rsp, 20h
0x18013eaee  mov     rbx, rcx
0x18013eaf1  add     rcx, 10h; ListHead
0x18013eaf5  call    cs:__imp_InterlockedPopEntrySList
0x18013eafb  test    rax, rax
0x18013eafe  jnz     short loc_18013EB64
0x18013eb00  mov     edx, [rbx]; dwSize
0x18013eb02  lea     r9d, [rax+4]; flProtect
0x18013eb06  xor     ecx, ecx; lpAddress
0x18013eb08  mov     r8d, 2000h; flAllocationType
0x18013eb0e  call    cs:__imp_VirtualAlloc
0x18013eb14  test    rax, rax
0x18013eb17  jz      short loc_18013EB64
0x18013eb19  mov     ecx, cs:?g_SystemInfo@@3U_SYSTEM_INFO@@A.dwPageSize; _SYSTEM_INFO g_SystemInfo ...
0x18013eb1f  mov     edx, 0FFFFFFFFh
0x18013eb24  shl     rcx, 4
0x18013eb28  cmp     rcx, rdx
0x18013eb2b  ja      short loc_18013EB51
0x18013eb2d  mov     ebx, ecx
0x18013eb2f  mov     r9d, 4; flProtect
0x18013eb35  mov     edx, ecx; dwSize
0x18013eb37  mov     r8d, 1000h; flAllocationType
0x18013eb3d  mov     rcx, rax; lpAddress
0x18013eb40  call    cs:__imp_VirtualAlloc
0x18013eb46  test    rax, rax
0x18013eb49  jz      short loc_18013EB64
0x18013eb4b  mov     [rax+10h], rbx
0x18013eb4f  jmp     short loc_18013EB64
0x18013eb51  xor     edx, edx; dwSize
0x18013eb53  mov     r8d, 8000h; dwFreeType
0x18013eb59  mov     rcx, rax; lpAddress
0x18013eb5c  call    cs:__imp_VirtualFree
0x18013eb62  xor     eax, eax
0x18013eb64  add     rsp, 20h
0x18013eb68  pop     rbx
0x18013eb69  retn
```
