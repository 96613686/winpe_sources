# HsmOsBlockPlaceholderAccess

- ea: `0x1400126ec`
- end: `0x140012bf8`
- name: `HsmOsBlockPlaceholderAccess`
- size: `1292`
- prototype: `__int64 __fastcall(PRKPROCESS PROCESS, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012c00`

## callees

- `0x140001a88`
- `0x140006dc0`
- `0x1400071b0`
- `0x14000d8e0`
- `0x1400126ec`
- `0x140013dc4`
- `0x140014200`
- `0x140014720`
- `0x14001e1c0`
- `0x1400370d8`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x140012b8e`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140012b8e`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400127bd`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400127fa`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001281a`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001287e`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400128bb`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400128db`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400127bd`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400127fa`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001281a`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14001287e`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400128bb`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400128db`
- `ntoskrnl!PsGetProcessPeb` at `0x1400127d1`
- `ntoskrnl!PsGetProcessPeb` at `0x14001283e`
- `ntoskrnl!PsGetProcessPeb` at `0x14001285e`
- `ntoskrnl!PsGetProcessPeb` at `0x140012892`
- `ntoskrnl!PsGetProcessPeb` at `0x1400128ff`
- `ntoskrnl!PsGetProcessPeb` at `0x14001291f`
- `ntoskrnl!PsGetProcessPeb` at `0x1400127d1`
- `ntoskrnl!PsGetProcessPeb` at `0x14001283e`
- `ntoskrnl!PsGetProcessPeb` at `0x14001285e`
- `ntoskrnl!PsGetProcessPeb` at `0x140012892`
- `ntoskrnl!PsGetProcessPeb` at `0x1400128ff`
- `ntoskrnl!PsGetProcessPeb` at `0x14001291f`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140012a3f`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140012a3f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400129fb`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400129fb`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001274e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400127eb`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001280b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001282f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001284f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400128ac`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400128cc`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400128f0`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012910`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001274e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400127eb`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001280b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001282f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001284f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400128ac`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400128cc`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400128f0`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012910`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001297e`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001297e`
- `ntoskrnl!ZwClose` at `0x140012bbc`
- `ntoskrnl!ZwClose` at `0x140012bbc`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400129e2`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400129e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ba6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ba6`

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
            v22 = HsmiOsPersistAppPolicy(Handle, (__int64)pImageFileName, (__int64)&v32, (__int64)&v31);
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
0x1400126ec  mov     [rsp+arg_10], rbx
0x1400126f1  mov     [rsp+arg_18], rsi
0x1400126f6  mov     [rsp+arg_8], dl
0x1400126fa  push    rdi
0x1400126fb  push    r12
0x1400126fd  push    r13
0x1400126ff  push    r14
0x140012701  push    r15
0x140012703  sub     rsp, 2F0h
0x14001270a  mov     rax, cs:__security_cookie
0x140012711  xor     rax, rsp
0x140012714  mov     [rsp+318h+var_38], rax
0x14001271c  mov     rsi, rcx
0x14001271f  mov     [rsp+318h+var_2E0], rcx
0x140012724  xorps   xmm0, xmm0
0x140012727  movups  xmmword ptr [rsp+318h+ApcState.ApcListHead.Flink], xmm0
0x14001272f  movups  xmmword ptr [rsp+318h+ApcState.ApcListHead.Flink+10h], xmm0
0x140012737  movups  xmmword ptr [rsp+318h+ApcState.Process], xmm0
0x14001273f  xor     edi, edi
0x140012741  mov     r12d, edi
0x140012744  mov     [rsp+318h+pImageFileName], rdi
0x140012749  mov     [rsp+318h+Handle], rdi
0x14001274e  call    cs:__imp_PsGetCurrentProcess
0x140012755  nop     dword ptr [rax+rax+00h]
0x14001275a  mov     rcx, rax
0x14001275d  call    HsmiOsGetProcessSessionIdFromEprocess
0x140012762  mov     ebx, eax
0x140012764  mov     rcx, rsi
0x140012767  call    HsmiOsGetProcessSessionIdFromEprocess
0x14001276c  mov     edx, eax
0x14001276e  mov     r8d, ebx
0x140012771  xor     ecx, ecx
0x140012773  call    HsmiOsIsInSameSession
0x140012778  test    al, al
0x14001277a  jnz     short loc_140012786
0x14001277c  mov     ebx, 0C000CF18h
0x140012781  jmp     loc_140012B86
0x140012786  mov     rcx, rsi
0x140012789  call    HsmiOsIsSyncProviderProcess
0x14001278e  test    al, al
0x140012790  jz      short loc_14001279C
0x140012792  mov     ebx, 0C000CF0Bh
0x140012797  jmp     loc_140012B86
0x14001279c  mov     ebx, edi
0x14001279e  lea     rdx, [rsp+318h+ApcState]; ApcState
0x1400127a6  mov     rcx, rsi; PROCESS
0x1400127a9  call    HsmiOsStackAttachProcess
0x1400127ae  mov     r13b, al
0x1400127b1  mov     [rsp+318h+var_2E8], al
0x1400127b5  test    rsi, rsi
0x1400127b8  jz      short loc_1400127EB
0x1400127ba  mov     rcx, rsi
0x1400127bd  call    cs:__imp_PsGetProcessWow64Process
0x1400127c4  nop     dword ptr [rax+rax+00h]
0x1400127c9  mov     rcx, rsi
0x1400127cc  test    rax, rax
0x1400127cf  jnz     short loc_14001281A
0x1400127d1  call    cs:__imp_PsGetProcessPeb
0x1400127d8  nop     dword ptr [rax+rax+00h]
0x1400127dd  test    rax, rax
0x1400127e0  jz      loc_140012873
0x1400127e6  mov     rcx, rsi
0x1400127e9  jmp     short loc_14001285E
0x1400127eb  call    cs:__imp_PsGetCurrentProcess
0x1400127f2  nop     dword ptr [rax+rax+00h]
0x1400127f7  mov     rcx, rax
0x1400127fa  call    cs:__imp_PsGetProcessWow64Process
0x140012801  nop     dword ptr [rax+rax+00h]
0x140012806  test    rax, rax
0x140012809  jz      short loc_14001282F
0x14001280b  call    cs:__imp_PsGetCurrentProcess
0x140012812  nop     dword ptr [rax+rax+00h]
0x140012817  mov     rcx, rax
0x14001281a  call    cs:__imp_PsGetProcessWow64Process
0x140012821  nop     dword ptr [rax+rax+00h]
0x140012826  lea     r14, [rax+1D8h]
0x14001282d  jmp     short loc_140012876
0x14001282f  call    cs:__imp_PsGetCurrentProcess
0x140012836  nop     dword ptr [rax+rax+00h]
0x14001283b  mov     rcx, rax
0x14001283e  call    cs:__imp_PsGetProcessPeb
0x140012845  nop     dword ptr [rax+rax+00h]
0x14001284a  test    rax, rax
0x14001284d  jz      short loc_140012873
0x14001284f  call    cs:__imp_PsGetCurrentProcess
0x140012856  nop     dword ptr [rax+rax+00h]
0x14001285b  mov     rcx, rax
0x14001285e  call    cs:__imp_PsGetProcessPeb
0x140012865  nop     dword ptr [rax+rax+00h]
0x14001286a  lea     r14, [rax+2C8h]
0x140012871  jmp     short loc_140012876
0x140012873  mov     r14, rdi
0x140012876  test    rsi, rsi
0x140012879  jz      short loc_1400128AC
0x14001287b  mov     rcx, rsi
0x14001287e  call    cs:__imp_PsGetProcessWow64Process
0x140012885  nop     dword ptr [rax+rax+00h]
0x14001288a  mov     rcx, rsi
0x14001288d  test    rax, rax
0x140012890  jnz     short loc_1400128DB
0x140012892  call    cs:__imp_PsGetProcessPeb
0x140012899  nop     dword ptr [rax+rax+00h]
0x14001289e  test    rax, rax
0x1400128a1  jz      loc_140012934
0x1400128a7  mov     rcx, rsi
0x1400128aa  jmp     short loc_14001291F
0x1400128ac  call    cs:__imp_PsGetCurrentProcess
0x1400128b3  nop     dword ptr [rax+rax+00h]
0x1400128b8  mov     rcx, rax
0x1400128bb  call    cs:__imp_PsGetProcessWow64Process
0x1400128c2  nop     dword ptr [rax+rax+00h]
0x1400128c7  test    rax, rax
0x1400128ca  jz      short loc_1400128F0
0x1400128cc  call    cs:__imp_PsGetCurrentProcess
0x1400128d3  nop     dword ptr [rax+rax+00h]
0x1400128d8  mov     rcx, rax
0x1400128db  call    cs:__imp_PsGetProcessWow64Process
0x1400128e2  nop     dword ptr [rax+rax+00h]
0x1400128e7  lea     r15, [rax+460h]
0x1400128ee  jmp     short loc_140012937
0x1400128f0  call    cs:__imp_PsGetCurrentProcess
0x1400128f7  nop     dword ptr [rax+rax+00h]
0x1400128fc  mov     rcx, rax
0x1400128ff  call    cs:__imp_PsGetProcessPeb
0x140012906  nop     dword ptr [rax+rax+00h]
0x14001290b  test    rax, rax
0x14001290e  jz      short loc_140012934
0x140012910  call    cs:__imp_PsGetCurrentProcess
0x140012917  nop     dword ptr [rax+rax+00h]
0x14001291c  mov     rcx, rax
0x14001291f  call    cs:__imp_PsGetProcessPeb
0x140012926  nop     dword ptr [rax+rax+00h]
0x14001292b  lea     r15, [rax+7A8h]
0x140012932  jmp     short loc_140012937
0x140012934  mov     r15, rdi
0x140012937  test    r14, r14
0x14001293a  jz      short loc_140012949
0x14001293c  mov     edx, 2000000h
0x140012941  mov     rcx, r14
0x140012944  call    RtlInterlockedOr32ToUserNoResult
0x140012949  test    r15, r15
0x14001294c  jz      short loc_14001295B
0x14001294e  mov     edx, 1
0x140012953  mov     rcx, r15
0x140012956  call    RtlInterlockedOr32ToUserNoResult
0x14001295b  jmp     short loc_140012971
0x14001295d  mov     ebx, 0C00000E5h
0x140012962  xor     edi, edi
0x140012964  mov     r12d, edi
0x140012967  mov     r13b, [rsp+318h+var_2E8]
0x14001296c  mov     rsi, [rsp+318h+var_2E0]
0x140012971  test    r13b, r13b
0x140012974  jz      short loc_14001298A
0x140012976  lea     rcx, [rsp+318h+ApcState]; ApcState
0x14001297e  call    cs:__imp_KeUnstackDetachProcess
0x140012985  nop     dword ptr [rax+rax+00h]
0x14001298a  test    ebx, ebx
0x14001298c  js      loc_140012B86
0x140012992  cmp     [rsp+318h+arg_8], dil
0x14001299a  jz      loc_140012B86
0x1400129a0  mov     [rsp+318h+var_2A0], 180016h
0x1400129a9  lea     rax, aBlockedapps; "BlockedApps"
0x1400129b0  mov     [rsp+318h+var_298], rax
0x1400129b8  mov     [rsp+318h+var_2D8], 100h
0x1400129c1  mov     [rsp+318h+var_2E0], 84h
0x1400129ca  xorps   xmm0, xmm0
0x1400129cd  movups  [rsp+318h+var_2B8], xmm0
0x1400129d2  xorps   xmm1, xmm1
0x1400129d5  movups  [rsp+318h+var_2C8], xmm1
0x1400129da  lea     rdx, [rsp+318h+pImageFileName]; pImageFileName
0x1400129df  mov     rcx, rsi; Process
0x1400129e2  call    cs:__imp_SeLocateProcessImageName
0x1400129e9  nop     dword ptr [rax+rax+00h]
0x1400129ee  mov     ebx, eax
0x1400129f0  test    eax, eax
0x1400129f2  js      loc_140012B86
0x1400129f8  mov     rcx, rsi; Process
0x1400129fb  call    cs:__imp_PsReferencePrimaryToken
0x140012a02  nop     dword ptr [rax+rax+00h]
0x140012a07  mov     r12, rax
0x140012a0a  test    rax, rax
0x140012a0d  jnz     short loc_140012A18
0x140012a0f  mov     ebx, 0C0000001h
0x140012a14  mov     ecx, ebx
0x140012a16  jmp     short loc_140012A63
0x140012a18  mov     [rsp+318h+var_2F0], rdi
0x140012a1d  lea     rax, [rsp+318h+var_2E0]
0x140012a22  mov     [rsp+318h+var_2F8], rax
0x140012a27  lea     r9, [rsp+318h+var_1C8]
0x140012a2f  lea     r8, [rsp+318h+var_2D8]
0x140012a34  lea     rdx, [rsp+318h+var_138]
0x140012a3c  mov     rcx, r12
0x140012a3f  call    cs:__imp_RtlQueryPackageIdentity
0x140012a46  nop     dword ptr [rax+rax+00h]
0x140012a4b  mov     ecx, eax
0x140012a4d  mov     ebx, 0C0000001h
0x140012a52  cmp     eax, 0C0000225h
0x140012a57  jnz     short loc_140012A63
0x140012a59  mov     [rsp+318h+var_2D8], rdi
0x140012a5e  mov     [rsp+318h+var_2E0], rdi
0x140012a63  mov     eax, edi
0x140012a65  cmp     ecx, 0C0000225h
0x140012a6b  cmovnz  eax, ecx
0x140012a6e  test    eax, eax
0x140012a70  js      loc_140012B84
0x140012a76  mov     eax, 0FFFFh
0x140012a7b  mov     rcx, [rsp+318h+var_2D8]
0x140012a80  cmp     rcx, rax
0x140012a83  ja      loc_140012B86
0x140012a89  cmp     [rsp+318h+var_2E0], rax
0x140012a8e  ja      loc_140012B86
0x140012a94  lea     rax, [rsp+318h+var_138]
0x140012a9c  test    rcx, rcx
0x140012a9f  cmovz   rax, qword ptr [rsp+318h+var_2B8+8]
0x140012aa5  mov     qword ptr [rsp+318h+var_2B8+8], rax
0x140012aaa  mov     eax, 7Fh
0x140012aaf  cmp     cx, ax
0x140012ab2  jnb     short loc_140012ABB
0x140012ab4  mov     word ptr [rsp+318h+var_2B8], cx
0x140012ab9  jmp     short loc_140012AC3
0x140012abb  movzx   ecx, ax
0x140012abe  mov     word ptr [rsp+318h+var_2B8], ax
0x140012ac3  test    cx, cx
0x140012ac6  jz      short loc_140012AD3
0x140012ac8  add     cx, 2
0x140012acc  mov     word ptr [rsp+318h+var_2B8+2], cx
0x140012ad1  jmp     short loc_140012AD8
0x140012ad3  mov     word ptr [rsp+318h+var_2B8+2], di
0x140012ad8  lea     rax, [rsp+318h+var_1C8]
0x140012ae0  mov     rcx, [rsp+318h+var_2E0]
0x140012ae5  test    rcx, rcx
0x140012ae8  cmovz   rax, qword ptr [rsp+318h+var_2C8+8]
0x140012aee  mov     qword ptr [rsp+318h+var_2C8+8], rax
0x140012af3  mov     eax, 41h ; 'A'
0x140012af8  cmp     cx, ax
0x140012afb  jnb     short loc_140012B04
0x140012afd  mov     word ptr [rsp+318h+var_2C8], cx
0x140012b02  jmp     short loc_140012B0C
0x140012b04  movzx   ecx, ax
0x140012b07  mov     word ptr [rsp+318h+var_2C8], ax
0x140012b0c  test    cx, cx
0x140012b0f  jz      short loc_140012B1C
0x140012b11  add     cx, 2
0x140012b15  mov     word ptr [rsp+318h+var_2C8+2], cx
0x140012b1a  jmp     short loc_140012B21
0x140012b1c  mov     word ptr [rsp+318h+var_2C8+2], di
0x140012b21  lea     r9, [rsp+318h+var_258]
0x140012b29  lea     r8, [rsp+318h+var_2C8]
0x140012b2e  lea     rdx, [rsp+318h+var_2B8]
0x140012b33  mov     rcx, [rsp+318h+pImageFileName]
0x140012b38  call    HsmiOsComputeAppIdentityString
0x140012b3d  mov     ebx, eax
0x140012b3f  test    eax, eax
0x140012b41  js      short loc_140012B86
0x140012b43  lea     rax, [rsp+318h+Handle]
0x140012b48  mov     [rsp+318h+var_2F8], rax
0x140012b4d  mov     r9b, 1
0x140012b50  mov     r8b, r9b
0x140012b53  lea     rdx, [rsp+318h+var_258]
0x140012b5b  lea     rcx, [rsp+318h+var_2A0]
0x140012b60  call    HsmiOsOpenAppPolicyKey
0x140012b65  mov     ebx, eax
0x140012b67  test    eax, eax
0x140012b69  js      short loc_140012B86
0x140012b6b  lea     r9, [rsp+318h+var_2C8]
0x140012b70  lea     r8, [rsp+318h+var_2B8]
0x140012b75  mov     rdx, [rsp+318h+pImageFileName]
0x140012b7a  mov     rcx, [rsp+318h+Handle]; KeyHandle
0x140012b7f  call    HsmiOsPersistAppPolicy
0x140012b84  mov     ebx, eax
0x140012b86  test    r12, r12
0x140012b89  jz      short loc_140012B9A
0x140012b8b  mov     rcx, r12; PrimaryToken
0x140012b8e  call    cs:__imp_PsDereferencePrimaryToken
0x140012b95  nop     dword ptr [rax+rax+00h]
0x140012b9a  mov     rcx, [rsp+318h+pImageFileName]; P
0x140012b9f  test    rcx, rcx
0x140012ba2  jz      short loc_140012BB2
0x140012ba4  xor     edx, edx; Tag
0x140012ba6  call    cs:__imp_ExFreePoolWithTag
0x140012bad  nop     dword ptr [rax+rax+00h]
0x140012bb2  mov     rcx, [rsp+318h+Handle]; Handle
0x140012bb7  test    rcx, rcx
0x140012bba  jz      short loc_140012BC8
0x140012bbc  call    cs:__imp_ZwClose
0x140012bc3  nop     dword ptr [rax+rax+00h]
0x140012bc8  mov     eax, ebx
0x140012bca  mov     rcx, [rsp+318h+var_38]
0x140012bd2  xor     rcx, rsp; StackCookie
0x140012bd5  call    __security_check_cookie
0x140012bda  lea     r11, [rsp+318h+var_28]
0x140012be2  mov     rbx, [r11+40h]
0x140012be6  mov     rsi, [r11+48h]
0x140012bea  mov     rsp, r11
0x140012bed  pop     r15
0x140012bef  pop     r14
0x140012bf1  pop     r13
0x140012bf3  pop     r12
0x140012bf5  pop     rdi
0x140012bf6  retn
  ... truncated ...
```
