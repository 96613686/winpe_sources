# CMsiOpExecute::GetSDFromService(SC_HANDLE__ * const,IMsiStream * &)

- ea: `0x1801e9cf0`
- end: `0x1801e9f9f`
- name: `?GetSDFromService@CMsiOpExecute@@IEAA_NQEAUSC_HANDLE__@@AEAPEAVIMsiStream@@@Z`
- size: `687`
- prototype: `bool(CMsiOpExecute *__hidden this, struct SC_HANDLE__ *const, struct IMsiStream **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f7864`

## callees

- `0x18000c4bc`
- `0x180018d44`
- `0x180019cc0`
- `0x1801e9cf0`
- `0x1801f90d8`
- `0x1802651d2`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `ADVAPI32!QueryServiceObjectSecurity` at `0x1801e9dbc`
- `ADVAPI32!QueryServiceObjectSecurity` at `0x1801e9e85`
- `ADVAPI32!QueryServiceObjectSecurity` at `0x1801e9dbc`
- `ADVAPI32!QueryServiceObjectSecurity` at `0x1801e9e85`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1801e9ec6`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1801e9ec6`
- `KERNEL32!GetLastError` at `0x1801e9dd1`
- `KERNEL32!GetLastError` at `0x1801e9e06`
- `KERNEL32!GetLastError` at `0x1801e9ea2`
- `KERNEL32!GetLastError` at `0x1801e9eed`
- `KERNEL32!GetLastError` at `0x1801e9dd1`
- `KERNEL32!GetLastError` at `0x1801e9e06`
- `KERNEL32!GetLastError` at `0x1801e9ea2`
- `KERNEL32!GetLastError` at `0x1801e9eed`

## string_xrefs

- `0x1801e9d47`: `Error: Invalid Argument. Failed while querying service security.`
- `0x1801e9e22`: `Error %d. Failed to allocate space while querying service security.`
- `0x1801e9ef9`: `Error %d. Failed to allocate space while querying service security.`
- `0x1801e9eae`: `Error %d. Failed while querying service security.`

## pseudocode

```c
char __fastcall CMsiOpExecute::GetSDFromService(
        CMsiOpExecute *this,
        struct SC_HANDLE__ *const a2,
        struct IMsiStream **a3)
{
  DWORD LastError; // eax
  PSECURITY_DESCRIPTOR v6; // r8
  DWORD v7; // eax
  PSECURITY_DESCRIPTOR v8; // rcx
  const unsigned __int16 *v9; // r9
  char *MemoryStream; // rax
  DWORD cbBufSize[4]; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR lpSecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  int v14; // [rsp+78h] [rbp-88h]
  _BYTE SecurityDescriptor[1024]; // [rsp+80h] [rbp-80h] BYREF

  if ( !a2 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"Error: Invalid Argument. Failed while querying service security.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    return 0;
  }
  cbBufSize[0] = 1024;
  memset_0(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v14 = 1024;
  lpSecurityDescriptor = SecurityDescriptor;
  if ( !QueryServiceObjectSecurity(a2, 7u, SecurityDescriptor, 0x400u, cbBufSize) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      if ( g_dmDiagnosticMode )
        goto LABEL_14;
      goto LABEL_21;
    }
    CTempBuffer<unsigned char,1024>::SetSize(&lpSecurityDescriptor, cbBufSize[0]);
    v6 = lpSecurityDescriptor;
    if ( !lpSecurityDescriptor )
    {
      if ( g_dmDiagnosticMode )
      {
        v7 = GetLastError();
        DebugString(
          10,
          0,
          0,
          L"Error %d. Failed to allocate space while querying service security.",
          (const unsigned __int16 *)v7,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
        v6 = lpSecurityDescriptor;
      }
      if ( v14 <= 1024 )
        return 0;
      v8 = v6;
      goto LABEL_23;
    }
    if ( !QueryServiceObjectSecurity(a2, 7u, lpSecurityDescriptor, cbBufSize[0], cbBufSize) )
    {
      if ( g_dmDiagnosticMode )
      {
        LastError = GetLastError();
LABEL_14:
        v9 = L"Error %d. Failed while querying service security.";
LABEL_20:
        DebugString(
          10,
          0,
          0,
          v9,
          (const unsigned __int16 *)LastError,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
LABEL_21:
      if ( v14 <= 1024 )
        return 0;
      v8 = lpSecurityDescriptor;
LABEL_23:
      operator delete(v8);
      return 0;
    }
  }
  cbBufSize[0] = GetSecurityDescriptorLength(lpSecurityDescriptor);
  MemoryStream = AllocateMemoryStream(cbBufSize[0], a3);
  if ( !MemoryStream )
  {
    if ( g_dmDiagnosticMode )
    {
      LastError = GetLastError();
      v9 = L"Error %d. Failed to allocate space while querying service security.";
      goto LABEL_20;
    }
    goto LABEL_21;
  }
  memcpy_0(MemoryStream, lpSecurityDescriptor, cbBufSize[0]);
  if ( v14 > 1024 )
    operator delete(lpSecurityDescriptor);
  return 1;
}

```

## disassembly

```asm
0x1801e9cf0  mov     [rsp-8+arg_0], rbx
0x1801e9cf5  mov     [rsp-8+arg_18], rsi
0x1801e9cfa  push    rbp
0x1801e9cfb  push    rdi
0x1801e9cfc  push    r14
0x1801e9cfe  lea     rbp, [rsp-390h]
0x1801e9d06  sub     rsp, 490h
0x1801e9d0d  mov     rax, cs:__security_cookie
0x1801e9d14  xor     rax, rsp
0x1801e9d17  mov     [rbp+3A0h+var_20], rax
0x1801e9d1e  xor     esi, esi
0x1801e9d20  mov     rdi, r8
0x1801e9d23  mov     rbx, rdx
0x1801e9d26  test    rdx, rdx
0x1801e9d29  jnz     short loc_1801E9D7C
0x1801e9d2b  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801e9d31  jz      loc_1801E9F4E
0x1801e9d37  lea     rcx, aNull; "(NULL)"
0x1801e9d3e  mov     [rsp+4A0h+var_448], rsi; void *
0x1801e9d43  mov     [rsp+4A0h+var_450], esi; unsigned int
0x1801e9d47  lea     r9, aErrorInvalidAr_0; "Error: Invalid Argument. Failed while q"...
0x1801e9d4e  mov     [rsp+4A0h+var_458], rcx; unsigned __int16 *
0x1801e9d53  xor     r8d, r8d; int
0x1801e9d56  mov     [rsp+4A0h+var_460], rcx; unsigned __int16 *
0x1801e9d5b  mov     [rsp+4A0h+var_468], rcx; unsigned __int16 *
0x1801e9d60  mov     [rsp+4A0h+var_470], rcx; unsigned __int16 *
0x1801e9d65  mov     [rsp+4A0h+var_478], rcx; unsigned __int16 *
0x1801e9d6a  mov     [rsp+4A0h+pcbBytesNeeded], rcx; unsigned __int16 *
0x1801e9d6f  lea     ecx, [rdx+0Ah]; int
0x1801e9d72  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801e9d77  jmp     loc_1801E9F4E
0x1801e9d7c  mov     r14d, 400h
0x1801e9d82  lea     rcx, [rbp+3A0h+SecurityDescriptor]; void *
0x1801e9d86  mov     r8d, r14d; Size
0x1801e9d89  mov     [rsp+4A0h+cbBufSize], r14d
0x1801e9d8e  xor     edx, edx; Val
0x1801e9d90  call    memset_0
0x1801e9d95  lea     rax, [rbp+3A0h+SecurityDescriptor]
0x1801e9d99  mov     [rsp+4A0h+var_428], r14d
0x1801e9d9e  mov     [rsp+4A0h+lpSecurityDescriptor], rax
0x1801e9da3  lea     r8, [rbp+3A0h+SecurityDescriptor]; lpSecurityDescriptor
0x1801e9da7  lea     rax, [rsp+4A0h+cbBufSize]
0x1801e9dac  mov     r9d, r14d; cbBufSize
0x1801e9daf  mov     edx, 7; dwSecurityInformation
0x1801e9db4  mov     [rsp+4A0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801e9db9  mov     rcx, rbx; hService
0x1801e9dbc  call    cs:__imp_QueryServiceObjectSecurity
0x1801e9dc3  nop     dword ptr [rax+rax+00h]
0x1801e9dc8  cmp     eax, 1
0x1801e9dcb  jz      loc_1801E9EC1
0x1801e9dd1  call    cs:__imp_GetLastError
0x1801e9dd8  nop     dword ptr [rax+rax+00h]
0x1801e9ddd  cmp     eax, 7Ah ; 'z'
0x1801e9de0  jnz     loc_1801E9EB7
0x1801e9de6  mov     edx, [rsp+4A0h+cbBufSize]
0x1801e9dea  lea     rcx, [rsp+4A0h+lpSecurityDescriptor]
0x1801e9def  call    ?SetSize@?$CTempBuffer@E$0EAA@@@QEAAXH@Z; CTempBuffer<uchar,1024>::SetSize(int)
0x1801e9df4  mov     r8, [rsp+4A0h+lpSecurityDescriptor]; lpSecurityDescriptor
0x1801e9df9  test    r8, r8
0x1801e9dfc  jnz     short loc_1801E9E6E
0x1801e9dfe  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801e9e04  jz      short loc_1801E9E5B
0x1801e9e06  call    cs:__imp_GetLastError
0x1801e9e0d  nop     dword ptr [rax+rax+00h]
0x1801e9e12  lea     rcx, aNull; "(NULL)"
0x1801e9e19  mov     [rsp+4A0h+var_448], rsi; void *
0x1801e9e1e  mov     [rsp+4A0h+var_450], esi; unsigned int
0x1801e9e22  lea     r9, aErrorDFailedTo_0; "Error %d. Failed to allocate space whil"...
0x1801e9e29  mov     [rsp+4A0h+var_458], rcx; unsigned __int16 *
0x1801e9e2e  xor     edx, edx; unsigned __int16
0x1801e9e30  mov     [rsp+4A0h+var_460], rcx; unsigned __int16 *
0x1801e9e35  xor     r8d, r8d; int
0x1801e9e38  mov     [rsp+4A0h+var_468], rcx; unsigned __int16 *
0x1801e9e3d  mov     [rsp+4A0h+var_470], rcx; unsigned __int16 *
0x1801e9e42  mov     [rsp+4A0h+var_478], rcx; unsigned __int16 *
0x1801e9e47  lea     ecx, [rdx+0Ah]; int
0x1801e9e4a  mov     eax, eax
0x1801e9e4c  mov     [rsp+4A0h+pcbBytesNeeded], rax; unsigned __int16 *
0x1801e9e51  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801e9e56  mov     r8, [rsp+4A0h+lpSecurityDescriptor]
0x1801e9e5b  cmp     [rsp+4A0h+var_428], r14d
0x1801e9e60  jle     loc_1801E9F4E
0x1801e9e66  mov     rcx, r8
0x1801e9e69  jmp     loc_1801E9F49
0x1801e9e6e  mov     r9d, [rsp+4A0h+cbBufSize]; cbBufSize
0x1801e9e73  lea     rax, [rsp+4A0h+cbBufSize]
0x1801e9e78  mov     edx, 7; dwSecurityInformation
0x1801e9e7d  mov     [rsp+4A0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801e9e82  mov     rcx, rbx; hService
0x1801e9e85  call    cs:__imp_QueryServiceObjectSecurity
0x1801e9e8c  nop     dword ptr [rax+rax+00h]
0x1801e9e91  cmp     eax, 1
0x1801e9e94  jz      short loc_1801E9EC1
0x1801e9e96  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801e9e9c  jz      loc_1801E9F3D
0x1801e9ea2  call    cs:__imp_GetLastError
0x1801e9ea9  nop     dword ptr [rax+rax+00h]
0x1801e9eae  lea     r9, aErrorDFailedWh; "Error %d. Failed while querying service"...
0x1801e9eb5  jmp     short loc_1801E9F00
0x1801e9eb7  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801e9ebd  jz      short loc_1801E9F3D
0x1801e9ebf  jmp     short loc_1801E9EAE
0x1801e9ec1  mov     rcx, [rsp+4A0h+lpSecurityDescriptor]; pSecurityDescriptor
0x1801e9ec6  call    cs:__imp_GetSecurityDescriptorLength
0x1801e9ecd  nop     dword ptr [rax+rax+00h]
0x1801e9ed2  mov     ecx, eax; unsigned int
0x1801e9ed4  mov     [rsp+4A0h+cbBufSize], eax
0x1801e9ed8  mov     rdx, rdi; struct IMsiStream **
0x1801e9edb  call    ?AllocateMemoryStream@@YAPEADIAEAPEAVIMsiStream@@@Z; AllocateMemoryStream(uint,IMsiStream * &)
0x1801e9ee0  test    rax, rax
0x1801e9ee3  jnz     short loc_1801E9F52
0x1801e9ee5  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x1801e9eeb  jz      short loc_1801E9F3D
0x1801e9eed  call    cs:__imp_GetLastError
0x1801e9ef4  nop     dword ptr [rax+rax+00h]
0x1801e9ef9  lea     r9, aErrorDFailedTo_0; "Error %d. Failed to allocate space whil"...
0x1801e9f00  mov     [rsp+4A0h+var_448], rsi; void *
0x1801e9f05  lea     rcx, aNull; "(NULL)"
0x1801e9f0c  mov     [rsp+4A0h+var_450], esi; unsigned int
0x1801e9f10  xor     edx, edx; unsigned __int16
0x1801e9f12  mov     [rsp+4A0h+var_458], rcx; unsigned __int16 *
0x1801e9f17  xor     r8d, r8d; int
0x1801e9f1a  mov     [rsp+4A0h+var_460], rcx; unsigned __int16 *
0x1801e9f1f  mov     [rsp+4A0h+var_468], rcx; unsigned __int16 *
0x1801e9f24  mov     [rsp+4A0h+var_470], rcx; unsigned __int16 *
0x1801e9f29  mov     [rsp+4A0h+var_478], rcx; unsigned __int16 *
0x1801e9f2e  lea     ecx, [rdx+0Ah]; int
0x1801e9f31  mov     eax, eax
0x1801e9f33  mov     [rsp+4A0h+pcbBytesNeeded], rax; unsigned __int16 *
0x1801e9f38  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801e9f3d  cmp     [rsp+4A0h+var_428], r14d
0x1801e9f42  jle     short loc_1801E9F4E
0x1801e9f44  mov     rcx, [rsp+4A0h+lpSecurityDescriptor]; void *
0x1801e9f49  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801e9f4e  xor     al, al
0x1801e9f50  jmp     short loc_1801E9F77
0x1801e9f52  mov     r8d, [rsp+4A0h+cbBufSize]; Size
0x1801e9f57  mov     rcx, rax; void *
0x1801e9f5a  mov     rdx, [rsp+4A0h+lpSecurityDescriptor]; Src
0x1801e9f5f  call    memcpy_0
0x1801e9f64  cmp     [rsp+4A0h+var_428], r14d
0x1801e9f69  jle     short loc_1801E9F75
0x1801e9f6b  mov     rcx, [rsp+4A0h+lpSecurityDescriptor]; void *
0x1801e9f70  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801e9f75  mov     al, 1
0x1801e9f77  mov     rcx, [rbp+3A0h+var_20]
0x1801e9f7e  xor     rcx, rsp; StackCookie
0x1801e9f81  call    __security_check_cookie
0x1801e9f86  lea     r11, [rsp+4A0h+var_10]
0x1801e9f8e  mov     rbx, [r11+20h]
0x1801e9f92  mov     rsi, [r11+38h]
0x1801e9f96  mov     rsp, r11
0x1801e9f99  pop     r14
0x1801e9f9b  pop     rdi
0x1801e9f9c  pop     rbp
0x1801e9f9d  retn
```
