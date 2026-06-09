# DwmGetWindowAttribute

- ea: `0x180004a40`
- end: `0x180004d17`
- name: `DwmGetWindowAttribute`
- size: `727`
- prototype: `HRESULT __stdcall(HWND hwnd, DWORD dwAttribute, PVOID pvAttribute, DWORD cbAttribute)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004a40`
- `0x180004d20`
- `0x180004d44`
- `0x180004fb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ad5`
- `USER32!GetWindowCompositionAttribute` at `0x180004a88`
- `USER32!GetWindowCompositionAttribute` at `0x180004a88`

## pseudocode

```c
HRESULT __stdcall DwmGetWindowAttribute(HWND hwnd, DWORD dwAttribute, PVOID pvAttribute, DWORD cbAttribute)
{
  int v5; // eax
  HRESULT v6; // ebx
  HRESULT result; // eax
  signed int LastError; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  int v11[2]; // [rsp+20h] [rbp-28h] BYREF
  PVOID v12; // [rsp+28h] [rbp-20h]
  DWORD v13; // [rsp+30h] [rbp-18h]
  int v14; // [rsp+34h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !pvAttribute || cbAttribute < 4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
      (const char *)0x80070057LL,
      v11[0]);
    return -2147024809;
  }
  if ( dwAttribute == 14 )
  {
    v5 = 18;
    goto LABEL_5;
  }
  if ( dwAttribute == 1 )
  {
    v5 = 1;
    goto LABEL_5;
  }
  if ( dwAttribute > 0x404 )
  {
    switch ( dwAttribute )
    {
      case 0x406u:
        v5 = 31;
        break;
      case 0x407u:
        v5 = 32;
        break;
      case 0x10000u:
        v5 = 10;
        break;
      case 0x10001u:
        v5 = 11;
        break;
      case 0x10002u:
        v5 = 12;
        break;
      default:
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAE,
          (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
          (const char *)0x80070057LL,
          v11[0]);
        return -2147024809;
    }
LABEL_5:
    v11[0] = v5;
    v11[1] = 0;
    v14 = 0;
    v12 = pvAttribute;
    v13 = cbAttribute;
    if ( (unsigned int)GetWindowCompositionAttribute(hwnd, v11) )
    {
      v6 = 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        return 0;
      if ( dwAttribute != 1 )
      {
        wil::details::in1diag3::_Log_Hr(retaddr, v9, v10, (const char *)(unsigned int)v6, v11[0]);
        return v6;
      }
    }
    if ( v6 >= 0 )
      return 0;
    return v6;
  }
  if ( dwAttribute == 1028 )
  {
    v5 = 29;
    goto LABEL_5;
  }
  switch ( dwAttribute )
  {
    case 2u:
      v5 = 2;
      goto LABEL_5;
    case 3u:
      v5 = 3;
      goto LABEL_5;
    case 4u:
      v5 = 4;
      goto LABEL_5;
    case 5u:
      v5 = 5;
      goto LABEL_5;
    case 6u:
      v5 = 6;
      goto LABEL_5;
    case 7u:
      v5 = 7;
      goto LABEL_5;
    case 9u:
      v5 = 8;
      goto LABEL_5;
    case 0xAu:
      v5 = 9;
      goto LABEL_5;
    case 0xBu:
      v5 = 16;
      goto LABEL_5;
    case 0xCu:
      v5 = 13;
      goto LABEL_5;
    case 0xDu:
      v5 = 17;
      goto LABEL_5;
    case 0xFu:
      v5 = 20;
      goto LABEL_5;
    case 0x10u:
      v5 = 25;
      goto LABEL_5;
    case 0x13u:
    case 0x14u:
      v5 = 26;
      goto LABEL_5;
    case 0x21u:
      v5 = 27;
      goto LABEL_5;
    case 0x26u:
      v5 = 30;
      goto LABEL_5;
    case 0x27u:
      v5 = 36;
      goto LABEL_5;
    case 0x28u:
      v5 = 37;
      goto LABEL_5;
    default:
      if ( dwAttribute != 37 )
        goto LABEL_37;
      result = GetVisibleBorderThickness(hwnd, pvAttribute, cbAttribute);
      break;
  }
  return result;
}

```

## disassembly

```asm
0x180004a40  push    rdi
0x180004a42  sub     rsp, 40h
0x180004a46  mov     r10, r8
0x180004a49  mov     edi, edx
0x180004a4b  mov     r11, rcx
0x180004a4e  test    r8, r8
0x180004a51  jz      short loc_180004AA5
0x180004a53  cmp     r9d, 4
0x180004a57  jb      short loc_180004AA5
0x180004a59  cmp     edx, 0Eh
0x180004a5c  jnz     short loc_180004ACC
0x180004a5e  mov     eax, 12h
0x180004a63  mov     [rsp+48h+var_28], eax; int
0x180004a67  lea     rdx, [rsp+48h+var_28]
0x180004a6c  xor     eax, eax
0x180004a6e  mov     [rsp+48h+arg_0], rbx
0x180004a73  mov     rcx, r11
0x180004a76  mov     [rsp+48h+var_24], eax
0x180004a7a  mov     [rsp+48h+var_14], eax
0x180004a7e  mov     [rsp+48h+var_20], r10
0x180004a83  mov     [rsp+48h+var_18], r9d
0x180004a88  call    cs:__imp_GetWindowCompositionAttribute
0x180004a8e  test    eax, eax
0x180004a90  jz      short loc_180004AD5
0x180004a92  xor     ebx, ebx
0x180004a94  test    ebx, ebx
0x180004a96  js      short loc_180004B00
0x180004a98  mov     rbx, [rsp+48h+arg_0]
0x180004a9d  xor     eax, eax
0x180004a9f  add     rsp, 40h
0x180004aa3  pop     rdi
0x180004aa4  retn
0x180004aa5  mov     rcx, [rsp+48h]; this
0x180004aaa  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x180004ab1  mov     r9d, 80070057h; char *
0x180004ab7  mov     edx, 9Ch; void *
0x180004abc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ac1  mov     eax, 80070057h
0x180004ac6  add     rsp, 40h
0x180004aca  pop     rdi
0x180004acb  retn
0x180004acc  cmp     edi, 1
0x180004acf  jnz     short loc_180004B0D
0x180004ad1  mov     eax, edi
0x180004ad3  jmp     short loc_180004A63
0x180004ad5  call    cs:__imp_GetLastError
0x180004adb  mov     ebx, eax
0x180004add  test    eax, eax
0x180004adf  jle     short loc_180004AEA
0x180004ae1  movzx   ebx, ax
0x180004ae4  or      ebx, 80070000h
0x180004aea  test    ebx, ebx
0x180004aec  jns     short loc_180004A98
0x180004aee  cmp     edi, 1
0x180004af1  jz      short loc_180004A94
0x180004af3  mov     rcx, [rsp+48h]; this
0x180004af8  mov     r9d, ebx; char *
0x180004afb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004b00  mov     eax, ebx
0x180004b02  mov     rbx, [rsp+48h+arg_0]
0x180004b07  add     rsp, 40h
0x180004b0b  pop     rdi
0x180004b0c  retn
0x180004b0d  cmp     edi, 404h
0x180004b13  ja      loc_180004BB4
0x180004b19  jz      loc_180004C68
0x180004b1f  lea     eax, [rdx-2]; switch 39 cases
0x180004b22  cmp     eax, 26h
0x180004b25  ja      short def_180004B40; jumptable 0000000180004B40 default case, cases 8,14,17,18,21-32,34-37
0x180004b27  lea     rdx, __ImageBase
0x180004b2e  movzx   eax, ds:(byte_180004CF0 - 180000000h)[rdx+rax]
0x180004b36  mov     ecx, ds:(jpt_180004B40 - 180000000h)[rdx+rax*4]
0x180004b3d  add     rcx, rdx
0x180004b40  jmp     rcx; switch jump
0x180004b42  mov     eax, 5; jumptable 0000000180004B40 case 5
0x180004b47  jmp     loc_180004A63
0x180004b4c  mov     eax, 8; jumptable 0000000180004B40 case 9
0x180004b51  jmp     loc_180004A63
0x180004b56  mov     eax, 11h; jumptable 0000000180004B40 case 13
0x180004b5b  jmp     loc_180004A63
0x180004b60  mov     eax, 1Eh; jumptable 0000000180004B40 case 38
0x180004b65  jmp     loc_180004A63
0x180004b6a  mov     eax, 14h; jumptable 0000000180004B40 case 15
0x180004b6f  jmp     loc_180004A63
0x180004b74  mov     eax, 1Bh; jumptable 0000000180004B40 case 33
0x180004b79  jmp     loc_180004A63
0x180004b7e  mov     eax, 3; jumptable 0000000180004B40 case 3
0x180004b83  jmp     loc_180004A63
0x180004b88  mov     eax, 1Ah; jumptable 0000000180004B40 cases 19,20
0x180004b8d  jmp     loc_180004A63
0x180004b92  mov     eax, 10h; jumptable 0000000180004B40 case 11
0x180004b97  jmp     loc_180004A63
0x180004b9c  cmp     edi, 25h ; '%'; jumptable 0000000180004B40 default case, cases 8,14,17,18,21-32,34-37
0x180004b9f  jnz     short loc_180004BE7
0x180004ba1  mov     r8d, r9d; unsigned int
0x180004ba4  mov     rdx, r10; void *
0x180004ba7  mov     rcx, r11; HWND
0x180004baa  add     rsp, 40h
0x180004bae  pop     rdi
0x180004baf  jmp     ?GetVisibleBorderThickness@@YAJPEAUHWND__@@PEAXK@Z; GetVisibleBorderThickness(HWND__ *,void *,ulong)
0x180004bb4  mov     eax, edi
0x180004bb6  sub     eax, 406h
0x180004bbb  jz      loc_180004C9A
0x180004bc1  sub     eax, 1
0x180004bc4  jz      loc_180004C90
0x180004bca  sub     eax, 0FBF9h
0x180004bcf  jz      loc_180004C86
0x180004bd5  sub     eax, 1
0x180004bd8  jz      loc_180004C7C
0x180004bde  cmp     eax, 1
0x180004be1  jz      loc_180004C72
0x180004be7  mov     rcx, [rsp+48h]; this
0x180004bec  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x180004bf3  mov     r9d, 80070057h; char *
0x180004bf9  mov     edx, 0AEh; void *
0x180004bfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c03  mov     eax, 80070057h
0x180004c08  add     rsp, 40h
0x180004c0c  pop     rdi
0x180004c0d  retn
0x180004c0e  mov     eax, 2; jumptable 0000000180004B40 case 2
0x180004c13  jmp     loc_180004A63
0x180004c18  mov     eax, 4; jumptable 0000000180004B40 case 4
0x180004c1d  jmp     loc_180004A63
0x180004c22  mov     eax, 6; jumptable 0000000180004B40 case 6
0x180004c27  jmp     loc_180004A63
0x180004c2c  mov     eax, 7; jumptable 0000000180004B40 case 7
0x180004c31  jmp     loc_180004A63
0x180004c36  mov     eax, 9; jumptable 0000000180004B40 case 10
0x180004c3b  jmp     loc_180004A63
0x180004c40  mov     eax, 0Dh; jumptable 0000000180004B40 case 12
0x180004c45  jmp     loc_180004A63
0x180004c4a  mov     eax, 19h; jumptable 0000000180004B40 case 16
0x180004c4f  jmp     loc_180004A63
0x180004c54  mov     eax, 24h ; '$'; jumptable 0000000180004B40 case 39
0x180004c59  jmp     loc_180004A63
0x180004c5e  mov     eax, 25h ; '%'; jumptable 0000000180004B40 case 40
0x180004c63  jmp     loc_180004A63
0x180004c68  mov     eax, 1Dh
0x180004c6d  jmp     loc_180004A63
0x180004c72  mov     eax, 0Ch
0x180004c77  jmp     loc_180004A63
0x180004c7c  mov     eax, 0Bh
0x180004c81  jmp     loc_180004A63
0x180004c86  mov     eax, 0Ah
0x180004c8b  jmp     loc_180004A63
0x180004c90  mov     eax, 20h ; ' '
0x180004c95  jmp     loc_180004A63
0x180004c9a  mov     eax, 1Fh
0x180004c9f  jmp     loc_180004A63
```
