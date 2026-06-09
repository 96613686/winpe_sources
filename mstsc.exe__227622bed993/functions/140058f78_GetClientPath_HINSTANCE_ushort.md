# GetClientPath(HINSTANCE__ *,ushort * *)

- ea: `0x140058f78`
- end: `0x140059203`
- name: `?GetClientPath@@YAJPEAUHINSTANCE__@@PEAPEAG@Z`
- size: `651`
- prototype: `__int64 __fastcall(HINSTANCE hModule, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x140058134`
- `0x140058884`

## callees

- `0x140008940`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14001e210`
- `0x140058f78`
- `0x1400b1d80`
- `0x140111220`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x1400590ec`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1400590ec`
- `KERNEL32!LocalFree` at `0x140059197`
- `KERNEL32!LocalFree` at `0x140059197`
- `KERNEL32!GetModuleFileNameW` at `0x14005902c`
- `KERNEL32!GetModuleFileNameW` at `0x14005902c`
- `KERNEL32!GetLastError` at `0x140059036`
- `KERNEL32!GetLastError` at `0x140059036`

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
0x140058f78  mov     [rsp+arg_10], rbx
0x140058f7d  push    rsi
0x140058f7e  push    rdi
0x140058f7f  push    r14
0x140058f81  sub     rsp, 50h
0x140058f85  mov     rax, cs:__security_cookie
0x140058f8c  xor     rax, rsp
0x140058f8f  mov     [rsp+68h+var_20], rax
0x140058f94  movups  xmm0, xmmword ptr cs:aMstscExe; "mstsc.exe"
0x140058f9b  mov     eax, dword ptr cs:aMstscExe+10h; "e"
0x140058fa1  mov     rbx, rcx
0x140058fa4  mov     ecx, 208h; size
0x140058fa9  mov     dword ptr [rsp+68h+var_28], eax
0x140058fad  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x140058fb2  mov     r14, rdx
0x140058fb5  mov     qword ptr [rdx], 0
0x140058fbc  call    MIDL_user_allocate
0x140058fc1  mov     rsi, rax
0x140058fc4  test    rax, rax
0x140058fc7  jnz     short loc_140059020
0x140058fc9  mov     rax, cs:WPP_GLOBAL_Control
0x140058fd0  lea     rdi, WPP_GLOBAL_Control
0x140058fd7  cmp     rax, rdi
0x140058fda  jz      short loc_140059016
0x140058fdc  test    byte ptr [rax+1Ch], 8
0x140058fe0  jz      short loc_140059016
0x140058fe2  cmp     byte ptr [rax+19h], 2
0x140058fe6  jb      short loc_140059016
0x140058fe8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058fed  lea     rcx, aTchar; "TCHAR"
0x140058ff4  mov     r9d, eax
0x140058ff7  mov     [rsp+68h+var_48], rcx
0x140058ffc  lea     edx, [rsi+0Eh]
0x140058fff  mov     rcx, cs:WPP_GLOBAL_Control
0x140059006  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005900d  mov     rcx, [rcx+10h]
0x140059011  call    WPP_SF_Ds
0x140059016  mov     ebx, 8007000Eh
0x14005901b  jmp     loc_1400591E3
0x140059020  mov     r8d, 104h; nSize
0x140059026  mov     rdx, rsi; lpFilename
0x140059029  mov     rcx, rbx; hModule
0x14005902c  call    cs:__imp_GetModuleFileNameW
0x140059032  test    eax, eax
0x140059034  jnz     short loc_1400590A1
0x140059036  call    cs:__imp_GetLastError
0x14005903c  mov     ebx, eax
0x14005903e  mov     rax, cs:WPP_GLOBAL_Control
0x140059045  lea     rdi, WPP_GLOBAL_Control
0x14005904c  cmp     rax, rdi
0x14005904f  jz      short loc_140059085
0x140059051  test    byte ptr [rax+1Ch], 8
0x140059055  jz      short loc_140059085
0x140059057  cmp     byte ptr [rax+19h], 2
0x14005905b  jb      short loc_140059085
0x14005905d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059062  mov     rcx, cs:WPP_GLOBAL_Control
0x140059069  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x140059070  mov     edx, 0Fh
0x140059075  mov     dword ptr [rsp+68h+var_48], ebx
0x140059079  mov     r9d, eax
0x14005907c  mov     rcx, [rcx+10h]
0x140059080  call    WPP_SF_Dd
0x140059085  test    ebx, ebx
0x140059087  jle     short loc_140059092
0x140059089  movzx   ebx, bx
0x14005908c  or      ebx, 80070000h
0x140059092  test    ebx, ebx
0x140059094  mov     eax, 80004005h
0x140059099  cmovns  ebx, eax
0x14005909c  jmp     loc_140059194
0x1400590a1  mov     rax, cs:WPP_GLOBAL_Control
0x1400590a8  lea     rdi, WPP_GLOBAL_Control
0x1400590af  cmp     rax, rdi
0x1400590b2  jz      short loc_1400590E9
0x1400590b4  test    byte ptr [rax+1Ch], 1
0x1400590b8  jz      short loc_1400590E9
0x1400590ba  cmp     byte ptr [rax+19h], 5
0x1400590be  jb      short loc_1400590E9
0x1400590c0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400590c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400590cc  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x1400590d3  mov     edx, 10h
0x1400590d8  mov     [rsp+68h+var_48], rsi
0x1400590dd  mov     r9d, eax
0x1400590e0  mov     rcx, [rcx+10h]
0x1400590e4  call    WPP_SF_DS
0x1400590e9  mov     rcx, rsi; pszPath
0x1400590ec  call    cs:__imp_PathRemoveFileSpecW
0x1400590f2  lea     r8, SubBlock; "\\"
0x1400590f9  mov     edx, 104h; unsigned __int64
0x1400590fe  mov     rcx, rsi; unsigned __int16 *
0x140059101  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140059106  mov     ebx, eax
0x140059108  test    eax, eax
0x14005910a  jns     short loc_140059130
0x14005910c  mov     rax, cs:WPP_GLOBAL_Control
0x140059113  cmp     rax, rdi
0x140059116  jz      short loc_140059194
0x140059118  test    byte ptr [rax+1Ch], 8
0x14005911c  jz      short loc_140059194
0x14005911e  cmp     byte ptr [rax+19h], 2
0x140059122  jb      short loc_140059194
0x140059124  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059129  mov     edx, 11h
0x14005912e  jmp     short loc_14005916A
0x140059130  lea     r8, [rsp+68h+var_38]; unsigned __int16 *
0x140059135  mov     edx, 104h; unsigned __int64
0x14005913a  mov     rcx, rsi; unsigned __int16 *
0x14005913d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140059142  mov     ebx, eax
0x140059144  test    eax, eax
0x140059146  jns     short loc_14005919F
0x140059148  mov     rax, cs:WPP_GLOBAL_Control
0x14005914f  cmp     rax, rdi
0x140059152  jz      short loc_140059194
0x140059154  test    byte ptr [rax+1Ch], 8
0x140059158  jz      short loc_140059194
0x14005915a  cmp     byte ptr [rax+19h], 2
0x14005915e  jb      short loc_140059194
0x140059160  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059165  mov     edx, 12h
0x14005916a  lea     rcx, aStringcchcatFa_4; "StringCchCat failed!"
0x140059171  mov     [rsp+68h+var_40], ebx
0x140059175  mov     [rsp+68h+var_48], rcx
0x14005917a  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x140059181  mov     rcx, cs:WPP_GLOBAL_Control
0x140059188  mov     r9d, eax
0x14005918b  mov     rcx, [rcx+10h]
0x14005918f  call    WPP_SF_DsD
0x140059194  mov     rcx, rsi; hMem
0x140059197  call    cs:__imp_LocalFree
0x14005919d  jmp     short loc_1400591E3
0x14005919f  mov     rax, cs:WPP_GLOBAL_Control
0x1400591a6  cmp     rax, rdi
0x1400591a9  jz      short loc_1400591E0
0x1400591ab  test    byte ptr [rax+1Ch], 1
0x1400591af  jz      short loc_1400591E0
0x1400591b1  cmp     byte ptr [rax+19h], 5
0x1400591b5  jb      short loc_1400591E0
0x1400591b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400591bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400591c3  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x1400591ca  mov     edx, 13h
0x1400591cf  mov     [rsp+68h+var_48], rsi
0x1400591d4  mov     r9d, eax
0x1400591d7  mov     rcx, [rcx+10h]
0x1400591db  call    WPP_SF_DS
0x1400591e0  mov     [r14], rsi
0x1400591e3  mov     eax, ebx
0x1400591e5  mov     rcx, [rsp+68h+var_20]
0x1400591ea  xor     rcx, rsp; StackCookie
0x1400591ed  call    __security_check_cookie
0x1400591f2  mov     rbx, [rsp+68h+arg_10]
0x1400591fa  add     rsp, 50h
0x1400591fe  pop     r14
0x140059200  pop     rdi
0x140059201  pop     rsi
0x140059202  retn
```
