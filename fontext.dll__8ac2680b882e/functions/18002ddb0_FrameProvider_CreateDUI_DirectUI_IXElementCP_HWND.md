# FrameProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)

- ea: `0x18002ddb0`
- end: `0x18002de16`
- name: `?CreateDUI@FrameProvider@@UEAAJPEAVIXElementCP@DirectUI@@PEAPEAUHWND__@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this, struct DirectUI::IXElementCP *, HWND *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002ddb0`
- `0x180030920`
- `0x180030988`

## import_xrefs

- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x18002dde3`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x18002dde3`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x18002ddf4`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x18002ddf4`

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
0x18002ddb0  mov     rax, rsp
0x18002ddb3  mov     [rax+8], rbx
0x18002ddb7  mov     [rax+10h], rsi
0x18002ddbb  push    rdi
0x18002ddbc  sub     rsp, 20h
0x18002ddc0  mov     rsi, rcx
0x18002ddc3  mov     qword ptr [rax+20h], 0
0x18002ddcb  lea     rcx, [rax+20h]
0x18002ddcf  mov     rbx, r8
0x18002ddd2  mov     rdi, rdx
0x18002ddd5  call    SHActivateContext
0x18002ddda  mov     r8, rbx
0x18002dddd  mov     rdx, rdi
0x18002dde0  mov     rcx, rsi
0x18002dde3  call    cs:__imp_?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z; DirectUI::XProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)
0x18002dde9  mov     ebx, eax
0x18002ddeb  test    eax, eax
0x18002dded  js      short loc_18002DDFA
0x18002ddef  mov     dl, 1
0x18002ddf1  mov     rcx, rsi
0x18002ddf4  call    cs:__imp_?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z; DirectUI::XProvider::SetHandleEnterKey(bool)
0x18002ddfa  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18002ddff  call    SHDeactivateContext
0x18002de04  mov     rsi, [rsp+28h+arg_8]
0x18002de09  mov     eax, ebx
0x18002de0b  mov     rbx, [rsp+28h+arg_0]
0x18002de10  add     rsp, 20h
0x18002de14  pop     rdi
0x18002de15  retn
```
