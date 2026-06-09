# DepFSPreCreate

- ea: `0x180008d60`
- end: `0x180009057`
- name: `DepFSPreCreate`
- size: `759`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001020`
- `0x18000844c`
- `0x1800084f4`
- `0x180008d60`
- `0x18000f91c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008fb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008fec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008fb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008fec`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x180008d86`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x180008d86`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008fac`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008fe0`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008fac`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008fe0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008f52`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008f52`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x180008e16`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x180008e16`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008f3d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008f3d`
- `ntoskrnl!SeAccessCheck` at `0x180008e65`
- `ntoskrnl!SeAccessCheck` at `0x180008e65`
- `FLTMGR!FltReleaseContext` at `0x180008ece`
- `FLTMGR!FltReleaseContext` at `0x180008ece`
- `FLTMGR!FltGetInstanceContext` at `0x180008dd8`
- `FLTMGR!FltGetInstanceContext` at `0x180008dd8`

## pseudocode

```c
__int64 __fastcall DepFSPreCreate(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  BOOLEAN v5; // al
  __int64 v6; // r8
  BOOLEAN v7; // cl
  __int64 v8; // rax
  char v9; // cl
  __int64 v10; // rax
  __int64 v11; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  DWORD GrantedAccess; // [rsp+50h] [rbp-18h] BYREF
  PFLT_CONTEXT Context[2]; // [rsp+58h] [rbp-10h] BYREF
  int AccessStatus; // [rsp+A8h] [rbp+40h] BYREF

  AccessStatus = 0;
  Context[0] = 0;
  v4 = 1;
  v5 = FsRtlAreVolumeStartupApplicationsComplete();
  v6 = *(_QWORD *)(a1 + 16);
  v7 = v5;
  v8 = *(_QWORD *)(v6 + 8);
  if ( !v8 )
    goto LABEL_35;
  if ( !v7 )
  {
    if ( (*(_DWORD *)(v8 + 80) & 0x400000) == 0
      || (*(_BYTE *)(v6 + 42) & 6) != 0
      || (*(_DWORD *)(*(_QWORD *)(v6 + 24) + 16LL) & 6) == 0 )
    {
      goto LABEL_35;
    }
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    AccessStatus = DepFSFindOurVolumeContext(*(_QWORD *)(a2 + 16), Context);
    if ( AccessStatus >= 0 )
    {
      if ( *((PFLT_CONTEXT *)Context[0] + 1) == (char *)Context[0] + 8
        || (unsigned int)(*((_DWORD *)Context[0] + 24) - 1) <= 1 )
      {
        ExReleaseResourceLite(&Resource);
        KeLeaveCriticalRegion();
      }
      else
      {
        *((_DWORD *)Context[0] + 24) = 1;
        *((_QWORD *)Context[0] + 13) = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL);
        ++dword_18000518C;
        ExReleaseResourceLite(&Resource);
        KeLeaveCriticalRegion();
        AccessStatus = DepFSHandleAutochkForHostVolume(Context[0], 1);
        v4 = (unsigned int)AccessStatus >> 31;
      }
      DereferenceVolumeContext(Context[0]);
      goto LABEL_35;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_35;
    }
    v14 = 12;
LABEL_34:
    WPP_SF_D(v13->AttachedDevice, v14, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids, (unsigned int)AccessStatus);
    goto LABEL_35;
  }
  if ( (*(_DWORD *)(v8 + 80) & 0x400000) == 0 )
    goto LABEL_35;
  v9 = *(_BYTE *)(a1 + 80);
  if ( (v9 || (*(_DWORD *)v6 & 1) == 0) && v9 != 1 )
    goto LABEL_35;
  AccessStatus = FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), Context);
  if ( AccessStatus < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_35;
    }
    v14 = 11;
    goto LABEL_34;
  }
  v10 = *(_QWORD *)(a1 + 16);
  GrantedAccess = 0;
  v11 = *(_QWORD *)(v10 + 24);
  if ( v11 && *((_QWORD *)Context[0] + 15) )
  {
    GenericMapping = IoGetFileObjectGenericMapping();
    if ( SeAccessCheck(
           *((PSECURITY_DESCRIPTOR *)Context[0] + 15),
           (PSECURITY_SUBJECT_CONTEXT)(*(_QWORD *)(v11 + 8) + 32LL),
           0,
           *(_DWORD *)(v11 + 16),
           0,
           0,
           GenericMapping,
           1,
           &GrantedAccess,
           &AccessStatus) )
    {
      *(_DWORD *)(*(_QWORD *)(v11 + 8) + 20LL) = GrantedAccess;
      *(_DWORD *)(*(_QWORD *)(v11 + 8) + 16LL) &= ~(GrantedAccess | 0x2000000);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_a4016d7e857d3af68560d770380f4c36_Traceguids,
        (unsigned int)AccessStatus);
    }
  }
  FltReleaseContext(Context[0]);
LABEL_35:
  if ( AccessStatus < 0 )
  {
    *(_DWORD *)(a1 + 24) = AccessStatus;
    return 4;
  }
  return v4;
}

```

## disassembly

```asm
0x180008d60  push    rbp
0x180008d62  push    rbx
0x180008d63  push    rsi
0x180008d64  push    rdi
0x180008d65  mov     rbp, rsp
0x180008d68  sub     rsp, 68h
0x180008d6c  mov     rdi, rdx
0x180008d6f  mov     [rbp+arg_18], 0
0x180008d76  mov     rsi, rcx
0x180008d79  mov     [rbp+Context], 0
0x180008d81  mov     ebx, 1
0x180008d86  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x180008d8d  nop     dword ptr [rax+rax+00h]
0x180008d92  mov     r8, [rsi+10h]
0x180008d96  mov     cl, al
0x180008d98  mov     rax, [r8+8]
0x180008d9c  test    rax, rax
0x180008d9f  jz      loc_18000903C
0x180008da5  test    cl, cl
0x180008da7  jz      loc_180008F15
0x180008dad  test    dword ptr [rax+50h], 400000h
0x180008db4  jz      loc_18000903C
0x180008dba  mov     cl, [rsi+50h]
0x180008dbd  test    cl, cl
0x180008dbf  jnz     short loc_180008DC8
0x180008dc1  mov     eax, [r8]
0x180008dc4  test    bl, al
0x180008dc6  jnz     short loc_180008DD0
0x180008dc8  cmp     cl, bl
0x180008dca  jnz     loc_18000903C
0x180008dd0  mov     rcx, [rdi+18h]; Instance
0x180008dd4  lea     rdx, [rbp+Context]; Context
0x180008dd8  call    cs:__imp_FltGetInstanceContext
0x180008ddf  nop     dword ptr [rax+rax+00h]
0x180008de4  mov     [rbp+arg_18], eax
0x180008de7  test    eax, eax
0x180008de9  js      loc_180008EDF
0x180008def  mov     rax, [rsi+10h]
0x180008df3  mov     [rbp+var_18], 0
0x180008dfa  mov     rdi, [rax+18h]
0x180008dfe  test    rdi, rdi
0x180008e01  jz      loc_180008ECA
0x180008e07  mov     rax, [rbp+Context]
0x180008e0b  cmp     qword ptr [rax+78h], 0
0x180008e10  jz      loc_180008ECA
0x180008e16  call    cs:__imp_IoGetFileObjectGenericMapping
0x180008e1d  nop     dword ptr [rax+rax+00h]
0x180008e22  mov     rdx, [rdi+8]
0x180008e26  lea     rcx, [rbp+arg_18]
0x180008e2a  mov     r9d, [rdi+10h]; DesiredAccess
0x180008e2e  add     rdx, 20h ; ' '; SubjectSecurityContext
0x180008e32  mov     [rsp+68h+AccessStatus], rcx; AccessStatus
0x180008e37  xor     r8d, r8d; SubjectContextLocked
0x180008e3a  lea     rcx, [rbp+var_18]
0x180008e3e  mov     [rsp+68h+GrantedAccess], rcx; GrantedAccess
0x180008e43  mov     rcx, [rbp+Context]
0x180008e47  mov     [rsp+68h+AccessMode], bl; AccessMode
0x180008e4b  mov     [rsp+68h+GenericMapping], rax; GenericMapping
0x180008e50  mov     [rsp+68h+Privileges], 0; Privileges
0x180008e59  mov     rcx, [rcx+78h]; SecurityDescriptor
0x180008e5d  mov     [rsp+68h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x180008e65  call    cs:__imp_SeAccessCheck
0x180008e6c  nop     dword ptr [rax+rax+00h]
0x180008e71  test    al, al
0x180008e73  jz      short loc_180008E91
0x180008e75  mov     rcx, [rdi+8]
0x180008e79  mov     eax, [rbp+var_18]
0x180008e7c  mov     [rcx+14h], eax
0x180008e7f  mov     eax, [rbp+var_18]
0x180008e82  mov     rcx, [rdi+8]
0x180008e86  bts     eax, 19h
0x180008e8a  not     eax
0x180008e8c  and     [rcx+10h], eax
0x180008e8f  jmp     short loc_180008ECA
0x180008e91  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e98  lea     rax, WPP_GLOBAL_Control
0x180008e9f  cmp     rcx, rax
0x180008ea2  jz      short loc_180008ECA
0x180008ea4  mov     eax, [rcx+2Ch]
0x180008ea7  test    bl, al
0x180008ea9  jz      short loc_180008ECA
0x180008eab  cmp     byte ptr [rcx+29h], 2
0x180008eaf  jb      short loc_180008ECA
0x180008eb1  mov     r9d, [rbp+arg_18]
0x180008eb5  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x180008ebc  mov     rcx, [rcx+18h]
0x180008ec0  mov     edx, 0Ah
0x180008ec5  call    WPP_SF_D
0x180008eca  mov     rcx, [rbp+Context]; Context
0x180008ece  call    cs:__imp_FltReleaseContext
0x180008ed5  nop     dword ptr [rax+rax+00h]
0x180008eda  jmp     loc_18000903C
0x180008edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ee6  lea     rax, WPP_GLOBAL_Control
0x180008eed  cmp     rcx, rax
0x180008ef0  jz      loc_18000903C
0x180008ef6  mov     eax, [rcx+2Ch]
0x180008ef9  test    bl, al
0x180008efb  jz      loc_18000903C
0x180008f01  cmp     byte ptr [rcx+29h], 2
0x180008f05  jb      loc_18000903C
0x180008f0b  mov     edx, 0Bh
0x180008f10  jmp     loc_180009028
0x180008f15  test    dword ptr [rax+50h], 400000h
0x180008f1c  jz      loc_18000903C
0x180008f22  test    byte ptr [r8+2Ah], 6
0x180008f27  jnz     loc_18000903C
0x180008f2d  mov     rax, [r8+18h]
0x180008f31  mov     ecx, [rax+10h]
0x180008f34  test    cl, 6
0x180008f37  jz      loc_18000903C
0x180008f3d  call    cs:__imp_KeEnterCriticalRegion
0x180008f44  nop     dword ptr [rax+rax+00h]
0x180008f49  mov     dl, bl; Wait
0x180008f4b  lea     rcx, Resource; Resource
0x180008f52  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180008f59  nop     dword ptr [rax+rax+00h]
0x180008f5e  mov     rcx, [rdi+10h]
0x180008f62  lea     rdx, [rbp+Context]
0x180008f66  call    DepFSFindOurVolumeContext
0x180008f6b  mov     [rbp+arg_18], eax
0x180008f6e  test    eax, eax
0x180008f70  js      loc_180009003
0x180008f76  mov     rdx, [rbp+Context]
0x180008f7a  lea     rax, [rdx+8]
0x180008f7e  cmp     [rax], rax
0x180008f81  jz      short loc_180008FD9
0x180008f83  mov     eax, [rdx+60h]
0x180008f86  sub     eax, ebx
0x180008f88  cmp     eax, ebx
0x180008f8a  jbe     short loc_180008FD9
0x180008f8c  mov     [rdx+60h], ebx
0x180008f8f  lea     rcx, Resource; Resource
0x180008f96  mov     rax, [rsi+10h]
0x180008f9a  mov     rdx, [rax+8]
0x180008f9e  mov     rax, [rbp+Context]
0x180008fa2  mov     [rax+68h], rdx
0x180008fa6  add     cs:dword_18000518C, ebx
0x180008fac  call    cs:__imp_ExReleaseResourceLite
0x180008fb3  nop     dword ptr [rax+rax+00h]
0x180008fb8  call    cs:__imp_KeLeaveCriticalRegion
0x180008fbf  nop     dword ptr [rax+rax+00h]
0x180008fc4  mov     rcx, [rbp+Context]
0x180008fc8  mov     edx, ebx
0x180008fca  call    DepFSHandleAutochkForHostVolume
0x180008fcf  mov     ebx, eax
0x180008fd1  mov     [rbp+arg_18], eax
0x180008fd4  shr     ebx, 1Fh
0x180008fd7  jmp     short loc_180008FF8
0x180008fd9  lea     rcx, Resource; Resource
0x180008fe0  call    cs:__imp_ExReleaseResourceLite
0x180008fe7  nop     dword ptr [rax+rax+00h]
0x180008fec  call    cs:__imp_KeLeaveCriticalRegion
0x180008ff3  nop     dword ptr [rax+rax+00h]
0x180008ff8  mov     rcx, [rbp+Context]
0x180008ffc  call    DereferenceVolumeContext
0x180009001  jmp     short loc_18000903C
0x180009003  mov     rcx, cs:WPP_GLOBAL_Control
0x18000900a  lea     rax, WPP_GLOBAL_Control
0x180009011  cmp     rcx, rax
0x180009014  jz      short loc_18000903C
0x180009016  mov     eax, [rcx+2Ch]
0x180009019  test    bl, al
0x18000901b  jz      short loc_18000903C
0x18000901d  cmp     byte ptr [rcx+29h], 2
0x180009021  jb      short loc_18000903C
0x180009023  mov     edx, 0Ch
0x180009028  mov     r9d, [rbp+arg_18]
0x18000902c  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x180009033  mov     rcx, [rcx+18h]
0x180009037  call    WPP_SF_D
0x18000903c  mov     eax, [rbp+arg_18]
0x18000903f  test    eax, eax
0x180009041  jns     short loc_18000904B
0x180009043  mov     [rsi+18h], eax
0x180009046  mov     ebx, 4
0x18000904b  mov     eax, ebx
0x18000904d  add     rsp, 68h
0x180009051  pop     rdi
0x180009052  pop     rsi
0x180009053  pop     rbx
0x180009054  pop     rbp
0x180009055  retn
```
