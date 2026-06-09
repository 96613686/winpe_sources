# Telemetryp_EventDataResolversComplete(unsigned __int64,_PCA_CHAIN_HISTORY_ROW *,_PCA_CHAIN_HISTORY_ROW *,void *,int,ushort const *)

- ea: `0x18001e6ec`
- end: `0x18001ebb0`
- name: `?Telemetryp_EventDataResolversComplete@@YAK_KPEAU_PCA_CHAIN_HISTORY_ROW@@1PEAXHPEBG@Z`
- size: `1220`
- prototype: `__int64 __fastcall(unsigned __int64, struct _PCA_CHAIN_HISTORY_ROW *, struct _PCA_CHAIN_HISTORY_ROW *, void *, int, wchar_t *Source)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001e440`

## callees

- `0x180012920`
- `0x180013fac`
- `0x1800156a4`
- `0x18001e6ec`
- `0x18001ec64`
- `0x18001fc44`
- `0x18001fca0`
- `0x180026858`
- `0x180034994`
- `0x18008c814`
- `0x1800b0bf4`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001eb79`
- `msvcrt!wcscpy_s` at `0x18001eb79`
- `ntdll!RtlLeaveCriticalSection` at `0x18001eb97`
- `ntdll!RtlLeaveCriticalSection` at `0x18001eb97`
- `ntdll!RtlDoesFileExists_U` at `0x18001e88d`
- `ntdll!RtlDoesFileExists_U` at `0x18001e88d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e743`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001eb8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001eb8e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e739`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e739`

## string_xrefs

- `0x18001e756`: `Telemetryp_EventDataResolversComplete`
- `0x18001e8cc`: `Telemetryp_EventDataResolversComplete`
- `0x18001e8fc`: `Telemetryp_EventDataResolversComplete`
- `0x18001e934`: `Telemetryp_EventDataResolversComplete`
- `0x18001e749`: `Failed to impersonate user [%d]`
- `0x18001e95f`: `Error when processing resolver complete message`
- `0x18001e83c`: `InstallerSuccess`
- `0x18001e9af`: `Exe changed during run`

## pseudocode

```c
__int64 __fastcall Telemetryp_EventDataResolversComplete(
        unsigned __int64 a1,
        struct _PCA_CHAIN_HISTORY_ROW *a2,
        struct _PCA_CHAIN_HISTORY_ROW *a3,
        void *a4,
        int a5,
        wchar_t *Source)
{
  unsigned int v10; // ebx
  struct _PCA_CHAIN *v11; // rsi
  struct _PCA_TELEMETRY_EVENT_DATA *v12; // rbx
  DWORD LastError; // edi
  int v14; // ebp
  __int64 v15; // r8
  const char *v16; // rdx
  int v17; // eax
  unsigned int MatchingInfo; // eax
  const unsigned __int16 *v19; // r8
  int v20; // eax
  const char *v21; // rdx
  const unsigned __int16 *v22; // r8
  unsigned int v23; // edx
  __int64 v24; // rax

  v10 = *((_DWORD *)PcapChainFromHandle(a1) + 4);
  v11 = PcapChainFromHandle(a1);
  v12 = Telemetryp_EventDataAcquire(v10);
  if ( v12 )
  {
    if ( !ImpersonateLoggedOnUser(a4) )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"Telemetryp_EventDataResolversComplete",
        1609,
        (unsigned int)"Failed to impersonate user [%d]");
      v14 = 0;
      if ( !LastError )
        goto LABEL_76;
LABEL_38:
      Telemetryp_SetDiscardedReason(v12, "Error when processing resolver complete message", 18);
      if ( !v14 )
      {
LABEL_76:
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v12);
        return LastError;
      }
LABEL_75:
      RevertToSelf();
      goto LABEL_76;
    }
    v14 = 1;
    if ( *((_DWORD *)v11 + 1193) )
      goto LABEL_80;
    if ( *((_DWORD *)a3 + 8) == 1 )
      *((_QWORD *)v12 + 645) = "FirstRunNoLayer";
    if ( *((_DWORD *)a3 + 9) == 10 )
    {
      *((_QWORD *)v12 + 645) = "StickyNoLayer";
      *((_QWORD *)v12 + 499) |= 0x200000000000uLL;
    }
    if ( *((_DWORD *)v11 + 1193) )
    {
LABEL_80:
      if ( !*((_DWORD *)a2 + 8) )
      {
        v15 = 22;
        v16 = "No baseline data";
LABEL_14:
        Telemetryp_SetDiscardedReason(v12, v16, v15);
LABEL_74:
        LastError = 0;
        goto LABEL_75;
      }
      if ( *((_DWORD *)a3 + 8) == 1 )
        *((_QWORD *)v12 + 645) = "FirstRunLayer";
      if ( *((_DWORD *)a3 + 9) == 5 )
      {
        *((_QWORD *)v12 + 499) |= 0x800uLL;
        *((_QWORD *)v12 + 645) = "StickyLayer";
      }
    }
    v17 = *((_DWORD *)v12 + 1001);
    if ( v17 && *((_QWORD *)v12 + 504) )
    {
      *((_QWORD *)v12 + 499) |= 0x20000000uLL;
      *((_QWORD *)v12 + 645) = "InstallerSuccess";
    }
    if ( !*((_QWORD *)v12 + 645) )
    {
      v15 = 0;
      v16 = "No reason to send";
      goto LABEL_14;
    }
    if ( !*((_DWORD *)v12 + 412) )
    {
      if ( v17 != 1 || *((_DWORD *)v12 + 1002) )
      {
        if ( !RtlDoesFileExists_U((PCWSTR)v11 + 1568) )
        {
          v15 = 17;
          v16 = "File no longer exists";
          goto LABEL_14;
        }
        MatchingInfo = PcaUtilityGetMatchingInfo((wchar_t *)v12 + 32, (LPCWSTR)v11 + 1568, v19);
      }
      else
      {
        MatchingInfo = Telemetryp_InstallerGetMatchingInfo(v12);
      }
      LastError = MatchingInfo;
      if ( MatchingInfo )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"Telemetryp_EventDataResolversComplete",
          1706,
          (unsigned int)"Failed to get matching info for chain head [%d]");
        goto LABEL_38;
      }
      v20 = *((_DWORD *)v12 + 276);
      if ( !v20 )
      {
        LastError = 1359;
        AslLogCallPrintf(1, (unsigned int)"Telemetryp_EventDataResolversComplete", 1716, (unsigned int)"Bad size [%d]");
        v21 = "File size not retrieved";
LABEL_37:
        Telemetryp_SetDiscardedReason(v12, v21, 23);
        goto LABEL_38;
      }
      if ( !*((_DWORD *)v12 + 277) )
      {
        LastError = 1359;
        AslLogCallPrintf(
          1,
          (unsigned int)"Telemetryp_EventDataResolversComplete",
          1725,
          (unsigned int)"Bad checksum [%d]");
        v21 = "Checksum not retrieved";
        goto LABEL_37;
      }
      *((_DWORD *)v12 + 412) = 1;
      if ( !*((_DWORD *)v11 + 141)
        && !*((_DWORD *)v12 + 1001)
        && (v20 != *((_DWORD *)v11 + 1177) || *((_DWORD *)v12 + 280) != *((_DWORD *)v11 + 1178)) )
      {
        Telemetryp_SetDiscardedReason(v12, "Exe changed during run", 23);
        PcaMarkEvent(6, *((unsigned int *)v12 + 1000));
        goto LABEL_74;
      }
    }
    *((_DWORD *)v12 + 416) = *((_QWORD *)a2 + 3) / 0x3E8uLL;
    *((_QWORD *)v12 + 209) = *((_QWORD *)a2 + 1);
    *((_DWORD *)v12 + 420) = *((_QWORD *)a3 + 3) / 0x3E8uLL;
    *((_QWORD *)v12 + 211) = *((_QWORD *)a3 + 1);
    *((_QWORD *)v12 + 207) = *(_QWORD *)a3;
    if ( a5 )
      *((_QWORD *)v12 + 499) |= 0x8000000uLL;
    if ( *((_DWORD *)v11 + 1191) )
      *((_QWORD *)v12 + 499) |= 0x200000000uLL;
    if ( *((_DWORD *)v11 + 1195) )
      *((_QWORD *)v12 + 499) |= 0x4000uLL;
    if ( *((_DWORD *)v11 + 1194) )
      *((_QWORD *)v12 + 499) |= 0x1000uLL;
    if ( *((_DWORD *)v11 + 1196) )
      *((_QWORD *)v12 + 499) |= 0x2000uLL;
    if ( *((_DWORD *)v11 + 1197) )
      *((_QWORD *)v12 + 499) |= 0x2000000000000uLL;
    if ( *((_DWORD *)v11 + 1192) )
      *((_QWORD *)v12 + 499) |= 0x10000uLL;
    if ( (unsigned int)PcaChainHasShimEventOccurred(a1, 0x20u, (const unsigned __int16 *)0x624DD2F1A9FBE77LL) )
      *((_QWORD *)v12 + 499) |= 0x20000uLL;
    if ( (unsigned int)PcaChainHasShimEventOccurred(a1, 0x40u, v22) )
      *((_QWORD *)v12 + 499) |= 0x40000uLL;
    if ( (unsigned int)PcaChainHasSlotData(a1, 8) )
      *((_QWORD *)v12 + 499) |= 0x80000uLL;
    if ( *((_DWORD *)v11 + 1193) )
      Telemetryp_PinnedDllGet((unsigned __int16 *)v12 + 848, v23, (const unsigned __int16 *)v11 + 1568);
    if ( *((_QWORD *)PcapChainFromHandle(a1) + 687) == 1 )
      *((_QWORD *)v12 + 499) |= 0x40000000000uLL;
    v24 = -1;
    do
      ++v24;
    while ( Source[v24] );
    if ( v24 )
      wcscpy_s((wchar_t *)v12 + 2594, 0x100u, Source);
    *((_DWORD *)v12 + 1294) = 1;
    *((_DWORD *)v12 + 554) = 1;
    goto LABEL_74;
  }
  return 0;
}

```

## disassembly

```asm
0x18001e6ec  push    rbx
0x18001e6ee  push    rbp
0x18001e6ef  push    rsi
0x18001e6f0  push    rdi
0x18001e6f1  push    r12
0x18001e6f3  push    r13
0x18001e6f5  push    r14
0x18001e6f7  push    r15
0x18001e6f9  sub     rsp, 38h
0x18001e6fd  mov     rdi, r9
0x18001e700  mov     r14, r8
0x18001e703  mov     r13, rdx
0x18001e706  mov     r15, rcx
0x18001e709  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x18001e70e  mov     rcx, r15; unsigned __int64
0x18001e711  mov     ebx, [rax+10h]
0x18001e714  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x18001e719  mov     ecx, ebx; unsigned int
0x18001e71b  mov     rsi, rax
0x18001e71e  call    ?Telemetryp_EventDataAcquire@@YAPEAU_PCA_TELEMETRY_EVENT_DATA@@I@Z; Telemetryp_EventDataAcquire(uint)
0x18001e723  xor     r12d, r12d
0x18001e726  mov     rbx, rax
0x18001e729  test    rax, rax
0x18001e72c  jnz     short loc_18001E736
0x18001e72e  mov     edi, r12d
0x18001e731  jmp     loc_18001EB9D
0x18001e736  mov     rcx, rdi; hToken
0x18001e739  call    cs:__imp_ImpersonateLoggedOnUser
0x18001e73f  test    eax, eax
0x18001e741  jnz     short loc_18001E77D
0x18001e743  call    cs:__imp_GetLastError
0x18001e749  lea     r9, aFailedToImpers_0; "Failed to impersonate user [%d]"
0x18001e750  mov     r8d, 649h
0x18001e756  lea     rdx, aTelemetrypEven_2; "Telemetryp_EventDataResolversComplete"
0x18001e75d  mov     [rsp+78h+var_58], eax
0x18001e761  mov     ecx, 1
0x18001e766  mov     edi, eax
0x18001e768  call    AslLogCallPrintf
0x18001e76d  mov     ebp, r12d
0x18001e770  test    edi, edi
0x18001e772  jnz     loc_18001E959
0x18001e778  jmp     loc_18001EB94
0x18001e77d  mov     ebp, 1
0x18001e782  cmp     [rsi+12A4h], r12d
0x18001e789  jnz     short loc_18001E7CE
0x18001e78b  cmp     [r14+20h], ebp
0x18001e78f  jnz     short loc_18001E79F
0x18001e791  lea     rax, aFirstrunnolaye; "FirstRunNoLayer"
0x18001e798  mov     [rbx+1428h], rax
0x18001e79f  cmp     dword ptr [r14+24h], 0Ah
0x18001e7a4  jnz     short loc_18001E7C5
0x18001e7a6  lea     rax, aStickynolayer; "StickyNoLayer"
0x18001e7ad  mov     [rbx+1428h], rax
0x18001e7b4  mov     rax, 200000000000h
0x18001e7be  or      [rbx+0F98h], rax
0x18001e7c5  cmp     [rsi+12A4h], r12d
0x18001e7cc  jz      short loc_18001E820
0x18001e7ce  cmp     [r13+20h], r12d
0x18001e7d2  jnz     short loc_18001E7EE
0x18001e7d4  mov     r8d, 16h
0x18001e7da  lea     rdx, aNoBaselineData; "No baseline data"
0x18001e7e1  mov     rcx, rbx
0x18001e7e4  call    ?Telemetryp_SetDiscardedReason@@YAXPEAU_PCA_TELEMETRY_EVENT_DATA@@PEBDW4_PCA_MARK_EVENT@@@Z; Telemetryp_SetDiscardedReason(_PCA_TELEMETRY_EVENT_DATA *,char const *,_PCA_MARK_EVENT)
0x18001e7e9  jmp     loc_18001EB8B
0x18001e7ee  cmp     [r14+20h], ebp
0x18001e7f2  jnz     short loc_18001E802
0x18001e7f4  lea     rax, aFirstrunlayer; "FirstRunLayer"
0x18001e7fb  mov     [rbx+1428h], rax
0x18001e802  cmp     dword ptr [r14+24h], 5
0x18001e807  jnz     short loc_18001E820
0x18001e809  bts     qword ptr [rbx+0F98h], 0Bh
0x18001e812  lea     rax, aStickylayer; "StickyLayer"
0x18001e819  mov     [rbx+1428h], rax
0x18001e820  mov     eax, [rbx+0FA4h]
0x18001e826  test    eax, eax
0x18001e828  jz      short loc_18001E84A
0x18001e82a  cmp     [rbx+0FC0h], r12
0x18001e831  jz      short loc_18001E84A
0x18001e833  bts     qword ptr [rbx+0F98h], 1Dh
0x18001e83c  lea     rcx, aInstallersucce; "InstallerSuccess"
0x18001e843  mov     [rbx+1428h], rcx
0x18001e84a  cmp     [rbx+1428h], r12
0x18001e851  jnz     short loc_18001E85F
0x18001e853  xor     r8d, r8d
0x18001e856  lea     rdx, aNoReasonToSend; "No reason to send"
0x18001e85d  jmp     short loc_18001E7E1
0x18001e85f  cmp     [rbx+670h], r12d
0x18001e866  jnz     loc_18001E9D3
0x18001e86c  cmp     eax, ebp
0x18001e86e  jnz     short loc_18001E883
0x18001e870  cmp     [rbx+0FA8h], r12d
0x18001e877  jnz     short loc_18001E883
0x18001e879  mov     rcx, rbx; struct _PCA_TELEMETRY_EVENT_DATA *
0x18001e87c  call    ?Telemetryp_InstallerGetMatchingInfo@@YAKPEAU_PCA_TELEMETRY_EVENT_DATA@@@Z; Telemetryp_InstallerGetMatchingInfo(_PCA_TELEMETRY_EVENT_DATA *)
0x18001e881  jmp     short loc_18001E8B5
0x18001e883  lea     rdi, [rsi+0C40h]
0x18001e88a  mov     rcx, rdi; FileName
0x18001e88d  call    cs:__imp_RtlDoesFileExists_U
0x18001e893  test    al, al
0x18001e895  jnz     short loc_18001E8A9
0x18001e897  mov     r8d, 11h
0x18001e89d  lea     rdx, aFileNoLongerEx; "File no longer exists"
0x18001e8a4  jmp     loc_18001E7E1
0x18001e8a9  lea     rcx, [rbx+40h]; Destination
0x18001e8ad  mov     rdx, rdi; lpszShortPath
0x18001e8b0  call    ?PcaUtilityGetMatchingInfo@@YAKPEAU_PCA_MATCHING_INFO@@PEBG1@Z; PcaUtilityGetMatchingInfo(_PCA_MATCHING_INFO *,ushort const *,ushort const *)
0x18001e8b5  mov     edi, eax
0x18001e8b7  test    eax, eax
0x18001e8b9  jz      short loc_18001E8DC
0x18001e8bb  lea     r9, aFailedToGetMat; "Failed to get matching info for chain h"...
0x18001e8c2  mov     [rsp+78h+var_58], eax
0x18001e8c6  mov     r8d, 6AAh
0x18001e8cc  lea     rdx, aTelemetrypEven_2; "Telemetryp_EventDataResolversComplete"
0x18001e8d3  mov     ecx, ebp
0x18001e8d5  call    AslLogCallPrintf
0x18001e8da  jmp     short loc_18001E959
0x18001e8dc  mov     eax, [rbx+450h]
0x18001e8e2  test    eax, eax
0x18001e8e4  jnz     short loc_18001E915
0x18001e8e6  mov     eax, 54Fh
0x18001e8eb  lea     r9, aBadSizeD; "Bad size [%d]"
0x18001e8f2  mov     r8d, 6B4h
0x18001e8f8  mov     [rsp+78h+var_58], eax
0x18001e8fc  lea     rdx, aTelemetrypEven_2; "Telemetryp_EventDataResolversComplete"
0x18001e903  mov     ecx, ebp
0x18001e905  mov     edi, eax
0x18001e907  call    AslLogCallPrintf
0x18001e90c  lea     rdx, aFileSizeNotRet; "File size not retrieved"
0x18001e913  jmp     short loc_18001E94B
0x18001e915  cmp     [rbx+454h], r12d
0x18001e91c  jnz     short loc_18001E97B
0x18001e91e  mov     eax, 54Fh
0x18001e923  lea     r9, aBadChecksumD; "Bad checksum [%d]"
0x18001e92a  mov     r8d, 6BDh
0x18001e930  mov     [rsp+78h+var_58], eax
0x18001e934  lea     rdx, aTelemetrypEven_2; "Telemetryp_EventDataResolversComplete"
0x18001e93b  mov     ecx, ebp
0x18001e93d  mov     edi, eax
0x18001e93f  call    AslLogCallPrintf
0x18001e944  lea     rdx, aChecksumNotRet; "Checksum not retrieved"
0x18001e94b  mov     r8d, 17h
0x18001e951  mov     rcx, rbx
0x18001e954  call    ?Telemetryp_SetDiscardedReason@@YAXPEAU_PCA_TELEMETRY_EVENT_DATA@@PEBDW4_PCA_MARK_EVENT@@@Z; Telemetryp_SetDiscardedReason(_PCA_TELEMETRY_EVENT_DATA *,char const *,_PCA_MARK_EVENT)
0x18001e959  mov     r8d, 12h
0x18001e95f  lea     rdx, aErrorWhenProce; "Error when processing resolver complete"...
0x18001e966  mov     rcx, rbx
0x18001e969  call    ?Telemetryp_SetDiscardedReason@@YAXPEAU_PCA_TELEMETRY_EVENT_DATA@@PEBDW4_PCA_MARK_EVENT@@@Z; Telemetryp_SetDiscardedReason(_PCA_TELEMETRY_EVENT_DATA *,char const *,_PCA_MARK_EVENT)
0x18001e96e  test    ebp, ebp
0x18001e970  jz      loc_18001EB94
0x18001e976  jmp     loc_18001EB8E
0x18001e97b  mov     [rbx+670h], ebp
0x18001e981  cmp     [rsi+234h], r12d
0x18001e988  jnz     short loc_18001E9D3
0x18001e98a  cmp     [rbx+0FA4h], r12d
0x18001e991  jnz     short loc_18001E9D3
0x18001e993  cmp     eax, [rsi+1264h]
0x18001e999  jnz     short loc_18001E9A9
0x18001e99b  mov     eax, [rsi+1268h]
0x18001e9a1  cmp     [rbx+460h], eax
0x18001e9a7  jz      short loc_18001E9D3
0x18001e9a9  mov     r8d, 17h
0x18001e9af  lea     rdx, aExeChangedDuri; "Exe changed during run"
0x18001e9b6  mov     rcx, rbx
0x18001e9b9  call    ?Telemetryp_SetDiscardedReason@@YAXPEAU_PCA_TELEMETRY_EVENT_DATA@@PEBDW4_PCA_MARK_EVENT@@@Z; Telemetryp_SetDiscardedReason(_PCA_TELEMETRY_EVENT_DATA *,char const *,_PCA_MARK_EVENT)
0x18001e9be  mov     edx, [rbx+0FA0h]
0x18001e9c4  mov     ecx, 6
0x18001e9c9  call    ?PcaMarkEvent@@YAXW4_PCA_MARK_EVENT@@I@Z; PcaMarkEvent(_PCA_MARK_EVENT,uint)
0x18001e9ce  jmp     loc_18001EB8B
0x18001e9d3  mov     rcx, [r13+18h]
0x18001e9d7  mov     r8, 624DD2F1A9FBE77h; unsigned __int16 *
0x18001e9e1  mov     rax, r8
0x18001e9e4  mul     rcx
0x18001e9e7  mov     rax, r8
0x18001e9ea  sub     rcx, rdx
0x18001e9ed  shr     rcx, 1
0x18001e9f0  add     rcx, rdx
0x18001e9f3  shr     rcx, 9
0x18001e9f7  mov     [rbx+680h], ecx
0x18001e9fd  mov     rcx, [r13+8]
0x18001ea01  mov     [rbx+688h], rcx
0x18001ea08  mov     rcx, [r14+18h]
0x18001ea0c  mul     rcx
0x18001ea0f  sub     rcx, rdx
0x18001ea12  shr     rcx, 1
0x18001ea15  add     rcx, rdx
0x18001ea18  shr     rcx, 9
0x18001ea1c  mov     [rbx+690h], ecx
0x18001ea22  mov     rax, [r14+8]
0x18001ea26  mov     [rbx+698h], rax
0x18001ea2d  mov     rax, [r14]
0x18001ea30  mov     [rbx+678h], rax
0x18001ea37  cmp     [rsp+78h+arg_20], r12d
0x18001ea3f  jz      short loc_18001EA4A
0x18001ea41  bts     qword ptr [rbx+0F98h], 1Bh
0x18001ea4a  cmp     [rsi+129Ch], r12d
0x18001ea51  jz      short loc_18001EA64
0x18001ea53  mov     rax, 200000000h
0x18001ea5d  or      [rbx+0F98h], rax
0x18001ea64  cmp     [rsi+12ACh], r12d
0x18001ea6b  jz      short loc_18001EA76
0x18001ea6d  bts     qword ptr [rbx+0F98h], 0Eh
0x18001ea76  cmp     [rsi+12A8h], r12d
0x18001ea7d  jz      short loc_18001EA88
0x18001ea7f  bts     qword ptr [rbx+0F98h], 0Ch
0x18001ea88  cmp     [rsi+12B0h], r12d
0x18001ea8f  jz      short loc_18001EA9A
0x18001ea91  bts     qword ptr [rbx+0F98h], 0Dh
0x18001ea9a  cmp     [rsi+12B4h], r12d
0x18001eaa1  jz      short loc_18001EAB4
0x18001eaa3  mov     rax, 2000000000000h
0x18001eaad  or      [rbx+0F98h], rax
0x18001eab4  cmp     [rsi+12A0h], r12d
0x18001eabb  jz      short loc_18001EAC6
0x18001eabd  bts     qword ptr [rbx+0F98h], 10h
0x18001eac6  mov     edx, 20h ; ' '; unsigned int
0x18001eacb  mov     rcx, r15; unsigned __int64
0x18001eace  call    ?PcaChainHasShimEventOccurred@@YAH_KIPEBG@Z; PcaChainHasShimEventOccurred(unsigned __int64,uint,ushort const *)
0x18001ead3  test    eax, eax
0x18001ead5  jz      short loc_18001EAE0
0x18001ead7  bts     qword ptr [rbx+0F98h], 11h
0x18001eae0  mov     edx, 40h ; '@'; unsigned int
0x18001eae5  mov     rcx, r15; unsigned __int64
0x18001eae8  call    ?PcaChainHasShimEventOccurred@@YAH_KIPEBG@Z; PcaChainHasShimEventOccurred(unsigned __int64,uint,ushort const *)
0x18001eaed  test    eax, eax
0x18001eaef  jz      short loc_18001EAFA
0x18001eaf1  bts     qword ptr [rbx+0F98h], 12h
0x18001eafa  mov     edx, 8
0x18001eaff  mov     rcx, r15
0x18001eb02  call    ?PcaChainHasSlotData@@YAH_KW4_PCA_SLOT_ID@@@Z; PcaChainHasSlotData(unsigned __int64,_PCA_SLOT_ID)
0x18001eb07  test    eax, eax
0x18001eb09  jz      short loc_18001EB14
0x18001eb0b  bts     qword ptr [rbx+0F98h], 13h
0x18001eb14  cmp     [rsi+12A4h], r12d
0x18001eb1b  jz      short loc_18001EB30
0x18001eb1d  lea     r8, [rsi+0C40h]; unsigned __int16 *
0x18001eb24  lea     rcx, [rbx+6A0h]; unsigned __int16 *
0x18001eb2b  call    ?Telemetryp_PinnedDllGet@@YAKPEAGKPEBG@Z; Telemetryp_PinnedDllGet(ushort *,ulong,ushort const *)
0x18001eb30  mov     rcx, r15; unsigned __int64
0x18001eb33  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x18001eb38  cmp     [rax+1578h], rbp
0x18001eb3f  jnz     short loc_18001EB52
0x18001eb41  mov     rax, 40000000000h
0x18001eb4b  or      [rbx+0F98h], rax
0x18001eb52  mov     r8, [rsp+78h+Source]; Source
0x18001eb5a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001eb5e  inc     rax
0x18001eb61  cmp     [r8+rax*2], r12w
0x18001eb66  jnz     short loc_18001EB5E
0x18001eb68  test    rax, rax
0x18001eb6b  jz      short loc_18001EB7F
0x18001eb6d  lea     rcx, [rbx+1444h]; Destination
0x18001eb74  mov     edx, 100h; SizeInWords
0x18001eb79  call    cs:__imp_wcscpy_s
0x18001eb7f  mov     [rbx+1438h], ebp
0x18001eb85  mov     [rbx+8A8h], ebp
0x18001eb8b  mov     edi, r12d
0x18001eb8e  call    cs:__imp_RevertToSelf
0x18001eb94  mov     rcx, rbx; CriticalSection
0x18001eb97  call    cs:__imp_RtlLeaveCriticalSection
0x18001eb9d  mov     eax, edi
0x18001eb9f  add     rsp, 38h
0x18001eba3  pop     r15
0x18001eba5  pop     r14
0x18001eba7  pop     r13
0x18001eba9  pop     r12
0x18001ebab  pop     rdi
0x18001ebac  pop     rsi
0x18001ebad  pop     rbp
0x18001ebae  pop     rbx
0x18001ebaf  retn
```
