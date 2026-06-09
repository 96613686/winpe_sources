# FrsReplicator::InitializeSsrKey(void)

- ea: `0x1400ec8c4`
- end: `0x1400eccb5`
- name: `?InitializeSsrKey@FrsReplicator@@IEAAXXZ`
- size: `1009`
- prototype: `void __fastcall(FrsReplicator *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x1400ec46c`

## callees

- `0x1400036a0`
- `0x14000c870`
- `0x14000c910`
- `0x14000cb00`
- `0x14000cdc0`
- `0x14000e34c`
- `0x140028eec`
- `0x14004b80c`
- `0x14004d4d0`
- `0x14004d658`
- `0x140072bb0`
- `0x1400ec8c4`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400ec967`
- `KERNEL32!GetCurrentThreadId` at `0x1400ec9ec`
- `KERNEL32!GetCurrentThreadId` at `0x1400eca8c`
- `KERNEL32!GetCurrentThreadId` at `0x1400ecbc6`
- `KERNEL32!GetCurrentThreadId` at `0x1400ec967`
- `KERNEL32!GetCurrentThreadId` at `0x1400ec9ec`
- `KERNEL32!GetCurrentThreadId` at `0x1400eca8c`
- `KERNEL32!GetCurrentThreadId` at `0x1400ecbc6`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1400ecabd`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1400ecb1a`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1400ecabd`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1400ecb1a`

## string_xrefs

- `0x1400ec94e`: `System\CurrentControlSet\Services\DFSR\Restore`
- `0x1400eca7c`: `Failed to get SSR authoritative information. Invalid registry key type:`
- `0x1400ecbb6`: `Failed to get SSR authoritative information. Invalid registry key value:%?`
- `0x1400ecc5f`: `Failed to get SSR registry information. Error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FrsReplicator::InitializeSsrKey(FrsReplicator *this)
{
  char *v2; // rsi
  __int64 SsrInstanceKey; // rbx
  unsigned int v4; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  DWORD v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  const wchar_t *v12; // rdx
  bool v13; // zf
  LPCRITICAL_SECTION v14; // rax
  __int64 v15; // rcx
  DWORD v16; // [rsp+40h] [rbp-51h]
  DWORD v17; // [rsp+40h] [rbp-51h]
  const wchar_t *v18; // [rsp+58h] [rbp-39h] BYREF
  int v19; // [rsp+60h] [rbp-31h]
  int v20; // [rsp+64h] [rbp-2Dh]
  const wchar_t *v21; // [rsp+68h] [rbp-29h]
  unsigned int v22; // [rsp+70h] [rbp-21h] BYREF
  unsigned int MaxCount[3]; // [rsp+74h] [rbp-1Dh] BYREF
  _QWORD v24[3]; // [rsp+80h] [rbp-11h] BYREF
  wchar_t String1[20]; // [rsp+98h] [rbp+7h] BYREF

  v2 = (char *)this + 120;
  SsrInstanceKey = PdbManager::GetSsrInstanceKey((char *)this + 104, (char *)this + 120);
  *(_QWORD *)&MaxCount[1] = SsrInstanceKey;
  if ( !SsrInstanceKey && *(_QWORD *)(*(_QWORD *)v2 + 8LL) )
  {
    memset(v24, 0, sizeof(v24));
    v4 = ATL::CRegKey::Open(
           (ATL::CRegKey *)v24,
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\DFSR\\Restore",
           0x2001Fu);
    CurrentThreadId = GetCurrentThreadId();
    SsrInstanceKey = FrsStatusList::PushNewError(
                       v6,
                       v4,
                       0,
                       1,
                       "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
                       "FrsReplicator::InitializeSsrKey",
                       4823,
                       CurrentThreadId,
                       0);
    *(_QWORD *)&MaxCount[1] = SsrInstanceKey;
    if ( SsrInstanceKey )
      goto LABEL_28;
    MaxCount[0] = 36;
    v22 = 1;
    v7 = ATL::CRegKey::QueryValue((ATL::CRegKey *)v24, L"SYSVOL", &v22, String1, MaxCount);
    v8 = GetCurrentThreadId();
    SsrInstanceKey = FrsStatusList::PushNewError(
                       v9,
                       v7,
                       0,
                       1,
                       "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
                       "FrsReplicator::InitializeSsrKey",
                       4831,
                       v8,
                       0);
    *(_QWORD *)&MaxCount[1] = SsrInstanceKey;
    if ( SsrInstanceKey )
      goto LABEL_28;
    if ( v22 != 1 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v18 = L"FrsReplicator::InitializeSsrKey";
        v19 = 4835;
        v20 = 2;
        v21 = L"FREP";
        dbgobj::DbgPrint<unsigned short,unsigned int>(
          &v18,
          L"Failed to get SSR authoritative information. Invalid registry key type:",
          &v22);
      }
      v16 = GetCurrentThreadId();
      v11 = FrsStatusList::PushNewError(
              v10,
              2,
              0,
              1,
              "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
              "FrsReplicator::InitializeSsrKey",
              4836,
              v16,
              0);
LABEL_27:
      *(_QWORD *)&MaxCount[1] = v11;
      SsrInstanceKey = v11;
      goto LABEL_28;
    }
    if ( !wcsncmp(String1, L"authoritative", MaxCount[0]) )
    {
      *((_DWORD *)this + 32) = 1;
      if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
        goto LABEL_28;
      v19 = 4840;
      v12 = L"SSR authoritative restore";
    }
    else
    {
      v13 = wcsncmp(String1, L"non-authoritative", MaxCount[0]) == 0;
      v14 = g_DebugLog;
      if ( !v13 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v18 = L"FrsReplicator::InitializeSsrKey";
          v19 = 4847;
          v20 = 2;
          v21 = L"FREP";
          dbgobj::DbgPrint<unsigned short,unsigned short [39]>(
            &v18,
            L"Failed to get SSR authoritative information. Invalid registry key value:%?",
            String1);
        }
        v17 = GetCurrentThreadId();
        v11 = FrsStatusList::PushNewError(
                v15,
                2,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
                "FrsReplicator::InitializeSsrKey",
                4848,
                v17,
                0);
        goto LABEL_27;
      }
      *((_DWORD *)this + 32) = 0;
      if ( !v14 || !LODWORD(v14[1].LockSemaphore) || SLODWORD(v14[1].OwningThread) < 4 )
        goto LABEL_28;
      v19 = 4844;
      v12 = L"SSR non-authoritative restore";
    }
    v21 = L"FREP";
    v20 = 4;
    v18 = L"FrsReplicator::InitializeSsrKey";
    dbgobj::DbgPrint<unsigned short>(&v18, v12);
LABEL_28:
    ATL::CRegKey::Close((ATL::CRegKey *)v24);
  }
  if ( SsrInstanceKey )
  {
    if ( *(_DWORD *)(SsrInstanceKey + 4) != 2
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v18 = L"FrsReplicator::InitializeSsrKey";
      v19 = 4856;
      v20 = 3;
      v21 = L"FREP";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(
        &v18,
        L"Failed to get SSR registry information. Error:%?",
        SsrInstanceKey);
    }
    CLEAR_ERROR((struct FrsStatus **)&MaxCount[1]);
    *(_OWORD *)((char *)this + 104) = 0;
    FrsStringImpl<unsigned short,char>::SetEmpty(v2);
  }
}

```

## disassembly

```asm
0x1400ec8c4  mov     rax, rsp
0x1400ec8c7  mov     [rax+10h], rbx
0x1400ec8cb  mov     [rax+18h], rsi
0x1400ec8cf  mov     [rax+20h], rdi
0x1400ec8d3  push    rbp
0x1400ec8d4  push    r12
0x1400ec8d6  push    r13
0x1400ec8d8  push    r14
0x1400ec8da  push    r15
0x1400ec8dc  lea     rbp, [rax-5Fh]
0x1400ec8e0  sub     rsp, 0C0h
0x1400ec8e7  mov     rax, cs:__security_cookie
0x1400ec8ee  xor     rax, rsp
0x1400ec8f1  mov     [rbp+57h+var_28], rax
0x1400ec8f5  mov     rdi, rcx
0x1400ec8f8  lea     rsi, [rcx+78h]
0x1400ec8fc  mov     rdx, rsi
0x1400ec8ff  add     rcx, 68h ; 'h'
0x1400ec903  call    ?GetSsrInstanceKey@PdbManager@@SAPEAVFrsStatus@@AEAU_GUID@@AEAV?$FrsStringImpl@GD@@@Z; PdbManager::GetSsrInstanceKey(_GUID &,FrsStringImpl<ushort,char> &)
0x1400ec908  mov     rbx, rax
0x1400ec90b  mov     qword ptr [rbp+57h+MaxCount+4], rax
0x1400ec90f  mov     r12d, 2
0x1400ec915  lea     r13, aFrsreplicatorI_1; "FrsReplicator::InitializeSsrKey"
0x1400ec91c  lea     rcx, aFrep; "FREP"
0x1400ec923  xor     r15d, r15d
0x1400ec926  test    rax, rax
0x1400ec929  jnz     loc_1400ECC23
0x1400ec92f  mov     rax, [rsi]
0x1400ec932  cmp     [rax+8], r15
0x1400ec936  jz      loc_1400ECC23
0x1400ec93c  mov     [rbp+57h+var_68], r15
0x1400ec940  mov     [rbp+57h+var_60], r15
0x1400ec944  mov     [rbp+57h+var_58], r15
0x1400ec948  mov     r9d, 2001Fh; unsigned int
0x1400ec94e  lea     r8, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\DF"...
0x1400ec955  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1400ec95c  lea     rcx, [rbp+57h+var_68]; this
0x1400ec960  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400ec965  mov     ebx, eax
0x1400ec967  call    cs:__imp_GetCurrentThreadId
0x1400ec96e  nop     dword ptr [rax+rax+00h]
0x1400ec973  mov     [rsp+0E0h+var_A0], r15
0x1400ec978  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1400ec97c  mov     [rsp+0E0h+var_B0], 12D7h
0x1400ec984  lea     rax, aFrsreplicatorI; "FrsReplicator::InitializeSsrKey"
0x1400ec98b  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400ec990  lea     rax, aBaseFsRemotefs_28; "base\\fs\\remotefs\\frs\\src\\sync\\frs"...
0x1400ec997  mov     [rsp+0E0h+var_C0], rax
0x1400ec99c  lea     r9d, [r12-1]
0x1400ec9a1  xor     r8d, r8d
0x1400ec9a4  mov     edx, ebx
0x1400ec9a6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ec9ab  mov     rbx, rax
0x1400ec9ae  mov     qword ptr [rbp+57h+MaxCount+4], rax
0x1400ec9b2  test    rax, rax
0x1400ec9b5  jnz     loc_1400ECC13
0x1400ec9bb  mov     dword ptr [rbp+57h+MaxCount], 24h ; '$'
0x1400ec9c2  mov     [rbp+57h+var_78], 1
0x1400ec9c9  lea     rax, [rbp+57h+MaxCount]
0x1400ec9cd  mov     [rsp+0E0h+var_C0], rax; unsigned int *
0x1400ec9d2  lea     r9, [rbp+57h+String1]; void *
0x1400ec9d6  lea     r8, [rbp+57h+var_78]; unsigned int *
0x1400ec9da  lea     rdx, aSysvol_0; "SYSVOL"
0x1400ec9e1  lea     rcx, [rbp+57h+var_68]; this
0x1400ec9e5  call    ?QueryValue@CRegKey@ATL@@QEAAJPEBGPEAKPEAX1@Z; ATL::CRegKey::QueryValue(ushort const *,ulong *,void *,ulong *)
0x1400ec9ea  mov     ebx, eax
0x1400ec9ec  call    cs:__imp_GetCurrentThreadId
0x1400ec9f3  nop     dword ptr [rax+rax+00h]
0x1400ec9f8  mov     [rsp+0E0h+var_A0], r15
0x1400ec9fd  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1400eca01  mov     [rsp+0E0h+var_B0], 12DFh
0x1400eca09  lea     rax, aFrsreplicatorI; "FrsReplicator::InitializeSsrKey"
0x1400eca10  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400eca15  lea     rax, aBaseFsRemotefs_28; "base\\fs\\remotefs\\frs\\src\\sync\\frs"...
0x1400eca1c  mov     [rsp+0E0h+var_C0], rax
0x1400eca21  lea     r9d, [r12-1]
0x1400eca26  xor     r8d, r8d
0x1400eca29  mov     edx, ebx
0x1400eca2b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400eca30  mov     rbx, rax
0x1400eca33  mov     qword ptr [rbp+57h+MaxCount+4], rax
0x1400eca37  test    rax, rax
0x1400eca3a  jnz     loc_1400ECC13
0x1400eca40  cmp     [rbp+57h+var_78], 1
0x1400eca44  jz      short loc_1400ECAAE
0x1400eca46  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400eca4d  test    rax, rax
0x1400eca50  jz      short loc_1400ECA8C
0x1400eca52  cmp     [rax+40h], r15d
0x1400eca56  jz      short loc_1400ECA8C
0x1400eca58  cmp     [rax+38h], r12d
0x1400eca5c  jl      short loc_1400ECA8C
0x1400eca5e  mov     [rbp+57h+var_90], r13
0x1400eca62  mov     [rbp+57h+var_88], 12E3h
0x1400eca69  mov     [rbp+57h+var_84], r12d
0x1400eca6d  lea     rax, aFrep; "FREP"
0x1400eca74  mov     [rbp+57h+var_80], rax
0x1400eca78  lea     r8, [rbp+57h+var_78]
0x1400eca7c  lea     rdx, aFailedToGetSsr; "Failed to get SSR authoritative informa"...
0x1400eca83  lea     rcx, [rbp+57h+var_90]
0x1400eca87  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x1400eca8c  call    cs:__imp_GetCurrentThreadId
0x1400eca93  nop     dword ptr [rax+rax+00h]
0x1400eca98  mov     [rsp+0E0h+var_A0], r15
0x1400eca9d  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1400ecaa1  mov     [rsp+0E0h+var_B0], 12E4h
0x1400ecaa9  jmp     loc_1400ECBE3
0x1400ecaae  mov     r8d, dword ptr [rbp+57h+MaxCount]; MaxCount
0x1400ecab2  lea     rdx, aAuthoritative_1; "authoritative"
0x1400ecab9  lea     rcx, [rbp+57h+String1]; String1
0x1400ecabd  call    cs:__imp_wcsncmp
0x1400ecac4  nop     dword ptr [rax+rax+00h]
0x1400ecac9  test    eax, eax
0x1400ecacb  jnz     short loc_1400ECB0B
0x1400ecacd  mov     dword ptr [rdi+80h], 1
0x1400ecad7  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ecade  test    rax, rax
0x1400ecae1  jz      loc_1400ECC13
0x1400ecae7  cmp     [rax+40h], r15d
0x1400ecaeb  jz      loc_1400ECC13
0x1400ecaf1  cmp     dword ptr [rax+38h], 4
0x1400ecaf5  jl      loc_1400ECC13
0x1400ecafb  mov     [rbp+57h+var_88], 12E8h
0x1400ecb02  lea     rdx, aSsrAuthoritati; "SSR authoritative restore"
0x1400ecb09  jmp     short loc_1400ECB63
0x1400ecb0b  mov     r8d, dword ptr [rbp+57h+MaxCount]; MaxCount
0x1400ecb0f  lea     rdx, aNonAuthoritati; "non-authoritative"
0x1400ecb16  lea     rcx, [rbp+57h+String1]; String1
0x1400ecb1a  call    cs:__imp_wcsncmp
0x1400ecb21  nop     dword ptr [rax+rax+00h]
0x1400ecb26  test    eax, eax
0x1400ecb28  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ecb2f  jnz     short loc_1400ECB87
0x1400ecb31  mov     [rdi+80h], r15d
0x1400ecb38  test    rax, rax
0x1400ecb3b  jz      loc_1400ECC13
0x1400ecb41  cmp     [rax+40h], r15d
0x1400ecb45  jz      loc_1400ECC13
0x1400ecb4b  cmp     dword ptr [rax+38h], 4
0x1400ecb4f  jl      loc_1400ECC13
0x1400ecb55  mov     [rbp+57h+var_88], 12ECh
0x1400ecb5c  lea     rdx, aSsrNonAuthorit; "SSR non-authoritative restore"
0x1400ecb63  lea     rax, aFrep; "FREP"
0x1400ecb6a  mov     [rbp+57h+var_80], rax
0x1400ecb6e  mov     [rbp+57h+var_84], 4
0x1400ecb75  mov     [rbp+57h+var_90], r13
0x1400ecb79  lea     rcx, [rbp+57h+var_90]
0x1400ecb7d  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400ecb82  jmp     loc_1400ECC13
0x1400ecb87  test    rax, rax
0x1400ecb8a  jz      short loc_1400ECBC6
0x1400ecb8c  cmp     [rax+40h], r15d
0x1400ecb90  jz      short loc_1400ECBC6
0x1400ecb92  cmp     [rax+38h], r12d
0x1400ecb96  jl      short loc_1400ECBC6
0x1400ecb98  mov     [rbp+57h+var_90], r13
0x1400ecb9c  mov     [rbp+57h+var_88], 12EFh
0x1400ecba3  mov     [rbp+57h+var_84], r12d
0x1400ecba7  lea     rax, aFrep; "FREP"
0x1400ecbae  mov     [rbp+57h+var_80], rax
0x1400ecbb2  lea     r8, [rbp+57h+String1]
0x1400ecbb6  lea     rdx, aFailedToGetSsr_1; "Failed to get SSR authoritative informa"...
0x1400ecbbd  lea     rcx, [rbp+57h+var_90]
0x1400ecbc1  call    ??$DbgPrint@G$$BY0CH@G@dbgobj@@QEAA_KPEBGAEAY0CH@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [39]>(ushort const *,ushort const (&)[39])
0x1400ecbc6  call    cs:__imp_GetCurrentThreadId
0x1400ecbcd  nop     dword ptr [rax+rax+00h]
0x1400ecbd2  mov     [rsp+0E0h+var_A0], r15
0x1400ecbd7  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1400ecbdb  mov     [rsp+0E0h+var_B0], 12F0h
0x1400ecbe3  lea     rax, aFrsreplicatorI; "FrsReplicator::InitializeSsrKey"
0x1400ecbea  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400ecbef  lea     rax, aBaseFsRemotefs_28; "base\\fs\\remotefs\\frs\\src\\sync\\frs"...
0x1400ecbf6  mov     [rsp+0E0h+var_C0], rax
0x1400ecbfb  mov     r9d, 1
0x1400ecc01  xor     r8d, r8d
0x1400ecc04  mov     edx, r12d
0x1400ecc07  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ecc0c  mov     qword ptr [rbp+57h+MaxCount+4], rax
0x1400ecc10  mov     rbx, rax
0x1400ecc13  lea     rcx, [rbp+57h+var_68]; this
0x1400ecc17  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400ecc1c  lea     rcx, aFrep; "FREP"
0x1400ecc23  test    rbx, rbx
0x1400ecc26  jz      short loc_1400ECC87
0x1400ecc28  cmp     [rbx+4], r12d
0x1400ecc2c  jz      short loc_1400ECC6F
0x1400ecc2e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ecc35  test    rax, rax
0x1400ecc38  jz      short loc_1400ECC6F
0x1400ecc3a  cmp     [rax+40h], r15d
0x1400ecc3e  jz      short loc_1400ECC6F
0x1400ecc40  cmp     dword ptr [rax+38h], 3
0x1400ecc44  jl      short loc_1400ECC6F
0x1400ecc46  mov     [rbp+57h+var_90], r13
0x1400ecc4a  mov     [rbp+57h+var_88], 12F8h
0x1400ecc51  mov     [rbp+57h+var_84], 3
0x1400ecc58  mov     [rbp+57h+var_80], rcx
0x1400ecc5c  mov     r8, rbx
0x1400ecc5f  lea     rdx, aFailedToGetSsr_0; "Failed to get SSR registry information."...
0x1400ecc66  lea     rcx, [rbp+57h+var_90]
0x1400ecc6a  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1400ecc6f  lea     rcx, [rbp+57h+MaxCount+4]; struct FrsStatus **
0x1400ecc73  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400ecc78  xorps   xmm0, xmm0
0x1400ecc7b  movups  xmmword ptr [rdi+68h], xmm0
0x1400ecc7f  mov     rcx, rsi
0x1400ecc82  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1400ecc87  mov     rcx, [rbp+57h+var_28]
0x1400ecc8b  xor     rcx, rsp; StackCookie
0x1400ecc8e  call    __security_check_cookie
0x1400ecc93  lea     r11, [rsp+0E0h+var_20]
0x1400ecc9b  mov     rbx, [r11+38h]
0x1400ecc9f  mov     rsi, [r11+40h]
0x1400ecca3  mov     rdi, [r11+48h]
0x1400ecca7  mov     rsp, r11
0x1400eccaa  pop     r15
0x1400eccac  pop     r14
0x1400eccae  pop     r13
0x1400eccb0  pop     r12
0x1400eccb2  pop     rbp
0x1400eccb3  retn
```
