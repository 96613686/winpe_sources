# KsecRemoveValidVm

- ea: `0x180005b58`
- end: `0x180005ce9`
- name: `KsecRemoveValidVm`
- size: `401`
- prototype: `__int64 __fastcall(struct _EPROCESS *, unsigned __int8 *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180005718`
- `0x18000ba98`
- `0x18000cbb4`
- `0x18000d664`
- `0x18000d94c`
- `0x180026fb8`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180005b58`
- `0x18000c648`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180005b76`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005c21`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005b76`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005c21`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180005c32`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180005c32`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180005cb3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180005cb3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005bd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005c15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005cbf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005bd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005c15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005cbf`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180005b96`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180005b96`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180005bc8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180005c09`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180005bc8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180005c09`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x180005bf4`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x180005bf4`

## pseudocode

```c
__int64 __fastcall KsecRemoveValidVm(struct _EPROCESS *a1, unsigned __int8 *a2)
{
  struct _KSECDDLSASTATE *v4; // rbx
  char *v5; // rdi
  unsigned int ValidVm; // ebp
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // rax
  struct _KSECDDLSASTATE *v11; // [rsp+80h] [rbp+18h] BYREF

  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v11);
  KeEnterCriticalRegion();
  v4 = v11;
  v5 = (char *)v11 + 568;
  ExAcquirePushLockSharedEx((char *)v11 + 568, 0);
  ValidVm = KsecFindValidVm(v4, a1, a2, 0, 0xFFFFFFFF);
  if ( ValidVm == -1 )
  {
    ExReleasePushLockSharedEx(v5, 0);
    KeLeaveCriticalRegion();
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v11);
    return 0;
  }
  else
  {
    if ( ((unsigned __int8)ExTryConvertPushLockSharedToExclusiveEx(v5, 0)
       || (ExReleasePushLockSharedEx(v5, 0),
           KeLeaveCriticalRegion(),
           KeEnterCriticalRegion(),
           ExAcquirePushLockExclusiveEx(v5, 0),
           ValidVm = KsecFindValidVm(v4, a1, a2, 0, ValidVm),
           ValidVm != -1))
      && (v8 = *((_QWORD *)v4 + 73), *(unsigned __int8 **)(v8 + 40LL * ValidVm + 16) == a2) )
    {
      v9 = *(_QWORD *)(v8 + 40LL * ValidVm);
      v10 = (unsigned int)(*((_DWORD *)v4 + 144) - 1);
      if ( ValidVm != (_DWORD)v10 )
      {
        *(_OWORD *)(v8 + 40LL * ValidVm) = *(_OWORD *)(v8 + 40 * v10);
        *(_OWORD *)(v8 + 40LL * ValidVm + 16) = *(_OWORD *)(v8 + 40 * v10 + 16);
        *(_QWORD *)(v8 + 40LL * ValidVm + 32) = *(_QWORD *)(v8 + 40 * v10 + 32);
      }
      --*((_DWORD *)v4 + 144);
    }
    else
    {
      v9 = 0;
    }
    ExReleasePushLockExclusiveEx(v5, 0);
    KeLeaveCriticalRegion();
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v11);
    return v9;
  }
}

```

## disassembly

```asm
0x180005b58  mov     rax, rsp
0x180005b5b  push    rbx
0x180005b5c  push    rbp
0x180005b5d  push    rsi
0x180005b5e  push    rdi
0x180005b5f  push    r14
0x180005b61  push    r15
0x180005b63  sub     rsp, 38h
0x180005b67  mov     r14, rcx
0x180005b6a  mov     rsi, rdx
0x180005b6d  lea     rcx, [rax+18h]; this
0x180005b71  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180005b76  call    cs:__imp_KeEnterCriticalRegion
0x180005b7d  nop     dword ptr [rax+rax+00h]
0x180005b82  mov     rbx, [rsp+68h+arg_10]
0x180005b8a  xor     edx, edx
0x180005b8c  lea     rdi, [rbx+238h]
0x180005b93  mov     rcx, rdi
0x180005b96  call    cs:__imp_ExAcquirePushLockSharedEx
0x180005b9d  nop     dword ptr [rax+rax+00h]
0x180005ba2  or      r15d, 0FFFFFFFFh
0x180005ba6  xor     r9d, r9d; unsigned int
0x180005ba9  mov     r8, rsi; unsigned __int8 *
0x180005bac  mov     [rsp+68h+var_48], r15d; unsigned int
0x180005bb1  mov     rdx, r14; struct _EPROCESS *
0x180005bb4  mov     rcx, rbx; struct _KSECDDLSASTATE *
0x180005bb7  call    ?KsecFindValidVm@@YAKPEAU_KSECDDLSASTATE@@PEAU_EPROCESS@@PEAEKK@Z; KsecFindValidVm(_KSECDDLSASTATE *,_EPROCESS *,uchar *,ulong,ulong)
0x180005bbc  xor     edx, edx
0x180005bbe  mov     ebp, eax
0x180005bc0  mov     rcx, rdi
0x180005bc3  cmp     eax, r15d
0x180005bc6  jnz     short loc_180005BF4
0x180005bc8  call    cs:__imp_ExReleasePushLockSharedEx
0x180005bcf  nop     dword ptr [rax+rax+00h]
0x180005bd4  call    cs:__imp_KeLeaveCriticalRegion
0x180005bdb  nop     dword ptr [rax+rax+00h]
0x180005be0  lea     rcx, [rsp+68h+arg_10]; this
0x180005be8  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180005bed  xor     eax, eax
0x180005bef  jmp     loc_180005CDB
0x180005bf4  call    cs:__imp_ExTryConvertPushLockSharedToExclusiveEx
0x180005bfb  nop     dword ptr [rax+rax+00h]
0x180005c00  test    al, al
0x180005c02  jnz     short loc_180005C5A
0x180005c04  xor     edx, edx
0x180005c06  mov     rcx, rdi
0x180005c09  call    cs:__imp_ExReleasePushLockSharedEx
0x180005c10  nop     dword ptr [rax+rax+00h]
0x180005c15  call    cs:__imp_KeLeaveCriticalRegion
0x180005c1c  nop     dword ptr [rax+rax+00h]
0x180005c21  call    cs:__imp_KeEnterCriticalRegion
0x180005c28  nop     dword ptr [rax+rax+00h]
0x180005c2d  xor     edx, edx
0x180005c2f  mov     rcx, rdi
0x180005c32  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x180005c39  nop     dword ptr [rax+rax+00h]
0x180005c3e  xor     r9d, r9d; unsigned int
0x180005c41  mov     [rsp+68h+var_48], ebp; unsigned int
0x180005c45  mov     r8, rsi; unsigned __int8 *
0x180005c48  mov     rdx, r14; struct _EPROCESS *
0x180005c4b  mov     rcx, rbx; struct _KSECDDLSASTATE *
0x180005c4e  call    ?KsecFindValidVm@@YAKPEAU_KSECDDLSASTATE@@PEAU_EPROCESS@@PEAEKK@Z; KsecFindValidVm(_KSECDDLSASTATE *,_EPROCESS *,uchar *,ulong,ulong)
0x180005c53  mov     ebp, eax
0x180005c55  cmp     eax, r15d
0x180005c58  jz      short loc_180005C6E
0x180005c5a  mov     rdx, [rbx+248h]
0x180005c61  mov     eax, ebp
0x180005c63  lea     r8, [rax+rax*4]
0x180005c67  cmp     [rdx+r8*8+10h], rsi
0x180005c6c  jz      short loc_180005C72
0x180005c6e  xor     esi, esi
0x180005c70  jmp     short loc_180005CAE
0x180005c72  mov     eax, [rbx+240h]
0x180005c78  mov     rsi, [rdx+r8*8]
0x180005c7c  dec     eax
0x180005c7e  cmp     ebp, eax
0x180005c80  jz      short loc_180005CA7
0x180005c82  lea     rcx, [rax+rax*4]
0x180005c86  movups  xmm0, xmmword ptr [rdx+rcx*8]
0x180005c8a  movups  xmmword ptr [rdx+r8*8], xmm0
0x180005c8f  movups  xmm1, xmmword ptr [rdx+rcx*8+10h]
0x180005c94  movups  xmmword ptr [rdx+r8*8+10h], xmm1
0x180005c9a  movsd   xmm0, qword ptr [rdx+rcx*8+20h]
0x180005ca0  movsd   qword ptr [rdx+r8*8+20h], xmm0
0x180005ca7  add     [rbx+240h], r15d
0x180005cae  xor     edx, edx
0x180005cb0  mov     rcx, rdi
0x180005cb3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180005cba  nop     dword ptr [rax+rax+00h]
0x180005cbf  call    cs:__imp_KeLeaveCriticalRegion
0x180005cc6  nop     dword ptr [rax+rax+00h]
0x180005ccb  lea     rcx, [rsp+68h+arg_10]; this
0x180005cd3  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180005cd8  mov     rax, rsi
0x180005cdb  add     rsp, 38h
0x180005cdf  pop     r15
0x180005ce1  pop     r14
0x180005ce3  pop     rdi
0x180005ce4  pop     rsi
0x180005ce5  pop     rbp
0x180005ce6  pop     rbx
0x180005ce7  retn
```
