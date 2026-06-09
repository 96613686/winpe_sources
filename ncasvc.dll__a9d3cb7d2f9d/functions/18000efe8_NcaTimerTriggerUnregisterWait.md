# NcaTimerTriggerUnregisterWait

- ea: `0x18000efe8`
- end: `0x18000f086`
- name: `NcaTimerTriggerUnregisterWait`
- size: `158`
- prototype: `__int64 __fastcall(PTP_TIMER *lpMem)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011bc0`

## callees

- `0x180003770`
- `0x180004f34`
- `0x18000efe8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f040`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f040`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f052`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f052`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f061`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f061`

## pseudocode

```c
__int64 __fastcall NcaTimerTriggerUnregisterWait(PTP_TIMER *lpMem)
{
  unsigned int v2; // edi
  struct _TP_TIMER *v3; // rcx

  if ( lpMem )
  {
    v3 = *lpMem;
    v2 = 0;
    if ( v3 )
    {
      SetThreadpoolTimer(v3, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*lpMem, 1);
      CloseThreadpoolTimer(*lpMem);
      *lpMem = 0;
    }
    NcaFree(lpMem);
  }
  else
  {
    v2 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_5d0151c57d1438c04f8a181df6bf2fb2_Traceguids, 87);
  }
  return v2;
}

```

## disassembly

```asm
0x18000efe8  mov     [rsp+arg_0], rbx
0x18000efed  push    rdi
0x18000efee  sub     rsp, 20h
0x18000eff2  mov     rbx, rcx
0x18000eff5  test    rcx, rcx
0x18000eff8  jnz     short loc_18000F02E
0x18000effa  lea     edi, [rcx+57h]
0x18000effd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f004  lea     rax, WPP_GLOBAL_Control
0x18000f00b  cmp     rcx, rax
0x18000f00e  jz      short loc_18000F078
0x18000f010  test    byte ptr [rcx+1Ch], 1
0x18000f014  jz      short loc_18000F078
0x18000f016  mov     rcx, [rcx+10h]
0x18000f01a  lea     edx, [rbx+0Dh]
0x18000f01d  mov     r9d, edi
0x18000f020  lea     r8, WPP_5d0151c57d1438c04f8a181df6bf2fb2_Traceguids
0x18000f027  call    WPP_SF_d
0x18000f02c  jmp     short loc_18000F078
0x18000f02e  mov     rcx, [rcx]; pti
0x18000f031  xor     edi, edi
0x18000f033  test    rcx, rcx
0x18000f036  jz      short loc_18000F070
0x18000f038  xor     r9d, r9d; msWindowLength
0x18000f03b  xor     r8d, r8d; msPeriod
0x18000f03e  xor     edx, edx; pftDueTime
0x18000f040  call    cs:__imp_SetThreadpoolTimer
0x18000f047  nop     dword ptr [rax+rax+00h]
0x18000f04c  mov     rcx, [rbx]; pti
0x18000f04f  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x18000f052  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f059  nop     dword ptr [rax+rax+00h]
0x18000f05e  mov     rcx, [rbx]; pti
0x18000f061  call    cs:__imp_CloseThreadpoolTimer
0x18000f068  nop     dword ptr [rax+rax+00h]
0x18000f06d  mov     [rbx], rdi
0x18000f070  mov     rcx, rbx; lpMem
0x18000f073  call    NcaFree
0x18000f078  mov     rbx, [rsp+28h+arg_0]
0x18000f07d  mov     eax, edi
0x18000f07f  add     rsp, 20h
0x18000f083  pop     rdi
0x18000f084  retn
```
