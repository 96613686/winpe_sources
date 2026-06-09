# CCopyableTextListViewCtrl::_ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x180025ecc`
- end: `0x180025fda`
- name: `?_ProcessWindowMessage@CCopyableTextListViewCtrl@@QEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `270`
- prototype: `__int64 __usercall@<rax>(CCopyableTextListViewCtrl *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64, __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800255a0`

## callees

- `0x180023584`
- `0x180025ecc`

## import_xrefs

- `USER32!GetKeyState` at `0x180025efb`
- `USER32!GetKeyState` at `0x180025f09`
- `USER32!GetKeyState` at `0x180025f17`
- `USER32!GetKeyState` at `0x180025f70`
- `USER32!GetKeyState` at `0x180025f80`
- `USER32!GetKeyState` at `0x180025f90`
- `USER32!GetKeyState` at `0x180025efb`
- `USER32!GetKeyState` at `0x180025f09`
- `USER32!GetKeyState` at `0x180025f17`
- `USER32!GetKeyState` at `0x180025f70`
- `USER32!GetKeyState` at `0x180025f80`
- `USER32!GetKeyState` at `0x180025f90`
- `USER32!SendMessageA` at `0x180025f31`
- `USER32!SendMessageA` at `0x180025faa`
- `USER32!SendMessageA` at `0x180025f31`
- `USER32!SendMessageA` at `0x180025faa`

## pseudocode

```c
_BOOL8 __fastcall CCopyableTextListViewCtrl::_ProcessWindowMessage(
        CCopyableTextListViewCtrl *this,
        HWND a2,
        int a3,
        __int16 a4,
        __int64 a5,
        __int64 *a6,
        unsigned int a7)
{
  int v8; // eax
  int v10; // eax

  if ( a7 )
    return 0;
  if ( a3 == 258 )
  {
    *((_DWORD *)this + 18) = 0;
    if ( a4 == 3 && GetKeyState(17) < 0 && GetKeyState(18) >= 0 && GetKeyState(16) >= 0 )
    {
      v8 = SendMessageA(*((HWND *)this + 1), 0x1042u, 0, 0);
      CCopyableTextListViewCtrl::CopyItemToClipboard((HWND *)this, v8);
    }
    *a6 = 0;
    return *((_DWORD *)this + 18) != 0;
  }
  if ( a3 != 256 )
    return 0;
  *((_DWORD *)this + 18) = 0;
  if ( a4 == 45 && GetKeyState(17) < 0 && GetKeyState(18) >= 0 && GetKeyState(16) >= 0 )
  {
    v10 = SendMessageA(*((HWND *)this + 1), 0x1042u, 0, 0);
    CCopyableTextListViewCtrl::CopyItemToClipboard((HWND *)this, v10);
  }
  *a6 = 0;
  return *((_DWORD *)this + 18) != 0;
}

```

## disassembly

```asm
0x180025ecc  mov     [rsp+arg_0], rbx
0x180025ed1  push    rdi
0x180025ed2  sub     rsp, 20h
0x180025ed6  xor     edi, edi
0x180025ed8  mov     rbx, rcx
0x180025edb  cmp     [rsp+28h+arg_30], edi
0x180025edf  jnz     loc_180025FCD
0x180025ee5  cmp     r8d, 102h
0x180025eec  jnz     short loc_180025F56
0x180025eee  mov     [rcx+48h], edi
0x180025ef1  cmp     r9w, 3
0x180025ef6  jnz     short loc_180025F42
0x180025ef8  lea     ecx, [rdi+11h]; nVirtKey
0x180025efb  call    cs:__imp_GetKeyState
0x180025f01  test    ax, ax
0x180025f04  jns     short loc_180025F42
0x180025f06  lea     ecx, [rdi+12h]; nVirtKey
0x180025f09  call    cs:__imp_GetKeyState
0x180025f0f  test    ax, ax
0x180025f12  js      short loc_180025F42
0x180025f14  lea     ecx, [rdi+10h]; nVirtKey
0x180025f17  call    cs:__imp_GetKeyState
0x180025f1d  test    ax, ax
0x180025f20  js      short loc_180025F42
0x180025f22  mov     rcx, [rbx+8]; hWnd
0x180025f26  xor     r9d, r9d; lParam
0x180025f29  xor     r8d, r8d; wParam
0x180025f2c  mov     edx, 1042h; Msg
0x180025f31  call    cs:__imp_SendMessageA
0x180025f37  mov     rdx, rax; int
0x180025f3a  mov     rcx, rbx; this
0x180025f3d  call    ?CopyItemToClipboard@CCopyableTextListViewCtrl@@QEAAXH@Z; CCopyableTextListViewCtrl::CopyItemToClipboard(int)
0x180025f42  mov     rax, [rsp+28h+arg_28]
0x180025f47  mov     [rax], rdi
0x180025f4a  cmp     [rbx+48h], edi
0x180025f4d  jz      short loc_180025FCD
0x180025f4f  mov     eax, 1
0x180025f54  jmp     short loc_180025FCF
0x180025f56  cmp     r8d, 100h
0x180025f5d  jnz     short loc_180025FCD
0x180025f5f  mov     eax, 2Dh ; '-'
0x180025f64  mov     [rcx+48h], edi
0x180025f67  cmp     ax, r9w
0x180025f6b  jnz     short loc_180025FBB
0x180025f6d  lea     ecx, [rax-1Ch]; nVirtKey
0x180025f70  call    cs:__imp_GetKeyState
0x180025f76  test    ax, ax
0x180025f79  jns     short loc_180025FBB
0x180025f7b  mov     ecx, 12h; nVirtKey
0x180025f80  call    cs:__imp_GetKeyState
0x180025f86  test    ax, ax
0x180025f89  js      short loc_180025FBB
0x180025f8b  mov     ecx, 10h; nVirtKey
0x180025f90  call    cs:__imp_GetKeyState
0x180025f96  test    ax, ax
0x180025f99  js      short loc_180025FBB
0x180025f9b  mov     rcx, [rbx+8]; hWnd
0x180025f9f  xor     r9d, r9d; lParam
0x180025fa2  xor     r8d, r8d; wParam
0x180025fa5  mov     edx, 1042h; Msg
0x180025faa  call    cs:__imp_SendMessageA
0x180025fb0  mov     rdx, rax; int
0x180025fb3  mov     rcx, rbx; this
0x180025fb6  call    ?CopyItemToClipboard@CCopyableTextListViewCtrl@@QEAAXH@Z; CCopyableTextListViewCtrl::CopyItemToClipboard(int)
0x180025fbb  mov     rax, [rsp+28h+arg_28]
0x180025fc0  mov     [rax], rdi
0x180025fc3  mov     eax, edi
0x180025fc5  cmp     [rbx+48h], edi
0x180025fc8  setnz   al
0x180025fcb  jmp     short loc_180025FCF
0x180025fcd  xor     eax, eax
0x180025fcf  mov     rbx, [rsp+28h+arg_0]
0x180025fd4  add     rsp, 20h
0x180025fd8  pop     rdi
0x180025fd9  retn
```
