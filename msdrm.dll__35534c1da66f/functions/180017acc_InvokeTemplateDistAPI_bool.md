# InvokeTemplateDistAPI(bool)

- ea: `0x180017acc`
- end: `0x180017ced`
- name: `?InvokeTemplateDistAPI@@YAJ_N@Z`
- size: `545`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180018750`

## callees

- `0x180001244`
- `0x180001284`
- `0x180001290`
- `0x180017acc`
- `0x180017cf4`
- `0x1800182e8`
- `0x18001b250`
- `0x18001b2a0`
- `0x18001c1c0`
- `0x18001e3e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017c56`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017c56`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180017b1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180017b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ca0`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall InvokeTemplateDistAPI(unsigned __int8 a1)
{
  HANDLE *pvContext; // rbx
  int v2; // r12d
  DRMHSESSION v3; // esi
  WCHAR *wszServiceURL; // r15
  UINT v5; // r14d
  int v6; // edi
  HANDLE EventA; // rbp
  signed int LastError; // eax
  char *v9; // rax
  signed int v10; // eax
  HANDLE v11; // rcx
  UINT puServiceURLLength; // [rsp+70h] [rbp+8h] BYREF
  DRMHSESSION hClient; // [rsp+78h] [rbp+10h] BYREF

  pvContext = 0;
  v2 = a1;
  v3 = 0;
  puServiceURLLength = 0;
  wszServiceURL = 0;
  hClient = 0;
  v5 = 8;
  if ( a1 )
  {
    v5 = 24;
    if ( !(unsigned int)IsScheduledToRun() )
    {
      v6 = 0;
      EventA = 0;
      goto LABEL_23;
    }
  }
  EventA = CreateEventA(0, 0, 0, 0);
  if ( EventA )
    goto LABEL_30;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_30:
    v9 = (char *)operator new(0x18u);
    pvContext = (HANDLE *)v9;
    if ( !v9 )
    {
      v6 = -2147024882;
      goto LABEL_23;
    }
    *(_QWORD *)(v9 + 12) = 0;
    *((_DWORD *)v9 + 5) = 0;
    *(_QWORD *)v9 = EventA;
    *((_DWORD *)v9 + 2) = 0;
    v6 = DRMCreateClientSession(OnStatus, 1u, (PWSTR)L"WindowsAuthProvider", 0, &hClient);
    if ( v6 < 0 )
    {
      v3 = hClient;
      goto LABEL_23;
    }
    v3 = hClient;
    v6 = DRMGetServiceLocation(hClient, v5, 2u, 0, &puServiceURLLength, 0);
    if ( v6 < 0 )
      goto LABEL_23;
    wszServiceURL = (WCHAR *)operator new[](saturated_mul(puServiceURLLength, 2u));
    if ( !wszServiceURL )
    {
      v6 = -2147024882;
      goto LABEL_23;
    }
    v6 = DRMGetServiceLocation(v3, v5, 2u, 0, &puServiceURLLength, wszServiceURL);
    if ( v6 >= 0 )
    {
      v6 = DRMAcquireIssuanceLicenseTemplate(v3, (v2 ^ 1) + 2, 0, 0, 0, wszServiceURL, pvContext);
      if ( !v6 )
      {
        if ( WaitForSingleObject(*pvContext, 0xFFFFFFFF) )
        {
          v10 = GetLastError();
          v6 = v10;
          if ( v10 > 0 )
            v6 = (unsigned __int16)v10 | 0x80070000;
          goto LABEL_23;
        }
        v6 = *((_DWORD *)pvContext + 2);
      }
      if ( v6 >= 0 )
        SetLastUpdatedTime();
    }
  }
LABEL_23:
  operator delete(wszServiceURL);
  DRMCloseSession(v3);
  if ( EventA )
    CloseHandle(EventA);
  if ( pvContext )
  {
    v11 = pvContext[2];
    *pvContext = 0;
    *((_DWORD *)pvContext + 2) = 0;
    operator delete(v11);
    pvContext[2] = 0;
  }
  operator delete(pvContext);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180017acc  mov     rax, rsp
0x180017acf  mov     [rax+18h], rbx
0x180017ad3  mov     [rax+20h], rbp
0x180017ad7  push    rsi
0x180017ad8  push    rdi
0x180017ad9  push    r12
0x180017adb  push    r14
0x180017add  push    r15
0x180017adf  sub     rsp, 40h
0x180017ae3  xor     ebx, ebx
0x180017ae5  movzx   r12d, cl
0x180017ae9  xor     esi, esi
0x180017aeb  mov     [rax+8], ebx
0x180017aee  xor     r15d, r15d
0x180017af1  mov     [rax+10h], esi
0x180017af4  lea     r14d, [rbx+8]
0x180017af8  test    cl, cl
0x180017afa  jz      short loc_180017B12
0x180017afc  lea     r14d, [rbx+18h]
0x180017b00  call    ?IsScheduledToRun@@YAHXZ; IsScheduledToRun(void)
0x180017b05  test    eax, eax
0x180017b07  jnz     short loc_180017B12
0x180017b09  xor     edi, edi
0x180017b0b  xor     ebp, ebp
0x180017b0d  jmp     loc_180017C89
0x180017b12  xor     r9d, r9d; lpName
0x180017b15  xor     r8d, r8d; bInitialState
0x180017b18  xor     edx, edx; bManualReset
0x180017b1a  xor     ecx, ecx; lpEventAttributes
0x180017b1c  call    cs:__imp_CreateEventA
0x180017b22  mov     rbp, rax
0x180017b25  test    rax, rax
0x180017b28  jnz     short loc_180017B47
0x180017b2a  call    cs:__imp_GetLastError
0x180017b30  mov     edi, eax
0x180017b32  test    eax, eax
0x180017b34  jle     short loc_180017B3F
0x180017b36  movzx   edi, ax
0x180017b39  or      edi, 80070000h
0x180017b3f  test    edi, edi
0x180017b41  js      loc_180017C89
0x180017b47  mov     ecx, 18h; Size
0x180017b4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017b51  mov     rbx, rax
0x180017b54  test    rax, rax
0x180017b57  jnz     short loc_180017B63
0x180017b59  mov     edi, 8007000Eh
0x180017b5e  jmp     loc_180017C89
0x180017b63  mov     [rax+0Ch], rsi
0x180017b67  lea     r8, aWindowsauthpro; "WindowsAuthProvider"
0x180017b6e  mov     [rax+14h], esi
0x180017b71  lea     rcx, ?OnStatus@@YAJW4_DRM_STATUS_MSG@@JPEAX1@Z; pfnCallback
0x180017b78  xor     r9d, r9d; wszGroupID
0x180017b7b  mov     [rax], rbp
0x180017b7e  mov     [rax+8], esi
0x180017b81  lea     rax, [rsp+68h+hClient]
0x180017b86  mov     [rsp+68h+phClient], rax; phClient
0x180017b8b  lea     edx, [r9+1]; uCallbackVersion
0x180017b8f  call    DRMCreateClientSession
0x180017b94  mov     edi, eax
0x180017b96  test    eax, eax
0x180017b98  js      loc_180017C85
0x180017b9e  xor     r9d, r9d; wszIssuanceLicense
0x180017ba1  mov     [rsp+68h+wszServiceURL], rsi; wszServiceURL
0x180017ba6  mov     esi, [rsp+68h+hClient]
0x180017baa  lea     rax, [rsp+68h+puServiceURLLength]
0x180017baf  mov     edx, r14d; uServiceType
0x180017bb2  mov     [rsp+68h+phClient], rax; puServiceURLLength
0x180017bb7  mov     ecx, esi; hClient
0x180017bb9  lea     r8d, [r9+2]; uServiceLocation
0x180017bbd  call    DRMGetServiceLocation
0x180017bc2  mov     edi, eax
0x180017bc4  test    eax, eax
0x180017bc6  js      loc_180017C89
0x180017bcc  mov     ecx, [rsp+68h+puServiceURLLength]
0x180017bd0  mov     edi, 2
0x180017bd5  mov     eax, edi
0x180017bd7  mul     rcx
0x180017bda  lea     rcx, [rdi-3]
0x180017bde  cmovb   rax, rcx
0x180017be2  mov     rcx, rax; unsigned __int64
0x180017be5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180017bea  mov     r15, rax
0x180017bed  test    rax, rax
0x180017bf0  jnz     short loc_180017BFC
0x180017bf2  mov     edi, 8007000Eh
0x180017bf7  jmp     loc_180017C89
0x180017bfc  lea     rax, [rsp+68h+puServiceURLLength]
0x180017c01  mov     [rsp+68h+wszServiceURL], r15; wszServiceURL
0x180017c06  xor     r9d, r9d; wszIssuanceLicense
0x180017c09  mov     [rsp+68h+phClient], rax; puServiceURLLength
0x180017c0e  mov     r8d, edi; uServiceLocation
0x180017c11  mov     edx, r14d; uServiceType
0x180017c14  mov     ecx, esi; hClient
0x180017c16  call    DRMGetServiceLocation
0x180017c1b  mov     edi, eax
0x180017c1d  test    eax, eax
0x180017c1f  js      short loc_180017C89
0x180017c21  mov     edx, r12d
0x180017c24  mov     [rsp+68h+pvContext], rbx; pvContext
0x180017c29  xor     edx, 1
0x180017c2c  mov     [rsp+68h+wszServiceURL], r15; wszUrl
0x180017c31  add     edx, 2; uFlags
0x180017c34  mov     [rsp+68h+phClient], 0; pwszTemplateIds
0x180017c3d  xor     r9d, r9d; cTemplates
0x180017c40  xor     r8d, r8d; pvReserved
0x180017c43  mov     ecx, esi; hClient
0x180017c45  call    DRMAcquireIssuanceLicenseTemplate
0x180017c4a  mov     edi, eax
0x180017c4c  test    eax, eax
0x180017c4e  jnz     short loc_180017C7A
0x180017c50  mov     rcx, [rbx]; hHandle
0x180017c53  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017c56  call    cs:__imp_WaitForSingleObject
0x180017c5c  test    eax, eax
0x180017c5e  jz      short loc_180017C77
0x180017c60  call    cs:__imp_GetLastError
0x180017c66  mov     edi, eax
0x180017c68  test    eax, eax
0x180017c6a  jle     short loc_180017C89
0x180017c6c  movzx   edi, ax
0x180017c6f  or      edi, 80070000h
0x180017c75  jmp     short loc_180017C89
0x180017c77  mov     edi, [rbx+8]
0x180017c7a  test    edi, edi
0x180017c7c  js      short loc_180017C89
0x180017c7e  call    ?SetLastUpdatedTime@@YAHXZ; SetLastUpdatedTime(void)
0x180017c83  jmp     short loc_180017C89
0x180017c85  mov     esi, [rsp+68h+hClient]
0x180017c89  mov     rcx, r15; Block
0x180017c8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017c91  mov     ecx, esi; hSession
0x180017c93  call    DRMCloseSession
0x180017c98  test    rbp, rbp
0x180017c9b  jz      short loc_180017CA6
0x180017c9d  mov     rcx, rbp; hObject
0x180017ca0  call    cs:__imp_CloseHandle
0x180017ca6  test    rbx, rbx
0x180017ca9  jz      short loc_180017CCA
0x180017cab  mov     rcx, [rbx+10h]; Block
0x180017caf  mov     qword ptr [rbx], 0
0x180017cb6  mov     dword ptr [rbx+8], 0
0x180017cbd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017cc2  mov     qword ptr [rbx+10h], 0
0x180017cca  mov     rcx, rbx; Block
0x180017ccd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017cd2  lea     r11, [rsp+68h+var_28]
0x180017cd7  mov     eax, edi
0x180017cd9  mov     rbx, [r11+40h]
0x180017cdd  mov     rbp, [r11+48h]
0x180017ce1  mov     rsp, r11
0x180017ce4  pop     r15
0x180017ce6  pop     r14
0x180017ce8  pop     r12
0x180017cea  pop     rdi
0x180017ceb  pop     rsi
0x180017cec  retn
```
