# StgpGetTempFileName(ushort *,unsigned __int64,int)

- ea: `0x18003aa00`
- end: `0x18003aac7`
- name: `?StgpGetTempFileName@@YAJPEAG_KH@Z`
- size: `199`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001defc`
- `0x180039ef0`

## callees

- `0x18001fd08`
- `0x180026bc4`
- `0x18003aa00`
- `0x180049df0`
- `0x18005d63c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa39`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18003aa1d`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18003aa1d`
- `ext-ms-win-cng-rng-l1-1-0!ProcessPrng` at `0x18003aa64`
- `ext-ms-win-cng-rng-l1-1-0!ProcessPrng` at `0x18003aa64`

## pseudocode

```c
__int64 __fastcall StgpGetTempFileName(unsigned __int16 *a1, __int64 a2, int a3)
{
  unsigned int TempPath2W; // eax
  __int64 v6; // rbx
  __int64 result; // rax
  DWORD LastError; // eax
  __int64 v9; // [rsp+68h] [rbp+10h] BYREF

  v9 = a2;
  TempPath2W = GetTempPath2W(260, a1);
  v6 = TempPath2W;
  if ( TempPath2W )
  {
    if ( (unsigned __int64)TempPath2W + 24 < 0x104 )
      goto LABEL_7;
    result = 2147680259LL;
  }
  else
  {
    LastError = GetLastError();
    result = Win32ErrorToScode(LastError);
  }
  if ( !a3 )
    return result;
  *a1 = 46;
  v6 = 1;
LABEL_7:
  a1[v6] = 92;
  if ( (unsigned int)ProcessPrng(&v9, 8) )
    return StringCchPrintfW(&a1[v6 + 1], 260 - (v6 + 1), L"~DF%08X%08X.TMP", (unsigned int)v9, HIDWORD(v9));
  if ( dword_180071078 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    ComTraceMessageT<>();
  return 2147942414LL;
}

```

## disassembly

```asm
0x18003aa00  mov     [rsp+arg_8], rdx
0x18003aa05  push    rbx
0x18003aa06  push    rbp
0x18003aa07  push    rsi
0x18003aa08  push    rdi
0x18003aa09  sub     rsp, 38h
0x18003aa0d  mov     rdi, rcx
0x18003aa10  mov     rdx, rcx
0x18003aa13  mov     esi, 104h
0x18003aa18  mov     ebp, r8d
0x18003aa1b  mov     ecx, esi
0x18003aa1d  call    cs:__imp_GetTempPath2W
0x18003aa23  mov     ebx, eax
0x18003aa25  test    eax, eax
0x18003aa27  jz      short loc_18003AA39
0x18003aa29  lea     rax, [rbx+18h]
0x18003aa2d  cmp     rax, rsi
0x18003aa30  jb      short loc_18003AA54
0x18003aa32  mov     eax, 80030003h
0x18003aa37  jmp     short loc_18003AA46
0x18003aa39  call    cs:__imp_GetLastError
0x18003aa3f  mov     ecx, eax; unsigned int
0x18003aa41  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18003aa46  test    ebp, ebp
0x18003aa48  jz      short loc_18003AABE
0x18003aa4a  mov     word ptr [rdi], 2Eh ; '.'
0x18003aa4f  mov     ebx, 1
0x18003aa54  mov     edx, 8
0x18003aa59  mov     word ptr [rdi+rbx*2], 5Ch ; '\'
0x18003aa5f  lea     rcx, [rsp+58h+arg_8]
0x18003aa64  call    cs:__imp_ProcessPrng
0x18003aa6a  test    eax, eax
0x18003aa6c  jnz     short loc_18003AA97
0x18003aa6e  mov     eax, cs:dword_180071078
0x18003aa74  test    eax, eax
0x18003aa76  jnz     short loc_18003AA8B
0x18003aa78  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18003aa7e  jz      short loc_18003AA90
0x18003aa80  xor     ecx, ecx
0x18003aa82  call    IsWppLevelEnabled
0x18003aa87  test    al, al
0x18003aa89  jz      short loc_18003AA90
0x18003aa8b  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18003aa90  mov     eax, 8007000Eh
0x18003aa95  jmp     short loc_18003AABE
0x18003aa97  mov     r9d, dword ptr [rsp+58h+arg_8]
0x18003aa9c  lea     rax, [rbx+1]
0x18003aaa0  sub     rsi, rax
0x18003aaa3  lea     rcx, [rdi+rax*2]; unsigned __int16 *
0x18003aaa7  mov     eax, dword ptr [rsp+58h+arg_8+4]
0x18003aaab  lea     r8, aDf08x08xTmp; "~DF%08X%08X.TMP"
0x18003aab2  mov     rdx, rsi; unsigned __int64
0x18003aab5  mov     [rsp+58h+var_38], eax
0x18003aab9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003aabe  add     rsp, 38h
0x18003aac2  pop     rdi
0x18003aac3  pop     rsi
0x18003aac4  pop     rbp
0x18003aac5  pop     rbx
0x18003aac6  retn
```
