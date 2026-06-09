# CddBitmap::ColorFillCallback(CLIP_RECTS_DATA *,uint,tagRECT const *)

- ea: `0x14001f5d0`
- end: `0x14001f770`
- name: `?ColorFillCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000df80`
- `0x14000fdb0`
- `0x14001f5d0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001f661`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001f679`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001f661`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001f679`
- `ntoskrnl!DbgPrint` at `0x14001f6fb`
- `ntoskrnl!DbgPrint` at `0x14001f6fb`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001f6e8`
- `watchdog!WdLogSingleEntry1` at `0x14001f5f6`
- `watchdog!WdLogSingleEntry1` at `0x14001f5f6`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f723`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f723`
- `watchdog!WdLogSingleEntry0` at `0x14001f70c`
- `watchdog!WdLogSingleEntry0` at `0x14001f70c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001f60d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001f60d`

## string_xrefs

- `0x14001f6f4`: `Error submitting ColorFill command`

## pseudocode

```c
__int64 __fastcall CddBitmap::ColorFillCallback(struct CLIP_RECTS_DATA *a1, unsigned int a2, const struct tagRECT *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v11; // [rsp+20h] [rbp-18h] BYREF
  __int16 v12; // [rsp+28h] [rbp-10h]
  char v13; // [rsp+2Ah] [rbp-Eh]

  if ( *((_DWORD *)a1 + 22) )
  {
    v11 = *(_QWORD *)(*((_QWORD *)a1 + 10) + 8LL);
    v12 = 257;
    v13 = 0;
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*(_QWORD *)(v11 + 2888));
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*(_QWORD *)(v11 + 2896));
    *((_QWORD *)a1 + 4) = &v11;
    if ( !(unsigned int)CHwCommandBuffer::AddColorFillCommand(
                          *(CDDPDEV ***)(*(_QWORD *)(*((_QWORD *)a1 + 10) + 8LL) + 12696LL),
                          a1,
                          a2,
                          a3)
      && !(unsigned int)CHwCommandBuffer::AddColorFillCommand(
                          *(CDDPDEV ***)(*(_QWORD *)(*((_QWORD *)a1 + 10) + 8LL) + 12696LL),
                          a1,
                          a2,
                          a3)
      && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 10) + 8LL) + 2744LL) & 0x400) == 0
      && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error submitting ColorFill command");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1606;
      v9 = (_QWORD *)WdLogNewEntry5_WdError(v8, v7);
      v9[3] = gCddImageInfo;
      v9[4] = (unsigned int)dword_14003E570;
      v9[5] = 215857758;
      WdLogGlobalForLineNumber = 1606;
      __debugbreak();
    }
    CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)&v11);
  }
  else
  {
    WdLogSingleEntry1(4, *((_QWORD *)a1 + 10));
    WdLogGlobalForLineNumber = 1596;
    v6 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 1596;
  }
  return 0;
}

```

## disassembly

```asm
0x14001f5d0  mov     [rsp+arg_0], rbx
0x14001f5d5  mov     [rsp+arg_8], rsi
0x14001f5da  push    rdi
0x14001f5db  sub     rsp, 30h
0x14001f5df  cmp     dword ptr [rcx+58h], 0
0x14001f5e3  mov     rdi, r8
0x14001f5e6  mov     esi, edx
0x14001f5e8  mov     rbx, rcx
0x14001f5eb  jnz     short loc_14001F641
0x14001f5ed  mov     rdx, [rcx+50h]
0x14001f5f1  mov     ecx, 4
0x14001f5f6  call    cs:__imp_WdLogSingleEntry1
0x14001f5fd  nop     dword ptr [rax+rax+00h]
0x14001f602  mov     ebx, 63Ch
0x14001f607  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f60d  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14001f614  nop     dword ptr [rax+rax+00h]
0x14001f619  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001f620  mov     [rax+18h], rcx
0x14001f624  mov     ecx, cs:dword_14003E570
0x14001f62a  mov     [rax+20h], rcx
0x14001f62e  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001f636  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f63c  jmp     loc_14001F75D
0x14001f641  mov     rax, [rcx+50h]
0x14001f645  mov     rcx, [rax+8]
0x14001f649  mov     [rsp+38h+var_18], rcx
0x14001f64e  mov     [rsp+38h+var_10], 101h
0x14001f655  mov     [rsp+38h+var_E], 0
0x14001f65a  mov     rcx, [rcx+0B48h]
0x14001f661  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001f668  nop     dword ptr [rax+rax+00h]
0x14001f66d  mov     rcx, [rsp+38h+var_18]
0x14001f672  mov     rcx, [rcx+0B50h]
0x14001f679  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001f680  nop     dword ptr [rax+rax+00h]
0x14001f685  lea     rax, [rsp+38h+var_18]
0x14001f68a  mov     r9, rdi; struct tagRECT *
0x14001f68d  mov     [rbx+20h], rax
0x14001f691  mov     r8d, esi; unsigned int
0x14001f694  mov     rax, [rbx+50h]
0x14001f698  mov     rdx, rbx; struct COLORFILL_DATA *
0x14001f69b  mov     rcx, [rax+8]
0x14001f69f  mov     rcx, [rcx+3198h]; this
0x14001f6a6  call    ?AddColorFillCommand@CHwCommandBuffer@@QEAAHPEAUCOLORFILL_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddColorFillCommand(COLORFILL_DATA *,uint,tagRECT const *)
0x14001f6ab  test    eax, eax
0x14001f6ad  jnz     loc_14001F753
0x14001f6b3  mov     rax, [rbx+50h]
0x14001f6b7  mov     r9, rdi; struct tagRECT *
0x14001f6ba  mov     r8d, esi; unsigned int
0x14001f6bd  mov     rdx, rbx; struct COLORFILL_DATA *
0x14001f6c0  mov     rcx, [rax+8]
0x14001f6c4  mov     rcx, [rcx+3198h]; this
0x14001f6cb  call    ?AddColorFillCommand@CHwCommandBuffer@@QEAAHPEAUCOLORFILL_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddColorFillCommand(COLORFILL_DATA *,uint,tagRECT const *)
0x14001f6d0  test    eax, eax
0x14001f6d2  jnz     short loc_14001F753
0x14001f6d4  mov     rax, [rbx+50h]
0x14001f6d8  mov     rcx, [rax+8]
0x14001f6dc  test    dword ptr [rcx+0AB8h], 400h
0x14001f6e6  jnz     short loc_14001F753
0x14001f6e8  mov     rax, cs:KdDebuggerEnabled
0x14001f6ef  cmp     byte ptr [rax], 0
0x14001f6f2  jz      short loc_14001F753
0x14001f6f4  lea     rcx, aErrorSubmittin_2; "Error submitting ColorFill command"
0x14001f6fb  call    cs:__imp_DbgPrint
0x14001f702  nop     dword ptr [rax+rax+00h]
0x14001f707  mov     ecx, 2
0x14001f70c  call    cs:__imp_WdLogSingleEntry0
0x14001f713  nop     dword ptr [rax+rax+00h]
0x14001f718  mov     ebx, 646h
0x14001f71d  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f723  call    cs:__imp_WdLogNewEntry5_WdError
0x14001f72a  nop     dword ptr [rax+rax+00h]
0x14001f72f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001f736  mov     [rax+18h], rcx
0x14001f73a  mov     ecx, cs:dword_14003E570
0x14001f740  mov     [rax+20h], rcx
0x14001f744  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001f74c  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f752  int     3; Trap to Debugger
0x14001f753  lea     rcx, [rsp+38h+var_18]; this
0x14001f758  call    ??1CCommandBufferMutex@@QEAA@XZ; CCommandBufferMutex::~CCommandBufferMutex(void)
0x14001f75d  mov     rbx, [rsp+38h+arg_0]
0x14001f762  xor     eax, eax
0x14001f764  mov     rsi, [rsp+38h+arg_8]
0x14001f769  add     rsp, 30h
0x14001f76d  pop     rdi
0x14001f76e  retn
```
