# GetEmf(IStream *,int,uint)

- ea: `0x1800d8740`
- end: `0x1800d8848`
- name: `?GetEmf@@YAPEAUHENHMETAFILE__@@PEAUIStream@@HI@Z`
- size: `264`
- prototype: `HENHMETAFILE __fastcall(struct IStream *, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b8c0`
- `0x18010c470`

## callees

- `0x1800d8740`
- `0x1800e73b8`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800d8790`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800d8790`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800d8768`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800d8768`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800d881f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800d881f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800d87c3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800d87c3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800d87fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800d87fd`
- `GDI32!SetMetaFileBitsEx` at `0x1800d87dd`
- `GDI32!SetMetaFileBitsEx` at `0x1800d87dd`
- `GDI32!SetEnhMetaFileBits` at `0x1800d87eb`
- `GDI32!SetEnhMetaFileBits` at `0x1800d87eb`

## pseudocode

```c
HENHMETAFILE __fastcall GetEmf(struct IStream *a1, int a2, unsigned int a3)
{
  __int64 v4; // rsi
  void *v6; // rbx
  HGLOBAL v7; // rax
  void *v8; // rdi
  const BYTE *v9; // rax
  void *v10; // rax
  __int64 v12[5]; // [rsp+20h] [rbp-28h] BYREF
  LPSTREAM ppstm; // [rsp+68h] [rbp+20h] BYREF

  v4 = a3;
  v6 = 0;
  v7 = GlobalAlloc(0x22u, a3);
  v8 = v7;
  if ( v7 )
  {
    ppstm = 0;
    if ( CreateStreamOnHGlobal(v7, 1, &ppstm) >= 0 && ppstm )
    {
      v12[0] = v4;
      if ( (unsigned int)CopyStream(a1, ppstm, v12) )
      {
        v9 = (const BYTE *)GlobalLock(v8);
        if ( v9 )
        {
          if ( a2 )
            v10 = SetMetaFileBitsEx(v4, v9);
          else
            v10 = SetEnhMetaFileBits(v4, v9);
          v6 = v10;
        }
        GlobalUnlock(v8);
      }
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    }
    else
    {
      GlobalFree(v8);
    }
  }
  return (HENHMETAFILE)v6;
}

```

## disassembly

```asm
0x1800d8740  mov     [rsp+arg_0], rbx
0x1800d8745  mov     [rsp+arg_8], rbp
0x1800d874a  mov     [rsp+arg_10], rsi
0x1800d874f  push    rdi
0x1800d8750  push    r14
0x1800d8752  push    r15
0x1800d8754  sub     rsp, 30h
0x1800d8758  mov     ebp, edx
0x1800d875a  mov     esi, r8d
0x1800d875d  mov     r15, rcx
0x1800d8760  mov     edx, r8d; dwBytes
0x1800d8763  xor     ebx, ebx
0x1800d8765  lea     ecx, [rbx+22h]; uFlags
0x1800d8768  call    cs:__imp_GlobalAlloc
0x1800d876f  nop     dword ptr [rax+rax+00h]
0x1800d8774  mov     rdi, rax
0x1800d8777  test    rax, rax
0x1800d877a  jz      loc_1800D882B
0x1800d8780  lea     r8, [rsp+48h+ppstm]; ppstm
0x1800d8785  mov     [rsp+48h+ppstm], rbx
0x1800d878a  lea     edx, [rbx+1]; fDeleteOnRelease
0x1800d878d  mov     rcx, rax; hGlobal
0x1800d8790  call    cs:__imp_CreateStreamOnHGlobal
0x1800d8797  nop     dword ptr [rax+rax+00h]
0x1800d879c  test    eax, eax
0x1800d879e  js      short loc_1800D881C
0x1800d87a0  mov     rdx, [rsp+48h+ppstm]; struct IStream *
0x1800d87a5  test    rdx, rdx
0x1800d87a8  jz      short loc_1800D881C
0x1800d87aa  lea     r8, [rsp+48h+var_28]; __int64 *
0x1800d87af  mov     [rsp+48h+var_28], rsi
0x1800d87b4  mov     rcx, r15; struct IStream *
0x1800d87b7  call    ?CopyStream@@YAHPEAUIStream@@0AEB_J@Z; CopyStream(IStream *,IStream *,__int64 const &)
0x1800d87bc  test    eax, eax
0x1800d87be  jz      short loc_1800D8809
0x1800d87c0  mov     rcx, rdi; hMem
0x1800d87c3  call    cs:__imp_GlobalLock
0x1800d87ca  nop     dword ptr [rax+rax+00h]
0x1800d87cf  test    rax, rax
0x1800d87d2  jz      short loc_1800D87FA
0x1800d87d4  mov     rdx, rax; pb
0x1800d87d7  mov     ecx, esi; nSize
0x1800d87d9  test    ebp, ebp
0x1800d87db  jz      short loc_1800D87EB
0x1800d87dd  call    cs:__imp_SetMetaFileBitsEx
0x1800d87e4  nop     dword ptr [rax+rax+00h]
0x1800d87e9  jmp     short loc_1800D87F7
0x1800d87eb  call    cs:__imp_SetEnhMetaFileBits
0x1800d87f2  nop     dword ptr [rax+rax+00h]
0x1800d87f7  mov     rbx, rax
0x1800d87fa  mov     rcx, rdi; hMem
0x1800d87fd  call    cs:__imp_GlobalUnlock
0x1800d8804  nop     dword ptr [rax+rax+00h]
0x1800d8809  mov     rcx, [rsp+48h+ppstm]
0x1800d880e  mov     rax, [rcx]
0x1800d8811  mov     rax, [rax+10h]
0x1800d8815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d881a  jmp     short loc_1800D882B
0x1800d881c  mov     rcx, rdi; hMem
0x1800d881f  call    cs:__imp_GlobalFree
0x1800d8826  nop     dword ptr [rax+rax+00h]
0x1800d882b  mov     rbp, [rsp+48h+arg_8]
0x1800d8830  mov     rax, rbx
0x1800d8833  mov     rbx, [rsp+48h+arg_0]
0x1800d8838  mov     rsi, [rsp+48h+arg_10]
0x1800d883d  add     rsp, 30h
0x1800d8841  pop     r15
0x1800d8843  pop     r14
0x1800d8845  pop     rdi
0x1800d8846  retn
```
