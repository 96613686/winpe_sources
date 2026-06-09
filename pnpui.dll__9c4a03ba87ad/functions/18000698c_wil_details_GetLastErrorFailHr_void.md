# wil::details::GetLastErrorFailHr(void)

- ea: `0x18000698c`
- end: `0x1800069da`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d1c`
- `0x1800050c0`
- `0x1800056f4`

## callees

- `0x180003dd4`
- `0x18000698c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006990`

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
0x18000698c  sub     rsp, 48h
0x180006990  call    cs:__imp_GetLastError
0x180006996  test    eax, eax
0x180006998  jnz     short loc_1800069CB
0x18000699a  mov     rax, [rsp+48h]
0x18000699f  xor     r9d, r9d; int
0x1800069a2  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1800069aa  xor     r8d, r8d; int
0x1800069ad  mov     [rsp+48h+var_20], rax; __int64
0x1800069b2  xor     edx, edx; int
0x1800069b4  xor     ecx, ecx; int
0x1800069b6  mov     [rsp+48h+var_28], 0; __int64
0x1800069bf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800069c4  mov     eax, 29Ch
0x1800069c9  jmp     short loc_1800069CD
0x1800069cb  jle     short loc_1800069D5
0x1800069cd  movzx   eax, ax
0x1800069d0  or      eax, 80070000h
0x1800069d5  add     rsp, 48h
0x1800069d9  retn
```
