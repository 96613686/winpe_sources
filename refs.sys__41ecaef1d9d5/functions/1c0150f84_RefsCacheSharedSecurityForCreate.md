# RefsCacheSharedSecurityForCreate

- ea: `0x1c0150f84`
- end: `0x1c0151127`
- name: `RefsCacheSharedSecurityForCreate`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c016752c`

## callees

- `0x1c000f770`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0150f84`
- `0x1c0151410`
- `0x1c016aad0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c017ddb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0181974`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017ddb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0181974`
- `ntoskrnl!IoFileObjectType` at `0x1c0150ff5`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c0150fd3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c0150fd3`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c015105e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c015105e`
- `ntoskrnl!SeAssignSecurityEx` at `0x1c0151040`
- `ntoskrnl!SeAssignSecurityEx` at `0x1c0151040`
- `ntoskrnl!SeComputeAutoInheritByObjectType` at `0x1c0150fff`
- `ntoskrnl!SeComputeAutoInheritByObjectType` at `0x1c0150fff`

## pseudocode

```c
__int64 __fastcall RefsCacheSharedSecurityForCreate(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  BOOLEAN IsDirectoryObject; // r12
  __int64 v6; // r15
  struct _GENERIC_MAPPING *GenericMapping; // rbx
  ULONG AutoInheritFlags; // eax
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  ULONG v11; // eax
  __int64 v12; // r9
  __int64 v13; // rsi
  PSECURITY_DESCRIPTOR v14; // rdi
  __int64 v15; // rbx
  void *v16; // rcx
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+80h] [rbp+8h] BYREF
  __int64 v19; // [rsp+88h] [rbp+10h]

  NewDescriptor = 0;
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 184LL);
  IsDirectoryObject = *(_BYTE *)(v4 + 16) & 1;
  v6 = *(_QWORD *)(*(_QWORD *)(v4 + 8) + 8LL);
  v19 = v6;
  if ( !*(_QWORD *)(a2 + 184) )
    RefsLoadSecurityDescriptor(a1, a2);
  GenericMapping = IoGetFileObjectGenericMapping();
  AutoInheritFlags = SeComputeAutoInheritByObjectType(
                       IoFileObjectType,
                       *(PSECURITY_DESCRIPTOR *)(v6 + 64),
                       (PSECURITY_DESCRIPTOR)(*(_QWORD *)(a2 + 184) + 20LL));
  v9 = SeAssignSecurityEx(
         (PSECURITY_DESCRIPTOR)(*(_QWORD *)(a2 + 184) + 20LL),
         *(PSECURITY_DESCRIPTOR *)(v6 + 64),
         &NewDescriptor,
         0,
         IsDirectoryObject,
         AutoInheritFlags,
         (PSECURITY_SUBJECT_CONTEXT)(v6 + 32),
         GenericMapping,
         PagedPool);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_838d735f45793e0c3968f803c105c9c3_Traceguids,
        (unsigned int)v9);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(v10);
    RefsRaiseStatusInternal(a1, v10);
    __debugbreak();
  }
  v11 = RtlLengthSecurityDescriptor(NewDescriptor);
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    v11 = RefsRaiseStatusInternal(a1, 3221225485LL);
  }
  LOBYTE(v12) = 1;
  v13 = RefsCacheSharedSecurityByDescriptor(a1, NewDescriptor, v11, v12);
  v14 = NewDescriptor;
  v15 = *(_QWORD *)(v6 + 72);
  v16 = *(void **)(v15 + 48);
  if ( v16 )
    ExFreePoolWithTag(v16, 0);
  *(_QWORD *)(v15 + 48) = v14;
  return v13;
}

```

## disassembly

```asm
0x1c0150f84  mov     rax, rsp
0x1c0150f87  mov     [rax+18h], rbx
0x1c0150f8b  push    rsi
0x1c0150f8c  push    rdi
0x1c0150f8d  push    r12
0x1c0150f8f  push    r14
0x1c0150f91  push    r15
0x1c0150f93  sub     rsp, 50h
0x1c0150f97  mov     r14, rdx
0x1c0150f9a  mov     rsi, rcx
0x1c0150f9d  and     qword ptr [rax+8], 0
0x1c0150fa2  mov     rax, [rcx+48h]
0x1c0150fa6  mov     rax, [rax+0B8h]
0x1c0150fad  mov     r12b, [rax+10h]
0x1c0150fb1  and     r12b, 1
0x1c0150fb5  mov     rax, [rax+8]
0x1c0150fb9  mov     r15, [rax+8]
0x1c0150fbd  mov     [rsp+78h+arg_8], r15
0x1c0150fc5  cmp     qword ptr [rdx+0B8h], 0
0x1c0150fcd  jz      loc_1C0181904
0x1c0150fd3  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c0150fda  nop     dword ptr [rax+rax+00h]
0x1c0150fdf  mov     rbx, rax
0x1c0150fe2  lea     rdi, [r15+20h]
0x1c0150fe6  mov     r8, [r14+0B8h]
0x1c0150fed  add     r8, 14h; ParentSecurityDescriptor
0x1c0150ff1  mov     rdx, [r15+40h]; SecurityDescriptor
0x1c0150ff5  mov     rcx, cs:__imp_IoFileObjectType
0x1c0150ffc  mov     rcx, [rcx]; ObjectType
0x1c0150fff  call    cs:__imp_SeComputeAutoInheritByObjectType
0x1c0151006  nop     dword ptr [rax+rax+00h]
0x1c015100b  mov     rcx, [r14+0B8h]
0x1c0151012  add     rcx, 14h; ParentDescriptor
0x1c0151016  mov     [rsp+78h+PoolType], 1; PoolType
0x1c015101e  mov     [rsp+78h+GenericMapping], rbx; GenericMapping
0x1c0151023  mov     [rsp+78h+SubjectContext], rdi; SubjectContext
0x1c0151028  mov     [rsp+78h+AutoInheritFlags], eax; AutoInheritFlags
0x1c015102c  mov     [rsp+78h+IsDirectoryObject], r12b; IsDirectoryObject
0x1c0151031  xor     r9d, r9d; ObjectType
0x1c0151034  lea     r8, [rsp+78h+NewDescriptor]; NewDescriptor
0x1c015103c  mov     rdx, [r15+40h]; ExplicitDescriptor
0x1c0151040  call    cs:__imp_SeAssignSecurityEx
0x1c0151047  nop     dword ptr [rax+rax+00h]
0x1c015104c  mov     ebx, eax
0x1c015104e  test    eax, eax
0x1c0151050  js      loc_1C018190F
0x1c0151056  mov     rcx, [rsp+78h+NewDescriptor]; SecurityDescriptor
0x1c015105e  call    cs:__imp_RtlLengthSecurityDescriptor
0x1c0151065  nop     dword ptr [rax+rax+00h]
0x1c015106a  nop
0x1c015106b  test    eax, eax
0x1c015106d  jnz     short loc_1C01510D8
0x1c015106f  lea     rdx, WPP_GLOBAL_Control
0x1c0151076  mov     rcx, cs:WPP_GLOBAL_Control
0x1c015107d  cmp     rcx, rdx
0x1c0151080  jz      short loc_1C01510AA
0x1c0151082  test    dword ptr [rcx+2Ch], 100h
0x1c0151089  jz      short loc_1C01510AA
0x1c015108b  cmp     byte ptr [rcx+29h], 4
0x1c015108f  jb      short loc_1C01510AA
0x1c0151091  lea     edx, [rax+20h]
0x1c0151094  mov     r9d, 0C000000Dh
0x1c015109a  lea     r8, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids
0x1c01510a1  mov     rcx, [rcx+18h]
0x1c01510a5  call    WPP_SF_D
0x1c01510aa  mov     al, cs:RefsStatusDebugEnabled
0x1c01510b0  test    al, al
0x1c01510b2  jz      short loc_1C01510CB
0x1c01510b4  mov     r8d, 0E69h
0x1c01510ba  lea     rdx, aSecursupC; "SecurSup.c"
0x1c01510c1  mov     ecx, 0C000000Dh; Status
0x1c01510c6  call    RefsStatusDebug
0x1c01510cb  mov     edx, 0C000000Dh
0x1c01510d0  mov     rcx, rsi
0x1c01510d3  call    RefsRaiseStatusInternal
0x1c01510d8  mov     r9b, 1
0x1c01510db  mov     r8d, eax
0x1c01510de  mov     rdx, [rsp+78h+NewDescriptor]
0x1c01510e6  mov     rcx, rsi
0x1c01510e9  call    RefsCacheSharedSecurityByDescriptor
0x1c01510ee  mov     rsi, rax
0x1c01510f1  mov     rdi, [rsp+78h+NewDescriptor]
0x1c01510f9  mov     rbx, [r15+48h]
0x1c01510fd  mov     rcx, [rbx+30h]; P
0x1c0151101  test    rcx, rcx
0x1c0151104  jnz     loc_1C0181972
0x1c015110a  mov     [rbx+30h], rdi
0x1c015110e  mov     rax, rsi
0x1c0151111  mov     rbx, [rsp+78h+arg_10]
0x1c0151119  add     rsp, 50h
0x1c015111d  pop     r15
0x1c015111f  pop     r14
0x1c0151121  pop     r12
0x1c0151123  pop     rdi
0x1c0151124  pop     rsi
0x1c0151125  retn
0x1c017dd8e  push    rbx
0x1c017dd90  push    rbp
0x1c017dd91  push    rdi
0x1c017dd92  sub     rsp, 50h
0x1c017dd96  mov     rbp, rdx
0x1c017dd99  mov     rdi, [rbp+80h]
0x1c017dda0  mov     rax, [rbp+88h]
0x1c017dda7  mov     rbx, [rax+48h]
0x1c017ddab  mov     rcx, [rbx+30h]; P
0x1c017ddaf  test    rcx, rcx
0x1c017ddb2  jz      short loc_1C017DDC3
0x1c017ddb4  xor     edx, edx; Tag
0x1c017ddb6  call    cs:__imp_ExFreePoolWithTag
0x1c017ddbd  nop     dword ptr [rax+rax+00h]
0x1c017ddc2  nop
0x1c017ddc3  mov     [rbx+30h], rdi
0x1c017ddc7  add     rsp, 50h
0x1c017ddcb  pop     rdi
0x1c017ddcc  pop     rbp
0x1c017ddcd  pop     rbx
0x1c017ddce  retn
0x1c0181904  call    RefsLoadSecurityDescriptor
0x1c0181909  nop
0x1c018190a  jmp     loc_1C0150FD3
0x1c018190f  lea     rdx, WPP_GLOBAL_Control
0x1c0181916  mov     rcx, cs:WPP_GLOBAL_Control
0x1c018191d  cmp     rcx, rdx
0x1c0181920  jz      short loc_1C0181949
0x1c0181922  test    dword ptr [rcx+2Ch], 100h
0x1c0181929  jz      short loc_1C0181949
0x1c018192b  cmp     byte ptr [rcx+29h], 4
0x1c018192f  jb      short loc_1C0181949
0x1c0181931  mov     edx, 1Fh
0x1c0181936  mov     r9d, ebx
0x1c0181939  lea     r8, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids
0x1c0181940  mov     rcx, [rcx+18h]
0x1c0181944  call    WPP_SF_D
0x1c0181949  mov     al, cs:RefsStatusDebugEnabled
0x1c018194f  test    al, al
0x1c0181951  jz      short loc_1C0181967
0x1c0181953  mov     r8d, 0E59h
0x1c0181959  lea     rdx, aSecursupC; "SecurSup.c"
0x1c0181960  mov     ecx, ebx; Status
0x1c0181962  call    RefsStatusDebug
0x1c0181967  mov     edx, ebx
0x1c0181969  mov     rcx, rsi
0x1c018196c  call    RefsRaiseStatusInternal
0x1c0181971  int     3; Trap to Debugger
0x1c0181972  xor     edx, edx; Tag
0x1c0181974  call    cs:__imp_ExFreePoolWithTag
0x1c018197b  nop     dword ptr [rax+rax+00h]
0x1c0181980  nop
0x1c0181981  jmp     loc_1C015110A
```
