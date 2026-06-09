# CGlobalSurfaceManager::ProcessLegacyTokens(void)

- ea: `0x180131690`
- end: `0x180131bdc`
- name: `?ProcessLegacyTokens@CGlobalSurfaceManager@@AEAAJXZ`
- size: `1356`
- prototype: `__int64 __fastcall(CGlobalSurfaceManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180130320`

## callees

- `0x180050270`
- `0x180051680`
- `0x1800517e0`
- `0x1800cc950`
- `0x180131690`
- `0x180131be4`
- `0x180131dc0`
- `0x1801324d0`
- `0x180188fb8`
- `0x1801cc46c`
- `0x1802284b0`

## import_xrefs

- `win32u!NtDCompositionGetFrameLegacyTokens` at `0x180131784`
- `win32u!NtDCompositionGetFrameLegacyTokens` at `0x180131a78`
- `win32u!NtDCompositionGetFrameLegacyTokens` at `0x180131784`
- `win32u!NtDCompositionGetFrameLegacyTokens` at `0x180131a78`

## pseudocode

```c
__int64 __fastcall CGlobalSurfaceManager::ProcessLegacyTokens(CGlobalSurfaceManager *this, __int64 a2, __int64 a3)
{
  int v4; // r14d
  int v5; // r13d
  _QWORD *v6; // rax
  __int128 v7; // rdi
  unsigned int *v8; // r8
  int v9; // edi
  __int64 v10; // rcx
  int FrameLegacyTokens; // eax
  unsigned int *v12; // r8
  int v13; // esi
  unsigned int v14; // eax
  __int64 v15; // r12
  unsigned int j; // esi
  int v18; // eax
  char *v19; // rax
  CGdiSpriteBitmap *TargetResource; // rax
  unsigned int i; // esi
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // r13d
  int v26; // eax
  bool v27; // r12
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  bool v32[4]; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v33; // [rsp+3Ch] [rbp-CCh] BYREF
  int v34; // [rsp+40h] [rbp-C8h] BYREF
  int v35; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B8h] BYREF
  void *v37; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v38; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v39; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+78h] [rbp-90h]
  _BYTE v41[16]; // [rsp+80h] [rbp-88h] BYREF
  void **v42; // [rsp+90h] [rbp-78h]
  __int64 v43; // [rsp+98h] [rbp-70h]
  void **v44; // [rsp+A0h] [rbp-68h]
  __int64 v45; // [rsp+A8h] [rbp-60h]
  _QWORD v46[2]; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v47[2]; // [rsp+C0h] [rbp-48h] BYREF
  char v48; // [rsp+D0h] [rbp-38h] BYREF
  int *v49; // [rsp+E0h] [rbp-28h]
  __int64 v50; // [rsp+E8h] [rbp-20h]
  int *v51; // [rsp+F0h] [rbp-18h]
  __int64 v52; // [rsp+F8h] [rbp-10h]

  v4 = 0;
  v5 = 0;
  v33 = 0;
  v35 = 0;
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      &EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_Start,
      a3,
      1,
      v46);
  v6 = (_QWORD *)((char *)this + 384);
  v40 = 0;
  v39 = 0;
  if ( &v39 != (__int128 *)((char *)this + 384) )
  {
    *(_QWORD *)&v7 = *v6;
    *v6 = 0;
    *((_QWORD *)&v7 + 1) = *((_QWORD *)this + 49);
    *((_QWORD *)this + 49) = 0;
    v40 = *((_QWORD *)this + 50);
    v39 = v7;
    for ( *((_QWORD *)this + 50) = 0; (_QWORD)v7 != *((_QWORD *)&v7 + 1); *(_QWORD *)&v7 = v7 + 8 )
    {
      TargetResource = (CGdiSpriteBitmap *)CWeakReference<CGdiSpriteBitmap>::GetTargetResource(*(_QWORD *)v7);
      if ( TargetResource )
      {
        *((_BYTE *)TargetResource + 153) = 1;
        CGdiSpriteBitmap::EnsureBitmapRealization(TargetResource);
      }
    }
  }
  std::vector<wil::com_ptr_t<CWeakReference<CGdiSpriteBitmap>,wil::err_returncode_policy>>::_Tidy(&v39);
  v9 = 0;
  if ( *((_DWORD *)this + 70) )
  {
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Dwm_Core_Provider_Context, "^", v8, 1, v46);
    for ( i = 0; i < *((_DWORD *)this + 70); ++i )
    {
      v22 = *((_QWORD *)this + 32);
      v23 = 16LL * i;
      v32[0] = 0;
      ++*(_DWORD *)(v23 + v22);
      v24 = *((_QWORD *)this + 32);
      v25 = *(_DWORD *)(v23 + v24);
      v37 = *(void **)(v23 + v24 + 8);
      v26 = CLegacySurfaceManager::ProcessToken(
              (CGlobalSurfaceManager *)((char *)this + 152),
              (const struct _D3DKMT_PRESENTHISTORYTOKEN *)v37,
              v8,
              v32);
      v9 = v26;
      if ( v26 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v26, 0x110u, 0);
        break;
      }
      v27 = v32[0];
      if ( v32[0] || v25 > 0x64 )
      {
        v30 = DynArray<ClipPlaneIterator::LineSegment,0>::RemoveAt((char *)this + 256, i);
        v9 = v30;
        if ( v30 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v30, 0x118u, 0);
          break;
        }
        operator delete(v37);
        if ( !v27 )
          ++*((_DWORD *)this + 63);
        --i;
      }
    }
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Dwm_Core_Provider_Context,
        &EVTDESC_MILEVENT_MEDIA_UCE_PROCESSDEFERREDTOKENS_Stop,
        v8,
        1,
        v47);
    if ( v9 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v9, 0xF0u, 0);
      v5 = 0;
      goto LABEL_15;
    }
    v5 = 0;
  }
  v10 = 0;
  if ( g_pComposition )
    v10 = *((_QWORD *)g_pComposition + 110);
  v47[0] = v10;
  FrameLegacyTokens = NtDCompositionGetFrameLegacyTokens(v47, &v33, &v35);
  if ( FrameLegacyTokens < 0 )
  {
    v13 = FrameLegacyTokens | 0x10000000;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, FrameLegacyTokens | 0x10000000, 0x1Du, 0);
  }
  else
  {
    v13 = 0;
  }
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
  {
    v38 = v33;
    v49 = &v34;
    v51 = (int *)&v38;
    v19 = &v48;
    v34 = v13;
    v50 = 4;
    v52 = 4;
LABEL_22:
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      &EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_GetPresentHistory,
      v12,
      3,
      v19);
  }
  while ( 1 )
  {
    *((_DWORD *)this + 62) = v13;
    if ( v13 < 0 )
      break;
    v14 = v33;
    v4 += v33;
    v15 = *((_QWORD *)this + 13);
    for ( j = 0; j < v14; ++j )
    {
      v32[0] = 0;
      v18 = CLegacySurfaceManager::ProcessToken(
              (CGlobalSurfaceManager *)((char *)this + 152),
              (const struct _D3DKMT_PRESENTHISTORYTOKEN *)v15,
              v12,
              v32);
      v9 = v18;
      if ( v18 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v18, 0x103u, 0);
        goto LABEL_15;
      }
      if ( !v32[0] )
      {
        v31 = CLegacySurfaceManager::AddUnclaimedToken(
                (CGlobalSurfaceManager *)((char *)this + 152),
                (const struct _D3DKMT_PRESENTHISTORYTOKEN *)v15);
        v9 = v31;
        if ( v31 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v31, 0x108u, 0);
          goto LABEL_15;
        }
      }
      v15 += *(unsigned int *)(v15 + 4);
      v14 = v33;
    }
    if ( !v35 )
      break;
    ++v5;
    v28 = 0;
    if ( g_pComposition )
      v28 = *((_QWORD *)g_pComposition + 110);
    v46[0] = v28;
    v29 = NtDCompositionGetFrameLegacyTokens(v46, &v33, &v35);
    if ( v29 < 0 )
    {
      v13 = v29 | 0x10000000;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v29 | 0x10000000, 0x1Du, 0);
    }
    else
    {
      v13 = 0;
    }
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    {
      LODWORD(v37) = v33;
      v42 = (void **)&v36;
      v44 = &v37;
      v19 = v41;
      LODWORD(v36) = v13;
      v43 = 4;
      v45 = 4;
      goto LABEL_22;
    }
  }
LABEL_15:
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
  {
    LODWORD(v36) = v5;
    v42 = &v37;
    LODWORD(v37) = v4;
    v44 = (void **)&v36;
    v43 = 4;
    v45 = 4;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      &EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_Stop,
      v12,
      3,
      v41);
  }
  dword_1803BADFC += v4;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180131690  mov     r11, rsp
0x180131693  push    rbp
0x180131694  push    r12
0x180131696  push    r13
0x180131698  push    r14
0x18013169a  lea     rbp, [r11-28h]
0x18013169e  sub     rsp, 108h
0x1801316a5  mov     rax, cs:__security_cookie
0x1801316ac  xor     rax, rsp
0x1801316af  mov     [rbp+20h+var_28], rax
0x1801316b3  xor     r12d, r12d
0x1801316b6  mov     [r11+10h], rbx
0x1801316ba  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1801316c1  mov     rbx, rcx
0x1801316c4  mov     [r11-28h], r15
0x1801316c8  mov     r14d, r12d
0x1801316cb  mov     r13d, r12d
0x1801316ce  mov     [rsp+120h+var_EC], r12d
0x1801316d3  mov     [rsp+120h+var_E0], r12d
0x1801316d8  jnz     loc_1801318A7
0x1801316de  lea     rax, [rbx+180h]
0x1801316e5  mov     [rsp+120h+arg_10], rsi
0x1801316ed  lea     rcx, [rsp+120h+var_C8+8]
0x1801316f2  mov     [rsp+120h+arg_18], rdi
0x1801316fa  mov     [rsp+120h+var_B0], r12
0x1801316ff  xorps   xmm0, xmm0
0x180131702  movdqu  [rsp+120h+var_C8+8], xmm0
0x180131708  cmp     rcx, rax
0x18013170b  jz      short loc_18013173B
0x18013170d  mov     rdi, [rax]
0x180131710  mov     [rax], r12
0x180131713  mov     rsi, [rax+8]
0x180131717  mov     [rax+8], r12
0x18013171b  mov     rcx, [rax+10h]
0x18013171f  mov     [rsp+120h+var_B0], rcx
0x180131724  mov     qword ptr [rsp+120h+var_C8+8], rdi
0x180131729  mov     [rsp+120h+var_B8], rsi
0x18013172e  mov     [rax+10h], r12
0x180131732  cmp     rdi, rsi
0x180131735  jnz     loc_180131923
0x18013173b  lea     rcx, [rsp+120h+var_C8+8]
0x180131740  call    ?_Tidy@?$vector@V?$com_ptr_t@V?$CWeakReference@VCGdiSpriteBitmap@@@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@V?$CWeakReference@VCGdiSpriteBitmap@@@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<CWeakReference<CGdiSpriteBitmap>,wil::err_returncode_policy>>::_Tidy(void)
0x180131745  lea     r15, [rbx+98h]
0x18013174c  mov     edi, r12d
0x18013174f  cmp     [r15+80h], r12d
0x180131756  ja      loc_180131975
0x18013175c  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x180131763  mov     rcx, r12
0x180131766  test    rax, rax
0x180131769  jz      short loc_180131772
0x18013176b  mov     rcx, [rax+370h]
0x180131772  mov     [rbp+20h+var_68], rcx
0x180131776  lea     r8, [rsp+120h+var_E0]
0x18013177b  lea     rcx, [rbp+20h+var_68]
0x18013177f  lea     rdx, [rsp+120h+var_EC]
0x180131784  call    cs:__imp_NtDCompositionGetFrameLegacyTokens
0x18013178a  mov     esi, eax
0x18013178c  test    eax, eax
0x18013178e  js      loc_180131B77
0x180131794  mov     esi, r12d
0x180131797  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x18013179e  jnz     loc_1801318CE
0x1801317a4  mov     [rbx+0F8h], esi
0x1801317aa  test    esi, esi
0x1801317ac  js      short loc_1801317CE
0x1801317ae  mov     eax, [rsp+120h+var_EC]
0x1801317b2  add     r14d, eax
0x1801317b5  mov     r12, [rbx+68h]
0x1801317b9  xor     esi, esi
0x1801317bb  cmp     esi, eax
0x1801317bd  jb      loc_18013186A
0x1801317c3  cmp     [rsp+120h+var_E0], 0
0x1801317c8  jnz     loc_180131A4A
0x1801317ce  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1801317d5  mov     r15, [rsp+100h]
0x1801317dd  mov     rsi, [rsp+120h+arg_10]
0x1801317e5  mov     rbx, [rsp+120h+arg_8]
0x1801317ed  jz      short loc_18013183E
0x1801317ef  lea     rax, [rsp+120h+var_D0]
0x1801317f4  mov     dword ptr [rsp+120h+var_D8], r13d
0x1801317f9  mov     [rbp+20h+var_98], rax
0x1801317fd  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_Stop
0x180131804  lea     rax, [rsp+120h+var_D8]
0x180131809  mov     dword ptr [rsp+120h+var_D0], r14d
0x18013180e  mov     [rbp+20h+var_88], rax
0x180131812  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180131819  lea     rax, [rsp+78h]
0x18013181e  mov     [rbp+20h+var_90], 4
0x180131826  mov     r9d, 3
0x18013182c  mov     qword ptr [rsp+120h+var_100], rax
0x180131831  mov     [rbp+20h+var_80], 4
0x180131839  call    McGenEventWrite_EventWriteTransfer
0x18013183e  add     cs:dword_1803BADFC, r14d
0x180131845  mov     eax, edi
0x180131847  mov     rdi, [rsp+120h+arg_18]
0x18013184f  mov     rcx, [rbp+20h+var_28]
0x180131853  xor     rcx, rsp; StackCookie
0x180131856  call    __security_check_cookie
0x18013185b  add     rsp, 108h
0x180131862  pop     r14
0x180131864  pop     r13
0x180131866  pop     r12
0x180131868  pop     rbp
0x180131869  retn
0x18013186a  lea     r9, [rsp+120h+var_F0]; bool *
0x18013186f  mov     [rsp+120h+var_F0], 0
0x180131874  mov     rdx, r12; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x180131877  mov     rcx, r15; this
0x18013187a  call    ?ProcessToken@CLegacySurfaceManager@@IEAAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@PEAIPEA_N@Z; CLegacySurfaceManager::ProcessToken(_D3DKMT_PRESENTHISTORYTOKEN const *,uint *,bool *)
0x18013187f  mov     edi, eax
0x180131881  test    eax, eax
0x180131883  js      loc_18013194E
0x180131889  cmp     [rsp+120h+var_F0], 0
0x18013188e  jz      loc_180131B4D
0x180131894  mov     eax, [r12+4]
0x180131899  add     r12, rax
0x18013189c  mov     eax, [rsp+120h+var_EC]
0x1801318a0  inc     esi
0x1801318a2  jmp     loc_1801317BB
0x1801318a7  lea     rax, [rbp+20h+var_78]
0x1801318ab  mov     r9d, 1
0x1801318b1  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_Start
0x1801318b8  mov     qword ptr [rsp+120h+var_100], rax
0x1801318bd  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801318c4  call    McGenEventWrite_EventWriteTransfer
0x1801318c9  jmp     loc_1801316DE
0x1801318ce  mov     eax, [rsp+120h+var_EC]
0x1801318d2  mov     dword ptr [rsp+120h+var_C8], eax
0x1801318d6  lea     rax, [rsp+120h+var_E8]
0x1801318db  mov     [rbp+20h+var_48], rax
0x1801318df  lea     rax, [rsp+120h+var_C8]
0x1801318e4  mov     [rbp+20h+var_38], rax
0x1801318e8  lea     rax, [rbp+20h+var_58]
0x1801318ec  mov     [rsp+120h+var_E8], esi
0x1801318f0  mov     [rbp+20h+var_40], 4
0x1801318f8  mov     [rbp+20h+var_30], 4
0x180131900  mov     r9d, 3
0x180131906  mov     qword ptr [rsp+120h+var_100], rax
0x18013190b  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_GetPresentHistory
0x180131912  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180131919  call    McGenEventWrite_EventWriteTransfer
0x18013191e  jmp     loc_1801317A4
0x180131923  mov     rcx, [rdi]
0x180131926  call    ?GetTargetResource@?$CWeakReference@VCGdiSpriteBitmap@@@@QEBAPEAVCGdiSpriteBitmap@@XZ; CWeakReference<CGdiSpriteBitmap>::GetTargetResource(void)
0x18013192b  test    rax, rax
0x18013192e  jz      short loc_18013193F
0x180131930  mov     rcx, rax; this
0x180131933  mov     byte ptr [rax+99h], 1
0x18013193a  call    ?EnsureBitmapRealization@CGdiSpriteBitmap@@AEAA_NXZ; CGdiSpriteBitmap::EnsureBitmapRealization(void)
0x18013193f  add     rdi, 8
0x180131943  cmp     rdi, rsi
0x180131946  jz      loc_18013173B
0x18013194c  jmp     short loc_180131923
0x18013194e  xor     r12d, r12d
0x180131951  mov     [rsp+120h+var_F8], r12; void *
0x180131956  mov     [rsp+120h+var_100], 103h; unsigned int
0x18013195e  mov     r9d, eax; int
0x180131961  xor     r8d, r8d; unsigned int
0x180131964  xor     edx, edx; int *
0x180131966  mov     ecx, 14h; unsigned int
0x18013196b  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180131970  jmp     loc_1801317CE
0x180131975  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x18013197c  jnz     loc_180131AF7
0x180131982  mov     esi, r12d
0x180131985  cmp     esi, [r15+80h]
0x18013198c  jnb     short loc_1801319E9
0x18013198e  mov     rax, [r15+68h]
0x180131992  lea     r9, [rsp+120h+var_F0]; bool *
0x180131997  mov     ecx, esi
0x180131999  shl     rcx, 4
0x18013199d  mov     [rsp+120h+var_F0], r14b
0x1801319a2  inc     dword ptr [rcx+rax]
0x1801319a5  mov     rax, [r15+68h]
0x1801319a9  mov     r13d, [rcx+rax]
0x1801319ad  mov     rax, [rcx+rax+8]
0x1801319b2  mov     rcx, r15; this
0x1801319b5  mov     rdx, rax; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x1801319b8  mov     [rsp+120h+var_D0], rax
0x1801319bd  call    ?ProcessToken@CLegacySurfaceManager@@IEAAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@PEAIPEA_N@Z; CLegacySurfaceManager::ProcessToken(_D3DKMT_PRESENTHISTORYTOKEN const *,uint *,bool *)
0x1801319c2  mov     edi, eax
0x1801319c4  test    eax, eax
0x1801319c6  js      loc_180131AD0
0x1801319cc  movzx   r12d, [rsp+120h+var_F0]
0x1801319d2  test    r12b, r12b
0x1801319d5  jnz     loc_180131B1E
0x1801319db  cmp     r13d, 64h ; 'd'
0x1801319df  ja      loc_180131B1E
0x1801319e5  inc     esi
0x1801319e7  jmp     short loc_180131985
0x1801319e9  xor     r12d, r12d
0x1801319ec  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1801319f3  jz      short loc_180131A17
0x1801319f5  lea     rax, [rbp+20h+var_68]
0x1801319f9  mov     r9d, 1
0x1801319ff  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSDEFERREDTOKENS_Stop
0x180131a06  mov     qword ptr [rsp+120h+var_100], rax
0x180131a0b  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180131a12  call    McGenEventWrite_EventWriteTransfer
0x180131a17  test    edi, edi
0x180131a19  js      short loc_180131A23
0x180131a1b  mov     r13d, r14d
0x180131a1e  jmp     loc_18013175C
0x180131a23  mov     [rsp+120h+var_F8], r12; void *
0x180131a28  mov     r9d, edi; int
0x180131a2b  xor     r8d, r8d; unsigned int
0x180131a2e  mov     [rsp+120h+var_100], 0F0h; unsigned int
0x180131a36  xor     edx, edx; int *
0x180131a38  mov     ecx, 14h; unsigned int
0x180131a3d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180131a42  mov     r13d, r14d
0x180131a45  jmp     loc_1801317CE
0x180131a4a  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x180131a51  xor     r12d, r12d
0x180131a54  inc     r13d
0x180131a57  mov     ecx, r12d
0x180131a5a  test    rax, rax
0x180131a5d  jz      short loc_180131A66
0x180131a5f  mov     rcx, [rax+370h]
0x180131a66  mov     [rbp+20h+var_78], rcx
0x180131a6a  lea     r8, [rsp+120h+var_E0]
0x180131a6f  lea     rcx, [rbp+20h+var_78]
0x180131a73  lea     rdx, [rsp+120h+var_EC]
0x180131a78  call    cs:__imp_NtDCompositionGetFrameLegacyTokens
0x180131a7e  mov     esi, eax
0x180131a80  test    eax, eax
0x180131a82  js      loc_180131B9F
0x180131a88  mov     esi, r12d
0x180131a8b  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x180131a92  jz      loc_1801317A4
0x180131a98  mov     eax, [rsp+120h+var_EC]
0x180131a9c  mov     dword ptr [rsp+120h+var_D0], eax
0x180131aa0  lea     rax, [rsp+120h+var_D8]
0x180131aa5  mov     [rbp+20h+var_98], rax
0x180131aa9  lea     rax, [rsp+120h+var_D0]
0x180131aae  mov     [rbp+20h+var_88], rax
0x180131ab2  lea     rax, [rsp+78h]
0x180131ab7  mov     dword ptr [rsp+120h+var_D8], esi
0x180131abb  mov     [rbp+20h+var_90], 4
0x180131ac3  mov     [rbp+20h+var_80], 4
0x180131acb  jmp     loc_180131900
0x180131ad0  xor     r12d, r12d
0x180131ad3  mov     [rsp+120h+var_F8], r12; void *
0x180131ad8  mov     [rsp+120h+var_100], 110h; unsigned int
0x180131ae0  mov     r9d, eax; int
0x180131ae3  xor     r8d, r8d; unsigned int
0x180131ae6  xor     edx, edx; int *
0x180131ae8  mov     ecx, 14h; unsigned int
0x180131aed  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180131af2  jmp     loc_1801319EC
0x180131af7  lea     rax, [rbp+20h+var_78]
0x180131afb  mov     r9d, 1
0x180131b01  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSDEFERREDTOKENS_Start; "^"
0x180131b08  mov     qword ptr [rsp+120h+var_100], rax
0x180131b0d  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180131b14  call    McGenEventWrite_EventWriteTransfer
0x180131b19  jmp     loc_180131982
0x180131b1e  mov     edx, esi
0x180131b20  lea     rcx, [r15+68h]
0x180131b24  call    ?RemoveAt@?$DynArray@ULineSegment@ClipPlaneIterator@@$0A@@@QEAAJI@Z; DynArray<ClipPlaneIterator::LineSegment,0>::RemoveAt(uint)
0x180131b29  mov     edi, eax
0x180131b2b  test    eax, eax
0x180131b2d  js      loc_180131BC7
0x180131b33  mov     rcx, [rsp+120h+var_D0]; void *
0x180131b38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180131b3d  test    r12b, r12b
0x180131b40  jnz     short loc_180131B46
0x180131b42  inc     dword ptr [r15+64h]
0x180131b46  dec     esi
0x180131b48  jmp     loc_1801319E5
0x180131b4d  mov     rdx, r12; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x180131b50  mov     rcx, r15; this
0x180131b53  call    ?AddUnclaimedToken@CLegacySurfaceManager@@IEAAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@@Z; CLegacySurfaceManager::AddUnclaimedToken(_D3DKMT_PRESENTHISTORYTOKEN const *)
0x180131b58  mov     edi, eax
0x180131b5a  test    eax, eax
0x180131b5c  jns     loc_180131894
0x180131b62  xor     r12d, r12d
0x180131b65  mov     [rsp+120h+var_F8], r12
0x180131b6a  mov     [rsp+120h+var_100], 108h
0x180131b72  jmp     loc_18013195E
0x180131b77  bts     esi, 1Ch
0x180131b7b  mov     [rsp+120h+var_F8], r12; void *
0x180131b80  mov     r9d, esi; int
0x180131b83  mov     [rsp+120h+var_100], 1Dh; unsigned int
0x180131b8b  xor     r8d, r8d; unsigned int
0x180131b8e  xor     edx, edx; int *
0x180131b90  mov     ecx, 14h; unsigned int
0x180131b95  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180131b9a  jmp     loc_180131797
0x180131b9f  bts     esi, 1Ch
0x180131ba3  mov     [rsp+120h+var_F8], r12; void *
0x180131ba8  mov     r9d, esi; int
0x180131bab  mov     [rsp+120h+var_100], 1Dh; unsigned int
0x180131bb3  xor     r8d, r8d; unsigned int
0x180131bb6  xor     edx, edx; int *
0x180131bb8  mov     ecx, 14h; unsigned int
0x180131bbd  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180131bc2  jmp     loc_180131A8B
0x180131bc7  xor     r12d, r12d
0x180131bca  mov     [rsp+120h+var_F8], r12
  ... truncated ...
```
