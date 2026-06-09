# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800030e8`
- end: `0x180003136`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024d4`
- `0x180002878`

## callees

- `0x180001c98`
- `0x1800030e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030ec`

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
0x1800030e8  sub     rsp, 48h
0x1800030ec  call    cs:__imp_GetLastError
0x1800030f2  test    eax, eax
0x1800030f4  jnz     short loc_180003127
0x1800030f6  mov     rax, [rsp+48h]
0x1800030fb  xor     r9d, r9d; int
0x1800030fe  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180003106  xor     r8d, r8d; int
0x180003109  mov     [rsp+48h+var_20], rax; __int64
0x18000310e  xor     edx, edx; int
0x180003110  xor     ecx, ecx; int
0x180003112  mov     [rsp+48h+var_28], 0; __int64
0x18000311b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003120  mov     eax, 29Ch
0x180003125  jmp     short loc_180003129
0x180003127  jle     short loc_180003131
0x180003129  movzx   eax, ax
0x18000312c  or      eax, 80070000h
0x180003131  add     rsp, 48h
0x180003135  retn
```
