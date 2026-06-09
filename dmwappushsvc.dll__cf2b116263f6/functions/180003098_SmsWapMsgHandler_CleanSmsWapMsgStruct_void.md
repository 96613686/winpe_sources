# SmsWapMsgHandler::CleanSmsWapMsgStruct(void)

- ea: `0x180003098`
- end: `0x1800030dd`
- name: `?CleanSmsWapMsgStruct@SmsWapMsgHandler@@AEAAXXZ`
- size: `69`
- prototype: `void __fastcall(SmsWapMsgHandler *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180002e94`
- `0x180003d3c`

## callees

- `0x180001a94`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800030ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800030b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800030ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800030b8`

## pseudocode

```c
void __fastcall SmsWapMsgHandler::CleanSmsWapMsgStruct(SmsWapMsgHandler *this)
{
  operator delete(*((void **)this + 2));
  WindowsDeleteString(*((HSTRING *)this + 4));
  WindowsDeleteString(*((HSTRING *)this + 5));
  operator delete(*((void **)this + 6));
  *((_QWORD *)this + 20) = 0;
  *((_WORD *)this + 84) = 0;
}

```

## disassembly

```asm
0x180003098  push    rbx
0x18000309a  sub     rsp, 20h
0x18000309e  mov     rbx, rcx
0x1800030a1  mov     rcx, [rcx+10h]; Block
0x1800030a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800030aa  mov     rcx, [rbx+20h]; string
0x1800030ae  call    cs:__imp_WindowsDeleteString
0x1800030b4  mov     rcx, [rbx+28h]; string
0x1800030b8  call    cs:__imp_WindowsDeleteString
0x1800030be  mov     rcx, [rbx+30h]; Block
0x1800030c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800030c7  xor     eax, eax
0x1800030c9  mov     [rbx+0A0h], rax
0x1800030d0  mov     [rbx+0A8h], ax
0x1800030d7  add     rsp, 20h
0x1800030db  pop     rbx
0x1800030dc  retn
```
