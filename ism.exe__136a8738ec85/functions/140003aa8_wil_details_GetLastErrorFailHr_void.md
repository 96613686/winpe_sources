# wil::details::GetLastErrorFailHr(void)

- ea: `0x140003aa8`
- end: `0x140003af9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002e78`
- `0x14000321c`

## callees

- `0x1400020a4`
- `0x140003aa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ab3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  wil::details *v2; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  result = GetLastError();
  if ( !result )
  {
    LODWORD(v2) = -2147024228;
    wil::details::ReportFailure_Hr<2>(0, 0, 0, 0, 0, retaddr, v2);
    result = 668;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140003aa8  push    rbx
0x140003aaa  sub     rsp, 40h
0x140003aae  mov     rbx, [rsp+48h]
0x140003ab3  call    cs:__imp_GetLastError
0x140003ab9  test    eax, eax
0x140003abb  jnz     short loc_140003AE7
0x140003abd  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140003ac5  mov     [rsp+48h+var_20], rbx; __int64
0x140003aca  mov     [rsp+48h+var_28], 0; __int64
0x140003ad3  xor     r9d, r9d; int
0x140003ad6  xor     r8d, r8d; int
0x140003ad9  xor     edx, edx; int
0x140003adb  xor     ecx, ecx; int
0x140003add  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140003ae2  mov     eax, 29Ch
0x140003ae7  test    eax, eax
0x140003ae9  jle     short loc_140003AF3
0x140003aeb  movzx   eax, ax
0x140003aee  or      eax, 80070000h
0x140003af3  add     rsp, 40h
0x140003af7  pop     rbx
0x140003af8  retn
```
