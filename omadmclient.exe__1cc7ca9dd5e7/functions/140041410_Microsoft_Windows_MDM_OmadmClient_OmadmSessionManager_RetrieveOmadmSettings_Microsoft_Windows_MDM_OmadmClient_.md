# Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::RetrieveOmadmSettings(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &)

- ea: `0x140041410`
- end: `0x140041700`
- name: `?RetrieveOmadmSettings@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@@Z`
- size: `752`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000e610`
- `0x140013404`
- `0x140041314`
- `0x140041410`
- `0x140069010`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140041487`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140041487`

## string_xrefs

- `0x140041623`: `BackCompatRetry`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::RetrieveOmadmSettings(
        Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, const wchar_t *, _QWORD, int, HKEY *); // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // r8
  int v8; // eax
  unsigned int v9; // ebx
  HKEY v10; // rdx
  _QWORD v12[3]; // [rsp+58h] [rbp-28h] BYREF
  int v13; // [rsp+70h] [rbp-10h]
  unsigned int *v14; // [rsp+78h] [rbp-8h]
  unsigned int v15; // [rsp+B0h] [rbp+30h] BYREF
  HKEY v16; // [rsp+C0h] [rbp+40h] BYREF

  v15 = 0;
  v12[0] = 0;
  v12[1] = "RetrieveOmadmSettings";
  v12[2] = COmaDmLogger::GetLogger();
  v13 = 2;
  v14 = &v15;
  v16 = 0;
  v4 = *((_QWORD *)this + 4);
  v5 = *(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, _QWORD, int, HKEY *))(*(_QWORD *)v4 + 16LL);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled("RetrieveOmadmSettings");
  v7 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM";
  if ( !IsStateSeparationEnabled )
    v7 = L"Software\\Microsoft\\Provisioning\\OMADM";
  v8 = v5(v4, -2147483646, v7, 0, 131097, &v16);
  v9 = v8;
  if ( (v8 & 0xFFFFFFFD) != 0 )
  {
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    v15 = v9;
    LODWORD(v12[0]) = 21063;
    HIDWORD(v12[0]) = v9;
    if ( v16 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 40LL))(*((_QWORD *)this + 4));
  }
  else
  {
    v10 = v16;
    if ( v16 )
    {
      Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(
        this,
        v16,
        L"MaxAuthRetry",
        3u,
        0,
        0xFFFFFFFF,
        (unsigned int *)a2 + 401);
      Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(
        this,
        v16,
        L"SMSResults",
        0,
        0,
        1u,
        (unsigned int *)a2 + 396);
      Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(
        this,
        v16,
        L"ConnRetryFreq",
        3u,
        0,
        0xFFFFFFFF,
        (unsigned int *)a2 + 192);
      Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(
        this,
        v16,
        L"ConnSendRecvTimeout",
        0x2BF20u,
        1u,
        0xFFFFFFFF,
        (unsigned int *)a2 + 193);
      Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(
        this,
        v16,
        L"ConnWaitTime",
        0xEA60u,
        1u,
        0xFFFFFFFF,
        (unsigned int *)a2 + 194);
      Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(
        this,
        v16,
        L"BackCompatRetry",
        1u,
        0,
        1u,
        (unsigned int *)a2 + 195);
      Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(
        this,
        v16,
        L"InitialBackOffTime",
        0x3E80u,
        1u,
        0xFFFFFFFF,
        (unsigned int *)a2 + 198);
      Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(
        this,
        v16,
        L"MaxBackOffTime",
        0x5265C00u,
        1u,
        0xFFFFFFFF,
        (unsigned int *)a2 + 197);
      Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(
        this,
        v16,
        L"MaxInvalidPkgRetry",
        3u,
        0,
        0xFFFFFFFF,
        (unsigned int *)a2 + 196);
      v10 = v16;
    }
    v9 = v15;
    if ( v10 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 40LL))(*((_QWORD *)this + 4));
  }
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v12);
  return v9;
}

```

## disassembly

```asm
0x140041410  mov     [rsp-28h+arg_8], rbx
0x140041415  push    rbp
0x140041416  push    rsi
0x140041417  push    rdi
0x140041418  push    r12
0x14004141a  push    r14
0x14004141c  mov     rbp, rsp
0x14004141f  sub     rsp, 80h
0x140041426  mov     r14, rdx
0x140041429  mov     rsi, rcx
0x14004142c  mov     [rbp+arg_0], 0
0x140041433  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140041438  mov     [rbp+var_28], 0
0x140041440  lea     rcx, aRetrieveomadms; "RetrieveOmadmSettings"
0x140041447  mov     [rbp+var_20], rcx
0x14004144b  mov     [rbp+var_18], rax
0x14004144f  mov     [rbp+var_10], 2
0x140041456  lea     rax, [rbp+arg_0]
0x14004145a  mov     [rbp+var_8], rax
0x14004145e  mov     [rbp+arg_10], 0
0x140041466  lea     rax, [rbp+arg_10]
0x14004146a  mov     [rbp+var_40], rax
0x14004146e  mov     [rbp+var_38], rsi
0x140041472  mov     r12d, 1
0x140041478  mov     [rbp+var_30], r12b
0x14004147c  mov     rdi, [rsi+20h]
0x140041480  mov     rax, [rdi]
0x140041483  mov     rbx, [rax+10h]
0x140041487  call    cs:__imp_RtlIsStateSeparationEnabled
0x14004148e  nop     dword ptr [rax+rax+00h]
0x140041493  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x14004149a  lea     r8, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Provisioni"...
0x1400414a1  test    al, al
0x1400414a3  cmovz   r8, rcx
0x1400414a7  lea     rax, [rbp+arg_10]
0x1400414ab  mov     qword ptr [rsp+80h+var_58], rax
0x1400414b0  mov     [rsp+80h+var_60], 20019h
0x1400414b8  xor     r9d, r9d
0x1400414bb  mov     rdx, 0FFFFFFFF80000002h
0x1400414c2  mov     rcx, rdi
0x1400414c5  mov     rax, rbx
0x1400414c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400414cd  mov     ebx, eax
0x1400414cf  test    eax, 0FFFFFFFDh
0x1400414d4  jz      short loc_14004150F
0x1400414d6  test    eax, eax
0x1400414d8  jle     short loc_1400414E3
0x1400414da  movzx   ebx, ax
0x1400414dd  or      ebx, 80070000h
0x1400414e3  mov     [rbp+arg_0], ebx
0x1400414e6  mov     dword ptr [rbp+var_28], 5247h
0x1400414ed  mov     dword ptr [rbp+var_28+4], ebx
0x1400414f0  mov     rdx, [rbp+arg_10]
0x1400414f4  test    rdx, rdx
0x1400414f7  jz      short loc_14004150A
0x1400414f9  mov     rcx, [rsi+20h]
0x1400414fd  mov     rax, [rcx]
0x140041500  mov     rax, [rax+28h]
0x140041504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041509  nop
0x14004150a  jmp     loc_1400416DD
0x14004150f  mov     rdx, [rbp+arg_10]; HKEY
0x140041513  test    rdx, rdx
0x140041516  jz      loc_1400416C4
0x14004151c  lea     rax, [r14+644h]
0x140041523  mov     [rsp+80h+var_50], rax; unsigned int *
0x140041528  or      edi, 0FFFFFFFFh
0x14004152b  mov     [rsp+80h+var_58], edi; unsigned int
0x14004152f  mov     [rsp+80h+var_60], 0; unsigned int
0x140041537  mov     ebx, 3
0x14004153c  mov     r9d, ebx; unsigned int
0x14004153f  lea     r8, ?gc_szRetriesValueName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "MaxAuthRetry"
0x140041546  mov     rcx, rsi; this
0x140041549  call    ?ReadBoundedDwordRegValue@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@IEAAXPEAUHKEY__@@PEBGKKKPEAK@Z; Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(HKEY__ *,ushort const *,ulong,ulong,ulong,ulong *)
0x14004154e  lea     rax, [r14+630h]
0x140041555  mov     [rsp+80h+var_50], rax; unsigned int *
0x14004155a  mov     [rsp+80h+var_58], r12d; unsigned int
0x14004155f  mov     [rsp+80h+var_60], 0; unsigned int
0x140041567  xor     r9d, r9d; unsigned int
0x14004156a  lea     r8, ?gc_szSmsResultsValueName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "SMSResults"
0x140041571  mov     rdx, [rbp+arg_10]; HKEY
0x140041575  mov     rcx, rsi; this
0x140041578  call    ?ReadBoundedDwordRegValue@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@IEAAXPEAUHKEY__@@PEBGKKKPEAK@Z; Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(HKEY__ *,ushort const *,ulong,ulong,ulong,ulong *)
0x14004157d  lea     rax, [r14+300h]
0x140041584  mov     [rsp+80h+var_50], rax; unsigned int *
0x140041589  mov     [rsp+80h+var_58], edi; unsigned int
0x14004158d  mov     [rsp+80h+var_60], 0; unsigned int
0x140041595  mov     r9d, ebx; unsigned int
0x140041598  lea     r8, ?gc_szConnectionRetryFreqName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "ConnRetryFreq"
0x14004159f  mov     rdx, [rbp+arg_10]; HKEY
0x1400415a3  mov     rcx, rsi; this
0x1400415a6  call    ?ReadBoundedDwordRegValue@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@IEAAXPEAUHKEY__@@PEBGKKKPEAK@Z; Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(HKEY__ *,ushort const *,ulong,ulong,ulong,ulong *)
0x1400415ab  lea     rax, [r14+304h]
0x1400415b2  mov     [rsp+80h+var_50], rax; unsigned int *
0x1400415b7  mov     [rsp+80h+var_58], edi; unsigned int
0x1400415bb  mov     [rsp+80h+var_60], r12d; unsigned int
0x1400415c0  mov     r9d, 2BF20h; unsigned int
0x1400415c6  lea     r8, ?gc_szConnectionSendRecvTimeout@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "ConnSendRecvTimeout"
0x1400415cd  mov     rdx, [rbp+arg_10]; HKEY
0x1400415d1  mov     rcx, rsi; this
0x1400415d4  call    ?ReadBoundedDwordRegValue@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@IEAAXPEAUHKEY__@@PEBGKKKPEAK@Z; Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(HKEY__ *,ushort const *,ulong,ulong,ulong,ulong *)
0x1400415d9  lea     rax, [r14+308h]
0x1400415e0  mov     [rsp+80h+var_50], rax; unsigned int *
0x1400415e5  mov     [rsp+80h+var_58], edi; unsigned int
0x1400415e9  mov     [rsp+80h+var_60], r12d; unsigned int
0x1400415ee  mov     r9d, 0EA60h; unsigned int
0x1400415f4  lea     r8, ?gc_szConnectionWaitTimeName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "ConnWaitTime"
0x1400415fb  mov     rdx, [rbp+arg_10]; HKEY
0x1400415ff  mov     rcx, rsi; this
0x140041602  call    ?ReadBoundedDwordRegValue@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@IEAAXPEAUHKEY__@@PEBGKKKPEAK@Z; Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(HKEY__ *,ushort const *,ulong,ulong,ulong,ulong *)
0x140041607  lea     rax, [r14+30Ch]
0x14004160e  mov     [rsp+80h+var_50], rax; unsigned int *
0x140041613  mov     [rsp+80h+var_58], r12d; unsigned int
0x140041618  mov     [rsp+80h+var_60], 0; unsigned int
0x140041620  mov     r9d, r12d; unsigned int
0x140041623  lea     r8, ?gc_szBackCompatRetryName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "BackCompatRetry"
0x14004162a  mov     rdx, [rbp+arg_10]; HKEY
0x14004162e  mov     rcx, rsi; this
0x140041631  call    ?ReadBoundedDwordRegValue@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@IEAAXPEAUHKEY__@@PEBGKKKPEAK@Z; Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(HKEY__ *,ushort const *,ulong,ulong,ulong,ulong *)
0x140041636  lea     rax, [r14+318h]
0x14004163d  mov     [rsp+80h+var_50], rax; unsigned int *
0x140041642  mov     [rsp+80h+var_58], edi; unsigned int
0x140041646  mov     [rsp+80h+var_60], r12d; unsigned int
0x14004164b  mov     r9d, 3E80h; unsigned int
0x140041651  lea     r8, ?gc_szInitialBackOffTimeName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "InitialBackOffTime"
0x140041658  mov     rdx, [rbp+arg_10]; HKEY
0x14004165c  mov     rcx, rsi; this
0x14004165f  call    ?ReadBoundedDwordRegValue@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@IEAAXPEAUHKEY__@@PEBGKKKPEAK@Z; Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(HKEY__ *,ushort const *,ulong,ulong,ulong,ulong *)
0x140041664  lea     rax, [r14+314h]
0x14004166b  mov     [rsp+80h+var_50], rax; unsigned int *
0x140041670  mov     [rsp+80h+var_58], edi; unsigned int
0x140041674  mov     [rsp+80h+var_60], r12d; unsigned int
0x140041679  mov     r9d, 5265C00h; unsigned int
0x14004167f  lea     r8, ?gc_szMaxBackOffTimeName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "MaxBackOffTime"
0x140041686  mov     rdx, [rbp+arg_10]; HKEY
0x14004168a  mov     rcx, rsi; this
0x14004168d  call    ?ReadBoundedDwordRegValue@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@IEAAXPEAUHKEY__@@PEBGKKKPEAK@Z; Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(HKEY__ *,ushort const *,ulong,ulong,ulong,ulong *)
0x140041692  lea     rax, [r14+310h]
0x140041699  mov     [rsp+80h+var_50], rax; unsigned int *
0x14004169e  mov     [rsp+80h+var_58], edi; unsigned int
0x1400416a2  mov     [rsp+80h+var_60], 0; unsigned int
0x1400416aa  mov     r9d, ebx; unsigned int
0x1400416ad  lea     r8, ?gc_szMaxInvalidPkgRetry@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "MaxInvalidPkgRetry"
0x1400416b4  mov     rdx, [rbp+arg_10]; HKEY
0x1400416b8  mov     rcx, rsi; this
0x1400416bb  call    ?ReadBoundedDwordRegValue@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@IEAAXPEAUHKEY__@@PEBGKKKPEAK@Z; Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::ReadBoundedDwordRegValue(HKEY__ *,ushort const *,ulong,ulong,ulong,ulong *)
0x1400416c0  mov     rdx, [rbp+arg_10]
0x1400416c4  mov     ebx, [rbp+arg_0]
0x1400416c7  test    rdx, rdx
0x1400416ca  jz      short loc_1400416DD
0x1400416cc  mov     rcx, [rsi+20h]
0x1400416d0  mov     rax, [rcx]
0x1400416d3  mov     rax, [rax+28h]
0x1400416d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400416dc  nop
0x1400416dd  lea     rcx, [rbp+var_28]; this
0x1400416e1  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x1400416e6  mov     eax, ebx
0x1400416e8  mov     rbx, [rsp+80h+arg_8]
0x1400416f0  add     rsp, 80h
0x1400416f7  pop     r14
0x1400416f9  pop     r12
0x1400416fb  pop     rdi
0x1400416fc  pop     rsi
0x1400416fd  pop     rbp
0x1400416fe  retn
```
