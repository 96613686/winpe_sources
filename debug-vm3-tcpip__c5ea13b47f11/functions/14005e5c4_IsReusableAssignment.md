# IsReusableAssignment

- ea: `0x14005e5c4`
- end: `0x14005e90c`
- name: `IsReusableAssignment`
- size: `840`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, __int64, __int16, __int64, PKLOCK_QUEUE_HANDLE LockHandle)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005c164`
- `0x14005d1f0`

## callees

- `0x14005e5c4`
- `0x14005e920`
- `0x14005e94c`
- `0x14005e9cc`
- `0x1401bf4d0`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14005e849`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14005e849`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14005e830`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14005e830`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14005e820`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14005e820`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x14005e810`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x14005e810`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005e892`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005e892`
- `ntoskrnl!SeAccessCheck` at `0x14005e8d5`
- `ntoskrnl!SeAccessCheck` at `0x14005e8d5`
- `ntoskrnl!SeLockSubjectContext` at `0x14005e744`
- `ntoskrnl!SeLockSubjectContext` at `0x14005e744`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14005e734`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14005e734`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e6a7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e6a7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e776`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e78d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e7bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e776`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e78d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e7bb`

## pseudocode

```c
__int64 __fastcall IsReusableAssignment(
        __int64 a1,
        __int64 a2,
        int *a3,
        unsigned int a4,
        int a5,
        struct _KPROCESS *a6,
        struct _KTHREAD *a7,
        unsigned __int16 a8,
        __int64 a9,
        PKLOCK_QUEUE_HANDLE LockHandle)
{
  int v12; // eax
  __int64 i; // rbx
  char v14; // di
  unsigned __int64 v15; // rbx
  __int64 v16; // rsi
  int v17; // ecx
  __int64 v18; // rdx
  void *v19; // rdi
  BOOLEAN v20; // si
  __int64 result; // rax
  struct _GENERIC_MAPPING *GenericMapping; // rax
  int AccessStatus; // [rsp+48h] [rbp-B8h]
  _BYTE v24[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v25; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  PEPROCESS Process; // [rsp+80h] [rbp-80h]
  PETHREAD Thread; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING v34; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING v35; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t pszDest[16]; // [rsp+E8h] [rbp-18h] BYREF

  Process = a6;
  Thread = a7;
  v29 = a9;
  v12 = *a3;
  v28 = a4;
  v32 = a2;
  if ( (v12 & 1) != 0 )
    return 3221225506LL;
  if ( (a5 & 0x10) == 0 )
  {
    for ( i = *((_QWORD *)a3 + 2); i; i = *(_QWORD *)v15 )
    {
      v27 = -1073741802;
      v25 = 0;
      v14 = i & 3;
      if ( (i & 3) != 0 )
      {
        v15 = i & 0xFFFFFFFFFFFFFFFCuLL;
        LOBYTE(a2) = v14;
        v16 = (*(__int64 (__fastcall **)(unsigned __int64, __int64, unsigned __int16 *))(a1 + 112))(v15, a2, &v25);
        if ( v16 != -1 )
        {
          v17 = *(_DWORD *)(v15 + 16);
          if ( (v17 & 2) == 0 && ((v17 & 1) == 0 || (a5 & 2) == 0) )
          {
            KeReleaseInStackQueuedSpinLock(LockHandle);
            LOBYTE(v18) = v14;
            v19 = (void *)(*(__int64 (__fastcall **)(unsigned __int64, __int64))(a1 + 120))(v15, v18);
            v27 = CheckAddressesForPortReusability(a5, *a3 & 0x1F, a8, v25, v29, v16, (__int64)v19);
            if ( (a5 & 0x80u) == 0 )
            {
              v20 = 0;
              GrantedAccess = 0;
              memset(&SubjectContext, 0, sizeof(SubjectContext));
              v24[0] = 0;
              DestinationString = 0;
              v34 = 0;
              v35 = 0;
              SeCaptureSubjectContextEx(Thread, Process, &SubjectContext);
              SeLockSubjectContext(&SubjectContext);
              if ( v27 == 259 )
              {
                GenericMapping = IoGetFileObjectGenericMapping();
                v20 = SeAccessCheck(v19, &SubjectContext, 1u, 3u, 0, 0, GenericMapping, 1, &GrantedAccess, &v27);
              }
              else if ( v27 >= 0 )
              {
                v20 = 1;
                GrantedAccess = 3;
              }
              else
              {
                GrantedAccess = 0;
              }
              RtlInitUnicodeString(&DestinationString, L"TCP/IP");
              RtlInitUnicodeString(&v35, L"InternetPort");
              RtlStringCbPrintfW(pszDest, 0x20u, L"Port %u", v28);
              RtlInitUnicodeString(&v34, pszDest);
              if ( v19 )
              {
                LOBYTE(AccessStatus) = v20;
                SeOpenObjectAuditAlarmForNonObObject(
                  &DestinationString,
                  0,
                  &v35,
                  &v34,
                  v19,
                  &SubjectContext,
                  3,
                  GrantedAccess,
                  0,
                  AccessStatus,
                  v24);
              }
              SeUnlockSubjectContext(&SubjectContext);
              SeReleaseSubjectContext(&SubjectContext);
            }
            if ( v19 )
              ObDereferenceSecurityDescriptor(v19, 1);
            RtlAcquireWriteLock(v32, LockHandle);
            result = (unsigned int)v27;
            if ( v27 < 0 )
              return result;
          }
        }
      }
      else
      {
        v15 = i & 0xFFFFFFFFFFFFFFFCuLL;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14005e5c4  push    rbp
0x14005e5c6  push    rbx
0x14005e5c7  push    rsi
0x14005e5c8  push    rdi
0x14005e5c9  push    r12
0x14005e5cb  push    r13
0x14005e5cd  push    r15
0x14005e5cf  lea     rbp, [rsp-10h]
0x14005e5d4  sub     rsp, 110h
0x14005e5db  mov     rax, cs:__security_cookie
0x14005e5e2  xor     rax, rsp
0x14005e5e5  mov     [rbp+40h+var_38], rax
0x14005e5e9  mov     rax, [rbp+40h+arg_28]
0x14005e5ed  mov     r15, r8
0x14005e5f0  mov     r12, [rbp+40h+LockHandle]
0x14005e5f7  mov     r13, rcx
0x14005e5fa  mov     [rbp+40h+Process], rax
0x14005e5fe  mov     rax, [rbp+40h+arg_30]
0x14005e605  mov     [rbp+40h+Thread], rax
0x14005e609  mov     rax, [rbp+40h+arg_40]
0x14005e610  mov     [rsp+140h+var_C8], rax
0x14005e615  mov     eax, [r8]
0x14005e618  mov     [rsp+140h+var_D0], r9d
0x14005e61d  mov     [rbp+40h+var_B0], rdx
0x14005e621  test    al, 1
0x14005e623  jnz     loc_14005E8F9
0x14005e629  test    byte ptr [rbp+40h+arg_20], 10h
0x14005e62d  jnz     loc_14005E871
0x14005e633  mov     rbx, [r8+10h]
0x14005e637  test    rbx, rbx
0x14005e63a  jz      loc_14005E871
0x14005e640  xor     eax, eax
0x14005e642  mov     [rsp+140h+var_D4], 0C0000016h
0x14005e64a  mov     dil, bl
0x14005e64d  mov     [rsp+140h+var_DC], ax
0x14005e652  and     dil, 3
0x14005e656  jz      loc_14005E903
0x14005e65c  mov     rax, [r13+70h]
0x14005e660  lea     r8, [rsp+140h+var_DC]
0x14005e665  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14005e669  mov     dl, dil
0x14005e66c  mov     rcx, rbx
0x14005e66f  call    _guard_dispatch_icall
0x14005e674  mov     rsi, rax
0x14005e677  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005e67b  jz      loc_14005E869
0x14005e681  mov     ecx, [rbx+10h]
0x14005e684  test    cl, 2
0x14005e687  jnz     loc_14005E869
0x14005e68d  test    cl, 1
0x14005e690  setnz   r8b
0x14005e694  test    byte ptr [rbp+40h+arg_20], 2
0x14005e698  setnz   cl
0x14005e69b  test    cl, r8b
0x14005e69e  jnz     loc_14005E869
0x14005e6a4  mov     rcx, r12; LockHandle
0x14005e6a7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e6ae  nop     dword ptr [rax+rax+00h]
0x14005e6b3  mov     rax, [r13+78h]
0x14005e6b7  mov     dl, dil
0x14005e6ba  mov     rcx, rbx
0x14005e6bd  call    _guard_dispatch_icall
0x14005e6c2  mov     edx, [r15]
0x14005e6c5  mov     rdi, rax
0x14005e6c8  movzx   r9d, [rsp+140h+var_DC]
0x14005e6ce  and     edx, 1Fh
0x14005e6d1  movzx   r8d, [rbp+40h+arg_38]
0x14005e6d9  mov     ecx, [rbp+40h+arg_20]
0x14005e6dc  mov     [rsp+140h+GenericMapping], rax
0x14005e6e1  mov     rax, [rsp+140h+var_C8]
0x14005e6e6  mov     [rsp+140h+Privileges], rsi
0x14005e6eb  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax
0x14005e6f0  call    CheckAddressesForPortReusability
0x14005e6f5  test    byte ptr [rbp+40h+arg_20], 80h
0x14005e6f9  mov     [rsp+140h+var_D4], eax
0x14005e6fd  jnz     loc_14005E83C
0x14005e703  mov     rdx, [rbp+40h+Process]; Process
0x14005e707  lea     r8, [rbp+40h+SubjectContext]; SubjectContext
0x14005e70b  mov     rcx, [rbp+40h+Thread]; Thread
0x14005e70f  xorps   xmm0, xmm0
0x14005e712  xor     esi, esi
0x14005e714  xorps   xmm1, xmm1
0x14005e717  mov     [rsp+140h+var_D8], esi
0x14005e71b  movups  xmmword ptr [rbp+40h+SubjectContext.ClientToken], xmm0
0x14005e71f  mov     [rsp+140h+var_E0], sil
0x14005e724  movups  xmmword ptr [rbp+40h+SubjectContext.PrimaryToken], xmm0
0x14005e728  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x14005e72c  movups  xmmword ptr [rbp+40h+var_88.Length], xmm1
0x14005e730  movups  xmmword ptr [rbp+40h+var_78.Length], xmm0
0x14005e734  call    cs:__imp_SeCaptureSubjectContextEx
0x14005e73b  nop     dword ptr [rax+rax+00h]
0x14005e740  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x14005e744  call    cs:__imp_SeLockSubjectContext
0x14005e74b  nop     dword ptr [rax+rax+00h]
0x14005e750  mov     eax, [rsp+140h+var_D4]
0x14005e754  cmp     eax, 103h
0x14005e759  jz      loc_14005E892
0x14005e75f  test    eax, eax
0x14005e761  jns     loc_14005E8E9
0x14005e767  mov     [rsp+140h+var_D8], esi
0x14005e76b  lea     rdx, SourceString; "TCP/IP"
0x14005e772  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x14005e776  call    cs:__imp_RtlInitUnicodeString
0x14005e77d  nop     dword ptr [rax+rax+00h]
0x14005e782  lea     rdx, aInternetport; "InternetPort"
0x14005e789  lea     rcx, [rbp+40h+var_78]; DestinationString
0x14005e78d  call    cs:__imp_RtlInitUnicodeString
0x14005e794  nop     dword ptr [rax+rax+00h]
0x14005e799  mov     r9d, [rsp+140h+var_D0]
0x14005e79e  lea     r8, aPortU; "Port %u"
0x14005e7a5  mov     edx, 20h ; ' '; cbDest
0x14005e7aa  lea     rcx, [rbp+40h+pszDest]; pszDest
0x14005e7ae  call    RtlStringCbPrintfW
0x14005e7b3  lea     rdx, [rbp+40h+pszDest]; SourceString
0x14005e7b7  lea     rcx, [rbp+40h+var_88]; DestinationString
0x14005e7bb  call    cs:__imp_RtlInitUnicodeString
0x14005e7c2  nop     dword ptr [rax+rax+00h]
0x14005e7c7  test    rdi, rdi
0x14005e7ca  jz      short loc_14005E81C
0x14005e7cc  lea     rax, [rsp+140h+var_E0]
0x14005e7d1  xor     edx, edx
0x14005e7d3  mov     [rsp+140h+var_F0], rax
0x14005e7d8  lea     r9, [rbp+40h+var_88]
0x14005e7dc  mov     eax, [rsp+140h+var_D8]
0x14005e7e0  lea     r8, [rbp+40h+var_78]
0x14005e7e4  mov     byte ptr [rsp+140h+AccessStatus], sil
0x14005e7e9  lea     rcx, [rbp+40h+DestinationString]
0x14005e7ed  mov     [rsp+140h+GrantedAccess], 0
0x14005e7f6  mov     dword ptr [rsp+140h+AccessMode], eax
0x14005e7fa  lea     rax, [rbp+40h+SubjectContext]
0x14005e7fe  mov     dword ptr [rsp+140h+GenericMapping], 3
0x14005e806  mov     [rsp+140h+Privileges], rax
0x14005e80b  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rdi
0x14005e810  call    cs:__imp_SeOpenObjectAuditAlarmForNonObObject
0x14005e817  nop     dword ptr [rax+rax+00h]
0x14005e81c  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x14005e820  call    cs:__imp_SeUnlockSubjectContext
0x14005e827  nop     dword ptr [rax+rax+00h]
0x14005e82c  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x14005e830  call    cs:__imp_SeReleaseSubjectContext
0x14005e837  nop     dword ptr [rax+rax+00h]
0x14005e83c  test    rdi, rdi
0x14005e83f  jz      short loc_14005E855
0x14005e841  mov     edx, 1
0x14005e846  mov     rcx, rdi
0x14005e849  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14005e850  nop     dword ptr [rax+rax+00h]
0x14005e855  mov     rcx, [rbp+40h+var_B0]
0x14005e859  mov     rdx, r12
0x14005e85c  call    RtlAcquireWriteLock
0x14005e861  mov     eax, [rsp+140h+var_D4]
0x14005e865  test    eax, eax
0x14005e867  js      short loc_14005E873
0x14005e869  mov     rbx, [rbx]
0x14005e86c  jmp     loc_14005E637
0x14005e871  xor     eax, eax
0x14005e873  mov     rcx, [rbp+40h+var_38]
0x14005e877  xor     rcx, rsp; StackCookie
0x14005e87a  call    __security_check_cookie
0x14005e87f  add     rsp, 110h
0x14005e886  pop     r15
0x14005e888  pop     r13
0x14005e88a  pop     r12
0x14005e88c  pop     rdi
0x14005e88d  pop     rsi
0x14005e88e  pop     rbx
0x14005e88f  pop     rbp
0x14005e890  retn
0x14005e892  call    cs:__imp_IoGetFileObjectGenericMapping
0x14005e899  nop     dword ptr [rax+rax+00h]
0x14005e89e  lea     rcx, [rsp+140h+var_D4]
0x14005e8a3  mov     r9d, 3; DesiredAccess
0x14005e8a9  mov     [rsp+140h+AccessStatus], rcx; AccessStatus
0x14005e8ae  lea     rdx, [rbp+40h+SubjectContext]; SubjectSecurityContext
0x14005e8b2  lea     rcx, [rsp+140h+var_D8]
0x14005e8b7  mov     r8b, 1; SubjectContextLocked
0x14005e8ba  mov     [rsp+140h+GrantedAccess], rcx; GrantedAccess
0x14005e8bf  mov     rcx, rdi; SecurityDescriptor
0x14005e8c2  mov     [rsp+140h+AccessMode], 1; AccessMode
0x14005e8c7  mov     [rsp+140h+GenericMapping], rax; GenericMapping
0x14005e8cc  mov     [rsp+140h+Privileges], rsi; Privileges
0x14005e8d1  mov     [rsp+140h+PreviouslyGrantedAccess], esi; PreviouslyGrantedAccess
0x14005e8d5  call    cs:__imp_SeAccessCheck
0x14005e8dc  nop     dword ptr [rax+rax+00h]
0x14005e8e1  mov     sil, al
0x14005e8e4  jmp     loc_14005E76B
0x14005e8e9  mov     sil, 1
0x14005e8ec  mov     [rsp+140h+var_D8], 3
0x14005e8f4  jmp     loc_14005E76B
0x14005e8f9  mov     eax, 0C0000022h
0x14005e8fe  jmp     loc_14005E873
0x14005e903  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14005e907  jmp     loc_14005E869
```
