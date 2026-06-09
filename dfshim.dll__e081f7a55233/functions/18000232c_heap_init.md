# _heap_init

- ea: `0x18000232c`
- end: `0x18000239a`
- name: `_heap_init`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800010b4`

## callees

- `0x18000232c`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x18000233e`
- `KERNEL32!HeapCreate` at `0x18000233e`
- `KERNEL32!HeapSetInformation` at `0x180002368`
- `KERNEL32!HeapSetInformation` at `0x18000238a`
- `KERNEL32!HeapSetInformation` at `0x180002368`
- `KERNEL32!HeapSetInformation` at `0x18000238a`

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
0x18000232c  mov     [rsp+HeapInformation], ecx
0x180002330  sub     rsp, 28h
0x180002334  xor     r8d, r8d; dwMaximumSize
0x180002337  mov     edx, 1000h; dwInitialSize
0x18000233c  xor     ecx, ecx; flOptions
0x18000233e  call    cs:__imp_HeapCreate
0x180002344  mov     cs:_crtheap, rax
0x18000234b  test    rax, rax
0x18000234e  jz      short loc_180002395
0x180002350  mov     r9d, 4; HeapInformationLength
0x180002356  mov     [rsp+28h+HeapInformation], 2
0x18000235e  lea     r8, [rsp+28h+HeapInformation]; HeapInformation
0x180002363  xor     edx, edx; HeapInformationClass
0x180002365  mov     rcx, rax; HeapHandle
0x180002368  call    cs:__imp_HeapSetInformation
0x18000236e  mov     rcx, cs:_crtheap; HeapHandle
0x180002375  lea     r8, [rsp+28h+HeapInformation]; HeapInformation
0x18000237a  mov     r9d, 4; HeapInformationLength
0x180002380  mov     [rsp+28h+HeapInformation], 2
0x180002388  xor     edx, edx; HeapInformationClass
0x18000238a  call    cs:__imp_HeapSetInformation
0x180002390  mov     eax, 1
0x180002395  add     rsp, 28h
0x180002399  retn
```
