# _ProcessUserSIDInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18003f3c0`
- end: `0x18003f6b8`
- name: `?_ProcessUserSIDInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `760`
- prototype: `_BOOL8 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008b00`
- `0x18003eeb4`
- `0x18003f3c0`
- `0x18003f6c0`
- `0x180046ec0`
- `0x180047818`
- `0x18007333c`
- `0x18007773c`
- `0x180077824`
- `0x18007790c`
- `0x1800779dc`
- `0x180077b04`
- `0x180078088`
- `0x180086b1c`

## import_xrefs

- `ntdll!RtlQueryPackageClaims` at `0x18003f610`
- `ntdll!RtlQueryPackageClaims` at `0x18003f610`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f665`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f56e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f5b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f56e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f5b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f67d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f67d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003f46e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003f46e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003f45b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003f45b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003f564`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003f5ae`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003f564`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003f5ae`

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
  HANDLE v19[2]; // [rsp+50h] [rbp-B0h] BYREF
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
                  if ( !v10 || CopySid(0x44u, &g_rgbAppContainerSID, &v23) )
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
                      else if ( (BYTE3(xmmword_1800AB5A0) & 0x20) != 0 )
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
  AutoTokenImpersonate::~AutoTokenImpersonate(v19);
  return TokenUserSID >= 0;
}

```

## disassembly

```asm
0x18003f3c0  mov     [rsp-8+arg_0], rbx
0x18003f3c5  mov     [rsp-8+arg_8], rsi
0x18003f3ca  push    rbp
0x18003f3cb  push    rdi
0x18003f3cc  push    r14
0x18003f3ce  lea     rbp, [rsp-20h]
0x18003f3d3  sub     rsp, 120h
0x18003f3da  mov     rax, cs:__security_cookie
0x18003f3e1  xor     rax, rsp
0x18003f3e4  mov     [rbp+30h+var_20], rax
0x18003f3e8  xor     esi, esi
0x18003f3ea  lea     rcx, [rsp+130h+pSourceSid]; void *
0x18003f3ef  mov     rbx, r8
0x18003f3f2  mov     [rsp+130h+var_EC], esi
0x18003f3f6  xor     edx, edx; Val
0x18003f3f8  mov     [rsp+130h+var_D8], rsi
0x18003f3fd  mov     [rsp+130h+var_E0], rsi
0x18003f402  lea     r14d, [rsi+44h]
0x18003f406  mov     [rsp+130h+TokenHandle], rsi
0x18003f40b  mov     r8d, r14d; Size
0x18003f40e  call    memset_0
0x18003f413  mov     r8d, r14d; Size
0x18003f416  lea     rcx, [rbp+30h+var_70]; void *
0x18003f41a  xor     edx, edx; Val
0x18003f41c  call    memset_0
0x18003f421  mov     [rsp+130h+var_E8], esi
0x18003f425  mov     [rsp+130h+var_E4], esi
0x18003f429  mov     [rsp+130h+var_F0], 1000h
0x18003f431  mov     [rsp+130h+var_C8], rsi
0x18003f436  test    rbx, rbx
0x18003f439  jz      short loc_18003F43E
0x18003f43b  mov     [rbx], rsi
0x18003f43e  lea     rcx, [rsp+130h+var_E0]; this
0x18003f443  call    ?Impersonate@AutoTokenImpersonate@@QEAAJPEAX@Z; AutoTokenImpersonate::Impersonate(void *)
0x18003f448  mov     ebx, eax
0x18003f44a  test    eax, eax
0x18003f44c  jns     short loc_18003F45B
0x18003f44e  mov     [rsp+130h+var_EC], 3Fh ; '?'
0x18003f456  jmp     loc_18003F65C
0x18003f45b  call    cs:__imp_GetCurrentProcess
0x18003f461  lea     r8, [rsp+130h+TokenHandle]; TokenHandle
0x18003f466  mov     edx, 20008h; DesiredAccess
0x18003f46b  mov     rcx, rax; ProcessHandle
0x18003f46e  call    cs:__imp_OpenProcessToken
0x18003f474  test    eax, eax
0x18003f476  jnz     short loc_18003F4A4
0x18003f478  call    cs:__imp_GetLastError
0x18003f47e  mov     ebx, eax
0x18003f480  test    eax, eax
0x18003f482  jle     short loc_18003F48D
0x18003f484  movzx   ebx, ax
0x18003f487  or      ebx, 80070000h
0x18003f48d  test    ebx, ebx
0x18003f48f  mov     [rsp+130h+var_EC], 41h ; 'A'
0x18003f497  mov     eax, 8000FFFFh
0x18003f49c  cmovns  ebx, eax
0x18003f49f  jmp     loc_18003F65C
0x18003f4a4  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x18003f4a9  lea     rdx, [rsp+130h+pSourceSid]; pDestinationSid
0x18003f4ae  call    ?WxGetTokenUserSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenUserSID(void *,_SID *,ulong)
0x18003f4b3  mov     ebx, eax
0x18003f4b5  test    eax, eax
0x18003f4b7  jns     short loc_18003F4C6
0x18003f4b9  mov     [rsp+130h+var_EC], 43h ; 'C'
0x18003f4c1  jmp     loc_18003F65C
0x18003f4c6  mov     rcx, [rsp+130h+TokenHandle]; void *
0x18003f4cb  lea     rdx, [rsp+130h+var_E8]; int *
0x18003f4d0  call    ?WxIsTokenAppContainer@@YAJPEAXPEAH@Z; WxIsTokenAppContainer(void *,int *)
0x18003f4d5  mov     ebx, eax
0x18003f4d7  test    eax, eax
0x18003f4d9  jns     short loc_18003F4E8
0x18003f4db  mov     [rsp+130h+var_EC], 45h ; 'E'
0x18003f4e3  jmp     loc_18003F65C
0x18003f4e8  mov     edi, [rsp+130h+var_E8]
0x18003f4ec  test    edi, edi
0x18003f4ee  jz      short loc_18003F511
0x18003f4f0  mov     rcx, [rsp+130h+TokenHandle]; void *
0x18003f4f5  lea     rdx, [rbp+30h+var_70]; struct _SID *
0x18003f4f9  call    ?WxGetTokenAppContainerSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenAppContainerSID(void *,_SID *,ulong)
0x18003f4fe  mov     ebx, eax
0x18003f500  test    eax, eax
0x18003f502  jns     short loc_18003F511
0x18003f504  mov     [rsp+130h+var_EC], 48h ; 'H'
0x18003f50c  jmp     loc_18003F65C
0x18003f511  mov     rcx, [rsp+130h+TokenHandle]; void *
0x18003f516  lea     rdx, [rsp+130h+var_E4]; unsigned int *
0x18003f51b  call    ?WxGetTokenSessionId@@YAJPEAXPEAK@Z; WxGetTokenSessionId(void *,ulong *)
0x18003f520  mov     ebx, eax
0x18003f522  test    eax, eax
0x18003f524  jns     short loc_18003F533
0x18003f526  mov     [rsp+130h+var_EC], 4Bh ; 'K'
0x18003f52e  jmp     loc_18003F65C
0x18003f533  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x18003f538  lea     rdx, [rsp+130h+var_F0]; unsigned int *
0x18003f53d  call    ?WxGetTokenIntegrityLevel@@YAJPEAXPEAK@Z; WxGetTokenIntegrityLevel(void *,ulong *)
0x18003f542  mov     ebx, eax
0x18003f544  test    eax, eax
0x18003f546  jns     short loc_18003F555
0x18003f548  mov     [rsp+130h+var_EC], 4Dh ; 'M'
0x18003f550  jmp     loc_18003F65C
0x18003f555  lea     r8, [rsp+130h+pSourceSid]; pSourceSid
0x18003f55a  mov     ecx, r14d; nDestinationSidLength
0x18003f55d  lea     rdx, ?g_rgbProcessUserSID@@3PAEA; pDestinationSid
0x18003f564  call    cs:__imp_CopySid
0x18003f56a  test    eax, eax
0x18003f56c  jnz     short loc_18003F59A
0x18003f56e  call    cs:__imp_GetLastError
0x18003f574  mov     ebx, eax
0x18003f576  test    eax, eax
0x18003f578  jle     short loc_18003F583
0x18003f57a  movzx   ebx, ax
0x18003f57d  or      ebx, 80070000h
0x18003f583  test    ebx, ebx
0x18003f585  mov     [rsp+130h+var_EC], 4Fh ; 'O'
0x18003f58d  mov     eax, 8000FFFFh
0x18003f592  cmovns  ebx, eax
0x18003f595  jmp     loc_18003F65C
0x18003f59a  mov     ebx, esi
0x18003f59c  test    edi, edi
0x18003f59e  jz      short loc_18003F5E1
0x18003f5a0  lea     r8, [rbp+30h+var_70]; pSourceSid
0x18003f5a4  mov     ecx, r14d; nDestinationSidLength
0x18003f5a7  lea     rdx, ?g_rgbAppContainerSID@@3PAEA; pDestinationSid
0x18003f5ae  call    cs:__imp_CopySid
0x18003f5b4  test    eax, eax
0x18003f5b6  jnz     short loc_18003F5E1
0x18003f5b8  call    cs:__imp_GetLastError
0x18003f5be  mov     ebx, eax
0x18003f5c0  test    eax, eax
0x18003f5c2  jle     short loc_18003F5CD
0x18003f5c4  movzx   ebx, ax
0x18003f5c7  or      ebx, 80070000h
0x18003f5cd  test    ebx, ebx
0x18003f5cf  mov     [rsp+130h+var_EC], 55h ; 'U'
0x18003f5d7  mov     eax, 8000FFFFh
0x18003f5dc  cmovns  ebx, eax
0x18003f5df  jmp     short loc_18003F65C
0x18003f5e1  call    Feature_WinInetCacheAppBrokerForUWPMediumIL__private_IsEnabledDeviceUsageNoInline
0x18003f5e6  test    eax, eax
0x18003f5e8  jz      short loc_18003F65C
0x18003f5ea  mov     rcx, [rsp+130h+TokenHandle]
0x18003f5ef  lea     rax, [rsp+130h+var_C8]
0x18003f5f4  mov     [rsp+130h+var_F8], rsi
0x18003f5f9  xor     r9d, r9d
0x18003f5fc  mov     [rsp+130h+var_100], rax
0x18003f601  xor     r8d, r8d
0x18003f604  mov     [rsp+130h+var_108], rsi
0x18003f609  xor     edx, edx
0x18003f60b  mov     [rsp+130h+var_110], rsi
0x18003f610  call    cs:__imp_RtlQueryPackageClaims
0x18003f616  test    eax, eax
0x18003f618  js      short loc_18003F640
0x18003f61a  test    byte ptr cs:xmmword_1800AB5A0+3, 20h
0x18003f621  jz      short loc_18003F65C
0x18003f623  mov     r9d, dword ptr [rsp+130h+var_C8]
0x18003f628  lea     r8, WPP_7d9643b54b3c301717e84a9acfdbd0a4_Traceguids
0x18003f62f  mov     edx, 0Ah
0x18003f634  mov     ecx, 41Dh
0x18003f639  call    WPP_SF_d
0x18003f63e  jmp     short loc_18003F65C
0x18003f640  cmp     eax, 0C0000225h
0x18003f645  jz      short loc_18003F65C
0x18003f647  mov     ecx, eax; int
0x18003f649  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x18003f64e  mov     ebx, eax
0x18003f650  test    eax, eax
0x18003f652  jns     short loc_18003F65C
0x18003f654  mov     [rsp+130h+var_EC], 6Bh ; 'k'
0x18003f65c  mov     ecx, ebx
0x18003f65e  call    WX_WIN32_FROM_HR
0x18003f663  mov     ecx, eax; dwErrCode
0x18003f665  call    cs:__imp_SetLastError
0x18003f66b  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x18003f670  test    ebx, ebx
0x18003f672  mov     edi, esi
0x18003f674  setns   dil
0x18003f678  test    rcx, rcx
0x18003f67b  jz      short loc_18003F688
0x18003f67d  call    cs:__imp_CloseHandle
0x18003f683  mov     [rsp+130h+TokenHandle], rsi
0x18003f688  lea     rcx, [rsp+130h+var_E0]; this
0x18003f68d  call    ??1AutoTokenImpersonate@@QEAA@XZ; AutoTokenImpersonate::~AutoTokenImpersonate(void)
0x18003f692  mov     eax, edi
0x18003f694  mov     rcx, [rbp+30h+var_20]
0x18003f698  xor     rcx, rsp; StackCookie
0x18003f69b  call    __security_check_cookie
0x18003f6a0  lea     r11, [rsp+130h+var_10]
0x18003f6a8  mov     rbx, [r11+20h]
0x18003f6ac  mov     rsi, [r11+28h]
0x18003f6b0  mov     rsp, r11
0x18003f6b3  pop     r14
0x18003f6b5  pop     rdi
0x18003f6b6  pop     rbp
0x18003f6b7  retn
```
