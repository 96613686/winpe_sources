# CreateLinkInfoA

- ea: `0x1800054e0`
- end: `0x18000553c`
- name: `CreateLinkInfoA`
- size: `92`
- prototype: `int __fastcall(const CHAR *, struct _ilinkinfoW **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001ca0`
- `0x180005750`

## import_xrefs

- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180005509`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180005509`

## pseudocode

```c
int __fastcall CreateLinkInfoA(const CHAR *a1, struct _ilinkinfoW **a2)
{
  WCHAR pwszDst[264]; // [rsp+20h] [rbp-228h] BYREF

  SHAnsiToUnicode(a1, pwszDst, 260);
  return CreateLinkInfoW(pwszDst, a2);
}

```

## disassembly

```asm
0x1800054e0  push    rbx; CreateLinkInfo
0x1800054e2  sub     rsp, 240h
0x1800054e9  mov     rax, cs:__security_cookie
0x1800054f0  xor     rax, rsp
0x1800054f3  mov     [rsp+248h+var_18], rax
0x1800054fb  mov     rbx, rdx
0x1800054fe  mov     r8d, 104h; cwchBuf
0x180005504  lea     rdx, [rsp+248h+pwszDst]; pwszDst
0x180005509  call    cs:__imp_SHAnsiToUnicode
0x180005510  nop     dword ptr [rax+rax+00h]
0x180005515  mov     rdx, rbx
0x180005518  lea     rcx, [rsp+248h+pwszDst]
0x18000551d  call    CreateLinkInfoW
0x180005522  mov     rcx, [rsp+248h+var_18]
0x18000552a  xor     rcx, rsp; StackCookie
0x18000552d  call    __security_check_cookie
0x180005532  add     rsp, 240h
0x180005539  pop     rbx
0x18000553a  retn
```
