# DnsApiInit

- ea: `0x18007932c`
- end: `0x18007953d`
- name: `DnsApiInit`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008fff4`

## callees

- `0x1800096d0`
- `0x180063a40`
- `0x180064e58`
- `0x1800662b0`
- `0x18007932c`
- `0x1800dc9e0`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007935d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007935d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800794cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007952d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800794cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007952d`
- `IPHLPAPI!GetDefaultCompartmentId` at `0x180079498`
- `IPHLPAPI!GetDefaultCompartmentId` at `0x180079498`

## pseudocode

```c
__int64 DnsApiInit()
{
  struct _RTL_CRITICAL_SECTION *v0; // rcx
  int v1; // eax
  unsigned int v2; // eax
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  struct _RTL_CRITICAL_SECTION *v5; // rcx

  if ( g_InitLevel == -1 )
    return 1;
  v0 = &g_csInit;
  if ( !g_fVelocityLockGeneralCleanup )
    v0 = &g_csGeneralDnsapi;
  EnterCriticalSection(v0);
  v1 = g_InitLevel;
  if ( (g_InitLevel & 0x100000) == 0 )
  {
    qword_180112B80 = 0;
    qword_180112B68 = (__int64)&g_DnsPolicyTable;
    v1 = g_InitLevel | 0x100000;
    g_DnsPolicyTable = (__int64)&g_DnsPolicyTable;
    xmmword_180112B70 = 0;
    g_InitLevel |= 0x100000u;
    dword_180111FF4 = -1;
    dword_180111FF8 = 0;
    qword_180112528 = 0;
    qword_180112520 = 0;
    dword_18011251C = 0;
    byte_180111F7A = 1;
    byte_180111F7B = 0;
    g_DAConfigured = 0;
    byte_180111F78 = 0;
    byte_180111F79 = 0;
    hLibModule = 0;
    dword_180112538 = -1;
    byte_180111F7D = 0;
    byte_180111F7E = 0;
  }
  if ( (v1 & 0x100) == 0 )
  {
    if ( !g_fVelocityLockGeneralCleanup )
    {
      g_NetFailureTime = 0;
      g_NetFailureStatus = 0;
    }
    Coalesce_Initialize();
    v1 = g_InitLevel | 0x100;
    g_InitLevel |= 0x100u;
    if ( (xmmword_1801119E0 & 4) != 0 )
    {
      WPP_SF_(1026, 10, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids);
      v1 = g_InitLevel;
    }
  }
  if ( !g_fVelocityDisableInternalExports && (v1 & 0x10000) == 0 )
  {
    Dns_StartSecurity(1);
    g_InitLevel |= 0x10000u;
    if ( (xmmword_1801119E0 & 4) != 0 )
      WPP_SF_(1026, 11, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids);
  }
  g_DefaultCompartmentId = GetDefaultCompartmentId();
  if ( !g_fVelocityDisableInternalExports )
    GetXboxProductType();
  v2 = OpenRegistryPaths();
  if ( !v2 )
  {
    if ( g_fVelocityLockGeneralCleanup )
      v3 = &g_csInit;
    else
      v3 = &g_csGeneralDnsapi;
    LeaveCriticalSection(v3);
    return 1;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 12, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids, v2);
  v5 = &g_csInit;
  if ( !g_fVelocityLockGeneralCleanup )
    v5 = &g_csGeneralDnsapi;
  LeaveCriticalSection(v5);
  return 0;
}

```

## disassembly

```asm
0x18007932c  mov     [rsp+arg_0], rbx
0x180079331  push    rdi
0x180079332  sub     rsp, 20h
0x180079336  or      edi, 0FFFFFFFFh
0x180079339  cmp     cs:g_InitLevel, edi
0x18007933f  jz      loc_1800794DB
0x180079345  xor     ebx, ebx
0x180079347  lea     rcx, g_csInit
0x18007934e  cmp     cs:g_fVelocityLockGeneralCleanup, ebx
0x180079354  jnz     short loc_18007935D
0x180079356  lea     rcx, g_csGeneralDnsapi; lpCriticalSection
0x18007935d  call    cs:__imp_EnterCriticalSection
0x180079364  nop     dword ptr [rax+rax+00h]
0x180079369  mov     eax, cs:g_InitLevel
0x18007936f  mov     edx, 100000h
0x180079374  test    edx, eax
0x180079376  jnz     loc_180079403
0x18007937c  lea     rcx, g_DnsPolicyTable
0x180079383  mov     cs:qword_180112B80, rbx
0x18007938a  xorps   xmm0, xmm0
0x18007938d  mov     cs:qword_180112B68, rcx
0x180079394  or      eax, edx
0x180079396  mov     cs:g_DnsPolicyTable, rcx
0x18007939d  movdqu  cs:xmmword_180112B70, xmm0
0x1800793a5  mov     cs:g_InitLevel, eax
0x1800793ab  mov     cs:dword_180111FF4, edi
0x1800793b1  mov     cs:dword_180111FF8, ebx
0x1800793b7  mov     cs:qword_180112528, rbx
0x1800793be  mov     cs:qword_180112520, rbx
0x1800793c5  mov     cs:dword_18011251C, ebx
0x1800793cb  mov     cs:byte_180111F7A, 1
0x1800793d2  mov     cs:byte_180111F7B, bl
0x1800793d8  mov     cs:g_DAConfigured, bl
0x1800793de  mov     cs:byte_180111F78, bl
0x1800793e4  mov     cs:byte_180111F79, bl
0x1800793ea  mov     cs:hLibModule, rbx
0x1800793f1  mov     cs:dword_180112538, edi
0x1800793f7  mov     cs:byte_180111F7D, bl
0x1800793fd  mov     cs:byte_180111F7E, bl
0x180079403  mov     edi, 100h
0x180079408  test    edi, eax
0x18007940a  jnz     short loc_180079458
0x18007940c  cmp     cs:g_fVelocityLockGeneralCleanup, ebx
0x180079412  jnz     short loc_180079420
0x180079414  mov     cs:g_NetFailureTime, ebx
0x18007941a  mov     cs:g_NetFailureStatus, ebx
0x180079420  call    Coalesce_Initialize
0x180079425  mov     eax, cs:g_InitLevel
0x18007942b  or      eax, edi
0x18007942d  mov     cs:g_InitLevel, eax
0x180079433  test    byte ptr cs:xmmword_1801119E0, 4
0x18007943a  jz      short loc_180079458
0x18007943c  mov     edx, 0Ah
0x180079441  lea     r8, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids
0x180079448  mov     ecx, 402h
0x18007944d  call    WPP_SF_
0x180079452  mov     eax, cs:g_InitLevel
0x180079458  cmp     cs:g_fVelocityDisableInternalExports, ebx
0x18007945e  jnz     short loc_180079498
0x180079460  mov     edi, 10000h
0x180079465  test    edi, eax
0x180079467  jnz     short loc_180079498
0x180079469  mov     ecx, 1
0x18007946e  call    Dns_StartSecurity
0x180079473  or      cs:g_InitLevel, edi
0x180079479  test    byte ptr cs:xmmword_1801119E0, 4
0x180079480  jz      short loc_180079498
0x180079482  mov     edx, 0Bh
0x180079487  lea     r8, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids
0x18007948e  mov     ecx, 402h
0x180079493  call    WPP_SF_
0x180079498  call    cs:__imp_GetDefaultCompartmentId
0x18007949f  nop     dword ptr [rax+rax+00h]
0x1800794a4  cmp     cs:g_fVelocityDisableInternalExports, ebx
0x1800794aa  mov     cs:g_DefaultCompartmentId, eax
0x1800794b0  jnz     short loc_1800794B7
0x1800794b2  call    GetXboxProductType
0x1800794b7  call    OpenRegistryPaths
0x1800794bc  test    eax, eax
0x1800794be  jnz     short loc_1800794F5
0x1800794c0  cmp     cs:g_fVelocityLockGeneralCleanup, ebx
0x1800794c6  jz      short loc_1800794EC
0x1800794c8  lea     rcx, g_csInit; lpCriticalSection
0x1800794cf  call    cs:__imp_LeaveCriticalSection
0x1800794d6  nop     dword ptr [rax+rax+00h]
0x1800794db  mov     eax, 1
0x1800794e0  mov     rbx, [rsp+28h+arg_0]
0x1800794e5  add     rsp, 20h
0x1800794e9  pop     rdi
0x1800794ea  retn
0x1800794ec  lea     rcx, g_csGeneralDnsapi
0x1800794f3  jmp     short loc_1800794CF
0x1800794f5  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800794fc  jz      short loc_180079517
0x1800794fe  mov     edx, 0Ch
0x180079503  lea     r8, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids
0x18007950a  mov     ecx, 40Bh
0x18007950f  mov     r9d, eax
0x180079512  call    WPP_SF_d
0x180079517  cmp     cs:g_fVelocityLockGeneralCleanup, ebx
0x18007951d  lea     rcx, g_csInit
0x180079524  jnz     short loc_18007952D
0x180079526  lea     rcx, g_csGeneralDnsapi; lpCriticalSection
0x18007952d  call    cs:__imp_LeaveCriticalSection
0x180079534  nop     dword ptr [rax+rax+00h]
0x180079539  xor     eax, eax
0x18007953b  jmp     short loc_1800794E0
```
