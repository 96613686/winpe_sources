# FwpmEngineOpen0

- ea: `0x180007380`
- end: `0x18000754a`
- name: `FwpmEngineOpen0`
- size: `458`
- prototype: `DWORD __stdcall(const wchar_t *serverName, UINT32 authnService, SEC_WINNT_AUTH_IDENTITY_W *authIdentity, const FWPM_SESSION0 *session, HANDLE *engineHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038ae8`

## callees

- `0x180007380`
- `0x180007550`
- `0x180007b60`
- `0x180007e38`
- `0x18000e898`
- `0x18003b2c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800074ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800074ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073b7`

## string_xrefs

- `0x180007431`: `FwpmEngineOpen0`
- `0x1800074ff`: `FwppCompleteInit`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
DWORD __stdcall FwpmEngineOpen0(
        const wchar_t *serverName,
        UINT32 authnService,
        SEC_WINNT_AUTH_IDENTITY_W *authIdentity,
        const FWPM_SESSION0 *session,
        HANDLE *engineHandle)
{
  __int64 v9; // rdi
  __int64 v10; // rax
  int v11; // ecx
  void *v12; // rcx
  int v13; // edx

  if ( !engineHandle )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (_DWORD)authIdentity,
        0,
        (__int64)"FwpmEngineOpen0",
        -2144206820);
    }
    if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v12, *(_QWORD *)&authnService, "FwpmEngineOpen0", 2150760476LL);
    v11 = -2144206820;
    goto LABEL_13;
  }
  v9 = 0;
  EnterCriticalSection(&gFwppInitializationLock);
  if ( gFwppSessionInitialized || (v9 = WfpComponentsStart((__int64 *)&FWPP_SESSION_COMPONENTS)) != 0 )
  {
    LeaveCriticalSection(&gFwppInitializationLock);
    if ( v9 )
      WfpReportError(v9, "FwppCompleteInit");
  }
  else
  {
    gFwppSessionInitialized = 1;
    LeaveCriticalSection(&gFwppInitializationLock);
  }
  v10 = FwppSessionCreate((__int64)serverName, authnService, (__int64)authIdentity, (__int64)session, engineHandle);
  v11 = v10;
  if ( v10 )
  {
LABEL_13:
    v13 = (unsigned __int16)v11;
    if ( (v11 & 0x1FFF0000) != 0x70000 )
      v13 = v11;
    switch ( v13 )
    {
      case 1727:
      case 6:
        LODWORD(v10) = -2144206832;
        break;
      case 1733:
        LODWORD(v10) = -2144206819;
        break;
      case 1775:
      case 1780:
        LODWORD(v10) = -2144206820;
        break;
      default:
        LODWORD(v10) = v13;
        break;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180007380  mov     [rsp+arg_8], rbx
0x180007385  mov     [rsp+arg_10], rbp
0x18000738a  push    rsi
0x18000738b  push    r14
0x18000738d  push    r15
0x18000738f  sub     rsp, 30h
0x180007393  mov     rbx, [rsp+48h+engineHandle]
0x180007398  mov     rsi, r9
0x18000739b  mov     rbp, r8
0x18000739e  mov     r14d, edx
0x1800073a1  mov     r15, rcx
0x1800073a4  test    rbx, rbx
0x1800073a7  jz      short loc_180007423
0x1800073a9  mov     [rsp+48h+arg_0], rdi
0x1800073ae  lea     rcx, gFwppInitializationLock; lpCriticalSection
0x1800073b5  xor     edi, edi
0x1800073b7  call    cs:__imp_EnterCriticalSection
0x1800073be  nop     dword ptr [rax+rax+00h]
0x1800073c3  cmp     cs:gFwppSessionInitialized, edi
0x1800073c9  jz      loc_180007485
0x1800073cf  lea     rcx, gFwppInitializationLock; lpCriticalSection
0x1800073d6  call    cs:__imp_LeaveCriticalSection
0x1800073dd  nop     dword ptr [rax+rax+00h]
0x1800073e2  test    rdi, rdi
0x1800073e5  jnz     loc_1800074FF
0x1800073eb  mov     r9, rsi
0x1800073ee  mov     [rsp+48h+var_28], rbx
0x1800073f3  mov     r8, rbp
0x1800073f6  mov     edx, r14d
0x1800073f9  mov     rcx, r15
0x1800073fc  call    FwppSessionCreate
0x180007401  mov     rdi, [rsp+48h+arg_0]
0x180007406  mov     rcx, rax
0x180007409  test    rax, rax
0x18000740c  jnz     short loc_180007460
0x18000740e  mov     rbx, [rsp+48h+arg_8]
0x180007413  mov     rbp, [rsp+48h+arg_10]
0x180007418  add     rsp, 30h
0x18000741c  pop     r15
0x18000741e  pop     r14
0x180007420  pop     rsi
0x180007421  retn
0x180007423  mov     rcx, cs:WPP_GLOBAL_Control
0x18000742a  lea     rax, WPP_GLOBAL_Control
0x180007431  lea     rbx, aFwpmengineopen_0; "FwpmEngineOpen0"
0x180007438  cmp     rcx, rax
0x18000743b  jz      short loc_180007443
0x18000743d  cmp     byte ptr [rcx+19h], 2
0x180007441  jnb     short loc_1800074BF
0x180007443  cmp     cs:gWfpLogUserModeErrors, 0
0x18000744a  jz      short loc_180007459
0x18000744c  test    cs:byte_18007C665, 1
0x180007453  jnz     loc_1800074EC
0x180007459  mov     rcx, 0FFFFFFFF8032001Ch
0x180007460  mov     eax, ecx
0x180007462  movzx   edx, cx
0x180007465  and     eax, 1FFF0000h
0x18000746a  cmp     eax, 70000h
0x18000746f  cmovnz  edx, ecx
0x180007472  cmp     edx, 6BFh
0x180007478  jnz     loc_180007513
0x18000747e  mov     eax, 80320010h
0x180007483  jmp     short loc_18000740E
0x180007485  lea     rcx, FWPP_SESSION_COMPONENTS
0x18000748c  call    WfpComponentsStart
0x180007491  mov     rdi, rax
0x180007494  test    rax, rax
0x180007497  jnz     loc_1800073CF
0x18000749d  lea     rcx, gFwppInitializationLock; lpCriticalSection
0x1800074a4  mov     cs:gFwppSessionInitialized, 1
0x1800074ae  call    cs:__imp_LeaveCriticalSection
0x1800074b5  nop     dword ptr [rax+rax+00h]
0x1800074ba  jmp     loc_1800073EB
0x1800074bf  test    byte ptr [rcx+1Ch], 1
0x1800074c3  jz      loc_180007443
0x1800074c9  mov     rcx, [rcx+10h]
0x1800074cd  mov     edx, 17h
0x1800074d2  mov     [rsp+48h+var_20], 8032001Ch
0x1800074da  xor     r9d, r9d
0x1800074dd  mov     [rsp+48h+var_28], rbx
0x1800074e2  call    WPP_SF_Ssd
0x1800074e7  jmp     loc_180007443
0x1800074ec  mov     r9d, 8032001Ch
0x1800074f2  mov     r8, rbx
0x1800074f5  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800074fa  jmp     loc_180007459
0x1800074ff  lea     rdx, aFwppcompletein; "FwppCompleteInit"
0x180007506  mov     rcx, rdi
0x180007509  call    WfpReportError
0x18000750e  jmp     loc_1800073EB
0x180007513  mov     eax, edx
0x180007515  sub     eax, 6
0x180007518  jz      loc_18000747E
0x18000751e  sub     eax, 6BFh
0x180007523  jz      short loc_180007540
0x180007525  sub     eax, 2Ah ; '*'
0x180007528  jz      short loc_180007536
0x18000752a  cmp     eax, 5
0x18000752d  jz      short loc_180007536
0x18000752f  mov     eax, edx
0x180007531  jmp     loc_18000740E
0x180007536  mov     eax, 8032001Ch
0x18000753b  jmp     loc_18000740E
0x180007540  mov     eax, 8032001Dh
0x180007545  jmp     loc_18000740E
```
