# Microsoft::Windows::MDM::OmadmClient::SyncmlManager::SaveProtoVer(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort const *)

- ea: `0x140045b20`
- end: `0x140045fca`
- name: `?SaveProtoVer@SyncmlManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@PEBG@Z`
- size: `1194`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::SyncmlManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x140045b20`
- `0x1400548a4`
- `0x140054938`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140045c86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140045f53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140045c86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140045f53`
- `DMCmnUtils!CopyString` at `0x140045c46`
- `DMCmnUtils!CopyString` at `0x140045c46`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x140045f67`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x140045f67`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x140045d71`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x140045d71`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x140045c22`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x140045c22`
- `omadmapi!__imp_OmaDmSetValueInStruct` at `0x140045caf`
- `omadmapi!__imp_OmaDmSetValueInStruct` at `0x140045caf`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::SyncmlManager::SaveProtoVer(
        Microsoft::Windows::MDM::OmadmClient::SyncmlManager *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // r8
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  int v12; // r14d
  unsigned int v13; // eax
  __int64 v14; // rax
  __int64 v15; // r14
  int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rcx
  HLOCAL v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v23[3]; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+68h] [rbp-98h]
  int *v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+80h] [rbp-80h] BYREF
  int v27; // [rsp+88h] [rbp-78h]
  __int64 v28; // [rsp+90h] [rbp-70h]
  int v29; // [rsp+98h] [rbp-68h]
  _OWORD v30[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-40h]
  int v32; // [rsp+C8h] [rbp-38h]
  __int64 v33; // [rsp+D0h] [rbp-30h]
  int v34; // [rsp+D8h] [rbp-28h]
  __int64 v35; // [rsp+E0h] [rbp-20h]
  _DWORD v36[128]; // [rsp+F0h] [rbp-10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+2F0h] [rbp+1F0h] BYREF
  HLOCAL *p_hMem; // [rsp+300h] [rbp+200h]
  __int64 v39; // [rsp+308h] [rbp+208h]
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v21 = 0;
  v23[0] = 0;
  v23[1] = "SaveProtoVer";
  v23[2] = COmaDmLogger::GetLogger();
  v24 = 2;
  v25 = &v21;
  memset_0(v36, 0, sizeof(v36));
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    LODWORD(hMem) = 31;
    p_hMem = &hMem;
    v39 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v6,
      2u,
      &v37);
  }
  v37.Ptr = (ULONGLONG)&v21;
  *(_QWORD *)&v37.Size = v36;
  LOBYTE(p_hMem) = 1;
  v36[0] = 512;
  if ( (unsigned int)OmaDmIsNodeValuePresent(21, (char *)a2 + 48) )
    goto LABEL_38;
  hMem = 0;
  v7 = CopyString(a3, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
  v8 = v7;
  v21 = v7;
  if ( v7 < 0 )
  {
    v9 = 976;
LABEL_6:
    v10 = (unsigned int)v7;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\syncmlmanager.cpp",
      (const char *)v10,
      (int)v20);
    goto LABEL_8;
  }
  v20 = hMem;
  v11 = OmaDmSetValueInStruct(21, v36, 0xFFFFFFFFLL);
  v8 = v11;
  v21 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v23[0]) = 21060;
LABEL_12:
    HIDWORD(v23[0]) = v11;
    goto LABEL_8;
  }
  hMem = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _DWORD *))(**((_QWORD **)this + 6) + 48LL))(
          *((_QWORD *)this + 6),
          *(_QWORD *)(*((_QWORD *)a2 + 5) + 16LL),
          *(unsigned int *)(*((_QWORD *)a2 + 5) + 24LL),
          v36);
  v8 = v11;
  v21 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v23[0]) = 21055;
    goto LABEL_12;
  }
  v12 = *((_DWORD *)a2 + 113);
  v11 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 8LL))(
          *((_QWORD *)this + 8),
          (char *)a2 + 48,
          *(_QWORD *)(*((_QWORD *)a2 + 5) + 16LL),
          *(unsigned int *)(*((_QWORD *)a2 + 5) + 24LL));
  v8 = v11;
  v21 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v23[0]) = 21067;
    goto LABEL_12;
  }
  v13 = *((_DWORD *)a2 + 113);
  if ( v13 == v12 || !v13 || v13 > 3 )
  {
LABEL_36:
    if ( hMem )
      LocalFree(hMem);
LABEL_38:
    v8 = v21;
    goto LABEL_39;
  }
  if ( !(unsigned int)OmaDmIsNodePresent(60, (char *)a2 + 48) )
    *((_DWORD *)a2 + 114) = 1;
  if ( !*((_QWORD *)a2 + 58) && !*((_QWORD *)a2 + 59) )
  {
    v8 = -2102656509;
    v21 = -2102656509;
    v10 = 2192310787LL;
    v9 = 1029;
    goto LABEL_7;
  }
  v14 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 32LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
  v7 = (*(__int64 (__fastcall **)(__int64, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *))(*(_QWORD *)v14 + 80LL))(
         v14,
         a2);
  v8 = v7;
  v21 = v7;
  if ( v7 < 0 )
  {
    v9 = 1024;
    goto LABEL_6;
  }
  v26 = 6;
  v27 = 1;
  v28 = 0;
  v29 = 0;
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  if ( !*((_QWORD *)a2 + 250) )
  {
LABEL_35:
    Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo::Reset((Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *)&v26);
    std::vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>::~vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>((char *)v30 + 8);
    goto LABEL_36;
  }
  v15 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 32LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
  LODWORD(v20) = 1;
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *, HLOCAL, __int64 *))(*(_QWORD *)v15 + 8LL))(
          v15,
          *(_QWORD *)(*((_QWORD *)a2 + 5) + 16LL),
          *(unsigned int *)(*((_QWORD *)a2 + 5) + 24LL),
          (char *)a2 + 48,
          v20,
          &v26);
  v8 = v16;
  v21 = v16;
  if ( v16 >= 0 )
  {
    if ( *(_QWORD *)&v30[0] )
      goto LABEL_33;
    Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo::Reset((Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *)&v26);
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *, _DWORD, __int64 *))(*(_QWORD *)v15 + 8LL))(
            v15,
            *(_QWORD *)(*((_QWORD *)a2 + 5) + 16LL),
            *(unsigned int *)(*((_QWORD *)a2 + 5) + 24LL),
            (char *)a2 + 48,
            0,
            &v26);
    v8 = v16;
    v21 = v16;
    if ( v16 < 0 )
      goto LABEL_29;
    if ( *(_QWORD *)&v30[0] )
    {
LABEL_33:
      if ( (unsigned int)(*((_DWORD *)a2 + 113) - 2) <= 1 )
      {
        *((_QWORD *)a2 + 264) = v28;
        v28 = 0;
      }
    }
    goto LABEL_35;
  }
LABEL_29:
  LODWORD(v23[0]) = 18007;
  HIDWORD(v23[0]) = v16;
  Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo::Reset((Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *)&v26);
  std::vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>::~vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>((char *)v30 + 8);
LABEL_8:
  if ( hMem )
    LocalFree(hMem);
LABEL_39:
  v17 = OmaDmFreeAcctInfo(v36);
  v21 = v17;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    McTemplateU0qq_EventWriteTransfer(v18, OmaDmClientFunctionReturnValueEvent, 31, v17);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v23);
  return v8;
}

```

## disassembly

```asm
0x140045b20  mov     [rsp-8+arg_18], rbx
0x140045b25  push    rbp
0x140045b26  push    rsi
0x140045b27  push    rdi
0x140045b28  push    r12
0x140045b2a  push    r13
0x140045b2c  push    r14
0x140045b2e  push    r15
0x140045b30  lea     rbp, [rsp-220h]
0x140045b38  sub     rsp, 320h
0x140045b3f  mov     rax, cs:__security_cookie
0x140045b46  xor     rax, rsp
0x140045b49  mov     [rbp+250h+var_40], rax
0x140045b50  mov     rbx, r8
0x140045b53  mov     rdi, rdx
0x140045b56  mov     r15, rcx
0x140045b59  xor     r12d, r12d
0x140045b5c  mov     [rsp+350h+var_310], r12d
0x140045b61  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140045b66  mov     [rsp+350h+var_300], r12
0x140045b6b  lea     rcx, aSaveprotover; "SaveProtoVer"
0x140045b72  mov     [rsp+350h+var_2F8], rcx
0x140045b77  mov     [rsp+350h+var_2F0], rax
0x140045b7c  lea     r14d, [r12+2]
0x140045b81  mov     [rsp+350h+var_2E8], r14d
0x140045b86  lea     rax, [rsp+350h+var_310]
0x140045b8b  mov     [rsp+350h+var_2E0], rax
0x140045b90  mov     esi, 200h
0x140045b95  mov     r8d, esi; Size
0x140045b98  xor     edx, edx; Val
0x140045b9a  lea     rcx, [rbp+250h+var_260]; void *
0x140045b9e  call    memset_0
0x140045ba3  lea     r13d, [r12+1Fh]
0x140045ba8  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140045baf  jz      short loc_140045BEF
0x140045bb1  mov     dword ptr [rsp+350h+hMem], r13d
0x140045bb6  lea     rax, [rsp+350h+hMem]
0x140045bbb  mov     [rbp+250h+var_50], rax
0x140045bc2  mov     [rbp+250h+var_48], 4
0x140045bcd  lea     rax, [rbp+250h+var_60]
0x140045bd4  mov     qword ptr [rsp+350h+var_330], rax; int
0x140045bd9  mov     r9d, r14d
0x140045bdc  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x140045be3  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140045bea  call    McGenEventWrite_EventWriteTransfer
0x140045bef  lea     rax, [rsp+350h+var_310]
0x140045bf4  mov     qword ptr [rbp+250h+var_60], rax
0x140045bfb  lea     rax, [rbp+250h+var_260]
0x140045bff  mov     [rbp+250h+var_58], rax
0x140045c06  mov     byte ptr [rbp+250h+var_50], 1
0x140045c0d  mov     [rbp+250h+var_260], esi
0x140045c10  lea     rsi, [rdi+30h]
0x140045c14  or      r14d, 0FFFFFFFFh
0x140045c18  mov     r8d, r14d
0x140045c1b  mov     rdx, rsi
0x140045c1e  lea     ecx, [r14+16h]
0x140045c22  call    cs:__imp_OmaDmIsNodeValuePresent
0x140045c29  nop     dword ptr [rax+rax+00h]
0x140045c2e  test    eax, eax
0x140045c30  jnz     loc_140045F5F
0x140045c36  mov     [rsp+350h+hMem], r12
0x140045c3b  lea     r8, [rsp+350h+hMem]
0x140045c40  or      edx, 0FFFFFFFFh
0x140045c43  mov     rcx, rbx
0x140045c46  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140045c4d  nop     dword ptr [rax+rax+00h]
0x140045c52  mov     ebx, eax
0x140045c54  mov     [rsp+350h+var_310], eax
0x140045c58  test    eax, eax
0x140045c5a  jns     short loc_140045C97
0x140045c5c  mov     edx, 3D0h; void *
0x140045c61  mov     r9d, eax; char *
0x140045c64  mov     rcx, [rbp+258h]; this
0x140045c6b  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140045c72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045c77  nop
0x140045c78  mov     rcx, [rsp+350h+hMem]; hMem
0x140045c7d  test    rcx, rcx
0x140045c80  jz      loc_140045F63
0x140045c86  call    cs:__imp_LocalFree
0x140045c8d  nop     dword ptr [rax+rax+00h]
0x140045c92  jmp     loc_140045F63
0x140045c97  mov     rax, [rsp+350h+hMem]
0x140045c9c  mov     qword ptr [rsp+350h+var_330], rax
0x140045ca1  xor     r9d, r9d
0x140045ca4  mov     r8d, r14d
0x140045ca7  lea     rdx, [rbp+250h+var_260]
0x140045cab  lea     ecx, [r9+15h]
0x140045caf  call    cs:__imp_OmaDmSetValueInStruct
0x140045cb6  nop     dword ptr [rax+rax+00h]
0x140045cbb  mov     ebx, eax
0x140045cbd  mov     [rsp+350h+var_310], eax
0x140045cc1  test    eax, eax
0x140045cc3  jns     short loc_140045CD3
0x140045cc5  mov     dword ptr [rsp+350h+var_300], 5244h
0x140045ccd  mov     dword ptr [rsp+350h+var_300+4], eax
0x140045cd1  jmp     short loc_140045C78
0x140045cd3  mov     [rsp+350h+hMem], r12
0x140045cd8  mov     rcx, [r15+30h]
0x140045cdc  mov     rdx, [rdi+28h]
0x140045ce0  mov     rax, [rcx]
0x140045ce3  lea     r9, [rbp+250h+var_260]
0x140045ce7  mov     r8d, [rdx+18h]
0x140045ceb  mov     rdx, [rdx+10h]
0x140045cef  mov     rax, [rax+30h]
0x140045cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045cf8  mov     ebx, eax
0x140045cfa  mov     [rsp+350h+var_310], eax
0x140045cfe  test    eax, eax
0x140045d00  jns     short loc_140045D0C
0x140045d02  mov     dword ptr [rsp+350h+var_300], 523Fh
0x140045d0a  jmp     short loc_140045CCD
0x140045d0c  mov     r14d, [rdi+1C4h]
0x140045d13  mov     rcx, [r15+40h]
0x140045d17  mov     r8, [rdi+28h]
0x140045d1b  mov     rax, [rcx]
0x140045d1e  mov     r9d, [r8+18h]
0x140045d22  mov     r8, [r8+10h]
0x140045d26  mov     rdx, rsi
0x140045d29  mov     rax, [rax+8]
0x140045d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045d32  mov     ebx, eax
0x140045d34  mov     [rsp+350h+var_310], eax
0x140045d38  test    eax, eax
0x140045d3a  jns     short loc_140045D46
0x140045d3c  mov     dword ptr [rsp+350h+var_300], 524Bh
0x140045d44  jmp     short loc_140045CCD
0x140045d46  mov     eax, [rdi+1C4h]
0x140045d4c  cmp     eax, r14d
0x140045d4f  jz      loc_140045F49
0x140045d55  test    eax, eax
0x140045d57  jz      loc_140045F49
0x140045d5d  cmp     eax, 3
0x140045d60  ja      loc_140045F49
0x140045d66  or      r8d, 0FFFFFFFFh
0x140045d6a  mov     rdx, rsi
0x140045d6d  lea     ecx, [r8+3Dh]
0x140045d71  call    cs:__imp_OmaDmIsNodePresent
0x140045d78  nop     dword ptr [rax+rax+00h]
0x140045d7d  test    eax, eax
0x140045d7f  jnz     short loc_140045D8B
0x140045d81  mov     dword ptr [rdi+1C8h], 1
0x140045d8b  cmp     [rdi+1D0h], r12
0x140045d92  jnz     short loc_140045DB3
0x140045d94  cmp     [rdi+1D8h], r12
0x140045d9b  jnz     short loc_140045DB3
0x140045d9d  mov     ebx, 82AC0203h
0x140045da2  mov     [rsp+350h+var_310], ebx
0x140045da6  mov     r9d, ebx
0x140045da9  mov     edx, 405h
0x140045dae  jmp     loc_140045C64
0x140045db3  mov     rcx, cs:?g_pIAbstractFactory@OmadmClient@MDM@Windows@Microsoft@@3PEAVIAbstractFactory@1234@EA; Microsoft::Windows::MDM::OmadmClient::IAbstractFactory * Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory
0x140045dba  mov     rax, [rcx]
0x140045dbd  mov     rax, [rax+20h]
0x140045dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045dc6  mov     r8, rax
0x140045dc9  mov     rcx, [rax]
0x140045dcc  mov     rax, [rcx+50h]
0x140045dd0  mov     rdx, rdi
0x140045dd3  mov     rcx, r8
0x140045dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ddb  mov     ebx, eax
0x140045ddd  mov     [rsp+350h+var_310], eax
0x140045de1  test    eax, eax
0x140045de3  jns     short loc_140045DEF
0x140045de5  mov     edx, 400h
0x140045dea  jmp     loc_140045C61
0x140045def  mov     [rbp+250h+var_2D0], 6
0x140045df7  mov     [rbp+250h+var_2C8], 1
0x140045dfe  mov     [rbp+250h+var_2C0], r12
0x140045e02  mov     [rbp+250h+var_2B8], r12d
0x140045e06  xorps   xmm0, xmm0
0x140045e09  movdqa  [rbp+250h+var_2B0], xmm0
0x140045e0e  xorps   xmm1, xmm1
0x140045e11  movdqa  [rbp+250h+var_2A0], xmm1
0x140045e16  mov     [rbp+250h+var_290], r12
0x140045e1a  mov     [rbp+250h+var_288], r12d
0x140045e1e  mov     [rbp+250h+var_280], r12
0x140045e22  mov     [rbp+250h+var_278], r12d
0x140045e26  mov     [rbp+250h+var_270], r12
0x140045e2a  cmp     [rdi+7D0h], r12
0x140045e31  jz      loc_140045F36
0x140045e37  mov     rcx, cs:?g_pIAbstractFactory@OmadmClient@MDM@Windows@Microsoft@@3PEAVIAbstractFactory@1234@EA; Microsoft::Windows::MDM::OmadmClient::IAbstractFactory * Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory
0x140045e3e  mov     rax, [rcx]
0x140045e41  mov     rax, [rax+20h]
0x140045e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045e4a  mov     r14, rax
0x140045e4d  mov     rdx, [rdi+28h]
0x140045e51  mov     rcx, [rax]
0x140045e54  mov     rax, [rcx+8]
0x140045e58  lea     rcx, [rbp+250h+var_2D0]
0x140045e5c  mov     [rsp+350h+var_328], rcx
0x140045e61  mov     [rsp+350h+var_330], 1
0x140045e69  mov     r9, rsi
0x140045e6c  mov     r8d, [rdx+18h]
0x140045e70  mov     rdx, [rdx+10h]
0x140045e74  mov     rcx, r14
0x140045e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045e7c  mov     ebx, eax
0x140045e7e  mov     [rsp+350h+var_310], eax
0x140045e82  test    eax, eax
0x140045e84  jns     short loc_140045EAA
0x140045e86  mov     dword ptr [rsp+350h+var_300], 4657h
0x140045e8e  mov     dword ptr [rsp+350h+var_300+4], eax
0x140045e92  lea     rcx, [rbp+250h+var_2D0]; this
0x140045e96  call    ?Reset@SslClientCertInfo@OmadmClient@MDM@Windows@Microsoft@@QEAAXXZ; Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo::Reset(void)
0x140045e9b  lea     rcx, [rbp+250h+var_2B0+8]
0x140045e9f  call    ??1?$vector@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@V?$allocator@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>::~vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>(void)
0x140045ea4  nop
0x140045ea5  jmp     loc_140045C78
0x140045eaa  cmp     qword ptr [rbp+250h+var_2B0], r12
0x140045eae  jnz     short loc_140045F19
0x140045eb0  lea     rcx, [rbp+250h+var_2D0]; this
0x140045eb4  call    ?Reset@SslClientCertInfo@OmadmClient@MDM@Windows@Microsoft@@QEAAXXZ; Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo::Reset(void)
0x140045eb9  mov     rdx, [rdi+28h]
0x140045ebd  mov     rax, [r14]
0x140045ec0  lea     rcx, [rbp+250h+var_2D0]
0x140045ec4  mov     [rsp+350h+var_328], rcx
0x140045ec9  mov     [rsp+350h+var_330], r12d
0x140045ece  mov     r9, rsi
0x140045ed1  mov     r8d, [rdx+18h]
0x140045ed5  mov     rdx, [rdx+10h]
0x140045ed9  mov     rcx, r14
0x140045edc  mov     rax, [rax+8]
0x140045ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ee5  mov     ebx, eax
0x140045ee7  mov     [rsp+350h+var_310], eax
0x140045eeb  test    eax, eax
0x140045eed  jns     short loc_140045F13
0x140045eef  mov     dword ptr [rsp+350h+var_300], 4657h
0x140045ef7  mov     dword ptr [rsp+350h+var_300+4], eax
0x140045efb  lea     rcx, [rbp+250h+var_2D0]; this
0x140045eff  call    ?Reset@SslClientCertInfo@OmadmClient@MDM@Windows@Microsoft@@QEAAXXZ; Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo::Reset(void)
0x140045f04  lea     rcx, [rbp+250h+var_2B0+8]
0x140045f08  call    ??1?$vector@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@V?$allocator@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>::~vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>(void)
0x140045f0d  nop
0x140045f0e  jmp     loc_140045C78
0x140045f13  cmp     qword ptr [rbp+250h+var_2B0], r12
0x140045f17  jz      short loc_140045F36
0x140045f19  mov     eax, [rdi+1C4h]
0x140045f1f  sub     eax, 2
0x140045f22  cmp     eax, 1
0x140045f25  ja      short loc_140045F36
0x140045f27  mov     rax, [rbp+250h+var_2C0]
0x140045f2b  mov     [rdi+840h], rax
0x140045f32  mov     [rbp+250h+var_2C0], r12
0x140045f36  lea     rcx, [rbp+250h+var_2D0]; this
0x140045f3a  call    ?Reset@SslClientCertInfo@OmadmClient@MDM@Windows@Microsoft@@QEAAXXZ; Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo::Reset(void)
0x140045f3f  lea     rcx, [rbp+250h+var_2B0+8]
0x140045f43  call    ??1?$vector@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@V?$allocator@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>::~vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>(void)
0x140045f48  nop
0x140045f49  mov     rcx, [rsp+350h+hMem]; hMem
0x140045f4e  test    rcx, rcx
0x140045f51  jz      short loc_140045F5F
0x140045f53  call    cs:__imp_LocalFree
0x140045f5a  nop     dword ptr [rax+rax+00h]
0x140045f5f  mov     ebx, [rsp+350h+var_310]
0x140045f63  lea     rcx, [rbp+250h+var_260]
0x140045f67  call    cs:__imp_OmaDmFreeAcctInfo
0x140045f6e  nop     dword ptr [rax+rax+00h]
0x140045f73  mov     [rsp+350h+var_310], eax
0x140045f77  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140045f7e  jz      short loc_140045F93
0x140045f80  mov     r9d, eax
0x140045f83  mov     r8d, r13d
0x140045f86  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140045f8d  call    McTemplateU0qq_EventWriteTransfer
0x140045f92  nop
0x140045f93  lea     rcx, [rsp+350h+var_300]; this
0x140045f98  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x140045f9d  mov     eax, ebx
0x140045f9f  mov     rcx, [rbp+250h+var_40]
0x140045fa6  xor     rcx, rsp; StackCookie
0x140045fa9  call    __security_check_cookie
0x140045fae  mov     rbx, [rsp+350h+arg_18]
0x140045fb6  add     rsp, 320h
0x140045fbd  pop     r15
0x140045fbf  pop     r14
0x140045fc1  pop     r13
0x140045fc3  pop     r12
0x140045fc5  pop     rdi
0x140045fc6  pop     rsi
0x140045fc7  pop     rbp
0x140045fc8  retn
```
