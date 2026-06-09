# Ssl::ReadData(ushort const *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x10042f9c0`
- end: `0x10042faec`
- name: `?ReadData@Ssl@@CAKPEBGAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(wchar_t *FileName)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x10042d8b8`
- `0x10042dec4`
- `0x10042f68c`

## callees

- `0x10042a7b4`
- `0x10042f9c0`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10042fa88`
- `KERNEL32!GetLastError` at `0x10042fa88`
- `api-ms-win-crt-stdio-l1-1-0!_wfopen_s` at `0x10042fa28`
- `api-ms-win-crt-stdio-l1-1-0!_wfopen_s` at `0x10042fa28`
- `api-ms-win-crt-stdio-l1-1-0!ftell` at `0x10042fa4a`
- `api-ms-win-crt-stdio-l1-1-0!ftell` at `0x10042fa4a`
- `api-ms-win-crt-stdio-l1-1-0!fseek` at `0x10042fa3f`
- `api-ms-win-crt-stdio-l1-1-0!fseek` at `0x10042fa5c`
- `api-ms-win-crt-stdio-l1-1-0!fseek` at `0x10042fa3f`
- `api-ms-win-crt-stdio-l1-1-0!fseek` at `0x10042fa5c`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x10042fa7d`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x10042fa7d`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x10042fac9`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x10042fac9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Ssl::ReadData(wchar_t *FileName, void **a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  FILE *Stream; // [rsp+50h] [rbp+18h] BYREF
  __int64 v8; // [rsp+58h] [rbp+20h] BYREF

  v8 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7BA0[0] )
    bidScopeEnterW(&v8, off_1005E7BA0[0], FileName);
  Stream = 0;
  LastError = _wfopen_s(&Stream, FileName, L"rb");
  if ( LastError
    || (fseek(Stream, 0, 2),
        v5 = (unsigned int)ftell(Stream),
        fseek(Stream, 0, 0),
        std::vector<unsigned char>::_Resize<_lambda_2b51424039c320f102fd798e073c89b2_>(a2, (unsigned int)v5, a2),
        v5 != fread(*a2, 1u, (unsigned int)v5, Stream))
    && (LastError = GetLastError()) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E53A8[0] )
      bidTraceW(0, 884736, off_1005E53A8[0], LastError);
  }
  if ( Stream )
    fclose(Stream);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v8);
  return LastError;
}

```

## disassembly

```asm
0x10042f9c0  mov     r11, rsp
0x10042f9c3  push    rdi
0x10042f9c4  sub     rsp, 30h
0x10042f9c8  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x10042f9d0  mov     [r11+8], rbx
0x10042f9d4  mov     [r11+10h], rsi
0x10042f9d8  mov     rsi, rdx
0x10042f9db  mov     rbx, rcx
0x10042f9de  or      qword ptr [r11+20h], 0FFFFFFFFFFFFFFFFh
0x10042f9e3  mov     eax, cs:_bidGblFlags
0x10042f9e9  mov     ecx, 20004h
0x10042f9ee  and     eax, ecx
0x10042f9f0  cmp     eax, ecx
0x10042f9f2  jnz     short loc_10042FA13
0x10042f9f4  mov     rax, cs:off_1005E7BA0; "<Ssl::ReadData|API|SNI> fileName: %s\n"
0x10042f9fb  test    rax, rax
0x10042f9fe  jz      short loc_10042FA13
0x10042fa00  mov     r8, rbx
0x10042fa03  mov     rdx, cs:off_1005E7BA0; "<Ssl::ReadData|API|SNI> fileName: %s\n"
0x10042fa0a  lea     rcx, [r11+20h]
0x10042fa0e  call    _bidScopeEnterW
0x10042fa13  and     [rsp+38h+Stream], 0
0x10042fa19  lea     r8, aRb; "rb"
0x10042fa20  mov     rdx, rbx; FileName
0x10042fa23  lea     rcx, [rsp+38h+Stream]; Stream
0x10042fa28  call    cs:__imp__wfopen_s
0x10042fa2e  mov     edi, eax
0x10042fa30  test    eax, eax
0x10042fa32  jnz     short loc_10042FA94
0x10042fa34  xor     edx, edx; Offset
0x10042fa36  lea     r8d, [rax+2]; Origin
0x10042fa3a  mov     rcx, [rsp+38h+Stream]; Stream
0x10042fa3f  call    cs:__imp_fseek
0x10042fa45  mov     rcx, [rsp+38h+Stream]; Stream
0x10042fa4a  call    cs:__imp_ftell
0x10042fa50  mov     ebx, eax
0x10042fa52  xor     r8d, r8d; Origin
0x10042fa55  xor     edx, edx; Offset
0x10042fa57  mov     rcx, [rsp+38h+Stream]; Stream
0x10042fa5c  call    cs:__imp_fseek
0x10042fa62  mov     r8, rsi
0x10042fa65  mov     edx, ebx
0x10042fa67  mov     rcx, rsi
0x10042fa6a  call    ??$_Resize@V_lambda_2b51424039c320f102fd798e073c89b2_@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KV_lambda_2b51424039c320f102fd798e073c89b2_@@@Z; std::vector<uchar>::_Resize<_lambda_2b51424039c320f102fd798e073c89b2_>(unsigned __int64,_lambda_2b51424039c320f102fd798e073c89b2_)
0x10042fa6f  mov     r9, [rsp+38h+Stream]; Stream
0x10042fa74  mov     r8d, ebx; ElementCount
0x10042fa77  lea     edx, [rdi+1]; ElementSize
0x10042fa7a  mov     rcx, [rsi]; Buffer
0x10042fa7d  call    cs:__imp_fread
0x10042fa83  cmp     rbx, rax
0x10042fa86  jz      short loc_10042FABF
0x10042fa88  call    cs:__imp_GetLastError
0x10042fa8e  mov     edi, eax
0x10042fa90  test    eax, eax
0x10042fa92  jz      short loc_10042FABF
0x10042fa94  test    byte ptr cs:_bidGblFlags, 2
0x10042fa9b  jz      short loc_10042FABF
0x10042fa9d  mov     rax, cs:off_1005E53A8; "<Ssl::ReadData|ERR|SNI> ReadData failed"...
0x10042faa4  test    rax, rax
0x10042faa7  jz      short loc_10042FABF
0x10042faa9  mov     r9d, edi
0x10042faac  mov     r8, cs:off_1005E53A8; "<Ssl::ReadData|ERR|SNI> ReadData failed"...
0x10042fab3  mov     edx, 0D8000h
0x10042fab8  xor     ecx, ecx
0x10042faba  call    _bidTraceW
0x10042fabf  mov     rcx, [rsp+38h+Stream]; Stream
0x10042fac4  test    rcx, rcx
0x10042fac7  jz      short loc_10042FAD0
0x10042fac9  call    cs:__imp_fclose
0x10042facf  nop
0x10042fad0  lea     rcx, [rsp+38h+arg_18]; this
0x10042fad5  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10042fada  mov     eax, edi
0x10042fadc  mov     rbx, [rsp+38h+arg_0]
0x10042fae1  mov     rsi, [rsp+38h+arg_8]
0x10042fae6  add     rsp, 30h
0x10042faea  pop     rdi
0x10042faeb  retn
```
