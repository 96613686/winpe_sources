# OpenSupplementalCredentialStore(ulong,HKEY__ * *)

- ea: `0x1800376a0`
- end: `0x180037a54`
- name: `?OpenSupplementalCredentialStore@@YAKKPEAPEAUHKEY__@@@Z`
- size: `948`
- prototype: `DWORD __fastcall(REGSAM samDesired, PHKEY phkResult)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800382f4`
- `0x1800385fc`

## callees

- `0x180007f10`
- `0x180008a44`
- `0x180010d78`
- `0x180013bec`
- `0x18001c9c0`
- `0x18001d810`
- `0x180037214`
- `0x1800375a0`
- `0x1800376a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800379c0`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800379c0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037a0a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003770f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003770f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037852`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037852`

## string_xrefs

- `0x180037778`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x18003797e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
DWORD __fastcall OpenSupplementalCredentialStore(REGSAM samDesired, PHKEY phkResult)
{
  __int64 v4; // rdi
  UINT SystemDirectoryW; // eax
  __int64 v6; // r14
  unsigned int KeyW; // ebx
  __int64 v9; // r9
  __int64 v10; // rsi
  __int64 v11; // rax
  WCHAR *v12; // rcx
  unsigned __int16 *v13; // rdx
  WCHAR v14; // r8
  unsigned __int16 *v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rcx
  unsigned int v18; // eax
  struct _LUID p_FileW; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE FileW; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v21[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v22; // [rsp+70h] [rbp-90h]
  __int64 v23; // [rsp+80h] [rbp-80h]
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v25[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
  v4 = 261;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x105u);
  v6 = SystemDirectoryW;
  if ( !SystemDirectoryW )
    return GetLastError();
  *(_OWORD *)v21 = *(_OWORD *)L"\\Microsoft\\Protect\\";
  v22 = *(_OWORD *)L"ft\\Protect\\";
  v23 = *(_QWORD *)L"ct\\";
  KeyW = StringCchCatW(Buffer, 0x105u, v21);
  if ( KeyW )
  {
    v9 = 1425;
LABEL_8:
    DebugTraceError(KeyW, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v9);
    return KeyW;
  }
  KeyW = StringCchCatW(Buffer, 0x105u, L"Recovery\\");
  if ( KeyW )
  {
    v9 = 1432;
    goto LABEL_8;
  }
  v10 = -1;
  do
    ++v10;
  while ( Buffer[v10] );
  KeyW = StringCchCatW(Buffer, 0x105u, L"Recovery.dat");
  if ( KeyW )
  {
    v9 = 1441;
    goto LABEL_8;
  }
  p_FileW = (struct _LUID)17LL;
  KeyW = ObtainPrivilege((struct _LUID)17LL);
  if ( KeyW )
  {
    v9 = 1453;
    goto LABEL_8;
  }
  p_FileW = (struct _LUID)18LL;
  KeyW = ObtainPrivilege((struct _LUID)18LL);
  if ( KeyW )
  {
    v9 = 1462;
    goto LABEL_8;
  }
  FileW = CreateFileW(Buffer, 0x80000000, 1u, 0, 3u, 0, 0);
  p_FileW = (struct _LUID)&FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
    if ( GetLastError() == 3 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
      if ( (unsigned int)v10 > 0x7FFFFFFE )
      {
        KeyW = -2147024809;
        v25[0] = 0;
LABEL_37:
        v16 = 1502;
        v17 = KeyW;
LABEL_41:
        DebugTraceError(v17, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v16);
        ScopedCloseHandle::~ScopedCloseHandle((ScopedCloseHandle *)&p_FileW);
        return KeyW;
      }
      v11 = (unsigned int)v10;
      v12 = Buffer;
      v13 = v25;
      do
      {
        if ( !v11 )
          break;
        v14 = *v12;
        if ( !*v12 )
          break;
        ++v12;
        *v13++ = v14;
        --v11;
        --v4;
      }
      while ( v4 );
      KeyW = v4 == 0 ? 0x8007007A : 0;
      v15 = v13 - 1;
      if ( v4 )
        v15 = v13;
      *v15 = 0;
      if ( !v4 )
        goto LABEL_37;
      DPAPICreateNestedDirectories(v25, &v25[v6]);
    }
    v18 = MigrateLegacyRecovery(Buffer);
    KeyW = v18;
    if ( v18 )
    {
      v16 = 1515;
      v17 = v18;
      goto LABEL_41;
    }
  }
  ScopedCloseHandle::~ScopedCloseHandle((ScopedCloseHandle *)&p_FileW);
  KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"C80ED86A-0D28-40dc-B379-BB594E14EA1B", Buffer);
  if ( KeyW )
  {
    v9 = 1526;
    goto LABEL_8;
  }
  KeyW = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"C80ED86A-0D28-40dc-B379-BB594E14EA1B",
           0,
           (LPWSTR)&Class,
           0,
           samDesired,
           0,
           phkResult,
           0);
  if ( KeyW )
  {
    v9 = 1541;
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x1800376a0  mov     [rsp-8+arg_10], rbx
0x1800376a5  push    rbp
0x1800376a6  push    rsi
0x1800376a7  push    rdi
0x1800376a8  push    r12
0x1800376aa  push    r13
0x1800376ac  push    r14
0x1800376ae  push    r15
0x1800376b0  lea     rbp, [rsp-3C0h]
0x1800376b8  sub     rsp, 4C0h
0x1800376bf  mov     rax, cs:__security_cookie
0x1800376c6  xor     rax, rsp
0x1800376c9  mov     [rbp+3F0h+var_40], rax
0x1800376d0  mov     r12, rdx
0x1800376d3  mov     r15d, ecx
0x1800376d6  lea     rax, WPP_GLOBAL_Control
0x1800376dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376e4  cmp     rcx, rax
0x1800376e7  jz      short loc_180037704
0x1800376e9  test    byte ptr [rcx+1Ch], 4
0x1800376ed  jz      short loc_180037704
0x1800376ef  mov     edx, 16h
0x1800376f4  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x1800376fb  mov     rcx, [rcx+10h]
0x1800376ff  call    WPP_SF_
0x180037704  mov     edi, 105h
0x180037709  mov     edx, edi; uSize
0x18003770b  lea     rcx, [rbp+3F0h+Buffer]; lpBuffer
0x18003770f  call    cs:__imp_GetSystemDirectoryW
0x180037716  nop     dword ptr [rax+rax+00h]
0x18003771b  mov     r14d, eax
0x18003771e  xor     r13d, r13d
0x180037721  test    eax, eax
0x180037723  jnz     short loc_180037736
0x180037725  call    cs:__imp_GetLastError
0x18003772c  nop     dword ptr [rax+rax+00h]
0x180037731  jmp     loc_180037A29
0x180037736  movups  xmm0, xmmword ptr cs:aMicrosoftProte; "\\Microsoft\\Protect\\"
0x18003773d  movups  xmmword ptr [rsp+4F0h+var_490], xmm0
0x180037742  movups  xmm1, xmmword ptr cs:aMicrosoftProte+10h; "ft\\Protect\\"
0x180037749  movups  [rsp+4F0h+var_480], xmm1
0x18003774e  movsd   xmm0, qword ptr cs:aMicrosoftProte+20h; "ct\\"
0x180037756  movsd   [rbp+3F0h+var_470], xmm0
0x18003775b  lea     r8, [rsp+4F0h+var_490]; unsigned __int16 *
0x180037760  mov     rdx, rdi; unsigned __int64
0x180037763  lea     rcx, [rbp+3F0h+Buffer]; unsigned __int16 *
0x180037767  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003776c  mov     ebx, eax
0x18003776e  test    eax, eax
0x180037770  jz      short loc_180037794
0x180037772  mov     r9d, 591h
0x180037778  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003777f  lea     rdx, aDwerror; "dwError"
0x180037786  mov     ecx, ebx
0x180037788  call    DebugTraceError
0x18003778d  mov     eax, ebx
0x18003778f  jmp     loc_180037A29
0x180037794  lea     r8, aRecovery; "Recovery\\"
0x18003779b  mov     rdx, rdi; unsigned __int64
0x18003779e  lea     rcx, [rbp+3F0h+Buffer]; unsigned __int16 *
0x1800377a2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800377a7  mov     ebx, eax
0x1800377a9  test    eax, eax
0x1800377ab  jz      short loc_1800377B5
0x1800377ad  mov     r9d, 598h
0x1800377b3  jmp     short loc_180037778
0x1800377b5  lea     rax, [rbp+3F0h+Buffer]
0x1800377b9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800377bd  inc     rsi
0x1800377c0  cmp     [rax+rsi*2], r13w
0x1800377c5  jnz     short loc_1800377BD
0x1800377c7  lea     r8, aRecoveryDat; "Recovery.dat"
0x1800377ce  mov     rdx, rdi; unsigned __int64
0x1800377d1  lea     rcx, [rbp+3F0h+Buffer]; unsigned __int16 *
0x1800377d5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800377da  mov     ebx, eax
0x1800377dc  test    eax, eax
0x1800377de  jz      short loc_1800377E8
0x1800377e0  mov     r9d, 5A1h
0x1800377e6  jmp     short loc_180037778
0x1800377e8  mov     qword ptr [rsp+4F0h+var_4A0.LowPart], 11h
0x1800377f1  mov     rcx, qword ptr [rsp+4F0h+var_4A0.LowPart]; struct _LUID
0x1800377f6  call    ?ObtainPrivilege@@YAKU_LUID@@@Z; ObtainPrivilege(_LUID)
0x1800377fb  mov     ebx, eax
0x1800377fd  test    eax, eax
0x1800377ff  jz      short loc_18003780C
0x180037801  mov     r9d, 5ADh
0x180037807  jmp     loc_180037778
0x18003780c  mov     qword ptr [rsp+4F0h+var_4A0.LowPart], 12h
0x180037815  mov     rcx, qword ptr [rsp+4F0h+var_4A0.LowPart]; struct _LUID
0x18003781a  call    ?ObtainPrivilege@@YAKU_LUID@@@Z; ObtainPrivilege(_LUID)
0x18003781f  mov     ebx, eax
0x180037821  test    eax, eax
0x180037823  jz      short loc_180037830
0x180037825  mov     r9d, 5B6h
0x18003782b  jmp     loc_180037778
0x180037830  mov     [rsp+4F0h+hTemplateFile], r13; hTemplateFile
0x180037835  mov     [rsp+4F0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18003783a  mov     [rsp+4F0h+dwCreationDisposition], 3; dwCreationDisposition
0x180037842  xor     r9d, r9d; lpSecurityAttributes
0x180037845  mov     edx, 80000000h; dwDesiredAccess
0x18003784a  lea     r8d, [r9+1]; dwShareMode
0x18003784e  lea     rcx, [rbp+3F0h+Buffer]; lpFileName
0x180037852  call    cs:__imp_CreateFileW
0x180037859  nop     dword ptr [rax+rax+00h]
0x18003785e  mov     [rsp+4F0h+var_498], rax
0x180037863  lea     rcx, [rsp+4F0h+var_498]
0x180037868  mov     qword ptr [rsp+4F0h+var_4A0.LowPart], rcx
0x18003786d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037871  jnz     loc_1800379A1
0x180037877  mov     rcx, cs:WPP_GLOBAL_Control
0x18003787e  lea     rbx, WPP_GLOBAL_Control
0x180037885  cmp     rcx, rbx
0x180037888  jz      short loc_1800378A3
0x18003788a  test    byte ptr [rcx+1Ch], 4
0x18003788e  jz      short loc_1800378A3
0x180037890  lea     edx, [rax+18h]
0x180037893  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x18003789a  mov     rcx, [rcx+10h]
0x18003789e  call    WPP_SF_
0x1800378a3  call    cs:__imp_GetLastError
0x1800378aa  nop     dword ptr [rax+rax+00h]
0x1800378af  cmp     eax, 3
0x1800378b2  jnz     loc_180037967
0x1800378b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800378bf  cmp     rcx, rbx
0x1800378c2  jz      short loc_1800378DD
0x1800378c4  test    byte ptr [rcx+1Ch], 4
0x1800378c8  jz      short loc_1800378DD
0x1800378ca  lea     edx, [rax+15h]
0x1800378cd  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x1800378d4  mov     rcx, [rcx+10h]
0x1800378d8  call    WPP_SF_
0x1800378dd  cmp     esi, 7FFFFFFEh
0x1800378e3  jbe     short loc_1800378F4
0x1800378e5  mov     ebx, 80070057h
0x1800378ea  mov     [rbp+3F0h+var_250], r13w
0x1800378f2  jmp     short loc_180037946
0x1800378f4  mov     eax, esi
0x1800378f6  lea     rcx, [rbp+3F0h+Buffer]
0x1800378fa  lea     rdx, [rbp+3F0h+var_250]
0x180037901  test    rax, rax
0x180037904  jz      short loc_180037925
0x180037906  movzx   r8d, word ptr [rcx]
0x18003790a  test    r8w, r8w
0x18003790e  jz      short loc_180037925
0x180037910  add     rcx, 2
0x180037914  mov     [rdx], r8w
0x180037918  add     rdx, 2
0x18003791c  dec     rax
0x18003791f  sub     rdi, 1
0x180037923  jnz     short loc_180037901
0x180037925  mov     rax, rdi
0x180037928  neg     rax
0x18003792b  sbb     ebx, ebx
0x18003792d  not     ebx
0x18003792f  and     ebx, 8007007Ah
0x180037935  lea     rcx, [rdx-2]
0x180037939  test    rdi, rdi
0x18003793c  cmovnz  rcx, rdx
0x180037940  mov     [rcx], r13w
0x180037944  jnz     short loc_180037950
0x180037946  mov     r9d, 5DEh
0x18003794c  mov     ecx, ebx
0x18003794e  jmp     short loc_18003797E
0x180037950  lea     rdx, [rbp+3F0h+var_250]
0x180037957  lea     rdx, [rdx+r14*2]; lpString
0x18003795b  lea     rcx, [rbp+3F0h+var_250]; unsigned __int16 *
0x180037962  call    DPAPICreateNestedDirectories
0x180037967  lea     rcx, [rbp+3F0h+Buffer]; lpFile
0x18003796b  call    ?MigrateLegacyRecovery@@YAKPEAG@Z; MigrateLegacyRecovery(ushort *)
0x180037970  mov     ebx, eax
0x180037972  test    eax, eax
0x180037974  jz      short loc_1800379A1
0x180037976  mov     r9d, 5EBh
0x18003797c  mov     ecx, eax
0x18003797e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180037985  lea     rdx, aDwerror; "dwError"
0x18003798c  call    DebugTraceError
0x180037991  nop
0x180037992  lea     rcx, [rsp+4F0h+var_4A0]; this
0x180037997  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x18003799c  jmp     loc_18003778D
0x1800379a1  lea     rcx, [rsp+4F0h+var_4A0]; this
0x1800379a6  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x1800379ab  lea     r8, [rbp+3F0h+Buffer]; lpFile
0x1800379af  lea     rdx, aC80ed86a0d2840; "C80ED86A-0D28-40dc-B379-BB594E14EA1B"
0x1800379b6  mov     rdi, 0FFFFFFFF80000002h
0x1800379bd  mov     rcx, rdi; hKey
0x1800379c0  call    cs:__imp_RegLoadKeyW
0x1800379c7  nop     dword ptr [rax+rax+00h]
0x1800379cc  mov     ebx, eax
0x1800379ce  test    eax, eax
0x1800379d0  jz      short loc_1800379DD
0x1800379d2  mov     r9d, 5F6h
0x1800379d8  jmp     loc_180037778
0x1800379dd  mov     [rsp+4F0h+lpdwDisposition], r13; lpdwDisposition
0x1800379e2  mov     [rsp+4F0h+phkResult], r12; phkResult
0x1800379e7  mov     [rsp+4F0h+hTemplateFile], r13; lpSecurityAttributes
0x1800379ec  mov     [rsp+4F0h+dwFlagsAndAttributes], r15d; samDesired
0x1800379f1  mov     [rsp+4F0h+dwCreationDisposition], r13d; dwOptions
0x1800379f6  lea     r9, Class; lpClass
0x1800379fd  xor     r8d, r8d; Reserved
0x180037a00  lea     rdx, aC80ed86a0d2840; "C80ED86A-0D28-40dc-B379-BB594E14EA1B"
0x180037a07  mov     rcx, rdi; hKey
0x180037a0a  call    cs:__imp_RegCreateKeyExW
0x180037a11  nop     dword ptr [rax+rax+00h]
0x180037a16  mov     ebx, eax
0x180037a18  test    eax, eax
0x180037a1a  jz      short loc_180037A27
0x180037a1c  mov     r9d, 605h
0x180037a22  jmp     loc_180037778
0x180037a27  xor     eax, eax
0x180037a29  mov     rcx, [rbp+3F0h+var_40]
0x180037a30  xor     rcx, rsp; StackCookie
0x180037a33  call    __security_check_cookie
0x180037a38  mov     rbx, [rsp+4F0h+arg_10]
0x180037a40  add     rsp, 4C0h
0x180037a47  pop     r15
0x180037a49  pop     r14
0x180037a4b  pop     r13
0x180037a4d  pop     r12
0x180037a4f  pop     rdi
0x180037a50  pop     rsi
0x180037a51  pop     rbp
0x180037a52  retn
```
