# FlatSB_ShowScrollBar

- ea: `0x1800349c0`
- end: `0x180034ae3`
- name: `FlatSB_ShowScrollBar`
- size: `291`
- prototype: `BOOL __stdcall(HWND, int code, BOOL)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005b7fc`

## callees

- `0x180018090`
- `0x180030440`
- `0x180030800`
- `0x1800330c4`
- `0x1800349c0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180034a74`
- `GDI32!DeleteObject` at `0x180034a81`
- `GDI32!DeleteObject` at `0x180034a74`
- `GDI32!DeleteObject` at `0x180034a81`
- `KERNEL32!LocalFree` at `0x180034a8a`
- `KERNEL32!LocalFree` at `0x180034a8a`
- `USER32!ShowScrollBar` at `0x180034a0a`
- `USER32!ShowScrollBar` at `0x180034abd`
- `USER32!ShowScrollBar` at `0x180034a0a`
- `USER32!ShowScrollBar` at `0x180034abd`

## pseudocode

```c
BOOL __stdcall FlatSB_ShowScrollBar(HWND a1, int code, BOOL a3)
{
  DWORD_PTR v6; // rdi
  int v8; // ebx
  char *inited; // rax
  DWORD_PTR v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  GetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, &v10);
  v6 = v10;
  if ( !v10 )
    return ShowScrollBar(a1, code, a3);
  if ( code )
  {
    if ( code == 1 )
    {
      v8 = 0x200000;
    }
    else
    {
      if ( code != 3 )
        return 0;
      v8 = 3145728;
    }
  }
  else
  {
    v8 = 0x100000;
  }
  if ( v10 == -1 )
  {
    if ( !a3 )
      return 0;
    inited = FlatSB_Internal_InitPwSB((__int64)a1);
    v6 = (DWORD_PTR)inited;
    if ( !inited )
      return 0;
    if ( !SetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, (DWORD_PTR)inited) )
    {
      DeleteObject(*(HGDIOBJ *)(v6 + 248));
      DeleteObject(*(HGDIOBJ *)(v6 + 240));
      LocalFree((HLOCAL)v6);
      return 0;
    }
LABEL_18:
    if ( (v8 & *(_DWORD *)(v6 + 8)) != v8 )
    {
      *(_DWORD *)(v6 + 8) |= v8;
      goto LABEL_20;
    }
    return 1;
  }
  if ( a3 )
    goto LABEL_18;
  if ( (v8 & *(_DWORD *)(v10 + 8)) != 0 )
  {
    *(_DWORD *)(v10 + 8) &= ~v8;
LABEL_20:
    ShowScrollBar(a1, code, a3);
    CCInvalidateFrame(a1);
  }
  return 1;
}

```

## disassembly

```asm
0x1800349c0  mov     rax, rsp
0x1800349c3  mov     [rax+8], rbx
0x1800349c7  mov     [rax+10h], rbp
0x1800349cb  push    rsi
0x1800349cc  push    rdi
0x1800349cd  push    r14
0x1800349cf  sub     rsp, 20h
0x1800349d3  mov     ebp, r8d
0x1800349d6  mov     qword ptr [rax+20h], 0
0x1800349de  mov     r14d, edx
0x1800349e1  lea     r9, [rax+20h]; pdwRefData
0x1800349e5  xor     r8d, r8d; uIdSubclass
0x1800349e8  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x1800349ef  mov     rsi, rcx
0x1800349f2  call    GetWindowSubclass
0x1800349f7  mov     rdi, [rsp+38h+arg_18]
0x1800349fc  test    rdi, rdi
0x1800349ff  jnz     short loc_180034A15
0x180034a01  mov     r8d, ebp; bShow
0x180034a04  mov     edx, r14d; wBar
0x180034a07  mov     rcx, rsi; hWnd
0x180034a0a  call    cs:__imp_ShowScrollBar
0x180034a10  jmp     loc_180034AD0
0x180034a15  mov     ecx, r14d
0x180034a18  test    r14d, r14d
0x180034a1b  jz      short loc_180034A35
0x180034a1d  sub     ecx, 1
0x180034a20  jz      short loc_180034A2E
0x180034a22  cmp     ecx, 2
0x180034a25  jnz     short loc_180034A90
0x180034a27  mov     ebx, 300000h
0x180034a2c  jmp     short loc_180034A3A
0x180034a2e  mov     ebx, 200000h
0x180034a33  jmp     short loc_180034A3A
0x180034a35  mov     ebx, 100000h
0x180034a3a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180034a3e  jnz     short loc_180034A94
0x180034a40  test    ebp, ebp
0x180034a42  jz      short loc_180034A90
0x180034a44  mov     rcx, rsi
0x180034a47  call    FlatSB_Internal_InitPwSB
0x180034a4c  mov     rdi, rax
0x180034a4f  test    rax, rax
0x180034a52  jz      short loc_180034A90
0x180034a54  mov     r9, rax; dwRefData
0x180034a57  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x180034a5e  xor     r8d, r8d; uIdSubclass
0x180034a61  mov     rcx, rsi; hWnd
0x180034a64  call    SetWindowSubclass
0x180034a69  test    eax, eax
0x180034a6b  jnz     short loc_180034AA4
0x180034a6d  mov     rcx, [rdi+0F8h]; ho
0x180034a74  call    cs:__imp_DeleteObject
0x180034a7a  mov     rcx, [rdi+0F0h]; ho
0x180034a81  call    cs:__imp_DeleteObject
0x180034a87  mov     rcx, rdi; hMem
0x180034a8a  call    cs:__imp_LocalFree
0x180034a90  xor     eax, eax
0x180034a92  jmp     short loc_180034AD0
0x180034a94  test    ebp, ebp
0x180034a96  jnz     short loc_180034AA4
0x180034a98  test    [rdi+8], ebx
0x180034a9b  jz      short loc_180034ACB
0x180034a9d  not     ebx
0x180034a9f  and     [rdi+8], ebx
0x180034aa2  jmp     short loc_180034AB4
0x180034aa4  mov     ecx, [rdi+8]
0x180034aa7  mov     eax, ecx
0x180034aa9  and     eax, ebx
0x180034aab  cmp     eax, ebx
0x180034aad  jz      short loc_180034ACB
0x180034aaf  or      ecx, ebx
0x180034ab1  mov     [rdi+8], ecx
0x180034ab4  mov     r8d, ebp; bShow
0x180034ab7  mov     edx, r14d; wBar
0x180034aba  mov     rcx, rsi; hWnd
0x180034abd  call    cs:__imp_ShowScrollBar
0x180034ac3  mov     rcx, rsi
0x180034ac6  call    CCInvalidateFrame
0x180034acb  mov     eax, 1
0x180034ad0  mov     rbx, [rsp+38h+arg_0]
0x180034ad5  mov     rbp, [rsp+38h+arg_8]
0x180034ada  add     rsp, 20h
0x180034ade  pop     r14
0x180034ae0  pop     rdi
0x180034ae1  pop     rsi
0x180034ae2  retn
```
