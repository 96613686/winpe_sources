# GetClientPath(HINSTANCE__ *,ushort * *)

- ea: `0x14005b0e8`
- end: `0x14005b373`
- name: `?GetClientPath@@YAJPEAUHINSTANCE__@@PEAPEAG@Z`
- size: `651`
- prototype: `__int64 __fastcall(HINSTANCE hModule, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x14005a2a4`
- `0x14005a9f4`

## callees

- `0x140008940`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14001e210`
- `0x14005b0e8`
- `0x1400b3ef0`
- `0x140113390`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x14005b25c`
- `SHLWAPI!PathRemoveFileSpecW` at `0x14005b25c`
- `KERNEL32!LocalFree` at `0x14005b307`
- `KERNEL32!LocalFree` at `0x14005b307`
- `KERNEL32!GetModuleFileNameW` at `0x14005b19c`
- `KERNEL32!GetModuleFileNameW` at `0x14005b19c`
- `KERNEL32!GetLastError` at `0x14005b1a6`
- `KERNEL32!GetLastError` at `0x14005b1a6`

## pseudocode

```c
__int64 __fastcall GetClientPath(HINSTANCE hModule, unsigned __int16 **a2)
{
  WCHAR *v4; // rax
  WCHAR *v5; // rsi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int LastError; // ebx
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  int v11; // edx
  unsigned int v12; // eax
  unsigned __int16 v14[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-28h]

  LODWORD(v15) = *(_DWORD *)L"e";
  *(_OWORD *)v14 = *(_OWORD *)L"mstsc.exe";
  *a2 = 0;
  v4 = (WCHAR *)MIDL_user_allocate(0x208u);
  v5 = v4;
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"TCHAR");
    }
    return (unsigned int)-2147024882;
  }
  if ( !GetModuleFileNameW(hModule, v4, 0x104u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids, v8, LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
      v9,
      (__int64)v5);
  }
  PathRemoveFileSpecW(v5);
  LastError = StringCchCatW(v5, 0x104u, L"\\");
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 17;
LABEL_31:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
      v10,
      (__int64)"StringCchCat failed!",
      LastError,
      *(_QWORD *)v14,
      *(_QWORD *)&v14[4],
      v15);
LABEL_32:
    LocalFree(v5);
    return (unsigned int)LastError;
  }
  LastError = StringCchCatW(v5, 0x104u, v14);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 18;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
      v12,
      (__int64)v5);
  }
  *a2 = v5;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14005b0e8  mov     [rsp+arg_10], rbx
0x14005b0ed  push    rsi
0x14005b0ee  push    rdi
0x14005b0ef  push    r14
0x14005b0f1  sub     rsp, 50h
0x14005b0f5  mov     rax, cs:__security_cookie
0x14005b0fc  xor     rax, rsp
0x14005b0ff  mov     [rsp+68h+var_20], rax
0x14005b104  movups  xmm0, xmmword ptr cs:aMstscExe; "mstsc.exe"
0x14005b10b  mov     eax, dword ptr cs:aMstscExe+10h; "e"
0x14005b111  mov     rbx, rcx
0x14005b114  mov     ecx, 208h; size
0x14005b119  mov     dword ptr [rsp+68h+var_28], eax
0x14005b11d  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x14005b122  mov     r14, rdx
0x14005b125  mov     qword ptr [rdx], 0
0x14005b12c  call    MIDL_user_allocate
0x14005b131  mov     rsi, rax
0x14005b134  test    rax, rax
0x14005b137  jnz     short loc_14005B190
0x14005b139  mov     rax, cs:WPP_GLOBAL_Control
0x14005b140  lea     rdi, WPP_GLOBAL_Control
0x14005b147  cmp     rax, rdi
0x14005b14a  jz      short loc_14005B186
0x14005b14c  test    byte ptr [rax+1Ch], 8
0x14005b150  jz      short loc_14005B186
0x14005b152  cmp     byte ptr [rax+19h], 2
0x14005b156  jb      short loc_14005B186
0x14005b158  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b15d  lea     rcx, aTchar; "TCHAR"
0x14005b164  mov     r9d, eax
0x14005b167  mov     [rsp+68h+var_48], rcx
0x14005b16c  lea     edx, [rsi+0Eh]
0x14005b16f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b176  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005b17d  mov     rcx, [rcx+10h]
0x14005b181  call    WPP_SF_Ds
0x14005b186  mov     ebx, 8007000Eh
0x14005b18b  jmp     loc_14005B353
0x14005b190  mov     r8d, 104h; nSize
0x14005b196  mov     rdx, rsi; lpFilename
0x14005b199  mov     rcx, rbx; hModule
0x14005b19c  call    cs:__imp_GetModuleFileNameW
0x14005b1a2  test    eax, eax
0x14005b1a4  jnz     short loc_14005B211
0x14005b1a6  call    cs:__imp_GetLastError
0x14005b1ac  mov     ebx, eax
0x14005b1ae  mov     rax, cs:WPP_GLOBAL_Control
0x14005b1b5  lea     rdi, WPP_GLOBAL_Control
0x14005b1bc  cmp     rax, rdi
0x14005b1bf  jz      short loc_14005B1F5
0x14005b1c1  test    byte ptr [rax+1Ch], 8
0x14005b1c5  jz      short loc_14005B1F5
0x14005b1c7  cmp     byte ptr [rax+19h], 2
0x14005b1cb  jb      short loc_14005B1F5
0x14005b1cd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b1d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b1d9  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005b1e0  mov     edx, 0Fh
0x14005b1e5  mov     dword ptr [rsp+68h+var_48], ebx
0x14005b1e9  mov     r9d, eax
0x14005b1ec  mov     rcx, [rcx+10h]
0x14005b1f0  call    WPP_SF_Dd
0x14005b1f5  test    ebx, ebx
0x14005b1f7  jle     short loc_14005B202
0x14005b1f9  movzx   ebx, bx
0x14005b1fc  or      ebx, 80070000h
0x14005b202  test    ebx, ebx
0x14005b204  mov     eax, 80004005h
0x14005b209  cmovns  ebx, eax
0x14005b20c  jmp     loc_14005B304
0x14005b211  mov     rax, cs:WPP_GLOBAL_Control
0x14005b218  lea     rdi, WPP_GLOBAL_Control
0x14005b21f  cmp     rax, rdi
0x14005b222  jz      short loc_14005B259
0x14005b224  test    byte ptr [rax+1Ch], 1
0x14005b228  jz      short loc_14005B259
0x14005b22a  cmp     byte ptr [rax+19h], 5
0x14005b22e  jb      short loc_14005B259
0x14005b230  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b235  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b23c  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005b243  mov     edx, 10h
0x14005b248  mov     [rsp+68h+var_48], rsi
0x14005b24d  mov     r9d, eax
0x14005b250  mov     rcx, [rcx+10h]
0x14005b254  call    WPP_SF_DS
0x14005b259  mov     rcx, rsi; pszPath
0x14005b25c  call    cs:__imp_PathRemoveFileSpecW
0x14005b262  lea     r8, SubBlock; "\\"
0x14005b269  mov     edx, 104h; unsigned __int64
0x14005b26e  mov     rcx, rsi; unsigned __int16 *
0x14005b271  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005b276  mov     ebx, eax
0x14005b278  test    eax, eax
0x14005b27a  jns     short loc_14005B2A0
0x14005b27c  mov     rax, cs:WPP_GLOBAL_Control
0x14005b283  cmp     rax, rdi
0x14005b286  jz      short loc_14005B304
0x14005b288  test    byte ptr [rax+1Ch], 8
0x14005b28c  jz      short loc_14005B304
0x14005b28e  cmp     byte ptr [rax+19h], 2
0x14005b292  jb      short loc_14005B304
0x14005b294  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b299  mov     edx, 11h
0x14005b29e  jmp     short loc_14005B2DA
0x14005b2a0  lea     r8, [rsp+68h+var_38]; unsigned __int16 *
0x14005b2a5  mov     edx, 104h; unsigned __int64
0x14005b2aa  mov     rcx, rsi; unsigned __int16 *
0x14005b2ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005b2b2  mov     ebx, eax
0x14005b2b4  test    eax, eax
0x14005b2b6  jns     short loc_14005B30F
0x14005b2b8  mov     rax, cs:WPP_GLOBAL_Control
0x14005b2bf  cmp     rax, rdi
0x14005b2c2  jz      short loc_14005B304
0x14005b2c4  test    byte ptr [rax+1Ch], 8
0x14005b2c8  jz      short loc_14005B304
0x14005b2ca  cmp     byte ptr [rax+19h], 2
0x14005b2ce  jb      short loc_14005B304
0x14005b2d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b2d5  mov     edx, 12h
0x14005b2da  lea     rcx, aStringcchcatFa_4; "StringCchCat failed!"
0x14005b2e1  mov     [rsp+68h+var_40], ebx
0x14005b2e5  mov     [rsp+68h+var_48], rcx
0x14005b2ea  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005b2f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b2f8  mov     r9d, eax
0x14005b2fb  mov     rcx, [rcx+10h]
0x14005b2ff  call    WPP_SF_DsD
0x14005b304  mov     rcx, rsi; hMem
0x14005b307  call    cs:__imp_LocalFree
0x14005b30d  jmp     short loc_14005B353
0x14005b30f  mov     rax, cs:WPP_GLOBAL_Control
0x14005b316  cmp     rax, rdi
0x14005b319  jz      short loc_14005B350
0x14005b31b  test    byte ptr [rax+1Ch], 1
0x14005b31f  jz      short loc_14005B350
0x14005b321  cmp     byte ptr [rax+19h], 5
0x14005b325  jb      short loc_14005B350
0x14005b327  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b32c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b333  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005b33a  mov     edx, 13h
0x14005b33f  mov     [rsp+68h+var_48], rsi
0x14005b344  mov     r9d, eax
0x14005b347  mov     rcx, [rcx+10h]
0x14005b34b  call    WPP_SF_DS
0x14005b350  mov     [r14], rsi
0x14005b353  mov     eax, ebx
0x14005b355  mov     rcx, [rsp+68h+var_20]
0x14005b35a  xor     rcx, rsp; StackCookie
0x14005b35d  call    __security_check_cookie
0x14005b362  mov     rbx, [rsp+68h+arg_10]
0x14005b36a  add     rsp, 50h
0x14005b36e  pop     r14
0x14005b370  pop     rdi
0x14005b371  pop     rsi
0x14005b372  retn
```
