# BookKeepingXml::Flush(void)

- ea: `0x18000c6e0`
- end: `0x18000c83d`
- name: `?Flush@BookKeepingXml@@AEAAJXZ`
- size: `349`
- prototype: `__int64 __fastcall(BookKeepingXml *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000c3e8`
- `0x18000c464`

## callees

- `0x18000c6e0`
- `0x18000cfbc`
- `0x18001b550`
- `0x18001b610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c76c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c76c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7b6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c7ac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c7ac`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000c762`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000c762`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::Flush(const WCHAR *this)
{
  signed int v2; // ebx
  _WORD *v3; // rsi
  DWORD v4; // eax
  signed int v5; // eax
  void *v6; // rcx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1028h] BYREF
  CHAR MultiByteStr[4096]; // [rsp+50h] [rbp-1018h] BYREF

  if ( *((_QWORD *)this + 2) == -1 )
  {
    return (unsigned int)-2147221497;
  }
  else
  {
    v2 = 1;
    if ( *((_QWORD *)this + 4) != 4096 )
    {
      v3 = this + 20;
      v4 = WideCharToMultiByte(0, 0, this + 20, 4096 - *((_DWORD *)this + 8), MultiByteStr, 4096, 0, 0);
      if ( v4 )
      {
        v6 = (void *)*((_QWORD *)this + 2);
        NumberOfBytesWritten = 0;
        if ( !WriteFile(v6, MultiByteStr, v4, &NumberOfBytesWritten, 0) )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
        }
        *((_QWORD *)this + 3) = v3;
        *((_QWORD *)this + 4) = 4096;
        *v3 = 0;
        if ( v2 < 0
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            16,
            (unsigned int)WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids,
            *((_QWORD *)this + 1),
            v2);
        }
      }
      else
      {
        v5 = GetLastError();
        v2 = v5;
        if ( v5 > 0 )
          return (unsigned __int16)v5 | 0x80070000;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000c6e0  mov     [rsp+arg_8], rbx
0x18000c6e5  mov     [rsp+arg_10], rsi
0x18000c6ea  push    rdi
0x18000c6eb  mov     eax, 1060h
0x18000c6f0  call    _alloca_probe
0x18000c6f5  sub     rsp, rax
0x18000c6f8  mov     rax, cs:__security_cookie
0x18000c6ff  xor     rax, rsp
0x18000c702  mov     [rsp+1068h+var_18], rax
0x18000c70a  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x18000c70f  mov     rdi, rcx
0x18000c712  jnz     short loc_18000C71E
0x18000c714  mov     ebx, 80040007h
0x18000c719  jmp     loc_18000C816
0x18000c71e  mov     r9d, 1000h
0x18000c724  mov     ebx, 1
0x18000c729  sub     r9, [rcx+20h]; cchWideChar
0x18000c72d  jz      loc_18000C816
0x18000c733  lea     rsi, [rcx+28h]
0x18000c737  mov     [rsp+1068h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000c740  mov     [rsp+1068h+lpDefaultChar], 0; lpDefaultChar
0x18000c749  lea     rax, [rsp+1068h+MultiByteStr]
0x18000c74e  mov     [rsp+1068h+cbMultiByte], 1000h; cbMultiByte
0x18000c756  mov     r8, rsi; lpWideCharStr
0x18000c759  xor     edx, edx; dwFlags
0x18000c75b  mov     [rsp+1068h+lpMultiByteStr], rax; lpMultiByteStr
0x18000c760  xor     ecx, ecx; CodePage
0x18000c762  call    cs:__imp_WideCharToMultiByte
0x18000c768  test    eax, eax
0x18000c76a  jnz     short loc_18000C78A
0x18000c76c  call    cs:__imp_GetLastError
0x18000c772  mov     ebx, eax
0x18000c774  test    eax, eax
0x18000c776  jle     loc_18000C816
0x18000c77c  movzx   ebx, ax
0x18000c77f  or      ebx, 80070000h
0x18000c785  jmp     loc_18000C816
0x18000c78a  mov     rcx, [rdi+10h]; hFile
0x18000c78e  lea     r9, [rsp+1068h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000c793  mov     r8d, eax; nNumberOfBytesToWrite
0x18000c796  mov     [rsp+1068h+NumberOfBytesWritten], 0
0x18000c79e  lea     rdx, [rsp+1068h+MultiByteStr]; lpBuffer
0x18000c7a3  mov     [rsp+1068h+lpMultiByteStr], 0; lpOverlapped
0x18000c7ac  call    cs:__imp_WriteFile
0x18000c7b2  test    eax, eax
0x18000c7b4  jnz     short loc_18000C7CB
0x18000c7b6  call    cs:__imp_GetLastError
0x18000c7bc  mov     ebx, eax
0x18000c7be  test    eax, eax
0x18000c7c0  jle     short loc_18000C7CB
0x18000c7c2  movzx   ebx, ax
0x18000c7c5  or      ebx, 80070000h
0x18000c7cb  xor     eax, eax
0x18000c7cd  mov     [rdi+18h], rsi
0x18000c7d1  mov     qword ptr [rdi+20h], 1000h
0x18000c7d9  mov     [rsi], ax
0x18000c7dc  test    ebx, ebx
0x18000c7de  jns     short loc_18000C816
0x18000c7e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7e7  lea     rax, WPP_GLOBAL_Control
0x18000c7ee  cmp     rcx, rax
0x18000c7f1  jz      short loc_18000C816
0x18000c7f3  cmp     byte ptr [rcx+19h], 2
0x18000c7f7  jb      short loc_18000C816
0x18000c7f9  mov     r9, [rdi+8]
0x18000c7fd  lea     r8, WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids
0x18000c804  mov     rcx, [rcx+10h]
0x18000c808  mov     edx, 10h
0x18000c80d  mov     dword ptr [rsp+1068h+lpMultiByteStr], ebx
0x18000c811  call    WPP_SF_Sd
0x18000c816  mov     eax, ebx
0x18000c818  mov     rcx, [rsp+1068h+var_18]
0x18000c820  xor     rcx, rsp; StackCookie
0x18000c823  call    __security_check_cookie
0x18000c828  lea     r11, [rsp+1068h+var_8]
0x18000c830  mov     rbx, [r11+18h]
0x18000c834  mov     rsi, [r11+20h]
0x18000c838  mov     rsp, r11
0x18000c83b  pop     rdi
0x18000c83c  retn
```
