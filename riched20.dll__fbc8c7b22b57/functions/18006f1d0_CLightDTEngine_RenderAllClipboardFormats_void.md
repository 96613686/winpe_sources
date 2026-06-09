# CLightDTEngine::RenderAllClipboardFormats(void)

- ea: `0x18006f1d0`
- end: `0x18006f2a1`
- name: `?RenderAllClipboardFormats@CLightDTEngine@@QEAAJXZ`
- size: `209`
- prototype: `__int64 __fastcall(CLightDTEngine *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180027b20`

## callees

- `0x180040b14`
- `0x18006f1d0`
- `0x18006f2a8`

## import_xrefs

- `USER32!OpenClipboard` at `0x18006f223`
- `USER32!OpenClipboard` at `0x18006f223`
- `USER32!EmptyClipboard` at `0x18006f233`
- `USER32!EmptyClipboard` at `0x18006f233`
- `USER32!CloseClipboard` at `0x18006f283`
- `USER32!CloseClipboard` at `0x18006f283`
- `USER32!GetClipboardOwner` at `0x18006f1e7`
- `USER32!GetClipboardOwner` at `0x18006f1e7`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::RenderAllClipboardFormats(CLightDTEngine *this)
{
  HWND ClipboardOwner; // rax
  HWND v3; // rbx
  unsigned int v4; // ebx
  HWND hWndNewOwner; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 25) )
    return 0;
  ClipboardOwner = GetClipboardOwner();
  hWndNewOwner = 0;
  v3 = ClipboardOwner;
  if ( !ClipboardOwner
    || (unsigned int)CTxtEdit::TxGetWindow(*(CTxtEdit **)this, &hWndNewOwner)
    || v3 != hWndNewOwner
    || !OpenClipboard(hWndNewOwner) )
  {
    return 0;
  }
  EmptyClipboard();
  v4 = CLightDTEngine::RenderClipboardFormat(this, (unsigned __int16)xmmword_1800A61F0);
  if ( !v4 )
  {
    v4 = CLightDTEngine::RenderClipboardFormat(this, 0xDu);
    if ( !v4 )
    {
      v4 = CLightDTEngine::RenderClipboardFormat(this, 8u);
      if ( !v4 )
        v4 = CLightDTEngine::RenderClipboardFormat(this, 1u);
    }
  }
  CloseClipboard();
  return v4;
}

```

## disassembly

```asm
0x18006f1d0  mov     [rsp+arg_8], rbx
0x18006f1d5  push    rdi
0x18006f1d6  sub     rsp, 20h
0x18006f1da  cmp     byte ptr [rcx+19h], 0
0x18006f1de  mov     rdi, rcx
0x18006f1e1  jz      loc_18006F293
0x18006f1e7  call    cs:__imp_GetClipboardOwner
0x18006f1ee  nop     dword ptr [rax+rax+00h]
0x18006f1f3  mov     [rsp+28h+hWndNewOwner], 0
0x18006f1fc  mov     rbx, rax
0x18006f1ff  test    rax, rax
0x18006f202  jz      loc_18006F293
0x18006f208  mov     rcx, [rdi]; this
0x18006f20b  lea     rdx, [rsp+28h+hWndNewOwner]; HWND *
0x18006f210  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18006f215  test    eax, eax
0x18006f217  jnz     short loc_18006F293
0x18006f219  mov     rcx, [rsp+28h+hWndNewOwner]; hWndNewOwner
0x18006f21e  cmp     rbx, rcx
0x18006f221  jnz     short loc_18006F293
0x18006f223  call    cs:__imp_OpenClipboard
0x18006f22a  nop     dword ptr [rax+rax+00h]
0x18006f22f  test    eax, eax
0x18006f231  jz      short loc_18006F293
0x18006f233  call    cs:__imp_EmptyClipboard
0x18006f23a  nop     dword ptr [rax+rax+00h]
0x18006f23f  movzx   edx, word ptr cs:xmmword_1800A61F0; unsigned __int64
0x18006f246  mov     rcx, rdi; this
0x18006f249  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18006f24e  mov     ebx, eax
0x18006f250  test    eax, eax
0x18006f252  jnz     short loc_18006F283
0x18006f254  lea     edx, [rax+0Dh]; unsigned __int64
0x18006f257  mov     rcx, rdi; this
0x18006f25a  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18006f25f  mov     ebx, eax
0x18006f261  test    eax, eax
0x18006f263  jnz     short loc_18006F283
0x18006f265  lea     edx, [rax+8]; unsigned __int64
0x18006f268  mov     rcx, rdi; this
0x18006f26b  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18006f270  mov     ebx, eax
0x18006f272  test    eax, eax
0x18006f274  jnz     short loc_18006F283
0x18006f276  lea     edx, [rax+1]; unsigned __int64
0x18006f279  mov     rcx, rdi; this
0x18006f27c  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18006f281  mov     ebx, eax
0x18006f283  call    cs:__imp_CloseClipboard
0x18006f28a  nop     dword ptr [rax+rax+00h]
0x18006f28f  mov     eax, ebx
0x18006f291  jmp     short loc_18006F295
0x18006f293  xor     eax, eax
0x18006f295  mov     rbx, [rsp+28h+arg_8]
0x18006f29a  add     rsp, 20h
0x18006f29e  pop     rdi
0x18006f29f  retn
```
