# MQSec_RemovePrivilegesFromProcessToken(wchar_t const * const *,ulong)

- ea: `0x180029370`
- end: `0x180029601`
- name: `?MQSec_RemovePrivilegesFromProcessToken@@YAJPEBQEB_WK@Z`
- size: `657`
- prototype: `__int64 __fastcall(const wchar_t *const *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x1800041cc`
- `0x1800049ac`
- `0x1800049ec`
- `0x18001353c`
- `0x180013940`
- `0x18001722c`
- `0x180029370`

## import_xrefs

- `msvcrt!free` at `0x18002947a`
- `msvcrt!free` at `0x18002951a`
- `msvcrt!free` at `0x180029572`
- `msvcrt!free` at `0x1800295e1`
- `msvcrt!free` at `0x18002947a`
- `msvcrt!free` at `0x18002951a`
- `msvcrt!free` at `0x180029572`
- `msvcrt!free` at `0x1800295e1`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180029545`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180029545`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1800293cd`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1800293cd`
- `ADVAPI32!OpenProcessToken` at `0x1800294a4`
- `ADVAPI32!OpenProcessToken` at `0x1800294a4`
- `KERNEL32!GetCurrentProcess` at `0x180029491`
- `KERNEL32!GetCurrentProcess` at `0x180029491`
- `KERNEL32!GetLastError` at `0x180029414`
- `KERNEL32!GetLastError` at `0x1800294ae`
- `KERNEL32!GetLastError` at `0x18002954d`
- `KERNEL32!GetLastError` at `0x180029414`
- `KERNEL32!GetLastError` at `0x1800294ae`
- `KERNEL32!GetLastError` at `0x18002954d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MQSec_RemovePrivilegesFromProcessToken(const wchar_t *const *a1, DWORD a2)
{
  struct _TOKEN_PRIVILEGES *v4; // rbx
  DWORD i; // edi
  DWORD LastError; // eax
  signed int v7; // edi
  bool v8; // sf
  HANDLE CurrentProcess; // rax
  DWORD v11; // eax
  bool v12; // sf
  BOOL v13; // edi
  DWORD v14; // eax
  signed int v15; // esi
  bool v16; // sf
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF
  struct _TOKEN_PRIVILEGES *v18; // [rsp+78h] [rbp+20h]

  v4 = (struct _TOKEN_PRIVILEGES *)MmAllocate(12 * a2 + 16);
  v18 = v4;
  v4->PrivilegeCount = a2;
  for ( i = 0; i < a2; ++i )
  {
    if ( !LookupPrivilegeValueW(0, a1[i], &v4->Privileges[i].Luid) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 32), LastError);
      v8 = v7 < 0;
      if ( v7 > 0 )
      {
        v7 = (unsigned __int16)v7 | 0x80070000;
        v8 = v7 < 0;
      }
      if ( v8 )
        LogMsgHR(v7, (wchar_t *)L"acssctrl/privilge", 0x33u);
      free(v4);
      return (unsigned int)v7;
    }
    v4->Privileges[i].Attributes = 4;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 32));
  }
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
  {
    v11 = GetLastError();
    v7 = v11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 16, &WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids, v11);
    v12 = v7 < 0;
    if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
      v12 = v7 < 0;
    }
    if ( v12 )
      LogMsgHR(v7, (wchar_t *)L"acssctrl/privilge", 0x32u);
    CHandle::~CHandle((CHandle *)&TokenHandle);
    free(v4);
    return (unsigned int)v7;
  }
  v13 = AdjustTokenPrivileges(TokenHandle, 0, v4, 0, 0, 0);
  v14 = GetLastError();
  v15 = v14;
  if ( v13 && (!v14 || v14 == 1300) )
  {
    CHandle::~CHandle((CHandle *)&TokenHandle);
    free(v4);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 17, &WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids, v14);
    v16 = v15 < 0;
    if ( v15 > 0 )
    {
      v15 = (unsigned __int16)v15 | 0x80070000;
      v16 = v15 < 0;
    }
    if ( v16 )
      LogMsgHR(v15, (wchar_t *)L"acssctrl/privilge", 0x34u);
    CHandle::~CHandle((CHandle *)&TokenHandle);
    free(v4);
    return (unsigned int)v15;
  }
}

```

## disassembly

```asm
0x180029370  mov     [rsp+arg_0], rbx
0x180029375  mov     [rsp+arg_8], rbp
0x18002937a  push    rsi
0x18002937b  push    rdi
0x18002937c  push    r13
0x18002937e  push    r14
0x180029380  push    r15
0x180029382  sub     rsp, 30h
0x180029386  mov     r14d, edx
0x180029389  mov     r15, rcx
0x18002938c  lea     eax, [rdx+rdx*2]
0x18002938f  lea     ecx, ds:10h[rax*4]; unsigned __int64
0x180029396  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002939b  mov     rbx, rax
0x18002939e  mov     [rsp+58h+arg_18], rax
0x1800293a3  mov     [rax], r14d
0x1800293a6  xor     edi, edi
0x1800293a8  lea     r13, WPP_GLOBAL_Control
0x1800293af  cmp     edi, r14d
0x1800293b2  jnb     loc_180029488
0x1800293b8  movsxd  rsi, edi
0x1800293bb  lea     rbp, [rsi+rsi*2]
0x1800293bf  lea     r8, [rbx+4]
0x1800293c3  lea     r8, [r8+rbp*4]; lpLuid
0x1800293c7  mov     rdx, [r15+rsi*8]; lpName
0x1800293cb  xor     ecx, ecx; lpSystemName
0x1800293cd  call    cs:__imp_LookupPrivilegeValueW
0x1800293d3  test    eax, eax
0x1800293d5  jz      short loc_180029414
0x1800293d7  mov     dword ptr [rbx+rbp*4+0Ch], 4
0x1800293df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293e6  cmp     rcx, r13
0x1800293e9  jz      short loc_180029410
0x1800293eb  test    byte ptr [rcx+10Ch], 4
0x1800293f2  jz      short loc_180029410
0x1800293f4  mov     edx, 0Fh
0x1800293f9  mov     r9, [r15+rsi*8]
0x1800293fd  lea     r8, WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids
0x180029404  mov     rcx, [rcx+100h]; LoggerHandle
0x18002940b  call    WPP_SF_S
0x180029410  inc     edi
0x180029412  jmp     short loc_1800293AF
0x180029414  call    cs:__imp_GetLastError
0x18002941a  mov     edi, eax
0x18002941c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029423  cmp     rcx, r13
0x180029426  jz      short loc_180029451
0x180029428  test    byte ptr [rcx+10Ch], 1
0x18002942f  jz      short loc_180029451
0x180029431  mov     edx, 0Eh
0x180029436  mov     dword ptr [rsp+58h+PreviousState], eax; char
0x18002943a  mov     r9, [r15+rsi*8]
0x18002943e  lea     r8, WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids
0x180029445  mov     rcx, [rcx+100h]; LoggerHandle
0x18002944c  call    WPP_SF_Sd
0x180029451  test    edi, edi
0x180029453  jle     short loc_180029460
0x180029455  movzx   edi, di
0x180029458  or      edi, 80070000h
0x18002945e  test    edi, edi
0x180029460  jns     short loc_180029477
0x180029462  mov     r8d, 33h ; '3'; unsigned __int16
0x180029468  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x18002946f  mov     ecx, edi; int
0x180029471  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029476  nop
0x180029477  mov     rcx, rbx; Block
0x18002947a  call    cs:__imp_free
0x180029480  nop
0x180029481  mov     eax, edi
0x180029483  jmp     loc_1800295EA
0x180029488  mov     [rsp+58h+TokenHandle], 0
0x180029491  call    cs:__imp_GetCurrentProcess
0x180029497  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18002949c  mov     edx, 20h ; ' '; DesiredAccess
0x1800294a1  mov     rcx, rax; ProcessHandle
0x1800294a4  call    cs:__imp_OpenProcessToken
0x1800294aa  test    eax, eax
0x1800294ac  jnz     short loc_180029526
0x1800294ae  call    cs:__imp_GetLastError
0x1800294b4  mov     edi, eax
0x1800294b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294bd  cmp     rcx, r13
0x1800294c0  jz      short loc_1800294E6
0x1800294c2  test    byte ptr [rcx+10Ch], 1
0x1800294c9  jz      short loc_1800294E6
0x1800294cb  mov     edx, 10h
0x1800294d0  mov     r9d, eax
0x1800294d3  lea     r8, WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids
0x1800294da  mov     rcx, [rcx+100h]
0x1800294e1  call    WPP_SF_d
0x1800294e6  test    edi, edi
0x1800294e8  jle     short loc_1800294F5
0x1800294ea  movzx   edi, di
0x1800294ed  or      edi, 80070000h
0x1800294f3  test    edi, edi
0x1800294f5  jns     short loc_18002950C
0x1800294f7  mov     r8d, 32h ; '2'; unsigned __int16
0x1800294fd  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029504  mov     ecx, edi; int
0x180029506  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002950b  nop
0x18002950c  lea     rcx, [rsp+58h+TokenHandle]; this
0x180029511  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180029516  nop
0x180029517  mov     rcx, rbx; Block
0x18002951a  call    cs:__imp_free
0x180029520  nop
0x180029521  jmp     loc_180029481
0x180029526  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18002952f  mov     [rsp+58h+PreviousState], 0; PreviousState
0x180029538  xor     r9d, r9d; BufferLength
0x18002953b  mov     r8, rbx; NewState
0x18002953e  xor     edx, edx; DisableAllPrivileges
0x180029540  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180029545  call    cs:__imp_AdjustTokenPrivileges
0x18002954b  mov     edi, eax
0x18002954d  call    cs:__imp_GetLastError
0x180029553  mov     esi, eax
0x180029555  test    edi, edi
0x180029557  jz      short loc_18002957D
0x180029559  test    eax, eax
0x18002955b  jz      short loc_180029564
0x18002955d  cmp     eax, 514h
0x180029562  jnz     short loc_18002957D
0x180029564  lea     rcx, [rsp+58h+TokenHandle]; this
0x180029569  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18002956e  nop
0x18002956f  mov     rcx, rbx; Block
0x180029572  call    cs:__imp_free
0x180029578  nop
0x180029579  xor     eax, eax
0x18002957b  jmp     short loc_1800295EA
0x18002957d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029584  cmp     rcx, r13
0x180029587  jz      short loc_1800295AD
0x180029589  test    byte ptr [rcx+10Ch], 1
0x180029590  jz      short loc_1800295AD
0x180029592  mov     edx, 11h
0x180029597  mov     r9d, esi
0x18002959a  lea     r8, WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids
0x1800295a1  mov     rcx, [rcx+100h]
0x1800295a8  call    WPP_SF_d
0x1800295ad  test    esi, esi
0x1800295af  jle     short loc_1800295BC
0x1800295b1  movzx   esi, si
0x1800295b4  or      esi, 80070000h
0x1800295ba  test    esi, esi
0x1800295bc  jns     short loc_1800295D3
0x1800295be  mov     r8d, 34h ; '4'; unsigned __int16
0x1800295c4  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x1800295cb  mov     ecx, esi; int
0x1800295cd  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800295d2  nop
0x1800295d3  lea     rcx, [rsp+58h+TokenHandle]; this
0x1800295d8  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1800295dd  nop
0x1800295de  mov     rcx, rbx; Block
0x1800295e1  call    cs:__imp_free
0x1800295e7  nop
0x1800295e8  mov     eax, esi
0x1800295ea  mov     rbx, [rsp+58h+arg_0]
0x1800295ef  mov     rbp, [rsp+58h+arg_8]
0x1800295f4  add     rsp, 30h
0x1800295f8  pop     r15
0x1800295fa  pop     r14
0x1800295fc  pop     r13
0x1800295fe  pop     rdi
0x1800295ff  pop     rsi
0x180029600  retn
```
