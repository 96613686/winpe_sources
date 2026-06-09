# SavePolicyState(_GPOINFO *)

- ea: `0x18009dfc8`
- end: `0x18009e369`
- name: `?SavePolicyState@@YAKPEAU_GPOINFO@@@Z`
- size: `929`
- prototype: `unsigned int __fastcall(struct _GPOINFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ce5c`

## callees

- `0x180003770`
- `0x18001dcf0`
- `0x18002ddc4`
- `0x18002e188`
- `0x180075ec0`
- `0x18007d320`
- `0x18009dfc8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e33e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e33e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e030`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e2e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e2e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e0e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e1ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e20b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e23d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e0e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e1ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e20b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e23d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009e0a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009e0a8`

## string_xrefs

- `0x18009e231`: `SlowLink`
- `0x18009e294`: `GPLink-List`
- `0x18009e2b7`: `Loopback-GPLink-List`
- `0x18009e302`: `SavePolicyState: Failed Registry operation with %d`
- `0x18009e32a`: `SavePolicyState: Failed Registry operation with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SavePolicyState(struct _GPOINFO *a1)
{
  unsigned int v2; // ecx
  char v3; // r15
  const BYTE *v4; // r13
  const BYTE *v5; // r12
  DWORD LastError; // ebx
  int v7; // r15d
  const wchar_t *v8; // r9
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // r14
  __int64 v12; // rcx
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v16; // [rsp+60h] [rbp-A0h]
  BYTE Data[4]; // [rsp+64h] [rbp-9Ch] BYREF
  BYTE v18[8]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = *(_DWORD *)a1;
  v3 = v2;
  hKey = 0;
  v4 = (const BYTE *)&DomainName;
  v5 = (const BYTE *)&DomainName;
  if ( *((_QWORD *)a1 + 28) )
    v5 = (const BYTE *)*((_QWORD *)a1 + 28);
  if ( *((_QWORD *)a1 + 3) )
    v4 = (const BYTE *)*((_QWORD *)a1 + 3);
  *(_DWORD *)v18 = (v2 >> 18) & 1;
  LastError = GetLastError();
  v16 = LastError;
  v7 = v3 & 1;
  v8 = L"Machine";
  if ( !v7 )
    v8 = (const wchar_t *)*((_QWORD *)a1 + 9);
  v9 = StringCchPrintfW(SubKey, 0x105u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\State\\%ws", v8);
  if ( v9 < 0 )
  {
    LastError = (unsigned __int16)v9;
    v10 = (unsigned __int16)v9;
    v16 = (unsigned __int16)v9;
    goto LABEL_33;
  }
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( !v10 )
  {
    if ( (*(_DWORD *)a1 & 0x10000) != 0
      || (*(_DWORD *)Data = 0, (v10 = RegSetValueExW(hKey, L"ForceForegroundLogging", 0, 4u, Data, 4u)) == 0) )
    {
      cbData = 0;
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)&v5[2 * v12] );
      if ( (int)ULongLongToULong(2 * v12 + 2, &cbData) < 0 )
        goto LABEL_15;
      v10 = RegSetValueExW(hKey, L"Site-Name", 0, 1u, v5, cbData);
      if ( v10 )
        goto LABEL_33;
      cbData = 0;
      do
        ++v11;
      while ( *(_WORD *)&v4[2 * v11] );
      if ( (int)ULongLongToULong(2 * v11 + 2, &cbData) < 0 )
      {
LABEL_15:
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
          }
        }
      }
      else
      {
        v10 = RegSetValueExW(hKey, L"Distinguished-Name", 0, 1u, v4, cbData);
        if ( !v10 )
        {
          v10 = RegSetValueExW(hKey, L"SlowLink", 0, 4u, v18, 4u);
          if ( !v10 )
          {
            v10 = RegSaveGPOs(hKey, *((const BYTE **)a1 + 20), v7, L"GPO-List");
            if ( !v10 && (v7 || (v10 = RegSaveGPOs(hKey, *((const BYTE **)a1 + 22), 0, L"Loopback-GPO-List")) == 0) )
            {
              v10 = RegSaveGPL(hKey, *((struct _SCOPEOFMGMT **)a1 + 19), L"GPLink-List");
              if ( !v10 && !v7 )
                v10 = RegSaveGPL(hKey, *((struct _SCOPEOFMGMT **)a1 + 21), L"Loopback-GPLink-List");
            }
          }
        }
      }
    }
  }
LABEL_33:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v10 && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"SavePolicyState: Failed Registry operation with %d", v10);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"SavePolicyState: Failed Registry operation with %d", v10);
    }
  }
  SetLastError(LastError);
  return v10;
}

```

## disassembly

```asm
0x18009dfc8  push    rbp
0x18009dfca  push    rbx
0x18009dfcb  push    rsi
0x18009dfcc  push    rdi
0x18009dfcd  push    r12
0x18009dfcf  push    r13
0x18009dfd1  push    r14
0x18009dfd3  push    r15
0x18009dfd5  lea     rbp, [rsp-198h]
0x18009dfdd  sub     rsp, 298h
0x18009dfe4  mov     rax, cs:__security_cookie
0x18009dfeb  xor     rax, rsp
0x18009dfee  mov     [rbp+1D0h+var_50], rax
0x18009dff5  mov     rsi, rcx
0x18009dff8  mov     ecx, [rcx]
0x18009dffa  mov     r15d, ecx
0x18009dffd  xor     r14d, r14d
0x18009e000  mov     [rsp+2D0h+hKey], r14
0x18009e005  mov     rax, [rsi+0E0h]
0x18009e00c  lea     r13, DomainName
0x18009e013  mov     r12, r13
0x18009e016  test    rax, rax
0x18009e019  cmovnz  r12, rax
0x18009e01d  cmp     [rsi+18h], r14
0x18009e021  cmovnz  r13, [rsi+18h]
0x18009e026  shr     ecx, 12h
0x18009e029  and     ecx, 1
0x18009e02c  mov     dword ptr [rsp+2D0h+var_268], ecx
0x18009e030  call    cs:__imp_GetLastError
0x18009e036  mov     ebx, eax
0x18009e038  mov     [rsp+2D0h+var_270], eax
0x18009e03c  and     r15d, 1
0x18009e040  lea     r9, aMachine; "Machine"
0x18009e047  jnz     short loc_18009E04D
0x18009e049  mov     r9, [rsi+48h]
0x18009e04d  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009e054  mov     edx, 105h; unsigned __int64
0x18009e059  lea     rcx, [rsp+2D0h+SubKey]; unsigned __int16 *
0x18009e05e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009e063  test    eax, eax
0x18009e065  jns     short loc_18009E075
0x18009e067  movzx   ebx, ax
0x18009e06a  mov     edi, ebx
0x18009e06c  mov     [rsp+2D0h+var_270], ebx
0x18009e070  jmp     loc_18009E2D6
0x18009e075  mov     [rsp+2D0h+lpdwDisposition], r14; lpdwDisposition
0x18009e07a  lea     rax, [rsp+2D0h+hKey]
0x18009e07f  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18009e084  mov     [rsp+2D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18009e089  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x18009e091  mov     [rsp+2D0h+dwOptions], r14d; dwOptions
0x18009e096  xor     r9d, r9d; lpClass
0x18009e099  xor     r8d, r8d; Reserved
0x18009e09c  lea     rdx, [rsp+2D0h+SubKey]; lpSubKey
0x18009e0a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009e0a8  call    cs:__imp_RegCreateKeyExW
0x18009e0ae  mov     edi, eax
0x18009e0b0  test    eax, eax
0x18009e0b2  jnz     loc_18009E2D6
0x18009e0b8  lea     ecx, [rax+4]
0x18009e0bb  test    dword ptr [rsi], 10000h
0x18009e0c1  jnz     short loc_18009E0F8
0x18009e0c3  mov     dword ptr [rsp+2D0h+Data], r14d
0x18009e0c8  mov     [rsp+2D0h+samDesired], ecx; cbData
0x18009e0cc  lea     rax, [rsp+2D0h+Data]
0x18009e0d1  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18009e0d6  mov     r9d, ecx; dwType
0x18009e0d9  xor     r8d, r8d; Reserved
0x18009e0dc  lea     rdx, aForceforegroun; "ForceForegroundLogging"
0x18009e0e3  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18009e0e8  call    cs:__imp_RegSetValueExW
0x18009e0ee  mov     edi, eax
0x18009e0f0  test    eax, eax
0x18009e0f2  jnz     loc_18009E2D6
0x18009e0f8  mov     [rsp+2D0h+cbData], r14d
0x18009e0fd  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009e101  mov     rcx, r14
0x18009e104  xor     r9d, r9d
0x18009e107  inc     rcx
0x18009e10a  cmp     [r12+rcx*2], r9w
0x18009e10f  jnz     short loc_18009E107
0x18009e111  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x18009e119  lea     rdx, [rsp+2D0h+cbData]; unsigned int *
0x18009e11e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18009e123  test    eax, eax
0x18009e125  jns     short loc_18009E189
0x18009e127  xor     r14d, r14d
0x18009e12a  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18009e131  jz      loc_18009E2D6
0x18009e137  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009e13e  test    rax, rax
0x18009e141  jz      short loc_18009E159
0x18009e143  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x18009e14a  mov     ecx, 2
0x18009e14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e154  jmp     loc_18009E2D6
0x18009e159  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18009e160  jz      loc_18009E2D6
0x18009e166  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009e16d  jz      loc_18009E2D6
0x18009e173  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x18009e17a  mov     ecx, 2; unsigned int
0x18009e17f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009e184  jmp     loc_18009E2D6
0x18009e189  mov     eax, [rsp+2D0h+cbData]
0x18009e18d  mov     [rsp+2D0h+samDesired], eax; cbData
0x18009e191  mov     qword ptr [rsp+2D0h+dwOptions], r12; lpData
0x18009e196  mov     r12d, 1
0x18009e19c  mov     r9d, r12d; dwType
0x18009e19f  xor     r8d, r8d; Reserved
0x18009e1a2  lea     rdx, aSiteName; "Site-Name"
0x18009e1a9  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18009e1ae  call    cs:__imp_RegSetValueExW
0x18009e1b4  mov     edi, eax
0x18009e1b6  xor     eax, eax
0x18009e1b8  test    edi, edi
0x18009e1ba  jnz     loc_18009E2D3
0x18009e1c0  mov     [rsp+2D0h+cbData], eax
0x18009e1c4  inc     r14
0x18009e1c7  cmp     [r13+r14*2+0], ax
0x18009e1cd  jnz     short loc_18009E1C4
0x18009e1cf  lea     rcx, ds:2[r14*2]; unsigned __int64
0x18009e1d7  lea     rdx, [rsp+2D0h+cbData]; unsigned int *
0x18009e1dc  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18009e1e1  xor     r14d, r14d
0x18009e1e4  test    eax, eax
0x18009e1e6  js      loc_18009E12A
0x18009e1ec  mov     eax, [rsp+2D0h+cbData]
0x18009e1f0  mov     [rsp+2D0h+samDesired], eax; cbData
0x18009e1f4  mov     qword ptr [rsp+2D0h+dwOptions], r13; lpData
0x18009e1f9  mov     r9d, r12d; dwType
0x18009e1fc  xor     r8d, r8d; Reserved
0x18009e1ff  lea     rdx, aDistinguishedN; "Distinguished-Name"
0x18009e206  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18009e20b  call    cs:__imp_RegSetValueExW
0x18009e211  mov     edi, eax
0x18009e213  test    eax, eax
0x18009e215  jnz     loc_18009E2D6
0x18009e21b  lea     r9d, [r14+4]; dwType
0x18009e21f  mov     [rsp+2D0h+samDesired], r9d; cbData
0x18009e224  lea     rax, [rsp+2D0h+var_268]
0x18009e229  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18009e22e  xor     r8d, r8d; Reserved
0x18009e231  lea     rdx, aSlowlink_0; "SlowLink"
0x18009e238  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18009e23d  call    cs:__imp_RegSetValueExW
0x18009e243  mov     edi, eax
0x18009e245  test    eax, eax
0x18009e247  jnz     loc_18009E2D6
0x18009e24d  lea     r9, aGpoList; "GPO-List"
0x18009e254  mov     r8d, r15d; int
0x18009e257  mov     rdx, [rsi+0A0h]; struct _GPCONTAINER *
0x18009e25e  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18009e263  call    ?RegSaveGPOs@@YAKPEAUHKEY__@@PEAU_GPCONTAINER@@HPEBG@Z; RegSaveGPOs(HKEY__ *,_GPCONTAINER *,int,ushort const *)
0x18009e268  mov     edi, eax
0x18009e26a  test    eax, eax
0x18009e26c  jnz     short loc_18009E2D6
0x18009e26e  test    r15d, r15d
0x18009e271  jnz     short loc_18009E294
0x18009e273  lea     r9, aLoopbackGpoLis; "Loopback-GPO-List"
0x18009e27a  xor     r8d, r8d; int
0x18009e27d  mov     rdx, [rsi+0B0h]; struct _GPCONTAINER *
0x18009e284  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18009e289  call    ?RegSaveGPOs@@YAKPEAUHKEY__@@PEAU_GPCONTAINER@@HPEBG@Z; RegSaveGPOs(HKEY__ *,_GPCONTAINER *,int,ushort const *)
0x18009e28e  mov     edi, eax
0x18009e290  test    eax, eax
0x18009e292  jnz     short loc_18009E2D6
0x18009e294  lea     r8, aGplinkList; "GPLink-List"
0x18009e29b  mov     rdx, [rsi+98h]; struct _SCOPEOFMGMT *
0x18009e2a2  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18009e2a7  call    ?RegSaveGPL@@YAKPEAUHKEY__@@PEAU_SCOPEOFMGMT@@PEBG@Z; RegSaveGPL(HKEY__ *,_SCOPEOFMGMT *,ushort const *)
0x18009e2ac  mov     edi, eax
0x18009e2ae  test    eax, eax
0x18009e2b0  jnz     short loc_18009E2D6
0x18009e2b2  test    r15d, r15d
0x18009e2b5  jnz     short loc_18009E2D6
0x18009e2b7  lea     r8, aLoopbackGplink; "Loopback-GPLink-List"
0x18009e2be  mov     rdx, [rsi+0A8h]; struct _SCOPEOFMGMT *
0x18009e2c5  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18009e2ca  call    ?RegSaveGPL@@YAKPEAUHKEY__@@PEAU_SCOPEOFMGMT@@PEBG@Z; RegSaveGPL(HKEY__ *,_SCOPEOFMGMT *,ushort const *)
0x18009e2cf  mov     edi, eax
0x18009e2d1  jmp     short loc_18009E2D6
0x18009e2d3  xor     r14d, r14d
0x18009e2d6  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18009e2db  test    rcx, rcx
0x18009e2de  jz      short loc_18009E2E6
0x18009e2e0  call    cs:__imp_RegCloseKey
0x18009e2e6  test    edi, edi
0x18009e2e8  jz      short loc_18009E33C
0x18009e2ea  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18009e2f1  jz      short loc_18009E33C
0x18009e2f3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009e2fa  test    rax, rax
0x18009e2fd  jz      short loc_18009E315
0x18009e2ff  mov     r8d, edi
0x18009e302  lea     rdx, aSavepolicystat; "SavePolicyState: Failed Registry operat"...
0x18009e309  mov     ecx, 2
0x18009e30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e313  jmp     short loc_18009E33C
0x18009e315  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18009e31c  jz      short loc_18009E33C
0x18009e31e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009e325  jz      short loc_18009E33C
0x18009e327  mov     r8d, edi
0x18009e32a  lea     rdx, aSavepolicystat; "SavePolicyState: Failed Registry operat"...
0x18009e331  mov     ecx, 2; unsigned int
0x18009e336  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009e33b  nop
0x18009e33c  mov     ecx, ebx; dwErrCode
0x18009e33e  call    cs:__imp_SetLastError
0x18009e344  mov     eax, edi
0x18009e346  mov     rcx, [rbp+1D0h+var_50]
0x18009e34d  xor     rcx, rsp; StackCookie
0x18009e350  call    __security_check_cookie
0x18009e355  add     rsp, 298h
0x18009e35c  pop     r15
0x18009e35e  pop     r14
0x18009e360  pop     r13
0x18009e362  pop     r12
0x18009e364  pop     rdi
0x18009e365  pop     rsi
0x18009e366  pop     rbx
0x18009e367  pop     rbp
0x18009e368  retn
```
