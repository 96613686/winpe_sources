# wil::details::PrintLoggingMessage(ushort *,unsigned __int64,char const *,char *)

- ea: `0x140008348`
- end: `0x1400083ef`
- name: `?PrintLoggingMessage@details@wil@@YAXPEAG_KPEBDPEAD@Z`
- size: `167`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned __int16 *, unsigned __int64, const char *, char *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140003af8`
- `0x140003bb4`
- `0x140010e84`
- `0x140011688`

## callees

- `0x140002600`
- `0x140003198`
- `0x140008348`
- `0x14000a30c`
- `0x1400130e0`

## pseudocode

```c
void __fastcall wil::details::PrintLoggingMessage(wil::details *this, unsigned __int16 *a2, __int64 a3, va_list a4)
{
  wchar_t Format[2048]; // [rsp+20h] [rbp-1018h] BYREF

  if ( a3 )
  {
    if ( a4 )
    {
      StringCchPrintfW(Format, 0x800u, L"%hs", a3);
      if ( (unsigned int)vsnwprintf((wchar_t *)this, 0x7FFu, Format, a4) > 0x7FE )
        *((_WORD *)this + 2047) = 0;
    }
    else
    {
      StringCchPrintfW((unsigned __int16 *)this, 0x800u, L"%hs", a3);
    }
  }
  else
  {
    *(_WORD *)this = 0;
  }
}

```

## disassembly

```asm
0x140008348  mov     [rsp+arg_8], rbx
0x14000834d  push    rdi
0x14000834e  mov     eax, 1030h
0x140008353  call    _alloca_probe
0x140008358  sub     rsp, rax
0x14000835b  mov     rax, cs:__security_cookie
0x140008362  xor     rax, rsp
0x140008365  mov     [rsp+1038h+var_18], rax
0x14000836d  mov     rdi, r9
0x140008370  mov     rbx, rcx
0x140008373  test    r8, r8
0x140008376  jnz     short loc_14000837F
0x140008378  xor     eax, eax
0x14000837a  mov     [rcx], ax
0x14000837d  jmp     short loc_1400083CE
0x14000837f  mov     r9, r8
0x140008382  lea     r8, aHs_0; "%hs"
0x140008389  mov     edx, 800h; unsigned __int64
0x14000838e  test    rdi, rdi
0x140008391  jnz     short loc_14000839A
0x140008393  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008398  jmp     short loc_1400083CE
0x14000839a  lea     rcx, [rsp+1038h+Format]; unsigned __int16 *
0x14000839f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400083a4  mov     r9, rdi; Args
0x1400083a7  lea     r8, [rsp+1038h+Format]; Format
0x1400083ac  mov     edi, 7FFh
0x1400083b1  mov     rcx, rbx; Buffer
0x1400083b4  mov     edx, edi; BufferCount
0x1400083b6  call    _vsnwprintf
0x1400083bb  test    eax, eax
0x1400083bd  js      short loc_1400083C5
0x1400083bf  cmp     eax, edi
0x1400083c1  ja      short loc_1400083C5
0x1400083c3  jnz     short loc_1400083CE
0x1400083c5  xor     eax, eax
0x1400083c7  mov     [rbx+0FFEh], ax
0x1400083ce  mov     rcx, [rsp+1038h+var_18]
0x1400083d6  xor     rcx, rsp; StackCookie
0x1400083d9  call    __security_check_cookie
0x1400083de  mov     rbx, [rsp+1038h+arg_8]
0x1400083e6  add     rsp, 1030h
0x1400083ed  pop     rdi
0x1400083ee  retn
```
