# CmsVolumeAnalyzer::DestageContainers(CmsTransactionContext *,_EMS_STORAGE_TIER_MEDIA_TYPE,_EMS_STORAGE_TIER_MEDIA_TYPE,_RTL_BITMAP *,ulong *,_EmsAllocationType,uchar *,ulong,ulong *,uchar,uchar,CmsContainerRotationQueue *)

- ea: `0x1c00c0b98`
- end: `0x1c00c0ff5`
- name: `?DestageContainers@CmsVolumeAnalyzer@@IEAAJPEAVCmsTransactionContext@@W4_EMS_STORAGE_TIER_MEDIA_TYPE@@1PEAU_RTL_BITMAP@@PEAKW4_EmsAllocationType@@PEAEK3EEPEAVCmsContainerRotationQueue@@@Z`
- size: `1117`
- prototype: `int __high(struct CmsTransactionContext *, enum _EMS_STORAGE_TIER_MEDIA_TYPE, enum _EMS_STORAGE_TIER_MEDIA_TYPE, struct _RTL_BITMAP *, unsigned int *, enum _EmsAllocationType, unsigned __int8 *, unsigned int, unsigned int *, unsigned __int8, unsigned __int8, struct CmsContainerRotationQueue *)`
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1c00c01e4`
- `0x1c00c0ffc`
- `0x1c00c1124`
- `0x1c00c120c`

## callees

- `0x1c00224d0`
- `0x1c0024964`
- `0x1c0024b68`
- `0x1c0028050`
- `0x1c0052880`
- `0x1c00b10c0`
- `0x1c00c0b98`
- `0x1c00d34d0`
- `0x1c00d830c`
- `0x1c00f5d70`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c0eeb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c0eeb`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00c0c64`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00c0f01`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00c0c64`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00c0f01`
- `ntoskrnl!RtlTestBit` at `0x1c00c0d17`
- `ntoskrnl!RtlTestBit` at `0x1c00c0d17`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00c0c3f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00c0c3f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00c0e3b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00c0f93`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00c0e3b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00c0f93`

## pseudocode

```c
__int64 __fastcall CmsVolumeAnalyzer::DestageContainers(
        __int64 a1,
        struct CmsTransactionContext *a2,
        int a3,
        int a4,
        struct _RTL_BITMAP *a5,
        ULONG *a6,
        int a7,
        _BYTE *a8,
        unsigned int a9,
        unsigned int *a10,
        char a11,
        char a12,
        __int64 a13)
{
  NTSTATUS ContainerReference; // edi
  struct _RTL_BITMAP *v16; // rbx
  ULONG *v17; // r15
  char v18; // al
  unsigned int *v19; // r12
  unsigned int NextForwardRunSet; // ebx
  ULONG v21; // r13d
  unsigned __int64 v22; // rbx
  int v23; // ecx
  unsigned __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rcx
  CmsVolumeContainer *v27; // r10
  ULONG_PTR v28; // rbx
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // eax
  _BYTE *v33; // rax
  __int64 v34; // rcx
  unsigned __int8 *v36; // [rsp+20h] [rbp-79h]
  int v37; // [rsp+30h] [rbp-69h]
  struct _SmsQuickIndex *v38; // [rsp+40h] [rbp-59h]
  unsigned __int8 v39; // [rsp+48h] [rbp-51h]
  CmsRangeMap *v40; // [rsp+50h] [rbp-49h]
  __int128 v41; // [rsp+58h] [rbp-41h] BYREF
  __int128 v42; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v43[3]; // [rsp+78h] [rbp-21h] BYREF
  _QWORD v44[8]; // [rsp+90h] [rbp-9h] BYREF
  struct SmsContainer *v45; // [rsp+E0h] [rbp+47h] BYREF
  ULONG BitNumber; // [rsp+F0h] [rbp+57h] BYREF
  int v47; // [rsp+F8h] [rbp+5Fh]

  v47 = a4;
  v45 = 0;
  v42 = 0;
  ContainerReference = 0;
  v41 = 0;
  v40 = (CmsRangeMap *)(((a7 + 3LL * a3) << 6) + a1 + 1632);
  if ( *((_QWORD *)v40 + 3) )
  {
    v16 = a5;
    v17 = a6;
    if ( *a6 >= a5->SizeOfBitMap )
      *a6 = 0;
    v18 = *(_BYTE *)(a1 + 104);
    if ( (v18 & 2) == 0 )
    {
      v19 = a10;
      while ( (v18 & 4) == 0 && *v19 < a9 )
      {
        ExAcquirePushLockSharedEx(a1, 0);
        BitNumber = *v17;
        NextForwardRunSet = CmsClusterOperations::FindNextForwardRunSet(v16, BitNumber, &BitNumber);
        ExReleasePushLockEx(a1, 0);
        if ( !NextForwardRunSet )
        {
          *v17 = 0;
          goto LABEL_41;
        }
        v21 = BitNumber;
        v22 = BitNumber;
        v43[0] = BitNumber;
        *v17 = BitNumber + 1;
        v43[1] = (unsigned int)(*(__int64 *)(*(_QWORD *)(a1 + 3360) + 56LL) >> *(_DWORD *)(a1 + 200)) - v21;
        if ( v41 != 0 && v22 >= (unsigned __int64)v41 && v22 < *((_QWORD *)&v41 + 1) + (_QWORD)v41
          || CmsRangeMap::FindMappedValueInternal(
               v40,
               a2,
               (const struct _RANGE *)v43,
               (struct _RANGE *)&v41,
               0,
               0,
               0,
               0,
               v38,
               v39) )
        {
          if ( !RtlTestBit((PRTL_BITMAP)(a1 + 384), v21) )
          {
            v23 = *(_DWORD *)(a1 + 200);
            v24 = v22 << v23;
            v25 = 1LL << v23;
            v26 = *(_QWORD *)(*(_QWORD *)(a1 + 3360) + 3048LL);
            v44[1] = v25;
            v44[0] = v24;
            LOBYTE(v36) = 0;
            ContainerReference = CmsVolumeContainer::RealRangeToContainerRange(v26, a2, v44, &v42, (_DWORD)v36, 0);
            if ( ContainerReference < 0 )
              break;
            v27 = *(CmsVolumeContainer **)(*(_QWORD *)(a1 + 3360) + 3048LL);
            v28 = (unsigned __int64)v42 >> ((unsigned __int8)*(_DWORD *)(*((_QWORD *)v27 + 1) + 76LL) + 1);
            ContainerReference = CmsVolumeContainer::GetContainerReference(
                                   v27,
                                   a2,
                                   v28,
                                   (PRTL_DYNAMIC_HASH_TABLE_ENTRY *)&v45,
                                   0,
                                   0,
                                   0);
            if ( ContainerReference < 0 )
              break;
            if ( *((_DWORD *)v45 + 21)
              || *((_BYTE *)v45 + 28)
              || (v29 = *((_DWORD *)v45 + 143), (v29 & 1) != 0)
              || (v29 & 0x200) != 0
              || (v29 & 0x100) != 0
              || a11 && ((v29 & 0x20) != 0 || *((_QWORD *)v45 + 74)) )
            {
              v34 = *(_QWORD *)(*(_QWORD *)(a1 + 3360) + 3048LL);
              _InterlockedDecrement((volatile signed __int32 *)v45 + 22);
              IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v34 + 328), 0, 0x20u);
              --*((_DWORD *)a2 + 706);
            }
            else
            {
              v30 = *(_QWORD *)(*(_QWORD *)(a1 + 3360) + 3048LL);
              _InterlockedDecrement((volatile signed __int32 *)v45 + 22);
              IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v30 + 328), 0, 0x20u);
              --*((_DWORD *)a2 + 706);
              v31 = *(_QWORD *)(*(_QWORD *)(a1 + 3360) + 3048LL);
              if ( a11 )
              {
                LOWORD(v36) = 0;
                v32 = CmsVolumeContainer::CompactAndCompressContainer(v31, (__int64)a2, v28, 0, (__int64)v36, 0, 0, 0);
              }
              else
              {
                LOBYTE(v38) = 0;
                LOBYTE(v37) = a12;
                v32 = CmsVolumeContainer::MoveContainerToTier(v31, a2, v28, &v42, v47, a7, v37, a13);
              }
              ContainerReference = v32;
              if ( v32 >= 0 )
              {
                CmsTransactionContext::Commit(a2, 0, 0, 0);
                v33 = a8;
                ++*v19;
                *v33 = 1;
              }
              else
              {
                CmsTransactionContext::Abort(a2);
                if ( ContainerReference != -1073741267 )
                {
                  if ( ContainerReference == -1073741536 )
                  {
                    --*v17;
                    ExAcquirePushLockExclusiveEx(a1 + 8, 0);
                    *(_BYTE *)(a1 + 105) |= 2u;
                    ExReleasePushLockEx(a1 + 8, 0);
                  }
                  if ( ContainerReference != -1073741432 && ContainerReference != -1073740759 )
                    break;
                  ContainerReference = CmsVolume::Flush(
                                         *(CmsVolume **)(a1 + 3360),
                                         0x11u,
                                         0,
                                         0,
                                         0,
                                         0,
                                         (struct _KEVENT *)(a1 + 3656));
                  if ( ContainerReference < 0 )
                    break;
                  --*v17;
                }
              }
            }
          }
        }
        else
        {
          *v17 = v41 + DWORD2(v41);
          v41 = MsZeroRange;
        }
        v18 = *(_BYTE *)(a1 + 104);
        v16 = a5;
        if ( (v18 & 2) != 0 )
          break;
      }
    }
  }
  else
  {
LABEL_41:
    ContainerReference = -1073741267;
  }
  if ( (*(_BYTE *)(a1 + 104) & 6) != 0 )
    ContainerReference = -1073741431;
  if ( ContainerReference < 0 )
    CmsTransactionContext::Abort(a2);
  return (unsigned int)ContainerReference;
}

```

## disassembly

```asm
0x1c00c0b98  mov     [rsp-8+arg_8], rbx
0x1c00c0b9d  mov     [rsp-8+arg_18], r9d
0x1c00c0ba2  push    rbp
0x1c00c0ba3  push    rsi
0x1c00c0ba4  push    rdi
0x1c00c0ba5  push    r12
0x1c00c0ba7  push    r13
0x1c00c0ba9  push    r14
0x1c00c0bab  push    r15
0x1c00c0bad  lea     rbp, [rsp-7]
0x1c00c0bb2  sub     rsp, 0A0h
0x1c00c0bb9  movsxd  rax, r8d
0x1c00c0bbc  xor     r13d, r13d
0x1c00c0bbf  xorps   xmm0, xmm0
0x1c00c0bc2  mov     [rbp+37h+arg_0], r13
0x1c00c0bc6  mov     r14, rdx
0x1c00c0bc9  mov     rsi, rcx
0x1c00c0bcc  movups  [rbp+37h+var_68], xmm0
0x1c00c0bd0  lea     r8, [rax+rax*2]
0x1c00c0bd4  mov     edi, r13d
0x1c00c0bd7  movsxd  rax, [rbp+37h+arg_30]
0x1c00c0bdb  add     r8, rax
0x1c00c0bde  lea     rax, [rcx+660h]
0x1c00c0be5  shl     r8, 6
0x1c00c0be9  add     rax, r8
0x1c00c0bec  movups  [rbp+37h+var_78], xmm0
0x1c00c0bf0  mov     [rbp+37h+var_80], rax
0x1c00c0bf4  cmp     [rax+18h], r13
0x1c00c0bf8  jz      loc_1C00C0FBA
0x1c00c0bfe  mov     rbx, [rbp+37h+arg_20]
0x1c00c0c02  mov     r15, [rbp+37h+arg_28]
0x1c00c0c06  mov     eax, [rbx]
0x1c00c0c08  cmp     [r15], eax
0x1c00c0c0b  jb      short loc_1C00C0C10
0x1c00c0c0d  mov     [r15], r13d
0x1c00c0c10  mov     al, [rcx+68h]
0x1c00c0c13  test    al, 2
0x1c00c0c15  jnz     loc_1C00C0FBF
0x1c00c0c1b  mov     r12, [rbp+37h+arg_48]
0x1c00c0c22  test    al, 4
0x1c00c0c24  jnz     loc_1C00C0FBF
0x1c00c0c2a  mov     eax, [rbp+37h+arg_40]
0x1c00c0c30  cmp     [r12], eax
0x1c00c0c34  jnb     loc_1C00C0FBF
0x1c00c0c3a  xor     edx, edx
0x1c00c0c3c  mov     rcx, rsi
0x1c00c0c3f  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c00c0c46  nop     dword ptr [rax+rax+00h]
0x1c00c0c4b  mov     edx, [r15]; unsigned int
0x1c00c0c4e  lea     r8, [rbp+37h+BitNumber]; unsigned int *
0x1c00c0c52  mov     rcx, rbx; struct _RTL_BITMAP *
0x1c00c0c55  mov     [rbp+37h+BitNumber], edx
0x1c00c0c58  call    ?FindNextForwardRunSet@CmsClusterOperations@@SAKPEAU_RTL_BITMAP@@KPEAK@Z; CmsClusterOperations::FindNextForwardRunSet(_RTL_BITMAP *,ulong,ulong *)
0x1c00c0c5d  xor     edx, edx
0x1c00c0c5f  mov     rcx, rsi
0x1c00c0c62  mov     ebx, eax
0x1c00c0c64  call    cs:__imp_ExReleasePushLockEx
0x1c00c0c6b  nop     dword ptr [rax+rax+00h]
0x1c00c0c70  test    ebx, ebx
0x1c00c0c72  jz      loc_1C00C0FB7
0x1c00c0c78  mov     r13d, [rbp+37h+BitNumber]
0x1c00c0c7c  xor     edx, edx
0x1c00c0c7e  mov     ebx, r13d
0x1c00c0c81  mov     [rbp+37h+var_58], rbx
0x1c00c0c85  lea     eax, [r13+1]
0x1c00c0c89  mov     [r15], eax
0x1c00c0c8c  mov     rax, [rsi+0D20h]
0x1c00c0c93  mov     ecx, [rsi+0C8h]
0x1c00c0c99  mov     rax, [rax+38h]
0x1c00c0c9d  sar     rax, cl
0x1c00c0ca0  sub     eax, r13d
0x1c00c0ca3  mov     [rbp+37h+var_50], rax
0x1c00c0ca7  cmp     qword ptr [rbp+37h+var_78], rdx
0x1c00c0cab  jnz     short loc_1C00C0CB3
0x1c00c0cad  cmp     qword ptr [rbp+37h+var_78+8], rdx
0x1c00c0cb1  jz      short loc_1C00C0CC5
0x1c00c0cb3  mov     rcx, qword ptr [rbp+37h+var_78]
0x1c00c0cb7  cmp     rbx, rcx
0x1c00c0cba  jb      short loc_1C00C0CC5
0x1c00c0cbc  add     rcx, qword ptr [rbp+37h+var_78+8]
0x1c00c0cc0  cmp     rbx, rcx
0x1c00c0cc3  jb      short loc_1C00C0D0D
0x1c00c0cc5  mov     rcx, [rbp+37h+var_80]; this
0x1c00c0cc9  lea     r9, [rbp+37h+var_78]; struct _RANGE *
0x1c00c0ccd  mov     [rsp+0D0h+var_98], rdx; unsigned __int64 *
0x1c00c0cd2  lea     r8, [rbp+37h+var_58]; struct _RANGE *
0x1c00c0cd6  mov     [rsp+0D0h+var_A0], rdx; unsigned __int64 *
0x1c00c0cdb  mov     [rsp+0D0h+var_A8], rdx; struct _SmsQuickIndex *
0x1c00c0ce0  mov     byte ptr [rsp+0D0h+var_B0], dl; char
0x1c00c0ce4  mov     rdx, r14; struct CmsTransactionCore *
0x1c00c0ce7  call    ?FindMappedValueInternal@CmsRangeMap@@IEAAEPEAVCmsTransactionCore@@PEBU_RANGE@@PEAU3@EPEAU_SmsQuickIndex@@PEA_K43E@Z; CmsRangeMap::FindMappedValueInternal(CmsTransactionCore *,_RANGE const *,_RANGE *,uchar,_SmsQuickIndex *,unsigned __int64 *,unsigned __int64 *,_SmsQuickIndex *,uchar)
0x1c00c0cec  test    al, al
0x1c00c0cee  jnz     short loc_1C00C0D0D
0x1c00c0cf0  mov     ecx, dword ptr [rbp+37h+var_78+8]
0x1c00c0cf3  add     ecx, dword ptr [rbp+37h+var_78]
0x1c00c0cf6  mov     [r15], ecx
0x1c00c0cf9  xor     r13d, r13d
0x1c00c0cfc  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00c0d03  movdqu  [rbp+37h+var_78], xmm0
0x1c00c0d08  jmp     loc_1C00C0FA6
0x1c00c0d0d  lea     rcx, [rsi+180h]; BitMapHeader
0x1c00c0d14  mov     edx, r13d; BitNumber
0x1c00c0d17  call    cs:__imp_RtlTestBit
0x1c00c0d1e  nop     dword ptr [rax+rax+00h]
0x1c00c0d23  xor     r13d, r13d
0x1c00c0d26  test    al, al
0x1c00c0d28  jnz     loc_1C00C0FA6
0x1c00c0d2e  mov     rax, [rsi+0D20h]
0x1c00c0d35  lea     r9, [rbp+37h+var_68]
0x1c00c0d39  mov     ecx, [rsi+0C8h]
0x1c00c0d3f  lea     r8, [rbp+37h+var_40]
0x1c00c0d43  shl     rbx, cl
0x1c00c0d46  mov     rdx, r14
0x1c00c0d49  mov     [rsp+0D0h+var_A8], r13
0x1c00c0d4e  mov     r10, [rax+0BE8h]
0x1c00c0d55  lea     eax, [r13+1]
0x1c00c0d59  shl     rax, cl
0x1c00c0d5c  mov     rcx, r10
0x1c00c0d5f  mov     [rbp+37h+var_38], rax
0x1c00c0d63  mov     [rbp+37h+var_40], rbx
0x1c00c0d67  mov     byte ptr [rsp+0D0h+var_B0], r13b
0x1c00c0d6c  call    ?RealRangeToContainerRange@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@PEAU3@EPEA_K@Z; CmsVolumeContainer::RealRangeToContainerRange(CmsTransactionContext *,_RANGE,_RANGE *,uchar,unsigned __int64 *)
0x1c00c0d71  mov     edi, eax
0x1c00c0d73  test    eax, eax
0x1c00c0d75  js      loc_1C00C0FBF
0x1c00c0d7b  mov     rax, [rsi+0D20h]
0x1c00c0d82  lea     r9, [rbp+37h+arg_0]; struct SmsContainer **
0x1c00c0d86  mov     rbx, qword ptr [rbp+37h+var_68]
0x1c00c0d8a  mov     rdx, r14; struct CmsTransactionContext *
0x1c00c0d8d  mov     byte ptr [rsp+0D0h+var_A0], r13b; unsigned __int8
0x1c00c0d92  mov     byte ptr [rsp+0D0h+var_A8], r13b; unsigned __int8
0x1c00c0d97  mov     r10, [rax+0BE8h]
0x1c00c0d9e  mov     byte ptr [rsp+0D0h+var_B0], r13b; unsigned __int8
0x1c00c0da3  mov     rax, [r10+8]
0x1c00c0da7  mov     ecx, [rax+4Ch]
0x1c00c0daa  inc     ecx
0x1c00c0dac  shr     rbx, cl
0x1c00c0daf  mov     rcx, r10; this
0x1c00c0db2  mov     r8, rbx; unsigned __int64
0x1c00c0db5  call    ?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EEE@Z; CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar,uchar)
0x1c00c0dba  mov     edi, eax
0x1c00c0dbc  test    eax, eax
0x1c00c0dbe  js      loc_1C00C0FBF
0x1c00c0dc4  mov     rdx, [rbp+37h+arg_0]
0x1c00c0dc8  cmp     [rdx+54h], r13d
0x1c00c0dcc  jnz     loc_1C00C0F72
0x1c00c0dd2  cmp     [rdx+1Ch], r13b
0x1c00c0dd6  jnz     loc_1C00C0F72
0x1c00c0ddc  mov     eax, [rdx+23Ch]
0x1c00c0de2  test    al, 1
0x1c00c0de4  jnz     loc_1C00C0F72
0x1c00c0dea  bt      eax, 9
0x1c00c0dee  jb      loc_1C00C0F72
0x1c00c0df4  bt      eax, 8
0x1c00c0df8  jb      loc_1C00C0F72
0x1c00c0dfe  cmp     [rbp+37h+arg_50], r13b
0x1c00c0e05  jz      short loc_1C00C0E1C
0x1c00c0e07  test    al, 20h
0x1c00c0e09  jnz     loc_1C00C0F72
0x1c00c0e0f  cmp     [rdx+250h], r13
0x1c00c0e16  ja      loc_1C00C0F72
0x1c00c0e1c  mov     rax, [rsi+0D20h]
0x1c00c0e23  mov     rcx, [rax+0BE8h]
0x1c00c0e2a  lock dec dword ptr [rdx+58h]
0x1c00c0e2e  add     rcx, 148h; RemoveLock
0x1c00c0e35  xor     edx, edx; Tag
0x1c00c0e37  lea     r8d, [rdx+20h]; RemlockSize
0x1c00c0e3b  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00c0e42  nop     dword ptr [rax+rax+00h]
0x1c00c0e47  dec     dword ptr [r14+0B08h]
0x1c00c0e4e  mov     r8, rbx
0x1c00c0e51  mov     rdx, r14
0x1c00c0e54  mov     rax, [rsi+0D20h]
0x1c00c0e5b  mov     rcx, [rax+0BE8h]
0x1c00c0e62  cmp     [rbp+37h+arg_50], r13b
0x1c00c0e69  jz      short loc_1C00C0E8A
0x1c00c0e6b  mov     [rsp+0D0h+var_98], r13
0x1c00c0e70  xor     r9d, r9d
0x1c00c0e73  mov     [rsp+0D0h+var_A0], r13
0x1c00c0e78  mov     dword ptr [rsp+0D0h+var_A8], r13d
0x1c00c0e7d  mov     word ptr [rsp+0D0h+var_B0], r13w
0x1c00c0e83  call    ?CompactAndCompressContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KW4_MS_COMPRESSION_FORMATS@@GKPEBU_RANGE_TUPLE@@1@Z; CmsVolumeContainer::CompactAndCompressContainer(CmsTransactionContext *,unsigned __int64,_MS_COMPRESSION_FORMATS,ushort,ulong,_RANGE_TUPLE const *,unsigned __int64)
0x1c00c0e88  jmp     short loc_1C00C0EBC
0x1c00c0e8a  mov     rax, [rbp+37h+arg_60]
0x1c00c0e91  lea     r9, [rbp+37h+var_68]
0x1c00c0e95  mov     byte ptr [rsp+0D0h+var_90], r13b
0x1c00c0e9a  mov     [rsp+0D0h+var_98], rax
0x1c00c0e9f  mov     al, [rbp+37h+arg_58]
0x1c00c0ea5  mov     byte ptr [rsp+0D0h+var_A0], al
0x1c00c0ea9  mov     eax, [rbp+37h+arg_30]
0x1c00c0eac  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1c00c0eb0  mov     eax, [rbp+37h+arg_18]
0x1c00c0eb3  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1c00c0eb7  call    ?MoveContainerToTier@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEBU_RANGE@@W4_EMS_STORAGE_TIER_MEDIA_TYPE@@W4_EmsAllocationType@@EPEAVCmsContainerRotationQueue@@E@Z; CmsVolumeContainer::MoveContainerToTier(CmsTransactionContext *,unsigned __int64,_RANGE const *,_EMS_STORAGE_TIER_MEDIA_TYPE,_EmsAllocationType,uchar,CmsContainerRotationQueue *,uchar)
0x1c00c0ebc  mov     edi, eax
0x1c00c0ebe  mov     rcx, r14; this
0x1c00c0ec1  test    eax, eax
0x1c00c0ec3  jns     loc_1C00C0F58
0x1c00c0ec9  call    ?Abort@CmsTransactionContext@@QEAAXXZ; CmsTransactionContext::Abort(void)
0x1c00c0ece  cmp     edi, 0C000022Dh
0x1c00c0ed4  jz      loc_1C00C0FA6
0x1c00c0eda  cmp     edi, 0C0000120h
0x1c00c0ee0  jnz     short loc_1C00C0F0D
0x1c00c0ee2  dec     dword ptr [r15]
0x1c00c0ee5  lea     rcx, [rsi+8]
0x1c00c0ee9  xor     edx, edx
0x1c00c0eeb  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00c0ef2  nop     dword ptr [rax+rax+00h]
0x1c00c0ef7  or      byte ptr [rsi+69h], 2
0x1c00c0efb  lea     rcx, [rsi+8]
0x1c00c0eff  xor     edx, edx
0x1c00c0f01  call    cs:__imp_ExReleasePushLockEx
0x1c00c0f08  nop     dword ptr [rax+rax+00h]
0x1c00c0f0d  cmp     edi, 0C0000188h
0x1c00c0f13  jz      short loc_1C00C0F21
0x1c00c0f15  cmp     edi, 0C0000429h
0x1c00c0f1b  jnz     loc_1C00C0FBF
0x1c00c0f21  mov     rcx, [rsi+0D20h]; this
0x1c00c0f28  lea     rax, [rsi+0E48h]
0x1c00c0f2f  mov     [rsp+0D0h+var_A0], rax; struct _KEVENT *
0x1c00c0f34  xor     r9d, r9d; unsigned int
0x1c00c0f37  mov     [rsp+0D0h+var_A8], r13; unsigned __int8 *
0x1c00c0f3c  xor     r8d, r8d; void *
0x1c00c0f3f  mov     [rsp+0D0h+var_B0], r13; unsigned __int8 *
0x1c00c0f44  lea     edx, [r9+11h]; unsigned int
0x1c00c0f48  call    ?Flush@CmsVolume@@QEAAJKPEAXKPEAE1PEAU_KEVENT@@@Z; CmsVolume::Flush(ulong,void *,ulong,uchar *,uchar *,_KEVENT *)
0x1c00c0f4d  mov     edi, eax
0x1c00c0f4f  test    eax, eax
0x1c00c0f51  js      short loc_1C00C0FBF
0x1c00c0f53  dec     dword ptr [r15]
0x1c00c0f56  jmp     short loc_1C00C0FA6
0x1c00c0f58  xor     r9d, r9d; unsigned __int8
0x1c00c0f5b  xor     r8d, r8d; struct _SmsLsn *
0x1c00c0f5e  xor     edx, edx; unsigned __int8
0x1c00c0f60  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x1c00c0f65  mov     rax, [rbp+37h+arg_38]
0x1c00c0f69  inc     dword ptr [r12]
0x1c00c0f6d  mov     byte ptr [rax], 1
0x1c00c0f70  jmp     short loc_1C00C0FA6
0x1c00c0f72  mov     rax, [rsi+0D20h]
0x1c00c0f79  mov     r8d, 20h ; ' '; RemlockSize
0x1c00c0f7f  mov     rcx, [rax+0BE8h]
0x1c00c0f86  lock dec dword ptr [rdx+58h]
0x1c00c0f8a  add     rcx, 148h; RemoveLock
0x1c00c0f91  xor     edx, edx; Tag
0x1c00c0f93  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00c0f9a  nop     dword ptr [rax+rax+00h]
0x1c00c0f9f  dec     dword ptr [r14+0B08h]
0x1c00c0fa6  mov     al, [rsi+68h]
0x1c00c0fa9  mov     rbx, [rbp+37h+arg_20]
0x1c00c0fad  test    al, 2
0x1c00c0faf  jz      loc_1C00C0C22
0x1c00c0fb5  jmp     short loc_1C00C0FBF
0x1c00c0fb7  mov     [r15], r13d
0x1c00c0fba  mov     edi, 0C000022Dh
0x1c00c0fbf  test    byte ptr [rsi+68h], 6
0x1c00c0fc3  mov     eax, 0C0000189h
0x1c00c0fc8  cmovnz  edi, eax
0x1c00c0fcb  test    edi, edi
0x1c00c0fcd  jns     short loc_1C00C0FD7
0x1c00c0fcf  mov     rcx, r14; this
0x1c00c0fd2  call    ?Abort@CmsTransactionContext@@QEAAXXZ; CmsTransactionContext::Abort(void)
0x1c00c0fd7  mov     rbx, [rsp+0D0h+arg_8]
0x1c00c0fdf  mov     eax, edi
0x1c00c0fe1  add     rsp, 0A0h
0x1c00c0fe8  pop     r15
0x1c00c0fea  pop     r14
0x1c00c0fec  pop     r13
0x1c00c0fee  pop     r12
0x1c00c0ff0  pop     rdi
0x1c00c0ff1  pop     rsi
0x1c00c0ff2  pop     rbp
0x1c00c0ff3  retn
```
