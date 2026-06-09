# _heap_init

- ea: `0x18001ce00`
- end: `0x18001ce6e`
- name: `_heap_init`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007c78`

## callees

- `0x18001ce00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001ce12`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001ce12`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x18001ce3c`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x18001ce5e`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x18001ce3c`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x18001ce5e`

## pseudocode

```c
__int64 __fastcall heap_init(int a1)
{
  __int64 result; // rax
  int HeapInformation; // [rsp+30h] [rbp+8h] BYREF

  HeapInformation = a1;
  result = (__int64)HeapCreate(0, 0x1000u, 0);
  crtheap = (HANDLE)result;
  if ( result )
  {
    HeapInformation = 2;
    HeapSetInformation((HANDLE)result, HeapCompatibilityInformation, &HeapInformation, 4u);
    HeapInformation = 2;
    HeapSetInformation(crtheap, HeapCompatibilityInformation, &HeapInformation, 4u);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001ce00  mov     [rsp+HeapInformation], ecx
0x18001ce04  sub     rsp, 28h
0x18001ce08  xor     r8d, r8d; dwMaximumSize
0x18001ce0b  mov     edx, 1000h; dwInitialSize
0x18001ce10  xor     ecx, ecx; flOptions
0x18001ce12  call    cs:__imp_HeapCreate
0x18001ce18  mov     cs:_crtheap, rax
0x18001ce1f  test    rax, rax
0x18001ce22  jz      short loc_18001CE69
0x18001ce24  mov     r9d, 4; HeapInformationLength
0x18001ce2a  mov     [rsp+28h+HeapInformation], 2
0x18001ce32  lea     r8, [rsp+28h+HeapInformation]; HeapInformation
0x18001ce37  xor     edx, edx; HeapInformationClass
0x18001ce39  mov     rcx, rax; HeapHandle
0x18001ce3c  call    cs:__imp_HeapSetInformation
0x18001ce42  mov     rcx, cs:_crtheap; HeapHandle
0x18001ce49  lea     r8, [rsp+28h+HeapInformation]; HeapInformation
0x18001ce4e  mov     r9d, 4; HeapInformationLength
0x18001ce54  mov     [rsp+28h+HeapInformation], 2
0x18001ce5c  xor     edx, edx; HeapInformationClass
0x18001ce5e  call    cs:__imp_HeapSetInformation
0x18001ce64  mov     eax, 1
0x18001ce69  add     rsp, 28h
0x18001ce6d  retn
```
