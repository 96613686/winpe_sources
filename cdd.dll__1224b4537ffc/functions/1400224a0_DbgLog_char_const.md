# DbgLog(char const *,...)

- ea: `0x1400224a0`
- end: `0x140022521`
- name: `?DbgLog@@YAXPEBDZZ`
- size: `129`
- prototype: `void(const char *Format, ...)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140002020`
- `0x1400087ac`
- `0x1400089ec`
- `0x140008d28`
- `0x140008da4`
- `0x14000919c`
- `0x140011510`
- `0x1400161b0`
- `0x140018730`
- `0x14001f270`
- `0x140022270`
- `0x140033db0`
- `0x140033e60`
- `0x140034204`
- `0x1400342e0`

## callees

- `0x1400371f0`

## import_xrefs

- `ntoskrnl!vsprintf_s` at `0x1400224e6`
- `ntoskrnl!vsprintf_s` at `0x1400224e6`
- `ntoskrnl!DbgPrintEx` at `0x1400224fc`
- `ntoskrnl!DbgPrintEx` at `0x1400224fc`

## pseudocode

```c
void DbgLog(const char *Format, ...)
{
  char DstBuf[256]; // [rsp+30h] [rbp-118h] BYREF
  va_list va; // [rsp+158h] [rbp+10h] BYREF

  va_start(va, Format);
  vsprintf_s(DstBuf, 0x100u, Format, va);
  DbgPrintEx(0x70u, 0, DstBuf);
}

```

## disassembly

```asm
0x1400224a0  mov     r11, rsp
0x1400224a3  mov     [r11+8], rcx
0x1400224a7  mov     [r11+10h], rdx
0x1400224ab  mov     [r11+18h], r8
0x1400224af  mov     [r11+20h], r9
0x1400224b3  sub     rsp, 148h
0x1400224ba  mov     rax, cs:__security_cookie
0x1400224c1  xor     rax, rsp
0x1400224c4  mov     [rsp+148h+var_18], rax
0x1400224cc  mov     r8, rcx; Format
0x1400224cf  mov     [rsp+148h+var_128], 0
0x1400224d8  lea     rcx, [rsp+148h+DstBuf]; DstBuf
0x1400224dd  mov     edx, 100h; SizeInBytes
0x1400224e2  lea     r9, [r11+10h]; ArgList
0x1400224e6  call    cs:__imp_vsprintf_s
0x1400224ed  nop     dword ptr [rax+rax+00h]
0x1400224f2  xor     edx, edx; Level
0x1400224f4  lea     r8, [rsp+148h+DstBuf]; Format
0x1400224f9  lea     ecx, [rdx+70h]; ComponentId
0x1400224fc  call    cs:__imp_DbgPrintEx
0x140022503  nop     dword ptr [rax+rax+00h]
0x140022508  mov     rcx, [rsp+148h+var_18]
0x140022510  xor     rcx, rsp; StackCookie
0x140022513  call    __security_check_cookie
0x140022518  add     rsp, 148h
0x14002251f  retn
```
