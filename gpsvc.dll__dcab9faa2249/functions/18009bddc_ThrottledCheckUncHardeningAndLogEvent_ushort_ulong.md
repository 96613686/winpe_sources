# ThrottledCheckUncHardeningAndLogEvent(ushort *,ulong)

- ea: `0x18009bddc`
- end: `0x18009c04d`
- name: `?ThrottledCheckUncHardeningAndLogEvent@@YAXPEAGK@Z`
- size: `625`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ce5c`

## callees

- `0x1800568fc`
- `0x180075ec0`
- `0x18009bddc`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c032`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c032`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009bf86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009bf86`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009be4d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009be4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009bf0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009bf0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009bf26`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009bf26`

## string_xrefs

- `0x18009be14`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Group Policy\Cache`
- `0x18009beb8`: `Created New Registry Key- this must have been accidentally deleted`
- `0x18009bedb`: `Created New Registry Key- this must have been accidentally deleted`
- `0x18009be80`: `Opened Existing Registry key`
- `0x18009be9b`: `Opened Existing Registry key`
- `0x18009bfa7`: `Failed to set Current Logging time in Registry = 0x%x`
- `0x18009bfca`: `Failed to set Current Logging time in Registry = 0x%x`

## pseudocode

```c
void __fastcall ThrottledCheckUncHardeningAndLogEvent(unsigned __int16 *a1, unsigned int a2)
{
  LSTATUS v4; // eax
  bool v5; // sf
  void (*v6)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v7; // rdx
  int v8; // ebx
  LSTATUS v9; // eax
  int v10; // [rsp+50h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-8h] BYREF
  DWORD v15; // [rsp+A0h] [rbp+30h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+38h] BYREF

  Type = 11;
  hKey = 0;
  v15 = 0;
  SystemTimeAsFileTime = 0;
  *(_QWORD *)Data = 0;
  cbData = 8;
  v10 = 0;
  v4 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Cache",
         0,
         0,
         0,
         3u,
         0,
         &hKey,
         &v15);
  v5 = v4 < 0;
  if ( !v4 )
  {
    if ( v15 == 1 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
      {
LABEL_17:
        v5 = RegQueryValueExW(hKey, L"LastLoggedTime", 0, &Type, Data, &cbData) < 0;
        goto LABEL_18;
      }
      v6 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"Created New Registry Key- this must have been accidentally deleted");
        goto LABEL_17;
      }
      v7 = L"Created New Registry Key- this must have been accidentally deleted";
    }
    else
    {
      if ( v15 != 2 || !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_17;
      v6 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"Opened Existing Registry key");
        goto LABEL_17;
      }
      v7 = L"Opened Existing Registry key";
    }
    v6(2u, v7);
    goto LABEL_17;
  }
LABEL_18:
  if ( v5 || Type != 11 )
    *(_QWORD *)Data = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)Data > 0xC92A69C000uLL )
  {
    v8 = CheckUncHardeningAndLogEvent(a1, a2, &v10);
    if ( v10 )
    {
      if ( hKey )
      {
        v9 = RegSetValueExW(hKey, L"LastLoggedTime", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u);
        if ( v9 < 0 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"Failed to set Current Logging time in Registry = 0x%x", (unsigned int)v9);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"Failed to set Current Logging time in Registry = 0x%x", (unsigned int)v9);
            }
          }
        }
      }
    }
    if ( v8 < 0 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Failed to check UNC Hardening with Error = 0x%x", (unsigned int)v8);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Failed to check UNC Hardening with Error = 0x%x", (unsigned int)v8);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18009bddc  mov     r11, rsp
0x18009bddf  mov     [r11+8], rbx
0x18009bde3  mov     [r11+10h], rsi
0x18009bde7  push    rbp
0x18009bde8  push    rdi
0x18009bde9  push    r14
0x18009bdeb  mov     rbp, rsp
0x18009bdee  sub     rsp, 70h
0x18009bdf2  xor     esi, esi
0x18009bdf4  mov     [rbp+Type], 0Bh
0x18009bdfb  lea     rax, [rbp+arg_10]
0x18009bdff  mov     [rbp+hKey], rsi
0x18009be03  mov     [r11-48h], rax
0x18009be07  mov     ebx, edx
0x18009be09  lea     rax, [rbp+hKey]
0x18009be0d  mov     [rbp+arg_10], esi
0x18009be10  mov     [r11-50h], rax
0x18009be14  lea     rdx, aSoftwareMicros_35; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18009be1b  mov     [r11-58h], rsi
0x18009be1f  mov     rdi, rcx
0x18009be22  mov     [rsp+70h+samDesired], 3; samDesired
0x18009be2a  xor     r9d, r9d; lpClass
0x18009be2d  xor     r8d, r8d; Reserved
0x18009be30  mov     [rsp+70h+dwOptions], esi; dwOptions
0x18009be34  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009be3b  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18009be3f  mov     qword ptr [rbp+Data], rsi
0x18009be43  mov     [rbp+cbData], 8
0x18009be4a  mov     [rbp+var_20], esi
0x18009be4d  call    cs:__imp_RegCreateKeyExW
0x18009be53  lea     r14d, [rsi+2]
0x18009be57  test    eax, eax
0x18009be59  jnz     loc_18009BF16
0x18009be5f  mov     eax, [rbp+arg_10]
0x18009be62  sub     eax, 1
0x18009be65  jz      short loc_18009BEA4
0x18009be67  cmp     eax, 1
0x18009be6a  jnz     short loc_18009BEEA
0x18009be6c  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18009be72  jz      short loc_18009BEEA
0x18009be74  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009be7b  test    rax, rax
0x18009be7e  jz      short loc_18009BE89
0x18009be80  lea     rdx, aOpenedExisting; "Opened Existing Registry key"
0x18009be87  jmp     short loc_18009BEBF
0x18009be89  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18009be90  jz      short loc_18009BEEA
0x18009be92  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009be99  jz      short loc_18009BEEA
0x18009be9b  lea     rdx, aOpenedExisting; "Opened Existing Registry key"
0x18009bea2  jmp     short loc_18009BEE2
0x18009bea4  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18009beaa  jz      short loc_18009BEEA
0x18009beac  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009beb3  test    rax, rax
0x18009beb6  jz      short loc_18009BEC9
0x18009beb8  lea     rdx, aCreatedNewRegi; "Created New Registry Key- this must hav"...
0x18009bebf  mov     ecx, r14d
0x18009bec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bec7  jmp     short loc_18009BEEA
0x18009bec9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18009bed0  jz      short loc_18009BEEA
0x18009bed2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009bed9  jz      short loc_18009BEEA
0x18009bedb  lea     rdx, aCreatedNewRegi; "Created New Registry Key- this must hav"...
0x18009bee2  mov     ecx, r14d; unsigned int
0x18009bee5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009beea  mov     rcx, [rbp+hKey]; hKey
0x18009beee  lea     rax, [rbp+cbData]
0x18009bef2  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x18009bef7  lea     r9, [rbp+Type]; lpType
0x18009befb  lea     rax, [rbp+Data]
0x18009beff  xor     r8d, r8d; lpReserved
0x18009bf02  lea     rdx, aLastloggedtime; "LastLoggedTime"
0x18009bf09  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18009bf0e  call    cs:__imp_RegQueryValueExW
0x18009bf14  test    eax, eax
0x18009bf16  js      short loc_18009BF1E
0x18009bf18  cmp     [rbp+Type], 0Bh
0x18009bf1c  jz      short loc_18009BF22
0x18009bf1e  mov     qword ptr [rbp+Data], rsi
0x18009bf22  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18009bf26  call    cs:__imp_GetSystemTimeAsFileTime
0x18009bf2c  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18009bf30  mov     rcx, 0C92A69C000h
0x18009bf3a  sub     rax, qword ptr [rbp+Data]
0x18009bf3e  cmp     rax, rcx
0x18009bf41  jbe     loc_18009C029
0x18009bf47  lea     r8, [rbp+var_20]; int *
0x18009bf4b  mov     edx, ebx; unsigned int
0x18009bf4d  mov     rcx, rdi; unsigned __int16 *
0x18009bf50  call    ?CheckUncHardeningAndLogEvent@@YAJPEAGKPEAH@Z; CheckUncHardeningAndLogEvent(ushort *,ulong,int *)
0x18009bf55  mov     ebx, eax
0x18009bf57  cmp     [rbp+var_20], esi
0x18009bf5a  jz      short loc_18009BFD9
0x18009bf5c  mov     rcx, [rbp+hKey]; hKey
0x18009bf60  test    rcx, rcx
0x18009bf63  jz      short loc_18009BFD9
0x18009bf65  lea     rax, [rbp+SystemTimeAsFileTime]
0x18009bf69  mov     [rsp+70h+samDesired], 8; cbData
0x18009bf71  mov     r9d, 0Bh; dwType
0x18009bf77  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18009bf7c  xor     r8d, r8d; Reserved
0x18009bf7f  lea     rdx, aLastloggedtime; "LastLoggedTime"
0x18009bf86  call    cs:__imp_RegSetValueExW
0x18009bf8c  mov     r8d, eax
0x18009bf8f  test    eax, eax
0x18009bf91  jns     short loc_18009BFD9
0x18009bf93  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18009bf99  jz      short loc_18009BFD9
0x18009bf9b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009bfa2  test    rax, rax
0x18009bfa5  jz      short loc_18009BFB8
0x18009bfa7  lea     rdx, aFailedToSetCur; "Failed to set Current Logging time in R"...
0x18009bfae  mov     ecx, r14d
0x18009bfb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bfb6  jmp     short loc_18009BFD9
0x18009bfb8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18009bfbf  jz      short loc_18009BFD9
0x18009bfc1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009bfc8  jz      short loc_18009BFD9
0x18009bfca  lea     rdx, aFailedToSetCur; "Failed to set Current Logging time in R"...
0x18009bfd1  mov     ecx, r14d; unsigned int
0x18009bfd4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009bfd9  test    ebx, ebx
0x18009bfdb  jns     short loc_18009C029
0x18009bfdd  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18009bfe3  jz      short loc_18009C029
0x18009bfe5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009bfec  test    rax, rax
0x18009bfef  jz      short loc_18009C005
0x18009bff1  mov     r8d, ebx
0x18009bff4  lea     rdx, aFailedToCheckU_0; "Failed to check UNC Hardening with Erro"...
0x18009bffb  mov     ecx, r14d
0x18009bffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c003  jmp     short loc_18009C029
0x18009c005  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18009c00c  jz      short loc_18009C029
0x18009c00e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009c015  jz      short loc_18009C029
0x18009c017  mov     r8d, ebx
0x18009c01a  lea     rdx, aFailedToCheckU_0; "Failed to check UNC Hardening with Erro"...
0x18009c021  mov     ecx, r14d; unsigned int
0x18009c024  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009c029  mov     rcx, [rbp+hKey]; hKey
0x18009c02d  test    rcx, rcx
0x18009c030  jz      short loc_18009C038
0x18009c032  call    cs:__imp_RegCloseKey
0x18009c038  lea     r11, [rsp+70h+var_s0]
0x18009c03d  mov     rbx, [r11+20h]
0x18009c041  mov     rsi, [r11+28h]
0x18009c045  mov     rsp, r11
0x18009c048  pop     r14
0x18009c04a  pop     rdi
0x18009c04b  pop     rbp
0x18009c04c  retn
```
