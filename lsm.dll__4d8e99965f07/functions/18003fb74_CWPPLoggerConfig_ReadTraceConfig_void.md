# CWPPLoggerConfig::ReadTraceConfig(void)

- ea: `0x18003fb74`
- end: `0x18003fde4`
- name: `?ReadTraceConfig@CWPPLoggerConfig@@QEAAJXZ`
- size: `624`
- prototype: `__int64 __fastcall(CWPPLoggerConfig *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003fdec`
- `0x180083e28`

## callees

- `0x1800038a8`
- `0x180003a44`
- `0x180022080`
- `0x180027dd4`
- `0x18003fb74`
- `0x18004e850`
- `0x18004f354`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fbf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fbf0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003fcb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003fcb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fdba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fdba`

## string_xrefs

- `0x18003fc31`: `RegOpenKeyEx failed`
- `0x18003fd0b`: `Setting log file size from registry entry DebugMaxFileSize`

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
        if ( (unsigned int)dword_1800DF020 <= 5 )
          goto LABEL_21;
        v11 = &word_1800CD616;
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
      if ( (unsigned int)dword_1800DF020 <= 5 )
        goto LABEL_21;
      v11 = (__int16 *)byte_1800CD5D5;
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
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v14 = "Ignoring DebugMaxFileSize, it has be greater than 0, using default";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1800DF020,
        (unsigned int)&byte_1800CD657,
        0,
        0,
        (__int64)&v14);
    }
    goto LABEL_17;
  }
  if ( v2 > 0 )
    v6 = (unsigned __int16)v2 | 0x80070000;
  if ( (unsigned int)dword_1800DF020 > 2 )
  {
    LODWORD(v18) = v6;
    v19 = v21;
    v14 = "RegOpenKeyEx failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v3,
      (unsigned int)&word_1800CD50E,
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
0x18003fb74  push    rbp
0x18003fb76  push    rbx
0x18003fb77  push    rsi
0x18003fb78  push    rdi
0x18003fb79  lea     rbp, [rsp-198h]
0x18003fb81  sub     rsp, 298h
0x18003fb88  mov     rax, cs:__security_cookie
0x18003fb8f  xor     rax, rsp
0x18003fb92  mov     [rbp+1B0h+var_30], rax
0x18003fb99  mov     rbx, rcx
0x18003fb9c  mov     [rsp+2B0h+hKey], 0
0x18003fba5  lea     rcx, [rsp+2B0h+var_240]; void *
0x18003fbaa  xor     edx, edx; Val
0x18003fbac  mov     r8d, 208h; Size
0x18003fbb2  call    memset_0
0x18003fbb7  lea     rax, [rsp+2B0h+hKey]
0x18003fbbc  mov     [rsp+2B0h+cbData], 0
0x18003fbc4  mov     r9d, 20019h; samDesired
0x18003fbca  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18003fbcf  xor     r8d, r8d; ulOptions
0x18003fbd2  mov     [rsp+2B0h+Type], 0
0x18003fbda  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18003fbe1  mov     dword ptr [rsp+2B0h+Data], 0
0x18003fbe9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003fbf0  call    cs:__imp_RegOpenKeyExW
0x18003fbf7  nop     dword ptr [rax+rax+00h]
0x18003fbfc  mov     edi, eax
0x18003fbfe  test    eax, eax
0x18003fc00  jz      short loc_18003FC65
0x18003fc02  jle     short loc_18003FC0D
0x18003fc04  movzx   edi, ax
0x18003fc07  or      edi, 80070000h
0x18003fc0d  mov     eax, cs:dword_1800DF020
0x18003fc13  cmp     eax, 2
0x18003fc16  jbe     loc_18003FDB0
0x18003fc1c  lea     rax, [rsp+2B0h+var_240]
0x18003fc21  mov     dword ptr [rsp+2B0h+var_258], edi
0x18003fc25  mov     [rsp+2B0h+var_250], rax
0x18003fc2a  lea     rdx, word_1800CD50E
0x18003fc31  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x18003fc38  mov     [rsp+2B0h+var_270], rax
0x18003fc3d  lea     rax, [rsp+2B0h+var_250]
0x18003fc42  mov     [rsp+2B0h+var_280], rax
0x18003fc47  lea     rax, [rsp+2B0h+var_258]
0x18003fc4c  mov     [rsp+2B0h+lpcbData], rax
0x18003fc51  lea     rax, [rsp+2B0h+var_270]
0x18003fc56  mov     [rsp+2B0h+phkResult], rax
0x18003fc5b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003fc60  jmp     loc_18003FDB0
0x18003fc65  xor     edi, edi
0x18003fc67  xor     esi, esi
0x18003fc69  cmp     [rbx+8], esi
0x18003fc6c  jbe     short loc_18003FC86
0x18003fc6e  mov     rax, [rbx+10h]
0x18003fc72  lea     rcx, [rsi+rsi*4]
0x18003fc76  lea     rcx, [rax+rcx*8]; this
0x18003fc7a  call    ?ReadTraceConfig@CWPPLoggerGuidConfig@@QEAAJXZ; CWPPLoggerGuidConfig::ReadTraceConfig(void)
0x18003fc7f  inc     esi
0x18003fc81  cmp     esi, [rbx+8]
0x18003fc84  jb      short loc_18003FC6E
0x18003fc86  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003fc8b  lea     rax, [rsp+2B0h+cbData]
0x18003fc90  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18003fc95  lea     r9, [rsp+2B0h+Type]; lpType
0x18003fc9a  lea     rax, [rsp+2B0h+Data]
0x18003fc9f  mov     [rsp+2B0h+cbData], 4
0x18003fca7  xor     r8d, r8d; lpReserved
0x18003fcaa  mov     [rsp+2B0h+phkResult], rax; lpData
0x18003fcaf  lea     rdx, aDebugmaxfilesi; "DebugMaxFileSize"
0x18003fcb6  call    cs:__imp_RegQueryValueExW
0x18003fcbd  nop     dword ptr [rax+rax+00h]
0x18003fcc2  test    eax, eax
0x18003fcc4  jnz     loc_18003FD52
0x18003fcca  cmp     [rsp+2B0h+Type], 4
0x18003fccf  mov     eax, dword ptr [rsp+2B0h+Data]
0x18003fcd3  jnz     short loc_18003FD14
0x18003fcd5  test    eax, eax
0x18003fcd7  jz      short loc_18003FD18
0x18003fcd9  cmp     [rbx+34h], eax
0x18003fcdc  jz      loc_18003FDB0
0x18003fce2  mov     [rbx+34h], eax
0x18003fce5  mov     eax, cs:dword_1800DF020
0x18003fceb  cmp     eax, 5
0x18003fcee  jbe     loc_18003FDB0
0x18003fcf4  mov     rax, [rbx]
0x18003fcf7  lea     rdx, word_1800CD616
0x18003fcfe  mov     [rsp+2B0h+var_270], rax
0x18003fd03  mov     eax, [rbx+34h]
0x18003fd06  mov     [rsp+2B0h+var_250], rax
0x18003fd0b  lea     rax, aSettingLogFile; "Setting log file size from registry ent"...
0x18003fd12  jmp     short loc_18003FD88
0x18003fd14  test    eax, eax
0x18003fd16  jnz     short loc_18003FD52
0x18003fd18  mov     eax, cs:dword_1800DF020
0x18003fd1e  cmp     eax, 5
0x18003fd21  jbe     short loc_18003FD52
0x18003fd23  lea     rax, aIgnoringDebugm; "Ignoring DebugMaxFileSize, it has be gr"...
0x18003fd2a  xor     r9d, r9d
0x18003fd2d  mov     [rsp+2B0h+var_270], rax
0x18003fd32  lea     rdx, byte_1800CD657
0x18003fd39  lea     rax, [rsp+2B0h+var_270]
0x18003fd3e  xor     r8d, r8d
0x18003fd41  lea     rcx, dword_1800DF020
0x18003fd48  mov     [rsp+2B0h+phkResult], rax
0x18003fd4d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003fd52  mov     eax, 800h
0x18003fd57  cmp     [rbx+34h], eax
0x18003fd5a  jz      short loc_18003FDB0
0x18003fd5c  mov     [rbx+34h], eax
0x18003fd5f  mov     eax, cs:dword_1800DF020
0x18003fd65  cmp     eax, 5
0x18003fd68  jbe     short loc_18003FDB0
0x18003fd6a  mov     rax, [rbx]
0x18003fd6d  lea     rdx, byte_1800CD5D5
0x18003fd74  mov     [rsp+2B0h+var_270], rax
0x18003fd79  mov     eax, [rbx+34h]
0x18003fd7c  mov     [rsp+2B0h+var_250], rax
0x18003fd81  lea     rax, aUsingDefaultLo; "Using Default log file size"
0x18003fd88  mov     [rsp+2B0h+var_258], rax
0x18003fd8d  lea     rax, [rsp+2B0h+var_270]
0x18003fd92  mov     [rsp+2B0h+var_280], rax
0x18003fd97  lea     rax, [rsp+2B0h+var_250]
0x18003fd9c  mov     [rsp+2B0h+lpcbData], rax
0x18003fda1  lea     rax, [rsp+2B0h+var_258]
0x18003fda6  mov     [rsp+2B0h+phkResult], rax
0x18003fdab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18003fdb0  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003fdb5  test    rcx, rcx
0x18003fdb8  jz      short loc_18003FDC6
0x18003fdba  call    cs:__imp_RegCloseKey
0x18003fdc1  nop     dword ptr [rax+rax+00h]
0x18003fdc6  mov     eax, edi
0x18003fdc8  mov     rcx, [rbp+1B0h+var_30]
0x18003fdcf  xor     rcx, rsp; StackCookie
0x18003fdd2  call    __security_check_cookie
0x18003fdd7  add     rsp, 298h
0x18003fdde  pop     rdi
0x18003fddf  pop     rsi
0x18003fde0  pop     rbx
0x18003fde1  pop     rbp
0x18003fde2  retn
```
