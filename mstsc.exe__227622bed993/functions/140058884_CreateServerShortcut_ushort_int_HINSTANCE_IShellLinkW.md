# CreateServerShortcut(ushort *,int,HINSTANCE__ *,IShellLinkW * *)

- ea: `0x140058884`
- end: `0x140058f70`
- name: `?CreateServerShortcut@@YAJPEAGHPEAUHINSTANCE__@@PEAPEAUIShellLinkW@@@Z`
- size: `1772`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, HINSTANCE, struct IShellLinkW **)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14005800c`

## callees

- `0x140004703`
- `0x140008a34`
- `0x140008a78`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x140058884`
- `0x140058f78`
- `0x140059498`
- `0x1400fa960`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!CharLowerW` at `0x1400589b1`
- `USER32!CharLowerW` at `0x140058b5c`
- `USER32!CharLowerW` at `0x140058b69`
- `USER32!CharLowerW` at `0x1400589b1`
- `USER32!CharLowerW` at `0x140058b5c`
- `USER32!CharLowerW` at `0x140058b69`
- `KERNEL32!LocalFree` at `0x140058efa`
- `KERNEL32!LocalFree` at `0x140058efa`
- `KERNEL32!GetLastError` at `0x140058a80`
- `KERNEL32!GetLastError` at `0x140058a80`
- `ole32!CoCreateInstance` at `0x140058b8d`
- `ole32!CoCreateInstance` at `0x140058b8d`

## string_xrefs

- `0x14005897d`: `StringCchCopy failed!`
- `0x140058c2c`: `SetPath failed!`
- `0x140058bce`: `CoCreateInstance(IID_IShellLink) failed!`
- `0x140058b4d`: `GetClientPath failed!`
- `0x140058ec8`: `Commit failed!`

## pseudocode

```c
__int64 __fastcall CreateServerShortcut(unsigned __int16 *a1, __int64 a2, HINSTANCE a3, LPVOID *a4)
{
  int v7; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  unsigned int v11; // eax
  signed int LastError; // eax
  int ClientPath; // eax
  LPWSTR v14; // rdi
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h]
  WCHAR sz[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v25[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v26[512]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v27[512]; // [rsp+880h] [rbp+780h] BYREF

  ppv = 0;
  v20 = 0;
  v23 = 0;
  v22 = 0;
  memset_0(v25, 0, 0x208u);
  lpsz = 0;
  memset_0(sz, 0, 0x208u);
  memset_0(v26, 0, sizeof(v26));
  memset_0(v27, 0, sizeof(v27));
  v7 = StringCchCopyW(sz, 0x104u, a1);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 20;
      v10 = "StringCchCopy failed!";
LABEL_6:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v10,
        v7);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  CharLowerW(sz);
  v7 = StringCchPrintfW(v25, 0x104u, L"/v:\"%s\"", a1);
  if ( v7 >= 0 )
  {
    if ( !TSLoadString(a3, 0x3F0u, v26, 512) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids, v11, 1008);
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_77;
    }
    v7 = StringCbPrintfW(v27, 0x400u, v26, sz);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 23;
        v10 = "StringCbPrintf failed!";
        goto LABEL_6;
      }
      goto LABEL_77;
    }
    ClientPath = GetClientPath(a3, &lpsz);
    v14 = lpsz;
    v7 = ClientPath;
    if ( ClientPath >= 0 )
    {
      CharLowerW(lpsz);
      CharLowerW(v25);
      v7 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &ppv);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(LPVOID, LPWSTR))(*(_QWORD *)ppv + 160LL))(ppv, v14);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 88LL))(ppv, v25);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(LPVOID, LPWSTR, _QWORD))(*(_QWORD *)ppv + 136LL))(ppv, v14, 0);
            if ( v7 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 120LL))(ppv, 1);
              if ( v7 >= 0 )
              {
                v7 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 56LL))(ppv, v27);
                if ( v7 >= 0 )
                {
                  v7 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPropertyStore, &v20);
                  if ( v7 >= 0 )
                  {
                    LOWORD(v22) = 31;
                    *((_QWORD *)&v22 + 1) = sz;
                    v7 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v20 + 48LL))(
                           v20,
                           &PKEY_Title,
                           &v22);
                    if ( v7 >= 0 )
                    {
                      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 56LL))(v20);
                      if ( v7 < 0
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
                        v16 = 33;
                        v17 = "Commit failed!";
                        goto LABEL_74;
                      }
                    }
                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
                      v16 = 32;
                      v17 = "SetValue failed!";
                      goto LABEL_74;
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
                    v16 = 31;
                    v17 = "QueryInterface(IID_IPropertyStore) failed!";
                    goto LABEL_74;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v16 = 30;
                  v17 = "SetDescription failed!";
                  goto LABEL_74;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v15 = RdpWppGetCurrentThreadActivityIdPrefix();
                v16 = 29;
                v17 = "SetShowCmd failed!";
                goto LABEL_74;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = RdpWppGetCurrentThreadActivityIdPrefix();
              v16 = 28;
              v17 = "SetIconLocation failed!";
              goto LABEL_74;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = RdpWppGetCurrentThreadActivityIdPrefix();
            v16 = 27;
            v17 = "SetArguments failed!";
            goto LABEL_74;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          v16 = 26;
          v17 = "SetPath failed!";
          goto LABEL_74;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        v16 = 25;
        v17 = "CoCreateInstance(IID_IShellLink) failed!";
        goto LABEL_74;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 24;
      v17 = "GetClientPath failed!";
LABEL_74:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
        v15,
        (__int64)v17,
        v7);
    }
    if ( v14 )
      LocalFree(v14);
    goto LABEL_77;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 21;
    v10 = "StringCchPrintf failed!";
    goto LABEL_6;
  }
LABEL_77:
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v7 >= 0 )
  {
    if ( a4 )
      *a4 = ppv;
  }
  else if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140058884  mov     [rsp-8+arg_8], rbx
0x140058889  push    rbp
0x14005888a  push    rsi
0x14005888b  push    rdi
0x14005888c  push    r12
0x14005888e  push    r14
0x140058890  lea     rbp, [rsp-0B90h]
0x140058898  sub     rsp, 0C90h
0x14005889f  mov     rax, cs:__security_cookie
0x1400588a6  xor     rax, rsp
0x1400588a9  mov     [rbp+0BB0h+var_30], rax
0x1400588b0  mov     rdi, r8
0x1400588b3  mov     [rsp+0CB0h+var_C80], 0
0x1400588bc  mov     rsi, rcx
0x1400588bf  mov     [rsp+0CB0h+var_C78], 0
0x1400588c8  xorps   xmm0, xmm0
0x1400588cb  lea     rcx, [rbp+0BB0h+var_A40]; void *
0x1400588d2  xor     eax, eax
0x1400588d4  mov     ebx, 208h
0x1400588d9  mov     r8d, ebx; Size
0x1400588dc  mov     [rsp+0CB0h+var_C58], rax
0x1400588e1  xor     edx, edx; Val
0x1400588e3  mov     r14, r9
0x1400588e6  movups  [rsp+0CB0h+var_C68], xmm0
0x1400588eb  call    memset_0
0x1400588f0  mov     r8d, ebx; Size
0x1400588f3  mov     [rsp+0CB0h+lpsz], 0
0x1400588fc  xor     edx, edx; Val
0x1400588fe  lea     rcx, [rsp+0CB0h+sz]; void *
0x140058903  call    memset_0
0x140058908  mov     r12d, 400h
0x14005890e  lea     rcx, [rbp+0BB0h+var_830]; void *
0x140058915  mov     r8d, r12d; Size
0x140058918  xor     edx, edx; Val
0x14005891a  call    memset_0
0x14005891f  mov     r8d, r12d; Size
0x140058922  lea     rcx, [rbp+0BB0h+var_430]; void *
0x140058929  xor     edx, edx; Val
0x14005892b  call    memset_0
0x140058930  mov     r8, rsi; unsigned __int16 *
0x140058933  lea     rcx, [rsp+0CB0h+sz]; unsigned __int16 *
0x140058938  mov     edx, 104h; unsigned __int64
0x14005893d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140058942  mov     ebx, eax
0x140058944  test    eax, eax
0x140058946  jns     short loc_1400589AC
0x140058948  mov     rcx, cs:WPP_GLOBAL_Control
0x14005894f  lea     rax, WPP_GLOBAL_Control
0x140058956  cmp     rcx, rax
0x140058959  jz      loc_140058F00
0x14005895f  test    byte ptr [rcx+1Ch], 8
0x140058963  jz      loc_140058F00
0x140058969  cmp     byte ptr [rcx+19h], 2
0x14005896d  jb      loc_140058F00
0x140058973  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058978  mov     edx, 14h
0x14005897d  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x140058984  mov     [rsp+0CB0h+var_C88], ebx
0x140058988  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005898f  mov     [rsp+0CB0h+ppv], rcx
0x140058994  mov     r9d, eax
0x140058997  mov     rcx, cs:WPP_GLOBAL_Control
0x14005899e  mov     rcx, [rcx+10h]
0x1400589a2  call    WPP_SF_DsD
0x1400589a7  jmp     loc_140058F00
0x1400589ac  lea     rcx, [rsp+0CB0h+sz]; lpsz
0x1400589b1  call    cs:__imp_CharLowerW
0x1400589b7  mov     r9, rsi
0x1400589ba  lea     r8, aVS; "/v:\"%s\""
0x1400589c1  mov     edx, 104h; unsigned __int64
0x1400589c6  lea     rcx, [rbp+0BB0h+var_A40]; unsigned __int16 *
0x1400589cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400589d2  mov     ebx, eax
0x1400589d4  test    eax, eax
0x1400589d6  jns     short loc_140058A19
0x1400589d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400589df  lea     rax, WPP_GLOBAL_Control
0x1400589e6  cmp     rcx, rax
0x1400589e9  jz      loc_140058F00
0x1400589ef  test    byte ptr [rcx+1Ch], 8
0x1400589f3  jz      loc_140058F00
0x1400589f9  cmp     byte ptr [rcx+19h], 2
0x1400589fd  jb      loc_140058F00
0x140058a03  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058a08  mov     edx, 15h
0x140058a0d  lea     rcx, aStringcchprint_1; "StringCchPrintf failed!"
0x140058a14  jmp     loc_140058984
0x140058a19  mov     ebx, 3F0h
0x140058a1e  lea     r8, [rbp+0BB0h+var_830]; unsigned __int16 *
0x140058a25  mov     edx, ebx; unsigned int
0x140058a27  mov     r9d, 200h; int
0x140058a2d  mov     rcx, rdi; HINSTANCE
0x140058a30  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140058a35  test    eax, eax
0x140058a37  jnz     short loc_140058A9E
0x140058a39  mov     rcx, cs:WPP_GLOBAL_Control
0x140058a40  lea     rax, WPP_GLOBAL_Control
0x140058a47  cmp     rcx, rax
0x140058a4a  jz      short loc_140058A80
0x140058a4c  test    byte ptr [rcx+1Ch], 1
0x140058a50  jz      short loc_140058A80
0x140058a52  cmp     byte ptr [rcx+19h], 2
0x140058a56  jb      short loc_140058A80
0x140058a58  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140058a64  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x140058a6b  mov     edx, 16h
0x140058a70  mov     dword ptr [rsp+0CB0h+ppv], ebx
0x140058a74  mov     r9d, eax
0x140058a77  mov     rcx, [rcx+10h]
0x140058a7b  call    WPP_SF_Dd
0x140058a80  call    cs:__imp_GetLastError
0x140058a86  mov     ebx, eax
0x140058a88  test    eax, eax
0x140058a8a  jle     loc_140058F00
0x140058a90  movzx   ebx, ax
0x140058a93  or      ebx, 80070000h
0x140058a99  jmp     loc_140058F00
0x140058a9e  lea     r9, [rsp+0CB0h+sz]
0x140058aa3  mov     rdx, r12; unsigned __int64
0x140058aa6  lea     r8, [rbp+0BB0h+var_830]; unsigned __int16 *
0x140058aad  lea     rcx, [rbp+0BB0h+var_430]; unsigned __int16 *
0x140058ab4  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140058ab9  mov     ebx, eax
0x140058abb  test    eax, eax
0x140058abd  jns     short loc_140058B00
0x140058abf  mov     rcx, cs:WPP_GLOBAL_Control
0x140058ac6  lea     rax, WPP_GLOBAL_Control
0x140058acd  cmp     rcx, rax
0x140058ad0  jz      loc_140058F00
0x140058ad6  test    byte ptr [rcx+1Ch], 8
0x140058ada  jz      loc_140058F00
0x140058ae0  cmp     byte ptr [rcx+19h], 2
0x140058ae4  jb      loc_140058F00
0x140058aea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058aef  mov     edx, 17h
0x140058af4  lea     rcx, aStringcbprintf; "StringCbPrintf failed!"
0x140058afb  jmp     loc_140058984
0x140058b00  lea     rdx, [rsp+0CB0h+lpsz]; unsigned __int16 **
0x140058b05  mov     rcx, rdi; hModule
0x140058b08  call    ?GetClientPath@@YAJPEAUHINSTANCE__@@PEAPEAG@Z; GetClientPath(HINSTANCE__ *,ushort * *)
0x140058b0d  mov     rdi, [rsp+0CB0h+lpsz]
0x140058b12  mov     ebx, eax
0x140058b14  test    eax, eax
0x140058b16  jns     short loc_140058B59
0x140058b18  mov     rcx, cs:WPP_GLOBAL_Control
0x140058b1f  lea     rax, WPP_GLOBAL_Control
0x140058b26  cmp     rcx, rax
0x140058b29  jz      loc_140058EF2
0x140058b2f  test    byte ptr [rcx+1Ch], 8
0x140058b33  jz      loc_140058EF2
0x140058b39  cmp     byte ptr [rcx+19h], 2
0x140058b3d  jb      loc_140058EF2
0x140058b43  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058b48  mov     edx, 18h
0x140058b4d  lea     rcx, aGetclientpathF; "GetClientPath failed!"
0x140058b54  jmp     loc_140058ECF
0x140058b59  mov     rcx, rdi; lpsz
0x140058b5c  call    cs:__imp_CharLowerW
0x140058b62  lea     rcx, [rbp+0BB0h+var_A40]; lpsz
0x140058b69  call    cs:__imp_CharLowerW
0x140058b6f  xor     edx, edx; pUnkOuter
0x140058b71  lea     rax, [rsp+0CB0h+var_C80]
0x140058b76  lea     r9, IID_IShellLinkW; riid
0x140058b7d  mov     [rsp+0CB0h+ppv], rax; ppv
0x140058b82  lea     rcx, CLSID_ShellLink; rclsid
0x140058b89  lea     r8d, [rdx+1]; dwClsContext
0x140058b8d  call    cs:__imp_CoCreateInstance
0x140058b93  mov     ebx, eax
0x140058b95  test    eax, eax
0x140058b97  jns     short loc_140058BDA
0x140058b99  mov     rcx, cs:WPP_GLOBAL_Control
0x140058ba0  lea     rax, WPP_GLOBAL_Control
0x140058ba7  cmp     rcx, rax
0x140058baa  jz      loc_140058EF2
0x140058bb0  test    byte ptr [rcx+1Ch], 8
0x140058bb4  jz      loc_140058EF2
0x140058bba  cmp     byte ptr [rcx+19h], 2
0x140058bbe  jb      loc_140058EF2
0x140058bc4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058bc9  mov     edx, 19h
0x140058bce  lea     rcx, aCocreateinstan_2; "CoCreateInstance(IID_IShellLink) failed"...
0x140058bd5  jmp     loc_140058ECF
0x140058bda  mov     rcx, [rsp+0CB0h+var_C80]
0x140058bdf  mov     rdx, rdi
0x140058be2  mov     rax, [rcx]
0x140058be5  mov     rax, [rax+0A0h]
0x140058bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058bf1  mov     ebx, eax
0x140058bf3  test    eax, eax
0x140058bf5  jns     short loc_140058C38
0x140058bf7  mov     rcx, cs:WPP_GLOBAL_Control
0x140058bfe  lea     rax, WPP_GLOBAL_Control
0x140058c05  cmp     rcx, rax
0x140058c08  jz      loc_140058EF2
0x140058c0e  test    byte ptr [rcx+1Ch], 8
0x140058c12  jz      loc_140058EF2
0x140058c18  cmp     byte ptr [rcx+19h], 2
0x140058c1c  jb      loc_140058EF2
0x140058c22  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058c27  mov     edx, 1Ah
0x140058c2c  lea     rcx, aSetpathFailed; "SetPath failed!"
0x140058c33  jmp     loc_140058ECF
0x140058c38  mov     rcx, [rsp+0CB0h+var_C80]
0x140058c3d  lea     rdx, [rbp+0BB0h+var_A40]
0x140058c44  mov     rax, [rcx]
0x140058c47  mov     rax, [rax+58h]
0x140058c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058c50  mov     ebx, eax
0x140058c52  test    eax, eax
0x140058c54  jns     short loc_140058C97
0x140058c56  mov     rcx, cs:WPP_GLOBAL_Control
0x140058c5d  lea     rax, WPP_GLOBAL_Control
0x140058c64  cmp     rcx, rax
0x140058c67  jz      loc_140058EF2
0x140058c6d  test    byte ptr [rcx+1Ch], 8
0x140058c71  jz      loc_140058EF2
0x140058c77  cmp     byte ptr [rcx+19h], 2
0x140058c7b  jb      loc_140058EF2
0x140058c81  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058c86  mov     edx, 1Bh
0x140058c8b  lea     rcx, aSetargumentsFa; "SetArguments failed!"
0x140058c92  jmp     loc_140058ECF
0x140058c97  mov     rcx, [rsp+0CB0h+var_C80]
0x140058c9c  xor     r8d, r8d
0x140058c9f  mov     rdx, rdi
0x140058ca2  mov     rax, [rcx]
0x140058ca5  mov     rax, [rax+88h]
0x140058cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058cb1  mov     ebx, eax
0x140058cb3  test    eax, eax
0x140058cb5  jns     short loc_140058CF8
0x140058cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140058cbe  lea     rax, WPP_GLOBAL_Control
0x140058cc5  cmp     rcx, rax
0x140058cc8  jz      loc_140058EF2
0x140058cce  test    byte ptr [rcx+1Ch], 8
0x140058cd2  jz      loc_140058EF2
0x140058cd8  cmp     byte ptr [rcx+19h], 2
0x140058cdc  jb      loc_140058EF2
0x140058ce2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058ce7  mov     edx, 1Ch
0x140058cec  lea     rcx, aSeticonlocatio; "SetIconLocation failed!"
0x140058cf3  jmp     loc_140058ECF
0x140058cf8  mov     rcx, [rsp+0CB0h+var_C80]
0x140058cfd  mov     edx, 1
0x140058d02  mov     rax, [rcx]
0x140058d05  mov     rax, [rax+78h]
0x140058d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058d0e  mov     ebx, eax
0x140058d10  test    eax, eax
0x140058d12  jns     short loc_140058D55
0x140058d14  mov     rcx, cs:WPP_GLOBAL_Control
0x140058d1b  lea     rax, WPP_GLOBAL_Control
0x140058d22  cmp     rcx, rax
0x140058d25  jz      loc_140058EF2
0x140058d2b  test    byte ptr [rcx+1Ch], 8
0x140058d2f  jz      loc_140058EF2
0x140058d35  cmp     byte ptr [rcx+19h], 2
0x140058d39  jb      loc_140058EF2
0x140058d3f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058d44  mov     edx, 1Dh
0x140058d49  lea     rcx, aSetshowcmdFail; "SetShowCmd failed!"
0x140058d50  jmp     loc_140058ECF
0x140058d55  mov     rcx, [rsp+0CB0h+var_C80]
0x140058d5a  lea     rdx, [rbp+0BB0h+var_430]
0x140058d61  mov     rax, [rcx]
0x140058d64  mov     rax, [rax+38h]
0x140058d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058d6d  mov     ebx, eax
0x140058d6f  test    eax, eax
0x140058d71  jns     short loc_140058DB4
0x140058d73  mov     rcx, cs:WPP_GLOBAL_Control
0x140058d7a  lea     rax, WPP_GLOBAL_Control
0x140058d81  cmp     rcx, rax
0x140058d84  jz      loc_140058EF2
0x140058d8a  test    byte ptr [rcx+1Ch], 8
0x140058d8e  jz      loc_140058EF2
0x140058d94  cmp     byte ptr [rcx+19h], 2
0x140058d98  jb      loc_140058EF2
0x140058d9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058da3  mov     edx, 1Eh
0x140058da8  lea     rcx, aSetdescription; "SetDescription failed!"
0x140058daf  jmp     loc_140058ECF
0x140058db4  mov     rcx, [rsp+0CB0h+var_C80]
0x140058db9  lea     r8, [rsp+0CB0h+var_C78]
0x140058dbe  lea     rdx, IID_IPropertyStore
0x140058dc5  mov     rax, [rcx]
0x140058dc8  mov     rax, [rax]
0x140058dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058dd0  mov     ebx, eax
0x140058dd2  test    eax, eax
0x140058dd4  jns     short loc_140058E17
0x140058dd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140058ddd  lea     rax, WPP_GLOBAL_Control
0x140058de4  cmp     rcx, rax
0x140058de7  jz      loc_140058EF2
0x140058ded  test    byte ptr [rcx+1Ch], 8
0x140058df1  jz      loc_140058EF2
0x140058df7  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
