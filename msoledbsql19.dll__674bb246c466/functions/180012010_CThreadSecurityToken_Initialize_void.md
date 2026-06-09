# CThreadSecurityToken::Initialize(void)

- ea: `0x180012010`
- end: `0x180012241`
- name: `?Initialize@CThreadSecurityToken@@QEAAJXZ`
- size: `561`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010b00`
- `0x180031080`
- `0x180195410`

## callees

- `0x1800030c0`
- `0x180012010`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001203e`
- `KERNEL32!GetLastError` at `0x1800120ae`
- `KERNEL32!GetLastError` at `0x18001210c`
- `KERNEL32!GetLastError` at `0x18001203e`
- `KERNEL32!GetLastError` at `0x1800120ae`
- `KERNEL32!GetLastError` at `0x18001210c`
- `KERNEL32!GetCurrentProcess` at `0x1800120f1`
- `KERNEL32!GetCurrentProcess` at `0x1800120f1`
- `KERNEL32!GetCurrentThread` at `0x180012019`
- `KERNEL32!GetCurrentThread` at `0x18001204c`
- `KERNEL32!GetCurrentThread` at `0x180012019`
- `KERNEL32!GetCurrentThread` at `0x18001204c`
- `ADVAPI32!OpenProcessToken` at `0x180012102`
- `ADVAPI32!OpenProcessToken` at `0x180012102`
- `ADVAPI32!OpenThreadToken` at `0x180012030`
- `ADVAPI32!OpenThreadToken` at `0x180012060`
- `ADVAPI32!OpenThreadToken` at `0x180012030`
- `ADVAPI32!OpenThreadToken` at `0x180012060`

## pseudocode

```c
__int64 __fastcall CThreadSecurityToken::Initialize(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v4; // r9
  HANDLE v5; // rax
  wchar_t *v6; // r9
  __int64 v7; // r8
  char *v8; // rdx
  HANDLE CurrentProcess; // rax
  DWORD v10; // eax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, TokenHandle) )
  {
    if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::Initialize'::`66'::_bidPtrSA_030_3375[0] || bidID == -1 )
      return 0;
    v6 = `CThreadSecurityToken::Initialize'::`66'::_bidPtrSA_030_3375[0];
    v7 = 3456000;
    v8 = `CThreadSecurityToken::Initialize'::`66'::_bidSrcFileA[0];
    goto LABEL_30;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError == 5 )
  {
    v5 = GetCurrentThread();
    if ( OpenThreadToken(v5, 0xEu, 0, TokenHandle) )
    {
      if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::Initialize'::`16'::_bidPtrSA_030_3337[0] || bidID == -1 )
        return 0;
      v6 = `CThreadSecurityToken::Initialize'::`16'::_bidPtrSA_030_3337[0];
      v7 = 3417088;
      v8 = `CThreadSecurityToken::Initialize'::`16'::_bidSrcFileA[0];
LABEL_30:
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(bidID, v8, v7, v6, 0);
      return 0;
    }
    v4 = GetLastError();
  }
  if ( (_DWORD)v4 != 1008 )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Initialize'::`57'::_bidPtrSA_030_3368[0] )
      bidTraceW(
        `CThreadSecurityToken::Initialize'::`57'::_bidSrcFileA[0],
        3448832,
        `CThreadSecurityToken::Initialize'::`57'::_bidPtrSA_030_3368[0],
        v4);
    return 2147500037LL;
  }
  if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Initialize'::`31'::_bidPtrSA_030_3349[0] )
    bidTraceW(
      `CThreadSecurityToken::Initialize'::`31'::_bidSrcFileA[0],
      3429376,
      `CThreadSecurityToken::Initialize'::`31'::_bidPtrSA_030_3349[0],
      v4);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xEu, TokenHandle) )
  {
    v10 = GetLastError();
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Initialize'::`41'::_bidPtrSA_030_3358[0] )
    {
      bidTraceW(
        `CThreadSecurityToken::Initialize'::`41'::_bidSrcFileA[0],
        3438592,
        `CThreadSecurityToken::Initialize'::`41'::_bidPtrSA_030_3358[0],
        v10);
      return 2147500037LL;
    }
    return 2147500037LL;
  }
  if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Initialize'::`48'::_bidPtrSA_030_3363[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
      bidID,
      `CThreadSecurityToken::Initialize'::`48'::_bidSrcFileA[0],
      3443712,
      `CThreadSecurityToken::Initialize'::`48'::_bidPtrSA_030_3363[0],
      0);
  *((_BYTE *)TokenHandle + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x180012010  push    rbx
0x180012012  sub     rsp, 30h
0x180012016  mov     rbx, rcx
0x180012019  call    cs:__imp_GetCurrentThread
0x18001201f  mov     r9, rbx; TokenHandle
0x180012022  mov     edx, 0Eh; DesiredAccess
0x180012027  mov     rcx, rax; ThreadHandle
0x18001202a  mov     r8d, 1; OpenAsSelf
0x180012030  call    cs:__imp_OpenThreadToken
0x180012036  test    eax, eax
0x180012038  jnz     loc_1800121E9
0x18001203e  call    cs:__imp_GetLastError
0x180012044  mov     r9d, eax
0x180012047  cmp     eax, 5
0x18001204a  jnz     short loc_1800120B7
0x18001204c  call    cs:__imp_GetCurrentThread
0x180012052  mov     r9, rbx; TokenHandle
0x180012055  xor     r8d, r8d; OpenAsSelf
0x180012058  mov     rcx, rax; ThreadHandle
0x18001205b  mov     edx, 0Eh; DesiredAccess
0x180012060  call    cs:__imp_OpenThreadToken
0x180012066  test    eax, eax
0x180012068  jz      short loc_1800120AE
0x18001206a  test    byte ptr cs:_bidGblFlags, 2
0x180012071  jz      loc_180012239
0x180012077  mov     rax, cs:?_bidPtrSA_030_3337@?BA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`16'::_bidPtrSA_030_3337
0x18001207e  test    rax, rax
0x180012081  jz      loc_180012239
0x180012087  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18001208f  jz      loc_180012239
0x180012095  mov     r9, cs:?_bidPtrSA_030_3337@?BA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`16'::_bidPtrSA_030_3337
0x18001209c  mov     r8d, 342400h
0x1800120a2  mov     rdx, cs:?_bidSrcFileA@?BA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`16'::_bidSrcFileA
0x1800120a9  jmp     loc_18001221C
0x1800120ae  call    cs:__imp_GetLastError
0x1800120b4  mov     r9d, eax
0x1800120b7  cmp     r9d, 3F0h
0x1800120be  jnz     loc_1800121B1
0x1800120c4  test    byte ptr cs:_bidGblFlags, 2
0x1800120cb  jz      short loc_1800120F1
0x1800120cd  mov     rax, cs:?_bidPtrSA_030_3349@?BP@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`31'::_bidPtrSA_030_3349
0x1800120d4  test    rax, rax
0x1800120d7  jz      short loc_1800120F1
0x1800120d9  mov     r8, cs:?_bidPtrSA_030_3349@?BP@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`31'::_bidPtrSA_030_3349
0x1800120e0  mov     edx, 345400h
0x1800120e5  mov     rcx, cs:?_bidSrcFileA@?BP@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`31'::_bidSrcFileA
0x1800120ec  call    _bidTraceW
0x1800120f1  call    cs:__imp_GetCurrentProcess
0x1800120f7  mov     r8, rbx; TokenHandle
0x1800120fa  mov     edx, 0Eh; DesiredAccess
0x1800120ff  mov     rcx, rax; ProcessHandle
0x180012102  call    cs:__imp_OpenProcessToken
0x180012108  test    eax, eax
0x18001210a  jnz     short loc_180012155
0x18001210c  call    cs:__imp_GetLastError
0x180012112  test    byte ptr cs:_bidGblFlags, 2
0x180012119  jz      loc_1800121DE
0x18001211f  mov     rcx, cs:?_bidPtrSA_030_3358@?CJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`41'::_bidPtrSA_030_3358
0x180012126  test    rcx, rcx
0x180012129  jz      loc_1800121DE
0x18001212f  mov     r8, cs:?_bidPtrSA_030_3358@?CJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`41'::_bidPtrSA_030_3358
0x180012136  mov     r9d, eax
0x180012139  mov     rcx, cs:?_bidSrcFileA@?CJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`41'::_bidSrcFileA
0x180012140  mov     edx, 347800h
0x180012145  call    _bidTraceW
0x18001214a  mov     eax, 80004005h
0x18001214f  add     rsp, 30h
0x180012153  pop     rbx
0x180012154  retn
0x180012155  test    byte ptr cs:_bidGblFlags, 2
0x18001215c  jz      short loc_1800121A5
0x18001215e  mov     rax, cs:?_bidPtrSA_030_3363@?DA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`48'::_bidPtrSA_030_3363
0x180012165  test    rax, rax
0x180012168  jz      short loc_1800121A5
0x18001216a  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180012172  jz      short loc_1800121A5
0x180012174  mov     r9, cs:?_bidPtrSA_030_3363@?DA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`48'::_bidPtrSA_030_3363
0x18001217b  mov     r8d, 348C00h
0x180012181  mov     rdx, cs:?_bidSrcFileA@?DA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`48'::_bidSrcFileA
0x180012188  mov     rcx, cs:_bidID
0x18001218f  mov     rax, cs:off_180248050
0x180012196  mov     [rsp+38h+var_18], 0
0x18001219f  call    cs:__guard_dispatch_icall_fptr
0x1800121a5  mov     byte ptr [rbx+8], 1
0x1800121a9  xor     eax, eax
0x1800121ab  add     rsp, 30h
0x1800121af  pop     rbx
0x1800121b0  retn
0x1800121b1  test    byte ptr cs:_bidGblFlags, 2
0x1800121b8  jz      short loc_1800121DE
0x1800121ba  mov     rax, cs:?_bidPtrSA_030_3368@?DJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`57'::_bidPtrSA_030_3368
0x1800121c1  test    rax, rax
0x1800121c4  jz      short loc_1800121DE
0x1800121c6  mov     r8, cs:?_bidPtrSA_030_3368@?DJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`57'::_bidPtrSA_030_3368
0x1800121cd  mov     edx, 34A000h
0x1800121d2  mov     rcx, cs:?_bidSrcFileA@?DJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`57'::_bidSrcFileA
0x1800121d9  call    _bidTraceW
0x1800121de  mov     eax, 80004005h
0x1800121e3  add     rsp, 30h
0x1800121e7  pop     rbx
0x1800121e8  retn
0x1800121e9  test    byte ptr cs:_bidGblFlags, 2
0x1800121f0  jz      short loc_180012239
0x1800121f2  mov     rax, cs:?_bidPtrSA_030_3375@?EC@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`66'::_bidPtrSA_030_3375
0x1800121f9  test    rax, rax
0x1800121fc  jz      short loc_180012239
0x1800121fe  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180012206  jz      short loc_180012239
0x180012208  mov     r9, cs:?_bidPtrSA_030_3375@?EC@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REB_WEB; wchar_t const * const `CThreadSecurityToken::Initialize(void)'::`66'::_bidPtrSA_030_3375
0x18001220f  mov     r8d, 34BC00h
0x180012215  mov     rdx, cs:?_bidSrcFileA@?EC@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`66'::_bidSrcFileA
0x18001221c  mov     rcx, cs:_bidID
0x180012223  mov     rax, cs:off_180248050
0x18001222a  mov     [rsp+38h+var_18], 0
0x180012233  call    cs:__guard_dispatch_icall_fptr
0x180012239  xor     eax, eax
0x18001223b  add     rsp, 30h
0x18001223f  pop     rbx
0x180012240  retn
```
