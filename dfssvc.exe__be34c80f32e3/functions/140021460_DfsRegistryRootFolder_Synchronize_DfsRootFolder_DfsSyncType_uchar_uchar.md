# DfsRegistryRootFolder::Synchronize(DfsRootFolder::DfsSyncType,uchar,uchar)

- ea: `0x140021460`
- end: `0x1400218d5`
- name: `?Synchronize@DfsRegistryRootFolder@@UEAAKW4DfsSyncType@DfsRootFolder@@EE@Z`
- size: `1141`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140005a94`
- `0x140005f20`
- `0x140005f44`
- `0x1400096ac`
- `0x1400096d8`
- `0x14000971c`
- `0x14000a318`
- `0x14000a354`
- `0x14000ae0c`
- `0x14000ae38`
- `0x14000b3b8`
- `0x14000b40c`
- `0x14000b4bc`
- `0x14000b714`
- `0x14000b7bc`
- `0x140020be8`
- `0x140020cf8`
- `0x140020fc0`
- `0x1400212e4`
- `0x140021460`
- `0x140028098`
- `0x140028f18`
- `0x14002ccc4`
- `0x14002fbb0`
- `0x140031108`
- `0x14003b7b4`
- `0x140057f64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400215d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400215d6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14002167a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14002167a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400217f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400217f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002187b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002187b`

## pseudocode

```c
unsigned int __fastcall DfsRegistryRootFolder::Synchronize(unsigned __int64 a1, char a2, unsigned __int8 a3, char a4)
{
  unsigned int MetadataKey; // edi
  int v5; // r14d
  DWORD v6; // r13d
  char v7; // si
  char v8; // r15
  unsigned __int64 v9; // rbx
  int TotalRegistryValueSizeForKey; // r12d
  unsigned int result; // eax
  DWORD v12; // r15d
  int updated; // esi
  WCHAR *v14; // r14
  HKEY v15; // rsi
  _DFS_UPDATE_LINK_WORK_CONTEXT *v16; // rax
  DfsThreadpoolWrapper *v17; // rcx
  unsigned int (*v18)(void *); // r9
  _DFS_UPDATE_LINK_WORK_CONTEXT *v19; // rdi
  unsigned int v20; // edx
  __int64 v21; // rdx
  unsigned __int8 v22; // r8
  char v23; // al
  int v24; // edx
  int v25; // ecx
  DWORD cSubKeys; // [rsp+68h] [rbp-19h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-15h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-9h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+80h] [rbp-1h] BYREF
  HKEY v31; // [rsp+88h] [rbp+7h] BYREF
  int v32; // [rsp+90h] [rbp+Fh]
  _QWORD v33[8]; // [rsp+98h] [rbp+17h] BYREF

  MetadataKey = 0;
  v5 = a3;
  hKey = 0;
  v6 = 0;
  cbMaxSubKeyLen = 0;
  v7 = a4;
  cchName = 0;
  v8 = a2;
  ftLastWriteTime = 0;
  v9 = a1;
  cSubKeys = 0;
  v33[0] = 0;
  v33[1] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LODWORD(a1) = (_DWORD)pWppControl;
    if ( pWppControl )
    {
      if ( (pWppControl[7] & 0x20) != 0 && *((_BYTE *)pWppControl + 25) >= 2u )
        WPP_SF_q(*((_QWORD *)pWppControl + 2), 10, WPP_83cf391c31d7303d06f3fe2b286347ad_Traceguids, v9);
    }
  }
  TotalRegistryValueSizeForKey = -1;
  if ( v7 || (result = DfsRootFolder::AcquireRootLock((DfsRootFolder *)v9, 1u)) == 0 )
  {
    if ( (*(_DWORD *)(v9 + 272) & 0x1000) != 0 )
    {
LABEL_59:
      if ( !v7 )
      {
        ++*(_DWORD *)(v9 + 120);
        ReleaseSRWLockExclusive((PSRWLOCK)(v9 + 112));
      }
      if ( (Microsoft_Windows_DFSN_ServerEnableBits & 0x100) != 0 )
      {
        v23 = CDfsTimer::Stop((CDfsTimer *)v33);
        McTemplateU0ztqqx_EtwEventWriteTransfer(
          v25,
          v24,
          *(_QWORD *)(v9 + 304),
          (unsigned __int8)v5,
          v8,
          MetadataKey,
          v23);
      }
      return MetadataKey;
    }
    if ( (Microsoft_Windows_DFSN_ServerEnableBits & 0x100) != 0 )
      McTemplateU0ztq_EtwEventWriteTransfer(a1, a2, *(_QWORD *)(v9 + 304), v5, v8);
    CDfsTimer::Start((CDfsTimer *)v33);
    DfsRootFolder::AcquireRootShareDirectory((DfsRootFolder *)v9);
    v12 = 0;
    MetadataKey = DfsRegistryRootFolder::GetMetadataKey((DfsRegistryRootFolder *)v9, &hKey);
    if ( MetadataKey )
    {
LABEL_51:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x20) != 0
        && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_qd(*((_QWORD *)pWppControl + 2), 13, WPP_83cf391c31d7303d06f3fe2b286347ad_Traceguids, v9, MetadataKey);
      }
      if ( !TotalRegistryValueSizeForKey )
        *(_DWORD *)(v9 + 504) = v12;
      DfsRegistryRootFolder::CheckNamespaceDelegation((DfsRegistryRootFolder *)v9);
      DfsRootFolder::MakeDfsShareOnline(v9, v21, v22);
      v8 = a2;
      goto LABEL_59;
    }
    DfsRootFolder::UpdateLinkInformation((DfsRootFolder *)v9, (unsigned __int64)hKey, 0, 0);
    MetadataKey = 0;
    TotalRegistryValueSizeForKey = DfsGetTotalRegistryValueSizeForKey(hKey, &cSubKeys);
    if ( !TotalRegistryValueSizeForKey )
      v12 = cSubKeys;
    DfsRegistryRootFolder::CheckPreSynchronize((DfsRegistryRootFolder *)v9, hKey);
    updated = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !updated )
    {
      if ( cbMaxSubKeyLen < 0x7FFF )
      {
        ++cbMaxSubKeyLen;
        updated = DfsRootFolder::UpdateLinkInformationPrologue((HANDLE *)v9, cSubKeys);
        if ( !updated )
        {
          v31 = 0;
          v32 = 0;
          while ( 1 )
          {
            cchName = cbMaxSubKeyLen;
            v14 = (WCHAR *)operator new(saturated_mul(cbMaxSubKeyLen, 2u));
            if ( !v14 )
              break;
            updated = RegEnumKeyExW(hKey, v6, v14, &cchName, 0, 0, 0, &ftLastWriteTime);
            if ( updated )
              goto LABEL_32;
            ++v6;
            v12 += 2 * cchName + 2;
            if ( (unsigned int)CRegistry::OpenKey((CRegistry *)&v31, hKey, v14, 0x20019u) )
            {
              TotalRegistryValueSizeForKey = DfsGetTotalRegistryValueSizeForKey(v31, &cSubKeys);
              if ( !TotalRegistryValueSizeForKey )
                v12 += cSubKeys;
              CRegistry::CloseKey((CRegistry *)&v31);
            }
            else
            {
              TotalRegistryValueSizeForKey = v32;
            }
            v15 = hKey;
            v16 = (_DFS_UPDATE_LINK_WORK_CONTEXT *)operator new(0x20u);
            v19 = v16;
            if ( !v16 )
            {
              operator delete(v14);
              MetadataKey = 0;
              break;
            }
            *(_QWORD *)v16 = v9;
            *((_QWORD *)v16 + 1) = v15;
            *((_QWORD *)v16 + 2) = v14;
            *((_DWORD *)v16 + 6) = 1;
            updated = DfsThreadpoolWrapper::SubmitWork(v17, (struct _TP_CALLBACK_ENVIRON_V3 *)(v9 + 328), v16, v18);
            if ( updated )
            {
              _DFS_UPDATE_LINK_WORK_CONTEXT::`scalar deleting destructor'(v19, v20);
              MetadataKey = 0;
              goto LABEL_32;
            }
            MetadataKey = 0;
          }
          updated = 8;
LABEL_32:
          CRegistry::~CRegistry((CRegistry *)&v31);
          LOBYTE(v5) = a3;
        }
      }
      else
      {
        updated = 206;
      }
    }
    if ( updated != 259 )
      MetadataKey = updated;
    if ( MetadataKey )
    {
      DfsRootFolder::UpdateLinkInformationCancel((PTP_CLEANUP_GROUP *)v9);
    }
    else
    {
      MetadataKey = DfsRootFolder::UpdateLinkInformationEpilogue((DfsRootFolder *)v9);
      if ( !MetadataKey )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x20) != 0
          && *((_BYTE *)pWppControl + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)pWppControl + 2), 11, WPP_83cf391c31d7303d06f3fe2b286347ad_Traceguids);
        }
        DfsRootFolder::SetRootFolderSynchronized((DfsRootFolder *)v9);
LABEL_50:
        RegCloseKey(hKey);
        v7 = a4;
        goto LABEL_51;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 12, WPP_83cf391c31d7303d06f3fe2b286347ad_Traceguids, MetadataKey);
    }
    DfsRootFolder::ClearRootFolderSynchronized((DfsRootFolder *)v9);
    goto LABEL_50;
  }
  return result;
}

```

## disassembly

```asm
0x140021460  mov     rax, rsp
0x140021463  mov     [rax+8], rbx
0x140021467  mov     [rax+20h], r9b
0x14002146b  mov     [rax+18h], r8b
0x14002146f  mov     [rax+10h], edx
0x140021472  push    rbp
0x140021473  push    rsi
0x140021474  push    rdi
0x140021475  push    r12
0x140021477  push    r13
0x140021479  push    r14
0x14002147b  push    r15
0x14002147d  lea     rbp, [rax-5Fh]
0x140021481  sub     rsp, 0A0h
0x140021488  xor     edi, edi
0x14002148a  movzx   r14d, r8b
0x14002148e  mov     [rbp+57h+hKey], rdi
0x140021492  mov     r13d, edi
0x140021495  mov     [rbp+57h+cbMaxSubKeyLen], edi
0x140021498  mov     sil, r9b
0x14002149b  mov     [rbp+57h+cchName], edi
0x14002149e  mov     r15d, edx
0x1400214a1  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], rdi
0x1400214a5  mov     rbx, rcx
0x1400214a8  mov     [rbp+57h+cSubKeys], edi
0x1400214ab  mov     [rbp+57h+var_40], rdi
0x1400214af  mov     [rbp+57h+var_38], rdi
0x1400214b3  lea     rax, WPP_GLOBAL_Control
0x1400214ba  cmp     cs:WPP_GLOBAL_Control, rax
0x1400214c1  jz      short loc_1400214F1
0x1400214c3  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400214ca  test    rcx, rcx
0x1400214cd  jz      short loc_1400214F1
0x1400214cf  test    byte ptr [rcx+1Ch], 20h
0x1400214d3  jz      short loc_1400214F1
0x1400214d5  cmp     byte ptr [rcx+19h], 2
0x1400214d9  jb      short loc_1400214F1
0x1400214db  mov     rcx, [rcx+10h]
0x1400214df  lea     edx, [rdi+0Ah]
0x1400214e2  mov     r9, rbx
0x1400214e5  lea     r8, WPP_83cf391c31d7303d06f3fe2b286347ad_Traceguids
0x1400214ec  call    WPP_SF_q
0x1400214f1  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400214f5  test    sil, sil
0x1400214f8  jnz     short loc_14002150C
0x1400214fa  mov     dl, 1; unsigned __int8
0x1400214fc  mov     rcx, rbx; this
0x1400214ff  call    ?AcquireRootLock@DfsRootFolder@@QEAAKE@Z; DfsRootFolder::AcquireRootLock(uchar)
0x140021504  test    eax, eax
0x140021506  jnz     loc_1400218B9
0x14002150c  test    dword ptr [rbx+110h], 1000h
0x140021516  jnz     loc_14002186F
0x14002151c  test    byte ptr cs:Microsoft_Windows_DFSN_ServerEnableBits+1, 1
0x140021523  jz      short loc_140021539
0x140021525  mov     r8, [rbx+130h]
0x14002152c  mov     r9d, r14d
0x14002152f  mov     dword ptr [rsp+0D0h+lpcSubKeys], r15d
0x140021534  call    McTemplateU0ztq_EtwEventWriteTransfer
0x140021539  lea     rcx, [rbp+57h+var_40]; this
0x14002153d  call    ?Start@CDfsTimer@@QEAAXXZ; CDfsTimer::Start(void)
0x140021542  mov     rcx, rbx; this
0x140021545  call    ?AcquireRootShareDirectory@DfsRootFolder@@QEAAKXZ; DfsRootFolder::AcquireRootShareDirectory(void)
0x14002154a  lea     rdx, [rbp+57h+hKey]; HKEY *
0x14002154e  mov     rcx, rbx; this
0x140021551  mov     r15d, edi
0x140021554  call    ?GetMetadataKey@DfsRegistryRootFolder@@AEAAKPEAPEAUHKEY__@@@Z; DfsRegistryRootFolder::GetMetadataKey(HKEY__ * *)
0x140021559  mov     edi, eax
0x14002155b  test    eax, eax
0x14002155d  jnz     loc_14002180B
0x140021563  mov     rdx, [rbp+57h+hKey]; unsigned __int64
0x140021567  xor     r9d, r9d; unsigned __int8
0x14002156a  xor     r8d, r8d; unsigned __int16 *
0x14002156d  mov     rcx, rbx; this
0x140021570  call    ?UpdateLinkInformation@DfsRootFolder@@QEAAK_KPEAGE@Z; DfsRootFolder::UpdateLinkInformation(unsigned __int64,ushort *,uchar)
0x140021575  mov     rcx, [rbp+57h+hKey]; hKey
0x140021579  lea     rdx, [rbp+57h+cSubKeys]; unsigned int *
0x14002157d  call    ?DfsGetTotalRegistryValueSizeForKey@@YAJPEAUHKEY__@@PEAK@Z; DfsGetTotalRegistryValueSizeForKey(HKEY__ *,ulong *)
0x140021582  mov     rdx, [rbp+57h+hKey]; HKEY
0x140021586  xor     edi, edi
0x140021588  test    eax, eax
0x14002158a  mov     rcx, rbx; this
0x14002158d  mov     r12d, eax
0x140021590  cmovz   r15d, [rbp+57h+cSubKeys]
0x140021595  call    ?CheckPreSynchronize@DfsRegistryRootFolder@@AEAAXPEAUHKEY__@@@Z; DfsRegistryRootFolder::CheckPreSynchronize(HKEY__ *)
0x14002159a  mov     rcx, [rbp+57h+hKey]; hKey
0x14002159e  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1400215a2  mov     [rsp+58h], rdi; lpftLastWriteTime
0x1400215a7  xor     r9d, r9d; lpReserved
0x1400215aa  mov     [rsp+0D0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1400215af  xor     r8d, r8d; lpcchClass
0x1400215b2  mov     [rsp+0D0h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1400215b7  xor     edx, edx; lpClass
0x1400215b9  mov     [rsp+0D0h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1400215be  mov     [rsp+0D0h+lpcValues], rdi; lpcValues
0x1400215c3  mov     [rsp+0D0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1400215c8  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1400215cd  lea     rax, [rbp+57h+cSubKeys]
0x1400215d1  mov     [rsp+0D0h+lpcSubKeys], rax; lpcSubKeys
0x1400215d6  call    cs:__imp_RegQueryInfoKeyW
0x1400215dd  nop     dword ptr [rax+rax+00h]
0x1400215e2  mov     esi, eax
0x1400215e4  test    eax, eax
0x1400215e6  jnz     loc_140021748
0x1400215ec  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1400215ef  cmp     eax, 7FFFh
0x1400215f4  jb      short loc_140021600
0x1400215f6  mov     esi, 0CEh
0x1400215fb  jmp     loc_140021748
0x140021600  mov     edx, [rbp+57h+cSubKeys]; unsigned int
0x140021603  inc     eax
0x140021605  mov     rcx, rbx; this
0x140021608  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x14002160b  call    ?UpdateLinkInformationPrologue@DfsRootFolder@@QEAAKK@Z; DfsRootFolder::UpdateLinkInformationPrologue(ulong)
0x140021610  mov     esi, eax
0x140021612  test    eax, eax
0x140021614  jnz     loc_140021748
0x14002161a  mov     [rbp+57h+var_50], rdi
0x14002161e  mov     [rbp+57h+var_48], edi
0x140021621  jmp     short loc_140021625
0x140021623  xor     edi, edi
0x140021625  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x140021628  mov     ecx, eax
0x14002162a  mov     [rbp+57h+cchName], eax
0x14002162d  mov     eax, 2
0x140021632  mul     rcx
0x140021635  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14002163c  cmovo   rax, rcx
0x140021640  mov     rcx, rax; Size
0x140021643  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140021648  mov     r14, rax
0x14002164b  test    rax, rax
0x14002164e  jz      loc_140021736
0x140021654  mov     rcx, [rbp+57h+hKey]; hKey
0x140021658  lea     rax, [rbp+57h+ftLastWriteTime]
0x14002165c  mov     [rsp+0D0h+lpcValues], rax; lpftLastWriteTime
0x140021661  lea     r9, [rbp+57h+cchName]; lpcchName
0x140021665  mov     [rsp+0D0h+lpcbMaxClassLen], rdi; lpcchClass
0x14002166a  mov     r8, r14; lpName
0x14002166d  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdi; lpClass
0x140021672  mov     edx, r13d; dwIndex
0x140021675  mov     [rsp+0D0h+lpcSubKeys], rdi; unsigned int (*)(void *)
0x14002167a  call    cs:__imp_RegEnumKeyExW
0x140021681  nop     dword ptr [rax+rax+00h]
0x140021686  mov     esi, eax
0x140021688  test    eax, eax
0x14002168a  jnz     loc_14002173B
0x140021690  mov     eax, [rbp+57h+cchName]
0x140021693  lea     rcx, [rbp+57h+var_50]; this
0x140021697  mov     rdx, [rbp+57h+hKey]; HKEY
0x14002169b  mov     r9d, 20019h; unsigned int
0x1400216a1  mov     r8, r14; unsigned __int16 *
0x1400216a4  inc     r13d
0x1400216a7  lea     r15d, [r15+rax*2]
0x1400216ab  add     r15d, 2
0x1400216af  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x1400216b4  test    eax, eax
0x1400216b6  jz      short loc_1400216DB
0x1400216b8  mov     rcx, [rbp+57h+var_50]; hKey
0x1400216bc  lea     rdx, [rbp+57h+cSubKeys]; unsigned int *
0x1400216c0  call    ?DfsGetTotalRegistryValueSizeForKey@@YAJPEAUHKEY__@@PEAK@Z; DfsGetTotalRegistryValueSizeForKey(HKEY__ *,ulong *)
0x1400216c5  mov     r12d, eax
0x1400216c8  test    eax, eax
0x1400216ca  jnz     short loc_1400216D0
0x1400216cc  add     r15d, [rbp+57h+cSubKeys]
0x1400216d0  lea     rcx, [rbp+57h+var_50]; this
0x1400216d4  call    ?CloseKey@CRegistry@@QEAAXXZ; CRegistry::CloseKey(void)
0x1400216d9  jmp     short loc_1400216DF
0x1400216db  mov     r12d, [rbp+57h+var_48]
0x1400216df  mov     rsi, [rbp+57h+hKey]
0x1400216e3  mov     ecx, 20h ; ' '; Size
0x1400216e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400216ed  mov     rdi, rax
0x1400216f0  test    rax, rax
0x1400216f3  jz      short loc_14002172C
0x1400216f5  lea     rdx, [rbx+148h]; struct _TP_CALLBACK_ENVIRON_V3 *
0x1400216fc  mov     [rax], rbx
0x1400216ff  mov     r8, rax; void *
0x140021702  mov     [rax+8], rsi
0x140021706  mov     [rax+10h], r14
0x14002170a  mov     dword ptr [rax+18h], 1
0x140021711  call    ?SubmitWork@DfsThreadpoolWrapper@@QEAAKPEAU_TP_CALLBACK_ENVIRON_V3@@PEAXP6AK1@Z2@Z; DfsThreadpoolWrapper::SubmitWork(_TP_CALLBACK_ENVIRON_V3 *,void *,ulong (*)(void *),ulong (*)(void *))
0x140021716  mov     esi, eax
0x140021718  test    eax, eax
0x14002171a  jz      loc_140021623
0x140021720  mov     rcx, rdi; this
0x140021723  call    ??_G_DFS_UPDATE_LINK_WORK_CONTEXT@@QEAAPEAXI@Z; _DFS_UPDATE_LINK_WORK_CONTEXT::`scalar deleting destructor'(uint)
0x140021728  xor     edi, edi
0x14002172a  jmp     short loc_14002173B
0x14002172c  mov     rcx, r14; Block
0x14002172f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140021734  xor     edi, edi
0x140021736  mov     esi, 8
0x14002173b  lea     rcx, [rbp+57h+var_50]; this
0x14002173f  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x140021744  mov     r14b, [rbp+57h+arg_10]
0x140021748  cmp     esi, 103h
0x14002174e  mov     rcx, rbx; this
0x140021751  cmovnz  edi, esi
0x140021754  test    edi, edi
0x140021756  jnz     short loc_1400217A8
0x140021758  call    ?UpdateLinkInformationEpilogue@DfsRootFolder@@QEAAKXZ; DfsRootFolder::UpdateLinkInformationEpilogue(void)
0x14002175d  mov     edi, eax
0x14002175f  test    eax, eax
0x140021761  jnz     short loc_1400217AD
0x140021763  lea     r13, WPP_GLOBAL_Control
0x14002176a  cmp     cs:WPP_GLOBAL_Control, r13
0x140021771  jz      short loc_14002179E
0x140021773  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002177a  test    rcx, rcx
0x14002177d  jz      short loc_14002179E
0x14002177f  test    byte ptr [rcx+1Ch], 20h
0x140021783  jz      short loc_14002179E
0x140021785  cmp     byte ptr [rcx+19h], 2
0x140021789  jb      short loc_14002179E
0x14002178b  mov     rcx, [rcx+10h]
0x14002178f  lea     edx, [rax+0Bh]
0x140021792  lea     r8, WPP_83cf391c31d7303d06f3fe2b286347ad_Traceguids
0x140021799  call    WPP_SF_
0x14002179e  mov     rcx, rbx; this
0x1400217a1  call    ?SetRootFolderSynchronized@DfsRootFolder@@QEAAXXZ; DfsRootFolder::SetRootFolderSynchronized(void)
0x1400217a6  jmp     short loc_1400217F5
0x1400217a8  call    ?UpdateLinkInformationCancel@DfsRootFolder@@QEAAXXZ; DfsRootFolder::UpdateLinkInformationCancel(void)
0x1400217ad  lea     r13, WPP_GLOBAL_Control
0x1400217b4  cmp     cs:WPP_GLOBAL_Control, r13
0x1400217bb  jz      short loc_1400217ED
0x1400217bd  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400217c4  test    rcx, rcx
0x1400217c7  jz      short loc_1400217ED
0x1400217c9  test    byte ptr [rcx+1Ch], 20h
0x1400217cd  jz      short loc_1400217ED
0x1400217cf  cmp     byte ptr [rcx+19h], 2
0x1400217d3  jb      short loc_1400217ED
0x1400217d5  mov     rcx, [rcx+10h]
0x1400217d9  lea     r8, WPP_83cf391c31d7303d06f3fe2b286347ad_Traceguids
0x1400217e0  mov     edx, 0Ch
0x1400217e5  mov     r9d, edi
0x1400217e8  call    WPP_SF_D
0x1400217ed  mov     rcx, rbx; this
0x1400217f0  call    ?ClearRootFolderSynchronized@DfsRootFolder@@QEAAXXZ; DfsRootFolder::ClearRootFolderSynchronized(void)
0x1400217f5  mov     rcx, [rbp+57h+hKey]; hKey
0x1400217f9  call    cs:__imp_RegCloseKey
0x140021800  nop     dword ptr [rax+rax+00h]
0x140021805  mov     sil, [rbp+57h+arg_18]
0x140021809  jmp     short loc_140021812
0x14002180b  lea     r13, WPP_GLOBAL_Control
0x140021812  cmp     cs:WPP_GLOBAL_Control, r13
0x140021819  jz      short loc_14002184F
0x14002181b  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140021822  test    rcx, rcx
0x140021825  jz      short loc_14002184F
0x140021827  test    byte ptr [rcx+1Ch], 20h
0x14002182b  jz      short loc_14002184F
0x14002182d  cmp     byte ptr [rcx+19h], 2
0x140021831  jb      short loc_14002184F
0x140021833  mov     rcx, [rcx+10h]
0x140021837  lea     r8, WPP_83cf391c31d7303d06f3fe2b286347ad_Traceguids
0x14002183e  mov     edx, 0Dh
0x140021843  mov     dword ptr [rsp+0D0h+lpcSubKeys], edi
0x140021847  mov     r9, rbx
0x14002184a  call    WPP_SF_qd
0x14002184f  test    r12d, r12d
0x140021852  jnz     short loc_14002185B
0x140021854  mov     [rbx+1F8h], r15d
0x14002185b  mov     rcx, rbx; this
0x14002185e  call    ?CheckNamespaceDelegation@DfsRegistryRootFolder@@QEAAXXZ; DfsRegistryRootFolder::CheckNamespaceDelegation(void)
0x140021863  mov     rcx, rbx; this
0x140021866  call    ?MakeDfsShareOnline@DfsRootFolder@@QEAAKXZ; DfsRootFolder::MakeDfsShareOnline(void)
0x14002186b  mov     r15d, [rbp+57h+arg_8]
0x14002186f  test    sil, sil
0x140021872  jnz     short loc_140021887
0x140021874  inc     dword ptr [rbx+78h]
0x140021877  lea     rcx, [rbx+70h]; SRWLock
0x14002187b  call    cs:__imp_ReleaseSRWLockExclusive
0x140021882  nop     dword ptr [rax+rax+00h]
0x140021887  test    byte ptr cs:Microsoft_Windows_DFSN_ServerEnableBits+1, 1
0x14002188e  jz      short loc_1400218B7
0x140021890  lea     rcx, [rbp+57h+var_40]; this
0x140021894  call    ?Stop@CDfsTimer@@QEAA_KXZ; CDfsTimer::Stop(void)
0x140021899  mov     r8, [rbx+130h]
0x1400218a0  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x1400218a5  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], edi
0x1400218a9  movzx   r9d, r14b
0x1400218ad  mov     dword ptr [rsp+0D0h+lpcSubKeys], r15d
0x1400218b2  call    McTemplateU0ztqqx_EtwEventWriteTransfer
0x1400218b7  mov     eax, edi
0x1400218b9  mov     rbx, [rsp+0D0h+arg_0]
0x1400218c1  add     rsp, 0A0h
0x1400218c8  pop     r15
0x1400218ca  pop     r14
0x1400218cc  pop     r13
0x1400218ce  pop     r12
0x1400218d0  pop     rdi
0x1400218d1  pop     rsi
0x1400218d2  pop     rbp
0x1400218d3  retn
```
