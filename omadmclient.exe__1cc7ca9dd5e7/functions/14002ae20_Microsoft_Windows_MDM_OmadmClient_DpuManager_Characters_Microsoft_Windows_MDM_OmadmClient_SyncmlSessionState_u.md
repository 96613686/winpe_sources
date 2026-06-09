# Microsoft::Windows::MDM::OmadmClient::DpuManager::Characters(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort const *,uint)

- ea: `0x14002ae20`
- end: `0x14002b024`
- name: `?Characters@DpuManager@OmadmClient@MDM@Windows@Microsoft@@AEAAJAEAVSyncmlSessionState@2345@PEBGI@Z`
- size: `516`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::DpuManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002f3c0`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14002a99c`
- `0x14002ae20`
- `0x1400303d8`
- `0x1400552f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002afad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002afad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002afcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002afcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002af35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002afbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002afe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002af35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002afbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002afe9`
- `DMCmnUtils!BigStrcat` at `0x14002af6f`
- `DMCmnUtils!BigStrcat` at `0x14002af6f`
- `DMCmnUtils!CopyString` at `0x14002aef4`
- `DMCmnUtils!CopyString` at `0x14002aef4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::DpuManager::Characters(
        Microsoft::Windows::MDM::OmadmClient::DpuManager *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  unsigned int v4; // ebx
  char v8; // al
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rdx
  unsigned __int16 *v13; // rsi
  HLOCAL v14; // rcx
  void *v15; // r14
  DWORD LastError; // ebx
  __int64 v18; // [rsp+20h] [rbp-68h]
  int v19; // [rsp+30h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+40h] [rbp-48h] BYREF
  HLOCAL *p_hMem; // [rsp+50h] [rbp-38h]
  __int64 v23; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = a4;
  v19 = 0;
  v8 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    LODWORD(hMem) = 15;
    p_hMem = &hMem;
    v23 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      (__int64)a3,
      2u,
      &v21);
    v8 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  }
  v21.Ptr = (ULONGLONG)&v19;
  LOBYTE(v21.Size) = 1;
  if ( *((_DWORD *)a2 + 403) )
  {
    if ( (v8 & 8) != 0 )
      McTemplateU0qz_EventWriteTransfer(&v19, IgnoringElementContentEvent, v4, a3, v18);
    goto LABEL_21;
  }
  if ( !v4 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(&v19, a2, a3, a4, v18);
LABEL_21:
    v10 = v19;
    goto LABEL_22;
  }
  hMem = 0;
  v9 = CopyString(a3, v4, (unsigned __int16 **)&hMem);
  v10 = v9;
  v19 = v9;
  if ( v9 < 0 )
  {
    v11 = (unsigned int)v9;
    v12 = 1912;
    goto LABEL_10;
  }
  if ( !*((_QWORD *)this + 17) )
  {
    v13 = (unsigned __int16 *)hMem;
    v14 = 0;
    hMem = 0;
LABEL_19:
    *((_QWORD *)this + 17) = v13;
    if ( v14 )
      LocalFree(v14);
    goto LABEL_21;
  }
  v13 = BigStrcat(2u, *((_QWORD *)this + 17), hMem);
  if ( v13 )
  {
    v19 = 0;
    v15 = (void *)*((_QWORD *)this + 17);
    if ( v15 )
    {
      LastError = GetLastError();
      LocalFree(v15);
      SetLastError(LastError);
    }
    v14 = hMem;
    goto LABEL_19;
  }
  v10 = -2147024882;
  v19 = -2147024882;
  v11 = 2147942414LL;
  v12 = 1923;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
    (const char *)v11,
    v18);
  if ( hMem )
    LocalFree(hMem);
LABEL_22:
  wil::details::ScopeExitFn__lambda_80e4b8e3765238c857805899fafbe193___::_ScopeExitFn__lambda_80e4b8e3765238c857805899fafbe193___(&v21);
  return v10;
}

```

## disassembly

```asm
0x14002ae20  mov     r11, rsp
0x14002ae23  mov     [r11+10h], rbx
0x14002ae27  push    rsi
0x14002ae28  push    rdi
0x14002ae29  push    r14
0x14002ae2b  sub     rsp, 70h
0x14002ae2f  mov     rax, cs:__security_cookie
0x14002ae36  xor     rax, rsp
0x14002ae39  mov     [rsp+88h+var_28], rax
0x14002ae3e  mov     ebx, r9d
0x14002ae41  mov     rsi, r8
0x14002ae44  mov     r14, rdx
0x14002ae47  mov     rdi, rcx
0x14002ae4a  mov     [rsp+88h+var_58], 0
0x14002ae52  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x14002ae58  test    al, 8
0x14002ae5a  jz      short loc_14002AE9B
0x14002ae5c  mov     dword ptr [rsp+88h+hMem], 0Fh
0x14002ae64  lea     rax, [r11-50h]
0x14002ae68  mov     [r11-38h], rax
0x14002ae6c  mov     qword ptr [r11-30h], 4
0x14002ae74  lea     rax, [r11-48h]
0x14002ae78  mov     [r11-68h], rax
0x14002ae7c  mov     r9d, 2
0x14002ae82  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14002ae89  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14002ae90  call    McGenEventWrite_EventWriteTransfer
0x14002ae95  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x14002ae9b  lea     rcx, [rsp+88h+var_58]
0x14002aea0  mov     [rsp+88h+var_48], rcx
0x14002aea5  mov     [rsp+88h+var_40], 1
0x14002aeaa  cmp     dword ptr [r14+64Ch], 0
0x14002aeb2  jz      short loc_14002AED3
0x14002aeb4  test    al, 8
0x14002aeb6  jz      loc_14002AFF5
0x14002aebc  mov     r9, rsi
0x14002aebf  mov     r8d, ebx
0x14002aec2  lea     rdx, IgnoringElementContentEvent
0x14002aec9  call    McTemplateU0qz_EventWriteTransfer
0x14002aece  jmp     loc_14002AFF5
0x14002aed3  test    ebx, ebx
0x14002aed5  jnz     short loc_14002AEE1
0x14002aed7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0 < cchChars")
0x14002aedc  jmp     loc_14002AFF5
0x14002aee1  mov     [rsp+88h+hMem], 0
0x14002aeea  lea     r8, [rsp+88h+hMem]
0x14002aeef  mov     edx, ebx
0x14002aef1  mov     rcx, rsi
0x14002aef4  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x14002aefb  nop     dword ptr [rax+rax+00h]
0x14002af00  mov     ebx, eax
0x14002af02  mov     [rsp+88h+var_58], eax
0x14002af06  test    eax, eax
0x14002af08  jns     short loc_14002AF46
0x14002af0a  mov     r9d, eax; char *
0x14002af0d  mov     edx, 778h; void *
0x14002af12  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14002af19  mov     rcx, [rsp+88h]; this
0x14002af21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002af26  nop
0x14002af27  mov     rcx, [rsp+88h+hMem]; hMem
0x14002af2c  test    rcx, rcx
0x14002af2f  jz      loc_14002AFF9
0x14002af35  call    cs:__imp_LocalFree
0x14002af3c  nop     dword ptr [rax+rax+00h]
0x14002af41  jmp     loc_14002AFF9
0x14002af46  cmp     qword ptr [rdi+88h], 0
0x14002af4e  jnz     short loc_14002AF5E
0x14002af50  mov     rsi, [rsp+88h+hMem]
0x14002af55  xor     ecx, ecx
0x14002af57  mov     [rsp+88h+hMem], rcx
0x14002af5c  jmp     short loc_14002AFDD
0x14002af5e  mov     r8, [rsp+88h+hMem]
0x14002af63  mov     rdx, [rdi+88h]
0x14002af6a  mov     ecx, 2
0x14002af6f  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x14002af76  nop     dword ptr [rax+rax+00h]
0x14002af7b  mov     rsi, rax
0x14002af7e  test    rax, rax
0x14002af81  jnz     short loc_14002AF99
0x14002af83  mov     ebx, 8007000Eh
0x14002af88  mov     [rsp+88h+var_58], ebx
0x14002af8c  mov     r9d, ebx
0x14002af8f  mov     edx, 783h
0x14002af94  jmp     loc_14002AF12
0x14002af99  mov     [rsp+88h+var_58], 0
0x14002afa1  mov     r14, [rdi+88h]
0x14002afa8  test    r14, r14
0x14002afab  jz      short loc_14002AFD8
0x14002afad  call    cs:__imp_GetLastError
0x14002afb4  nop     dword ptr [rax+rax+00h]
0x14002afb9  mov     ebx, eax
0x14002afbb  mov     rcx, r14; hMem
0x14002afbe  call    cs:__imp_LocalFree
0x14002afc5  nop     dword ptr [rax+rax+00h]
0x14002afca  mov     ecx, ebx; dwErrCode
0x14002afcc  call    cs:__imp_SetLastError
0x14002afd3  nop     dword ptr [rax+rax+00h]
0x14002afd8  mov     rcx, [rsp+88h+hMem]; hMem
0x14002afdd  mov     [rdi+88h], rsi
0x14002afe4  test    rcx, rcx
0x14002afe7  jz      short loc_14002AFF5
0x14002afe9  call    cs:__imp_LocalFree
0x14002aff0  nop     dword ptr [rax+rax+00h]
0x14002aff5  mov     ebx, [rsp+88h+var_58]
0x14002aff9  lea     rcx, [rsp+88h+var_48]
0x14002affe  call    wil__details__ScopeExitFn__lambda_80e4b8e3765238c857805899fafbe193______ScopeExitFn__lambda_80e4b8e3765238c857805899fafbe193___
0x14002b003  mov     eax, ebx
0x14002b005  mov     rcx, [rsp+88h+var_28]
0x14002b00a  xor     rcx, rsp; StackCookie
0x14002b00d  call    __security_check_cookie
0x14002b012  mov     rbx, [rsp+88h+arg_8]
0x14002b01a  add     rsp, 70h
0x14002b01e  pop     r14
0x14002b020  pop     rdi
0x14002b021  pop     rsi
0x14002b022  retn
```
