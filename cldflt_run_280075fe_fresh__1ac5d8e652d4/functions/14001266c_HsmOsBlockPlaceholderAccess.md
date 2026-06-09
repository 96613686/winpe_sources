# HsmOsBlockPlaceholderAccess

- ea: `0x14001266c`
- end: `0x140012b78`
- name: `HsmOsBlockPlaceholderAccess`
- size: `1292`
- prototype: `__int64 __fastcall(PRKPROCESS PROCESS)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012b80`

## callees

- `0x140001a88`
- `0x140006dc0`
- `0x1400071b0`
- `0x14000d8e0`
- `0x14001266c`
- `0x140013d44`
- `0x140014180`
- `0x1400146a0`
- `0x14001e140`
- `0x1400370b8`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x140012b0e`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140012b0e`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001273d`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001277a`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001279a`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400127fe`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001283b`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001285b`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001273d`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001277a`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001279a`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400127fe`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001283b`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001285b`
- `ntoskrnl!PsGetProcessPeb` at `0x140012751`
- `ntoskrnl!PsGetProcessPeb` at `0x1400127be`
- `ntoskrnl!PsGetProcessPeb` at `0x1400127de`
- `ntoskrnl!PsGetProcessPeb` at `0x140012812`
- `ntoskrnl!PsGetProcessPeb` at `0x14001287f`
- `ntoskrnl!PsGetProcessPeb` at `0x14001289f`
- `ntoskrnl!PsGetProcessPeb` at `0x140012751`
- `ntoskrnl!PsGetProcessPeb` at `0x1400127be`
- `ntoskrnl!PsGetProcessPeb` at `0x1400127de`
- `ntoskrnl!PsGetProcessPeb` at `0x140012812`
- `ntoskrnl!PsGetProcessPeb` at `0x14001287f`
- `ntoskrnl!PsGetProcessPeb` at `0x14001289f`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1400129bf`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1400129bf`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14001297b`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14001297b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400126ce`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001276b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001278b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400127af`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400127cf`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001282c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001284c`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012870`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012890`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400126ce`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001276b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001278b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400127af`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400127cf`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001282c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001284c`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012870`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012890`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400128fe`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400128fe`
- `ntoskrnl!ZwClose` at `0x140012b3c`
- `ntoskrnl!ZwClose` at `0x140012b3c`
- `ntoskrnl!SeLocateProcessImageName` at `0x140012962`
- `ntoskrnl!SeLocateProcessImageName` at `0x140012962`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b26`

## pseudocode

```c
__int64 __fastcall HsmOsBlockPlaceholderAccess(PRKPROCESS PROCESS, char a2)
{
  PACCESS_TOKEN v3; // r12
  __int64 CurrentProcess; // rax
  unsigned int ProcessSessionIdFromEprocess; // ebx
  unsigned int v6; // eax
  int v7; // ebx
  char v8; // r13
  __int64 ProcessWow64Process; // rax
  PRKPROCESS v10; // rcx
  PRKPROCESS v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rax
  PRKPROCESS v16; // rcx
  PRKPROCESS v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r15
  __int64 v20; // rax
  int v21; // ecx
  int v22; // eax
  __int16 v23; // cx
  _BYTE *v24; // rax
  _BYTE *v25; // rax
  __int16 v26; // cx
  unsigned __int64 v28; // [rsp+38h] [rbp-2E0h] BYREF
  unsigned __int64 v29; // [rsp+40h] [rbp-2D8h] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+48h] [rbp-2D0h] BYREF
  __int128 v31; // [rsp+50h] [rbp-2C8h] BYREF
  __int128 v32; // [rsp+60h] [rbp-2B8h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-2A8h] BYREF
  struct _UNICODE_STRING v34; // [rsp+78h] [rbp-2A0h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+88h] [rbp-290h] BYREF
  WCHAR v36[72]; // [rsp+C0h] [rbp-258h] BYREF
  _BYTE v37[144]; // [rsp+150h] [rbp-1C8h] BYREF
  _BYTE v38[256]; // [rsp+1E0h] [rbp-138h] BYREF

  v28 = (unsigned __int64)PROCESS;
  memset(&ApcState, 0, sizeof(ApcState));
  v3 = 0;
  pImageFileName = 0;
  Handle = 0;
  CurrentProcess = PsGetCurrentProcess();
  ProcessSessionIdFromEprocess = HsmiOsGetProcessSessionIdFromEprocess(CurrentProcess);
  v6 = HsmiOsGetProcessSessionIdFromEprocess(PROCESS);
  if ( !(unsigned __int8)HsmiOsIsInSameSession(0, v6, ProcessSessionIdFromEprocess) )
  {
    v7 = -1073688808;
    goto LABEL_64;
  }
  if ( (unsigned __int8)HsmiOsIsSyncProviderProcess(PROCESS) )
  {
    v7 = -1073688821;
    goto LABEL_64;
  }
  v7 = 0;
  v8 = HsmiOsStackAttachProcess(PROCESS, &ApcState);
  if ( PROCESS )
  {
    ProcessWow64Process = PsGetProcessWow64Process(PROCESS);
    v10 = PROCESS;
    if ( !ProcessWow64Process )
    {
      if ( PsGetProcessPeb(PROCESS) )
      {
        v11 = PROCESS;
LABEL_14:
        v13 = PsGetProcessPeb(v11) + 712;
        goto LABEL_16;
      }
      goto LABEL_15;
    }
LABEL_11:
    v13 = PsGetProcessWow64Process(v10) + 472;
    goto LABEL_16;
  }
  v12 = PsGetCurrentProcess();
  if ( PsGetProcessWow64Process(v12) )
  {
    v10 = (PRKPROCESS)PsGetCurrentProcess();
    goto LABEL_11;
  }
  v14 = PsGetCurrentProcess();
  if ( PsGetProcessPeb(v14) )
  {
    v11 = (PRKPROCESS)PsGetCurrentProcess();
    goto LABEL_14;
  }
LABEL_15:
  v13 = 0;
LABEL_16:
  if ( PROCESS )
  {
    v15 = PsGetProcessWow64Process(PROCESS);
    v16 = PROCESS;
    if ( !v15 )
    {
      if ( PsGetProcessPeb(PROCESS) )
      {
        v17 = PROCESS;
LABEL_25:
        v19 = PsGetProcessPeb(v17) + 1960;
        goto LABEL_27;
      }
      goto LABEL_26;
    }
LABEL_22:
    v19 = PsGetProcessWow64Process(v16) + 1120;
    goto LABEL_27;
  }
  v18 = PsGetCurrentProcess();
  if ( PsGetProcessWow64Process(v18) )
  {
    v16 = (PRKPROCESS)PsGetCurrentProcess();
    goto LABEL_22;
  }
  v20 = PsGetCurrentProcess();
  if ( PsGetProcessPeb(v20) )
  {
    v17 = (PRKPROCESS)PsGetCurrentProcess();
    goto LABEL_25;
  }
LABEL_26:
  v19 = 0;
LABEL_27:
  if ( v13 )
    RtlInterlockedOr32ToUserNoResult(v13, 0x2000000);
  if ( v19 )
    RtlInterlockedOr32ToUserNoResult(v19, 1);
  if ( v8 )
    KeUnstackDetachProcess(&ApcState);
  if ( a2 )
  {
    *(_QWORD *)&v34.Length = 1572886;
    v34.Buffer = L"BlockedApps";
    v29 = 256;
    v28 = 132;
    v32 = 0;
    v31 = 0;
    v7 = SeLocateProcessImageName(PROCESS, &pImageFileName);
    if ( v7 >= 0 )
    {
      v3 = PsReferencePrimaryToken(PROCESS);
      if ( v3 )
      {
        v21 = RtlQueryPackageIdentity(v3, v38, &v29, v37, &v28, 0, v8);
        v7 = -1073741823;
        if ( v21 == -1073741275 )
        {
          v29 = 0;
          v28 = 0;
        }
      }
      else
      {
        v7 = -1073741823;
        v21 = -1073741823;
      }
      v22 = 0;
      if ( v21 != -1073741275 )
        v22 = v21;
      if ( v22 < 0 )
        goto LABEL_63;
      v23 = v29;
      if ( v29 <= 0xFFFF && v28 <= 0xFFFF )
      {
        v24 = v38;
        if ( !v29 )
          v24 = (_BYTE *)*((_QWORD *)&v32 + 1);
        *((_QWORD *)&v32 + 1) = v24;
        if ( (unsigned __int16)v29 >= 0x7Fu )
        {
          v23 = 127;
          LOWORD(v32) = 127;
        }
        else
        {
          LOWORD(v32) = v29;
        }
        if ( v23 )
          WORD1(v32) = v23 + 2;
        else
          WORD1(v32) = 0;
        v25 = v37;
        v26 = v28;
        if ( !v28 )
          v25 = (_BYTE *)*((_QWORD *)&v31 + 1);
        *((_QWORD *)&v31 + 1) = v25;
        if ( (unsigned __int16)v28 >= 0x41u )
        {
          v26 = 65;
          LOWORD(v31) = 65;
        }
        else
        {
          LOWORD(v31) = v28;
        }
        WORD1(v31) = v26 ? v26 + 2 : 0;
        v7 = HsmiOsComputeAppIdentityString(pImageFileName, &v32, &v31, v36);
        if ( v7 >= 0 )
        {
          v7 = HsmiOsOpenAppPolicyKey(&v34, v36, 1, 1, &Handle);
          if ( v7 >= 0 )
          {
            v22 = HsmiOsPersistAppPolicy(Handle);
LABEL_63:
            v7 = v22;
          }
        }
      }
    }
  }
LABEL_64:
  if ( v3 )
    PsDereferencePrimaryToken(v3);
  if ( pImageFileName )
    ExFreePoolWithTag(pImageFileName, 0);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001266c  mov     [rsp+arg_10], rbx
0x140012671  mov     [rsp+arg_18], rsi
0x140012676  mov     [rsp+arg_8], dl
0x14001267a  push    rdi
0x14001267b  push    r12
0x14001267d  push    r13
0x14001267f  push    r14
0x140012681  push    r15
0x140012683  sub     rsp, 2F0h
0x14001268a  mov     rax, cs:__security_cookie
0x140012691  xor     rax, rsp
0x140012694  mov     [rsp+318h+var_38], rax
0x14001269c  mov     rsi, rcx
0x14001269f  mov     [rsp+318h+var_2E0], rcx
0x1400126a4  xorps   xmm0, xmm0
0x1400126a7  movups  xmmword ptr [rsp+318h+ApcState.ApcListHead.Flink], xmm0
0x1400126af  movups  xmmword ptr [rsp+318h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400126b7  movups  xmmword ptr [rsp+318h+ApcState.Process], xmm0
0x1400126bf  xor     edi, edi
0x1400126c1  mov     r12d, edi
0x1400126c4  mov     [rsp+318h+pImageFileName], rdi
0x1400126c9  mov     [rsp+318h+Handle], rdi
0x1400126ce  call    cs:__imp_PsGetCurrentProcess
0x1400126d5  nop     dword ptr [rax+rax+00h]
0x1400126da  mov     rcx, rax
0x1400126dd  call    HsmiOsGetProcessSessionIdFromEprocess
0x1400126e2  mov     ebx, eax
0x1400126e4  mov     rcx, rsi
0x1400126e7  call    HsmiOsGetProcessSessionIdFromEprocess
0x1400126ec  mov     edx, eax
0x1400126ee  mov     r8d, ebx
0x1400126f1  xor     ecx, ecx
0x1400126f3  call    HsmiOsIsInSameSession
0x1400126f8  test    al, al
0x1400126fa  jnz     short loc_140012706
0x1400126fc  mov     ebx, 0C000CF18h
0x140012701  jmp     loc_140012B06
0x140012706  mov     rcx, rsi
0x140012709  call    HsmiOsIsSyncProviderProcess
0x14001270e  test    al, al
0x140012710  jz      short loc_14001271C
0x140012712  mov     ebx, 0C000CF0Bh
0x140012717  jmp     loc_140012B06
0x14001271c  mov     ebx, edi
0x14001271e  lea     rdx, [rsp+318h+ApcState]; ApcState
0x140012726  mov     rcx, rsi; PROCESS
0x140012729  call    HsmiOsStackAttachProcess
0x14001272e  mov     r13b, al
0x140012731  mov     [rsp+318h+var_2E8], al
0x140012735  test    rsi, rsi
0x140012738  jz      short loc_14001276B
0x14001273a  mov     rcx, rsi
0x14001273d  call    cs:__imp_PsGetProcessWow64Process
0x140012744  nop     dword ptr [rax+rax+00h]
0x140012749  mov     rcx, rsi
0x14001274c  test    rax, rax
0x14001274f  jnz     short loc_14001279A
0x140012751  call    cs:__imp_PsGetProcessPeb
0x140012758  nop     dword ptr [rax+rax+00h]
0x14001275d  test    rax, rax
0x140012760  jz      loc_1400127F3
0x140012766  mov     rcx, rsi
0x140012769  jmp     short loc_1400127DE
0x14001276b  call    cs:__imp_PsGetCurrentProcess
0x140012772  nop     dword ptr [rax+rax+00h]
0x140012777  mov     rcx, rax
0x14001277a  call    cs:__imp_PsGetProcessWow64Process
0x140012781  nop     dword ptr [rax+rax+00h]
0x140012786  test    rax, rax
0x140012789  jz      short loc_1400127AF
0x14001278b  call    cs:__imp_PsGetCurrentProcess
0x140012792  nop     dword ptr [rax+rax+00h]
0x140012797  mov     rcx, rax
0x14001279a  call    cs:__imp_PsGetProcessWow64Process
0x1400127a1  nop     dword ptr [rax+rax+00h]
0x1400127a6  lea     r14, [rax+1D8h]
0x1400127ad  jmp     short loc_1400127F6
0x1400127af  call    cs:__imp_PsGetCurrentProcess
0x1400127b6  nop     dword ptr [rax+rax+00h]
0x1400127bb  mov     rcx, rax
0x1400127be  call    cs:__imp_PsGetProcessPeb
0x1400127c5  nop     dword ptr [rax+rax+00h]
0x1400127ca  test    rax, rax
0x1400127cd  jz      short loc_1400127F3
0x1400127cf  call    cs:__imp_PsGetCurrentProcess
0x1400127d6  nop     dword ptr [rax+rax+00h]
0x1400127db  mov     rcx, rax
0x1400127de  call    cs:__imp_PsGetProcessPeb
0x1400127e5  nop     dword ptr [rax+rax+00h]
0x1400127ea  lea     r14, [rax+2C8h]
0x1400127f1  jmp     short loc_1400127F6
0x1400127f3  mov     r14, rdi
0x1400127f6  test    rsi, rsi
0x1400127f9  jz      short loc_14001282C
0x1400127fb  mov     rcx, rsi
0x1400127fe  call    cs:__imp_PsGetProcessWow64Process
0x140012805  nop     dword ptr [rax+rax+00h]
0x14001280a  mov     rcx, rsi
0x14001280d  test    rax, rax
0x140012810  jnz     short loc_14001285B
0x140012812  call    cs:__imp_PsGetProcessPeb
0x140012819  nop     dword ptr [rax+rax+00h]
0x14001281e  test    rax, rax
0x140012821  jz      loc_1400128B4
0x140012827  mov     rcx, rsi
0x14001282a  jmp     short loc_14001289F
0x14001282c  call    cs:__imp_PsGetCurrentProcess
0x140012833  nop     dword ptr [rax+rax+00h]
0x140012838  mov     rcx, rax
0x14001283b  call    cs:__imp_PsGetProcessWow64Process
0x140012842  nop     dword ptr [rax+rax+00h]
0x140012847  test    rax, rax
0x14001284a  jz      short loc_140012870
0x14001284c  call    cs:__imp_PsGetCurrentProcess
0x140012853  nop     dword ptr [rax+rax+00h]
0x140012858  mov     rcx, rax
0x14001285b  call    cs:__imp_PsGetProcessWow64Process
0x140012862  nop     dword ptr [rax+rax+00h]
0x140012867  lea     r15, [rax+460h]
0x14001286e  jmp     short loc_1400128B7
0x140012870  call    cs:__imp_PsGetCurrentProcess
0x140012877  nop     dword ptr [rax+rax+00h]
0x14001287c  mov     rcx, rax
0x14001287f  call    cs:__imp_PsGetProcessPeb
0x140012886  nop     dword ptr [rax+rax+00h]
0x14001288b  test    rax, rax
0x14001288e  jz      short loc_1400128B4
0x140012890  call    cs:__imp_PsGetCurrentProcess
0x140012897  nop     dword ptr [rax+rax+00h]
0x14001289c  mov     rcx, rax
0x14001289f  call    cs:__imp_PsGetProcessPeb
0x1400128a6  nop     dword ptr [rax+rax+00h]
0x1400128ab  lea     r15, [rax+7A8h]
0x1400128b2  jmp     short loc_1400128B7
0x1400128b4  mov     r15, rdi
0x1400128b7  test    r14, r14
0x1400128ba  jz      short loc_1400128C9
0x1400128bc  mov     edx, 2000000h
0x1400128c1  mov     rcx, r14
0x1400128c4  call    RtlInterlockedOr32ToUserNoResult
0x1400128c9  test    r15, r15
0x1400128cc  jz      short loc_1400128DB
0x1400128ce  mov     edx, 1
0x1400128d3  mov     rcx, r15
0x1400128d6  call    RtlInterlockedOr32ToUserNoResult
0x1400128db  jmp     short loc_1400128F1
0x1400128dd  mov     ebx, 0C00000E5h
0x1400128e2  xor     edi, edi
0x1400128e4  mov     r12d, edi
0x1400128e7  mov     r13b, [rsp+318h+var_2E8]
0x1400128ec  mov     rsi, [rsp+318h+var_2E0]
0x1400128f1  test    r13b, r13b
0x1400128f4  jz      short loc_14001290A
0x1400128f6  lea     rcx, [rsp+318h+ApcState]; ApcState
0x1400128fe  call    cs:__imp_KeUnstackDetachProcess
0x140012905  nop     dword ptr [rax+rax+00h]
0x14001290a  test    ebx, ebx
0x14001290c  js      loc_140012B06
0x140012912  cmp     [rsp+318h+arg_8], dil
0x14001291a  jz      loc_140012B06
0x140012920  mov     [rsp+318h+var_2A0], 180016h
0x140012929  lea     rax, aBlockedapps; "BlockedApps"
0x140012930  mov     [rsp+318h+var_298], rax
0x140012938  mov     [rsp+318h+var_2D8], 100h
0x140012941  mov     [rsp+318h+var_2E0], 84h
0x14001294a  xorps   xmm0, xmm0
0x14001294d  movups  [rsp+318h+var_2B8], xmm0
0x140012952  xorps   xmm1, xmm1
0x140012955  movups  [rsp+318h+var_2C8], xmm1
0x14001295a  lea     rdx, [rsp+318h+pImageFileName]; pImageFileName
0x14001295f  mov     rcx, rsi; Process
0x140012962  call    cs:__imp_SeLocateProcessImageName
0x140012969  nop     dword ptr [rax+rax+00h]
0x14001296e  mov     ebx, eax
0x140012970  test    eax, eax
0x140012972  js      loc_140012B06
0x140012978  mov     rcx, rsi; Process
0x14001297b  call    cs:__imp_PsReferencePrimaryToken
0x140012982  nop     dword ptr [rax+rax+00h]
0x140012987  mov     r12, rax
0x14001298a  test    rax, rax
0x14001298d  jnz     short loc_140012998
0x14001298f  mov     ebx, 0C0000001h
0x140012994  mov     ecx, ebx
0x140012996  jmp     short loc_1400129E3
0x140012998  mov     [rsp+318h+var_2F0], rdi
0x14001299d  lea     rax, [rsp+318h+var_2E0]
0x1400129a2  mov     [rsp+318h+var_2F8], rax
0x1400129a7  lea     r9, [rsp+318h+var_1C8]
0x1400129af  lea     r8, [rsp+318h+var_2D8]
0x1400129b4  lea     rdx, [rsp+318h+var_138]
0x1400129bc  mov     rcx, r12
0x1400129bf  call    cs:__imp_RtlQueryPackageIdentity
0x1400129c6  nop     dword ptr [rax+rax+00h]
0x1400129cb  mov     ecx, eax
0x1400129cd  mov     ebx, 0C0000001h
0x1400129d2  cmp     eax, 0C0000225h
0x1400129d7  jnz     short loc_1400129E3
0x1400129d9  mov     [rsp+318h+var_2D8], rdi
0x1400129de  mov     [rsp+318h+var_2E0], rdi
0x1400129e3  mov     eax, edi
0x1400129e5  cmp     ecx, 0C0000225h
0x1400129eb  cmovnz  eax, ecx
0x1400129ee  test    eax, eax
0x1400129f0  js      loc_140012B04
0x1400129f6  mov     eax, 0FFFFh
0x1400129fb  mov     rcx, [rsp+318h+var_2D8]
0x140012a00  cmp     rcx, rax
0x140012a03  ja      loc_140012B06
0x140012a09  cmp     [rsp+318h+var_2E0], rax
0x140012a0e  ja      loc_140012B06
0x140012a14  lea     rax, [rsp+318h+var_138]
0x140012a1c  test    rcx, rcx
0x140012a1f  cmovz   rax, qword ptr [rsp+318h+var_2B8+8]
0x140012a25  mov     qword ptr [rsp+318h+var_2B8+8], rax
0x140012a2a  mov     eax, 7Fh
0x140012a2f  cmp     cx, ax
0x140012a32  jnb     short loc_140012A3B
0x140012a34  mov     word ptr [rsp+318h+var_2B8], cx
0x140012a39  jmp     short loc_140012A43
0x140012a3b  movzx   ecx, ax
0x140012a3e  mov     word ptr [rsp+318h+var_2B8], ax
0x140012a43  test    cx, cx
0x140012a46  jz      short loc_140012A53
0x140012a48  add     cx, 2
0x140012a4c  mov     word ptr [rsp+318h+var_2B8+2], cx
0x140012a51  jmp     short loc_140012A58
0x140012a53  mov     word ptr [rsp+318h+var_2B8+2], di
0x140012a58  lea     rax, [rsp+318h+var_1C8]
0x140012a60  mov     rcx, [rsp+318h+var_2E0]
0x140012a65  test    rcx, rcx
0x140012a68  cmovz   rax, qword ptr [rsp+318h+var_2C8+8]
0x140012a6e  mov     qword ptr [rsp+318h+var_2C8+8], rax
0x140012a73  mov     eax, 41h ; 'A'
0x140012a78  cmp     cx, ax
0x140012a7b  jnb     short loc_140012A84
0x140012a7d  mov     word ptr [rsp+318h+var_2C8], cx
0x140012a82  jmp     short loc_140012A8C
0x140012a84  movzx   ecx, ax
0x140012a87  mov     word ptr [rsp+318h+var_2C8], ax
0x140012a8c  test    cx, cx
0x140012a8f  jz      short loc_140012A9C
0x140012a91  add     cx, 2
0x140012a95  mov     word ptr [rsp+318h+var_2C8+2], cx
0x140012a9a  jmp     short loc_140012AA1
0x140012a9c  mov     word ptr [rsp+318h+var_2C8+2], di
0x140012aa1  lea     r9, [rsp+318h+var_258]
0x140012aa9  lea     r8, [rsp+318h+var_2C8]
0x140012aae  lea     rdx, [rsp+318h+var_2B8]
0x140012ab3  mov     rcx, [rsp+318h+pImageFileName]
0x140012ab8  call    HsmiOsComputeAppIdentityString
0x140012abd  mov     ebx, eax
0x140012abf  test    eax, eax
0x140012ac1  js      short loc_140012B06
0x140012ac3  lea     rax, [rsp+318h+Handle]
0x140012ac8  mov     [rsp+318h+var_2F8], rax
0x140012acd  mov     r9b, 1
0x140012ad0  mov     r8b, r9b
0x140012ad3  lea     rdx, [rsp+318h+var_258]
0x140012adb  lea     rcx, [rsp+318h+var_2A0]
0x140012ae0  call    HsmiOsOpenAppPolicyKey
0x140012ae5  mov     ebx, eax
0x140012ae7  test    eax, eax
0x140012ae9  js      short loc_140012B06
0x140012aeb  lea     r9, [rsp+318h+var_2C8]
0x140012af0  lea     r8, [rsp+318h+var_2B8]
0x140012af5  mov     rdx, [rsp+318h+pImageFileName]
0x140012afa  mov     rcx, [rsp+318h+Handle]; KeyHandle
0x140012aff  call    HsmiOsPersistAppPolicy
0x140012b04  mov     ebx, eax
0x140012b06  test    r12, r12
0x140012b09  jz      short loc_140012B1A
0x140012b0b  mov     rcx, r12; PrimaryToken
0x140012b0e  call    cs:__imp_PsDereferencePrimaryToken
0x140012b15  nop     dword ptr [rax+rax+00h]
0x140012b1a  mov     rcx, [rsp+318h+pImageFileName]; P
0x140012b1f  test    rcx, rcx
0x140012b22  jz      short loc_140012B32
0x140012b24  xor     edx, edx; Tag
0x140012b26  call    cs:__imp_ExFreePoolWithTag
0x140012b2d  nop     dword ptr [rax+rax+00h]
0x140012b32  mov     rcx, [rsp+318h+Handle]; Handle
0x140012b37  test    rcx, rcx
0x140012b3a  jz      short loc_140012B48
0x140012b3c  call    cs:__imp_ZwClose
0x140012b43  nop     dword ptr [rax+rax+00h]
0x140012b48  mov     eax, ebx
0x140012b4a  mov     rcx, [rsp+318h+var_38]
0x140012b52  xor     rcx, rsp; StackCookie
0x140012b55  call    __security_check_cookie
0x140012b5a  lea     r11, [rsp+318h+var_28]
0x140012b62  mov     rbx, [r11+40h]
0x140012b66  mov     rsi, [r11+48h]
0x140012b6a  mov     rsp, r11
0x140012b6d  pop     r15
0x140012b6f  pop     r14
0x140012b71  pop     r13
0x140012b73  pop     r12
0x140012b75  pop     rdi
0x140012b76  retn
  ... truncated ...
```
