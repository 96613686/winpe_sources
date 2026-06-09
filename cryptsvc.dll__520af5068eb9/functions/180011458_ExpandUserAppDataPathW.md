# _ExpandUserAppDataPathW

- ea: `0x180011458`
- end: `0x1800114be`
- name: `_ExpandUserAppDataPathW`
- size: `102`
- prototype: `DWORD __fastcall(WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006db0`

## callees

- `0x18000e2f0`
- `0x180011458`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180011481`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180011481`

## pseudocode

```c
DWORD __fastcall ExpandUserAppDataPathW(WCHAR *a1)
{
  DWORD result; // eax
  WCHAR Dst[264]; // [rsp+20h] [rbp-228h] BYREF

  result = ExpandEnvironmentStringsW(a1, Dst, 0x104u);
  if ( result - 1 <= 0x103 )
    return (unsigned int)memcpy_0(a1, Dst, 2LL * result);
  return result;
}

```

## disassembly

```asm
0x180011458  push    rbx
0x18001145a  sub     rsp, 240h
0x180011461  mov     rax, cs:__security_cookie
0x180011468  xor     rax, rsp
0x18001146b  mov     [rsp+248h+var_18], rax
0x180011473  mov     r8d, 104h; nSize
0x180011479  lea     rdx, [rsp+248h+Dst]; lpDst
0x18001147e  mov     rbx, rcx
0x180011481  call    cs:__imp_ExpandEnvironmentStringsW
0x180011487  lea     edx, [rax-1]
0x18001148a  cmp     edx, 103h
0x180011490  ja      short loc_1800114A5
0x180011492  mov     r8d, eax
0x180011495  lea     rdx, [rsp+248h+Dst]; Src
0x18001149a  add     r8, r8; Size
0x18001149d  mov     rcx, rbx; void *
0x1800114a0  call    memcpy_0
0x1800114a5  mov     rcx, [rsp+248h+var_18]
0x1800114ad  xor     rcx, rsp; StackCookie
0x1800114b0  call    __security_check_cookie
0x1800114b5  add     rsp, 240h
0x1800114bc  pop     rbx
0x1800114bd  retn
```
