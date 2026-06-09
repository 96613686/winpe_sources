# FrameProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)

- ea: `0x18002e080`
- end: `0x18002e0e6`
- name: `?CreateDUI@FrameProvider@@UEAAJPEAVIXElementCP@DirectUI@@PEAPEAUHWND__@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this, struct DirectUI::IXElementCP *, HWND *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002d7c8`
- `0x18002d838`
- `0x18002e080`

## import_xrefs

- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x18002e0c4`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x18002e0c4`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x18002e0b3`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x18002e0b3`

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
0x18002e080  mov     rax, rsp
0x18002e083  mov     [rax+8], rbx
0x18002e087  mov     [rax+10h], rsi
0x18002e08b  push    rdi
0x18002e08c  sub     rsp, 20h
0x18002e090  mov     rsi, rcx
0x18002e093  mov     qword ptr [rax+20h], 0
0x18002e09b  lea     rcx, [rax+20h]
0x18002e09f  mov     rbx, r8
0x18002e0a2  mov     rdi, rdx
0x18002e0a5  call    SHActivateContext
0x18002e0aa  mov     r8, rbx
0x18002e0ad  mov     rdx, rdi
0x18002e0b0  mov     rcx, rsi
0x18002e0b3  call    cs:__imp_?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z; DirectUI::XProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)
0x18002e0b9  mov     ebx, eax
0x18002e0bb  test    eax, eax
0x18002e0bd  js      short loc_18002E0CA
0x18002e0bf  mov     dl, 1
0x18002e0c1  mov     rcx, rsi
0x18002e0c4  call    cs:__imp_?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z; DirectUI::XProvider::SetHandleEnterKey(bool)
0x18002e0ca  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18002e0cf  call    SHDeactivateContext
0x18002e0d4  mov     rsi, [rsp+28h+arg_8]
0x18002e0d9  mov     eax, ebx
0x18002e0db  mov     rbx, [rsp+28h+arg_0]
0x18002e0e0  add     rsp, 20h
0x18002e0e4  pop     rdi
0x18002e0e5  retn
```
