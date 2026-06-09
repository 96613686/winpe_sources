# CWebDriverHost::_ConvertCoreWebViewPrivateIdToWindowHandle(ulong)

- ea: `0x180066a44`
- end: `0x180066a81`
- name: `?_ConvertCoreWebViewPrivateIdToWindowHandle@CWebDriverHost@@AEAAPEAGK@Z`
- size: `61`
- prototype: `unsigned __int16 *(CWebDriverHost *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180065cd0`
- `0x180066fb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x180066a6d`
- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x180066a6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180066a55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180066a55`

## pseudocode

```c
unsigned __int16 *__fastcall CWebDriverHost::_ConvertCoreWebViewPrivateIdToWindowHandle(CWebDriverHost *this, int a2)
{
  wchar_t *v3; // rbx

  v3 = (wchar_t *)CoTaskMemAlloc(0x18u);
  _ltow_s(a2, v3, 0xCu, 10);
  return v3;
}

```

## disassembly

```asm
0x180066a44  mov     [rsp+arg_0], rbx
0x180066a49  push    rdi
0x180066a4a  sub     rsp, 20h
0x180066a4e  mov     ecx, 18h; cb
0x180066a53  mov     edi, edx
0x180066a55  call    cs:__imp_CoTaskMemAlloc
0x180066a5b  mov     r9d, 0Ah; Radix
0x180066a61  mov     ecx, edi; Value
0x180066a63  mov     rdx, rax; Buffer
0x180066a66  mov     rbx, rax
0x180066a69  lea     r8d, [r9+2]; BufferCount
0x180066a6d  call    cs:__imp__ltow_s
0x180066a73  mov     rax, rbx
0x180066a76  mov     rbx, [rsp+28h+arg_0]
0x180066a7b  add     rsp, 20h
0x180066a7f  pop     rdi
0x180066a80  retn
```
