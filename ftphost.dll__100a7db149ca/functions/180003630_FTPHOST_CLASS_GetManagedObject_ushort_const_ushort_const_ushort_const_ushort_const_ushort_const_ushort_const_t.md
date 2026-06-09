# FTPHOST_CLASS::GetManagedObject(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagSAFEARRAY *,IUnknown * *)

- ea: `0x180003630`
- end: `0x1800037d4`
- name: `?GetManagedObject@FTPHOST_CLASS@@UEAAJPEBG00000PEAUtagSAFEARRAY@@PEAPEAUIUnknown@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct tagSAFEARRAY *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003630`
- `0x180003800`
- `0x180005010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000368f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000368f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800036c4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800036c4`
- `iisutil!PuDbgPrintError` at `0x180003702`
- `iisutil!PuDbgPrintError` at `0x180003793`
- `iisutil!PuDbgPrintError` at `0x180003702`
- `iisutil!PuDbgPrintError` at `0x180003793`

## string_xrefs

- `0x1800036ac`: `Microsoft.Web.FtpServer.Host.HostService,Microsoft.Web.FtpServer,Version=7.5.0.0,Culture=neutral,PublicKeyToken=31bf3856ad364e35`
- `0x1800036de`: `Failed to instantiate Microsoft.Web.FtpServer.Host.HostService\n`
- `0x18000376a`: `_pFtpHostService->GetHostedObject(%S) call failed\n`

## pseudocode

```c
__int64 __fastcall FTPHOST_CLASS::GetManagedObject(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        struct tagSAFEARRAY *a8,
        struct IUnknown **a9)
{
  int ClrHost; // ebx
  RTL_SRWLOCK *v14; // rsi
  struct IUnknown *v15; // rcx
  PVOID Ptr; // rcx
  struct IUnknown *v18; // [rsp+40h] [rbp-30h] BYREF
  __int128 v19; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int128 v20; // [rsp+58h] [rbp-18h]
  const unsigned __int16 *v21; // [rsp+68h] [rbp-8h]

  ClrHost = 0;
  v18 = 0;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  if ( !FTPHOST_CLASS::sm_pClrHostingHelper )
  {
    ClrHost = FTPHOST_CLASS::LoadClrHost((FTPHOST_CLASS *)this);
    if ( ClrHost < 0 )
    {
LABEL_9:
      v15 = v18;
      goto LABEL_14;
    }
  }
  v14 = this + 2;
  if ( !this[2].Ptr )
  {
    AcquireSRWLockExclusive(this + 3);
    if ( !v14->Ptr )
      ClrHost = (**(__int64 (__fastcall ***)(struct IClrHostingHelper *, const wchar_t *, GUID *, char *))FTPHOST_CLASS::sm_pClrHostingHelper)(
                  FTPHOST_CLASS::sm_pClrHostingHelper,
                  L"Microsoft.Web.FtpServer.Host.HostService,Microsoft.Web.FtpServer,Version=7.5.0.0,Culture=neutral,Publi"
                   "cKeyToken=31bf3856ad364e35",
                  &GUID_45a7e15a_1386_459f_85b9_1e1e9e81219b,
                  (char *)&this[2]);
    ReleaseSRWLockExclusive(this + 3);
    if ( ClrHost < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class.cxx",
          484,
          "FTPHOST_CLASS::GetManagedObject",
          ClrHost,
          "Failed to instantiate Microsoft.Web.FtpServer.Host.HostService\n");
      goto LABEL_9;
    }
  }
  Ptr = v14->Ptr;
  v20 = __PAIR128__((unsigned __int64)a6, (unsigned __int64)a5);
  v21 = a7;
  *(_QWORD *)&v19 = a3;
  *((_QWORD *)&v19 + 1) = a4;
  ClrHost = (*(__int64 (__fastcall **)(PVOID, const unsigned __int16 *, __int128 *, struct tagSAFEARRAY *, struct IUnknown **))(*(_QWORD *)Ptr + 24LL))(
              Ptr,
              a2,
              &v19,
              a8,
              &v18);
  if ( ClrHost < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class.cxx",
        506,
        "FTPHOST_CLASS::GetManagedObject",
        ClrHost,
        "_pFtpHostService->GetHostedObject(%S) call failed\n");
    goto LABEL_9;
  }
  *a9 = v18;
  v15 = 0;
  v18 = 0;
LABEL_14:
  if ( v15 )
    ((void (__fastcall *)(struct IUnknown *))v15->lpVtbl->Release)(v15);
  return (unsigned int)ClrHost;
}

```

## disassembly

```asm
0x180003630  push    rbp
0x180003632  push    rbx
0x180003633  push    rsi
0x180003634  push    rdi
0x180003635  push    r12
0x180003637  push    r14
0x180003639  push    r15
0x18000363b  mov     rbp, rsp
0x18000363e  sub     rsp, 70h
0x180003642  xor     ebx, ebx
0x180003644  xor     eax, eax
0x180003646  cmp     cs:?sm_pClrHostingHelper@FTPHOST_CLASS@@0PEAUIClrHostingHelper@@EA, rax; IClrHostingHelper * FTPHOST_CLASS::sm_pClrHostingHelper
0x18000364d  xorps   xmm0, xmm0
0x180003650  mov     r15, r9
0x180003653  mov     [rbp+var_30], rbx
0x180003657  mov     r12, r8
0x18000365a  mov     [rbp+var_8], rax
0x18000365e  mov     r14, rdx
0x180003661  mov     rdi, rcx
0x180003664  movups  [rbp+var_28], xmm0
0x180003668  movups  [rbp+var_18], xmm0
0x18000366c  jnz     short loc_18000367D
0x18000366e  call    ?LoadClrHost@FTPHOST_CLASS@@QEAAJXZ; FTPHOST_CLASS::LoadClrHost(void)
0x180003673  mov     ebx, eax
0x180003675  test    eax, eax
0x180003677  js      loc_180003708
0x18000367d  lea     rsi, [rdi+10h]
0x180003681  cmp     qword ptr [rsi], 0
0x180003685  jnz     loc_180003711
0x18000368b  lea     rcx, [rdi+18h]; SRWLock
0x18000368f  call    cs:__imp_AcquireSRWLockExclusive
0x180003695  cmp     qword ptr [rsi], 0
0x180003699  jnz     short loc_1800036C0
0x18000369b  mov     rcx, cs:?sm_pClrHostingHelper@FTPHOST_CLASS@@0PEAUIClrHostingHelper@@EA; IClrHostingHelper * FTPHOST_CLASS::sm_pClrHostingHelper
0x1800036a2  lea     r8, _GUID_45a7e15a_1386_459f_85b9_1e1e9e81219b
0x1800036a9  mov     r9, rsi
0x1800036ac  lea     rdx, aMicrosoftWebFt; "Microsoft.Web.FtpServer.Host.HostServic"...
0x1800036b3  mov     rax, [rcx]
0x1800036b6  mov     rax, [rax]
0x1800036b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036be  mov     ebx, eax
0x1800036c0  lea     rcx, [rdi+18h]; SRWLock
0x1800036c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800036ca  test    ebx, ebx
0x1800036cc  jns     short loc_180003711
0x1800036ce  test    cs:g_dwDebugFlags, 0Fh
0x1800036d5  jz      short loc_180003708
0x1800036d7  mov     rcx, cs:g_pDebug
0x1800036de  lea     rax, aFailedToInstan; "Failed to instantiate Microsoft.Web.Ftp"...
0x1800036e5  mov     [rsp+70h+var_48], rax
0x1800036ea  lea     r9, aFtphostClassGe; "FTPHOST_CLASS::GetManagedObject"
0x1800036f1  mov     r8d, 1E4h
0x1800036f7  mov     dword ptr [rsp+70h+var_50], ebx
0x1800036fb  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x180003702  call    cs:__imp_PuDbgPrintError
0x180003708  mov     rcx, [rbp+var_30]
0x18000370c  jmp     loc_1800037B2
0x180003711  mov     rax, [rbp+arg_20]
0x180003715  lea     rdx, [rbp+var_30]
0x180003719  mov     rcx, [rsi]
0x18000371c  lea     r8, [rbp+var_28]
0x180003720  mov     r9, [rbp+arg_38]
0x180003724  mov     qword ptr [rbp+var_18], rax
0x180003728  mov     rax, [rbp+arg_28]
0x18000372c  mov     qword ptr [rbp+var_18+8], rax
0x180003730  mov     rax, [rbp+arg_30]
0x180003734  mov     [rbp+var_8], rax
0x180003738  mov     qword ptr [rbp+var_28], r12
0x18000373c  mov     qword ptr [rbp+var_28+8], r15
0x180003740  mov     rax, [rcx]
0x180003743  mov     [rsp+70h+var_50], rdx
0x180003748  mov     rdx, r14
0x18000374b  mov     rax, [rax+18h]
0x18000374f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003754  mov     ebx, eax
0x180003756  test    eax, eax
0x180003758  jns     short loc_18000379E
0x18000375a  test    cs:g_dwDebugFlags, 0Fh
0x180003761  jz      short loc_180003708
0x180003763  mov     rcx, cs:g_pDebug
0x18000376a  lea     rax, aPftphostservic; "_pFtpHostService->GetHostedObject(%S) c"...
0x180003771  mov     [rsp+70h+var_40], r14
0x180003776  lea     r9, aFtphostClassGe; "FTPHOST_CLASS::GetManagedObject"
0x18000377d  mov     [rsp+70h+var_48], rax
0x180003782  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x180003789  mov     r8d, 1FAh
0x18000378f  mov     dword ptr [rsp+70h+var_50], ebx
0x180003793  call    cs:__imp_PuDbgPrintError
0x180003799  jmp     loc_180003708
0x18000379e  mov     rcx, [rbp+arg_40]
0x1800037a5  mov     rax, [rbp+var_30]
0x1800037a9  mov     [rcx], rax
0x1800037ac  xor     ecx, ecx
0x1800037ae  mov     [rbp+var_30], rcx
0x1800037b2  test    rcx, rcx
0x1800037b5  jz      short loc_1800037C3
0x1800037b7  mov     rax, [rcx]
0x1800037ba  mov     rax, [rax+10h]
0x1800037be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c3  mov     eax, ebx
0x1800037c5  add     rsp, 70h
0x1800037c9  pop     r15
0x1800037cb  pop     r14
0x1800037cd  pop     r12
0x1800037cf  pop     rdi
0x1800037d0  pop     rsi
0x1800037d1  pop     rbx
0x1800037d2  pop     rbp
0x1800037d3  retn
```
