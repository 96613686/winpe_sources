# CRdpSettingsFileStream::Write(ushort const *)

- ea: `0x1400a85b0`
- end: `0x1400a8855`
- name: `?Write@CRdpSettingsFileStream@@UEAAJPEBG@Z`
- size: `677`
- prototype: `int(CRdpSettingsFileStream *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cffc`
- `0x1400a85b0`
- `0x1400b1d80`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1400a8774`
- `KERNEL32!WideCharToMultiByte` at `0x1400a8774`
- `KERNEL32!WriteFile` at `0x1400a861b`
- `KERNEL32!WriteFile` at `0x1400a879d`
- `KERNEL32!WriteFile` at `0x1400a861b`
- `KERNEL32!WriteFile` at `0x1400a879d`
- `KERNEL32!LocalFree` at `0x1400a86d8`
- `KERNEL32!LocalFree` at `0x1400a86d8`
- `KERNEL32!GetLastError` at `0x1400a8625`
- `KERNEL32!GetLastError` at `0x1400a8625`

## pseudocode

```c
int __fastcall CRdpSettingsFileStream::Write(CRdpSettingsFileStream *this, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rsi
  void *v4; // rcx
  int result; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  __int64 v8; // rdi
  DWORD v9; // edi
  __int64 v10; // rax
  unsigned int v11; // ebp
  unsigned int cbMultiByte; // eax
  void *v13; // rcx
  void *v14; // rax
  unsigned int v15; // eax
  int v16; // eax
  unsigned int v17; // eax
  __int16 v18; // [rsp+60h] [rbp+8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+18h] BYREF

  v2 = a2;
  NumberOfBytesWritten = 0;
  if ( *((_DWORD *)this + 19) )
  {
    if ( !a2 )
      return -2147467259;
    if ( *((_DWORD *)this + 158) )
    {
      if ( *((_DWORD *)this + 159) )
      {
        v4 = (void *)*((_QWORD *)this + 10);
        v18 = -257;
        if ( !WriteFile(v4, &v18, 2u, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        if ( NumberOfBytesWritten != 2 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return -2147023883;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v7 = 22;
          goto LABEL_13;
        }
        *((_DWORD *)this + 159) = 0;
      }
      v8 = -1;
      do
        ++v8;
      while ( v2[v8] );
      v9 = 2 * v8;
      goto LABEL_33;
    }
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v11 = v10 + 1;
    cbMultiByte = *((_DWORD *)this + 24);
    if ( v11 > cbMultiByte )
    {
      v13 = (void *)*((_QWORD *)this + 11);
      if ( v13 )
      {
        LocalFree(v13);
        *((_QWORD *)this + 11) = 0;
      }
      v14 = MIDL_user_allocate(v11);
      *((_QWORD *)this + 11) = v14;
      if ( !v14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
            v15,
            (__int64)"_pAnsiLineBuf");
        }
        return -2147024882;
      }
      *((_DWORD *)this + 24) = v11;
      cbMultiByte = v11;
    }
    v16 = WideCharToMultiByte(0, 0x640u, v2, -1, *((LPSTR *)this + 11), cbMultiByte, 0, 0);
    if ( !v16 )
      goto LABEL_6;
    v2 = (const WCHAR *)*((_QWORD *)this + 11);
    v9 = v16 - 1;
LABEL_33:
    if ( WriteFile(*((HANDLE *)this + 10), v2, v9, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten == v9 )
        return 0;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return -2147023883;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 24;
LABEL_13:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
        CurrentThreadActivityIdPrefix);
      return -2147023883;
    }
LABEL_6:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v17);
  }
  return -2147024891;
}

```

## disassembly

```asm
0x1400a85b0  mov     r11, rsp
0x1400a85b3  mov     [r11+10h], rbx
0x1400a85b7  mov     [r11+20h], rbp
0x1400a85bb  push    rsi
0x1400a85bc  push    rdi
0x1400a85bd  push    r14
0x1400a85bf  sub     rsp, 40h
0x1400a85c3  xor     r14d, r14d
0x1400a85c6  mov     rsi, rdx
0x1400a85c9  mov     rbx, rcx
0x1400a85cc  mov     [r11+18h], r14d
0x1400a85d0  cmp     [rcx+4Ch], r14d
0x1400a85d4  jz      loc_1400A87FA
0x1400a85da  test    rdx, rdx
0x1400a85dd  jz      loc_1400A87F3
0x1400a85e3  cmp     [rcx+278h], r14d
0x1400a85ea  jz      loc_1400A86B0
0x1400a85f0  cmp     [rcx+27Ch], r14d
0x1400a85f7  jz      loc_1400A869B
0x1400a85fd  mov     rcx, [rcx+50h]; hFile
0x1400a8601  lea     r9, [r11+18h]; lpNumberOfBytesWritten
0x1400a8605  mov     eax, 0FEFFh
0x1400a860a  mov     [r11-38h], r14
0x1400a860e  lea     r8d, [r14+2]; nNumberOfBytesToWrite
0x1400a8612  mov     [rsp+58h+arg_0], ax
0x1400a8617  lea     rdx, [r11+8]; lpBuffer
0x1400a861b  call    cs:__imp_WriteFile
0x1400a8621  test    eax, eax
0x1400a8623  jnz     short loc_1400A8640
0x1400a8625  call    cs:__imp_GetLastError
0x1400a862b  test    eax, eax
0x1400a862d  jle     loc_1400A8842
0x1400a8633  movzx   eax, ax
0x1400a8636  or      eax, 80070000h
0x1400a863b  jmp     loc_1400A8842
0x1400a8640  cmp     [rsp+58h+NumberOfBytesWritten], 2
0x1400a8645  jz      short loc_1400A8694
0x1400a8647  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a864e  lea     rax, WPP_GLOBAL_Control
0x1400a8655  cmp     rcx, rax
0x1400a8658  jz      short loc_1400A868A
0x1400a865a  test    byte ptr [rcx+1Ch], 1
0x1400a865e  jz      short loc_1400A868A
0x1400a8660  cmp     byte ptr [rcx+19h], 2
0x1400a8664  jb      short loc_1400A868A
0x1400a8666  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a866b  mov     edx, 16h
0x1400a8670  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8677  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a867e  mov     r9d, eax
0x1400a8681  mov     rcx, [rcx+10h]
0x1400a8685  call    WPP_SF_d
0x1400a868a  mov     eax, 800703F5h
0x1400a868f  jmp     loc_1400A8842
0x1400a8694  mov     [rbx+27Ch], r14d
0x1400a869b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400a869f  inc     rdi
0x1400a86a2  cmp     [rsi+rdi*2], r14w
0x1400a86a7  jnz     short loc_1400A869F
0x1400a86a9  add     edi, edi
0x1400a86ab  jmp     loc_1400A8789
0x1400a86b0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400a86b4  mov     rax, rdi
0x1400a86b7  inc     rax
0x1400a86ba  cmp     [rdx+rax*2], r14w
0x1400a86bf  jnz     short loc_1400A86B7
0x1400a86c1  lea     ebp, [rax+1]
0x1400a86c4  mov     eax, [rcx+60h]
0x1400a86c7  cmp     ebp, eax
0x1400a86c9  jbe     loc_1400A8750
0x1400a86cf  mov     rcx, [rcx+58h]; hMem
0x1400a86d3  test    rcx, rcx
0x1400a86d6  jz      short loc_1400A86E2
0x1400a86d8  call    cs:__imp_LocalFree
0x1400a86de  mov     [rbx+58h], r14
0x1400a86e2  mov     ecx, ebp; size
0x1400a86e4  call    MIDL_user_allocate
0x1400a86e9  mov     [rbx+58h], rax
0x1400a86ed  test    rax, rax
0x1400a86f0  jnz     short loc_1400A874B
0x1400a86f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a86f9  lea     rax, WPP_GLOBAL_Control
0x1400a8700  cmp     rcx, rax
0x1400a8703  jz      short loc_1400A8741
0x1400a8705  test    byte ptr [rcx+1Ch], 8
0x1400a8709  jz      short loc_1400A8741
0x1400a870b  cmp     byte ptr [rcx+19h], 2
0x1400a870f  jb      short loc_1400A8741
0x1400a8711  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a8716  lea     rcx, aPansilinebuf; "_pAnsiLineBuf"
0x1400a871d  mov     edx, 17h
0x1400a8722  mov     [rsp+58h+lpMultiByteStr], rcx
0x1400a8727  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a872e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8735  mov     r9d, eax
0x1400a8738  mov     rcx, [rcx+10h]
0x1400a873c  call    WPP_SF_Ds
0x1400a8741  mov     eax, 8007000Eh
0x1400a8746  jmp     loc_1400A8842
0x1400a874b  mov     [rbx+60h], ebp
0x1400a874e  mov     eax, ebp
0x1400a8750  mov     [rsp+58h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1400a8755  mov     r9d, edi; cchWideChar
0x1400a8758  mov     [rsp+58h+lpDefaultChar], r14; lpDefaultChar
0x1400a875d  mov     r8, rsi; lpWideCharStr
0x1400a8760  mov     [rsp+58h+cbMultiByte], eax; cbMultiByte
0x1400a8764  mov     edx, 640h; dwFlags
0x1400a8769  mov     rax, [rbx+58h]
0x1400a876d  xor     ecx, ecx; CodePage
0x1400a876f  mov     [rsp+58h+lpMultiByteStr], rax; lpMultiByteStr
0x1400a8774  call    cs:__imp_WideCharToMultiByte
0x1400a877a  test    eax, eax
0x1400a877c  jz      loc_1400A8625
0x1400a8782  mov     rsi, [rbx+58h]
0x1400a8786  lea     edi, [rax-1]
0x1400a8789  mov     rcx, [rbx+50h]; hFile
0x1400a878d  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400a8792  mov     r8d, edi; nNumberOfBytesToWrite
0x1400a8795  mov     [rsp+58h+lpMultiByteStr], r14; lpOverlapped
0x1400a879a  mov     rdx, rsi; lpBuffer
0x1400a879d  call    cs:__imp_WriteFile
0x1400a87a3  test    eax, eax
0x1400a87a5  jz      loc_1400A8625
0x1400a87ab  cmp     [rsp+58h+NumberOfBytesWritten], edi
0x1400a87af  jnz     short loc_1400A87B9
0x1400a87b1  mov     eax, r14d
0x1400a87b4  jmp     loc_1400A8842
0x1400a87b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a87c0  lea     rax, WPP_GLOBAL_Control
0x1400a87c7  cmp     rcx, rax
0x1400a87ca  jz      loc_1400A868A
0x1400a87d0  test    byte ptr [rcx+1Ch], 1
0x1400a87d4  jz      loc_1400A868A
0x1400a87da  cmp     byte ptr [rcx+19h], 2
0x1400a87de  jb      loc_1400A868A
0x1400a87e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a87e9  mov     edx, 18h
0x1400a87ee  jmp     loc_1400A8670
0x1400a87f3  mov     eax, 80004005h
0x1400a87f8  jmp     short loc_1400A8842
0x1400a87fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8801  lea     rax, WPP_GLOBAL_Control
0x1400a8808  cmp     rcx, rax
0x1400a880b  jz      short loc_1400A883D
0x1400a880d  test    byte ptr [rcx+1Ch], 1
0x1400a8811  jz      short loc_1400A883D
0x1400a8813  cmp     byte ptr [rcx+19h], 2
0x1400a8817  jb      short loc_1400A883D
0x1400a8819  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a881e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8825  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a882c  mov     edx, 19h
0x1400a8831  mov     r9d, eax
0x1400a8834  mov     rcx, [rcx+10h]
0x1400a8838  call    WPP_SF_d
0x1400a883d  mov     eax, 80070005h
0x1400a8842  mov     rbx, [rsp+58h+arg_8]
0x1400a8847  mov     rbp, [rsp+58h+arg_18]
0x1400a884c  add     rsp, 40h
0x1400a8850  pop     r14
0x1400a8852  pop     rdi
0x1400a8853  pop     rsi
0x1400a8854  retn
```
