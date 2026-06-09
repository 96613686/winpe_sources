# CddBitmap::TransparentBltCallback(CLIP_RECTS_DATA *,uint,tagRECT const *)

- ea: `0x140031110`
- end: `0x140031284`
- name: `?TransparentBltCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000df80`
- `0x14001d488`
- `0x14002ea64`
- `0x140031110`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14003120f`
- `ntoskrnl!DbgPrint` at `0x14003120f`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400311fc`
- `watchdog!WdLogSingleEntry1` at `0x140031136`
- `watchdog!WdLogSingleEntry1` at `0x140031136`
- `watchdog!WdLogNewEntry5_WdError` at `0x140031237`
- `watchdog!WdLogNewEntry5_WdError` at `0x140031237`
- `watchdog!WdLogSingleEntry0` at `0x140031220`
- `watchdog!WdLogSingleEntry0` at `0x140031220`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14003114d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14003114d`

## string_xrefs

- `0x140031208`: `Error submitting TransparentBlt command`

## pseudocode

```c
__int64 __fastcall CddBitmap::TransparentBltCallback(
        struct CLIP_RECTS_DATA *a1,
        unsigned int a2,
        const struct tagRECT *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  _BYTE v11[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( *((_DWORD *)a1 + 25) )
  {
    CCommandBufferMutex::CCommandBufferMutex(
      (CCommandBufferMutex *)v11,
      *(struct _KTHREAD ***)(*((_QWORD *)a1 + 11) + 8LL),
      0,
      0);
    *((_QWORD *)a1 + 4) = v11;
    if ( !(unsigned int)CHwCommandBuffer::AddTransparentBltCommand(
                          *(CHwCommandBuffer **)(*(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL) + 12696LL),
                          a1,
                          a2,
                          a3)
      && !(unsigned int)CHwCommandBuffer::AddTransparentBltCommand(
                          *(CHwCommandBuffer **)(*(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL) + 12696LL),
                          a1,
                          a2,
                          a3)
      && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL) + 2744LL) & 0x400) == 0
      && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error submitting TransparentBlt command");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1704;
      v9 = (_QWORD *)WdLogNewEntry5_WdError(v8, v7);
      v9[3] = gCddImageInfo;
      v9[4] = (unsigned int)dword_14003E570;
      v9[5] = 215857758;
      WdLogGlobalForLineNumber = 1704;
      __debugbreak();
    }
    CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)v11);
  }
  else
  {
    WdLogSingleEntry1(4, *((_QWORD *)a1 + 11));
    WdLogGlobalForLineNumber = 1695;
    v6 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 1695;
  }
  return 0;
}

```

## disassembly

```asm
0x140031110  mov     [rsp+arg_0], rbx
0x140031115  mov     [rsp+arg_8], rsi
0x14003111a  push    rdi
0x14003111b  sub     rsp, 30h
0x14003111f  cmp     dword ptr [rcx+64h], 0
0x140031123  mov     rdi, r8
0x140031126  mov     esi, edx
0x140031128  mov     rbx, rcx
0x14003112b  jnz     short loc_140031181
0x14003112d  mov     rdx, [rcx+58h]
0x140031131  mov     ecx, 4
0x140031136  call    cs:__imp_WdLogSingleEntry1
0x14003113d  nop     dword ptr [rax+rax+00h]
0x140031142  mov     ebx, 69Fh
0x140031147  mov     cs:WdLogGlobalForLineNumber, ebx
0x14003114d  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140031154  nop     dword ptr [rax+rax+00h]
0x140031159  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140031160  mov     [rax+18h], rcx
0x140031164  mov     ecx, cs:dword_14003E570
0x14003116a  mov     [rax+20h], rcx
0x14003116e  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140031176  mov     cs:WdLogGlobalForLineNumber, ebx
0x14003117c  jmp     loc_140031271
0x140031181  mov     rdx, [rcx+58h]
0x140031185  xor     r9d, r9d; unsigned __int8
0x140031188  xor     r8d, r8d; unsigned __int8
0x14003118b  lea     rcx, [rsp+38h+var_18]; this
0x140031190  mov     rdx, [rdx+8]; struct CDDPDEV *
0x140031194  call    ??0CCommandBufferMutex@@QEAA@PEAUCDDPDEV@@EE@Z; CCommandBufferMutex::CCommandBufferMutex(CDDPDEV *,uchar,uchar)
0x140031199  lea     rax, [rsp+38h+var_18]
0x14003119e  mov     r9, rdi; struct tagRECT *
0x1400311a1  mov     [rbx+20h], rax
0x1400311a5  mov     r8d, esi; unsigned int
0x1400311a8  mov     rax, [rbx+58h]
0x1400311ac  mov     rdx, rbx; struct TRANSPARENTBLT_DATA *
0x1400311af  mov     rcx, [rax+8]
0x1400311b3  mov     rcx, [rcx+3198h]; this
0x1400311ba  call    ?AddTransparentBltCommand@CHwCommandBuffer@@QEAAHPEAUTRANSPARENTBLT_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddTransparentBltCommand(TRANSPARENTBLT_DATA *,uint,tagRECT const *)
0x1400311bf  test    eax, eax
0x1400311c1  jnz     loc_140031267
0x1400311c7  mov     rax, [rbx+58h]
0x1400311cb  mov     r9, rdi; struct tagRECT *
0x1400311ce  mov     r8d, esi; unsigned int
0x1400311d1  mov     rdx, rbx; struct TRANSPARENTBLT_DATA *
0x1400311d4  mov     rcx, [rax+8]
0x1400311d8  mov     rcx, [rcx+3198h]; this
0x1400311df  call    ?AddTransparentBltCommand@CHwCommandBuffer@@QEAAHPEAUTRANSPARENTBLT_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddTransparentBltCommand(TRANSPARENTBLT_DATA *,uint,tagRECT const *)
0x1400311e4  test    eax, eax
0x1400311e6  jnz     short loc_140031267
0x1400311e8  mov     rax, [rbx+58h]
0x1400311ec  mov     rcx, [rax+8]
0x1400311f0  test    dword ptr [rcx+0AB8h], 400h
0x1400311fa  jnz     short loc_140031267
0x1400311fc  mov     rax, cs:KdDebuggerEnabled
0x140031203  cmp     byte ptr [rax], 0
0x140031206  jz      short loc_140031267
0x140031208  lea     rcx, aErrorSubmittin_1; "Error submitting TransparentBlt command"
0x14003120f  call    cs:__imp_DbgPrint
0x140031216  nop     dword ptr [rax+rax+00h]
0x14003121b  mov     ecx, 2
0x140031220  call    cs:__imp_WdLogSingleEntry0
0x140031227  nop     dword ptr [rax+rax+00h]
0x14003122c  mov     ebx, 6A8h
0x140031231  mov     cs:WdLogGlobalForLineNumber, ebx
0x140031237  call    cs:__imp_WdLogNewEntry5_WdError
0x14003123e  nop     dword ptr [rax+rax+00h]
0x140031243  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14003124a  mov     [rax+18h], rcx
0x14003124e  mov     ecx, cs:dword_14003E570
0x140031254  mov     [rax+20h], rcx
0x140031258  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140031260  mov     cs:WdLogGlobalForLineNumber, ebx
0x140031266  int     3; Trap to Debugger
0x140031267  lea     rcx, [rsp+38h+var_18]; this
0x14003126c  call    ??1CCommandBufferMutex@@QEAA@XZ; CCommandBufferMutex::~CCommandBufferMutex(void)
0x140031271  mov     rbx, [rsp+38h+arg_0]
0x140031276  xor     eax, eax
0x140031278  mov     rsi, [rsp+38h+arg_8]
0x14003127d  add     rsp, 30h
0x140031281  pop     rdi
0x140031282  retn
```
