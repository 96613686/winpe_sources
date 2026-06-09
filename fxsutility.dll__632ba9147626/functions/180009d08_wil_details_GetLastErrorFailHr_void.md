# wil::details::GetLastErrorFailHr(void)

- ea: `0x180009d08`
- end: `0x180009d59`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008828`
- `0x180008bcc`
- `0x180009044`

## callees

- `0x1800076d0`
- `0x180009d08`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009d13`
- `KERNEL32!GetLastError` at `0x180009d13`

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
0x180009d08  push    rbx
0x180009d0a  sub     rsp, 40h
0x180009d0e  mov     rbx, [rsp+48h]
0x180009d13  call    cs:__imp_GetLastError
0x180009d19  test    eax, eax
0x180009d1b  jnz     short loc_180009D47
0x180009d1d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180009d25  mov     [rsp+48h+var_20], rbx; __int64
0x180009d2a  mov     [rsp+48h+var_28], 0; __int64
0x180009d33  xor     r9d, r9d; int
0x180009d36  xor     r8d, r8d; int
0x180009d39  xor     edx, edx; int
0x180009d3b  xor     ecx, ecx; int
0x180009d3d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009d42  mov     eax, 29Ch
0x180009d47  test    eax, eax
0x180009d49  jle     short loc_180009D53
0x180009d4b  movzx   eax, ax
0x180009d4e  or      eax, 80070000h
0x180009d53  add     rsp, 40h
0x180009d57  pop     rbx
0x180009d58  retn
```
