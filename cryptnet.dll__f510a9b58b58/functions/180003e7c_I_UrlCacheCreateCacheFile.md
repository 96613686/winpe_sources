# I_UrlCacheCreateCacheFile

- ea: `0x180003e7c`
- end: `0x180003eea`
- name: `I_UrlCacheCreateCacheFile`
- size: `110`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *@<rdx>, void *@<r8>, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001154`
- `0x180001460`
- `0x180002460`
- `0x180003274`
- `0x180004b40`
- `0x180019334`

## callees

- `0x1800021e0`
- `0x180002810`
- `0x1800265b0`

## pseudocode

```c
HANDLE __fastcall I_UrlCacheCreateCacheFile(_WORD *Src, _WORD *a2, _WORD *a3, UCHAR *a4, int a5)
{
  _WORD v9[40]; // [rsp+30h] [rbp-88h] BYREF

  I_UrlCacheGetUrlFileName(a4, v9);
  return I_UrlCacheCreateCacheFileFromUrlHash(Src, a2, a3, (__int64)v9, a5);
}

```

## disassembly

```asm
0x180003e7c  push    rbx
0x180003e7e  push    rbp
0x180003e7f  push    rsi
0x180003e80  push    rdi
0x180003e81  sub     rsp, 98h
0x180003e88  mov     rax, cs:__security_cookie
0x180003e8f  xor     rax, rsp
0x180003e92  mov     [rsp+0B8h+var_38], rax
0x180003e9a  mov     ebx, [rsp+0B8h+arg_20]
0x180003ea1  mov     rsi, rdx
0x180003ea4  mov     rdi, rcx
0x180003ea7  lea     rdx, [rsp+0B8h+var_88]
0x180003eac  mov     rcx, r9
0x180003eaf  mov     rbp, r8
0x180003eb2  call    I_UrlCacheGetUrlFileName
0x180003eb7  lea     r9, [rsp+0B8h+var_88]
0x180003ebc  mov     [rsp+0B8h+var_98], ebx; int
0x180003ec0  mov     r8, rbp; void *
0x180003ec3  mov     rdx, rsi; void *
0x180003ec6  mov     rcx, rdi; Src
0x180003ec9  call    I_UrlCacheCreateCacheFileFromUrlHash
0x180003ece  mov     rcx, [rsp+0B8h+var_38]
0x180003ed6  xor     rcx, rsp; StackCookie
0x180003ed9  call    __security_check_cookie
0x180003ede  add     rsp, 98h
0x180003ee5  pop     rdi
0x180003ee6  pop     rsi
0x180003ee7  pop     rbp
0x180003ee8  pop     rbx
0x180003ee9  retn
```
