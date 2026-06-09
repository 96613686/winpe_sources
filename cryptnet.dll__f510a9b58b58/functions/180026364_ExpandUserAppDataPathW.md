# _ExpandUserAppDataPathW

- ea: `0x180026364`
- end: `0x1800263ca`
- name: `_ExpandUserAppDataPathW`
- size: `102`
- prototype: `DWORD __fastcall(WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006710`

## callees

- `0x180026364`
- `0x180026552`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002638d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002638d`

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
0x180026364  push    rbx
0x180026366  sub     rsp, 240h
0x18002636d  mov     rax, cs:__security_cookie
0x180026374  xor     rax, rsp
0x180026377  mov     [rsp+248h+var_18], rax
0x18002637f  mov     r8d, 104h; nSize
0x180026385  lea     rdx, [rsp+248h+Dst]; lpDst
0x18002638a  mov     rbx, rcx
0x18002638d  call    cs:__imp_ExpandEnvironmentStringsW
0x180026393  lea     edx, [rax-1]
0x180026396  cmp     edx, 103h
0x18002639c  ja      short loc_1800263B1
0x18002639e  mov     r8d, eax
0x1800263a1  lea     rdx, [rsp+248h+Dst]; Src
0x1800263a6  add     r8, r8; Size
0x1800263a9  mov     rcx, rbx; void *
0x1800263ac  call    memcpy_0
0x1800263b1  mov     rcx, [rsp+248h+var_18]
0x1800263b9  xor     rcx, rsp; StackCookie
0x1800263bc  call    __security_check_cookie
0x1800263c1  add     rsp, 240h
0x1800263c8  pop     rbx
0x1800263c9  retn
```
