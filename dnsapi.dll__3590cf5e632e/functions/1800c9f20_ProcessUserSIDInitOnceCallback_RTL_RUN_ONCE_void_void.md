# _ProcessUserSIDInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800c9f20`
- end: `0x1800ca262`
- name: `?_ProcessUserSIDInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `834`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18003de30`
- `0x180076e78`
- `0x180076f2c`
- `0x18007f24c`
- `0x18008545c`
- `0x180087480`
- `0x180087708`
- `0x180087a50`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800c9d18`
- `0x1800c9f20`
- `0x1800ca64c`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ca202`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ca202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca0e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca0e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca146`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ca220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ca220`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c9fd4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c9fd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c9fbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c9fbb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800ca0d6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800ca136`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800ca0d6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800ca136`
- `ntdll!RtlQueryPackageClaims` at `0x1800ca1a7`
- `ntdll!RtlQueryPackageClaims` at `0x1800ca1a7`

## pseudocode

```c
_BOOL8 __fastcall _ProcessUserSIDInitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  void *v4; // rdx
  signed int TokenUserSID; // ebx
  HANDLE CurrentProcess; // rax
  unsigned int v7; // r8d
  signed int v8; // eax
  unsigned int v9; // r8d
  int v10; // edi
  signed int v11; // eax
  signed int LastError; // eax
  int v13; // eax
  DWORD v14; // eax
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v18; // [rsp+4Ch] [rbp-B4h] BYREF
  _QWORD v19[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pSourceSid[80]; // [rsp+70h] [rbp-90h] BYREF
  _SID v23; // [rsp+C0h] [rbp-40h] BYREF

  v19[1] = 0;
  v19[0] = 0;
  TokenHandle = 0;
  memset_0(pSourceSid, 0, 0x44u);
  memset_0(&v23, 0, 0x44u);
  v17 = 0;
  v18 = 0;
  v16 = 4096;
  v21 = 0;
  if ( Context )
    *Context = 0;
  TokenUserSID = AutoTokenImpersonate::Impersonate((AutoTokenImpersonate *)v19, v4);
  if ( TokenUserSID >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      TokenUserSID = WxGetTokenUserSID(TokenHandle, pSourceSid, v7);
      if ( TokenUserSID >= 0 )
      {
        TokenUserSID = WxIsTokenAppContainer(TokenHandle, &v17);
        if ( TokenUserSID >= 0 )
        {
          v10 = v17;
          if ( v17 && (TokenUserSID = WxGetTokenAppContainerSID(TokenHandle, &v23, v9), TokenUserSID < 0) )
          {
            HIDWORD(v16) = 72;
          }
          else
          {
            TokenUserSID = WxGetTokenSessionId(TokenHandle, &v18);
            if ( TokenUserSID >= 0 )
            {
              TokenUserSID = WxGetTokenIntegrityLevel(TokenHandle, (unsigned int *)&v16);
              if ( TokenUserSID >= 0 )
              {
                if ( CopySid(0x44u, &g_rgbProcessUserSID, pSourceSid) )
                {
                  TokenUserSID = 0;
                  if ( !v10 || (g_fIsProcessAppContainer = 1, CopySid(0x44u, &g_rgbAppContainerSID, &v23)) )
                  {
                    if ( (unsigned int)Feature_WinInetCacheAppBrokerForUWPMediumIL__private_IsEnabledDeviceUsageNoInline() )
                    {
                      v13 = RtlQueryPackageClaims(TokenHandle, 0, 0, 0, 0, 0, &v21, 0, v16);
                      if ( v13 < 0 )
                      {
                        if ( v13 != -1073741275 )
                        {
                          TokenUserSID = HRESULT_FROM_NTSTATUS(v13);
                          if ( TokenUserSID < 0 )
                            HIDWORD(v16) = 107;
                        }
                      }
                      else if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
                      {
                        WPP_SF_d(1053, 10, WPP_7d9643b54b3c301717e84a9acfdbd0a4_Traceguids, (unsigned int)v21);
                      }
                    }
                  }
                  else
                  {
                    LastError = GetLastError();
                    TokenUserSID = LastError;
                    if ( LastError > 0 )
                      TokenUserSID = (unsigned __int16)LastError | 0x80070000;
                    HIDWORD(v16) = 85;
                    if ( TokenUserSID >= 0 )
                      TokenUserSID = -2147418113;
                  }
                }
                else
                {
                  v11 = GetLastError();
                  TokenUserSID = v11;
                  if ( v11 > 0 )
                    TokenUserSID = (unsigned __int16)v11 | 0x80070000;
                  HIDWORD(v16) = 79;
                  if ( TokenUserSID >= 0 )
                    TokenUserSID = -2147418113;
                }
              }
              else
              {
                HIDWORD(v16) = 77;
              }
            }
            else
            {
              HIDWORD(v16) = 75;
            }
          }
        }
        else
        {
          HIDWORD(v16) = 69;
        }
      }
      else
      {
        HIDWORD(v16) = 67;
      }
    }
    else
    {
      v8 = GetLastError();
      TokenUserSID = v8;
      if ( v8 > 0 )
        TokenUserSID = (unsigned __int16)v8 | 0x80070000;
      HIDWORD(v16) = 65;
      if ( TokenUserSID >= 0 )
        TokenUserSID = -2147418113;
    }
  }
  else
  {
    HIDWORD(v16) = 63;
  }
  v14 = WX_WIN32_FROM_HR((unsigned int)TokenUserSID);
  SetLastError(v14);
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  AutoTokenImpersonate::~AutoTokenImpersonate((AutoTokenImpersonate *)v19);
  return TokenUserSID >= 0;
}

```

## disassembly

```asm
0x1800c9f20  mov     [rsp-8+arg_0], rbx
0x1800c9f25  mov     [rsp-8+arg_8], rsi
0x1800c9f2a  push    rbp
0x1800c9f2b  push    rdi
0x1800c9f2c  push    r14
0x1800c9f2e  lea     rbp, [rsp-20h]
0x1800c9f33  sub     rsp, 120h
0x1800c9f3a  mov     rax, cs:__security_cookie
0x1800c9f41  xor     rax, rsp
0x1800c9f44  mov     [rbp+30h+var_20], rax
0x1800c9f48  xor     esi, esi
0x1800c9f4a  lea     rcx, [rsp+130h+pSourceSid]; void *
0x1800c9f4f  mov     rbx, r8
0x1800c9f52  mov     [rsp+130h+var_EC], esi
0x1800c9f56  xor     edx, edx; Val
0x1800c9f58  mov     [rsp+130h+var_D8], rsi
0x1800c9f5d  mov     [rsp+130h+var_E0], rsi
0x1800c9f62  lea     r14d, [rsi+44h]
0x1800c9f66  mov     [rsp+130h+TokenHandle], rsi
0x1800c9f6b  mov     r8d, r14d; Size
0x1800c9f6e  call    memset_0
0x1800c9f73  mov     r8d, r14d; Size
0x1800c9f76  lea     rcx, [rbp+30h+var_70]; void *
0x1800c9f7a  xor     edx, edx; Val
0x1800c9f7c  call    memset_0
0x1800c9f81  mov     [rsp+130h+var_E8], esi
0x1800c9f85  mov     [rsp+130h+var_E4], esi
0x1800c9f89  mov     [rsp+130h+var_F0], 1000h
0x1800c9f91  mov     [rsp+130h+var_C8], rsi
0x1800c9f96  test    rbx, rbx
0x1800c9f99  jz      short loc_1800C9F9E
0x1800c9f9b  mov     [rbx], rsi
0x1800c9f9e  lea     rcx, [rsp+130h+var_E0]; this
0x1800c9fa3  call    ?Impersonate@AutoTokenImpersonate@@QEAAJPEAX@Z; AutoTokenImpersonate::Impersonate(void *)
0x1800c9fa8  mov     ebx, eax
0x1800c9faa  test    eax, eax
0x1800c9fac  jns     short loc_1800C9FBB
0x1800c9fae  mov     [rsp+130h+var_EC], 3Fh ; '?'
0x1800c9fb6  jmp     loc_1800CA1F9
0x1800c9fbb  call    cs:__imp_GetCurrentProcess
0x1800c9fc2  nop     dword ptr [rax+rax+00h]
0x1800c9fc7  lea     r8, [rsp+130h+TokenHandle]; TokenHandle
0x1800c9fcc  mov     edx, 20008h; DesiredAccess
0x1800c9fd1  mov     rcx, rax; ProcessHandle
0x1800c9fd4  call    cs:__imp_OpenProcessToken
0x1800c9fdb  nop     dword ptr [rax+rax+00h]
0x1800c9fe0  test    eax, eax
0x1800c9fe2  jnz     short loc_1800CA016
0x1800c9fe4  call    cs:__imp_GetLastError
0x1800c9feb  nop     dword ptr [rax+rax+00h]
0x1800c9ff0  mov     ebx, eax
0x1800c9ff2  test    eax, eax
0x1800c9ff4  jle     short loc_1800C9FFF
0x1800c9ff6  movzx   ebx, ax
0x1800c9ff9  or      ebx, 80070000h
0x1800c9fff  test    ebx, ebx
0x1800ca001  mov     [rsp+130h+var_EC], 41h ; 'A'
0x1800ca009  mov     eax, 8000FFFFh
0x1800ca00e  cmovns  ebx, eax
0x1800ca011  jmp     loc_1800CA1F9
0x1800ca016  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x1800ca01b  lea     rdx, [rsp+130h+pSourceSid]; pDestinationSid
0x1800ca020  call    ?WxGetTokenUserSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenUserSID(void *,_SID *,ulong)
0x1800ca025  mov     ebx, eax
0x1800ca027  test    eax, eax
0x1800ca029  jns     short loc_1800CA038
0x1800ca02b  mov     [rsp+130h+var_EC], 43h ; 'C'
0x1800ca033  jmp     loc_1800CA1F9
0x1800ca038  mov     rcx, [rsp+130h+TokenHandle]; void *
0x1800ca03d  lea     rdx, [rsp+130h+var_E8]; int *
0x1800ca042  call    ?WxIsTokenAppContainer@@YAJPEAXPEAH@Z; WxIsTokenAppContainer(void *,int *)
0x1800ca047  mov     ebx, eax
0x1800ca049  test    eax, eax
0x1800ca04b  jns     short loc_1800CA05A
0x1800ca04d  mov     [rsp+130h+var_EC], 45h ; 'E'
0x1800ca055  jmp     loc_1800CA1F9
0x1800ca05a  mov     edi, [rsp+130h+var_E8]
0x1800ca05e  test    edi, edi
0x1800ca060  jz      short loc_1800CA083
0x1800ca062  mov     rcx, [rsp+130h+TokenHandle]; void *
0x1800ca067  lea     rdx, [rbp+30h+var_70]; struct _SID *
0x1800ca06b  call    ?WxGetTokenAppContainerSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenAppContainerSID(void *,_SID *,ulong)
0x1800ca070  mov     ebx, eax
0x1800ca072  test    eax, eax
0x1800ca074  jns     short loc_1800CA083
0x1800ca076  mov     [rsp+130h+var_EC], 48h ; 'H'
0x1800ca07e  jmp     loc_1800CA1F9
0x1800ca083  mov     rcx, [rsp+130h+TokenHandle]; void *
0x1800ca088  lea     rdx, [rsp+130h+var_E4]; unsigned int *
0x1800ca08d  call    ?WxGetTokenSessionId@@YAJPEAXPEAK@Z; WxGetTokenSessionId(void *,ulong *)
0x1800ca092  mov     ebx, eax
0x1800ca094  test    eax, eax
0x1800ca096  jns     short loc_1800CA0A5
0x1800ca098  mov     [rsp+130h+var_EC], 4Bh ; 'K'
0x1800ca0a0  jmp     loc_1800CA1F9
0x1800ca0a5  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x1800ca0aa  lea     rdx, [rsp+130h+var_F0]; unsigned int *
0x1800ca0af  call    ?WxGetTokenIntegrityLevel@@YAJPEAXPEAK@Z; WxGetTokenIntegrityLevel(void *,ulong *)
0x1800ca0b4  mov     ebx, eax
0x1800ca0b6  test    eax, eax
0x1800ca0b8  jns     short loc_1800CA0C7
0x1800ca0ba  mov     [rsp+130h+var_EC], 4Dh ; 'M'
0x1800ca0c2  jmp     loc_1800CA1F9
0x1800ca0c7  lea     r8, [rsp+130h+pSourceSid]; pSourceSid
0x1800ca0cc  mov     ecx, r14d; nDestinationSidLength
0x1800ca0cf  lea     rdx, ?g_rgbProcessUserSID@@3PAEA; pDestinationSid
0x1800ca0d6  call    cs:__imp_CopySid
0x1800ca0dd  nop     dword ptr [rax+rax+00h]
0x1800ca0e2  test    eax, eax
0x1800ca0e4  jnz     short loc_1800CA118
0x1800ca0e6  call    cs:__imp_GetLastError
0x1800ca0ed  nop     dword ptr [rax+rax+00h]
0x1800ca0f2  mov     ebx, eax
0x1800ca0f4  test    eax, eax
0x1800ca0f6  jle     short loc_1800CA101
0x1800ca0f8  movzx   ebx, ax
0x1800ca0fb  or      ebx, 80070000h
0x1800ca101  test    ebx, ebx
0x1800ca103  mov     [rsp+130h+var_EC], 4Fh ; 'O'
0x1800ca10b  mov     eax, 8000FFFFh
0x1800ca110  cmovns  ebx, eax
0x1800ca113  jmp     loc_1800CA1F9
0x1800ca118  mov     ebx, esi
0x1800ca11a  test    edi, edi
0x1800ca11c  jz      short loc_1800CA178
0x1800ca11e  lea     r8, [rbp+30h+var_70]; pSourceSid
0x1800ca122  mov     cs:?g_fIsProcessAppContainer@@3HA, 1; int g_fIsProcessAppContainer
0x1800ca12c  lea     rdx, ?g_rgbAppContainerSID@@3PAEA; pDestinationSid
0x1800ca133  mov     ecx, r14d; nDestinationSidLength
0x1800ca136  call    cs:__imp_CopySid
0x1800ca13d  nop     dword ptr [rax+rax+00h]
0x1800ca142  test    eax, eax
0x1800ca144  jnz     short loc_1800CA178
0x1800ca146  call    cs:__imp_GetLastError
0x1800ca14d  nop     dword ptr [rax+rax+00h]
0x1800ca152  mov     ebx, eax
0x1800ca154  test    eax, eax
0x1800ca156  jle     short loc_1800CA161
0x1800ca158  movzx   ebx, ax
0x1800ca15b  or      ebx, 80070000h
0x1800ca161  test    ebx, ebx
0x1800ca163  mov     [rsp+130h+var_EC], 55h ; 'U'
0x1800ca16b  mov     eax, 8000FFFFh
0x1800ca170  cmovns  ebx, eax
0x1800ca173  jmp     loc_1800CA1F9
0x1800ca178  call    Feature_WinInetCacheAppBrokerForUWPMediumIL__private_IsEnabledDeviceUsageNoInline
0x1800ca17d  test    eax, eax
0x1800ca17f  jz      short loc_1800CA1F9
0x1800ca181  mov     rcx, [rsp+130h+TokenHandle]
0x1800ca186  lea     rax, [rsp+130h+var_C8]
0x1800ca18b  mov     [rsp+130h+var_F8], rsi
0x1800ca190  xor     r9d, r9d
0x1800ca193  mov     [rsp+130h+var_100], rax
0x1800ca198  xor     r8d, r8d
0x1800ca19b  mov     [rsp+130h+var_108], rsi
0x1800ca1a0  xor     edx, edx
0x1800ca1a2  mov     [rsp+130h+var_110], rsi
0x1800ca1a7  call    cs:__imp_RtlQueryPackageClaims
0x1800ca1ae  nop     dword ptr [rax+rax+00h]
0x1800ca1b3  test    eax, eax
0x1800ca1b5  js      short loc_1800CA1DD
0x1800ca1b7  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x1800ca1be  jz      short loc_1800CA1F9
0x1800ca1c0  mov     r9d, dword ptr [rsp+130h+var_C8]
0x1800ca1c5  lea     r8, WPP_7d9643b54b3c301717e84a9acfdbd0a4_Traceguids
0x1800ca1cc  mov     edx, 0Ah
0x1800ca1d1  mov     ecx, 41Dh
0x1800ca1d6  call    WPP_SF_d
0x1800ca1db  jmp     short loc_1800CA1F9
0x1800ca1dd  cmp     eax, 0C0000225h
0x1800ca1e2  jz      short loc_1800CA1F9
0x1800ca1e4  mov     ecx, eax; int
0x1800ca1e6  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x1800ca1eb  mov     ebx, eax
0x1800ca1ed  test    eax, eax
0x1800ca1ef  jns     short loc_1800CA1F9
0x1800ca1f1  mov     [rsp+130h+var_EC], 6Bh ; 'k'
0x1800ca1f9  mov     ecx, ebx
0x1800ca1fb  call    WX_WIN32_FROM_HR
0x1800ca200  mov     ecx, eax; dwErrCode
0x1800ca202  call    cs:__imp_SetLastError
0x1800ca209  nop     dword ptr [rax+rax+00h]
0x1800ca20e  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x1800ca213  test    ebx, ebx
0x1800ca215  mov     edi, esi
0x1800ca217  setns   dil
0x1800ca21b  test    rcx, rcx
0x1800ca21e  jz      short loc_1800CA231
0x1800ca220  call    cs:__imp_CloseHandle
0x1800ca227  nop     dword ptr [rax+rax+00h]
0x1800ca22c  mov     [rsp+130h+TokenHandle], rsi
0x1800ca231  lea     rcx, [rsp+130h+var_E0]; this
0x1800ca236  call    ??1AutoTokenImpersonate@@QEAA@XZ; AutoTokenImpersonate::~AutoTokenImpersonate(void)
0x1800ca23b  mov     eax, edi
0x1800ca23d  mov     rcx, [rbp+30h+var_20]
0x1800ca241  xor     rcx, rsp; StackCookie
0x1800ca244  call    __security_check_cookie
0x1800ca249  lea     r11, [rsp+130h+var_10]
0x1800ca251  mov     rbx, [r11+20h]
0x1800ca255  mov     rsi, [r11+28h]
0x1800ca259  mov     rsp, r11
0x1800ca25c  pop     r14
0x1800ca25e  pop     rdi
0x1800ca25f  pop     rbp
0x1800ca260  retn
```
