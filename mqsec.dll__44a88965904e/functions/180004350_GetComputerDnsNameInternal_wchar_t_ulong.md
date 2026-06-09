# GetComputerDnsNameInternal(wchar_t *,ulong *)

- ea: `0x180004350`
- end: `0x1800043c4`
- name: `?GetComputerDnsNameInternal@@YAJPEA_WPEAK@Z`
- size: `116`
- prototype: `__int64 __fastcall(LPWSTR lpsz, LPDWORD nSize)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004350`
- `0x1800049ac`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x180004364`
- `KERNEL32!GetComputerNameExW` at `0x180004364`
- `KERNEL32!GetLastError` at `0x180004394`
- `KERNEL32!GetLastError` at `0x180004394`
- `USER32!CharLowerW` at `0x180004371`
- `USER32!CharLowerW` at `0x180004371`

## pseudocode

```c
__int64 __fastcall GetComputerDnsNameInternal(LPWSTR lpsz, LPDWORD nSize)
{
  DWORD LastError; // eax

  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, lpsz, nSize) )
  {
    CharLowerW(lpsz);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_2d00db894b443409422f6842f1d0ba08_Traceguids, LastError);
    }
    return 3222142977LL;
  }
}

```

## disassembly

```asm
0x180004350  push    rbx
0x180004352  sub     rsp, 20h
0x180004356  mov     r8, rdx; nSize
0x180004359  mov     rbx, rcx
0x18000435c  mov     rdx, rcx; lpBuffer
0x18000435f  mov     ecx, 3; NameType
0x180004364  call    cs:__imp_GetComputerNameExW
0x18000436a  test    eax, eax
0x18000436c  jz      short loc_18000437B
0x18000436e  mov     rcx, rbx; lpsz
0x180004371  call    cs:__imp_CharLowerW
0x180004377  xor     eax, eax
0x180004379  jmp     short loc_1800043BE
0x18000437b  mov     rax, cs:WPP_GLOBAL_Control
0x180004382  lea     rcx, WPP_GLOBAL_Control
0x180004389  cmp     rax, rcx
0x18000438c  jz      short loc_1800043B9
0x18000438e  test    byte ptr [rax+1Ch], 1
0x180004392  jz      short loc_1800043B9
0x180004394  call    cs:__imp_GetLastError
0x18000439a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043a1  lea     r8, WPP_2d00db894b443409422f6842f1d0ba08_Traceguids
0x1800043a8  mov     edx, 0Ch
0x1800043ad  mov     r9d, eax
0x1800043b0  mov     rcx, [rcx+10h]
0x1800043b4  call    WPP_SF_d
0x1800043b9  mov     eax, 0C00E0001h
0x1800043be  add     rsp, 20h
0x1800043c2  pop     rbx
0x1800043c3  retn
```
