# DrawDibFree

- ea: `0x18000a860`
- end: `0x18000aac2`
- name: `DrawDibFree`
- size: `610`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008400`
- `0x180009b30`
- `0x18000a830`

## callees

- `0x180002640`
- `0x180003a60`
- `0x18000a860`
- `0x18000dae0`
- `0x18000e17c`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000a8c2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000a9cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000aa03`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000aa3a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000a8c2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000a9cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000aa03`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000aa3a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000a8b9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000a8cf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000a9c3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000a9d6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000a9fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000aa10`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000aa31`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000aa44`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000a8b9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000a8cf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000a9c3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000a9d6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000a9fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000aa10`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000aa31`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000aa44`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a8d8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a9df`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000aa19`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000aa4d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a8d8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a9df`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000aa19`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000aa4d`
- `GDI32!DeleteObject` at `0x18000a890`
- `GDI32!DeleteObject` at `0x18000a89f`
- `GDI32!DeleteObject` at `0x18000a99e`
- `GDI32!DeleteObject` at `0x18000a890`
- `GDI32!DeleteObject` at `0x18000a89f`
- `GDI32!DeleteObject` at `0x18000a99e`
- `GDI32!DeleteDC` at `0x18000a98c`
- `GDI32!DeleteDC` at `0x18000a98c`
- `GDI32!SelectObject` at `0x18000a97f`
- `GDI32!SelectObject` at `0x18000a97f`

## pseudocode

```c
__int64 __fastcall DrawDibFree(__int64 a1, int a2, int a3)
{
  void *v7; // rcx
  void *v8; // rcx
  const void *v9; // rcx
  HGLOBAL v10; // rax
  HGLOBAL v11; // rax
  const void *v12; // rcx
  HIC v13; // rcx
  HDC v14; // rcx
  void *v15; // rcx
  const void *v16; // rcx
  HGLOBAL v17; // rax
  HGLOBAL v18; // rax
  const void *v19; // rcx
  HGLOBAL v20; // rax
  HGLOBAL v21; // rax
  const void *v22; // rcx
  HGLOBAL v23; // rax
  HGLOBAL v24; // rax

  if ( !a1 )
    return 0;
  if ( !a2 )
  {
    v7 = *(void **)(a1 + 32);
    if ( v7 )
      DeleteObject(v7);
    v8 = *(void **)(a1 + 40);
    if ( v8 )
      DeleteObject(v8);
    v9 = *(const void **)(a1 + 336);
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    if ( v9 )
    {
      v10 = GlobalHandle(v9);
      GlobalUnlock(v10);
      v11 = GlobalHandle(*(LPCVOID *)(a1 + 336));
      GlobalFree(v11);
      *(_QWORD *)(a1 + 336) = 0;
      *(_QWORD *)(a1 + 344) = 0;
    }
    v12 = *(const void **)(a1 + 320);
    if ( v12 )
    {
      DitherTerm(v12);
      *(_QWORD *)(a1 + 320) = 0;
    }
    v13 = *(HIC *)(a1 + 328);
    if ( (unsigned __int64)v13 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      ICSendMessage(v13, 0x400Eu, 0, 0);
      ICSendMessage(*(HIC *)(a1 + 328), 0x403Fu, 0, 0);
      ICClose(*(HIC *)(a1 + 328));
    }
    *(_DWORD *)(a1 + 4) &= ~0x100000u;
    *(_QWORD *)(a1 + 328) = 0;
    *(_QWORD *)(a1 + 68) = 0;
    *(_DWORD *)(a1 + 76) = 0;
  }
  if ( !a3 || !a2 )
  {
    v14 = *(HDC *)(a1 + 288);
    if ( v14 )
    {
      if ( h )
        SelectObject(v14, h);
      DeleteDC(*(HDC *)(a1 + 288));
    }
    v15 = *(void **)(a1 + 280);
    if ( v15 )
    {
      DeleteObject(v15);
      if ( (*(_DWORD *)(a1 + 4) & 0x200000) != 0 )
        *(_QWORD *)(a1 + 104) = 0;
    }
    v16 = *(const void **)(a1 + 104);
    if ( v16 && v16 != *(const void **)(a1 + 304) )
    {
      v17 = GlobalHandle(v16);
      GlobalUnlock(v17);
      v18 = GlobalHandle(*(LPCVOID *)(a1 + 104));
      GlobalFree(v18);
    }
    v19 = *(const void **)(a1 + 312);
    if ( v19 && v19 != *(const void **)(a1 + 304) )
    {
      v20 = GlobalHandle(v19);
      GlobalUnlock(v20);
      v21 = GlobalHandle(*(LPCVOID *)(a1 + 312));
      GlobalFree(v21);
    }
    v22 = *(const void **)(a1 + 96);
    if ( v22 && v22 != *(const void **)(a1 + 304) )
    {
      v23 = GlobalHandle(v22);
      GlobalUnlock(v23);
      v24 = GlobalHandle(*(LPCVOID *)(a1 + 96));
      GlobalFree(v24);
    }
    if ( *(_QWORD *)(a1 + 280) )
      SetBitmapEnd(a1 + 112);
    *(_DWORD *)(a1 + 4) &= 0x103FFFu;
    *(_DWORD *)(a1 + 4) |= 0x1000000u;
    *(_QWORD *)(a1 + 288) = 0;
    *(_QWORD *)(a1 + 280) = 0;
    *(_QWORD *)(a1 + 304) = 0;
    *(_QWORD *)(a1 + 104) = 0;
    *(_QWORD *)(a1 + 312) = 0;
    *(_QWORD *)(a1 + 96) = 0;
    *(_WORD *)(a1 + 1482) = 0;
    *(_QWORD *)(a1 + 1472) = 0;
    *(_WORD *)(a1 + 366) = 0;
    *(_QWORD *)(a1 + 356) = 0;
    *(_DWORD *)(a1 + 12) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000a860  push    rbx
0x18000a862  push    rbp
0x18000a863  push    rsi
0x18000a864  push    rdi
0x18000a865  sub     rsp, 28h
0x18000a869  xor     ebp, ebp
0x18000a86b  mov     esi, r8d
0x18000a86e  mov     edi, edx
0x18000a870  mov     rbx, rcx
0x18000a873  test    rcx, rcx
0x18000a876  jnz     short loc_18000A87F
0x18000a878  xor     eax, eax
0x18000a87a  jmp     loc_18000AAB9
0x18000a87f  test    edi, edi
0x18000a881  jnz     loc_18000A95B
0x18000a887  mov     rcx, [rcx+20h]; ho
0x18000a88b  test    rcx, rcx
0x18000a88e  jz      short loc_18000A896
0x18000a890  call    cs:__imp_DeleteObject
0x18000a896  mov     rcx, [rbx+28h]; ho
0x18000a89a  test    rcx, rcx
0x18000a89d  jz      short loc_18000A8A5
0x18000a89f  call    cs:__imp_DeleteObject
0x18000a8a5  mov     rcx, [rbx+150h]; pMem
0x18000a8ac  mov     [rbx+20h], rbp
0x18000a8b0  mov     [rbx+28h], rbp
0x18000a8b4  test    rcx, rcx
0x18000a8b7  jz      short loc_18000A8EC
0x18000a8b9  call    cs:__imp_GlobalHandle
0x18000a8bf  mov     rcx, rax; hMem
0x18000a8c2  call    cs:__imp_GlobalUnlock
0x18000a8c8  mov     rcx, [rbx+150h]; pMem
0x18000a8cf  call    cs:__imp_GlobalHandle
0x18000a8d5  mov     rcx, rax; hMem
0x18000a8d8  call    cs:__imp_GlobalFree
0x18000a8de  mov     [rbx+150h], rbp
0x18000a8e5  mov     [rbx+158h], rbp
0x18000a8ec  mov     rcx, [rbx+140h]; pMem
0x18000a8f3  test    rcx, rcx
0x18000a8f6  jz      short loc_18000A904
0x18000a8f8  call    DitherTerm
0x18000a8fd  mov     [rbx+140h], rbp
0x18000a904  mov     rcx, [rbx+148h]; hic
0x18000a90b  lea     rax, [rcx-1]
0x18000a90f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a913  ja      short loc_18000A948
0x18000a915  xor     r9d, r9d; dw2
0x18000a918  xor     r8d, r8d; dw1
0x18000a91b  mov     edx, 400Eh; msg
0x18000a920  call    ICSendMessage
0x18000a925  mov     rcx, [rbx+148h]; hic
0x18000a92c  xor     r9d, r9d; dw2
0x18000a92f  xor     r8d, r8d; dw1
0x18000a932  mov     edx, 403Fh; msg
0x18000a937  call    ICSendMessage
0x18000a93c  mov     rcx, [rbx+148h]; hic
0x18000a943  call    ICClose
0x18000a948  btr     dword ptr [rbx+4], 14h
0x18000a94d  mov     [rbx+148h], rbp
0x18000a954  mov     [rbx+44h], rbp
0x18000a958  mov     [rbx+4Ch], ebp
0x18000a95b  test    esi, esi
0x18000a95d  jz      short loc_18000A967
0x18000a95f  test    edi, edi
0x18000a961  jnz     loc_18000AAB4
0x18000a967  mov     rcx, [rbx+120h]; hdc
0x18000a96e  test    rcx, rcx
0x18000a971  jz      short loc_18000A992
0x18000a973  mov     rdx, cs:h; h
0x18000a97a  test    rdx, rdx
0x18000a97d  jz      short loc_18000A985
0x18000a97f  call    cs:__imp_SelectObject
0x18000a985  mov     rcx, [rbx+120h]; hdc
0x18000a98c  call    cs:__imp_DeleteDC
0x18000a992  mov     rcx, [rbx+118h]; ho
0x18000a999  test    rcx, rcx
0x18000a99c  jz      short loc_18000A9B1
0x18000a99e  call    cs:__imp_DeleteObject
0x18000a9a4  test    dword ptr [rbx+4], 200000h
0x18000a9ab  jz      short loc_18000A9B1
0x18000a9ad  mov     [rbx+68h], rbp
0x18000a9b1  mov     rcx, [rbx+68h]; pMem
0x18000a9b5  test    rcx, rcx
0x18000a9b8  jz      short loc_18000A9E5
0x18000a9ba  cmp     rcx, [rbx+130h]
0x18000a9c1  jz      short loc_18000A9E5
0x18000a9c3  call    cs:__imp_GlobalHandle
0x18000a9c9  mov     rcx, rax; hMem
0x18000a9cc  call    cs:__imp_GlobalUnlock
0x18000a9d2  mov     rcx, [rbx+68h]; pMem
0x18000a9d6  call    cs:__imp_GlobalHandle
0x18000a9dc  mov     rcx, rax; hMem
0x18000a9df  call    cs:__imp_GlobalFree
0x18000a9e5  mov     rcx, [rbx+138h]; pMem
0x18000a9ec  test    rcx, rcx
0x18000a9ef  jz      short loc_18000AA1F
0x18000a9f1  cmp     rcx, [rbx+130h]
0x18000a9f8  jz      short loc_18000AA1F
0x18000a9fa  call    cs:__imp_GlobalHandle
0x18000aa00  mov     rcx, rax; hMem
0x18000aa03  call    cs:__imp_GlobalUnlock
0x18000aa09  mov     rcx, [rbx+138h]; pMem
0x18000aa10  call    cs:__imp_GlobalHandle
0x18000aa16  mov     rcx, rax; hMem
0x18000aa19  call    cs:__imp_GlobalFree
0x18000aa1f  mov     rcx, [rbx+60h]; pMem
0x18000aa23  test    rcx, rcx
0x18000aa26  jz      short loc_18000AA53
0x18000aa28  cmp     rcx, [rbx+130h]
0x18000aa2f  jz      short loc_18000AA53
0x18000aa31  call    cs:__imp_GlobalHandle
0x18000aa37  mov     rcx, rax; hMem
0x18000aa3a  call    cs:__imp_GlobalUnlock
0x18000aa40  mov     rcx, [rbx+60h]; pMem
0x18000aa44  call    cs:__imp_GlobalHandle
0x18000aa4a  mov     rcx, rax; hMem
0x18000aa4d  call    cs:__imp_GlobalFree
0x18000aa53  cmp     [rbx+118h], rbp
0x18000aa5a  jz      short loc_18000AA65
0x18000aa5c  lea     rcx, [rbx+70h]
0x18000aa60  call    SetBitmapEnd
0x18000aa65  and     dword ptr [rbx+4], 103FFFh
0x18000aa6c  bts     dword ptr [rbx+4], 18h
0x18000aa71  mov     [rbx+120h], rbp
0x18000aa78  mov     [rbx+118h], rbp
0x18000aa7f  mov     [rbx+130h], rbp
0x18000aa86  mov     [rbx+68h], rbp
0x18000aa8a  mov     [rbx+138h], rbp
0x18000aa91  mov     [rbx+60h], rbp
0x18000aa95  mov     [rbx+5CAh], bp
0x18000aa9c  mov     [rbx+5C0h], rbp
0x18000aaa3  mov     [rbx+16Eh], bp
0x18000aaaa  mov     [rbx+164h], rbp
0x18000aab1  mov     [rbx+0Ch], ebp
0x18000aab4  mov     eax, 1
0x18000aab9  add     rsp, 28h
0x18000aabd  pop     rdi
0x18000aabe  pop     rsi
0x18000aabf  pop     rbp
0x18000aac0  pop     rbx
0x18000aac1  retn
```
