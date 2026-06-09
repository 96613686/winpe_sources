# BlRootDcbFilterCreate

- ea: `0x140084f80`
- end: `0x140085133`
- name: `BlRootDcbFilterCreate`
- size: `435`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140084f80`
- `0x14008513c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008511f`
- `ntoskrnl!IofCompleteRequest` at `0x14008511f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400850c7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400850c7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400850b7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400850b7`
- `ntoskrnl!SeAccessCheck` at `0x1400850a5`
- `ntoskrnl!SeAccessCheck` at `0x1400850a5`
- `ntoskrnl!SeLockSubjectContext` at `0x140085046`
- `ntoskrnl!SeLockSubjectContext` at `0x140085046`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140085036`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140085036`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140084fdd`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008505f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140084fdd`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008505f`
- `ntoskrnl!RtlMapGenericMask` at `0x140084ff0`
- `ntoskrnl!RtlMapGenericMask` at `0x140084ff0`

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
0x140084f80  mov     [rsp-18h+arg_0], rbx
0x140084f85  push    rbp
0x140084f86  push    rsi
0x140084f87  push    rdi
0x140084f88  mov     rbp, rsp
0x140084f8b  sub     rsp, 80h
0x140084f92  mov     rax, [rdx+0B8h]
0x140084f99  xorps   xmm0, xmm0
0x140084f9c  mov     [rbp+AccessMask], 0
0x140084fa3  mov     rsi, rdx
0x140084fa6  mov     [rbp+var_30], 0
0x140084fad  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140084fb1  mov     [rbp+arg_8], 0
0x140084fb8  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140084fbc  mov     r8, [rax+8]
0x140084fc0  mov     eax, [r8+10h]
0x140084fc4  mov     [rbp+AccessMask], eax
0x140084fc7  call    BlGetRootDcb
0x140084fcc  test    rax, rax
0x140084fcf  jz      short loc_14008501E
0x140084fd1  mov     rdi, [rax+0C8h]
0x140084fd8  test    rdi, rdi
0x140084fdb  jz      short loc_14008501E
0x140084fdd  call    cs:__imp_IoGetFileObjectGenericMapping
0x140084fe4  nop     dword ptr [rax+rax+00h]
0x140084fe9  mov     rdx, rax; GenericMapping
0x140084fec  lea     rcx, [rbp+AccessMask]; AccessMask
0x140084ff0  call    cs:__imp_RtlMapGenericMask
0x140084ff7  nop     dword ptr [rax+rax+00h]
0x140084ffc  test    [rbp+AccessMask], 102h
0x140085003  jnz     short loc_140085032
0x140085005  mov     eax, 0C0000002h
0x14008500a  mov     rbx, [rsp+80h+arg_0]
0x140085012  add     rsp, 80h
0x140085019  pop     rdi
0x14008501a  pop     rsi
0x14008501b  pop     rbp
0x14008501c  retn
0x14008501e  mov     eax, 0C000000Dh
0x140085023  mov     [rbp+arg_8], eax
0x140085026  cmp     eax, 0C0000002h
0x14008502b  jz      short loc_14008500A
0x14008502d  jmp     loc_14008510F
0x140085032  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140085036  call    cs:__imp_SeCaptureSubjectContext
0x14008503d  nop     dword ptr [rax+rax+00h]
0x140085042  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140085046  call    cs:__imp_SeLockSubjectContext
0x14008504d  nop     dword ptr [rax+rax+00h]
0x140085052  mov     bl, [rsi+40h]
0x140085055  mov     [rbp+arg_8], 0C0000022h
0x14008505c  mov     rdi, [rdi]
0x14008505f  call    cs:__imp_IoGetFileObjectGenericMapping
0x140085066  nop     dword ptr [rax+rax+00h]
0x14008506b  mov     r9d, [rbp+AccessMask]; DesiredAccess
0x14008506f  lea     rcx, [rbp+arg_8]
0x140085073  mov     [rsp+80h+AccessStatus], rcx; AccessStatus
0x140085078  lea     rdx, [rbp+SubjectContext]; SubjectSecurityContext
0x14008507c  lea     rcx, [rbp+var_30]
0x140085080  mov     r8b, 1; SubjectContextLocked
0x140085083  mov     [rsp+80h+GrantedAccess], rcx; GrantedAccess
0x140085088  mov     rcx, rdi; SecurityDescriptor
0x14008508b  mov     [rsp+80h+AccessMode], bl; AccessMode
0x14008508f  mov     [rsp+80h+GenericMapping], rax; GenericMapping
0x140085094  mov     [rsp+80h+Privileges], 0; Privileges
0x14008509d  mov     [rsp+80h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1400850a5  call    cs:__imp_SeAccessCheck
0x1400850ac  nop     dword ptr [rax+rax+00h]
0x1400850b1  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400850b5  mov     bl, al
0x1400850b7  call    cs:__imp_SeUnlockSubjectContext
0x1400850be  nop     dword ptr [rax+rax+00h]
0x1400850c3  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400850c7  call    cs:__imp_SeReleaseSubjectContext
0x1400850ce  nop     dword ptr [rax+rax+00h]
0x1400850d3  mov     eax, [rbp+arg_8]
0x1400850d6  test    eax, eax
0x1400850d8  js      loc_140085026
0x1400850de  test    bl, bl
0x1400850e0  jnz     short loc_1400850EA
0x1400850e2  mov     eax, 0C0000022h
0x1400850e7  mov     [rbp+arg_8], eax
0x1400850ea  test    eax, eax
0x1400850ec  js      loc_140085026
0x1400850f2  test    bl, bl
0x1400850f4  jz      loc_140085026
0x1400850fa  test    [rbp+var_30], 102h
0x140085101  jnz     loc_140085005
0x140085107  mov     eax, 0C000000Dh
0x14008510c  mov     [rbp+arg_8], eax
0x14008510f  xor     edx, edx; PriorityBoost
0x140085111  mov     qword ptr [rsi+38h], 0
0x140085119  mov     rcx, rsi; Irp
0x14008511c  mov     [rsi+30h], eax
0x14008511f  call    cs:__imp_IofCompleteRequest
0x140085126  nop     dword ptr [rax+rax+00h]
0x14008512b  mov     eax, [rbp+arg_8]
0x14008512e  jmp     loc_14008500A
```
