# ShowServerMessage(ushort *)

- ea: `0x140001d5c`
- end: `0x140001e1c`
- name: `?ShowServerMessage@@YAXPEAG@Z`
- size: `192`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140001e24`

## callees

- `0x140001ac8`
- `0x140001d5c`
- `0x140004cd0`
- `0x140004d60`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140001d8a`
- `KERNEL32!GetModuleHandleW` at `0x140001dab`
- `KERNEL32!GetModuleHandleW` at `0x140001d8a`
- `KERNEL32!GetModuleHandleW` at `0x140001dab`
- `USER32!LoadStringW` at `0x140001da3`
- `USER32!LoadStringW` at `0x140001dc7`
- `USER32!LoadStringW` at `0x140001da3`
- `USER32!LoadStringW` at `0x140001dc7`
- `USER32!MessageBoxW` at `0x140001dfd`
- `USER32!MessageBoxW` at `0x140001dfd`

## pseudocode

```c
void __fastcall ShowServerMessage(unsigned __int16 *a1)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v3; // rax
  WCHAR Buffer[1000]; // [rsp+20h] [rbp-2728h] BYREF
  WCHAR Source[2000]; // [rsp+7F0h] [rbp-1F58h] BYREF
  WCHAR Text[2000]; // [rsp+1790h] [rbp-FB8h] BYREF

  if ( a1 )
  {
    ModuleHandleW = GetModuleHandleW(0);
    LoadStringW(ModuleHandleW, 0x64u, Buffer, 1000);
    v3 = GetModuleHandleW(0);
    LoadStringW(v3, 0x65u, Source, 2000);
    GetFormattedMessage(Source, Text, 0x7D0u, a1);
    MessageBoxW(0, Text, Buffer, 0);
  }
}

```

## disassembly

```asm
0x140001d5c  test    rcx, rcx
0x140001d5f  jz      locret_140001E1B
0x140001d65  push    rbx
0x140001d66  mov     eax, 2740h
0x140001d6b  call    _alloca_probe
0x140001d70  sub     rsp, rax
0x140001d73  mov     rax, cs:__security_cookie
0x140001d7a  xor     rax, rsp
0x140001d7d  mov     [rsp+2748h+var_18], rax
0x140001d85  mov     rbx, rcx
0x140001d88  xor     ecx, ecx; lpModuleName
0x140001d8a  call    cs:__imp_GetModuleHandleW
0x140001d90  mov     r9d, 3E8h; cchBufferMax
0x140001d96  lea     r8, [rsp+2748h+Buffer]; lpBuffer
0x140001d9b  mov     rcx, rax; hInstance
0x140001d9e  mov     edx, 64h ; 'd'; uID
0x140001da3  call    cs:__imp_LoadStringW
0x140001da9  xor     ecx, ecx; lpModuleName
0x140001dab  call    cs:__imp_GetModuleHandleW
0x140001db1  mov     r9d, 7D0h; cchBufferMax
0x140001db7  lea     r8, [rsp+2748h+Source]; lpBuffer
0x140001dbf  mov     rcx, rax; hInstance
0x140001dc2  mov     edx, 65h ; 'e'; uID
0x140001dc7  call    cs:__imp_LoadStringW
0x140001dcd  mov     r9, rbx
0x140001dd0  lea     rdx, [rsp+2748h+Text]; unsigned __int16 *
0x140001dd8  mov     r8d, 7D0h; unsigned int
0x140001dde  lea     rcx, [rsp+2748h+Source]; lpSource
0x140001de6  call    ?GetFormattedMessage@@YAXPEAG0IZZ; GetFormattedMessage(ushort *,ushort *,uint,...)
0x140001deb  xor     r9d, r9d; uType
0x140001dee  lea     r8, [rsp+2748h+Buffer]; lpCaption
0x140001df3  lea     rdx, [rsp+2748h+Text]; lpText
0x140001dfb  xor     ecx, ecx; hWnd
0x140001dfd  call    cs:__imp_MessageBoxW
0x140001e03  mov     rcx, [rsp+2748h+var_18]
0x140001e0b  xor     rcx, rsp; StackCookie
0x140001e0e  call    __security_check_cookie
0x140001e13  add     rsp, 2740h
0x140001e1a  pop     rbx
0x140001e1b  retn
```
