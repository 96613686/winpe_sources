# IsSlowLink(HKEY__ *,ulong,ulong,int *,ulong *,int *)

- ea: `0x18009a05c`
- end: `0x18009a4b1`
- name: `?IsSlowLink@@YAKPEAUHKEY__@@KKPEAHPEAK1@Z`
- size: `1109`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int, unsigned int, int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180098c40`

## callees

- `0x1800183d4`
- `0x18001ae40`
- `0x180075ec0`
- `0x18009a05c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a119`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a21e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a119`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a21e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a0d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a18d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a0d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a18d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a10f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a1c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a10f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a1c7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009a25d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009a25d`

## string_xrefs

- `0x18009a138`: `IsSlowLink: Bandwidth Threshold (WINLOGON) = %d.`
- `0x18009a160`: `IsSlowLink: Bandwidth Threshold (WINLOGON) = %d.`
- `0x18009a1e6`: `IsSlowLink: Bandwidth Threshold (SYSTEM) = %d.`
- `0x18009a20c`: `IsSlowLink: Bandwidth Threshold (SYSTEM) = %d.`
- `0x18009a248`: `SlowLinkDefaultFor3G`
- `0x18009a27c`: `IsSlowLink: WWAN Policy (SYSTEM) = %d.`
- `0x18009a2ab`: `IsSlowLink: WWAN Policy (SYSTEM) = %d.`
- `0x18009a2fd`: `IsSlowLink: Current Bandwidth < Bandwidth Threshold.`
- `0x18009a318`: `IsSlowLink: Current Bandwidth < Bandwidth Threshold.`
- `0x18009a339`: `IsSlowLink: Current Bandwidth >= Bandwidth Threshold.`
- `0x18009a34c`: `IsSlowLink: Current Bandwidth >= Bandwidth Threshold.`
- `0x18009a369`: `IsSlowLink: Current Bandwidth or Bandwidth Threshold is zero.`
- `0x18009a386`: `IsSlowLink: Current Bandwidth or Bandwidth Threshold is zero.`
- `0x18009a437`: `IsSlowLink: Slow Link set to true by virtue of a WWAN connection and policy.`
- `0x18009a454`: `IsSlowLink: Slow Link set to true by virtue of a WWAN connection and policy.`
- `0x18009a3e7`: `IsSlowLink: Connection Type is = %d.`
- `0x18009a412`: `IsSlowLink: Connection Type is = %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsSlowLink(HKEY hKey, unsigned int a2, unsigned int a3, int *a4, unsigned int *a5, int *a6)
{
  unsigned int *v10; // r14
  int *v11; // r12
  void (*v12)(unsigned int, const unsigned __int16 *, ...); // r9
  void *v13; // rdx
  void (*v14)(void *, unsigned int, const unsigned __int16 *, char **); // rcx
  unsigned int v15; // eax
  const wchar_t *v16; // rdx
  int v17; // r8d
  DWORD cbData; // [rsp+40h] [rbp-38h] BYREF
  unsigned int pvData; // [rsp+44h] [rbp-34h] BYREF
  DWORD Type; // [rsp+48h] [rbp-30h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v23[4]; // [rsp+58h] [rbp-20h] BYREF
  unsigned int Data; // [rsp+D8h] [rbp+60h] BYREF

  cbData = 0;
  Type = 0;
  hKeya = 0;
  pvData = 0;
  if ( a4 )
  {
    v10 = a5;
    if ( a5 )
    {
      v11 = a6;
      if ( a6 )
      {
        *a6 = 0;
        Data = 500;
        if ( !RegOpenKeyExW(hKey, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 0x20019u, &hKeya) )
        {
          cbData = 4;
          RegQueryValueExW(hKeya, L"GroupPolicyMinTransferRate", 0, &Type, (LPBYTE)&Data, &cbData);
          RegCloseKey(hKeya);
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"IsSlowLink: Bandwidth Threshold (WINLOGON) = %d.", Data);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"IsSlowLink: Bandwidth Threshold (WINLOGON) = %d.", Data);
            }
          }
        }
        if ( !RegOpenKeyExW(hKey, L"Software\\Policies\\Microsoft\\Windows\\System", 0, 0x20019u, &hKeya) )
        {
          cbData = 4;
          RegQueryValueExW(hKeya, L"GroupPolicyMinTransferRate", 0, &Type, (LPBYTE)&Data, &cbData);
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"IsSlowLink: Bandwidth Threshold (SYSTEM) = %d.", Data);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"IsSlowLink: Bandwidth Threshold (SYSTEM) = %d.", Data);
            }
          }
          RegCloseKey(hKeya);
        }
        cbData = 4;
        RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows\\System",
          L"SlowLinkDefaultFor3G",
          0x10u,
          &Type,
          &pvData,
          &cbData);
        v12 = g_lpDebugMsg;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"IsSlowLink: WWAN Policy (SYSTEM) = %d.", pvData);
          }
          else
          {
            v13 = g_lpDebugMsgContextInstance;
            v14 = g_lpDebugMsgContext;
            if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
            {
LABEL_27:
              v15 = Data;
              *v10 = Data;
              if ( a2 && v15 )
              {
                if ( a2 < v15 )
                {
                  *a4 = 1;
                  if ( !*(_DWORD *)&g_dwDebugLevel )
                    goto LABEL_66;
                  if ( !v12 )
                  {
                    if ( !v13 || !v14 )
                      goto LABEL_66;
                    RedirectDebugMsg(4u, L"IsSlowLink: Current Bandwidth < Bandwidth Threshold.");
                    goto LABEL_49;
                  }
                  v16 = L"IsSlowLink: Current Bandwidth < Bandwidth Threshold.";
                  goto LABEL_45;
                }
                *a4 = 0;
                v17 = *(_DWORD *)&g_dwDebugLevel;
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( v12 )
                  {
                    v16 = L"IsSlowLink: Current Bandwidth >= Bandwidth Threshold.";
LABEL_45:
                    v12(4u, v16);
                    goto LABEL_49;
                  }
                  if ( v13 && v14 )
                  {
                    RedirectDebugMsg(4u, L"IsSlowLink: Current Bandwidth >= Bandwidth Threshold.");
LABEL_49:
                    if ( *a4 )
                      goto LABEL_66;
                    v17 = *(_DWORD *)&g_dwDebugLevel;
                    v12 = g_lpDebugMsg;
                    v13 = g_lpDebugMsgContextInstance;
                    v14 = g_lpDebugMsgContext;
                  }
                }
              }
              else
              {
                *a4 = 0;
                v17 = *(_DWORD *)&g_dwDebugLevel;
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( v12 )
                  {
                    v16 = L"IsSlowLink: Current Bandwidth or Bandwidth Threshold is zero.";
                    goto LABEL_45;
                  }
                  if ( v13 && v14 )
                  {
                    RedirectDebugMsg(4u, L"IsSlowLink: Current Bandwidth or Bandwidth Threshold is zero.");
                    goto LABEL_49;
                  }
                }
              }
              if ( pvData )
              {
                if ( a3 != 237 && a3 - 243 > 1 )
                {
                  if ( v17 )
                  {
                    if ( v12 )
                    {
                      v12(4u, L"IsSlowLink: Connection Type is = %d.", a3);
                    }
                    else if ( v13 )
                    {
                      if ( v14 )
                        RedirectDebugMsg(4u, L"IsSlowLink: Connection Type is = %d.", a3);
                    }
                  }
                  return 0;
                }
                *a4 = 1;
                *v11 = 1;
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( v12 )
                  {
                    v12(4u, L"IsSlowLink: Slow Link set to true by virtue of a WWAN connection and policy.");
                  }
                  else if ( v13 && v14 )
                  {
                    RedirectDebugMsg(
                      4u,
                      L"IsSlowLink: Slow Link set to true by virtue of a WWAN connection and policy.");
                  }
                }
              }
LABEL_66:
              if ( a3 == 237 || a3 - 243 <= 1 )
              {
                v23[0] = 0;
                v23[1] = 0;
                COperationalBaseEvent::ReportOperationalEvent((COperationalBaseEvent *)v23, &CSE_3G_INTERFACE_TYPE);
                CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent((CServiceConfigurationChangeOperationalEvent *)v23);
              }
              return 0;
            }
            RedirectDebugMsg(4u, L"IsSlowLink: WWAN Policy (SYSTEM) = %d.", pvData, 0);
          }
          v12 = g_lpDebugMsg;
        }
        v13 = g_lpDebugMsgContextInstance;
        v14 = g_lpDebugMsgContext;
        goto LABEL_27;
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x18009a05c  push    rbp
0x18009a05e  push    rbx
0x18009a05f  push    rsi
0x18009a060  push    rdi
0x18009a061  push    r12
0x18009a063  push    r13
0x18009a065  push    r14
0x18009a067  push    r15
0x18009a069  mov     rbp, rsp
0x18009a06c  sub     rsp, 78h
0x18009a070  mov     rbx, r9
0x18009a073  mov     edi, r8d
0x18009a076  mov     r15d, edx
0x18009a079  mov     rsi, rcx
0x18009a07c  xor     r13d, r13d
0x18009a07f  mov     [rbp+cbData], r13d
0x18009a083  mov     [rbp+Type], r13d
0x18009a087  mov     [rbp+hKey], r13
0x18009a08b  mov     [rbp+pvData], r13d
0x18009a08f  test    r9, r9
0x18009a092  jz      loc_18009A49B
0x18009a098  mov     r14, [rbp+arg_20]
0x18009a09c  test    r14, r14
0x18009a09f  jz      loc_18009A49B
0x18009a0a5  mov     r12, [rbp+arg_28]
0x18009a0a9  test    r12, r12
0x18009a0ac  jz      loc_18009A49B
0x18009a0b2  mov     [r12], r13d
0x18009a0b6  mov     [rbp+Data], 1F4h
0x18009a0bd  lea     rax, [rbp+hKey]
0x18009a0c1  mov     [rsp+78h+phkResult], rax; phkResult
0x18009a0c6  mov     r9d, 20019h; samDesired
0x18009a0cc  xor     r8d, r8d; ulOptions
0x18009a0cf  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x18009a0d6  call    cs:__imp_RegOpenKeyExW
0x18009a0dc  test    eax, eax
0x18009a0de  jnz     loc_18009A171
0x18009a0e4  mov     [rbp+cbData], 4
0x18009a0eb  lea     rax, [rbp+cbData]
0x18009a0ef  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18009a0f4  lea     rax, [rbp+Data]
0x18009a0f8  mov     [rsp+78h+phkResult], rax; lpData
0x18009a0fd  lea     r9, [rbp+Type]; lpType
0x18009a101  xor     r8d, r8d; lpReserved
0x18009a104  lea     rdx, aGrouppolicymin; "GroupPolicyMinTransferRate"
0x18009a10b  mov     rcx, [rbp+hKey]; hKey
0x18009a10f  call    cs:__imp_RegQueryValueExW
0x18009a115  mov     rcx, [rbp+hKey]; hKey
0x18009a119  call    cs:__imp_RegCloseKey
0x18009a11f  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18009a126  jz      short loc_18009A171
0x18009a128  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009a12f  test    rax, rax
0x18009a132  jz      short loc_18009A14A
0x18009a134  mov     r8d, [rbp+Data]
0x18009a138  lea     rdx, aIsslowlinkBand_0; "IsSlowLink: Bandwidth Threshold (WINLOG"...
0x18009a13f  lea     ecx, [r13+4]
0x18009a143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a148  jmp     short loc_18009A171
0x18009a14a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18009a151  jz      short loc_18009A171
0x18009a153  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009a15a  jz      short loc_18009A171
0x18009a15c  mov     r8d, [rbp+Data]
0x18009a160  lea     rdx, aIsslowlinkBand_0; "IsSlowLink: Bandwidth Threshold (WINLOG"...
0x18009a167  mov     ecx, 4; unsigned int
0x18009a16c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009a171  lea     rax, [rbp+hKey]
0x18009a175  mov     [rsp+78h+phkResult], rax; phkResult
0x18009a17a  mov     r9d, 20019h; samDesired
0x18009a180  xor     r8d, r8d; ulOptions
0x18009a183  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18009a18a  mov     rcx, rsi; hKey
0x18009a18d  call    cs:__imp_RegOpenKeyExW
0x18009a193  mov     esi, 4
0x18009a198  test    eax, eax
0x18009a19a  jnz     loc_18009A224
0x18009a1a0  mov     [rbp+cbData], esi
0x18009a1a3  lea     rax, [rbp+cbData]
0x18009a1a7  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18009a1ac  lea     rax, [rbp+Data]
0x18009a1b0  mov     [rsp+78h+phkResult], rax; lpData
0x18009a1b5  lea     r9, [rbp+Type]; lpType
0x18009a1b9  xor     r8d, r8d; lpReserved
0x18009a1bc  lea     rdx, aGrouppolicymin; "GroupPolicyMinTransferRate"
0x18009a1c3  mov     rcx, [rbp+hKey]; hKey
0x18009a1c7  call    cs:__imp_RegQueryValueExW
0x18009a1cd  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18009a1d4  jz      short loc_18009A21A
0x18009a1d6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009a1dd  test    rax, rax
0x18009a1e0  jz      short loc_18009A1F6
0x18009a1e2  mov     r8d, [rbp+Data]
0x18009a1e6  lea     rdx, aIsslowlinkBand; "IsSlowLink: Bandwidth Threshold (SYSTEM"...
0x18009a1ed  mov     ecx, esi
0x18009a1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a1f4  jmp     short loc_18009A21A
0x18009a1f6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18009a1fd  jz      short loc_18009A21A
0x18009a1ff  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009a206  jz      short loc_18009A21A
0x18009a208  mov     r8d, [rbp+Data]
0x18009a20c  lea     rdx, aIsslowlinkBand; "IsSlowLink: Bandwidth Threshold (SYSTEM"...
0x18009a213  mov     ecx, esi; unsigned int
0x18009a215  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009a21a  mov     rcx, [rbp+hKey]; hKey
0x18009a21e  call    cs:__imp_RegCloseKey
0x18009a224  mov     [rbp+cbData], esi
0x18009a227  lea     rax, [rbp+cbData]
0x18009a22b  mov     [rsp+78h+pcbData], rax; pcbData
0x18009a230  lea     rax, [rbp+pvData]
0x18009a234  mov     [rsp+78h+lpcbData], rax; pvData
0x18009a239  lea     rax, [rbp+Type]
0x18009a23d  mov     [rsp+78h+phkResult], rax; pdwType
0x18009a242  mov     r9d, 10h; dwFlags
0x18009a248  lea     r8, aSlowlinkdefaul; "SlowLinkDefaultFor3G"
0x18009a24f  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18009a256  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18009a25d  call    cs:__imp_RegGetValueW
0x18009a263  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009a26a  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18009a271  jz      short loc_18009A2C0
0x18009a273  test    r9, r9
0x18009a276  jz      short loc_18009A28F
0x18009a278  mov     r8d, [rbp+pvData]
0x18009a27c  lea     rdx, aIsslowlinkWwan; "IsSlowLink: WWAN Policy (SYSTEM) = %d."
0x18009a283  mov     ecx, esi
0x18009a285  mov     rax, r9
0x18009a288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a28d  jmp     short loc_18009A2B9
0x18009a28f  mov     rdx, cs:?g_lpDebugMsgContextInstance@@3PEAXEA; void * g_lpDebugMsgContextInstance
0x18009a296  mov     rcx, cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009a29d  test    rdx, rdx
0x18009a2a0  jz      short loc_18009A2CE
0x18009a2a2  test    rcx, rcx
0x18009a2a5  jz      short loc_18009A2CE
0x18009a2a7  mov     r8d, [rbp+pvData]
0x18009a2ab  lea     rdx, aIsslowlinkWwan; "IsSlowLink: WWAN Policy (SYSTEM) = %d."
0x18009a2b2  mov     ecx, esi; unsigned int
0x18009a2b4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009a2b9  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009a2c0  mov     rdx, cs:?g_lpDebugMsgContextInstance@@3PEAXEA; void * g_lpDebugMsgContextInstance
0x18009a2c7  mov     rcx, cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009a2ce  mov     eax, [rbp+Data]
0x18009a2d1  mov     [r14], eax
0x18009a2d4  mov     r14d, 1
0x18009a2da  test    r15d, r15d
0x18009a2dd  jz      short loc_18009A355
0x18009a2df  test    eax, eax
0x18009a2e1  jz      short loc_18009A355
0x18009a2e3  cmp     r15d, eax
0x18009a2e6  jnb     short loc_18009A321
0x18009a2e8  mov     [rbx], r14d
0x18009a2eb  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18009a2f2  jz      loc_18009A462
0x18009a2f8  test    r9, r9
0x18009a2fb  jz      short loc_18009A306
0x18009a2fd  lea     rdx, aIsslowlinkCurr_1; "IsSlowLink: Current Bandwidth < Bandwid"...
0x18009a304  jmp     short loc_18009A370
0x18009a306  test    rdx, rdx
0x18009a309  jz      loc_18009A462
0x18009a30f  test    rcx, rcx
0x18009a312  jz      loc_18009A462
0x18009a318  lea     rdx, aIsslowlinkCurr_1; "IsSlowLink: Current Bandwidth < Bandwid"...
0x18009a31f  jmp     short loc_18009A38D
0x18009a321  mov     [rbx], r13d
0x18009a324  mov     r8d, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x18009a32b  test    r8d, r8d
0x18009a32e  jz      loc_18009A3B9
0x18009a334  test    r9, r9
0x18009a337  jz      short loc_18009A342
0x18009a339  lea     rdx, aIsslowlinkCurr_0; "IsSlowLink: Current Bandwidth >= Bandwi"...
0x18009a340  jmp     short loc_18009A370
0x18009a342  test    rdx, rdx
0x18009a345  jz      short loc_18009A3B9
0x18009a347  test    rcx, rcx
0x18009a34a  jz      short loc_18009A3B9
0x18009a34c  lea     rdx, aIsslowlinkCurr_0; "IsSlowLink: Current Bandwidth >= Bandwi"...
0x18009a353  jmp     short loc_18009A38D
0x18009a355  mov     [rbx], r13d
0x18009a358  mov     r8d, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x18009a35f  test    r8d, r8d
0x18009a362  jz      short loc_18009A3B9
0x18009a364  test    r9, r9
0x18009a367  jz      short loc_18009A37C
0x18009a369  lea     rdx, aIsslowlinkCurr; "IsSlowLink: Current Bandwidth or Bandwi"...
0x18009a370  mov     ecx, esi
0x18009a372  mov     rax, r9
0x18009a375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a37a  jmp     short loc_18009A394
0x18009a37c  test    rdx, rdx
0x18009a37f  jz      short loc_18009A3B9
0x18009a381  test    rcx, rcx
0x18009a384  jz      short loc_18009A3B9
0x18009a386  lea     rdx, aIsslowlinkCurr; "IsSlowLink: Current Bandwidth or Bandwi"...
0x18009a38d  mov     ecx, esi; unsigned int
0x18009a38f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009a394  cmp     [rbx], r13d
0x18009a397  jnz     loc_18009A462
0x18009a39d  mov     r8d, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x18009a3a4  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009a3ab  mov     rdx, cs:?g_lpDebugMsgContextInstance@@3PEAXEA; void * g_lpDebugMsgContextInstance
0x18009a3b2  mov     rcx, cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009a3b9  cmp     [rbp+pvData], r13d
0x18009a3bd  jz      loc_18009A462
0x18009a3c3  cmp     edi, 0EDh
0x18009a3c9  jz      short loc_18009A422
0x18009a3cb  lea     eax, [rdi-0F3h]
0x18009a3d1  cmp     eax, r14d
0x18009a3d4  jbe     short loc_18009A422
0x18009a3d6  test    r8d, r8d
0x18009a3d9  jz      loc_18009A497
0x18009a3df  test    r9, r9
0x18009a3e2  jz      short loc_18009A3FD
0x18009a3e4  mov     r8d, edi
0x18009a3e7  lea     rdx, aIsslowlinkConn; "IsSlowLink: Connection Type is = %d."
0x18009a3ee  mov     ecx, esi
0x18009a3f0  mov     rax, r9
0x18009a3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a3f8  jmp     loc_18009A497
0x18009a3fd  test    rdx, rdx
0x18009a400  jz      loc_18009A497
0x18009a406  test    rcx, rcx
0x18009a409  jz      loc_18009A497
0x18009a40f  mov     r8d, edi
0x18009a412  lea     rdx, aIsslowlinkConn; "IsSlowLink: Connection Type is = %d."
0x18009a419  mov     ecx, esi; unsigned int
0x18009a41b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009a420  jmp     short loc_18009A497
0x18009a422  mov     [rbx], r14d
0x18009a425  mov     [r12], r14d
0x18009a429  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18009a430  jz      short loc_18009A462
0x18009a432  test    r9, r9
0x18009a435  jz      short loc_18009A44A
0x18009a437  lea     rdx, aIsslowlinkSlow; "IsSlowLink: Slow Link set to true by vi"...
0x18009a43e  mov     ecx, esi
0x18009a440  mov     rax, r9
0x18009a443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a448  jmp     short loc_18009A462
0x18009a44a  test    rdx, rdx
0x18009a44d  jz      short loc_18009A462
0x18009a44f  test    rcx, rcx
0x18009a452  jz      short loc_18009A462
0x18009a454  lea     rdx, aIsslowlinkSlow; "IsSlowLink: Slow Link set to true by vi"...
0x18009a45b  mov     ecx, esi; unsigned int
0x18009a45d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009a462  cmp     edi, 0EDh
0x18009a468  jz      short loc_18009A475
0x18009a46a  lea     eax, [rdi-0F3h]
0x18009a470  cmp     eax, r14d
0x18009a473  ja      short loc_18009A497
0x18009a475  mov     [rbp+var_20], r13
0x18009a479  mov     [rbp+var_18], r13
0x18009a47d  lea     rdx, CSE_3G_INTERFACE_TYPE; struct _EVENT_DESCRIPTOR *
0x18009a484  lea     rcx, [rbp+var_20]; this
0x18009a488  call    ?ReportOperationalEvent@COperationalBaseEvent@@IEAAKPEBU_EVENT_DESCRIPTOR@@@Z; COperationalBaseEvent::ReportOperationalEvent(_EVENT_DESCRIPTOR const *)
0x18009a48d  nop
0x18009a48e  lea     rcx, [rbp+var_20]; this
0x18009a492  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x18009a497  xor     eax, eax
0x18009a499  jmp     short loc_18009A4A0
0x18009a49b  mov     eax, 57h ; 'W'
0x18009a4a0  add     rsp, 78h
0x18009a4a4  pop     r15
0x18009a4a6  pop     r14
0x18009a4a8  pop     r13
0x18009a4aa  pop     r12
0x18009a4ac  pop     rdi
0x18009a4ad  pop     rsi
0x18009a4ae  pop     rbx
0x18009a4af  pop     rbp
0x18009a4b0  retn
```
