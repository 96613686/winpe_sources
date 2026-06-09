# CRDPVideoBitmapPresentation::Initialize(ulong,ulong,ulong,unsigned __int64,_RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *,CRDPVideoBitmapPresentationManager *)

- ea: `0x18009f480`
- end: `0x18009fc1a`
- name: `?Initialize@CRDPVideoBitmapPresentation@@EEAAJKKK_KPEAU_RDPGFX_PROVIDER_VIDEO_HINT_UPDATE@@PEAVCRDPVideoBitmapPresentationManager@@@Z`
- size: `1946`
- prototype: `__int64 __usercall@<rax>(CRDPVideoBitmapPresentation *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int64, struct _RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *, struct CRDPVideoBitmapPresentationManager *)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update`

## callers

- `0x18002fb9c`

## callees

- `0x1800071c0`
- `0x1800091a8`
- `0x18000a93c`
- `0x18000bef4`
- `0x18000c8c0`
- `0x18000eb98`
- `0x18002e600`
- `0x1800598d0`
- `0x180077fc8`
- `0x180081ba8`
- `0x18009c3b8`
- `0x18009f480`
- `0x18009fe80`
- `0x1800a0c78`
- `0x1800a1ed4`
- `0x1800a4640`
- `0x18013e7d0`
- `0x18013ead8`
- `0x18013eb00`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009f60c`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009f684`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009f6fc`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009f60c`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009f684`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009f6fc`

## string_xrefs

- `0x18009f807`: `CTSMfWrapper::CreateInstance() failed`
- `0x18009f66f`: `RDV::RDP::VirtChan::BufferReady`
- `0x18009f6ad`: `RDPAPI_GetGenericCounter( RDV::RDP::VirtChan::BufferReady ) failed.  Non-Fatal`
- `0x18009f984`: `spMFWrapper->TS_MFCreateMemoryBuffer() failed`
- `0x18009f929`: `spMFWrapper->TS_MFCreateSample() failed`
- `0x18009fa4f`: `CBitmapEncoder::CreateInstance() failed`

## pseudocode

```c
__int64 __fastcall CRDPVideoBitmapPresentation::Initialize(
        CRDPVideoBitmapPresentation *this,
        char a2,
        int a3,
        int a4,
        unsigned __int64 a5,
        struct _RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *a6,
        struct CRDPVideoBitmapPresentationManager *a7)
{
  PVOID *v8; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  int Instance; // ebx
  unsigned int v14; // eax
  int GenericCounter; // ebx
  unsigned int v16; // eax
  int v17; // ebx
  unsigned int v18; // eax
  int v19; // ebx
  PVOID *v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // r13d
  unsigned int v23; // r12d
  unsigned int v24; // eax
  int v25; // edx
  const char *v26; // rcx
  __int64 v27; // rdx
  struct _RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *v28; // rcx
  _OWORD *v29; // rax
  __int128 v30; // xmm1
  __int128 v31; // xmm1
  CTSMfWrapper *v32; // rcx
  unsigned int v33; // r8d
  int v34; // ebx
  int v35; // edi
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r8
  struct CBitmapEncoder **v42; // [rsp+28h] [rbp-38h]
  struct CBitmapEncoder **v43; // [rsp+28h] [rbp-38h]
  struct CBitmapEncoder **v44; // [rsp+28h] [rbp-38h]
  CTSMfWrapper *v45; // [rsp+40h] [rbp-20h] BYREF
  struct IMFMediaBuffer *v46; // [rsp+48h] [rbp-18h] BYREF
  struct IMFMediaType *v47[2]; // [rsp+50h] [rbp-10h] BYREF

  v47[0] = 0;
  v46 = 0;
  v45 = 0;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      &WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
      CurrentThreadActivityIdPrefix,
      this);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a6 )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
      goto LABEL_11;
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 20;
    v12 = "pVideoHint";
LABEL_10:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
      v10,
      (__int64)v12);
LABEL_11:
    Instance = -2147467261;
    goto LABEL_88;
  }
  if ( !a7 )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
      goto LABEL_11;
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 21;
    v12 = "pPresentationManager";
    goto LABEL_10;
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRDPVideoBitmapPresentation *)((char *)this + 64)) )
  {
    Instance = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
        v14,
        (__int64)"m_csLock.Initialize()",
        -2147467259);
    }
    goto LABEL_88;
  }
  *((_QWORD *)this + 67) = 0;
  CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init();
  GenericCounter = RDPAPI_GetGenericCounter(
                     L"RDV::RDP::VOBREvents::VOBREncodeFrame",
                     0xFFFFFFFFLL,
                     0xFFFFFFFFLL,
                     0xFFFFFFFFLL,
                     4,
                     (char *)this + 1800);
  if ( GenericCounter < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v42) = GenericCounter;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
      v16,
      (__int64)"RDPAPI_GetGenericCounter( RDV::RDP::VOBREvents::VOBREncodeFrame ) failed.  Non-Fatal",
      v42);
  }
  v17 = RDPAPI_GetGenericCounter(
          L"RDV::RDP::VirtChan::BufferReady",
          0xFFFFFFFFLL,
          0xFFFFFFFFLL,
          0xFFFFFFFFLL,
          4,
          (char *)this + 1808);
  if ( v17 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v43) = v17;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
      v18,
      (__int64)"RDPAPI_GetGenericCounter( RDV::RDP::VirtChan::BufferReady ) failed.  Non-Fatal",
      v43);
  }
  v19 = RDPAPI_GetGenericCounter(
          L"RDV::RDP::VOBREvents::VOBRCaptureFrameVideoHint",
          0xFFFFFFFFLL,
          0xFFFFFFFFLL,
          0xFFFFFFFFLL,
          4,
          (char *)this + 1816);
  if ( v19 >= 0 )
    goto LABEL_37;
  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v44) = v19;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
      v21,
      (__int64)"RDPAPI_GetGenericCounter( RDV::RDP::VOBREvents::VOBRCaptureFrameVideoHint ) failed.  Non-Fatal",
      v44);
LABEL_37:
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  v22 = *((_DWORD *)a6 + 279) - *((_DWORD *)a6 + 277);
  v23 = *((_DWORD *)a6 + 278) - *((_DWORD *)a6 + 276);
  if ( !(v23 * v22) )
  {
    Instance = -2147467259;
    if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 8) == 0 || *((_BYTE *)v20 + 25) < 2u )
      goto LABEL_88;
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 27;
    LODWORD(v44) = -2147467259;
    v26 = "Encoding rectangle must not be empty.";
    goto LABEL_87;
  }
  Instance = CTSMfWrapper::CreateInstance((struct ITSPlatform *)v20, &v45);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 28;
    v26 = "CTSMfWrapper::CreateInstance() failed";
    goto LABEL_86;
  }
  *((_BYTE *)this + 576) = a2;
  *((_DWORD *)this + 143) = a3;
  if ( a7 != *((struct CRDPVideoBitmapPresentationManager **)this + 10) )
  {
    TCntPtr<CRDPVideoBitmapPresentationManager>::SafeRelease((char *)this + 80);
    *((_QWORD *)this + 10) = a7;
    TCntPtr<CRDPVideoBitmapPresentationManager>::SafeAddRef((char *)this + 80);
  }
  v27 = 8;
  *((_QWORD *)this + 216) = a5;
  v28 = a6;
  v29 = (_OWORD *)((char *)this + 608);
  do
  {
    *v29 = *(_OWORD *)v28;
    v29[1] = *((_OWORD *)v28 + 1);
    v29[2] = *((_OWORD *)v28 + 2);
    v29[3] = *((_OWORD *)v28 + 3);
    v29[4] = *((_OWORD *)v28 + 4);
    v29[5] = *((_OWORD *)v28 + 5);
    v29[6] = *((_OWORD *)v28 + 6);
    v30 = *((_OWORD *)v28 + 7);
    v28 = (struct _RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *)((char *)v28 + 128);
    v29[7] = v30;
    v29 += 8;
    --v27;
  }
  while ( v27 );
  *v29 = *(_OWORD *)v28;
  v29[1] = *((_OWORD *)v28 + 1);
  v29[2] = *((_OWORD *)v28 + 2);
  v29[3] = *((_OWORD *)v28 + 3);
  v29[4] = *((_OWORD *)v28 + 4);
  v31 = *((_OWORD *)v28 + 5);
  v32 = v45;
  v29[5] = v31;
  Instance = CTSMfWrapper::TS_MFCreateSample(v32, (struct IMFSample **)this + 12);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 29;
    v26 = "spMFWrapper->TS_MFCreateSample() failed";
    goto LABEL_86;
  }
  Instance = CTSMfWrapper::TS_MFCreateMemoryBuffer(v45, 4 * v23 * v22, &v46);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 30;
    v26 = "spMFWrapper->TS_MFCreateMemoryBuffer() failed";
    goto LABEL_86;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, struct IMFMediaBuffer *))(**((_QWORD **)this + 12) + 336LL))(
               *((_QWORD *)this + 12),
               v46);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 31;
    v26 = "m_spRgbSample->AddBuffer() failed";
    goto LABEL_86;
  }
  Instance = CBitmapEncoder::CreateInstance(
               v23,
               v22,
               v33,
               *((_DWORD *)this + 143),
               *((_DWORD *)this + 142),
               (struct CBitmapEncoder **)this + 11);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 32;
    v26 = "CBitmapEncoder::CreateInstance() failed";
    goto LABEL_86;
  }
  Instance = CBitmapEncoder::GetEncoderMediaType(*((CBitmapEncoder **)this + 11), v47);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 33;
    v26 = "m_spEncoder->GetEncoderMediaType() failed";
    goto LABEL_86;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v34 = *((_DWORD *)this + 143);
    v35 = *((_DWORD *)this + 142);
    v36 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
      v36,
      v23,
      v22,
      v35,
      v34);
  }
  Instance = CRDPVideoBitmapPresentation::SendPresentationStartToClient(
               (CRDPVideoBitmapPresentationManager **)this,
               *((unsigned __int8 *)this + 576),
               a6,
               v47[0],
               *((_QWORD *)this + 73));
  if ( Instance >= 0 )
  {
    *((_DWORD *)this + 150) = a4;
    *((_DWORD *)this + 151) = 1;
    goto LABEL_93;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 35;
    v26 = "SendPresentationStartToClient() failed";
LABEL_86:
    LODWORD(v44) = Instance;
LABEL_87:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v25,
      (unsigned int)&WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids,
      v24,
      (__int64)v26,
      v44);
  }
LABEL_88:
  if ( *((_QWORD *)this + 11) )
  {
    TCntPtr<CWppAutoTrace>::SafeRelease((char *)this + 88);
    *((_QWORD *)this + 11) = 0;
    TCntPtr<CTermInputMgr>::SafeAddRef((char *)this + 88);
  }
  if ( *((_QWORD *)this + 10) )
  {
    TCntPtr<CRDPVideoBitmapPresentationManager>::SafeRelease((char *)this + 80);
    *((_QWORD *)this + 10) = 0;
    TCntPtr<CRDPVideoBitmapPresentationManager>::SafeAddRef((char *)this + 80);
  }
LABEL_93:
  TCntPtr<CWppAutoTrace>::SafeRelease(&v45);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v46, v37, v38);
  TCntPtr<IRdpSQMLogger>::SafeRelease(v47, v39, v40);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18009f480  mov     [rsp-38h+arg_18], r9d
0x18009f485  mov     [rsp-38h+arg_10], r8d
0x18009f48a  mov     [rsp-38h+arg_8], edx
0x18009f48e  push    rbp
0x18009f48f  push    rbx
0x18009f490  push    rdi
0x18009f491  push    r12
0x18009f493  push    r13
0x18009f495  push    r14
0x18009f497  push    r15
0x18009f499  mov     rbp, rsp
0x18009f49c  sub     rsp, 60h
0x18009f4a0  xor     ebx, ebx
0x18009f4a2  mov     r14, rcx
0x18009f4a5  mov     [rbp+var_10], rbx
0x18009f4a9  mov     [rbp+var_18], rbx
0x18009f4ad  mov     [rbp+var_20], rbx
0x18009f4b1  mov     rax, cs:WPP_GLOBAL_Control
0x18009f4b8  lea     rdi, WPP_GLOBAL_Control
0x18009f4bf  lea     r12, WPP_63eddfd253623a7d3ac5b0d68f6ecb3a_Traceguids
0x18009f4c6  cmp     rax, rdi
0x18009f4c9  jz      short loc_18009F504
0x18009f4cb  test    dword ptr [rax+1Ch], 200h
0x18009f4d2  jz      short loc_18009F504
0x18009f4d4  cmp     byte ptr [rax+19h], 4
0x18009f4d8  jb      short loc_18009F504
0x18009f4da  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f4df  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f4e6  lea     edx, [rbx+13h]
0x18009f4e9  mov     r9d, eax
0x18009f4ec  mov     qword ptr [rsp+60h+var_40], r14
0x18009f4f1  mov     r8, r12
0x18009f4f4  mov     rcx, [rcx+10h]
0x18009f4f8  call    WPP_SF_Dq
0x18009f4fd  mov     rax, cs:WPP_GLOBAL_Control
0x18009f504  mov     r15, [rbp+arg_28]
0x18009f508  test    r15, r15
0x18009f50b  jnz     short loc_18009F553
0x18009f50d  cmp     rax, rdi
0x18009f510  jz      short loc_18009F549
0x18009f512  test    byte ptr [rax+1Ch], 8
0x18009f516  jz      short loc_18009F549
0x18009f518  cmp     byte ptr [rax+19h], 2
0x18009f51c  jb      short loc_18009F549
0x18009f51e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f523  lea     edx, [r15+14h]
0x18009f527  lea     rcx, aPvideohint; "pVideoHint"
0x18009f52e  mov     qword ptr [rsp+60h+var_40], rcx
0x18009f533  mov     r9d, eax
0x18009f536  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f53d  mov     r8, r12
0x18009f540  mov     rcx, [rcx+10h]
0x18009f544  call    WPP_SF_Ds
0x18009f549  mov     ebx, 80004003h
0x18009f54e  jmp     loc_18009FB94
0x18009f553  cmp     [rbp+arg_30], rbx
0x18009f557  jnz     short loc_18009F57D
0x18009f559  cmp     rax, rdi
0x18009f55c  jz      short loc_18009F549
0x18009f55e  test    byte ptr [rax+1Ch], 8
0x18009f562  jz      short loc_18009F549
0x18009f564  cmp     byte ptr [rax+19h], 2
0x18009f568  jb      short loc_18009F549
0x18009f56a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f56f  mov     edx, 15h
0x18009f574  lea     rcx, aPpresentationm; "pPresentationManager"
0x18009f57b  jmp     short loc_18009F52E
0x18009f57d  lea     rcx, [r14+40h]; this
0x18009f581  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18009f586  test    eax, eax
0x18009f588  jnz     short loc_18009F5D4
0x18009f58a  mov     ebx, 80004005h
0x18009f58f  mov     rax, cs:WPP_GLOBAL_Control
0x18009f596  cmp     rax, rdi
0x18009f599  jz      loc_18009FB94
0x18009f59f  test    byte ptr [rax+1Ch], 8
0x18009f5a3  jz      loc_18009FB94
0x18009f5a9  cmp     byte ptr [rax+19h], 2
0x18009f5ad  jb      loc_18009FB94
0x18009f5b3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f5b8  mov     edx, 16h
0x18009f5bd  mov     dword ptr [rsp+60h+var_38], 80004005h
0x18009f5c5  lea     rcx, aMCslockInitial; "m_csLock.Initialize()"
0x18009f5cc  mov     r8, r12
0x18009f5cf  jmp     loc_18009FB7C
0x18009f5d4  lea     rcx, [r14+78h]
0x18009f5d8  mov     [rcx+1A0h], rbx
0x18009f5df  call    ?Init@?$CTNodePool@UNODEBLOCK@CVPtrList@@UNODE@2@$0BA@@@QEAAXK@Z; CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init(ulong)
0x18009f5e4  lea     rdx, [r14+708h]
0x18009f5eb  or      r13d, 0FFFFFFFFh
0x18009f5ef  mov     [rsp+60h+var_38], rdx
0x18009f5f4  lea     rcx, aRdvRdpVobreven; "RDV::RDP::VOBREvents::VOBREncodeFrame"
0x18009f5fb  mov     edx, r13d
0x18009f5fe  mov     [rsp+60h+var_40], 4
0x18009f606  mov     r9d, r13d
0x18009f609  mov     r8d, r13d
0x18009f60c  call    cs:__imp_RDPAPI_GetGenericCounter
0x18009f612  mov     ebx, eax
0x18009f614  test    eax, eax
0x18009f616  jns     short loc_18009F660
0x18009f618  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f61f  cmp     rcx, rdi
0x18009f622  jz      short loc_18009F660
0x18009f624  test    byte ptr [rcx+1Ch], 8
0x18009f628  jz      short loc_18009F660
0x18009f62a  cmp     byte ptr [rcx+19h], 2
0x18009f62e  jb      short loc_18009F660
0x18009f630  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f635  lea     rcx, aRdpapiGetgener_17; "RDPAPI_GetGenericCounter( RDV::RDP::VOB"...
0x18009f63c  mov     dword ptr [rsp+60h+var_38], ebx
0x18009f640  mov     qword ptr [rsp+60h+var_40], rcx
0x18009f645  mov     edx, 18h
0x18009f64a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f651  mov     r9d, eax
0x18009f654  mov     r8, r12
0x18009f657  mov     rcx, [rcx+10h]
0x18009f65b  call    WPP_SF_DsD
0x18009f660  lea     rax, [r14+710h]
0x18009f667  mov     r9d, r13d
0x18009f66a  mov     [rsp+60h+var_38], rax
0x18009f66f  lea     rcx, aRdvRdpVirtchan; "RDV::RDP::VirtChan::BufferReady"
0x18009f676  mov     r8d, r13d
0x18009f679  mov     [rsp+60h+var_40], 4
0x18009f681  mov     edx, r13d
0x18009f684  call    cs:__imp_RDPAPI_GetGenericCounter
0x18009f68a  mov     ebx, eax
0x18009f68c  test    eax, eax
0x18009f68e  jns     short loc_18009F6D8
0x18009f690  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f697  cmp     rcx, rdi
0x18009f69a  jz      short loc_18009F6D8
0x18009f69c  test    byte ptr [rcx+1Ch], 8
0x18009f6a0  jz      short loc_18009F6D8
0x18009f6a2  cmp     byte ptr [rcx+19h], 2
0x18009f6a6  jb      short loc_18009F6D8
0x18009f6a8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f6ad  lea     rcx, aRdpapiGetgener_2; "RDPAPI_GetGenericCounter( RDV::RDP::Vir"...
0x18009f6b4  mov     dword ptr [rsp+60h+var_38], ebx
0x18009f6b8  mov     qword ptr [rsp+60h+var_40], rcx
0x18009f6bd  mov     edx, 19h
0x18009f6c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f6c9  mov     r9d, eax
0x18009f6cc  mov     r8, r12
0x18009f6cf  mov     rcx, [rcx+10h]
0x18009f6d3  call    WPP_SF_DsD
0x18009f6d8  lea     rax, [r14+718h]
0x18009f6df  mov     r9d, r13d
0x18009f6e2  mov     [rsp+60h+var_38], rax
0x18009f6e7  lea     rcx, aRdvRdpVobreven_1; "RDV::RDP::VOBREvents::VOBRCaptureFrameV"...
0x18009f6ee  mov     r8d, r13d
0x18009f6f1  mov     [rsp+60h+var_40], 4
0x18009f6f9  mov     edx, r13d
0x18009f6fc  call    cs:__imp_RDPAPI_GetGenericCounter
0x18009f702  mov     ebx, eax
0x18009f704  test    eax, eax
0x18009f706  jns     short loc_18009F750
0x18009f708  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f70f  cmp     rcx, rdi
0x18009f712  jz      short loc_18009F757
0x18009f714  test    byte ptr [rcx+1Ch], 8
0x18009f718  jz      short loc_18009F757
0x18009f71a  cmp     byte ptr [rcx+19h], 2
0x18009f71e  jb      short loc_18009F757
0x18009f720  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f725  lea     rcx, aRdpapiGetgener_18; "RDPAPI_GetGenericCounter( RDV::RDP::VOB"...
0x18009f72c  mov     dword ptr [rsp+60h+var_38], ebx
0x18009f730  mov     qword ptr [rsp+60h+var_40], rcx
0x18009f735  mov     edx, 1Ah
0x18009f73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f741  mov     r9d, eax
0x18009f744  mov     r8, r12
0x18009f747  mov     rcx, [rcx+10h]
0x18009f74b  call    WPP_SF_DsD
0x18009f750  mov     rcx, cs:WPP_GLOBAL_Control; struct ITSPlatform *
0x18009f757  mov     r13d, [r15+45Ch]
0x18009f75e  sub     r13d, [r15+454h]
0x18009f765  mov     r12d, [r15+458h]
0x18009f76c  mov     edi, r13d
0x18009f76f  sub     r12d, [r15+450h]
0x18009f776  imul    edi, r12d
0x18009f77a  test    edi, edi
0x18009f77c  jnz     short loc_18009F7C3
0x18009f77e  mov     ebx, 80004005h
0x18009f783  lea     rdx, WPP_GLOBAL_Control
0x18009f78a  cmp     rcx, rdx
0x18009f78d  jz      loc_18009FB94
0x18009f793  test    byte ptr [rcx+1Ch], 8
0x18009f797  jz      loc_18009FB94
0x18009f79d  cmp     byte ptr [rcx+19h], 2
0x18009f7a1  jb      loc_18009FB94
0x18009f7a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f7ac  lea     edx, [rdi+1Bh]
0x18009f7af  mov     dword ptr [rsp+60h+var_38], 80004005h
0x18009f7b7  lea     rcx, aEncodingRectan; "Encoding rectangle must not be empty."
0x18009f7be  jmp     loc_18009FB75
0x18009f7c3  lea     rdx, [rbp+var_20]; struct CTSMfWrapper **
0x18009f7c7  call    ?CreateInstance@CTSMfWrapper@@SAJPEAVITSPlatform@@PEAPEAV1@@Z; CTSMfWrapper::CreateInstance(ITSPlatform *,CTSMfWrapper * *)
0x18009f7cc  mov     ebx, eax
0x18009f7ce  test    eax, eax
0x18009f7d0  jns     short loc_18009F813
0x18009f7d2  mov     rax, cs:WPP_GLOBAL_Control
0x18009f7d9  lea     rdx, WPP_GLOBAL_Control
0x18009f7e0  cmp     rax, rdx
0x18009f7e3  jz      loc_18009FB94
0x18009f7e9  test    byte ptr [rax+1Ch], 8
0x18009f7ed  jz      loc_18009FB94
0x18009f7f3  cmp     byte ptr [rax+19h], 2
0x18009f7f7  jb      loc_18009FB94
0x18009f7fd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f802  mov     edx, 1Ch
0x18009f807  lea     rcx, aCtsmfwrapperCr; "CTSMfWrapper::CreateInstance() failed"
0x18009f80e  jmp     loc_18009FB71
0x18009f813  mov     eax, [rbp+arg_8]
0x18009f816  lea     rbx, [r14+50h]
0x18009f81a  mov     [r14+240h], al
0x18009f821  mov     eax, [rbp+arg_10]
0x18009f824  mov     [r14+23Ch], eax
0x18009f82b  mov     rax, [rbp+arg_30]
0x18009f82f  cmp     rax, [rbx]
0x18009f832  jz      short loc_18009F84B
0x18009f834  mov     rcx, rbx
0x18009f837  call    ?SafeRelease@?$TCntPtr@VCRDPVideoBitmapPresentationManager@@@@AEAAXXZ; TCntPtr<CRDPVideoBitmapPresentationManager>::SafeRelease(void)
0x18009f83c  mov     rax, [rbp+arg_30]
0x18009f840  mov     rcx, rbx
0x18009f843  mov     [rbx], rax
0x18009f846  call    ?SafeAddRef@?$TCntPtr@VCRDPVideoBitmapPresentationManager@@@@AEAAXXZ; TCntPtr<CRDPVideoBitmapPresentationManager>::SafeAddRef(void)
0x18009f84b  mov     rax, [rbp+arg_20]
0x18009f84f  mov     edx, 8
0x18009f854  mov     [r14+6C0h], rax
0x18009f85b  mov     rcx, r15
0x18009f85e  lea     rax, [r14+260h]
0x18009f865  lea     r8d, [rdx+78h]
0x18009f869  movups  xmm0, xmmword ptr [rcx]
0x18009f86c  movups  xmmword ptr [rax], xmm0
0x18009f86f  movups  xmm1, xmmword ptr [rcx+10h]
0x18009f873  movups  xmmword ptr [rax+10h], xmm1
0x18009f877  movups  xmm0, xmmword ptr [rcx+20h]
0x18009f87b  movups  xmmword ptr [rax+20h], xmm0
0x18009f87f  movups  xmm1, xmmword ptr [rcx+30h]
0x18009f883  movups  xmmword ptr [rax+30h], xmm1
0x18009f887  movups  xmm0, xmmword ptr [rcx+40h]
0x18009f88b  movups  xmmword ptr [rax+40h], xmm0
0x18009f88f  movups  xmm1, xmmword ptr [rcx+50h]
0x18009f893  movups  xmmword ptr [rax+50h], xmm1
0x18009f897  movups  xmm0, xmmword ptr [rcx+60h]
0x18009f89b  movups  xmmword ptr [rax+60h], xmm0
0x18009f89f  movups  xmm1, xmmword ptr [rcx+70h]
0x18009f8a3  add     rcx, r8
0x18009f8a6  movups  xmmword ptr [rax+70h], xmm1
0x18009f8aa  add     rax, r8
0x18009f8ad  sub     rdx, 1
0x18009f8b1  jnz     short loc_18009F869
0x18009f8b3  movups  xmm0, xmmword ptr [rcx]
0x18009f8b6  lea     rdx, [r14+60h]; struct IMFSample **
0x18009f8ba  movups  xmmword ptr [rax], xmm0
0x18009f8bd  movups  xmm1, xmmword ptr [rcx+10h]
0x18009f8c1  movups  xmmword ptr [rax+10h], xmm1
0x18009f8c5  movups  xmm0, xmmword ptr [rcx+20h]
0x18009f8c9  movups  xmmword ptr [rax+20h], xmm0
0x18009f8cd  movups  xmm1, xmmword ptr [rcx+30h]
0x18009f8d1  movups  xmmword ptr [rax+30h], xmm1
0x18009f8d5  movups  xmm0, xmmword ptr [rcx+40h]
0x18009f8d9  movups  xmmword ptr [rax+40h], xmm0
0x18009f8dd  movups  xmm1, xmmword ptr [rcx+50h]
0x18009f8e1  mov     rcx, [rbp+var_20]; this
0x18009f8e5  movups  xmmword ptr [rax+50h], xmm1
0x18009f8e9  call    ?TS_MFCreateSample@CTSMfWrapper@@QEAAJPEAPEAUIMFSample@@@Z; CTSMfWrapper::TS_MFCreateSample(IMFSample * *)
0x18009f8ee  mov     ebx, eax
0x18009f8f0  test    eax, eax
0x18009f8f2  jns     short loc_18009F935
0x18009f8f4  mov     rax, cs:WPP_GLOBAL_Control
0x18009f8fb  lea     rdx, WPP_GLOBAL_Control
0x18009f902  cmp     rax, rdx
0x18009f905  jz      loc_18009FB94
0x18009f90b  test    byte ptr [rax+1Ch], 8
0x18009f90f  jz      loc_18009FB94
0x18009f915  cmp     byte ptr [rax+19h], 2
0x18009f919  jb      loc_18009FB94
0x18009f91f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f924  mov     edx, 1Dh
0x18009f929  lea     rcx, aSpmfwrapperTsM_0; "spMFWrapper->TS_MFCreateSample() failed"
0x18009f930  jmp     loc_18009FB71
0x18009f935  mov     rcx, [rbp+var_20]; this
0x18009f939  lea     edx, ds:0[rdi*4]; unsigned int
0x18009f940  lea     r8, [rbp+var_18]; struct IMFMediaBuffer **
0x18009f944  call    ?TS_MFCreateMemoryBuffer@CTSMfWrapper@@QEAAJKPEAPEAUIMFMediaBuffer@@@Z; CTSMfWrapper::TS_MFCreateMemoryBuffer(ulong,IMFMediaBuffer * *)
0x18009f949  mov     ebx, eax
0x18009f94b  test    eax, eax
0x18009f94d  jns     short loc_18009F990
0x18009f94f  mov     rax, cs:WPP_GLOBAL_Control
0x18009f956  lea     rdx, WPP_GLOBAL_Control
0x18009f95d  cmp     rax, rdx
0x18009f960  jz      loc_18009FB94
0x18009f966  test    byte ptr [rax+1Ch], 8
0x18009f96a  jz      loc_18009FB94
0x18009f970  cmp     byte ptr [rax+19h], 2
0x18009f974  jb      loc_18009FB94
0x18009f97a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f97f  mov     edx, 1Eh
0x18009f984  lea     rcx, aSpmfwrapperTsM; "spMFWrapper->TS_MFCreateMemoryBuffer() "...
  ... truncated ...
```
