# _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18000af40`
- end: `0x18000b2f2`
- name: `?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `946`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x18000ab9c`
- `0x18003c344`
- `0x18003ea08`

## callees

- `0x18000113c`
- `0x180002890`
- `0x1800028b4`
- `0x18000a074`
- `0x18000af40`
- `0x18000b2f8`
- `0x18000c1a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b212`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000b03b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000b1e9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000b03b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000b1e9`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathByHandle(HANDLE hFile, __int64 a2)
{
  int FinalPathOnUnmountedVolume; // ebx
  int *v5; // rax
  int *v6; // rcx
  void *v7; // rdx
  DWORD FinalPathNameByHandleW; // eax
  unsigned __int64 v9; // rdi
  signed int LastError; // eax
  WCHAR *v11; // rdx
  LPWSTR v12; // r8
  unsigned __int64 v13; // rax
  DWORD v14; // eax
  int v16; // [rsp+30h] [rbp-39h] BYREF
  int v17; // [rsp+34h] [rbp-35h] BYREF
  LPWSTR lpszFilePath; // [rsp+38h] [rbp-31h] BYREF
  WCHAR *v19; // [rsp+40h] [rbp-29h]
  _WORD v20[12]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-9h] BYREF
  int *v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+88h] [rbp+1Fh]
  int *v24; // [rsp+90h] [rbp+27h]
  __int64 v25; // [rsp+98h] [rbp+2Fh]

  lpszFilePath = v20;
  v19 = v20;
  v20[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                           &lpszFilePath,
                           261) )
  {
    FinalPathOnUnmountedVolume = -2147024882;
    if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    {
      v17 = -2147024882;
      v5 = &v17;
      v16 = 261;
      v6 = &v16;
      v7 = &unk_180057780;
LABEL_6:
      v22 = v6;
      v24 = v5;
      v23 = 4;
      v25 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180062000, v7, 0, 0, 4, v21);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, lpszFilePath, v19 - lpszFilePath, 0);
  v9 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    FinalPathOnUnmountedVolume = LastError;
    if ( LastError == 3 )
    {
      FinalPathOnUnmountedVolume = _werDetail::UtilGetFinalPathOnUnmountedVolume(hFile, a2);
    }
    else
    {
      if ( LastError > 0 )
        FinalPathOnUnmountedVolume = (unsigned __int16)LastError | 0x80070000;
      if ( FinalPathOnUnmountedVolume >= 0 )
        FinalPathOnUnmountedVolume = -2147467259;
      if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
      {
        v16 = FinalPathOnUnmountedVolume;
        v22 = &v16;
        v23 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_180062000, &dword_18005774C, 0, 0, 3, v21);
      }
    }
    goto LABEL_44;
  }
  v11 = v19;
  v12 = lpszFilePath;
  v13 = v19 - lpszFilePath;
  if ( v9 == v13 )
  {
    FinalPathOnUnmountedVolume = -2147418113;
    if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    {
      v16 = -2147418113;
      v22 = &v16;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180062000, &byte_18005770F, 0, 0, 3, v21);
    }
    goto LABEL_44;
  }
  if ( v9 <= v13 )
    goto LABEL_41;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &lpszFilePath,
                          v9) )
  {
    v14 = GetFinalPathNameByHandleW(hFile, lpszFilePath, v19 - lpszFilePath, 0);
    v9 = v14;
    if ( !v14 )
    {
      FinalPathOnUnmountedVolume = GetLastError();
      if ( FinalPathOnUnmountedVolume <= 0 )
      {
LABEL_35:
        if ( FinalPathOnUnmountedVolume >= 0 )
          FinalPathOnUnmountedVolume = -2147467259;
        if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
        {
          v16 = FinalPathOnUnmountedVolume;
          v22 = &v16;
          v23 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_180062000, &dword_180057694, 0, 0, 3, v21);
        }
        goto LABEL_44;
      }
LABEL_34:
      FinalPathOnUnmountedVolume = (unsigned __int16)FinalPathOnUnmountedVolume | 0x80070000;
      goto LABEL_35;
    }
    v11 = v19;
    v12 = lpszFilePath;
    if ( v14 >= (unsigned __int64)(v19 - lpszFilePath) )
    {
      LOWORD(FinalPathOnUnmountedVolume) = 111;
      goto LABEL_34;
    }
LABEL_41:
    if ( (unsigned int)v9 > (unsigned __int64)(v11 - v12) )
      __int2c();
    v19 = &v12[v9];
    *v19 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, (__int64)&lpszFilePath);
    FinalPathOnUnmountedVolume = 0;
    goto LABEL_44;
  }
  FinalPathOnUnmountedVolume = -2147024882;
  if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
  {
    v16 = -2147024882;
    v5 = &v16;
    v17 = v9;
    v6 = &v17;
    v7 = &unk_1800576C8;
    goto LABEL_6;
  }
LABEL_44:
  if ( lpszFilePath != v20 )
    operator delete(lpszFilePath, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)FinalPathOnUnmountedVolume;
}

```

## disassembly

```asm
0x18000af40  mov     [rsp-8+arg_10], rbx
0x18000af45  mov     [rsp-8+arg_18], rsi
0x18000af4a  push    rbp
0x18000af4b  push    rdi
0x18000af4c  push    r14
0x18000af4e  lea     rbp, [rsp-47h]
0x18000af53  sub     rsp, 0B0h
0x18000af5a  mov     rax, cs:__security_cookie
0x18000af61  xor     rax, rsp
0x18000af64  mov     [rbp+57h+var_20], rax
0x18000af68  lea     rax, [rbp+57h+var_78]
0x18000af6c  mov     r14, rdx
0x18000af6f  mov     [rbp+57h+lpszFilePath], rax
0x18000af73  mov     rsi, rcx
0x18000af76  lea     rax, [rbp+57h+var_78]
0x18000af7a  mov     edi, 105h
0x18000af7f  mov     [rbp+57h+var_80], rax
0x18000af83  lea     rcx, [rbp+57h+lpszFilePath]
0x18000af87  xor     eax, eax
0x18000af89  mov     edx, edi
0x18000af8b  mov     [rbp+57h+var_78], ax
0x18000af8f  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18000af94  test    al, al
0x18000af96  jnz     loc_18000B027
0x18000af9c  mov     eax, cs:dword_180062000
0x18000afa2  mov     ebx, 8007000Eh
0x18000afa7  cmp     eax, 2
0x18000afaa  jbe     loc_18000B2B3
0x18000afb0  mov     rcx, cs:qword_180062018
0x18000afb7  mov     rax, cs:qword_180062010
0x18000afbe  test    al, 8
0x18000afc0  jz      loc_18000B2B3
0x18000afc6  mov     rax, rcx
0x18000afc9  and     eax, 8
0x18000afcc  cmp     rax, rcx
0x18000afcf  jnz     loc_18000B2B3
0x18000afd5  mov     [rbp+57h+var_8C], 8007000Eh
0x18000afdc  lea     rax, [rbp+57h+var_8C]
0x18000afe0  mov     [rbp+57h+var_90], edi
0x18000afe3  lea     rcx, [rbp+57h+var_90]
0x18000afe7  lea     rdx, unk_180057780
0x18000afee  mov     [rbp+57h+var_40], rcx
0x18000aff2  lea     rcx, [rbp+57h+var_60]
0x18000aff6  mov     [rbp+57h+var_30], rax
0x18000affa  mov     eax, 4
0x18000afff  mov     [rsp+0C0h+var_98], rcx
0x18000b004  mov     [rsp+0C0h+var_A0], eax
0x18000b008  mov     [rbp+57h+var_38], rax
0x18000b00c  mov     [rbp+57h+var_28], rax
0x18000b010  xor     r9d, r9d
0x18000b013  lea     rcx, dword_180062000
0x18000b01a  xor     r8d, r8d
0x18000b01d  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b022  jmp     loc_18000B2B3
0x18000b027  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x18000b02b  xor     r9d, r9d; dwFlags
0x18000b02e  mov     r8, [rbp+57h+var_80]
0x18000b032  mov     rcx, rsi; hFile
0x18000b035  sub     r8, rdx
0x18000b038  sar     r8, 1; cchFilePath
0x18000b03b  call    cs:__imp_GetFinalPathNameByHandleW
0x18000b041  mov     edi, eax
0x18000b043  test    eax, eax
0x18000b045  jnz     loc_18000B0E5
0x18000b04b  call    cs:__imp_GetLastError
0x18000b051  mov     ebx, eax
0x18000b053  cmp     eax, 3
0x18000b056  jnz     short loc_18000B06A
0x18000b058  mov     rdx, r14
0x18000b05b  mov     rcx, rsi
0x18000b05e  call    ?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18000b063  mov     ebx, eax
0x18000b065  jmp     loc_18000B2B3
0x18000b06a  test    eax, eax
0x18000b06c  jle     short loc_18000B077
0x18000b06e  movzx   ebx, ax
0x18000b071  or      ebx, 80070000h
0x18000b077  test    ebx, ebx
0x18000b079  mov     eax, 80004005h
0x18000b07e  cmovns  ebx, eax
0x18000b081  mov     eax, cs:dword_180062000
0x18000b087  cmp     eax, 2
0x18000b08a  jbe     loc_18000B2B3
0x18000b090  mov     rcx, cs:qword_180062018
0x18000b097  mov     rax, cs:qword_180062010
0x18000b09e  test    al, 8
0x18000b0a0  jz      loc_18000B2B3
0x18000b0a6  mov     rax, rcx
0x18000b0a9  and     eax, 8
0x18000b0ac  cmp     rax, rcx
0x18000b0af  jnz     loc_18000B2B3
0x18000b0b5  lea     rax, [rbp+57h+var_90]
0x18000b0b9  mov     [rbp+57h+var_90], ebx
0x18000b0bc  mov     [rbp+57h+var_40], rax
0x18000b0c0  lea     rdx, dword_18005774C
0x18000b0c7  lea     rax, [rbp+57h+var_60]
0x18000b0cb  mov     [rbp+57h+var_38], 4
0x18000b0d3  mov     [rsp+0C0h+var_98], rax
0x18000b0d8  mov     [rsp+0C0h+var_A0], 3
0x18000b0e0  jmp     loc_18000B010
0x18000b0e5  mov     rdx, [rbp+57h+var_80]
0x18000b0e9  mov     r8, [rbp+57h+lpszFilePath]
0x18000b0ed  mov     rax, rdx
0x18000b0f0  sub     rax, r8
0x18000b0f3  sar     rax, 1
0x18000b0f6  cmp     rdi, rax
0x18000b0f9  jnz     short loc_18000B168
0x18000b0fb  mov     eax, cs:dword_180062000
0x18000b101  mov     ebx, 8000FFFFh
0x18000b106  cmp     eax, 2
0x18000b109  jbe     loc_18000B2B3
0x18000b10f  mov     rcx, cs:qword_180062018
0x18000b116  mov     rax, cs:qword_180062010
0x18000b11d  test    al, 8
0x18000b11f  jz      loc_18000B2B3
0x18000b125  mov     rax, rcx
0x18000b128  and     eax, 8
0x18000b12b  cmp     rax, rcx
0x18000b12e  jnz     loc_18000B2B3
0x18000b134  lea     rax, [rbp+57h+var_90]
0x18000b138  mov     [rbp+57h+var_90], 8000FFFFh
0x18000b13f  mov     [rbp+57h+var_40], rax
0x18000b143  lea     rdx, byte_18005770F
0x18000b14a  lea     rax, [rbp+57h+var_60]
0x18000b14e  mov     [rbp+57h+var_38], 4
0x18000b156  mov     [rsp+0C0h+var_98], rax
0x18000b15b  mov     [rsp+0C0h+var_A0], 3
0x18000b163  jmp     loc_18000B010
0x18000b168  jbe     loc_18000B289
0x18000b16e  mov     rdx, rdi
0x18000b171  lea     rcx, [rbp+57h+lpszFilePath]
0x18000b175  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18000b17a  test    al, al
0x18000b17c  jnz     short loc_18000B1D5
0x18000b17e  mov     eax, cs:dword_180062000
0x18000b184  mov     ebx, 8007000Eh
0x18000b189  cmp     eax, 2
0x18000b18c  jbe     loc_18000B2B3
0x18000b192  mov     rcx, cs:qword_180062018
0x18000b199  mov     rax, cs:qword_180062010
0x18000b1a0  test    al, 8
0x18000b1a2  jz      loc_18000B2B3
0x18000b1a8  mov     rax, rcx
0x18000b1ab  and     eax, 8
0x18000b1ae  cmp     rax, rcx
0x18000b1b1  jnz     loc_18000B2B3
0x18000b1b7  mov     [rbp+57h+var_90], 8007000Eh
0x18000b1be  lea     rax, [rbp+57h+var_90]
0x18000b1c2  mov     [rbp+57h+var_8C], edi
0x18000b1c5  lea     rcx, [rbp+57h+var_8C]
0x18000b1c9  lea     rdx, unk_1800576C8
0x18000b1d0  jmp     loc_18000AFEE
0x18000b1d5  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x18000b1d9  xor     r9d, r9d; dwFlags
0x18000b1dc  mov     r8, [rbp+57h+var_80]
0x18000b1e0  mov     rcx, rsi; hFile
0x18000b1e3  sub     r8, rdx
0x18000b1e6  sar     r8, 1; cchFilePath
0x18000b1e9  call    cs:__imp_GetFinalPathNameByHandleW
0x18000b1ef  mov     edi, eax
0x18000b1f1  test    eax, eax
0x18000b1f3  jz      short loc_18000B212
0x18000b1f5  mov     rdx, [rbp+57h+var_80]
0x18000b1f9  mov     r8, [rbp+57h+lpszFilePath]
0x18000b1fd  mov     rcx, rdx
0x18000b200  sub     rcx, r8
0x18000b203  sar     rcx, 1
0x18000b206  cmp     rdi, rcx
0x18000b209  jb      short loc_18000B289
0x18000b20b  mov     ebx, 6Fh ; 'o'
0x18000b210  jmp     short loc_18000B21E
0x18000b212  call    cs:__imp_GetLastError
0x18000b218  mov     ebx, eax
0x18000b21a  test    eax, eax
0x18000b21c  jle     short loc_18000B227
0x18000b21e  movzx   ebx, bx
0x18000b221  or      ebx, 80070000h
0x18000b227  test    ebx, ebx
0x18000b229  mov     eax, 80004005h
0x18000b22e  cmovns  ebx, eax
0x18000b231  mov     eax, cs:dword_180062000
0x18000b237  cmp     eax, 2
0x18000b23a  jbe     short loc_18000B2B3
0x18000b23c  mov     rcx, cs:qword_180062018
0x18000b243  mov     rax, cs:qword_180062010
0x18000b24a  test    al, 8
0x18000b24c  jz      short loc_18000B2B3
0x18000b24e  mov     rax, rcx
0x18000b251  and     eax, 8
0x18000b254  cmp     rax, rcx
0x18000b257  jnz     short loc_18000B2B3
0x18000b259  lea     rax, [rbp+57h+var_90]
0x18000b25d  mov     [rbp+57h+var_90], ebx
0x18000b260  mov     [rbp+57h+var_40], rax
0x18000b264  lea     rdx, dword_180057694
0x18000b26b  lea     rax, [rbp+57h+var_60]
0x18000b26f  mov     [rbp+57h+var_38], 4
0x18000b277  mov     [rsp+0C0h+var_98], rax
0x18000b27c  mov     [rsp+0C0h+var_A0], 3
0x18000b284  jmp     loc_18000B010
0x18000b289  sub     rdx, r8
0x18000b28c  mov     eax, edi
0x18000b28e  sar     rdx, 1
0x18000b291  cmp     rax, rdx
0x18000b294  jbe     short loc_18000B298
0x18000b296  int     2Ch; Windows NT - assertion failure
0x18000b298  lea     rcx, [r8+rdi*2]
0x18000b29c  xor     eax, eax
0x18000b29e  mov     [rbp+57h+var_80], rcx
0x18000b2a2  lea     rdx, [rbp+57h+lpszFilePath]
0x18000b2a6  mov     [rcx], ax
0x18000b2a9  mov     rcx, r14
0x18000b2ac  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18000b2b1  xor     ebx, ebx
0x18000b2b3  mov     rcx, [rbp+57h+lpszFilePath]; void *
0x18000b2b7  lea     rax, [rbp+57h+var_78]
0x18000b2bb  cmp     rcx, rax
0x18000b2be  jz      short loc_18000B2CC
0x18000b2c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b2c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b2cc  mov     eax, ebx
0x18000b2ce  mov     rcx, [rbp+57h+var_20]
0x18000b2d2  xor     rcx, rsp; StackCookie
0x18000b2d5  call    __security_check_cookie
0x18000b2da  lea     r11, [rsp+0C0h+var_10]
0x18000b2e2  mov     rbx, [r11+30h]
0x18000b2e6  mov     rsi, [r11+38h]
0x18000b2ea  mov     rsp, r11
0x18000b2ed  pop     r14
0x18000b2ef  pop     rdi
0x18000b2f0  pop     rbp
0x18000b2f1  retn
```
