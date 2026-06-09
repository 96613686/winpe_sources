# CRichEdDoc::ShowContextMenu(HWND__ *,HWND__ *,int,int)

- ea: `0x1800656c4`
- end: `0x180065841`
- name: `?ShowContextMenu@CRichEdDoc@@AEAAJPEAUHWND__@@0HH@Z`
- size: `381`
- prototype: `int(CRichEdDoc *__hidden this, HWND, HWND, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180065a50`

## callees

- `0x180063b7c`
- `0x1800656c4`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `USER32!RemoveMenu` at `0x18006572c`
- `USER32!RemoveMenu` at `0x18006573d`
- `USER32!RemoveMenu` at `0x18006572c`
- `USER32!RemoveMenu` at `0x18006573d`
- `USER32!DestroyMenu` at `0x180065821`
- `USER32!DestroyMenu` at `0x180065821`
- `USER32!SendMessageA` at `0x18006577a`
- `USER32!SendMessageA` at `0x18006577a`
- `USER32!EnableMenuItem` at `0x18006574d`
- `USER32!EnableMenuItem` at `0x18006575d`
- `USER32!EnableMenuItem` at `0x18006579c`
- `USER32!EnableMenuItem` at `0x1800657ac`
- `USER32!EnableMenuItem` at `0x18006574d`
- `USER32!EnableMenuItem` at `0x18006575d`
- `USER32!EnableMenuItem` at `0x18006579c`
- `USER32!EnableMenuItem` at `0x1800657ac`
- `USER32!TrackPopupMenu` at `0x1800657dc`
- `USER32!TrackPopupMenu` at `0x1800657dc`
- `USER32!GetParent` at `0x1800657b5`
- `USER32!GetParent` at `0x1800657b5`

## pseudocode

```c
__int64 __fastcall CRichEdDoc::ShowContextMenu(CRichEdDoc *this, HWND a2, HWND a3, int a4, int y)
{
  unsigned int v8; // edi
  HMENU PopupMenu; // rax
  HMENU v10; // rbx
  HWND v11; // rcx
  int v12; // eax
  HWND hWnd; // rax
  int v14; // eax
  __int64 v15; // r8

  if ( !*((_QWORD *)this + 101) )
  {
    PopupMenu = LoadPopupMenu(2u);
    v10 = PopupMenu;
    if ( !PopupMenu )
      return (unsigned int)-2147467259;
    v8 = 0;
    RemoveMenu(PopupMenu, 0xDFu, 0);
    RemoveMenu(v10, 0xE0u, 0);
    EnableMenuItem(v10, 0x79u, 1u);
    EnableMenuItem(v10, 0x7Au, 1u);
    v11 = (HWND)*((_QWORD *)this + 92);
    if ( v11 )
    {
      v12 = SendMessageA(v11, 0xB0u, 0, 0);
      EnableMenuItem(v10, 0x66u, (_WORD)v12 == HIWORD(v12));
    }
    EnableMenuItem(v10, 0x69u, 0);
    hWnd = GetParent(a2);
    v14 = TrackPopupMenu(v10, 0x102u, a4, y, 0, hWnd, 0);
    if ( v14 )
    {
      if ( v14 == 102 )
      {
        v15 = 12;
        goto LABEL_12;
      }
      if ( v14 == 105 )
      {
        v15 = 17;
LABEL_12:
        (*(void (__fastcall **)(char *, _QWORD, __int64, _QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 4) + 280LL))(
          (char *)this + 32,
          0,
          v15,
          0,
          0,
          0);
      }
    }
    DestroyMenu(v10);
    return v8;
  }
  return (unsigned int)-2147024891;
}

```

## disassembly

```asm
0x1800656c4  push    rbx
0x1800656c6  push    rbp
0x1800656c7  push    rsi
0x1800656c8  push    rdi
0x1800656c9  push    r14
0x1800656cb  sub     rsp, 60h
0x1800656cf  mov     rax, cs:__security_cookie
0x1800656d6  xor     rax, rsp
0x1800656d9  mov     [rsp+88h+var_38], rax
0x1800656de  cmp     qword ptr [rcx+328h], 0
0x1800656e6  xorps   xmm0, xmm0
0x1800656e9  movups  [rsp+88h+var_48], xmm0
0x1800656ee  mov     r14d, r9d
0x1800656f1  mov     rbp, rdx
0x1800656f4  mov     rsi, rcx
0x1800656f7  jz      short loc_180065703
0x1800656f9  mov     edi, 80070005h
0x1800656fe  jmp     loc_180065827
0x180065703  mov     ecx, 2; unsigned int
0x180065708  call    ?LoadPopupMenu@@YAPEAUHMENU__@@I@Z; LoadPopupMenu(uint)
0x18006570d  mov     rbx, rax
0x180065710  test    rax, rax
0x180065713  jnz     short loc_18006571F
0x180065715  mov     edi, 80004005h
0x18006571a  jmp     loc_180065827
0x18006571f  xor     r8d, r8d; uFlags
0x180065722  mov     edx, 0DFh; uPosition
0x180065727  mov     rcx, rbx; hMenu
0x18006572a  xor     edi, edi
0x18006572c  call    cs:__imp_RemoveMenu
0x180065732  xor     r8d, r8d; uFlags
0x180065735  mov     edx, 0E0h; uPosition
0x18006573a  mov     rcx, rbx; hMenu
0x18006573d  call    cs:__imp_RemoveMenu
0x180065743  lea     edx, [rdi+79h]; uIDEnableItem
0x180065746  mov     rcx, rbx; hMenu
0x180065749  lea     r8d, [rdi+1]; uEnable
0x18006574d  call    cs:__imp_EnableMenuItem
0x180065753  lea     edx, [rdi+7Ah]; uIDEnableItem
0x180065756  mov     rcx, rbx; hMenu
0x180065759  lea     r8d, [rdi+1]; uEnable
0x18006575d  call    cs:__imp_EnableMenuItem
0x180065763  mov     rcx, [rsi+2E0h]; hWnd
0x18006576a  test    rcx, rcx
0x18006576d  jz      short loc_1800657A2
0x18006576f  xor     r9d, r9d; lParam
0x180065772  xor     r8d, r8d; wParam
0x180065775  mov     edx, 0B0h; Msg
0x18006577a  call    cs:__imp_SendMessageA
0x180065780  mov     rcx, rax
0x180065783  lea     edx, [rdi+66h]; uIDEnableItem
0x180065786  shr     eax, 10h
0x180065789  cmp     cx, ax
0x18006578c  mov     rcx, rbx; hMenu
0x18006578f  jz      short loc_180065796
0x180065791  xor     r8d, r8d
0x180065794  jmp     short loc_18006579C
0x180065796  mov     r8d, 1; uEnable
0x18006579c  call    cs:__imp_EnableMenuItem
0x1800657a2  xor     r8d, r8d; uEnable
0x1800657a5  mov     rcx, rbx; hMenu
0x1800657a8  lea     edx, [r8+69h]; uIDEnableItem
0x1800657ac  call    cs:__imp_EnableMenuItem
0x1800657b2  mov     rcx, rbp; hWnd
0x1800657b5  call    cs:__imp_GetParent
0x1800657bb  mov     r9d, [rsp+88h+y]; y
0x1800657c3  mov     r8d, r14d; x
0x1800657c6  mov     [rsp+88h+prcRect], rdi; prcRect
0x1800657cb  mov     edx, 102h; uFlags
0x1800657d0  mov     [rsp+88h+hWnd], rax; hWnd
0x1800657d5  mov     rcx, rbx; hMenu
0x1800657d8  mov     [rsp+88h+nReserved], edi; nReserved
0x1800657dc  call    cs:__imp_TrackPopupMenu
0x1800657e2  test    eax, eax
0x1800657e4  jz      short loc_18006581E
0x1800657e6  cmp     eax, 66h ; 'f'
0x1800657e9  jz      short loc_1800657F6
0x1800657eb  cmp     eax, 69h ; 'i'
0x1800657ee  jnz     short loc_18006581E
0x1800657f0  lea     r8d, [rax-58h]
0x1800657f4  jmp     short loc_1800657FC
0x1800657f6  mov     r8d, 0Ch
0x1800657fc  lea     rcx, [rsi+20h]
0x180065800  mov     [rsp+88h+hWnd], rdi
0x180065805  mov     rax, [rcx]
0x180065808  xor     r9d, r9d
0x18006580b  xor     edx, edx
0x18006580d  mov     qword ptr [rsp+88h+nReserved], rdi
0x180065812  mov     rax, [rax+118h]
0x180065819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006581e  mov     rcx, rbx; hMenu
0x180065821  call    cs:__imp_DestroyMenu
0x180065827  mov     eax, edi
0x180065829  mov     rcx, [rsp+88h+var_38]
0x18006582e  xor     rcx, rsp; StackCookie
0x180065831  call    __security_check_cookie
0x180065836  add     rsp, 60h
0x18006583a  pop     r14
0x18006583c  pop     rdi
0x18006583d  pop     rsi
0x18006583e  pop     rbp
0x18006583f  pop     rbx
0x180065840  retn
```
