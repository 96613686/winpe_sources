# wil::details::GetLastErrorFailHr(void)

- ea: `0x140006fb8`
- end: `0x140007009`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140004bd0`
- `0x140005600`
- `0x14000bef0`
- `0x140013330`

## callees

- `0x1400034b0`
- `0x140006fb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006fc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006fc3`

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
0x140006fb8  push    rbx
0x140006fba  sub     rsp, 40h
0x140006fbe  mov     rbx, [rsp+48h]
0x140006fc3  call    cs:__imp_GetLastError
0x140006fc9  test    eax, eax
0x140006fcb  jnz     short loc_140006FF7
0x140006fcd  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140006fd5  mov     [rsp+48h+var_20], rbx; __int64
0x140006fda  mov     [rsp+48h+var_28], 0; __int64
0x140006fe3  xor     r9d, r9d; int
0x140006fe6  xor     r8d, r8d; int
0x140006fe9  xor     edx, edx; int
0x140006feb  xor     ecx, ecx; int
0x140006fed  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006ff2  mov     eax, 29Ch
0x140006ff7  test    eax, eax
0x140006ff9  jle     short loc_140007003
0x140006ffb  movzx   eax, ax
0x140006ffe  or      eax, 80070000h
0x140007003  add     rsp, 40h
0x140007007  pop     rbx
0x140007008  retn
```
