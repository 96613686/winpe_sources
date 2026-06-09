# UlNotifyIPListenListChanges

- ea: `0x1400d475c`
- end: `0x1400d4946`
- name: `UlNotifyIPListenListChanges`
- size: `490`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x14012ec44`
- `0x14012ef80`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140024bac`
- `0x1400d475c`
- `0x1400d7748`
- `0x140167c40`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400d4869`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d4869`
- `ntoskrnl!KeInitializeEvent` at `0x1400d47c1`
- `ntoskrnl!KeInitializeEvent` at `0x1400d47c1`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d48df`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d48df`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d47fc`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d47fc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d48eb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d48eb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d47e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d47e9`

## pseudocode

```c
__int64 __fastcall UlNotifyIPListenListChanges(__int64 a1, __int64 a2)
{
  __int64 v4; // r9
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rsi
  int v8; // eax
  int v9; // ecx
  _BYTE BugCheckParameter2[128]; // [rsp+30h] [rbp-29h] BYREF

  memset(BugCheckParameter2, 0, 0x60u);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qq(1028, 176, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, a1, a2);
  *(_DWORD *)&BugCheckParameter2[48] = 259;
  *(_QWORD *)&BugCheckParameter2[56] = 0;
  KeInitializeEvent((PRKEVENT)&BugCheckParameter2[64], NotificationEvent, 0);
  *(_QWORD *)BugCheckParameter2 = 0;
  *(_QWORD *)&BugCheckParameter2[16] = 0;
  *(_QWORD *)&BugCheckParameter2[32] = 0;
  *(_QWORD *)&BugCheckParameter2[88] = a2;
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 1368));
  if ( *(_QWORD *)BugCheckParameter2 || *(_QWORD *)&BugCheckParameter2[16] || *(_QWORD *)&BugCheckParameter2[32] )
    UlBugCheckEx(1u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)"minio\\http\\sys\\cgroup.c", 0x210Cu);
  LOBYTE(v4) = 1;
  UlThreadPoolEnqueueWorkItem(2, BugCheckParameter2, UxTlUpdateListenAddressList, v4, -1, -1);
  KeWaitForSingleObject(&BugCheckParameter2[64], UserRequest, 0, 0, 0);
  UlNotifyForAllChannels(a1, UlpNotifyIPListenListChangesOfServerSession);
  v5 = *(_QWORD *)(a1 + 1320);
  if ( *(_DWORD *)(v5 + 8) )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = *(_QWORD *)(v5 + 8 * v6 + 32);
      v8 = *(_DWORD *)(v7 + 60);
      if ( v8 == 1 )
        break;
      if ( v8 == 2 )
      {
        v9 = -2147468628;
        goto LABEL_12;
      }
LABEL_13:
      *(_DWORD *)(v7 + 60) = 0;
      v6 = (unsigned int)(v6 + 1);
      v5 = *(_QWORD *)(a1 + 1320);
      if ( (unsigned int)v6 >= *(_DWORD *)(v5 + 8) )
        goto LABEL_14;
    }
    v9 = -2147468629;
LABEL_12:
    UlEventLogOneStringEntry(v9);
    goto LABEL_13;
  }
LABEL_14:
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 1368));
  KeLeaveCriticalRegion();
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 177, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, *(unsigned int *)&BugCheckParameter2[48]);
  return *(unsigned int *)&BugCheckParameter2[48];
}

```

## disassembly

```asm
0x1400d475c  push    rbp
0x1400d475e  push    rbx
0x1400d475f  push    rsi
0x1400d4760  push    rdi
0x1400d4761  lea     rbp, [rsp-3Fh]
0x1400d4766  sub     rsp, 98h
0x1400d476d  mov     rdi, rdx
0x1400d4770  mov     rbx, rcx
0x1400d4773  xor     edx, edx; Val
0x1400d4775  lea     rcx, [rbp+57h+BugCheckParameter2]; void *
0x1400d4779  lea     r8d, [rdx+60h]; Size
0x1400d477d  call    memset
0x1400d4782  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d4789  jz      short loc_1400D47A9
0x1400d478b  mov     edx, 0B0h
0x1400d4790  mov     [rsp+0B0h+Timeout], rdi
0x1400d4795  mov     ecx, 404h
0x1400d479a  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400d47a1  mov     r9, rbx
0x1400d47a4  call    WPP_SF_qq
0x1400d47a9  xor     r8d, r8d; State
0x1400d47ac  mov     [rbp+57h+var_50], 103h
0x1400d47b3  xor     edx, edx; Type
0x1400d47b5  mov     [rbp+57h+var_48], 0
0x1400d47bd  lea     rcx, [rbp+57h+Event]; Event
0x1400d47c1  call    cs:__imp_KeInitializeEvent
0x1400d47c8  nop     dword ptr [rax+rax+00h]
0x1400d47cd  mov     [rbp+57h+BugCheckParameter2], 0
0x1400d47d5  mov     [rbp+57h+var_70], 0
0x1400d47dd  mov     [rbp+57h+var_60], 0
0x1400d47e5  mov     [rbp+57h+var_28], rdi
0x1400d47e9  call    cs:__imp_KeEnterCriticalRegion
0x1400d47f0  nop     dword ptr [rax+rax+00h]
0x1400d47f5  mov     rcx, [rbx+558h]
0x1400d47fc  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d4803  nop     dword ptr [rax+rax+00h]
0x1400d4808  cmp     [rbp+57h+BugCheckParameter2], 0
0x1400d480d  jnz     loc_1400D492A
0x1400d4813  cmp     [rbp+57h+var_70], 0
0x1400d4818  jnz     loc_1400D492A
0x1400d481e  cmp     [rbp+57h+var_60], 0
0x1400d4823  jnz     loc_1400D492A
0x1400d4829  mov     [rsp+0B0h+var_88], 0FFFFFFFFh
0x1400d4831  lea     r8, UxTlUpdateListenAddressList
0x1400d4838  mov     r9b, 1
0x1400d483b  mov     [rsp+0B0h+Timeout], 0FFFFFFFFFFFFFFFFh
0x1400d4844  lea     rdx, [rbp+57h+BugCheckParameter2]
0x1400d4848  mov     ecx, 2
0x1400d484d  call    UlThreadPoolEnqueueWorkItem
0x1400d4852  xor     r9d, r9d; Alertable
0x1400d4855  mov     [rsp+0B0h+Timeout], 0; Timeout
0x1400d485e  xor     r8d, r8d; WaitMode
0x1400d4861  lea     rcx, [rbp+57h+Event]; Object
0x1400d4865  lea     edx, [r9+6]; WaitReason
0x1400d4869  call    cs:__imp_KeWaitForSingleObject
0x1400d4870  nop     dword ptr [rax+rax+00h]
0x1400d4875  lea     rdx, UlpNotifyIPListenListChangesOfServerSession
0x1400d487c  mov     rcx, rbx
0x1400d487f  call    UlNotifyForAllChannels
0x1400d4884  mov     rcx, [rbx+528h]
0x1400d488b  cmp     dword ptr [rcx+8], 0
0x1400d488f  jbe     short loc_1400D48D8
0x1400d4891  xor     edi, edi
0x1400d4893  mov     rsi, [rcx+rdi*8+20h]
0x1400d4898  mov     eax, [rsi+3Ch]
0x1400d489b  cmp     eax, 1
0x1400d489e  jnz     short loc_1400D48A7
0x1400d48a0  mov     ecx, 80003AABh
0x1400d48a5  jmp     short loc_1400D48B1
0x1400d48a7  cmp     eax, 2
0x1400d48aa  jnz     short loc_1400D48C3
0x1400d48ac  mov     ecx, 80003AACh; int
0x1400d48b1  xor     r9d, r9d
0x1400d48b4  lea     rdx, [rsi+90h]
0x1400d48bb  xor     r8d, r8d
0x1400d48be  call    UlEventLogOneStringEntry
0x1400d48c3  mov     dword ptr [rsi+3Ch], 0
0x1400d48ca  inc     edi
0x1400d48cc  mov     rcx, [rbx+528h]
0x1400d48d3  cmp     edi, [rcx+8]
0x1400d48d6  jb      short loc_1400D4893
0x1400d48d8  mov     rcx, [rbx+558h]
0x1400d48df  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400d48e6  nop     dword ptr [rax+rax+00h]
0x1400d48eb  call    cs:__imp_KeLeaveCriticalRegion
0x1400d48f2  nop     dword ptr [rax+rax+00h]
0x1400d48f7  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d48fe  jz      short loc_1400D491A
0x1400d4900  mov     r9d, [rbp+57h+var_50]
0x1400d4904  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400d490b  mov     edx, 0B1h
0x1400d4910  mov     ecx, 404h
0x1400d4915  call    WPP_SF_d
0x1400d491a  mov     eax, [rbp+57h+var_50]
0x1400d491d  add     rsp, 98h
0x1400d4924  pop     rdi
0x1400d4925  pop     rsi
0x1400d4926  pop     rbx
0x1400d4927  pop     rbp
0x1400d4928  retn
0x1400d492a  mov     r9d, 210Ch; BugCheckParameter4
0x1400d4930  lea     r8, aMinioHttpSysCg; "minio\\http\\sys\\cgroup.c"
0x1400d4937  lea     rdx, [rbp+57h+BugCheckParameter2]; BugCheckParameter2
0x1400d493b  mov     ecx, 1; BugCheckParameter1
0x1400d4940  call    UlBugCheckEx
```
