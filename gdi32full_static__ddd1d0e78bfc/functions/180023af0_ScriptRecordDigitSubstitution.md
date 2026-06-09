# ScriptRecordDigitSubstitution

- ea: `0x180023af0`
- end: `0x180023ec4`
- name: `ScriptRecordDigitSubstitution`
- size: `980`
- prototype: `HRESULT __stdcall(LCID Locale, SCRIPT_DIGITSUBSTITUTE *psds)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000dda0`
- `0x180019840`
- `0x180020880`
- `0x180021f80`
- `0x180023a20`

## callees

- `0x18000d200`
- `0x180022950`
- `0x180023af0`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180023d2f`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180023d2f`
- `api-ms-win-core-localization-l1-2-0!ConvertDefaultLocale` at `0x180023b53`
- `api-ms-win-core-localization-l1-2-0!ConvertDefaultLocale` at `0x180023b53`
- `api-ms-win-core-localization-l1-2-0!IsValidLocale` at `0x180023b6c`
- `api-ms-win-core-localization-l1-2-0!IsValidLocale` at `0x180023b6c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180023ba2`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180023bf0`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180023ba2`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180023bf0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180023db2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180023db2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023dcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023dcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180023d6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180023d6f`

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
0x180023af0  mov     [rsp-18h+arg_10], rbx
0x180023af5  mov     [rsp-18h+arg_18], rdi
0x180023afa  push    rbp
0x180023afb  push    r14
0x180023afd  push    r15
0x180023aff  mov     rbp, rsp
0x180023b02  sub     rsp, 80h
0x180023b09  mov     rax, cs:__security_cookie
0x180023b10  xor     rax, rsp
0x180023b13  mov     [rbp+var_10], rax
0x180023b17  mov     [rbp+cbData], 0
0x180023b1e  mov     rbx, rdx
0x180023b21  mov     [rbp+Type], 0
0x180023b28  mov     edi, ecx
0x180023b2a  mov     [rbp+hKey], 0
0x180023b32  test    rdx, rdx
0x180023b35  jz      loc_180023D1B
0x180023b3b  call    ?UspAcquireTempAlloc@@YAHK@Z; UspAcquireTempAlloc(ulong)
0x180023b40  mov     [rbp+var_48], eax
0x180023b43  mov     ecx, edi; Locale
0x180023b45  mov     qword ptr [rbx], 90009h
0x180023b4c  mov     dword ptr [rbx+8], 0
0x180023b53  call    cs:__imp_ConvertDefaultLocale
0x180023b5a  nop     dword ptr [rax+rax+00h]
0x180023b5f  mov     r14d, 1
0x180023b65  mov     ecx, eax; Locale
0x180023b67  mov     edx, r14d; dwFlags
0x180023b6a  mov     edi, eax
0x180023b6c  call    cs:__imp_IsValidLocale
0x180023b73  nop     dword ptr [rax+rax+00h]
0x180023b78  test    eax, eax
0x180023b7a  jz      loc_180023D25
0x180023b80  mov     ecx, 3FFh
0x180023b85  mov     byte ptr [rbx+4], 0
0x180023b89  movzx   eax, di
0x180023b8c  lea     r9d, [r14+13h]; cchData
0x180023b90  and     ax, cx
0x180023b93  lea     r8, [rbp+LCData]; lpLCData
0x180023b97  mov     ecx, edi; Locale
0x180023b99  mov     [rbx+2], ax
0x180023b9d  mov     edx, 1014h; LCType
0x180023ba2  call    cs:__imp_GetLocaleInfoW
0x180023ba9  nop     dword ptr [rax+rax+00h]
0x180023bae  mov     [rbp+cbData], eax
0x180023bb1  test    eax, eax
0x180023bb3  jz      loc_180023D4F
0x180023bb9  cmp     [rbp+cbData], 0
0x180023bbd  jbe     short loc_180023BD0
0x180023bbf  movzx   ecx, [rbp+LCData]
0x180023bc3  sub     ecx, 31h ; '1'
0x180023bc6  jnz     loc_180023DDE
0x180023bcc  mov     [rbx+4], r14b
0x180023bd0  cmp     byte ptr [rbx+4], 0
0x180023bd4  mov     r15d, 29h ; ')'
0x180023bda  jz      loc_180023DF0
0x180023be0  mov     r9d, 14h; cchData
0x180023be6  lea     r8, [rbp+LCData]; lpLCData
0x180023bea  mov     ecx, edi; Locale
0x180023bec  lea     edx, [r9-1]; LCType
0x180023bf0  call    cs:__imp_GetLocaleInfoW
0x180023bf7  nop     dword ptr [rax+rax+00h]
0x180023bfc  mov     [rbp+cbData], eax
0x180023bff  test    eax, eax
0x180023c01  jz      loc_180023D2F
0x180023c07  movzx   ecx, [rbp+var_36]
0x180023c0b  mov     eax, 0C67h
0x180023c10  cmp     ecx, eax
0x180023c12  ja      loc_180023CBB
0x180023c18  jz      loc_180023E61
0x180023c1e  cmp     ecx, 661h
0x180023c24  jz      loc_180023D46
0x180023c2a  cmp     ecx, 6F1h
0x180023c30  jz      loc_180023E4B
0x180023c36  cmp     ecx, 967h
0x180023c3c  jz      loc_180023E41
0x180023c42  cmp     ecx, 9E7h
0x180023c48  jz      loc_180023E37
0x180023c4e  cmp     ecx, 0A67h
0x180023c54  jz      loc_180023E2D
0x180023c5a  cmp     ecx, 0AE7h
0x180023c60  jz      loc_180023E23
0x180023c66  cmp     ecx, 0B67h
0x180023c6c  jz      loc_180023E19
0x180023c72  cmp     ecx, 0BE7h
0x180023c78  jz      loc_180023E0F
0x180023c7e  cmp     byte ptr [rbx+4], 2
0x180023c82  jz      loc_180023EB1
0x180023c88  xor     ebx, ebx
0x180023c8a  lea     rcx, [rbp+var_48]; this
0x180023c8e  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x180023c93  mov     eax, ebx
0x180023c95  mov     rcx, [rbp+var_10]
0x180023c99  xor     rcx, rsp; StackCookie
0x180023c9c  call    __security_check_cookie
0x180023ca1  lea     r11, [rsp+80h+var_s0]
0x180023ca9  mov     rbx, [r11+30h]
0x180023cad  mov     rdi, [r11+38h]
0x180023cb1  mov     rsp, r11
0x180023cb4  pop     r15
0x180023cb6  pop     r14
0x180023cb8  pop     rbp
0x180023cb9  retn
0x180023cbb  sub     ecx, 0CE7h
0x180023cc1  jz      loc_180023EA7
0x180023cc7  mov     eax, 80h
0x180023ccc  sub     ecx, eax
0x180023cce  jz      loc_180023E9D
0x180023cd4  sub     ecx, 0EAh
0x180023cda  jz      loc_180023E93
0x180023ce0  sub     ecx, eax
0x180023ce2  jz      loc_180023E89
0x180023ce8  mov     eax, 50h ; 'P'
0x180023ced  sub     ecx, eax
0x180023cef  jz      loc_180023E7F
0x180023cf5  sub     ecx, 120h
0x180023cfb  jz      loc_180023E75
0x180023d01  sub     ecx, 7A0h
0x180023d07  jz      loc_180023E6B
0x180023d0d  cmp     ecx, 30h ; '0'
0x180023d10  jnz     loc_180023C7E
0x180023d16  jmp     loc_180023E59
0x180023d1b  mov     eax, 80070057h
0x180023d20  jmp     loc_180023C95
0x180023d25  mov     ebx, 80070057h
0x180023d2a  jmp     loc_180023C8A
0x180023d2f  call    cs:__imp_GetACP
0x180023d36  nop     dword ptr [rax+rax+00h]
0x180023d3b  cmp     eax, 4E8h
0x180023d40  jnz     loc_180023C7E
0x180023d46  mov     [rbx], r14w
0x180023d4a  jmp     loc_180023C7E
0x180023d4f  lea     rax, [rbp+hKey]
0x180023d53  mov     r9d, 20019h; samDesired
0x180023d59  xor     r8d, r8d; ulOptions
0x180023d5c  mov     [rsp+80h+phkResult], rax; phkResult
0x180023d61  lea     rdx, SubKey; "Control Panel\\International"
0x180023d68  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180023d6f  call    cs:__imp_RegOpenKeyExA
0x180023d76  nop     dword ptr [rax+rax+00h]
0x180023d7b  test    eax, eax
0x180023d7d  jnz     loc_180023BB9
0x180023d83  mov     rcx, [rbp+hKey]; hKey
0x180023d87  lea     r9, [rbp+Type]; lpType
0x180023d8b  mov     [rbp+LCData], ax
0x180023d8f  lea     rdx, ValueName; "NumShape"
0x180023d96  lea     rax, [rbp+cbData]
0x180023d9a  mov     [rbp+cbData], 14h
0x180023da1  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180023da6  xor     r8d, r8d; lpReserved
0x180023da9  lea     rax, [rbp+LCData]
0x180023dad  mov     [rsp+80h+phkResult], rax; lpData
0x180023db2  call    cs:__imp_RegQueryValueExA
0x180023db9  nop     dword ptr [rax+rax+00h]
0x180023dbe  test    eax, eax
0x180023dc0  jz      short loc_180023DC9
0x180023dc2  mov     [rbp+cbData], 0
0x180023dc9  mov     rcx, [rbp+hKey]; hKey
0x180023dcd  call    cs:__imp_RegCloseKey
0x180023dd4  nop     dword ptr [rax+rax+00h]
0x180023dd9  jmp     loc_180023BB9
0x180023dde  cmp     ecx, r14d
0x180023de1  jnz     loc_180023BD0
0x180023de7  mov     byte ptr [rbx+4], 2
0x180023deb  jmp     loc_180023BD0
0x180023df0  cmp     [rbx+2], r14w
0x180023df5  jz      loc_180023BE0
0x180023dfb  cmp     [rbx+2], r15w
0x180023e00  jz      loc_180023BE0
0x180023e06  mov     [rbx+4], r14b
0x180023e0a  jmp     loc_180023BE0
0x180023e0f  mov     word ptr [rbx], 49h ; 'I'
0x180023e14  jmp     loc_180023C7E
0x180023e19  mov     word ptr [rbx], 48h ; 'H'
0x180023e1e  jmp     loc_180023C7E
0x180023e23  mov     word ptr [rbx], 47h ; 'G'
0x180023e28  jmp     loc_180023C7E
0x180023e2d  mov     word ptr [rbx], 46h ; 'F'
0x180023e32  jmp     loc_180023C7E
0x180023e37  mov     word ptr [rbx], 45h ; 'E'
0x180023e3c  jmp     loc_180023C7E
0x180023e41  mov     word ptr [rbx], 39h ; '9'
0x180023e46  jmp     loc_180023C7E
0x180023e4b  mov     eax, 20h ; ' '
0x180023e50  cmp     [rbx+2], ax
0x180023e54  cmovnz  ax, r15w
0x180023e59  mov     [rbx], ax
0x180023e5c  jmp     loc_180023C7E
0x180023e61  mov     word ptr [rbx], 4Ah ; 'J'
0x180023e66  jmp     loc_180023C7E
0x180023e6b  mov     word ptr [rbx], 53h ; 'S'
0x180023e70  jmp     loc_180023C7E
0x180023e75  mov     word ptr [rbx], 55h ; 'U'
0x180023e7a  jmp     loc_180023C7E
0x180023e7f  mov     word ptr [rbx], 51h ; 'Q'
0x180023e84  jmp     loc_180023C7E
0x180023e89  mov     word ptr [rbx], 54h ; 'T'
0x180023e8e  jmp     loc_180023C7E
0x180023e93  mov     word ptr [rbx], 1Eh
0x180023e98  jmp     loc_180023C7E
0x180023e9d  mov     word ptr [rbx], 4Ch ; 'L'
0x180023ea2  jmp     loc_180023C7E
0x180023ea7  mov     word ptr [rbx], 4Bh ; 'K'
0x180023eac  jmp     loc_180023C7E
0x180023eb1  cmp     word ptr [rbx], 9
0x180023eb5  jnz     loc_180023C88
0x180023ebb  mov     [rbx+4], r14b
0x180023ebf  jmp     loc_180023C88
```
