# IcmCleanupIcmInfo

- ea: `0x180032694`
- end: `0x180032761`
- name: `IcmCleanupIcmInfo`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180032570`
- `0x180089090`

## callees

- `0x180025090`
- `0x180032694`
- `0x180032768`
- `0x180032848`
- `0x180032cd0`
- `0x180032d38`
- `0x180032db0`

## import_xrefs

- `GDI32!ghICM` at `0x18003269e`
- `GDI32!ghICM` at `0x1800326cc`
- `win32u!NtGdiDeleteColorSpace` at `0x18003274e`
- `win32u!NtGdiDeleteColorSpace` at `0x18003274e`
- `win32u!NtGdiSetColorSpace` at `0x18003273e`
- `win32u!NtGdiSetColorSpace` at `0x18003273e`

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
0x180032694  mov     [rsp+arg_0], rbx
0x180032699  push    rdi
0x18003269a  sub     rsp, 20h
0x18003269e  mov     rax, cs:__imp_ghICM
0x1800326a5  mov     rbx, rdx
0x1800326a8  mov     rdi, rcx
0x1800326ab  cmp     qword ptr [rax], 0
0x1800326af  jz      short loc_1800326BE
0x1800326b1  mov     r8, rdx
0x1800326b4  mov     edx, 1
0x1800326b9  call    IcmRestoreDC
0x1800326be  mov     rcx, [rbx+58h]
0x1800326c2  lea     rax, [rcx-1]
0x1800326c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800326ca  jbe     short loc_180032722
0x1800326cc  mov     rax, cs:__imp_ghICM
0x1800326d3  cmp     qword ptr [rax], 0
0x1800326d7  jz      short loc_1800326FB
0x1800326d9  mov     rcx, rbx
0x1800326dc  call    IcmDeleteDCColorTransforms
0x1800326e1  mov     rcx, [rbx+10h]
0x1800326e5  call    IcmDeleteCachedColorTransforms
0x1800326ea  mov     rcx, rbx
0x1800326ed  call    IcmReleaseDCColorSpace
0x1800326f2  mov     rcx, [rbx+10h]
0x1800326f6  call    IcmReleaseCachedColorSpace
0x1800326fb  mov     qword ptr [rbx+10h], 0
0x180032703  mov     eax, 1
0x180032708  mov     qword ptr [rbx+18h], 0
0x180032710  mov     dword ptr [rbx+20h], 0
0x180032717  mov     rbx, [rsp+28h+arg_0]
0x18003271c  add     rsp, 20h
0x180032720  pop     rdi
0x180032721  retn
0x180032722  test    rdi, rdi
0x180032725  jz      short loc_180032744
0x180032727  cmp     rcx, [rdi+10h]
0x18003272b  jnz     short loc_180032744
0x18003272d  mov     ecx, 14h; i
0x180032732  call    GetStockObject
0x180032737  mov     rcx, [rbx+10h]
0x18003273b  mov     rdx, rax
0x18003273e  call    cs:__imp_NtGdiSetColorSpace
0x180032744  test    byte ptr [rbx+20h], 4
0x180032748  jz      short loc_180032754
0x18003274a  mov     rcx, [rbx+58h]
0x18003274e  call    cs:__imp_NtGdiDeleteColorSpace
0x180032754  mov     qword ptr [rbx+58h], 0
0x18003275c  jmp     loc_1800326CC
```
