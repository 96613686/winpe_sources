# CreateServerShortcut(ushort *,int,HINSTANCE__ *,IShellLinkW * *)

- ea: `0x14005a9f4`
- end: `0x14005b0e0`
- name: `?CreateServerShortcut@@YAJPEAGHPEAUHINSTANCE__@@PEAPEAUIShellLinkW@@@Z`
- size: `1772`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, HINSTANCE, struct IShellLinkW **)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14005a17c`

## callees

- `0x140004703`
- `0x140008a34`
- `0x140008a78`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14005a9f4`
- `0x14005b0e8`
- `0x14005b608`
- `0x1400fcad0`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `USER32!CharLowerW` at `0x14005ab21`
- `USER32!CharLowerW` at `0x14005accc`
- `USER32!CharLowerW` at `0x14005acd9`
- `USER32!CharLowerW` at `0x14005ab21`
- `USER32!CharLowerW` at `0x14005accc`
- `USER32!CharLowerW` at `0x14005acd9`
- `KERNEL32!LocalFree` at `0x14005b06a`
- `KERNEL32!LocalFree` at `0x14005b06a`
- `KERNEL32!GetLastError` at `0x14005abf0`
- `KERNEL32!GetLastError` at `0x14005abf0`
- `ole32!CoCreateInstance` at `0x14005acfd`
- `ole32!CoCreateInstance` at `0x14005acfd`

## string_xrefs

- `0x14005aaed`: `StringCchCopy failed!`
- `0x14005ad9c`: `SetPath failed!`
- `0x14005ad3e`: `CoCreateInstance(IID_IShellLink) failed!`
- `0x14005acbd`: `GetClientPath failed!`
- `0x14005b038`: `Commit failed!`

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
  v7 = StringCchPrintfW(v25, 0x104u, (size_t *)L"/v:\"%s\"", a1);
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
0x14005a9f4  mov     [rsp-8+arg_8], rbx
0x14005a9f9  push    rbp
0x14005a9fa  push    rsi
0x14005a9fb  push    rdi
0x14005a9fc  push    r12
0x14005a9fe  push    r14
0x14005aa00  lea     rbp, [rsp-0B90h]
0x14005aa08  sub     rsp, 0C90h
0x14005aa0f  mov     rax, cs:__security_cookie
0x14005aa16  xor     rax, rsp
0x14005aa19  mov     [rbp+0BB0h+var_30], rax
0x14005aa20  mov     rdi, r8
0x14005aa23  mov     [rsp+0CB0h+var_C80], 0
0x14005aa2c  mov     rsi, rcx
0x14005aa2f  mov     [rsp+0CB0h+var_C78], 0
0x14005aa38  xorps   xmm0, xmm0
0x14005aa3b  lea     rcx, [rbp+0BB0h+var_A40]; void *
0x14005aa42  xor     eax, eax
0x14005aa44  mov     ebx, 208h
0x14005aa49  mov     r8d, ebx; Size
0x14005aa4c  mov     [rsp+0CB0h+var_C58], rax
0x14005aa51  xor     edx, edx; Val
0x14005aa53  mov     r14, r9
0x14005aa56  movups  [rsp+0CB0h+var_C68], xmm0
0x14005aa5b  call    memset_0
0x14005aa60  mov     r8d, ebx; Size
0x14005aa63  mov     [rsp+0CB0h+lpsz], 0
0x14005aa6c  xor     edx, edx; Val
0x14005aa6e  lea     rcx, [rsp+0CB0h+sz]; void *
0x14005aa73  call    memset_0
0x14005aa78  mov     r12d, 400h
0x14005aa7e  lea     rcx, [rbp+0BB0h+var_830]; void *
0x14005aa85  mov     r8d, r12d; Size
0x14005aa88  xor     edx, edx; Val
0x14005aa8a  call    memset_0
0x14005aa8f  mov     r8d, r12d; Size
0x14005aa92  lea     rcx, [rbp+0BB0h+var_430]; void *
0x14005aa99  xor     edx, edx; Val
0x14005aa9b  call    memset_0
0x14005aaa0  mov     r8, rsi; unsigned __int16 *
0x14005aaa3  lea     rcx, [rsp+0CB0h+sz]; unsigned __int16 *
0x14005aaa8  mov     edx, 104h; unsigned __int64
0x14005aaad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14005aab2  mov     ebx, eax
0x14005aab4  test    eax, eax
0x14005aab6  jns     short loc_14005AB1C
0x14005aab8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aabf  lea     rax, WPP_GLOBAL_Control
0x14005aac6  cmp     rcx, rax
0x14005aac9  jz      loc_14005B070
0x14005aacf  test    byte ptr [rcx+1Ch], 8
0x14005aad3  jz      loc_14005B070
0x14005aad9  cmp     byte ptr [rcx+19h], 2
0x14005aadd  jb      loc_14005B070
0x14005aae3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005aae8  mov     edx, 14h
0x14005aaed  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x14005aaf4  mov     [rsp+0CB0h+var_C88], ebx
0x14005aaf8  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005aaff  mov     [rsp+0CB0h+ppv], rcx
0x14005ab04  mov     r9d, eax
0x14005ab07  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab0e  mov     rcx, [rcx+10h]
0x14005ab12  call    WPP_SF_DsD
0x14005ab17  jmp     loc_14005B070
0x14005ab1c  lea     rcx, [rsp+0CB0h+sz]; lpsz
0x14005ab21  call    cs:__imp_CharLowerW
0x14005ab27  mov     r9, rsi
0x14005ab2a  lea     r8, aVS; "/v:\"%s\""
0x14005ab31  mov     edx, 104h; unsigned __int64
0x14005ab36  lea     rcx, [rbp+0BB0h+var_A40]; unsigned __int16 *
0x14005ab3d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005ab42  mov     ebx, eax
0x14005ab44  test    eax, eax
0x14005ab46  jns     short loc_14005AB89
0x14005ab48  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab4f  lea     rax, WPP_GLOBAL_Control
0x14005ab56  cmp     rcx, rax
0x14005ab59  jz      loc_14005B070
0x14005ab5f  test    byte ptr [rcx+1Ch], 8
0x14005ab63  jz      loc_14005B070
0x14005ab69  cmp     byte ptr [rcx+19h], 2
0x14005ab6d  jb      loc_14005B070
0x14005ab73  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ab78  mov     edx, 15h
0x14005ab7d  lea     rcx, aStringcchprint_1; "StringCchPrintf failed!"
0x14005ab84  jmp     loc_14005AAF4
0x14005ab89  mov     ebx, 3F0h
0x14005ab8e  lea     r8, [rbp+0BB0h+var_830]; unsigned __int16 *
0x14005ab95  mov     edx, ebx; unsigned int
0x14005ab97  mov     r9d, 200h; int
0x14005ab9d  mov     rcx, rdi; HINSTANCE
0x14005aba0  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14005aba5  test    eax, eax
0x14005aba7  jnz     short loc_14005AC0E
0x14005aba9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005abb0  lea     rax, WPP_GLOBAL_Control
0x14005abb7  cmp     rcx, rax
0x14005abba  jz      short loc_14005ABF0
0x14005abbc  test    byte ptr [rcx+1Ch], 1
0x14005abc0  jz      short loc_14005ABF0
0x14005abc2  cmp     byte ptr [rcx+19h], 2
0x14005abc6  jb      short loc_14005ABF0
0x14005abc8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005abcd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005abd4  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005abdb  mov     edx, 16h
0x14005abe0  mov     dword ptr [rsp+0CB0h+ppv], ebx
0x14005abe4  mov     r9d, eax
0x14005abe7  mov     rcx, [rcx+10h]
0x14005abeb  call    WPP_SF_Dd
0x14005abf0  call    cs:__imp_GetLastError
0x14005abf6  mov     ebx, eax
0x14005abf8  test    eax, eax
0x14005abfa  jle     loc_14005B070
0x14005ac00  movzx   ebx, ax
0x14005ac03  or      ebx, 80070000h
0x14005ac09  jmp     loc_14005B070
0x14005ac0e  lea     r9, [rsp+0CB0h+sz]
0x14005ac13  mov     rdx, r12; unsigned __int64
0x14005ac16  lea     r8, [rbp+0BB0h+var_830]; unsigned __int16 *
0x14005ac1d  lea     rcx, [rbp+0BB0h+var_430]; unsigned __int16 *
0x14005ac24  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005ac29  mov     ebx, eax
0x14005ac2b  test    eax, eax
0x14005ac2d  jns     short loc_14005AC70
0x14005ac2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ac36  lea     rax, WPP_GLOBAL_Control
0x14005ac3d  cmp     rcx, rax
0x14005ac40  jz      loc_14005B070
0x14005ac46  test    byte ptr [rcx+1Ch], 8
0x14005ac4a  jz      loc_14005B070
0x14005ac50  cmp     byte ptr [rcx+19h], 2
0x14005ac54  jb      loc_14005B070
0x14005ac5a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ac5f  mov     edx, 17h
0x14005ac64  lea     rcx, aStringcbprintf; "StringCbPrintf failed!"
0x14005ac6b  jmp     loc_14005AAF4
0x14005ac70  lea     rdx, [rsp+0CB0h+lpsz]; unsigned __int16 **
0x14005ac75  mov     rcx, rdi; hModule
0x14005ac78  call    ?GetClientPath@@YAJPEAUHINSTANCE__@@PEAPEAG@Z; GetClientPath(HINSTANCE__ *,ushort * *)
0x14005ac7d  mov     rdi, [rsp+0CB0h+lpsz]
0x14005ac82  mov     ebx, eax
0x14005ac84  test    eax, eax
0x14005ac86  jns     short loc_14005ACC9
0x14005ac88  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ac8f  lea     rax, WPP_GLOBAL_Control
0x14005ac96  cmp     rcx, rax
0x14005ac99  jz      loc_14005B062
0x14005ac9f  test    byte ptr [rcx+1Ch], 8
0x14005aca3  jz      loc_14005B062
0x14005aca9  cmp     byte ptr [rcx+19h], 2
0x14005acad  jb      loc_14005B062
0x14005acb3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005acb8  mov     edx, 18h
0x14005acbd  lea     rcx, aGetclientpathF; "GetClientPath failed!"
0x14005acc4  jmp     loc_14005B03F
0x14005acc9  mov     rcx, rdi; lpsz
0x14005accc  call    cs:__imp_CharLowerW
0x14005acd2  lea     rcx, [rbp+0BB0h+var_A40]; lpsz
0x14005acd9  call    cs:__imp_CharLowerW
0x14005acdf  xor     edx, edx; pUnkOuter
0x14005ace1  lea     rax, [rsp+0CB0h+var_C80]
0x14005ace6  lea     r9, IID_IShellLinkW; riid
0x14005aced  mov     [rsp+0CB0h+ppv], rax; ppv
0x14005acf2  lea     rcx, CLSID_ShellLink; rclsid
0x14005acf9  lea     r8d, [rdx+1]; dwClsContext
0x14005acfd  call    cs:__imp_CoCreateInstance
0x14005ad03  mov     ebx, eax
0x14005ad05  test    eax, eax
0x14005ad07  jns     short loc_14005AD4A
0x14005ad09  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ad10  lea     rax, WPP_GLOBAL_Control
0x14005ad17  cmp     rcx, rax
0x14005ad1a  jz      loc_14005B062
0x14005ad20  test    byte ptr [rcx+1Ch], 8
0x14005ad24  jz      loc_14005B062
0x14005ad2a  cmp     byte ptr [rcx+19h], 2
0x14005ad2e  jb      loc_14005B062
0x14005ad34  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ad39  mov     edx, 19h
0x14005ad3e  lea     rcx, aCocreateinstan_2; "CoCreateInstance(IID_IShellLink) failed"...
0x14005ad45  jmp     loc_14005B03F
0x14005ad4a  mov     rcx, [rsp+0CB0h+var_C80]
0x14005ad4f  mov     rdx, rdi
0x14005ad52  mov     rax, [rcx]
0x14005ad55  mov     rax, [rax+0A0h]
0x14005ad5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ad61  mov     ebx, eax
0x14005ad63  test    eax, eax
0x14005ad65  jns     short loc_14005ADA8
0x14005ad67  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ad6e  lea     rax, WPP_GLOBAL_Control
0x14005ad75  cmp     rcx, rax
0x14005ad78  jz      loc_14005B062
0x14005ad7e  test    byte ptr [rcx+1Ch], 8
0x14005ad82  jz      loc_14005B062
0x14005ad88  cmp     byte ptr [rcx+19h], 2
0x14005ad8c  jb      loc_14005B062
0x14005ad92  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ad97  mov     edx, 1Ah
0x14005ad9c  lea     rcx, aSetpathFailed; "SetPath failed!"
0x14005ada3  jmp     loc_14005B03F
0x14005ada8  mov     rcx, [rsp+0CB0h+var_C80]
0x14005adad  lea     rdx, [rbp+0BB0h+var_A40]
0x14005adb4  mov     rax, [rcx]
0x14005adb7  mov     rax, [rax+58h]
0x14005adbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005adc0  mov     ebx, eax
0x14005adc2  test    eax, eax
0x14005adc4  jns     short loc_14005AE07
0x14005adc6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005adcd  lea     rax, WPP_GLOBAL_Control
0x14005add4  cmp     rcx, rax
0x14005add7  jz      loc_14005B062
0x14005addd  test    byte ptr [rcx+1Ch], 8
0x14005ade1  jz      loc_14005B062
0x14005ade7  cmp     byte ptr [rcx+19h], 2
0x14005adeb  jb      loc_14005B062
0x14005adf1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005adf6  mov     edx, 1Bh
0x14005adfb  lea     rcx, aSetargumentsFa; "SetArguments failed!"
0x14005ae02  jmp     loc_14005B03F
0x14005ae07  mov     rcx, [rsp+0CB0h+var_C80]
0x14005ae0c  xor     r8d, r8d
0x14005ae0f  mov     rdx, rdi
0x14005ae12  mov     rax, [rcx]
0x14005ae15  mov     rax, [rax+88h]
0x14005ae1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ae21  mov     ebx, eax
0x14005ae23  test    eax, eax
0x14005ae25  jns     short loc_14005AE68
0x14005ae27  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ae2e  lea     rax, WPP_GLOBAL_Control
0x14005ae35  cmp     rcx, rax
0x14005ae38  jz      loc_14005B062
0x14005ae3e  test    byte ptr [rcx+1Ch], 8
0x14005ae42  jz      loc_14005B062
0x14005ae48  cmp     byte ptr [rcx+19h], 2
0x14005ae4c  jb      loc_14005B062
0x14005ae52  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ae57  mov     edx, 1Ch
0x14005ae5c  lea     rcx, aSeticonlocatio; "SetIconLocation failed!"
0x14005ae63  jmp     loc_14005B03F
0x14005ae68  mov     rcx, [rsp+0CB0h+var_C80]
0x14005ae6d  mov     edx, 1
0x14005ae72  mov     rax, [rcx]
0x14005ae75  mov     rax, [rax+78h]
0x14005ae79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ae7e  mov     ebx, eax
0x14005ae80  test    eax, eax
0x14005ae82  jns     short loc_14005AEC5
0x14005ae84  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ae8b  lea     rax, WPP_GLOBAL_Control
0x14005ae92  cmp     rcx, rax
0x14005ae95  jz      loc_14005B062
0x14005ae9b  test    byte ptr [rcx+1Ch], 8
0x14005ae9f  jz      loc_14005B062
0x14005aea5  cmp     byte ptr [rcx+19h], 2
0x14005aea9  jb      loc_14005B062
0x14005aeaf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005aeb4  mov     edx, 1Dh
0x14005aeb9  lea     rcx, aSetshowcmdFail; "SetShowCmd failed!"
0x14005aec0  jmp     loc_14005B03F
0x14005aec5  mov     rcx, [rsp+0CB0h+var_C80]
0x14005aeca  lea     rdx, [rbp+0BB0h+var_430]
0x14005aed1  mov     rax, [rcx]
0x14005aed4  mov     rax, [rax+38h]
0x14005aed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005aedd  mov     ebx, eax
0x14005aedf  test    eax, eax
0x14005aee1  jns     short loc_14005AF24
0x14005aee3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aeea  lea     rax, WPP_GLOBAL_Control
0x14005aef1  cmp     rcx, rax
0x14005aef4  jz      loc_14005B062
0x14005aefa  test    byte ptr [rcx+1Ch], 8
0x14005aefe  jz      loc_14005B062
0x14005af04  cmp     byte ptr [rcx+19h], 2
0x14005af08  jb      loc_14005B062
0x14005af0e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005af13  mov     edx, 1Eh
0x14005af18  lea     rcx, aSetdescription; "SetDescription failed!"
0x14005af1f  jmp     loc_14005B03F
0x14005af24  mov     rcx, [rsp+0CB0h+var_C80]
0x14005af29  lea     r8, [rsp+0CB0h+var_C78]
0x14005af2e  lea     rdx, IID_IPropertyStore
0x14005af35  mov     rax, [rcx]
0x14005af38  mov     rax, [rax]
0x14005af3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005af40  mov     ebx, eax
0x14005af42  test    eax, eax
0x14005af44  jns     short loc_14005AF87
0x14005af46  mov     rcx, cs:WPP_GLOBAL_Control
0x14005af4d  lea     rax, WPP_GLOBAL_Control
0x14005af54  cmp     rcx, rax
0x14005af57  jz      loc_14005B062
0x14005af5d  test    byte ptr [rcx+1Ch], 8
0x14005af61  jz      loc_14005B062
0x14005af67  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
