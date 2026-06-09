# eksvcOpenLog(void)

- ea: `0x180007ce4`
- end: `0x180007d6f`
- name: `?eksvcOpenLog@@YA_NXZ`
- size: `139`
- prototype: `bool __fastcall(const char *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003750`

## callees

- `0x180007a60`
- `0x180007bcc`
- `0x180007ce4`
- `0x18000a800`

## import_xrefs

- `msvcrt!fopen` at `0x180007d2a`
- `msvcrt!fopen` at `0x180007d2a`

## pseudocode

```c
bool __fastcall eksvcOpenLog(const char *a1, __int64 a2, unsigned int a3)
{
  char FileName[272]; // [rsp+20h] [rbp-128h] BYREF

  if ( Stream )
    return 1;
  if ( !s_szLogFileName )
    return 0;
  if ( !eksvcGetLogFileNameA(a1, FileName, a3) )
  {
    Stream = fopen(FileName, "at");
    eksvcLogStringA(0, 0, L"================================");
  }
  return Stream != 0;
}

```

## disassembly

```asm
0x180007ce4  sub     rsp, 148h
0x180007ceb  mov     rax, cs:__security_cookie
0x180007cf2  xor     rax, rsp
0x180007cf5  mov     [rsp+148h+var_18], rax
0x180007cfd  cmp     cs:Stream, 0
0x180007d05  jnz     short loc_180007D55
0x180007d07  cmp     cs:?s_szLogFileName@@3PADA, 0; char near * s_szLogFileName
0x180007d0e  jz      short loc_180007D51
0x180007d10  lea     rdx, [rsp+148h+FileName]; char *
0x180007d15  call    ?eksvcGetLogFileNameA@@YAJPEBDPEADK@Z; eksvcGetLogFileNameA(char const *,char *,ulong)
0x180007d1a  test    eax, eax
0x180007d1c  jnz     short loc_180007D47
0x180007d1e  lea     rdx, Mode; "at"
0x180007d25  lea     rcx, [rsp+148h+FileName]; FileName
0x180007d2a  call    cs:__imp_fopen
0x180007d30  lea     r8, asc_18000E210; "================================"
0x180007d37  xor     edx, edx; int
0x180007d39  xor     ecx, ecx; char *
0x180007d3b  mov     cs:Stream, rax
0x180007d42  call    ?eksvcLogStringA@@YAXPEBDJPEBG@Z; eksvcLogStringA(char const *,long,ushort const *)
0x180007d47  cmp     cs:Stream, 0
0x180007d4f  jnz     short loc_180007D55
0x180007d51  xor     al, al
0x180007d53  jmp     short loc_180007D57
0x180007d55  mov     al, 1
0x180007d57  mov     rcx, [rsp+148h+var_18]
0x180007d5f  xor     rcx, rsp; StackCookie
0x180007d62  call    __security_check_cookie
0x180007d67  add     rsp, 148h
0x180007d6e  retn
```
