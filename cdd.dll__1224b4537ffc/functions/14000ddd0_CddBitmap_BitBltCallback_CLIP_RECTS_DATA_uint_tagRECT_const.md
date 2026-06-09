# CddBitmap::BitBltCallback(CLIP_RECTS_DATA *,uint,tagRECT const *)

- ea: `0x14000ddd0`
- end: `0x14000df73`
- name: `?BitBltCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000ddd0`
- `0x14000df80`
- `0x14000f370`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000de6b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000de83`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000de6b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000de83`
- `ntoskrnl!DbgPrint` at `0x14000df16`
- `ntoskrnl!DbgPrint` at `0x14000df16`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000df03`
- `watchdog!WdLogSingleEntry1` at `0x14000ddf6`
- `watchdog!WdLogSingleEntry1` at `0x14000ddf6`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000df3e`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000df3e`
- `watchdog!WdLogSingleEntry0` at `0x14000df27`
- `watchdog!WdLogSingleEntry0` at `0x14000df27`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000de0d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000de0d`

## string_xrefs

- `0x14000df0f`: `Error submitting BitBlt command`

## pseudocode

```c
__int64 __fastcall CddBitmap::BitBltCallback(struct CLIP_RECTS_DATA *a1, unsigned int a2, const struct tagRECT *a3)
{
  _QWORD *v6; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // [rsp+30h] [rbp-18h] BYREF
  __int16 v11; // [rsp+38h] [rbp-10h]
  char v12; // [rsp+3Ah] [rbp-Eh]

  if ( *((_DWORD *)a1 + 25) )
  {
    v10 = *((_QWORD *)a1 + 9);
    v11 = 257;
    v12 = 0;
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*(_QWORD *)(v10 + 2888));
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*(_QWORD *)(v10 + 2896));
    v8 = *((_QWORD *)a1 + 9);
    *((_QWORD *)a1 + 4) = &v10;
    if ( !(unsigned int)CHwCommandBuffer::AddBitBltCommand(
                          *(CHwCommandBuffer **)(v8 + 12696),
                          a1,
                          a2,
                          a3,
                          *((const struct tagPOINT **)a1 + 5))
      && !(unsigned int)CHwCommandBuffer::AddBitBltCommand(
                          *(CHwCommandBuffer **)(*((_QWORD *)a1 + 9) + 12696LL),
                          a1,
                          a2,
                          a3,
                          *((const struct tagPOINT **)a1 + 5))
      && (*(_DWORD *)(*((_QWORD *)a1 + 9) + 2744LL) & 0x400) == 0
      && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error submitting BitBlt command");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1573;
      v9 = (_QWORD *)WdLogNewEntry5_WdError();
      v9[3] = gCddImageInfo;
      v9[4] = (unsigned int)dword_14003E570;
      v9[5] = 215857758;
      WdLogGlobalForLineNumber = 1573;
      __debugbreak();
    }
    CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)&v10);
  }
  else
  {
    WdLogSingleEntry1(4, *((_QWORD *)a1 + 11));
    WdLogGlobalForLineNumber = 1563;
    v6 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 1563;
  }
  return 0;
}

```

## disassembly

```asm
0x14000ddd0  mov     [rsp+arg_0], rbx
0x14000ddd5  mov     [rsp+arg_8], rsi
0x14000ddda  push    rdi
0x14000dddb  sub     rsp, 40h
0x14000dddf  cmp     dword ptr [rcx+64h], 0
0x14000dde3  mov     rdi, r8
0x14000dde6  mov     esi, edx
0x14000dde8  mov     rbx, rcx
0x14000ddeb  jnz     short loc_14000DE4F
0x14000dded  mov     rdx, [rcx+58h]
0x14000ddf1  mov     ecx, 4
0x14000ddf6  call    cs:__imp_WdLogSingleEntry1
0x14000ddfd  nop     dword ptr [rax+rax+00h]
0x14000de02  mov     ebx, 61Bh
0x14000de07  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000de0d  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14000de14  nop     dword ptr [rax+rax+00h]
0x14000de19  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000de20  mov     [rax+18h], rcx
0x14000de24  mov     ecx, cs:dword_14003E570
0x14000de2a  mov     [rax+20h], rcx
0x14000de2e  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000de36  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000de3c  mov     rbx, [rsp+48h+arg_0]
0x14000de41  xor     eax, eax
0x14000de43  mov     rsi, [rsp+48h+arg_8]
0x14000de48  add     rsp, 40h
0x14000de4c  pop     rdi
0x14000de4d  retn
0x14000de4f  mov     rcx, [rcx+48h]
0x14000de53  mov     [rsp+48h+var_18], rcx
0x14000de58  mov     [rsp+48h+var_10], 101h
0x14000de5f  mov     [rsp+48h+var_E], 0
0x14000de64  mov     rcx, [rcx+0B48h]
0x14000de6b  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000de72  nop     dword ptr [rax+rax+00h]
0x14000de77  mov     rcx, [rsp+48h+var_18]
0x14000de7c  mov     rcx, [rcx+0B50h]
0x14000de83  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000de8a  nop     dword ptr [rax+rax+00h]
0x14000de8f  mov     rcx, [rbx+48h]
0x14000de93  lea     rax, [rsp+48h+var_18]
0x14000de98  mov     [rbx+20h], rax
0x14000de9c  mov     r9, rdi; struct tagRECT *
0x14000de9f  mov     rax, [rbx+28h]
0x14000dea3  mov     r8d, esi; unsigned int
0x14000dea6  mov     rdx, rbx; struct BITBLT_DATA *
0x14000dea9  mov     [rsp+48h+var_28], rax; struct tagPOINT *
0x14000deae  mov     rcx, [rcx+3198h]; this
0x14000deb5  call    ?AddBitBltCommand@CHwCommandBuffer@@QEAAHPEAUBITBLT_DATA@@IPEBUtagRECT@@PEBUtagPOINT@@@Z; CHwCommandBuffer::AddBitBltCommand(BITBLT_DATA *,uint,tagRECT const *,tagPOINT const *)
0x14000deba  test    eax, eax
0x14000debc  jz      short loc_14000DECD
0x14000debe  lea     rcx, [rsp+48h+var_18]; this
0x14000dec3  call    ??1CCommandBufferMutex@@QEAA@XZ; CCommandBufferMutex::~CCommandBufferMutex(void)
0x14000dec8  jmp     loc_14000DE3C
0x14000decd  mov     rcx, [rbx+48h]
0x14000ded1  mov     r9, rdi; struct tagRECT *
0x14000ded4  mov     rax, [rbx+28h]
0x14000ded8  mov     r8d, esi; unsigned int
0x14000dedb  mov     rdx, rbx; struct BITBLT_DATA *
0x14000dede  mov     [rsp+48h+var_28], rax; struct tagPOINT *
0x14000dee3  mov     rcx, [rcx+3198h]; this
0x14000deea  call    ?AddBitBltCommand@CHwCommandBuffer@@QEAAHPEAUBITBLT_DATA@@IPEBUtagRECT@@PEBUtagPOINT@@@Z; CHwCommandBuffer::AddBitBltCommand(BITBLT_DATA *,uint,tagRECT const *,tagPOINT const *)
0x14000deef  test    eax, eax
0x14000def1  jnz     short loc_14000DEBE
0x14000def3  mov     rax, [rbx+48h]
0x14000def7  test    dword ptr [rax+0AB8h], 400h
0x14000df01  jnz     short loc_14000DEBE
0x14000df03  mov     rax, cs:KdDebuggerEnabled
0x14000df0a  cmp     byte ptr [rax], 0
0x14000df0d  jz      short loc_14000DEBE
0x14000df0f  lea     rcx, aErrorSubmittin_4; "Error submitting BitBlt command"
0x14000df16  call    cs:__imp_DbgPrint
0x14000df1d  nop     dword ptr [rax+rax+00h]
0x14000df22  mov     ecx, 2
0x14000df27  call    cs:__imp_WdLogSingleEntry0
0x14000df2e  nop     dword ptr [rax+rax+00h]
0x14000df33  mov     ebx, 625h
0x14000df38  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000df3e  call    cs:__imp_WdLogNewEntry5_WdError
0x14000df45  nop     dword ptr [rax+rax+00h]
0x14000df4a  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000df51  mov     [rax+18h], rcx
0x14000df55  mov     ecx, cs:dword_14003E570
0x14000df5b  mov     [rax+20h], rcx
0x14000df5f  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000df67  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000df6d  int     3; Trap to Debugger
0x14000df6e  jmp     loc_14000DEBE
```
