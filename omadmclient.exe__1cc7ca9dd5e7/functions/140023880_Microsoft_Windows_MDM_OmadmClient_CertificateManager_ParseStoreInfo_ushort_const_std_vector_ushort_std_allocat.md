# Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseStoreInfo(ushort const *,std::vector<ushort *,std::allocator<ushort *>> &,std::vector<ushort *,std::allocator<ushort *>> &)

- ea: `0x140023880`
- end: `0x140023ba4`
- name: `?ParseStoreInfo@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGAEAV?$vector@PEAGV?$allocator@PEAG@std@@@std@@1@Z`
- size: `804`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140022fac`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x14001ea6c`
- `0x140023880`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140023940`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140023940`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023a1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023ab7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023b01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023a1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023ab7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023b01`
- `DMCmnUtils!CopyString` at `0x1400239de`
- `DMCmnUtils!CopyString` at `0x1400239de`
- `DMCmnUtils!InvStrCmpNIW` at `0x1400239b6`
- `DMCmnUtils!InvStrCmpNIW` at `0x1400239b6`
- `DMCmnUtils!InvStrCmpIW` at `0x14002396c`
- `DMCmnUtils!InvStrCmpIW` at `0x140023986`
- `DMCmnUtils!InvStrCmpIW` at `0x140023a63`
- `DMCmnUtils!InvStrCmpIW` at `0x14002396c`
- `DMCmnUtils!InvStrCmpIW` at `0x140023986`
- `DMCmnUtils!InvStrCmpIW` at `0x140023a63`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseStoreInfo(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // r8
  wchar_t *v8; // rax
  HLOCAL v9; // rcx
  const unsigned __int16 *v10; // r14
  int v11; // eax
  unsigned int v12; // r14d
  HLOCAL v13; // rcx
  const unsigned __int16 **v14; // r14
  const unsigned __int16 **v15; // r15
  HLOCAL v16; // rax
  _QWORD *v17; // rdx
  unsigned int v18; // ebx
  HLOCAL v20; // rcx
  int v21; // [rsp+20h] [rbp-A8h]
  unsigned int v22; // [rsp+30h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-90h] BYREF
  _QWORD v24[3]; // [rsp+40h] [rbp-88h] BYREF
  int v25; // [rsp+58h] [rbp-70h]
  unsigned int *v26; // [rsp+60h] [rbp-68h]
  HLOCAL v27; // [rsp+68h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+70h] [rbp-58h] BYREF
  HLOCAL *p_hMem; // [rsp+80h] [rbp-48h]
  __int64 v30; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v22 = 0;
  v24[0] = 0;
  v24[1] = "ParseStoreInfo";
  v24[2] = COmaDmLogger::GetLogger();
  v25 = 2;
  v26 = &v22;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    LODWORD(hMem) = 54;
    p_hMem = &hMem;
    v30 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v7,
      2u,
      &v28);
  }
  v28.Ptr = (ULONGLONG)&v22;
  LOBYTE(v28.Size) = 1;
  v8 = wcschr(a2, 0x5Cu);
  if ( !v8 )
  {
    LODWORD(v24[0]) = 12042;
LABEL_33:
    HIDWORD(v24[0]) = -2147024809;
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v9, OmaDmClientFunctionReturnValueEvent, 54, v22);
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v24);
    return 2147942487LL;
  }
  v10 = v8 + 1;
  if ( InvStrCmpIW(v8 + 1, L"System") )
  {
    if ( InvStrCmpIW(v10, L"User") )
    {
      LODWORD(v24[0]) = 12043;
      goto LABEL_33;
    }
    a3 = a4;
  }
  if ( a3 && !InvStrCmpNIW(a2, L"MY", 2u) )
  {
    hMem = 0;
    v11 = CopyString(L"MY", 0xFFFFFFFF, (unsigned __int16 **)&hMem);
    v12 = v11;
    v22 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70C,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\certificatemanager.cpp",
        (const char *)(unsigned int)v11,
        v21);
      v13 = hMem;
      if ( hMem )
        LocalFree(hMem);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v13, OmaDmClientFunctionReturnValueEvent, 54, v22);
LABEL_31:
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v24);
      return v12;
    }
    v14 = *(const unsigned __int16 ***)a3;
    v15 = *(const unsigned __int16 ***)(a3 + 8);
    while ( v14 != v15 )
    {
      if ( !InvStrCmpIW(*v14, (const unsigned __int16 *)hMem) )
        goto LABEL_21;
      ++v14;
    }
    v16 = hMem;
    hMem = 0;
    v27 = v16;
    v17 = *(_QWORD **)(a3 + 8);
    if ( v17 == *(_QWORD **)(a3 + 16) )
    {
      try
      {
        std::vector<unsigned short *>::_Emplace_reallocate<unsigned short *>(a3, v17, &v27);
      }
      catch ( std::bad_alloc )
      {
        v22 = -2147024882;
        v20 = hMem;
        if ( hMem )
          LocalFree(hMem);
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          McTemplateU0qq_EventWriteTransfer(v20, OmaDmClientFunctionReturnValueEvent, 54, v22);
        v12 = -2147024882;
        goto LABEL_31;
      }
    }
    else
    {
      *v17 = v16;
      *(_QWORD *)(a3 + 8) += 8LL;
    }
LABEL_21:
    v9 = hMem;
    if ( hMem )
      LocalFree(hMem);
  }
  v18 = v22;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    McTemplateU0qq_EventWriteTransfer(v9, OmaDmClientFunctionReturnValueEvent, 54, v22);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v24);
  return v18;
}

```

## disassembly

```asm
0x140023880  push    rbx
0x140023882  push    rdi
0x140023883  push    r12
0x140023885  push    r14
0x140023887  push    r15
0x140023889  sub     rsp, 0A0h
0x140023890  mov     rax, cs:__security_cookie
0x140023897  xor     rax, rsp
0x14002389a  mov     [rsp+0C8h+var_38], rax
0x1400238a2  mov     r12, r9
0x1400238a5  mov     rdi, r8
0x1400238a8  mov     r15, rdx
0x1400238ab  xor     ebx, ebx
0x1400238ad  mov     [rsp+0C8h+var_98], ebx
0x1400238b1  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x1400238b6  mov     [rsp+0C8h+var_88], rbx
0x1400238bb  lea     rcx, aParsestoreinfo; "ParseStoreInfo"
0x1400238c2  mov     [rsp+0C8h+var_80], rcx
0x1400238c7  mov     [rsp+0C8h+var_78], rax
0x1400238cc  mov     [rsp+0C8h+var_70], 2
0x1400238d4  lea     rax, [rsp+0C8h+var_98]
0x1400238d9  mov     [rsp+0C8h+var_68], rax
0x1400238de  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x1400238e5  jz      short loc_140023929
0x1400238e7  mov     dword ptr [rsp+0C8h+hMem], 36h ; '6'
0x1400238ef  lea     rax, [rsp+0C8h+hMem]
0x1400238f4  mov     [rsp+0C8h+var_48], rax
0x1400238fc  mov     [rsp+0C8h+var_40], 4
0x140023908  lea     rax, [rsp+0C8h+var_58]
0x14002390d  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x140023912  lea     r9d, [rbx+2]
0x140023916  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14002391d  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140023924  call    McGenEventWrite_EventWriteTransfer
0x140023929  lea     rax, [rsp+0C8h+var_98]
0x14002392e  mov     qword ptr [rsp+0C8h+var_58], rax
0x140023933  mov     [rsp+0C8h+var_50], 1
0x140023938  mov     edx, 5Ch ; '\'; Ch
0x14002393d  mov     rcx, r15; Str
0x140023940  call    cs:__imp_wcschr
0x140023947  nop     dword ptr [rax+rax+00h]
0x14002394c  test    rax, rax
0x14002394f  jnz     short loc_14002395E
0x140023951  mov     dword ptr [rsp+0C8h+var_88], 2F0Ah
0x140023959  jmp     loc_140023B4B
0x14002395e  lea     r14, [rax+2]
0x140023962  lea     rdx, aSystem; "System"
0x140023969  mov     rcx, r14
0x14002396c  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x140023973  nop     dword ptr [rax+rax+00h]
0x140023978  test    eax, eax
0x14002397a  jz      short loc_14002399D
0x14002397c  lea     rdx, aUser_1; "User"
0x140023983  mov     rcx, r14
0x140023986  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x14002398d  nop     dword ptr [rax+rax+00h]
0x140023992  test    eax, eax
0x140023994  jnz     loc_140023B43
0x14002399a  mov     rdi, r12
0x14002399d  test    rdi, rdi
0x1400239a0  jz      loc_140023AC3
0x1400239a6  mov     r8d, 2
0x1400239ac  lea     rdx, aMy; "MY"
0x1400239b3  mov     rcx, r15
0x1400239b6  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x1400239bd  nop     dword ptr [rax+rax+00h]
0x1400239c2  test    eax, eax
0x1400239c4  jnz     loc_140023AC3
0x1400239ca  mov     [rsp+0C8h+hMem], rbx
0x1400239cf  lea     r8, [rsp+0C8h+hMem]
0x1400239d4  or      edx, 0FFFFFFFFh
0x1400239d7  lea     rcx, aMy; "MY"
0x1400239de  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1400239e5  nop     dword ptr [rax+rax+00h]
0x1400239ea  mov     r14d, eax
0x1400239ed  mov     [rsp+0C8h+var_98], eax
0x1400239f1  test    eax, eax
0x1400239f3  jns     short loc_140023A52
0x1400239f5  mov     rcx, [rsp+0C8h]; this
0x1400239fd  mov     r9d, eax; char *
0x140023a00  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140023a07  mov     edx, 70Ch; void *
0x140023a0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023a11  nop
0x140023a12  mov     rcx, [rsp+0C8h+hMem]; hMem
0x140023a17  test    rcx, rcx
0x140023a1a  jz      short loc_140023A29
0x140023a1c  call    cs:__imp_LocalFree
0x140023a23  nop     dword ptr [rax+rax+00h]
0x140023a28  nop
0x140023a29  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140023a30  jz      loc_140023B34
0x140023a36  mov     r9d, [rsp+0C8h+var_98]
0x140023a3b  mov     r8d, 36h ; '6'
0x140023a41  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140023a48  call    McTemplateU0qq_EventWriteTransfer
0x140023a4d  jmp     loc_140023B34
0x140023a52  mov     r14, [rdi]
0x140023a55  mov     r15, [rdi+8]
0x140023a59  jmp     short loc_140023A77
0x140023a5b  mov     rdx, [rsp+0C8h+hMem]
0x140023a60  mov     rcx, [r14]
0x140023a63  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x140023a6a  nop     dword ptr [rax+rax+00h]
0x140023a6f  test    eax, eax
0x140023a71  jz      short loc_140023AAD
0x140023a73  add     r14, 8
0x140023a77  cmp     r14, r15
0x140023a7a  jnz     short loc_140023A5B
0x140023a7c  mov     rax, [rsp+0C8h+hMem]
0x140023a81  mov     [rsp+0C8h+hMem], rbx
0x140023a86  mov     [rsp+0C8h+var_60], rax
0x140023a8b  mov     rdx, [rdi+8]
0x140023a8f  cmp     rdx, [rdi+10h]
0x140023a93  jz      short loc_140023A9F
0x140023a95  mov     [rdx], rax
0x140023a98  add     qword ptr [rdi+8], 8
0x140023a9d  jmp     short loc_140023AAD
0x140023a9f  lea     r8, [rsp+0C8h+var_60]
0x140023aa4  mov     rcx, rdi
0x140023aa7  call    ??$_Emplace_reallocate@PEAG@?$vector@PEAGV?$allocator@PEAG@std@@@std@@AEAAPEAPEAGQEAPEAG$$QEAPEAG@Z; std::vector<ushort *>::_Emplace_reallocate<ushort *>(ushort * * const,ushort * &&)
0x140023aac  nop
0x140023aad  mov     rcx, [rsp+0C8h+hMem]; hMem
0x140023ab2  test    rcx, rcx
0x140023ab5  jz      short loc_140023AC3
0x140023ab7  call    cs:__imp_LocalFree
0x140023abe  nop     dword ptr [rax+rax+00h]
0x140023ac3  mov     ebx, [rsp+0C8h+var_98]
0x140023ac7  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140023ace  jz      short loc_140023AE6
0x140023ad0  mov     r9d, ebx
0x140023ad3  mov     r8d, 36h ; '6'
0x140023ad9  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140023ae0  call    McTemplateU0qq_EventWriteTransfer
0x140023ae5  nop
0x140023ae6  lea     rcx, [rsp+0C8h+var_88]; this
0x140023aeb  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x140023af0  mov     eax, ebx
0x140023af2  jmp     loc_140023B83
0x140023af7  mov     rcx, [rsp+0C8h+hMem]; hMem
0x140023afc  test    rcx, rcx
0x140023aff  jz      short loc_140023B0E
0x140023b01  call    cs:__imp_LocalFree
0x140023b08  nop     dword ptr [rax+rax+00h]
0x140023b0d  nop
0x140023b0e  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140023b15  jz      short loc_140023B2E
0x140023b17  mov     r9d, [rsp+0C8h+var_98]
0x140023b1c  mov     r8d, 36h ; '6'
0x140023b22  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140023b29  call    McTemplateU0qq_EventWriteTransfer
0x140023b2e  mov     r14d, 8007000Eh
0x140023b34  lea     rcx, [rsp+0C8h+var_88]; this
0x140023b39  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x140023b3e  mov     eax, r14d
0x140023b41  jmp     short loc_140023B83
0x140023b43  mov     dword ptr [rsp+0C8h+var_88], 2F0Bh
0x140023b4b  mov     dword ptr [rsp+0C8h+var_88+4], 80070057h
0x140023b53  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140023b5a  jz      short loc_140023B74
0x140023b5c  mov     r9d, [rsp+0C8h+var_98]
0x140023b61  mov     r8d, 36h ; '6'
0x140023b67  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140023b6e  call    McTemplateU0qq_EventWriteTransfer
0x140023b73  nop
0x140023b74  lea     rcx, [rsp+0C8h+var_88]; this
0x140023b79  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x140023b7e  mov     eax, 80070057h
0x140023b83  mov     rcx, [rsp+0C8h+var_38]
0x140023b8b  xor     rcx, rsp; StackCookie
0x140023b8e  call    __security_check_cookie
0x140023b93  add     rsp, 0A0h
0x140023b9a  pop     r15
0x140023b9c  pop     r14
0x140023b9e  pop     r12
0x140023ba0  pop     rdi
0x140023ba1  pop     rbx
0x140023ba2  retn
```
