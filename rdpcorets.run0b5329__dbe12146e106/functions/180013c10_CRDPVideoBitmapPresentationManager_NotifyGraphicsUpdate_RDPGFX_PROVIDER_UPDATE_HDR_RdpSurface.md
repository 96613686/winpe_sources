# CRDPVideoBitmapPresentationManager::NotifyGraphicsUpdate(_RDPGFX_PROVIDER_UPDATE_HDR *,RdpSurface *)

- ea: `0x180013c10`
- end: `0x18001412a`
- name: `?NotifyGraphicsUpdate@CRDPVideoBitmapPresentationManager@@UEAAXPEAU_RDPGFX_PROVIDER_UPDATE_HDR@@PEAVRdpSurface@@@Z`
- size: `1306`
- prototype: `void __fastcall(CRDPVideoBitmapPresentationManager *__hidden this, struct _RDPGFX_PROVIDER_UPDATE_HDR *, struct RdpSurface *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x1800091a8`
- `0x180012200`
- `0x180013c10`
- `0x18001b710`
- `0x18002e600`
- `0x180032f60`
- `0x180033da0`
- `0x180034970`
- `0x180059838`
- `0x1800598d0`
- `0x18009aeec`
- `0x18009cc90`
- `0x18009d5f0`
- `0x1800a5ee0`

## import_xrefs

- `RDPBASE!PAL_System_CritSecEnter` at `0x180013d4b`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180013d4b`
- `RDPBASE!PAL_System_CritSecLeave` at `0x180013f45`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800140fa`
- `RDPBASE!PAL_System_CritSecLeave` at `0x180013f45`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800140fa`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x180013c6f`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x180013cf4`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x180013ece`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x180014035`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x1800140bb`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x180013c6f`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x180013cf4`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x180013ece`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x180014035`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x1800140bb`

## string_xrefs

- `0x180013c5b`: `VideoBitmapPresentationManagerError_NotifyGraphicsUpdateNullPointer`
- `0x180013ce0`: `VideoBitmapPresentationManagerError_NotifyGraphicsUpdateNullPointer`
- `0x180013caa`: `pGraphicsUpdateHeader`
- `0x180013eba`: `VideoBitmapPresentationManagerError_NotifyGraphicsUpdateAddObservationFail`
- `0x180014021`: `VideoBitmapPresentationManagerError_NotifyGraphicsUpdateSetVideoHintFail`
- `0x1800140a7`: `VideoBitmapPresentationManagerError_NotifyGraphicsUpdateShutdownFail`

## pseudocode

```c
void __fastcall CRDPVideoBitmapPresentationManager::NotifyGraphicsUpdate(
        CRDPVideoBitmapPresentationManager *this,
        struct _RDPGFX_PROVIDER_UPDATE_HDR *a2,
        struct RdpSurface *a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  _QWORD *v9; // rbx
  unsigned int v10; // eax
  __int64 v11; // rax
  int v12; // edx
  unsigned int v13; // r13d
  int v14; // r8d
  int v15; // r9d
  int v16; // r10d
  signed int v17; // eax
  signed int v18; // r14d
  unsigned int v19; // eax
  int EstimatedFrameRate; // eax
  int v21; // r14d
  unsigned int v22; // eax
  signed int v23; // eax
  signed int v24; // edi
  unsigned int v25; // eax
  int v26; // edx
  const char *v27; // rcx
  signed int v28; // eax
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+30h] [rbp-D0h]
  int v31; // [rsp+34h] [rbp-CCh]
  _DWORD v32[4]; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v33[4]; // [rsp+48h] [rbp-B8h] BYREF
  char *v34; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h]
  __int64 v37; // [rsp+498h] [rbp+398h]

  if ( !a2 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpVideoProcessor",
      "VideoBitmapPresentationManagerError_NotifyGraphicsUpdateNullPointer",
      (char *)0x2D4,
      0x80004003,
      v29);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 58;
    v8 = "pGraphicsUpdateHeader";
    goto LABEL_6;
  }
  if ( !a3 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpVideoProcessor",
      "VideoBitmapPresentationManagerError_NotifyGraphicsUpdateNullPointer",
      (char *)0x2D6,
      0x80004003,
      v29);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 59;
    v8 = "pSurface";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)&WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v8);
    return;
  }
  v9 = (_QWORD *)((char *)this + 56);
  v34 = (char *)this + 56;
  if ( *((_DWORD *)this + 16) )
    PAL_System_CritSecEnter(*v9, a2, a3);
  if ( !*((_QWORD *)this + 23) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids, v10);
    }
    goto LABEL_31;
  }
  v11 = *((_QWORD *)a3 + 47);
  if ( v11 == -1 || v11 != *((_QWORD *)this + 169) )
  {
    if ( v9 && *((_DWORD *)v9 + 2) )
      PAL_System_CritSecLeave(*v9);
  }
  else
  {
    v12 = *((_DWORD *)this + 332);
    v13 = 0;
    v14 = *((_DWORD *)this + 333);
    v15 = *((_DWORD *)a3 + 96);
    v16 = *((_DWORD *)a3 + 97);
    v33[0] = v12 + *((_DWORD *)this + 334);
    v31 = v15;
    v33[2] = v12 + *((_DWORD *)this + 336);
    v30 = v16;
    v33[1] = v14 + *((_DWORD *)this + 335);
    v33[3] = v14 + *((_DWORD *)this + 337);
    while ( v13 < *((_DWORD *)a2 + 4) )
    {
      v32[0] = v15 + *((_DWORD *)a2 + 4 * v13 + 10);
      v32[2] = v15 + *((_DWORD *)a2 + 4 * v13 + 12);
      v32[1] = v16 + *((_DWORD *)a2 + 4 * v13 + 11);
      v32[3] = v16 + *((_DWORD *)a2 + 4 * v13 + 13);
      if ( RdpRect::Intersect((RdpRect *)v32, (const struct RdpRect *)v33) )
      {
        v17 = CRdpRectObservationQueue::AddObservation(
                (CRdpRectObservationQueue *)(*((_QWORD *)this + 23) + 72LL),
                (struct RdpRect *)v32);
        v18 = v17;
        if ( v17 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpVideoProcessor",
            "VideoBitmapPresentationManagerError_NotifyGraphicsUpdateAddObservationFail",
            (char *)0x305,
            v17,
            v29);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              62,
              (unsigned int)&WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids,
              v19,
              (__int64)"m_spRectObserver->AddObservation() failed",
              v18);
          }
LABEL_31:
          CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v34);
          return;
        }
        v16 = v30;
      }
      v15 = v31;
      ++v13;
    }
    if ( v9 && *((_DWORD *)v9 + 2) )
      PAL_System_CritSecLeave(*v9);
    if ( !*((_DWORD *)this + 56) )
    {
      EstimatedFrameRate = CRDPVideoBitmapPresentationManager::GetEstimatedFrameRate((CRDPVideoBitmapPresentationManager *)((char *)this - 16));
      v21 = EstimatedFrameRate;
      if ( *((_DWORD *)this + 55) )
      {
        if ( EstimatedFrameRate < 5 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v22 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              63,
              &WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids,
              v22,
              v21);
          }
          if ( *((__int64 *)this + 164) < 0 )
          {
            v28 = CRDPVideoBitmapPresentationManager::ShutdownVideoPresentation((CRDPVideoBitmapPresentationManager *)((char *)this - 16));
            v24 = v28;
            if ( v28 >= 0 )
              return;
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpVideoProcessor",
              "VideoBitmapPresentationManagerError_NotifyGraphicsUpdateShutdownFail",
              (char *)0x333,
              v28,
              v29);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              return;
            }
            v25 = RdpWppGetCurrentThreadActivityIdPrefix();
            v26 = 65;
            v27 = "ShutdownVideoPresentation() failed";
          }
          else
          {
            memset_0(v35, 0, 0x460u);
            v36 = *((unsigned __int16 *)a3 + 28);
            v35[0] = 1120;
            v35[1] = 6;
            v37 = 0;
            v23 = CRDPVideoBitmapPresentationManager::SetVideoHint(
                    this,
                    (struct _RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *)v35);
            v24 = v23;
            if ( v23 >= 0 )
              return;
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpVideoProcessor",
              "VideoBitmapPresentationManagerError_NotifyGraphicsUpdateSetVideoHintFail",
              (char *)0x32A,
              v23,
              v29);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              return;
            }
            v25 = RdpWppGetCurrentThreadActivityIdPrefix();
            v26 = 64;
            v27 = "SetVideoHint() failed";
          }
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v26,
            (unsigned int)&WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids,
            v25,
            (__int64)v27,
            v24);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180013c10  mov     [rsp-8+arg_8], rbx
0x180013c15  push    rbp
0x180013c16  push    rsi
0x180013c17  push    rdi
0x180013c18  push    r12
0x180013c1a  push    r13
0x180013c1c  push    r14
0x180013c1e  push    r15
0x180013c20  lea     rbp, [rsp-3D0h]
0x180013c28  sub     rsp, 4D0h
0x180013c2f  mov     rax, cs:__security_cookie
0x180013c36  xor     rax, rsp
0x180013c39  mov     [rbp+400h+var_40], rax
0x180013c40  xor     r14d, r14d
0x180013c43  mov     rsi, r8
0x180013c46  mov     r12, rdx
0x180013c49  mov     rdi, rcx
0x180013c4c  test    rdx, rdx
0x180013c4f  jnz     loc_180013CD5
0x180013c55  mov     r9d, 80004003h
0x180013c5b  lea     rdx, aVideobitmappre_17; "VideoBitmapPresentationManagerError_Not"...
0x180013c62  mov     r8d, 2D4h
0x180013c68  lea     rcx, aIidIrdpvideopr; "IID_IRdpVideoProcessor"
0x180013c6f  call    cs:__imp_?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180013c75  mov     rax, cs:WPP_GLOBAL_Control
0x180013c7c  lea     rbx, WPP_GLOBAL_Control
0x180013c83  cmp     rax, rbx
0x180013c86  jz      loc_180014100
0x180013c8c  test    byte ptr [rax+1Ch], 8
0x180013c90  jz      loc_180014100
0x180013c96  cmp     byte ptr [rax+19h], 2
0x180013c9a  jb      loc_180014100
0x180013ca0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180013ca5  lea     edx, [r12+3Ah]
0x180013caa  lea     rcx, aPgraphicsupdat; "pGraphicsUpdateHeader"
0x180013cb1  mov     [rsp+500h+var_4E0], rcx
0x180013cb6  lea     r8, WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids
0x180013cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cc4  mov     r9d, eax
0x180013cc7  mov     rcx, [rcx+10h]
0x180013ccb  call    WPP_SF_Ds
0x180013cd0  jmp     loc_180014100
0x180013cd5  test    rsi, rsi
0x180013cd8  jnz     short loc_180013D39
0x180013cda  mov     r9d, 80004003h
0x180013ce0  lea     rdx, aVideobitmappre_17; "VideoBitmapPresentationManagerError_Not"...
0x180013ce7  mov     r8d, 2D6h
0x180013ced  lea     rcx, aIidIrdpvideopr; "IID_IRdpVideoProcessor"
0x180013cf4  call    cs:__imp_?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180013cfa  mov     rax, cs:WPP_GLOBAL_Control
0x180013d01  lea     rbx, WPP_GLOBAL_Control
0x180013d08  cmp     rax, rbx
0x180013d0b  jz      loc_180014100
0x180013d11  test    byte ptr [rax+1Ch], 8
0x180013d15  jz      loc_180014100
0x180013d1b  cmp     byte ptr [rax+19h], 2
0x180013d1f  jb      loc_180014100
0x180013d25  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180013d2a  lea     edx, [rsi+3Bh]
0x180013d2d  lea     rcx, aPsurface; "pSurface"
0x180013d34  jmp     loc_180013CB1
0x180013d39  lea     rbx, [rcx+38h]
0x180013d3d  mov     [rsp+500h+var_4A8], rbx
0x180013d42  cmp     [rbx+8], r14d
0x180013d46  jz      short loc_180013D51
0x180013d48  mov     rcx, [rbx]
0x180013d4b  call    cs:__imp_PAL_System_CritSecEnter
0x180013d51  cmp     [rdi+0B8h], r14
0x180013d58  jnz     short loc_180013DB1
0x180013d5a  mov     rax, cs:WPP_GLOBAL_Control
0x180013d61  lea     rbx, WPP_GLOBAL_Control
0x180013d68  cmp     rax, rbx
0x180013d6b  jz      loc_180013F28
0x180013d71  test    dword ptr [rax+1Ch], 200h
0x180013d78  jz      loc_180013F28
0x180013d7e  cmp     byte ptr [rax+19h], 4
0x180013d82  jb      loc_180013F28
0x180013d88  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180013d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d94  lea     r8, WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids
0x180013d9b  mov     edx, 3Dh ; '='
0x180013da0  mov     r9d, eax
0x180013da3  mov     rcx, [rcx+10h]
0x180013da7  call    WPP_SF_d
0x180013dac  jmp     loc_180013F28
0x180013db1  mov     rax, [rsi+178h]
0x180013db8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013dbc  jz      loc_1800140EC
0x180013dc2  cmp     rax, [rdi+548h]
0x180013dc9  jnz     loc_1800140EC
0x180013dcf  mov     edx, [rdi+530h]
0x180013dd5  mov     r13d, r14d
0x180013dd8  mov     r8d, [rdi+534h]
0x180013ddf  mov     ecx, [rdi+538h]
0x180013de5  mov     r9d, [rsi+180h]
0x180013dec  add     ecx, edx
0x180013dee  mov     r10d, [rsi+184h]
0x180013df5  mov     [rsp+500h+var_4B8], ecx
0x180013df9  mov     ecx, [rdi+540h]
0x180013dff  add     ecx, edx
0x180013e01  mov     [rsp+500h+var_4CC], r9d
0x180013e06  mov     [rsp+500h+var_4B0], ecx
0x180013e0a  mov     ecx, [rdi+53Ch]
0x180013e10  add     ecx, r8d
0x180013e13  mov     [rsp+500h+var_4D0], r10d
0x180013e18  mov     [rsp+500h+var_4B4], ecx
0x180013e1c  mov     ecx, [rdi+544h]
0x180013e22  add     ecx, r8d
0x180013e25  mov     [rsp+500h+var_4AC], ecx
0x180013e29  cmp     r13d, [r12+10h]
0x180013e2e  jnb     loc_180013F37
0x180013e34  mov     r8d, r13d
0x180013e37  lea     rdx, [rsp+500h+var_4B8]; struct RdpRect *
0x180013e3c  add     r8, r8
0x180013e3f  mov     eax, r13d
0x180013e42  add     rax, 3
0x180013e46  add     rax, rax
0x180013e49  mov     ecx, [r12+r8*8+28h]
0x180013e4e  add     ecx, r9d
0x180013e51  mov     [rsp+500h+var_4C8], ecx
0x180013e55  mov     ecx, [r12+rax*8]
0x180013e59  add     ecx, r9d
0x180013e5c  mov     [rsp+500h+var_4C0], ecx
0x180013e60  mov     ecx, [r12+r8*8+2Ch]
0x180013e65  add     ecx, r10d
0x180013e68  mov     [rsp+500h+var_4C4], ecx
0x180013e6c  mov     ecx, [r12+r8*8+34h]
0x180013e71  add     ecx, r10d
0x180013e74  mov     [rsp+500h+var_4BC], ecx
0x180013e78  lea     rcx, [rsp+500h+var_4C8]; this
0x180013e7d  call    ?Intersect@RdpRect@@QEAA_NAEBU1@@Z; RdpRect::Intersect(RdpRect const &)
0x180013e82  test    al, al
0x180013e84  jz      short loc_180013EAA
0x180013e86  mov     rcx, [rdi+0B8h]
0x180013e8d  lea     rdx, [rsp+500h+var_4C8]; struct RdpRect *
0x180013e92  add     rcx, 48h ; 'H'; this
0x180013e96  call    ?AddObservation@CRdpRectObservationQueue@@UEAAJPEAURdpRect@@@Z; CRdpRectObservationQueue::AddObservation(RdpRect *)
0x180013e9b  mov     r14d, eax
0x180013e9e  test    eax, eax
0x180013ea0  js      short loc_180013EB7
0x180013ea2  mov     r10d, [rsp+500h+var_4D0]
0x180013ea7  xor     r14d, r14d
0x180013eaa  mov     r9d, [rsp+500h+var_4CC]
0x180013eaf  inc     r13d
0x180013eb2  jmp     loc_180013E29
0x180013eb7  mov     r9d, r14d
0x180013eba  lea     rdx, aVideobitmappre_4; "VideoBitmapPresentationManagerError_Not"...
0x180013ec1  mov     r8d, 305h
0x180013ec7  lea     rcx, aIidIrdpvideopr; "IID_IRdpVideoProcessor"
0x180013ece  call    cs:__imp_?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180013ed4  mov     rax, cs:WPP_GLOBAL_Control
0x180013edb  lea     rbx, WPP_GLOBAL_Control
0x180013ee2  cmp     rax, rbx
0x180013ee5  jz      short loc_180013F28
0x180013ee7  test    byte ptr [rax+1Ch], 8
0x180013eeb  jz      short loc_180013F28
0x180013eed  cmp     byte ptr [rax+19h], 2
0x180013ef1  jb      short loc_180013F28
0x180013ef3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180013ef8  lea     rcx, aMSprectobserve_0; "m_spRectObserver->AddObservation() fail"...
0x180013eff  mov     [rsp+500h+var_4D8], r14d
0x180013f04  mov     [rsp+500h+var_4E0], rcx
0x180013f09  lea     r8, WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids
0x180013f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f17  mov     edx, 3Eh ; '>'
0x180013f1c  mov     r9d, eax
0x180013f1f  mov     rcx, [rcx+10h]
0x180013f23  call    WPP_SF_DsD
0x180013f28  lea     rcx, [rsp+500h+var_4A8]; this
0x180013f2d  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180013f32  jmp     loc_180014100
0x180013f37  test    rbx, rbx
0x180013f3a  jz      short loc_180013F4B
0x180013f3c  cmp     [rbx+8], r14d
0x180013f40  jz      short loc_180013F4B
0x180013f42  mov     rcx, [rbx]
0x180013f45  call    cs:__imp_PAL_System_CritSecLeave
0x180013f4b  cmp     [rdi+0E0h], r14d
0x180013f52  jnz     loc_180014100
0x180013f58  lea     rcx, [rdi-10h]; this
0x180013f5c  call    ?GetEstimatedFrameRate@CRDPVideoBitmapPresentationManager@@EEAAJXZ; CRDPVideoBitmapPresentationManager::GetEstimatedFrameRate(void)
0x180013f61  xor     r12d, r12d
0x180013f64  mov     r14d, eax
0x180013f67  cmp     [rdi+0DCh], r12d
0x180013f6e  jz      loc_180014100
0x180013f74  cmp     eax, 5
0x180013f77  jge     loc_180014100
0x180013f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f84  lea     rbx, WPP_GLOBAL_Control
0x180013f8b  cmp     rcx, rbx
0x180013f8e  jz      short loc_180013FC8
0x180013f90  test    dword ptr [rcx+1Ch], 200h
0x180013f97  jz      short loc_180013FC8
0x180013f99  cmp     byte ptr [rcx+19h], 4
0x180013f9d  jb      short loc_180013FC8
0x180013f9f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180013fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fab  lea     edx, [r12+3Fh]
0x180013fb0  mov     r9d, eax
0x180013fb3  mov     dword ptr [rsp+500h+var_4E0], r14d
0x180013fb8  lea     r8, WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids
0x180013fbf  mov     rcx, [rcx+10h]
0x180013fc3  call    WPP_SF_Dd
0x180013fc8  cmp     [rdi+520h], r12
0x180013fcf  jl      loc_180014095
0x180013fd5  mov     r14d, 460h
0x180013fdb  lea     rcx, [rsp+500h+var_4A0]; void *
0x180013fe0  mov     r8d, r14d; Size
0x180013fe3  xor     edx, edx; Val
0x180013fe5  call    memset_0
0x180013fea  movzx   eax, word ptr [rsi+38h]
0x180013fee  lea     rdx, [rsp+500h+var_4A0]; struct _RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *
0x180013ff3  mov     rcx, rdi; this
0x180013ff6  mov     [rsp+500h+var_498], rax
0x180013ffb  mov     [rsp+500h+var_4A0], r14d
0x180014000  mov     [rsp+500h+var_49C], 6
0x180014008  mov     [rbp+400h+var_68], r12
0x18001400f  call    ?SetVideoHint@CRDPVideoBitmapPresentationManager@@UEAAJPEAU_RDPGFX_PROVIDER_VIDEO_HINT_UPDATE@@@Z; CRDPVideoBitmapPresentationManager::SetVideoHint(_RDPGFX_PROVIDER_VIDEO_HINT_UPDATE *)
0x180014014  mov     edi, eax
0x180014016  test    eax, eax
0x180014018  jns     loc_180014100
0x18001401e  mov     r9d, eax
0x180014021  lea     rdx, aVideobitmappre_10; "VideoBitmapPresentationManagerError_Not"...
0x180014028  mov     r8d, 32Ah
0x18001402e  lea     rcx, aIidIrdpvideopr; "IID_IRdpVideoProcessor"
0x180014035  call    cs:__imp_?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18001403b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014042  cmp     rcx, rbx
0x180014045  jz      loc_180014100
0x18001404b  test    byte ptr [rcx+1Ch], 8
0x18001404f  jz      loc_180014100
0x180014055  cmp     byte ptr [rcx+19h], 2
0x180014059  jb      loc_180014100
0x18001405f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180014064  mov     edx, 40h ; '@'
0x180014069  lea     rcx, aSetvideohintFa_1; "SetVideoHint() failed"
0x180014070  mov     [rsp+500h+var_4D8], edi
0x180014074  lea     r8, WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids
0x18001407b  mov     [rsp+500h+var_4E0], rcx
0x180014080  mov     r9d, eax
0x180014083  mov     rcx, cs:WPP_GLOBAL_Control
0x18001408a  mov     rcx, [rcx+10h]
0x18001408e  call    WPP_SF_DsD
0x180014093  jmp     short loc_180014100
0x180014095  lea     rcx, [rdi-10h]; this
0x180014099  call    ?ShutdownVideoPresentation@CRDPVideoBitmapPresentationManager@@EEAAJXZ; CRDPVideoBitmapPresentationManager::ShutdownVideoPresentation(void)
0x18001409e  mov     edi, eax
0x1800140a0  test    eax, eax
0x1800140a2  jns     short loc_180014100
0x1800140a4  mov     r9d, eax
0x1800140a7  lea     rdx, aVideobitmappre_2; "VideoBitmapPresentationManagerError_Not"...
0x1800140ae  mov     r8d, 333h
0x1800140b4  lea     rcx, aIidIrdpvideopr; "IID_IRdpVideoProcessor"
0x1800140bb  call    cs:__imp_?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800140c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140c8  cmp     rcx, rbx
0x1800140cb  jz      short loc_180014100
0x1800140cd  test    byte ptr [rcx+1Ch], 8
0x1800140d1  jz      short loc_180014100
0x1800140d3  cmp     byte ptr [rcx+19h], 2
0x1800140d7  jb      short loc_180014100
0x1800140d9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800140de  mov     edx, 41h ; 'A'
0x1800140e3  lea     rcx, aShutdownvideop; "ShutdownVideoPresentation() failed"
0x1800140ea  jmp     short loc_180014070
0x1800140ec  test    rbx, rbx
0x1800140ef  jz      short loc_180014100
0x1800140f1  cmp     [rbx+8], r14d
0x1800140f5  jz      short loc_180014100
0x1800140f7  mov     rcx, [rbx]
0x1800140fa  call    cs:__imp_PAL_System_CritSecLeave
0x180014100  mov     rcx, [rbp+400h+var_40]
0x180014107  xor     rcx, rsp; StackCookie
0x18001410a  call    __security_check_cookie
0x18001410f  mov     rbx, [rsp+500h+arg_8]
0x180014117  add     rsp, 4D0h
0x18001411e  pop     r15
0x180014120  pop     r14
0x180014122  pop     r13
0x180014124  pop     r12
0x180014126  pop     rdi
0x180014127  pop     rsi
0x180014128  pop     rbp
0x180014129  retn
```
