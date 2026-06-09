# FeTelemetryInit

- ea: `0x14006aa50`
- end: `0x14006ab93`
- name: `FeTelemetryInit`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400643a0`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14000afa0`
- `0x14003d590`
- `0x14005c080`
- `0x14006aa50`
- `0x14006ab9c`
- `0x14006bbb8`
- `0x14006bf4c`
- `0x1400ace20`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14006aac4`
- `ntoskrnl!ZwClose` at `0x14006aac4`

## string_xrefs

- `0x14006aa66`: `\Registry\Machine\System\CurrentControlSet\Services\BFE\Parameters`
- `0x14006aaa1`: `FeTelemetryRaiseOnTxnCommit`

## pseudocode

```c
__int64 FeTelemetryInit()
{
  __int64 v0; // rbx
  unsigned int v1; // eax
  __int64 v2; // rcx
  int v4; // [rsp+50h] [rbp+18h] BYREF
  int v5; // [rsp+58h] [rbp+20h]
  int v6; // [rsp+60h] [rbp+28h]
  HANDLE Handle; // [rsp+68h] [rbp+30h] BYREF

  Handle = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  if ( !WfpRegOpenKey(&Handle, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\BFE\\Parameters", &v4) && v4 )
  {
    if ( !WfpRegGetUint32Value(Handle) && v5 )
      gFeTelemetryRaiseOnTxnCommit = v6;
    ZwClose(Handle);
    Handle = 0;
  }
  TlgRegisterAggregateProvider(&dword_14009A0D0);
  v0 = WfpPoolAllocNonPaged(56, 1700029766, &gWfpGlobal[10].L.Future[4]);
  if ( v0 )
    goto LABEL_10;
  v1 = NetioTimerWorkItemInitialize(
         *(_QWORD *)&gWfpGlobal[10].L.Future[4],
         (__int64)FeTelemetryCallback,
         0,
         1,
         0,
         *(PVOID *)&gWfpGlobal[9].L.FreeMisses);
  if ( !v1 )
  {
    NetioTimerWorkItemStart(*(PKSPIN_LOCK *)&gWfpGlobal[10].L.Future[4]);
    return v0;
  }
  v0 = WfpReportSysErrorAsNtStatus(v2, "NetioTimerWorkItemInitialize", v1, 1);
  if ( v0 )
  {
LABEL_10:
    FeTelemetryShutdown();
    WfpReportError(v0, "FeTelemetryInit");
  }
  return v0;
}

```

## disassembly

```asm
0x14006aa50  push    rbp
0x14006aa52  push    rbx
0x14006aa53  mov     rbp, rsp
0x14006aa56  sub     rsp, 38h
0x14006aa5a  lea     r8, [rbp+arg_0]
0x14006aa5e  mov     [rbp+Handle], 0
0x14006aa66  lea     rdx, aRegistryMachin_9; "\\Registry\\Machine\\System\\CurrentCon"...
0x14006aa6d  mov     [rbp+arg_0], 0
0x14006aa74  lea     rcx, [rbp+Handle]; KeyHandle
0x14006aa78  mov     [rbp+arg_8], 0
0x14006aa7f  mov     [rbp+arg_10], 0
0x14006aa86  call    WfpRegOpenKey
0x14006aa8b  test    rax, rax
0x14006aa8e  jnz     short loc_14006AAD8
0x14006aa90  cmp     [rbp+arg_0], eax
0x14006aa93  jz      short loc_14006AAD8
0x14006aa95  mov     rcx, [rbp+Handle]; KeyHandle
0x14006aa99  lea     r9, [rbp+arg_8]
0x14006aa9d  lea     r8, [rbp+arg_10]
0x14006aaa1  lea     rdx, aFetelemetryrai; "FeTelemetryRaiseOnTxnCommit"
0x14006aaa8  call    WfpRegGetUint32Value
0x14006aaad  test    rax, rax
0x14006aab0  jnz     short loc_14006AAC0
0x14006aab2  cmp     [rbp+arg_8], eax
0x14006aab5  jz      short loc_14006AAC0
0x14006aab7  mov     eax, [rbp+arg_10]
0x14006aaba  mov     cs:gFeTelemetryRaiseOnTxnCommit, eax
0x14006aac0  mov     rcx, [rbp+Handle]; Handle
0x14006aac4  call    cs:__imp_ZwClose
0x14006aacb  nop     dword ptr [rax+rax+00h]
0x14006aad0  mov     [rbp+Handle], 0
0x14006aad8  lea     rcx, dword_14009A0D0
0x14006aadf  call    TlgRegisterAggregateProvider
0x14006aae4  mov     r8, cs:gWfpGlobal
0x14006aaeb  mov     edx, 65546546h
0x14006aaf0  add     r8, 568h
0x14006aaf7  mov     ecx, 38h ; '8'
0x14006aafc  call    WfpPoolAllocNonPaged
0x14006ab01  mov     rbx, rax
0x14006ab04  test    rax, rax
0x14006ab07  jnz     short loc_14006AB5A
0x14006ab09  mov     rcx, cs:gWfpGlobal
0x14006ab10  lea     r9d, [rax+1]; int
0x14006ab14  xor     r8d, r8d; int
0x14006ab17  mov     rdx, [rcx+4A0h]
0x14006ab1e  mov     rcx, [rcx+568h]; int
0x14006ab25  mov     [rsp+38h+IoObject], rdx; IoObject
0x14006ab2a  lea     rdx, FeTelemetryCallback; int
0x14006ab31  mov     [rsp+38h+var_18], rax; __int64
0x14006ab36  call    NetioTimerWorkItemInitialize
0x14006ab3b  test    eax, eax
0x14006ab3d  jz      short loc_14006AB79
0x14006ab3f  lea     r9d, [rbx+1]
0x14006ab43  mov     r8d, eax
0x14006ab46  lea     rdx, aNetiotimerwork; "NetioTimerWorkItemInitialize"
0x14006ab4d  call    WfpReportSysErrorAsNtStatus
0x14006ab52  mov     rbx, rax
0x14006ab55  test    rax, rax
0x14006ab58  jz      short loc_14006AB6E
0x14006ab5a  call    FeTelemetryShutdown
0x14006ab5f  lea     rdx, aFetelemetryini; "FeTelemetryInit"
0x14006ab66  mov     rcx, rbx
0x14006ab69  call    WfpReportError
0x14006ab6e  mov     rax, rbx
0x14006ab71  add     rsp, 38h
0x14006ab75  pop     rbx
0x14006ab76  pop     rbp
0x14006ab77  retn
0x14006ab79  mov     rcx, cs:gWfpGlobal
0x14006ab80  mov     edx, 36EE80h
0x14006ab85  mov     rcx, [rcx+568h]; SpinLock
0x14006ab8c  call    NetioTimerWorkItemStart
0x14006ab91  jmp     short loc_14006AB6E
```
