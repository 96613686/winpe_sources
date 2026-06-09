# FltEnlistInTransaction

- ea: `0x180055570`
- end: `0x180055835`
- name: `FltEnlistInTransaction`
- size: `709`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance, PKTRANSACTION Transaction, PFLT_CONTEXT TransactionContext, NOTIFICATION_MASK NotificationMask)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x180010f30`
- `0x1800183b0`
- `0x180055570`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180055795`
- `ntoskrnl!ObfDereferenceObject` at `0x180055795`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180055613`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180055613`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180055758`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800557c3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180055758`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800557c3`
- `ntoskrnl!ZwClose` at `0x180055780`
- `ntoskrnl!ZwClose` at `0x180055780`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x180055770`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x180055770`
- `ntoskrnl!TmCreateEnlistment` at `0x1800556c5`
- `ntoskrnl!TmCreateEnlistment` at `0x1800556c5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005570e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005570e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180055625`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180055625`
- `ntoskrnl!ExReleasePushLockEx` at `0x18005574c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1800557b7`
- `ntoskrnl!ExReleasePushLockEx` at `0x18005574c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1800557b7`

## pseudocode

```c
NTSTATUS __stdcall FltEnlistInTransaction(
        PFLT_INSTANCE Instance,
        PKTRANSACTION Transaction,
        PFLT_CONTEXT TransactionContext,
        NOTIFICATION_MASK NotificationMask)
{
  __int64 v9; // rbx
  _FLT_FILTER *Filter; // r13
  char *v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  void *EnlistmentHandle; // [rsp+50h] [rbp-29h] BYREF
  PVOID Object; // [rsp+58h] [rbp-21h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF

  Object = 0;
  EnlistmentHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (NotificationMask & 0xBFFFFFF0) != 0 )
    return -1073741582;
  LODWORD(v9) = FltObjectReference(Instance);
  if ( (int)FltpDbgStatus((unsigned int)v9, "minkernel\\fs\\filtermgr\\filter\\transsup.c", 585, 3223060491LL) >= 0 )
  {
    Filter = Instance->Filter;
    v11 = (char *)TransactionContext - 96;
    if ( Filter->KtmNotification )
    {
      v12 = *(_QWORD *)v11;
      KeEnterGuardedRegion();
      ExAcquirePushLockExclusiveEx(v12 + 64, 0);
      if ( *(_QWORD *)(*(_QWORD *)v11 + 8LL) == -1 )
      {
        *(_QWORD *)(*(_QWORD *)v11 + 8LL) = -3;
        v13 = *(_QWORD *)v11;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 512;
        ObjectAttributes.ObjectName = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        *(_DWORD *)(v13 + 16) = NotificationMask;
        FltReferenceContext(TransactionContext);
        v9 = (unsigned int)TmCreateEnlistment(
                             &EnlistmentHandle,
                             0,
                             0xF001Fu,
                             &ObjectAttributes,
                             Filter->Frame->KtmResourceManager,
                             Transaction,
                             0,
                             NotificationMask & 0xBFFFFFF3 | 0xC,
                             (char *)TransactionContext - 96);
        if ( (int)FltpDbgStatus(v9, "minkernel\\fs\\filtermgr\\filter\\transsup.c", 696, 0) >= 0 )
        {
          v9 = (unsigned int)ObReferenceObjectByHandle(EnlistmentHandle, 0, 0, 0, &Object, 0);
          if ( (int)FltpDbgStatus(v9, "minkernel\\fs\\filtermgr\\filter\\transsup.c", 732, 0) >= 0 )
          {
            *(_QWORD *)(*(_QWORD *)v11 + 8LL) = Object;
            ExReleasePushLockEx(*(_QWORD *)v11 + 64LL, 0);
            KeLeaveGuardedRegion();
            **(_QWORD **)v11 = EnlistmentHandle;
            EnlistmentHandle = 0;
            Object = 0;
LABEL_19:
            if ( (int)FltpDbgStatus((unsigned int)v9, "minkernel\\fs\\filtermgr\\filter\\transsup.c", 817, 0) < 0
              && (_DWORD)v9 != -1071906789
              && *(_QWORD *)(*(_QWORD *)v11 + 8LL) == -3 )
            {
              *(_QWORD *)(*(_QWORD *)v11 + 8LL) = -1;
            }
            FltObjectDereference(Instance);
            return v9;
          }
          Object = 0;
        }
        else
        {
          EnlistmentHandle = 0;
        }
        FltReleaseContext(TransactionContext);
      }
      else
      {
        LODWORD(v9) = -1071906789;
      }
      ExReleasePushLockEx(*(_QWORD *)v11 + 64LL, 0);
      KeLeaveGuardedRegion();
    }
    else
    {
      LODWORD(v9) = -1073741811;
    }
    if ( EnlistmentHandle )
    {
      TmReadOnlyEnlistment((PKENLISTMENT)Object, 0);
      ZwClose(EnlistmentHandle);
    }
    if ( Object )
      ObfDereferenceObject(Object);
    goto LABEL_19;
  }
  return v9;
}

```

## disassembly

```asm
0x180055570  push    rbp
0x180055572  push    rbx
0x180055573  push    rsi
0x180055574  push    rdi
0x180055575  push    r12
0x180055577  push    r13
0x180055579  push    r14
0x18005557b  push    r15
0x18005557d  lea     rbp, [rsp-1Fh]
0x180055582  sub     rsp, 98h
0x180055589  xor     edi, edi
0x18005558b  xorps   xmm0, xmm0
0x18005558e  xor     eax, eax
0x180055590  mov     [rbp+57h+Object], rdi
0x180055594  mov     [rbp+57h+EnlistmentHandle], rdi
0x180055598  mov     r15d, r9d
0x18005559b  mov     r14, r8
0x18005559e  mov     r12, rdx
0x1800555a1  mov     rsi, rcx
0x1800555a4  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800555a8  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800555ac  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800555b0  test    r9d, 0BFFFFFF0h
0x1800555b7  jz      short loc_1800555C3
0x1800555b9  mov     eax, 0C00000F2h
0x1800555be  jmp     loc_180055820
0x1800555c3  call    FltObjectReference
0x1800555c8  mov     r8d, 249h
0x1800555ce  mov     [rsp+0D0h+ResourceManager], rdi
0x1800555d3  mov     r9d, 0C01C000Bh
0x1800555d9  lea     rdx, aMinkernelFsFil_6; "minkernel\\fs\\filtermgr\\filter\\trans"...
0x1800555e0  mov     ecx, eax
0x1800555e2  mov     ebx, eax
0x1800555e4  call    FltpDbgStatus
0x1800555e9  test    eax, eax
0x1800555eb  js      loc_18005581E
0x1800555f1  mov     r13, [rsi+48h]
0x1800555f5  lea     rdi, [r14-60h]
0x1800555f9  cmp     qword ptr [r13+1A0h], 0
0x180055601  jnz     short loc_180055610
0x180055603  mov     ebx, 0C000000Dh
0x180055608  xor     r15d, r15d
0x18005560b  jmp     loc_180055764
0x180055610  mov     rbx, [rdi]
0x180055613  call    cs:__imp_KeEnterGuardedRegion
0x18005561a  nop     dword ptr [rax+rax+00h]
0x18005561f  xor     edx, edx
0x180055621  lea     rcx, [rbx+40h]
0x180055625  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x18005562c  nop     dword ptr [rax+rax+00h]
0x180055631  mov     rax, [rdi]
0x180055634  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180055639  jz      short loc_180055648
0x18005563b  mov     ebx, 0C01C001Bh
0x180055640  xor     r15d, r15d
0x180055643  jmp     loc_180055743
0x180055648  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFDh
0x180055650  xorps   xmm0, xmm0
0x180055653  mov     rax, [rdi]
0x180055656  mov     rcx, r14; Context
0x180055659  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180055660  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180055668  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x18005566f  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x180055677  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005567c  mov     [rax+10h], r15d
0x180055680  call    FltReferenceContext
0x180055685  mov     rax, [r13+38h]
0x180055689  lea     r9, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005568d  mov     [rsp+0D0h+EnlistmentKey], rdi; EnlistmentKey
0x180055692  lea     rcx, [rbp+57h+EnlistmentHandle]; EnlistmentHandle
0x180055696  btr     r15d, 1Eh
0x18005569b  xor     edx, edx; PreviousMode
0x18005569d  or      r15d, 0Ch
0x1800556a1  mov     r8d, 0F001Fh; DesiredAccess
0x1800556a7  mov     rax, [rax+200h]
0x1800556ae  mov     [rsp+0D0h+NotificationMask], r15d; NotificationMask
0x1800556b3  xor     r15d, r15d
0x1800556b6  mov     [rsp+0D0h+CreateOptions], r15d; CreateOptions
0x1800556bb  mov     [rsp+0D0h+Transaction], r12; Transaction
0x1800556c0  mov     [rsp+0D0h+ResourceManager], rax; ResourceManager
0x1800556c5  call    cs:__imp_TmCreateEnlistment
0x1800556cc  nop     dword ptr [rax+rax+00h]
0x1800556d1  mov     r8d, 2B8h
0x1800556d7  lea     rdx, aMinkernelFsFil_6; "minkernel\\fs\\filtermgr\\filter\\trans"...
0x1800556de  mov     ecx, eax
0x1800556e0  xor     r9d, r9d
0x1800556e3  mov     ebx, eax
0x1800556e5  call    FltpDbgStatus
0x1800556ea  test    eax, eax
0x1800556ec  jns     short loc_1800556F4
0x1800556ee  mov     [rbp+57h+EnlistmentHandle], r15
0x1800556f2  jmp     short loc_18005573B
0x1800556f4  mov     rcx, [rbp+57h+EnlistmentHandle]; Handle
0x1800556f8  lea     rax, [rbp+57h+Object]
0x1800556fc  mov     [rsp+0D0h+Transaction], r15; HandleInformation
0x180055701  xor     r9d, r9d; AccessMode
0x180055704  xor     r8d, r8d; ObjectType
0x180055707  mov     [rsp+0D0h+ResourceManager], rax; Object
0x18005570c  xor     edx, edx; DesiredAccess
0x18005570e  call    cs:__imp_ObReferenceObjectByHandle
0x180055715  nop     dword ptr [rax+rax+00h]
0x18005571a  mov     r8d, 2DCh
0x180055720  lea     rdx, aMinkernelFsFil_6; "minkernel\\fs\\filtermgr\\filter\\trans"...
0x180055727  mov     ecx, eax
0x180055729  xor     r9d, r9d
0x18005572c  mov     ebx, eax
0x18005572e  call    FltpDbgStatus
0x180055733  test    eax, eax
0x180055735  jns     short loc_1800557A3
0x180055737  mov     [rbp+57h+Object], r15
0x18005573b  mov     rcx, r14; Context
0x18005573e  call    FltReleaseContext
0x180055743  mov     rcx, [rdi]
0x180055746  xor     edx, edx
0x180055748  add     rcx, 40h ; '@'
0x18005574c  call    cs:__imp_ExReleasePushLockEx
0x180055753  nop     dword ptr [rax+rax+00h]
0x180055758  call    cs:__imp_KeLeaveGuardedRegion
0x18005575f  nop     dword ptr [rax+rax+00h]
0x180055764  cmp     [rbp+57h+EnlistmentHandle], r15
0x180055768  jz      short loc_18005578C
0x18005576a  mov     rcx, [rbp+57h+Object]; Enlistment
0x18005576e  xor     edx, edx; TmVirtualClock
0x180055770  call    cs:__imp_TmReadOnlyEnlistment
0x180055777  nop     dword ptr [rax+rax+00h]
0x18005577c  mov     rcx, [rbp+57h+EnlistmentHandle]; Handle
0x180055780  call    cs:__imp_ZwClose
0x180055787  nop     dword ptr [rax+rax+00h]
0x18005578c  mov     rcx, [rbp+57h+Object]; Object
0x180055790  test    rcx, rcx
0x180055793  jz      short loc_1800557E1
0x180055795  call    cs:__imp_ObfDereferenceObject
0x18005579c  nop     dword ptr [rax+rax+00h]
0x1800557a1  jmp     short loc_1800557E1
0x1800557a3  mov     rcx, [rdi]
0x1800557a6  xor     edx, edx
0x1800557a8  mov     rax, [rbp+57h+Object]
0x1800557ac  mov     [rcx+8], rax
0x1800557b0  mov     rcx, [rdi]
0x1800557b3  add     rcx, 40h ; '@'
0x1800557b7  call    cs:__imp_ExReleasePushLockEx
0x1800557be  nop     dword ptr [rax+rax+00h]
0x1800557c3  call    cs:__imp_KeLeaveGuardedRegion
0x1800557ca  nop     dword ptr [rax+rax+00h]
0x1800557cf  mov     rax, [rbp+57h+EnlistmentHandle]
0x1800557d3  mov     rcx, [rdi]
0x1800557d6  mov     [rcx], rax
0x1800557d9  mov     [rbp+57h+EnlistmentHandle], r15
0x1800557dd  mov     [rbp+57h+Object], r15
0x1800557e1  mov     r8d, 331h
0x1800557e7  lea     rdx, aMinkernelFsFil_6; "minkernel\\fs\\filtermgr\\filter\\trans"...
0x1800557ee  xor     r9d, r9d
0x1800557f1  mov     ecx, ebx
0x1800557f3  call    FltpDbgStatus
0x1800557f8  test    eax, eax
0x1800557fa  jns     short loc_180055816
0x1800557fc  cmp     ebx, 0C01C001Bh
0x180055802  jz      short loc_180055816
0x180055804  mov     rax, [rdi]
0x180055807  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFDh
0x18005580c  jnz     short loc_180055816
0x18005580e  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180055816  mov     rcx, rsi; FltObject
0x180055819  call    FltObjectDereference
0x18005581e  mov     eax, ebx
0x180055820  add     rsp, 98h
0x180055827  pop     r15
0x180055829  pop     r14
0x18005582b  pop     r13
0x18005582d  pop     r12
0x18005582f  pop     rdi
0x180055830  pop     rsi
0x180055831  pop     rbx
0x180055832  pop     rbp
0x180055833  retn
```
