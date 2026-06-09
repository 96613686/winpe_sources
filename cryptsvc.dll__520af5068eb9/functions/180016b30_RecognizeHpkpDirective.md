# _RecognizeHpkpDirective

- ea: `0x180016b30`
- end: `0x180016bee`
- name: `_RecognizeHpkpDirective`
- size: `190`
- prototype: `__int64 __fastcall(PCNZCH lpString2, int cchCount2)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016bf4`

## callees

- `0x180016580`
- `0x180016b30`

## string_xrefs

- `0x180016bbe`: `report-uri`

## pseudocode

```c
__int64 __fastcall RecognizeHpkpDirective(PCNZCH lpString2, int cchCount2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( lpString2 && cchCount2 )
  {
    if ( (unsigned int)CompareDirectiveString("max-age", 7, lpString2, cchCount2) )
    {
      return 1;
    }
    else if ( (unsigned int)CompareDirectiveString("includeSubDomains", 17, lpString2, cchCount2) )
    {
      return 2;
    }
    else if ( (unsigned int)CompareDirectiveString("pin-sha256", 10, lpString2, cchCount2) )
    {
      return 3;
    }
    else if ( (unsigned int)CompareDirectiveString("report-uri", 10, lpString2, cchCount2) )
    {
      return 4;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180016b30  mov     [rsp+arg_0], rbx
0x180016b35  mov     [rsp+arg_8], rsi
0x180016b3a  push    rdi
0x180016b3b  sub     rsp, 20h
0x180016b3f  xor     ebx, ebx
0x180016b41  mov     edi, edx
0x180016b43  mov     rsi, rcx
0x180016b46  test    rcx, rcx
0x180016b49  jz      loc_180016BDC
0x180016b4f  test    edx, edx
0x180016b51  jz      loc_180016BDC
0x180016b57  mov     r9d, edx; cchCount2
0x180016b5a  mov     r8, rcx; lpString2
0x180016b5d  lea     edx, [rbx+7]; cchCount1
0x180016b60  lea     rcx, String1; "max-age"
0x180016b67  call    _CompareDirectiveString
0x180016b6c  test    eax, eax
0x180016b6e  jz      short loc_180016B77
0x180016b70  mov     ebx, 1
0x180016b75  jmp     short loc_180016BDC
0x180016b77  mov     r9d, edi; cchCount2
0x180016b7a  lea     rcx, aIncludesubdoma; "includeSubDomains"
0x180016b81  mov     r8, rsi; lpString2
0x180016b84  mov     edx, 11h; cchCount1
0x180016b89  call    _CompareDirectiveString
0x180016b8e  test    eax, eax
0x180016b90  jz      short loc_180016B99
0x180016b92  mov     ebx, 2
0x180016b97  jmp     short loc_180016BDC
0x180016b99  mov     r9d, edi; cchCount2
0x180016b9c  lea     rcx, aPinSha256; "pin-sha256"
0x180016ba3  mov     r8, rsi; lpString2
0x180016ba6  mov     edx, 0Ah; cchCount1
0x180016bab  call    _CompareDirectiveString
0x180016bb0  test    eax, eax
0x180016bb2  jz      short loc_180016BBB
0x180016bb4  mov     ebx, 3
0x180016bb9  jmp     short loc_180016BDC
0x180016bbb  mov     r9d, edi; cchCount2
0x180016bbe  lea     rcx, aReportUri; "report-uri"
0x180016bc5  mov     r8, rsi; lpString2
0x180016bc8  mov     edx, 0Ah; cchCount1
0x180016bcd  call    _CompareDirectiveString
0x180016bd2  test    eax, eax
0x180016bd4  mov     ecx, 4
0x180016bd9  cmovnz  ebx, ecx
0x180016bdc  mov     rsi, [rsp+28h+arg_8]
0x180016be1  mov     eax, ebx
0x180016be3  mov     rbx, [rsp+28h+arg_0]
0x180016be8  add     rsp, 20h
0x180016bec  pop     rdi
0x180016bed  retn
```
