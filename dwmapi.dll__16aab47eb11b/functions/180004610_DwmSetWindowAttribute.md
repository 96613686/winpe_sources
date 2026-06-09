# DwmSetWindowAttribute

- ea: `0x180004610`
- end: `0x180004a37`
- name: `DwmSetWindowAttribute`
- size: `1063`
- prototype: `HRESULT __stdcall(HWND hwnd, DWORD dwAttribute, LPCVOID pvAttribute, DWORD cbAttribute)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800035f0`
- `0x180004610`
- `0x180004d20`
- `0x180004da8`
- `0x180004e30`
- `0x18000d0a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048a3`
- `USER32!SetWindowCompositionAttribute` at `0x18000468d`
- `USER32!SetWindowCompositionAttribute` at `0x180004895`
- `USER32!SetWindowCompositionAttribute` at `0x18000468d`
- `USER32!SetWindowCompositionAttribute` at `0x180004895`
- `USER32!__imp_IsShellManagedWindow` at `0x180004775`
- `USER32!__imp_IsShellManagedWindow` at `0x180004775`

## pseudocode

```c
HRESULT __stdcall DwmSetWindowAttribute(HWND hwnd, DWORD dwAttribute, LPCVOID pvAttribute, DWORD cbAttribute)
{
  int v9; // edi
  signed int v10; // eax
  HRESULT v11; // edi
  wil::details::in1diag3 *v12; // rcx
  __int64 v13; // rdx
  bool v14; // zf
  int v15; // edi
  signed int LastError; // eax
  HRESULT v17; // ebx
  int v18[2]; // [rsp+20h] [rbp-58h] BYREF
  __int128 *v19; // [rsp+28h] [rbp-50h]
  __int64 v20; // [rsp+30h] [rbp-48h]
  __int128 v21; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !pvAttribute || cbAttribute < 4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
      (const char *)0x80070057LL,
      v18[0]);
    return -2147024809;
  }
  if ( dwAttribute == 14 )
  {
    v9 = 18;
    goto LABEL_4;
  }
  if ( dwAttribute == 1 )
  {
    v9 = 1;
    goto LABEL_4;
  }
  if ( dwAttribute > 0x404 )
  {
    switch ( dwAttribute )
    {
      case 0x406u:
        v9 = 31;
        goto LABEL_4;
      case 0x407u:
        v9 = 32;
        goto LABEL_4;
      case 0x10000u:
        v9 = 10;
        goto LABEL_4;
      case 0x10001u:
        v9 = 11;
        goto LABEL_4;
      case 0x10002u:
        v9 = 12;
        goto LABEL_4;
    }
LABEL_41:
    if ( dwAttribute == 17 )
    {
      if ( cbAttribute == 4 )
      {
        *(_QWORD *)v18 = 19;
        v14 = *(_DWORD *)pvAttribute == 1;
        v20 = 16;
        v21 = 0;
        v15 = 5;
        if ( !v14 )
          v15 = 0;
        v19 = &v21;
        LODWORD(v21) = v15;
        if ( !(unsigned int)SetWindowCompositionAttribute(hwnd, v18) )
        {
          LastError = GetLastError();
          v17 = LastError;
          if ( LastError > 0 )
            v17 = (unsigned __int16)LastError | 0x80070000;
          if ( v17 < 0 )
          {
            if ( v17 == -2147024890 )
              return -2147024890;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x138,
              (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
              (const char *)(unsigned int)v17,
              v18[0]);
            return v17;
          }
        }
        return 0;
      }
      v12 = retaddr;
      v13 = 302;
    }
    else
    {
      if ( dwAttribute - 34 <= 2 )
        return SetPartColor(hwnd, dwAttribute, pvAttribute, cbAttribute);
      v12 = retaddr;
      v13 = 320;
    }
LABEL_54:
    wil::details::in1diag3::Return_Hr(
      v12,
      (void *)v13,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
      (const char *)0x80070057LL,
      v18[0]);
    return -2147024809;
  }
  if ( dwAttribute == 1028 )
  {
    v9 = 29;
    goto LABEL_4;
  }
  switch ( dwAttribute )
  {
    case 2u:
      v9 = 2;
      goto LABEL_4;
    case 3u:
      v9 = 3;
      goto LABEL_4;
    case 4u:
      v9 = 4;
      goto LABEL_4;
    case 5u:
      v9 = 5;
      goto LABEL_4;
    case 6u:
      v9 = 6;
      goto LABEL_4;
    case 7u:
      v9 = 7;
      goto LABEL_4;
    case 9u:
      v9 = 8;
      goto LABEL_4;
    case 0xAu:
      v9 = 9;
      goto LABEL_4;
    case 0xBu:
      v9 = 16;
      goto LABEL_4;
    case 0xCu:
      v9 = 13;
      goto LABEL_4;
    case 0xDu:
      v9 = 17;
      goto LABEL_4;
    case 0xFu:
      v9 = 20;
      break;
    case 0x10u:
      v9 = 25;
      goto LABEL_4;
    case 0x13u:
    case 0x14u:
      v9 = 26;
      if ( dwAttribute != 15 )
        goto LABEL_4;
      break;
    case 0x21u:
      v9 = 27;
      goto LABEL_4;
    case 0x26u:
      v9 = 30;
      goto LABEL_4;
    case 0x27u:
      v9 = 36;
      goto LABEL_4;
    case 0x28u:
      v9 = 37;
      goto LABEL_4;
    default:
      goto LABEL_41;
  }
  if ( !(unsigned int)IsShellManagedWindow(hwnd) )
  {
    v12 = retaddr;
    v13 = 284;
    goto LABEL_54;
  }
LABEL_4:
  v18[0] = v9;
  v18[1] = 0;
  v19 = (__int128 *)pvAttribute;
  v20 = cbAttribute;
  if ( (unsigned int)SetWindowCompositionAttribute(hwnd, v18) )
    goto LABEL_5;
  v10 = GetLastError();
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 >= 0 )
  {
LABEL_5:
    if ( dwAttribute == 38 )
    {
      LogSystemBackDropAPITelemetry(pvAttribute);
    }
    else if ( cbAttribute == 4 && dwAttribute == 15 )
    {
      if ( *(_DWORD *)pvAttribute )
        DwmFlush();
    }
    return 0;
  }
  if ( v11 == -2147024890 )
    return -2147024890;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x124,
    (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
    (const char *)(unsigned int)v11,
    v18[0]);
  return v11;
}

```

## disassembly

```asm
0x180004610  push    rbx
0x180004612  push    rbp
0x180004613  push    rsi
0x180004614  push    r14
0x180004616  sub     rsp, 58h
0x18000461a  mov     rax, cs:__security_cookie
0x180004621  xor     rax, rsp
0x180004624  mov     [rsp+78h+var_30], rax
0x180004629  mov     ebp, r9d
0x18000462c  mov     rsi, r8
0x18000462f  mov     ebx, edx
0x180004631  mov     r14, rcx
0x180004634  test    r8, r8
0x180004637  jnz     loc_1800046C2
0x18000463d  mov     rcx, [rsp+78h]; this
0x180004642  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x180004649  mov     r9d, 80070057h; char *
0x18000464f  mov     edx, 114h; void *
0x180004654  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004659  mov     eax, 80070057h
0x18000465e  jmp     short loc_1800046AB
0x180004660  mov     edi, 1Ah; jumptable 0000000180004761 cases 19,20
0x180004665  cmp     ebx, 0Fh
0x180004668  jz      loc_180004772
0x18000466e  xor     eax, eax
0x180004670  mov     [rsp+78h+var_58], edi; int
0x180004674  lea     rdx, [rsp+78h+var_58]
0x180004679  mov     [rsp+78h+var_58+4], eax
0x18000467d  mov     rcx, r14
0x180004680  mov     dword ptr [rsp+78h+var_48+4], eax
0x180004684  mov     [rsp+78h+var_50], rsi
0x180004689  mov     dword ptr [rsp+78h+var_48], ebp
0x18000468d  call    cs:__imp_SetWindowCompositionAttribute
0x180004693  test    eax, eax
0x180004695  jz      short loc_1800046E5
0x180004697  cmp     ebx, 26h ; '&'
0x18000469a  jnz     short loc_180004711
0x18000469c  mov     rcx, rsi; void *
0x18000469f  call    ?LogSystemBackDropAPITelemetry@@YAXPEBX@Z; LogSystemBackDropAPITelemetry(void const *)
0x1800046a4  xor     eax, eax
0x1800046a6  mov     rdi, [rsp+78h+var_28]
0x1800046ab  mov     rcx, [rsp+78h+var_30]
0x1800046b0  xor     rcx, rsp; StackCookie
0x1800046b3  call    __security_check_cookie
0x1800046b8  add     rsp, 58h
0x1800046bc  pop     r14
0x1800046be  pop     rsi
0x1800046bf  pop     rbp
0x1800046c0  pop     rbx
0x1800046c1  retn
0x1800046c2  cmp     ebp, 4
0x1800046c5  jb      loc_18000463D
0x1800046cb  mov     [rsp+78h+var_28], rdi
0x1800046d0  cmp     ebx, 0Eh
0x1800046d3  jnz     short loc_1800046DC
0x1800046d5  mov     edi, 12h
0x1800046da  jmp     short loc_18000466E
0x1800046dc  cmp     ebx, 1
0x1800046df  jnz     short loc_18000472A
0x1800046e1  mov     edi, ebx
0x1800046e3  jmp     short loc_18000466E
0x1800046e5  call    cs:__imp_GetLastError
0x1800046eb  mov     edi, eax
0x1800046ed  test    eax, eax
0x1800046ef  jle     short loc_1800046FA
0x1800046f1  movzx   edi, ax
0x1800046f4  or      edi, 80070000h
0x1800046fa  test    edi, edi
0x1800046fc  jns     short loc_180004697
0x1800046fe  cmp     edi, 80070006h
0x180004704  jnz     loc_1800047A9
0x18000470a  mov     eax, 80070006h
0x18000470f  jmp     short loc_1800046A6
0x180004711  cmp     ebp, 4
0x180004714  jnz     short loc_1800046A4
0x180004716  cmp     ebx, 0Fh
0x180004719  jnz     short loc_1800046A4
0x18000471b  cmp     dword ptr [rsi], 0
0x18000471e  jz      short loc_1800046A4
0x180004720  call    DwmFlush
0x180004725  jmp     loc_1800046A4
0x18000472a  cmp     ebx, 404h
0x180004730  ja      loc_1800047FB
0x180004736  jz      loc_18000496C
0x18000473c  lea     eax, [rdx-2]; switch 39 cases
0x18000473f  cmp     eax, 26h
0x180004742  ja      def_180004761; jumptable 0000000180004761 default case, cases 8,14,17,18,21-32,34-37
0x180004748  lea     rdx, __ImageBase
0x18000474f  movzx   eax, ds:(byte_180004A10 - 180000000h)[rdx+rax]
0x180004757  mov     ecx, ds:(jpt_180004761 - 180000000h)[rdx+rax*4]
0x18000475e  add     rcx, rdx
0x180004761  jmp     rcx; switch jump
0x180004763  mov     edi, 5; jumptable 0000000180004761 case 5
0x180004768  jmp     loc_18000466E
0x18000476d  mov     edi, 14h; jumptable 0000000180004761 case 15
0x180004772  mov     rcx, r14
0x180004775  call    cs:__imp_IsShellManagedWindow
0x18000477b  test    eax, eax
0x18000477d  jnz     loc_18000466E
0x180004783  mov     rcx, [rsp+78h]
0x180004788  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x18000478f  mov     r9d, 80070057h
0x180004795  mov     edx, 11Ch
0x18000479a  jmp     loc_180004903
0x18000479f  mov     edi, 8; jumptable 0000000180004761 case 9
0x1800047a4  jmp     loc_18000466E
0x1800047a9  mov     rcx, [rsp+78h]; this
0x1800047ae  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x1800047b5  mov     r9d, edi; char *
0x1800047b8  mov     edx, 124h; void *
0x1800047bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047c2  mov     eax, edi
0x1800047c4  jmp     loc_1800046A6
0x1800047c9  mov     edi, 11h; jumptable 0000000180004761 case 13
0x1800047ce  jmp     loc_18000466E
0x1800047d3  mov     edi, 1Eh; jumptable 0000000180004761 case 38
0x1800047d8  jmp     loc_18000466E
0x1800047dd  mov     edi, 1Bh; jumptable 0000000180004761 case 33
0x1800047e2  jmp     loc_18000466E
0x1800047e7  mov     edi, 3; jumptable 0000000180004761 case 3
0x1800047ec  jmp     loc_18000466E
0x1800047f1  mov     edi, 10h; jumptable 0000000180004761 case 11
0x1800047f6  jmp     loc_18000466E
0x1800047fb  mov     eax, ebx
0x1800047fd  sub     eax, 406h
0x180004802  jz      loc_1800049BA
0x180004808  sub     eax, 1
0x18000480b  jz      loc_1800049B0
0x180004811  sub     eax, 0FBF9h
0x180004816  jz      loc_1800049A6
0x18000481c  sub     eax, 1
0x18000481f  jz      loc_18000499C
0x180004825  cmp     eax, 1
0x180004828  jz      loc_180004992
0x18000482e  cmp     ebx, 11h; jumptable 0000000180004761 default case, cases 8,14,17,18,21-32,34-37
0x180004831  jz      short loc_18000484E
0x180004833  lea     eax, [rbx-22h]
0x180004836  cmp     eax, 2
0x180004839  ja      loc_1800048EC
0x18000483f  mov     edx, ebx; unsigned int
0x180004841  mov     rcx, r14; HWND
0x180004844  call    ?SetPartColor@@YAJPEAUHWND__@@KPEBXK@Z; SetPartColor(HWND__ *,ulong,void const *,ulong)
0x180004849  jmp     loc_1800046A6
0x18000484e  cmp     ebp, 4
0x180004851  jnz     loc_180004976
0x180004857  xor     eax, eax
0x180004859  mov     qword ptr [rsp+78h+var_58], 13h; int
0x180004862  cmp     dword ptr [r8], 1
0x180004866  lea     rdx, [rsp+78h+var_58]
0x18000486b  xorps   xmm0, xmm0
0x18000486e  mov     [rsp+78h+var_48], 10h
0x180004877  movups  [rsp+78h+var_40], xmm0
0x18000487c  mov     edi, 5
0x180004881  mov     rcx, r14
0x180004884  cmovnz  edi, eax
0x180004887  lea     rax, [rsp+78h+var_40]
0x18000488c  mov     [rsp+78h+var_50], rax
0x180004891  mov     dword ptr [rsp+78h+var_40], edi
0x180004895  call    cs:__imp_SetWindowCompositionAttribute
0x18000489b  test    eax, eax
0x18000489d  jnz     loc_1800046A4
0x1800048a3  call    cs:__imp_GetLastError
0x1800048a9  mov     ebx, eax
0x1800048ab  test    eax, eax
0x1800048ad  jle     short loc_1800048B8
0x1800048af  movzx   ebx, ax
0x1800048b2  or      ebx, 80070000h
0x1800048b8  test    ebx, ebx
0x1800048ba  jns     loc_1800046A4
0x1800048c0  cmp     ebx, 80070006h
0x1800048c6  jz      loc_18000470A
0x1800048cc  mov     rcx, [rsp+78h]; this
0x1800048d1  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x1800048d8  mov     r9d, ebx; char *
0x1800048db  mov     edx, 138h; void *
0x1800048e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048e5  mov     eax, ebx
0x1800048e7  jmp     loc_1800046A6
0x1800048ec  mov     rcx, [rsp+78h]; this
0x1800048f1  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x1800048f8  mov     r9d, 80070057h; char *
0x1800048fe  mov     edx, 140h; void *
0x180004903  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004908  mov     eax, 80070057h
0x18000490d  jmp     loc_1800046A6
0x180004912  mov     edi, 2; jumptable 0000000180004761 case 2
0x180004917  jmp     loc_18000466E
0x18000491c  mov     edi, 4; jumptable 0000000180004761 case 4
0x180004921  jmp     loc_18000466E
0x180004926  mov     edi, 6; jumptable 0000000180004761 case 6
0x18000492b  jmp     loc_18000466E
0x180004930  mov     edi, 7; jumptable 0000000180004761 case 7
0x180004935  jmp     loc_18000466E
0x18000493a  mov     edi, 9; jumptable 0000000180004761 case 10
0x18000493f  jmp     loc_18000466E
0x180004944  mov     edi, 0Dh; jumptable 0000000180004761 case 12
0x180004949  jmp     loc_18000466E
0x18000494e  mov     edi, 19h; jumptable 0000000180004761 case 16
0x180004953  jmp     loc_18000466E
0x180004958  mov     edi, 24h ; '$'; jumptable 0000000180004761 case 39
0x18000495d  jmp     loc_18000466E
0x180004962  mov     edi, 25h ; '%'; jumptable 0000000180004761 case 40
0x180004967  jmp     loc_18000466E
0x18000496c  mov     edi, 1Dh
0x180004971  jmp     loc_18000466E
0x180004976  mov     rcx, [rsp+78h]
0x18000497b  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x180004982  mov     r9d, 80070057h
0x180004988  mov     edx, 12Eh
0x18000498d  jmp     loc_180004903
0x180004992  mov     edi, 0Ch
0x180004997  jmp     loc_18000466E
0x18000499c  mov     edi, 0Bh
0x1800049a1  jmp     loc_18000466E
0x1800049a6  mov     edi, 0Ah
0x1800049ab  jmp     loc_18000466E
0x1800049b0  mov     edi, 20h ; ' '
0x1800049b5  jmp     loc_18000466E
0x1800049ba  mov     edi, 1Fh
0x1800049bf  jmp     loc_18000466E
```
