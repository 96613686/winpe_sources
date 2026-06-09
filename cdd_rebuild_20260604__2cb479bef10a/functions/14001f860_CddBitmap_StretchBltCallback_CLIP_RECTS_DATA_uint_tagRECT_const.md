# CddBitmap::StretchBltCallback(CLIP_RECTS_DATA *,uint,tagRECT const *)

- ea: `0x14001f860`
- end: `0x14001fa00`
- name: `?StretchBltCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000df80`
- `0x14001f860`
- `0x14001fa08`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001f8f1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001f909`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001f8f1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001f909`
- `ntoskrnl!DbgPrint` at `0x14001f98b`
- `ntoskrnl!DbgPrint` at `0x14001f98b`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001f978`
- `watchdog!WdLogSingleEntry1` at `0x14001f886`
- `watchdog!WdLogSingleEntry1` at `0x14001f886`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f9b3`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f9b3`
- `watchdog!WdLogSingleEntry0` at `0x14001f99c`
- `watchdog!WdLogSingleEntry0` at `0x14001f99c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001f89d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001f89d`

## string_xrefs

- `0x14001f984`: `Error submitting StretchBlt command`

## pseudocode

```c
__int64 __fastcall CddBitmap::StretchBltCallback(struct CLIP_RECTS_DATA *a1, unsigned int a2, const struct tagRECT *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v11; // [rsp+20h] [rbp-18h] BYREF
  __int16 v12; // [rsp+28h] [rbp-10h]
  char v13; // [rsp+2Ah] [rbp-Eh]

  if ( *((_DWORD *)a1 + 25) )
  {
    v11 = *(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL);
    v12 = 257;
    v13 = 0;
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*(_QWORD *)(v11 + 2888));
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*(_QWORD *)(v11 + 2896));
    *((_QWORD *)a1 + 4) = &v11;
    if ( !(unsigned int)CHwCommandBuffer::AddStretchBltCommand(
                          *(CHwCommandBuffer **)(*(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL) + 12696LL),
                          a1,
                          a2,
                          a3)
      && !(unsigned int)CHwCommandBuffer::AddStretchBltCommand(
                          *(CHwCommandBuffer **)(*(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL) + 12696LL),
                          a1,
                          a2,
                          a3)
      && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL) + 2744LL) & 0x400) == 0
      && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error submitting StretchBlt command");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1736;
      v9 = (_QWORD *)WdLogNewEntry5_WdError(v8, v7);
      v9[3] = gCddImageInfo;
      v9[4] = (unsigned int)dword_14003E570;
      v9[5] = 215857758;
      WdLogGlobalForLineNumber = 1736;
      __debugbreak();
    }
    CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)&v11);
  }
  else
  {
    WdLogSingleEntry1(4, *((_QWORD *)a1 + 11));
    WdLogGlobalForLineNumber = 1727;
    v6 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 1727;
  }
  return 0;
}

```

## disassembly

```asm
0x14001f860  mov     [rsp+arg_0], rbx
0x14001f865  mov     [rsp+arg_8], rsi
0x14001f86a  push    rdi
0x14001f86b  sub     rsp, 30h
0x14001f86f  cmp     dword ptr [rcx+64h], 0
0x14001f873  mov     rdi, r8
0x14001f876  mov     esi, edx
0x14001f878  mov     rbx, rcx
0x14001f87b  jnz     short loc_14001F8D1
0x14001f87d  mov     rdx, [rcx+58h]
0x14001f881  mov     ecx, 4
0x14001f886  call    cs:__imp_WdLogSingleEntry1
0x14001f88d  nop     dword ptr [rax+rax+00h]
0x14001f892  mov     ebx, 6BFh
0x14001f897  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f89d  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14001f8a4  nop     dword ptr [rax+rax+00h]
0x14001f8a9  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001f8b0  mov     [rax+18h], rcx
0x14001f8b4  mov     ecx, cs:dword_14003E570
0x14001f8ba  mov     [rax+20h], rcx
0x14001f8be  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001f8c6  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f8cc  jmp     loc_14001F9ED
0x14001f8d1  mov     rax, [rcx+58h]
0x14001f8d5  mov     rcx, [rax+8]
0x14001f8d9  mov     [rsp+38h+var_18], rcx
0x14001f8de  mov     [rsp+38h+var_10], 101h
0x14001f8e5  mov     [rsp+38h+var_E], 0
0x14001f8ea  mov     rcx, [rcx+0B48h]
0x14001f8f1  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001f8f8  nop     dword ptr [rax+rax+00h]
0x14001f8fd  mov     rcx, [rsp+38h+var_18]
0x14001f902  mov     rcx, [rcx+0B50h]
0x14001f909  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001f910  nop     dword ptr [rax+rax+00h]
0x14001f915  lea     rax, [rsp+38h+var_18]
0x14001f91a  mov     r9, rdi; struct tagRECT *
0x14001f91d  mov     [rbx+20h], rax
0x14001f921  mov     r8d, esi; unsigned int
0x14001f924  mov     rax, [rbx+58h]
0x14001f928  mov     rdx, rbx; struct STRETCHBLT_DATA *
0x14001f92b  mov     rcx, [rax+8]
0x14001f92f  mov     rcx, [rcx+3198h]; this
0x14001f936  call    ?AddStretchBltCommand@CHwCommandBuffer@@QEAAHPEAUSTRETCHBLT_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddStretchBltCommand(STRETCHBLT_DATA *,uint,tagRECT const *)
0x14001f93b  test    eax, eax
0x14001f93d  jnz     loc_14001F9E3
0x14001f943  mov     rax, [rbx+58h]
0x14001f947  mov     r9, rdi; struct tagRECT *
0x14001f94a  mov     r8d, esi; unsigned int
0x14001f94d  mov     rdx, rbx; struct STRETCHBLT_DATA *
0x14001f950  mov     rcx, [rax+8]
0x14001f954  mov     rcx, [rcx+3198h]; this
0x14001f95b  call    ?AddStretchBltCommand@CHwCommandBuffer@@QEAAHPEAUSTRETCHBLT_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddStretchBltCommand(STRETCHBLT_DATA *,uint,tagRECT const *)
0x14001f960  test    eax, eax
0x14001f962  jnz     short loc_14001F9E3
0x14001f964  mov     rax, [rbx+58h]
0x14001f968  mov     rcx, [rax+8]
0x14001f96c  test    dword ptr [rcx+0AB8h], 400h
0x14001f976  jnz     short loc_14001F9E3
0x14001f978  mov     rax, cs:KdDebuggerEnabled
0x14001f97f  cmp     byte ptr [rax], 0
0x14001f982  jz      short loc_14001F9E3
0x14001f984  lea     rcx, aErrorSubmittin; "Error submitting StretchBlt command"
0x14001f98b  call    cs:__imp_DbgPrint
0x14001f992  nop     dword ptr [rax+rax+00h]
0x14001f997  mov     ecx, 2
0x14001f99c  call    cs:__imp_WdLogSingleEntry0
0x14001f9a3  nop     dword ptr [rax+rax+00h]
0x14001f9a8  mov     ebx, 6C8h
0x14001f9ad  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f9b3  call    cs:__imp_WdLogNewEntry5_WdError
0x14001f9ba  nop     dword ptr [rax+rax+00h]
0x14001f9bf  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001f9c6  mov     [rax+18h], rcx
0x14001f9ca  mov     ecx, cs:dword_14003E570
0x14001f9d0  mov     [rax+20h], rcx
0x14001f9d4  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001f9dc  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f9e2  int     3; Trap to Debugger
0x14001f9e3  lea     rcx, [rsp+38h+var_18]; this
0x14001f9e8  call    ??1CCommandBufferMutex@@QEAA@XZ; CCommandBufferMutex::~CCommandBufferMutex(void)
0x14001f9ed  mov     rbx, [rsp+38h+arg_0]
0x14001f9f2  xor     eax, eax
0x14001f9f4  mov     rsi, [rsp+38h+arg_8]
0x14001f9f9  add     rsp, 30h
0x14001f9fd  pop     rdi
0x14001f9fe  retn
```
