# wil::details::GetLastErrorFailHr(void)

- ea: `0x1400036c8`
- end: `0x140003716`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002ab8`
- `0x140002e5c`

## callees

- `0x14000227c`
- `0x1400036c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400036cc`
- `KERNEL32!GetLastError` at `0x1400036cc`

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
0x1400036c8  sub     rsp, 48h
0x1400036cc  call    cs:__imp_GetLastError
0x1400036d2  test    eax, eax
0x1400036d4  jnz     short loc_140003707
0x1400036d6  mov     rax, [rsp+48h]
0x1400036db  xor     r9d, r9d; int
0x1400036de  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1400036e6  xor     r8d, r8d; int
0x1400036e9  mov     [rsp+48h+var_20], rax; __int64
0x1400036ee  xor     edx, edx; int
0x1400036f0  xor     ecx, ecx; int
0x1400036f2  mov     [rsp+48h+var_28], 0; __int64
0x1400036fb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140003700  mov     eax, 29Ch
0x140003705  jmp     short loc_140003709
0x140003707  jle     short loc_140003711
0x140003709  movzx   eax, ax
0x14000370c  or      eax, 80070000h
0x140003711  add     rsp, 48h
0x140003715  retn
```
