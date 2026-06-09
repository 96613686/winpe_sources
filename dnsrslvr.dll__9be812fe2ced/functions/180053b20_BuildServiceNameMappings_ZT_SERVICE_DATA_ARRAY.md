# BuildServiceNameMappings(_ZT_SERVICE_DATA_ARRAY * *)

- ea: `0x180053b20`
- end: `0x180053dd3`
- name: `?BuildServiceNameMappings@@YAJPEAPEAU_ZT_SERVICE_DATA_ARRAY@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(struct _ZT_SERVICE_DATA_ARRAY **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800544c0`

## callees

- `0x180008870`
- `0x18000b130`
- `0x180019720`
- `0x180046ec0`
- `0x180053b20`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053c8a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180053d7c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180053d7c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180053b80`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180053b80`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180053bef`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180053c80`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180053bef`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180053c80`

## pseudocode

```c
__int64 __fastcall BuildServiceNameMappings(struct _ZT_SERVICE_DATA_ARRAY **a1)
{
  signed int v1; // ebx
  struct _ZT_SERVICE_DATA_ARRAY *v3; // rdi
  BYTE *lpServices; // r14
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r15
  signed int LastError; // eax
  DWORD v8; // ecx
  int v9; // esi
  __int64 cbBufSize; // r12
  unsigned __int64 v11; // rdx
  DWORD i; // r11d
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // r11d
  DWORD ServicesReturned; // [rsp+58h] [rbp-20h] BYREF
  DWORD pcbBytesNeeded; // [rsp+5Ch] [rbp-1Ch] BYREF
  DWORD ResumeHandle; // [rsp+60h] [rbp-18h] BYREF

  v1 = 0;
  v3 = 0;
  pcbBytesNeeded = 0;
  lpServices = 0;
  ServicesReturned = 0;
  ResumeHandle = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 26, WPP_75f1376952c23bd1eaf4acbe431c69f9_Traceguids, a1);
  v5 = OpenSCManagerW(0, 0, 4u);
  v6 = v5;
  if ( v5 )
  {
    EnumServicesStatusExW(
      v5,
      SC_ENUM_PROCESS_INFO,
      0x30u,
      3u,
      0,
      0,
      &pcbBytesNeeded,
      &ServicesReturned,
      &ResumeHandle,
      0);
    if ( GetLastError() == 234 )
    {
      v8 = pcbBytesNeeded;
      if ( pcbBytesNeeded )
      {
        v9 = 1;
        while ( 1 )
        {
          cbBufSize = v8 * v9;
          lpServices = (BYTE *)Dns_Allocate(cbBufSize);
          if ( !lpServices )
            goto LABEL_31;
          if ( EnumServicesStatusExW(
                 v6,
                 SC_ENUM_PROCESS_INFO,
                 0x30u,
                 3u,
                 lpServices,
                 cbBufSize,
                 &pcbBytesNeeded,
                 &ServicesReturned,
                 &ResumeHandle,
                 0) )
          {
            break;
          }
          if ( GetLastError() != 234 )
          {
            v1 = 12;
            goto LABEL_32;
          }
          v1 = 0;
          if ( !pcbBytesNeeded )
          {
            v1 = 13;
            goto LABEL_32;
          }
          MIDL_user_free(lpServices);
          if ( (unsigned int)++v9 > 2 )
          {
            v1 = -2147019873;
            goto LABEL_32;
          }
          v8 = pcbBytesNeeded;
        }
        if ( !ServicesReturned )
          goto LABEL_32;
        v3 = (struct _ZT_SERVICE_DATA_ARRAY *)Dns_Allocate(520LL * (ServicesReturned - 1) + 528);
        if ( !v3 )
        {
LABEL_31:
          v1 = -2147024882;
          goto LABEL_32;
        }
        v1 = 0;
        for ( i = 0; i < ServicesReturned; i = v15 + 1 )
        {
          v13 = 520LL * i;
          v14 = 56LL * i;
          *(_QWORD *)((char *)v3 + v13 + 8) = *(unsigned int *)&lpServices[v14 + 44];
          v1 = StringCchCopyW(
                 (unsigned __int16 *)((char *)v3 + v13 + 16),
                 v11,
                 *(const unsigned __int16 **)&lpServices[v14]);
          if ( v1 < 0 )
            goto LABEL_32;
        }
        *(_DWORD *)v3 = ServicesReturned;
        *a1 = v3;
        v3 = 0;
      }
      else
      {
        v1 = 13;
      }
    }
    else
    {
      v1 = 12;
    }
LABEL_32:
    CloseServiceHandle(v6);
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 >= 0 )
      v1 = -2147418113;
  }
  MIDL_user_free(lpServices);
  MIDL_user_free(v3);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 27, WPP_75f1376952c23bd1eaf4acbe431c69f9_Traceguids, (unsigned int)v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180053b20  push    rbp
0x180053b22  push    rbx
0x180053b23  push    rsi
0x180053b24  push    rdi
0x180053b25  push    r12
0x180053b27  push    r13
0x180053b29  push    r14
0x180053b2b  push    r15
0x180053b2d  mov     rbp, rsp
0x180053b30  sub     rsp, 78h
0x180053b34  mov     rax, cs:__security_cookie
0x180053b3b  xor     rax, rsp
0x180053b3e  mov     [rbp+var_10], rax
0x180053b42  xor     ebx, ebx
0x180053b44  mov     r13, rcx
0x180053b47  mov     [rbp+var_24], ebx
0x180053b4a  mov     edi, ebx
0x180053b4c  mov     [rbp+var_1C], ebx
0x180053b4f  mov     r14d, ebx
0x180053b52  mov     [rbp+ServicesReturned], ebx
0x180053b55  mov     [rbp+ResumeHandle], ebx
0x180053b58  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180053b5f  jz      short loc_180053B78
0x180053b61  lea     edx, [rbx+1Ah]
0x180053b64  mov     ecx, 40Bh
0x180053b69  mov     r9, r13
0x180053b6c  lea     r8, WPP_75f1376952c23bd1eaf4acbe431c69f9_Traceguids
0x180053b73  call    WPP_SF_q
0x180053b78  xor     edx, edx; lpDatabaseName
0x180053b7a  xor     ecx, ecx; lpMachineName
0x180053b7c  lea     r8d, [rdx+4]; dwDesiredAccess
0x180053b80  call    cs:__imp_OpenSCManagerW
0x180053b86  mov     r15, rax
0x180053b89  test    rax, rax
0x180053b8c  jnz     short loc_180053BB9
0x180053b8e  call    cs:__imp_GetLastError
0x180053b94  mov     ebx, eax
0x180053b96  test    eax, eax
0x180053b98  jle     short loc_180053BA3
0x180053b9a  movzx   ebx, ax
0x180053b9d  or      ebx, 80070000h
0x180053ba3  test    ebx, ebx
0x180053ba5  mov     [rbp+var_24], 0D8h
0x180053bac  mov     eax, 8000FFFFh
0x180053bb1  cmovns  ebx, eax
0x180053bb4  jmp     loc_180053D82
0x180053bb9  mov     [rsp+78h+pszGroupName], rbx; pszGroupName
0x180053bbe  lea     rax, [rbp+ResumeHandle]
0x180053bc2  mov     [rsp+78h+lpResumeHandle], rax; lpResumeHandle
0x180053bc7  xor     edx, edx; InfoLevel
0x180053bc9  lea     rax, [rbp+ServicesReturned]
0x180053bcd  mov     rcx, r15; hSCManager
0x180053bd0  mov     [rsp+78h+lpServicesReturned], rax; lpServicesReturned
0x180053bd5  lea     rax, [rbp+var_1C]
0x180053bd9  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180053bde  mov     [rsp+78h+cbBufSize], ebx; cbBufSize
0x180053be2  lea     r9d, [rdx+3]; dwServiceState
0x180053be6  lea     r8d, [rdx+30h]; dwServiceType
0x180053bea  mov     [rsp+78h+lpServices], rbx; lpServices
0x180053bef  call    cs:__imp_EnumServicesStatusExW
0x180053bf5  call    cs:__imp_GetLastError
0x180053bfb  cmp     eax, 0EAh
0x180053c00  jz      short loc_180053C13
0x180053c02  mov     ebx, 0Ch
0x180053c07  mov     [rbp+var_24], 0E6h
0x180053c0e  jmp     loc_180053D79
0x180053c13  mov     ecx, [rbp+var_1C]
0x180053c16  test    ecx, ecx
0x180053c18  jnz     short loc_180053C29
0x180053c1a  lea     ebx, [rcx+0Dh]
0x180053c1d  mov     [rbp+var_24], 0E7h
0x180053c24  jmp     loc_180053D79
0x180053c29  mov     esi, 1
0x180053c2e  mov     eax, esi
0x180053c30  imul    eax, ecx
0x180053c33  mov     ecx, eax
0x180053c35  mov     r12d, eax
0x180053c38  call    Dns_Allocate
0x180053c3d  mov     r14, rax
0x180053c40  test    rax, rax
0x180053c43  jz      loc_180053D6D
0x180053c49  mov     [rsp+78h+pszGroupName], rdi; pszGroupName
0x180053c4e  lea     rax, [rbp+ResumeHandle]
0x180053c52  mov     [rsp+78h+lpResumeHandle], rax; lpResumeHandle
0x180053c57  xor     edx, edx; InfoLevel
0x180053c59  lea     rax, [rbp+ServicesReturned]
0x180053c5d  mov     rcx, r15; hSCManager
0x180053c60  mov     [rsp+78h+lpServicesReturned], rax; lpServicesReturned
0x180053c65  lea     rax, [rbp+var_1C]
0x180053c69  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180053c6e  mov     [rsp+78h+cbBufSize], r12d; cbBufSize
0x180053c73  lea     r9d, [rdx+3]; dwServiceState
0x180053c77  lea     r8d, [rdx+30h]; dwServiceType
0x180053c7b  mov     [rsp+78h+lpServices], r14; lpServices
0x180053c80  call    cs:__imp_EnumServicesStatusExW
0x180053c86  test    eax, eax
0x180053c88  jnz     short loc_180053CE8
0x180053c8a  call    cs:__imp_GetLastError
0x180053c90  cmp     eax, 0EAh
0x180053c95  jnz     short loc_180053CD7
0x180053c97  xor     ebx, ebx
0x180053c99  cmp     [rbp+var_1C], ebx
0x180053c9c  jbe     short loc_180053CC6
0x180053c9e  mov     rcx, r14; void *
0x180053ca1  call    MIDL_user_free
0x180053ca6  inc     esi
0x180053ca8  cmp     esi, 2
0x180053cab  ja      short loc_180053CB5
0x180053cad  mov     ecx, [rbp+var_1C]
0x180053cb0  jmp     loc_180053C2E
0x180053cb5  mov     ebx, 8007139Fh
0x180053cba  mov     [rbp+var_24], 10Dh
0x180053cc1  jmp     loc_180053D79
0x180053cc6  mov     ebx, 0Dh
0x180053ccb  mov     [rbp+var_24], 102h
0x180053cd2  jmp     loc_180053D79
0x180053cd7  mov     ebx, 0Ch
0x180053cdc  mov     [rbp+var_24], 101h
0x180053ce3  jmp     loc_180053D79
0x180053ce8  mov     eax, [rbp+ServicesReturned]
0x180053ceb  test    eax, eax
0x180053ced  jz      loc_180053D79
0x180053cf3  lea     ecx, [rax-1]
0x180053cf6  imul    rcx, 208h
0x180053cfd  add     rcx, 210h
0x180053d04  call    Dns_Allocate
0x180053d09  mov     rdi, rax
0x180053d0c  test    rax, rax
0x180053d0f  jnz     short loc_180053D1A
0x180053d11  mov     [rbp+var_24], 116h
0x180053d18  jmp     short loc_180053D74
0x180053d1a  xor     ebx, ebx
0x180053d1c  xor     r11d, r11d
0x180053d1f  mov     eax, [rbp+ServicesReturned]
0x180053d22  cmp     r11d, eax
0x180053d25  jnb     short loc_180053D63
0x180053d27  mov     eax, r11d
0x180053d2a  imul    rcx, rax, 208h
0x180053d31  imul    r8, rax, 38h ; '8'
0x180053d35  mov     eax, [r8+r14+2Ch]
0x180053d3a  mov     [rcx+rdi+8], rax
0x180053d3f  add     rcx, 10h
0x180053d43  mov     r8, [r8+r14]; unsigned __int16 *
0x180053d47  add     rcx, rdi; unsigned __int16 *
0x180053d4a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180053d4f  mov     ebx, eax
0x180053d51  test    eax, eax
0x180053d53  js      short loc_180053D5A
0x180053d55  inc     r11d
0x180053d58  jmp     short loc_180053D1F
0x180053d5a  mov     [rbp+var_24], 11Dh
0x180053d61  jmp     short loc_180053D79
0x180053d63  mov     [rdi], eax
0x180053d65  mov     [r13+0], rdi
0x180053d69  xor     edi, edi
0x180053d6b  jmp     short loc_180053D79
0x180053d6d  mov     [rbp+var_24], 0EEh
0x180053d74  mov     ebx, 8007000Eh
0x180053d79  mov     rcx, r15; hSCObject
0x180053d7c  call    cs:__imp_CloseServiceHandle
0x180053d82  mov     rcx, r14; void *
0x180053d85  call    MIDL_user_free
0x180053d8a  mov     rcx, rdi; void *
0x180053d8d  call    MIDL_user_free
0x180053d92  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180053d99  jz      short loc_180053DB4
0x180053d9b  mov     edx, 1Bh
0x180053da0  lea     r8, WPP_75f1376952c23bd1eaf4acbe431c69f9_Traceguids
0x180053da7  mov     ecx, 40Bh
0x180053dac  mov     r9d, ebx
0x180053daf  call    WPP_SF_d
0x180053db4  mov     eax, ebx
0x180053db6  mov     rcx, [rbp+var_10]
0x180053dba  xor     rcx, rsp; StackCookie
0x180053dbd  call    __security_check_cookie
0x180053dc2  add     rsp, 78h
0x180053dc6  pop     r15
0x180053dc8  pop     r14
0x180053dca  pop     r13
0x180053dcc  pop     r12
0x180053dce  pop     rdi
0x180053dcf  pop     rsi
0x180053dd0  pop     rbx
0x180053dd1  pop     rbp
0x180053dd2  retn
```
