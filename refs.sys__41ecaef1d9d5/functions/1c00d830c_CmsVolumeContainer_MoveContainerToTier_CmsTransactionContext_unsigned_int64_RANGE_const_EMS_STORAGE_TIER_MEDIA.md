# CmsVolumeContainer::MoveContainerToTier(CmsTransactionContext *,unsigned __int64,_RANGE const *,_EMS_STORAGE_TIER_MEDIA_TYPE,_EmsAllocationType,uchar,CmsContainerRotationQueue *,uchar)

- ea: `0x1c00d830c`
- end: `0x1c00d879f`
- name: `?MoveContainerToTier@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEBU_RANGE@@W4_EMS_STORAGE_TIER_MEDIA_TYPE@@W4_EmsAllocationType@@EPEAVCmsContainerRotationQueue@@E@Z`
- size: `1171`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1c00c0b98`
- `0x1c00c140c`

## callees

- `0x1c00b763c`
- `0x1c00c15a0`
- `0x1c00c3244`
- `0x1c00d7d34`
- `0x1c00d830c`
- `0x1c00d8e38`
- `0x1c00da6c4`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x1c00d84db`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00d84db`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00d84fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00d8783`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00d84fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00d8783`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c00d85d7`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c00d85d7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00d84bb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00d84bb`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::MoveContainerToTier(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 *a4,
        unsigned int a5,
        unsigned int a6,
        char a7,
        __int64 a8,
        char a9)
{
  _QWORD *v9; // r10
  unsigned __int64 v10; // r13
  __int64 v11; // rdi
  __int64 v12; // r14
  __int64 v13; // rax
  bool v14; // zf
  unsigned int v15; // ebx
  __int64 v16; // rcx
  unsigned __int64 v17; // r12
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  __int128 v20; // xmm6
  int ContainerIdFromRealRange; // r9d
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // edi
  int v26; // ebx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // r12
  __int64 v31; // r13
  __int64 v32; // rdi
  char v33; // si
  int v34; // r14d
  int v35; // r15d
  int v36; // edx
  int ActivityIdThread; // r8d
  int v38; // r9d
  __int64 v39; // rax
  int v40; // edx
  __int64 v41; // r8
  __int64 v42; // r8
  __int64 v43; // rax
  PLARGE_INTEGER Timeout; // [rsp+28h] [rbp-E0h]
  __int64 v46; // [rsp+30h] [rbp-D8h]
  __int64 v47; // [rsp+48h] [rbp-C0h]
  char v48; // [rsp+68h] [rbp-A0h]
  int v49; // [rsp+78h] [rbp-90h] BYREF
  int v50; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v51; // [rsp+80h] [rbp-88h]
  __int128 v52; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v53; // [rsp+98h] [rbp-70h] BYREF
  __int128 v54; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int64 v55; // [rsp+B8h] [rbp-50h]
  _QWORD v56[3]; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v57; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v58; // [rsp+E8h] [rbp-20h] BYREF
  _OWORD v59[6]; // [rsp+F8h] [rbp-10h] BYREF

  v9 = *(_QWORD **)(a1 + 8);
  v10 = a3;
  v11 = a2;
  v12 = a1;
  v56[1] = v9[7];
  v13 = v9[383];
  v52 = MsZeroRange;
  v50 = 0;
  v56[0] = 0;
  v14 = (*(_BYTE *)(v13 + 104) & 2) == 0;
  v54 = 0;
  v53 = 0;
  if ( v14 )
  {
    while ( (*(_BYTE *)(v9[383] + 104LL) & 4) == 0 )
    {
      v15 = a5;
      v47 = 0;
      LODWORD(Timeout) = a5;
      if ( !(unsigned __int8)CmsAllocationZones::GetZone(v9[377], &v50, v56, a6, Timeout, &v52) )
        return (unsigned int)-1073741697;
      v16 = -*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 8) + 3032LL) + 60LL);
      v17 = v16 & (v52 + *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 8) + 3032LL) + 60LL) - 1);
      v55 = v17;
      v18 = v16 & (v52 + *((_QWORD *)&v52 + 1) - v17);
      *(_QWORD *)&v52 = v17;
      *((_QWORD *)&v52 + 1) = v18;
      if ( v18 )
      {
        do
        {
          v19 = *(_QWORD *)(v12 + 8);
          LOBYTE(v49) = 0;
          CmsVolumeAnalyzer::FindFreeRangeInBitmap(*(_QWORD *)(v19 + 3064), &v52, v15, a6, &v49, &v54);
          if ( !(_BYTE)v49 )
            break;
          v20 = v54;
          v57 = v54;
          ContainerIdFromRealRange = CmsVolumeContainer::GetContainerIdFromRealRange(v12, v11, &v57, &v53);
          if ( ContainerIdFromRealRange < 0 )
            return (unsigned int)ContainerIdFromRealRange;
          if ( a7 )
          {
            ExAcquirePushLockSharedEx(a8 + 24, 0);
            v25 = *(_DWORD *)(a8 + 196);
            v26 = *(_DWORD *)(a8 + 200);
            ExReleasePushLockEx(a8 + 24, 0);
            if ( v25 >= v26 )
              KeWaitForSingleObject((PVOID)(a8 + 80), Executive, 0, 0, 0);
            if ( *(_BYTE *)(a8 + 176) )
            {
              KeWaitForSingleObject((PVOID)(a8 + 152), Executive, 0, 0, 0);
              return (unsigned int)-1073741823;
            }
            v15 = a5;
            v58 = v20;
            LOBYTE(v47) = a9;
            LODWORD(v46) = a5;
            v59[0] = *(_OWORD *)a4;
            v22 = CmsVolumeContainer::QueueContainerRotation(v28, v27, a8, v10, v53, v46, v59, &v58, v47);
          }
          else
          {
            v22 = CmsVolumeContainer::RotateContainers(v12, v11, v10, v53, v15, 0, 0);
          }
          v51 = v22;
          ContainerIdFromRealRange = v22;
          if ( v22 >= 0 && !a7 )
          {
            if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
            {
              v29 = *(_QWORD *)(*(_QWORD *)(v12 + 8) + 3064LL);
              v30 = a4[1];
              v31 = *a4;
              v32 = *(_QWORD *)(v29 + 3368);
              v33 = *(_BYTE *)(v29 + 3401);
              v34 = *(_DWORD *)(v29 + 3380);
              v35 = *(_DWORD *)(v29 + 3376);
              v48 = *(_BYTE *)(v29 + 3400);
              ActivityIdThread = IoGetActivityIdThread(v29, v23, v24, (unsigned int)v22);
              v15 = a5;
              v38 = 2;
              if ( a5 != 5 )
                v38 = 5;
              McTemplateK0qqiiiqqtit_EtwWriteTransfer(
                (unsigned int)MinstoreEventProvider_Context,
                v36,
                ActivityIdThread,
                v38,
                a5,
                v31,
                v30,
                v54,
                v35,
                v34,
                v33,
                v32,
                v48);
              ContainerIdFromRealRange = v51;
              v12 = a1;
              v17 = v55;
              v10 = a3;
            }
            v39 = *(_QWORD *)(v12 + 8);
            v40 = 1;
            if ( v15 == *(_DWORD *)(v39 + 3488) )
            {
              _InterlockedAdd((volatile signed __int32 *)(v39 + 772), 1u);
              _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v12 + 8) + 832LL), 1u);
              v41 = *(_QWORD *)(v12 + 8);
              if ( *(int *)(*(_QWORD *)(v41 + 3032) + 60LL) > 1 )
                v40 = *(_DWORD *)(*(_QWORD *)(v41 + 3032) + 60LL);
              _InterlockedExchangeAdd(
                (volatile signed __int32 *)(v41 + 828),
                100LL * *(_QWORD *)(*(_QWORD *)(v41 + 3064) + 3368LL) / (unsigned __int64)v40);
            }
            else
            {
              _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v39 + 3064) + 3680LL), 1u);
              _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v12 + 8) + 776LL), 1u);
              _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v12 + 8) + 840LL), 1u);
              v42 = *(_QWORD *)(v12 + 8);
              if ( *(int *)(*(_QWORD *)(v42 + 3032) + 60LL) > 1 )
                v40 = *(_DWORD *)(*(_QWORD *)(v42 + 3032) + 60LL);
              _InterlockedExchangeAdd(
                (volatile signed __int32 *)(v42 + 836),
                100LL * *(_QWORD *)(*(_QWORD *)(v42 + 3064) + 3368LL) / (unsigned __int64)v40);
            }
          }
          if ( ContainerIdFromRealRange != -1073740759 )
            return (unsigned int)ContainerIdFromRealRange;
          if ( v17 > (unsigned __int64)v54 )
            v43 = 0;
          else
            v43 = v54 - v17;
          v11 = a2;
          *((_QWORD *)&v52 + 1) = v43;
        }
        while ( v43 );
      }
      v9 = *(_QWORD **)(v12 + 8);
      ++v50;
      if ( (*(_BYTE *)(v9[383] + 104LL) & 2) != 0 )
        break;
    }
  }
  return (unsigned int)-1073741431;
}

```

## disassembly

```asm
0x1c00d830c  mov     rax, rsp
0x1c00d830f  mov     [rax+20h], r9
0x1c00d8313  mov     [rax+18h], r8
0x1c00d8317  mov     [rax+10h], rdx
0x1c00d831b  mov     [rax+8], rcx
0x1c00d831f  push    rbp
0x1c00d8320  push    rbx
0x1c00d8321  push    rsi
0x1c00d8322  push    rdi
0x1c00d8323  push    r12
0x1c00d8325  push    r13
0x1c00d8327  push    r14
0x1c00d8329  push    r15
0x1c00d832b  lea     rbp, [rax-58h]
0x1c00d832f  sub     rsp, 118h
0x1c00d8336  mov     r10, [rcx+8]
0x1c00d833a  xor     esi, esi
0x1c00d833c  movups  xmm0, cs:?MsZeroRange@@3U_RANGE@@B; _RANGE const MsZeroRange
0x1c00d8343  mov     r13, r8
0x1c00d8346  mov     rdi, rdx
0x1c00d8349  movaps  xmmword ptr [rax-58h], xmm6
0x1c00d834d  mov     r14, rcx
0x1c00d8350  mov     rax, [r10+38h]
0x1c00d8354  mov     [rbp+50h+var_90], rax
0x1c00d8358  mov     rax, [r10+0BF8h]
0x1c00d835f  movdqu  [rbp+50h+var_D0], xmm0
0x1c00d8364  mov     [rsp+150h+var_DC], esi
0x1c00d8368  xorps   xmm0, xmm0
0x1c00d836b  mov     [rbp+50h+var_98], rsi
0x1c00d836f  test    byte ptr [rax+68h], 2
0x1c00d8373  movups  [rbp+50h+var_B0], xmm0
0x1c00d8377  mov     [rbp+50h+var_C0], rsi
0x1c00d837b  jnz     loc_1C00D8749
0x1c00d8381  lea     r15d, [rsi+1]
0x1c00d8385  mov     rax, [r10+0BF8h]
0x1c00d838c  test    byte ptr [rax+68h], 4
0x1c00d8390  jnz     loc_1C00D8749
0x1c00d8396  mov     rcx, [r10+0BC8h]
0x1c00d839d  lea     rax, [rbp+50h+var_D0]
0x1c00d83a1  mov     ebx, [rbp+50h+arg_20]
0x1c00d83a7  lea     r8, [rbp+50h+var_98]
0x1c00d83ab  mov     r9d, [rbp+50h+arg_28]
0x1c00d83b2  lea     rdx, [rsp+150h+var_DC]
0x1c00d83b7  mov     [rsp+150h+var_110], rsi
0x1c00d83bc  mov     [rsp+150h+var_118], rsi
0x1c00d83c1  mov     [rsp+150h+var_128], rax
0x1c00d83c6  mov     dword ptr [rsp+150h+Timeout], ebx
0x1c00d83ca  call    ?GetZone@CmsAllocationZones@@QEAAEPEAKPEBU_RANGE@@W4_EmsAllocationType@@W4_EMS_STORAGE_TIER_MEDIA_TYPE@@PEAU2@PEAW43@PEAW44@PEAW4AllocationPriority@SmsAllocationZone@@@Z; CmsAllocationZones::GetZone(ulong *,_RANGE const *,_EmsAllocationType,_EMS_STORAGE_TIER_MEDIA_TYPE,_RANGE *,_EmsAllocationType *,_EMS_STORAGE_TIER_MEDIA_TYPE *,SmsAllocationZone::AllocationPriority *)
0x1c00d83cf  test    al, al
0x1c00d83d1  jz      loc_1C00D8797
0x1c00d83d7  mov     rax, [r14+8]
0x1c00d83db  mov     rcx, [rax+0BD8h]
0x1c00d83e2  mov     edx, [rcx+3Ch]
0x1c00d83e5  mov     eax, edx
0x1c00d83e7  neg     eax
0x1c00d83e9  movsxd  rcx, eax
0x1c00d83ec  lea     eax, [rdx-1]
0x1c00d83ef  movsxd  r12, eax
0x1c00d83f2  add     r12, qword ptr [rbp+50h+var_D0]
0x1c00d83f6  mov     rax, qword ptr [rbp+50h+var_D0+8]
0x1c00d83fa  and     r12, rcx
0x1c00d83fd  sub     rax, r12
0x1c00d8400  mov     [rbp+50h+var_A0], r12
0x1c00d8404  add     rax, qword ptr [rbp+50h+var_D0]
0x1c00d8408  and     rax, rcx
0x1c00d840b  mov     qword ptr [rbp+50h+var_D0], r12
0x1c00d840f  mov     qword ptr [rbp+50h+var_D0+8], rax
0x1c00d8413  jbe     loc_1C00D872F
0x1c00d8419  mov     rcx, [r14+8]
0x1c00d841d  lea     rax, [rbp+50h+var_B0]
0x1c00d8421  mov     r9d, [rbp+50h+arg_28]
0x1c00d8428  lea     rdx, [rbp+50h+var_D0]
0x1c00d842c  mov     [rsp+150h+var_128], rax
0x1c00d8431  mov     r8d, ebx
0x1c00d8434  lea     rax, [rsp+150h+var_E0]
0x1c00d8439  mov     byte ptr [rsp+150h+var_E0], sil
0x1c00d843e  mov     rcx, [rcx+0BF8h]
0x1c00d8445  mov     [rsp+150h+Timeout], rax
0x1c00d844a  call    ?FindFreeRangeInBitmap@CmsVolumeAnalyzer@@QEAAXPEBU_RANGE@@W4_EMS_STORAGE_TIER_MEDIA_TYPE@@W4_EmsAllocationType@@PEAEPEAU2@@Z; CmsVolumeAnalyzer::FindFreeRangeInBitmap(_RANGE const *,_EMS_STORAGE_TIER_MEDIA_TYPE,_EmsAllocationType,uchar *,_RANGE *)
0x1c00d844f  cmp     byte ptr [rsp+150h+var_E0], sil
0x1c00d8454  jz      loc_1C00D872F
0x1c00d845a  movaps  xmm6, [rbp+50h+var_B0]
0x1c00d845e  lea     r9, [rbp+50h+var_C0]
0x1c00d8462  lea     r8, [rbp+50h+var_80]
0x1c00d8466  movdqa  [rbp+50h+var_80], xmm6
0x1c00d846b  mov     rdx, rdi
0x1c00d846e  mov     rcx, r14
0x1c00d8471  call    ?GetContainerIdFromRealRange@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@PEA_K@Z; CmsVolumeContainer::GetContainerIdFromRealRange(CmsTransactionContext *,_RANGE,unsigned __int64 *)
0x1c00d8476  mov     r9d, eax
0x1c00d8479  test    eax, eax
0x1c00d847b  js      loc_1C00D874F
0x1c00d8481  cmp     [rbp+50h+arg_30], sil
0x1c00d8488  jnz     short loc_1C00D84AE
0x1c00d848a  mov     r9, [rbp+50h+var_C0]
0x1c00d848e  mov     r8, r13
0x1c00d8491  mov     dword ptr [rsp+150h+var_120], esi
0x1c00d8495  mov     rdx, rdi
0x1c00d8498  mov     byte ptr [rsp+150h+var_128], sil
0x1c00d849d  mov     rcx, r14
0x1c00d84a0  mov     dword ptr [rsp+150h+Timeout], ebx
0x1c00d84a4  call    ?RotateContainers@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_K1W4_EMS_STORAGE_TIER_MEDIA_TYPE@@EJ@Z; CmsVolumeContainer::RotateContainers(CmsTransactionContext *,unsigned __int64,unsigned __int64,_EMS_STORAGE_TIER_MEDIA_TYPE,uchar,long)
0x1c00d84a9  jmp     loc_1C00D8568
0x1c00d84ae  mov     r15, [rbp+50h+arg_38]
0x1c00d84b5  xor     edx, edx
0x1c00d84b7  lea     rcx, [r15+18h]
0x1c00d84bb  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c00d84c2  nop     dword ptr [rax+rax+00h]
0x1c00d84c7  mov     edi, [r15+0C4h]
0x1c00d84ce  lea     rcx, [r15+18h]
0x1c00d84d2  mov     ebx, [r15+0C8h]
0x1c00d84d9  xor     edx, edx
0x1c00d84db  call    cs:__imp_ExReleasePushLockEx
0x1c00d84e2  nop     dword ptr [rax+rax+00h]
0x1c00d84e7  xor     esi, esi
0x1c00d84e9  cmp     edi, ebx
0x1c00d84eb  jl      short loc_1C00D850A
0x1c00d84ed  lea     rcx, [r15+50h]; Object
0x1c00d84f1  mov     [rsp+150h+Timeout], rsi; Timeout
0x1c00d84f6  xor     r9d, r9d; Alertable
0x1c00d84f9  xor     r8d, r8d; WaitMode
0x1c00d84fc  xor     edx, edx; WaitReason
0x1c00d84fe  call    cs:__imp_KeWaitForSingleObject
0x1c00d8505  nop     dword ptr [rax+rax+00h]
0x1c00d850a  cmp     [r15+0B0h], sil
0x1c00d8511  jnz     loc_1C00D876F
0x1c00d8517  mov     rax, [rbp+50h+arg_18]
0x1c00d851b  mov     r9, r13
0x1c00d851e  mov     ebx, [rbp+50h+arg_20]
0x1c00d8524  mov     r8, r15
0x1c00d8527  movdqa  [rbp+50h+var_70], xmm6
0x1c00d852c  movups  xmm0, xmmword ptr [rax]
0x1c00d852f  mov     al, [rbp+50h+arg_40]
0x1c00d8535  mov     byte ptr [rsp+150h+var_110], al
0x1c00d8539  lea     rax, [rbp+50h+var_70]
0x1c00d853d  mov     [rsp+150h+var_118], rax
0x1c00d8542  lea     rax, [rbp+50h+var_60]
0x1c00d8546  mov     [rsp+150h+var_120], rax
0x1c00d854b  mov     rax, [rbp+50h+var_C0]
0x1c00d854f  mov     dword ptr [rsp+150h+var_128], ebx
0x1c00d8553  mov     [rsp+150h+Timeout], rax
0x1c00d8558  movdqu  [rbp+50h+var_60], xmm0
0x1c00d855d  call    ?QueueContainerRotation@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAVCmsContainerRotationQueue@@_K2W4_EMS_STORAGE_TIER_MEDIA_TYPE@@U_RANGE@@4E@Z; CmsVolumeContainer::QueueContainerRotation(CmsTransactionContext *,CmsContainerRotationQueue *,unsigned __int64,unsigned __int64,_EMS_STORAGE_TIER_MEDIA_TYPE,_RANGE,_RANGE,uchar)
0x1c00d8562  mov     r15d, 1
0x1c00d8568  mov     [rsp+150h+var_D8], eax
0x1c00d856c  mov     r9d, eax
0x1c00d856f  test    eax, eax
0x1c00d8571  js      loc_1C00D8704
0x1c00d8577  cmp     [rbp+50h+arg_30], sil
0x1c00d857e  jnz     loc_1C00D8704
0x1c00d8584  cmp     cs:dword_1C012D0B4, r15d
0x1c00d858b  jnz     loc_1C00D8650
0x1c00d8591  test    cs:Microsoft_Windows_MinstoreEnableBits, r15b
0x1c00d8598  jz      loc_1C00D8650
0x1c00d859e  mov     rax, [r14+8]
0x1c00d85a2  mov     rcx, [rax+0BF8h]
0x1c00d85a9  mov     rax, [rbp+50h+arg_18]
0x1c00d85ad  movzx   ebx, byte ptr [rcx+0D48h]
0x1c00d85b4  mov     r12, [rax+8]
0x1c00d85b8  mov     r13, [rax]
0x1c00d85bb  mov     rdi, [rcx+0D28h]
0x1c00d85c2  movzx   esi, byte ptr [rcx+0D49h]
0x1c00d85c9  mov     r14d, [rcx+0D34h]
0x1c00d85d0  mov     r15d, [rcx+0D30h]
0x1c00d85d7  call    cs:__imp_IoGetActivityIdThread
0x1c00d85de  nop     dword ptr [rax+rax+00h]
0x1c00d85e3  mov     [rsp+60h], ebx
0x1c00d85e7  mov     ecx, 5
0x1c00d85ec  cmp     [rbp+50h+arg_20], ecx
0x1c00d85f2  mov     r8, rax
0x1c00d85f5  mov     ebx, [rbp+50h+arg_20]
0x1c00d85fb  mov     qword ptr [rsp+150h+var_F8], rdi
0x1c00d8600  mov     dword ptr [rsp+150h+var_100], esi
0x1c00d8604  lea     r9d, [rcx-3]
0x1c00d8608  mov     [rsp+150h+var_108], r14d
0x1c00d860d  cmovnz  r9d, ecx
0x1c00d8611  mov     rcx, qword ptr [rbp+50h+var_B0]
0x1c00d8615  mov     dword ptr [rsp+150h+var_110], r15d
0x1c00d861a  mov     [rsp+150h+var_118], rcx
0x1c00d861f  lea     rcx, MinstoreEventProvider_Context
0x1c00d8626  mov     [rsp+150h+var_120], r12
0x1c00d862b  mov     [rsp+150h+var_128], r13
0x1c00d8630  mov     dword ptr [rsp+150h+Timeout], ebx
0x1c00d8634  call    McTemplateK0qqiiiqqtit_EtwWriteTransfer
0x1c00d8639  mov     r9d, [rsp+150h+var_D8]
0x1c00d863e  xor     esi, esi
0x1c00d8640  mov     r14, [rbp+50h+arg_0]
0x1c00d8644  mov     r12, [rbp+50h+var_A0]
0x1c00d8648  mov     r13, [rbp+50h+arg_10]
0x1c00d864c  lea     r15d, [rsi+1]
0x1c00d8650  mov     rax, [r14+8]
0x1c00d8654  mov     edx, r15d
0x1c00d8657  cmp     ebx, [rax+0DA0h]
0x1c00d865d  jnz     short loc_1C00D86A9
0x1c00d865f  lock add [rax+304h], r15d
0x1c00d8667  mov     rax, [r14+8]
0x1c00d866b  lock add [rax+340h], r15d
0x1c00d8673  mov     r8, [r14+8]
0x1c00d8677  mov     rax, [r8+0BD8h]
0x1c00d867e  mov     ecx, [rax+3Ch]
0x1c00d8681  cmp     ecx, r15d
0x1c00d8684  mov     rax, [r8+0BF8h]
0x1c00d868b  cmovg   edx, ecx
0x1c00d868e  movsxd  rcx, edx
0x1c00d8691  xor     edx, edx
0x1c00d8693  imul    rax, [rax+0D28h], 64h ; 'd'
0x1c00d869b  div     rcx
0x1c00d869e  lock xadd [r8+33Ch], eax
0x1c00d86a7  jmp     short loc_1C00D8704
0x1c00d86a9  mov     rax, [rax+0BF8h]
0x1c00d86b0  lock add [rax+0E60h], r15d
0x1c00d86b8  mov     rax, [r14+8]
0x1c00d86bc  lock add [rax+308h], r15d
0x1c00d86c4  mov     rax, [r14+8]
0x1c00d86c8  lock add [rax+348h], r15d
0x1c00d86d0  mov     r8, [r14+8]
0x1c00d86d4  mov     rax, [r8+0BD8h]
0x1c00d86db  mov     ecx, [rax+3Ch]
0x1c00d86de  cmp     ecx, r15d
0x1c00d86e1  mov     rax, [r8+0BF8h]
0x1c00d86e8  cmovg   edx, ecx
0x1c00d86eb  movsxd  rcx, edx
0x1c00d86ee  xor     edx, edx
0x1c00d86f0  imul    rax, [rax+0D28h], 64h ; 'd'
0x1c00d86f8  div     rcx
0x1c00d86fb  lock xadd [r8+344h], eax
0x1c00d8704  cmp     r9d, 0C0000429h
0x1c00d870b  jnz     short loc_1C00D874F
0x1c00d870d  mov     rax, qword ptr [rbp+50h+var_B0]
0x1c00d8711  cmp     r12, rax
0x1c00d8714  ja      short loc_1C00D871B
0x1c00d8716  sub     rax, r12
0x1c00d8719  jmp     short loc_1C00D871E
0x1c00d871b  mov     rax, rsi
0x1c00d871e  mov     rdi, [rbp+50h+arg_8]
0x1c00d8722  mov     qword ptr [rbp+50h+var_D0+8], rax
0x1c00d8726  test    rax, rax
0x1c00d8729  jnz     loc_1C00D8419
0x1c00d872f  mov     r10, [r14+8]
0x1c00d8733  add     [rsp+150h+var_DC], r15d
0x1c00d8738  mov     rax, [r10+0BF8h]
0x1c00d873f  test    byte ptr [rax+68h], 2
0x1c00d8743  jz      loc_1C00D8385
0x1c00d8749  mov     r9d, 0C0000189h
0x1c00d874f  movaps  xmm6, [rsp+150h+var_60+10h]
0x1c00d8757  mov     eax, r9d
0x1c00d875a  add     rsp, 118h
0x1c00d8761  pop     r15
0x1c00d8763  pop     r14
0x1c00d8765  pop     r13
0x1c00d8767  pop     r12
0x1c00d8769  pop     rdi
0x1c00d876a  pop     rsi
0x1c00d876b  pop     rbx
0x1c00d876c  pop     rbp
0x1c00d876d  retn
0x1c00d876f  lea     rcx, [r15+98h]; Object
0x1c00d8776  mov     [rsp+150h+Timeout], rsi; Timeout
0x1c00d877b  xor     r9d, r9d; Alertable
0x1c00d877e  xor     r8d, r8d; WaitMode
0x1c00d8781  xor     edx, edx; WaitReason
0x1c00d8783  call    cs:__imp_KeWaitForSingleObject
0x1c00d878a  nop     dword ptr [rax+rax+00h]
0x1c00d878f  mov     r9d, 0C0000001h
0x1c00d8795  jmp     short loc_1C00D874F
0x1c00d8797  mov     r9d, 0C000007Fh
0x1c00d879d  jmp     short loc_1C00D874F
```
