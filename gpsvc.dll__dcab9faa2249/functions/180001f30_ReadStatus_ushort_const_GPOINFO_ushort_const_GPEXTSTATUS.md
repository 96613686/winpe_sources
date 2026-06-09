# ReadStatus(ushort const *,_GPOINFO *,ushort const *,_GPEXTSTATUS *)

- ea: `0x180001f30`
- end: `0x180002528`
- name: `?ReadStatus@@YAXPEBGPEAU_GPOINFO@@0PEAU_GPEXTSTATUS@@@Z`
- size: `1528`
- prototype: `void(const unsigned __int16 *, struct _GPOINFO *, const unsigned __int16 *, struct _GPEXTSTATUS *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800016d0`
- `0x180058f20`
- `0x18005ce5c`
- `0x18006a2e0`
- `0x18009db40`

## callees

- `0x180001f30`
- `0x180003770`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000200d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000200d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000251c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000251c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001fe2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001fe2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002089`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800020c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002107`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002140`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000217d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800021bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002089`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800020c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002107`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002140`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000217d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800021bd`

## string_xrefs

- `0x180001fa7`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\Status\GPExtensions\%ws`
- `0x180002042`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\Status\%ws\GPExtensions\%ws`
- `0x180002134`: `PrevSlowLink`
- `0x180002241`: `ReadStatus: Failed to open reg key with %d.`
- `0x180002274`: `ReadStatus: Failed to open reg key with %d.`
- `0x1800022ae`: `ReadStatus: Failed to read status reg value with %d.`
- `0x1800022e1`: `ReadStatus: Failed to read status reg value with %d.`
- `0x180002315`: `ReadStatus: Failed to read rsop status reg value with %d.`
- `0x18000233d`: `ReadStatus: Failed to read rsop status reg value with %d.`
- `0x18000220d`: `ReadStatus: Failed to read time reg value with %d.`
- `0x18000237d`: `ReadStatus: Failed to read time reg value with %d.`
- `0x1800023b4`: `ReadStatus: Failed to read slowlink reg value with %d.`
- `0x1800023ea`: `ReadStatus: Failed to read slowlink reg value with %d.`
- `0x18000241b`: `ReadStatus: Failed to read rsop logging reg value with %d.`
- `0x180002451`: `ReadStatus: Failed to read rsop logging reg value with %d.`
- `0x180002482`: `ReadStatus: Failed to read ForceRefreshFG value with %d.`
- `0x1800024b8`: `ReadStatus: Failed to read ForceRefreshFG value with %d.`
- `0x1800024d3`: `ReadStatus: Read Extension's Previous status successfully.`
- `0x180002506`: `ReadStatus: Read Extension's Previous status successfully.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ReadStatus(const unsigned __int16 *a1, struct _GPOINFO *a2, const unsigned __int16 *a3, BYTE *a4)
{
  DWORD LastError; // ebx
  int v9; // eax
  int v10; // esi
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // edi
  DWORD v14; // ecx
  unsigned int v15; // edi
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  void (*v20)(unsigned int, const unsigned __int16 *, ...); // r9
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v24; // [rsp+40h] [rbp-C0h]
  WCHAR SubKey[400]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  LastError = GetLastError();
  v24 = LastError;
  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 12) = 0;
  if ( a3 )
    v9 = StringCchPrintfW(
           SubKey,
           0x190u,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Status\\%ws\\GPExtensions\\%ws",
           a3,
           a1);
  else
    v9 = StringCchPrintfW(
           SubKey,
           0x190u,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Status\\GPExtensions\\%ws",
           a1);
  if ( v9 < 0 )
  {
    v14 = 122;
    goto LABEL_12;
  }
  v10 = 0;
  if ( a3 )
    v11 = -2147483646;
  else
    v11 = *((_QWORD *)a2 + 5);
  v12 = RegOpenKeyExW((HKEY)v11, SubKey, 0, 0x20019u, &hKey);
  v13 = v12;
  if ( !v12 )
  {
    cbData = 4;
    v13 = RegQueryValueExW(hKey, L"Status", 0, &Type, a4 + 8, &cbData);
    if ( v13 )
    {
      if ( v13 != 2 && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"ReadStatus: Failed to read status reg value with %d.", v13);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ReadStatus: Failed to read status reg value with %d.", v13);
          LastError = v13;
          goto LABEL_9;
        }
      }
      goto LABEL_8;
    }
    cbData = 4;
    v15 = RegQueryValueExW(hKey, L"RsopStatus", 0, &Type, a4 + 12, &cbData);
    if ( v15 )
    {
      if ( v15 != 2 && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"ReadStatus: Failed to read rsop status reg value with %d.", v15);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ReadStatus: Failed to read rsop status reg value with %d.", v15);
        }
      }
      *((_DWORD *)a4 + 3) = -2147024846;
      LastError = v15;
      v24 = v15;
    }
    cbData = 4;
    v16 = RegQueryValueExW(hKey, L"LastPolicyTime", 0, &Type, a4 + 16, &cbData);
    if ( v16 )
    {
      LastError = v16;
      v24 = v16;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"ReadStatus: Failed to read time reg value with %d.", v16);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ReadStatus: Failed to read time reg value with %d.", v16);
        }
      }
      goto LABEL_9;
    }
    cbData = 4;
    v17 = RegQueryValueExW(hKey, L"PrevSlowLink", 0, &Type, a4, &cbData);
    if ( v17 )
    {
      LastError = v17;
      v24 = v17;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"ReadStatus: Failed to read slowlink reg value with %d.", v17);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ReadStatus: Failed to read slowlink reg value with %d.", v17);
        }
      }
      goto LABEL_9;
    }
    cbData = 4;
    v18 = RegQueryValueExW(hKey, L"PrevRsopLogging", 0, &Type, a4 + 4, &cbData);
    if ( v18 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"ReadStatus: Failed to read rsop logging reg value with %d.", v18);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"ReadStatus: Failed to read rsop logging reg value with %d.", v18);
      }
    }
    *((_DWORD *)a4 + 6) = 0;
    cbData = 4;
    v19 = RegQueryValueExW(hKey, L"ForceRefreshFG", 0, &Type, a4 + 24, &cbData);
    if ( v19 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
      {
LABEL_24:
        v10 = 1;
        goto LABEL_9;
      }
      v20 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"ReadStatus: Failed to read ForceRefreshFG value with %d.", v19);
      }
      else
      {
        if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        {
LABEL_23:
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( v20 )
            {
              v20(4u, L"ReadStatus: Read Extension's Previous status successfully.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"ReadStatus: Read Extension's Previous status successfully.");
            }
          }
          goto LABEL_24;
        }
        RedirectDebugMsg(4u, L"ReadStatus: Failed to read ForceRefreshFG value with %d.", v19);
      }
    }
    v20 = g_lpDebugMsg;
    goto LABEL_23;
  }
  if ( v12 != 2 && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ReadStatus: Failed to open reg key with %d.", v12);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ReadStatus: Failed to open reg key with %d.", v12);
    }
  }
LABEL_8:
  LastError = v13;
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
  *((_DWORD *)a4 + 5) = v10;
  v14 = LastError;
LABEL_12:
  SetLastError(v14);
}

```

## disassembly

```asm
0x180001f30  push    rbp
0x180001f32  push    rbx
0x180001f33  push    rsi
0x180001f34  push    rdi
0x180001f35  push    r12
0x180001f37  push    r14
0x180001f39  push    r15
0x180001f3b  lea     rbp, [rsp-280h]
0x180001f43  sub     rsp, 380h
0x180001f4a  mov     rax, cs:__security_cookie
0x180001f51  xor     rax, rsp
0x180001f54  mov     [rbp+2B0h+var_40], rax
0x180001f5b  mov     r14, r9
0x180001f5e  mov     rdi, r8
0x180001f61  mov     r15, rdx
0x180001f64  mov     rsi, rcx
0x180001f67  xor     r12d, r12d
0x180001f6a  mov     [rsp+3B0h+hKey], r12
0x180001f6f  mov     [rsp+3B0h+Type], r12d
0x180001f74  mov     [rsp+3B0h+cbData], r12d
0x180001f79  call    cs:__imp_GetLastError
0x180001f7f  mov     ebx, eax
0x180001f81  mov     [rsp+3B0h+var_370], eax
0x180001f85  xorps   xmm0, xmm0
0x180001f88  movups  xmmword ptr [r14], xmm0
0x180001f8c  movups  xmmword ptr [r14+0Ch], xmm0
0x180001f91  mov     edx, 190h; unsigned __int64
0x180001f96  lea     rcx, [rsp+3B0h+SubKey]; unsigned __int16 *
0x180001f9b  test    rdi, rdi
0x180001f9e  jnz     loc_18000203A
0x180001fa4  mov     r9, rsi
0x180001fa7  lea     r8, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001fae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001fb3  test    eax, eax
0x180001fb5  js      loc_180002053
0x180001fbb  mov     esi, r12d
0x180001fbe  test    rdi, rdi
0x180001fc1  jz      short loc_180002034
0x180001fc3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001fca  lea     rax, [rsp+3B0h+hKey]
0x180001fcf  mov     [rsp+3B0h+phkResult], rax; phkResult
0x180001fd4  mov     r9d, 20019h; samDesired
0x180001fda  xor     r8d, r8d; ulOptions
0x180001fdd  lea     rdx, [rsp+3B0h+SubKey]; lpSubKey
0x180001fe2  call    cs:__imp_RegOpenKeyExW
0x180001fe8  mov     edi, eax
0x180001fea  test    eax, eax
0x180001fec  jz      short loc_18000205A
0x180001fee  cmp     eax, 2
0x180001ff1  jnz     loc_180002226
0x180001ff7  mov     ebx, edi
0x180001ff9  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180001ffe  test    rcx, rcx
0x180002001  jnz     loc_18000251C
0x180002007  mov     [r14+14h], esi
0x18000200b  mov     ecx, ebx; dwErrCode
0x18000200d  call    cs:__imp_SetLastError
0x180002013  mov     rcx, [rbp+2B0h+var_40]
0x18000201a  xor     rcx, rsp; StackCookie
0x18000201d  call    __security_check_cookie
0x180002022  add     rsp, 380h
0x180002029  pop     r15
0x18000202b  pop     r14
0x18000202d  pop     r12
0x18000202f  pop     rdi
0x180002030  pop     rsi
0x180002031  pop     rbx
0x180002032  pop     rbp
0x180002033  retn
0x180002034  mov     rcx, [r15+28h]
0x180002038  jmp     short loc_180001FCA
0x18000203a  mov     [rsp+3B0h+phkResult], rsi
0x18000203f  mov     r9, rdi
0x180002042  lea     r8, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180002049  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000204e  jmp     loc_180001FB3
0x180002053  mov     ecx, 7Ah ; 'z'
0x180002058  jmp     short loc_18000200D
0x18000205a  mov     [rsp+3B0h+cbData], 4
0x180002062  lea     rax, [r14+8]
0x180002066  lea     rcx, [rsp+3B0h+cbData]
0x18000206b  mov     [rsp+3B0h+lpcbData], rcx; lpcbData
0x180002070  mov     [rsp+3B0h+phkResult], rax; lpData
0x180002075  lea     r9, [rsp+3B0h+Type]; lpType
0x18000207a  xor     r8d, r8d; lpReserved
0x18000207d  lea     rdx, aStatus_0; "Status"
0x180002084  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180002089  call    cs:__imp_RegQueryValueExW
0x18000208f  mov     edi, eax
0x180002091  test    eax, eax
0x180002093  jnz     loc_18000228A
0x180002099  mov     [rsp+3B0h+cbData], 4
0x1800020a1  lea     r15, [r14+0Ch]
0x1800020a5  lea     rax, [rsp+3B0h+cbData]
0x1800020aa  mov     [rsp+3B0h+lpcbData], rax; lpcbData
0x1800020af  mov     [rsp+3B0h+phkResult], r15; lpData
0x1800020b4  lea     r9, [rsp+3B0h+Type]; lpType
0x1800020b9  xor     r8d, r8d; lpReserved
0x1800020bc  lea     rdx, aRsopstatus; "RsopStatus"
0x1800020c3  mov     rcx, [rsp+3B0h+hKey]; hKey
0x1800020c8  call    cs:__imp_RegQueryValueExW
0x1800020ce  mov     edi, eax
0x1800020d0  test    eax, eax
0x1800020d2  jnz     loc_1800022F9
0x1800020d8  mov     [rsp+3B0h+cbData], 4
0x1800020e0  lea     rax, [r14+10h]
0x1800020e4  lea     rcx, [rsp+3B0h+cbData]
0x1800020e9  mov     [rsp+3B0h+lpcbData], rcx; lpcbData
0x1800020ee  mov     [rsp+3B0h+phkResult], rax; lpData
0x1800020f3  lea     r9, [rsp+3B0h+Type]; lpType
0x1800020f8  xor     r8d, r8d; lpReserved
0x1800020fb  lea     rdx, aLastpolicytime; "LastPolicyTime"
0x180002102  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180002107  call    cs:__imp_RegQueryValueExW
0x18000210d  test    eax, eax
0x18000210f  jnz     loc_1800021E8
0x180002115  mov     [rsp+3B0h+cbData], 4
0x18000211d  lea     rax, [rsp+3B0h+cbData]
0x180002122  mov     [rsp+3B0h+lpcbData], rax; lpcbData
0x180002127  mov     [rsp+3B0h+phkResult], r14; lpData
0x18000212c  lea     r9, [rsp+3B0h+Type]; lpType
0x180002131  xor     r8d, r8d; lpReserved
0x180002134  lea     rdx, aPrevslowlink; "PrevSlowLink"
0x18000213b  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180002140  call    cs:__imp_RegQueryValueExW
0x180002146  test    eax, eax
0x180002148  jnz     loc_180002393
0x18000214e  mov     [rsp+3B0h+cbData], 4
0x180002156  lea     rax, [r14+4]
0x18000215a  lea     rcx, [rsp+3B0h+cbData]
0x18000215f  mov     [rsp+3B0h+lpcbData], rcx; lpcbData
0x180002164  mov     [rsp+3B0h+phkResult], rax; lpData
0x180002169  lea     r9, [rsp+3B0h+Type]; lpType
0x18000216e  xor     r8d, r8d; lpReserved
0x180002171  lea     rdx, aPrevrsoploggin; "PrevRsopLogging"
0x180002178  mov     rcx, [rsp+3B0h+hKey]; hKey
0x18000217d  call    cs:__imp_RegQueryValueExW
0x180002183  test    eax, eax
0x180002185  jnz     loc_180002400
0x18000218b  lea     rax, [r14+18h]
0x18000218f  mov     [rax], r12d
0x180002192  mov     [rsp+3B0h+cbData], 4
0x18000219a  lea     rcx, [rsp+3B0h+cbData]
0x18000219f  mov     [rsp+3B0h+lpcbData], rcx; lpcbData
0x1800021a4  mov     [rsp+3B0h+phkResult], rax; lpData
0x1800021a9  lea     r9, [rsp+3B0h+Type]; lpType
0x1800021ae  xor     r8d, r8d; lpReserved
0x1800021b1  lea     rdx, aForcerefreshfg; "ForceRefreshFG"
0x1800021b8  mov     rcx, [rsp+3B0h+hKey]; hKey
0x1800021bd  call    cs:__imp_RegQueryValueExW
0x1800021c3  test    eax, eax
0x1800021c5  jnz     loc_180002467
0x1800021cb  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800021d2  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800021d8  jnz     loc_1800024CE
0x1800021de  mov     esi, 1
0x1800021e3  jmp     loc_180001FF9
0x1800021e8  mov     ebx, eax
0x1800021ea  mov     [rsp+3B0h+var_370], eax
0x1800021ee  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800021f4  jz      loc_180001FF9
0x1800021fa  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180002201  test    r9, r9
0x180002204  jz      loc_180002360
0x18000220a  mov     r8d, eax
0x18000220d  lea     rdx, aReadstatusFail_4; "ReadStatus: Failed to read time reg val"...
0x180002214  mov     ecx, 4
0x180002219  mov     rax, r9
0x18000221c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002221  jmp     loc_180001FF9
0x180002226  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18000222c  jz      loc_180001FF7
0x180002232  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180002239  test    rax, rax
0x18000223c  jz      short loc_180002257
0x18000223e  mov     r8d, edi
0x180002241  lea     rdx, aReadstatusFail_2; "ReadStatus: Failed to open reg key with"...
0x180002248  mov     ecx, 4
0x18000224d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002252  jmp     loc_180001FF7
0x180002257  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18000225e  jz      loc_180001FF7
0x180002264  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000226b  jz      loc_180001FF7
0x180002271  mov     r8d, edi
0x180002274  lea     rdx, aReadstatusFail_2; "ReadStatus: Failed to open reg key with"...
0x18000227b  mov     ecx, 4; unsigned int
0x180002280  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180002285  jmp     loc_180001FF7
0x18000228a  cmp     edi, 2
0x18000228d  jz      loc_180001FF7
0x180002293  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180002299  jz      loc_180001FF7
0x18000229f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800022a6  test    rax, rax
0x1800022a9  jz      short loc_1800022C4
0x1800022ab  mov     r8d, edi
0x1800022ae  lea     rdx, aReadstatusFail; "ReadStatus: Failed to read status reg v"...
0x1800022b5  mov     ecx, 4
0x1800022ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022bf  jmp     loc_180001FF7
0x1800022c4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800022cb  jz      loc_180001FF7
0x1800022d1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800022d8  jz      loc_180001FF7
0x1800022de  mov     r8d, edi
0x1800022e1  lea     rdx, aReadstatusFail; "ReadStatus: Failed to read status reg v"...
0x1800022e8  mov     ecx, 4; unsigned int
0x1800022ed  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800022f2  mov     ebx, edi
0x1800022f4  jmp     loc_180001FF9
0x1800022f9  cmp     edi, 2
0x1800022fc  jz      short loc_18000234E
0x1800022fe  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180002304  jz      short loc_18000234E
0x180002306  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000230d  test    rax, rax
0x180002310  jz      short loc_180002328
0x180002312  mov     r8d, edi
0x180002315  lea     rdx, aReadstatusFail_1; "ReadStatus: Failed to read rsop status "...
0x18000231c  mov     ecx, 4
0x180002321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002326  jmp     short loc_18000234E
0x180002328  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18000232f  jz      short loc_18000234E
0x180002331  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180002338  jz      short loc_18000234E
0x18000233a  mov     r8d, edi
0x18000233d  lea     rdx, aReadstatusFail_1; "ReadStatus: Failed to read rsop status "...
0x180002344  mov     ecx, 4; unsigned int
0x180002349  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000234e  mov     dword ptr [r15], 80070032h
0x180002355  mov     ebx, edi
0x180002357  mov     [rsp+3B0h+var_370], ebx
0x18000235b  jmp     loc_1800020D8
0x180002360  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180002367  jz      loc_180001FF9
0x18000236d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180002374  jz      loc_180001FF9
0x18000237a  mov     r8d, eax
0x18000237d  lea     rdx, aReadstatusFail_4; "ReadStatus: Failed to read time reg val"...
0x180002384  mov     ecx, 4; unsigned int
0x180002389  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000238e  jmp     loc_180001FF9
0x180002393  mov     ebx, eax
0x180002395  mov     [rsp+3B0h+var_370], eax
0x180002399  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18000239f  jz      loc_180001FF9
0x1800023a5  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800023ac  test    r9, r9
0x1800023af  jz      short loc_1800023CD
0x1800023b1  mov     r8d, eax
0x1800023b4  lea     rdx, aReadstatusFail_0; "ReadStatus: Failed to read slowlink reg"...
0x1800023bb  mov     ecx, 4
0x1800023c0  mov     rax, r9
0x1800023c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c8  jmp     loc_180001FF9
0x1800023cd  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800023d4  jz      loc_180001FF9
0x1800023da  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800023e1  jz      loc_180001FF9
0x1800023e7  mov     r8d, eax
0x1800023ea  lea     rdx, aReadstatusFail_0; "ReadStatus: Failed to read slowlink reg"...
0x1800023f1  mov     ecx, 4; unsigned int
0x1800023f6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800023fb  jmp     loc_180001FF9
0x180002400  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180002406  jz      loc_18000218B
0x18000240c  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180002413  test    r9, r9
0x180002416  jz      short loc_180002434
0x180002418  mov     r8d, eax
0x18000241b  lea     rdx, aReadstatusFail_5; "ReadStatus: Failed to read rsop logging"...
0x180002422  mov     ecx, 4
0x180002427  mov     rax, r9
0x18000242a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000242f  jmp     loc_18000218B
0x180002434  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18000243b  jz      loc_18000218B
0x180002441  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180002448  jz      loc_18000218B
0x18000244e  mov     r8d, eax
0x180002451  lea     rdx, aReadstatusFail_5; "ReadStatus: Failed to read rsop logging"...
0x180002458  mov     ecx, 4; unsigned int
0x18000245d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180002462  jmp     loc_18000218B
0x180002467  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18000246d  jz      loc_1800021DE
0x180002473  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000247a  test    r9, r9
0x18000247d  jz      short loc_18000249B
0x18000247f  mov     r8d, eax
0x180002482  lea     rdx, aReadstatusFail_3; "ReadStatus: Failed to read ForceRefresh"...
0x180002489  mov     ecx, 4
0x18000248e  mov     rax, r9
0x180002491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002496  jmp     loc_1800021CB
0x18000249b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800024a2  jz      loc_1800021D2
0x1800024a8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
  ... truncated ...
```
