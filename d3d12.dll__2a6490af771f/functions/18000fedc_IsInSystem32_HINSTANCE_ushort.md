# IsInSystem32(HINSTANCE__ *,ushort *)

- ea: `0x18000fedc`
- end: `0x18000ff63`
- name: `?IsInSystem32@@YA_NPEAUHINSTANCE__@@PEAG@Z`
- size: `135`
- prototype: `bool __fastcall(HINSTANCE hModule, wchar_t *SubStr)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000670c`

## callees

- `0x18000b410`
- `0x18000be78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000ff36`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000ff36`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000ff28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000ff28`

## pseudocode

```c
bool __fastcall IsInSystem32(HINSTANCE hModule, wchar_t *SubStr)
{
  WCHAR Filename; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v6[526]; // [rsp+22h] [rbp-226h] BYREF

  Filename = 0;
  memset_0(v6, 0, 0x206u);
  GetModuleFileNameW(hModule, &Filename, 0x104u);
  return wcsstr(&Filename, SubStr) != 0;
}

```

## disassembly

```asm
0x18000fedc  mov     [rsp+arg_10], rbx
0x18000fee1  push    rdi
0x18000fee2  sub     rsp, 240h
0x18000fee9  mov     rax, cs:__security_cookie
0x18000fef0  xor     rax, rsp
0x18000fef3  mov     [rsp+248h+var_18], rax
0x18000fefb  mov     rdi, rdx
0x18000fefe  mov     rbx, rcx
0x18000ff01  xor     eax, eax
0x18000ff03  lea     rcx, [rsp+248h+var_226]; void *
0x18000ff08  xor     edx, edx; Val
0x18000ff0a  mov     [rsp+248h+Filename], ax
0x18000ff0f  mov     r8d, 206h; Size
0x18000ff15  call    memset_0
0x18000ff1a  mov     r8d, 104h; nSize
0x18000ff20  lea     rdx, [rsp+248h+Filename]; lpFilename
0x18000ff25  mov     rcx, rbx; hModule
0x18000ff28  call    cs:__imp_GetModuleFileNameW
0x18000ff2e  mov     rdx, rdi; SubStr
0x18000ff31  lea     rcx, [rsp+248h+Filename]; Str
0x18000ff36  call    cs:__imp_wcsstr
0x18000ff3c  test    rax, rax
0x18000ff3f  setnz   al
0x18000ff42  mov     rcx, [rsp+248h+var_18]
0x18000ff4a  xor     rcx, rsp; StackCookie
0x18000ff4d  call    __security_check_cookie
0x18000ff52  mov     rbx, [rsp+248h+arg_10]
0x18000ff5a  add     rsp, 240h
0x18000ff61  pop     rdi
0x18000ff62  retn
```
