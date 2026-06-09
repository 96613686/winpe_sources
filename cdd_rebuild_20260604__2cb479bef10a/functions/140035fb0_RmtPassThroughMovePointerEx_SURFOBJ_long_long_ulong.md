# RmtPassThroughMovePointerEx(_SURFOBJ *,long,long,ulong)

- ea: `0x140035fb0`
- end: `0x140036078`
- name: `?RmtPassThroughMovePointerEx@@YAXPEAU_SURFOBJ@@JJK@Z`
- size: `200`
- prototype: `void(struct _SURFOBJ *, int, int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14001d1b0`
- `0x1400347a4`
- `0x140035fb0`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry1` at `0x140036028`
- `watchdog!WdLogSingleEntry1` at `0x140036028`
- `watchdog!WdLogNewEntry5_WdError` at `0x14003603f`
- `watchdog!WdLogNewEntry5_WdError` at `0x14003603f`
- `WIN32K!W32GetSessionState` at `0x140035fc4`
- `WIN32K!W32GetSessionState` at `0x140035feb`
- `WIN32K!W32GetSessionState` at `0x140035fc4`
- `WIN32K!W32GetSessionState` at `0x140035feb`

## pseudocode

```c
void __fastcall RmtPassThroughMovePointerEx(struct _SURFOBJ *a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned int v6; // ebp
  __int64 SessionState; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  struct PASSTHROUGH_PDEV *PDev; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rax

  v6 = a2;
  SessionState = W32GetSessionState(a1, a2);
  (*(void (__fastcall **)(struct _SURFOBJ *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(SessionState + 72) + 1576LL))(
    a1,
    v6,
    a3,
    a4);
  v11 = W32GetSessionState(v10, v9);
  PDev = RemotePDevMgr::FindPDev(*(RemotePDevMgr **)(*(_QWORD *)(v11 + 72) + 3352LL), a1->dhpdev);
  if ( PDev )
  {
    MovePointerInternal((struct PASSTHROUGH_PDEV *)((char *)PDev + 8), v6, a3, a4);
  }
  else
  {
    WdLogSingleEntry1(2, v13);
    WdLogGlobalForLineNumber = 2964;
    v16 = (_QWORD *)WdLogNewEntry5_WdError(v15, v14);
    v16[3] = gCddImageInfo;
    v16[4] = (unsigned int)dword_14003E570;
    v16[5] = 215857758;
    WdLogGlobalForLineNumber = 2964;
  }
}

```

## disassembly

```asm
0x140035fb0  push    rbx
0x140035fb2  push    rbp
0x140035fb3  push    rsi
0x140035fb4  push    rdi
0x140035fb5  sub     rsp, 38h
0x140035fb9  mov     edi, r9d
0x140035fbc  mov     esi, r8d
0x140035fbf  mov     ebp, edx
0x140035fc1  mov     rbx, rcx
0x140035fc4  call    cs:__imp_W32GetSessionState
0x140035fcb  nop     dword ptr [rax+rax+00h]
0x140035fd0  mov     r9d, edi
0x140035fd3  mov     r8d, esi
0x140035fd6  mov     edx, ebp
0x140035fd8  mov     rcx, rbx
0x140035fdb  mov     r10, [rax+48h]
0x140035fdf  mov     rax, [r10+628h]
0x140035fe6  call    _guard_dispatch_icall
0x140035feb  call    cs:__imp_W32GetSessionState
0x140035ff2  nop     dword ptr [rax+rax+00h]
0x140035ff7  mov     rdx, [rbx+10h]; struct DHPDEV__ *
0x140035ffb  mov     rcx, [rax+48h]
0x140035fff  mov     rcx, [rcx+0D18h]; this
0x140036006  call    ?FindPDev@RemotePDevMgr@@QEAAPEAUPASSTHROUGH_PDEV@@PEAUDHPDEV__@@@Z; RemotePDevMgr::FindPDev(DHPDEV__ *)
0x14003600b  test    rax, rax
0x14003600e  jz      short loc_140036023
0x140036010  lea     rcx, [rax+8]; struct _POINTER_INFO *
0x140036014  mov     r9d, edi; unsigned int
0x140036017  mov     r8d, esi; int
0x14003601a  mov     edx, ebp; int
0x14003601c  call    ?MovePointerInternal@@YAXPEAU_POINTER_INFO@@JJK@Z; MovePointerInternal(_POINTER_INFO *,long,long,ulong)
0x140036021  jmp     short loc_14003606E
0x140036023  mov     ecx, 2
0x140036028  call    cs:__imp_WdLogSingleEntry1
0x14003602f  nop     dword ptr [rax+rax+00h]
0x140036034  mov     ebx, 0B94h
0x140036039  mov     cs:WdLogGlobalForLineNumber, ebx
0x14003603f  call    cs:__imp_WdLogNewEntry5_WdError
0x140036046  nop     dword ptr [rax+rax+00h]
0x14003604b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140036052  mov     [rax+18h], rcx
0x140036056  mov     ecx, cs:dword_14003E570
0x14003605c  mov     [rax+20h], rcx
0x140036060  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140036068  mov     cs:WdLogGlobalForLineNumber, ebx
0x14003606e  add     rsp, 38h
0x140036072  pop     rdi
0x140036073  pop     rsi
0x140036074  pop     rbp
0x140036075  pop     rbx
0x140036076  retn
```
