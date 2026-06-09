# CmsDurableLog::Start(CmsTransactionContext *,_MS_CREATE_DISPOSITION,__int64,__int64,__int64,__int64,_ML_LSN)

- ea: `0x1c0053e1c`
- end: `0x1c0054042`
- name: `?Start@CmsDurableLog@@QEAAJPEAVCmsTransactionContext@@W4_MS_CREATE_DISPOSITION@@_J222T_ML_LSN@@@Z`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1c0053c74`

## callees

- `0x1c0037108`
- `0x1c004bc94`
- `0x1c004cb00`
- `0x1c004fc1c`
- `0x1c0052880`
- `0x1c00534c4`
- `0x1c0053710`
- `0x1c0053e1c`
- `0x1c0054048`
- `0x1c0054198`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c00c5c44`
- `0x1c00e5af0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0053f81`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c008842c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0053f81`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c008842c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0054005`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0088499`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0054005`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0088499`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0088254`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0088254`

## pseudocode

```c
__int64 __fastcall CmsDurableLog::Start(
        __int64 a1,
        struct CmsTransactionContext *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // r8
  char v11; // r15
  int v12; // r12d
  PVOID *v13; // r14
  int v14; // ecx
  __int64 v15; // r13
  int v16; // r12d
  int Timer_high; // edx
  int HostInfo; // esi
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rax
  int v22; // edx
  void *v23; // rcx
  CmsRestarter *v24; // rax
  CmsRestarter *v25; // r10
  void *v26; // rbx
  __int64 ActivityIdThread; // rax
  CmsReadCache *v29; // rcx
  CmsVolume *v30; // rcx
  __int64 v31; // rbx
  CmsVolume *v32; // rcx
  _DWORD *PoolWithTag; // rax
  void *v34; // r14
  __int64 v35; // rdx
  _BYTE v36[8]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v37; // [rsp+88h] [rbp-21h] BYREF
  _QWORD v38[2]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v39; // [rsp+110h] [rbp+67h]
  __int64 v40; // [rsp+118h] [rbp+6Fh]
  __int64 v41; // [rsp+120h] [rbp+77h]

  v8 = *((_QWORD *)a2 + 4);
  v11 = 1;
  v12 = *(_DWORD *)(v8 + 3116);
  v13 = (PVOID *)(a1 + 72);
  DbgRedoCreatedCount = 0;
  *(_QWORD *)(a1 + 80) = v8;
  v14 = *(_DWORD *)(v8 + 64);
  v15 = a4 << v14;
  LODWORD(v37) = 2 << v14;
  v16 = (8 * (v12 & 2)) | 1;
  v41 = a7 << v14;
  v40 = a6 << v14;
  v39 = a5 << v14;
  HostInfo = MlLogOpenLog(v8, 0, v8, v41, v39, a4 << v14, v40, v41, v16);
  if ( HostInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_a26a0f824fd733884f700469454722c9_Traceguids,
          (unsigned int)HostInfo);
    }
    *(_DWORD *)(*(_QWORD *)(a1 + 80) + 3116LL) &= ~0x800u;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 80) + 3116LL) & 2) != 0 )
    {
      HostInfo = 0;
    }
    else
    {
      if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 4) != 0 )
      {
        ActivityIdThread = IoGetActivityIdThread();
        McTemplateK0d_EtwWriteTransfer(
          MinstoreEventProvider_Context,
          LogSkipReplay,
          ActivityIdThread,
          (unsigned int)HostInfo);
      }
      if ( qword_1C0136B30 )
        qword_1C0136B30(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 48LL), 0, (unsigned int)HostInfo, 0);
      HostInfo = 0;
      v29 = *(CmsReadCache **)(*(_QWORD *)(a1 + 80) + 2600LL);
      if ( v29 )
      {
        v38[0] = 0;
        v38[1] = -1;
        if ( *((_DWORD *)v29 + 108) )
          HostInfo = CmsReadCache::InvalidateCacheInformation(v29, a2, (const struct _RANGE *)v38, 0, 0, 0);
      }
      if ( HostInfo >= 0 )
      {
        LOBYTE(Timer_high) = 1;
        HostInfo = MlLogOpenLog(*(_QWORD *)(a1 + 80), Timer_high, v19, v20, v39, v15, v40, v41, v16);
        if ( HostInfo >= 0 )
        {
          v30 = *(CmsVolume **)(a1 + 80);
          if ( a8 )
          {
            *((_QWORD *)v30 + 234) = a8;
            v30 = *(CmsVolume **)(a1 + 80);
          }
          HostInfo = CmsVolume::Flush(v30, 0x811u, 0, 0, 0, 0, 0);
          if ( HostInfo < 0 || (HostInfo = MlLogSetEndOfLog(*v13), HostInfo < 0) )
            MlLogCloseLog(*v13);
          else
            *(_DWORD *)(a1 + 296) |= 4u;
        }
      }
    }
  }
  else
  {
    v21 = *(_QWORD *)(a1 + 80);
    v22 = *(_DWORD *)(a1 + 296) | 4;
    *(_DWORD *)(a1 + 296) = v22;
    v23 = *(void **)(a1 + 72);
    if ( (*(_DWORD *)(v21 + 3116) & 2) != 0 )
    {
      *(_DWORD *)(a1 + 296) = v22 & 0xFFFFFFFB;
      MlLogCloseLog(v23);
      *v13 = 0;
    }
    else
    {
      v37 = 0;
      v38[0] = 0;
      v36[0] = 0;
      HostInfo = MlLogGetHostInfo(v23, &v37);
      if ( HostInfo >= 0 )
      {
        HostInfo = MlLogGetLogInfo((unsigned int)*v13, (unsigned int)v38, 0, 0, 0, 0, (__int64)v36);
        if ( HostInfo >= 0 )
        {
          if ( v36[0] )
          {
            v31 = v38[0];
            *(_DWORD *)(*(_QWORD *)(a1 + 80) + 3116LL) &= ~0x800u;
            v32 = *(CmsVolume **)(a1 + 80);
            if ( v31 )
            {
              *((_QWORD *)v32 + 234) = v31;
              v32 = *(CmsVolume **)(a1 + 80);
            }
            HostInfo = CmsVolume::Flush(v32, 0x811u, 0, 0, 0, 0, 0);
            if ( HostInfo >= 0 )
              HostInfo = MlLogSetEndOfLog(*v13);
            if ( qword_1C0136BA0 )
            {
              PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0xC8u, 0x6950534Du);
              v34 = PoolWithTag;
              if ( PoolWithTag )
              {
                *PoolWithTag = 0;
                v35 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 48LL);
                *((_QWORD *)PoolWithTag + 1) = v35;
                LOBYTE(v35) = 1;
                PoolWithTag[4] = HostInfo;
                *((_QWORD *)PoolWithTag + 3) = v31;
                *((_QWORD *)PoolWithTag + 4) = v31;
                *((_QWORD *)PoolWithTag + 7) = 0;
                *((_QWORD *)PoolWithTag + 8) = 0;
                PoolWithTag[18] = 0;
                *((_QWORD *)PoolWithTag + 5) = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 1840LL);
                *((_QWORD *)PoolWithTag + 6) = v37;
                ((void (__fastcall *)(_DWORD *, __int64))qword_1C0136BA0)(PoolWithTag, v35);
                ExFreePoolWithTag(v34, 0);
              }
            }
          }
          else
          {
            v24 = (CmsRestarter *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x248u, 0x6950534Du);
            if ( v24 )
              v25 = CmsRestarter::CmsRestarter(v24, *(struct CmsVolume **)(a1 + 80), (struct CmsDurableLog *)a1);
            else
              v25 = 0;
            *(_QWORD *)(a1 + 280) = v25;
            if ( v25 )
            {
              if ( !byte_1C0136977 && (*(_DWORD *)(*(_QWORD *)(a1 + 80) + 3116LL) & 0x80u) == 0 )
                v11 = 0;
              HostInfo = CmsRestarter::Restart((__int64)v25, a2, a8, v37, v11);
            }
            else
            {
              HostInfo = -1073741670;
            }
          }
        }
      }
    }
  }
  v26 = *(void **)(a1 + 280);
  if ( v26 )
  {
    CmsRestarter::~CmsRestarter(*(CmsRestarter **)(a1 + 280));
    ExFreePoolWithTag(v26, 0);
    *(_QWORD *)(a1 + 280) = 0;
  }
  return (unsigned int)HostInfo;
}

```

## disassembly

```asm
0x1c0053e1c  mov     [rsp-8+arg_10], rbx
0x1c0053e21  push    rbp
0x1c0053e22  push    rsi
0x1c0053e23  push    rdi
0x1c0053e24  push    r12
0x1c0053e26  push    r13
0x1c0053e28  push    r14
0x1c0053e2a  push    r15
0x1c0053e2c  lea     rbp, [rsp-7]
0x1c0053e31  sub     rsp, 0B0h
0x1c0053e38  mov     rax, cs:__security_cookie
0x1c0053e3f  xor     rax, rsp
0x1c0053e42  mov     [rbp+37h+var_40], rax
0x1c0053e46  mov     r8, [rdx+20h]
0x1c0053e4a  mov     rdi, rcx
0x1c0053e4d  mov     r10, [rbp+37h+arg_28]
0x1c0053e51  mov     rbx, rdx
0x1c0053e54  mov     r11, [rbp+37h+arg_20]
0x1c0053e58  mov     r13, r9
0x1c0053e5b  mov     r9, [rbp+37h+arg_30]
0x1c0053e5f  mov     r15d, 1
0x1c0053e65  mov     r12d, [r8+0C2Ch]
0x1c0053e6c  lea     r14, [rdi+48h]
0x1c0053e70  and     cs:?DbgRedoCreatedCount@@3KA, 0; ulong DbgRedoCreatedCount
0x1c0053e77  and     r12d, 2
0x1c0053e7b  mov     [rsp+0E0h+var_70], r14
0x1c0053e80  and     [rsp+0E0h+var_78], 0
0x1c0053e86  lea     edx, [r15+1]
0x1c0053e8a  mov     [rcx+50h], r8
0x1c0053e8e  mov     ecx, [r8+40h]
0x1c0053e92  mov     eax, [r8+0C08h]
0x1c0053e99  shl     edx, cl
0x1c0053e9b  mov     [rsp+0E0h+var_80], edx
0x1c0053e9f  mov     [rsp+0E0h+var_90], eax
0x1c0053ea3  shl     r9, cl
0x1c0053ea6  shl     r10, cl
0x1c0053ea9  shl     r11, cl
0x1c0053eac  shl     r13, cl
0x1c0053eaf  mov     rcx, r8
0x1c0053eb2  mov     dword ptr [rbp+37h+var_58], edx
0x1c0053eb5  xor     edx, edx
0x1c0053eb7  shl     r12d, 3
0x1c0053ebb  or      r12d, r15d
0x1c0053ebe  mov     [rbp+37h+arg_30], r9
0x1c0053ec2  mov     [rsp+0E0h+var_A0], r12d
0x1c0053ec7  mov     [rsp+0E0h+var_A8], r9
0x1c0053ecc  mov     [rsp+0E0h+var_B0], r10
0x1c0053ed1  mov     [rsp+0E0h+var_B8], r13
0x1c0053ed6  mov     [rsp+0E0h+var_C0], r11
0x1c0053edb  mov     [rbp+37h+arg_28], r10
0x1c0053edf  mov     [rbp+37h+arg_20], r11
0x1c0053ee3  call    MlLogOpenLog
0x1c0053ee8  mov     esi, eax
0x1c0053eea  test    eax, eax
0x1c0053eec  js      loc_1C00881EA
0x1c0053ef2  mov     edx, [rdi+128h]
0x1c0053ef8  mov     rax, [rdi+50h]
0x1c0053efc  or      edx, 4
0x1c0053eff  mov     [rdi+128h], edx
0x1c0053f05  mov     ecx, [rax+0C2Ch]
0x1c0053f0b  test    cl, 2
0x1c0053f0e  mov     rcx, [rdi+48h]; P
0x1c0053f12  jnz     loc_1C00884BD
0x1c0053f18  xor     r12d, r12d
0x1c0053f1b  lea     rdx, [rbp+37h+var_58]
0x1c0053f1f  mov     [rbp+37h+var_58], r12
0x1c0053f23  mov     [rbp+37h+var_50], r12
0x1c0053f27  mov     [rbp+37h+var_60], r12b
0x1c0053f2b  call    MlLogGetHostInfo
0x1c0053f30  mov     esi, eax
0x1c0053f32  test    eax, eax
0x1c0053f34  js      loc_1C0053FEC
0x1c0053f3a  mov     rcx, [r14]
0x1c0053f3d  lea     rax, [rbp+37h+var_60]
0x1c0053f41  mov     [rsp+0E0h+var_B0], rax
0x1c0053f46  lea     rdx, [rbp+37h+var_50]
0x1c0053f4a  mov     [rsp+0E0h+var_B8], r12
0x1c0053f4f  xor     r9d, r9d
0x1c0053f52  xor     r8d, r8d
0x1c0053f55  mov     [rsp+0E0h+var_C0], r12
0x1c0053f5a  call    MlLogGetLogInfo
0x1c0053f5f  mov     esi, eax
0x1c0053f61  test    eax, eax
0x1c0053f63  js      loc_1C0053FEC
0x1c0053f69  cmp     [rbp+37h+var_60], r12b
0x1c0053f6d  jnz     loc_1C00883B5
0x1c0053f73  mov     edx, 248h; NumberOfBytes
0x1c0053f78  mov     r8d, 6950534Dh; Tag
0x1c0053f7e  lea     ecx, [rdx-48h]; PoolType
0x1c0053f81  call    cs:__imp_ExAllocatePoolWithTag
0x1c0053f88  nop     dword ptr [rax+rax+00h]
0x1c0053f8d  test    rax, rax
0x1c0053f90  jz      loc_1C00884AB
0x1c0053f96  mov     rdx, [rdi+50h]; struct CmsVolume *
0x1c0053f9a  mov     r8, rdi; struct CmsDurableLog *
0x1c0053f9d  mov     rcx, rax; this
0x1c0053fa0  call    ??0CmsRestarter@@QEAA@PEAVCmsVolume@@PEAVCmsDurableLog@@@Z; CmsRestarter::CmsRestarter(CmsVolume *,CmsDurableLog *)
0x1c0053fa5  mov     r10, rax
0x1c0053fa8  mov     [rdi+118h], r10
0x1c0053faf  test    r10, r10
0x1c0053fb2  jz      loc_1C00884B3
0x1c0053fb8  cmp     cs:byte_1C0136977, r12b
0x1c0053fbf  jnz     short loc_1C0053FD2
0x1c0053fc1  mov     rax, [rdi+50h]
0x1c0053fc5  mov     ecx, [rax+0C2Ch]
0x1c0053fcb  test    cl, cl
0x1c0053fcd  js      short loc_1C0053FD2
0x1c0053fcf  mov     r15b, r12b
0x1c0053fd2  mov     r9, [rbp+37h+var_58]
0x1c0053fd6  mov     rdx, rbx
0x1c0053fd9  mov     r8, [rbp+37h+arg_38]
0x1c0053fdd  mov     rcx, r10
0x1c0053fe0  mov     byte ptr [rsp+0E0h+var_C0], r15b
0x1c0053fe5  call    ?Restart@CmsRestarter@@QEAAJPEAVCmsTransactionContext@@T_ML_LSN@@_J_N@Z; CmsRestarter::Restart(CmsTransactionContext *,_ML_LSN,__int64,bool)
0x1c0053fea  mov     esi, eax
0x1c0053fec  mov     rbx, [rdi+118h]
0x1c0053ff3  test    rbx, rbx
0x1c0053ff6  jz      short loc_1C0054018
0x1c0053ff8  mov     rcx, rbx; this
0x1c0053ffb  call    ??1CmsRestarter@@QEAA@XZ; CmsRestarter::~CmsRestarter(void)
0x1c0054000  xor     edx, edx; Tag
0x1c0054002  mov     rcx, rbx; P
0x1c0054005  call    cs:__imp_ExFreePoolWithTag
0x1c005400c  nop     dword ptr [rax+rax+00h]
0x1c0054011  mov     [rdi+118h], r12
0x1c0054018  mov     eax, esi
0x1c005401a  mov     rcx, [rbp+37h+var_40]
0x1c005401e  xor     rcx, rsp; StackCookie
0x1c0054021  call    __security_check_cookie
0x1c0054026  mov     rbx, [rsp+0E0h+arg_10]
0x1c005402e  add     rsp, 0B0h
0x1c0054035  pop     r15
0x1c0054037  pop     r14
0x1c0054039  pop     r13
0x1c005403b  pop     r12
0x1c005403d  pop     rdi
0x1c005403e  pop     rsi
0x1c005403f  pop     rbp
0x1c0054040  retn
0x1c00881ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00881f1  lea     rax, WPP_GLOBAL_Control
0x1c00881f8  cmp     rcx, rax
0x1c00881fb  jz      short loc_1C0088223
0x1c00881fd  mov     edx, [rcx+2Ch]
0x1c0088200  test    dl, 2
0x1c0088203  jz      short loc_1C0088223
0x1c0088205  cmp     byte ptr [rcx+29h], 2
0x1c0088209  jb      short loc_1C0088223
0x1c008820b  mov     rcx, [rcx+18h]
0x1c008820f  lea     r8, WPP_a26a0f824fd733884f700469454722c9_Traceguids
0x1c0088216  mov     edx, 0Ah
0x1c008821b  mov     r9d, esi
0x1c008821e  call    WPP_SF_D
0x1c0088223  mov     rax, [rdi+50h]
0x1c0088227  btr     dword ptr [rax+0C2Ch], 0Bh
0x1c008822f  mov     rax, [rdi+50h]
0x1c0088233  mov     ecx, [rax+0C2Ch]
0x1c0088239  test    cl, 2
0x1c008823c  jnz     loc_1C00883AA
0x1c0088242  cmp     cs:dword_1C012D0B4, r15d
0x1c0088249  jnz     short loc_1C0088279
0x1c008824b  test    cs:Microsoft_Windows_MinstoreEnableBits, 4
0x1c0088252  jz      short loc_1C0088279
0x1c0088254  call    cs:__imp_IoGetActivityIdThread
0x1c008825b  nop     dword ptr [rax+rax+00h]
0x1c0088260  mov     r9d, esi
0x1c0088263  lea     rdx, LogSkipReplay
0x1c008826a  mov     r8, rax
0x1c008826d  lea     rcx, MinstoreEventProvider_Context
0x1c0088274  call    McTemplateK0d_EtwWriteTransfer
0x1c0088279  mov     rax, cs:qword_1C0136B30
0x1c0088280  test    rax, rax
0x1c0088283  jz      short loc_1C008829B
0x1c0088285  mov     rcx, [rdi+50h]
0x1c0088289  xor     r9d, r9d
0x1c008828c  mov     r8d, esi
0x1c008828f  xor     edx, edx
0x1c0088291  mov     rcx, [rcx+30h]
0x1c0088295  call    cs:__guard_dispatch_icall_fptr
0x1c008829b  mov     rax, [rdi+50h]
0x1c008829f  xor     esi, esi
0x1c00882a1  mov     rcx, [rax+0A28h]; this
0x1c00882a8  test    rcx, rcx
0x1c00882ab  jz      short loc_1C00882D9
0x1c00882ad  and     [rbp+37h+var_50], rsi
0x1c00882b1  or      [rbp+37h+var_48], 0FFFFFFFFFFFFFFFFh
0x1c00882b6  cmp     [rcx+1B0h], esi
0x1c00882bc  jz      short loc_1C00882D9
0x1c00882be  mov     byte ptr [rsp+0E0h+var_B8], sil; unsigned __int8
0x1c00882c3  lea     r8, [rbp+37h+var_50]; struct _RANGE *
0x1c00882c7  xor     r9d, r9d; unsigned __int8
0x1c00882ca  mov     byte ptr [rsp+0E0h+var_C0], sil; unsigned __int8
0x1c00882cf  mov     rdx, rbx; struct CmsTransactionContext *
0x1c00882d2  call    ?InvalidateCacheInformation@CmsReadCache@@QEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@EEE@Z; CmsReadCache::InvalidateCacheInformation(CmsTransactionContext *,_RANGE const *,uchar,uchar,uchar)
0x1c00882d7  mov     esi, eax
0x1c00882d9  test    esi, esi
0x1c00882db  js      loc_1C00884D6
0x1c00882e1  mov     rcx, [rdi+50h]
0x1c00882e5  lea     rax, [rbp+37h+arg_38]
0x1c00882e9  mov     [rsp+0E0h+var_70], r14
0x1c00882ee  mov     dl, r15b
0x1c00882f1  mov     [rsp+0E0h+var_78], rax
0x1c00882f6  mov     eax, dword ptr [rbp+37h+var_58]
0x1c00882f9  mov     [rsp+0E0h+var_80], eax
0x1c00882fd  mov     eax, [rcx+0C08h]
0x1c0088303  mov     [rsp+0E0h+var_90], eax
0x1c0088307  mov     rax, [rbp+37h+arg_30]
0x1c008830b  mov     [rsp+0E0h+var_A0], r12d
0x1c0088310  mov     [rsp+0E0h+var_A8], rax
0x1c0088315  mov     rax, [rbp+37h+arg_28]
0x1c0088319  mov     [rsp+0E0h+var_B0], rax
0x1c008831e  mov     rax, [rbp+37h+arg_20]
0x1c0088322  mov     [rsp+0E0h+var_B8], r13
0x1c0088327  mov     [rsp+0E0h+var_C0], rax
0x1c008832c  call    MlLogOpenLog
0x1c0088331  xor     r12d, r12d
0x1c0088334  mov     esi, eax
0x1c0088336  test    eax, eax
0x1c0088338  js      loc_1C0053FEC
0x1c008833e  mov     rbx, [rbp+37h+arg_38]
0x1c0088342  mov     rcx, [rdi+50h]
0x1c0088346  test    rbx, rbx
0x1c0088349  jz      short loc_1C0088356
0x1c008834b  mov     [rcx+750h], rbx
0x1c0088352  mov     rcx, [rdi+50h]; this
0x1c0088356  mov     [rsp+0E0h+var_B0], r12; struct _KEVENT *
0x1c008835b  xor     r9d, r9d; unsigned int
0x1c008835e  mov     [rsp+0E0h+var_B8], r12; unsigned __int8 *
0x1c0088363  xor     r8d, r8d; void *
0x1c0088366  mov     edx, 811h; unsigned int
0x1c008836b  mov     [rsp+0E0h+var_C0], r12; unsigned __int8 *
0x1c0088370  call    ?Flush@CmsVolume@@QEAAJKPEAXKPEAE1PEAU_KEVENT@@@Z; CmsVolume::Flush(ulong,void *,ulong,uchar *,uchar *,_KEVENT *)
0x1c0088375  mov     esi, eax
0x1c0088377  test    eax, eax
0x1c0088379  js      short loc_1C008839C
0x1c008837b  mov     rdx, [rdi+50h]
0x1c008837f  mov     r8, rbx
0x1c0088382  mov     rcx, [r14]; Src
0x1c0088385  call    MlLogSetEndOfLog
0x1c008838a  mov     esi, eax
0x1c008838c  test    eax, eax
0x1c008838e  js      short loc_1C008839C
0x1c0088390  or      dword ptr [rdi+128h], 4
0x1c0088397  jmp     loc_1C0053FEC
0x1c008839c  mov     rcx, [r14]; P
0x1c008839f  call    MlLogCloseLog
0x1c00883a4  nop
0x1c00883a5  jmp     loc_1C0053FEC
0x1c00883aa  xor     r12d, r12d
0x1c00883ad  mov     esi, r12d
0x1c00883b0  jmp     loc_1C0053FEC
0x1c00883b5  mov     rax, [rdi+50h]
0x1c00883b9  mov     rbx, [rbp+37h+var_50]
0x1c00883bd  btr     dword ptr [rax+0C2Ch], 0Bh
0x1c00883c5  mov     rcx, [rdi+50h]
0x1c00883c9  test    rbx, rbx
0x1c00883cc  jz      short loc_1C00883D9
0x1c00883ce  mov     [rcx+750h], rbx
0x1c00883d5  mov     rcx, [rdi+50h]; this
0x1c00883d9  mov     [rsp+0E0h+var_B0], r12; struct _KEVENT *
0x1c00883de  xor     r9d, r9d; unsigned int
0x1c00883e1  mov     [rsp+0E0h+var_B8], r12; unsigned __int8 *
0x1c00883e6  xor     r8d, r8d; void *
0x1c00883e9  mov     edx, 811h; unsigned int
0x1c00883ee  mov     [rsp+0E0h+var_C0], r12; unsigned __int8 *
0x1c00883f3  call    ?Flush@CmsVolume@@QEAAJKPEAXKPEAE1PEAU_KEVENT@@@Z; CmsVolume::Flush(ulong,void *,ulong,uchar *,uchar *,_KEVENT *)
0x1c00883f8  mov     esi, eax
0x1c00883fa  test    eax, eax
0x1c00883fc  js      short loc_1C008840F
0x1c00883fe  mov     rdx, [rdi+50h]
0x1c0088402  mov     r8, rbx
0x1c0088405  mov     rcx, [r14]; Src
0x1c0088408  call    MlLogSetEndOfLog
0x1c008840d  mov     esi, eax
0x1c008840f  cmp     cs:qword_1C0136BA0, r12
0x1c0088416  jz      loc_1C0053FEC
0x1c008841c  mov     edx, 0C8h; NumberOfBytes
0x1c0088421  mov     ecx, 200h; PoolType
0x1c0088426  mov     r8d, 6950534Dh; Tag
0x1c008842c  call    cs:__imp_ExAllocatePoolWithTag
0x1c0088433  nop     dword ptr [rax+rax+00h]
0x1c0088438  mov     r14, rax
0x1c008843b  test    rax, rax
0x1c008843e  jz      loc_1C0053FEC
0x1c0088444  mov     [rax], r12d
0x1c0088447  mov     rcx, [rdi+50h]
0x1c008844b  mov     rdx, [rcx+30h]
0x1c008844f  mov     [rax+8], rdx
0x1c0088453  mov     dl, r15b
0x1c0088456  mov     [rax+10h], esi
0x1c0088459  mov     [rax+18h], rbx
0x1c008845d  mov     [rax+20h], rbx
0x1c0088461  mov     [rax+38h], r12
0x1c0088465  mov     [rax+40h], r12
0x1c0088469  mov     [rax+48h], r12d
0x1c008846d  mov     rcx, [rdi+50h]
0x1c0088471  mov     rax, [rcx+730h]
0x1c0088478  mov     rcx, r14
0x1c008847b  mov     [r14+28h], rax
0x1c008847f  mov     rax, [rbp+37h+var_58]
  ... truncated ...
```
