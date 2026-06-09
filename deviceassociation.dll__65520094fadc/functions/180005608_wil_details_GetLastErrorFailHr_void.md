# wil::details::GetLastErrorFailHr(void)

- ea: `0x180005608`
- end: `0x180005656`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000410c`
- `0x1800044b0`
- `0x180004880`

## callees

- `0x180003310`
- `0x180005608`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000560c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000560c`

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
0x180005608  sub     rsp, 48h
0x18000560c  call    cs:__imp_GetLastError
0x180005612  test    eax, eax
0x180005614  jnz     short loc_180005647
0x180005616  mov     rax, [rsp+48h]
0x18000561b  xor     r9d, r9d; int
0x18000561e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180005626  xor     r8d, r8d; int
0x180005629  mov     [rsp+48h+var_20], rax; __int64
0x18000562e  xor     edx, edx; int
0x180005630  xor     ecx, ecx; int
0x180005632  mov     [rsp+48h+var_28], 0; __int64
0x18000563b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005640  mov     eax, 29Ch
0x180005645  jmp     short loc_180005649
0x180005647  jle     short loc_180005651
0x180005649  movzx   eax, ax
0x18000564c  or      eax, 80070000h
0x180005651  add     rsp, 48h
0x180005655  retn
```
