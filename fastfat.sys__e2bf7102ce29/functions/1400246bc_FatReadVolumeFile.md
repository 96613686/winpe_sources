# FatReadVolumeFile

- ea: `0x1400246bc`
- end: `0x140024753`
- name: `FatReadVolumeFile`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400216f4`
- `0x140021ff8`
- `0x14003b698`
- `0x1400497f4`

## callees

- `0x1400246bc`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x140024727`
- `ntoskrnl!CcMapData` at `0x140024727`
- `ntoskrnl!ExRaiseStatus` at `0x1400246e4`
- `ntoskrnl!ExRaiseStatus` at `0x14002473f`
- `ntoskrnl!ExRaiseStatus` at `0x1400246e4`
- `ntoskrnl!ExRaiseStatus` at `0x14002473f`

## pseudocode

```c
BOOLEAN __fastcall FatReadVolumeFile(__int64 a1, __int64 a2, unsigned int a3, ULONG a4, PVOID *Bcb, PVOID *Buffer)
{
  unsigned int v8; // r9d
  struct _FILE_OBJECT *v9; // rcx
  BOOLEAN result; // al
  union _LARGE_INTEGER FileOffset; // [rsp+30h] [rbp-18h] BYREF

  if ( ((a3 ^ (a4 + a3 - 1)) & 0xFFFC0000) != 0 )
  {
    *(_DWORD *)(a1 + 72) = -1073741566;
    ExRaiseStatus(-1073741566);
  }
  v8 = *(_DWORD *)(a1 + 68);
  v9 = *(struct _FILE_OBJECT **)(a2 + 728);
  FileOffset.QuadPart = a3;
  result = CcMapData(v9, &FileOffset, a4, (v8 >> 1) & 1, Bcb, Buffer);
  if ( !result )
  {
    *(_DWORD *)(a1 + 72) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  return result;
}

```

## disassembly

```asm
0x1400246bc  push    rbx
0x1400246be  sub     rsp, 40h
0x1400246c2  lea     eax, [r8-1]
0x1400246c6  mov     r10d, r9d
0x1400246c9  add     eax, r9d
0x1400246cc  mov     r11, rdx
0x1400246cf  xor     eax, r8d
0x1400246d2  mov     rbx, rcx
0x1400246d5  test    eax, 0FFFC0000h
0x1400246da  jz      short loc_1400246F1
0x1400246dc  mov     ecx, 0C0000102h; Status
0x1400246e1  mov     [rbx+48h], ecx
0x1400246e4  call    cs:__imp_ExRaiseStatus
0x1400246f1  mov     r9d, [rcx+44h]
0x1400246f5  lea     rdx, [rsp+48h+FileOffset]; FileOffset
0x1400246fa  mov     rcx, [r11+2D8h]; FileObject
0x140024701  mov     eax, r8d
0x140024704  mov     r8d, r10d; Length
0x140024707  mov     qword ptr [rsp+48h+FileOffset], rax
0x14002470c  mov     rax, [rsp+48h+arg_28]
0x140024711  mov     [rsp+48h+Buffer], rax; Buffer
0x140024716  mov     rax, [rsp+48h+arg_20]
0x14002471b  shr     r9d, 1
0x14002471e  and     r9d, 1; Flags
0x140024722  mov     [rsp+48h+Bcb], rax; Bcb
0x140024727  call    cs:__imp_CcMapData
0x14002472e  nop     dword ptr [rax+rax+00h]
0x140024733  test    al, al
0x140024735  jnz     short loc_14002474C
0x140024737  mov     ecx, 0C00000D8h; Status
0x14002473c  mov     [rbx+48h], ecx
0x14002473f  call    cs:__imp_ExRaiseStatus
0x14002474c  add     rsp, 40h
0x140024750  pop     rbx
0x140024751  retn
```
