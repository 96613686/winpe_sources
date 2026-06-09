# DavPromptForCredentialsUsingCallback

- ea: `0x18000da5c`
- end: `0x18000dd2f`
- name: `DavPromptForCredentialsUsingCallback`
- size: `723`
- prototype: `__int64 __fastcall(LPCWSTR UncPath, __int64, _QWORD *, _QWORD *, _QWORD *, _DWORD *, unsigned int, unsigned int, _DWORD *, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000bda0`
- `0x18000e034`
- `0x18000e2b0`

## callees

- `0x18000b494`
- `0x18000da5c`
- `0x180010a14`
- `0x180010c88`
- `0x180010d00`
- `0x180010f90`
- `0x180011290`
- `0x180011e82`
- `0x180011eb0`
- `0x180013010`

## import_xrefs

- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000db49`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000db49`

## pseudocode

```c
__int64 __fastcall DavPromptForCredentialsUsingCallback(
        LPCWSTR UncPath,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        _DWORD *a6,
        unsigned int a7,
        unsigned int a8,
        _DWORD *a9,
        _DWORD *a10,
        _QWORD *a11)
{
  DWORD v14; // ebx
  DWORD HTTPFromUNCPath; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  _QWORD *v18; // rcx
  DWORD Size; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v22; // [rsp+58h] [rbp-A8h]
  __int128 v23; // [rsp+68h] [rbp-98h]
  __int64 v24; // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+80h] [rbp-80h]
  _DWORD *v26; // [rsp+88h] [rbp-78h]
  _DWORD *v27; // [rsp+90h] [rbp-70h]
  WCHAR Url[264]; // [rsp+A0h] [rbp-60h] BYREF

  v26 = a6;
  v14 = 0;
  v27 = a9;
  v25 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), a8, (_DWORD)a3, (_DWORD)UncPath, a2, a8);
  *a10 = 0;
  if ( CallBackRegistered() )
  {
    v24 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    memset_0(Url, 0, 0x208u);
    Size = 260;
    HTTPFromUNCPath = DavGetHTTPFromUNCPath(UncPath, Url, &Size);
    v14 = HTTPFromUNCPath;
    if ( HTTPFromUNCPath )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          317,
          (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
          (_DWORD)UncPath,
          HTTPFromUNCPath);
      return v14;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        318,
        (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
        (_DWORD)UncPath,
        (__int64)Url);
    if ( a4 )
      *(_QWORD *)&v22 = *a4;
    else
      *(_QWORD *)&v22 = 0;
    DWORD2(v22) = 513;
    *(_QWORD *)&v23 = 0;
    DWORD2(v23) = 0;
    if ( a3 )
      *(_QWORD *)&v21 = *a3;
    else
      *(_QWORD *)&v21 = 0;
    DWORD2(v21) = Size;
    v24 = 0;
    v14 = ((__int64 (__fastcall *)(__int64, WCHAR *, _QWORD, _QWORD, __int128 *, _DWORD *, _QWORD *))qword_18001A6E0)(
            v25,
            Url,
            a8,
            a7,
            &v21,
            a10,
            a11);
    if ( *a10 && a4 && a5 )
    {
      *a4 = v22;
      *a5 = v23;
    }
    if ( a3 )
      *a3 = v21;
    if ( !a11 || !*a11 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
LABEL_33:
        *v26 = HIDWORD(v24);
        *v27 = v24;
        return v14;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_30:
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 )
          WPP_SF_dddd(v18[2], v16, v17, v14, HIDWORD(v24), v24, *a10);
        goto LABEL_33;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 319, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
    }
    v18 = WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  return v14;
}

```

## disassembly

```asm
0x18000da5c  push    rbp
0x18000da5e  push    rbx
0x18000da5f  push    rsi
0x18000da60  push    rdi
0x18000da61  push    r12
0x18000da63  push    r13
0x18000da65  push    r14
0x18000da67  push    r15
0x18000da69  lea     rbp, [rsp-1C8h]
0x18000da71  sub     rsp, 2C8h
0x18000da78  mov     rax, cs:__security_cookie
0x18000da7f  xor     rax, rsp
0x18000da82  mov     [rbp+200h+var_50], rax
0x18000da89  mov     r12, [rbp+200h+arg_20]
0x18000da90  mov     rdi, rcx
0x18000da93  mov     rcx, [rbp+200h+arg_28]
0x18000da9a  mov     r14, r9
0x18000da9d  mov     r13, [rbp+200h+arg_48]
0x18000daa4  mov     rsi, r8
0x18000daa7  mov     r15, [rbp+200h+arg_50]
0x18000daae  mov     rax, rdx
0x18000dab1  mov     [rbp+200h+var_278], rcx
0x18000dab5  xor     ebx, ebx
0x18000dab7  mov     rcx, [rbp+200h+arg_40]
0x18000dabe  mov     [rbp+200h+var_270], rcx
0x18000dac2  mov     [rbp+200h+var_280], rdx
0x18000dac6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dacd  lea     rdx, WPP_GLOBAL_Control
0x18000dad4  cmp     rcx, rdx
0x18000dad7  jz      short loc_18000DAFA
0x18000dad9  test    byte ptr [rcx+1Ch], 2
0x18000dadd  jz      short loc_18000DAFA
0x18000dadf  mov     edx, [rbp+200h+arg_38]
0x18000dae5  mov     r9, rdi
0x18000dae8  mov     rcx, [rcx+10h]
0x18000daec  mov     dword ptr [rsp+300h+var_2D8], edx
0x18000daf0  mov     [rsp+300h+var_2E0], rax
0x18000daf5  call    WPP_SF_SSd
0x18000dafa  mov     [r13+0], ebx
0x18000dafe  call    CallBackRegistered
0x18000db03  test    eax, eax
0x18000db05  jz      loc_18000DD0A
0x18000db0b  xorps   xmm0, xmm0
0x18000db0e  lea     rcx, [rbp+200h+Url]; void *
0x18000db12  xor     eax, eax
0x18000db14  xor     edx, edx; Val
0x18000db16  mov     r8d, 208h; Size
0x18000db1c  mov     [rsp+300h+var_288], rax
0x18000db21  movups  [rsp+300h+var_2B8], xmm0
0x18000db26  movups  [rsp+300h+var_2A8], xmm0
0x18000db2b  movups  [rsp+300h+var_298], xmm0
0x18000db30  call    memset_0
0x18000db35  lea     r8, [rsp+300h+Size]; lpSize
0x18000db3a  mov     [rsp+300h+Size], 104h
0x18000db42  lea     rdx, [rbp+200h+Url]; Url
0x18000db46  mov     rcx, rdi; UncPath
0x18000db49  call    cs:__imp_DavGetHTTPFromUNCPath
0x18000db4f  mov     ebx, eax
0x18000db51  test    eax, eax
0x18000db53  jz      short loc_18000DB97
0x18000db55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db5c  lea     rsi, WPP_GLOBAL_Control
0x18000db63  cmp     rcx, rsi
0x18000db66  jz      loc_18000DD0A
0x18000db6c  test    byte ptr [rcx+1Ch], 1
0x18000db70  jz      loc_18000DD0A
0x18000db76  mov     rcx, [rcx+10h]
0x18000db7a  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000db81  mov     edx, 13Dh
0x18000db86  mov     dword ptr [rsp+300h+var_2E0], eax
0x18000db8a  mov     r9, rdi
0x18000db8d  call    WPP_SF_Sd
0x18000db92  jmp     loc_18000DD0A
0x18000db97  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db9e  lea     rax, WPP_GLOBAL_Control
0x18000dba5  cmp     rcx, rax
0x18000dba8  jz      short loc_18000DBD1
0x18000dbaa  test    byte ptr [rcx+1Ch], 1
0x18000dbae  jz      short loc_18000DBD1
0x18000dbb0  mov     rcx, [rcx+10h]
0x18000dbb4  lea     rax, [rbp+200h+Url]
0x18000dbb8  mov     edx, 13Eh
0x18000dbbd  mov     [rsp+300h+var_2E0], rax
0x18000dbc2  mov     r9, rdi
0x18000dbc5  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000dbcc  call    WPP_SF_SS
0x18000dbd1  xor     edi, edi
0x18000dbd3  test    r14, r14
0x18000dbd6  jz      short loc_18000DBE2
0x18000dbd8  mov     rax, [r14]
0x18000dbdb  mov     qword ptr [rsp+300h+var_2A8], rax
0x18000dbe0  jmp     short loc_18000DBE7
0x18000dbe2  mov     qword ptr [rsp+300h+var_2A8], rdi
0x18000dbe7  mov     dword ptr [rsp+300h+var_2A8+8], 201h
0x18000dbef  mov     qword ptr [rsp+300h+var_298], rdi
0x18000dbf4  mov     dword ptr [rsp+300h+var_298+8], edi
0x18000dbf8  test    rsi, rsi
0x18000dbfb  jz      short loc_18000DC07
0x18000dbfd  mov     rax, [rsi]
0x18000dc00  mov     qword ptr [rsp+300h+var_2B8], rax
0x18000dc05  jmp     short loc_18000DC0C
0x18000dc07  mov     qword ptr [rsp+300h+var_2B8], rdi
0x18000dc0c  mov     eax, [rsp+300h+Size]
0x18000dc10  lea     rdx, [rbp+200h+Url]
0x18000dc14  mov     r9d, [rbp+200h+arg_30]
0x18000dc1b  mov     r8d, [rbp+200h+arg_38]
0x18000dc22  mov     rcx, [rbp+200h+var_280]
0x18000dc26  mov     dword ptr [rsp+300h+var_2B8+8], eax
0x18000dc2a  lea     rax, [rsp+300h+var_2B8]
0x18000dc2f  mov     [rsp+300h+var_2D0], r15
0x18000dc34  mov     [rsp+300h+var_2D8], r13
0x18000dc39  mov     [rsp+300h+var_2E0], rax
0x18000dc3e  mov     rax, cs:qword_18001A6E0
0x18000dc45  mov     [rsp+300h+var_288], rdi
0x18000dc4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc4f  mov     ebx, eax
0x18000dc51  cmp     [r13+0], edi
0x18000dc55  jz      short loc_18000DC72
0x18000dc57  test    r14, r14
0x18000dc5a  jz      short loc_18000DC72
0x18000dc5c  test    r12, r12
0x18000dc5f  jz      short loc_18000DC72
0x18000dc61  mov     rax, qword ptr [rsp+300h+var_2A8]
0x18000dc66  mov     [r14], rax
0x18000dc69  mov     rax, qword ptr [rsp+300h+var_298]
0x18000dc6e  mov     [r12], rax
0x18000dc72  test    rsi, rsi
0x18000dc75  jz      short loc_18000DC7F
0x18000dc77  mov     rax, qword ptr [rsp+300h+var_2B8]
0x18000dc7c  mov     [rsi], rax
0x18000dc7f  test    r15, r15
0x18000dc82  jz      short loc_18000DC92
0x18000dc84  cmp     [r15], rdi
0x18000dc87  jz      short loc_18000DC92
0x18000dc89  lea     rsi, WPP_GLOBAL_Control
0x18000dc90  jmp     short loc_18000DCC0
0x18000dc92  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc99  lea     rsi, WPP_GLOBAL_Control
0x18000dca0  cmp     rcx, rsi
0x18000dca3  jz      short loc_18000DCF6
0x18000dca5  test    byte ptr [rcx+1Ch], 1
0x18000dca9  jz      short loc_18000DCC7
0x18000dcab  mov     rcx, [rcx+10h]
0x18000dcaf  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000dcb6  mov     edx, 13Fh
0x18000dcbb  call    WPP_SF_
0x18000dcc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcc7  cmp     rcx, rsi
0x18000dcca  jz      short loc_18000DCF6
0x18000dccc  test    byte ptr [rcx+1Ch], 2
0x18000dcd0  jz      short loc_18000DCF6
0x18000dcd2  mov     eax, [r13+0]
0x18000dcd6  mov     r9d, ebx
0x18000dcd9  mov     rcx, [rcx+10h]
0x18000dcdd  mov     dword ptr [rsp+300h+var_2D0], eax
0x18000dce1  mov     eax, dword ptr [rsp+300h+var_288]
0x18000dce5  mov     dword ptr [rsp+300h+var_2D8], eax
0x18000dce9  mov     eax, dword ptr [rsp+300h+var_288+4]
0x18000dced  mov     dword ptr [rsp+300h+var_2E0], eax
0x18000dcf1  call    WPP_SF_dddd
0x18000dcf6  mov     rcx, [rbp+200h+var_278]
0x18000dcfa  mov     eax, dword ptr [rsp+300h+var_288+4]
0x18000dcfe  mov     [rcx], eax
0x18000dd00  mov     rcx, [rbp+200h+var_270]
0x18000dd04  mov     eax, dword ptr [rsp+300h+var_288]
0x18000dd08  mov     [rcx], eax
0x18000dd0a  mov     eax, ebx
0x18000dd0c  mov     rcx, [rbp+200h+var_50]
0x18000dd13  xor     rcx, rsp; StackCookie
0x18000dd16  call    __security_check_cookie
0x18000dd1b  add     rsp, 2C8h
0x18000dd22  pop     r15
0x18000dd24  pop     r14
0x18000dd26  pop     r13
0x18000dd28  pop     r12
0x18000dd2a  pop     rdi
0x18000dd2b  pop     rsi
0x18000dd2c  pop     rbx
0x18000dd2d  pop     rbp
0x18000dd2e  retn
```
