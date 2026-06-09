# CActivityID::getCurrentCActivityID(CActivityID * const)

- ea: `0x18013ffb0`
- end: `0x180140206`
- name: `?getCurrentCActivityID@CActivityID@@SAHQEAU1@@Z`
- size: `598`
- prototype: `__int64 __fastcall(GUID *pguid)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18013f360`
- `0x180140210`
- `0x180196a00`

## callees

- `0x1800030c0`
- `0x180003d80`
- `0x18013ffb0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801400c4`
- `KERNEL32!GetLastError` at `0x18014019f`
- `KERNEL32!GetLastError` at `0x1801400c4`
- `KERNEL32!GetLastError` at `0x18014019f`
- `KERNEL32!TlsSetValue` at `0x180140174`
- `KERNEL32!TlsSetValue` at `0x180140174`
- `KERNEL32!TlsGetValue` at `0x1801400ac`
- `KERNEL32!TlsGetValue` at `0x1801400ac`
- `ole32!CoCreateGuid` at `0x180140143`
- `ole32!CoCreateGuid` at `0x180140143`

## pseudocode

```c
__int64 __fastcall CActivityID::getCurrentCActivityID(GUID *pguid)
{
  unsigned int Value; // eax
  __int64 (*v4)(void); // rsi
  unsigned int v5; // edi
  DWORD LastError; // eax
  __int64 (*v7)(void); // rax
  DWORD v8; // eax
  GUID v9; // [rsp+30h] [rbp-28h] BYREF

  if ( !g_pfnEventActivityIdControl )
  {
    if ( (bidGblFlags & 2) != 0 && off_180263AD0[0] && bidID != -1 )
    {
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        off_180260770[0],
        1895424,
        off_180263AD0[0],
        0);
      return 0;
    }
    return 0;
  }
  if ( g_dwCorrelationIndex == -1 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180263AD8[0] && bidID != -1 )
    {
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        off_180260770[0],
        1901568,
        off_180263AD8[0],
        0);
      return 0;
    }
    return 0;
  }
  Value = (unsigned int)TlsGetValue(g_dwCorrelationIndex);
  v4 = g_pfnEventActivityIdControl;
  v5 = Value;
  if ( Value )
  {
    v7 = g_pfnEventActivityIdControl;
    *pguid = GUID_NULL;
    if ( !((unsigned int (__fastcall *)(__int64, GUID *))v7)(1, pguid) )
    {
      pguid[1].Data1 = v5;
      return 1;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( (bidGblFlags & 2) != 0 && off_180263AE0[0] )
        bidTraceW(off_180260770[0], 1913856, off_180263AE0[0], LastError);
      return 0;
    }
    v9 = GUID_NULL;
    ((void (__fastcall *)(__int64, GUID *))v4)(1, &v9);
    if ( *(_OWORD *)&v9 != *(_OWORD *)&GUID_NULL
      || !CoCreateGuid(pguid) && !((unsigned int (__fastcall *)(__int64, GUID *))v4)(2, pguid) )
    {
      pguid[1].Data1 = 1;
      if ( TlsSetValue(g_dwCorrelationIndex, (LPVOID)1) )
        return 1;
    }
  }
  v8 = GetLastError();
  if ( (bidGblFlags & 2) == 0 || !off_180263AE8[0] )
    return 0;
  bidTraceW(off_180260770[0], 1951744, off_180263AE8[0], v8);
  return 0;
}

```

## disassembly

```asm
0x18013ffb0  mov     [rsp+arg_8], rbx
0x18013ffb5  mov     [rsp+arg_10], rsi
0x18013ffba  push    rdi
0x18013ffbb  sub     rsp, 50h
0x18013ffbf  mov     rax, cs:__security_cookie
0x18013ffc6  xor     rax, rsp
0x18013ffc9  mov     [rsp+58h+var_18], rax
0x18013ffce  cmp     cs:?g_pfnEventActivityIdControl@@3P6A_JXZEA, 0; __int64 (*g_pfnEventActivityIdControl)(void)
0x18013ffd6  mov     rbx, rcx
0x18013ffd9  jnz     short loc_18014003E
0x18013ffdb  test    byte ptr cs:_bidGblFlags, 2
0x18013ffe2  jz      loc_1801400FE
0x18013ffe8  mov     rax, cs:off_180263AD0; "<CActivityID::getCurrentCActivityID|ERR"...
0x18013ffef  test    rax, rax
0x18013fff2  jz      loc_1801400FE
0x18013fff8  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180140000  jz      loc_1801400FE
0x180140006  mov     r9, cs:off_180263AD0; "<CActivityID::getCurrentCActivityID|ERR"...
0x18014000d  mov     r8d, 1CEC00h
0x180140013  mov     rdx, cs:off_180260770; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\cl"...
0x18014001a  mov     rcx, cs:_bidID
0x180140021  mov     rax, cs:off_180248050
0x180140028  mov     [rsp+58h+var_38], 0
0x180140031  call    cs:__guard_dispatch_icall_fptr
0x180140037  xor     eax, eax
0x180140039  jmp     loc_1801401E9
0x18014003e  mov     ecx, cs:?g_dwCorrelationIndex@@3KA; dwTlsIndex
0x180140044  cmp     ecx, 0FFFFFFFFh
0x180140047  jnz     short loc_1801400AC
0x180140049  test    byte ptr cs:_bidGblFlags, 2
0x180140050  jz      loc_1801400FE
0x180140056  mov     rax, cs:off_180263AD8; "<CActivityID::getCurrentCActivityID|ERR"...
0x18014005d  test    rax, rax
0x180140060  jz      loc_1801400FE
0x180140066  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18014006e  jz      loc_1801400FE
0x180140074  mov     r9, cs:off_180263AD8; "<CActivityID::getCurrentCActivityID|ERR"...
0x18014007b  mov     r8d, 1D0400h
0x180140081  mov     rdx, cs:off_180260770; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\cl"...
0x180140088  mov     rcx, cs:_bidID
0x18014008f  mov     rax, cs:off_180248050
0x180140096  mov     [rsp+58h+var_38], 0
0x18014009f  call    cs:__guard_dispatch_icall_fptr
0x1801400a5  xor     eax, eax
0x1801400a7  jmp     loc_1801401E9
0x1801400ac  call    cs:__imp_TlsGetValue
0x1801400b2  mov     rsi, cs:?g_pfnEventActivityIdControl@@3P6A_JXZEA; __int64 (*g_pfnEventActivityIdControl)(void)
0x1801400b9  mov     rdi, rax
0x1801400bc  test    eax, eax
0x1801400be  jnz     loc_180140180
0x1801400c4  call    cs:__imp_GetLastError
0x1801400ca  test    eax, eax
0x1801400cc  jz      short loc_180140105
0x1801400ce  test    byte ptr cs:_bidGblFlags, 2
0x1801400d5  jz      short loc_1801400FE
0x1801400d7  mov     rcx, cs:off_180263AE0; "<CActivityID::getCurrentCActivityID|ERR"...
0x1801400de  test    rcx, rcx
0x1801400e1  jz      short loc_1801400FE
0x1801400e3  mov     r8, cs:off_180263AE0; "<CActivityID::getCurrentCActivityID|ERR"...
0x1801400ea  mov     r9d, eax
0x1801400ed  mov     rcx, cs:off_180260770; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\cl"...
0x1801400f4  mov     edx, 1D3400h
0x1801400f9  call    _bidTraceW
0x1801400fe  xor     eax, eax
0x180140100  jmp     loc_1801401E9
0x180140105  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014010c  lea     rdx, [rsp+58h+var_28]
0x180140111  mov     ecx, 1
0x180140116  mov     rax, rsi
0x180140119  movups  [rsp+58h+var_28], xmm0
0x18014011e  call    cs:__guard_dispatch_icall_fptr
0x180140124  mov     rax, qword ptr [rsp+58h+var_28]
0x180140129  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180140130  jnz     short loc_180140162
0x180140132  mov     rax, qword ptr [rsp+58h+var_28+8]
0x180140137  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18014013e  jnz     short loc_180140162
0x180140140  mov     rcx, rbx; pguid
0x180140143  call    cs:__imp_CoCreateGuid
0x180140149  test    eax, eax
0x18014014b  jnz     short loc_18014019F
0x18014014d  mov     rdx, rbx
0x180140150  mov     ecx, 2
0x180140155  mov     rax, rsi
0x180140158  call    cs:__guard_dispatch_icall_fptr
0x18014015e  test    eax, eax
0x180140160  jnz     short loc_18014019F
0x180140162  mov     dword ptr [rbx+10h], 1
0x180140169  mov     edx, 1; lpTlsValue
0x18014016e  mov     ecx, cs:?g_dwCorrelationIndex@@3KA; dwTlsIndex
0x180140174  call    cs:__imp_TlsSetValue
0x18014017a  test    eax, eax
0x18014017c  jz      short loc_18014019F
0x18014017e  jmp     short loc_1801401E4
0x180140180  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180140187  mov     rdx, rbx
0x18014018a  mov     ecx, 1
0x18014018f  mov     rax, rsi
0x180140192  movups  xmmword ptr [rbx], xmm0
0x180140195  call    cs:__guard_dispatch_icall_fptr
0x18014019b  test    eax, eax
0x18014019d  jz      short loc_1801401E1
0x18014019f  call    cs:__imp_GetLastError
0x1801401a5  test    byte ptr cs:_bidGblFlags, 2
0x1801401ac  jz      loc_1801400FE
0x1801401b2  mov     rcx, cs:off_180263AE8; "<CActivityID::getCurrentCActivityID|ERR"...
0x1801401b9  test    rcx, rcx
0x1801401bc  jz      loc_1801400FE
0x1801401c2  mov     r8, cs:off_180263AE8; "<CActivityID::getCurrentCActivityID|ERR"...
0x1801401c9  mov     r9d, eax
0x1801401cc  mov     rcx, cs:off_180260770; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\cl"...
0x1801401d3  mov     edx, 1DC800h
0x1801401d8  call    _bidTraceW
0x1801401dd  xor     eax, eax
0x1801401df  jmp     short loc_1801401E9
0x1801401e1  mov     [rbx+10h], edi
0x1801401e4  mov     eax, 1
0x1801401e9  mov     rcx, [rsp+58h+var_18]
0x1801401ee  xor     rcx, rsp; StackCookie
0x1801401f1  call    __security_check_cookie
0x1801401f6  mov     rbx, [rsp+58h+arg_8]
0x1801401fb  mov     rsi, [rsp+58h+arg_10]
0x180140200  add     rsp, 50h
0x180140204  pop     rdi
0x180140205  retn
```
