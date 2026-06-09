# NcaGetLongPathName

- ea: `0x180019638`
- end: `0x18001977d`
- name: `NcaGetLongPathName`
- size: `325`
- prototype: `__int64 __fastcall(const wchar_t *Src, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180019520`

## callees

- `0x1800033bc`
- `0x180004f04`
- `0x180019638`
- `0x1800199b4`
- `0x180019c70`
- `0x18001cc70`

## import_xrefs

- `msvcrt!wcschr` at `0x18001969b`
- `msvcrt!wcschr` at `0x18001969b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019700`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800196f0`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800196f0`

## string_xrefs

- `0x180019722`: `NcaGetLongPathName`
- `0x18001975c`: `NcaGetLongPathName`
- `0x18001976a`: `NcaGetLongPathName`
- `0x18001971b`: `GetLongPathNameW`

## pseudocode

```c
__int64 __fastcall NcaGetLongPathName(const wchar_t *Src, _QWORD *a2, _DWORD *a3)
{
  wchar_t *v6; // rax
  WCHAR *v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  DWORD LongPathNameW; // eax
  DWORD LastError; // eax
  __int64 v13; // rdx
  WCHAR szLongPath[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
  *a2 = 0;
  v6 = wcschr(Src, 0x7Eu);
  v7 = (WCHAR *)Src;
  if ( v6 )
  {
    LongPathNameW = GetLongPathNameW(Src, szLongPath, 0x104u);
    if ( !LongPathNameW )
    {
      LastError = GetLastError();
      if ( LastError - 2 <= 1 )
      {
        *a3 = 0;
      }
      else if ( LastError )
      {
        v9 = NcaReportErrorAsWinError("NcaGetLongPathName", "GetLongPathNameW", LastError);
        if ( (v9 & 0x80000000) == 0 )
          return v9;
        return (unsigned int)NcaReportReturnError("NcaGetLongPathName", v9);
      }
      return 0;
    }
    if ( LongPathNameW >= 0x104 )
    {
      v9 = -2147024809;
      v13 = 2147942487LL;
LABEL_19:
      NcaReportReturnError("NcaGetLongPathName", v13);
      return (unsigned int)NcaReportReturnError("NcaGetLongPathName", v9);
    }
    v7 = szLongPath;
  }
  v8 = NcaStringCopy(v7);
  v9 = v8;
  if ( v8 < 0 )
  {
    v13 = (unsigned int)v8;
    goto LABEL_19;
  }
  *a3 = 1;
  return v9;
}

```

## disassembly

```asm
0x180019638  push    rbx
0x18001963a  push    rsi
0x18001963b  push    rdi
0x18001963c  sub     rsp, 240h
0x180019643  mov     rax, cs:__security_cookie
0x18001964a  xor     rax, rsp
0x18001964d  mov     [rsp+258h+var_28], rax
0x180019655  mov     rdi, r8
0x180019658  mov     rbx, rdx
0x18001965b  mov     rsi, rcx
0x18001965e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019665  lea     rax, WPP_GLOBAL_Control
0x18001966c  cmp     rcx, rax
0x18001966f  jz      short loc_18001968C
0x180019671  test    byte ptr [rcx+1Ch], 8
0x180019675  jz      short loc_18001968C
0x180019677  mov     rcx, [rcx+10h]
0x18001967b  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x180019682  mov     edx, 1Dh
0x180019687  call    WPP_SF_
0x18001968c  mov     edx, 7Eh ; '~'; Ch
0x180019691  mov     qword ptr [rbx], 0
0x180019698  mov     rcx, rsi; Str
0x18001969b  call    cs:__imp_wcschr
0x1800196a2  nop     dword ptr [rax+rax+00h]
0x1800196a7  mov     rcx, rsi; Src
0x1800196aa  test    rax, rax
0x1800196ad  jnz     short loc_1800196E5
0x1800196af  mov     rdx, rbx
0x1800196b2  call    NcaStringCopy
0x1800196b7  mov     ebx, eax
0x1800196b9  test    eax, eax
0x1800196bb  js      loc_18001975A
0x1800196c1  mov     dword ptr [rdi], 1
0x1800196c7  mov     eax, ebx
0x1800196c9  mov     rcx, [rsp+258h+var_28]
0x1800196d1  xor     rcx, rsp; StackCookie
0x1800196d4  call    __security_check_cookie
0x1800196d9  add     rsp, 240h
0x1800196e0  pop     rdi
0x1800196e1  pop     rsi
0x1800196e2  pop     rbx
0x1800196e3  retn
0x1800196e5  mov     r8d, 104h; cchBuffer
0x1800196eb  lea     rdx, [rsp+258h+szLongPath]; lpszLongPath
0x1800196f0  call    cs:__imp_GetLongPathNameW
0x1800196f7  nop     dword ptr [rax+rax+00h]
0x1800196fc  test    eax, eax
0x1800196fe  jnz     short loc_180019740
0x180019700  call    cs:__imp_GetLastError
0x180019707  nop     dword ptr [rax+rax+00h]
0x18001970c  lea     ecx, [rax-2]
0x18001970f  cmp     ecx, 1
0x180019712  jbe     short loc_180019736
0x180019714  test    eax, eax
0x180019716  jz      short loc_18001973C
0x180019718  mov     r8d, eax
0x18001971b  lea     rdx, aGetlongpathnam; "GetLongPathNameW"
0x180019722  lea     rcx, aNcagetlongpath; "NcaGetLongPathName"
0x180019729  call    NcaReportErrorAsWinError
0x18001972e  mov     ebx, eax
0x180019730  test    eax, eax
0x180019732  js      short loc_180019768
0x180019734  jmp     short loc_1800196C7
0x180019736  mov     dword ptr [rdi], 0
0x18001973c  xor     ebx, ebx
0x18001973e  jmp     short loc_1800196C7
0x180019740  cmp     eax, 104h
0x180019745  jb      short loc_180019750
0x180019747  mov     ebx, 80070057h
0x18001974c  mov     edx, ebx
0x18001974e  jmp     short loc_18001975C
0x180019750  lea     rcx, [rsp+258h+szLongPath]
0x180019755  jmp     loc_1800196AF
0x18001975a  mov     edx, eax
0x18001975c  lea     rcx, aNcagetlongpath; "NcaGetLongPathName"
0x180019763  call    NcaReportReturnError
0x180019768  mov     edx, ebx
0x18001976a  lea     rcx, aNcagetlongpath; "NcaGetLongPathName"
0x180019771  call    NcaReportReturnError
0x180019776  mov     ebx, eax
0x180019778  jmp     loc_1800196C7
```
