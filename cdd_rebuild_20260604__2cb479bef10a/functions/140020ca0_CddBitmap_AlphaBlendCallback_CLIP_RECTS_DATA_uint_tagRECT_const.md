# CddBitmap::AlphaBlendCallback(CLIP_RECTS_DATA *,uint,tagRECT const *)

- ea: `0x140020ca0`
- end: `0x140020e40`
- name: `?AlphaBlendCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000df80`
- `0x140020ca0`
- `0x140020e48`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140020d31`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140020d49`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140020d31`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140020d49`
- `ntoskrnl!DbgPrint` at `0x140020dcb`
- `ntoskrnl!DbgPrint` at `0x140020dcb`
- `ntoskrnl!KdDebuggerEnabled` at `0x140020db8`
- `watchdog!WdLogSingleEntry1` at `0x140020cc6`
- `watchdog!WdLogSingleEntry1` at `0x140020cc6`
- `watchdog!WdLogNewEntry5_WdError` at `0x140020df3`
- `watchdog!WdLogNewEntry5_WdError` at `0x140020df3`
- `watchdog!WdLogSingleEntry0` at `0x140020ddc`
- `watchdog!WdLogSingleEntry0` at `0x140020ddc`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140020cdd`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140020cdd`

## string_xrefs

- `0x140020dc4`: `Error submitting AlphaBlend command`

## pseudocode

```c
__int64 __fastcall CddBitmap::AlphaBlendCallback(struct CLIP_RECTS_DATA *a1, unsigned int a2, const struct tagRECT *a3)
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
    if ( !(unsigned int)CHwCommandBuffer::AddAlphaBlendCommand(
                          *(CHwCommandBuffer **)(*(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL) + 12696LL),
                          a1,
                          a2,
                          a3)
      && !(unsigned int)CHwCommandBuffer::AddAlphaBlendCommand(
                          *(CHwCommandBuffer **)(*(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL) + 12696LL),
                          a1,
                          a2,
                          a3)
      && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL) + 2744LL) & 0x400) == 0
      && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error submitting AlphaBlend command");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1672;
      v9 = (_QWORD *)WdLogNewEntry5_WdError(v8, v7);
      v9[3] = gCddImageInfo;
      v9[4] = (unsigned int)dword_14003E570;
      v9[5] = 215857758;
      WdLogGlobalForLineNumber = 1672;
      __debugbreak();
    }
    CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)&v11);
  }
  else
  {
    WdLogSingleEntry1(4, *((_QWORD *)a1 + 11));
    WdLogGlobalForLineNumber = 1663;
    v6 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 1663;
  }
  return 0;
}

```

## disassembly

```asm
0x140020ca0  mov     [rsp+arg_0], rbx
0x140020ca5  mov     [rsp+arg_8], rsi
0x140020caa  push    rdi
0x140020cab  sub     rsp, 30h
0x140020caf  cmp     dword ptr [rcx+64h], 0
0x140020cb3  mov     rdi, r8
0x140020cb6  mov     esi, edx
0x140020cb8  mov     rbx, rcx
0x140020cbb  jnz     short loc_140020D11
0x140020cbd  mov     rdx, [rcx+58h]
0x140020cc1  mov     ecx, 4
0x140020cc6  call    cs:__imp_WdLogSingleEntry1
0x140020ccd  nop     dword ptr [rax+rax+00h]
0x140020cd2  mov     ebx, 67Fh
0x140020cd7  mov     cs:WdLogGlobalForLineNumber, ebx
0x140020cdd  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140020ce4  nop     dword ptr [rax+rax+00h]
0x140020ce9  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140020cf0  mov     [rax+18h], rcx
0x140020cf4  mov     ecx, cs:dword_14003E570
0x140020cfa  mov     [rax+20h], rcx
0x140020cfe  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140020d06  mov     cs:WdLogGlobalForLineNumber, ebx
0x140020d0c  jmp     loc_140020E2D
0x140020d11  mov     rax, [rcx+58h]
0x140020d15  mov     rcx, [rax+8]
0x140020d19  mov     [rsp+38h+var_18], rcx
0x140020d1e  mov     [rsp+38h+var_10], 101h
0x140020d25  mov     [rsp+38h+var_E], 0
0x140020d2a  mov     rcx, [rcx+0B48h]
0x140020d31  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x140020d38  nop     dword ptr [rax+rax+00h]
0x140020d3d  mov     rcx, [rsp+38h+var_18]
0x140020d42  mov     rcx, [rcx+0B50h]
0x140020d49  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x140020d50  nop     dword ptr [rax+rax+00h]
0x140020d55  lea     rax, [rsp+38h+var_18]
0x140020d5a  mov     r9, rdi; struct tagRECT *
0x140020d5d  mov     [rbx+20h], rax
0x140020d61  mov     r8d, esi; unsigned int
0x140020d64  mov     rax, [rbx+58h]
0x140020d68  mov     rdx, rbx; struct ALPHABLEND_DATA *
0x140020d6b  mov     rcx, [rax+8]
0x140020d6f  mov     rcx, [rcx+3198h]; this
0x140020d76  call    ?AddAlphaBlendCommand@CHwCommandBuffer@@QEAAHPEAUALPHABLEND_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddAlphaBlendCommand(ALPHABLEND_DATA *,uint,tagRECT const *)
0x140020d7b  test    eax, eax
0x140020d7d  jnz     loc_140020E23
0x140020d83  mov     rax, [rbx+58h]
0x140020d87  mov     r9, rdi; struct tagRECT *
0x140020d8a  mov     r8d, esi; unsigned int
0x140020d8d  mov     rdx, rbx; struct ALPHABLEND_DATA *
0x140020d90  mov     rcx, [rax+8]
0x140020d94  mov     rcx, [rcx+3198h]; this
0x140020d9b  call    ?AddAlphaBlendCommand@CHwCommandBuffer@@QEAAHPEAUALPHABLEND_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddAlphaBlendCommand(ALPHABLEND_DATA *,uint,tagRECT const *)
0x140020da0  test    eax, eax
0x140020da2  jnz     short loc_140020E23
0x140020da4  mov     rax, [rbx+58h]
0x140020da8  mov     rcx, [rax+8]
0x140020dac  test    dword ptr [rcx+0AB8h], 400h
0x140020db6  jnz     short loc_140020E23
0x140020db8  mov     rax, cs:KdDebuggerEnabled
0x140020dbf  cmp     byte ptr [rax], 0
0x140020dc2  jz      short loc_140020E23
0x140020dc4  lea     rcx, aErrorSubmittin_0; "Error submitting AlphaBlend command"
0x140020dcb  call    cs:__imp_DbgPrint
0x140020dd2  nop     dword ptr [rax+rax+00h]
0x140020dd7  mov     ecx, 2
0x140020ddc  call    cs:__imp_WdLogSingleEntry0
0x140020de3  nop     dword ptr [rax+rax+00h]
0x140020de8  mov     ebx, 688h
0x140020ded  mov     cs:WdLogGlobalForLineNumber, ebx
0x140020df3  call    cs:__imp_WdLogNewEntry5_WdError
0x140020dfa  nop     dword ptr [rax+rax+00h]
0x140020dff  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140020e06  mov     [rax+18h], rcx
0x140020e0a  mov     ecx, cs:dword_14003E570
0x140020e10  mov     [rax+20h], rcx
0x140020e14  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140020e1c  mov     cs:WdLogGlobalForLineNumber, ebx
0x140020e22  int     3; Trap to Debugger
0x140020e23  lea     rcx, [rsp+38h+var_18]; this
0x140020e28  call    ??1CCommandBufferMutex@@QEAA@XZ; CCommandBufferMutex::~CCommandBufferMutex(void)
0x140020e2d  mov     rbx, [rsp+38h+arg_0]
0x140020e32  xor     eax, eax
0x140020e34  mov     rsi, [rsp+38h+arg_8]
0x140020e39  add     rsp, 30h
0x140020e3d  pop     rdi
0x140020e3e  retn
```
