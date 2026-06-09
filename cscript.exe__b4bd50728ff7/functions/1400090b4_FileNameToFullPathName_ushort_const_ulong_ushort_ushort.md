# FileNameToFullPathName(ushort const *,ulong,ushort *,ushort * *)

- ea: `0x1400090b4`
- end: `0x140009244`
- name: `?FileNameToFullPathName@@YAJPEBGKPEAGPEAPEAG@Z`
- size: `400`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400014b0`
- `0x14000d4a8`
- `0x140012360`

## callees

- `0x1400090b4`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1400091f4`
- `KERNEL32!MultiByteToWideChar` at `0x140009219`
- `KERNEL32!MultiByteToWideChar` at `0x1400091f4`
- `KERNEL32!MultiByteToWideChar` at `0x140009219`
- `KERNEL32!WideCharToMultiByte` at `0x14000913e`
- `KERNEL32!WideCharToMultiByte` at `0x14000919f`
- `KERNEL32!WideCharToMultiByte` at `0x14000913e`
- `KERNEL32!WideCharToMultiByte` at `0x14000919f`
- `KERNEL32!GetLastError` at `0x140009102`
- `KERNEL32!GetLastError` at `0x140009102`
- `KERNEL32!GetFullPathNameA` at `0x1400091ce`
- `KERNEL32!GetFullPathNameA` at `0x1400091ce`
- `KERNEL32!GetFullPathNameW` at `0x1400090f4`
- `KERNEL32!GetFullPathNameW` at `0x1400090f4`

## pseudocode

```c
__int64 __fastcall FileNameToFullPathName(
        LPCWCH lpWideCharStr,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned int v4; // ebx
  signed int LastError; // eax
  int cbMultiByte; // eax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  void *v14; // rsp
  CHAR Buffer[208]; // [rsp+20h] [rbp-110h] BYREF
  CHAR MultiByteStr[8]; // [rsp+130h] [rbp+0h] BYREF

  v4 = 0;
  *(_QWORD *)MultiByteStr = 0;
  if ( Global::g_fWindowsNT )
  {
    if ( GetFullPathNameW(lpWideCharStr, 0x104u, a3, a4) )
      return v4;
  }
  else
  {
    cbMultiByte = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( cbMultiByte )
    {
      v10 = cbMultiByte + 15LL;
      if ( v10 < cbMultiByte )
        v10 = 0xFFFFFFFFFFFFFF0LL;
      v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
      v12 = alloca(v11);
      v13 = alloca(v11);
      if ( !MultiByteStr )
        return (unsigned int)-2147024882;
      if ( WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, cbMultiByte, 0, 0) )
      {
        v14 = alloca(272);
        if ( GetFullPathNameA(MultiByteStr, 0x104u, Buffer, (LPSTR *)MultiByteStr) )
        {
          if ( MultiByteToWideChar(0, 0, Buffer, -1, a3, 260) )
          {
            *a4 = &a3[MultiByteToWideChar(0, 0, Buffer, *(_DWORD *)MultiByteStr - (unsigned int)Buffer, 0, 0)];
            return v4;
          }
        }
      }
    }
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v4;
}

```

## disassembly

```asm
0x1400090b4  push    rbp
0x1400090b6  push    rbx
0x1400090b7  push    rsi
0x1400090b8  push    rdi
0x1400090b9  push    r14
0x1400090bb  push    r15
0x1400090bd  sub     rsp, 58h
0x1400090c1  lea     rbp, [rsp+40h]
0x1400090c6  mov     rax, cs:__security_cookie
0x1400090cd  xor     rax, rbp
0x1400090d0  mov     [rbp+40h+var_38], rax
0x1400090d4  xor     ebx, ebx
0x1400090d6  mov     qword ptr [rbp+40h+MultiByteStr], 0
0x1400090de  cmp     cs:?g_fWindowsNT@Global@@2_NA, bl; bool Global::g_fWindowsNT
0x1400090e4  mov     r15, r9
0x1400090e7  mov     r14, r8
0x1400090ea  mov     rdi, rcx
0x1400090ed  jz      short loc_140009120
0x1400090ef  mov     edx, 104h; nBufferLength
0x1400090f4  call    cs:__imp_GetFullPathNameW
0x1400090fa  test    eax, eax
0x1400090fc  jnz     loc_140009229
0x140009102  call    cs:__imp_GetLastError
0x140009108  mov     ebx, eax
0x14000910a  test    eax, eax
0x14000910c  jle     loc_140009229
0x140009112  movzx   ebx, ax
0x140009115  or      ebx, 80070000h
0x14000911b  jmp     loc_140009229
0x140009120  mov     [rsp+80h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x140009125  or      r9d, 0FFFFFFFFh; cchWideChar
0x140009129  mov     [rsp+80h+lpDefaultChar], rbx; lpDefaultChar
0x14000912e  mov     r8, rdi; lpWideCharStr
0x140009131  mov     [rsp+80h+cbMultiByte], ebx; cbMultiByte
0x140009135  xor     edx, edx; dwFlags
0x140009137  xor     ecx, ecx; CodePage
0x140009139  mov     [rsp+80h+lpMultiByteStr], rbx; lpMultiByteStr
0x14000913e  call    cs:__imp_WideCharToMultiByte
0x140009144  movsxd  rdx, eax
0x140009147  test    eax, eax
0x140009149  jz      short loc_140009102
0x14000914b  lea     rcx, [rdx+0Fh]
0x14000914f  cmp     rcx, rdx
0x140009152  ja      short loc_14000915E
0x140009154  mov     rcx, 0FFFFFFFFFFFFFF0h
0x14000915e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140009162  mov     rax, rcx
0x140009165  call    _alloca_probe
0x14000916a  sub     rsp, rcx
0x14000916d  lea     rsi, [rsp+80h+MultiByteStr]
0x140009172  test    rsi, rsi
0x140009175  jnz     short loc_140009181
0x140009177  mov     ebx, 8007000Eh
0x14000917c  jmp     loc_140009229
0x140009181  mov     [rsp+80h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x140009186  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000918a  mov     [rsp+80h+lpDefaultChar], rbx; lpDefaultChar
0x14000918f  mov     r8, rdi; lpWideCharStr
0x140009192  mov     [rsp+80h+cbMultiByte], edx; cbMultiByte
0x140009196  xor     ecx, ecx; CodePage
0x140009198  xor     edx, edx; dwFlags
0x14000919a  mov     [rsp+80h+lpMultiByteStr], rsi; lpMultiByteStr
0x14000919f  call    cs:__imp_WideCharToMultiByte
0x1400091a5  test    eax, eax
0x1400091a7  jz      loc_140009102
0x1400091ad  mov     eax, [rsp+80h+var_80]
0x1400091b0  mov     eax, 110h
0x1400091b5  sub     rsp, rax
0x1400091b8  lea     rdi, [rsp+190h+Buffer]
0x1400091bd  mov     eax, [rdi]
0x1400091bf  lea     r9, [rbp+40h+MultiByteStr]; lpFilePart
0x1400091c3  mov     r8, rdi; lpBuffer
0x1400091c6  mov     edx, 104h; nBufferLength
0x1400091cb  mov     rcx, rsi; lpFileName
0x1400091ce  call    cs:__imp_GetFullPathNameA
0x1400091d4  test    eax, eax
0x1400091d6  jz      loc_140009102
0x1400091dc  mov     [rsp+190h+cchWideChar], 104h; cchWideChar
0x1400091e4  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1400091e8  mov     r8, rdi; lpMultiByteStr
0x1400091eb  mov     [rsp+190h+lpWideCharStr], r14; lpWideCharStr
0x1400091f0  xor     edx, edx; dwFlags
0x1400091f2  xor     ecx, ecx; CodePage
0x1400091f4  call    cs:__imp_MultiByteToWideChar
0x1400091fa  test    eax, eax
0x1400091fc  jz      loc_140009102
0x140009202  mov     r9d, dword ptr [rbp+40h+MultiByteStr]
0x140009206  mov     r8, rdi; lpMultiByteStr
0x140009209  sub     r9d, edi; cbMultiByte
0x14000920c  mov     [rsp+190h+cchWideChar], ebx; cchWideChar
0x140009210  xor     edx, edx; dwFlags
0x140009212  mov     [rsp+190h+lpWideCharStr], rbx; lpWideCharStr
0x140009217  xor     ecx, ecx; CodePage
0x140009219  call    cs:__imp_MultiByteToWideChar
0x14000921f  movsxd  rcx, eax
0x140009222  lea     rdx, [r14+rcx*2]
0x140009226  mov     [r15], rdx
0x140009229  mov     eax, ebx
0x14000922b  mov     rcx, [rbp+40h+var_38]
0x14000922f  xor     rcx, rbp; StackCookie
0x140009232  call    __security_check_cookie
0x140009237  lea     rsp, [rbp+18h]
0x14000923b  pop     r15
0x14000923d  pop     r14
0x14000923f  pop     rdi
0x140009240  pop     rsi
0x140009241  pop     rbx
0x140009242  pop     rbp
0x140009243  retn
```
