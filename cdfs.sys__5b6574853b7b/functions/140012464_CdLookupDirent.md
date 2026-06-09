# CdLookupDirent

- ea: `0x140012464`
- end: `0x140012500`
- name: `CdLookupDirent`
- size: `156`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64 Buffer)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b1a4`
- `0x14000b684`
- `0x14000dc38`
- `0x140011138`
- `0x1400120cc`
- `0x140012198`
- `0x14001233c`
- `0x1400135d0`

## callees

- `0x140011fd4`
- `0x140012464`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x1400124da`
- `ntoskrnl!CcMapData` at `0x1400124da`

## pseudocode

```c
__int64 __fastcall CdLookupDirent(__int64 a1, __int64 a2, int a3, __int64 Buffer)
{
  ULONG v5; // r10d
  union _LARGE_INTEGER v6; // rdx
  __int64 v9; // rax
  ULONG v10; // eax
  __int64 result; // rax
  union _LARGE_INTEGER FileOffset; // [rsp+48h] [rbp+10h] BYREF

  v5 = 2048;
  *(_DWORD *)(Buffer + 12) = 2048;
  v6.QuadPart = a3 & 0xFFFFF800;
  *(_DWORD *)(Buffer + 8) = v6.LowPart;
  *(_DWORD *)(Buffer + 24) = a3 & 0x7FF;
  v9 = *(_QWORD *)(a2 + 32) - v6.QuadPart;
  FileOffset = v6;
  if ( v9 < 2048 )
  {
    v10 = *(_DWORD *)(a2 + 32) - v6.LowPart;
    *(_DWORD *)(Buffer + 12) = v10;
    v5 = v10;
  }
  CcMapData(*(PFILE_OBJECT *)(a2 + 472), &FileOffset, v5, 1u, (PVOID *)(Buffer + 16), (PVOID *)Buffer);
  result = CdCheckRawDirentBounds(a1, (__int64 *)Buffer);
  *(_DWORD *)(Buffer + 28) = result;
  return result;
}

```

## disassembly

```asm
0x140012464  mov     [rsp+arg_0], rbx
0x140012469  push    rdi
0x14001246a  sub     rsp, 30h
0x14001246e  mov     r11, rdx
0x140012471  mov     r10d, 800h
0x140012477  mov     edx, r8d
0x14001247a  mov     [r9+0Ch], r10d
0x14001247e  and     edx, 0FFFFF800h
0x140012484  and     r8d, 7FFh
0x14001248b  mov     [r9+8], edx
0x14001248f  mov     rbx, r9
0x140012492  mov     [r9+18h], r8d
0x140012496  mov     rdi, rcx
0x140012499  mov     rax, [r11+20h]
0x14001249d  sub     rax, rdx
0x1400124a0  mov     qword ptr [rsp+38h+FileOffset], rdx
0x1400124a5  cmp     rax, r10
0x1400124a8  jge     short loc_1400124B7
0x1400124aa  mov     eax, [r11+20h]
0x1400124ae  sub     eax, edx
0x1400124b0  mov     [r9+0Ch], eax
0x1400124b4  mov     r10d, eax
0x1400124b7  mov     rcx, [r11+1D8h]; FileObject
0x1400124be  lea     rax, [r9+10h]
0x1400124c2  mov     r9d, 1; Flags
0x1400124c8  mov     [rsp+38h+Buffer], rbx; Buffer
0x1400124cd  mov     r8d, r10d; Length
0x1400124d0  mov     [rsp+38h+Bcb], rax; Bcb
0x1400124d5  lea     rdx, [rsp+38h+FileOffset]; FileOffset
0x1400124da  call    cs:__imp_CcMapData
0x1400124e1  nop     dword ptr [rax+rax+00h]
0x1400124e6  mov     rdx, rbx
0x1400124e9  mov     rcx, rdi
0x1400124ec  call    CdCheckRawDirentBounds
0x1400124f1  mov     [rbx+1Ch], eax
0x1400124f4  mov     rbx, [rsp+38h+arg_0]
0x1400124f9  add     rsp, 30h
0x1400124fd  pop     rdi
0x1400124fe  retn
```
