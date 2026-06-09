# SaveMembershipList(_GPOINFO *,ushort const *,_TOKEN_GROUPS *)

- ea: `0x18002d9b8`
- end: `0x18002ddbc`
- name: `?SaveMembershipList@@YAXPEAU_GPOINFO@@PEBGPEAU_TOKEN_GROUPS@@@Z`
- size: `1028`
- prototype: `void __fastcall(struct _GPOINFO *, const unsigned __int16 *, struct _TOKEN_GROUPS *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800014e0`

## callees

- `0x180003770`
- `0x18001dcf0`
- `0x18002d9b8`
- `0x18002f6e0`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dd95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dd95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd8c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dc27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dd7c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dc27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dd7c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002db04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002db04`
- `ntdll!RtlFreeUnicodeString` at `0x18002dc34`
- `ntdll!RtlFreeUnicodeString` at `0x18002dc34`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18002dba1`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18002dba1`

## string_xrefs

- `0x18002db2a`: `SaveMemberList: Failed to create key with %d.`
- `0x18002db5a`: `SaveMemberList: Failed to create key with %d.`
- `0x18002dd2b`: `SaveMembershipList: RtlConvertSidToUnicodeString failed, status = 0x%x`
- `0x18002dd49`: `SaveMembershipList: RtlConvertSidToUnicodeString failed, status = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SaveMembershipList(struct _GPOINFO *a1, const unsigned __int16 *a2, struct _TOKEN_GROUPS *a3)
{
  DWORD LastError; // ebx
  int v7; // eax
  DWORD v8; // ecx
  __int64 v9; // rdi
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // r8
  void (*v13)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v14; // rdx
  DWORD i; // edi
  NTSTATUS v16; // eax
  unsigned __int64 v17; // rcx
  const BYTE *v18; // r9
  unsigned int v19; // esi
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v21; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v22; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[32]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[256]; // [rsp+C0h] [rbp-40h] BYREF

  *(_DWORD *)Data = 0;
  dwDisposition = 0;
  UnicodeString = 0;
  hKey = 0;
  LastError = GetLastError();
  v22 = LastError;
  if ( a2 )
    v7 = StringCchPrintfW(
           SubKey,
           0xFAu,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\%ws\\GroupMembership",
           a2);
  else
    v7 = StringCchPrintfW(SubKey, 0xFAu, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\GroupMembership");
  if ( v7 < 0 )
  {
    v8 = (unsigned __int16)v7;
    goto LABEL_57;
  }
  v9 = -2147483646;
  v10 = -2147483646;
  if ( !a2 )
    v10 = *((_QWORD *)a1 + 5);
  if ( GPRegDelnode((HKEY)v10, SubKey) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"SaveMembershipList: GPRegDelnode failed.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"SaveMembershipList: GPRegDelnode failed.");
      }
    }
    goto LABEL_56;
  }
  if ( !a2 )
    v9 = *((_QWORD *)a1 + 5);
  v11 = RegCreateKeyExW((HKEY)v9, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
  v12 = v11;
  if ( v11 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v13 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v14 = L"SaveMemberList: Failed to create key with %d.";
LABEL_21:
        v13(2u, v14, v12);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"SaveMemberList: Failed to create key with %d.", v12);
      }
    }
    goto LABEL_54;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= a3->GroupCount )
    {
      RegSetValueExW(hKey, L"Count", 0, 4u, Data, 4u);
      goto LABEL_54;
    }
    if ( (a3->Groups[i].Attributes & 0xC0000000) != 0 )
      continue;
    ++*(_DWORD *)Data;
    v16 = RtlConvertSidToUnicodeString(&UnicodeString, a3->Groups[i].Sid, 1u);
    v12 = (unsigned int)v16;
    if ( v16 < 0 )
      break;
    StringCchPrintfW(ValueName, 0x1Eu, L"Group%d", (unsigned int)(*(_DWORD *)Data - 1));
    v21 = 0;
    v17 = -1;
    do
      ++v17;
    while ( UnicodeString.Buffer[v17] );
    if ( (int)ULongLongToULong(v17, &v21) < 0 )
    {
      LastError = GetLastError();
      v22 = LastError;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert unicodeStr.Buffer length to DWORD");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert unicodeStr.Buffer length to DWORD");
        }
      }
      goto LABEL_54;
    }
    v19 = RegSetValueExW(hKey, ValueName, 0, 1u, v18, 2 * (v18 != 0 ? v21 : 0) + 2);
    RtlFreeUnicodeString(&UnicodeString);
    if ( v19 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SaveMemberList: Failed to set value %ws with %d.", ValueName, v19);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SaveMemberList: Failed to set value %ws with %d.", ValueName, v19);
        }
      }
      goto LABEL_54;
    }
  }
  if ( !*(_DWORD *)&g_dwDebugLevel )
    goto LABEL_54;
  v13 = g_lpDebugMsg;
  if ( g_lpDebugMsg )
  {
    v14 = L"SaveMembershipList: RtlConvertSidToUnicodeString failed, status = 0x%x";
    goto LABEL_21;
  }
  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    RedirectDebugMsg(2u, L"SaveMembershipList: RtlConvertSidToUnicodeString failed, status = 0x%x", v12);
LABEL_54:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_56:
  v8 = LastError;
LABEL_57:
  SetLastError(v8);
}

```

## disassembly

```asm
0x18002d9b8  push    rbp
0x18002d9ba  push    rbx
0x18002d9bb  push    rsi
0x18002d9bc  push    rdi
0x18002d9bd  push    r12
0x18002d9bf  push    r14
0x18002d9c1  push    r15
0x18002d9c3  lea     rbp, [rsp-1D0h]
0x18002d9cb  sub     rsp, 2D0h
0x18002d9d2  mov     rax, cs:__security_cookie
0x18002d9d9  xor     rax, rsp
0x18002d9dc  mov     [rbp+200h+var_40], rax
0x18002d9e3  mov     r15, r8
0x18002d9e6  mov     rsi, rdx
0x18002d9e9  mov     r14, rcx
0x18002d9ec  xor     r12d, r12d
0x18002d9ef  mov     dword ptr [rsp+300h+Data], r12d
0x18002d9f4  mov     [rsp+300h+dwDisposition], r12d
0x18002d9f9  xorps   xmm0, xmm0
0x18002d9fc  movups  xmmword ptr [rsp+300h+UnicodeString.Length], xmm0
0x18002da01  mov     [rsp+300h+hKey], r12
0x18002da06  call    cs:__imp_GetLastError
0x18002da0c  mov     ebx, eax
0x18002da0e  mov     [rsp+300h+var_2A8], eax
0x18002da12  mov     edx, 0FAh; unsigned __int64
0x18002da17  lea     rcx, [rbp+200h+SubKey]; unsigned __int16 *
0x18002da1b  test    rsi, rsi
0x18002da1e  jnz     short loc_18002DA2E
0x18002da20  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002da27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002da2c  jmp     short loc_18002DA3D
0x18002da2e  mov     r9, rsi
0x18002da31  lea     r8, aSoftwareMicros_33; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002da38  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002da3d  test    eax, eax
0x18002da3f  jns     short loc_18002DA49
0x18002da41  movzx   ecx, ax
0x18002da44  jmp     loc_18002DD95
0x18002da49  mov     rdi, 0FFFFFFFF80000002h
0x18002da50  test    rsi, rsi
0x18002da53  mov     rcx, rdi
0x18002da56  jnz     short loc_18002DA5C
0x18002da58  mov     rcx, [r14+28h]; HKEY
0x18002da5c  lea     rdx, [rbp+200h+SubKey]; unsigned __int16 *
0x18002da60  call    ?GPRegDelnode@@YAKPEAUHKEY__@@PEBG@Z; GPRegDelnode(HKEY__ *,ushort const *)
0x18002da65  test    eax, eax
0x18002da67  jz      short loc_18002DAC8
0x18002da69  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002da70  jz      loc_18002DD93
0x18002da76  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002da7d  test    rax, rax
0x18002da80  jz      short loc_18002DA98
0x18002da82  lea     rdx, aSavemembership; "SaveMembershipList: GPRegDelnode failed"...
0x18002da89  mov     ecx, 4
0x18002da8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da93  jmp     loc_18002DD93
0x18002da98  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002da9f  jz      loc_18002DD93
0x18002daa5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002daac  jz      loc_18002DD93
0x18002dab2  lea     rdx, aSavemembership; "SaveMembershipList: GPRegDelnode failed"...
0x18002dab9  mov     ecx, 4; unsigned int
0x18002dabe  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002dac3  jmp     loc_18002DD93
0x18002dac8  test    rsi, rsi
0x18002dacb  jnz     short loc_18002DAD1
0x18002dacd  mov     rdi, [r14+28h]
0x18002dad1  lea     rax, [rsp+300h+dwDisposition]
0x18002dad6  mov     [rsp+300h+lpdwDisposition], rax; lpdwDisposition
0x18002dadb  lea     rax, [rsp+300h+hKey]
0x18002dae0  mov     [rsp+300h+phkResult], rax; phkResult
0x18002dae5  mov     [rsp+300h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18002daea  mov     [rsp+300h+samDesired], 20006h; samDesired
0x18002daf2  mov     [rsp+300h+dwOptions], r12d; dwOptions
0x18002daf7  xor     r9d, r9d; lpClass
0x18002dafa  xor     r8d, r8d; Reserved
0x18002dafd  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x18002db01  mov     rcx, rdi; hKey
0x18002db04  call    cs:__imp_RegCreateKeyExW
0x18002db0a  mov     r8d, eax
0x18002db0d  test    eax, eax
0x18002db0f  jz      short loc_18002DB70
0x18002db11  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002db18  jz      loc_18002DD82
0x18002db1e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002db25  test    rax, rax
0x18002db28  jz      short loc_18002DB40
0x18002db2a  lea     rdx, aSavememberlist_0; "SaveMemberList: Failed to create key wi"...
0x18002db31  mov     ecx, 2
0x18002db36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db3b  jmp     loc_18002DD82
0x18002db40  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002db47  jz      loc_18002DD82
0x18002db4d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002db54  jz      loc_18002DD82
0x18002db5a  lea     rdx, aSavememberlist_0; "SaveMemberList: Failed to create key wi"...
0x18002db61  mov     ecx, 2; unsigned int
0x18002db66  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002db6b  jmp     loc_18002DD82
0x18002db70  mov     edi, r12d
0x18002db73  cmp     edi, [r15]
0x18002db76  jnb     loc_18002DD55
0x18002db7c  mov     edx, edi
0x18002db7e  add     rdx, rdx
0x18002db81  test    dword ptr [r15+rdx*8+10h], 0C0000000h
0x18002db8a  jnz     loc_18002DC3E
0x18002db90  inc     dword ptr [rsp+300h+Data]
0x18002db94  mov     r8b, 1; AllocateDestinationString
0x18002db97  mov     rdx, [r15+rdx*8+8]; Sid
0x18002db9c  lea     rcx, [rsp+300h+UnicodeString]; UnicodeString
0x18002dba1  call    cs:__imp_RtlConvertSidToUnicodeString
0x18002dba7  mov     r8d, eax
0x18002dbaa  test    eax, eax
0x18002dbac  js      loc_18002DD16
0x18002dbb2  mov     r9d, dword ptr [rsp+300h+Data]
0x18002dbb7  dec     r9d
0x18002dbba  lea     r8, aGroupD; "Group%d"
0x18002dbc1  mov     edx, 1Eh; unsigned __int64
0x18002dbc6  lea     rcx, [rbp+200h+ValueName]; unsigned __int16 *
0x18002dbca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002dbcf  mov     [rsp+300h+var_2AC], r12d
0x18002dbd4  mov     r9, [rsp+300h+UnicodeString.Buffer]
0x18002dbd9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002dbdd  inc     rcx; unsigned __int64
0x18002dbe0  cmp     [r9+rcx*2], r12w
0x18002dbe5  jnz     short loc_18002DBDD
0x18002dbe7  lea     rdx, [rsp+300h+var_2AC]; unsigned int *
0x18002dbec  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002dbf1  test    eax, eax
0x18002dbf3  js      loc_18002DCB2
0x18002dbf9  mov     rax, r9
0x18002dbfc  neg     rax
0x18002dbff  sbb     eax, eax
0x18002dc01  and     eax, [rsp+300h+var_2AC]
0x18002dc05  lea     eax, ds:2[rax*2]
0x18002dc0c  mov     [rsp+300h+samDesired], eax; cbData
0x18002dc10  mov     qword ptr [rsp+300h+dwOptions], r9; lpData
0x18002dc15  mov     r9d, 1; dwType
0x18002dc1b  xor     r8d, r8d; Reserved
0x18002dc1e  lea     rdx, [rbp+200h+ValueName]; lpValueName
0x18002dc22  mov     rcx, [rsp+300h+hKey]; hKey
0x18002dc27  call    cs:__imp_RegSetValueExW
0x18002dc2d  mov     esi, eax
0x18002dc2f  lea     rcx, [rsp+300h+UnicodeString]; UnicodeString
0x18002dc34  call    cs:__imp_RtlFreeUnicodeString
0x18002dc3a  test    esi, esi
0x18002dc3c  jnz     short loc_18002DC45
0x18002dc3e  inc     edi
0x18002dc40  jmp     loc_18002DB73
0x18002dc45  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002dc4c  jz      loc_18002DD82
0x18002dc52  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002dc59  test    rax, rax
0x18002dc5c  jz      short loc_18002DC7B
0x18002dc5e  mov     r9d, esi
0x18002dc61  lea     r8, [rbp+200h+ValueName]
0x18002dc65  lea     rdx, aSavememberlist; "SaveMemberList: Failed to set value %ws"...
0x18002dc6c  mov     ecx, 2
0x18002dc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc76  jmp     loc_18002DD82
0x18002dc7b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002dc82  jz      loc_18002DD82
0x18002dc88  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002dc8f  jz      loc_18002DD82
0x18002dc95  mov     r9d, esi
0x18002dc98  lea     r8, [rbp+200h+ValueName]
0x18002dc9c  lea     rdx, aSavememberlist; "SaveMemberList: Failed to set value %ws"...
0x18002dca3  mov     ecx, 2; unsigned int
0x18002dca8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002dcad  jmp     loc_18002DD82
0x18002dcb2  call    cs:__imp_GetLastError
0x18002dcb8  mov     ebx, eax
0x18002dcba  mov     [rsp+300h+var_2A8], eax
0x18002dcbe  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002dcc5  jz      loc_18002DD82
0x18002dccb  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002dcd2  test    rax, rax
0x18002dcd5  jz      short loc_18002DCED
0x18002dcd7  lea     rdx, aSizettodwordFa_3; "SizeTToDWord() Failed to convert unicod"...
0x18002dcde  mov     ecx, 2
0x18002dce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dce8  jmp     loc_18002DD82
0x18002dced  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002dcf4  jz      loc_18002DD82
0x18002dcfa  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002dd01  jz      short loc_18002DD82
0x18002dd03  lea     rdx, aSizettodwordFa_3; "SizeTToDWord() Failed to convert unicod"...
0x18002dd0a  mov     ecx, 2; unsigned int
0x18002dd0f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002dd14  jmp     short loc_18002DD82
0x18002dd16  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002dd1d  jz      short loc_18002DD82
0x18002dd1f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002dd26  test    rax, rax
0x18002dd29  jz      short loc_18002DD37
0x18002dd2b  lea     rdx, aSavemembership_0; "SaveMembershipList: RtlConvertSidToUnic"...
0x18002dd32  jmp     loc_18002DB31
0x18002dd37  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002dd3e  jz      short loc_18002DD82
0x18002dd40  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002dd47  jz      short loc_18002DD82
0x18002dd49  lea     rdx, aSavemembership_0; "SaveMembershipList: RtlConvertSidToUnic"...
0x18002dd50  jmp     loc_18002DB61
0x18002dd55  mov     [rsp+300h+samDesired], 4; cbData
0x18002dd5d  lea     rax, [rsp+300h+Data]
0x18002dd62  mov     qword ptr [rsp+300h+dwOptions], rax; lpData
0x18002dd67  mov     r9d, 4; dwType
0x18002dd6d  xor     r8d, r8d; Reserved
0x18002dd70  lea     rdx, ValueName; "Count"
0x18002dd77  mov     rcx, [rsp+300h+hKey]; hKey
0x18002dd7c  call    cs:__imp_RegSetValueExW
0x18002dd82  mov     rcx, [rsp+300h+hKey]; hKey
0x18002dd87  test    rcx, rcx
0x18002dd8a  jz      short loc_18002DD93
0x18002dd8c  call    cs:__imp_RegCloseKey
0x18002dd92  nop
0x18002dd93  mov     ecx, ebx; dwErrCode
0x18002dd95  call    cs:__imp_SetLastError
0x18002dd9b  mov     rcx, [rbp+200h+var_40]
0x18002dda2  xor     rcx, rsp; StackCookie
0x18002dda5  call    __security_check_cookie
0x18002ddaa  add     rsp, 2D0h
0x18002ddb1  pop     r15
0x18002ddb3  pop     r14
0x18002ddb5  pop     r12
0x18002ddb7  pop     rdi
0x18002ddb8  pop     rsi
0x18002ddb9  pop     rbx
0x18002ddba  pop     rbp
0x18002ddbb  retn
```
