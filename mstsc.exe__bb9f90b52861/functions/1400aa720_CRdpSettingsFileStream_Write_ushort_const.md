# CRdpSettingsFileStream::Write(ushort const *)

- ea: `0x1400aa720`
- end: `0x1400aa9c5`
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
- `0x1400aa720`
- `0x1400b3ef0`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1400aa8e4`
- `KERNEL32!WideCharToMultiByte` at `0x1400aa8e4`
- `KERNEL32!WriteFile` at `0x1400aa78b`
- `KERNEL32!WriteFile` at `0x1400aa90d`
- `KERNEL32!WriteFile` at `0x1400aa78b`
- `KERNEL32!WriteFile` at `0x1400aa90d`
- `KERNEL32!LocalFree` at `0x1400aa848`
- `KERNEL32!LocalFree` at `0x1400aa848`
- `KERNEL32!GetLastError` at `0x1400aa795`
- `KERNEL32!GetLastError` at `0x1400aa795`

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
0x1400aa720  mov     r11, rsp
0x1400aa723  mov     [r11+10h], rbx
0x1400aa727  mov     [r11+20h], rbp
0x1400aa72b  push    rsi
0x1400aa72c  push    rdi
0x1400aa72d  push    r14
0x1400aa72f  sub     rsp, 40h
0x1400aa733  xor     r14d, r14d
0x1400aa736  mov     rsi, rdx
0x1400aa739  mov     rbx, rcx
0x1400aa73c  mov     [r11+18h], r14d
0x1400aa740  cmp     [rcx+4Ch], r14d
0x1400aa744  jz      loc_1400AA96A
0x1400aa74a  test    rdx, rdx
0x1400aa74d  jz      loc_1400AA963
0x1400aa753  cmp     [rcx+278h], r14d
0x1400aa75a  jz      loc_1400AA820
0x1400aa760  cmp     [rcx+27Ch], r14d
0x1400aa767  jz      loc_1400AA80B
0x1400aa76d  mov     rcx, [rcx+50h]; hFile
0x1400aa771  lea     r9, [r11+18h]; lpNumberOfBytesWritten
0x1400aa775  mov     eax, 0FEFFh
0x1400aa77a  mov     [r11-38h], r14
0x1400aa77e  lea     r8d, [r14+2]; nNumberOfBytesToWrite
0x1400aa782  mov     [rsp+58h+arg_0], ax
0x1400aa787  lea     rdx, [r11+8]; lpBuffer
0x1400aa78b  call    cs:__imp_WriteFile
0x1400aa791  test    eax, eax
0x1400aa793  jnz     short loc_1400AA7B0
0x1400aa795  call    cs:__imp_GetLastError
0x1400aa79b  test    eax, eax
0x1400aa79d  jle     loc_1400AA9B2
0x1400aa7a3  movzx   eax, ax
0x1400aa7a6  or      eax, 80070000h
0x1400aa7ab  jmp     loc_1400AA9B2
0x1400aa7b0  cmp     [rsp+58h+NumberOfBytesWritten], 2
0x1400aa7b5  jz      short loc_1400AA804
0x1400aa7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa7be  lea     rax, WPP_GLOBAL_Control
0x1400aa7c5  cmp     rcx, rax
0x1400aa7c8  jz      short loc_1400AA7FA
0x1400aa7ca  test    byte ptr [rcx+1Ch], 1
0x1400aa7ce  jz      short loc_1400AA7FA
0x1400aa7d0  cmp     byte ptr [rcx+19h], 2
0x1400aa7d4  jb      short loc_1400AA7FA
0x1400aa7d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa7db  mov     edx, 16h
0x1400aa7e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa7e7  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400aa7ee  mov     r9d, eax
0x1400aa7f1  mov     rcx, [rcx+10h]
0x1400aa7f5  call    WPP_SF_d
0x1400aa7fa  mov     eax, 800703F5h
0x1400aa7ff  jmp     loc_1400AA9B2
0x1400aa804  mov     [rbx+27Ch], r14d
0x1400aa80b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400aa80f  inc     rdi
0x1400aa812  cmp     [rsi+rdi*2], r14w
0x1400aa817  jnz     short loc_1400AA80F
0x1400aa819  add     edi, edi
0x1400aa81b  jmp     loc_1400AA8F9
0x1400aa820  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400aa824  mov     rax, rdi
0x1400aa827  inc     rax
0x1400aa82a  cmp     [rdx+rax*2], r14w
0x1400aa82f  jnz     short loc_1400AA827
0x1400aa831  lea     ebp, [rax+1]
0x1400aa834  mov     eax, [rcx+60h]
0x1400aa837  cmp     ebp, eax
0x1400aa839  jbe     loc_1400AA8C0
0x1400aa83f  mov     rcx, [rcx+58h]; hMem
0x1400aa843  test    rcx, rcx
0x1400aa846  jz      short loc_1400AA852
0x1400aa848  call    cs:__imp_LocalFree
0x1400aa84e  mov     [rbx+58h], r14
0x1400aa852  mov     ecx, ebp; size
0x1400aa854  call    MIDL_user_allocate
0x1400aa859  mov     [rbx+58h], rax
0x1400aa85d  test    rax, rax
0x1400aa860  jnz     short loc_1400AA8BB
0x1400aa862  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa869  lea     rax, WPP_GLOBAL_Control
0x1400aa870  cmp     rcx, rax
0x1400aa873  jz      short loc_1400AA8B1
0x1400aa875  test    byte ptr [rcx+1Ch], 8
0x1400aa879  jz      short loc_1400AA8B1
0x1400aa87b  cmp     byte ptr [rcx+19h], 2
0x1400aa87f  jb      short loc_1400AA8B1
0x1400aa881  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa886  lea     rcx, aPansilinebuf; "_pAnsiLineBuf"
0x1400aa88d  mov     edx, 17h
0x1400aa892  mov     [rsp+58h+lpMultiByteStr], rcx
0x1400aa897  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400aa89e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa8a5  mov     r9d, eax
0x1400aa8a8  mov     rcx, [rcx+10h]
0x1400aa8ac  call    WPP_SF_Ds
0x1400aa8b1  mov     eax, 8007000Eh
0x1400aa8b6  jmp     loc_1400AA9B2
0x1400aa8bb  mov     [rbx+60h], ebp
0x1400aa8be  mov     eax, ebp
0x1400aa8c0  mov     [rsp+58h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1400aa8c5  mov     r9d, edi; cchWideChar
0x1400aa8c8  mov     [rsp+58h+lpDefaultChar], r14; lpDefaultChar
0x1400aa8cd  mov     r8, rsi; lpWideCharStr
0x1400aa8d0  mov     [rsp+58h+cbMultiByte], eax; cbMultiByte
0x1400aa8d4  mov     edx, 640h; dwFlags
0x1400aa8d9  mov     rax, [rbx+58h]
0x1400aa8dd  xor     ecx, ecx; CodePage
0x1400aa8df  mov     [rsp+58h+lpMultiByteStr], rax; lpMultiByteStr
0x1400aa8e4  call    cs:__imp_WideCharToMultiByte
0x1400aa8ea  test    eax, eax
0x1400aa8ec  jz      loc_1400AA795
0x1400aa8f2  mov     rsi, [rbx+58h]
0x1400aa8f6  lea     edi, [rax-1]
0x1400aa8f9  mov     rcx, [rbx+50h]; hFile
0x1400aa8fd  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400aa902  mov     r8d, edi; nNumberOfBytesToWrite
0x1400aa905  mov     [rsp+58h+lpMultiByteStr], r14; lpOverlapped
0x1400aa90a  mov     rdx, rsi; lpBuffer
0x1400aa90d  call    cs:__imp_WriteFile
0x1400aa913  test    eax, eax
0x1400aa915  jz      loc_1400AA795
0x1400aa91b  cmp     [rsp+58h+NumberOfBytesWritten], edi
0x1400aa91f  jnz     short loc_1400AA929
0x1400aa921  mov     eax, r14d
0x1400aa924  jmp     loc_1400AA9B2
0x1400aa929  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa930  lea     rax, WPP_GLOBAL_Control
0x1400aa937  cmp     rcx, rax
0x1400aa93a  jz      loc_1400AA7FA
0x1400aa940  test    byte ptr [rcx+1Ch], 1
0x1400aa944  jz      loc_1400AA7FA
0x1400aa94a  cmp     byte ptr [rcx+19h], 2
0x1400aa94e  jb      loc_1400AA7FA
0x1400aa954  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa959  mov     edx, 18h
0x1400aa95e  jmp     loc_1400AA7E0
0x1400aa963  mov     eax, 80004005h
0x1400aa968  jmp     short loc_1400AA9B2
0x1400aa96a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa971  lea     rax, WPP_GLOBAL_Control
0x1400aa978  cmp     rcx, rax
0x1400aa97b  jz      short loc_1400AA9AD
0x1400aa97d  test    byte ptr [rcx+1Ch], 1
0x1400aa981  jz      short loc_1400AA9AD
0x1400aa983  cmp     byte ptr [rcx+19h], 2
0x1400aa987  jb      short loc_1400AA9AD
0x1400aa989  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa98e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa995  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400aa99c  mov     edx, 19h
0x1400aa9a1  mov     r9d, eax
0x1400aa9a4  mov     rcx, [rcx+10h]
0x1400aa9a8  call    WPP_SF_d
0x1400aa9ad  mov     eax, 80070005h
0x1400aa9b2  mov     rbx, [rsp+58h+arg_8]
0x1400aa9b7  mov     rbp, [rsp+58h+arg_18]
0x1400aa9bc  add     rsp, 40h
0x1400aa9c0  pop     r14
0x1400aa9c2  pop     rdi
0x1400aa9c3  pop     rsi
0x1400aa9c4  retn
```
