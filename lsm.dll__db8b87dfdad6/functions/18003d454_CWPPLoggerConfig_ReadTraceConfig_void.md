# CWPPLoggerConfig::ReadTraceConfig(void)

- ea: `0x18003d454`
- end: `0x18003d6b1`
- name: `?ReadTraceConfig@CWPPLoggerConfig@@QEAAJXZ`
- size: `605`
- prototype: `__int64 __fastcall(CWPPLoggerConfig *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003d6b8`
- `0x18007f274`

## callees

- `0x180003884`
- `0x180003a20`
- `0x18001fc20`
- `0x180025d30`
- `0x18003d454`
- `0x18004b460`
- `0x18004bf44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d4d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d4d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d590`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d590`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d68e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d68e`

## string_xrefs

- `0x18003d50b`: `RegOpenKeyEx failed`
- `0x18003d5df`: `Setting log file size from registry entry DebugMaxFileSize`

## pseudocode

```c
__int64 __fastcall CWPPLoggerConfig::ReadTraceConfig(CWPPLoggerConfig *this)
{
  LSTATUS v2; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  unsigned int v6; // edi
  __int64 i; // rsi
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  __int16 *v11; // rdx
  const char *v12; // rax
  const char *v14; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  const char *v18; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE *v19; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v21[528]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  memset_0(v21, 0, 0x208u);
  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v6 = v2;
  if ( !v2 )
  {
    v6 = 0;
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
      CWPPLoggerGuidConfig::ReadTraceConfig((CWPPLoggerGuidConfig *)(*((_QWORD *)this + 2) + 40 * i));
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"DebugMaxFileSize", 0, &Type, Data, &cbData) )
      goto LABEL_17;
    if ( Type == 4 )
    {
      if ( *(_DWORD *)Data )
      {
        if ( *((_DWORD *)this + 13) == *(_DWORD *)Data )
          goto LABEL_21;
        *((_DWORD *)this + 13) = *(_DWORD *)Data;
        if ( (unsigned int)dword_1800DA020 <= 5 )
          goto LABEL_21;
        v11 = &word_1800C848E;
        v14 = *(const char **)this;
        v19 = (_BYTE *)*((unsigned int *)this + 13);
        v12 = "Setting log file size from registry entry DebugMaxFileSize";
        goto LABEL_20;
      }
    }
    else if ( *(_DWORD *)Data )
    {
LABEL_17:
      if ( *((_DWORD *)this + 13) == 2048 )
        goto LABEL_21;
      *((_DWORD *)this + 13) = 2048;
      if ( (unsigned int)dword_1800DA020 <= 5 )
        goto LABEL_21;
      v11 = (__int16 *)byte_1800C844D;
      v14 = *(const char **)this;
      v19 = (_BYTE *)*((unsigned int *)this + 13);
      v12 = "Using Default log file size";
LABEL_20:
      v18 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v8,
        (_DWORD)v11,
        v9,
        v10,
        (__int64)&v18,
        (__int64)&v19,
        (__int64)&v14);
      goto LABEL_21;
    }
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      v14 = "Ignoring DebugMaxFileSize, it has be greater than 0, using default";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1800DA020,
        (unsigned int)&byte_1800C84CF,
        0,
        0,
        (__int64)&v14);
    }
    goto LABEL_17;
  }
  if ( v2 > 0 )
    v6 = (unsigned __int16)v2 | 0x80070000;
  if ( (unsigned int)dword_1800DA020 > 2 )
  {
    LODWORD(v18) = v6;
    v19 = v21;
    v14 = "RegOpenKeyEx failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v3,
      (unsigned int)&word_1800C8386,
      v4,
      v5,
      (__int64)&v14,
      (__int64)&v18,
      (__int64)&v19);
  }
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18003d454  push    rbp
0x18003d456  push    rbx
0x18003d457  push    rsi
0x18003d458  push    rdi
0x18003d459  lea     rbp, [rsp-198h]
0x18003d461  sub     rsp, 298h
0x18003d468  mov     rax, cs:__security_cookie
0x18003d46f  xor     rax, rsp
0x18003d472  mov     [rbp+1B0h+var_30], rax
0x18003d479  mov     rbx, rcx
0x18003d47c  mov     [rsp+2B0h+hKey], 0
0x18003d485  lea     rcx, [rsp+2B0h+var_240]; void *
0x18003d48a  xor     edx, edx; Val
0x18003d48c  mov     r8d, 208h; Size
0x18003d492  call    memset_0
0x18003d497  lea     rax, [rsp+2B0h+hKey]
0x18003d49c  mov     [rsp+2B0h+cbData], 0
0x18003d4a4  mov     r9d, 20019h; samDesired
0x18003d4aa  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18003d4af  xor     r8d, r8d; ulOptions
0x18003d4b2  mov     [rsp+2B0h+Type], 0
0x18003d4ba  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18003d4c1  mov     dword ptr [rsp+2B0h+Data], 0
0x18003d4c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d4d0  call    cs:__imp_RegOpenKeyExW
0x18003d4d6  mov     edi, eax
0x18003d4d8  test    eax, eax
0x18003d4da  jz      short loc_18003D53F
0x18003d4dc  jle     short loc_18003D4E7
0x18003d4de  movzx   edi, ax
0x18003d4e1  or      edi, 80070000h
0x18003d4e7  mov     eax, cs:dword_1800DA020
0x18003d4ed  cmp     eax, 2
0x18003d4f0  jbe     loc_18003D684
0x18003d4f6  lea     rax, [rsp+2B0h+var_240]
0x18003d4fb  mov     dword ptr [rsp+2B0h+var_258], edi
0x18003d4ff  mov     [rsp+2B0h+var_250], rax
0x18003d504  lea     rdx, word_1800C8386
0x18003d50b  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x18003d512  mov     [rsp+2B0h+var_270], rax
0x18003d517  lea     rax, [rsp+2B0h+var_250]
0x18003d51c  mov     [rsp+2B0h+var_280], rax
0x18003d521  lea     rax, [rsp+2B0h+var_258]
0x18003d526  mov     [rsp+2B0h+lpcbData], rax
0x18003d52b  lea     rax, [rsp+2B0h+var_270]
0x18003d530  mov     [rsp+2B0h+phkResult], rax
0x18003d535  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003d53a  jmp     loc_18003D684
0x18003d53f  xor     edi, edi
0x18003d541  xor     esi, esi
0x18003d543  cmp     [rbx+8], esi
0x18003d546  jbe     short loc_18003D560
0x18003d548  mov     rax, [rbx+10h]
0x18003d54c  lea     rcx, [rsi+rsi*4]
0x18003d550  lea     rcx, [rax+rcx*8]; this
0x18003d554  call    ?ReadTraceConfig@CWPPLoggerGuidConfig@@QEAAJXZ; CWPPLoggerGuidConfig::ReadTraceConfig(void)
0x18003d559  inc     esi
0x18003d55b  cmp     esi, [rbx+8]
0x18003d55e  jb      short loc_18003D548
0x18003d560  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003d565  lea     rax, [rsp+2B0h+cbData]
0x18003d56a  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18003d56f  lea     r9, [rsp+2B0h+Type]; lpType
0x18003d574  lea     rax, [rsp+2B0h+Data]
0x18003d579  mov     [rsp+2B0h+cbData], 4
0x18003d581  xor     r8d, r8d; lpReserved
0x18003d584  mov     [rsp+2B0h+phkResult], rax; lpData
0x18003d589  lea     rdx, aDebugmaxfilesi; "DebugMaxFileSize"
0x18003d590  call    cs:__imp_RegQueryValueExW
0x18003d596  test    eax, eax
0x18003d598  jnz     loc_18003D626
0x18003d59e  cmp     [rsp+2B0h+Type], 4
0x18003d5a3  mov     eax, dword ptr [rsp+2B0h+Data]
0x18003d5a7  jnz     short loc_18003D5E8
0x18003d5a9  test    eax, eax
0x18003d5ab  jz      short loc_18003D5EC
0x18003d5ad  cmp     [rbx+34h], eax
0x18003d5b0  jz      loc_18003D684
0x18003d5b6  mov     [rbx+34h], eax
0x18003d5b9  mov     eax, cs:dword_1800DA020
0x18003d5bf  cmp     eax, 5
0x18003d5c2  jbe     loc_18003D684
0x18003d5c8  mov     rax, [rbx]
0x18003d5cb  lea     rdx, word_1800C848E
0x18003d5d2  mov     [rsp+2B0h+var_270], rax
0x18003d5d7  mov     eax, [rbx+34h]
0x18003d5da  mov     [rsp+2B0h+var_250], rax
0x18003d5df  lea     rax, aSettingLogFile; "Setting log file size from registry ent"...
0x18003d5e6  jmp     short loc_18003D65C
0x18003d5e8  test    eax, eax
0x18003d5ea  jnz     short loc_18003D626
0x18003d5ec  mov     eax, cs:dword_1800DA020
0x18003d5f2  cmp     eax, 5
0x18003d5f5  jbe     short loc_18003D626
0x18003d5f7  lea     rax, aIgnoringDebugm; "Ignoring DebugMaxFileSize, it has be gr"...
0x18003d5fe  xor     r9d, r9d
0x18003d601  mov     [rsp+2B0h+var_270], rax
0x18003d606  lea     rdx, byte_1800C84CF
0x18003d60d  lea     rax, [rsp+2B0h+var_270]
0x18003d612  xor     r8d, r8d
0x18003d615  lea     rcx, dword_1800DA020
0x18003d61c  mov     [rsp+2B0h+phkResult], rax
0x18003d621  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d626  mov     eax, 800h
0x18003d62b  cmp     [rbx+34h], eax
0x18003d62e  jz      short loc_18003D684
0x18003d630  mov     [rbx+34h], eax
0x18003d633  mov     eax, cs:dword_1800DA020
0x18003d639  cmp     eax, 5
0x18003d63c  jbe     short loc_18003D684
0x18003d63e  mov     rax, [rbx]
0x18003d641  lea     rdx, byte_1800C844D
0x18003d648  mov     [rsp+2B0h+var_270], rax
0x18003d64d  mov     eax, [rbx+34h]
0x18003d650  mov     [rsp+2B0h+var_250], rax
0x18003d655  lea     rax, aUsingDefaultLo; "Using Default log file size"
0x18003d65c  mov     [rsp+2B0h+var_258], rax
0x18003d661  lea     rax, [rsp+2B0h+var_270]
0x18003d666  mov     [rsp+2B0h+var_280], rax
0x18003d66b  lea     rax, [rsp+2B0h+var_250]
0x18003d670  mov     [rsp+2B0h+lpcbData], rax
0x18003d675  lea     rax, [rsp+2B0h+var_258]
0x18003d67a  mov     [rsp+2B0h+phkResult], rax
0x18003d67f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18003d684  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003d689  test    rcx, rcx
0x18003d68c  jz      short loc_18003D694
0x18003d68e  call    cs:__imp_RegCloseKey
0x18003d694  mov     eax, edi
0x18003d696  mov     rcx, [rbp+1B0h+var_30]
0x18003d69d  xor     rcx, rsp; StackCookie
0x18003d6a0  call    __security_check_cookie
0x18003d6a5  add     rsp, 298h
0x18003d6ac  pop     rdi
0x18003d6ad  pop     rsi
0x18003d6ae  pop     rbx
0x18003d6af  pop     rbp
0x18003d6b0  retn
```
