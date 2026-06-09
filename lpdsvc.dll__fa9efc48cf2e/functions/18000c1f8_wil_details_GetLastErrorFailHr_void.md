# wil::details::GetLastErrorFailHr(void)

- ea: `0x18000c1f8`
- end: `0x18000c246`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b59c`
- `0x18000b940`

## callees

- `0x18000ad60`
- `0x18000c1f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c1fc`
- `KERNEL32!GetLastError` at `0x18000c1fc`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  wil::details *v2; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  result = GetLastError();
  if ( result )
  {
    if ( result <= 0 )
      return result;
  }
  else
  {
    LODWORD(v2) = -2147024228;
    wil::details::ReportFailure_Hr<2>(0, 0, 0, 0, 0, retaddr, v2);
    LOWORD(result) = 668;
  }
  return (unsigned __int16)result | 0x80070000;
}

```

## disassembly

```asm
0x18000c1f8  sub     rsp, 48h
0x18000c1fc  call    cs:__imp_GetLastError
0x18000c202  test    eax, eax
0x18000c204  jnz     short loc_18000C237
0x18000c206  mov     rax, [rsp+48h]
0x18000c20b  xor     r9d, r9d; int
0x18000c20e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x18000c216  xor     r8d, r8d; int
0x18000c219  mov     [rsp+48h+var_20], rax; __int64
0x18000c21e  xor     edx, edx; int
0x18000c220  xor     ecx, ecx; int
0x18000c222  mov     [rsp+48h+var_28], 0; __int64
0x18000c22b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000c230  mov     eax, 29Ch
0x18000c235  jmp     short loc_18000C239
0x18000c237  jle     short loc_18000C241
0x18000c239  movzx   eax, ax
0x18000c23c  or      eax, 80070000h
0x18000c241  add     rsp, 48h
0x18000c245  retn
```
