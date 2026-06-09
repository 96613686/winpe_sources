# RemoveKeyFromLegacyStore

- ea: `0x18005cd34`
- end: `0x18005cf5e`
- name: `RemoveKeyFromLegacyStore`
- size: `554`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003770`

## callees

- `0x180004850`
- `0x180005848`
- `0x180007298`
- `0x1800090c0`
- `0x18000af80`
- `0x18000d3d0`
- `0x18001e4cc`
- `0x18005cd34`
- `0x180062310`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005cd82`
- `ntdll!RtlInitUnicodeString` at `0x18005cd82`
- `ntdll!RtlFreeAnsiString` at `0x18005cf1e`
- `ntdll!RtlFreeAnsiString` at `0x18005cf1e`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18005cd9b`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18005cd9b`

## string_xrefs

- `0x18005ce00`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18005ce7c`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18005cefe`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`

## pseudocode

```c
__int64 __fastcall RemoveKeyFromLegacyStore(__int64 a1, unsigned int a2)
{
  const WCHAR *v4; // rdx
  void *v5; // rdi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rcx
  unsigned int LegacyUserDirectory; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  struct _STRING AnsiString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v18[224]; // [rsp+70h] [rbp-90h] BYREF

  v4 = *(const WCHAR **)(a1 + 8);
  v5 = 0;
  AnsiString = 0;
  v15 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v4);
  if ( RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u) < 0 || !AnsiString.Buffer )
  {
    v7 = -2146893810;
    AnsiString.Buffer = 0;
    v9 = 2148073486LL;
    v8 = 3229;
    goto LABEL_16;
  }
  v6 = AddMachineGuidAndAppContainerSidHashToContainerNameA(AnsiString.Buffer);
  v7 = v6;
  if ( v6 )
  {
    v8 = 3244;
    v9 = v6;
LABEL_16:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", v8);
    goto LABEL_17;
  }
  LegacyUserDirectory = GetLegacyUserDirectory(*(unsigned int *)(a1 + 32), a2, *(_QWORD *)(a1 + 72), &v15);
  v7 = LegacyUserDirectory;
  if ( LegacyUserDirectory )
  {
    DebugTraceError(LegacyUserDirectory, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", 3256);
    v5 = v15;
    goto LABEL_17;
  }
  v5 = v15;
  v7 = DeleteFileInStorageArea(v11, v15, v18);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_d3c89702f7ce32abfafe624753d31df6_Traceguids,
        (_DWORD)v5,
        (__int64)v18);
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", 3268);
    if ( v7 != -2146893802 )
    {
      KspCryptAuditKeyFileOperation(0, v13, a1, v5, v18, 2457, v7);
      goto LABEL_17;
    }
  }
  else
  {
    KspCryptAuditKeyFileOperation(1, v12, a1, v5, v18, 2457, 0);
  }
  v7 = 0;
LABEL_17:
  if ( AnsiString.Buffer )
    RtlFreeAnsiString(&AnsiString);
  if ( v5 )
    MSCryptFree(v5);
  return v7;
}

```

## disassembly

```asm
0x18005cd34  mov     [rsp-8+arg_8], rbx
0x18005cd39  mov     [rsp-8+arg_10], rsi
0x18005cd3e  push    rbp
0x18005cd3f  push    rdi
0x18005cd40  push    r14
0x18005cd42  lea     rbp, [rsp-60h]
0x18005cd47  sub     rsp, 160h
0x18005cd4e  mov     rax, cs:__security_cookie
0x18005cd55  xor     rax, rsp
0x18005cd58  mov     [rbp+70h+var_20], rax
0x18005cd5c  mov     r14d, edx
0x18005cd5f  mov     rsi, rcx
0x18005cd62  mov     rdx, [rcx+8]; SourceString
0x18005cd66  xorps   xmm0, xmm0
0x18005cd69  xorps   xmm1, xmm1
0x18005cd6c  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x18005cd71  xor     edi, edi
0x18005cd73  movups  xmmword ptr [rsp+170h+AnsiString.Length], xmm0
0x18005cd78  mov     [rsp+170h+var_130], rdi
0x18005cd7d  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm1
0x18005cd82  call    cs:__imp_RtlInitUnicodeString
0x18005cd89  nop     dword ptr [rax+rax+00h]
0x18005cd8e  mov     r8b, 1; AllocateDestinationString
0x18005cd91  lea     rdx, [rsp+170h+DestinationString]; SourceString
0x18005cd96  lea     rcx, [rsp+170h+AnsiString]; DestinationString
0x18005cd9b  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18005cda2  nop     dword ptr [rax+rax+00h]
0x18005cda7  test    eax, eax
0x18005cda9  js      loc_18005CEEC
0x18005cdaf  mov     rcx, [rsp+170h+AnsiString.Buffer]; pszSrc
0x18005cdb4  test    rcx, rcx
0x18005cdb7  jz      loc_18005CEEC
0x18005cdbd  mov     edx, [rsi+210h]
0x18005cdc3  lea     r8, [rsp+170h+var_100]
0x18005cdc8  call    AddMachineGuidAndAppContainerSidHashToContainerNameA
0x18005cdcd  mov     ebx, eax
0x18005cdcf  test    eax, eax
0x18005cdd1  jz      short loc_18005CDE0
0x18005cdd3  mov     r9d, 0CACh
0x18005cdd9  mov     ecx, eax
0x18005cddb  jmp     loc_18005CEFE
0x18005cde0  mov     r8, [rsi+48h]
0x18005cde4  lea     r9, [rsp+170h+var_130]
0x18005cde9  mov     ecx, [rsi+20h]
0x18005cdec  mov     edx, r14d
0x18005cdef  call    GetLegacyUserDirectory
0x18005cdf4  mov     ebx, eax
0x18005cdf6  test    eax, eax
0x18005cdf8  jz      short loc_18005CE1F
0x18005cdfa  mov     r9d, 0CB8h
0x18005ce00  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005ce07  lea     rdx, aStatus; "Status"
0x18005ce0e  mov     ecx, eax
0x18005ce10  call    DebugTraceError
0x18005ce15  mov     rdi, [rsp+170h+var_130]
0x18005ce1a  jmp     loc_18005CF11
0x18005ce1f  mov     rdi, [rsp+170h+var_130]
0x18005ce24  lea     r8, [rsp+170h+var_100]
0x18005ce29  mov     rdx, rdi
0x18005ce2c  call    DeleteFileInStorageArea
0x18005ce31  mov     ebx, eax
0x18005ce33  test    eax, eax
0x18005ce35  jz      loc_18005CEBE
0x18005ce3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ce42  lea     rax, WPP_GLOBAL_Control
0x18005ce49  cmp     rcx, rax
0x18005ce4c  jz      short loc_18005CE76
0x18005ce4e  test    byte ptr [rcx+1Ch], 1
0x18005ce52  jz      short loc_18005CE76
0x18005ce54  mov     rcx, [rcx+10h]
0x18005ce58  lea     rax, [rsp+170h+var_100]
0x18005ce5d  mov     edx, 0Dh
0x18005ce62  mov     [rsp+170h+var_150], rax
0x18005ce67  mov     r9, rdi
0x18005ce6a  lea     r8, WPP_d3c89702f7ce32abfafe624753d31df6_Traceguids
0x18005ce71  call    WPP_SF_SS
0x18005ce76  mov     r9d, 0CC4h
0x18005ce7c  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005ce83  lea     rdx, aStatus; "Status"
0x18005ce8a  mov     ecx, ebx
0x18005ce8c  call    DebugTraceError
0x18005ce91  cmp     ebx, 80090016h
0x18005ce97  jz      short loc_18005CEE8
0x18005ce99  mov     [rsp+170h+var_140], ebx
0x18005ce9d  lea     rax, [rsp+170h+var_100]
0x18005cea2  mov     [rsp+170h+var_148], 999h
0x18005ceaa  mov     r9, rdi
0x18005cead  mov     r8, rsi
0x18005ceb0  mov     [rsp+170h+var_150], rax
0x18005ceb5  xor     ecx, ecx
0x18005ceb7  call    KspCryptAuditKeyFileOperation
0x18005cebc  jmp     short loc_18005CF11
0x18005cebe  mov     [rsp+170h+var_140], 0
0x18005cec6  lea     rax, [rsp+170h+var_100]
0x18005cecb  mov     [rsp+170h+var_148], 999h
0x18005ced3  mov     r9, rdi
0x18005ced6  mov     r8, rsi
0x18005ced9  mov     [rsp+170h+var_150], rax
0x18005cede  mov     ecx, 1
0x18005cee3  call    KspCryptAuditKeyFileOperation
0x18005cee8  xor     ebx, ebx
0x18005ceea  jmp     short loc_18005CF11
0x18005ceec  mov     ebx, 8009000Eh
0x18005cef1  mov     [rsp+170h+AnsiString.Buffer], rdi
0x18005cef6  mov     ecx, ebx
0x18005cef8  mov     r9d, 0C9Dh
0x18005cefe  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cf05  lea     rdx, aStatus; "Status"
0x18005cf0c  call    DebugTraceError
0x18005cf11  cmp     [rsp+170h+AnsiString.Buffer], 0
0x18005cf17  jz      short loc_18005CF2A
0x18005cf19  lea     rcx, [rsp+170h+AnsiString]; AnsiString
0x18005cf1e  call    cs:__imp_RtlFreeAnsiString
0x18005cf25  nop     dword ptr [rax+rax+00h]
0x18005cf2a  test    rdi, rdi
0x18005cf2d  jz      short loc_18005CF37
0x18005cf2f  mov     rcx, rdi
0x18005cf32  call    MSCryptFree
0x18005cf37  mov     eax, ebx
0x18005cf39  mov     rcx, [rbp+70h+var_20]
0x18005cf3d  xor     rcx, rsp; StackCookie
0x18005cf40  call    __security_check_cookie
0x18005cf45  lea     r11, [rsp+170h+var_10]
0x18005cf4d  mov     rbx, [r11+28h]
0x18005cf51  mov     rsi, [r11+30h]
0x18005cf55  mov     rsp, r11
0x18005cf58  pop     r14
0x18005cf5a  pop     rdi
0x18005cf5b  pop     rbp
0x18005cf5c  retn
```
