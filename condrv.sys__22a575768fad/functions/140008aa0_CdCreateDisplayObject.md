# CdCreateDisplayObject

- ea: `0x140008aa0`
- end: `0x140008c7a`
- name: `CdCreateDisplayObject`
- size: `474`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400014d0`
- `0x140008aa0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140008c23`
- `ntoskrnl!ExAllocatePool2` at `0x140008c23`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008b7e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008b7e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008bde`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008bff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008bde`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008bff`
- `ntoskrnl!IofCompleteRequest` at `0x140008afb`
- `ntoskrnl!IofCompleteRequest` at `0x140008c67`
- `ntoskrnl!IofCompleteRequest` at `0x140008afb`
- `ntoskrnl!IofCompleteRequest` at `0x140008c67`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x140008ad6`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x140008ad6`
- `ntoskrnl!SeExports` at `0x140008b38`
- `ntoskrnl!SePrivilegeCheck` at `0x140008b64`
- `ntoskrnl!SePrivilegeCheck` at `0x140008b64`
- `ntoskrnl!RtlRunOnceBeginInitialize` at `0x140008b96`
- `ntoskrnl!RtlRunOnceBeginInitialize` at `0x140008b96`
- `ntoskrnl!BgkGetConsoleState` at `0x140008bb2`
- `ntoskrnl!BgkGetConsoleState` at `0x140008bb2`
- `ntoskrnl!RtlRunOnceComplete` at `0x140008bd2`
- `ntoskrnl!RtlRunOnceComplete` at `0x140008bf1`
- `ntoskrnl!RtlRunOnceComplete` at `0x140008bd2`
- `ntoskrnl!RtlRunOnceComplete` at `0x140008bf1`

## pseudocode

```c
__int64 __fastcall CdCreateDisplayObject(PIRP Irp, __int64 a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int ConsoleState; // ebx
  KPROCESSOR_MODE RequestorMode; // r8
  _QWORD *Pool2; // rax
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+20h] [rbp-28h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  if ( (unsigned __int8)PsIsCurrentThreadInServerSilo(Irp, a2, a3) )
  {
    ConsoleState = -1073741637;
LABEL_3:
    Irp->IoStatus.Status = ConsoleState;
    Irp->IoStatus.Information = 0;
    IofCompleteRequest(Irp, 0);
    return (unsigned int)ConsoleState;
  }
  RequestorMode = Irp->RequestorMode;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Luid = SeExports->SeTcbPrivilege;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  if ( !SePrivilegeCheck(
          &RequiredPrivileges,
          (PSECURITY_SUBJECT_CONTEXT)(*(_QWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 8) + 32LL),
          RequestorMode) )
  {
    ConsoleState = -1073741727;
    goto LABEL_3;
  }
  KeEnterCriticalRegion();
  ConsoleState = RtlRunOnceBeginInitialize(&CdpDisplayInitialized, 0, 0);
  if ( ConsoleState == 259 )
  {
    ConsoleState = BgkGetConsoleState(&CdpDisplayState);
    if ( ConsoleState < 0 )
    {
      RtlRunOnceComplete(&CdpDisplayInitialized, 4u, 0);
      KeLeaveCriticalRegion();
      goto LABEL_3;
    }
    ConsoleState = RtlRunOnceComplete(&CdpDisplayInitialized, 0, 0);
  }
  KeLeaveCriticalRegion();
  if ( ConsoleState < 0 )
    goto LABEL_3;
  Pool2 = (_QWORD *)ExAllocatePool2(257, 8, 1766089795);
  if ( !Pool2 )
  {
    ConsoleState = -1073741670;
    goto LABEL_3;
  }
  *Pool2 = CdDisplayType;
  CurrentStackLocation->FileObject->FsContext = Pool2;
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x140008aa0  mov     [rsp+arg_8], rbx
0x140008aa5  mov     [rsp+arg_10], rsi
0x140008aaa  push    rdi
0x140008aab  sub     rsp, 40h
0x140008aaf  mov     rax, cs:__security_cookie
0x140008ab6  xor     rax, rsp
0x140008ab9  mov     [rsp+48h+var_10], rax
0x140008abe  mov     rsi, [rcx+0B8h]
0x140008ac5  xorps   xmm0, xmm0
0x140008ac8  xor     eax, eax
0x140008aca  mov     rdi, rcx
0x140008acd  movups  xmmword ptr [rsp+48h+RequiredPrivileges.PrivilegeCount], xmm0
0x140008ad2  mov     [rsp+48h+RequiredPrivileges.Privilege.Attributes], eax
0x140008ad6  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x140008add  nop     dword ptr [rax+rax+00h]
0x140008ae2  test    al, al
0x140008ae4  jz      short loc_140008B27
0x140008ae6  mov     ebx, 0C00000BBh
0x140008aeb  xor     edx, edx; PriorityBoost
0x140008aed  mov     [rdi+30h], ebx
0x140008af0  mov     rcx, rdi; Irp
0x140008af3  mov     qword ptr [rdi+38h], 0
0x140008afb  call    cs:__imp_IofCompleteRequest
0x140008b02  nop     dword ptr [rax+rax+00h]
0x140008b07  mov     eax, ebx
0x140008b09  mov     rcx, [rsp+48h+var_10]
0x140008b0e  xor     rcx, rsp; StackCookie
0x140008b11  call    __security_check_cookie
0x140008b16  mov     rbx, [rsp+48h+arg_8]
0x140008b1b  mov     rsi, [rsp+48h+arg_10]
0x140008b20  add     rsp, 40h
0x140008b24  pop     rdi
0x140008b25  retn
0x140008b27  mov     r8b, [rdi+40h]; AccessMode
0x140008b2b  mov     eax, 1
0x140008b30  mov     [rsp+48h+RequiredPrivileges.PrivilegeCount], eax
0x140008b34  mov     [rsp+48h+RequiredPrivileges.Control], eax
0x140008b38  mov     rax, cs:__imp_SeExports
0x140008b3f  mov     rcx, [rax]
0x140008b42  mov     rax, [rcx+28h]
0x140008b46  lea     rcx, [rsp+48h+RequiredPrivileges]; RequiredPrivileges
0x140008b4b  mov     qword ptr [rsp+48h+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x140008b50  mov     [rsp+48h+RequiredPrivileges.Privilege.Attributes], 0
0x140008b58  mov     rax, [rsi+8]
0x140008b5c  mov     rdx, [rax+8]
0x140008b60  add     rdx, 20h ; ' '; SubjectSecurityContext
0x140008b64  call    cs:__imp_SePrivilegeCheck
0x140008b6b  nop     dword ptr [rax+rax+00h]
0x140008b70  test    al, al
0x140008b72  jnz     short loc_140008B7E
0x140008b74  mov     ebx, 0C0000061h
0x140008b79  jmp     loc_140008AEB
0x140008b7e  call    cs:__imp_KeEnterCriticalRegion
0x140008b85  nop     dword ptr [rax+rax+00h]
0x140008b8a  xor     r8d, r8d; Context
0x140008b8d  lea     rcx, CdpDisplayInitialized; RunOnce
0x140008b94  xor     edx, edx; Flags
0x140008b96  call    cs:__imp_RtlRunOnceBeginInitialize
0x140008b9d  nop     dword ptr [rax+rax+00h]
0x140008ba2  mov     ebx, eax
0x140008ba4  cmp     eax, 103h
0x140008ba9  jnz     short loc_140008BFF
0x140008bab  lea     rcx, CdpDisplayState
0x140008bb2  call    cs:__imp_BgkGetConsoleState
0x140008bb9  nop     dword ptr [rax+rax+00h]
0x140008bbe  xor     r8d, r8d; Context
0x140008bc1  lea     rcx, CdpDisplayInitialized; RunOnce
0x140008bc8  mov     ebx, eax
0x140008bca  test    eax, eax
0x140008bcc  jns     short loc_140008BEF
0x140008bce  lea     edx, [r8+4]; Flags
0x140008bd2  call    cs:__imp_RtlRunOnceComplete
0x140008bd9  nop     dword ptr [rax+rax+00h]
0x140008bde  call    cs:__imp_KeLeaveCriticalRegion
0x140008be5  nop     dword ptr [rax+rax+00h]
0x140008bea  jmp     loc_140008AEB
0x140008bef  xor     edx, edx; Flags
0x140008bf1  call    cs:__imp_RtlRunOnceComplete
0x140008bf8  nop     dword ptr [rax+rax+00h]
0x140008bfd  mov     ebx, eax
0x140008bff  call    cs:__imp_KeLeaveCriticalRegion
0x140008c06  nop     dword ptr [rax+rax+00h]
0x140008c0b  test    ebx, ebx
0x140008c0d  js      loc_140008AEB
0x140008c13  mov     edx, 8
0x140008c18  mov     ecx, 101h
0x140008c1d  mov     r8d, 69446443h
0x140008c23  call    cs:__imp_ExAllocatePool2
0x140008c2a  nop     dword ptr [rax+rax+00h]
0x140008c2f  mov     rcx, rax
0x140008c32  test    rax, rax
0x140008c35  jnz     short loc_140008C41
0x140008c37  mov     ebx, 0C000009Ah
0x140008c3c  jmp     loc_140008AEB
0x140008c41  lea     rax, CdDisplayType
0x140008c48  xor     edx, edx; PriorityBoost
0x140008c4a  mov     [rcx], rax
0x140008c4d  mov     rax, [rsi+30h]
0x140008c51  mov     [rax+18h], rcx
0x140008c55  mov     rcx, rdi; Irp
0x140008c58  mov     dword ptr [rdi+30h], 0
0x140008c5f  mov     qword ptr [rdi+38h], 0
0x140008c67  call    cs:__imp_IofCompleteRequest
0x140008c6e  nop     dword ptr [rax+rax+00h]
0x140008c73  xor     eax, eax
0x140008c75  jmp     loc_140008B09
```
