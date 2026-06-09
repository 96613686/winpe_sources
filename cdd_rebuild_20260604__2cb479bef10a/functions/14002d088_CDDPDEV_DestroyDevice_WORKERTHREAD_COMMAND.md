# CDDPDEV::DestroyDevice(_WORKERTHREAD_COMMAND)

- ea: `0x14002d088`
- end: `0x14002d222`
- name: `?DestroyDevice@CDDPDEV@@QEAAXW4_WORKERTHREAD_COMMAND@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011510`
- `0x140021d5c`
- `0x140022c28`

## callees

- `0x14002cf5c`
- `0x14002d088`
- `0x14002d228`
- `0x14002e61c`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x14002d0ac`
- `watchdog!WdLogSingleEntry2` at `0x14002d0ac`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002d142`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002d1c8`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002d142`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002d1c8`
- `watchdog!WdLogSingleEntry0` at `0x14002d12b`
- `watchdog!WdLogSingleEntry0` at `0x14002d1b1`
- `watchdog!WdLogSingleEntry0` at `0x14002d12b`
- `watchdog!WdLogSingleEntry0` at `0x14002d1b1`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002d0c2`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002d0c2`

## pseudocode

```c
_QWORD *__fastcall CDDPDEV::DestroyDevice(__int64 a1, unsigned int a2)
{
  _QWORD *result; // rax
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  bool v11; // [rsp+20h] [rbp-18h]

  WdLogSingleEntry2(4, a1, *(unsigned int *)(a1 + 784));
  WdLogGlobalForLineNumber = 2093;
  result = (_QWORD *)WdLogNewEntry5_WdEvent();
  v5 = (unsigned int)dword_14003E570;
  result[3] = gCddImageInfo;
  result[4] = v5;
  result[5] = 215857758;
  WdLogGlobalForLineNumber = 2093;
  if ( (*(_DWORD *)(a1 + 2744) & 0x100) != 0 )
    result = (_QWORD *)CDDPDEV::InvalidateInternalBitmaps(a1, a2);
  if ( *(_DWORD *)(a1 + 2520) )
  {
    if ( (int)CDDPDEV::DestroyResidencyState((CDDPDEV *)a1) < 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2105;
      v8 = (_QWORD *)WdLogNewEntry5_WdAssertion(v7, v6);
      v8[3] = gCddImageInfo;
      v8[4] = (unsigned int)dword_14003E570;
      v8[5] = 215857758;
      WdLogGlobalForLineNumber = 2105;
    }
    CDDPDEV::DestroyBootGraphicsRelayAnimation((CDDPDEV *)a1);
    v11 = (*(_DWORD *)(a1 + 2744) & 0x400) != 0;
    result = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, bool))(a1 + 96))(
                         *(unsigned int *)(a1 + 2520),
                         *(unsigned int *)(a1 + 2524),
                         *(unsigned int *)(a1 + 2528),
                         *(_QWORD *)(a1 + 2488),
                         v11);
    if ( (int)result < 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2111;
      result = (_QWORD *)WdLogNewEntry5_WdAssertion(v10, v9);
      result[3] = gCddImageInfo;
      result[4] = (unsigned int)dword_14003E570;
      result[5] = 215857758;
      WdLogGlobalForLineNumber = 2111;
    }
  }
  *(_DWORD *)(a1 + 2744) |= 0x400u;
  *(_QWORD *)(a1 + 2520) = 0;
  *(_DWORD *)(a1 + 2528) = 0;
  return result;
}

```

## disassembly

```asm
0x14002d088  mov     [rsp+arg_0], rbx
0x14002d08d  mov     [rsp+arg_8], rdi
0x14002d092  push    r14
0x14002d094  sub     rsp, 30h
0x14002d098  mov     edi, edx
0x14002d09a  mov     rbx, rcx
0x14002d09d  mov     r8d, [rcx+310h]
0x14002d0a4  mov     rdx, rcx
0x14002d0a7  mov     ecx, 4
0x14002d0ac  call    cs:__imp_WdLogSingleEntry2
0x14002d0b3  nop     dword ptr [rax+rax+00h]
0x14002d0b8  mov     cs:WdLogGlobalForLineNumber, 82Dh
0x14002d0c2  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14002d0c9  nop     dword ptr [rax+rax+00h]
0x14002d0ce  mov     r8, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d0d5  mov     r14d, 0CDDBA5Eh
0x14002d0db  mov     edx, cs:dword_14003E570
0x14002d0e1  mov     [rax+18h], r8
0x14002d0e5  mov     [rax+20h], rdx
0x14002d0e9  mov     [rax+28h], r14
0x14002d0ed  mov     cs:WdLogGlobalForLineNumber, 82Dh
0x14002d0f7  test    dword ptr [rbx+0AB8h], 100h
0x14002d101  jz      short loc_14002D10D
0x14002d103  mov     edx, edi
0x14002d105  mov     rcx, rbx
0x14002d108  call    ?InvalidateInternalBitmaps@CDDPDEV@@QEAAXW4_WORKERTHREAD_COMMAND@@@Z; CDDPDEV::InvalidateInternalBitmaps(_WORKERTHREAD_COMMAND)
0x14002d10d  cmp     dword ptr [rbx+9D8h], 0
0x14002d114  jz      loc_14002D1F3
0x14002d11a  mov     rcx, rbx; this
0x14002d11d  call    ?DestroyResidencyState@CDDPDEV@@QEAAJXZ; CDDPDEV::DestroyResidencyState(void)
0x14002d122  test    eax, eax
0x14002d124  jns     short loc_14002D16D
0x14002d126  mov     ecx, 1
0x14002d12b  call    cs:__imp_WdLogSingleEntry0
0x14002d132  nop     dword ptr [rax+rax+00h]
0x14002d137  mov     edi, 839h
0x14002d13c  mov     cs:WdLogGlobalForLineNumber, edi
0x14002d142  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002d149  nop     dword ptr [rax+rax+00h]
0x14002d14e  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d155  mov     [rax+18h], rcx
0x14002d159  mov     ecx, cs:dword_14003E570
0x14002d15f  mov     [rax+20h], rcx
0x14002d163  mov     [rax+28h], r14
0x14002d167  mov     cs:WdLogGlobalForLineNumber, edi
0x14002d16d  mov     rcx, rbx; this
0x14002d170  call    ?DestroyBootGraphicsRelayAnimation@CDDPDEV@@QEAAXXZ; CDDPDEV::DestroyBootGraphicsRelayAnimation(void)
0x14002d175  mov     edx, [rbx+0AB8h]
0x14002d17b  mov     rax, [rbx+60h]
0x14002d17f  mov     r9, [rbx+9B8h]
0x14002d186  mov     r8d, [rbx+9E0h]
0x14002d18d  mov     ecx, [rbx+9D8h]
0x14002d193  shr     edx, 0Ah
0x14002d196  and     dl, 1
0x14002d199  mov     [rsp+38h+var_18], dl
0x14002d19d  mov     edx, [rbx+9DCh]
0x14002d1a3  call    _guard_dispatch_icall
0x14002d1a8  test    eax, eax
0x14002d1aa  jns     short loc_14002D1F3
0x14002d1ac  mov     ecx, 1
0x14002d1b1  call    cs:__imp_WdLogSingleEntry0
0x14002d1b8  nop     dword ptr [rax+rax+00h]
0x14002d1bd  mov     edi, 83Fh
0x14002d1c2  mov     cs:WdLogGlobalForLineNumber, edi
0x14002d1c8  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002d1cf  nop     dword ptr [rax+rax+00h]
0x14002d1d4  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d1db  mov     [rax+18h], rcx
0x14002d1df  mov     ecx, cs:dword_14003E570
0x14002d1e5  mov     [rax+20h], rcx
0x14002d1e9  mov     [rax+28h], r14
0x14002d1ed  mov     cs:WdLogGlobalForLineNumber, edi
0x14002d1f3  bts     dword ptr [rbx+0AB8h], 0Ah
0x14002d1fb  mov     rdi, [rsp+38h+arg_8]
0x14002d200  mov     qword ptr [rbx+9D8h], 0
0x14002d20b  mov     dword ptr [rbx+9E0h], 0
0x14002d215  mov     rbx, [rsp+38h+arg_0]
0x14002d21a  add     rsp, 30h
0x14002d21e  pop     r14
0x14002d220  retn
```
