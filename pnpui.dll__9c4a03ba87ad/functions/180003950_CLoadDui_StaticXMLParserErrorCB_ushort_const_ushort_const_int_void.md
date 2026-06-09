# CLoadDui::StaticXMLParserErrorCB(ushort const *,ushort const *,int,void *)

- ea: `0x180003950`
- end: `0x1800039c2`
- name: `?StaticXMLParserErrorCB@CLoadDui@@CAXPEBG0HPEAX@Z`
- size: `114`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003614`
- `0x180003950`
- `0x18000cd10`

## pseudocode

```c
void __fastcall CLoadDui::StaticXMLParserErrorCB(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        void *a4)
{
  unsigned __int16 v5[208]; // [rsp+30h] [rbp-1B8h] BYREF

  if ( a3 == -1 )
    StringCchPrintfW(v5, 0xC9u, L"%s '%s'", a1, a2);
  else
    StringCchPrintfW(v5, 0xC9u, L"%s '%s' at line %d", a1, a2, a3);
}

```

## disassembly

```asm
0x180003950  sub     rsp, 1E8h
0x180003957  mov     rax, cs:__security_cookie
0x18000395e  xor     rax, rsp
0x180003961  mov     [rsp+1E8h+var_18], rax
0x180003969  mov     r9, rcx
0x18000396c  lea     rcx, [rsp+1E8h+var_1B8]; unsigned __int16 *
0x180003971  cmp     r8d, 0FFFFFFFFh
0x180003975  jz      short loc_180003994
0x180003977  mov     [rsp+1E8h+var_1C0], r8d
0x18000397c  lea     r8, aSSAtLineD; "%s '%s' at line %d"
0x180003983  mov     [rsp+1E8h+var_1C8], rdx
0x180003988  mov     edx, 0C9h; unsigned __int64
0x18000398d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003992  jmp     short loc_1800039AA
0x180003994  mov     [rsp+1E8h+var_1C8], rdx
0x180003999  lea     r8, aSS; "%s '%s'"
0x1800039a0  mov     edx, 0C9h; unsigned __int64
0x1800039a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800039aa  mov     rcx, [rsp+1E8h+var_18]
0x1800039b2  xor     rcx, rsp; StackCookie
0x1800039b5  call    __security_check_cookie
0x1800039ba  add     rsp, 1E8h
0x1800039c1  retn
```
