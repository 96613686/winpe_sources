# _heap_init

- ea: `0x18000feec`
- end: `0x18000ff5a`
- name: `_heap_init`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bdf4`

## callees

- `0x18000feec`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x18000fefe`
- `KERNEL32!HeapCreate` at `0x18000fefe`
- `KERNEL32!HeapSetInformation` at `0x18000ff28`
- `KERNEL32!HeapSetInformation` at `0x18000ff4a`
- `KERNEL32!HeapSetInformation` at `0x18000ff28`
- `KERNEL32!HeapSetInformation` at `0x18000ff4a`

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
0x18000feec  mov     [rsp+HeapInformation], ecx
0x18000fef0  sub     rsp, 28h
0x18000fef4  xor     r8d, r8d; dwMaximumSize
0x18000fef7  mov     edx, 1000h; dwInitialSize
0x18000fefc  xor     ecx, ecx; flOptions
0x18000fefe  call    cs:__imp_HeapCreate
0x18000ff04  mov     cs:_crtheap, rax
0x18000ff0b  test    rax, rax
0x18000ff0e  jz      short loc_18000FF55
0x18000ff10  mov     r9d, 4; HeapInformationLength
0x18000ff16  mov     [rsp+28h+HeapInformation], 2
0x18000ff1e  lea     r8, [rsp+28h+HeapInformation]; HeapInformation
0x18000ff23  xor     edx, edx; HeapInformationClass
0x18000ff25  mov     rcx, rax; HeapHandle
0x18000ff28  call    cs:__imp_HeapSetInformation
0x18000ff2e  mov     rcx, cs:_crtheap; HeapHandle
0x18000ff35  lea     r8, [rsp+28h+HeapInformation]; HeapInformation
0x18000ff3a  mov     r9d, 4; HeapInformationLength
0x18000ff40  mov     [rsp+28h+HeapInformation], 2
0x18000ff48  xor     edx, edx; HeapInformationClass
0x18000ff4a  call    cs:__imp_HeapSetInformation
0x18000ff50  mov     eax, 1
0x18000ff55  add     rsp, 28h
0x18000ff59  retn
```
