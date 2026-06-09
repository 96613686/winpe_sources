# GetComputerNameInternal(wchar_t *,ulong *)

- ea: `0x1800043d0`
- end: `0x180004439`
- name: `?GetComputerNameInternal@@YAJPEA_WPEAK@Z`
- size: `105`
- prototype: `__int64 __fastcall(LPWSTR lpsz, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013b18`
- `0x18002b590`

## callees

- `0x1800043d0`
- `0x1800049ac`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x1800043d9`
- `KERNEL32!GetComputerNameW` at `0x1800043d9`
- `KERNEL32!GetLastError` at `0x180004409`
- `KERNEL32!GetLastError` at `0x180004409`
- `USER32!CharLowerW` at `0x1800043e6`
- `USER32!CharLowerW` at `0x1800043e6`

## pseudocode

```c
__int64 __fastcall GetComputerNameInternal(LPWSTR lpsz, unsigned int *a2)
{
  DWORD LastError; // eax

  if ( GetComputerNameW(lpsz, a2) )
  {
    CharLowerW(lpsz);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_2d00db894b443409422f6842f1d0ba08_Traceguids, LastError);
    }
    return 3222142977LL;
  }
}

```

## disassembly

```asm
0x1800043d0  push    rbx
0x1800043d2  sub     rsp, 20h
0x1800043d6  mov     rbx, rcx
0x1800043d9  call    cs:__imp_GetComputerNameW
0x1800043df  test    eax, eax
0x1800043e1  jz      short loc_1800043F0
0x1800043e3  mov     rcx, rbx; lpsz
0x1800043e6  call    cs:__imp_CharLowerW
0x1800043ec  xor     eax, eax
0x1800043ee  jmp     short loc_180004433
0x1800043f0  mov     rax, cs:WPP_GLOBAL_Control
0x1800043f7  lea     rcx, WPP_GLOBAL_Control
0x1800043fe  cmp     rax, rcx
0x180004401  jz      short loc_18000442E
0x180004403  test    byte ptr [rax+1Ch], 1
0x180004407  jz      short loc_18000442E
0x180004409  call    cs:__imp_GetLastError
0x18000440f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004416  lea     r8, WPP_2d00db894b443409422f6842f1d0ba08_Traceguids
0x18000441d  mov     edx, 0Bh
0x180004422  mov     r9d, eax
0x180004425  mov     rcx, [rcx+10h]
0x180004429  call    WPP_SF_d
0x18000442e  mov     eax, 0C00E0001h
0x180004433  add     rsp, 20h
0x180004437  pop     rbx
0x180004438  retn
```
