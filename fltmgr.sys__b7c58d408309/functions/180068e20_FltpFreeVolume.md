# FltpFreeVolume

- ea: `0x180068e20`
- end: `0x180069169`
- name: `FltpFreeVolume`
- size: `841`
- prototype: `void __fastcall(char *OwnerId, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180067db0`
- `0x1800682b0`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x180024c00`
- `0x18005dcc0`
- `0x180062ba0`
- `0x180063b40`
- `0x180063f70`
- `0x1800648b0`
- `0x180068e20`
- `0x180070b30`
- `0x1800745f0`
- `0x180076570`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x180069092`
- `ntoskrnl!ExReleaseFastMutex` at `0x180069092`
- `ntoskrnl!ExAcquireFastMutex` at `0x18006907e`
- `ntoskrnl!ExAcquireFastMutex` at `0x18006907e`
- `ntoskrnl!ObfDereferenceObject` at `0x1800690b3`
- `ntoskrnl!ObfDereferenceObject` at `0x1800690b3`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180068e4a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180068e4a`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180068ee1`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180068ee1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180068ec6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180068ec6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180068f49`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180068f7e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180068f49`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180068f7e`
- `ntoskrnl!ExReleaseFastResource` at `0x180068f3d`
- `ntoskrnl!ExReleaseFastResource` at `0x180068f72`
- `ntoskrnl!ExReleaseFastResource` at `0x180068f3d`
- `ntoskrnl!ExReleaseFastResource` at `0x180068f72`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180068fe6`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18006901f`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180068fe6`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18006901f`
- `ntoskrnl!ExDeleteFastResource` at `0x180068ff9`
- `ntoskrnl!ExDeleteFastResource` at `0x18006900c`
- `ntoskrnl!ExDeleteFastResource` at `0x180069032`
- `ntoskrnl!ExDeleteFastResource` at `0x180068ff9`
- `ntoskrnl!ExDeleteFastResource` at `0x18006900c`
- `ntoskrnl!ExDeleteFastResource` at `0x180069032`
- `ntoskrnl!ExRundownCompleted` at `0x1800690d1`
- `ntoskrnl!ExRundownCompleted` at `0x1800690d1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180069066`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180069105`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180069118`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006912b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180069066`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180069105`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180069118`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006912b`

## pseudocode

```c
void __fastcall FltpFreeVolume(char *OwnerId, unsigned int a2)
{
  int v4; // eax
  char *v5; // rsi
  __int64 v6; // r8
  char *i; // rdi
  NTSTATUS v8; // eax
  __int64 v9; // r8
  __int64 v10; // rdi
  void *v11; // rcx
  __int64 v12; // rax
  char *v13; // rcx
  _BYTE v14[80]; // [rsp+30h] [rbp-78h] BYREF

  memset(v14, 0, 0x48u);
  ExInitializeFastOwnerEntry(v14);
  v4 = FltpStartingToDrainObject((int *)OwnerId);
  if ( (int)FltpDbgStatus(v4) >= 0 )
  {
    v5 = OwnerId + 296;
LABEL_4:
    KeEnterCriticalRegion();
    LOBYTE(v6) = 1;
    ExAcquireFastResourceShared(OwnerId + 192, v14, v6);
    for ( i = *(char **)v5; i != v5; i = *(char **)i )
    {
      if ( (*((_DWORD *)i - 4) & 1) == 0 && (*((_DWORD *)i + 16) & 4) == 0 )
      {
        v8 = FltObjectReference(i - 16);
        if ( (int)FltpDbgStatus(v8) >= 0 )
        {
          ExReleaseFastResource(OwnerId + 192, v14);
          KeLeaveCriticalRegion();
          FltpFreeInstance(i - 16, a2, v9);
          goto LABEL_4;
        }
      }
    }
    ExReleaseFastResource(OwnerId + 192, v14);
    KeLeaveCriticalRegion();
    FltObjectDereference(OwnerId);
    FltpObjectRundownWait((__int64)OwnerId);
    FltpDeleteTxVolContextList(OwnerId);
    FltpDeleteAllStreamListCtrls(OwnerId);
    _InterlockedOr((volatile signed __int32 *)OwnerId + 399, 1u);
    FltpDeleteAllFileListCtrls(OwnerId);
    _InterlockedOr((volatile signed __int32 *)OwnerId + 431, 1u);
    FltpDeleteContextList((__int64)(OwnerId + 1336), (__int64)(OwnerId + 1320), -1, -1);
    ExCleanupAutoExpandPushLock(OwnerId + 2040);
    ExDeleteFastResource(OwnerId + 1472);
    ExDeleteFastResource(OwnerId + 1600);
    ExCleanupAutoExpandPushLock(OwnerId + 1320);
    ExDeleteFastResource(OwnerId + 1928);
    if ( *((_QWORD *)OwnerId + 19) )
      RtlFreeUnicodeString((PUNICODE_STRING)OwnerId + 9);
    v10 = *(_QWORD *)(*((_QWORD *)OwnerId + 8) + 64LL);
    ExAcquireFastMutex((PFAST_MUTEX)(v10 + 24));
    *(_QWORD *)(v10 + 80) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(v10 + 24));
    v11 = (void *)*((_QWORD *)OwnerId + 9);
    *((_QWORD *)OwnerId + 8) = 0;
    if ( v11 )
    {
      ObfDereferenceObject(v11);
      *((_QWORD *)OwnerId + 9) = 0;
    }
    if ( (*(_DWORD *)OwnerId & 2) == 0 )
      _InterlockedOr((volatile signed __int32 *)OwnerId, 2u);
    ExRundownCompleted((PEX_RUNDOWN_REF)OwnerId + 1);
    v12 = *((_QWORD *)OwnerId + 13);
    if ( v12 )
    {
      if ( *(_DWORD *)(v12 + 24) )
      {
        v13 = (char *)*((_QWORD *)OwnerId + 11);
        if ( v13 )
        {
          FltpObjectPointerDereference(v13);
          *((_QWORD *)OwnerId + 11) = 0;
        }
      }
    }
    RtlFreeUnicodeString((PUNICODE_STRING)OwnerId + 136);
    RtlFreeUnicodeString((PUNICODE_STRING)(OwnerId + 2200));
    RtlFreeUnicodeString((PUNICODE_STRING)OwnerId + 139);
    memset(OwnerId + 2168, 0, 0x50u);
    FltpObjectPointerDereference(OwnerId);
  }
  else
  {
    FltObjectDereference(OwnerId);
  }
}

```

## disassembly

```asm
0x180068e20  push    rbx
0x180068e22  push    r12
0x180068e24  push    r15
0x180068e26  sub     rsp, 90h
0x180068e2d  mov     r15d, edx
0x180068e30  mov     rbx, rcx
0x180068e33  xor     edx, edx; Val
0x180068e35  lea     rcx, [rsp+0A8h+var_78]; void *
0x180068e3a  mov     r8d, 48h ; 'H'; Size
0x180068e40  call    memset
0x180068e45  lea     rcx, [rsp+0A8h+var_78]
0x180068e4a  call    cs:__imp_ExInitializeFastOwnerEntry
0x180068e51  nop     dword ptr [rax+rax+00h]
0x180068e56  mov     rcx, rbx
0x180068e59  mov     r8d, 200h
0x180068e5f  call    FltpStartingToDrainObject
0x180068e64  xor     r12d, r12d
0x180068e67  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x180068e6e  mov     ecx, eax
0x180068e70  mov     [rsp+0A8h+var_88], r12
0x180068e75  mov     r9d, 0C01C000Bh
0x180068e7b  call    FltpDbgStatus
0x180068e80  test    eax, eax
0x180068e82  jns     short loc_180068E91
0x180068e84  mov     rcx, rbx; FltObject
0x180068e87  call    FltObjectDereference
0x180068e8c  jmp     loc_18006915B
0x180068e91  mov     [rsp+0A8h+arg_0], rbp
0x180068e99  mov     [rsp+0A8h+arg_8], rsi
0x180068ea1  lea     rsi, [rbx+128h]
0x180068ea8  mov     [rsp+0A8h+arg_10], rdi
0x180068eb0  mov     [rsp+0A8h+var_20], r13
0x180068eb8  mov     r13d, 238h
0x180068ebe  mov     [rsp+0A8h+var_28], r14
0x180068ec6  call    cs:__imp_KeEnterCriticalRegion
0x180068ecd  nop     dword ptr [rax+rax+00h]
0x180068ed2  mov     r8b, 1
0x180068ed5  lea     rdx, [rsp+0A8h+var_78]
0x180068eda  lea     rcx, [rbx+0C0h]
0x180068ee1  call    cs:__imp_ExAcquireFastResourceShared
0x180068ee8  nop     dword ptr [rax+rax+00h]
0x180068eed  mov     rdi, [rsi]
0x180068ef0  cmp     rdi, rsi
0x180068ef3  jz      short loc_180068F66
0x180068ef5  mov     eax, [rdi-10h]
0x180068ef8  test    al, 1
0x180068efa  jnz     short loc_180068F2C
0x180068efc  mov     eax, [rdi+40h]
0x180068eff  test    al, 4
0x180068f01  jnz     short loc_180068F2C
0x180068f03  lea     rcx, [rdi-10h]; FltObject
0x180068f07  call    FltObjectReference
0x180068f0c  mov     r9d, 0C01C000Bh
0x180068f12  mov     [rsp+0A8h+var_88], r12
0x180068f17  mov     r8d, r13d
0x180068f1a  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x180068f21  mov     ecx, eax
0x180068f23  call    FltpDbgStatus
0x180068f28  test    eax, eax
0x180068f2a  jns     short loc_180068F31
0x180068f2c  mov     rdi, [rdi]
0x180068f2f  jmp     short loc_180068EF0
0x180068f31  lea     rdx, [rsp+0A8h+var_78]
0x180068f36  lea     rcx, [rbx+0C0h]
0x180068f3d  call    cs:__imp_ExReleaseFastResource
0x180068f44  nop     dword ptr [rax+rax+00h]
0x180068f49  call    cs:__imp_KeLeaveCriticalRegion
0x180068f50  nop     dword ptr [rax+rax+00h]
0x180068f55  mov     edx, r15d
0x180068f58  lea     rcx, [rdi-10h]; FltObject
0x180068f5c  call    FltpFreeInstance
0x180068f61  jmp     loc_180068EC6
0x180068f66  lea     rdx, [rsp+0A8h+var_78]
0x180068f6b  lea     rcx, [rbx+0C0h]
0x180068f72  call    cs:__imp_ExReleaseFastResource
0x180068f79  nop     dword ptr [rax+rax+00h]
0x180068f7e  call    cs:__imp_KeLeaveCriticalRegion
0x180068f85  nop     dword ptr [rax+rax+00h]
0x180068f8a  mov     rcx, rbx; FltObject
0x180068f8d  call    FltObjectDereference
0x180068f92  mov     rcx, rbx
0x180068f95  call    FltpObjectRundownWait
0x180068f9a  mov     rcx, rbx
0x180068f9d  call    FltpDeleteTxVolContextList
0x180068fa2  mov     rcx, rbx; OwnerId
0x180068fa5  call    FltpDeleteAllStreamListCtrls
0x180068faa  lock or dword ptr [rbx+63Ch], 1
0x180068fb2  mov     rcx, rbx
0x180068fb5  call    FltpDeleteAllFileListCtrls
0x180068fba  lock or dword ptr [rbx+6BCh], 1
0x180068fc2  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180068fc9  lea     rcx, [rbx+538h]
0x180068fd0  mov     r8, r9
0x180068fd3  lea     rdx, [rbx+528h]
0x180068fda  call    FltpDeleteContextList
0x180068fdf  lea     rcx, [rbx+7F8h]
0x180068fe6  call    cs:__imp_ExCleanupAutoExpandPushLock
0x180068fed  nop     dword ptr [rax+rax+00h]
0x180068ff2  lea     rcx, [rbx+5C0h]
0x180068ff9  call    cs:__imp_ExDeleteFastResource
0x180069000  nop     dword ptr [rax+rax+00h]
0x180069005  lea     rcx, [rbx+640h]
0x18006900c  call    cs:__imp_ExDeleteFastResource
0x180069013  nop     dword ptr [rax+rax+00h]
0x180069018  lea     rcx, [rbx+528h]
0x18006901f  call    cs:__imp_ExCleanupAutoExpandPushLock
0x180069026  nop     dword ptr [rax+rax+00h]
0x18006902b  lea     rcx, [rbx+788h]
0x180069032  call    cs:__imp_ExDeleteFastResource
0x180069039  nop     dword ptr [rax+rax+00h]
0x18006903e  mov     r14, [rsp+0A8h+var_28]
0x180069046  mov     r13, [rsp+0A8h+var_20]
0x18006904e  mov     rbp, [rsp+0A8h+arg_0]
0x180069056  cmp     [rbx+98h], r12
0x18006905d  jz      short loc_180069072
0x18006905f  lea     rcx, [rbx+90h]; UnicodeString
0x180069066  call    cs:__imp_RtlFreeUnicodeString
0x18006906d  nop     dword ptr [rax+rax+00h]
0x180069072  mov     rax, [rbx+40h]
0x180069076  mov     rdi, [rax+40h]
0x18006907a  lea     rcx, [rdi+18h]; FastMutex
0x18006907e  call    cs:__imp_ExAcquireFastMutex
0x180069085  nop     dword ptr [rax+rax+00h]
0x18006908a  lea     rcx, [rdi+18h]; FastMutex
0x18006908e  mov     [rdi+50h], r12
0x180069092  call    cs:__imp_ExReleaseFastMutex
0x180069099  nop     dword ptr [rax+rax+00h]
0x18006909e  mov     rcx, [rbx+48h]; Object
0x1800690a2  mov     rsi, [rsp+0A8h+arg_8]
0x1800690aa  mov     [rbx+40h], r12
0x1800690ae  test    rcx, rcx
0x1800690b1  jz      short loc_1800690C3
0x1800690b3  call    cs:__imp_ObfDereferenceObject
0x1800690ba  nop     dword ptr [rax+rax+00h]
0x1800690bf  mov     [rbx+48h], r12
0x1800690c3  mov     eax, [rbx]
0x1800690c5  test    al, 2
0x1800690c7  jnz     short loc_1800690CD
0x1800690c9  lock or dword ptr [rbx], 2
0x1800690cd  lea     rcx, [rbx+8]; RunRef
0x1800690d1  call    cs:__imp_ExRundownCompleted
0x1800690d8  nop     dword ptr [rax+rax+00h]
0x1800690dd  mov     rax, [rbx+68h]
0x1800690e1  test    rax, rax
0x1800690e4  jz      short loc_1800690FE
0x1800690e6  cmp     [rax+18h], r12d
0x1800690ea  jz      short loc_1800690FE
0x1800690ec  mov     rcx, [rbx+58h]
0x1800690f0  test    rcx, rcx
0x1800690f3  jz      short loc_1800690FE
0x1800690f5  call    FltpObjectPointerDereference
0x1800690fa  mov     [rbx+58h], r12
0x1800690fe  lea     rcx, [rbx+880h]; UnicodeString
0x180069105  call    cs:__imp_RtlFreeUnicodeString
0x18006910c  nop     dword ptr [rax+rax+00h]
0x180069111  lea     rcx, [rbx+898h]; UnicodeString
0x180069118  call    cs:__imp_RtlFreeUnicodeString
0x18006911f  nop     dword ptr [rax+rax+00h]
0x180069124  lea     rcx, [rbx+8B0h]; UnicodeString
0x18006912b  call    cs:__imp_RtlFreeUnicodeString
0x180069132  nop     dword ptr [rax+rax+00h]
0x180069137  xor     edx, edx; Val
0x180069139  lea     rcx, [rbx+878h]; void *
0x180069140  mov     r8d, 50h ; 'P'; Size
0x180069146  call    memset
0x18006914b  mov     rcx, rbx
0x18006914e  call    FltpObjectPointerDereference
0x180069153  mov     rdi, [rsp+0A8h+arg_10]
0x18006915b  add     rsp, 90h
0x180069162  pop     r15
0x180069164  pop     r12
0x180069166  pop     rbx
0x180069167  retn
```
