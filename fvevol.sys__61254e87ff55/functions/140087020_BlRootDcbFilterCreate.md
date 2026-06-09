# BlRootDcbFilterCreate

- ea: `0x140087020`
- end: `0x1400871d3`
- name: `BlRootDcbFilterCreate`
- size: `435`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140087020`
- `0x1400871dc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400871bf`
- `ntoskrnl!IofCompleteRequest` at `0x1400871bf`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140087167`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140087167`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140087157`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140087157`
- `ntoskrnl!SeAccessCheck` at `0x140087145`
- `ntoskrnl!SeAccessCheck` at `0x140087145`
- `ntoskrnl!SeLockSubjectContext` at `0x1400870e6`
- `ntoskrnl!SeLockSubjectContext` at `0x1400870e6`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400870d6`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400870d6`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008707d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400870ff`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008707d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400870ff`
- `ntoskrnl!RtlMapGenericMask` at `0x140087090`
- `ntoskrnl!RtlMapGenericMask` at `0x140087090`

## pseudocode

```c
__int64 __fastcall BlRootDcbFilterCreate(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 RootDcb; // rax
  void **v5; // rdi
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  __int64 result; // rax
  KPROCESSOR_MODE AccessMode; // bl
  void *v9; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v11; // bl
  DWORD GrantedAccess; // [rsp+50h] [rbp-30h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+58h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+A8h] [rbp+28h] BYREF
  DWORD AccessMask; // [rsp+B8h] [rbp+38h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  AccessMask = 0;
  GrantedAccess = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AccessStatus = 0;
  AccessMask = *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16);
  RootDcb = BlGetRootDcb(a1);
  if ( RootDcb && (v5 = *(void ***)(RootDcb + 200)) != 0 )
  {
    FileObjectGenericMapping = IoGetFileObjectGenericMapping();
    RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
    if ( (AccessMask & 0x102) == 0 )
      return 3221225474LL;
    SeCaptureSubjectContext(&SubjectContext);
    SeLockSubjectContext(&SubjectContext);
    AccessMode = a2->RequestorMode;
    AccessStatus = -1073741790;
    v9 = *v5;
    GenericMapping = IoGetFileObjectGenericMapping();
    v11 = SeAccessCheck(
            v9,
            &SubjectContext,
            1u,
            AccessMask,
            0,
            0,
            GenericMapping,
            AccessMode,
            &GrantedAccess,
            &AccessStatus);
    SeUnlockSubjectContext(&SubjectContext);
    SeReleaseSubjectContext(&SubjectContext);
    result = (unsigned int)AccessStatus;
    if ( AccessStatus >= 0 )
    {
      if ( !v11 )
      {
        result = 3221225506LL;
        AccessStatus = -1073741790;
      }
      if ( (int)result >= 0 && v11 )
      {
        if ( (GrantedAccess & 0x102) != 0 )
          return 3221225474LL;
        LODWORD(result) = -1073741811;
        AccessStatus = -1073741811;
LABEL_16:
        a2->IoStatus.Information = 0;
        a2->IoStatus.Status = result;
        IofCompleteRequest(a2, 0);
        return (unsigned int)AccessStatus;
      }
    }
  }
  else
  {
    result = 3221225485LL;
    AccessStatus = -1073741811;
  }
  if ( (_DWORD)result != -1073741822 )
    goto LABEL_16;
  return result;
}

```

## disassembly

```asm
0x140087020  mov     [rsp-18h+arg_0], rbx
0x140087025  push    rbp
0x140087026  push    rsi
0x140087027  push    rdi
0x140087028  mov     rbp, rsp
0x14008702b  sub     rsp, 80h
0x140087032  mov     rax, [rdx+0B8h]
0x140087039  xorps   xmm0, xmm0
0x14008703c  mov     [rbp+AccessMask], 0
0x140087043  mov     rsi, rdx
0x140087046  mov     [rbp+var_30], 0
0x14008704d  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140087051  mov     [rbp+arg_8], 0
0x140087058  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14008705c  mov     r8, [rax+8]
0x140087060  mov     eax, [r8+10h]
0x140087064  mov     [rbp+AccessMask], eax
0x140087067  call    BlGetRootDcb
0x14008706c  test    rax, rax
0x14008706f  jz      short loc_1400870BE
0x140087071  mov     rdi, [rax+0C8h]
0x140087078  test    rdi, rdi
0x14008707b  jz      short loc_1400870BE
0x14008707d  call    cs:__imp_IoGetFileObjectGenericMapping
0x140087084  nop     dword ptr [rax+rax+00h]
0x140087089  mov     rdx, rax; GenericMapping
0x14008708c  lea     rcx, [rbp+AccessMask]; AccessMask
0x140087090  call    cs:__imp_RtlMapGenericMask
0x140087097  nop     dword ptr [rax+rax+00h]
0x14008709c  test    [rbp+AccessMask], 102h
0x1400870a3  jnz     short loc_1400870D2
0x1400870a5  mov     eax, 0C0000002h
0x1400870aa  mov     rbx, [rsp+80h+arg_0]
0x1400870b2  add     rsp, 80h
0x1400870b9  pop     rdi
0x1400870ba  pop     rsi
0x1400870bb  pop     rbp
0x1400870bc  retn
0x1400870be  mov     eax, 0C000000Dh
0x1400870c3  mov     [rbp+arg_8], eax
0x1400870c6  cmp     eax, 0C0000002h
0x1400870cb  jz      short loc_1400870AA
0x1400870cd  jmp     loc_1400871AF
0x1400870d2  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400870d6  call    cs:__imp_SeCaptureSubjectContext
0x1400870dd  nop     dword ptr [rax+rax+00h]
0x1400870e2  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400870e6  call    cs:__imp_SeLockSubjectContext
0x1400870ed  nop     dword ptr [rax+rax+00h]
0x1400870f2  mov     bl, [rsi+40h]
0x1400870f5  mov     [rbp+arg_8], 0C0000022h
0x1400870fc  mov     rdi, [rdi]
0x1400870ff  call    cs:__imp_IoGetFileObjectGenericMapping
0x140087106  nop     dword ptr [rax+rax+00h]
0x14008710b  mov     r9d, [rbp+AccessMask]; DesiredAccess
0x14008710f  lea     rcx, [rbp+arg_8]
0x140087113  mov     [rsp+80h+AccessStatus], rcx; AccessStatus
0x140087118  lea     rdx, [rbp+SubjectContext]; SubjectSecurityContext
0x14008711c  lea     rcx, [rbp+var_30]
0x140087120  mov     r8b, 1; SubjectContextLocked
0x140087123  mov     [rsp+80h+GrantedAccess], rcx; GrantedAccess
0x140087128  mov     rcx, rdi; SecurityDescriptor
0x14008712b  mov     [rsp+80h+AccessMode], bl; AccessMode
0x14008712f  mov     [rsp+80h+GenericMapping], rax; GenericMapping
0x140087134  mov     [rsp+80h+Privileges], 0; Privileges
0x14008713d  mov     [rsp+80h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140087145  call    cs:__imp_SeAccessCheck
0x14008714c  nop     dword ptr [rax+rax+00h]
0x140087151  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140087155  mov     bl, al
0x140087157  call    cs:__imp_SeUnlockSubjectContext
0x14008715e  nop     dword ptr [rax+rax+00h]
0x140087163  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140087167  call    cs:__imp_SeReleaseSubjectContext
0x14008716e  nop     dword ptr [rax+rax+00h]
0x140087173  mov     eax, [rbp+arg_8]
0x140087176  test    eax, eax
0x140087178  js      loc_1400870C6
0x14008717e  test    bl, bl
0x140087180  jnz     short loc_14008718A
0x140087182  mov     eax, 0C0000022h
0x140087187  mov     [rbp+arg_8], eax
0x14008718a  test    eax, eax
0x14008718c  js      loc_1400870C6
0x140087192  test    bl, bl
0x140087194  jz      loc_1400870C6
0x14008719a  test    [rbp+var_30], 102h
0x1400871a1  jnz     loc_1400870A5
0x1400871a7  mov     eax, 0C000000Dh
0x1400871ac  mov     [rbp+arg_8], eax
0x1400871af  xor     edx, edx; PriorityBoost
0x1400871b1  mov     qword ptr [rsi+38h], 0
0x1400871b9  mov     rcx, rsi; Irp
0x1400871bc  mov     [rsi+30h], eax
0x1400871bf  call    cs:__imp_IofCompleteRequest
0x1400871c6  nop     dword ptr [rax+rax+00h]
0x1400871cb  mov     eax, [rbp+arg_8]
0x1400871ce  jmp     loc_1400870AA
```
