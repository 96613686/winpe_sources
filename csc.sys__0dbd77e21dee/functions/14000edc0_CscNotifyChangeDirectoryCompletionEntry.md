# CscNotifyChangeDirectoryCompletionEntry

- ea: `0x14000edc0`
- end: `0x14000eee3`
- name: `CscNotifyChangeDirectoryCompletionEntry`
- size: `291`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000a4f0`
- `0x14000edc0`
- `0x14000eef0`
- `0x140018930`
- `0x140020028`
- `0x14006eba0`

## import_xrefs

- `rdbss!RxLowIoCompletion` at `0x14000ee5a`
- `rdbss!RxPostToWorkerThread` at `0x14000ee87`
- `rdbss!RxPostToWorkerThread` at `0x14000ee87`

## pseudocode

```c
__int64 __fastcall CscNotifyChangeDirectoryCompletionEntry(unsigned int *pContext)
{
  __int64 v2; // rax
  char v3; // r8
  __int64 v4; // rdi
  __int64 v5; // rcx
  unsigned int v6; // ebx

  v2 = CscFcbContext(*((_QWORD *)pContext + 7));
  v4 = v2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    if ( v2 )
      LODWORD(v2) = *(_DWORD *)(v2 + 4);
    WPP_SF_qDqd(
      WPP_GLOBAL_Control->AttachedDevice,
      55,
      (unsigned int)WPP_f1d0093ed16337749994f41f70b429cb_Traceguids,
      (_DWORD)pContext,
      pContext[44],
      v3,
      v2);
  }
  v5 = pContext[44];
  if ( (int)v5 >= 0
    || !(unsigned __int8)CscTransitnOKToGoOffline(v5)
    || !v4
    || (*(_DWORD *)(v4 + 4) & 0x1000000) != 0
    || (*((_BYTE *)pContext + 522) & 1) != 0 )
  {
    v6 = CscNotifyChangeDirectoryCompletion((PMRX_FCB)pContext);
  }
  else
  {
    *((_QWORD *)pContext + 66) = CscNotifyChangeDirectoryCompletion;
    RxPostToWorkerThread(
      (PRDBSS_DEVICE_OBJECT)CscDeviceObject,
      HyperCriticalWorkQueue,
      (PRX_WORK_QUEUE_ITEM)(pContext + 76),
      (PRX_WORKERTHREAD_ROUTINE)RxLowIoCompletion,
      pContext);
    v6 = -1071906810;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x14000edc0  mov     [rsp+arg_0], rbx
0x14000edc5  mov     [rsp+arg_8], rsi
0x14000edca  push    rdi
0x14000edcb  sub     rsp, 40h
0x14000edcf  mov     r8, [rcx+38h]
0x14000edd3  mov     rbx, rcx
0x14000edd6  mov     rcx, r8
0x14000edd9  call    CscFcbContext
0x14000edde  mov     rdi, rax
0x14000ede1  mov     r10, cs:WPP_GLOBAL_Control
0x14000ede8  lea     rsi, WPP_GLOBAL_Control
0x14000edef  cmp     r10, rsi
0x14000edf2  jz      short loc_14000EE30
0x14000edf4  mov     ecx, [r10+2Ch]
0x14000edf8  test    cl, 20h
0x14000edfb  jz      short loc_14000EE30
0x14000edfd  test    rax, rax
0x14000ee00  jz      short loc_14000EE05
0x14000ee02  mov     eax, [rax+4]
0x14000ee05  mov     rcx, [r10+18h]
0x14000ee09  mov     edx, 37h ; '7'
0x14000ee0e  mov     [rsp+48h+var_18], eax
0x14000ee12  mov     r9, rbx
0x14000ee15  mov     eax, [rbx+0B0h]
0x14000ee1b  mov     [rsp+48h+var_20], r8
0x14000ee20  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x14000ee27  mov     dword ptr [rsp+48h+pContext], eax
0x14000ee2b  call    WPP_SF_qDqd
0x14000ee30  mov     ecx, [rbx+0B0h]
0x14000ee36  test    ecx, ecx
0x14000ee38  jns     short loc_14000EE9A
0x14000ee3a  call    CscTransitnOKToGoOffline
0x14000ee3f  test    al, al
0x14000ee41  jz      short loc_14000EE9A
0x14000ee43  test    rdi, rdi
0x14000ee46  jz      short loc_14000EE9A
0x14000ee48  test    dword ptr [rdi+4], 1000000h
0x14000ee4f  jnz     short loc_14000EE9A
0x14000ee51  test    byte ptr [rbx+20Ah], 1
0x14000ee58  jnz     short loc_14000EE9A
0x14000ee5a  mov     r9, cs:__imp_RxLowIoCompletion; Routine
0x14000ee61  lea     rax, CscNotifyChangeDirectoryCompletion
0x14000ee68  mov     [rbx+210h], rax
0x14000ee6f  lea     r8, [rbx+130h]; pWorkQueueItem
0x14000ee76  mov     rcx, cs:CscDeviceObject; pMRxDeviceObject
0x14000ee7d  mov     edx, 2; WorkQueueType
0x14000ee82  mov     [rsp+48h+pContext], rbx; pContext
0x14000ee87  call    cs:__imp_RxPostToWorkerThread
0x14000ee8e  nop     dword ptr [rax+rax+00h]
0x14000ee93  mov     ebx, 0C01C0006h
0x14000ee98  jmp     short loc_14000EEA4
0x14000ee9a  mov     rcx, rbx; Fcb
0x14000ee9d  call    CscNotifyChangeDirectoryCompletion
0x14000eea2  mov     ebx, eax
0x14000eea4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eeab  cmp     rcx, rsi
0x14000eeae  jz      short loc_14000EED0
0x14000eeb0  mov     edx, [rcx+2Ch]
0x14000eeb3  test    dl, 20h
0x14000eeb6  jz      short loc_14000EED0
0x14000eeb8  mov     rcx, [rcx+18h]
0x14000eebc  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x14000eec3  mov     edx, 38h ; '8'
0x14000eec8  mov     r9d, ebx
0x14000eecb  call    WPP_SF_d
0x14000eed0  mov     rsi, [rsp+48h+arg_8]
0x14000eed5  mov     eax, ebx
0x14000eed7  mov     rbx, [rsp+48h+arg_0]
0x14000eedc  add     rsp, 40h
0x14000eee0  pop     rdi
0x14000eee1  retn
```
