# CStagingPoolBase::PickFreeStagingBitmap(void)

- ea: `0x14001eda8`
- end: `0x14001ef23`
- name: `?PickFreeStagingBitmap@CStagingPoolBase@@IEAAJXZ`
- size: `379`
- prototype: `__int64 __fastcall(CStagingPoolBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cf80`
- `0x14002ee20`

## callees

- `0x14001eda8`
- `0x14001ef2c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001ede9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ede9`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001eea9`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001eea9`
- `ntoskrnl!DbgPrint` at `0x14001ee41`
- `ntoskrnl!DbgPrint` at `0x14001ee41`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001ee2e`
- `watchdog!WdLogSingleEntry1` at `0x14001eed6`
- `watchdog!WdLogSingleEntry1` at `0x14001eed6`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001ee68`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001eeed`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001ee68`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001eeed`
- `watchdog!WdLogSingleEntry0` at `0x14001ee52`
- `watchdog!WdLogSingleEntry0` at `0x14001ee52`

## string_xrefs

- `0x14001ee3a`: `The bitmap with no GDI access was not found`

## pseudocode

```c
__int64 __fastcall CStagingPoolBase::PickFreeStagingBitmap(CStagingPoolBase *this)
{
  __int64 v2; // rbx
  NTSTATUS v3; // eax
  unsigned int v4; // ecx
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rax

  v2 = *(_QWORD *)(*((_QWORD *)this + 11) + 152LL) - 152LL;
  if ( !*(_DWORD *)(v2 + 144) )
  {
LABEL_10:
    CStagingPoolBase::SetCurrentBitmap(this, (struct CddBitmapStagingApertureMem *)v2);
    return 0;
  }
  v3 = KeWaitForSingleObject(*((PVOID *)this + 7), Executive, 0, 0, 0);
  if ( !v3 )
  {
    v4 = *((_DWORD *)this + 12);
    if ( v4 )
    {
      while ( *(_DWORD *)(v2 + 144) )
      {
        ++v3;
        v2 = *(_QWORD *)(v2 + 152) - 152LL;
        if ( v3 >= v4 )
          goto LABEL_6;
      }
    }
    else
    {
LABEL_6:
      if ( *(_DWORD *)(v2 + 144) )
      {
        if ( (_BYTE)KdDebuggerEnabled )
        {
          DbgPrint("The bitmap with no GDI access was not found");
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 303;
          v7 = (_QWORD *)WdLogNewEntry5_WdError(v6, v5);
          v7[3] = gCddImageInfo;
          v7[4] = (unsigned int)dword_14003E570;
          v7[5] = 215857758;
          WdLogGlobalForLineNumber = 303;
          __debugbreak();
        }
      }
    }
    KeReleaseSemaphore(*((PRKSEMAPHORE *)this + 7), 0, 1, 0);
    goto LABEL_10;
  }
  WdLogSingleEntry1(2, v3);
  WdLogGlobalForLineNumber = 310;
  v11 = (_QWORD *)WdLogNewEntry5_WdError(v10, v9);
  v11[3] = gCddImageInfo;
  v11[4] = (unsigned int)dword_14003E570;
  v11[5] = 215857758;
  result = 3221225473LL;
  WdLogGlobalForLineNumber = 310;
  return result;
}

```

## disassembly

```asm
0x14001eda8  mov     [rsp+arg_0], rbx
0x14001edad  push    rdi
0x14001edae  sub     rsp, 30h
0x14001edb2  mov     rax, [rcx+58h]
0x14001edb6  mov     rdi, rcx
0x14001edb9  mov     rbx, [rax+98h]
0x14001edc0  sub     rbx, 98h
0x14001edc7  cmp     dword ptr [rbx+90h], 0
0x14001edce  jbe     loc_14001EEB5
0x14001edd4  mov     rcx, [rcx+38h]; Object
0x14001edd8  xor     r9d, r9d; Alertable
0x14001eddb  xor     r8d, r8d; WaitMode
0x14001edde  mov     [rsp+38h+Timeout], 0; Timeout
0x14001ede7  xor     edx, edx; WaitReason
0x14001ede9  call    cs:__imp_KeWaitForSingleObject
0x14001edf0  nop     dword ptr [rax+rax+00h]
0x14001edf5  test    eax, eax
0x14001edf7  jnz     loc_14001EECE
0x14001edfd  mov     ecx, [rdi+30h]
0x14001ee00  test    ecx, ecx
0x14001ee02  jz      short loc_14001EE25
0x14001ee04  cmp     dword ptr [rbx+90h], 0
0x14001ee0b  jz      loc_14001EE9C
0x14001ee11  mov     rbx, [rbx+98h]
0x14001ee18  inc     eax
0x14001ee1a  sub     rbx, 98h
0x14001ee21  cmp     eax, ecx
0x14001ee23  jb      short loc_14001EE04
0x14001ee25  cmp     dword ptr [rbx+90h], 0
0x14001ee2c  jz      short loc_14001EE9C
0x14001ee2e  mov     rax, cs:KdDebuggerEnabled
0x14001ee35  cmp     byte ptr [rax], 0
0x14001ee38  jz      short loc_14001EE9C
0x14001ee3a  lea     rcx, aTheBitmapWithN; "The bitmap with no GDI access was not f"...
0x14001ee41  call    cs:__imp_DbgPrint
0x14001ee48  nop     dword ptr [rax+rax+00h]
0x14001ee4d  mov     ecx, 2
0x14001ee52  call    cs:__imp_WdLogSingleEntry0
0x14001ee59  nop     dword ptr [rax+rax+00h]
0x14001ee5e  mov     cs:WdLogGlobalForLineNumber, 12Fh
0x14001ee68  call    cs:__imp_WdLogNewEntry5_WdError
0x14001ee6f  nop     dword ptr [rax+rax+00h]
0x14001ee74  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001ee7b  mov     [rax+18h], rcx
0x14001ee7f  mov     ecx, cs:dword_14003E570
0x14001ee85  mov     [rax+20h], rcx
0x14001ee89  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001ee91  mov     cs:WdLogGlobalForLineNumber, 12Fh
0x14001ee9b  int     3; Trap to Debugger
0x14001ee9c  mov     rcx, [rdi+38h]; Semaphore
0x14001eea0  xor     r9d, r9d; Wait
0x14001eea3  xor     edx, edx; Increment
0x14001eea5  lea     r8d, [r9+1]; Adjustment
0x14001eea9  call    cs:__imp_KeReleaseSemaphore
0x14001eeb0  nop     dword ptr [rax+rax+00h]
0x14001eeb5  mov     rdx, rbx; struct CddBitmapStagingApertureMem *
0x14001eeb8  mov     rcx, rdi; this
0x14001eebb  call    ?SetCurrentBitmap@CStagingPoolBase@@IEAAXPEAVCddBitmapStagingApertureMem@@@Z; CStagingPoolBase::SetCurrentBitmap(CddBitmapStagingApertureMem *)
0x14001eec0  xor     eax, eax
0x14001eec2  mov     rbx, [rsp+38h+arg_0]
0x14001eec7  add     rsp, 30h
0x14001eecb  pop     rdi
0x14001eecc  retn
0x14001eece  movsxd  rdx, eax
0x14001eed1  mov     ecx, 2
0x14001eed6  call    cs:__imp_WdLogSingleEntry1
0x14001eedd  nop     dword ptr [rax+rax+00h]
0x14001eee2  mov     ebx, 136h
0x14001eee7  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001eeed  call    cs:__imp_WdLogNewEntry5_WdError
0x14001eef4  nop     dword ptr [rax+rax+00h]
0x14001eef9  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001ef00  mov     [rax+18h], rcx
0x14001ef04  mov     ecx, cs:dword_14003E570
0x14001ef0a  mov     [rax+20h], rcx
0x14001ef0e  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001ef16  mov     eax, 0C0000001h
0x14001ef1b  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001ef21  jmp     short loc_14001EEC2
```
