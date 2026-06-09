# FveAADKeyDeleteRequest::DeleteAsyncRequest(void * *,ulong)

- ea: `0x1800f2b50`
- end: `0x1800f31f7`
- name: `?DeleteAsyncRequest@FveAADKeyDeleteRequest@@SAJPEAPEAXK@Z`
- size: `1703`
- prototype: `__int64 __fastcall(void **, unsigned int)`
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x180004968`
- `0x180008d70`
- `0x1800090c0`
- `0x180019128`
- `0x180038730`
- `0x180044054`
- `0x180045ff0`
- `0x1800485f0`
- `0x18004a264`
- `0x18004ad74`
- `0x1800ee890`
- `0x1800eebc4`
- `0x1800eef10`
- `0x1800f12c8`
- `0x1800f144c`
- `0x1800f2b50`
- `0x1800f3328`
- `0x1800f3400`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f2fa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f2fc9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f2ffa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f2fa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f2fc9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f2ffa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f2f8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f2fb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f2fe6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f2f8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f2fb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f2fe6`
- `FVESKYBACKUP!FveDeleteRecoveryPasswordsFromCloudDomain` at `0x1800f2d83`
- `FVESKYBACKUP!FveDeleteRecoveryPasswordsFromCloudDomain` at `0x1800f2d83`

## string_xrefs

- `0x1800f2dd6`: `FveDeleteRPFromCloudDomain`

## pseudocode

```c
__int64 __fastcall FveAADKeyDeleteRequest::DeleteAsyncRequest(void **a1, unsigned int a2)
{
  unsigned int v2; // esi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  struct _LIST_ENTRY *v7; // r15
  int v8; // r14d
  int v9; // r12d
  const wchar_t *v10; // r13
  PVOID v11; // rcx
  int OSVolume; // ebx
  int AsyncRequestList; // ebx
  int AADDeletionRequests; // eax
  PVOID *v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rdi
  unsigned int v18; // eax
  unsigned int v19; // esi
  int v20; // eax
  PVOID *v21; // r11
  int v22; // eax
  __int64 v23; // r11
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  HANDLE ProcessHeap; // rax
  void *v28; // rdi
  HANDLE v29; // rax
  struct _FVE_AAD_DELETE_INFO_V2 *v30; // rdi
  HANDLE v31; // rax
  unsigned int v33; // r14d
  PVOID *v34; // r10
  int v35; // r15d
  char *v36; // r9
  int v37; // eax
  unsigned int PersistentRequestDelayTimer; // eax
  unsigned int v39; // edi
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v41; // [rsp+64h] [rbp-9Ch] BYREF
  int v42; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v43; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v44; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+74h] [rbp-8Ch] BYREF
  struct _LIST_ENTRY *v46; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v47; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v48[24]; // [rsp+90h] [rbp-70h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-58h] BYREF
  struct _FVE_AAD_DELETE_INFO_V2 *v50; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v51; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v52; // [rsp+BCh] [rbp-44h] BYREF
  int v53; // [rsp+C0h] [rbp-40h] BYREF
  int v54[3]; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned __int16 v55[264]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = a2;
  v41 = a2;
  v53 = 0;
  memset_0(v55, 0, 0x208u);
  v7 = 0;
  v46 = 0;
  v50 = 0;
  v8 = 0;
  lpMem = 0;
  v9 = 0;
  v51 = 0;
  v40 = 0;
  v52 = 0;
  v44 = 0;
  v54[0] = 0;
  v42 = 0;
  v45 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids);
  v10 = L"NgscbGetOSVolume";
  OSVolume = NgscbGetOSVolume(v55, v4, v5, v6);
  if ( !OSVolume )
    goto LABEL_9;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
      (unsigned int)OSVolume);
  if ( OSVolume >= 0 )
  {
LABEL_9:
    v51 = v2;
    AsyncRequestList = GetAsyncRequestList(v11, &v46);
    if ( AsyncRequestList < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
          (unsigned int)AsyncRequestList);
      v10 = L"GetAsyncRequestList";
      v42 = AsyncRequestList;
    }
    v7 = v46;
    AADDeletionRequests = FveAADKeyDeleteRequest::GetAADDeletionRequests(
                            a1,
                            v2,
                            v46,
                            &v50,
                            (struct _FVE_AAD_DELETE_REQUEST **)&lpMem,
                            &v51);
    OSVolume = AADDeletionRequests;
    if ( AADDeletionRequests < 0 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          77,
          WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
          (unsigned int)AADDeletionRequests);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      v10 = L"GetAADDeletionRequests";
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x40) != 0 )
        WPP_SF_d(v15[2], 78, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, (unsigned int)OSVolume);
      goto LABEL_42;
    }
    v16 = v51;
    v17 = 0;
    v43 = 0;
    if ( v51 )
    {
      while ( 1 )
      {
        v18 = v16 - v17;
        v19 = 16;
        if ( v18 < 0x10 )
          v19 = v18;
        v20 = FveDeleteRecoveryPasswordsFromCloudDomain(
                v55,
                (struct _FVE_AAD_DELETE_REQUEST *)((char *)lpMem + 20 * v17),
                v19,
                0,
                &v53,
                v54,
                &v52);
        OSVolume = v20;
        if ( v20 >= 0 )
          break;
        v21 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
            (unsigned int)v20);
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
        v10 = L"FveDeleteRPFromCloudDomain";
        v9 = OSVolume;
        v45 = OSVolume;
        if ( v53 )
        {
          if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
          {
            WPP_SF_(v21[2], 80, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids);
            v21 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v54[0] )
          {
            if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
              WPP_SF_D(v21[2], 81, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, v52);
            v22 = ULongLongToULong(1000LL * v52, &v44);
            OSVolume = v22;
            if ( v22 >= 0 )
            {
              PersistentRequestDelayTimer = FveGetPersistentRequestDelayTimer();
              v39 = PersistentRequestDelayTimer;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_D(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  83,
                  WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
                  PersistentRequestDelayTimer);
              if ( v39 < v44 )
                FveSetPersistentRequestDelayTimer(v44);
            }
            else
            {
              if ( (PVOID *)v23 != &WPP_GLOBAL_Control && (*(_BYTE *)(v23 + 28) & 2) != 0 )
                WPP_SF_d(*(_QWORD *)(v23 + 16), 82, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, (unsigned int)v22);
              v10 = L"ULongMult";
            }
          }
          v8 = v40;
          v2 = v41;
          goto LABEL_42;
        }
LABEL_75:
        v16 = v51;
        v17 = (unsigned int)(v17 + 16);
        v43 = v17;
        if ( (unsigned int)v17 >= v51 )
        {
          v2 = v41;
          v8 = v40;
          v9 = v45;
          goto LABEL_77;
        }
      }
      v33 = v17;
      if ( (unsigned int)v17 >= v19 + (unsigned int)v17 )
        goto LABEL_75;
      v34 = (PVOID *)WPP_GLOBAL_Control;
      v35 = v40;
      while ( 1 )
      {
        v36 = (char *)lpMem + 20 * v33;
        if ( v36[16] )
        {
          if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 2) != 0 )
            WPP_SF__guid_(v34[2], 84, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, v36);
          v47 = *(struct _GUID *)((char *)v50 + 576 * v33 + 540);
          v37 = FveDeletePersistentRequest(v55, 2u, &v47);
          if ( v37 >= 0 )
          {
            ++v35;
          }
          else
          {
            v34 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_73;
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              85,
              WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
              (unsigned int)v37);
          }
        }
        else
        {
          if ( v34 == &WPP_GLOBAL_Control || (*((_BYTE *)v34 + 28) & 2) == 0 )
            goto LABEL_73;
          WPP_SF__guid_(v34[2], 86, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, v36);
        }
        v34 = (PVOID *)WPP_GLOBAL_Control;
LABEL_73:
        if ( ++v33 >= v19 + (unsigned int)v17 )
        {
          LODWORD(v17) = v43;
          v40 = v35;
          v7 = v46;
          goto LABEL_75;
        }
      }
    }
LABEL_77:
    if ( v8 == v2 )
      FveAADKeyDeleteRequest::FveDeleteDecryptedVolumePersistentRequests(v55, v7);
  }
LABEL_42:
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v48,
    &g_hBitLockerKeyRollProvider,
    &g_bitLockerKeyRollProviderInitLock,
    &g_bitLockerKeyRollProviderRefCount);
  if ( (OSVolume < 0 || v9 < 0 || v42 < 0)
    && (unsigned int)dword_180172588 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180172588, 0x400000000000LL) )
  {
    v44 = v51;
    v46 = (struct _LIST_ENTRY *)0x1000000;
    *(_QWORD *)&v47.Data1 = v10;
    v45 = v8;
    v43 = v2;
    v42 = v25;
    v41 = v9;
    v40 = OSVolume;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v24,
      (int)&byte_18016050F,
      v25,
      v26,
      (__int64)&v40,
      (__int64)&v41,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v44,
      (__int64)&v45,
      (const size_t **)&v47,
      (__int64)&v46);
  }
  if ( v7 )
  {
    FveClearAsyncRequestList(v7);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v28 = lpMem;
  if ( lpMem )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
    lpMem = 0;
  }
  v30 = v50;
  if ( v50 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v30);
    v50 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
      (unsigned int)OSVolume);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v48);
  return (unsigned int)OSVolume;
}

```

## disassembly

```asm
0x1800f2b50  mov     [rsp-8+arg_10], rbx
0x1800f2b55  push    rbp
0x1800f2b56  push    rsi
0x1800f2b57  push    rdi
0x1800f2b58  push    r12
0x1800f2b5a  push    r13
0x1800f2b5c  push    r14
0x1800f2b5e  push    r15
0x1800f2b60  lea     rbp, [rsp-1F0h]
0x1800f2b68  sub     rsp, 2F0h
0x1800f2b6f  mov     rax, cs:__security_cookie
0x1800f2b76  xor     rax, rsp
0x1800f2b79  mov     [rbp+220h+var_40], rax
0x1800f2b80  mov     esi, edx
0x1800f2b82  mov     [rsp+320h+var_2BC], edx
0x1800f2b86  mov     rdi, rcx
0x1800f2b89  xor     ebx, ebx
0x1800f2b8b  xor     edx, edx; Val
0x1800f2b8d  mov     [rbp+220h+var_260], ebx
0x1800f2b90  lea     rcx, [rbp+220h+var_250]; void *
0x1800f2b94  mov     r8d, 208h; Size
0x1800f2b9a  call    memset_0
0x1800f2b9f  mov     r15d, ebx
0x1800f2ba2  mov     [rsp+320h+var_2A8], rbx
0x1800f2ba7  mov     [rbp+220h+var_270], rbx
0x1800f2bab  mov     r14d, ebx
0x1800f2bae  mov     [rbp+220h+lpMem], rbx
0x1800f2bb2  mov     r12d, ebx
0x1800f2bb5  mov     [rbp+220h+var_268], ebx
0x1800f2bb8  mov     [rsp+320h+var_2C0], ebx
0x1800f2bbc  mov     [rbp+220h+var_264], ebx
0x1800f2bbf  mov     [rsp+320h+var_2B0], ebx
0x1800f2bc3  mov     [rbp+220h+var_25C], ebx
0x1800f2bc6  mov     [rsp+320h+var_2B8], ebx
0x1800f2bca  mov     [rsp+320h+var_2AC], ebx
0x1800f2bce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f2bd5  lea     rax, WPP_GLOBAL_Control
0x1800f2bdc  cmp     rcx, rax
0x1800f2bdf  jz      short loc_1800F2BFA
0x1800f2be1  test    byte ptr [rcx+1Ch], 20h
0x1800f2be5  jz      short loc_1800F2BFA
0x1800f2be7  mov     rcx, [rcx+10h]
0x1800f2beb  lea     edx, [rbx+4Ah]
0x1800f2bee  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800f2bf5  call    WPP_SF_
0x1800f2bfa  lea     rcx, [rbp+220h+var_250]
0x1800f2bfe  lea     r13, aNgscbgetosvolu; "NgscbGetOSVolume"
0x1800f2c05  call    NgscbGetOSVolume
0x1800f2c0a  mov     ebx, eax
0x1800f2c0c  test    eax, eax
0x1800f2c0e  jz      short loc_1800F2C49
0x1800f2c10  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f2c17  lea     rax, WPP_GLOBAL_Control
0x1800f2c1e  cmp     rcx, rax
0x1800f2c21  jz      short loc_1800F2C41
0x1800f2c23  test    byte ptr [rcx+1Ch], 40h
0x1800f2c27  jz      short loc_1800F2C41
0x1800f2c29  mov     rcx, [rcx+10h]
0x1800f2c2d  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800f2c34  mov     edx, 4Bh ; 'K'
0x1800f2c39  mov     r9d, ebx
0x1800f2c3c  call    WPP_SF_d
0x1800f2c41  test    ebx, ebx
0x1800f2c43  js      loc_1800F2E97
0x1800f2c49  lea     rdx, [rsp+320h+var_2A8]
0x1800f2c4e  mov     [rbp+220h+var_268], esi
0x1800f2c51  call    ?GetAsyncRequestList@@YAJW4_FVE_REQUEST_TYPE@@PEAPEAU_LIST_ENTRY@@@Z; GetAsyncRequestList(_FVE_REQUEST_TYPE,_LIST_ENTRY * *)
0x1800f2c56  mov     ebx, eax
0x1800f2c58  test    eax, eax
0x1800f2c5a  jns     short loc_1800F2C98
0x1800f2c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f2c63  lea     rax, WPP_GLOBAL_Control
0x1800f2c6a  cmp     rcx, rax
0x1800f2c6d  jz      short loc_1800F2C8D
0x1800f2c6f  test    byte ptr [rcx+1Ch], 2
0x1800f2c73  jz      short loc_1800F2C8D
0x1800f2c75  mov     rcx, [rcx+10h]
0x1800f2c79  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800f2c80  mov     edx, 4Ch ; 'L'
0x1800f2c85  mov     r9d, ebx
0x1800f2c88  call    WPP_SF_d
0x1800f2c8d  lea     r13, aGetasyncreques; "GetAsyncRequestList"
0x1800f2c94  mov     [rsp+320h+var_2B8], ebx
0x1800f2c98  mov     r15, [rsp+320h+var_2A8]
0x1800f2c9d  lea     rax, [rbp+220h+var_268]
0x1800f2ca1  mov     [rsp+320h+var_2F8], rax; unsigned int *
0x1800f2ca6  lea     r9, [rbp+220h+var_270]; struct _FVE_AAD_DELETE_INFO_V2 **
0x1800f2caa  lea     rax, [rbp+220h+lpMem]
0x1800f2cae  mov     r8, r15; struct _LIST_ENTRY *
0x1800f2cb1  mov     edx, esi; unsigned int
0x1800f2cb3  mov     [rsp+320h+var_300], rax; struct _FVE_AAD_DELETE_REQUEST **
0x1800f2cb8  mov     rcx, rdi; void **
0x1800f2cbb  call    ?GetAADDeletionRequests@FveAADKeyDeleteRequest@@SAJPEAPEAXKPEAU_LIST_ENTRY@@PEAPEAU_FVE_AAD_DELETE_INFO_V2@@PEAPEAU_FVE_AAD_DELETE_REQUEST@@PEAK@Z; FveAADKeyDeleteRequest::GetAADDeletionRequests(void * *,ulong,_LIST_ENTRY *,_FVE_AAD_DELETE_INFO_V2 * *,_FVE_AAD_DELETE_REQUEST * *,ulong *)
0x1800f2cc0  mov     ebx, eax
0x1800f2cc2  test    eax, eax
0x1800f2cc4  jns     short loc_1800F2D35
0x1800f2cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f2ccd  lea     rdi, WPP_GLOBAL_Control
0x1800f2cd4  cmp     rcx, rdi
0x1800f2cd7  jz      short loc_1800F2CFE
0x1800f2cd9  test    byte ptr [rcx+1Ch], 2
0x1800f2cdd  jz      short loc_1800F2CFE
0x1800f2cdf  mov     rcx, [rcx+10h]
0x1800f2ce3  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800f2cea  mov     edx, 4Dh ; 'M'
0x1800f2cef  mov     r9d, eax
0x1800f2cf2  call    WPP_SF_d
0x1800f2cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f2cfe  lea     r13, aGetaaddeletion; "GetAADDeletionRequests"
0x1800f2d05  cmp     rcx, rdi
0x1800f2d08  jz      loc_1800F2E97
0x1800f2d0e  test    byte ptr [rcx+1Ch], 40h
0x1800f2d12  jz      loc_1800F2E97
0x1800f2d18  mov     rcx, [rcx+10h]
0x1800f2d1c  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800f2d23  mov     edx, 4Eh ; 'N'
0x1800f2d28  mov     r9d, ebx
0x1800f2d2b  call    WPP_SF_d
0x1800f2d30  jmp     loc_1800F2E97
0x1800f2d35  mov     eax, [rbp+220h+var_268]
0x1800f2d38  xor     edi, edi
0x1800f2d3a  mov     [rsp+320h+var_2B4], edi
0x1800f2d3e  test    eax, eax
0x1800f2d40  jz      loc_1800F3196
0x1800f2d46  sub     eax, edi
0x1800f2d48  lea     rcx, [rdi+rdi*4]
0x1800f2d4c  mov     esi, 10h
0x1800f2d51  cmp     eax, esi
0x1800f2d53  cmovb   esi, eax
0x1800f2d56  mov     rax, [rbp+220h+lpMem]
0x1800f2d5a  xor     r9d, r9d
0x1800f2d5d  mov     r8d, esi
0x1800f2d60  lea     rdx, [rax+rcx*4]
0x1800f2d64  lea     rax, [rbp+220h+var_264]
0x1800f2d68  mov     [rsp+320h+var_2F0], rax
0x1800f2d6d  lea     rcx, [rbp+220h+var_250]
0x1800f2d71  lea     rax, [rbp+220h+var_25C]
0x1800f2d75  mov     [rsp+320h+var_2F8], rax
0x1800f2d7a  lea     rax, [rbp+220h+var_260]
0x1800f2d7e  mov     [rsp+320h+var_300], rax
0x1800f2d83  call    cs:__imp_?FveDeleteRecoveryPasswordsFromCloudDomain@@YAJPEBGPEAU_FVE_AAD_DELETE_REQUEST@@KHPEAH2PEAK@Z; FveDeleteRecoveryPasswordsFromCloudDomain(ushort const *,_FVE_AAD_DELETE_REQUEST *,ulong,int,int *,int *,ulong *)
0x1800f2d8a  nop     dword ptr [rax+rax+00h]
0x1800f2d8f  mov     ebx, eax
0x1800f2d91  test    eax, eax
0x1800f2d93  jns     loc_1800F3075
0x1800f2d99  mov     r11, cs:WPP_GLOBAL_Control
0x1800f2da0  lea     rsi, WPP_GLOBAL_Control
0x1800f2da7  cmp     r11, rsi
0x1800f2daa  jz      short loc_1800F2DD2
0x1800f2dac  test    byte ptr [r11+1Ch], 2
0x1800f2db1  jz      short loc_1800F2DD2
0x1800f2db3  mov     rcx, [r11+10h]
0x1800f2db7  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800f2dbe  mov     edx, 4Fh ; 'O'
0x1800f2dc3  mov     r9d, eax
0x1800f2dc6  call    WPP_SF_d
0x1800f2dcb  mov     r11, cs:WPP_GLOBAL_Control
0x1800f2dd2  cmp     [rbp+220h+var_260], 0
0x1800f2dd6  lea     r13, aFvedeleterpfro; "FveDeleteRPFromCloudDomain"
0x1800f2ddd  mov     r12d, ebx
0x1800f2de0  mov     [rsp+320h+var_2AC], ebx
0x1800f2de4  jz      loc_1800F3176
0x1800f2dea  mov     r14b, 8
0x1800f2ded  cmp     r11, rsi
0x1800f2df0  jz      short loc_1800F2E14
0x1800f2df2  test    [r11+1Ch], r14b
0x1800f2df6  jz      short loc_1800F2E14
0x1800f2df8  mov     rcx, [r11+10h]
0x1800f2dfc  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800f2e03  mov     edx, 50h ; 'P'
0x1800f2e08  call    WPP_SF_
0x1800f2e0d  mov     r11, cs:WPP_GLOBAL_Control
0x1800f2e14  cmp     [rbp+220h+var_25C], 0
0x1800f2e18  jz      short loc_1800F2E8E
0x1800f2e1a  cmp     r11, rsi
0x1800f2e1d  jz      short loc_1800F2E45
0x1800f2e1f  test    [r11+1Ch], r14b
0x1800f2e23  jz      short loc_1800F2E45
0x1800f2e25  mov     r9d, [rbp+220h+var_264]
0x1800f2e29  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800f2e30  mov     rcx, [r11+10h]
0x1800f2e34  mov     edx, 51h ; 'Q'
0x1800f2e39  call    WPP_SF_D
0x1800f2e3e  mov     r11, cs:WPP_GLOBAL_Control
0x1800f2e45  mov     eax, [rbp+220h+var_264]
0x1800f2e48  lea     rdx, [rsp+320h+var_2B0]; unsigned int *
0x1800f2e4d  imul    rcx, rax, 3E8h; unsigned __int64
0x1800f2e54  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800f2e59  mov     ebx, eax
0x1800f2e5b  test    eax, eax
0x1800f2e5d  jns     loc_1800F31B0
0x1800f2e63  cmp     r11, rsi
0x1800f2e66  jz      short loc_1800F2E87
0x1800f2e68  test    byte ptr [r11+1Ch], 2
0x1800f2e6d  jz      short loc_1800F2E87
0x1800f2e6f  mov     rcx, [r11+10h]
0x1800f2e73  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800f2e7a  mov     edx, 52h ; 'R'
0x1800f2e7f  mov     r9d, eax
0x1800f2e82  call    WPP_SF_d
0x1800f2e87  lea     r13, aUlongmult; "ULongMult"
0x1800f2e8e  mov     r14d, [rsp+320h+var_2C0]
0x1800f2e93  mov     esi, [rsp+320h+var_2BC]
0x1800f2e97  lea     r9, ?g_bitLockerKeyRollProviderRefCount@@3JC; volatile int *
0x1800f2e9e  lea     r8, ?g_bitLockerKeyRollProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x1800f2ea5  lea     rdx, g_hBitLockerKeyRollProvider; struct _tlgProvider_t **
0x1800f2eac  lea     rcx, [rbp+220h+var_290]; this
0x1800f2eb0  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z; TelemetryProviderRegistrar::TelemetryProviderRegistrar(_tlgProvider_t const * const *,_RTL_SRWLOCK *,long volatile *)
0x1800f2eb5  mov     r8d, [rsp+320h+var_2B8]
0x1800f2eba  test    ebx, ebx
0x1800f2ebc  js      short loc_1800F2ECC
0x1800f2ebe  test    r12d, r12d
0x1800f2ec1  js      short loc_1800F2ECC
0x1800f2ec3  test    r8d, r8d
0x1800f2ec6  jns     loc_1800F2F7F
0x1800f2ecc  mov     eax, cs:dword_180172588
0x1800f2ed2  cmp     eax, 5
0x1800f2ed5  jbe     loc_1800F2F7F
0x1800f2edb  mov     rdx, 400000000000h
0x1800f2ee5  lea     rcx, dword_180172588
0x1800f2eec  call    _tlgKeywordOn
0x1800f2ef1  test    al, al
0x1800f2ef3  jz      loc_1800F2F7F
0x1800f2ef9  mov     eax, [rbp+220h+var_268]
0x1800f2efc  lea     rdx, byte_18016050F
0x1800f2f03  mov     [rsp+320h+var_2B0], eax
0x1800f2f07  lea     rax, [rsp+320h+var_2A8]
0x1800f2f0c  mov     [rsp+320h+var_2C8], rax
0x1800f2f11  lea     rax, [rbp+220h+var_2A0]
0x1800f2f15  mov     [rsp+320h+var_2D0], rax
0x1800f2f1a  lea     rax, [rsp+320h+var_2AC]
0x1800f2f1f  mov     [rsp+320h+var_2D8], rax
0x1800f2f24  lea     rax, [rsp+320h+var_2B0]
0x1800f2f29  mov     [rsp+320h+var_2E0], rax
0x1800f2f2e  lea     rax, [rsp+320h+var_2B4]
0x1800f2f33  mov     [rsp+320h+var_2E8], rax
0x1800f2f38  lea     rax, [rsp+320h+var_2B8]
0x1800f2f3d  mov     [rsp+320h+var_2F0], rax
0x1800f2f42  lea     rax, [rsp+320h+var_2BC]
0x1800f2f47  mov     [rsp+320h+var_2F8], rax
0x1800f2f4c  lea     rax, [rsp+320h+var_2C0]
0x1800f2f51  mov     [rsp+320h+var_300], rax
0x1800f2f56  mov     [rsp+320h+var_2A8], 1000000h
0x1800f2f5f  mov     qword ptr [rbp+220h+var_2A0], r13
0x1800f2f63  mov     [rsp+320h+var_2AC], r14d
0x1800f2f68  mov     [rsp+320h+var_2B4], esi
0x1800f2f6c  mov     [rsp+320h+var_2B8], r8d
0x1800f2f71  mov     [rsp+320h+var_2BC], r12d
0x1800f2f76  mov     [rsp+320h+var_2C0], ebx
0x1800f2f7a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33333AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800f2f7f  test    r15, r15
0x1800f2f82  jz      short loc_1800F2FAC
0x1800f2f84  mov     rcx, r15; struct _LIST_ENTRY *
0x1800f2f87  call    ?FveClearAsyncRequestList@@YAXPEAU_LIST_ENTRY@@@Z; FveClearAsyncRequestList(_LIST_ENTRY *)
0x1800f2f8c  call    cs:__imp_GetProcessHeap
0x1800f2f93  nop     dword ptr [rax+rax+00h]
0x1800f2f98  mov     r8, r15; lpMem
0x1800f2f9b  xor     edx, edx; dwFlags
0x1800f2f9d  mov     rcx, rax; hHeap
0x1800f2fa0  call    cs:__imp_HeapFree
0x1800f2fa7  nop     dword ptr [rax+rax+00h]
0x1800f2fac  mov     rdi, [rbp+220h+lpMem]
0x1800f2fb0  test    rdi, rdi
0x1800f2fb3  jz      short loc_1800F2FDD
0x1800f2fb5  call    cs:__imp_GetProcessHeap
0x1800f2fbc  nop     dword ptr [rax+rax+00h]
0x1800f2fc1  mov     r8, rdi; lpMem
0x1800f2fc4  xor     edx, edx; dwFlags
0x1800f2fc6  mov     rcx, rax; hHeap
0x1800f2fc9  call    cs:__imp_HeapFree
0x1800f2fd0  nop     dword ptr [rax+rax+00h]
0x1800f2fd5  mov     [rbp+220h+lpMem], 0
0x1800f2fdd  mov     rdi, [rbp+220h+var_270]
0x1800f2fe1  test    rdi, rdi
0x1800f2fe4  jz      short loc_1800F300E
0x1800f2fe6  call    cs:__imp_GetProcessHeap
0x1800f2fed  nop     dword ptr [rax+rax+00h]
0x1800f2ff2  mov     r8, rdi; lpMem
0x1800f2ff5  xor     edx, edx; dwFlags
0x1800f2ff7  mov     rcx, rax; hHeap
0x1800f2ffa  call    cs:__imp_HeapFree
0x1800f3001  nop     dword ptr [rax+rax+00h]
0x1800f3006  mov     [rbp+220h+var_270], 0
0x1800f300e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3015  lea     rax, WPP_GLOBAL_Control
0x1800f301c  cmp     rcx, rax
0x1800f301f  jz      short loc_1800F303F
0x1800f3021  test    byte ptr [rcx+1Ch], 20h
0x1800f3025  jz      short loc_1800F303F
0x1800f3027  mov     rcx, [rcx+10h]
0x1800f302b  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800f3032  mov     edx, 57h ; 'W'
0x1800f3037  mov     r9d, ebx
0x1800f303a  call    WPP_SF_d
0x1800f303f  lea     rcx, [rbp+220h+var_290]; this
0x1800f3043  call    ??1TelemetryProviderRegistrar@@QEAA@XZ; TelemetryProviderRegistrar::~TelemetryProviderRegistrar(void)
0x1800f3048  mov     eax, ebx
0x1800f304a  mov     rcx, [rbp+220h+var_40]
0x1800f3051  xor     rcx, rsp; StackCookie
0x1800f3054  call    __security_check_cookie
  ... truncated ...
```
