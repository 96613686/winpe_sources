# CddBitmap::ClearTypeBlendCallback(CLIP_RECTS_DATA *,uint,tagRECT const *)

- ea: `0x14002f640`
- end: `0x14002f7ab`
- name: `?ClearTypeBlendCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000df80`
- `0x14001cce4`
- `0x14001d488`
- `0x14002f640`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14002f736`
- `ntoskrnl!DbgPrint` at `0x14002f736`
- `ntoskrnl!KdDebuggerEnabled` at `0x14002f723`
- `watchdog!WdLogSingleEntry1` at `0x14002f669`
- `watchdog!WdLogSingleEntry1` at `0x14002f669`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002f75e`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002f75e`
- `watchdog!WdLogSingleEntry0` at `0x14002f747`
- `watchdog!WdLogSingleEntry0` at `0x14002f747`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002f680`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002f680`

## string_xrefs

- `0x14002f72f`: `Error submitting ClearTypeBlend command`

## pseudocode

```c
__int64 __fastcall CddBitmap::ClearTypeBlendCallback(
        struct CLIP_RECTS_DATA *a1,
        unsigned int a2,
        const struct tagRECT *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  _QWORD *v10; // rax
  _BYTE v12[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( *((_DWORD *)a1 + 34) )
  {
    CCommandBufferMutex::CCommandBufferMutex(
      (CCommandBufferMutex *)v12,
      *(struct _KTHREAD ***)(*((_QWORD *)a1 + 10) + 8LL),
      0,
      0);
    v7 = *((_QWORD *)a1 + 9);
    *((_QWORD *)a1 + 4) = v12;
    if ( !(unsigned int)CHwCommandBuffer::AddClearTypeBlendCommand(*(CHwCommandBuffer **)(v7 + 12696), a1, a2, a3)
      && !(unsigned int)CHwCommandBuffer::AddClearTypeBlendCommand(
                          *(CHwCommandBuffer **)(*((_QWORD *)a1 + 9) + 12696LL),
                          a1,
                          a2,
                          a3)
      && (*(_DWORD *)(*((_QWORD *)a1 + 9) + 2744LL) & 0x400) == 0
      && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error submitting ClearTypeBlend command");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1768;
      v10 = (_QWORD *)WdLogNewEntry5_WdError(v9, v8);
      v10[3] = gCddImageInfo;
      v10[4] = (unsigned int)dword_14003E570;
      v10[5] = 215857758;
      WdLogGlobalForLineNumber = 1768;
      __debugbreak();
    }
    CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)v12);
  }
  else
  {
    WdLogSingleEntry1(4, *((_QWORD *)a1 + 10));
    WdLogGlobalForLineNumber = 1759;
    v6 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 1759;
  }
  return 0;
}

```

## disassembly

```asm
0x14002f640  mov     [rsp+arg_0], rbx
0x14002f645  mov     [rsp+arg_8], rsi
0x14002f64a  push    rdi
0x14002f64b  sub     rsp, 30h
0x14002f64f  cmp     dword ptr [rcx+88h], 0
0x14002f656  mov     rdi, r8
0x14002f659  mov     esi, edx
0x14002f65b  mov     rbx, rcx
0x14002f65e  jnz     short loc_14002F6B4
0x14002f660  mov     rdx, [rcx+50h]
0x14002f664  mov     ecx, 4
0x14002f669  call    cs:__imp_WdLogSingleEntry1
0x14002f670  nop     dword ptr [rax+rax+00h]
0x14002f675  mov     ebx, 6DFh
0x14002f67a  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002f680  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14002f687  nop     dword ptr [rax+rax+00h]
0x14002f68c  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002f693  mov     [rax+18h], rcx
0x14002f697  mov     ecx, cs:dword_14003E570
0x14002f69d  mov     [rax+20h], rcx
0x14002f6a1  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002f6a9  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002f6af  jmp     loc_14002F798
0x14002f6b4  mov     rdx, [rcx+50h]
0x14002f6b8  xor     r9d, r9d; unsigned __int8
0x14002f6bb  xor     r8d, r8d; unsigned __int8
0x14002f6be  lea     rcx, [rsp+38h+var_18]; this
0x14002f6c3  mov     rdx, [rdx+8]; struct CDDPDEV *
0x14002f6c7  call    ??0CCommandBufferMutex@@QEAA@PEAUCDDPDEV@@EE@Z; CCommandBufferMutex::CCommandBufferMutex(CDDPDEV *,uchar,uchar)
0x14002f6cc  mov     rcx, [rbx+48h]
0x14002f6d0  lea     rax, [rsp+38h+var_18]
0x14002f6d5  mov     [rbx+20h], rax
0x14002f6d9  mov     r9, rdi; struct tagRECT *
0x14002f6dc  mov     r8d, esi; unsigned int
0x14002f6df  mov     rdx, rbx; struct CLEARTYPEBLEND_DATA *
0x14002f6e2  mov     rcx, [rcx+3198h]; this
0x14002f6e9  call    ?AddClearTypeBlendCommand@CHwCommandBuffer@@QEAAHPEAUCLEARTYPEBLEND_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddClearTypeBlendCommand(CLEARTYPEBLEND_DATA *,uint,tagRECT const *)
0x14002f6ee  test    eax, eax
0x14002f6f0  jnz     loc_14002F78E
0x14002f6f6  mov     rcx, [rbx+48h]
0x14002f6fa  mov     r9, rdi; struct tagRECT *
0x14002f6fd  mov     r8d, esi; unsigned int
0x14002f700  mov     rdx, rbx; struct CLEARTYPEBLEND_DATA *
0x14002f703  mov     rcx, [rcx+3198h]; this
0x14002f70a  call    ?AddClearTypeBlendCommand@CHwCommandBuffer@@QEAAHPEAUCLEARTYPEBLEND_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddClearTypeBlendCommand(CLEARTYPEBLEND_DATA *,uint,tagRECT const *)
0x14002f70f  test    eax, eax
0x14002f711  jnz     short loc_14002F78E
0x14002f713  mov     rax, [rbx+48h]
0x14002f717  test    dword ptr [rax+0AB8h], 400h
0x14002f721  jnz     short loc_14002F78E
0x14002f723  mov     rax, cs:KdDebuggerEnabled
0x14002f72a  cmp     byte ptr [rax], 0
0x14002f72d  jz      short loc_14002F78E
0x14002f72f  lea     rcx, aErrorSubmittin_3; "Error submitting ClearTypeBlend command"
0x14002f736  call    cs:__imp_DbgPrint
0x14002f73d  nop     dword ptr [rax+rax+00h]
0x14002f742  mov     ecx, 2
0x14002f747  call    cs:__imp_WdLogSingleEntry0
0x14002f74e  nop     dword ptr [rax+rax+00h]
0x14002f753  mov     ebx, 6E8h
0x14002f758  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002f75e  call    cs:__imp_WdLogNewEntry5_WdError
0x14002f765  nop     dword ptr [rax+rax+00h]
0x14002f76a  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002f771  mov     [rax+18h], rcx
0x14002f775  mov     ecx, cs:dword_14003E570
0x14002f77b  mov     [rax+20h], rcx
0x14002f77f  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002f787  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002f78d  int     3; Trap to Debugger
0x14002f78e  lea     rcx, [rsp+38h+var_18]; this
0x14002f793  call    ??1CCommandBufferMutex@@QEAA@XZ; CCommandBufferMutex::~CCommandBufferMutex(void)
0x14002f798  mov     rbx, [rsp+38h+arg_0]
0x14002f79d  xor     eax, eax
0x14002f79f  mov     rsi, [rsp+38h+arg_8]
0x14002f7a4  add     rsp, 30h
0x14002f7a8  pop     rdi
0x14002f7a9  retn
```
