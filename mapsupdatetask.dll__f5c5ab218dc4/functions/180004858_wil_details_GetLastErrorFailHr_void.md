# wil::details::GetLastErrorFailHr(void)

- ea: `0x180004858`
- end: `0x1800048a9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037d4`
- `0x180003bb4`

## callees

- `0x1800029fc`
- `0x180004858`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004863`

## pseudocode

```c
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
0x180004858  push    rbx
0x18000485a  sub     rsp, 40h
0x18000485e  mov     rbx, [rsp+48h]
0x180004863  call    cs:__imp_GetLastError
0x180004869  test    eax, eax
0x18000486b  jnz     short loc_180004897
0x18000486d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004875  mov     [rsp+48h+var_20], rbx; __int64
0x18000487a  mov     [rsp+48h+var_28], 0; __int64
0x180004883  xor     r9d, r9d; int
0x180004886  xor     r8d, r8d; int
0x180004889  xor     edx, edx; int
0x18000488b  xor     ecx, ecx; int
0x18000488d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004892  mov     eax, 29Ch
0x180004897  test    eax, eax
0x180004899  jle     short loc_1800048A3
0x18000489b  movzx   eax, ax
0x18000489e  or      eax, 80070000h
0x1800048a3  add     rsp, 40h
0x1800048a7  pop     rbx
0x1800048a8  retn
```
