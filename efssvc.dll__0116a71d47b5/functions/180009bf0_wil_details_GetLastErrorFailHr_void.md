# wil::details::GetLastErrorFailHr(void)

- ea: `0x180009bf0`
- end: `0x180009c3e`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008fc8`
- `0x18000936c`

## callees

- `0x18000872c`
- `0x180009bf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bf4`

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
0x180009bf0  sub     rsp, 48h
0x180009bf4  call    cs:__imp_GetLastError
0x180009bfa  test    eax, eax
0x180009bfc  jnz     short loc_180009C2F
0x180009bfe  mov     rax, [rsp+48h]
0x180009c03  xor     r9d, r9d; int
0x180009c06  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180009c0e  xor     r8d, r8d; int
0x180009c11  mov     [rsp+48h+var_20], rax; __int64
0x180009c16  xor     edx, edx; int
0x180009c18  xor     ecx, ecx; int
0x180009c1a  mov     [rsp+48h+var_28], 0; __int64
0x180009c23  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009c28  mov     eax, 29Ch
0x180009c2d  jmp     short loc_180009C31
0x180009c2f  jle     short loc_180009C39
0x180009c31  movzx   eax, ax
0x180009c34  or      eax, 80070000h
0x180009c39  add     rsp, 48h
0x180009c3d  retn
```
