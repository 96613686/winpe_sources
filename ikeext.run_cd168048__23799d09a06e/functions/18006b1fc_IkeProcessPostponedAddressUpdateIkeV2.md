# IkeProcessPostponedAddressUpdateIkeV2

- ea: `0x18006b1fc`
- end: `0x18006b673`
- name: `IkeProcessPostponedAddressUpdateIkeV2`
- size: `1143`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update`

## callers

- `0x18000c880`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x18000b940`
- `0x180018b90`
- `0x180025d88`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x180066d30`
- `0x180068174`
- `0x180069738`
- `0x18006a328`
- `0x18006a4c0`
- `0x18006b1fc`
- `0x18006df9c`
- `0x180070bb0`
- `0x1800ddbe8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b37f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b4de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b649`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b37f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b4de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b649`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b397`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b397`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18006b3a0`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18006b3a0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006b38a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006b38a`

## string_xrefs

- `0x18006b2fd`: `Performing postponed address update`
- `0x18006b245`: `IkeProcessPostponedAddressUpdateIkeV2`
- `0x18006b361`: `IkeProcessPostponedAddressUpdateIkeV2`
- `0x18006b520`: `IkeProcessPostponedAddressUpdateIkeV2`
- `0x18006b52c`: `IkeProcessPostponedAddressUpdateIkeV2`

## pseudocode

```c
__int64 __fastcall IkeProcessPostponedAddressUpdateIkeV2(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  int v3; // r13d
  int v5; // r12d
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // edi
  __int64 v11; // rsi
  __int64 TlsPeerAddr; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int TlsMmLuid; // eax
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 inserted; // rbx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v30; // rdi
  __int64 v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rax
  int v39; // r8d
  unsigned int v40; // ebx
  __int64 v41; // [rsp+40h] [rbp-89h] BYREF
  __int64 v42; // [rsp+48h] [rbp-81h]
  int v43; // [rsp+50h] [rbp-79h] BYREF
  int v44; // [rsp+54h] [rbp-75h] BYREF
  __int64 v45; // [rsp+58h] [rbp-71h] BYREF
  _QWORD v46[2]; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v47[32]; // [rsp+70h] [rbp-59h] BYREF
  __int64 *v48; // [rsp+90h] [rbp-39h]
  __int64 v49; // [rsp+98h] [rbp-31h]
  _BYTE v50[16]; // [rsp+A0h] [rbp-29h] BYREF
  const char *v51; // [rsp+B0h] [rbp-19h]
  __int64 v52; // [rsp+B8h] [rbp-11h]
  __int64 *v53; // [rsp+C0h] [rbp-9h]
  __int64 v54; // [rsp+C8h] [rbp-1h]
  int *v55; // [rsp+D0h] [rbp+7h]
  __int64 v56; // [rsp+D8h] [rbp+Fh]

  v2 = *(_QWORD *)(a1 + 16);
  v3 = 0;
  v41 = 0;
  v5 = 0;
  v42 = 0;
  v43 = 0;
  TraceLogHelper("IkeProcessPostponedAddressUpdateIkeV2", 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v10 = *(_DWORD *)(a2 + 16);
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v7);
    TlsMmLuid = IkeGetTlsMmLuid(v14, v13, v15, v16);
    WPP_SF_iSqD(v11, 65, (unsigned int)WPP_27bc70e61d40360834a5a0166f146b13_Traceguids, TlsMmLuid, TlsPeerAddr, v2, v10);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v45 = IkeGetTlsMmLuid(v7, v6, v8, v9);
    v49 = 8;
    v48 = &v45;
    v19 = IkeGetTlsPeerAddr(v18);
    tlgCreate1Sz_wchar_t(v50, v19);
    v52 = 36;
    v53 = v46;
    v44 = *(_DWORD *)(a2 + 16);
    v55 = &v44;
    v51 = "Performing postponed address update";
    v46[0] = v2;
    v54 = 8;
    v56 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_180151DB3,
      v20,
      v21,
      7,
      (__int64)v47);
  }
  if ( !(unsigned int)IkeDoingIkeV2NonRasTunnel(v2) )
  {
    while ( 1 )
    {
      EnterCriticalSection(gIkeExtGlobals);
      if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v2) )
        break;
      LeaveCriticalSection(gIkeExtGlobals);
      Sleep(0xAu);
    }
    IkeRemoveMMSAFromLists((_DWORD *)v2, 0);
    *(_OWORD *)(v2 + 376) = *(_OWORD *)(a2 + 24);
    *(_OWORD *)(v2 + 392) = *(_OWORD *)(a2 + 40);
    *(_OWORD *)(v2 + 408) = *(_OWORD *)(a2 + 56);
    *(_OWORD *)(v2 + 424) = *(_OWORD *)(a2 + 72);
    *(_OWORD *)(v2 + 440) = *(_OWORD *)(a2 + 88);
    *(_OWORD *)(v2 + 456) = *(_OWORD *)(a2 + 104);
    *(_OWORD *)(v2 + 472) = *(_OWORD *)(a2 + 120);
    *(_OWORD *)(v2 + 488) = *(_OWORD *)(a2 + 136);
    *(_OWORD *)(v2 + 504) = *(_OWORD *)(a2 + 152);
    *(_OWORD *)(v2 + 520) = *(_OWORD *)(a2 + 168);
    *(_QWORD *)(v2 + 536) = *(_QWORD *)(a2 + 184);
    inserted = WfpMemAlloc(0x20u, 8u);
    if ( inserted )
      goto LABEL_18;
    inserted = WfpMemAlloc(0x20u, 8u);
    if ( inserted )
      goto LABEL_18;
    inserted = IkeInsertMMSAToHash(v2, v41);
    if ( inserted )
      goto LABEL_18;
    v3 = 1;
    inserted = IkeInsertMMSAToAddrHash(v2, v42);
    if ( inserted )
      goto LABEL_18;
    v5 = 1;
    v43 = 1;
    if ( *(_DWORD *)(a2 + 16) == 1 )
    {
      inserted = IkeGetIfIndexAndIfLUID(v2 + 376, v2 + 496, v2 + 280);
      if ( inserted || (inserted = IkeSendMobikeNotify(v2)) != 0 )
      {
LABEL_18:
        LeaveCriticalSection(gIkeExtGlobals);
        goto LABEL_19;
      }
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)(v2 + 1104) + 280LL) = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v30 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v31 = IkeGetTlsPeerAddr(v26);
        v36 = IkeGetTlsMmLuid(v33, v32, v34, v35);
        WPP_SF_iSq(v30, 66, (unsigned int)WPP_27bc70e61d40360834a5a0166f146b13_Traceguids, v36, v31, v2);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v46[0] = IkeGetTlsMmLuid(v26, v25, v27, v28);
        v48 = v46;
        v49 = 8;
        v38 = IkeGetTlsPeerAddr(v37);
        tlgCreate1Sz_wchar_t(v50, v38);
        v52 = 28;
        v53 = &v45;
        v51 = "Unblocking mobike pended SA";
        v45 = v2;
        v54 = 8;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)qword_180151E00,
          v39,
          (unsigned int)"Unblocking mobike pended SA",
          6,
          (__int64)v47);
      }
    }
    v40 = 0;
    LeaveCriticalSection(gIkeExtGlobals);
    if ( *(_DWORD *)(a2 + 16) == 2 )
    {
      IkeMigrateNatStateIkeV2(v2);
      v40 = 1;
    }
    v23 = IkeMigrateQmsMobikeIkeV2(v2, v40);
    goto LABEL_35;
  }
  v23 = WfpReportSysErrorAsWinError(v22, "IkeProcessPostponedAddressUpdateIkeV2", 13804, 1);
LABEL_35:
  inserted = v23;
LABEL_19:
  if ( inserted )
  {
    if ( !v3 )
      WfpMemFree(&v41);
    if ( !v5 )
      WfpMemFree(&v43);
    *(_QWORD *)(a2 + 208) = inserted;
    IkeCleanupMMNegotiation(v2, inserted, 3);
  }
  TraceLogHelper("IkeProcessPostponedAddressUpdateIkeV2", 0);
  return IkeReturnError(inserted, "IkeProcessPostponedAddressUpdateIkeV2");
}

```

## disassembly

```asm
0x18006b1fc  mov     [rsp-8+arg_10], rbx
0x18006b201  push    rbp
0x18006b202  push    rsi
0x18006b203  push    rdi
0x18006b204  push    r12
0x18006b206  push    r13
0x18006b208  push    r14
0x18006b20a  push    r15
0x18006b20c  lea     rbp, [rsp-27h]
0x18006b211  sub     rsp, 0F0h
0x18006b218  mov     rax, cs:__security_cookie
0x18006b21f  xor     rax, rsp
0x18006b222  mov     [rbp+57h+var_40], rax
0x18006b226  mov     r14, [rcx+10h]
0x18006b22a  xor     r13d, r13d
0x18006b22d  mov     r15, rdx
0x18006b230  mov     [rsp+120h+var_E0], 0
0x18006b239  xor     r12d, r12d
0x18006b23c  mov     [rsp+120h+var_D8], 0
0x18006b245  lea     rcx, aIkeprocesspost_0; "IkeProcessPostponedAddressUpdateIkeV2"
0x18006b24c  mov     [rbp+57h+var_D0], r12d
0x18006b250  lea     edx, [r13+1]
0x18006b254  call    TraceLogHelper
0x18006b259  mov     rsi, cs:WPP_GLOBAL_Control
0x18006b260  lea     rax, WPP_GLOBAL_Control
0x18006b267  cmp     rsi, rax
0x18006b26a  jz      short loc_18006B2B1
0x18006b26c  cmp     byte ptr [rsi+19h], 4
0x18006b270  jb      short loc_18006B2B1
0x18006b272  test    byte ptr [rsi+1Ch], 10h
0x18006b276  jz      short loc_18006B2B1
0x18006b278  mov     edi, [r15+10h]
0x18006b27c  mov     rsi, [rsi+10h]
0x18006b280  call    IkeGetTlsPeerAddr
0x18006b285  mov     rbx, rax
0x18006b288  call    IkeGetTlsMmLuid
0x18006b28d  mov     [rsp+120h+var_F0], edi
0x18006b291  lea     edx, [r13+41h]
0x18006b295  mov     r9, rax
0x18006b298  mov     [rsp+120h+var_F8], r14
0x18006b29d  lea     r8, WPP_27bc70e61d40360834a5a0166f146b13_Traceguids
0x18006b2a4  mov     [rsp+120h+var_100], rbx
0x18006b2a9  mov     rcx, rsi
0x18006b2ac  call    WPP_SF_iSqD
0x18006b2b1  mov     eax, cs:dword_180173278
0x18006b2b7  mov     ebx, 8
0x18006b2bc  cmp     eax, 4
0x18006b2bf  jbe     loc_18006B34D
0x18006b2c5  call    IkeGetTlsMmLuid
0x18006b2ca  mov     [rbp+57h+var_C8], rax
0x18006b2ce  xor     esi, esi
0x18006b2d0  lea     rax, [rbp+57h+var_C8]
0x18006b2d4  mov     [rbp+57h+var_88], rbx
0x18006b2d8  mov     [rbp+57h+var_90], rax
0x18006b2dc  call    IkeGetTlsPeerAddr
0x18006b2e1  mov     rdx, rax
0x18006b2e4  lea     rcx, [rbp+57h+var_80]
0x18006b2e8  call    _tlgCreate1Sz_wchar_t
0x18006b2ed  lea     rax, [rbp+57h+var_C0]
0x18006b2f1  mov     [rbp+57h+var_68], 24h ; '$'
0x18006b2f9  mov     [rbp+57h+var_60], rax
0x18006b2fd  lea     rcx, aPerformingPost; "Performing postponed address update"
0x18006b304  mov     eax, [r15+10h]
0x18006b308  lea     rdx, byte_180151DB3
0x18006b30f  mov     [rbp+57h+var_CC], eax
0x18006b312  lea     rax, [rbp+57h+var_CC]
0x18006b316  mov     [rbp+57h+var_50], rax
0x18006b31a  lea     rax, [rbp+57h+var_B0]
0x18006b31e  mov     [rbp+57h+var_70], rcx
0x18006b322  lea     rcx, dword_180173278
0x18006b329  mov     [rsp+120h+var_F8], rax
0x18006b32e  mov     dword ptr [rsp+120h+var_100], 7
0x18006b336  mov     [rbp+57h+var_C0], r14
0x18006b33a  mov     [rbp+57h+var_58], rbx
0x18006b33e  mov     [rbp+57h+var_48], 4
0x18006b346  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18006b34b  jmp     short loc_18006B34F
0x18006b34d  xor     esi, esi
0x18006b34f  mov     rcx, r14
0x18006b352  call    IkeDoingIkeV2NonRasTunnel
0x18006b357  test    eax, eax
0x18006b359  jz      short loc_18006B390
0x18006b35b  mov     r9d, 1
0x18006b361  lea     rdx, aIkeprocesspost_0; "IkeProcessPostponedAddressUpdateIkeV2"
0x18006b368  mov     r8d, 35ECh
0x18006b36e  call    WfpReportSysErrorAsWinError
0x18006b373  jmp     loc_18006B66B
0x18006b378  mov     rcx, cs:gIkeExtGlobals; lpCriticalSection
0x18006b37f  call    cs:__imp_LeaveCriticalSection
0x18006b385  mov     ecx, 0Ah; dwMilliseconds
0x18006b38a  call    cs:__imp_Sleep
0x18006b390  mov     rcx, cs:gIkeExtGlobals; lpCriticalSection
0x18006b397  call    cs:__imp_EnterCriticalSection
0x18006b39d  mov     rcx, r14; lpCriticalSection
0x18006b3a0  call    cs:__imp_TryEnterCriticalSection
0x18006b3a6  test    eax, eax
0x18006b3a8  jz      short loc_18006B378
0x18006b3aa  xor     edx, edx
0x18006b3ac  mov     rcx, r14
0x18006b3af  call    IkeRemoveMMSAFromLists
0x18006b3b4  movups  xmm0, xmmword ptr [r15+18h]
0x18006b3b9  lea     rdi, [r14+178h]
0x18006b3c0  mov     edx, ebx; dwFlags
0x18006b3c2  lea     r8, [rsp+120h+var_E0]
0x18006b3c7  mov     ecx, 20h ; ' '; dwBytes
0x18006b3cc  movups  xmmword ptr [rdi], xmm0
0x18006b3cf  movups  xmm1, xmmword ptr [r15+28h]
0x18006b3d4  movups  xmmword ptr [rdi+10h], xmm1
0x18006b3d8  movups  xmm0, xmmword ptr [r15+38h]
0x18006b3dd  movups  xmmword ptr [rdi+20h], xmm0
0x18006b3e1  movups  xmm1, xmmword ptr [r15+48h]
0x18006b3e6  movups  xmmword ptr [rdi+30h], xmm1
0x18006b3ea  movups  xmm0, xmmword ptr [r15+58h]
0x18006b3ef  movups  xmmword ptr [rdi+40h], xmm0
0x18006b3f3  movups  xmm1, xmmword ptr [r15+68h]
0x18006b3f8  movups  xmmword ptr [rdi+50h], xmm1
0x18006b3fc  movups  xmm0, xmmword ptr [r15+78h]
0x18006b401  movups  xmmword ptr [rdi+60h], xmm0
0x18006b405  movups  xmm1, xmmword ptr [r15+88h]
0x18006b40d  movups  xmmword ptr [rdi+70h], xmm1
0x18006b411  movups  xmm0, xmmword ptr [r15+98h]
0x18006b419  movups  xmmword ptr [rdi+80h], xmm0
0x18006b420  movups  xmm1, xmmword ptr [r15+0A8h]
0x18006b428  movups  xmmword ptr [rdi+90h], xmm1
0x18006b42f  mov     rax, [r15+0B8h]
0x18006b436  mov     [rdi+0A0h], rax
0x18006b43d  call    WfpMemAlloc
0x18006b442  mov     rbx, rax
0x18006b445  test    rax, rax
0x18006b448  jnz     loc_18006B4D7
0x18006b44e  lea     r8, [rsp+120h+var_D8]
0x18006b453  lea     edx, [rax+8]; dwFlags
0x18006b456  lea     ecx, [rax+20h]; dwBytes
0x18006b459  call    WfpMemAlloc
0x18006b45e  mov     rbx, rax
0x18006b461  test    rax, rax
0x18006b464  jnz     short loc_18006B4D7
0x18006b466  mov     rdx, [rsp+120h+var_E0]
0x18006b46b  mov     rcx, r14
0x18006b46e  call    IkeInsertMMSAToHash
0x18006b473  mov     rbx, rax
0x18006b476  test    rax, rax
0x18006b479  jnz     short loc_18006B4D7
0x18006b47b  mov     rdx, [rsp+120h+var_D8]
0x18006b480  lea     r13d, [rax+1]
0x18006b484  mov     rcx, r14
0x18006b487  call    IkeInsertMMSAToAddrHash
0x18006b48c  mov     rbx, rax
0x18006b48f  test    rax, rax
0x18006b492  jnz     short loc_18006B4D7
0x18006b494  mov     r12d, r13d
0x18006b497  mov     [rbp+57h+var_D0], r13d
0x18006b49b  cmp     [r15+10h], r13d
0x18006b49f  jnz     loc_18006B562
0x18006b4a5  lea     r8, [r14+118h]
0x18006b4ac  mov     rcx, rdi
0x18006b4af  lea     rdx, [r14+1F0h]
0x18006b4b6  call    IkeGetIfIndexAndIfLUID
0x18006b4bb  mov     rbx, rax
0x18006b4be  test    rax, rax
0x18006b4c1  jnz     short loc_18006B4D7
0x18006b4c3  mov     rcx, r14
0x18006b4c6  call    IkeSendMobikeNotify
0x18006b4cb  mov     rbx, rax
0x18006b4ce  test    rax, rax
0x18006b4d1  jz      loc_18006B640
0x18006b4d7  mov     rcx, cs:gIkeExtGlobals; lpCriticalSection
0x18006b4de  call    cs:__imp_LeaveCriticalSection
0x18006b4e4  test    rbx, rbx
0x18006b4e7  jz      short loc_18006B51E
0x18006b4e9  test    r13d, r13d
0x18006b4ec  jnz     short loc_18006B4F8
0x18006b4ee  lea     rcx, [rsp+120h+var_E0]
0x18006b4f3  call    WfpMemFree
0x18006b4f8  test    r12d, r12d
0x18006b4fb  jnz     short loc_18006B506
0x18006b4fd  lea     rcx, [rbp+57h+var_D0]
0x18006b501  call    WfpMemFree
0x18006b506  mov     r8d, 3
0x18006b50c  mov     [r15+0D0h], rbx
0x18006b513  mov     rdx, rbx
0x18006b516  mov     rcx, r14
0x18006b519  call    IkeCleanupMMNegotiation
0x18006b51e  xor     edx, edx
0x18006b520  lea     rcx, aIkeprocesspost_0; "IkeProcessPostponedAddressUpdateIkeV2"
0x18006b527  call    TraceLogHelper
0x18006b52c  lea     rdx, aIkeprocesspost_0; "IkeProcessPostponedAddressUpdateIkeV2"
0x18006b533  mov     rcx, rbx
0x18006b536  call    IkeReturnError
0x18006b53b  mov     rcx, [rbp+57h+var_40]
0x18006b53f  xor     rcx, rsp; StackCookie
0x18006b542  call    __security_check_cookie
0x18006b547  mov     rbx, [rsp+120h+arg_10]
0x18006b54f  add     rsp, 0F0h
0x18006b556  pop     r15
0x18006b558  pop     r14
0x18006b55a  pop     r13
0x18006b55c  pop     r12
0x18006b55e  pop     rdi
0x18006b55f  pop     rsi
0x18006b560  pop     rbp
0x18006b561  retn
0x18006b562  mov     rax, [r14+450h]
0x18006b569  mov     [rax+118h], esi
0x18006b56f  mov     rdi, cs:WPP_GLOBAL_Control
0x18006b576  lea     rax, WPP_GLOBAL_Control
0x18006b57d  cmp     rdi, rax
0x18006b580  jz      short loc_18006B5C0
0x18006b582  cmp     byte ptr [rdi+19h], 4
0x18006b586  jb      short loc_18006B5C0
0x18006b588  test    byte ptr [rdi+1Ch], 10h
0x18006b58c  jz      short loc_18006B5C0
0x18006b58e  mov     rdi, [rdi+10h]
0x18006b592  call    IkeGetTlsPeerAddr
0x18006b597  mov     rbx, rax
0x18006b59a  call    IkeGetTlsMmLuid
0x18006b59f  mov     r9, rax
0x18006b5a2  mov     [rsp+120h+var_F8], r14
0x18006b5a7  mov     edx, 42h ; 'B'
0x18006b5ac  mov     [rsp+120h+var_100], rbx
0x18006b5b1  lea     r8, WPP_27bc70e61d40360834a5a0166f146b13_Traceguids
0x18006b5b8  mov     rcx, rdi
0x18006b5bb  call    WPP_SF_iSq
0x18006b5c0  mov     eax, cs:dword_180173278
0x18006b5c6  cmp     eax, 4
0x18006b5c9  jbe     short loc_18006B640
0x18006b5cb  call    IkeGetTlsMmLuid
0x18006b5d0  mov     [rbp+57h+var_C0], rax
0x18006b5d4  lea     rax, [rbp+57h+var_C0]
0x18006b5d8  mov     [rbp+57h+var_90], rax
0x18006b5dc  mov     [rbp+57h+var_88], 8
0x18006b5e4  call    IkeGetTlsPeerAddr
0x18006b5e9  mov     rdx, rax
0x18006b5ec  lea     rcx, [rbp+57h+var_80]
0x18006b5f0  call    _tlgCreate1Sz_wchar_t
0x18006b5f5  lea     rax, [rbp+57h+var_C8]
0x18006b5f9  mov     [rbp+57h+var_68], 1Ch
0x18006b601  mov     [rbp+57h+var_60], rax
0x18006b605  lea     r9, aUnblockingMobi; "Unblocking mobike pended SA"
0x18006b60c  lea     rax, [rbp+57h+var_B0]
0x18006b610  mov     [rbp+57h+var_70], r9
0x18006b614  mov     [rsp+120h+var_F8], rax
0x18006b619  lea     rdx, qword_180151E00
0x18006b620  lea     rcx, dword_180173278
0x18006b627  mov     dword ptr [rsp+120h+var_100], 6
0x18006b62f  mov     [rbp+57h+var_C8], r14
0x18006b633  mov     [rbp+57h+var_58], 8
0x18006b63b  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18006b640  mov     rcx, cs:gIkeExtGlobals; lpCriticalSection
0x18006b647  mov     ebx, esi
0x18006b649  call    cs:__imp_LeaveCriticalSection
0x18006b64f  cmp     dword ptr [r15+10h], 2
0x18006b654  jnz     short loc_18006B661
0x18006b656  mov     rcx, r14
0x18006b659  call    IkeMigrateNatStateIkeV2
0x18006b65e  mov     ebx, r13d
0x18006b661  mov     edx, ebx
0x18006b663  mov     rcx, r14
0x18006b666  call    IkeMigrateQmsMobikeIkeV2
0x18006b66b  mov     rbx, rax
0x18006b66e  jmp     loc_18006B4E4
```
