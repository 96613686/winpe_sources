# ScriptRecordDigitSubstitution

- ea: `0x1800169c0`
- end: `0x180016d63`
- name: `ScriptRecordDigitSubstitution`
- size: `931`
- prototype: `HRESULT __stdcall(LCID Locale, SCRIPT_DIGITSUBSTITUTE *psds)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011050`
- `0x180013954`
- `0x180015aa0`
- `0x180015dc0`
- `0x180017010`

## callees

- `0x180009ea0`
- `0x180016750`
- `0x1800169c0`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180016be6`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180016be6`
- `api-ms-win-core-localization-l1-2-0!ConvertDefaultLocale` at `0x180016a23`
- `api-ms-win-core-localization-l1-2-0!ConvertDefaultLocale` at `0x180016a23`
- `api-ms-win-core-localization-l1-2-0!IsValidLocale` at `0x180016a36`
- `api-ms-win-core-localization-l1-2-0!IsValidLocale` at `0x180016a36`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180016a66`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180016aae`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180016a66`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180016aae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180016c5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180016c5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180016c20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180016c20`

## pseudocode

```c
HRESULT __stdcall ScriptRecordDigitSubstitution(LCID Locale, SCRIPT_DIGITSUBSTITUTE *psds)
{
  LCID v4; // edi
  HRESULT v5; // ebx
  __int16 v7; // ax
  DWORD cbData; // [rsp+30h] [rbp-50h] BYREF
  DWORD Type; // [rsp+34h] [rbp-4Ch] BYREF
  int v10; // [rsp+38h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  WCHAR LCData; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 v13; // [rsp+4Ah] [rbp-36h]

  cbData = 0;
  Type = 0;
  hKey = 0;
  if ( psds )
  {
    v10 = UspAcquireTempAlloc(Locale);
    *(_QWORD *)psds = 589833;
    psds->dwReserved = 0;
    v4 = ConvertDefaultLocale(Locale);
    if ( !IsValidLocale(v4, 1u) )
    {
      v5 = -2147024809;
LABEL_22:
      CTempMemory::~CTempMemory((CTempMemory *)&v10);
      return v5;
    }
    *((_BYTE *)psds + 4) = 0;
    *((_WORD *)psds + 1) = v4 & 0x3FF;
    cbData = GetLocaleInfoW(v4, 0x1014u, &LCData, 20);
    if ( !cbData && !RegOpenKeyExA(HKEY_CURRENT_USER, "Control Panel\\International", 0, 0x20019u, &hKey) )
    {
      LCData = 0;
      cbData = 20;
      if ( RegQueryValueExA(hKey, "NumShape", 0, &Type, (LPBYTE)&LCData, &cbData) )
        cbData = 0;
      RegCloseKey(hKey);
    }
    if ( cbData )
    {
      if ( LCData == 49 )
      {
        *((_BYTE *)psds + 4) = 1;
      }
      else if ( LCData == 50 )
      {
        *((_BYTE *)psds + 4) = 2;
      }
    }
    if ( !*((_BYTE *)psds + 4) && *((_WORD *)psds + 1) != 1 && *((_WORD *)psds + 1) != 41 )
      *((_BYTE *)psds + 4) = 1;
    cbData = GetLocaleInfoW(v4, 0x13u, &LCData, 20);
    if ( cbData )
    {
      if ( v13 <= 0xC67u )
      {
        if ( v13 == 3175 )
        {
          *(_WORD *)psds = 74;
          goto LABEL_20;
        }
        if ( v13 != 1633 )
        {
          if ( v13 != 1777 )
          {
            switch ( v13 )
            {
              case 0x967u:
                *(_WORD *)psds = 57;
                break;
              case 0x9E7u:
                *(_WORD *)psds = 69;
                break;
              case 0xA67u:
                *(_WORD *)psds = 70;
                break;
              case 0xAE7u:
                *(_WORD *)psds = 71;
                break;
              case 0xB67u:
                *(_WORD *)psds = 72;
                break;
              case 0xBE7u:
                *(_WORD *)psds = 73;
                break;
            }
            goto LABEL_20;
          }
          v7 = 32;
          if ( *((_WORD *)psds + 1) != 32 )
            v7 = 41;
LABEL_52:
          *(_WORD *)psds = v7;
          goto LABEL_20;
        }
        goto LABEL_35;
      }
      switch ( v13 )
      {
        case 0xCE7u:
          *(_WORD *)psds = 75;
          goto LABEL_20;
        case 0xD67u:
          *(_WORD *)psds = 76;
          goto LABEL_20;
        case 0xE51u:
          *(_WORD *)psds = 30;
          goto LABEL_20;
        case 0xED1u:
          *(_WORD *)psds = 84;
          goto LABEL_20;
      }
      v7 = 80;
      switch ( v13 )
      {
        case 0xF21u:
          *(_WORD *)psds = 81;
          break;
        case 0x1041u:
          *(_WORD *)psds = 85;
          break;
        case 0x17E1u:
          *(_WORD *)psds = 83;
          break;
        case 0x1811u:
          goto LABEL_52;
      }
    }
    else if ( GetACP() == 1256 )
    {
LABEL_35:
      *(_WORD *)psds = 1;
    }
LABEL_20:
    if ( *((_BYTE *)psds + 4) == 2 && *(_WORD *)psds == 9 )
      *((_BYTE *)psds + 4) = 1;
    v5 = 0;
    goto LABEL_22;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x1800169c0  mov     [rsp-18h+arg_10], rbx
0x1800169c5  mov     [rsp-18h+arg_18], rdi
0x1800169ca  push    rbp
0x1800169cb  push    r14
0x1800169cd  push    r15
0x1800169cf  mov     rbp, rsp
0x1800169d2  sub     rsp, 80h
0x1800169d9  mov     rax, cs:__security_cookie
0x1800169e0  xor     rax, rsp
0x1800169e3  mov     [rbp+var_10], rax
0x1800169e7  mov     [rbp+cbData], 0
0x1800169ee  mov     rbx, rdx
0x1800169f1  mov     [rbp+Type], 0
0x1800169f8  mov     edi, ecx
0x1800169fa  mov     [rbp+hKey], 0
0x180016a02  test    rdx, rdx
0x180016a05  jz      loc_180016BD2
0x180016a0b  call    ?UspAcquireTempAlloc@@YAHK@Z; UspAcquireTempAlloc(ulong)
0x180016a10  mov     [rbp+var_48], eax
0x180016a13  mov     ecx, edi; Locale
0x180016a15  mov     qword ptr [rbx], 90009h
0x180016a1c  mov     dword ptr [rbx+8], 0
0x180016a23  call    cs:__imp_ConvertDefaultLocale
0x180016a29  mov     r14d, 1
0x180016a2f  mov     ecx, eax; Locale
0x180016a31  mov     edx, r14d; dwFlags
0x180016a34  mov     edi, eax
0x180016a36  call    cs:__imp_IsValidLocale
0x180016a3c  test    eax, eax
0x180016a3e  jz      loc_180016BDC
0x180016a44  mov     ecx, 3FFh
0x180016a49  mov     byte ptr [rbx+4], 0
0x180016a4d  movzx   eax, di
0x180016a50  lea     r9d, [r14+13h]; cchData
0x180016a54  and     ax, cx
0x180016a57  lea     r8, [rbp+LCData]; lpLCData
0x180016a5b  mov     ecx, edi; Locale
0x180016a5d  mov     [rbx+2], ax
0x180016a61  mov     edx, 1014h; LCType
0x180016a66  call    cs:__imp_GetLocaleInfoW
0x180016a6c  mov     [rbp+cbData], eax
0x180016a6f  test    eax, eax
0x180016a71  jz      loc_180016C00
0x180016a77  cmp     [rbp+cbData], 0
0x180016a7b  jbe     short loc_180016A8E
0x180016a7d  movzx   ecx, [rbp+LCData]
0x180016a81  sub     ecx, 31h ; '1'
0x180016a84  jnz     loc_180016C7D
0x180016a8a  mov     [rbx+4], r14b
0x180016a8e  cmp     byte ptr [rbx+4], 0
0x180016a92  mov     r15d, 29h ; ')'
0x180016a98  jz      loc_180016C8F
0x180016a9e  mov     r9d, 14h; cchData
0x180016aa4  lea     r8, [rbp+LCData]; lpLCData
0x180016aa8  mov     ecx, edi; Locale
0x180016aaa  lea     edx, [r9-1]; LCType
0x180016aae  call    cs:__imp_GetLocaleInfoW
0x180016ab4  mov     [rbp+cbData], eax
0x180016ab7  test    eax, eax
0x180016ab9  jz      loc_180016BE6
0x180016abf  movzx   ecx, [rbp+var_36]
0x180016ac3  mov     eax, 0C67h
0x180016ac8  cmp     ecx, eax
0x180016aca  ja      loc_180016B72
0x180016ad0  jz      loc_180016D00
0x180016ad6  cmp     ecx, 661h
0x180016adc  jz      loc_180016BF7
0x180016ae2  cmp     ecx, 6F1h
0x180016ae8  jz      loc_180016CEA
0x180016aee  cmp     ecx, 967h
0x180016af4  jz      loc_180016CE0
0x180016afa  cmp     ecx, 9E7h
0x180016b00  jz      loc_180016CD6
0x180016b06  cmp     ecx, 0A67h
0x180016b0c  jz      loc_180016CCC
0x180016b12  cmp     ecx, 0AE7h
0x180016b18  jz      loc_180016CC2
0x180016b1e  cmp     ecx, 0B67h
0x180016b24  jz      loc_180016CB8
0x180016b2a  cmp     ecx, 0BE7h
0x180016b30  jz      loc_180016CAE
0x180016b36  cmp     byte ptr [rbx+4], 2
0x180016b3a  jz      loc_180016D50
0x180016b40  xor     ebx, ebx
0x180016b42  lea     rcx, [rbp+var_48]; this
0x180016b46  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x180016b4b  mov     eax, ebx
0x180016b4d  mov     rcx, [rbp+var_10]
0x180016b51  xor     rcx, rsp; StackCookie
0x180016b54  call    __security_check_cookie
0x180016b59  lea     r11, [rsp+80h+var_s0]
0x180016b61  mov     rbx, [r11+30h]
0x180016b65  mov     rdi, [r11+38h]
0x180016b69  mov     rsp, r11
0x180016b6c  pop     r15
0x180016b6e  pop     r14
0x180016b70  pop     rbp
0x180016b71  retn
0x180016b72  sub     ecx, 0CE7h
0x180016b78  jz      loc_180016D46
0x180016b7e  mov     eax, 80h
0x180016b83  sub     ecx, eax
0x180016b85  jz      loc_180016D3C
0x180016b8b  sub     ecx, 0EAh
0x180016b91  jz      loc_180016D32
0x180016b97  sub     ecx, eax
0x180016b99  jz      loc_180016D28
0x180016b9f  mov     eax, 50h ; 'P'
0x180016ba4  sub     ecx, eax
0x180016ba6  jz      loc_180016D1E
0x180016bac  sub     ecx, 120h
0x180016bb2  jz      loc_180016D14
0x180016bb8  sub     ecx, 7A0h
0x180016bbe  jz      loc_180016D0A
0x180016bc4  cmp     ecx, 30h ; '0'
0x180016bc7  jnz     loc_180016B36
0x180016bcd  jmp     loc_180016CF8
0x180016bd2  mov     eax, 80070057h
0x180016bd7  jmp     loc_180016B4D
0x180016bdc  mov     ebx, 80070057h
0x180016be1  jmp     loc_180016B42
0x180016be6  call    cs:__imp_GetACP
0x180016bec  cmp     eax, 4E8h
0x180016bf1  jnz     loc_180016B36
0x180016bf7  mov     [rbx], r14w
0x180016bfb  jmp     loc_180016B36
0x180016c00  lea     rax, [rbp+hKey]
0x180016c04  mov     r9d, 20019h; samDesired
0x180016c0a  xor     r8d, r8d; ulOptions
0x180016c0d  mov     [rsp+80h+phkResult], rax; phkResult
0x180016c12  lea     rdx, SubKey; "Control Panel\\International"
0x180016c19  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180016c20  call    cs:__imp_RegOpenKeyExA
0x180016c26  test    eax, eax
0x180016c28  jnz     loc_180016A77
0x180016c2e  mov     rcx, [rbp+hKey]; hKey
0x180016c32  lea     r9, [rbp+Type]; lpType
0x180016c36  mov     [rbp+LCData], ax
0x180016c3a  lea     rdx, ValueName; "NumShape"
0x180016c41  lea     rax, [rbp+cbData]
0x180016c45  mov     [rbp+cbData], 14h
0x180016c4c  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180016c51  xor     r8d, r8d; lpReserved
0x180016c54  lea     rax, [rbp+LCData]
0x180016c58  mov     [rsp+80h+phkResult], rax; lpData
0x180016c5d  call    cs:__imp_RegQueryValueExA
0x180016c63  test    eax, eax
0x180016c65  jz      short loc_180016C6E
0x180016c67  mov     [rbp+cbData], 0
0x180016c6e  mov     rcx, [rbp+hKey]; hKey
0x180016c72  call    cs:__imp_RegCloseKey
0x180016c78  jmp     loc_180016A77
0x180016c7d  cmp     ecx, r14d
0x180016c80  jnz     loc_180016A8E
0x180016c86  mov     byte ptr [rbx+4], 2
0x180016c8a  jmp     loc_180016A8E
0x180016c8f  cmp     [rbx+2], r14w
0x180016c94  jz      loc_180016A9E
0x180016c9a  cmp     [rbx+2], r15w
0x180016c9f  jz      loc_180016A9E
0x180016ca5  mov     [rbx+4], r14b
0x180016ca9  jmp     loc_180016A9E
0x180016cae  mov     word ptr [rbx], 49h ; 'I'
0x180016cb3  jmp     loc_180016B36
0x180016cb8  mov     word ptr [rbx], 48h ; 'H'
0x180016cbd  jmp     loc_180016B36
0x180016cc2  mov     word ptr [rbx], 47h ; 'G'
0x180016cc7  jmp     loc_180016B36
0x180016ccc  mov     word ptr [rbx], 46h ; 'F'
0x180016cd1  jmp     loc_180016B36
0x180016cd6  mov     word ptr [rbx], 45h ; 'E'
0x180016cdb  jmp     loc_180016B36
0x180016ce0  mov     word ptr [rbx], 39h ; '9'
0x180016ce5  jmp     loc_180016B36
0x180016cea  mov     eax, 20h ; ' '
0x180016cef  cmp     [rbx+2], ax
0x180016cf3  cmovnz  ax, r15w
0x180016cf8  mov     [rbx], ax
0x180016cfb  jmp     loc_180016B36
0x180016d00  mov     word ptr [rbx], 4Ah ; 'J'
0x180016d05  jmp     loc_180016B36
0x180016d0a  mov     word ptr [rbx], 53h ; 'S'
0x180016d0f  jmp     loc_180016B36
0x180016d14  mov     word ptr [rbx], 55h ; 'U'
0x180016d19  jmp     loc_180016B36
0x180016d1e  mov     word ptr [rbx], 51h ; 'Q'
0x180016d23  jmp     loc_180016B36
0x180016d28  mov     word ptr [rbx], 54h ; 'T'
0x180016d2d  jmp     loc_180016B36
0x180016d32  mov     word ptr [rbx], 1Eh
0x180016d37  jmp     loc_180016B36
0x180016d3c  mov     word ptr [rbx], 4Ch ; 'L'
0x180016d41  jmp     loc_180016B36
0x180016d46  mov     word ptr [rbx], 4Bh ; 'K'
0x180016d4b  jmp     loc_180016B36
0x180016d50  cmp     word ptr [rbx], 9
0x180016d54  jnz     loc_180016B40
0x180016d5a  mov     [rbx+4], r14b
0x180016d5e  jmp     loc_180016B40
```
