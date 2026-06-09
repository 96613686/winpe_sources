# Siuf_ChainStartAsync(_PCA_EVENT_TYPE,void *)

- ea: `0x1800a7a60`
- end: `0x1800a7e53`
- name: `?Siuf_ChainStartAsync@@YAKW4_PCA_EVENT_TYPE@@PEAX@Z`
- size: `1011`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008e14`
- `0x18000b6f0`
- `0x18000c73c`
- `0x180012920`
- `0x180013fac`
- `0x18001b320`
- `0x18001e688`
- `0x1800212b0`
- `0x180021f0c`
- `0x18007a9cf`
- `0x180092ab8`
- `0x1800a7a60`
- `0x1800a81a8`
- `0x1800a82f0`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800a7ca6`
- `msvcrt!wcscpy_s` at `0x1800a7ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7d5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7d5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7dde`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800a7dd4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800a7dd4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800a7d50`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800a7d50`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1800a7cd8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1800a7cd8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800a7ce5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800a7ce5`

## string_xrefs

- `0x1800a7b63`: `Opt-in by Telecommand`
- `0x1800a7b37`: `Failed to check Telecommand [%d]`
- `0x1800a7df1`: `Failed to delete timer [%d]`
- `0x1800a7d12`: `Failed to cache shortcut scan result [%d]`
- `0x1800a7d62`: `Failed to create Siuf timer [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Siuf_ChainStartAsync(__int64 a1, __int64 a2)
{
  const unsigned __int16 *v3; // rsi
  int v4; // r12d
  struct _PCA_CHAIN *v5; // rax
  DWORD IsCandidate_Telecommand; // ebx
  const char *v7; // r9
  int v8; // r8d
  struct _PCA_CHAIN *v9; // rax
  const wchar_t **v10; // r8
  unsigned int DueTime; // [rsp+20h] [rbp-E0h]
  __int64 Period; // [rsp+28h] [rbp-D8h]
  ULONGLONG pullResult; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[8]; // [rsp+48h] [rbp-B8h] BYREF
  ULONGLONG ullMultiplicand; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  ULONGLONG v18; // [rsp+70h] [rbp-90h]
  unsigned int Parameter[6]; // [rsp+80h] [rbp-80h] BYREF
  void *phNewTimer; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v21[260]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v22; // [rsp+2B0h] [rbp+1B0h] BYREF
  struct _GUID v23; // [rsp+2B4h] [rbp+1B4h] BYREF
  wchar_t Destination[260]; // [rsp+9A8h] [rbp+8A8h] BYREF

  LODWORD(pullResult) = 0;
  memset_0(Parameter, 0, 0xB30u);
  RtlNameValueArray::RtlNameValueArray((RtlNameValueArray *)v15);
  memset_0(Parameter, 0, 0xB30u);
  Parameter[0] = *((_DWORD *)PcapChainFromHandle(*(_QWORD *)(a2 + 8)) + 4);
  v3 = (const unsigned __int16 *)PcapChainFromHandle(*(_QWORD *)(a2 + 8));
  v4 = 0;
  if ( !g_Siuf )
    goto LABEL_27;
  v5 = PcapChainFromHandle(*(_QWORD *)(a2 + 8));
  IsCandidate_Telecommand = Siufp_IsCandidate_Telecommand(
                              (int *)&pullResult,
                              v21,
                              &v22,
                              qword_1801586C8,
                              v3 + 1568,
                              *((_DWORD *)v5 + 4));
  if ( !IsCandidate_Telecommand )
  {
    if ( (_DWORD)pullResult )
    {
      PcaTracePrintf("Siuf", Parameter[0], 0, "Opt-in by Telecommand");
    }
    else
    {
      IsCandidate_Telecommand = Siufp_IsCandidate_Sdb((int *)&pullResult, &v23, qword_1801586C0, v3 + 1568);
      if ( IsCandidate_Telecommand )
      {
        v7 = "Failed to check sdb [%d]";
        v8 = 1238;
        goto LABEL_4;
      }
      if ( !(_DWORD)pullResult )
        goto LABEL_27;
      v9 = PcapChainFromHandle(*(_QWORD *)(a2 + 8));
      PcaTracePrintf("Siuf", *((_DWORD *)v9 + 4), 0, "Opt-in by Sdb");
    }
    if ( (unsigned int)PcaStoreGetValueEx(Destination, 520, v3 + 18, v3 + 2088, 11, Period) )
    {
      if ( _InterlockedCompareExchange(&dword_18015C1F8, 1, 0) )
      {
        PcaTracePrintf("Siuf", Parameter[0], 0, "Skipping,Shortcut scan in progress for another chain");
        goto LABEL_27;
      }
      v4 = 1;
      if ( !PcaUtilityNameValueArrayScanShortcuts(
              (struct RtlNameValueArray *)v15,
              v3 + 18,
              v3 + 1568,
              v3 + 544,
              DueTime)
        && v17 )
      {
        pullResult = 0;
        if ( ULongLongMult(ullMultiplicand, 0, &pullResult) < 0
          || (v10 = (const wchar_t **)(v18 + pullResult), v18 + pullResult < v18) )
        {
          v10 = 0;
        }
        wcscpy_s(Destination, 0x104u, *v10);
        PcaTracePrintf("Siuf", Parameter[0], 0, "Shortcut name,%S", Destination);
        PathStripPathW(Destination);
        PathRemoveExtensionW(Destination);
      }
      IsCandidate_Telecommand = PcaStoreSetValueEx(v3 + 18, v3 + 2088, 11, Destination, 520);
      if ( IsCandidate_Telecommand )
      {
        v7 = "Failed to cache shortcut scan result [%d]";
        v8 = 1296;
        goto LABEL_4;
      }
    }
    if ( !CreateTimerQueueTimer(&phNewTimer, 0, Siufp_ChainTimeout, (PVOID)Parameter[0], 0x1B7740u, 0, 8u) )
    {
      IsCandidate_Telecommand = GetLastError();
      v7 = "Failed to create Siuf timer [%d]";
      v8 = 1313;
      goto LABEL_4;
    }
    IsCandidate_Telecommand = PcaChainSetSlot(*(_QWORD *)(a2 + 8), 11, Parameter, 2864, Siufp_ChainDataCleanup);
    if ( IsCandidate_Telecommand )
    {
      v7 = "Failed to set data block for chain [%d]";
      v8 = 1327;
      goto LABEL_4;
    }
    phNewTimer = 0;
LABEL_27:
    IsCandidate_Telecommand = 0;
    goto LABEL_28;
  }
  v7 = "Failed to check Telecommand [%d]";
  v8 = 1222;
LABEL_4:
  AslLogCallPrintf(1, (unsigned int)"Siuf_ChainStartAsync", v8, (_DWORD)v7);
LABEL_28:
  if ( phNewTimer )
  {
    if ( !DeleteTimerQueueTimer(0, phNewTimer, 0) )
    {
      IsCandidate_Telecommand = GetLastError();
      if ( IsCandidate_Telecommand != 997 )
        AslLogCallPrintf(1, (unsigned int)"Siuf_ChainStartAsync", 1345, (unsigned int)"Failed to delete timer [%d]");
    }
  }
  if ( v4 )
    dword_18015C1F8 = 0;
  RtlStringArray::~RtlStringArray((RtlStringArray *)v15);
  return IsCandidate_Telecommand;
}

```

## disassembly

```asm
0x1800a7a60  mov     [rsp-8+arg_0], rbx
0x1800a7a65  mov     [rsp-8+arg_10], rsi
0x1800a7a6a  push    rbp
0x1800a7a6b  push    rdi
0x1800a7a6c  push    r12
0x1800a7a6e  push    r14
0x1800a7a70  push    r15
0x1800a7a72  lea     rbp, [rsp-0AC0h]
0x1800a7a7a  sub     rsp, 0BC0h
0x1800a7a81  mov     rax, cs:__security_cookie
0x1800a7a88  xor     rax, rsp
0x1800a7a8b  mov     [rbp+0AE0h+var_30], rax
0x1800a7a92  mov     r14, rdx
0x1800a7a95  mov     dword ptr [rsp+0BE0h+pullResult], 0
0x1800a7a9d  mov     ebx, 0B30h
0x1800a7aa2  mov     r8d, ebx; Size
0x1800a7aa5  xor     edx, edx; Val
0x1800a7aa7  lea     rcx, [rbp+0AE0h+Parameter]; void *
0x1800a7aab  call    memset_0
0x1800a7ab0  lea     rcx, [rsp+0BE0h+var_B98]; this
0x1800a7ab5  call    ??0RtlNameValueArray@@QEAA@XZ; RtlNameValueArray::RtlNameValueArray(void)
0x1800a7aba  nop
0x1800a7abb  mov     r8d, ebx; Size
0x1800a7abe  xor     edx, edx; Val
0x1800a7ac0  lea     rcx, [rbp+0AE0h+Parameter]; void *
0x1800a7ac4  call    memset_0
0x1800a7ac9  mov     rcx, [r14+8]; unsigned __int64
0x1800a7acd  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800a7ad2  mov     ecx, [rax+10h]
0x1800a7ad5  mov     [rbp+0AE0h+Parameter], ecx
0x1800a7ad8  mov     rcx, [r14+8]; unsigned __int64
0x1800a7adc  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800a7ae1  mov     rsi, rax
0x1800a7ae4  xor     r12d, r12d
0x1800a7ae7  lea     r15d, [r12+1]
0x1800a7aec  cmp     cs:?g_Siuf@@3U_SIUF_GLOBALS@@A, r12d; _SIUF_GLOBALS g_Siuf
0x1800a7af3  jz      loc_1800A7DC4
0x1800a7af9  mov     rcx, [r14+8]; unsigned __int64
0x1800a7afd  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800a7b02  mov     ecx, [rax+10h]
0x1800a7b05  lea     rdi, [rsi+0C40h]
0x1800a7b0c  mov     dword ptr [rsp+0BE0h+Period], ecx; unsigned int
0x1800a7b10  mov     qword ptr [rsp+0BE0h+DueTime], rdi; unsigned __int16 *
0x1800a7b15  mov     r9, cs:qword_1801586C8; struct ITelecommandCache *
0x1800a7b1c  lea     r8, [rbp+0AE0h+var_930]; unsigned int *
0x1800a7b23  lea     rdx, [rbp+0AE0h+var_B38]; unsigned __int16 *
0x1800a7b27  lea     rcx, [rsp+0BE0h+pullResult]; int *
0x1800a7b2c  call    ?Siufp_IsCandidate_Telecommand@@YAKPEAHPEAGPEAIPEAVITelecommandCache@@PEBGI@Z; Siufp_IsCandidate_Telecommand(int *,ushort *,uint *,ITelecommandCache *,ushort const *,uint)
0x1800a7b31  mov     ebx, eax
0x1800a7b33  test    eax, eax
0x1800a7b35  jz      short loc_1800A7B5C
0x1800a7b37  lea     r9, aFailedToCheckT_0; "Failed to check Telecommand [%d]"
0x1800a7b3e  mov     r8d, 4C6h
0x1800a7b44  mov     [rsp+0BE0h+DueTime], eax
0x1800a7b48  lea     rdx, aSiufChainstart; "Siuf_ChainStartAsync"
0x1800a7b4f  mov     ecx, r15d
0x1800a7b52  call    AslLogCallPrintf
0x1800a7b57  jmp     loc_1800A7DC6
0x1800a7b5c  cmp     dword ptr [rsp+0BE0h+pullResult], r12d
0x1800a7b61  jz      short loc_1800A7B6F
0x1800a7b63  lea     r9, aOptInByTelecom; "Opt-in by Telecommand"
0x1800a7b6a  mov     edx, [rbp+0AE0h+Parameter]
0x1800a7b6d  jmp     short loc_1800A7BBD
0x1800a7b6f  mov     r9, rdi; unsigned __int16 *
0x1800a7b72  mov     r8, cs:qword_1801586C0; void *
0x1800a7b79  lea     rdx, [rbp+0AE0h+var_92C]; struct _GUID *
0x1800a7b80  lea     rcx, [rsp+0BE0h+pullResult]; int *
0x1800a7b85  call    ?Siufp_IsCandidate_Sdb@@YAKPEAHPEAU_GUID@@PEAXPEBG@Z; Siufp_IsCandidate_Sdb(int *,_GUID *,void *,ushort const *)
0x1800a7b8a  mov     ebx, eax
0x1800a7b8c  test    eax, eax
0x1800a7b8e  jz      short loc_1800A7B9F
0x1800a7b90  lea     r9, aFailedToCheckS; "Failed to check sdb [%d]"
0x1800a7b97  mov     r8d, 4D6h
0x1800a7b9d  jmp     short loc_1800A7B44
0x1800a7b9f  cmp     dword ptr [rsp+0BE0h+pullResult], r12d
0x1800a7ba4  jz      loc_1800A7DC4
0x1800a7baa  mov     rcx, [r14+8]; unsigned __int64
0x1800a7bae  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800a7bb3  lea     r9, aOptInBySdb; "Opt-in by Sdb"
0x1800a7bba  mov     edx, [rax+10h]; unsigned int
0x1800a7bbd  xor     r8d, r8d; unsigned int
0x1800a7bc0  lea     rcx, aSiuf; "Siuf"
0x1800a7bc7  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a7bcc  lea     r15, [rsi+1050h]
0x1800a7bd3  lea     rbx, [rsi+24h]
0x1800a7bd7  mov     [rsp+0BE0h+DueTime], 0Bh; unsigned int
0x1800a7bdf  mov     r9, r15
0x1800a7be2  mov     r8, rbx
0x1800a7be5  mov     edx, 208h
0x1800a7bea  lea     rcx, [rbp+0AE0h+Destination]
0x1800a7bf1  call    ?PcaStoreGetValueEx@@YAKPEAX_KPEBG2W4_PCA_SLOT_ID@@@Z; PcaStoreGetValueEx(void *,unsigned __int64,ushort const *,ushort const *,_PCA_SLOT_ID)
0x1800a7bf6  test    eax, eax
0x1800a7bf8  jz      loc_1800A7D27
0x1800a7bfe  xor     eax, eax
0x1800a7c00  lea     ecx, [rax+1]
0x1800a7c03  lock cmpxchg cs:dword_18015C1F8, ecx
0x1800a7c0b  jz      short loc_1800A7C31
0x1800a7c0d  lea     r9, aSkippingShortc; "Skipping,Shortcut scan in progress for "...
0x1800a7c14  xor     r8d, r8d; unsigned int
0x1800a7c17  mov     edx, [rbp+0AE0h+Parameter]; unsigned int
0x1800a7c1a  lea     rcx, aSiuf; "Siuf"
0x1800a7c21  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a7c26  mov     r15d, 1
0x1800a7c2c  jmp     loc_1800A7DC4
0x1800a7c31  mov     r12d, ecx
0x1800a7c34  lea     r9, [rsi+440h]; unsigned __int16 *
0x1800a7c3b  mov     r8, rdi; unsigned __int16 *
0x1800a7c3e  mov     rdx, rbx; unsigned __int16 *
0x1800a7c41  lea     rcx, [rsp+0BE0h+var_B98]; struct RtlNameValueArray *
0x1800a7c46  call    ?PcaUtilityNameValueArrayScanShortcuts@@YAKAEAVRtlNameValueArray@@PEBG11I@Z; PcaUtilityNameValueArrayScanShortcuts(RtlNameValueArray &,ushort const *,ushort const *,ushort const *,uint)
0x1800a7c4b  test    eax, eax
0x1800a7c4d  jnz     loc_1800A7CEB
0x1800a7c53  mov     rax, [rsp+0BE0h+var_B88]
0x1800a7c58  test    rax, rax
0x1800a7c5b  jz      loc_1800A7CEB
0x1800a7c61  xor     r8d, r8d
0x1800a7c64  test    rax, rax
0x1800a7c67  jz      short loc_1800A7C97
0x1800a7c69  mov     [rsp+0BE0h+pullResult], r8
0x1800a7c6e  lea     r8, [rsp+0BE0h+pullResult]; pullResult
0x1800a7c73  xor     edx, edx; ullMultiplier
0x1800a7c75  mov     rcx, [rsp+0BE0h+ullMultiplicand]; ullMultiplicand
0x1800a7c7a  call    ULongLongMult
0x1800a7c7f  test    eax, eax
0x1800a7c81  js      short loc_1800A7C94
0x1800a7c83  mov     r8, [rsp+0BE0h+pullResult]
0x1800a7c88  add     r8, [rsp+0BE0h+var_B70]
0x1800a7c8d  cmp     r8, [rsp+0BE0h+var_B70]
0x1800a7c92  jnb     short loc_1800A7C97
0x1800a7c94  xor     r8d, r8d
0x1800a7c97  mov     r8, [r8]; Source
0x1800a7c9a  mov     edx, 104h; SizeInWords
0x1800a7c9f  lea     rcx, [rbp+0AE0h+Destination]; Destination
0x1800a7ca6  call    cs:__imp_wcscpy_s
0x1800a7cac  lea     rax, [rbp+0AE0h+Destination]
0x1800a7cb3  mov     qword ptr [rsp+0BE0h+DueTime], rax
0x1800a7cb8  lea     r9, aShortcutNameS; "Shortcut name,%S"
0x1800a7cbf  xor     r8d, r8d; unsigned int
0x1800a7cc2  mov     edx, [rbp+0AE0h+Parameter]; unsigned int
0x1800a7cc5  lea     rcx, aSiuf; "Siuf"
0x1800a7ccc  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a7cd1  lea     rcx, [rbp+0AE0h+Destination]; pszPath
0x1800a7cd8  call    cs:__imp_PathStripPathW
0x1800a7cde  lea     rcx, [rbp+0AE0h+Destination]; pszPath
0x1800a7ce5  call    cs:__imp_PathRemoveExtensionW
0x1800a7ceb  mov     qword ptr [rsp+0BE0h+DueTime], 208h
0x1800a7cf4  lea     r9, [rbp+0AE0h+Destination]
0x1800a7cfb  mov     r8d, 0Bh
0x1800a7d01  mov     rdx, r15
0x1800a7d04  mov     rcx, rbx
0x1800a7d07  call    ?PcaStoreSetValueEx@@YAKPEBG0W4_PCA_SLOT_ID@@PEAX_K@Z; PcaStoreSetValueEx(ushort const *,ushort const *,_PCA_SLOT_ID,void *,unsigned __int64)
0x1800a7d0c  mov     ebx, eax
0x1800a7d0e  test    eax, eax
0x1800a7d10  jz      short loc_1800A7D27
0x1800a7d12  lea     r9, aFailedToCacheS; "Failed to cache shortcut scan result [%"...
0x1800a7d19  mov     r8d, 510h
0x1800a7d1f  mov     r15d, r12d
0x1800a7d22  jmp     loc_1800A7B44
0x1800a7d27  mov     r9d, [rbp+0AE0h+Parameter]; Parameter
0x1800a7d2b  mov     [rsp+0BE0h+Flags], 8; Flags
0x1800a7d33  mov     dword ptr [rsp+0BE0h+Period], 0; Period
0x1800a7d3b  mov     [rsp+0BE0h+DueTime], 1B7740h; DueTime
0x1800a7d43  lea     r8, ?Siufp_ChainTimeout@@YAXPEAXE@Z; Callback
0x1800a7d4a  xor     edx, edx; TimerQueue
0x1800a7d4c  lea     rcx, [rbp+0AE0h+phNewTimer]; phNewTimer
0x1800a7d50  call    cs:__imp_CreateTimerQueueTimer
0x1800a7d56  test    eax, eax
0x1800a7d58  jnz     short loc_1800A7D7A
0x1800a7d5a  call    cs:__imp_GetLastError
0x1800a7d60  mov     ebx, eax
0x1800a7d62  lea     r9, aFailedToCreate_26; "Failed to create Siuf timer [%d]"
0x1800a7d69  mov     r8d, 521h
0x1800a7d6f  mov     r15d, 1
0x1800a7d75  jmp     loc_1800A7B44
0x1800a7d7a  lea     rax, ?Siufp_ChainDataCleanup@@YAXPEAX@Z; Siufp_ChainDataCleanup(void *)
0x1800a7d81  mov     qword ptr [rsp+0BE0h+DueTime], rax
0x1800a7d86  mov     r9d, 0B30h
0x1800a7d8c  lea     r8, [rbp+0AE0h+Parameter]
0x1800a7d90  mov     edx, 0Bh
0x1800a7d95  mov     rcx, [r14+8]
0x1800a7d99  call    ?PcaChainSetSlot@@YAK_KW4_PCA_SLOT_ID@@PEAX0P6AX2@Z@Z; PcaChainSetSlot(unsigned __int64,_PCA_SLOT_ID,void *,unsigned __int64,void (*)(void *))
0x1800a7d9e  mov     ebx, eax
0x1800a7da0  mov     r15d, 1
0x1800a7da6  test    eax, eax
0x1800a7da8  jz      short loc_1800A7DBC
0x1800a7daa  lea     r9, aFailedToSetDat_8; "Failed to set data block for chain [%d]"
0x1800a7db1  mov     r8d, 52Fh
0x1800a7db7  jmp     loc_1800A7B44
0x1800a7dbc  mov     [rbp+0AE0h+phNewTimer], 0
0x1800a7dc4  xor     ebx, ebx
0x1800a7dc6  mov     rdx, [rbp+0AE0h+phNewTimer]; Timer
0x1800a7dca  test    rdx, rdx
0x1800a7dcd  jz      short loc_1800A7E0D
0x1800a7dcf  xor     r8d, r8d; CompletionEvent
0x1800a7dd2  xor     ecx, ecx; TimerQueue
0x1800a7dd4  call    cs:__imp_DeleteTimerQueueTimer
0x1800a7dda  test    eax, eax
0x1800a7ddc  jnz     short loc_1800A7E0D
0x1800a7dde  call    cs:__imp_GetLastError
0x1800a7de4  mov     ebx, eax
0x1800a7de6  cmp     eax, 3E5h
0x1800a7deb  jz      short loc_1800A7E0D
0x1800a7ded  mov     [rsp+0BE0h+DueTime], eax
0x1800a7df1  lea     r9, aFailedToDelete_6; "Failed to delete timer [%d]"
0x1800a7df8  mov     r8d, 541h
0x1800a7dfe  lea     rdx, aSiufChainstart; "Siuf_ChainStartAsync"
0x1800a7e05  mov     ecx, r15d
0x1800a7e08  call    AslLogCallPrintf
0x1800a7e0d  test    r12d, r12d
0x1800a7e10  jz      short loc_1800A7E1C
0x1800a7e12  mov     cs:dword_18015C1F8, 0
0x1800a7e1c  lea     rcx, [rsp+0BE0h+var_B98]; this
0x1800a7e21  call    ??1RtlStringArray@@QEAA@XZ; RtlStringArray::~RtlStringArray(void)
0x1800a7e26  mov     eax, ebx
0x1800a7e28  mov     rcx, [rbp+0AE0h+var_30]
0x1800a7e2f  xor     rcx, rsp; StackCookie
0x1800a7e32  call    __security_check_cookie
0x1800a7e37  lea     r11, [rsp+0BE0h+var_20]
0x1800a7e3f  mov     rbx, [r11+30h]
0x1800a7e43  mov     rsi, [r11+40h]
0x1800a7e47  mov     rsp, r11
0x1800a7e4a  pop     r15
0x1800a7e4c  pop     r14
0x1800a7e4e  pop     r12
0x1800a7e50  pop     rdi
0x1800a7e51  pop     rbp
0x1800a7e52  retn
```
