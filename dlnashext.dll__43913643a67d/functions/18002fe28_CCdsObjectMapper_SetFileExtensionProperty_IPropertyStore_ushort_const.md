# CCdsObjectMapper::_SetFileExtensionProperty(IPropertyStore *,ushort const *)

- ea: `0x18002fe28`
- end: `0x180030029`
- name: `?_SetFileExtensionProperty@CCdsObjectMapper@@AEAAJPEAUIPropertyStore@@PEBG@Z`
- size: `513`
- prototype: `int(CCdsObjectMapper *__hidden this, struct IPropertyStore *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002cfb4`

## callees

- `0x18000bca4`
- `0x180011930`
- `0x1800125c4`
- `0x1800198d4`
- `0x18002fe28`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030011`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002fea8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002fea8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ffab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ffab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ff57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ff57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030003`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030003`

## string_xrefs

- `0x18002ffe0`: `Extension`

## pseudocode

```c
__int64 __fastcall CCdsObjectMapper::_SetFileExtensionProperty(
        CCdsObjectMapper *this,
        struct IPropertyStore *a2,
        const unsigned __int16 *a3)
{
  unsigned int i; // ebx
  signed int v6; // eax
  bool v7; // sf
  int v8; // ebx
  __int64 result; // rax
  signed int LastError; // eax
  bool v11; // sf
  signed int v12; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v15[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 pvData[256]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  memset_0(pvData, 0, sizeof(pvData));
  pcbData = 512;
  for ( i = 0; i < 0x14; ++i )
  {
    if ( CompareStringOrdinal(a3, -1, off_180038850[2 * i], -1, 1) == 2 )
    {
      v6 = StringCchCopyW(pvData, 0x100u, off_180038850[2 * i + 1]);
LABEL_6:
      v7 = v6 < 0;
      goto LABEL_7;
    }
  }
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"MIME\\Database\\Content Type", 0, 1u, &hKey) )
  {
    LastError = GetLastError();
    v11 = LastError < 0;
    if ( LastError > 0 )
      v11 = 1;
    if ( v11 )
      goto LABEL_8;
  }
  if ( !RegGetValueW(hKey, a3, L"Extension", 2u, 0, pvData, &pcbData) )
    goto LABEL_13;
  v12 = GetLastError();
  v7 = v12 < 0;
  if ( v12 > 0 )
  {
    v6 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_6;
  }
LABEL_7:
  if ( !v7 )
    goto LABEL_13;
LABEL_8:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_28f76f838e153eeeda4709e76ebe7f13_Traceguids, a3);
  }
  pvData[0] = 0;
LABEL_13:
  v15[2] = 0;
  v15[0] = 31;
  v15[1] = pvData;
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, _QWORD *))a2->lpVtbl->SetValue)(
         a2,
         &PKEY_FileExtension,
         v15);
  if ( hKey )
    RegCloseKey(hKey);
  result = 0;
  if ( v8 >= 0 )
    return (unsigned int)v8;
  return result;
}

```

## disassembly

```asm
0x18002fe28  mov     [rsp-8+arg_0], rbx
0x18002fe2d  push    rbp
0x18002fe2e  push    rsi
0x18002fe2f  push    rdi
0x18002fe30  push    r12
0x18002fe32  push    r14
0x18002fe34  lea     rbp, [rsp-180h]
0x18002fe3c  sub     rsp, 280h
0x18002fe43  mov     rax, cs:__security_cookie
0x18002fe4a  xor     rax, rsp
0x18002fe4d  mov     [rbp+1A0h+var_30], rax
0x18002fe54  mov     rsi, r8
0x18002fe57  mov     [rsp+2A0h+hKey], 0
0x18002fe60  mov     r14, rdx
0x18002fe63  lea     rcx, [rsp+2A0h+var_230]; void *
0x18002fe68  mov     ebx, 200h
0x18002fe6d  xor     edx, edx; Val
0x18002fe6f  mov     r8d, ebx; Size
0x18002fe72  call    memset_0
0x18002fe77  mov     [rsp+2A0h+var_260], ebx
0x18002fe7b  lea     r12, off_180038850; "audio/3g2"
0x18002fe82  xor     ebx, ebx
0x18002fe84  cmp     ebx, 14h
0x18002fe87  jnb     loc_18002FF8A
0x18002fe8d  or      r9d, 0FFFFFFFFh; cchCount2
0x18002fe91  mov     edi, ebx
0x18002fe93  add     rdi, rdi
0x18002fe96  mov     [rsp+2A0h+bIgnoreCase], 1; bIgnoreCase
0x18002fe9e  or      edx, r9d; cchCount1
0x18002fea1  mov     rcx, rsi; lpString1
0x18002fea4  mov     r8, [r12+rdi*8]; lpString2
0x18002fea8  call    cs:__imp_CompareStringOrdinal
0x18002feae  cmp     eax, 2
0x18002feb1  jz      short loc_18002FEB7
0x18002feb3  inc     ebx
0x18002feb5  jmp     short loc_18002FE84
0x18002feb7  mov     r8, [r12+rdi*8+8]; unsigned __int16 *
0x18002febc  lea     rcx, [rsp+2A0h+var_230]; unsigned __int16 *
0x18002fec1  mov     edx, 100h; unsigned __int64
0x18002fec6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fecb  test    eax, eax
0x18002fecd  jns     short loc_18002FF0D
0x18002fecf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fed6  lea     rax, WPP_GLOBAL_Control
0x18002fedd  cmp     rcx, rax
0x18002fee0  jz      short loc_18002FF06
0x18002fee2  test    byte ptr [rcx+1Ch], 4
0x18002fee6  jz      short loc_18002FF06
0x18002fee8  cmp     byte ptr [rcx+19h], 4
0x18002feec  jb      short loc_18002FF06
0x18002feee  mov     rcx, [rcx+10h]
0x18002fef2  lea     r8, WPP_28f76f838e153eeeda4709e76ebe7f13_Traceguids
0x18002fef9  mov     edx, 0Fh
0x18002fefe  mov     r9, rsi
0x18002ff01  call    WPP_SF_S
0x18002ff06  xor     eax, eax
0x18002ff08  mov     [rsp+2A0h+var_230], ax
0x18002ff0d  xor     eax, eax
0x18002ff0f  lea     r8, [rsp+2A0h+var_250]
0x18002ff14  mov     [rsp+2A0h+var_240], rax
0x18002ff19  lea     rdx, PKEY_FileExtension
0x18002ff20  xorps   xmm0, xmm0
0x18002ff23  mov     eax, 1Fh
0x18002ff28  movups  [rsp+2A0h+var_250], xmm0
0x18002ff2d  mov     word ptr [rsp+2A0h+var_250], ax
0x18002ff32  mov     rcx, r14
0x18002ff35  lea     rax, [rsp+2A0h+var_230]
0x18002ff3a  mov     qword ptr [rsp+2A0h+var_250+8], rax
0x18002ff3f  mov     rax, [r14]
0x18002ff42  mov     rax, [rax+30h]
0x18002ff46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff4b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18002ff50  mov     ebx, eax
0x18002ff52  test    rcx, rcx
0x18002ff55  jz      short loc_18002FF5D
0x18002ff57  call    cs:__imp_RegCloseKey
0x18002ff5d  xor     eax, eax
0x18002ff5f  test    ebx, ebx
0x18002ff61  cmovns  eax, ebx
0x18002ff64  mov     rcx, [rbp+1A0h+var_30]
0x18002ff6b  xor     rcx, rsp; StackCookie
0x18002ff6e  call    __security_check_cookie
0x18002ff73  mov     rbx, [rsp+2A0h+arg_0]
0x18002ff7b  add     rsp, 280h
0x18002ff82  pop     r14
0x18002ff84  pop     r12
0x18002ff86  pop     rdi
0x18002ff87  pop     rsi
0x18002ff88  pop     rbp
0x18002ff89  retn
0x18002ff8a  lea     rax, [rsp+2A0h+hKey]
0x18002ff8f  mov     r9d, 1; samDesired
0x18002ff95  xor     r8d, r8d; ulOptions
0x18002ff98  mov     qword ptr [rsp+2A0h+bIgnoreCase], rax; phkResult
0x18002ff9d  lea     rdx, aMimeDatabaseCo; "MIME\\Database\\Content Type"
0x18002ffa4  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18002ffab  call    cs:__imp_RegOpenKeyExW
0x18002ffb1  mov     ebx, 80070000h
0x18002ffb6  test    eax, eax
0x18002ffb8  jz      short loc_18002FFD1
0x18002ffba  call    cs:__imp_GetLastError
0x18002ffc0  test    eax, eax
0x18002ffc2  jle     short loc_18002FFCB
0x18002ffc4  movzx   eax, ax
0x18002ffc7  or      eax, ebx
0x18002ffc9  test    eax, eax
0x18002ffcb  js      loc_18002FECF
0x18002ffd1  mov     rcx, [rsp+2A0h+hKey]; hkey
0x18002ffd6  lea     rax, [rsp+2A0h+var_260]
0x18002ffdb  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18002ffe0  lea     r8, aExtension; "Extension"
0x18002ffe7  lea     rax, [rsp+2A0h+var_230]
0x18002ffec  mov     r9d, 2; dwFlags
0x18002fff2  mov     [rsp+2A0h+pvData], rax; pvData
0x18002fff7  mov     rdx, rsi; lpSubKey
0x18002fffa  mov     qword ptr [rsp+2A0h+bIgnoreCase], 0; pdwType
0x180030003  call    cs:__imp_RegGetValueW
0x180030009  test    eax, eax
0x18003000b  jz      loc_18002FF0D
0x180030011  call    cs:__imp_GetLastError
0x180030017  test    eax, eax
0x180030019  jle     loc_18002FECD
0x18003001f  movzx   eax, ax
0x180030022  or      eax, ebx
0x180030024  jmp     loc_18002FECB
```
