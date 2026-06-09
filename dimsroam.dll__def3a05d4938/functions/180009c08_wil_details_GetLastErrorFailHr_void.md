# wil::details::GetLastErrorFailHr(void)

- ea: `0x180009c08`
- end: `0x180009c56`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000870c`
- `0x180008ab0`
- `0x180008e80`

## callees

- `0x180007910`
- `0x180009c08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c0c`

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
0x180009c08  sub     rsp, 48h
0x180009c0c  call    cs:__imp_GetLastError
0x180009c12  test    eax, eax
0x180009c14  jnz     short loc_180009C47
0x180009c16  mov     rax, [rsp+48h]
0x180009c1b  xor     r9d, r9d; int
0x180009c1e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180009c26  xor     r8d, r8d; int
0x180009c29  mov     [rsp+48h+var_20], rax; __int64
0x180009c2e  xor     edx, edx; int
0x180009c30  xor     ecx, ecx; int
0x180009c32  mov     [rsp+48h+var_28], 0; __int64
0x180009c3b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009c40  mov     eax, 29Ch
0x180009c45  jmp     short loc_180009C49
0x180009c47  jle     short loc_180009C51
0x180009c49  movzx   eax, ax
0x180009c4c  or      eax, 80070000h
0x180009c51  add     rsp, 48h
0x180009c55  retn
```
