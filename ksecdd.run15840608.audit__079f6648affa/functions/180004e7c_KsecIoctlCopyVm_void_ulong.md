# KsecIoctlCopyVm(void *,ulong)

- ea: `0x180004e7c`
- end: `0x18000515a`
- name: `?KsecIoctlCopyVm@@YAJPEAXK@Z`
- size: `734`
- prototype: `__int64 __fastcall(void *Src, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800053e0`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180004dbc`
- `0x180004e7c`
- `0x180007a64`
- `0x18000c648`
- `0x18000df18`
- `0x18000dfdc`
- `0x18000e1c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180004fd4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180004fd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800050c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800050c8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180004ff4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180004ff4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800050bc`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800050bc`
- `ntoskrnl!ObfDereferenceObject` at `0x1800050d7`
- `ntoskrnl!ObfDereferenceObject` at `0x1800050d7`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x180004ee9`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x180004ee9`
- `ntoskrnl!ProbeForRead` at `0x180004f11`
- `ntoskrnl!ProbeForRead` at `0x180004f11`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180004f4c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180004f4c`
- `ntoskrnl!PsProcessType` at `0x180004f3b`

## pseudocode

```c
__int64 __fastcall KsecIoctlCopyVm(void *Src, int a2)
{
  __int64 v4; // r8
  struct _KSECDDLSASTATE *v5; // rbx
  NTSTATUS v7; // eax
  __int64 v8; // r8
  unsigned int v9; // edi
  struct _EPROCESS *v10; // rdi
  struct _EPROCESS *v11; // rsi
  volatile void *v12; // r14
  struct _EPROCESS *v13; // r15
  void *v14; // r12
  __int64 v15; // r13
  __int64 v16; // r8
  SIZE_T v17; // r9
  unsigned int v18; // ebx
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rdx
  __int128 Handle; // [rsp+40h] [rbp-58h] BYREF
  __int128 Address; // [rsp+50h] [rbp-48h]
  struct _KSECDDLSASTATE *v24; // [rsp+A0h] [rbp+8h] BYREF
  PVOID Object; // [rsp+B0h] [rbp+18h] BYREF
  char *v26; // [rsp+B8h] [rbp+20h]

  Handle = 0;
  Address = 0;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
  if ( Src && (v4 = 32, a2 == 32) )
  {
    v5 = v24;
    if ( v24 )
    {
      if ( ((unsigned __int8)Src & 7) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(&Handle, Src, 0x20u);
      ProbeForRead((volatile void *)Address, DWORD2(Address), 1u);
      Object = 0;
      v7 = ObReferenceObjectByHandle((HANDLE)Handle, 0, (POBJECT_TYPE)PsProcessType, 0, &Object, 0);
      v9 = v7;
      if ( v7 >= 0 )
      {
        v10 = (struct _EPROCESS *)Object;
        if ( HIDWORD(Address) )
        {
          v11 = *(struct _EPROCESS **)v5;
          v12 = (volatile void *)Address;
          v13 = (struct _EPROCESS *)Object;
          v14 = (void *)*((_QWORD *)&Handle + 1);
        }
        else
        {
          v11 = (struct _EPROCESS *)Object;
          v12 = (volatile void *)*((_QWORD *)&Handle + 1);
          v13 = *(struct _EPROCESS **)v5;
          v14 = (void *)Address;
        }
        KeEnterCriticalRegion();
        v26 = (char *)v5 + 568;
        ExAcquirePushLockSharedEx((char *)v5 + 568, 0);
        v15 = *((_QWORD *)&Handle + 1);
        if ( KsecFindValidVm(v5, v10, *((unsigned __int8 **)&Handle + 1), DWORD2(Address), 0xFFFFFFFF) == -1 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 3), &WPP_GLOBAL_Control, v16, v10, v15, v17);
          v18 = -1073741790;
        }
        else
        {
          v19 = KsecCopyVirtualMemory(v11, v12, v13, v14, v17);
          v18 = v19;
          if ( v19 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v21 = *((unsigned int *)WPP_GLOBAL_Control + 11);
            if ( (v21 & 1) != 0 )
              WPP_SF_qqqqL(*((_QWORD *)WPP_GLOBAL_Control + 3), v21, v20, v11, v12, v13, v14, v19);
          }
        }
        ExReleasePushLockSharedEx(v26, 0);
        KeLeaveCriticalRegion();
        ObfDereferenceObject(v10);
        KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
        return v18;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 3), 53, v8, Handle, v7);
        KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
        return v9;
      }
    }
    else
    {
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
      return 3221226238LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 3), 52, v4, Src, a2);
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v24);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180004e7c  mov     rax, rsp
0x180004e7f  push    rbx
0x180004e80  push    rsi
0x180004e81  push    rdi
0x180004e82  push    r12
0x180004e84  push    r13
0x180004e86  push    r14
0x180004e88  push    r15
0x180004e8a  sub     rsp, 60h
0x180004e8e  mov     ebx, edx
0x180004e90  mov     rdi, rcx
0x180004e93  xorps   xmm0, xmm0
0x180004e96  movups  xmmword ptr [rax-58h], xmm0
0x180004e9a  movups  xmmword ptr [rax-48h], xmm0
0x180004e9e  lea     rcx, [rax+8]; this
0x180004ea2  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180004ea7  xor     esi, esi
0x180004ea9  test    rdi, rdi
0x180004eac  jz      loc_180005108
0x180004eb2  lea     r8d, [rsi+20h]
0x180004eb6  cmp     ebx, r8d
0x180004eb9  jnz     loc_180005108
0x180004ebf  mov     rbx, [rsp+98h+arg_0]
0x180004ec7  test    rbx, rbx
0x180004eca  jnz     short loc_180004EE3
0x180004ecc  lea     rcx, [rsp+98h+arg_0]; this
0x180004ed4  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180004ed9  mov     eax, 0C00002FEh
0x180004ede  jmp     loc_180005149
0x180004ee3  test    dil, 7
0x180004ee7  jz      short loc_180004EF5
0x180004ee9  call    cs:__imp_ExRaiseDatatypeMisalignment
0x180004ef0  nop     dword ptr [rax+rax+00h]
0x180004ef5  mov     rdx, rdi; Src
0x180004ef8  lea     rcx, [rsp+98h+Handle]; void *
0x180004efd  call    RtlCopyFromUser
0x180004f02  mov     edx, dword ptr [rsp+98h+Length]; Length
0x180004f06  mov     r8d, 1; Alignment
0x180004f0c  mov     rcx, [rsp+98h+Address]; Address
0x180004f11  call    cs:__imp_ProbeForRead
0x180004f18  nop     dword ptr [rax+rax+00h]
0x180004f1d  nop
0x180004f1e  mov     [rsp+98h+arg_10], rsi
0x180004f26  mov     [rsp+98h+HandleInformation], rsi; HandleInformation
0x180004f2b  lea     rax, [rsp+98h+arg_10]
0x180004f33  mov     [rsp+98h+Object], rax; Object
0x180004f38  xor     r9d, r9d; AccessMode
0x180004f3b  mov     r8, cs:__imp_PsProcessType
0x180004f42  mov     r8, [r8]; ObjectType
0x180004f45  xor     edx, edx; DesiredAccess
0x180004f47  mov     rcx, [rsp+98h+Handle]; Handle
0x180004f4c  call    cs:__imp_ObReferenceObjectByHandle
0x180004f53  nop     dword ptr [rax+rax+00h]
0x180004f58  mov     edi, eax
0x180004f5a  test    eax, eax
0x180004f5c  jns     short loc_180004FA4
0x180004f5e  lea     rdx, WPP_GLOBAL_Control
0x180004f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f6c  cmp     rcx, rdx
0x180004f6f  jz      short loc_180004F90
0x180004f71  mov     edx, [rcx+2Ch]
0x180004f74  test    dl, 1
0x180004f77  jz      short loc_180004F90
0x180004f79  mov     edx, 35h ; '5'
0x180004f7e  mov     dword ptr [rsp+98h+Object], eax
0x180004f82  mov     r9, [rsp+98h+Handle]
0x180004f87  mov     rcx, [rcx+18h]
0x180004f8b  call    WPP_SF_qL
0x180004f90  lea     rcx, [rsp+98h+arg_0]; this
0x180004f98  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180004f9d  mov     eax, edi
0x180004f9f  jmp     loc_180005149
0x180004fa4  mov     rdi, [rsp+98h+arg_10]
0x180004fac  cmp     dword ptr [rsp+98h+Length+4], esi
0x180004fb0  jz      short loc_180004FC4
0x180004fb2  mov     rsi, [rbx]
0x180004fb5  mov     r14, [rsp+98h+Address]
0x180004fba  mov     r15, rdi
0x180004fbd  mov     r12, [rsp+98h+var_50]
0x180004fc2  jmp     short loc_180004FD4
0x180004fc4  mov     rsi, rdi
0x180004fc7  mov     r14, [rsp+98h+var_50]
0x180004fcc  mov     r15, [rbx]
0x180004fcf  mov     r12, [rsp+98h+Address]
0x180004fd4  call    cs:__imp_KeEnterCriticalRegion
0x180004fdb  nop     dword ptr [rax+rax+00h]
0x180004fe0  lea     rax, [rbx+238h]
0x180004fe7  mov     [rsp+98h+arg_18], rax
0x180004fef  xor     edx, edx
0x180004ff1  mov     rcx, rax
0x180004ff4  call    cs:__imp_ExAcquirePushLockSharedEx
0x180004ffb  nop     dword ptr [rax+rax+00h]
0x180005000  mov     dword ptr [rsp+98h+Object], 0FFFFFFFFh; unsigned int
0x180005008  mov     r9d, dword ptr [rsp+98h+Length]; unsigned int
0x18000500d  mov     r13, [rsp+98h+var_50]
0x180005012  mov     r8, r13; unsigned __int8 *
0x180005015  mov     rdx, rdi; struct _EPROCESS *
0x180005018  mov     rcx, rbx; struct _KSECDDLSASTATE *
0x18000501b  call    ?KsecFindValidVm@@YAKPEAU_KSECDDLSASTATE@@PEAU_EPROCESS@@PEAEKK@Z; KsecFindValidVm(_KSECDDLSASTATE *,_EPROCESS *,uchar *,ulong,ulong)
0x180005020  cmp     eax, 0FFFFFFFFh
0x180005023  jnz     short loc_18000505C
0x180005025  lea     rdx, WPP_GLOBAL_Control
0x18000502c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005033  cmp     rcx, rdx
0x180005036  jz      short loc_180005055
0x180005038  mov     eax, [rcx+2Ch]
0x18000503b  test    al, 1
0x18000503d  jz      short loc_180005055
0x18000503f  mov     dword ptr [rsp+98h+HandleInformation], r9d
0x180005044  mov     [rsp+98h+Object], r13
0x180005049  mov     r9, rdi
0x18000504c  mov     rcx, [rcx+18h]
0x180005050  call    WPP_SF_qqD
0x180005055  mov     ebx, 0C0000022h
0x18000505a  jmp     short loc_1800050B2
0x18000505c  mov     [rsp+98h+Object], r9; unsigned __int64
0x180005061  mov     r9, r12; void *
0x180005064  mov     r8, r15; struct _EPROCESS *
0x180005067  mov     rdx, r14; void *
0x18000506a  mov     rcx, rsi; struct _EPROCESS *
0x18000506d  call    ?KsecCopyVirtualMemory@@YAJPEAU_EPROCESS@@PEBX0PEAX_K@Z; KsecCopyVirtualMemory(_EPROCESS *,void const *,_EPROCESS *,void *,unsigned __int64)
0x180005072  mov     ebx, eax
0x180005074  test    eax, eax
0x180005076  jns     short loc_1800050B2
0x180005078  lea     rdx, WPP_GLOBAL_Control
0x18000507f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005086  cmp     rcx, rdx
0x180005089  jz      short loc_1800050B2
0x18000508b  mov     edx, [rcx+2Ch]
0x18000508e  test    dl, 1
0x180005091  jz      short loc_1800050B2
0x180005093  mov     [rsp+98h+var_60], eax
0x180005097  mov     [rsp+98h+var_68], r12
0x18000509c  mov     [rsp+98h+HandleInformation], r15
0x1800050a1  mov     [rsp+98h+Object], r14
0x1800050a6  mov     r9, rsi
0x1800050a9  mov     rcx, [rcx+18h]
0x1800050ad  call    WPP_SF_qqqqL
0x1800050b2  xor     edx, edx
0x1800050b4  mov     rcx, [rsp+98h+arg_18]
0x1800050bc  call    cs:__imp_ExReleasePushLockSharedEx
0x1800050c3  nop     dword ptr [rax+rax+00h]
0x1800050c8  call    cs:__imp_KeLeaveCriticalRegion
0x1800050cf  nop     dword ptr [rax+rax+00h]
0x1800050d4  mov     rcx, rdi; Object
0x1800050d7  call    cs:__imp_ObfDereferenceObject
0x1800050de  nop     dword ptr [rax+rax+00h]
0x1800050e3  lea     rcx, [rsp+98h+arg_0]; this
0x1800050eb  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800050f0  mov     eax, ebx
0x1800050f2  jmp     short loc_180005149
0x1800050f4  lea     rcx, [rsp+98h+arg_0]; this
0x1800050fc  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180005101  mov     eax, 0C0000005h
0x180005106  jmp     short loc_180005149
0x180005108  lea     rdx, WPP_GLOBAL_Control
0x18000510f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005116  cmp     rcx, rdx
0x180005119  jz      short loc_180005137
0x18000511b  mov     eax, [rcx+2Ch]
0x18000511e  test    al, 1
0x180005120  jz      short loc_180005137
0x180005122  mov     edx, 34h ; '4'
0x180005127  mov     dword ptr [rsp+98h+Object], ebx
0x18000512b  mov     r9, rdi
0x18000512e  mov     rcx, [rcx+18h]
0x180005132  call    WPP_SF_qL
0x180005137  lea     rcx, [rsp+98h+arg_0]; this
0x18000513f  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180005144  mov     eax, 0C000000Dh
0x180005149  add     rsp, 60h
0x18000514d  pop     r15
0x18000514f  pop     r14
0x180005151  pop     r13
0x180005153  pop     r12
0x180005155  pop     rdi
0x180005156  pop     rsi
0x180005157  pop     rbx
0x180005158  retn
```
