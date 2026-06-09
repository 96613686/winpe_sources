# CStagingPoolBase::InvalidateStagingPool(_WORKERTHREAD_COMMAND)

- ea: `0x140030bd0`
- end: `0x140030dba`
- name: `?InvalidateStagingPool@CStagingPoolBase@@QEAAXW4_WORKERTHREAD_COMMAND@@@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002e61c`

## callees

- `0x140001a5c`
- `0x1400225ac`
- `0x140030bd0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140030caf`
- `ntoskrnl!KeWaitForSingleObject` at `0x140030d15`
- `ntoskrnl!KeWaitForSingleObject` at `0x140030caf`
- `ntoskrnl!KeWaitForSingleObject` at `0x140030d15`
- `ntoskrnl!KeReleaseSemaphore` at `0x140030d6a`
- `ntoskrnl!KeReleaseSemaphore` at `0x140030d9d`
- `ntoskrnl!KeReleaseSemaphore` at `0x140030d6a`
- `ntoskrnl!KeReleaseSemaphore` at `0x140030d9d`
- `ntoskrnl!DbgPrint` at `0x140030c16`
- `ntoskrnl!DbgPrint` at `0x140030c16`
- `ntoskrnl!KdDebuggerEnabled` at `0x140030c03`
- `watchdog!WdLogNewEntry5_WdError` at `0x140030c3e`
- `watchdog!WdLogNewEntry5_WdError` at `0x140030c3e`
- `watchdog!WdLogSingleEntry0` at `0x140030c27`
- `watchdog!WdLogSingleEntry0` at `0x140030c27`

## string_xrefs

- `0x140030c0f`: `InvalidateStagingPool is not called from the worker thread`

## pseudocode

```c
void __fastcall CStagingPoolBase::InvalidateStagingPool(PVOID *a1, int a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  unsigned int i; // edi
  unsigned int v8; // r8d
  __int64 j; // rdi
  CddBitmapStagingApertureMem *v10; // rcx
  struct _KSEMAPHORE *v11; // rcx
  __int64 v12; // rcx
  char v13; // [rsp+40h] [rbp+8h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+50h] [rbp+18h] BYREF

  if ( *((_DWORD *)a1 + 2) )
  {
    if ( KeGetCurrentThread() != *((struct _KTHREAD **)*a1 + 321) && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("InvalidateStagingPool is not called from the worker thread");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 169;
      v4 = (_QWORD *)WdLogNewEntry5_WdError();
      v4[3] = gCddImageInfo;
      v4[4] = (unsigned int)dword_14003E570;
      v4[5] = 215857758;
      WdLogGlobalForLineNumber = 169;
      __debugbreak();
    }
    v5 = *a1;
    *((_DWORD *)a1 + 2) = 0;
    Timeout.QuadPart = -2000000;
    v13 = 1;
    if ( v5[895] )
    {
      while ( 1 )
      {
        v6 = (_QWORD *)*((_QWORD *)*a1 + 895);
        if ( KeWaitForSingleObject(v6, Executive, 0, 0, &Timeout) != 258 )
          break;
        CDDPDEV::ReleaseClientThread((__int64)*a1, a2, &v13);
      }
      v6[4] = KeGetCurrentThread();
    }
    if ( a1[7] )
    {
      for ( i = 0; i < *((_DWORD *)a1 + 12); ++i )
      {
        while ( KeWaitForSingleObject(a1[7], Executive, 0, 0, &Timeout) == 258 )
          CDDPDEV::ReleaseClientThread((__int64)*a1, a2, &v13);
      }
    }
    v8 = *((_DWORD *)a1 + 12);
    for ( j = 0; (unsigned int)j < v8; j = (unsigned int)(j + 1) )
    {
      v10 = (CddBitmapStagingApertureMem *)a1[j + 8];
      if ( v10 )
        CddBitmapStagingApertureMem::InvalidateDeviceAllocations(v10);
      v8 = *((_DWORD *)a1 + 12);
    }
    v11 = (struct _KSEMAPHORE *)a1[7];
    a1[11] = 0;
    if ( v11 )
      KeReleaseSemaphore(v11, 0, v8, 0);
    v12 = *((_QWORD *)*a1 + 895);
    if ( v12 )
    {
      if ( *(_QWORD *)(v12 + 32) )
      {
        *(_QWORD *)(v12 + 32) = 0;
        KeReleaseSemaphore((PRKSEMAPHORE)v12, 0, 1, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x140030bd0  mov     [rsp+arg_8], rbx
0x140030bd5  mov     [rsp+arg_18], rsi
0x140030bda  push    rdi
0x140030bdb  sub     rsp, 30h
0x140030bdf  cmp     dword ptr [rcx+8], 0
0x140030be3  mov     esi, edx
0x140030be5  mov     rbx, rcx
0x140030be8  jz      loc_140030DA9
0x140030bee  mov     r8, gs:188h
0x140030bf7  mov     rax, [rcx]
0x140030bfa  cmp     r8, [rax+0A08h]
0x140030c01  jz      short loc_140030C6E
0x140030c03  mov     rax, cs:KdDebuggerEnabled
0x140030c0a  cmp     byte ptr [rax], 0
0x140030c0d  jz      short loc_140030C6E
0x140030c0f  lea     rcx, aInvalidatestag; "InvalidateStagingPool is not called fro"...
0x140030c16  call    cs:__imp_DbgPrint
0x140030c1d  nop     dword ptr [rax+rax+00h]
0x140030c22  mov     ecx, 2
0x140030c27  call    cs:__imp_WdLogSingleEntry0
0x140030c2e  nop     dword ptr [rax+rax+00h]
0x140030c33  mov     edi, 0A9h
0x140030c38  mov     cs:WdLogGlobalForLineNumber, edi
0x140030c3e  call    cs:__imp_WdLogNewEntry5_WdError
0x140030c45  nop     dword ptr [rax+rax+00h]
0x140030c4a  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140030c51  mov     [rax+18h], rcx
0x140030c55  mov     ecx, cs:dword_14003E570
0x140030c5b  mov     [rax+20h], rcx
0x140030c5f  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140030c67  mov     cs:WdLogGlobalForLineNumber, edi
0x140030c6d  int     3; Trap to Debugger
0x140030c6e  mov     rax, [rbx]
0x140030c71  mov     dword ptr [rbx+8], 0
0x140030c78  mov     qword ptr [rsp+38h+arg_10], 0FFFFFFFFFFE17B80h
0x140030c81  mov     [rsp+38h+arg_0], 1
0x140030c86  cmp     qword ptr [rax+1BF8h], 0
0x140030c8e  jz      short loc_140030CE0
0x140030c90  mov     rax, [rbx]
0x140030c93  xor     r9d, r9d; Alertable
0x140030c96  xor     r8d, r8d; WaitMode
0x140030c99  xor     edx, edx; WaitReason
0x140030c9b  mov     rdi, [rax+1BF8h]
0x140030ca2  lea     rax, [rsp+38h+arg_10]
0x140030ca7  mov     rcx, rdi; Object
0x140030caa  mov     [rsp+38h+Timeout], rax; Timeout
0x140030caf  call    cs:__imp_KeWaitForSingleObject
0x140030cb6  nop     dword ptr [rax+rax+00h]
0x140030cbb  cmp     eax, 102h
0x140030cc0  jnz     short loc_140030CD3
0x140030cc2  mov     rcx, [rbx]
0x140030cc5  lea     r8, [rsp+38h+arg_0]
0x140030cca  mov     edx, esi
0x140030ccc  call    ?ReleaseClientThread@CDDPDEV@@QEAAXW4_WORKERTHREAD_COMMAND@@PEAE@Z; CDDPDEV::ReleaseClientThread(_WORKERTHREAD_COMMAND,uchar *)
0x140030cd1  jmp     short loc_140030C90
0x140030cd3  mov     rax, gs:188h
0x140030cdc  mov     [rdi+20h], rax
0x140030ce0  cmp     qword ptr [rbx+38h], 0
0x140030ce5  jz      short loc_140030D2F
0x140030ce7  xor     edi, edi
0x140030ce9  cmp     [rbx+30h], edi
0x140030cec  jbe     short loc_140030D2F
0x140030cee  jmp     short loc_140030CFF
0x140030cf0  mov     rcx, [rbx]
0x140030cf3  lea     r8, [rsp+38h+arg_0]
0x140030cf8  mov     edx, esi
0x140030cfa  call    ?ReleaseClientThread@CDDPDEV@@QEAAXW4_WORKERTHREAD_COMMAND@@PEAE@Z; CDDPDEV::ReleaseClientThread(_WORKERTHREAD_COMMAND,uchar *)
0x140030cff  mov     rcx, [rbx+38h]; Object
0x140030d03  lea     rax, [rsp+38h+arg_10]
0x140030d08  xor     r9d, r9d; Alertable
0x140030d0b  mov     [rsp+38h+Timeout], rax; Timeout
0x140030d10  xor     r8d, r8d; WaitMode
0x140030d13  xor     edx, edx; WaitReason
0x140030d15  call    cs:__imp_KeWaitForSingleObject
0x140030d1c  nop     dword ptr [rax+rax+00h]
0x140030d21  cmp     eax, 102h
0x140030d26  jz      short loc_140030CF0
0x140030d28  inc     edi
0x140030d2a  cmp     edi, [rbx+30h]
0x140030d2d  jb      short loc_140030CFF
0x140030d2f  mov     r8d, [rbx+30h]
0x140030d33  xor     edi, edi
0x140030d35  test    r8d, r8d
0x140030d38  jz      short loc_140030D54
0x140030d3a  mov     rcx, [rbx+rdi*8+40h]; this
0x140030d3f  test    rcx, rcx
0x140030d42  jz      short loc_140030D49
0x140030d44  call    ?InvalidateDeviceAllocations@CddBitmapStagingApertureMem@@QEAAXXZ; CddBitmapStagingApertureMem::InvalidateDeviceAllocations(void)
0x140030d49  mov     r8d, [rbx+30h]; Adjustment
0x140030d4d  inc     edi
0x140030d4f  cmp     edi, r8d
0x140030d52  jb      short loc_140030D3A
0x140030d54  mov     rcx, [rbx+38h]; Semaphore
0x140030d58  mov     qword ptr [rbx+58h], 0
0x140030d60  test    rcx, rcx
0x140030d63  jz      short loc_140030D76
0x140030d65  xor     r9d, r9d; Wait
0x140030d68  xor     edx, edx; Increment
0x140030d6a  call    cs:__imp_KeReleaseSemaphore
0x140030d71  nop     dword ptr [rax+rax+00h]
0x140030d76  mov     rax, [rbx]
0x140030d79  mov     rcx, [rax+1BF8h]; Semaphore
0x140030d80  test    rcx, rcx
0x140030d83  jz      short loc_140030DA9
0x140030d85  cmp     qword ptr [rcx+20h], 0
0x140030d8a  jz      short loc_140030DA9
0x140030d8c  xor     r9d, r9d; Wait
0x140030d8f  mov     qword ptr [rcx+20h], 0
0x140030d97  xor     edx, edx; Increment
0x140030d99  lea     r8d, [r9+1]; Adjustment
0x140030d9d  call    cs:__imp_KeReleaseSemaphore
0x140030da4  nop     dword ptr [rax+rax+00h]
0x140030da9  mov     rbx, [rsp+38h+arg_8]
0x140030dae  mov     rsi, [rsp+38h+arg_18]
0x140030db3  add     rsp, 30h
0x140030db7  pop     rdi
0x140030db8  retn
```
