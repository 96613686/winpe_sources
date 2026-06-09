# GetBandwidthThreshold(HKEY__ *,ulong *)

- ea: `0x180099254`
- end: `0x180099491`
- name: `?GetBandwidthThreshold@@YAKPEAUHKEY__@@PEAK@Z`
- size: `573`
- prototype: `unsigned int __fastcall(HKEY hKey, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180098c40`

## callees

- `0x180075ec0`
- `0x180099254`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800992e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099431`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800992e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099431`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800992a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800993a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800992a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800993a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800992dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800993d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800992dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800993d9`

## string_xrefs

- `0x180099355`: `GetBandwidthThreshold: Failed in reading Bandwidth Threshold (WINLOGON)`
- `0x180099378`: `GetBandwidthThreshold: Failed in reading Bandwidth Threshold (WINLOGON)`
- `0x18009944d`: `GetBandwidthThreshold: Failed in reading Bandwidth Threshold (SYSTEM)`
- `0x180099470`: `GetBandwidthThreshold: Failed in reading Bandwidth Threshold (SYSTEM)`

## pseudocode

```c
__int64 __fastcall GetBandwidthThreshold(HKEY hKey, unsigned int *a2)
{
  HKEY hKeya[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  cbData = 0;
  Type = 0;
  hKeya[0] = 0;
  if ( !a2 )
    return 87;
  Data = 500;
  if ( RegOpenKeyExW(hKey, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 0x20019u, hKeya) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetBandwidthThreshold: Failed in reading Bandwidth Threshold (WINLOGON)");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetBandwidthThreshold: Failed in reading Bandwidth Threshold (WINLOGON)");
      }
    }
  }
  else
  {
    cbData = 4;
    RegQueryValueExW(hKeya[0], L"GroupPolicyMinTransferRate", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKeya[0]);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetBandwidthThreshold: Bandwidth Threshold (WINLOGON) = %d.", Data);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetBandwidthThreshold: Bandwidth Threshold (WINLOGON) = %d.", Data);
      }
    }
  }
  if ( RegOpenKeyExW(hKey, L"Software\\Policies\\Microsoft\\Windows\\System", 0, 0x20019u, hKeya) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetBandwidthThreshold: Failed in reading Bandwidth Threshold (SYSTEM)");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetBandwidthThreshold: Failed in reading Bandwidth Threshold (SYSTEM)");
      }
    }
  }
  else
  {
    cbData = 4;
    RegQueryValueExW(hKeya[0], L"GroupPolicyMinTransferRate", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetBandwidthThreshold: Bandwidth Threshold (SYSTEM) = %d.", Data);
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(4u, L"GetBandwidthThreshold: Bandwidth Threshold (SYSTEM) = %d.", Data);
      }
    }
    RegCloseKey(hKeya[0]);
  }
  *a2 = Data;
  return 0;
}

```

## disassembly

```asm
0x180099254  push    rbp
0x180099256  push    rbx
0x180099257  push    rsi
0x180099258  push    rdi
0x180099259  push    r14
0x18009925b  mov     rbp, rsp
0x18009925e  sub     rsp, 40h
0x180099262  xor     esi, esi
0x180099264  mov     rbx, rdx
0x180099267  mov     [rbp+cbData], esi
0x18009926a  mov     rdi, rcx
0x18009926d  mov     [rbp+Type], esi
0x180099270  mov     [rbp+hKey], rsi
0x180099274  test    rdx, rdx
0x180099277  jnz     short loc_180099281
0x180099279  lea     eax, [rdx+57h]
0x18009927c  jmp     loc_180099486
0x180099281  lea     rax, [rbp+hKey]
0x180099285  mov     [rbp+Data], 1F4h
0x18009928c  mov     r9d, 20019h; samDesired
0x180099292  mov     [rsp+40h+phkResult], rax; phkResult
0x180099297  xor     r8d, r8d; ulOptions
0x18009929a  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800992a1  call    cs:__imp_RegOpenKeyExW
0x1800992a7  mov     r14d, 4
0x1800992ad  test    eax, eax
0x1800992af  jnz     loc_180099341
0x1800992b5  mov     rcx, [rbp+hKey]; hKey
0x1800992b9  lea     rax, [rbp+cbData]
0x1800992bd  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800992c2  lea     r9, [rbp+Type]; lpType
0x1800992c6  lea     rax, [rbp+Data]
0x1800992ca  mov     [rbp+cbData], r14d
0x1800992ce  xor     r8d, r8d; lpReserved
0x1800992d1  mov     [rsp+40h+phkResult], rax; lpData
0x1800992d6  lea     rdx, aGrouppolicymin; "GroupPolicyMinTransferRate"
0x1800992dd  call    cs:__imp_RegQueryValueExW
0x1800992e3  mov     rcx, [rbp+hKey]; hKey
0x1800992e7  call    cs:__imp_RegCloseKey
0x1800992ed  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800992f3  jz      loc_180099387
0x1800992f9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099300  test    rax, rax
0x180099303  jz      short loc_18009931A
0x180099305  mov     r8d, [rbp+Data]
0x180099309  lea     rdx, aGetbandwidthth_0; "GetBandwidthThreshold: Bandwidth Thresh"...
0x180099310  mov     ecx, r14d
0x180099313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099318  jmp     short loc_180099387
0x18009931a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180099321  jz      short loc_180099387
0x180099323  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009932a  jz      short loc_180099387
0x18009932c  mov     r8d, [rbp+Data]
0x180099330  lea     rdx, aGetbandwidthth_0; "GetBandwidthThreshold: Bandwidth Thresh"...
0x180099337  mov     ecx, r14d; unsigned int
0x18009933a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009933f  jmp     short loc_180099387
0x180099341  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180099347  jz      short loc_180099387
0x180099349  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099350  test    rax, rax
0x180099353  jz      short loc_180099366
0x180099355  lea     rdx, aGetbandwidthth; "GetBandwidthThreshold: Failed in readin"...
0x18009935c  mov     ecx, r14d
0x18009935f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099364  jmp     short loc_180099387
0x180099366  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18009936d  jz      short loc_180099387
0x18009936f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099376  jz      short loc_180099387
0x180099378  lea     rdx, aGetbandwidthth; "GetBandwidthThreshold: Failed in readin"...
0x18009937f  mov     ecx, r14d; unsigned int
0x180099382  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180099387  lea     rax, [rbp+hKey]
0x18009938b  mov     r9d, 20019h; samDesired
0x180099391  xor     r8d, r8d; ulOptions
0x180099394  mov     [rsp+40h+phkResult], rax; phkResult
0x180099399  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800993a0  mov     rcx, rdi; hKey
0x1800993a3  call    cs:__imp_RegOpenKeyExW
0x1800993a9  test    eax, eax
0x1800993ab  jnz     loc_180099439
0x1800993b1  mov     rcx, [rbp+hKey]; hKey
0x1800993b5  lea     rax, [rbp+cbData]
0x1800993b9  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800993be  lea     r9, [rbp+Type]; lpType
0x1800993c2  lea     rax, [rbp+Data]
0x1800993c6  mov     [rbp+cbData], r14d
0x1800993ca  xor     r8d, r8d; lpReserved
0x1800993cd  mov     [rsp+40h+phkResult], rax; lpData
0x1800993d2  lea     rdx, aGrouppolicymin; "GroupPolicyMinTransferRate"
0x1800993d9  call    cs:__imp_RegQueryValueExW
0x1800993df  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800993e5  jz      short loc_18009942D
0x1800993e7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800993ee  test    rax, rax
0x1800993f1  jz      short loc_180099408
0x1800993f3  mov     r8d, [rbp+Data]
0x1800993f7  lea     rdx, aGetbandwidthth_1; "GetBandwidthThreshold: Bandwidth Thresh"...
0x1800993fe  mov     ecx, r14d
0x180099401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099406  jmp     short loc_18009942D
0x180099408  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18009940f  jz      short loc_18009942D
0x180099411  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099418  jz      short loc_18009942D
0x18009941a  mov     r8d, [rbp+Data]
0x18009941e  lea     rdx, aGetbandwidthth_1; "GetBandwidthThreshold: Bandwidth Thresh"...
0x180099425  mov     ecx, r14d; unsigned int
0x180099428  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009942d  mov     rcx, [rbp+hKey]; hKey
0x180099431  call    cs:__imp_RegCloseKey
0x180099437  jmp     short loc_18009947F
0x180099439  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18009943f  jz      short loc_18009947F
0x180099441  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099448  test    rax, rax
0x18009944b  jz      short loc_18009945E
0x18009944d  lea     rdx, aGetbandwidthth_2; "GetBandwidthThreshold: Failed in readin"...
0x180099454  mov     ecx, r14d
0x180099457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009945c  jmp     short loc_18009947F
0x18009945e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180099465  jz      short loc_18009947F
0x180099467  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009946e  jz      short loc_18009947F
0x180099470  lea     rdx, aGetbandwidthth_2; "GetBandwidthThreshold: Failed in readin"...
0x180099477  mov     ecx, r14d; unsigned int
0x18009947a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009947f  mov     eax, [rbp+Data]
0x180099482  mov     [rbx], eax
0x180099484  xor     eax, eax
0x180099486  add     rsp, 40h
0x18009948a  pop     r14
0x18009948c  pop     rdi
0x18009948d  pop     rsi
0x18009948e  pop     rbx
0x18009948f  pop     rbp
0x180099490  retn
```
