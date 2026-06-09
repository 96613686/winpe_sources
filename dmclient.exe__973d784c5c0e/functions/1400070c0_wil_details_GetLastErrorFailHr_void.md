# wil::details::GetLastErrorFailHr(void)

- ea: `0x1400070c0`
- end: `0x140007118`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `88`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ce4`
- `0x14000c2a4`
- `0x14000c340`
- `0x140015fb4`

## callees

- `0x1400034f8`
- `0x1400070c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070cb`

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
0x1400070c0  push    rbx
0x1400070c2  sub     rsp, 40h
0x1400070c6  mov     rbx, [rsp+48h]
0x1400070cb  call    cs:__imp_GetLastError
0x1400070d2  nop     dword ptr [rax+rax+00h]
0x1400070d7  test    eax, eax
0x1400070d9  jnz     short loc_140007105
0x1400070db  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1400070e3  mov     [rsp+48h+var_20], rbx; __int64
0x1400070e8  mov     [rsp+48h+var_28], 0; __int64
0x1400070f1  xor     r9d, r9d; int
0x1400070f4  xor     r8d, r8d; int
0x1400070f7  xor     edx, edx; int
0x1400070f9  xor     ecx, ecx; int
0x1400070fb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140007100  mov     eax, 29Ch
0x140007105  test    eax, eax
0x140007107  jle     short loc_140007111
0x140007109  movzx   eax, ax
0x14000710c  or      eax, 80070000h
0x140007111  add     rsp, 40h
0x140007115  pop     rbx
0x140007116  retn
```
