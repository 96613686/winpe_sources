# _RtlpMuiRegLoadInstalledFromKey

- ea: `0x180124284`
- end: `0x18012451e`
- name: `_RtlpMuiRegLoadInstalledFromKey`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1801210e0`

## callees

- `0x1800c4700`
- `0x1800d7b80`
- `0x1800da250`
- `0x180124284`
- `0x18012d320`
- `0x18014cf40`
- `0x18014d8f8`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015f120`
- `0x180162810`

## string_xrefs

- `0x1801242b4`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\UILanguages`

## pseudocode

```c
__int64 __fastcall RtlpMuiRegLoadInstalledFromKey(int a1)
{
  size_t v2; // rax
  int v3; // ebx
  unsigned int v5; // edi
  int v6; // eax
  __int16 v7; // r10
  unsigned int v8; // r10d
  int v9; // [rsp+20h] [rbp-E0h]
  unsigned int v10; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v11; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v14; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+64h] [rbp-9Ch] BYREF
  _QWORD v18[4]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v19; // [rsp+88h] [rbp-78h]
  _BYTE v20[12]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v21; // [rsp+A4h] [rbp-5Ch]
  WCHAR SourceString[248]; // [rsp+A8h] [rbp-58h] BYREF

  v16 = 0;
  Handle = 0;
  DestinationString.Buffer = (wchar_t *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\UILanguages";
  v10 = 0;
  v11 = -1;
  v14 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  v2 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\UILanguages");
  v18[0] = 48;
  v18[3] = 64;
  if ( v2 >= 0xFFFE )
    LOWORD(v2) = -4;
  DestinationString.Length = v2;
  DestinationString.MaximumLength = v2 + 2;
  v14 = 0;
  v18[1] = 0;
  v18[2] = &DestinationString;
  v19 = 0;
  v3 = NtOpenKey(&v14, 131097, v18);
  if ( v3 < 0 )
    return 0;
  v5 = 0;
  while ( v3 != -2147483622 )
  {
    v6 = NtEnumerateKey(v14, v5, 0, v20, 512, &v16, v10, v12, Handle);
    v3 = v6;
    if ( v6 < 0 )
    {
      if ( v6 != -2147483622 )
        goto LABEL_26;
    }
    else if ( (unsigned __int64)v21 + 24 <= 0x200 )
    {
      SourceString[(unsigned __int64)v21 >> 1] = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      if ( (int)LdrpOpenKey(&DestinationString, v14, 131097, &Handle) >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"Type");
        LODWORD(v12) = 4;
        v17 = 4;
        if ( (int)LdrpQueryValueKey(Handle, &DestinationString, &v12, &v10, &v17) >= 0
          && (int)ValidateRegistrLangType(v10) >= 0 )
        {
          v8 = v7 & 0x419F;
          v10 = v8;
          if ( (v8 & 7) != 0 && (v8 & 7 & -(v8 & 7)) == (v8 & 7) )
          {
            if ( (v8 & 0x180) == 0 || (v8 & 0x180 & -(v8 & 0x180)) != (v8 & 0x180) )
            {
              v8 = v8 & 0xFFFFFE7F | 0x80;
              v10 = v8;
            }
            if ( (v8 & 0x18) != 0 && (v8 & 0x18 & -(v8 & 0x18)) == (v8 & 0x18) && (v8 & 0xC) != 8 )
              RtlpMuiRegAddLanguageByName(a1, (_DWORD)Handle, (unsigned int)SourceString, v8, v9, (__int64)&v11);
          }
        }
      }
    }
    if ( Handle )
    {
      NtClose(Handle);
      Handle = 0;
    }
    ++v5;
  }
  v3 = 0;
LABEL_26:
  if ( v14 )
    NtClose(v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180124284  push    rbp
0x180124286  push    rbx
0x180124287  push    rsi
0x180124288  push    rdi
0x180124289  lea     rbp, [rsp-1A8h]
0x180124291  sub     rsp, 2A8h
0x180124298  mov     rax, cs:__security_cookie
0x18012429f  xor     rax, rsp
0x1801242a2  mov     [rbp+1C0h+var_28], rax
0x1801242a9  mov     rsi, rcx
0x1801242ac  mov     [rsp+2C0h+var_260], 0
0x1801242b4  lea     rcx, aRegistryMachin_41; "\\Registry\\Machine\\System\\CurrentCon"...
0x1801242bb  mov     [rsp+2C0h+Handle], 0
0x1801242c4  or      eax, 0FFFFFFFFh
0x1801242c7  mov     [rsp+2C0h+DestinationString.Buffer], rcx
0x1801242cc  mov     [rsp+2C0h+var_290], 0
0x1801242d4  mov     [rsp+2C0h+var_28C], ax
0x1801242d9  mov     [rsp+2C0h+var_278], 0
0x1801242e2  mov     qword ptr [rsp+2C0h+DestinationString.Length], 0
0x1801242eb  call    wcslen
0x1801242f0  add     rax, rax
0x1801242f3  mov     [rsp+2C0h+var_258], 30h ; '0'
0x1801242fc  cmp     rax, 0FFFEh
0x180124302  mov     [rbp+1C0h+var_240], 40h ; '@'
0x18012430a  mov     ecx, 0FFFCh
0x18012430f  lea     r8, [rsp+2C0h+var_258]
0x180124314  cmovnb  rax, rcx
0x180124318  xorps   xmm0, xmm0
0x18012431b  mov     [rsp+2C0h+DestinationString.Length], ax
0x180124320  lea     rcx, [rsp+2C0h+var_278]
0x180124325  add     ax, 2
0x180124329  mov     edx, 20019h
0x18012432e  mov     [rsp+2C0h+DestinationString.MaximumLength], ax
0x180124333  xor     eax, eax
0x180124335  mov     [rsp+2C0h+var_278], rax
0x18012433a  mov     [rsp+2C0h+var_250], rax
0x18012433f  lea     rax, [rsp+2C0h+DestinationString]
0x180124344  mov     [rsp+2C0h+var_248], rax
0x180124349  movdqu  [rbp+1C0h+var_238], xmm0
0x18012434e  call    NtOpenKey
0x180124353  mov     ebx, eax
0x180124355  test    eax, eax
0x180124357  jns     short loc_180124360
0x180124359  xor     eax, eax
0x18012435b  jmp     loc_180124502
0x180124360  xor     edi, edi
0x180124362  cmp     ebx, 8000001Ah
0x180124368  jz      loc_1801244EF
0x18012436e  mov     rcx, [rsp+2C0h+var_278]
0x180124373  lea     rax, [rsp+2C0h+var_260]
0x180124378  mov     [rsp+2C0h+var_298], rax
0x18012437d  lea     r9, [rbp+1C0h+var_228]
0x180124381  xor     r8d, r8d
0x180124384  mov     dword ptr [rsp+2C0h+var_2A0], 200h
0x18012438c  mov     edx, edi
0x18012438e  call    NtEnumerateKey
0x180124393  mov     ebx, eax
0x180124395  test    eax, eax
0x180124397  js      loc_1801244C9
0x18012439d  mov     ecx, [rbp+1C0h+var_21C]
0x1801243a0  lea     rax, [rcx+18h]
0x1801243a4  cmp     rax, 200h
0x1801243aa  ja      loc_1801244D0
0x1801243b0  shr     rcx, 1
0x1801243b3  lea     rdx, [rbp+1C0h+SourceString]; SourceString
0x1801243b7  xor     eax, eax
0x1801243b9  mov     [rbp+rcx*2+1C0h+SourceString], ax
0x1801243be  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x1801243c3  call    RtlInitUnicodeString
0x1801243c8  mov     rdx, [rsp+2C0h+var_278]
0x1801243cd  lea     r9, [rsp+2C0h+Handle]
0x1801243d2  mov     r8d, 20019h
0x1801243d8  lea     rcx, [rsp+2C0h+DestinationString]
0x1801243dd  call    LdrpOpenKey
0x1801243e2  test    eax, eax
0x1801243e4  js      loc_1801244D0
0x1801243ea  lea     rdx, aType_0; "Type"
0x1801243f1  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x1801243f6  call    RtlInitUnicodeString
0x1801243fb  mov     rcx, [rsp+2C0h+Handle]
0x180124400  lea     rax, [rsp+2C0h+var_25C]
0x180124405  lea     r9, [rsp+2C0h+var_290]
0x18012440a  mov     [rsp+2C0h+var_2A0], rax
0x18012440f  lea     r8, [rsp+2C0h+var_288]
0x180124414  mov     dword ptr [rsp+2C0h+var_288], 4
0x18012441c  lea     rdx, [rsp+2C0h+DestinationString]
0x180124421  mov     [rsp+2C0h+var_25C], 4
0x180124429  call    LdrpQueryValueKey
0x18012442e  test    eax, eax
0x180124430  js      loc_1801244D0
0x180124436  mov     r10d, [rsp+2C0h+var_290]
0x18012443b  mov     ecx, r10d
0x18012443e  call    ValidateRegistrLangType
0x180124443  test    eax, eax
0x180124445  js      loc_1801244D0
0x18012444b  and     r10d, 419Fh
0x180124452  mov     ecx, r10d
0x180124455  mov     [rsp+2C0h+var_290], r10d
0x18012445a  and     ecx, 7
0x18012445d  jz      short loc_1801244D0
0x18012445f  mov     eax, ecx
0x180124461  neg     eax
0x180124463  and     eax, ecx
0x180124465  cmp     eax, ecx
0x180124467  jnz     short loc_1801244D0
0x180124469  mov     ecx, r10d
0x18012446c  and     ecx, 180h
0x180124472  jz      short loc_18012447E
0x180124474  mov     eax, ecx
0x180124476  neg     eax
0x180124478  and     eax, ecx
0x18012447a  cmp     eax, ecx
0x18012447c  jz      short loc_18012448D
0x18012447e  btr     r10d, 8
0x180124483  bts     r10d, 7
0x180124488  mov     [rsp+2C0h+var_290], r10d
0x18012448d  mov     ecx, r10d
0x180124490  mov     edx, ecx
0x180124492  and     edx, 18h
0x180124495  jz      short loc_1801244D0
0x180124497  mov     eax, edx
0x180124499  neg     eax
0x18012449b  and     eax, edx
0x18012449d  cmp     eax, edx
0x18012449f  jnz     short loc_1801244D0
0x1801244a1  and     cl, 0Ch
0x1801244a4  cmp     cl, 8
0x1801244a7  jz      short loc_1801244D0
0x1801244a9  mov     rdx, [rsp+2C0h+Handle]
0x1801244ae  lea     rax, [rsp+2C0h+var_28C]
0x1801244b3  mov     r9d, r10d
0x1801244b6  mov     [rsp+2C0h+var_298], rax
0x1801244bb  lea     r8, [rbp+1C0h+SourceString]
0x1801244bf  mov     rcx, rsi
0x1801244c2  call    RtlpMuiRegAddLanguageByName
0x1801244c7  jmp     short loc_1801244D0
0x1801244c9  cmp     eax, 8000001Ah
0x1801244ce  jnz     short loc_1801244F1
0x1801244d0  mov     rcx, [rsp+2C0h+Handle]; Handle
0x1801244d5  test    rcx, rcx
0x1801244d8  jz      short loc_1801244E8
0x1801244da  call    NtClose
0x1801244df  mov     [rsp+2C0h+Handle], 0
0x1801244e8  inc     edi
0x1801244ea  jmp     loc_180124362
0x1801244ef  xor     ebx, ebx
0x1801244f1  mov     rcx, [rsp+2C0h+var_278]; Handle
0x1801244f6  test    rcx, rcx
0x1801244f9  jz      short loc_180124500
0x1801244fb  call    NtClose
0x180124500  mov     eax, ebx
0x180124502  mov     rcx, [rbp+1C0h+var_28]
0x180124509  xor     rcx, rsp; StackCookie
0x18012450c  call    __security_check_cookie
0x180124511  add     rsp, 2A8h
0x180124518  pop     rdi
0x180124519  pop     rsi
0x18012451a  pop     rbx
0x18012451b  pop     rbp
0x18012451c  retn
```
