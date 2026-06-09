# HNS::Service::Core::NetworkEntityManager::CleanupOrphanNics(void)

- ea: `0x1800bfe38`
- end: `0x1800c02ca`
- name: `?CleanupOrphanNics@NetworkEntityManager@Core@Service@HNS@@AEAAJXZ`
- size: `1170`
- prototype: `__int64 __fastcall(HNS::Service::Core::NetworkEntityManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x1800ceef0`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x180063094`
- `0x1800759d8`
- `0x180075aac`
- `0x18007dc48`
- `0x18008c66c`
- `0x1800bfe38`

## import_xrefs

- `NetMgmtIF!NetMgmtGetNetworkAdapterType` at `0x1800bff33`
- `NetMgmtIF!NetMgmtGetNetworkAdapterType` at `0x1800bff33`
- `NetMgmtIF!NetMgmtEnumerateNic` at `0x1800bfe8c`
- `NetMgmtIF!NetMgmtEnumerateNic` at `0x1800bfe8c`
- `NetMgmtIF!NetMgmtRemoveOrphanedVirtualNics` at `0x1800c0183`
- `NetMgmtIF!NetMgmtRemoveOrphanedVirtualNics` at `0x1800c0183`
- `NetMgmtIF!NetMgmtMemFree` at `0x1800c02a2`
- `NetMgmtIF!NetMgmtMemFree` at `0x1800c02a2`
- `NetMgmtIF!NetMgmtRemoveOrphanedExtensionMiniports` at `0x1800c020b`
- `NetMgmtIF!NetMgmtRemoveOrphanedExtensionMiniports` at `0x1800c020b`
- `NetMgmtIF!NetMgmtDeleteInternalEthernetAdapterLW` at `0x1800bff4b`
- `NetMgmtIF!NetMgmtDeleteInternalEthernetAdapterLW` at `0x1800bff4b`
- `NetMgmtIF!NetMgmtDeleteInternalEthernetAdapter` at `0x1800bff53`
- `NetMgmtIF!NetMgmtDeleteInternalEthernetAdapter` at `0x1800bff53`

## string_xrefs

- `0x1800bfe9f`: `onecore\vm\dv\net\hns\service\core\networkentitymanager.cpp`
- `0x1800c0055`: `onecore\vm\dv\net\hns\service\core\networkentitymanager.cpp`
- `0x1800bff67`: `Deleted PnP adapter`
- `0x1800bff5e`: `Deleted lightweight adapter`
- `0x1800bfe64`: `HNS::Service::Core::NetworkEntityManager::CleanupOrphanNics`
- `0x1800c028e`: `HNS::Service::Core::NetworkEntityManager::CleanupOrphanNics`

## pseudocode

```c
__int64 __fastcall HNS::Service::Core::NetworkEntityManager::CleanupOrphanNics(
        HNS::Service::Core::NetworkEntityManager *this)
{
  int v1; // eax
  __int64 v2; // rdx
  unsigned int v3; // ebx
  __int64 v5; // r14
  unsigned int v6; // esi
  _WORD *v7; // rbx
  __int64 v8; // rcx
  int v9; // eax
  const wchar_t *v10; // rcx
  int v11; // edi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  int v23; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v24; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+48h] [rbp-B8h] BYREF
  int v27; // [rsp+4Ch] [rbp-B4h] BYREF
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v31; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+78h] [rbp-88h]
  int v33; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v34; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+94h] [rbp-6Ch]
  int v37[6]; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v38; // [rsp+B0h] [rbp-50h] BYREF
  int v39; // [rsp+C0h] [rbp-40h]
  int v40; // [rsp+C4h] [rbp-3Ch]
  _BYTE v41[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  int *v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  _BYTE v46[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v47; // [rsp+130h] [rbp+30h]
  __int64 v48; // [rsp+138h] [rbp+38h]
  _WORD *v49; // [rsp+140h] [rbp+40h]
  int v50; // [rsp+148h] [rbp+48h]
  int v51; // [rsp+14Ch] [rbp+4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  HNSTraceProvider::TraceEnter("HNS::Service::Core::NetworkEntityManager::CleanupOrphanNics", 0x5A3u);
  v24 = 0;
  v21 = 0;
  v29 = 0;
  v1 = NetMgmtEnumerateNic(&v29, &v24);
  v3 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A9,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
      (const char *)(unsigned int)v1,
      v19);
    return v3;
  }
  v5 = v29;
  v6 = 0;
  if ( v24 )
  {
    while ( 1 )
    {
      v7 = (_WORD *)(v5 + 2612LL * v6);
      if ( *((_BYTE *)v7 + 780) || *((_DWORD *)v7 + 193) != 1 )
      {
        if ( *(_DWORD *)qword_1803989E8 > 5u )
        {
          v30 = 2048;
          if ( v7 )
          {
            v16 = -1;
            do
              ++v16;
            while ( v7[v16] );
            v17 = 2 * v16 + 2;
          }
          else
          {
            v7 = &unk_1802E2A80;
            v17 = 2;
          }
          v50 = v17;
          v49 = v7;
          v47 = &v30;
          v51 = 0;
          v48 = 8;
          tlgWriteTransfer_EventWriteTransfer(qword_1803989E8, &unk_180336324, 0, 0, 4, v46);
        }
        goto LABEL_33;
      }
      v28 = 0;
      v27 = 0;
      v26 = 0;
      v23 = 0;
      if ( (int)NetMgmtGetNetworkAdapterType(v5 + 2612LL * v6, &v28, &v27, &v26, &v23) >= 0 )
        break;
LABEL_33:
      if ( ++v6 >= v24 )
        goto LABEL_34;
    }
    v8 = v5 + 2612LL * v6;
    if ( v23 )
      v9 = NetMgmtDeleteInternalEthernetAdapterLW(v8);
    else
      v9 = NetMgmtDeleteInternalEthernetAdapter(v8);
    v10 = L"Deleted lightweight adapter";
    v11 = v9;
    if ( !v23 )
      v10 = L"Deleted PnP adapter";
    v12 = -1;
    v38 = v10;
    do
      ++v12;
    while ( v10[v12] );
    v40 = 5;
    v39 = 2 * v12 + 2;
    if ( v7 )
    {
      v31 = (const wchar_t *)(v5 + 2612LL * v6);
      v13 = -1;
      do
        ++v13;
      while ( v7[v13] );
      v33 = 5;
      v32 = 2 * v13 + 2;
      v14 = (__int64)(v7 + 391);
      if ( !v14 )
      {
        v35 = 20;
        v34 = L"-Missing-";
LABEL_23:
        v36 = 5;
        v37[0] = v11;
        v37[4] = 4;
        v37[5] = 4;
        EventWrite(&ORPHAN_DETECTED, (struct HNSEventType *)&v38, &v31, &v34, v37, 0);
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5CE,
            (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
            (const char *)(unsigned int)v11,
            v20);
        ++v21;
        goto LABEL_33;
      }
    }
    else
    {
      v32 = 20;
      v31 = L"-Missing-";
      v14 = 782;
      v33 = 5;
    }
    v34 = (const wchar_t *)v14;
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v14 + 2 * v15) );
    v35 = 2 * v15 + 2;
    goto LABEL_23;
  }
LABEL_34:
  if ( v21 )
  {
    if ( *(_DWORD *)qword_1803989E8 > 5u )
    {
      v2 = *(_QWORD *)(qword_1803989E8 + 24);
      if ( (*(_QWORD *)(qword_1803989E8 + 16) & 0x400000000000LL) != 0 && (v2 & 0x400000000000LL) == v2 )
      {
        v22 = v21;
        v25 = 2048;
        v44 = &v22;
        v45 = 4;
        v42 = &v25;
        v43 = 8;
        tlgWriteTransfer_EventWriteTransfer(qword_1803989E8, &unk_180336359, 0, 0, 4, v41);
      }
    }
  }
  v21 = 0;
  NetMgmtRemoveOrphanedVirtualNics(&v21, v2);
  if ( v21 )
  {
    if ( *(_DWORD *)qword_1803989E8 > 5u )
    {
      v18 = *(_QWORD *)(qword_1803989E8 + 24);
      if ( (*(_QWORD *)(qword_1803989E8 + 16) & 0x400000000000LL) != 0 && (v18 & 0x400000000000LL) == v18 )
      {
        v22 = v21;
        v25 = 2048;
        v44 = &v22;
        v45 = 4;
        v42 = &v25;
        v43 = 8;
        tlgWriteTransfer_EventWriteTransfer(qword_1803989E8, &unk_1803362A2, 0, 0, 4, v41);
      }
    }
  }
  v21 = 0;
  NetMgmtRemoveOrphanedExtensionMiniports(&v21, v18);
  if ( v21
    && *(_DWORD *)qword_1803989E8 > 5u
    && (*(_QWORD *)(qword_1803989E8 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(qword_1803989E8 + 24) & 0x400000000000LL) == *(_QWORD *)(qword_1803989E8 + 24) )
  {
    v22 = v21;
    v25 = 2048;
    v44 = &v22;
    v45 = 4;
    v42 = &v25;
    v43 = 8;
    tlgWriteTransfer_EventWriteTransfer(qword_1803989E8, &unk_1803362E1, 0, 0, 4, v41);
  }
  HNSTraceProvider::TraceSuccess("HNS::Service::Core::NetworkEntityManager::CleanupOrphanNics", 0x60Au);
  if ( v5 )
    NetMgmtMemFree(v5);
  return 0;
}

```

## disassembly

```asm
0x1800bfe38  push    rbp
0x1800bfe3a  push    rbx
0x1800bfe3b  push    rsi
0x1800bfe3c  push    rdi
0x1800bfe3d  push    r12
0x1800bfe3f  push    r13
0x1800bfe41  push    r14
0x1800bfe43  push    r15
0x1800bfe45  lea     rbp, [rsp-68h]
0x1800bfe4a  sub     rsp, 168h
0x1800bfe51  mov     rax, cs:__security_cookie
0x1800bfe58  xor     rax, rsp
0x1800bfe5b  mov     [rbp+0A0h+var_50], rax
0x1800bfe5f  mov     edx, 5A3h; unsigned int
0x1800bfe64  lea     rcx, aHnsServiceCore_18; "HNS::Service::Core::NetworkEntityManage"...
0x1800bfe6b  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800bfe70  xor     r15d, r15d
0x1800bfe73  lea     rdx, [rsp+1A0h+var_164]
0x1800bfe78  lea     rcx, [rsp+1A0h+var_148]
0x1800bfe7d  mov     [rsp+1A0h+var_164], r15d
0x1800bfe82  mov     [rsp+1A0h+var_170], r15d
0x1800bfe87  mov     [rsp+1A0h+var_148], r15
0x1800bfe8c  call    cs:__imp_NetMgmtEnumerateNic
0x1800bfe92  mov     ebx, eax
0x1800bfe94  test    eax, eax
0x1800bfe96  jns     short loc_1800BFEBA
0x1800bfe98  mov     rcx, [rbp+0A8h]; this
0x1800bfe9f  lea     r8, aOnecoreVmDvNet_188; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800bfea6  mov     r9d, eax; char *
0x1800bfea9  mov     edx, 5A9h; void *
0x1800bfeae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bfeb3  mov     eax, ebx
0x1800bfeb5  jmp     loc_1800C02AA
0x1800bfeba  mov     r12d, 5
0x1800bfec0  mov     r14, [rsp+1A0h+var_148]
0x1800bfec5  mov     esi, r15d
0x1800bfec8  mov     edi, 800h
0x1800bfecd  lea     r13d, [r12-1]
0x1800bfed2  cmp     [rsp+1A0h+var_164], r15d
0x1800bfed7  jbe     loc_1800C00F7
0x1800bfedd  mov     eax, esi
0x1800bfedf  imul    rbx, rax, 0A34h
0x1800bfee6  add     rbx, r14
0x1800bfee9  cmp     [rbx+30Ch], r15b
0x1800bfef0  jnz     loc_1800C0074
0x1800bfef6  cmp     dword ptr [rbx+304h], 1
0x1800bfefd  jnz     loc_1800C0074
0x1800bff03  lea     rax, [rsp+1A0h+var_168]
0x1800bff08  mov     [rsp+1A0h+var_150], r15d
0x1800bff0d  lea     r9, [rsp+1A0h+var_158]
0x1800bff12  mov     qword ptr [rsp+1A0h+var_180], rax
0x1800bff17  lea     r8, [rsp+1A0h+var_154]
0x1800bff1c  mov     [rsp+1A0h+var_154], r15d
0x1800bff21  lea     rdx, [rsp+1A0h+var_150]
0x1800bff26  mov     [rsp+1A0h+var_158], r15d
0x1800bff2b  mov     rcx, rbx
0x1800bff2e  mov     [rsp+1A0h+var_168], r15d
0x1800bff33  call    cs:__imp_NetMgmtGetNetworkAdapterType
0x1800bff39  test    eax, eax
0x1800bff3b  js      loc_1800C00EB
0x1800bff41  mov     rcx, rbx
0x1800bff44  cmp     [rsp+1A0h+var_168], r15d
0x1800bff49  jz      short loc_1800BFF53
0x1800bff4b  call    cs:__imp_NetMgmtDeleteInternalEthernetAdapterLW
0x1800bff51  jmp     short loc_1800BFF59
0x1800bff53  call    cs:__imp_NetMgmtDeleteInternalEthernetAdapter
0x1800bff59  cmp     [rsp+1A0h+var_168], r15d
0x1800bff5e  lea     rcx, aDeletedLightwe; "Deleted lightweight adapter"
0x1800bff65  mov     edi, eax
0x1800bff67  lea     rax, aDeletedPnpAdap; "Deleted PnP adapter"
0x1800bff6e  cmovz   rcx, rax
0x1800bff72  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bff76  mov     rax, rdx
0x1800bff79  mov     [rbp+0A0h+var_F0], rcx
0x1800bff7d  inc     rax
0x1800bff80  cmp     [rcx+rax*2], r15w
0x1800bff85  jnz     short loc_1800BFF7D
0x1800bff87  mov     [rbp+0A0h+var_DC], r12d
0x1800bff8b  lea     eax, ds:2[rax*2]
0x1800bff92  mov     [rbp+0A0h+var_E0], eax
0x1800bff95  test    rbx, rbx
0x1800bff98  jz      short loc_1800BFFD9
0x1800bff9a  mov     [rsp+1A0h+var_138], rbx
0x1800bff9f  mov     rax, rdx
0x1800bffa2  inc     rax
0x1800bffa5  cmp     [rbx+rax*2], r15w
0x1800bffaa  jnz     short loc_1800BFFA2
0x1800bffac  mov     [rsp+1A0h+var_124], r12d
0x1800bffb1  lea     eax, ds:2[rax*2]
0x1800bffb8  mov     [rsp+1A0h+var_128], eax
0x1800bffbc  add     rbx, 30Eh
0x1800bffc3  jnz     short loc_1800BFFF9
0x1800bffc5  lea     rax, aMissing; "-Missing-"
0x1800bffcc  mov     [rbp+0A0h+var_110], 14h
0x1800bffd3  mov     [rbp+0A0h+var_120], rax
0x1800bffd7  jmp     short loc_1800C0014
0x1800bffd9  lea     rax, aMissing; "-Missing-"
0x1800bffe0  mov     [rsp+1A0h+var_128], 14h
0x1800bffe8  mov     [rsp+1A0h+var_138], rax
0x1800bffed  add     rbx, 30Eh
0x1800bfff4  mov     [rsp+1A0h+var_124], r12d
0x1800bfff9  mov     [rbp+0A0h+var_120], rbx
0x1800bfffd  mov     rax, rdx
0x1800c0000  inc     rax
0x1800c0003  cmp     [rbx+rax*2], r15w
0x1800c0008  jnz     short loc_1800C0000
0x1800c000a  lea     eax, ds:2[rax*2]
0x1800c0011  mov     [rbp+0A0h+var_110], eax
0x1800c0014  lea     rax, [rbp+0A0h+var_108]
0x1800c0018  mov     [rsp+1A0h+var_178], r15
0x1800c001d  lea     r9, [rbp+0A0h+var_120]
0x1800c0021  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x1800c0026  lea     r8, [rsp+1A0h+var_138]
0x1800c002b  mov     [rbp+0A0h+var_10C], r12d
0x1800c002f  lea     rdx, [rbp+0A0h+var_F0]; this
0x1800c0033  mov     [rbp+0A0h+var_108], edi
0x1800c0036  lea     rcx, ORPHAN_DETECTED; EventDescriptor
0x1800c003d  mov     [rbp+0A0h+var_F8], r13d
0x1800c0041  mov     [rbp+0A0h+var_F4], r13d
0x1800c0045  call    ?EventWrite@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVHNSEventType@@ZZ; EventWrite(_EVENT_DESCRIPTOR const *,HNSEventType *,...)
0x1800c004a  test    edi, edi
0x1800c004c  jns     short loc_1800C0069
0x1800c004e  mov     rcx, [rbp+0A8h]; this
0x1800c0055  lea     r8, aOnecoreVmDvNet_188; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800c005c  mov     r9d, edi; char *
0x1800c005f  mov     edx, 5CEh; void *
0x1800c0064  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c0069  inc     [rsp+1A0h+var_170]
0x1800c006d  mov     edi, 800h
0x1800c0072  jmp     short loc_1800C00EB
0x1800c0074  mov     rcx, cs:qword_1803989E8
0x1800c007b  mov     eax, [rcx]
0x1800c007d  cmp     eax, r12d
0x1800c0080  jbe     short loc_1800C00EB
0x1800c0082  mov     [rsp+1A0h+var_140], rdi
0x1800c0087  test    rbx, rbx
0x1800c008a  jz      short loc_1800C00A3
0x1800c008c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c0090  inc     rax
0x1800c0093  cmp     [rbx+rax*2], r15w
0x1800c0098  jnz     short loc_1800C0090
0x1800c009a  lea     eax, ds:2[rax*2]
0x1800c00a1  jmp     short loc_1800C00AF
0x1800c00a3  lea     rbx, unk_1802E2A80
0x1800c00aa  mov     eax, 2
0x1800c00af  mov     [rbp+0A0h+var_58], eax
0x1800c00b2  lea     rdx, unk_180336324
0x1800c00b9  lea     rax, [rsp+1A0h+var_140]
0x1800c00be  mov     [rbp+0A0h+var_60], rbx
0x1800c00c2  mov     [rbp+0A0h+var_70], rax
0x1800c00c6  xor     r9d, r9d
0x1800c00c9  lea     rax, [rbp+0A0h+var_90]
0x1800c00cd  mov     [rbp+0A0h+var_54], r15d
0x1800c00d1  mov     [rsp+1A0h+var_178], rax
0x1800c00d6  xor     r8d, r8d
0x1800c00d9  mov     [rsp+1A0h+var_180], r13d
0x1800c00de  mov     [rbp+0A0h+var_68], 8
0x1800c00e6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800c00eb  inc     esi
0x1800c00ed  cmp     esi, [rsp+1A0h+var_164]
0x1800c00f1  jb      loc_1800BFEDD
0x1800c00f7  mov     rbx, 400000000000h
0x1800c0101  cmp     [rsp+1A0h+var_170], r15d
0x1800c0106  jz      short loc_1800C0179
0x1800c0108  mov     rcx, cs:qword_1803989E8
0x1800c010f  mov     eax, [rcx]
0x1800c0111  cmp     eax, r12d
0x1800c0114  jbe     short loc_1800C0179
0x1800c0116  mov     rdx, [rcx+18h]
0x1800c011a  mov     rax, [rcx+10h]
0x1800c011e  test    rbx, rax
0x1800c0121  jz      short loc_1800C0179
0x1800c0123  mov     rax, rdx
0x1800c0126  and     rax, rbx
0x1800c0129  cmp     rax, rdx
0x1800c012c  jnz     short loc_1800C0179
0x1800c012e  mov     eax, [rsp+1A0h+var_170]
0x1800c0132  lea     rdx, unk_180336359
0x1800c0139  mov     [rsp+1A0h+var_16C], eax
0x1800c013d  xor     r9d, r9d
0x1800c0140  lea     rax, [rsp+1A0h+var_16C]
0x1800c0145  mov     [rsp+1A0h+var_160], rdi
0x1800c014a  mov     [rbp+0A0h+var_A0], rax
0x1800c014e  xor     r8d, r8d
0x1800c0151  lea     rax, [rsp+1A0h+var_160]
0x1800c0156  mov     [rbp+0A0h+var_98], r13
0x1800c015a  mov     [rbp+0A0h+var_B0], rax
0x1800c015e  lea     rax, [rbp+0A0h+var_D0]
0x1800c0162  mov     [rsp+1A0h+var_178], rax
0x1800c0167  mov     [rsp+1A0h+var_180], r13d
0x1800c016c  mov     [rbp+0A0h+var_A8], 8
0x1800c0174  call    _tlgWriteTransfer_EventWriteTransfer
0x1800c0179  lea     rcx, [rsp+1A0h+var_170]
0x1800c017e  mov     [rsp+1A0h+var_170], r15d
0x1800c0183  call    cs:__imp_NetMgmtRemoveOrphanedVirtualNics
0x1800c0189  cmp     [rsp+1A0h+var_170], r15d
0x1800c018e  jz      short loc_1800C0201
0x1800c0190  mov     rcx, cs:qword_1803989E8
0x1800c0197  mov     eax, [rcx]
0x1800c0199  cmp     eax, r12d
0x1800c019c  jbe     short loc_1800C0201
0x1800c019e  mov     rdx, [rcx+18h]
0x1800c01a2  mov     rax, [rcx+10h]
0x1800c01a6  test    rbx, rax
0x1800c01a9  jz      short loc_1800C0201
0x1800c01ab  mov     rax, rdx
0x1800c01ae  and     rax, rbx
0x1800c01b1  cmp     rax, rdx
0x1800c01b4  jnz     short loc_1800C0201
0x1800c01b6  mov     eax, [rsp+1A0h+var_170]
0x1800c01ba  lea     rdx, unk_1803362A2
0x1800c01c1  mov     [rsp+1A0h+var_16C], eax
0x1800c01c5  xor     r9d, r9d
0x1800c01c8  lea     rax, [rsp+1A0h+var_16C]
0x1800c01cd  mov     [rsp+1A0h+var_160], rdi
0x1800c01d2  mov     [rbp+0A0h+var_A0], rax
0x1800c01d6  xor     r8d, r8d
0x1800c01d9  lea     rax, [rsp+1A0h+var_160]
0x1800c01de  mov     [rbp+0A0h+var_98], r13
0x1800c01e2  mov     [rbp+0A0h+var_B0], rax
0x1800c01e6  lea     rax, [rbp+0A0h+var_D0]
0x1800c01ea  mov     [rsp+1A0h+var_178], rax
0x1800c01ef  mov     [rsp+1A0h+var_180], r13d
0x1800c01f4  mov     [rbp+0A0h+var_A8], 8
0x1800c01fc  call    _tlgWriteTransfer_EventWriteTransfer
0x1800c0201  lea     rcx, [rsp+1A0h+var_170]
0x1800c0206  mov     [rsp+1A0h+var_170], r15d
0x1800c020b  call    cs:__imp_NetMgmtRemoveOrphanedExtensionMiniports
0x1800c0211  cmp     [rsp+1A0h+var_170], r15d
0x1800c0216  jz      short loc_1800C0289
0x1800c0218  mov     rcx, cs:qword_1803989E8
0x1800c021f  mov     eax, [rcx]
0x1800c0221  cmp     eax, r12d
0x1800c0224  jbe     short loc_1800C0289
0x1800c0226  mov     rdx, [rcx+18h]
0x1800c022a  mov     rax, [rcx+10h]
0x1800c022e  test    rbx, rax
0x1800c0231  jz      short loc_1800C0289
0x1800c0233  mov     rax, rdx
0x1800c0236  and     rax, rbx
0x1800c0239  cmp     rax, rdx
0x1800c023c  jnz     short loc_1800C0289
0x1800c023e  mov     eax, [rsp+1A0h+var_170]
0x1800c0242  lea     rdx, unk_1803362E1
0x1800c0249  mov     [rsp+1A0h+var_16C], eax
0x1800c024d  xor     r9d, r9d
0x1800c0250  lea     rax, [rsp+1A0h+var_16C]
0x1800c0255  mov     [rsp+1A0h+var_160], rdi
0x1800c025a  mov     [rbp+0A0h+var_A0], rax
0x1800c025e  xor     r8d, r8d
0x1800c0261  lea     rax, [rsp+1A0h+var_160]
0x1800c0266  mov     [rbp+0A0h+var_98], r13
0x1800c026a  mov     [rbp+0A0h+var_B0], rax
0x1800c026e  lea     rax, [rbp+0A0h+var_D0]
0x1800c0272  mov     [rsp+1A0h+var_178], rax
0x1800c0277  mov     [rsp+1A0h+var_180], r13d
0x1800c027c  mov     [rbp+0A0h+var_A8], 8
0x1800c0284  call    _tlgWriteTransfer_EventWriteTransfer
0x1800c0289  mov     edx, 60Ah; unsigned int
0x1800c028e  lea     rcx, aHnsServiceCore_18; "HNS::Service::Core::NetworkEntityManage"...
0x1800c0295  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1800c029a  test    r14, r14
0x1800c029d  jz      short loc_1800C02A8
0x1800c029f  mov     rcx, r14
0x1800c02a2  call    cs:__imp_NetMgmtMemFree
0x1800c02a8  xor     eax, eax
0x1800c02aa  mov     rcx, [rbp+0A0h+var_50]
0x1800c02ae  xor     rcx, rsp; StackCookie
0x1800c02b1  call    __security_check_cookie
0x1800c02b6  add     rsp, 168h
0x1800c02bd  pop     r15
0x1800c02bf  pop     r14
0x1800c02c1  pop     r13
0x1800c02c3  pop     r12
0x1800c02c5  pop     rdi
0x1800c02c6  pop     rsi
0x1800c02c7  pop     rbx
0x1800c02c8  pop     rbp
0x1800c02c9  retn
```
