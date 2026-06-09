# FrameProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)

- ea: `0x18001ba40`
- end: `0x18001baa6`
- name: `?CreateDUI@FrameProvider@@UEAAJPEAVIXElementCP@DirectUI@@PEAPEAUHWND__@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this, struct DirectUI::IXElementCP *, HWND *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001b538`
- `0x18001b5a8`
- `0x18001ba40`

## import_xrefs

- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x18001ba73`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x18001ba73`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x18001ba84`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x18001ba84`

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
0x18001ba40  mov     rax, rsp
0x18001ba43  mov     [rax+8], rbx
0x18001ba47  mov     [rax+10h], rsi
0x18001ba4b  push    rdi
0x18001ba4c  sub     rsp, 20h
0x18001ba50  mov     rsi, rcx
0x18001ba53  mov     qword ptr [rax+20h], 0
0x18001ba5b  lea     rcx, [rax+20h]
0x18001ba5f  mov     rbx, r8
0x18001ba62  mov     rdi, rdx
0x18001ba65  call    SHActivateContext
0x18001ba6a  mov     r8, rbx
0x18001ba6d  mov     rdx, rdi
0x18001ba70  mov     rcx, rsi
0x18001ba73  call    cs:__imp_?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z; DirectUI::XProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)
0x18001ba79  mov     ebx, eax
0x18001ba7b  test    eax, eax
0x18001ba7d  js      short loc_18001BA8A
0x18001ba7f  mov     dl, 1
0x18001ba81  mov     rcx, rsi
0x18001ba84  call    cs:__imp_?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z; DirectUI::XProvider::SetHandleEnterKey(bool)
0x18001ba8a  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18001ba8f  call    SHDeactivateContext
0x18001ba94  mov     rsi, [rsp+28h+arg_8]
0x18001ba99  mov     eax, ebx
0x18001ba9b  mov     rbx, [rsp+28h+arg_0]
0x18001baa0  add     rsp, 20h
0x18001baa4  pop     rdi
0x18001baa5  retn
```
