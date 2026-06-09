# SetRegValInt(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x18003ca64`
- end: `0x18003cd68`
- name: `?SetRegValInt@@YAJPEAUHKEY__@@PEBG11KPEAEK@Z`
- size: `772`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004e80`
- `0x18003ca18`
- `0x18005e0e4`
- `0x18005e164`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18001e080`
- `0x18003ca64`
- `0x180042410`
- `0x18004317c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cd36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cd36`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cc72`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cc72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ccde`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ccde`

## string_xrefs

- `0x18003cb36`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003cbaf`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003cbf6`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003cc89`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003ccf5`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003cca4`: `RegCreateKeyEx`
- `0x18003cd10`: `RegSetValueEx`

## pseudocode

```c
__int64 __fastcall SetRegValInt(
        HKEY hKey,
        WCHAR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwType,
        unsigned __int8 *lpData,
        DWORD cbData)
{
  WCHAR *v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rax
  WCHAR *v14; // rcx
  unsigned int v15; // ebx
  const UCHAR *v16; // r9
  const UCHAR *v17; // rax
  bool v18; // zf
  const char *v19; // r9
  const char *v20; // r9
  LSTATUS v21; // eax
  const char *v22; // r9
  LSTATUS v23; // eax
  const char *v24; // r9
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[528]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(SubKey, 0, 0x414u);
  hKeya = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a2 )
  {
LABEL_22:
    SecurityAttributes.lpSecurityDescriptor = g_pSystemSD;
    SecurityAttributes.nLength = 24;
    v21 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2001Fu, &SecurityAttributes, &hKeya, 0);
    v15 = v21;
    if ( v21 )
    {
      if ( v21 > 0 )
        v15 = (unsigned __int16)v21 | 0xC0070000;
      v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      dwOptions[0] = 755;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v22, *(_QWORD *)dwOptions, "RegCreateKeyEx", &Class);
    }
    else
    {
      v23 = RegSetValueExW(hKeya, a4, 0, dwType, lpData, cbData);
      v15 = v23;
      if ( v23 )
      {
        if ( v23 > 0 )
          v15 = (unsigned __int16)v23 | 0xC0070000;
        v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        dwOptionsa[0] = 769;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v24, *(_QWORD *)dwOptionsa, "RegSetValueEx", &Class);
      }
      else
      {
        v15 = 0;
      }
    }
    goto LABEL_31;
  }
  v11 = SubKey;
  v12 = 522;
  v13 = 2147483646;
  do
  {
    if ( !v13 )
      break;
    if ( !*a2 )
      break;
    *v11++ = *a2++;
    --v13;
    --v12;
  }
  while ( v12 );
  v14 = v11 - 1;
  v15 = v12 == 0 ? 0x80000005 : 0;
  if ( v12 )
    v14 = v11;
  *v14 = 0;
  if ( v12 )
  {
    if ( a3 )
    {
      v15 = RtlStringCchCatW(SubKey, 0x20Au, L"\\");
      if ( v15 )
      {
        v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v19, 728, "RtlStringCchCatW", &Class);
        goto LABEL_31;
      }
      v15 = RtlStringCchCatW(SubKey, 0x20Au, a3);
      if ( v15 )
      {
        v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v20, 734, "RtlStringCchCatW", &Class);
        goto LABEL_31;
      }
    }
    goto LABEL_22;
  }
  v16 = "";
  while ( 1 )
  {
    v17 = v16--;
    v18 = *v16 == 92;
    if ( *v16 == 92 )
      break;
    if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
    {
      v18 = *v16 == 92;
      break;
    }
  }
  if ( v18 )
    v16 = v17;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v16, 719, "RtlStringCchPrintfW", &Class);
LABEL_31:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v15;
}

```

## disassembly

```asm
0x18003ca64  mov     [rsp-8+arg_8], rbx
0x18003ca69  push    rbp
0x18003ca6a  push    rsi
0x18003ca6b  push    rdi
0x18003ca6c  push    r12
0x18003ca6e  push    r13
0x18003ca70  push    r14
0x18003ca72  push    r15
0x18003ca74  lea     rbp, [rsp-3A0h]
0x18003ca7c  sub     rsp, 4A0h
0x18003ca83  mov     rax, cs:__security_cookie
0x18003ca8a  xor     rax, rsp
0x18003ca8d  mov     [rbp+3D0h+var_40], rax
0x18003ca94  mov     r14, [rbp+3D0h+lpData]
0x18003ca9b  mov     rdi, r8
0x18003ca9e  mov     rbx, rdx
0x18003caa1  mov     r15, rcx
0x18003caa4  xor     edx, edx; Val
0x18003caa6  lea     rcx, [rsp+4D0h+SubKey]; void *
0x18003caab  mov     r8d, 414h; Size
0x18003cab1  mov     rsi, r9
0x18003cab4  call    memset_0
0x18003cab9  xor     eax, eax
0x18003cabb  xor     r12d, r12d
0x18003cabe  mov     qword ptr [rsp+4D0h+SecurityAttributes.bInheritHandle], rax
0x18003cac3  xorps   xmm0, xmm0
0x18003cac6  mov     [rsp+4D0h+hKey], r12
0x18003cacb  movups  xmmword ptr [rsp+4D0h+SecurityAttributes.nLength], xmm0
0x18003cad0  test    rbx, rbx
0x18003cad3  jz      loc_18003CC2A
0x18003cad9  mov     r13d, 20Ah
0x18003cadf  lea     r8, [rsp+4D0h+SubKey]
0x18003cae4  mov     edx, r13d
0x18003cae7  mov     eax, 7FFFFFFEh
0x18003caec  test    rax, rax
0x18003caef  jz      short loc_18003CB0E
0x18003caf1  movzx   ecx, word ptr [rbx]
0x18003caf4  test    cx, cx
0x18003caf7  jz      short loc_18003CB0E
0x18003caf9  mov     [r8], cx
0x18003cafd  add     rbx, 2
0x18003cb01  add     r8, 2
0x18003cb05  dec     rax
0x18003cb08  sub     rdx, 1
0x18003cb0c  jnz     short loc_18003CAEC
0x18003cb0e  mov     rax, rdx
0x18003cb11  lea     rcx, [r8-2]
0x18003cb15  neg     rax
0x18003cb18  sbb     ebx, ebx
0x18003cb1a  not     ebx
0x18003cb1c  and     ebx, 80000005h
0x18003cb22  test    rdx, rdx
0x18003cb25  cmovnz  rcx, r8
0x18003cb29  mov     [rcx], r12w
0x18003cb2d  jnz     short loc_18003CB8C
0x18003cb2f  lea     r9, pbInput+24h; ""
0x18003cb36  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003cb3d  mov     rax, r9
0x18003cb40  dec     r9
0x18003cb43  cmp     byte ptr [r9], 5Ch ; '\'
0x18003cb47  jz      short loc_18003CB52
0x18003cb49  cmp     r9, rcx
0x18003cb4c  ja      short loc_18003CB3D
0x18003cb4e  cmp     byte ptr [r9], 5Ch ; '\'
0x18003cb52  cmovz   r9, rax
0x18003cb56  lea     rax, Class
0x18003cb5d  mov     [rsp+4D0h+lpSecurityAttributes], rax
0x18003cb62  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18003cb69  mov     qword ptr [rsp+4D0h+samDesired], rax
0x18003cb6e  mov     [rsp+4D0h+dwOptions], 2CFh
0x18003cb76  mov     r8d, ebx
0x18003cb79  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003cb80  xor     ecx, ecx
0x18003cb82  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003cb87  jmp     loc_18003CD2C
0x18003cb8c  test    rdi, rdi
0x18003cb8f  jz      loc_18003CC2A
0x18003cb95  lea     r8, asc_180085528; "\\"
0x18003cb9c  mov     rdx, r13; unsigned __int64
0x18003cb9f  lea     rcx, [rsp+4D0h+SubKey]; unsigned __int16 *
0x18003cba4  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003cba9  mov     ebx, eax
0x18003cbab  test    eax, eax
0x18003cbad  jz      short loc_18003CBE0
0x18003cbaf  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003cbb6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003cbbb  mov     r9, rax
0x18003cbbe  lea     rax, Class
0x18003cbc5  mov     [rsp+4D0h+lpSecurityAttributes], rax
0x18003cbca  lea     rax, aRtlstringcchca; "RtlStringCchCatW"
0x18003cbd1  mov     qword ptr [rsp+4D0h+samDesired], rax
0x18003cbd6  mov     [rsp+4D0h+dwOptions], 2D8h
0x18003cbde  jmp     short loc_18003CB76
0x18003cbe0  mov     r8, rdi; unsigned __int16 *
0x18003cbe3  lea     rcx, [rsp+4D0h+SubKey]; unsigned __int16 *
0x18003cbe8  mov     rdx, r13; unsigned __int64
0x18003cbeb  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003cbf0  mov     ebx, eax
0x18003cbf2  test    eax, eax
0x18003cbf4  jz      short loc_18003CC2A
0x18003cbf6  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003cbfd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003cc02  mov     r9, rax
0x18003cc05  lea     rax, Class
0x18003cc0c  mov     [rsp+4D0h+lpSecurityAttributes], rax
0x18003cc11  lea     rax, aRtlstringcchca; "RtlStringCchCatW"
0x18003cc18  mov     qword ptr [rsp+4D0h+samDesired], rax
0x18003cc1d  mov     [rsp+4D0h+dwOptions], 2DEh
0x18003cc25  jmp     loc_18003CB76
0x18003cc2a  mov     rax, cs:?g_pSystemSD@@3PEAXEA; void * g_pSystemSD
0x18003cc31  lea     rdx, [rsp+4D0h+SubKey]; lpSubKey
0x18003cc36  mov     [rsp+4D0h+lpdwDisposition], r12; lpdwDisposition
0x18003cc3b  xor     r9d, r9d; lpClass
0x18003cc3e  mov     [rsp+4D0h+SecurityAttributes.lpSecurityDescriptor], rax
0x18003cc43  xor     r8d, r8d; Reserved
0x18003cc46  lea     rax, [rsp+4D0h+hKey]
0x18003cc4b  mov     [rsp+4D0h+SecurityAttributes.nLength], 18h
0x18003cc53  mov     [rsp+4D0h+phkResult], rax; phkResult
0x18003cc58  mov     rcx, r15; hKey
0x18003cc5b  lea     rax, [rsp+4D0h+SecurityAttributes]
0x18003cc60  mov     [rsp+4D0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18003cc65  mov     [rsp+4D0h+samDesired], 2001Fh; samDesired
0x18003cc6d  mov     [rsp+4D0h+dwOptions], r12d; dwOptions
0x18003cc72  call    cs:__imp_RegCreateKeyExW
0x18003cc78  mov     ebx, eax
0x18003cc7a  test    eax, eax
0x18003cc7c  jz      short loc_18003CCBD
0x18003cc7e  jle     short loc_18003CC89
0x18003cc80  movzx   ebx, ax
0x18003cc83  or      ebx, 0C0070000h
0x18003cc89  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003cc90  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003cc95  mov     r9, rax
0x18003cc98  lea     rax, Class
0x18003cc9f  mov     [rsp+4D0h+lpSecurityAttributes], rax
0x18003cca4  lea     rax, aRegcreatekeyex; "RegCreateKeyEx"
0x18003ccab  mov     qword ptr [rsp+4D0h+samDesired], rax
0x18003ccb0  mov     [rsp+4D0h+dwOptions], 2F3h
0x18003ccb8  jmp     loc_18003CB76
0x18003ccbd  mov     eax, [rbp+3D0h+cbData]
0x18003ccc3  xor     r8d, r8d; Reserved
0x18003ccc6  mov     r9d, [rbp+3D0h+dwType]; dwType
0x18003cccd  mov     rdx, rsi; lpValueName
0x18003ccd0  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18003ccd5  mov     [rsp+4D0h+samDesired], eax; cbData
0x18003ccd9  mov     qword ptr [rsp+4D0h+dwOptions], r14; lpData
0x18003ccde  call    cs:__imp_RegSetValueExW
0x18003cce4  mov     ebx, eax
0x18003cce6  test    eax, eax
0x18003cce8  jz      short loc_18003CD29
0x18003ccea  jle     short loc_18003CCF5
0x18003ccec  movzx   ebx, ax
0x18003ccef  or      ebx, 0C0070000h
0x18003ccf5  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003ccfc  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003cd01  mov     r9, rax
0x18003cd04  lea     rax, Class
0x18003cd0b  mov     [rsp+4D0h+lpSecurityAttributes], rax
0x18003cd10  lea     rax, aRegsetvalueex; "RegSetValueEx"
0x18003cd17  mov     qword ptr [rsp+4D0h+samDesired], rax
0x18003cd1c  mov     [rsp+4D0h+dwOptions], 301h
0x18003cd24  jmp     loc_18003CB76
0x18003cd29  mov     ebx, r12d
0x18003cd2c  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18003cd31  test    rcx, rcx
0x18003cd34  jz      short loc_18003CD3C
0x18003cd36  call    cs:__imp_RegCloseKey
0x18003cd3c  mov     eax, ebx
0x18003cd3e  mov     rcx, [rbp+3D0h+var_40]
0x18003cd45  xor     rcx, rsp; StackCookie
0x18003cd48  call    __security_check_cookie
0x18003cd4d  mov     rbx, [rsp+4D0h+arg_8]
0x18003cd55  add     rsp, 4A0h
0x18003cd5c  pop     r15
0x18003cd5e  pop     r14
0x18003cd60  pop     r13
0x18003cd62  pop     r12
0x18003cd64  pop     rdi
0x18003cd65  pop     rsi
0x18003cd66  pop     rbp
0x18003cd67  retn
```
