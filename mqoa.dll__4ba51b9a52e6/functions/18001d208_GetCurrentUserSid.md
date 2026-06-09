# GetCurrentUserSid

- ea: `0x18001d208`
- end: `0x18001d3a3`
- name: `GetCurrentUserSid`
- size: `411`
- prototype: `__int64 __fastcall(PSID pDestinationSid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18001d774`

## callees

- `0x180013568`
- `0x1800138e0`
- `0x1800149b0`
- `0x1800149e0`
- `0x18001ca94`
- `0x18001d208`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d27d`
- `KERNEL32!GetLastError` at `0x18001d2f6`
- `KERNEL32!GetLastError` at `0x18001d27d`
- `KERNEL32!GetLastError` at `0x18001d2f6`
- `KERNEL32!GetCurrentThread` at `0x18001d258`
- `KERNEL32!GetCurrentThread` at `0x18001d258`
- `KERNEL32!GetCurrentProcess` at `0x18001d28a`
- `KERNEL32!GetCurrentProcess` at `0x18001d28a`
- `ADVAPI32!GetLengthSid` at `0x18001d35a`
- `ADVAPI32!GetLengthSid` at `0x18001d35a`
- `ADVAPI32!CopySid` at `0x18001d368`
- `ADVAPI32!CopySid` at `0x18001d368`
- `ADVAPI32!GetTokenInformation` at `0x18001d2ec`
- `ADVAPI32!GetTokenInformation` at `0x18001d340`
- `ADVAPI32!GetTokenInformation` at `0x18001d2ec`
- `ADVAPI32!GetTokenInformation` at `0x18001d340`
- `ADVAPI32!OpenProcessToken` at `0x18001d29a`
- `ADVAPI32!OpenProcessToken` at `0x18001d29a`
- `ADVAPI32!OpenThreadToken` at `0x18001d273`
- `ADVAPI32!OpenThreadToken` at `0x18001d273`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetCurrentUserSid(PSID pDestinationSid)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // edi
  HANDLE CurrentProcess; // rax
  DWORD BufferMaxSize; // ebx
  void *Buffer; // rax
  DWORD v8; // ebx
  void *v9; // rax
  void *v10; // rbx
  DWORD LengthSid; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v15[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+64h] [rbp-9Ch]

  v15[1] = 0;
  v16 = 0;
  v15[0] = &CStaticBufferGrowing<unsigned char,128>::`vftable';
  ReturnLength = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v3 = 1;
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
    || GetLastError() == 1008
    && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)) )
  {
    v14[0] = TokenHandle;
    BufferMaxSize = CBaseStaticBufferGrowing<unsigned char>::GetBufferMaxSize(v15);
    Buffer = (void *)CBaseStaticBufferGrowing<wchar_t>::GetBuffer((__int64)v15);
    if ( !GetTokenInformation(TokenHandle, TokenUser, Buffer, BufferMaxSize, &ReturnLength)
      && (GetLastError() != 122
       || (int)CBaseStaticBufferGrowing<unsigned char>::AllocateBuffer((__int64)v15, ReturnLength) < 0
       || (v8 = CBaseStaticBufferGrowing<unsigned char>::GetBufferMaxSize(v15),
           v9 = (void *)CBaseStaticBufferGrowing<wchar_t>::GetBuffer((__int64)v15),
           !GetTokenInformation(TokenHandle, TokenUser, v9, v8, &ReturnLength)))
      || (v10 = *(void **)CBaseStaticBufferGrowing<wchar_t>::GetBuffer((__int64)v15),
          LengthSid = GetLengthSid(v10),
          !CopySid(LengthSid, pDestinationSid, v10)) )
    {
      v3 = 0;
    }
    CAutoCloseHandle::~CAutoCloseHandle((CAutoCloseHandle *)v14);
    CBaseStaticBufferGrowing<unsigned char>::~CBaseStaticBufferGrowing<unsigned char>(v15);
    return v3;
  }
  else
  {
    CBaseStaticBufferGrowing<unsigned char>::~CBaseStaticBufferGrowing<unsigned char>(v15);
    return 0;
  }
}

```

## disassembly

```asm
0x18001d208  push    rbp
0x18001d20a  push    rbx
0x18001d20b  push    rsi
0x18001d20c  push    rdi
0x18001d20d  lea     rbp, [rsp-8]
0x18001d212  sub     rsp, 108h
0x18001d219  mov     rax, cs:__security_cookie
0x18001d220  xor     rax, rsp
0x18001d223  mov     [rbp+20h+var_30], rax
0x18001d227  mov     rsi, rcx
0x18001d22a  mov     [rsp+120h+var_C8], 0
0x18001d233  mov     [rsp+120h+var_BC], 0
0x18001d23b  lea     rax, ??_7?$CStaticBufferGrowing@E$0IA@@@6B@; const CStaticBufferGrowing<uchar,128>::`vftable'
0x18001d242  mov     [rsp+120h+var_D0], rax
0x18001d247  mov     [rsp+120h+var_F0], 0
0x18001d24f  mov     [rsp+120h+TokenHandle], 0
0x18001d258  call    cs:__imp_GetCurrentThread
0x18001d25e  mov     rcx, rax; ThreadHandle
0x18001d261  lea     r9, [rsp+120h+TokenHandle]; TokenHandle
0x18001d266  mov     edi, 1
0x18001d26b  mov     r8d, edi; OpenAsSelf
0x18001d26e  lea     ebx, [rdi+7]
0x18001d271  mov     edx, ebx; DesiredAccess
0x18001d273  call    cs:__imp_OpenThreadToken
0x18001d279  test    eax, eax
0x18001d27b  jnz     short loc_18001D2B5
0x18001d27d  call    cs:__imp_GetLastError
0x18001d283  cmp     eax, 3F0h
0x18001d288  jnz     short loc_18001D2A4
0x18001d28a  call    cs:__imp_GetCurrentProcess
0x18001d290  mov     rcx, rax; ProcessHandle
0x18001d293  lea     r8, [rsp+120h+TokenHandle]; TokenHandle
0x18001d298  mov     edx, ebx; DesiredAccess
0x18001d29a  call    cs:__imp_OpenProcessToken
0x18001d2a0  test    eax, eax
0x18001d2a2  jnz     short loc_18001D2B5
0x18001d2a4  lea     rcx, [rsp+120h+var_D0]
0x18001d2a9  call    ??1?$CBaseStaticBufferGrowing@E@@UEAA@XZ; CBaseStaticBufferGrowing<uchar>::~CBaseStaticBufferGrowing<uchar>(void)
0x18001d2ae  xor     eax, eax
0x18001d2b0  jmp     loc_18001D38B
0x18001d2b5  mov     rax, [rsp+120h+TokenHandle]
0x18001d2ba  mov     [rsp+120h+var_E0], rax
0x18001d2bf  lea     rcx, [rsp+120h+var_D0]
0x18001d2c4  call    ?GetBufferMaxSize@?$CBaseStaticBufferGrowing@E@@UEAAKXZ; CBaseStaticBufferGrowing<uchar>::GetBufferMaxSize(void)
0x18001d2c9  mov     ebx, eax
0x18001d2cb  lea     rcx, [rsp+120h+var_D0]
0x18001d2d0  call    ?GetBuffer@?$CBaseStaticBufferGrowing@_W@@UEAAPEA_WXZ; CBaseStaticBufferGrowing<wchar_t>::GetBuffer(void)
0x18001d2d5  lea     rcx, [rsp+120h+var_F0]
0x18001d2da  mov     [rsp+120h+ReturnLength], rcx; ReturnLength
0x18001d2df  mov     r9d, ebx; TokenInformationLength
0x18001d2e2  mov     r8, rax; TokenInformation
0x18001d2e5  mov     edx, edi; TokenInformationClass
0x18001d2e7  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18001d2ec  call    cs:__imp_GetTokenInformation
0x18001d2f2  test    eax, eax
0x18001d2f4  jnz     short loc_18001D34A
0x18001d2f6  call    cs:__imp_GetLastError
0x18001d2fc  cmp     eax, 7Ah ; 'z'
0x18001d2ff  jnz     short loc_18001D372
0x18001d301  mov     edx, [rsp+120h+var_F0]
0x18001d305  lea     rcx, [rsp+120h+var_D0]
0x18001d30a  call    ?AllocateBuffer@?$CBaseStaticBufferGrowing@E@@UEAAJK@Z; CBaseStaticBufferGrowing<uchar>::AllocateBuffer(ulong)
0x18001d30f  test    eax, eax
0x18001d311  js      short loc_18001D372
0x18001d313  lea     rcx, [rsp+120h+var_D0]
0x18001d318  call    ?GetBufferMaxSize@?$CBaseStaticBufferGrowing@E@@UEAAKXZ; CBaseStaticBufferGrowing<uchar>::GetBufferMaxSize(void)
0x18001d31d  mov     ebx, eax
0x18001d31f  lea     rcx, [rsp+120h+var_D0]
0x18001d324  call    ?GetBuffer@?$CBaseStaticBufferGrowing@_W@@UEAAPEA_WXZ; CBaseStaticBufferGrowing<wchar_t>::GetBuffer(void)
0x18001d329  lea     rcx, [rsp+120h+var_F0]
0x18001d32e  mov     [rsp+120h+ReturnLength], rcx; ReturnLength
0x18001d333  mov     r9d, ebx; TokenInformationLength
0x18001d336  mov     r8, rax; TokenInformation
0x18001d339  mov     edx, edi; TokenInformationClass
0x18001d33b  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18001d340  call    cs:__imp_GetTokenInformation
0x18001d346  test    eax, eax
0x18001d348  jz      short loc_18001D372
0x18001d34a  lea     rcx, [rsp+120h+var_D0]
0x18001d34f  call    ?GetBuffer@?$CBaseStaticBufferGrowing@_W@@UEAAPEA_WXZ; CBaseStaticBufferGrowing<wchar_t>::GetBuffer(void)
0x18001d354  mov     rbx, [rax]
0x18001d357  mov     rcx, rbx; pSid
0x18001d35a  call    cs:__imp_GetLengthSid
0x18001d360  mov     ecx, eax; nDestinationSidLength
0x18001d362  mov     r8, rbx; pSourceSid
0x18001d365  mov     rdx, rsi; pDestinationSid
0x18001d368  call    cs:__imp_CopySid
0x18001d36e  test    eax, eax
0x18001d370  jnz     short loc_18001D374
0x18001d372  xor     edi, edi
0x18001d374  lea     rcx, [rsp+120h+var_E0]; this
0x18001d379  call    ??1CAutoCloseHandle@@QEAA@XZ; CAutoCloseHandle::~CAutoCloseHandle(void)
0x18001d37e  nop
0x18001d37f  lea     rcx, [rsp+120h+var_D0]
0x18001d384  call    ??1?$CBaseStaticBufferGrowing@E@@UEAA@XZ; CBaseStaticBufferGrowing<uchar>::~CBaseStaticBufferGrowing<uchar>(void)
0x18001d389  mov     eax, edi
0x18001d38b  mov     rcx, [rbp+20h+var_30]
0x18001d38f  xor     rcx, rsp; StackCookie
0x18001d392  call    __security_check_cookie
0x18001d397  add     rsp, 108h
0x18001d39e  pop     rdi
0x18001d39f  pop     rsi
0x18001d3a0  pop     rbx
0x18001d3a1  pop     rbp
0x18001d3a2  retn
```
