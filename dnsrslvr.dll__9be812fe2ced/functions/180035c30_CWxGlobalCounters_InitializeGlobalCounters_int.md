# CWxGlobalCounters::InitializeGlobalCounters(int)

- ea: `0x180035c30`
- end: `0x180035e9d`
- name: `?InitializeGlobalCounters@CWxGlobalCounters@@AEAAJH@Z`
- size: `621`
- prototype: `__int64 __fastcall(CWxGlobalCounters *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003db8c`

## callees

- `0x180035c30`
- `0x180046ec0`
- `0x180047818`
- `0x18007337c`
- `0x180083a10`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035de8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035e78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035e78`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180035dda`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180035dda`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180035d5a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180035d5a`

## pseudocode

```c
__int64 __fastcall CWxGlobalCounters::InitializeGlobalCounters(CWxGlobalCounters *this)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  int v5; // edi
  HANDLE v6; // rbx
  signed int v7; // eax
  DWORD LastError; // r14d
  _QWORD *v9; // rsi
  signed int v10; // eax
  unsigned int dwMaximumSizeLow; // [rsp+20h] [rbp-E0h]
  unsigned int v13; // [rsp+40h] [rbp-C0h]
  unsigned int v14; // [rsp+50h] [rbp-B0h]
  unsigned int *v15; // [rsp+58h] [rbp-A8h]
  unsigned int v16; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+64h] [rbp-9Ch]
  int v18; // [rsp+68h] [rbp-98h]
  int v19; // [rsp+6Ch] [rbp-94h]
  unsigned int v20[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _SID *v21[4]; // [rsp+80h] [rbp-80h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v23[560]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(v23, 0, 0x228u);
  v16 = -1609564160;
  v20[0] = 12;
  v21[0] = (struct _SID *)c_rgbWorldSid;
  v21[1] = (struct _SID *)c_rgbWcmsvcSid;
  v21[2] = (struct _SID *)c_rgbDnsCacheSid;
  v21[3] = (struct _SID *)c_rgbWinHttpAutoProxySvcSid;
  v17 = 0x10000000;
  v18 = 0x10000000;
  v19 = 0x10000000;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  v20[1] = 32;
  v20[2] = 32;
  v20[3] = 32;
  if ( (xmmword_1800AB5A0 & 0x20) != 0 )
    WPP_SF_ql();
  v5 = ConstructSecurityDescriptorInternal(v2, v1, v3, v4, dwMaximumSizeLow, v21, v20, &v16, v13, v23, v14, v15);
  if ( v5 < 0 )
  {
    v17 = 297;
LABEL_24:
    v6 = 0;
    goto LABEL_25;
  }
  FileMappingAttributes.lpSecurityDescriptor = v23;
  v6 = CreateFileMappingW(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         &FileMappingAttributes,
         4u,
         0,
         8u,
         L"Global\\F932B6C7-3A20-46A0-B8A0-8894AA421973");
  if ( v6 )
  {
    LastError = GetLastError();
    if ( (xmmword_1800AB5A0 & 0x20) != 0 )
      WPP_SF_d(1029, 27, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids, LastError == 183);
    v9 = MapViewOfFile(v6, 2u, 0, 0, 8u);
    if ( v9 )
    {
      v5 = 0;
      if ( LastError != 183 )
      {
        if ( (xmmword_1800AB5A0 & 0x20) != 0 )
          WPP_SF_(1029, 29, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids);
        *v9 = 0;
      }
      qword_1800ABB90 = (__int64)v6;
      qword_1800ABB98 = (__int64)v9;
      goto LABEL_24;
    }
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    v17 = 337;
    if ( v5 >= 0 )
      v5 = -2147418113;
  }
  else
  {
    v7 = GetLastError();
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    v17 = 307;
    if ( v5 >= 0 )
      v5 = -2147418113;
  }
LABEL_25:
  if ( (xmmword_1800AB5A0 & 0x20) != 0 )
    WPP_SF_d(1029, 30, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids, (unsigned int)v5);
  if ( v6 )
    CloseHandle(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180035c30  push    rbp
0x180035c32  push    rbx
0x180035c33  push    rsi
0x180035c34  push    rdi
0x180035c35  push    r14
0x180035c37  lea     rbp, [rsp-200h]
0x180035c3f  sub     rsp, 300h
0x180035c46  mov     rax, cs:__security_cookie
0x180035c4d  xor     rax, rsp
0x180035c50  mov     [rbp+220h+var_30], rax
0x180035c57  xor     edx, edx; Val
0x180035c59  mov     [rsp+320h+var_2BC], 0
0x180035c61  mov     r8d, 228h; Size
0x180035c67  lea     rcx, [rbp+220h+var_260]; void *
0x180035c6b  call    memset_0
0x180035c70  xor     eax, eax
0x180035c72  mov     [rsp+320h+var_2C0], 0A0100000h
0x180035c7a  mov     qword ptr [rbp+220h+FileMappingAttributes.bInheritHandle], rax
0x180035c7e  xorps   xmm0, xmm0
0x180035c81  lea     rax, c_rgbWorldSid
0x180035c88  mov     [rsp+320h+var_2B0], 0Ch
0x180035c90  mov     [rbp+220h+var_2A0], rax
0x180035c94  lea     rax, c_rgbWcmsvcSid
0x180035c9b  mov     [rbp+220h+var_298], rax
0x180035c9f  lea     rax, c_rgbDnsCacheSid
0x180035ca6  mov     [rbp+220h+var_290], rax
0x180035caa  lea     rax, c_rgbWinHttpAutoProxySvcSid
0x180035cb1  mov     [rbp+220h+var_288], rax
0x180035cb5  mov     eax, 10000000h
0x180035cba  mov     [rsp+320h+var_2BC], eax
0x180035cbe  mov     [rsp+320h+var_2B8], eax
0x180035cc2  mov     [rsp+320h+var_2B4], eax
0x180035cc6  movups  xmmword ptr [rbp+220h+FileMappingAttributes.nLength], xmm0
0x180035cca  mov     [rsp+320h+var_2AC], 20h ; ' '
0x180035cd2  mov     [rsp+320h+var_2A8], 20h ; ' '
0x180035cda  mov     [rsp+320h+var_2A4], 20h ; ' '
0x180035ce2  test    byte ptr cs:xmmword_1800AB5A0, 20h
0x180035ce9  jz      short loc_180035CF0
0x180035ceb  call    WPP_SF_ql
0x180035cf0  lea     rax, [rbp+220h+var_260]
0x180035cf4  mov     [rsp+320h+var_2D8], rax; unsigned __int8 *
0x180035cf9  lea     rax, [rsp+320h+var_2C0]
0x180035cfe  mov     [rsp+320h+var_2E8], rax; unsigned int *
0x180035d03  lea     rax, [rsp+320h+var_2B0]
0x180035d08  mov     [rsp+320h+var_2F0], rax; unsigned int *
0x180035d0d  lea     rax, [rbp+220h+var_2A0]
0x180035d11  mov     [rsp+320h+lpName], rax; struct _SID **
0x180035d16  call    ?ConstructSecurityDescriptorInternal@@YAJKKKKKPEAPEAU_SID@@PEAK1KPEAEK1@Z; ConstructSecurityDescriptorInternal(ulong,ulong,ulong,ulong,ulong,_SID * *,ulong *,ulong *,ulong,uchar *,ulong,ulong *)
0x180035d1b  mov     edi, eax
0x180035d1d  test    eax, eax
0x180035d1f  jns     short loc_180035D2E
0x180035d21  mov     [rsp+320h+var_2BC], 129h
0x180035d29  jmp     loc_180035E4C
0x180035d2e  lea     rax, [rbp+220h+var_260]
0x180035d32  mov     edi, 8
0x180035d37  mov     [rbp+220h+FileMappingAttributes.lpSecurityDescriptor], rax
0x180035d3b  lea     rdx, [rbp+220h+FileMappingAttributes]; lpFileMappingAttributes
0x180035d3f  lea     rax, Name; "Global\\F932B6C7-3A20-46A0-B8A0-8894AA4"...
0x180035d46  xor     r9d, r9d; dwMaximumSizeHigh
0x180035d49  mov     [rsp+320h+lpName], rax; lpName
0x180035d4e  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180035d52  lea     r8d, [rdi-4]; flProtect
0x180035d56  mov     [rsp+320h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x180035d5a  call    cs:__imp_CreateFileMappingW
0x180035d60  mov     rbx, rax
0x180035d63  test    rax, rax
0x180035d66  jnz     short loc_180035D94
0x180035d68  call    cs:__imp_GetLastError
0x180035d6e  mov     edi, eax
0x180035d70  test    eax, eax
0x180035d72  jle     short loc_180035D7D
0x180035d74  movzx   edi, ax
0x180035d77  or      edi, 80070000h
0x180035d7d  test    edi, edi
0x180035d7f  mov     [rsp+320h+var_2BC], 133h
0x180035d87  mov     eax, 8000FFFFh
0x180035d8c  cmovns  edi, eax
0x180035d8f  jmp     loc_180035E4E
0x180035d94  call    cs:__imp_GetLastError
0x180035d9a  xor     r9d, r9d
0x180035d9d  mov     r14d, eax
0x180035da0  cmp     eax, 0B7h
0x180035da5  setz    r9b
0x180035da9  test    byte ptr cs:xmmword_1800AB5A0, 20h
0x180035db0  jz      short loc_180035DC8
0x180035db2  mov     edx, 1Bh
0x180035db7  lea     r8, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids
0x180035dbe  mov     ecx, 405h
0x180035dc3  call    WPP_SF_d
0x180035dc8  xor     r9d, r9d; dwFileOffsetLow
0x180035dcb  mov     qword ptr [rsp+320h+dwMaximumSizeLow], rdi; dwNumberOfBytesToMap
0x180035dd0  xor     r8d, r8d; dwFileOffsetHigh
0x180035dd3  mov     rcx, rbx; hFileMappingObject
0x180035dd6  lea     edx, [r9+2]; dwDesiredAccess
0x180035dda  call    cs:__imp_MapViewOfFile
0x180035de0  mov     rsi, rax
0x180035de3  test    rax, rax
0x180035de6  jnz     short loc_180035E11
0x180035de8  call    cs:__imp_GetLastError
0x180035dee  mov     edi, eax
0x180035df0  test    eax, eax
0x180035df2  jle     short loc_180035DFD
0x180035df4  movzx   edi, ax
0x180035df7  or      edi, 80070000h
0x180035dfd  test    edi, edi
0x180035dff  mov     [rsp+320h+var_2BC], 151h
0x180035e07  mov     eax, 8000FFFFh
0x180035e0c  cmovns  edi, eax
0x180035e0f  jmp     short loc_180035E4E
0x180035e11  xor     edi, edi
0x180035e13  cmp     r14d, 0B7h
0x180035e1a  jz      short loc_180035E3E
0x180035e1c  test    byte ptr cs:xmmword_1800AB5A0, 20h
0x180035e23  jz      short loc_180035E39
0x180035e25  lea     edx, [rdi+1Dh]
0x180035e28  mov     ecx, 405h
0x180035e2d  lea     r8, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids
0x180035e34  call    WPP_SF_
0x180035e39  xor     eax, eax
0x180035e3b  mov     [rsi], rax
0x180035e3e  mov     cs:qword_1800ABB90, rbx
0x180035e45  mov     cs:qword_1800ABB98, rsi
0x180035e4c  xor     ebx, ebx
0x180035e4e  test    byte ptr cs:xmmword_1800AB5A0, 20h
0x180035e55  jz      short loc_180035E70
0x180035e57  mov     edx, 1Eh
0x180035e5c  lea     r8, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids
0x180035e63  mov     ecx, 405h
0x180035e68  mov     r9d, edi
0x180035e6b  call    WPP_SF_d
0x180035e70  test    rbx, rbx
0x180035e73  jz      short loc_180035E7E
0x180035e75  mov     rcx, rbx; hObject
0x180035e78  call    cs:__imp_CloseHandle
0x180035e7e  mov     eax, edi
0x180035e80  mov     rcx, [rbp+220h+var_30]
0x180035e87  xor     rcx, rsp; StackCookie
0x180035e8a  call    __security_check_cookie
0x180035e8f  add     rsp, 300h
0x180035e96  pop     r14
0x180035e98  pop     rdi
0x180035e99  pop     rsi
0x180035e9a  pop     rbx
0x180035e9b  pop     rbp
0x180035e9c  retn
```
