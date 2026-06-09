# CLightDTEngine::RenderAllClipboardFormats(void)

- ea: `0x1801662cc`
- end: `0x18016639f`
- name: `?RenderAllClipboardFormats@CLightDTEngine@@QEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(CLightDTEngine *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18011ba20`

## callees

- `0x1801018a8`
- `0x1801662cc`
- `0x1801663a8`

## import_xrefs

- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x180166381`
- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x180166381`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x18016631f`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x18016631f`
- `ext-ms-win-ntuser-misc-l1-2-0!EmptyClipboard` at `0x18016632f`
- `ext-ms-win-ntuser-misc-l1-2-0!EmptyClipboard` at `0x18016632f`
- `ext-ms-win-ntuser-misc-l1-2-0!GetClipboardOwner` at `0x1801662e3`
- `ext-ms-win-ntuser-misc-l1-2-0!GetClipboardOwner` at `0x1801662e3`

## pseudocode

```c
_BOOL8 __fastcall CLightDTEngine::RenderAllClipboardFormats(CLightDTEngine *this)
{
  HWND ClipboardOwner; // rax
  HWND v3; // rdi
  BOOL v4; // edi
  HWND hWndNewOwner; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 26) )
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
  v4 = 1;
  if ( !CLightDTEngine::RenderClipboardFormat(this, stru_1802E19E0.cfFormat)
    && !CLightDTEngine::RenderClipboardFormat(this, 0xDu)
    && !CLightDTEngine::RenderClipboardFormat(this, 8u) )
  {
    v4 = CLightDTEngine::RenderClipboardFormat(this, 1u) != 0;
  }
  CloseClipboard();
  return v4;
}

```

## disassembly

```asm
0x1801662cc  mov     [rsp+arg_8], rbx
0x1801662d1  push    rdi
0x1801662d2  sub     rsp, 20h
0x1801662d6  cmp     byte ptr [rcx+1Ah], 0
0x1801662da  mov     rbx, rcx
0x1801662dd  jz      loc_180166391
0x1801662e3  call    cs:__imp_GetClipboardOwner
0x1801662ea  nop     dword ptr [rax+rax+00h]
0x1801662ef  mov     [rsp+28h+hWndNewOwner], 0
0x1801662f8  mov     rdi, rax
0x1801662fb  test    rax, rax
0x1801662fe  jz      loc_180166391
0x180166304  mov     rcx, [rbx]; this
0x180166307  lea     rdx, [rsp+28h+hWndNewOwner]; HWND *
0x18016630c  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x180166311  test    eax, eax
0x180166313  jnz     short loc_180166391
0x180166315  mov     rcx, [rsp+28h+hWndNewOwner]; hWndNewOwner
0x18016631a  cmp     rdi, rcx
0x18016631d  jnz     short loc_180166391
0x18016631f  call    cs:__imp_OpenClipboard
0x180166326  nop     dword ptr [rax+rax+00h]
0x18016632b  test    eax, eax
0x18016632d  jz      short loc_180166391
0x18016632f  call    cs:__imp_EmptyClipboard
0x180166336  nop     dword ptr [rax+rax+00h]
0x18016633b  movzx   edx, cs:stru_1802E19E0.cfFormat; unsigned __int64
0x180166342  mov     rcx, rbx; this
0x180166345  mov     edi, 1
0x18016634a  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18016634f  test    eax, eax
0x180166351  jnz     short loc_180166381
0x180166353  lea     edx, [rdi+0Ch]; unsigned __int64
0x180166356  mov     rcx, rbx; this
0x180166359  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18016635e  test    eax, eax
0x180166360  jnz     short loc_180166381
0x180166362  lea     edx, [rdi+7]; unsigned __int64
0x180166365  mov     rcx, rbx; this
0x180166368  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18016636d  test    eax, eax
0x18016636f  jnz     short loc_180166381
0x180166371  mov     edx, edi; unsigned __int64
0x180166373  mov     rcx, rbx; this
0x180166376  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18016637b  neg     eax
0x18016637d  sbb     ecx, ecx
0x18016637f  and     edi, ecx
0x180166381  call    cs:__imp_CloseClipboard
0x180166388  nop     dword ptr [rax+rax+00h]
0x18016638d  mov     eax, edi
0x18016638f  jmp     short loc_180166393
0x180166391  xor     eax, eax
0x180166393  mov     rbx, [rsp+28h+arg_8]
0x180166398  add     rsp, 20h
0x18016639c  pop     rdi
0x18016639d  retn
```
