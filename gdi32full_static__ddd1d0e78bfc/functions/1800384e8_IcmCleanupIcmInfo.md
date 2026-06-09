# IcmCleanupIcmInfo

- ea: `0x1800384e8`
- end: `0x1800385c2`
- name: `IcmCleanupIcmInfo`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800383a0`
- `0x18008e67c`

## callees

- `0x18002e130`
- `0x1800384e8`
- `0x1800385c8`
- `0x1800386a8`
- `0x180038b7c`
- `0x180038be8`
- `0x180038c70`

## import_xrefs

- `GDI32!ghICM` at `0x1800384f2`
- `GDI32!ghICM` at `0x180038520`
- `win32u!NtGdiDeleteColorSpace` at `0x1800385a9`
- `win32u!NtGdiDeleteColorSpace` at `0x1800385a9`
- `win32u!NtGdiSetColorSpace` at `0x180038593`
- `win32u!NtGdiSetColorSpace` at `0x180038593`

## pseudocode

```c
__int64 __fastcall IcmCleanupIcmInfo(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax
  HGDIOBJ StockObject; // rax

  if ( ghICM )
    IcmRestoreDC(a1, 1, a2);
  v4 = *(_QWORD *)(a2 + 88);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( a1 && v4 == *(_QWORD *)(a1 + 16) )
    {
      StockObject = GetStockObject(20);
      NtGdiSetColorSpace(*(_QWORD *)(a2 + 16), StockObject);
    }
    if ( (*(_BYTE *)(a2 + 32) & 4) != 0 )
      NtGdiDeleteColorSpace(*(_QWORD *)(a2 + 88));
    *(_QWORD *)(a2 + 88) = 0;
  }
  if ( ghICM )
  {
    IcmDeleteDCColorTransforms(a2);
    IcmDeleteCachedColorTransforms(*(_QWORD *)(a2 + 16));
    IcmReleaseDCColorSpace(a2);
    IcmReleaseCachedColorSpace(*(PVOID *)(a2 + 16));
  }
  *(_QWORD *)(a2 + 16) = 0;
  result = 1;
  *(_QWORD *)(a2 + 24) = 0;
  *(_DWORD *)(a2 + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x1800384e8  mov     [rsp+arg_0], rbx
0x1800384ed  push    rdi
0x1800384ee  sub     rsp, 20h
0x1800384f2  mov     rax, cs:__imp_ghICM
0x1800384f9  mov     rbx, rdx
0x1800384fc  mov     rdi, rcx
0x1800384ff  cmp     qword ptr [rax], 0
0x180038503  jz      short loc_180038512
0x180038505  mov     r8, rdx
0x180038508  mov     edx, 1
0x18003850d  call    IcmRestoreDC
0x180038512  mov     rcx, [rbx+58h]
0x180038516  lea     rax, [rcx-1]
0x18003851a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003851e  jbe     short loc_180038577
0x180038520  mov     rax, cs:__imp_ghICM
0x180038527  cmp     qword ptr [rax], 0
0x18003852b  jz      short loc_18003854F
0x18003852d  mov     rcx, rbx
0x180038530  call    IcmDeleteDCColorTransforms
0x180038535  mov     rcx, [rbx+10h]
0x180038539  call    IcmDeleteCachedColorTransforms
0x18003853e  mov     rcx, rbx
0x180038541  call    IcmReleaseDCColorSpace
0x180038546  mov     rcx, [rbx+10h]
0x18003854a  call    IcmReleaseCachedColorSpace
0x18003854f  mov     qword ptr [rbx+10h], 0
0x180038557  mov     eax, 1
0x18003855c  mov     qword ptr [rbx+18h], 0
0x180038564  mov     dword ptr [rbx+20h], 0
0x18003856b  mov     rbx, [rsp+28h+arg_0]
0x180038570  add     rsp, 20h
0x180038574  pop     rdi
0x180038575  retn
0x180038577  test    rdi, rdi
0x18003857a  jz      short loc_18003859F
0x18003857c  cmp     rcx, [rdi+10h]
0x180038580  jnz     short loc_18003859F
0x180038582  mov     ecx, 14h; i
0x180038587  call    GetStockObject
0x18003858c  mov     rcx, [rbx+10h]
0x180038590  mov     rdx, rax
0x180038593  call    cs:__imp_NtGdiSetColorSpace
0x18003859a  nop     dword ptr [rax+rax+00h]
0x18003859f  test    byte ptr [rbx+20h], 4
0x1800385a3  jz      short loc_1800385B5
0x1800385a5  mov     rcx, [rbx+58h]
0x1800385a9  call    cs:__imp_NtGdiDeleteColorSpace
0x1800385b0  nop     dword ptr [rax+rax+00h]
0x1800385b5  mov     qword ptr [rbx+58h], 0
0x1800385bd  jmp     loc_180038520
```
