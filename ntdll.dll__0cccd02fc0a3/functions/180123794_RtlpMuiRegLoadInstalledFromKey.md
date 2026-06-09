# _RtlpMuiRegLoadInstalledFromKey

- ea: `0x180123794`
- end: `0x180123a2e`
- name: `_RtlpMuiRegLoadInstalledFromKey`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1801205f0`

## callees

- `0x1800c0420`
- `0x1800d38d0`
- `0x1800d97d0`
- `0x180123794`
- `0x18012c830`
- `0x18014c5e0`
- `0x18014cf98`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e910`
- `0x180162000`

## string_xrefs

- `0x1801237c4`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\UILanguages`

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
0x180123794  push    rbp
0x180123796  push    rbx
0x180123797  push    rsi
0x180123798  push    rdi
0x180123799  lea     rbp, [rsp-1A8h]
0x1801237a1  sub     rsp, 2A8h
0x1801237a8  mov     rax, cs:__security_cookie
0x1801237af  xor     rax, rsp
0x1801237b2  mov     [rbp+1C0h+var_28], rax
0x1801237b9  mov     rsi, rcx
0x1801237bc  mov     [rsp+2C0h+var_260], 0
0x1801237c4  lea     rcx, aRegistryMachin_41; "\\Registry\\Machine\\System\\CurrentCon"...
0x1801237cb  mov     [rsp+2C0h+Handle], 0
0x1801237d4  or      eax, 0FFFFFFFFh
0x1801237d7  mov     [rsp+2C0h+DestinationString.Buffer], rcx
0x1801237dc  mov     [rsp+2C0h+var_290], 0
0x1801237e4  mov     [rsp+2C0h+var_28C], ax
0x1801237e9  mov     [rsp+2C0h+var_278], 0
0x1801237f2  mov     qword ptr [rsp+2C0h+DestinationString.Length], 0
0x1801237fb  call    wcslen
0x180123800  add     rax, rax
0x180123803  mov     [rsp+2C0h+var_258], 30h ; '0'
0x18012380c  cmp     rax, 0FFFEh
0x180123812  mov     [rbp+1C0h+var_240], 40h ; '@'
0x18012381a  mov     ecx, 0FFFCh
0x18012381f  lea     r8, [rsp+2C0h+var_258]
0x180123824  cmovnb  rax, rcx
0x180123828  xorps   xmm0, xmm0
0x18012382b  mov     [rsp+2C0h+DestinationString.Length], ax
0x180123830  lea     rcx, [rsp+2C0h+var_278]
0x180123835  add     ax, 2
0x180123839  mov     edx, 20019h
0x18012383e  mov     [rsp+2C0h+DestinationString.MaximumLength], ax
0x180123843  xor     eax, eax
0x180123845  mov     [rsp+2C0h+var_278], rax
0x18012384a  mov     [rsp+2C0h+var_250], rax
0x18012384f  lea     rax, [rsp+2C0h+DestinationString]
0x180123854  mov     [rsp+2C0h+var_248], rax
0x180123859  movdqu  [rbp+1C0h+var_238], xmm0
0x18012385e  call    NtOpenKey
0x180123863  mov     ebx, eax
0x180123865  test    eax, eax
0x180123867  jns     short loc_180123870
0x180123869  xor     eax, eax
0x18012386b  jmp     loc_180123A12
0x180123870  xor     edi, edi
0x180123872  cmp     ebx, 8000001Ah
0x180123878  jz      loc_1801239FF
0x18012387e  mov     rcx, [rsp+2C0h+var_278]
0x180123883  lea     rax, [rsp+2C0h+var_260]
0x180123888  mov     [rsp+2C0h+var_298], rax
0x18012388d  lea     r9, [rbp+1C0h+var_228]
0x180123891  xor     r8d, r8d
0x180123894  mov     dword ptr [rsp+2C0h+var_2A0], 200h
0x18012389c  mov     edx, edi
0x18012389e  call    NtEnumerateKey
0x1801238a3  mov     ebx, eax
0x1801238a5  test    eax, eax
0x1801238a7  js      loc_1801239D9
0x1801238ad  mov     ecx, [rbp+1C0h+var_21C]
0x1801238b0  lea     rax, [rcx+18h]
0x1801238b4  cmp     rax, 200h
0x1801238ba  ja      loc_1801239E0
0x1801238c0  shr     rcx, 1
0x1801238c3  lea     rdx, [rbp+1C0h+SourceString]; SourceString
0x1801238c7  xor     eax, eax
0x1801238c9  mov     [rbp+rcx*2+1C0h+SourceString], ax
0x1801238ce  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x1801238d3  call    RtlInitUnicodeString
0x1801238d8  mov     rdx, [rsp+2C0h+var_278]
0x1801238dd  lea     r9, [rsp+2C0h+Handle]
0x1801238e2  mov     r8d, 20019h
0x1801238e8  lea     rcx, [rsp+2C0h+DestinationString]
0x1801238ed  call    LdrpOpenKey
0x1801238f2  test    eax, eax
0x1801238f4  js      loc_1801239E0
0x1801238fa  lea     rdx, aType_0; "Type"
0x180123901  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x180123906  call    RtlInitUnicodeString
0x18012390b  mov     rcx, [rsp+2C0h+Handle]
0x180123910  lea     rax, [rsp+2C0h+var_25C]
0x180123915  lea     r9, [rsp+2C0h+var_290]
0x18012391a  mov     [rsp+2C0h+var_2A0], rax
0x18012391f  lea     r8, [rsp+2C0h+var_288]
0x180123924  mov     dword ptr [rsp+2C0h+var_288], 4
0x18012392c  lea     rdx, [rsp+2C0h+DestinationString]
0x180123931  mov     [rsp+2C0h+var_25C], 4
0x180123939  call    LdrpQueryValueKey
0x18012393e  test    eax, eax
0x180123940  js      loc_1801239E0
0x180123946  mov     r10d, [rsp+2C0h+var_290]
0x18012394b  mov     ecx, r10d
0x18012394e  call    ValidateRegistrLangType
0x180123953  test    eax, eax
0x180123955  js      loc_1801239E0
0x18012395b  and     r10d, 419Fh
0x180123962  mov     ecx, r10d
0x180123965  mov     [rsp+2C0h+var_290], r10d
0x18012396a  and     ecx, 7
0x18012396d  jz      short loc_1801239E0
0x18012396f  mov     eax, ecx
0x180123971  neg     eax
0x180123973  and     eax, ecx
0x180123975  cmp     eax, ecx
0x180123977  jnz     short loc_1801239E0
0x180123979  mov     ecx, r10d
0x18012397c  and     ecx, 180h
0x180123982  jz      short loc_18012398E
0x180123984  mov     eax, ecx
0x180123986  neg     eax
0x180123988  and     eax, ecx
0x18012398a  cmp     eax, ecx
0x18012398c  jz      short loc_18012399D
0x18012398e  btr     r10d, 8
0x180123993  bts     r10d, 7
0x180123998  mov     [rsp+2C0h+var_290], r10d
0x18012399d  mov     ecx, r10d
0x1801239a0  mov     edx, ecx
0x1801239a2  and     edx, 18h
0x1801239a5  jz      short loc_1801239E0
0x1801239a7  mov     eax, edx
0x1801239a9  neg     eax
0x1801239ab  and     eax, edx
0x1801239ad  cmp     eax, edx
0x1801239af  jnz     short loc_1801239E0
0x1801239b1  and     cl, 0Ch
0x1801239b4  cmp     cl, 8
0x1801239b7  jz      short loc_1801239E0
0x1801239b9  mov     rdx, [rsp+2C0h+Handle]
0x1801239be  lea     rax, [rsp+2C0h+var_28C]
0x1801239c3  mov     r9d, r10d
0x1801239c6  mov     [rsp+2C0h+var_298], rax
0x1801239cb  lea     r8, [rbp+1C0h+SourceString]
0x1801239cf  mov     rcx, rsi
0x1801239d2  call    RtlpMuiRegAddLanguageByName
0x1801239d7  jmp     short loc_1801239E0
0x1801239d9  cmp     eax, 8000001Ah
0x1801239de  jnz     short loc_180123A01
0x1801239e0  mov     rcx, [rsp+2C0h+Handle]; Handle
0x1801239e5  test    rcx, rcx
0x1801239e8  jz      short loc_1801239F8
0x1801239ea  call    NtClose
0x1801239ef  mov     [rsp+2C0h+Handle], 0
0x1801239f8  inc     edi
0x1801239fa  jmp     loc_180123872
0x1801239ff  xor     ebx, ebx
0x180123a01  mov     rcx, [rsp+2C0h+var_278]; Handle
0x180123a06  test    rcx, rcx
0x180123a09  jz      short loc_180123A10
0x180123a0b  call    NtClose
0x180123a10  mov     eax, ebx
0x180123a12  mov     rcx, [rbp+1C0h+var_28]
0x180123a19  xor     rcx, rsp; StackCookie
0x180123a1c  call    __security_check_cookie
0x180123a21  add     rsp, 2A8h
0x180123a28  pop     rdi
0x180123a29  pop     rsi
0x180123a2a  pop     rbx
0x180123a2b  pop     rbp
0x180123a2c  retn
```
