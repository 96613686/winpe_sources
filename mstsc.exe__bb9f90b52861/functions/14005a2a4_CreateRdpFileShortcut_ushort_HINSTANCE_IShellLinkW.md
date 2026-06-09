# CreateRdpFileShortcut(ushort *,HINSTANCE__ *,IShellLinkW * *)

- ea: `0x14005a2a4`
- end: `0x14005a9ec`
- name: `?CreateRdpFileShortcut@@YAJPEAGPEAUHINSTANCE__@@PEAPEAUIShellLinkW@@@Z`
- size: `1864`
- prototype: `__int64 __fastcall(unsigned __int16 *, HINSTANCE hModule, struct IShellLinkW **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14005a054`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000d078`
- `0x140042394`
- `0x14005a2a4`
- `0x14005b0e8`
- `0x14005b608`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `USER32!CharLowerW` at `0x14005a3ef`
- `USER32!CharLowerW` at `0x14005a57a`
- `USER32!CharLowerW` at `0x14005a583`
- `USER32!CharLowerW` at `0x14005a3ef`
- `USER32!CharLowerW` at `0x14005a57a`
- `USER32!CharLowerW` at `0x14005a583`
- `SHLWAPI!PathFindExtensionW` at `0x14005a3e6`
- `SHLWAPI!PathFindExtensionW` at `0x14005a3e6`
- `SHLWAPI!PathStripPathW` at `0x14005a3db`
- `SHLWAPI!PathStripPathW` at `0x14005a3db`
- `SHLWAPI!PathRemoveFileSpecW` at `0x14005a44e`
- `SHLWAPI!PathRemoveFileSpecW` at `0x14005a44e`
- `KERNEL32!LocalFree` at `0x14005a976`
- `KERNEL32!LocalFree` at `0x14005a976`
- `ole32!CoCreateInstance` at `0x14005a5a7`
- `ole32!CoCreateInstance` at `0x14005a5a7`

## string_xrefs

- `0x14005a3a7`: `StringCbCopy failed!`
- `0x14005a646`: `SetPath failed!`
- `0x14005a5e8`: `CoCreateInstance(IID_IShellLink) failed!`
- `0x14005a56b`: `GetClientPath failed!`
- `0x14005a944`: `Commit failed!`

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
  HRESULT v17; // [rsp+28h] [rbp-D8h]
  HRESULT v18; // [rsp+28h] [rbp-D8h]
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h]
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v25[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v26[256]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v27[264]; // [rsp+680h] [rbp+580h] BYREF
  unsigned __int16 v28[512]; // [rsp+890h] [rbp+790h] BYREF

  ppv = 0;
  v20 = 0;
  v23 = 0;
  lpsz = 0;
  v22 = 0;
  memset_0(pszPath, 0, 0x208u);
  memset_0(v25, 0, 0x208u);
  memset_0(v27, 0, 0x208u);
  memset_0(v28, 0, sizeof(v28));
  memset_0(v26, 0, sizeof(v26));
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
      v17 = v6;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v9,
        v17);
      goto LABEL_82;
    }
    goto LABEL_82;
  }
  PathStripPathW(pszPath);
  ExtensionW = PathFindExtensionW(pszPath);
  CharLowerW(ExtensionW);
  v6 = StringCbCopyW(v25, 0x208u, a1);
  if ( v6 >= 0 )
  {
    PathRemoveFileSpecW(v25);
    v6 = StringCbPrintfW(v28, 0x400u, L"%s (%s)", pszPath, v25);
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
    v6 = StringCbPrintfW(v26, 0x200u, L"%s", pszPath);
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
          v6 = StringCbPrintfW(v27, 0x208u, L"\"%s\"", a1);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 88LL))(ppv, v27);
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(LPVOID, LPWSTR, _QWORD))(*(_QWORD *)ppv + 136LL))(ppv, v12, 0);
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 120LL))(ppv, 1);
                if ( v6 >= 0 )
                {
                  v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 56LL))(ppv, v28);
                  if ( v6 >= 0 )
                  {
                    v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPropertyStore, &v20);
                    if ( v6 >= 0 )
                    {
                      LOWORD(v22) = 31;
                      *((_QWORD *)&v22 + 1) = v26;
                      v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v20 + 48LL))(
                             v20,
                             &PKEY_Title,
                             &v22);
                      if ( v6 >= 0 )
                      {
                        v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 56LL))(v20);
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
      v18 = v6;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
        v13,
        (__int64)v15,
        v18);
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
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
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
0x14005a2a4  mov     [rsp-8+arg_18], rbx
0x14005a2a9  push    rbp
0x14005a2aa  push    rsi
0x14005a2ab  push    rdi
0x14005a2ac  push    r13
0x14005a2ae  push    r14
0x14005a2b0  lea     rbp, [rsp-0BA0h]
0x14005a2b8  sub     rsp, 0CA0h
0x14005a2bf  mov     rax, cs:__security_cookie
0x14005a2c6  xor     rax, rsp
0x14005a2c9  mov     [rbp+0BC0h+var_30], rax
0x14005a2d0  xor     eax, eax
0x14005a2d2  mov     [rsp+0CC0h+var_C90], 0
0x14005a2db  mov     r14, r8
0x14005a2de  mov     [rsp+0CC0h+var_C88], 0
0x14005a2e7  mov     rdi, rdx
0x14005a2ea  mov     [rsp+0CC0h+var_C68], rax
0x14005a2ef  mov     rsi, rcx
0x14005a2f2  mov     [rsp+0CC0h+lpsz], rax
0x14005a2f7  xorps   xmm0, xmm0
0x14005a2fa  lea     rcx, [rsp+0CC0h+pszPath]; void *
0x14005a2ff  mov     r13d, 208h
0x14005a305  xor     edx, edx; Val
0x14005a307  mov     r8d, r13d; Size
0x14005a30a  movups  [rsp+0CC0h+var_C78], xmm0
0x14005a30f  call    memset_0
0x14005a314  mov     r8d, r13d; Size
0x14005a317  lea     rcx, [rbp+0BC0h+var_A50]; void *
0x14005a31e  xor     edx, edx; Val
0x14005a320  call    memset_0
0x14005a325  mov     r8d, r13d; Size
0x14005a328  lea     rcx, [rbp+0BC0h+var_640]; void *
0x14005a32f  xor     edx, edx; Val
0x14005a331  call    memset_0
0x14005a336  xor     edx, edx; Val
0x14005a338  lea     rcx, [rbp+0BC0h+var_430]; void *
0x14005a33f  mov     r8d, 400h; Size
0x14005a345  call    memset_0
0x14005a34a  xor     edx, edx; Val
0x14005a34c  lea     r8d, [r13-8]; Size
0x14005a350  lea     rcx, [rbp+0BC0h+var_840]; void *
0x14005a357  call    memset_0
0x14005a35c  mov     r8, rsi; unsigned __int16 *
0x14005a35f  lea     rcx, [rsp+0CC0h+pszPath]; unsigned __int16 *
0x14005a364  mov     edx, r13d; unsigned __int64
0x14005a367  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14005a36c  mov     ebx, eax
0x14005a36e  test    eax, eax
0x14005a370  jns     short loc_14005A3D6
0x14005a372  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a379  lea     rax, WPP_GLOBAL_Control
0x14005a380  cmp     rcx, rax
0x14005a383  jz      loc_14005A97C
0x14005a389  test    byte ptr [rcx+1Ch], 8
0x14005a38d  jz      loc_14005A97C
0x14005a393  cmp     byte ptr [rcx+19h], 2
0x14005a397  jb      loc_14005A97C
0x14005a39d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a3a2  mov     edx, 22h ; '"'
0x14005a3a7  lea     rcx, aStringcbcopyFa; "StringCbCopy failed!"
0x14005a3ae  mov     [rsp+0CC0h+var_C98], ebx
0x14005a3b2  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005a3b9  mov     [rsp+0CC0h+ppv], rcx
0x14005a3be  mov     r9d, eax
0x14005a3c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a3c8  mov     rcx, [rcx+10h]
0x14005a3cc  call    WPP_SF_DsD
0x14005a3d1  jmp     loc_14005A97C
0x14005a3d6  lea     rcx, [rsp+0CC0h+pszPath]; pszPath
0x14005a3db  call    cs:__imp_PathStripPathW
0x14005a3e1  lea     rcx, [rsp+0CC0h+pszPath]; pszPath
0x14005a3e6  call    cs:__imp_PathFindExtensionW
0x14005a3ec  mov     rcx, rax; lpsz
0x14005a3ef  call    cs:__imp_CharLowerW
0x14005a3f5  mov     r8, rsi; unsigned __int16 *
0x14005a3f8  lea     rcx, [rbp+0BC0h+var_A50]; unsigned __int16 *
0x14005a3ff  mov     rdx, r13; unsigned __int64
0x14005a402  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14005a407  mov     ebx, eax
0x14005a409  test    eax, eax
0x14005a40b  jns     short loc_14005A447
0x14005a40d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a414  lea     rax, WPP_GLOBAL_Control
0x14005a41b  cmp     rcx, rax
0x14005a41e  jz      loc_14005A97C
0x14005a424  test    byte ptr [rcx+1Ch], 8
0x14005a428  jz      loc_14005A97C
0x14005a42e  cmp     byte ptr [rcx+19h], 2
0x14005a432  jb      loc_14005A97C
0x14005a438  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a43d  mov     edx, 23h ; '#'
0x14005a442  jmp     loc_14005A3A7
0x14005a447  lea     rcx, [rbp+0BC0h+var_A50]; pszPath
0x14005a44e  call    cs:__imp_PathRemoveFileSpecW
0x14005a454  lea     rax, [rbp+0BC0h+var_A50]
0x14005a45b  mov     edx, 400h; unsigned __int64
0x14005a460  lea     r9, [rsp+0CC0h+pszPath]
0x14005a465  mov     [rsp+0CC0h+ppv], rax
0x14005a46a  lea     r8, aSS; "%s (%s)"
0x14005a471  lea     rcx, [rbp+0BC0h+var_430]; unsigned __int16 *
0x14005a478  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a47d  mov     ebx, eax
0x14005a47f  test    eax, eax
0x14005a481  jns     short loc_14005A4C4
0x14005a483  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a48a  lea     rax, WPP_GLOBAL_Control
0x14005a491  cmp     rcx, rax
0x14005a494  jz      loc_14005A97C
0x14005a49a  test    byte ptr [rcx+1Ch], 8
0x14005a49e  jz      loc_14005A97C
0x14005a4a4  cmp     byte ptr [rcx+19h], 2
0x14005a4a8  jb      loc_14005A97C
0x14005a4ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a4b3  mov     edx, 24h ; '$'
0x14005a4b8  lea     rcx, aStringcbprintf; "StringCbPrintf failed!"
0x14005a4bf  jmp     loc_14005A3AE
0x14005a4c4  lea     r9, [rsp+0CC0h+pszPath]
0x14005a4c9  mov     edx, 200h; unsigned __int64
0x14005a4ce  lea     r8, aS_3; "%s"
0x14005a4d5  lea     rcx, [rbp+0BC0h+var_840]; unsigned __int16 *
0x14005a4dc  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a4e1  mov     ebx, eax
0x14005a4e3  test    eax, eax
0x14005a4e5  jns     short loc_14005A51E
0x14005a4e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a4ee  lea     rax, WPP_GLOBAL_Control
0x14005a4f5  cmp     rcx, rax
0x14005a4f8  jz      loc_14005A97C
0x14005a4fe  test    byte ptr [rcx+1Ch], 8
0x14005a502  jz      loc_14005A97C
0x14005a508  cmp     byte ptr [rcx+19h], 2
0x14005a50c  jb      loc_14005A97C
0x14005a512  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a517  mov     edx, 25h ; '%'
0x14005a51c  jmp     short loc_14005A4B8
0x14005a51e  lea     rdx, [rsp+0CC0h+lpsz]; unsigned __int16 **
0x14005a523  mov     rcx, rdi; hModule
0x14005a526  call    ?GetClientPath@@YAJPEAUHINSTANCE__@@PEAPEAG@Z; GetClientPath(HINSTANCE__ *,ushort * *)
0x14005a52b  mov     rdi, [rsp+0CC0h+lpsz]
0x14005a530  mov     ebx, eax
0x14005a532  test    eax, eax
0x14005a534  jns     short loc_14005A577
0x14005a536  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a53d  lea     rax, WPP_GLOBAL_Control
0x14005a544  cmp     rcx, rax
0x14005a547  jz      loc_14005A96E
0x14005a54d  test    byte ptr [rcx+1Ch], 8
0x14005a551  jz      loc_14005A96E
0x14005a557  cmp     byte ptr [rcx+19h], 2
0x14005a55b  jb      loc_14005A96E
0x14005a561  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a566  mov     edx, 26h ; '&'
0x14005a56b  lea     rcx, aGetclientpathF; "GetClientPath failed!"
0x14005a572  jmp     loc_14005A94B
0x14005a577  mov     rcx, rdi; lpsz
0x14005a57a  call    cs:__imp_CharLowerW
0x14005a580  mov     rcx, rsi; lpsz
0x14005a583  call    cs:__imp_CharLowerW
0x14005a589  xor     edx, edx; pUnkOuter
0x14005a58b  lea     rax, [rsp+0CC0h+var_C90]
0x14005a590  lea     r9, IID_IShellLinkW; riid
0x14005a597  mov     [rsp+0CC0h+ppv], rax; ppv
0x14005a59c  lea     rcx, CLSID_ShellLink; rclsid
0x14005a5a3  lea     r8d, [rdx+1]; dwClsContext
0x14005a5a7  call    cs:__imp_CoCreateInstance
0x14005a5ad  mov     ebx, eax
0x14005a5af  test    eax, eax
0x14005a5b1  jns     short loc_14005A5F4
0x14005a5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a5ba  lea     rax, WPP_GLOBAL_Control
0x14005a5c1  cmp     rcx, rax
0x14005a5c4  jz      loc_14005A96E
0x14005a5ca  test    byte ptr [rcx+1Ch], 8
0x14005a5ce  jz      loc_14005A96E
0x14005a5d4  cmp     byte ptr [rcx+19h], 2
0x14005a5d8  jb      loc_14005A96E
0x14005a5de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a5e3  mov     edx, 27h ; '''
0x14005a5e8  lea     rcx, aCocreateinstan_2; "CoCreateInstance(IID_IShellLink) failed"...
0x14005a5ef  jmp     loc_14005A94B
0x14005a5f4  mov     rcx, [rsp+0CC0h+var_C90]
0x14005a5f9  mov     rdx, rdi
0x14005a5fc  mov     rax, [rcx]
0x14005a5ff  mov     rax, [rax+0A0h]
0x14005a606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a60b  mov     ebx, eax
0x14005a60d  test    eax, eax
0x14005a60f  jns     short loc_14005A652
0x14005a611  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a618  lea     rax, WPP_GLOBAL_Control
0x14005a61f  cmp     rcx, rax
0x14005a622  jz      loc_14005A96E
0x14005a628  test    byte ptr [rcx+1Ch], 8
0x14005a62c  jz      loc_14005A96E
0x14005a632  cmp     byte ptr [rcx+19h], 2
0x14005a636  jb      loc_14005A96E
0x14005a63c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a641  mov     edx, 28h ; '('
0x14005a646  lea     rcx, aSetpathFailed; "SetPath failed!"
0x14005a64d  jmp     loc_14005A94B
0x14005a652  mov     r9, rsi
0x14005a655  lea     r8, aS_1; "\"%s\""
0x14005a65c  mov     rdx, r13; unsigned __int64
0x14005a65f  lea     rcx, [rbp+0BC0h+var_640]; unsigned __int16 *
0x14005a666  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a66b  mov     ebx, eax
0x14005a66d  test    eax, eax
0x14005a66f  jns     short loc_14005A6B2
0x14005a671  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a678  lea     rax, WPP_GLOBAL_Control
0x14005a67f  cmp     rcx, rax
0x14005a682  jz      loc_14005A96E
0x14005a688  test    byte ptr [rcx+1Ch], 8
0x14005a68c  jz      loc_14005A96E
0x14005a692  cmp     byte ptr [rcx+19h], 2
0x14005a696  jb      loc_14005A96E
0x14005a69c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a6a1  mov     edx, 29h ; ')'
0x14005a6a6  lea     rcx, aStringcbprintf; "StringCbPrintf failed!"
0x14005a6ad  jmp     loc_14005A94B
0x14005a6b2  mov     rcx, [rsp+0CC0h+var_C90]
0x14005a6b7  lea     rdx, [rbp+0BC0h+var_640]
0x14005a6be  mov     rax, [rcx]
0x14005a6c1  mov     rax, [rax+58h]
0x14005a6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a6ca  mov     ebx, eax
0x14005a6cc  test    eax, eax
0x14005a6ce  jns     short loc_14005A711
0x14005a6d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a6d7  lea     rax, WPP_GLOBAL_Control
0x14005a6de  cmp     rcx, rax
0x14005a6e1  jz      loc_14005A96E
0x14005a6e7  test    byte ptr [rcx+1Ch], 8
0x14005a6eb  jz      loc_14005A96E
0x14005a6f1  cmp     byte ptr [rcx+19h], 2
0x14005a6f5  jb      loc_14005A96E
0x14005a6fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a700  mov     edx, 2Ah ; '*'
0x14005a705  lea     rcx, aSetargumentsFa; "SetArguments failed!"
0x14005a70c  jmp     loc_14005A94B
0x14005a711  mov     rcx, [rsp+0CC0h+var_C90]
0x14005a716  xor     r8d, r8d
0x14005a719  mov     rdx, rdi
0x14005a71c  mov     rax, [rcx]
0x14005a71f  mov     rax, [rax+88h]
0x14005a726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a72b  mov     ebx, eax
0x14005a72d  test    eax, eax
0x14005a72f  jns     short loc_14005A772
0x14005a731  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a738  lea     rax, WPP_GLOBAL_Control
0x14005a73f  cmp     rcx, rax
0x14005a742  jz      loc_14005A96E
0x14005a748  test    byte ptr [rcx+1Ch], 8
0x14005a74c  jz      loc_14005A96E
0x14005a752  cmp     byte ptr [rcx+19h], 2
0x14005a756  jb      loc_14005A96E
0x14005a75c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a761  mov     edx, 2Bh ; '+'
0x14005a766  lea     rcx, aSeticonlocatio; "SetIconLocation failed!"
0x14005a76d  jmp     loc_14005A94B
0x14005a772  mov     rcx, [rsp+0CC0h+var_C90]
0x14005a777  mov     edx, 1
0x14005a77c  mov     rax, [rcx]
0x14005a77f  mov     rax, [rax+78h]
0x14005a783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a788  mov     ebx, eax
0x14005a78a  test    eax, eax
0x14005a78c  jns     short loc_14005A7CF
0x14005a78e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a795  lea     rax, WPP_GLOBAL_Control
0x14005a79c  cmp     rcx, rax
0x14005a79f  jz      loc_14005A96E
0x14005a7a5  test    byte ptr [rcx+1Ch], 8
0x14005a7a9  jz      loc_14005A96E
0x14005a7af  cmp     byte ptr [rcx+19h], 2
0x14005a7b3  jb      loc_14005A96E
0x14005a7b9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a7be  mov     edx, 2Ch ; ','
0x14005a7c3  lea     rcx, aSetshowcmdFail; "SetShowCmd failed!"
0x14005a7ca  jmp     loc_14005A94B
0x14005a7cf  mov     rcx, [rsp+0CC0h+var_C90]
0x14005a7d4  lea     rdx, [rbp+0BC0h+var_430]
0x14005a7db  mov     rax, [rcx]
0x14005a7de  mov     rax, [rax+38h]
0x14005a7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a7e7  mov     ebx, eax
0x14005a7e9  test    eax, eax
0x14005a7eb  jns     short loc_14005A82E
0x14005a7ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a7f4  lea     rax, WPP_GLOBAL_Control
0x14005a7fb  cmp     rcx, rax
0x14005a7fe  jz      loc_14005A96E
0x14005a804  test    byte ptr [rcx+1Ch], 8
0x14005a808  jz      loc_14005A96E
0x14005a80e  cmp     byte ptr [rcx+19h], 2
0x14005a812  jb      loc_14005A96E
0x14005a818  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a81d  mov     edx, 2Dh ; '-'
0x14005a822  lea     rcx, aSetdescription; "SetDescription failed!"
  ... truncated ...
```
