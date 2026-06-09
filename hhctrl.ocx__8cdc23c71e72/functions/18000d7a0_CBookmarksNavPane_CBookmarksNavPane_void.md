# CBookmarksNavPane::~CBookmarksNavPane(void)

- ea: `0x18000d7a0`
- end: `0x18000d85a`
- name: `??1CBookmarksNavPane@@UEAA@XZ`
- size: `186`
- prototype: `void __fastcall(CBookmarksNavPane *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d860`

## callees

- `0x180001710`
- `0x18000d7a0`
- `0x18000e104`
- `0x18000ef78`

## import_xrefs

- `USER32!DestroyWindow` at `0x18000d829`
- `USER32!DestroyWindow` at `0x18000d829`
- `USER32!SendMessageA` at `0x18000d7d0`
- `USER32!SendMessageA` at `0x18000d80b`
- `USER32!SendMessageA` at `0x18000d7d0`
- `USER32!SendMessageA` at `0x18000d80b`
- `GDI32!DeleteObject` at `0x18000d81a`
- `GDI32!DeleteObject` at `0x18000d81a`

## pseudocode

```c
void __fastcall CBookmarksNavPane::~CBookmarksNavPane(HWND *this)
{
  int v2; // esi
  int v3; // edi
  char *Url; // rax
  HWND v5; // rcx
  HWND v6; // rcx
  HWND v7; // rcx

  *this = (HWND)&CBookmarksNavPane::`vftable';
  CBookmarksNavPane::SaveBookmarks((CBookmarksNavPane *)this);
  v2 = SendMessageA(this[4], 0x1004u, 0, 0);
  if ( v2 > 0 )
  {
    v3 = 0;
    do
    {
      Url = CBookmarksNavPane::GetUrl((CBookmarksNavPane *)this, v3);
      if ( Url )
        operator delete[](Url);
      ++v3;
    }
    while ( v3 < v2 );
    SendMessageA(this[4], 0x1009u, 0, 0);
  }
  v5 = this[2];
  if ( v5 )
    DeleteObject(v5);
  v6 = this[1];
  if ( v6 )
    DestroyWindow(v6);
  v7 = this[90];
  if ( v7 )
    operator delete[](v7);
  *this = (HWND)&INavUI::`vftable';
}

```

## disassembly

```asm
0x18000d7a0  mov     [rsp+arg_0], rbx
0x18000d7a5  mov     [rsp+arg_8], rsi
0x18000d7aa  push    rdi
0x18000d7ab  sub     rsp, 20h
0x18000d7af  mov     rbx, rcx
0x18000d7b2  lea     rax, ??_7CBookmarksNavPane@@6B@; const CBookmarksNavPane::`vftable'
0x18000d7b9  mov     [rcx], rax
0x18000d7bc  call    ?SaveBookmarks@CBookmarksNavPane@@AEAAXXZ; CBookmarksNavPane::SaveBookmarks(void)
0x18000d7c1  xor     r9d, r9d; lParam
0x18000d7c4  xor     r8d, r8d; wParam
0x18000d7c7  mov     edx, 1004h; Msg
0x18000d7cc  mov     rcx, [rbx+20h]; hWnd
0x18000d7d0  call    cs:__imp_SendMessageA
0x18000d7d6  mov     rsi, rax
0x18000d7d9  test    eax, eax
0x18000d7db  jle     short loc_18000D811
0x18000d7dd  xor     edi, edi
0x18000d7df  mov     edx, edi; int
0x18000d7e1  mov     rcx, rbx; this
0x18000d7e4  call    ?GetUrl@CBookmarksNavPane@@AEBAPEADH@Z; CBookmarksNavPane::GetUrl(int)
0x18000d7e9  test    rax, rax
0x18000d7ec  jz      short loc_18000D7F6
0x18000d7ee  mov     rcx, rax; void *
0x18000d7f1  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d7f6  inc     edi
0x18000d7f8  cmp     edi, esi
0x18000d7fa  jl      short loc_18000D7DF
0x18000d7fc  xor     r9d, r9d; lParam
0x18000d7ff  xor     r8d, r8d; wParam
0x18000d802  mov     edx, 1009h; Msg
0x18000d807  mov     rcx, [rbx+20h]; hWnd
0x18000d80b  call    cs:__imp_SendMessageA
0x18000d811  mov     rcx, [rbx+10h]; ho
0x18000d815  test    rcx, rcx
0x18000d818  jz      short loc_18000D820
0x18000d81a  call    cs:__imp_DeleteObject
0x18000d820  mov     rcx, [rbx+8]; hWnd
0x18000d824  test    rcx, rcx
0x18000d827  jz      short loc_18000D82F
0x18000d829  call    cs:__imp_DestroyWindow
0x18000d82f  mov     rcx, [rbx+2D0h]; void *
0x18000d836  test    rcx, rcx
0x18000d839  jz      short loc_18000D840
0x18000d83b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d840  lea     rax, ??_7INavUI@@6B@; const INavUI::`vftable'
0x18000d847  mov     [rbx], rax
0x18000d84a  mov     rbx, [rsp+28h+arg_0]
0x18000d84f  mov     rsi, [rsp+28h+arg_8]
0x18000d854  add     rsp, 20h
0x18000d858  pop     rdi
0x18000d859  retn
```
