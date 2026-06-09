# RmtPassThroughMovePointer(_SURFOBJ *,long,long,_RECTL *)

- ea: `0x140035ee0`
- end: `0x140035fa8`
- name: `?RmtPassThroughMovePointer@@YAXPEAU_SURFOBJ@@JJPEAU_RECTL@@@Z`
- size: `200`
- prototype: `void(struct _SURFOBJ *, int, int, struct _RECTL *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14001d1b0`
- `0x1400347a4`
- `0x140035ee0`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry1` at `0x140035f58`
- `watchdog!WdLogSingleEntry1` at `0x140035f58`
- `watchdog!WdLogNewEntry5_WdError` at `0x140035f6f`
- `watchdog!WdLogNewEntry5_WdError` at `0x140035f6f`
- `WIN32K!W32GetSessionState` at `0x140035ef4`
- `WIN32K!W32GetSessionState` at `0x140035f1b`
- `WIN32K!W32GetSessionState` at `0x140035ef4`
- `WIN32K!W32GetSessionState` at `0x140035f1b`

## pseudocode

```c
void __fastcall RmtPassThroughMovePointer(struct _SURFOBJ *a1, __int64 a2, unsigned int a3, struct _RECTL *a4)
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
  (*(void (__fastcall **)(struct _SURFOBJ *, _QWORD, _QWORD, struct _RECTL *))(*(_QWORD *)(SessionState + 72) + 1080LL))(
    a1,
    v6,
    a3,
    a4);
  v11 = W32GetSessionState(v10, v9);
  PDev = RemotePDevMgr::FindPDev(*(RemotePDevMgr **)(*(_QWORD *)(v11 + 72) + 3352LL), a1->dhpdev);
  if ( PDev )
  {
    MovePointerInternal((struct PASSTHROUGH_PDEV *)((char *)PDev + 8), v6, a3, 0);
  }
  else
  {
    WdLogSingleEntry1(2, v13);
    WdLogGlobalForLineNumber = 2935;
    v16 = (_QWORD *)WdLogNewEntry5_WdError(v15, v14);
    v16[3] = gCddImageInfo;
    v16[4] = (unsigned int)dword_14003E570;
    v16[5] = 215857758;
    WdLogGlobalForLineNumber = 2935;
  }
}

```

## disassembly

```asm
0x140035ee0  push    rbx
0x140035ee2  push    rbp
0x140035ee3  push    rsi
0x140035ee4  push    rdi
0x140035ee5  sub     rsp, 38h
0x140035ee9  mov     rbx, r9
0x140035eec  mov     esi, r8d
0x140035eef  mov     ebp, edx
0x140035ef1  mov     rdi, rcx
0x140035ef4  call    cs:__imp_W32GetSessionState
0x140035efb  nop     dword ptr [rax+rax+00h]
0x140035f00  mov     r9, rbx
0x140035f03  mov     r8d, esi
0x140035f06  mov     edx, ebp
0x140035f08  mov     rcx, rdi
0x140035f0b  mov     r10, [rax+48h]
0x140035f0f  mov     rax, [r10+438h]
0x140035f16  call    _guard_dispatch_icall
0x140035f1b  call    cs:__imp_W32GetSessionState
0x140035f22  nop     dword ptr [rax+rax+00h]
0x140035f27  mov     rdx, [rdi+10h]; struct DHPDEV__ *
0x140035f2b  mov     rcx, [rax+48h]
0x140035f2f  mov     rcx, [rcx+0D18h]; this
0x140035f36  call    ?FindPDev@RemotePDevMgr@@QEAAPEAUPASSTHROUGH_PDEV@@PEAUDHPDEV__@@@Z; RemotePDevMgr::FindPDev(DHPDEV__ *)
0x140035f3b  test    rax, rax
0x140035f3e  jz      short loc_140035F53
0x140035f40  lea     rcx, [rax+8]; struct _POINTER_INFO *
0x140035f44  xor     r9d, r9d; unsigned int
0x140035f47  mov     r8d, esi; int
0x140035f4a  mov     edx, ebp; int
0x140035f4c  call    ?MovePointerInternal@@YAXPEAU_POINTER_INFO@@JJK@Z; MovePointerInternal(_POINTER_INFO *,long,long,ulong)
0x140035f51  jmp     short loc_140035F9E
0x140035f53  mov     ecx, 2
0x140035f58  call    cs:__imp_WdLogSingleEntry1
0x140035f5f  nop     dword ptr [rax+rax+00h]
0x140035f64  mov     ebx, 0B77h
0x140035f69  mov     cs:WdLogGlobalForLineNumber, ebx
0x140035f6f  call    cs:__imp_WdLogNewEntry5_WdError
0x140035f76  nop     dword ptr [rax+rax+00h]
0x140035f7b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140035f82  mov     [rax+18h], rcx
0x140035f86  mov     ecx, cs:dword_14003E570
0x140035f8c  mov     [rax+20h], rcx
0x140035f90  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140035f98  mov     cs:WdLogGlobalForLineNumber, ebx
0x140035f9e  add     rsp, 38h
0x140035fa2  pop     rdi
0x140035fa3  pop     rsi
0x140035fa4  pop     rbp
0x140035fa5  pop     rbx
0x140035fa6  retn
```
