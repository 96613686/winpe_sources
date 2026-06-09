# CDoc::SwitchDualEngineIfNeeded(IUri *,ushort const *,unsigned __int64,CWindow *,CDwnBindInfo *)

- ea: `0x1808c99d0`
- end: `0x1808c9c62`
- name: `?SwitchDualEngineIfNeeded@CDoc@@QEAA_NPEAUIUri@@PEBG_KPEAVCWindow@@PEAVCDwnBindInfo@@@Z`
- size: `658`
- prototype: `bool __usercall@<al>(CDoc *__hidden this@<rcx>, IUri *pIUri@<rdx>, const unsigned __int16 *@<r8>, unsigned __int64@<r9>, struct CWindow *, struct CDwnBindInfo *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1804f8bf0`
- `0x1809677a0`
- `0x180b42018`

## callees

- `0x1801af6e0`
- `0x1801b0510`
- `0x1802cb2a4`
- `0x1804dc754`
- `0x18066d6c4`
- `0x1808c5fd4`
- `0x1808c75a0`
- `0x1808c7f40`
- `0x1808c8800`
- `0x1808c99d0`
- `0x1810849a4`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1808c9b39`
- `KERNEL32!GetCurrentThreadId` at `0x1808c9b39`
- `iertutil!CreateIUriBuilder` at `0x1808c9a43`
- `iertutil!CreateIUriBuilder` at `0x1808c9a43`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1808c9b10`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1808c9b10`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808c99f3`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808c9b01`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808c9b2a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808c9b89`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808c99f3`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808c9b01`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808c9b2a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808c9b89`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1808c9b83`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1808c9b83`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1808c9b6b`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1808c9b6b`

## pseudocode

```c
char __fastcall CDoc::SwitchDualEngineIfNeeded(
        CDoc *this,
        IUri *pIUri,
        const unsigned __int16 *a3,
        unsigned __int64 a4,
        CMarkup **a5,
        struct CDwnBindInfo *a6)
{
  char v10; // r13
  IUriBuilder **v11; // rax
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, __int64, _QWORD, _QWORD, __int64); // rbx
  __int64 v14; // rax
  int v15; // ebx
  char IsFrameSharedMemoryFlagSetForCurrentThread; // r12
  unsigned int v17; // r15d
  char v18; // di
  DWORD CurrentThreadId; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  struct IUri *v22; // rbx
  int v23; // eax
  int v25; // [rsp+20h] [rbp-38h]
  __int64 v26; // [rsp+30h] [rbp-28h] BYREF
  __int64 v27; // [rsp+38h] [rbp-20h] BYREF
  struct IUri *v28; // [rsp+40h] [rbp-18h] BYREF
  struct CMarkup *v29[2]; // [rsp+48h] [rbp-10h] BYREF

  v10 = 0;
  if ( IsDualEngineProcess() && (*((_DWORD *)this + 1217) & 0x800) == 0 )
  {
    TSmartPointer<CTransitionTimeValueDefinition>::TSmartPointer<CTransitionTimeValueDefinition>(&v28, pIUri);
    if ( a3 )
    {
      v27 = 0;
      v11 = (IUriBuilder **)TSmartPointer<ID3D11Device>::operator&(&v27);
      if ( CreateIUriBuilder(pIUri, 0, 0, v11) >= 0
        && (*(int (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v27 + 128LL))(v27, a3) >= 0 )
      {
        v12 = v27;
        v26 = 0;
        v13 = *(int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v27 + 32LL);
        v14 = TSmartPointer<ID3D11Device>::operator&(&v26);
        if ( v13(v12, 0xFFFFFFFFLL, 0, 0, v14) >= 0 )
          TSmartPointer<ID2D1Bitmap>::operator=<ID2D1Bitmap1>(&v28, &v26);
        TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&v26);
      }
      TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&v27);
    }
    if ( (a4 & 0x40000) != 0 )
    {
      v15 = 2;
    }
    else if ( (a4 & 0x80u) == 0LL )
    {
      v15 = 4;
      if ( (a4 & 4) != 0 && ((*((_BYTE *)this + 4872) & 0x20) != 0 || (a4 & 0x8000000000LL) != 0) )
        v15 = 3;
    }
    else
    {
      v15 = 1;
    }
    IsFrameSharedMemoryFlagSetForCurrentThread = 0;
    if ( IsDualEngineProcess() && (unsigned __int8)IEConfiguration_GetBool(268435541) )
      IsFrameSharedMemoryFlagSetForCurrentThread = DualEngine::Internal::IsFrameSharedMemoryFlagSetForCurrentThread(256);
    v17 = 0;
    v18 = 0;
    if ( IsDualEngineProcess() )
    {
      LODWORD(v26) = 0;
      CurrentThreadId = GetCurrentThreadId();
      if ( (int)DualEngine::Internal::GetFrameCompForThread(CurrentThreadId, &v26) >= 0 )
      {
        LODWORD(v27) = 0;
        v29[0] = 0;
        if ( (int)IsoGetTrustSplitComponent(v26, 2u, 0, (unsigned int *)&v27, v29) >= 0 )
        {
          v17 = *((_DWORD *)v29[0] + 33);
          IsoUnlockArtifact(v27);
        }
      }
    }
    if ( IsDualEngineProcess() )
      v18 = DualEngine::Internal::IsFrameSharedMemoryFlagSetForCurrentThread(128);
    v25 = v15;
    LOBYTE(v21) = IsFrameSharedMemoryFlagSetForCurrentThread;
    v22 = v28;
    LOBYTE(v20) = v18;
    if ( !(unsigned __int8)DualEngine::ShouldUriContinueNavigationInEdge(v28, v20, v17, v21, v25) )
      goto LABEL_36;
    if ( *((int *)this + 1214) < 0 )
      a4 = a4 & 0xFFFFFFFFF3BFFFFFuLL | 0x4400000;
    if ( (a4 & 0x400000) != 0 )
    {
      v23 = CDoc::DualEngineOpenURLInEdge(this, v22, a4, (struct CWindow *)a5, a6);
    }
    else
    {
      v29[0] = 0;
      if ( (int)CMarkup::GetNextLevelUpMarkup(a5[13], v29) < 0 || v29[0] != a5[13] )
        goto LABEL_35;
      v23 = CDoc::ContinueDualEngineNavigationInEdge(this, v22, 1, a6);
    }
    if ( v23 == -2147467262 )
    {
LABEL_36:
      TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&v28);
      return v10;
    }
LABEL_35:
    ++*((_DWORD *)this + 1397);
    v10 = 1;
    goto LABEL_36;
  }
  return v10;
}

```

## disassembly

```asm
0x1808c99d0  push    rbp
0x1808c99d2  push    rbx
0x1808c99d3  push    rsi
0x1808c99d4  push    rdi
0x1808c99d5  push    r12
0x1808c99d7  push    r13
0x1808c99d9  push    r14
0x1808c99db  push    r15
0x1808c99dd  mov     rbp, rsp
0x1808c99e0  sub     rsp, 58h
0x1808c99e4  mov     rsi, r9
0x1808c99e7  mov     rdi, r8
0x1808c99ea  mov     rbx, rdx
0x1808c99ed  mov     r14, rcx
0x1808c99f0  xor     r13b, r13b
0x1808c99f3  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1808c99f9  test    al, al
0x1808c99fb  jz      loc_1808C9C4E
0x1808c9a01  test    dword ptr [r14+1304h], 800h
0x1808c9a0c  jnz     loc_1808C9C4E
0x1808c9a12  mov     rdx, rbx
0x1808c9a15  lea     rcx, [rbp+var_18]
0x1808c9a19  call    ??0?$TSmartPointer@VCTransitionTimeValueDefinition@@@@QEAA@PEAVCTransitionTimeValueDefinition@@@Z; TSmartPointer<CTransitionTimeValueDefinition>::TSmartPointer<CTransitionTimeValueDefinition>(CTransitionTimeValueDefinition *)
0x1808c9a1e  test    rdi, rdi
0x1808c9a21  jz      loc_1808C9ABF
0x1808c9a27  lea     rcx, [rbp+var_20]
0x1808c9a2b  mov     [rbp+var_20], 0
0x1808c9a33  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1808c9a38  mov     r9, rax; ppIUriBuilder
0x1808c9a3b  xor     r8d, r8d; dwReserved
0x1808c9a3e  xor     edx, edx; dwFlags
0x1808c9a40  mov     rcx, rbx; pIUri
0x1808c9a43  call    cs:__imp_CreateIUriBuilder
0x1808c9a49  test    eax, eax
0x1808c9a4b  js      short loc_1808C9AB6
0x1808c9a4d  mov     rcx, [rbp+var_20]
0x1808c9a51  mov     rdx, rdi
0x1808c9a54  mov     rax, [rcx]
0x1808c9a57  mov     rax, [rax+80h]
0x1808c9a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c9a63  test    eax, eax
0x1808c9a65  js      short loc_1808C9AB6
0x1808c9a67  mov     rdi, [rbp+var_20]
0x1808c9a6b  lea     rcx, [rbp+var_28]
0x1808c9a6f  mov     [rbp+var_28], 0
0x1808c9a77  mov     rax, [rdi]
0x1808c9a7a  mov     rbx, [rax+20h]
0x1808c9a7e  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1808c9a83  mov     qword ptr [rsp+58h+var_38], rax
0x1808c9a88  xor     r9d, r9d
0x1808c9a8b  mov     rax, rbx
0x1808c9a8e  xor     r8d, r8d
0x1808c9a91  or      edx, 0FFFFFFFFh
0x1808c9a94  mov     rcx, rdi
0x1808c9a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c9a9c  test    eax, eax
0x1808c9a9e  js      short loc_1808C9AAD
0x1808c9aa0  lea     rdx, [rbp+var_28]
0x1808c9aa4  lea     rcx, [rbp+var_18]
0x1808c9aa8  call    ??$?4UID2D1Bitmap1@@@?$TSmartPointer@UID2D1Bitmap@@@@QEAAAEBV0@AEBV?$TSmartPointer@UID2D1Bitmap1@@@@@Z; TSmartPointer<ID2D1Bitmap>::operator=<ID2D1Bitmap1>(TSmartPointer<ID2D1Bitmap1> const &)
0x1808c9aad  lea     rcx, [rbp+var_28]; void *
0x1808c9ab1  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1808c9ab6  lea     rcx, [rbp+var_20]; void *
0x1808c9aba  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1808c9abf  bt      rsi, 12h
0x1808c9ac4  jnb     short loc_1808C9ACD
0x1808c9ac6  mov     ebx, 2
0x1808c9acb  jmp     short loc_1808C9AFE
0x1808c9acd  test    sil, sil
0x1808c9ad0  jns     short loc_1808C9AD9
0x1808c9ad2  mov     ebx, 1
0x1808c9ad7  jmp     short loc_1808C9AFE
0x1808c9ad9  mov     ebx, 4
0x1808c9ade  test    bl, sil
0x1808c9ae1  jz      short loc_1808C9AFE
0x1808c9ae3  test    byte ptr [r14+1308h], 20h
0x1808c9aeb  setz    cl
0x1808c9aee  bt      rsi, 27h ; '''
0x1808c9af3  setnb   al
0x1808c9af6  test    al, cl
0x1808c9af8  lea     eax, [rbx-1]
0x1808c9afb  cmovz   ebx, eax
0x1808c9afe  xor     r12b, r12b
0x1808c9b01  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1808c9b07  test    al, al
0x1808c9b09  jz      short loc_1808C9B27
0x1808c9b0b  mov     ecx, 10000055h
0x1808c9b10  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1808c9b16  test    al, al
0x1808c9b18  jz      short loc_1808C9B27
0x1808c9b1a  mov     ecx, 100h
0x1808c9b1f  call    DualEngine__Internal__IsFrameSharedMemoryFlagSetForCurrentThread
0x1808c9b24  mov     r12b, al
0x1808c9b27  xor     r15d, r15d
0x1808c9b2a  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1808c9b30  xor     edi, edi
0x1808c9b32  test    al, al
0x1808c9b34  jz      short loc_1808C9B89
0x1808c9b36  mov     dword ptr [rbp+var_28], edi
0x1808c9b39  call    cs:__imp_GetCurrentThreadId
0x1808c9b3f  mov     ecx, eax
0x1808c9b41  lea     rdx, [rbp+var_28]
0x1808c9b45  call    DualEngine__Internal__GetFrameCompForThread
0x1808c9b4a  test    eax, eax
0x1808c9b4c  js      short loc_1808C9B89
0x1808c9b4e  mov     ecx, dword ptr [rbp+var_28]
0x1808c9b51  lea     rax, [rbp+var_10]
0x1808c9b55  lea     r9, [rbp+var_20]
0x1808c9b59  mov     qword ptr [rsp+58h+var_38], rax
0x1808c9b5e  xor     r8d, r8d
0x1808c9b61  mov     dword ptr [rbp+var_20], edi
0x1808c9b64  lea     edx, [rdi+2]
0x1808c9b67  mov     [rbp+var_10], rdi
0x1808c9b6b  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x1808c9b71  test    eax, eax
0x1808c9b73  js      short loc_1808C9B89
0x1808c9b75  mov     rax, [rbp+var_10]
0x1808c9b79  mov     r15d, [rax+84h]
0x1808c9b80  mov     ecx, dword ptr [rbp+var_20]
0x1808c9b83  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1808c9b89  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1808c9b8f  test    al, al
0x1808c9b91  jz      short loc_1808C9BA0
0x1808c9b93  mov     ecx, 80h
0x1808c9b98  call    DualEngine__Internal__IsFrameSharedMemoryFlagSetForCurrentThread
0x1808c9b9d  mov     dil, al
0x1808c9ba0  mov     [rsp+58h+var_38], ebx
0x1808c9ba4  mov     r9b, r12b
0x1808c9ba7  mov     rbx, [rbp+var_18]
0x1808c9bab  mov     r8d, r15d
0x1808c9bae  mov     rcx, rbx
0x1808c9bb1  mov     dl, dil
0x1808c9bb4  call    ?ShouldUriContinueNavigationInEdge@DualEngine@@YA_NPEAUIUri@@_NW4__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0024@@1W4DualEngineNavigationType@1@@Z; DualEngine::ShouldUriContinueNavigationInEdge(IUri *,bool,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0024,bool,DualEngine::DualEngineNavigationType)
0x1808c9bb9  test    al, al
0x1808c9bbb  jz      loc_1808C9C45
0x1808c9bc1  cmp     dword ptr [r14+12F8h], 0
0x1808c9bc9  jge     short loc_1808C9BD7
0x1808c9bcb  btr     rsi, 1Bh
0x1808c9bd0  or      rsi, 4400000h
0x1808c9bd7  bt      rsi, 16h
0x1808c9bdc  jnb     short loc_1808C9BFB
0x1808c9bde  mov     rax, [rbp+arg_28]
0x1808c9be2  mov     r8, rsi; unsigned __int64
0x1808c9be5  mov     r9, [rbp+arg_20]; struct CWindow *
0x1808c9be9  mov     rdx, rbx; struct IUri *
0x1808c9bec  mov     rcx, r14; this
0x1808c9bef  mov     qword ptr [rsp+58h+var_38], rax; struct CDwnBindInfo *
0x1808c9bf4  call    ?DualEngineOpenURLInEdge@CDoc@@QEAAJPEAUIUri@@_KPEAVCWindow@@PEAVCDwnBindInfo@@@Z; CDoc::DualEngineOpenURLInEdge(IUri *,unsigned __int64,CWindow *,CDwnBindInfo *)
0x1808c9bf9  jmp     short loc_1808C9C34
0x1808c9bfb  mov     rdi, [rbp+arg_20]
0x1808c9bff  lea     rdx, [rbp+var_10]; struct CMarkup **
0x1808c9c03  mov     [rbp+var_10], 0
0x1808c9c0b  mov     rcx, [rdi+68h]; this
0x1808c9c0f  call    ?GetNextLevelUpMarkup@CMarkup@@QEAAJPEAPEAV1@@Z; CMarkup::GetNextLevelUpMarkup(CMarkup * *)
0x1808c9c14  test    eax, eax
0x1808c9c16  js      short loc_1808C9C3B
0x1808c9c18  mov     rax, [rdi+68h]
0x1808c9c1c  cmp     [rbp+var_10], rax
0x1808c9c20  jnz     short loc_1808C9C3B
0x1808c9c22  mov     r9, [rbp+arg_28]; struct CDwnBindInfo *
0x1808c9c26  mov     r8b, 1; bool
0x1808c9c29  mov     rdx, rbx; struct IUri *
0x1808c9c2c  mov     rcx, r14; this
0x1808c9c2f  call    ?ContinueDualEngineNavigationInEdge@CDoc@@QEAAJPEAUIUri@@_NPEAVCDwnBindInfo@@@Z; CDoc::ContinueDualEngineNavigationInEdge(IUri *,bool,CDwnBindInfo *)
0x1808c9c34  cmp     eax, 80004002h
0x1808c9c39  jz      short loc_1808C9C45
0x1808c9c3b  inc     dword ptr [r14+15D4h]
0x1808c9c42  mov     r13b, 1
0x1808c9c45  lea     rcx, [rbp+var_18]; void *
0x1808c9c49  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1808c9c4e  mov     al, r13b
0x1808c9c51  add     rsp, 58h
0x1808c9c55  pop     r15
0x1808c9c57  pop     r14
0x1808c9c59  pop     r13
0x1808c9c5b  pop     r12
0x1808c9c5d  pop     rdi
0x1808c9c5e  pop     rsi
0x1808c9c5f  pop     rbx
0x1808c9c60  pop     rbp
0x1808c9c61  retn
```
