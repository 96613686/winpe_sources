# EscapeUrlComponent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180010948`
- end: `0x180010b05`
- name: `?EscapeUrlComponent@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f8f4`

## callees

- `0x180001b2c`
- `0x180001ca4`
- `0x1800027d0`
- `0x1800028e0`
- `0x180002bb8`
- `0x180010948`
- `0x180010bc8`
- `0x1800222d0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180010ab0`
- `msvcrt!swprintf_s` at `0x180010ab0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800109df`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800109df`
- `KERNEL32!WideCharToMultiByte` at `0x1800109ba`
- `KERNEL32!WideCharToMultiByte` at `0x180010a67`
- `KERNEL32!WideCharToMultiByte` at `0x1800109ba`
- `KERNEL32!WideCharToMultiByte` at `0x180010a67`
- `KERNEL32!GetLastError` at `0x1800109c7`
- `KERNEL32!GetLastError` at `0x1800109c7`

## pseudocode

```c
__int64 __fastcall EscapeUrlComponent(const WCHAR *lpWideCharStr)
{
  unsigned int v2; // r14d
  signed int v3; // ebx
  CHAR *v4; // rsi
  const WCHAR *v5; // r8
  unsigned int v6; // eax
  int cbMultiByte; // r13d
  signed int LastError; // eax
  CHAR *lpMultiByteStr; // rax
  const WCHAR *v11; // r8
  int v12; // r15d
  unsigned int v13; // r12d
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rax
  int v17; // eax
  wchar_t Buffer; // [rsp+48h] [rbp-40h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = 0;
  if ( *((_QWORD *)lpWideCharStr + 2) )
  {
    if ( *((_QWORD *)lpWideCharStr + 3) < 8u )
      v5 = lpWideCharStr;
    else
      v5 = *(const WCHAR **)lpWideCharStr;
    v6 = WideCharToMultiByte(0xFDE9u, 0, v5, *((_DWORD *)lpWideCharStr + 4) + 1, 0, 0, 0, 0);
    cbMultiByte = v6;
    if ( v6 )
    {
      try
      {
        lpMultiByteStr = (CHAR *)operator new[](v6);
      }
      catch ( ... )
      {
        operator delete[](0);
        throw;
      }
      v4 = lpMultiByteStr;
      if ( !lpMultiByteStr )
      {
        v3 = -2147024882;
        goto LABEL_8;
      }
      if ( *((_QWORD *)lpWideCharStr + 3) < 8u )
        v11 = lpWideCharStr;
      else
        v11 = *(const WCHAR **)lpWideCharStr;
      if ( WideCharToMultiByte(0xFDE9u, 0, v11, *((_DWORD *)lpWideCharStr + 4) + 1, lpMultiByteStr, cbMultiByte, 0, 0) )
      {
        v12 = 0;
        while ( v2 < cbMultiByte - 1 )
        {
          v13 = (unsigned __int8)v4[v2];
          if ( (unsigned int)MustEncode(v4[v2]) )
          {
            swprintf_s(&Buffer, 4u, L"%%%02x", v13);
            v16 = std::char_traits<unsigned short>::length(&Buffer);
            std::wstring::replace((_DWORD)lpWideCharStr, v12, 1, (unsigned int)&Buffer, v16);
            v17 = 3;
          }
          else
          {
            std::wstring::replace((_DWORD)lpWideCharStr, v12, v14, v15, v13);
            v17 = 1;
          }
          ++v2;
          v12 += v17;
        }
        goto LABEL_8;
      }
    }
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_8:
  operator delete[](v4);
  if ( v3 < 0 )
    std::wstring::erase(lpWideCharStr, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180010948  mov     [rsp+arg_8], rbx
0x18001094d  mov     [rsp+arg_10], rsi
0x180010952  push    rdi
0x180010953  push    r12
0x180010955  push    r13
0x180010957  push    r14
0x180010959  push    r15
0x18001095b  sub     rsp, 60h
0x18001095f  mov     rax, cs:__security_cookie
0x180010966  xor     rax, rsp
0x180010969  mov     [rsp+88h+var_38], rax
0x18001096e  mov     rdi, rcx
0x180010971  xor     r14d, r14d
0x180010974  mov     ebx, r14d
0x180010977  mov     esi, r14d
0x18001097a  mov     [rsp+88h+var_48], r14
0x18001097f  cmp     [rcx+10h], r14
0x180010983  jz      short loc_1800109DC
0x180010985  mov     r9d, [rcx+10h]
0x180010989  inc     r9d; cchWideChar
0x18001098c  cmp     qword ptr [rcx+18h], 8
0x180010991  jb      short loc_180010998
0x180010993  mov     r8, [rcx]
0x180010996  jmp     short loc_18001099B
0x180010998  mov     r8, rdi; lpWideCharStr
0x18001099b  mov     [rsp+88h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1800109a0  mov     [rsp+88h+lpDefaultChar], r14; lpDefaultChar
0x1800109a5  mov     [rsp+88h+cbMultiByte], r14d; cbMultiByte
0x1800109aa  mov     [rsp+88h+lpMultiByteStr], r14; lpMultiByteStr
0x1800109af  xor     edx, edx; dwFlags
0x1800109b1  mov     r15d, 0FDE9h
0x1800109b7  mov     ecx, r15d; CodePage
0x1800109ba  call    cs:__imp_WideCharToMultiByte
0x1800109c0  mov     r13d, eax
0x1800109c3  test    eax, eax
0x1800109c5  jnz     short loc_180010A1C
0x1800109c7  call    cs:__imp_GetLastError
0x1800109cd  mov     ebx, eax
0x1800109cf  test    eax, eax
0x1800109d1  jle     short loc_1800109DC
0x1800109d3  movzx   ebx, ax
0x1800109d6  or      ebx, 80070000h
0x1800109dc  mov     rcx, rsi
0x1800109df  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800109e5  test    ebx, ebx
0x1800109e7  jns     short loc_1800109F3
0x1800109e9  xor     edx, edx
0x1800109eb  mov     rcx, rdi
0x1800109ee  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
0x1800109f3  mov     eax, ebx
0x1800109f5  mov     rcx, [rsp+88h+var_38]
0x1800109fa  xor     rcx, rsp; StackCookie
0x1800109fd  call    __security_check_cookie
0x180010a02  lea     r11, [rsp+88h+var_28]
0x180010a07  mov     rbx, [r11+38h]
0x180010a0b  mov     rsi, [r11+40h]
0x180010a0f  mov     rsp, r11
0x180010a12  pop     r15
0x180010a14  pop     r14
0x180010a16  pop     r13
0x180010a18  pop     r12
0x180010a1a  pop     rdi
0x180010a1b  retn
0x180010a1c  mov     rcx, r13; unsigned __int64
0x180010a1f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010a24  mov     rsi, rax
0x180010a27  mov     [rsp+88h+var_48], rax
0x180010a2c  test    rax, rax
0x180010a2f  jnz     short loc_180010A38
0x180010a31  mov     ebx, 8007000Eh
0x180010a36  jmp     short loc_1800109DC
0x180010a38  mov     r9d, [rdi+10h]
0x180010a3c  inc     r9d; cchWideChar
0x180010a3f  cmp     qword ptr [rdi+18h], 8
0x180010a44  jb      short loc_180010A4B
0x180010a46  mov     r8, [rdi]
0x180010a49  jmp     short loc_180010A4E
0x180010a4b  mov     r8, rdi; lpWideCharStr
0x180010a4e  mov     [rsp+88h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180010a53  mov     [rsp+88h+lpDefaultChar], r14; lpDefaultChar
0x180010a58  mov     [rsp+88h+cbMultiByte], r13d; cbMultiByte
0x180010a5d  mov     [rsp+88h+lpMultiByteStr], rsi; lpMultiByteStr
0x180010a62  xor     edx, edx; dwFlags
0x180010a64  mov     ecx, r15d; CodePage
0x180010a67  call    cs:__imp_WideCharToMultiByte
0x180010a6d  test    eax, eax
0x180010a6f  jz      loc_1800109C7
0x180010a75  mov     r15d, r14d
0x180010a78  lea     eax, [r13-1]
0x180010a7c  cmp     r14d, eax
0x180010a7f  jnb     loc_1800109DC
0x180010a85  mov     eax, r14d
0x180010a88  movzx   r12d, byte ptr [rax+rsi]
0x180010a8d  mov     cl, r12b; unsigned __int8
0x180010a90  call    ?MustEncode@@YAHE@Z; MustEncode(uchar)
0x180010a95  mov     ecx, r15d
0x180010a98  test    eax, eax
0x180010a9a  jz      short loc_180010AE2
0x180010a9c  mov     r9d, r12d
0x180010a9f  lea     r8, a02x_1; "%%%02x"
0x180010aa6  mov     edx, 4; BufferCount
0x180010aab  lea     rcx, [rsp+88h+Buffer]; Buffer
0x180010ab0  call    cs:__imp_swprintf_s
0x180010ab6  lea     rcx, [rsp+88h+Buffer]
0x180010abb  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180010ac0  mov     [rsp+88h+lpMultiByteStr], rax
0x180010ac5  lea     r9, [rsp+88h+Buffer]
0x180010aca  mov     r8d, 1
0x180010ad0  mov     edx, r15d
0x180010ad3  mov     rcx, rdi
0x180010ad6  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0PEBG0@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180010adb  mov     eax, 3
0x180010ae0  jmp     short loc_180010AF8
0x180010ae2  mov     word ptr [rsp+88h+lpMultiByteStr], r12w
0x180010ae8  mov     rdx, rcx
0x180010aeb  mov     rcx, rdi
0x180010aee  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K00G@Z; std::wstring::replace(unsigned __int64,unsigned __int64,unsigned __int64,ushort)
0x180010af3  mov     eax, 1
0x180010af8  inc     r14d
0x180010afb  add     r15d, eax
0x180010afe  jmp     loc_180010A78
```
