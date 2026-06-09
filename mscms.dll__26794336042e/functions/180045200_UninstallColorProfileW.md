# UninstallColorProfileW

- ea: `0x180045200`
- end: `0x180045464`
- name: `UninstallColorProfileW`
- size: `612`
- prototype: `BOOL __stdcall(PCWSTR pMachineName, PCWSTR pProfileName, BOOL bDelete)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180045180`

## callees

- `0x1800018dc`
- `0x18000242c`
- `0x180008bf0`
- `0x180008cc0`
- `0x180023a4c`
- `0x180029f14`
- `0x18002e5f0`
- `0x180045200`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800453ad`
- `ntdll!EtwEventWrite` at `0x1800453ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045293`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800452d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045293`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800452d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453eb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180045368`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180045368`

## pseudocode

```c
BOOL __stdcall UninstallColorProfileW(PCWSTR pMachineName, PCWSTR pProfileName, BOOL bDelete)
{
  BOOL v6; // r8d
  int v7; // r9d
  DWORD v8; // ecx
  __int64 v10; // rbx
  const unsigned __int16 *FilenameFromPath; // rsi
  BOOL v12; // edi
  DWORD v13; // ecx
  __int64 v14; // rax
  int v15; // r8d
  DWORD LastError; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  BOOL v20; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbNeeded; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v22; // [rsp+58h] [rbp-A8h] BYREF
  BOOL v23; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR v25; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+74h] [rbp-8Ch]
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF

  pcbNeeded = 0;
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
  {
    v20 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18009E080,
      (unsigned int)byte_180090FD1,
      v6,
      v7,
      (__int64)&v20);
  }
  if ( !pProfileName )
  {
    v8 = 87;
LABEL_6:
    SetLastError(v8);
    return 0;
  }
  if ( pMachineName )
  {
    v8 = 50;
    goto LABEL_6;
  }
  v10 = -1;
  FilenameFromPath = 0;
  if ( !bDelete )
    goto LABEL_23;
  v12 = 0;
  FilenameFromPath = (const unsigned __int16 *)GetFilenameFromPath(pProfileName);
  if ( FilenameFromPath )
  {
    pcbNeeded = 520;
    if ( !(unsigned int)InternalGetColorDirectory(0, FileName, &pcbNeeded) )
      goto LABEL_26;
    v14 = -1;
    do
      ++v14;
    while ( FileName[v14] );
    if ( FileName[v14 - 1] != 92 && (v15 = StringCchCatW(FileName, 0x104u, gszBackslash), v15 < 0)
      || (v15 = StringCchCatW(FileName, 0x104u, FilenameFromPath), v15 < 0) )
    {
      v13 = (unsigned __int16)v15;
      if ( (v15 & 0x1FFF0000) != 0x70000 )
        v13 = v15;
      goto LABEL_12;
    }
    if ( !DeleteFileW(FileName) )
      goto LABEL_26;
LABEL_23:
    v12 = 1;
    do
      ++v10;
    while ( pProfileName[v10] );
    v26 = 2 * v10 + 2;
    v25 = pProfileName;
    v27 = 0;
    EtwEventWrite(g_etwHandle, UNINSTALL_PROFILE, 1, &v25);
    goto LABEL_26;
  }
  v13 = 87;
LABEL_12:
  SetLastError(v13);
LABEL_26:
  if ( (unsigned int)dword_18009E080 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000001LL) )
    {
      v24 = 0x2000000;
      v20 = bDelete;
      v25 = FilenameFromPath;
      LastError = GetLastError();
      v23 = v12;
      v22 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v17,
        (unsigned int)&byte_18009138F,
        v18,
        v19,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v25,
        (__int64)&v20,
        (__int64)&v24);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180045200  mov     [rsp-8+arg_0], rbx
0x180045205  mov     [rsp-8+arg_10], rsi
0x18004520a  push    rbp
0x18004520b  push    rdi
0x18004520c  push    r12
0x18004520e  push    r14
0x180045210  push    r15
0x180045212  lea     rbp, [rsp-1A0h]
0x18004521a  sub     rsp, 2A0h
0x180045221  mov     rax, cs:__security_cookie
0x180045228  xor     rax, rsp
0x18004522b  mov     [rbp+1C0h+var_30], rax
0x180045232  mov     eax, cs:dword_18009E080
0x180045238  xor     r12d, r12d
0x18004523b  mov     [rsp+2C0h+pcbNeeded], r12d
0x180045240  mov     r15d, r8d
0x180045243  mov     r14, rdx
0x180045246  mov     rbx, rcx
0x180045249  cmp     eax, 5
0x18004524c  jbe     short loc_18004528A
0x18004524e  mov     rdx, 200000000000h
0x180045258  lea     rcx, dword_18009E080
0x18004525f  call    _tlgKeywordOn
0x180045264  test    al, al
0x180045266  jz      short loc_18004528A
0x180045268  lea     rax, [rsp+2C0h+var_270]
0x18004526d  mov     [rsp+2C0h+var_270], r8d
0x180045272  lea     rdx, byte_180090FD1
0x180045279  mov     [rsp+2C0h+var_2A0], rax
0x18004527e  lea     rcx, dword_18009E080
0x180045285  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004528a  test    r14, r14
0x18004528d  jnz     short loc_1800452A0
0x18004528f  lea     ecx, [r14+57h]; dwErrCode
0x180045293  call    cs:__imp_SetLastError
0x180045299  xor     eax, eax
0x18004529b  jmp     loc_180045439
0x1800452a0  test    rbx, rbx
0x1800452a3  jz      short loc_1800452AC
0x1800452a5  mov     ecx, 32h ; '2'
0x1800452aa  jmp     short loc_180045293
0x1800452ac  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800452b0  mov     rsi, r12
0x1800452b3  test    r15d, r15d
0x1800452b6  jz      loc_180045372
0x1800452bc  mov     rcx, r14; lpStringSource
0x1800452bf  mov     edi, r12d
0x1800452c2  call    GetFilenameFromPath
0x1800452c7  mov     rsi, rax
0x1800452ca  test    rax, rax
0x1800452cd  jnz     short loc_1800452DD
0x1800452cf  lea     ecx, [rbx+58h]; dwErrCode
0x1800452d2  call    cs:__imp_SetLastError
0x1800452d8  jmp     loc_1800453B3
0x1800452dd  lea     r8, [rsp+2C0h+pcbNeeded]; pcbNeeded
0x1800452e2  mov     [rsp+2C0h+pcbNeeded], 208h
0x1800452ea  lea     rdx, [rbp+1C0h+FileName]; unsigned __int16 *
0x1800452ee  xor     ecx, ecx; pName
0x1800452f0  call    ?InternalGetColorDirectory@@YAHPEBGPEAGPEAK@Z; InternalGetColorDirectory(ushort const *,ushort *,ulong *)
0x1800452f5  test    eax, eax
0x1800452f7  jz      loc_1800453B3
0x1800452fd  lea     rcx, [rbp+1C0h+FileName]
0x180045301  mov     rax, rbx
0x180045304  inc     rax
0x180045307  cmp     [rcx+rax*2], r12w
0x18004530c  jnz     short loc_180045304
0x18004530e  cmp     [rsp+rax*2+2C0h+var_242], 5Ch ; '\'
0x180045314  jz      short loc_180045332
0x180045316  lea     r8, gszBackslash; "\\"
0x18004531d  mov     edx, 104h; unsigned __int64
0x180045322  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x180045326  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004532b  mov     r8d, eax
0x18004532e  test    eax, eax
0x180045330  js      short loc_18004534A
0x180045332  mov     r8, rsi; unsigned __int16 *
0x180045335  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x180045339  mov     edx, 104h; unsigned __int64
0x18004533e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180045343  mov     r8d, eax
0x180045346  test    eax, eax
0x180045348  jns     short loc_180045364
0x18004534a  mov     eax, r8d
0x18004534d  movzx   ecx, r8w
0x180045351  and     eax, 1FFF0000h
0x180045356  cmp     eax, 70000h
0x18004535b  cmovnz  ecx, r8d
0x18004535f  jmp     loc_1800452D2
0x180045364  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x180045368  call    cs:__imp_DeleteFileW
0x18004536e  test    eax, eax
0x180045370  jz      short loc_1800453B3
0x180045372  mov     edi, 1
0x180045377  inc     rbx
0x18004537a  cmp     [r14+rbx*2], r12w
0x18004537f  jnz     short loc_180045377
0x180045381  mov     rcx, cs:g_etwHandle
0x180045388  lea     rax, ds:2[rbx*2]
0x180045390  lea     r9, [rsp+2C0h+var_258]
0x180045395  mov     [rsp+2C0h+var_250], eax
0x180045399  mov     r8d, edi
0x18004539c  mov     [rsp+2C0h+var_258], r14
0x1800453a1  lea     rdx, UNINSTALL_PROFILE
0x1800453a8  mov     [rsp+2C0h+var_24C], r12d
0x1800453ad  call    cs:__imp_EtwEventWrite
0x1800453b3  mov     eax, cs:dword_18009E080
0x1800453b9  cmp     eax, 5
0x1800453bc  jbe     short loc_180045437
0x1800453be  mov     rdx, 200000000001h
0x1800453c8  lea     rcx, dword_18009E080
0x1800453cf  call    _tlgKeywordOn
0x1800453d4  test    al, al
0x1800453d6  jz      short loc_180045437
0x1800453d8  mov     [rsp+2C0h+var_260], 2000000h
0x1800453e1  mov     [rsp+2C0h+var_270], r15d
0x1800453e6  mov     [rsp+2C0h+var_258], rsi
0x1800453eb  call    cs:__imp_GetLastError
0x1800453f1  lea     rdx, byte_18009138F
0x1800453f8  mov     [rsp+2C0h+var_264], edi
0x1800453fc  mov     [rsp+2C0h+var_268], eax
0x180045400  lea     rax, [rsp+2C0h+var_260]
0x180045405  mov     [rsp+2C0h+var_280], rax
0x18004540a  lea     rax, [rsp+2C0h+var_270]
0x18004540f  mov     [rsp+2C0h+var_288], rax
0x180045414  lea     rax, [rsp+2C0h+var_258]
0x180045419  mov     [rsp+2C0h+var_290], rax
0x18004541e  lea     rax, [rsp+2C0h+var_268]
0x180045423  mov     [rsp+2C0h+var_298], rax
0x180045428  lea     rax, [rsp+2C0h+var_264]
0x18004542d  mov     [rsp+2C0h+var_2A0], rax
0x180045432  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180045437  mov     eax, edi
0x180045439  mov     rcx, [rbp+1C0h+var_30]
0x180045440  xor     rcx, rsp; StackCookie
0x180045443  call    __security_check_cookie
0x180045448  lea     r11, [rsp+2C0h+var_20]
0x180045450  mov     rbx, [r11+30h]
0x180045454  mov     rsi, [r11+40h]
0x180045458  mov     rsp, r11
0x18004545b  pop     r15
0x18004545d  pop     r14
0x18004545f  pop     r12
0x180045461  pop     rdi
0x180045462  pop     rbp
0x180045463  retn
```
