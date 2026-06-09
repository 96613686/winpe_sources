# FrameProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)

- ea: `0x1800166f0`
- end: `0x180016756`
- name: `?CreateDUI@FrameProvider@@UEAAJPEAVIXElementCP@DirectUI@@PEAPEAUHWND__@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this, struct DirectUI::IXElementCP *, HWND *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800166f0`
- `0x180018740`
- `0x1800187a8`

## import_xrefs

- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x180016723`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x180016723`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x180016734`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x180016734`

## pseudocode

```c
__int64 __fastcall FrameProvider::CreateDUI(FrameProvider *this, struct DirectUI::IXElementCP *a2, HWND *a3)
{
  int DUI; // ebx
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+20h] BYREF

  ulCookie = 0;
  SHActivateContext(&ulCookie);
  DUI = DirectUI::XProvider::CreateDUI(this, a2, a3);
  if ( DUI >= 0 )
    DirectUI::XProvider::SetHandleEnterKey(this, 1);
  SHDeactivateContext(ulCookie);
  return (unsigned int)DUI;
}

```

## disassembly

```asm
0x1800166f0  mov     rax, rsp
0x1800166f3  mov     [rax+8], rbx
0x1800166f7  mov     [rax+10h], rsi
0x1800166fb  push    rdi
0x1800166fc  sub     rsp, 20h
0x180016700  mov     rsi, rcx
0x180016703  mov     qword ptr [rax+20h], 0
0x18001670b  lea     rcx, [rax+20h]
0x18001670f  mov     rbx, r8
0x180016712  mov     rdi, rdx
0x180016715  call    SHActivateContext
0x18001671a  mov     r8, rbx
0x18001671d  mov     rdx, rdi
0x180016720  mov     rcx, rsi
0x180016723  call    cs:__imp_?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z; DirectUI::XProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)
0x180016729  mov     ebx, eax
0x18001672b  test    eax, eax
0x18001672d  js      short loc_18001673A
0x18001672f  mov     dl, 1
0x180016731  mov     rcx, rsi
0x180016734  call    cs:__imp_?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z; DirectUI::XProvider::SetHandleEnterKey(bool)
0x18001673a  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18001673f  call    SHDeactivateContext
0x180016744  mov     rsi, [rsp+28h+arg_8]
0x180016749  mov     eax, ebx
0x18001674b  mov     rbx, [rsp+28h+arg_0]
0x180016750  add     rsp, 20h
0x180016754  pop     rdi
0x180016755  retn
```
