# UlNotifyIPListenListChanges

- ea: `0x1400d483c`
- end: `0x1400d4a26`
- name: `UlNotifyIPListenListChanges`
- size: `490`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x14012eb54`
- `0x14012ee90`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140024bac`
- `0x1400d483c`
- `0x1400d77f8`
- `0x140167b40`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400d4949`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d4949`
- `ntoskrnl!KeInitializeEvent` at `0x1400d48a1`
- `ntoskrnl!KeInitializeEvent` at `0x1400d48a1`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d49bf`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d49bf`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d48dc`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d48dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d49cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d49cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d48c9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d48c9`

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
    WPP_SF_qq(1028, 176, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, a1, a2);
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
    UlBugCheckEx(1u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)"minio\\http\\sys\\cgroup.c", 0x2103u);
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
    WPP_SF_d(1028, 177, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, *(unsigned int *)&BugCheckParameter2[48]);
  return *(unsigned int *)&BugCheckParameter2[48];
}

```

## disassembly

```asm
0x1400d483c  push    rbp
0x1400d483e  push    rbx
0x1400d483f  push    rsi
0x1400d4840  push    rdi
0x1400d4841  lea     rbp, [rsp-3Fh]
0x1400d4846  sub     rsp, 98h
0x1400d484d  mov     rdi, rdx
0x1400d4850  mov     rbx, rcx
0x1400d4853  xor     edx, edx; Val
0x1400d4855  lea     rcx, [rbp+57h+BugCheckParameter2]; void *
0x1400d4859  lea     r8d, [rdx+60h]; Size
0x1400d485d  call    memset
0x1400d4862  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d4869  jz      short loc_1400D4889
0x1400d486b  mov     edx, 0B0h
0x1400d4870  mov     [rsp+0B0h+Timeout], rdi
0x1400d4875  mov     ecx, 404h
0x1400d487a  lea     r8, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids
0x1400d4881  mov     r9, rbx
0x1400d4884  call    WPP_SF_qq
0x1400d4889  xor     r8d, r8d; State
0x1400d488c  mov     [rbp+57h+var_50], 103h
0x1400d4893  xor     edx, edx; Type
0x1400d4895  mov     [rbp+57h+var_48], 0
0x1400d489d  lea     rcx, [rbp+57h+Event]; Event
0x1400d48a1  call    cs:__imp_KeInitializeEvent
0x1400d48a8  nop     dword ptr [rax+rax+00h]
0x1400d48ad  mov     [rbp+57h+BugCheckParameter2], 0
0x1400d48b5  mov     [rbp+57h+var_70], 0
0x1400d48bd  mov     [rbp+57h+var_60], 0
0x1400d48c5  mov     [rbp+57h+var_28], rdi
0x1400d48c9  call    cs:__imp_KeEnterCriticalRegion
0x1400d48d0  nop     dword ptr [rax+rax+00h]
0x1400d48d5  mov     rcx, [rbx+558h]
0x1400d48dc  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d48e3  nop     dword ptr [rax+rax+00h]
0x1400d48e8  cmp     [rbp+57h+BugCheckParameter2], 0
0x1400d48ed  jnz     loc_1400D4A0A
0x1400d48f3  cmp     [rbp+57h+var_70], 0
0x1400d48f8  jnz     loc_1400D4A0A
0x1400d48fe  cmp     [rbp+57h+var_60], 0
0x1400d4903  jnz     loc_1400D4A0A
0x1400d4909  mov     [rsp+0B0h+var_88], 0FFFFFFFFh
0x1400d4911  lea     r8, UxTlUpdateListenAddressList
0x1400d4918  mov     r9b, 1
0x1400d491b  mov     [rsp+0B0h+Timeout], 0FFFFFFFFFFFFFFFFh
0x1400d4924  lea     rdx, [rbp+57h+BugCheckParameter2]
0x1400d4928  mov     ecx, 2
0x1400d492d  call    UlThreadPoolEnqueueWorkItem
0x1400d4932  xor     r9d, r9d; Alertable
0x1400d4935  mov     [rsp+0B0h+Timeout], 0; Timeout
0x1400d493e  xor     r8d, r8d; WaitMode
0x1400d4941  lea     rcx, [rbp+57h+Event]; Object
0x1400d4945  lea     edx, [r9+6]; WaitReason
0x1400d4949  call    cs:__imp_KeWaitForSingleObject
0x1400d4950  nop     dword ptr [rax+rax+00h]
0x1400d4955  lea     rdx, UlpNotifyIPListenListChangesOfServerSession
0x1400d495c  mov     rcx, rbx
0x1400d495f  call    UlNotifyForAllChannels
0x1400d4964  mov     rcx, [rbx+528h]
0x1400d496b  cmp     dword ptr [rcx+8], 0
0x1400d496f  jbe     short loc_1400D49B8
0x1400d4971  xor     edi, edi
0x1400d4973  mov     rsi, [rcx+rdi*8+20h]
0x1400d4978  mov     eax, [rsi+3Ch]
0x1400d497b  cmp     eax, 1
0x1400d497e  jnz     short loc_1400D4987
0x1400d4980  mov     ecx, 80003AABh
0x1400d4985  jmp     short loc_1400D4991
0x1400d4987  cmp     eax, 2
0x1400d498a  jnz     short loc_1400D49A3
0x1400d498c  mov     ecx, 80003AACh; int
0x1400d4991  xor     r9d, r9d
0x1400d4994  lea     rdx, [rsi+90h]
0x1400d499b  xor     r8d, r8d
0x1400d499e  call    UlEventLogOneStringEntry
0x1400d49a3  mov     dword ptr [rsi+3Ch], 0
0x1400d49aa  inc     edi
0x1400d49ac  mov     rcx, [rbx+528h]
0x1400d49b3  cmp     edi, [rcx+8]
0x1400d49b6  jb      short loc_1400D4973
0x1400d49b8  mov     rcx, [rbx+558h]
0x1400d49bf  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400d49c6  nop     dword ptr [rax+rax+00h]
0x1400d49cb  call    cs:__imp_KeLeaveCriticalRegion
0x1400d49d2  nop     dword ptr [rax+rax+00h]
0x1400d49d7  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d49de  jz      short loc_1400D49FA
0x1400d49e0  mov     r9d, [rbp+57h+var_50]
0x1400d49e4  lea     r8, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids
0x1400d49eb  mov     edx, 0B1h
0x1400d49f0  mov     ecx, 404h
0x1400d49f5  call    WPP_SF_d
0x1400d49fa  mov     eax, [rbp+57h+var_50]
0x1400d49fd  add     rsp, 98h
0x1400d4a04  pop     rdi
0x1400d4a05  pop     rsi
0x1400d4a06  pop     rbx
0x1400d4a07  pop     rbp
0x1400d4a08  retn
0x1400d4a0a  mov     r9d, 2103h; BugCheckParameter4
0x1400d4a10  lea     r8, aMinioHttpSysCg; "minio\\http\\sys\\cgroup.c"
0x1400d4a17  lea     rdx, [rbp+57h+BugCheckParameter2]; BugCheckParameter2
0x1400d4a1b  mov     ecx, 1; BugCheckParameter1
0x1400d4a20  call    UlBugCheckEx
```
