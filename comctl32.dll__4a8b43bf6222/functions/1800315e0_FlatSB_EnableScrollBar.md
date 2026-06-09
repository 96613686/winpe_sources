# FlatSB_EnableScrollBar

- ea: `0x1800315e0`
- end: `0x1800316a1`
- name: `FlatSB_EnableScrollBar`
- size: `193`
- prototype: `BOOL __stdcall(HWND, int, UINT)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180030440`
- `0x180030800`
- `0x1800315e0`
- `0x180032d6c`
- `0x1800330c4`

## import_xrefs

- `GDI32!DeleteObject` at `0x180031662`
- `GDI32!DeleteObject` at `0x18003166f`
- `GDI32!DeleteObject` at `0x180031662`
- `GDI32!DeleteObject` at `0x18003166f`
- `KERNEL32!LocalFree` at `0x180031678`
- `KERNEL32!LocalFree` at `0x180031678`
- `USER32!EnableScrollBar` at `0x180031620`
- `USER32!EnableScrollBar` at `0x180031620`

## pseudocode

```c
BOOL __stdcall FlatSB_EnableScrollBar(HWND a1, int a2, UINT a3)
{
  HGDIOBJ *v6; // rbx
  char *inited; // rax
  DWORD_PTR pdwRefData; // [rsp+68h] [rbp+20h] BYREF

  pdwRefData = 0;
  GetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, &pdwRefData);
  v6 = (HGDIOBJ *)pdwRefData;
  if ( !pdwRefData )
    return EnableScrollBar(a1, a2, a3);
  if ( pdwRefData == -1 )
  {
    if ( !a3 )
      return 0;
    inited = FlatSB_Internal_InitPwSB((__int64)a1);
    v6 = (HGDIOBJ *)inited;
    if ( !inited )
      return 0;
    if ( !SetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, (DWORD_PTR)inited) )
    {
      DeleteObject(v6[31]);
      DeleteObject(v6[30]);
      LocalFree(v6);
      return 0;
    }
  }
  else if ( a1 != *(HWND *)(pdwRefData + 264) )
  {
    return 0;
  }
  return FlatSB_Internal_EnableScrollBar(v6, (unsigned int)a2, a3);
}

```

## disassembly

```asm
0x1800315e0  push    rbx
0x1800315e2  push    rbp
0x1800315e3  push    rsi
0x1800315e4  push    rdi
0x1800315e5  sub     rsp, 28h
0x1800315e9  mov     esi, r8d
0x1800315ec  mov     [rsp+48h+pdwRefData], 0
0x1800315f5  mov     ebp, edx
0x1800315f7  lea     r9, [rsp+48h+pdwRefData]; pdwRefData
0x1800315fc  xor     r8d, r8d; uIdSubclass
0x1800315ff  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x180031606  mov     rdi, rcx
0x180031609  call    GetWindowSubclass
0x18003160e  mov     rbx, [rsp+48h+pdwRefData]
0x180031613  test    rbx, rbx
0x180031616  jnz     short loc_180031628
0x180031618  mov     r8d, esi; wArrows
0x18003161b  mov     edx, ebp; wSBflags
0x18003161d  mov     rcx, rdi; hWnd
0x180031620  call    cs:__imp_EnableScrollBar
0x180031626  jmp     short loc_180031698
0x180031628  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003162c  jnz     short loc_180031682
0x18003162e  test    esi, esi
0x180031630  jz      short loc_18003167E
0x180031632  mov     rcx, rdi
0x180031635  call    FlatSB_Internal_InitPwSB
0x18003163a  mov     rbx, rax
0x18003163d  test    rax, rax
0x180031640  jz      short loc_18003167E
0x180031642  mov     r9, rax; dwRefData
0x180031645  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x18003164c  xor     r8d, r8d; uIdSubclass
0x18003164f  mov     rcx, rdi; hWnd
0x180031652  call    SetWindowSubclass
0x180031657  test    eax, eax
0x180031659  jnz     short loc_18003168B
0x18003165b  mov     rcx, [rbx+0F8h]; ho
0x180031662  call    cs:__imp_DeleteObject
0x180031668  mov     rcx, [rbx+0F0h]; ho
0x18003166f  call    cs:__imp_DeleteObject
0x180031675  mov     rcx, rbx; hMem
0x180031678  call    cs:__imp_LocalFree
0x18003167e  xor     eax, eax
0x180031680  jmp     short loc_180031698
0x180031682  cmp     rdi, [rbx+108h]
0x180031689  jnz     short loc_18003167E
0x18003168b  mov     r8d, esi
0x18003168e  mov     edx, ebp
0x180031690  mov     rcx, rbx
0x180031693  call    FlatSB_Internal_EnableScrollBar
0x180031698  add     rsp, 28h
0x18003169c  pop     rdi
0x18003169d  pop     rsi
0x18003169e  pop     rbp
0x18003169f  pop     rbx
0x1800316a0  retn
```
