# IkeGetMySPNAuthIp

- ea: `0x18007e36c`
- end: `0x18007e5e4`
- name: `IkeGetMySPNAuthIp`
- size: `632`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18001e4e0`
- `0x18007d270`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x1800143b0`
- `0x1800162a4`
- `0x180019e40`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x180054620`
- `0x180074314`
- `0x18007e36c`
- `0x18007f760`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007e40f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007e4c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007e40f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007e4c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e4cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e4cf`

## string_xrefs

- `0x18007e42d`: `GetComputerNameExW`

## pseudocode

```c
__int64 __fastcall IkeGetMySPNAuthIp(__int64 a1, __int64 a2)
{
  __int64 UserNameFromToken; // r14
  const WCHAR **v5; // r15
  __int64 v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // rcx
  WCHAR *v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 TlsPeerAddr; // rbx
  __int64 v13; // rcx
  int TlsMmLuid; // eax
  __int64 v15; // rcx
  const WCHAR *v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  SIZE_T dwBytes; // [rsp+30h] [rbp-49h] BYREF
  WCHAR *v21; // [rsp+38h] [rbp-41h] BYREF
  DWORD nSize; // [rsp+40h] [rbp-39h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-31h] BYREF
  char v24[32]; // [rsp+50h] [rbp-29h] BYREF
  HANDLE *p_TokenHandle; // [rsp+70h] [rbp-9h]
  __int64 v26; // [rsp+78h] [rbp-1h]
  char v27[16]; // [rsp+80h] [rbp+7h] BYREF
  char v28[16]; // [rsp+90h] [rbp+17h] BYREF

  UserNameFromToken = 0;
  nSize = 0;
  v21 = 0;
  LODWORD(dwBytes) = 0;
  TokenHandle = 0;
  TraceLogHelper("IkeGetMySPNAuthIp", 1);
  v5 = (const WCHAR **)(a2 + 56);
  if ( *(_QWORD *)(a2 + 56) )
    goto LABEL_24;
  IkeGetImpersonationHandle(a1, a2, 0, 0, &TokenHandle);
  if ( TokenHandle )
  {
    UserNameFromToken = IkeGetUserNameFromToken(TokenHandle, (_QWORD *)(a2 + 56));
    if ( UserNameFromToken )
    {
LABEL_23:
      WfpMemFree((LPCVOID *)&v21);
      goto LABEL_24;
    }
    goto LABEL_16;
  }
  if ( !GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, 0, &nSize) )
  {
    LastError = GetLastError();
    if ( LastError != 234 )
    {
      if ( LastError )
      {
LABEL_8:
        UserNameFromToken = WfpReportSysErrorAsWinError(v8, "GetComputerNameExW", LastError, 1);
        goto LABEL_22;
      }
    }
  }
  UserNameFromToken = WfpUINT32Add(nSize, 6, &dwBytes);
  if ( UserNameFromToken )
    goto LABEL_23;
  UserNameFromToken = WfpUINT32Multiply((unsigned int)dwBytes, 2, &dwBytes);
  if ( UserNameFromToken )
    goto LABEL_23;
  UserNameFromToken = WfpMemAlloc((unsigned int)dwBytes, 8u, &v21);
  if ( UserNameFromToken )
    goto LABEL_23;
  v9 = v21;
  UserNameFromToken = WfpStringCchCopyW(L"host/");
  if ( UserNameFromToken )
    goto LABEL_23;
  if ( !GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, v9 + 5, &nSize) )
  {
    LastError = GetLastError();
    goto LABEL_8;
  }
  *v5 = v9;
LABEL_16:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v10 = (__int64)*v5;
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v6);
    TlsMmLuid = IkeGetTlsMmLuid(v13);
    WPP_SF_iSS(v11, 48, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr, v10);
  }
  if ( (unsigned int)dword_180173278 <= 4 )
    goto LABEL_24;
  TokenHandle = (HANDLE)IkeGetTlsMmLuid(v6);
  p_TokenHandle = &TokenHandle;
  v26 = 8;
  v16 = (const WCHAR *)IkeGetTlsPeerAddr(v15);
  tlgCreate1Sz_wchar_t((__int64)v27, v16);
  tlgCreate1Sz_wchar_t((__int64)v28, *v5);
  tlgWriteTransfer_EtwEventWriteTransfer(
    (__int64)&dword_180173278,
    (unsigned __int8 *)qword_1801554C0,
    v17,
    v18,
    5,
    (__int64)v24);
LABEL_22:
  if ( UserNameFromToken )
    goto LABEL_23;
LABEL_24:
  TraceLogHelper("IkeGetMySPNAuthIp", 0);
  return IkeReturnError(UserNameFromToken, "IkeGetMySPNAuthIp");
}

```

## disassembly

```asm
0x18007e36c  mov     [rsp-8+arg_10], rbx
0x18007e371  push    rbp
0x18007e372  push    rsi
0x18007e373  push    rdi
0x18007e374  push    r14
0x18007e376  push    r15
0x18007e378  lea     rbp, [rsp-37h]
0x18007e37d  sub     rsp, 0B0h
0x18007e384  mov     rax, cs:__security_cookie
0x18007e38b  xor     rax, rsp
0x18007e38e  mov     [rbp+57h+var_30], rax
0x18007e392  xor     r14d, r14d
0x18007e395  mov     rbx, rdx
0x18007e398  mov     rdi, rcx
0x18007e39b  mov     [rbp+57h+nSize], r14d
0x18007e39f  lea     rcx, aIkegetmyspnaut; "IkeGetMySPNAuthIp"
0x18007e3a6  mov     [rbp+57h+var_98], r14
0x18007e3aa  mov     dword ptr [rbp+57h+dwBytes], r14d
0x18007e3ae  lea     esi, [r14+1]
0x18007e3b2  mov     [rbp+57h+TokenHandle], r14
0x18007e3b6  mov     edx, esi
0x18007e3b8  call    TraceLogHelper
0x18007e3bd  lea     r15, [rbx+38h]
0x18007e3c1  cmp     [r15], r14
0x18007e3c4  jnz     loc_18007E5A4
0x18007e3ca  lea     rax, [rbp+57h+TokenHandle]
0x18007e3ce  xor     r9d, r9d
0x18007e3d1  xor     r8d, r8d
0x18007e3d4  mov     [rsp+0D0h+var_B0], rax
0x18007e3d9  mov     rdx, rbx
0x18007e3dc  mov     rcx, rdi
0x18007e3df  call    IkeGetImpersonationHandle
0x18007e3e4  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18007e3e8  test    rcx, rcx
0x18007e3eb  jz      short loc_18007E406
0x18007e3ed  mov     rdx, r15
0x18007e3f0  call    IkeGetUserNameFromToken
0x18007e3f5  mov     r14, rax
0x18007e3f8  test    rax, rax
0x18007e3fb  jnz     loc_18007E59B
0x18007e401  jmp     loc_18007E4DD
0x18007e406  xor     edx, edx; lpBuffer
0x18007e408  lea     r8, [rbp+57h+nSize]; nSize
0x18007e40c  lea     ecx, [rdx+7]; NameType
0x18007e40f  call    cs:__imp_GetComputerNameExW
0x18007e415  test    eax, eax
0x18007e417  jnz     short loc_18007E444
0x18007e419  call    cs:__imp_GetLastError
0x18007e41f  cmp     eax, 0EAh
0x18007e424  jz      short loc_18007E444
0x18007e426  test    eax, eax
0x18007e428  jz      short loc_18007E444
0x18007e42a  mov     r8d, eax
0x18007e42d  lea     rdx, aGetcomputernam; "GetComputerNameExW"
0x18007e434  mov     r9d, esi
0x18007e437  call    WfpReportSysErrorAsWinError
0x18007e43c  mov     r14, rax
0x18007e43f  jmp     loc_18007E596
0x18007e444  mov     ecx, [rbp+57h+nSize]
0x18007e447  lea     r8, [rbp+57h+dwBytes]
0x18007e44b  mov     edi, 6
0x18007e450  mov     edx, edi
0x18007e452  call    WfpUINT32Add
0x18007e457  mov     r14, rax
0x18007e45a  test    rax, rax
0x18007e45d  jnz     loc_18007E59B
0x18007e463  mov     ecx, dword ptr [rbp+57h+dwBytes]
0x18007e466  lea     r8, [rbp+57h+dwBytes]
0x18007e46a  lea     edx, [rdi-4]
0x18007e46d  call    WfpUINT32Multiply
0x18007e472  mov     r14, rax
0x18007e475  test    rax, rax
0x18007e478  jnz     loc_18007E59B
0x18007e47e  mov     ecx, dword ptr [rbp+57h+dwBytes]; dwBytes
0x18007e481  lea     r8, [rbp+57h+var_98]
0x18007e485  lea     edx, [rdi+2]; dwFlags
0x18007e488  call    WfpMemAlloc
0x18007e48d  mov     r14, rax
0x18007e490  test    rax, rax
0x18007e493  jnz     loc_18007E59B
0x18007e499  mov     rbx, [rbp+57h+var_98]
0x18007e49d  lea     rcx, aHost; "host/"
0x18007e4a4  mov     r8, rbx
0x18007e4a7  mov     edx, edi
0x18007e4a9  call    WfpStringCchCopyW
0x18007e4ae  mov     r14, rax
0x18007e4b1  test    rax, rax
0x18007e4b4  jnz     loc_18007E59B
0x18007e4ba  lea     rdx, [rbx+0Ah]; lpBuffer
0x18007e4be  lea     r8, [rbp+57h+nSize]; nSize
0x18007e4c2  lea     ecx, [rdi+1]; NameType
0x18007e4c5  call    cs:__imp_GetComputerNameExW
0x18007e4cb  test    eax, eax
0x18007e4cd  jnz     short loc_18007E4DA
0x18007e4cf  call    cs:__imp_GetLastError
0x18007e4d5  jmp     loc_18007E42A
0x18007e4da  mov     [r15], rbx
0x18007e4dd  mov     rsi, cs:WPP_GLOBAL_Control
0x18007e4e4  lea     rax, WPP_GLOBAL_Control
0x18007e4eb  cmp     rsi, rax
0x18007e4ee  jz      short loc_18007E531
0x18007e4f0  cmp     byte ptr [rsi+19h], 4
0x18007e4f4  jb      short loc_18007E531
0x18007e4f6  test    byte ptr [rsi+1Ch], 10h
0x18007e4fa  jz      short loc_18007E531
0x18007e4fc  mov     rdi, [r15]
0x18007e4ff  mov     rsi, [rsi+10h]
0x18007e503  call    IkeGetTlsPeerAddr
0x18007e508  mov     rbx, rax
0x18007e50b  call    IkeGetTlsMmLuid
0x18007e510  mov     r9, rax
0x18007e513  mov     [rsp+0D0h+var_A8], rdi
0x18007e518  mov     edx, 30h ; '0'
0x18007e51d  mov     [rsp+0D0h+var_B0], rbx
0x18007e522  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007e529  mov     rcx, rsi
0x18007e52c  call    WPP_SF_iSS
0x18007e531  mov     eax, cs:dword_180173278
0x18007e537  cmp     eax, 4
0x18007e53a  jbe     short loc_18007E5A4
0x18007e53c  call    IkeGetTlsMmLuid
0x18007e541  mov     [rbp+57h+TokenHandle], rax
0x18007e545  lea     rax, [rbp+57h+TokenHandle]
0x18007e549  mov     [rbp+57h+var_60], rax
0x18007e54d  mov     [rbp+57h+var_58], 8
0x18007e555  call    IkeGetTlsPeerAddr
0x18007e55a  mov     rdx, rax
0x18007e55d  lea     rcx, [rbp+57h+var_50]
0x18007e561  call    _tlgCreate1Sz_wchar_t
0x18007e566  mov     rdx, [r15]
0x18007e569  lea     rcx, [rbp+57h+var_40]
0x18007e56d  call    _tlgCreate1Sz_wchar_t
0x18007e572  lea     rcx, [rbp+57h+var_80]
0x18007e576  mov     [rsp+0D0h+var_A8], rcx
0x18007e57b  lea     rdx, qword_1801554C0
0x18007e582  lea     rcx, dword_180173278
0x18007e589  mov     dword ptr [rsp+0D0h+var_B0], 5
0x18007e591  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007e596  test    r14, r14
0x18007e599  jz      short loc_18007E5A4
0x18007e59b  lea     rcx, [rbp+57h+var_98]
0x18007e59f  call    WfpMemFree
0x18007e5a4  xor     edx, edx
0x18007e5a6  lea     rcx, aIkegetmyspnaut; "IkeGetMySPNAuthIp"
0x18007e5ad  call    TraceLogHelper
0x18007e5b2  lea     rdx, aIkegetmyspnaut; "IkeGetMySPNAuthIp"
0x18007e5b9  mov     rcx, r14
0x18007e5bc  call    IkeReturnError
0x18007e5c1  mov     rcx, [rbp+57h+var_30]
0x18007e5c5  xor     rcx, rsp; StackCookie
0x18007e5c8  call    __security_check_cookie
0x18007e5cd  mov     rbx, [rsp+0D0h+arg_10]
0x18007e5d5  add     rsp, 0B0h
0x18007e5dc  pop     r15
0x18007e5de  pop     r14
0x18007e5e0  pop     rdi
0x18007e5e1  pop     rsi
0x18007e5e2  pop     rbp
0x18007e5e3  retn
```
