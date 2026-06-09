# DavQueryCookieFromStore

- ea: `0x18000e034`
- end: `0x18000e2a7`
- name: `DavQueryCookieFromStore`
- size: `627`
- prototype: `__int64 __fastcall(LPCWSTR UncPath, __int64, unsigned int, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180007ad0`

## callees

- `0x180001010`
- `0x18000b494`
- `0x18000da5c`
- `0x18000e034`
- `0x180010c28`
- `0x180010c88`
- `0x180010d00`
- `0x180011e82`
- `0x180011eb0`

## import_xrefs

- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000e180`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000e180`

## pseudocode

```c
__int64 __fastcall DavQueryCookieFromStore(LPCWSTR UncPath, __int64 a2, unsigned int a3, _QWORD *a4, _DWORD *a5)
{
  unsigned int HTTPFromUNCPath; // ebx
  __int64 v10; // rax
  __int64 v12; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v13; // [rsp+68h] [rbp-98h] BYREF
  __int64 v14; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Url[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( !a2 || !UncPath || !a4 || !a5 )
    return 87;
  HTTPFromUNCPath = 224;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      303,
      (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
      (_DWORD)UncPath,
      a2);
  if ( CallBackRegistered() )
  {
    *a4 = 0;
    v14 = 0;
    v12 = 0;
    LODWORD(v13) = 0;
    *a5 = 0;
    HTTPFromUNCPath = DavPromptForCredentialsUsingCallback(
                        UncPath,
                        a2,
                        &v14,
                        0,
                        0,
                        (_DWORD *)&v12 + 1,
                        a3,
                        0x100000u,
                        &v13,
                        &v12,
                        0);
    if ( !HTTPFromUNCPath )
    {
      if ( (_DWORD)v12 == 1 )
      {
        memset_0(Url, 0, 0x208u);
        HIDWORD(v12) = 260;
        HTTPFromUNCPath = DavGetHTTPFromUNCPath(UncPath, Url, (LPDWORD)&v12 + 1);
        if ( HTTPFromUNCPath )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              304,
              (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
              (_DWORD)UncPath,
              HTTPFromUNCPath);
        }
        else
        {
          HTTPFromUNCPath = DavClntQueryWinInetCookies((__int64)Url, a4);
          if ( *a4 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                305,
                (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
                *a4,
                (__int64)Url);
            v10 = -1;
            do
              ++v10;
            while ( *(_WORD *)(*a4 + 2 * v10) );
            *a5 = v10 + 1;
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 306, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, Url);
          }
        }
      }
      else if ( (_DWORD)v12 == 2 )
      {
        return 1223;
      }
    }
  }
  return HTTPFromUNCPath;
}

```

## disassembly

```asm
0x18000e034  mov     [rsp-8+arg_10], rbx
0x18000e039  push    rbp
0x18000e03a  push    rsi
0x18000e03b  push    rdi
0x18000e03c  push    r12
0x18000e03e  push    r13
0x18000e040  push    r14
0x18000e042  push    r15
0x18000e044  lea     rbp, [rsp-1A0h]
0x18000e04c  sub     rsp, 2A0h
0x18000e053  mov     rax, cs:__security_cookie
0x18000e05a  xor     rax, rsp
0x18000e05d  mov     [rbp+1D0h+var_40], rax
0x18000e064  mov     r14, [rbp+1D0h+arg_20]
0x18000e06b  xor     r13d, r13d
0x18000e06e  mov     rdi, r9
0x18000e071  mov     r12d, r8d
0x18000e074  mov     r15, rdx
0x18000e077  mov     rsi, rcx
0x18000e07a  test    rdx, rdx
0x18000e07d  jz      loc_18000E278
0x18000e083  test    rcx, rcx
0x18000e086  jz      loc_18000E278
0x18000e08c  test    r9, r9
0x18000e08f  jz      loc_18000E278
0x18000e095  test    r14, r14
0x18000e098  jz      loc_18000E278
0x18000e09e  mov     ebx, 0E0h
0x18000e0a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0aa  lea     rax, WPP_GLOBAL_Control
0x18000e0b1  cmp     rcx, rax
0x18000e0b4  jz      short loc_18000E0D7
0x18000e0b6  test    byte ptr [rcx+1Ch], 2
0x18000e0ba  jz      short loc_18000E0D7
0x18000e0bc  mov     rcx, [rcx+10h]
0x18000e0c0  lea     edx, [rbx+4Fh]
0x18000e0c3  mov     r9, rsi
0x18000e0c6  mov     [rsp+2D0h+var_2B0], r15
0x18000e0cb  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e0d2  call    WPP_SF_SS
0x18000e0d7  call    CallBackRegistered
0x18000e0dc  test    eax, eax
0x18000e0de  jz      loc_18000E274
0x18000e0e4  mov     [rsp+2D0h+var_280], r13; __int64
0x18000e0e9  lea     rax, [rsp+2D0h+var_270]
0x18000e0ee  mov     [rsp+2D0h+var_288], rax; __int64
0x18000e0f3  lea     r8, [rsp+2D0h+var_260]
0x18000e0f8  lea     rax, [rsp+2D0h+var_268]
0x18000e0fd  mov     [rdi], r13
0x18000e100  mov     [rsp+2D0h+var_290], rax; __int64
0x18000e105  xor     r9d, r9d
0x18000e108  mov     [rsp+2D0h+var_298], 100000h; int
0x18000e110  lea     rax, [rsp+2D0h+var_270+4]
0x18000e115  mov     [rsp+2D0h+var_2A0], r12d; int
0x18000e11a  mov     rdx, r15
0x18000e11d  mov     [rsp+2D0h+var_2A8], rax; __int64
0x18000e122  mov     rcx, rsi; UncPath
0x18000e125  mov     [rsp+2D0h+var_2B0], r13; __int64
0x18000e12a  mov     [rsp+2D0h+var_260], r13
0x18000e12f  mov     dword ptr [rsp+2D0h+var_270], r13d
0x18000e134  mov     dword ptr [rsp+2D0h+var_270+4], r13d
0x18000e139  mov     dword ptr [rsp+2D0h+var_268], r13d
0x18000e13e  mov     [r14], r13d
0x18000e141  call    DavPromptForCredentialsUsingCallback
0x18000e146  mov     ebx, eax
0x18000e148  test    eax, eax
0x18000e14a  jnz     loc_18000E274
0x18000e150  cmp     dword ptr [rsp+2D0h+var_270], 1
0x18000e155  jnz     loc_18000E267
0x18000e15b  xor     edx, edx; Val
0x18000e15d  lea     rcx, [rbp+1D0h+Url]; void *
0x18000e161  mov     r8d, 208h; Size
0x18000e167  call    memset_0
0x18000e16c  lea     r8, [rsp+2D0h+var_270+4]; lpSize
0x18000e171  mov     dword ptr [rsp+2D0h+var_270+4], 104h
0x18000e179  lea     rdx, [rbp+1D0h+Url]; Url
0x18000e17d  mov     rcx, rsi; UncPath
0x18000e180  call    cs:__imp_DavGetHTTPFromUNCPath
0x18000e186  mov     ebx, eax
0x18000e188  test    eax, eax
0x18000e18a  jz      short loc_18000E1CE
0x18000e18c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e193  lea     rax, WPP_GLOBAL_Control
0x18000e19a  cmp     rcx, rax
0x18000e19d  jz      loc_18000E274
0x18000e1a3  test    byte ptr [rcx+1Ch], 1
0x18000e1a7  jz      loc_18000E274
0x18000e1ad  mov     rcx, [rcx+10h]
0x18000e1b1  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e1b8  mov     edx, 130h
0x18000e1bd  mov     dword ptr [rsp+2D0h+var_2B0], ebx
0x18000e1c1  mov     r9, rsi
0x18000e1c4  call    WPP_SF_Sd
0x18000e1c9  jmp     loc_18000E274
0x18000e1ce  mov     rdx, rdi
0x18000e1d1  lea     rcx, [rbp+1D0h+Url]
0x18000e1d5  call    DavClntQueryWinInetCookies
0x18000e1da  mov     r9, [rdi]
0x18000e1dd  mov     ebx, eax
0x18000e1df  test    r9, r9
0x18000e1e2  jz      short loc_18000E233
0x18000e1e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1eb  lea     rax, WPP_GLOBAL_Control
0x18000e1f2  cmp     rcx, rax
0x18000e1f5  jz      short loc_18000E21B
0x18000e1f7  test    byte ptr [rcx+1Ch], 2
0x18000e1fb  jz      short loc_18000E21B
0x18000e1fd  mov     rcx, [rcx+10h]
0x18000e201  lea     rax, [rbp+1D0h+Url]
0x18000e205  mov     edx, 131h
0x18000e20a  mov     [rsp+2D0h+var_2B0], rax
0x18000e20f  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e216  call    WPP_SF_SS
0x18000e21b  mov     rcx, [rdi]
0x18000e21e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e222  inc     rax
0x18000e225  cmp     [rcx+rax*2], r13w
0x18000e22a  jnz     short loc_18000E222
0x18000e22c  inc     eax
0x18000e22e  mov     [r14], eax
0x18000e231  jmp     short loc_18000E274
0x18000e233  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e23a  lea     rax, WPP_GLOBAL_Control
0x18000e241  cmp     rcx, rax
0x18000e244  jz      short loc_18000E274
0x18000e246  test    byte ptr [rcx+1Ch], 2
0x18000e24a  jz      short loc_18000E274
0x18000e24c  mov     rcx, [rcx+10h]
0x18000e250  lea     r9, [rbp+1D0h+Url]
0x18000e254  mov     edx, 132h
0x18000e259  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e260  call    WPP_SF_S
0x18000e265  jmp     short loc_18000E274
0x18000e267  cmp     dword ptr [rsp+2D0h+var_270], 2
0x18000e26c  mov     eax, 4C7h
0x18000e271  cmovz   ebx, eax
0x18000e274  mov     eax, ebx
0x18000e276  jmp     short loc_18000E27D
0x18000e278  mov     eax, 57h ; 'W'
0x18000e27d  mov     rcx, [rbp+1D0h+var_40]
0x18000e284  xor     rcx, rsp; StackCookie
0x18000e287  call    __security_check_cookie
0x18000e28c  mov     rbx, [rsp+2D0h+arg_10]
0x18000e294  add     rsp, 2A0h
0x18000e29b  pop     r15
0x18000e29d  pop     r14
0x18000e29f  pop     r13
0x18000e2a1  pop     r12
0x18000e2a3  pop     rdi
0x18000e2a4  pop     rsi
0x18000e2a5  pop     rbp
0x18000e2a6  retn
```
