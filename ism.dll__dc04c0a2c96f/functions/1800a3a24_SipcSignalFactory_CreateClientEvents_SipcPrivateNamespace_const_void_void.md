# SipcSignalFactory::CreateClientEvents(SipcPrivateNamespace const &,void * *,void * *)

- ea: `0x1800a3a24`
- end: `0x1800a3c07`
- name: `?CreateClientEvents@SipcSignalFactory@@SAJAEBVSipcPrivateNamespace@@PEAPEAX1@Z`
- size: `483`
- prototype: `__int64 __fastcall(const struct SipcPrivateNamespace *, void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801433e0`

## callees

- `0x1800a3a24`
- `0x1800a4198`
- `0x1800f0990`
- `0x1800f0e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3b87`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a3b06`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a3b77`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a3b06`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a3b77`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a3a78`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a3a78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3aa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3be5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3aa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3be5`

## pseudocode

```c
__int64 __fastcall SipcSignalFactory::CreateClientEvents(const struct SipcPrivateNamespace *a1, void **a2, void **a3)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  void *v9; // rbx
  signed int v10; // eax
  HANDLE v11; // rax
  signed int v12; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v14; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v15; // [rsp+40h] [rbp-C0h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Buffer[56]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Name[56]; // [rsp+D0h] [rbp-30h] BYREF

  *a2 = 0;
  *a3 = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;WD)", 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = -2147418113;
    if ( LastError < 0 )
      v7 = LastError;
    goto LABEL_6;
  }
  EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  swprintf_s(Buffer, 0x33u, L"%s\\%s", (char *)a1 + 8, L"ClientSignal");
  v14 = CreateEventW(&EventAttributes, 0, 0, Buffer);
  v9 = v14;
  if ( !v14 )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v7 = -2147418113;
    if ( v10 < 0 )
      v7 = v10;
LABEL_14:
    SipcWin32Handle::Reset((SipcWin32Handle *)&v14);
LABEL_6:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return v7;
  }
  swprintf_s(Name, 0x33u, L"%s\\%s", (char *)a1 + 8, L"ServerSignal");
  v11 = CreateEventW(&EventAttributes, 0, 0, Name);
  v15 = v11;
  if ( !v11 )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v7 = -2147418113;
    if ( v12 < 0 )
      v7 = v12;
    SipcWin32Handle::Reset((SipcWin32Handle *)&v15);
    goto LABEL_14;
  }
  *a2 = v9;
  *a3 = v11;
  v14 = 0;
  v15 = 0;
  SipcWin32Handle::Reset((SipcWin32Handle *)&v15);
  SipcWin32Handle::Reset((SipcWin32Handle *)&v14);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x1800a3a24  push    rbp
0x1800a3a26  push    rbx
0x1800a3a27  push    rsi
0x1800a3a28  push    rdi
0x1800a3a29  push    r14
0x1800a3a2b  lea     rbp, [rsp-50h]
0x1800a3a30  sub     rsp, 150h
0x1800a3a37  mov     rax, cs:__security_cookie
0x1800a3a3e  xor     rax, rsp
0x1800a3a41  mov     [rbp+70h+var_30], rax
0x1800a3a45  mov     qword ptr [rdx], 0
0x1800a3a4c  xor     r9d, r9d; SecurityDescriptorSize
0x1800a3a4f  mov     rsi, r8
0x1800a3a52  mov     qword ptr [r8], 0
0x1800a3a59  mov     rdi, rdx
0x1800a3a5c  mov     [rsp+170h+SecurityDescriptor], 0
0x1800a3a65  mov     r14, rcx
0x1800a3a68  lea     r8, [rsp+170h+SecurityDescriptor]; SecurityDescriptor
0x1800a3a6d  lea     edx, [r9+1]; StringSDRevision
0x1800a3a71  lea     rcx, aDAGaWd; "D:(A;;GA;;;WD)"
0x1800a3a78  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800a3a7e  test    eax, eax
0x1800a3a80  jnz     short loc_1800A3AB5
0x1800a3a82  call    cs:__imp_GetLastError
0x1800a3a88  test    eax, eax
0x1800a3a8a  jle     short loc_1800A3A94
0x1800a3a8c  movzx   eax, ax
0x1800a3a8f  or      eax, 80070000h
0x1800a3a94  test    eax, eax
0x1800a3a96  mov     ebx, 8000FFFFh
0x1800a3a9b  cmovs   ebx, eax
0x1800a3a9e  mov     rcx, [rsp+170h+SecurityDescriptor]; hMem
0x1800a3aa3  test    rcx, rcx
0x1800a3aa6  jz      short loc_1800A3AAE
0x1800a3aa8  call    cs:__imp_LocalFree
0x1800a3aae  mov     eax, ebx
0x1800a3ab0  jmp     loc_1800A3BED
0x1800a3ab5  mov     rax, [rsp+170h+SecurityDescriptor]
0x1800a3aba  lea     r9, [r14+8]
0x1800a3abe  mov     [rsp+170h+EventAttributes.lpSecurityDescriptor], rax
0x1800a3ac3  lea     r8, aSS; "%s\\%s"
0x1800a3aca  lea     rax, ?ClientSignalName@SipcSignalFactory@@0QBGB; "ClientSignal"
0x1800a3ad1  mov     qword ptr [rsp+170h+EventAttributes.nLength], 18h
0x1800a3ada  mov     edx, 33h ; '3'; BufferCount
0x1800a3adf  mov     [rsp+170h+var_150], rax
0x1800a3ae4  lea     rcx, [rsp+170h+Buffer]; Buffer
0x1800a3ae9  mov     qword ptr [rsp+170h+EventAttributes.bInheritHandle], 0
0x1800a3af2  call    swprintf_s
0x1800a3af7  lea     r9, [rsp+170h+Buffer]; lpName
0x1800a3afc  xor     r8d, r8d; bInitialState
0x1800a3aff  xor     edx, edx; bManualReset
0x1800a3b01  lea     rcx, [rsp+170h+EventAttributes]; lpEventAttributes
0x1800a3b06  call    cs:__imp_CreateEventW
0x1800a3b0c  mov     [rsp+170h+var_138], rax
0x1800a3b11  mov     rbx, rax
0x1800a3b14  test    rax, rax
0x1800a3b17  jnz     short loc_1800A3B44
0x1800a3b19  call    cs:__imp_GetLastError
0x1800a3b1f  test    eax, eax
0x1800a3b21  jle     short loc_1800A3B2B
0x1800a3b23  movzx   eax, ax
0x1800a3b26  or      eax, 80070000h
0x1800a3b2b  test    eax, eax
0x1800a3b2d  mov     ebx, 8000FFFFh
0x1800a3b32  cmovs   ebx, eax
0x1800a3b35  lea     rcx, [rsp+170h+var_138]; this
0x1800a3b3a  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a3b3f  jmp     loc_1800A3A9E
0x1800a3b44  lea     rax, ?ServerSignalName@SipcSignalFactory@@0QBGB; "ServerSignal"
0x1800a3b4b  mov     edx, 33h ; '3'; BufferCount
0x1800a3b50  lea     r9, [r14+8]
0x1800a3b54  mov     [rsp+170h+var_150], rax
0x1800a3b59  lea     r8, aSS; "%s\\%s"
0x1800a3b60  lea     rcx, [rbp+70h+Name]; Buffer
0x1800a3b64  call    swprintf_s
0x1800a3b69  lea     r9, [rbp+70h+Name]; lpName
0x1800a3b6d  xor     r8d, r8d; bInitialState
0x1800a3b70  xor     edx, edx; bManualReset
0x1800a3b72  lea     rcx, [rsp+170h+EventAttributes]; lpEventAttributes
0x1800a3b77  call    cs:__imp_CreateEventW
0x1800a3b7d  mov     [rsp+170h+var_130], rax
0x1800a3b82  test    rax, rax
0x1800a3b85  jnz     short loc_1800A3BAF
0x1800a3b87  call    cs:__imp_GetLastError
0x1800a3b8d  test    eax, eax
0x1800a3b8f  jle     short loc_1800A3B99
0x1800a3b91  movzx   eax, ax
0x1800a3b94  or      eax, 80070000h
0x1800a3b99  test    eax, eax
0x1800a3b9b  lea     rcx, [rsp+170h+var_130]; this
0x1800a3ba0  mov     ebx, 8000FFFFh
0x1800a3ba5  cmovs   ebx, eax
0x1800a3ba8  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a3bad  jmp     short loc_1800A3B35
0x1800a3baf  mov     [rdi], rbx
0x1800a3bb2  lea     rcx, [rsp+170h+var_130]; this
0x1800a3bb7  mov     [rsi], rax
0x1800a3bba  mov     [rsp+170h+var_138], 0
0x1800a3bc3  mov     [rsp+170h+var_130], 0
0x1800a3bcc  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a3bd1  lea     rcx, [rsp+170h+var_138]; this
0x1800a3bd6  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a3bdb  mov     rcx, [rsp+170h+SecurityDescriptor]; hMem
0x1800a3be0  test    rcx, rcx
0x1800a3be3  jz      short loc_1800A3BEB
0x1800a3be5  call    cs:__imp_LocalFree
0x1800a3beb  xor     eax, eax
0x1800a3bed  mov     rcx, [rbp+70h+var_30]
0x1800a3bf1  xor     rcx, rsp; StackCookie
0x1800a3bf4  call    __security_check_cookie
0x1800a3bf9  add     rsp, 150h
0x1800a3c00  pop     r14
0x1800a3c02  pop     rdi
0x1800a3c03  pop     rsi
0x1800a3c04  pop     rbx
0x1800a3c05  pop     rbp
0x1800a3c06  retn
```
