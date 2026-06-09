# FdiCallbacks::CallbackFileOpen(char *,int,int)

- ea: `0x18000cee0`
- end: `0x18000d04f`
- name: `?CallbackFileOpen@FdiCallbacks@@SA_JPEADHH@Z`
- size: `367`
- prototype: `INT_PTR __fastcall(LPSTR pszFile, unsigned int oflag, int pmode)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800088dc`
- `0x18000c8e0`

## callees

- `0x180001540`
- `0x180001564`
- `0x180001570`
- `0x180002e54`
- `0x180003648`
- `0x1800082b8`
- `0x18000b34c`
- `0x18000b5ac`
- `0x18000be70`
- `0x18000c7a4`
- `0x18000cee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d001`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d001`

## pseudocode

```c
INT_PTR __fastcall FdiCallbacks::CallbackFileOpen(LPSTR pszFile, unsigned int oflag, int pmode)
{
  __int64 v4; // rdi
  size_t v5; // r8
  int v6; // eax
  _QWORD *v7; // rdx
  char *v8; // rbx
  __int64 v9; // rax
  _QWORD *v11; // [rsp+20h] [rbp-60h] BYREF
  char *v12; // [rsp+28h] [rbp-58h]
  __int64 v13; // [rsp+30h] [rbp-50h]
  __int128 v14; // [rsp+38h] [rbp-48h] BYREF
  __int64 v15; // [rsp+48h] [rbp-38h]
  __int64 v16; // [rsp+50h] [rbp-30h]
  CHAR MultiByteStr[16]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v18; // [rsp+68h] [rbp-18h]
  __int64 v19; // [rsp+70h] [rbp-10h]

  v13 = -2;
  *(_OWORD *)MultiByteStr = 0;
  v18 = 0;
  v19 = 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( pszFile[v5] );
  std::string::_Construct<1,char const *>(MultiByteStr, pszFile, v5);
  v14 = 0;
  v15 = 0;
  v16 = 7;
  LOWORD(v14) = 0;
  v11 = 0;
  v6 = Utils::ConvertStringToPointer(MultiByteStr, &v11);
  if ( v6 >= 0 )
  {
    v7 = v11 + 16;
    if ( &v14 != (__int128 *)(v11 + 16) )
    {
      if ( v11[19] > 7u )
        v7 = (_QWORD *)*v7;
      std::wstring::_Assign<wchar_t>((void **)&v14, v7, v11[18]);
    }
    goto LABEL_10;
  }
  if ( v6 == -2147024883 && (int)Utils::ConvertMultiByteToUnicode(MultiByteStr) >= 0 )
  {
LABEL_10:
    v12 = 0;
    v8 = (char *)operator new(0x20u);
    *(_WORD *)(v8 + 29) = 0;
    v8[31] = 0;
    *(_QWORD *)v8 = 0;
    *((_QWORD *)v8 + 1) = 0;
    *((_QWORD *)v8 + 2) = 0;
    *((_DWORD *)v8 + 6) = 0;
    v12 = v8;
    v8[28] = 1;
    v9 = Utils::OpenFile(&v14, oflag);
    *(_QWORD *)v8 = v9;
    if ( v9 == -1 )
    {
      SetLastError(0x801882E8);
      operator delete(v8);
    }
    else
    {
      v4 = (__int64)v8;
    }
  }
  std::wstring::~wstring((char **)&v14);
  std::string::~string((char **)MultiByteStr);
  return v4;
}

```

## disassembly

```asm
0x18000cee0  mov     rax, rsp
0x18000cee3  push    rbp
0x18000cee4  push    rsi
0x18000cee5  push    rdi
0x18000cee6  mov     rbp, rsp
0x18000cee9  sub     rsp, 80h
0x18000cef0  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18000cef8  mov     [rax+18h], rbx
0x18000cefc  mov     rax, cs:__security_cookie
0x18000cf03  xor     rax, rsp
0x18000cf06  mov     [rbp+var_8], rax
0x18000cf0a  mov     esi, edx
0x18000cf0c  xorps   xmm0, xmm0
0x18000cf0f  movups  xmmword ptr [rbp+MultiByteStr], xmm0
0x18000cf13  mov     [rbp+var_18], 0
0x18000cf1b  mov     [rbp+var_10], 0
0x18000cf23  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000cf27  mov     r8, rdi
0x18000cf2a  inc     r8
0x18000cf2d  cmp     byte ptr [rcx+r8], 0
0x18000cf32  jnz     short loc_18000CF2A
0x18000cf34  mov     rdx, rcx
0x18000cf37  lea     rcx, [rbp+MultiByteStr]
0x18000cf3b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000cf40  nop
0x18000cf41  xorps   xmm0, xmm0
0x18000cf44  movups  [rbp+var_48], xmm0
0x18000cf48  mov     [rbp+var_38], 0
0x18000cf50  mov     [rbp+var_30], 7
0x18000cf58  xor     eax, eax
0x18000cf5a  mov     word ptr [rbp+var_48], ax
0x18000cf5e  mov     [rbp+var_60], rax
0x18000cf62  lea     rdx, [rbp+var_60]
0x18000cf66  lea     rcx, [rbp+MultiByteStr]
0x18000cf6a  call    ?ConvertStringToPointer@Utils@@SAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAX@Z; Utils::ConvertStringToPointer(std::string &,void * *)
0x18000cf6f  test    eax, eax
0x18000cf71  js      short loc_18000CF9D
0x18000cf73  mov     rdx, [rbp+var_60]
0x18000cf77  sub     rdx, 0FFFFFFFFFFFFFF80h
0x18000cf7b  lea     rax, [rbp+var_48]
0x18000cf7f  cmp     rax, rdx
0x18000cf82  jz      short loc_18000CFB5
0x18000cf84  mov     r8, [rdx+10h]
0x18000cf88  cmp     qword ptr [rdx+18h], 7
0x18000cf8d  jbe     short loc_18000CF92
0x18000cf8f  mov     rdx, [rdx]
0x18000cf92  lea     rcx, [rbp+var_48]
0x18000cf96  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000cf9b  jmp     short loc_18000CFB5
0x18000cf9d  cmp     eax, 8007000Dh
0x18000cfa2  jnz     short loc_18000D01A
0x18000cfa4  lea     rdx, [rbp+var_48]
0x18000cfa8  lea     rcx, [rbp+MultiByteStr]; lpMultiByteStr
0x18000cfac  call    ?ConvertMultiByteToUnicode@Utils@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Utils::ConvertMultiByteToUnicode(std::string const &,std::wstring *)
0x18000cfb1  test    eax, eax
0x18000cfb3  js      short loc_18000D01A
0x18000cfb5  mov     [rbp+var_58], 0
0x18000cfbd  mov     ecx, 20h ; ' '; Size
0x18000cfc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cfc7  mov     rbx, rax
0x18000cfca  xor     ecx, ecx
0x18000cfcc  mov     [rax+1Dh], cx
0x18000cfd0  mov     [rax+1Fh], cl
0x18000cfd3  mov     [rax], rcx
0x18000cfd6  mov     [rax+8], rcx
0x18000cfda  mov     [rax+10h], rcx
0x18000cfde  mov     [rax+18h], ecx
0x18000cfe1  mov     [rbp+var_58], rax
0x18000cfe5  mov     byte ptr [rax+1Ch], 1
0x18000cfe9  mov     edx, esi
0x18000cfeb  lea     rcx, [rbp+var_48]
0x18000cfef  call    ?OpenFile@Utils@@SA_JAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@HH@Z; Utils::OpenFile(std::wstring const &,int,int)
0x18000cff4  mov     [rbx], rax
0x18000cff7  cmp     rax, rdi
0x18000cffa  jnz     short loc_18000D017
0x18000cffc  mov     ecx, 801882E8h; dwErrCode
0x18000d001  call    cs:__imp_SetLastError
0x18000d007  nop
0x18000d008  mov     edx, 20h ; ' '; unsigned __int64
0x18000d00d  mov     rcx, rbx; void *
0x18000d010  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d015  jmp     short loc_18000D01A
0x18000d017  mov     rdi, rbx
0x18000d01a  lea     rcx, [rbp+var_48]
0x18000d01e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d023  nop
0x18000d024  lea     rcx, [rbp+MultiByteStr]
0x18000d028  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000d02d  mov     rax, rdi
0x18000d030  mov     rcx, [rbp+var_8]
0x18000d034  xor     rcx, rsp; StackCookie
0x18000d037  call    __security_check_cookie
0x18000d03c  mov     rbx, [rsp+80h+arg_10]
0x18000d044  add     rsp, 80h
0x18000d04b  pop     rdi
0x18000d04c  pop     rsi
0x18000d04d  pop     rbp
0x18000d04e  retn
```
