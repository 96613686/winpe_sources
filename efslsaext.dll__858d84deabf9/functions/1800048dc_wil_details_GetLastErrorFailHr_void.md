# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800048dc`
- end: `0x18000492a`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003bf8`
- `0x180003f9c`
- `0x18000cf30`

## callees

- `0x180003214`
- `0x1800048dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048e0`

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
0x1800048dc  sub     rsp, 48h
0x1800048e0  call    cs:__imp_GetLastError
0x1800048e6  test    eax, eax
0x1800048e8  jnz     short loc_18000491B
0x1800048ea  mov     rax, [rsp+48h]
0x1800048ef  xor     r9d, r9d; int
0x1800048f2  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1800048fa  xor     r8d, r8d; int
0x1800048fd  mov     [rsp+48h+var_20], rax; __int64
0x180004902  xor     edx, edx; int
0x180004904  xor     ecx, ecx; int
0x180004906  mov     [rsp+48h+var_28], 0; __int64
0x18000490f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004914  mov     eax, 29Ch
0x180004919  jmp     short loc_18000491D
0x18000491b  jle     short loc_180004925
0x18000491d  movzx   eax, ax
0x180004920  or      eax, 80070000h
0x180004925  add     rsp, 48h
0x180004929  retn
```
