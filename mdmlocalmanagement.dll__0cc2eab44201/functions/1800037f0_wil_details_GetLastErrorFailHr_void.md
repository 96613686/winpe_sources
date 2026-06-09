# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800037f0`
- end: `0x180003848`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `88`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f5c`
- `0x180005604`

## callees

- `0x1800022e8`
- `0x1800037f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800037f0  push    rbx
0x1800037f2  sub     rsp, 40h
0x1800037f6  mov     rbx, [rsp+48h]
0x1800037fb  call    cs:__imp_GetLastError
0x180003802  nop     dword ptr [rax+rax+00h]
0x180003807  test    eax, eax
0x180003809  jnz     short loc_180003835
0x18000380b  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180003813  mov     [rsp+48h+var_20], rbx; __int64
0x180003818  mov     [rsp+48h+var_28], 0; __int64
0x180003821  xor     r9d, r9d; int
0x180003824  xor     r8d, r8d; int
0x180003827  xor     edx, edx; int
0x180003829  xor     ecx, ecx; int
0x18000382b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003830  mov     eax, 29Ch
0x180003835  test    eax, eax
0x180003837  jle     short loc_180003841
0x180003839  movzx   eax, ax
0x18000383c  or      eax, 80070000h
0x180003841  add     rsp, 40h
0x180003845  pop     rbx
0x180003846  retn
```
