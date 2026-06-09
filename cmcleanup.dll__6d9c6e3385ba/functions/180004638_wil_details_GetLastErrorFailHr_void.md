# wil::details::GetLastErrorFailHr(void)

- ea: `0x180004638`
- end: `0x180004689`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b0c`
- `0x180003518`
- `0x180003964`

## callees

- `0x180002428`
- `0x180004638`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004643`

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
0x180004638  push    rbx
0x18000463a  sub     rsp, 40h
0x18000463e  mov     rbx, [rsp+48h]
0x180004643  call    cs:__imp_GetLastError
0x180004649  test    eax, eax
0x18000464b  jnz     short loc_180004677
0x18000464d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004655  mov     [rsp+48h+var_20], rbx; __int64
0x18000465a  mov     [rsp+48h+var_28], 0; __int64
0x180004663  xor     r9d, r9d; int
0x180004666  xor     r8d, r8d; int
0x180004669  xor     edx, edx; int
0x18000466b  xor     ecx, ecx; int
0x18000466d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004672  mov     eax, 29Ch
0x180004677  test    eax, eax
0x180004679  jle     short loc_180004683
0x18000467b  movzx   eax, ax
0x18000467e  or      eax, 80070000h
0x180004683  add     rsp, 40h
0x180004687  pop     rbx
0x180004688  retn
```
