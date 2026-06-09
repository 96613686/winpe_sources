# eksvcLogStringA(char const *,long,ushort const *)

- ea: `0x180007bcc`
- end: `0x180007cde`
- name: `?eksvcLogStringA@@YAXPEBDJPEBG@Z`
- size: `274`
- prototype: `void __fastcall(const char *, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180003750`
- `0x180007ce4`

## callees

- `0x1800078e8`
- `0x180007b38`
- `0x180007bcc`
- `0x18000a800`

## import_xrefs

- `msvcrt!fprintf` at `0x180007c95`
- `msvcrt!fprintf` at `0x180007c95`
- `msvcrt!fseek` at `0x180007c79`
- `msvcrt!fseek` at `0x180007c79`
- `msvcrt!fflush` at `0x180007ca2`
- `msvcrt!fflush` at `0x180007ca2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007cb0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007cbd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007cb0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180007cbd`

## pseudocode

```c
void __fastcall eksvcLogStringA(const char *a1, unsigned int a2, const unsigned __int16 *a3)
{
  const char *v6; // r8
  const char *v7; // r8
  char v8[80]; // [rsp+40h] [rbp-188h] BYREF
  CHAR OutputString[272]; // [rsp+90h] [rbp-138h] BYREF

  eksvcGetTime(v8, a2);
  if ( a1 )
  {
    v7 = "%hs: %hs: error 0x%08x (%d) (%ws)";
    if ( !a3 )
      v7 = "%hs: %hs: error 0x%08x (%d)";
    StringCchPrintfA(OutputString, 0x104u, v7, a1, v8, a2, a2, a3);
  }
  else
  {
    v6 = "%hs: %ws";
    if ( !a3 )
      v6 = "%hs";
    StringCchPrintfA(OutputString, 0x104u, v6, v8, a3);
  }
  if ( Stream )
  {
    fseek(Stream, 0, 2);
    fprintf(Stream, "%hs\n", OutputString);
    fflush(Stream);
  }
  OutputDebugStringA(OutputString);
  OutputDebugStringA("\n");
}

```

## disassembly

```asm
0x180007bcc  push    rbx
0x180007bce  push    rsi
0x180007bcf  push    rdi
0x180007bd0  sub     rsp, 1B0h
0x180007bd7  mov     rax, cs:__security_cookie
0x180007bde  xor     rax, rsp
0x180007be1  mov     [rsp+1C8h+var_28], rax
0x180007be9  mov     rdi, rcx
0x180007bec  mov     rbx, r8
0x180007bef  lea     rcx, [rsp+1C8h+var_188]; char *
0x180007bf4  mov     esi, edx
0x180007bf6  call    ?eksvcGetTime@@YAXPEADK@Z; eksvcGetTime(char *,ulong)
0x180007bfb  lea     rcx, [rsp+1C8h+OutputString]; char *
0x180007c03  mov     edx, 104h; unsigned __int64
0x180007c08  test    rdi, rdi
0x180007c0b  jnz     short loc_180007C33
0x180007c0d  test    rbx, rbx
0x180007c10  mov     [rsp+1C8h+var_1A8], rbx
0x180007c15  lea     rax, aHs; "%hs"
0x180007c1c  lea     r8, aHsWs; "%hs: %ws"
0x180007c23  cmovz   r8, rax; char *
0x180007c27  lea     r9, [rsp+1C8h+var_188]
0x180007c2c  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007c31  jmp     short loc_180007C67
0x180007c33  mov     [rsp+1C8h+var_190], rbx
0x180007c38  lea     rax, aHsHsError0x08x_0; "%hs: %hs: error 0x%08x (%d)"
0x180007c3f  test    rbx, rbx
0x180007c42  mov     [rsp+1C8h+var_198], esi
0x180007c46  lea     r8, aHsHsError0x08x; "%hs: %hs: error 0x%08x (%d) (%ws)"
0x180007c4d  mov     [rsp+1C8h+var_1A0], esi
0x180007c51  cmovz   r8, rax; char *
0x180007c55  mov     r9, rdi
0x180007c58  lea     rax, [rsp+1C8h+var_188]
0x180007c5d  mov     [rsp+1C8h+var_1A8], rax
0x180007c62  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007c67  mov     rcx, cs:Stream; Stream
0x180007c6e  test    rcx, rcx
0x180007c71  jz      short loc_180007CA8
0x180007c73  xor     edx, edx; Offset
0x180007c75  lea     r8d, [rdx+2]; Origin
0x180007c79  call    cs:__imp_fseek
0x180007c7f  mov     rcx, cs:Stream; Stream
0x180007c86  lea     r8, [rsp+1C8h+OutputString]
0x180007c8e  lea     rdx, Format; "%hs\n"
0x180007c95  call    cs:__imp_fprintf
0x180007c9b  mov     rcx, cs:Stream; Stream
0x180007ca2  call    cs:__imp_fflush
0x180007ca8  lea     rcx, [rsp+1C8h+OutputString]; lpOutputString
0x180007cb0  call    cs:__imp_OutputDebugStringA
0x180007cb6  lea     rcx, OutputString; "\n"
0x180007cbd  call    cs:__imp_OutputDebugStringA
0x180007cc3  mov     rcx, [rsp+1C8h+var_28]
0x180007ccb  xor     rcx, rsp; StackCookie
0x180007cce  call    __security_check_cookie
0x180007cd3  add     rsp, 1B0h
0x180007cda  pop     rdi
0x180007cdb  pop     rsi
0x180007cdc  pop     rbx
0x180007cdd  retn
```
