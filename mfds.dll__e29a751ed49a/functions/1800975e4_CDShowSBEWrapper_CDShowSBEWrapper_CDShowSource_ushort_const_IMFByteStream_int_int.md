# CDShowSBEWrapper::CDShowSBEWrapper(CDShowSource *,ushort const *,IMFByteStream *,int,int)

- ea: `0x1800975e4`
- end: `0x180097891`
- name: `??0CDShowSBEWrapper@@QEAA@PEAVCDShowSource@@PEBGPEAUIMFByteStream@@HH@Z`
- size: `685`
- prototype: `CDShowSBEWrapper *(CDShowSBEWrapper *__hidden this, struct CDShowSource *, const unsigned __int16 *, struct IMFByteStream *, int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034274`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800359b0`
- `0x180051bd8`
- `0x180074160`
- `0x180074a06`
- `0x180092898`
- `0x1800975e4`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800976e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097731`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800976e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097731`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009777b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009777b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800976f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009784f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800976f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009784f`
- `MFPlat!MFCreateStreamOnMFByteStream` at `0x180097866`
- `MFPlat!MFCreateStreamOnMFByteStream` at `0x180097866`

## pseudocode

```c
CDShowSBEWrapper *__fastcall CDShowSBEWrapper::CDShowSBEWrapper(
        CDShowSBEWrapper *this,
        struct CDShowSource *a2,
        const unsigned __int16 *a3,
        struct IMFByteStream *a4,
        int a5,
        int a6)
{
  int v8; // eax
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v10; // ebx
  __int128 v11; // xmm0
  BYTE v13[4]; // [rsp+30h] [rbp-40h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-3Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v18[16]; // [rsp+50h] [rbp-20h] BYREF

  CDShowWrapper::CDShowWrapper(this, a2, a3, a4, a5);
  *(_QWORD *)this = &CDShowSBEWrapper::`vftable'{for `CDShowWrapper'};
  *((_QWORD *)this + 62) = &CDShowSBEWrapper::`vftable'{for `IBroadcastEventEx'};
  *((_DWORD *)this + 128) = a6;
  *((_QWORD *)this + 63) = 1;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_WORD *)this + 280) = 0;
  *((_BYTE *)this + 562) = 0;
  memset_0((char *)this + 568, 0, 0xA0u);
  *((_DWORD *)this + 137) |= 1u;
  *((_QWORD *)this + 67) = &CTPtrArray<SampleSinkEntry,20>::`vftable';
  *((_QWORD *)this + 91) = 0;
  *((_DWORD *)this + 184) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 93) = 0;
  CMFSRWLock::CMFSRWLock((CDShowSBEWrapper *)((char *)this + 752));
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows Media Foundation\\ContentProtectionSystems",
         0,
         0x20019u,
         &hKey) )
  {
    v8 = 0;
  }
  else
  {
    RegCloseKey(hKey);
    v8 = 1;
  }
  *((_DWORD *)this + 133) = v8;
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Debug\\MF SBE Source", 0, 0x20019u, &phkResult) )
  {
    LODWORD(hKey) = 4;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(phkResult, L"EnableCP", 0, (LPDWORD)&hKey, Data, &cbData) && *(_DWORD *)Data )
    {
      *((_DWORD *)this + 132) = 1;
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v13, "CDShowSBEWrapper::CDShowSBEWrapper", 52);
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
        v11 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 60) + 280LL))(
                           *((_QWORD *)this + 60),
                           v18);
        *((_DWORD *)ThreadRelativeContext + 504) = v10;
        *((_OWORD *)ThreadRelativeContext + 125) = v11;
      }
      if ( (unsigned __int8)byte_1800EACCB >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 10, WPP_37ff27b5f7033090a0d8eec054f7c30c_Traceguids);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v13);
    }
    RegCloseKey(phkResult);
  }
  if ( a4 )
    MFCreateStreamOnMFByteStream(a4, (IStream **)this + 93);
  return this;
}

```

## disassembly

```asm
0x1800975e4  push    rbp
0x1800975e6  push    rbx
0x1800975e7  push    rsi
0x1800975e8  push    rdi
0x1800975e9  push    r12
0x1800975eb  push    r14
0x1800975ed  push    r15
0x1800975ef  mov     rbp, rsp
0x1800975f2  sub     rsp, 70h
0x1800975f6  mov     rax, cs:__security_cookie
0x1800975fd  xor     rax, rsp
0x180097600  mov     [rbp+var_10], rax
0x180097604  mov     eax, [rbp+arg_20]
0x180097607  mov     r14, r9
0x18009760a  mov     dword ptr [rsp+70h+phkResult], eax; int
0x18009760e  mov     rsi, rcx
0x180097611  call    ??0CDShowWrapper@@QEAA@PEAVCDShowSource@@PEBGPEAUIMFByteStream@@H@Z; CDShowWrapper::CDShowWrapper(CDShowSource *,ushort const *,IMFByteStream *,int)
0x180097616  xor     r12d, r12d
0x180097619  lea     rax, ??_7CDShowSBEWrapper@@6BCDShowWrapper@@@; const CDShowSBEWrapper::`vftable'{for `CDShowWrapper'}
0x180097620  mov     [rsi], rax
0x180097623  lea     rcx, [rsi+238h]; void *
0x18009762a  lea     rax, ??_7CDShowSBEWrapper@@6BIBroadcastEventEx@@@; const CDShowSBEWrapper::`vftable'{for `IBroadcastEventEx'}
0x180097631  mov     ebx, 1
0x180097636  mov     [rsi+1F0h], rax
0x18009763d  xor     edx, edx; Val
0x18009763f  mov     eax, [rbp+arg_28]
0x180097642  mov     r8d, 0A0h; Size
0x180097648  mov     [rsi+200h], eax
0x18009764e  xor     eax, eax
0x180097650  mov     [rsi+1F8h], rbx
0x180097657  mov     [rsi+208h], r12
0x18009765e  mov     [rsi+210h], r12
0x180097665  mov     [rsi+220h], r12
0x18009766c  mov     [rsi+230h], ax
0x180097673  mov     [rsi+232h], al
0x180097679  call    memset_0
0x18009767e  or      [rsi+224h], ebx
0x180097684  lea     rax, ??_7?$CTPtrArray@USampleSinkEntry@@$0BE@@@6B@; const CTPtrArray<SampleSinkEntry,20>::`vftable'
0x18009768b  mov     [rsi+218h], rax
0x180097692  lea     r15, [rsi+2E8h]
0x180097699  mov     [rsi+2D8h], r12
0x1800976a0  lea     rcx, [rsi+2F0h]; this
0x1800976a7  mov     [rsi+2E0h], r12d
0x1800976ae  mov     [rsi+228h], r12
0x1800976b5  mov     [r15], r12
0x1800976b8  call    ??0CMFSRWLock@@QEAA@XZ; CMFSRWLock::CMFSRWLock(void)
0x1800976bd  lea     rax, [rbp+hKey]
0x1800976c1  mov     [rbp+hKey], r12
0x1800976c5  mov     edi, 20019h
0x1800976ca  mov     [rsp+70h+phkResult], rax; phkResult
0x1800976cf  mov     r9d, edi; samDesired
0x1800976d2  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x1800976d9  xor     r8d, r8d; ulOptions
0x1800976dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800976e3  call    cs:__imp_RegOpenKeyExW
0x1800976ea  nop     dword ptr [rax+rax+00h]
0x1800976ef  test    eax, eax
0x1800976f1  jnz     short loc_180097707
0x1800976f3  mov     rcx, [rbp+hKey]; hKey
0x1800976f7  call    cs:__imp_RegCloseKey
0x1800976fe  nop     dword ptr [rax+rax+00h]
0x180097703  mov     eax, ebx
0x180097705  jmp     short loc_18009770A
0x180097707  mov     eax, r12d
0x18009770a  mov     [rsi+214h], eax
0x180097710  lea     rdx, aSoftwareDebugM; "Software\\Debug\\MF SBE Source"
0x180097717  lea     rax, [rbp+var_28]
0x18009771b  mov     [rbp+var_28], r12
0x18009771f  mov     r9d, edi; samDesired
0x180097722  mov     [rsp+70h+phkResult], rax; phkResult
0x180097727  xor     r8d, r8d; ulOptions
0x18009772a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180097731  call    cs:__imp_RegOpenKeyExW
0x180097738  nop     dword ptr [rax+rax+00h]
0x18009773d  test    eax, eax
0x18009773f  jnz     loc_18009785B
0x180097745  mov     rcx, [rbp+var_28]; hKey
0x180097749  lea     rax, [rbp+cbData]
0x18009774d  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180097752  lea     r9, [rbp+hKey]; lpType
0x180097756  lea     rax, [rbp+Data]
0x18009775a  mov     dword ptr [rbp+hKey], 4
0x180097761  xor     r8d, r8d; lpReserved
0x180097764  mov     [rsp+70h+phkResult], rax; lpData
0x180097769  lea     rdx, aEnablecp; "EnableCP"
0x180097770  mov     dword ptr [rbp+Data], r12d
0x180097774  mov     [rbp+cbData], 4
0x18009777b  call    cs:__imp_RegQueryValueExW
0x180097782  nop     dword ptr [rax+rax+00h]
0x180097787  test    eax, eax
0x180097789  jnz     loc_18009784B
0x18009778f  cmp     dword ptr [rbp+Data], r12d
0x180097793  jz      loc_18009784B
0x180097799  lea     r8d, [rax+34h]; int
0x18009779d  mov     [rsi+210h], ebx
0x1800977a3  lea     rdx, aCdshowsbewrapp_9; "CDShowSBEWrapper::CDShowSBEWrapper"
0x1800977aa  lea     rcx, [rbp+var_40]; this
0x1800977ae  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800977b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800977ba  cmp     [rcx+8], r12b
0x1800977be  jz      short loc_18009781A
0x1800977c0  cmp     [rsi+1E0h], r12
0x1800977c7  jz      short loc_18009781A
0x1800977c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800977ce  mov     rdx, [rsi+1E0h]
0x1800977d5  mov     rdi, rax
0x1800977d8  mov     rcx, [rdx]
0x1800977db  mov     rax, [rcx+128h]
0x1800977e2  mov     rcx, rdx
0x1800977e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800977ea  mov     r8, [rsi+1E0h]
0x1800977f1  lea     rdx, [rbp+var_20]
0x1800977f5  mov     ebx, eax
0x1800977f7  mov     rcx, [r8]
0x1800977fa  mov     rax, [rcx+118h]
0x180097801  mov     rcx, r8
0x180097804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097809  movups  xmm0, xmmword ptr [rax]
0x18009780c  mov     [rdi+7E0h], ebx
0x180097812  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18009781a  cmp     cs:byte_1800EACCB, 4
0x180097821  jb      short loc_180097842
0x180097823  mov     rcx, cs:WPP_GLOBAL_Control
0x18009782a  lea     r8, WPP_37ff27b5f7033090a0d8eec054f7c30c_Traceguids
0x180097831  mov     edx, 0Ah
0x180097836  mov     rcx, [rcx+88h]
0x18009783d  call    WPP_SF_
0x180097842  lea     rcx, [rbp+var_40]; this
0x180097846  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009784b  mov     rcx, [rbp+var_28]; hKey
0x18009784f  call    cs:__imp_RegCloseKey
0x180097856  nop     dword ptr [rax+rax+00h]
0x18009785b  test    r14, r14
0x18009785e  jz      short loc_180097872
0x180097860  mov     rdx, r15; ppStream
0x180097863  mov     rcx, r14; pByteStream
0x180097866  call    cs:__imp_MFCreateStreamOnMFByteStream
0x18009786d  nop     dword ptr [rax+rax+00h]
0x180097872  mov     rax, rsi
0x180097875  mov     rcx, [rbp+var_10]
0x180097879  xor     rcx, rsp; StackCookie
0x18009787c  call    __security_check_cookie
0x180097881  add     rsp, 70h
0x180097885  pop     r15
0x180097887  pop     r14
0x180097889  pop     r12
0x18009788b  pop     rdi
0x18009788c  pop     rsi
0x18009788d  pop     rbx
0x18009788e  pop     rbp
0x18009788f  retn
```
