# CreateRdpFileShortcut(ushort *,HINSTANCE__ *,IShellLinkW * *)

- ea: `0x140058134`
- end: `0x14005887c`
- name: `?CreateRdpFileShortcut@@YAJPEAGPEAUHINSTANCE__@@PEAPEAUIShellLinkW@@@Z`
- size: `1864`
- prototype: `__int64 __fastcall(unsigned __int16 *, HINSTANCE hModule, struct IShellLinkW **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140057ee4`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000d078`
- `0x1400403d0`
- `0x140058134`
- `0x140058f78`
- `0x140059498`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!CharLowerW` at `0x14005827f`
- `USER32!CharLowerW` at `0x14005840a`
- `USER32!CharLowerW` at `0x140058413`
- `USER32!CharLowerW` at `0x14005827f`
- `USER32!CharLowerW` at `0x14005840a`
- `USER32!CharLowerW` at `0x140058413`
- `SHLWAPI!PathFindExtensionW` at `0x140058276`
- `SHLWAPI!PathFindExtensionW` at `0x140058276`
- `SHLWAPI!PathStripPathW` at `0x14005826b`
- `SHLWAPI!PathStripPathW` at `0x14005826b`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1400582de`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1400582de`
- `KERNEL32!LocalFree` at `0x140058806`
- `KERNEL32!LocalFree` at `0x140058806`
- `ole32!CoCreateInstance` at `0x140058437`
- `ole32!CoCreateInstance` at `0x140058437`

## string_xrefs

- `0x140058237`: `StringCbCopy failed!`
- `0x1400584d6`: `SetPath failed!`
- `0x140058478`: `CoCreateInstance(IID_IShellLink) failed!`
- `0x1400583fb`: `GetClientPath failed!`
- `0x1400587d4`: `Commit failed!`

## pseudocode

```c
__int64 __fastcall CreateRdpFileShortcut(unsigned __int16 *a1, HINSTANCE hModule, LPVOID *a3)
{
  HRESULT v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  WCHAR *ExtensionW; // rax
  int ClientPath; // eax
  LPWSTR v12; // rdi
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h]
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v23[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v24[256]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v25[264]; // [rsp+680h] [rbp+580h] BYREF
  unsigned __int16 v26[512]; // [rsp+890h] [rbp+790h] BYREF

  ppv = 0;
  v18 = 0;
  v21 = 0;
  lpsz = 0;
  v20 = 0;
  memset_0(pszPath, 0, 0x208u);
  memset_0(v23, 0, 0x208u);
  memset_0(v25, 0, 0x208u);
  memset_0(v26, 0, sizeof(v26));
  memset_0(v24, 0, sizeof(v24));
  v6 = StringCbCopyW(pszPath, 0x208u, a1);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 34;
LABEL_6:
      v9 = "StringCbCopy failed!";
LABEL_7:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v9,
        v6);
      goto LABEL_82;
    }
    goto LABEL_82;
  }
  PathStripPathW(pszPath);
  ExtensionW = PathFindExtensionW(pszPath);
  CharLowerW(ExtensionW);
  v6 = StringCbCopyW(v23, 0x208u, a1);
  if ( v6 >= 0 )
  {
    PathRemoveFileSpecW(v23);
    v6 = StringCbPrintfW(v26, 0x400u, L"%s (%s)", pszPath, v23);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 36;
      goto LABEL_18;
    }
    v6 = StringCbPrintfW(v24, 0x200u, L"%s", pszPath);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 37;
LABEL_18:
      v9 = "StringCbPrintf failed!";
      goto LABEL_7;
    }
    ClientPath = GetClientPath(hModule, &lpsz);
    v12 = lpsz;
    v6 = ClientPath;
    if ( ClientPath >= 0 )
    {
      CharLowerW(lpsz);
      CharLowerW(a1);
      v6 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &ppv);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(LPVOID, LPWSTR))(*(_QWORD *)ppv + 160LL))(ppv, v12);
        if ( v6 >= 0 )
        {
          v6 = StringCbPrintfW(v25, 0x208u, L"\"%s\"", a1);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 88LL))(ppv, v25);
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(LPVOID, LPWSTR, _QWORD))(*(_QWORD *)ppv + 136LL))(ppv, v12, 0);
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 120LL))(ppv, 1);
                if ( v6 >= 0 )
                {
                  v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 56LL))(ppv, v26);
                  if ( v6 >= 0 )
                  {
                    v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPropertyStore, &v18);
                    if ( v6 >= 0 )
                    {
                      LOWORD(v20) = 31;
                      *((_QWORD *)&v20 + 1) = v24;
                      v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v18 + 48LL))(
                             v18,
                             &PKEY_Title,
                             &v20);
                      if ( v6 >= 0 )
                      {
                        v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 56LL))(v18);
                        if ( v6 < 0
                          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                          v14 = 48;
                          v15 = "Commit failed!";
                          goto LABEL_79;
                        }
                      }
                      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                        v14 = 47;
                        v15 = "SetValue failed!";
                        goto LABEL_79;
                      }
                    }
                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                      v14 = 46;
                      v15 = "QueryInterface(IID_IPropertyStore) failed!";
                      goto LABEL_79;
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                    v14 = 45;
                    v15 = "SetDescription failed!";
                    goto LABEL_79;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v14 = 44;
                  v15 = "SetShowCmd failed!";
                  goto LABEL_79;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                v14 = 43;
                v15 = "SetIconLocation failed!";
                goto LABEL_79;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v13 = RdpWppGetCurrentThreadActivityIdPrefix();
              v14 = 42;
              v15 = "SetArguments failed!";
              goto LABEL_79;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = RdpWppGetCurrentThreadActivityIdPrefix();
            v14 = 41;
            v15 = "StringCbPrintf failed!";
            goto LABEL_79;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          v14 = 40;
          v15 = "SetPath failed!";
          goto LABEL_79;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 39;
        v15 = "CoCreateInstance(IID_IShellLink) failed!";
        goto LABEL_79;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 38;
      v15 = "GetClientPath failed!";
LABEL_79:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
        v13,
        (__int64)v15,
        v6);
    }
    if ( v12 )
      LocalFree(v12);
    goto LABEL_82;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 35;
    goto LABEL_6;
  }
LABEL_82:
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v6 >= 0 )
  {
    if ( a3 )
      *a3 = ppv;
  }
  else if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140058134  mov     [rsp-8+arg_18], rbx
0x140058139  push    rbp
0x14005813a  push    rsi
0x14005813b  push    rdi
0x14005813c  push    r13
0x14005813e  push    r14
0x140058140  lea     rbp, [rsp-0BA0h]
0x140058148  sub     rsp, 0CA0h
0x14005814f  mov     rax, cs:__security_cookie
0x140058156  xor     rax, rsp
0x140058159  mov     [rbp+0BC0h+var_30], rax
0x140058160  xor     eax, eax
0x140058162  mov     [rsp+0CC0h+var_C90], 0
0x14005816b  mov     r14, r8
0x14005816e  mov     [rsp+0CC0h+var_C88], 0
0x140058177  mov     rdi, rdx
0x14005817a  mov     [rsp+0CC0h+var_C68], rax
0x14005817f  mov     rsi, rcx
0x140058182  mov     [rsp+0CC0h+lpsz], rax
0x140058187  xorps   xmm0, xmm0
0x14005818a  lea     rcx, [rsp+0CC0h+pszPath]; void *
0x14005818f  mov     r13d, 208h
0x140058195  xor     edx, edx; Val
0x140058197  mov     r8d, r13d; Size
0x14005819a  movups  [rsp+0CC0h+var_C78], xmm0
0x14005819f  call    memset_0
0x1400581a4  mov     r8d, r13d; Size
0x1400581a7  lea     rcx, [rbp+0BC0h+var_A50]; void *
0x1400581ae  xor     edx, edx; Val
0x1400581b0  call    memset_0
0x1400581b5  mov     r8d, r13d; Size
0x1400581b8  lea     rcx, [rbp+0BC0h+var_640]; void *
0x1400581bf  xor     edx, edx; Val
0x1400581c1  call    memset_0
0x1400581c6  xor     edx, edx; Val
0x1400581c8  lea     rcx, [rbp+0BC0h+var_430]; void *
0x1400581cf  mov     r8d, 400h; Size
0x1400581d5  call    memset_0
0x1400581da  xor     edx, edx; Val
0x1400581dc  lea     r8d, [r13-8]; Size
0x1400581e0  lea     rcx, [rbp+0BC0h+var_840]; void *
0x1400581e7  call    memset_0
0x1400581ec  mov     r8, rsi; unsigned __int16 *
0x1400581ef  lea     rcx, [rsp+0CC0h+pszPath]; unsigned __int16 *
0x1400581f4  mov     edx, r13d; unsigned __int64
0x1400581f7  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400581fc  mov     ebx, eax
0x1400581fe  test    eax, eax
0x140058200  jns     short loc_140058266
0x140058202  mov     rcx, cs:WPP_GLOBAL_Control
0x140058209  lea     rax, WPP_GLOBAL_Control
0x140058210  cmp     rcx, rax
0x140058213  jz      loc_14005880C
0x140058219  test    byte ptr [rcx+1Ch], 8
0x14005821d  jz      loc_14005880C
0x140058223  cmp     byte ptr [rcx+19h], 2
0x140058227  jb      loc_14005880C
0x14005822d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058232  mov     edx, 22h ; '"'
0x140058237  lea     rcx, aStringcbcopyFa; "StringCbCopy failed!"
0x14005823e  mov     [rsp+0CC0h+var_C98], ebx
0x140058242  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x140058249  mov     [rsp+0CC0h+ppv], rcx
0x14005824e  mov     r9d, eax
0x140058251  mov     rcx, cs:WPP_GLOBAL_Control
0x140058258  mov     rcx, [rcx+10h]
0x14005825c  call    WPP_SF_DsD
0x140058261  jmp     loc_14005880C
0x140058266  lea     rcx, [rsp+0CC0h+pszPath]; pszPath
0x14005826b  call    cs:__imp_PathStripPathW
0x140058271  lea     rcx, [rsp+0CC0h+pszPath]; pszPath
0x140058276  call    cs:__imp_PathFindExtensionW
0x14005827c  mov     rcx, rax; lpsz
0x14005827f  call    cs:__imp_CharLowerW
0x140058285  mov     r8, rsi; unsigned __int16 *
0x140058288  lea     rcx, [rbp+0BC0h+var_A50]; unsigned __int16 *
0x14005828f  mov     rdx, r13; unsigned __int64
0x140058292  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140058297  mov     ebx, eax
0x140058299  test    eax, eax
0x14005829b  jns     short loc_1400582D7
0x14005829d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400582a4  lea     rax, WPP_GLOBAL_Control
0x1400582ab  cmp     rcx, rax
0x1400582ae  jz      loc_14005880C
0x1400582b4  test    byte ptr [rcx+1Ch], 8
0x1400582b8  jz      loc_14005880C
0x1400582be  cmp     byte ptr [rcx+19h], 2
0x1400582c2  jb      loc_14005880C
0x1400582c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400582cd  mov     edx, 23h ; '#'
0x1400582d2  jmp     loc_140058237
0x1400582d7  lea     rcx, [rbp+0BC0h+var_A50]; pszPath
0x1400582de  call    cs:__imp_PathRemoveFileSpecW
0x1400582e4  lea     rax, [rbp+0BC0h+var_A50]
0x1400582eb  mov     edx, 400h; unsigned __int64
0x1400582f0  lea     r9, [rsp+0CC0h+pszPath]
0x1400582f5  mov     [rsp+0CC0h+ppv], rax
0x1400582fa  lea     r8, aSS; "%s (%s)"
0x140058301  lea     rcx, [rbp+0BC0h+var_430]; unsigned __int16 *
0x140058308  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005830d  mov     ebx, eax
0x14005830f  test    eax, eax
0x140058311  jns     short loc_140058354
0x140058313  mov     rcx, cs:WPP_GLOBAL_Control
0x14005831a  lea     rax, WPP_GLOBAL_Control
0x140058321  cmp     rcx, rax
0x140058324  jz      loc_14005880C
0x14005832a  test    byte ptr [rcx+1Ch], 8
0x14005832e  jz      loc_14005880C
0x140058334  cmp     byte ptr [rcx+19h], 2
0x140058338  jb      loc_14005880C
0x14005833e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058343  mov     edx, 24h ; '$'
0x140058348  lea     rcx, aStringcbprintf; "StringCbPrintf failed!"
0x14005834f  jmp     loc_14005823E
0x140058354  lea     r9, [rsp+0CC0h+pszPath]
0x140058359  mov     edx, 200h; unsigned __int64
0x14005835e  lea     r8, aS_3; "%s"
0x140058365  lea     rcx, [rbp+0BC0h+var_840]; unsigned __int16 *
0x14005836c  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140058371  mov     ebx, eax
0x140058373  test    eax, eax
0x140058375  jns     short loc_1400583AE
0x140058377  mov     rcx, cs:WPP_GLOBAL_Control
0x14005837e  lea     rax, WPP_GLOBAL_Control
0x140058385  cmp     rcx, rax
0x140058388  jz      loc_14005880C
0x14005838e  test    byte ptr [rcx+1Ch], 8
0x140058392  jz      loc_14005880C
0x140058398  cmp     byte ptr [rcx+19h], 2
0x14005839c  jb      loc_14005880C
0x1400583a2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400583a7  mov     edx, 25h ; '%'
0x1400583ac  jmp     short loc_140058348
0x1400583ae  lea     rdx, [rsp+0CC0h+lpsz]; unsigned __int16 **
0x1400583b3  mov     rcx, rdi; hModule
0x1400583b6  call    ?GetClientPath@@YAJPEAUHINSTANCE__@@PEAPEAG@Z; GetClientPath(HINSTANCE__ *,ushort * *)
0x1400583bb  mov     rdi, [rsp+0CC0h+lpsz]
0x1400583c0  mov     ebx, eax
0x1400583c2  test    eax, eax
0x1400583c4  jns     short loc_140058407
0x1400583c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400583cd  lea     rax, WPP_GLOBAL_Control
0x1400583d4  cmp     rcx, rax
0x1400583d7  jz      loc_1400587FE
0x1400583dd  test    byte ptr [rcx+1Ch], 8
0x1400583e1  jz      loc_1400587FE
0x1400583e7  cmp     byte ptr [rcx+19h], 2
0x1400583eb  jb      loc_1400587FE
0x1400583f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400583f6  mov     edx, 26h ; '&'
0x1400583fb  lea     rcx, aGetclientpathF; "GetClientPath failed!"
0x140058402  jmp     loc_1400587DB
0x140058407  mov     rcx, rdi; lpsz
0x14005840a  call    cs:__imp_CharLowerW
0x140058410  mov     rcx, rsi; lpsz
0x140058413  call    cs:__imp_CharLowerW
0x140058419  xor     edx, edx; pUnkOuter
0x14005841b  lea     rax, [rsp+0CC0h+var_C90]
0x140058420  lea     r9, IID_IShellLinkW; riid
0x140058427  mov     [rsp+0CC0h+ppv], rax; ppv
0x14005842c  lea     rcx, CLSID_ShellLink; rclsid
0x140058433  lea     r8d, [rdx+1]; dwClsContext
0x140058437  call    cs:__imp_CoCreateInstance
0x14005843d  mov     ebx, eax
0x14005843f  test    eax, eax
0x140058441  jns     short loc_140058484
0x140058443  mov     rcx, cs:WPP_GLOBAL_Control
0x14005844a  lea     rax, WPP_GLOBAL_Control
0x140058451  cmp     rcx, rax
0x140058454  jz      loc_1400587FE
0x14005845a  test    byte ptr [rcx+1Ch], 8
0x14005845e  jz      loc_1400587FE
0x140058464  cmp     byte ptr [rcx+19h], 2
0x140058468  jb      loc_1400587FE
0x14005846e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058473  mov     edx, 27h ; '''
0x140058478  lea     rcx, aCocreateinstan_2; "CoCreateInstance(IID_IShellLink) failed"...
0x14005847f  jmp     loc_1400587DB
0x140058484  mov     rcx, [rsp+0CC0h+var_C90]
0x140058489  mov     rdx, rdi
0x14005848c  mov     rax, [rcx]
0x14005848f  mov     rax, [rax+0A0h]
0x140058496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005849b  mov     ebx, eax
0x14005849d  test    eax, eax
0x14005849f  jns     short loc_1400584E2
0x1400584a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400584a8  lea     rax, WPP_GLOBAL_Control
0x1400584af  cmp     rcx, rax
0x1400584b2  jz      loc_1400587FE
0x1400584b8  test    byte ptr [rcx+1Ch], 8
0x1400584bc  jz      loc_1400587FE
0x1400584c2  cmp     byte ptr [rcx+19h], 2
0x1400584c6  jb      loc_1400587FE
0x1400584cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400584d1  mov     edx, 28h ; '('
0x1400584d6  lea     rcx, aSetpathFailed; "SetPath failed!"
0x1400584dd  jmp     loc_1400587DB
0x1400584e2  mov     r9, rsi
0x1400584e5  lea     r8, aS_1; "\"%s\""
0x1400584ec  mov     rdx, r13; unsigned __int64
0x1400584ef  lea     rcx, [rbp+0BC0h+var_640]; unsigned __int16 *
0x1400584f6  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400584fb  mov     ebx, eax
0x1400584fd  test    eax, eax
0x1400584ff  jns     short loc_140058542
0x140058501  mov     rcx, cs:WPP_GLOBAL_Control
0x140058508  lea     rax, WPP_GLOBAL_Control
0x14005850f  cmp     rcx, rax
0x140058512  jz      loc_1400587FE
0x140058518  test    byte ptr [rcx+1Ch], 8
0x14005851c  jz      loc_1400587FE
0x140058522  cmp     byte ptr [rcx+19h], 2
0x140058526  jb      loc_1400587FE
0x14005852c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058531  mov     edx, 29h ; ')'
0x140058536  lea     rcx, aStringcbprintf; "StringCbPrintf failed!"
0x14005853d  jmp     loc_1400587DB
0x140058542  mov     rcx, [rsp+0CC0h+var_C90]
0x140058547  lea     rdx, [rbp+0BC0h+var_640]
0x14005854e  mov     rax, [rcx]
0x140058551  mov     rax, [rax+58h]
0x140058555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005855a  mov     ebx, eax
0x14005855c  test    eax, eax
0x14005855e  jns     short loc_1400585A1
0x140058560  mov     rcx, cs:WPP_GLOBAL_Control
0x140058567  lea     rax, WPP_GLOBAL_Control
0x14005856e  cmp     rcx, rax
0x140058571  jz      loc_1400587FE
0x140058577  test    byte ptr [rcx+1Ch], 8
0x14005857b  jz      loc_1400587FE
0x140058581  cmp     byte ptr [rcx+19h], 2
0x140058585  jb      loc_1400587FE
0x14005858b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058590  mov     edx, 2Ah ; '*'
0x140058595  lea     rcx, aSetargumentsFa; "SetArguments failed!"
0x14005859c  jmp     loc_1400587DB
0x1400585a1  mov     rcx, [rsp+0CC0h+var_C90]
0x1400585a6  xor     r8d, r8d
0x1400585a9  mov     rdx, rdi
0x1400585ac  mov     rax, [rcx]
0x1400585af  mov     rax, [rax+88h]
0x1400585b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400585bb  mov     ebx, eax
0x1400585bd  test    eax, eax
0x1400585bf  jns     short loc_140058602
0x1400585c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400585c8  lea     rax, WPP_GLOBAL_Control
0x1400585cf  cmp     rcx, rax
0x1400585d2  jz      loc_1400587FE
0x1400585d8  test    byte ptr [rcx+1Ch], 8
0x1400585dc  jz      loc_1400587FE
0x1400585e2  cmp     byte ptr [rcx+19h], 2
0x1400585e6  jb      loc_1400587FE
0x1400585ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400585f1  mov     edx, 2Bh ; '+'
0x1400585f6  lea     rcx, aSeticonlocatio; "SetIconLocation failed!"
0x1400585fd  jmp     loc_1400587DB
0x140058602  mov     rcx, [rsp+0CC0h+var_C90]
0x140058607  mov     edx, 1
0x14005860c  mov     rax, [rcx]
0x14005860f  mov     rax, [rax+78h]
0x140058613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058618  mov     ebx, eax
0x14005861a  test    eax, eax
0x14005861c  jns     short loc_14005865F
0x14005861e  mov     rcx, cs:WPP_GLOBAL_Control
0x140058625  lea     rax, WPP_GLOBAL_Control
0x14005862c  cmp     rcx, rax
0x14005862f  jz      loc_1400587FE
0x140058635  test    byte ptr [rcx+1Ch], 8
0x140058639  jz      loc_1400587FE
0x14005863f  cmp     byte ptr [rcx+19h], 2
0x140058643  jb      loc_1400587FE
0x140058649  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005864e  mov     edx, 2Ch ; ','
0x140058653  lea     rcx, aSetshowcmdFail; "SetShowCmd failed!"
0x14005865a  jmp     loc_1400587DB
0x14005865f  mov     rcx, [rsp+0CC0h+var_C90]
0x140058664  lea     rdx, [rbp+0BC0h+var_430]
0x14005866b  mov     rax, [rcx]
0x14005866e  mov     rax, [rax+38h]
0x140058672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058677  mov     ebx, eax
0x140058679  test    eax, eax
0x14005867b  jns     short loc_1400586BE
0x14005867d  mov     rcx, cs:WPP_GLOBAL_Control
0x140058684  lea     rax, WPP_GLOBAL_Control
0x14005868b  cmp     rcx, rax
0x14005868e  jz      loc_1400587FE
0x140058694  test    byte ptr [rcx+1Ch], 8
0x140058698  jz      loc_1400587FE
0x14005869e  cmp     byte ptr [rcx+19h], 2
0x1400586a2  jb      loc_1400587FE
0x1400586a8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400586ad  mov     edx, 2Dh ; '-'
0x1400586b2  lea     rcx, aSetdescription; "SetDescription failed!"
  ... truncated ...
```
