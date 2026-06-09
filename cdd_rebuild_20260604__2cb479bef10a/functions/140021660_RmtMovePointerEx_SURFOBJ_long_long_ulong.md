# RmtMovePointerEx(_SURFOBJ *,long,long,ulong)

- ea: `0x140021660`
- end: `0x14002179d`
- name: `?RmtMovePointerEx@@YAHPEAU_SURFOBJ@@JJK@Z`
- size: `317`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, int, int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14001d1b0`
- `0x140021660`
- `0x140024f20`
- `0x140025030`
- `0x1400372d0`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x1400216aa`
- `WIN32K!W32GetSessionState` at `0x1400216cc`
- `WIN32K!W32GetSessionState` at `0x1400216fd`
- `WIN32K!W32GetSessionState` at `0x140021767`
- `WIN32K!W32GetSessionState` at `0x1400216aa`
- `WIN32K!W32GetSessionState` at `0x1400216cc`
- `WIN32K!W32GetSessionState` at `0x1400216fd`
- `WIN32K!W32GetSessionState` at `0x140021767`
- `WIN32K!EngReleaseSemaphore` at `0x14002177e`
- `WIN32K!EngReleaseSemaphore` at `0x14002177e`

## pseudocode

```c
__int64 __fastcall RmtMovePointerEx(struct _SURFOBJ *a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 SessionState; // rax
  __int64 v18; // [rsp+30h] [rbp-58h] BYREF
  __int64 v19; // [rsp+38h] [rbp-50h]
  __int64 v20; // [rsp+40h] [rbp-48h]
  int v21; // [rsp+48h] [rbp-40h]

  SURFSWITCHLOCK::SURFSWITCHLOCK((SURFSWITCHLOCK *)&v18, a1, 0);
  SURFACCESS::SURFACCESS((SURFACCESS *)&v18, a1);
  v10 = v20;
  if ( v20 )
    v11 = v20;
  else
    v11 = *(_QWORD *)(W32GetSessionState(v9, v8) + 72) + 840LL;
  if ( *(_QWORD *)(v11 + 736) )
  {
    if ( !v10 )
      v10 = *(_QWORD *)(W32GetSessionState(v9, v8) + 72) + 840LL;
    (*(void (__fastcall **)(struct _SURFOBJ *, _QWORD, _QWORD, _QWORD))(v10 + 736))(a1, a2, a3, a4);
  }
  else
  {
    if ( !v10 )
      v10 = *(_QWORD *)(W32GetSessionState(v9, v8) + 72) + 840LL;
    (*(void (__fastcall **)(struct _SURFOBJ *, _QWORD, _QWORD, _QWORD))(v10 + 240))(a1, a2, a3, 0);
  }
  v13 = v19;
  v14 = *(_QWORD *)(v19 + 8);
  if ( v14 )
    MovePointerInternal((struct _POINTER_INFO *)(v14 + 1120), a2, a3, a4);
  v15 = v18;
  if ( v18 && v21 )
  {
    v14 = 49151;
    *(_QWORD *)(v18 + 16) = v13;
    *(_WORD *)(v15 + 78) &= ~0x4000u;
  }
  SessionState = W32GetSessionState(v14, v12);
  EngReleaseSemaphore(*(HSEMAPHORE *)(*(_QWORD *)(SessionState + 72) + 3344LL));
  return 1;
}

```

## disassembly

```asm
0x140021660  push    rbx
0x140021662  push    rbp
0x140021663  push    rsi
0x140021664  push    rdi
0x140021665  push    r14
0x140021667  push    r15
0x140021669  sub     rsp, 58h
0x14002166d  mov     esi, edx
0x14002166f  mov     edi, r8d
0x140021672  mov     rdx, rcx; struct _SURFOBJ *
0x140021675  mov     rbp, rcx
0x140021678  lea     rcx, [rsp+88h+var_58]; this
0x14002167d  xor     r8d, r8d; struct _SURFOBJ *
0x140021680  mov     r14d, r9d
0x140021683  call    ??0SURFSWITCHLOCK@@QEAA@PEAU_SURFOBJ@@0@Z; SURFSWITCHLOCK::SURFSWITCHLOCK(_SURFOBJ *,_SURFOBJ *)
0x140021688  mov     rdx, rbp; struct _SURFOBJ *
0x14002168b  lea     rcx, [rsp+88h+var_58]; this
0x140021690  call    ??0SURFACCESS@@QEAA@PEAU_SURFOBJ@@@Z; SURFACCESS::SURFACCESS(_SURFOBJ *)
0x140021695  mov     rbx, [rsp+88h+var_48]
0x14002169a  mov     r15d, 348h
0x1400216a0  test    rbx, rbx
0x1400216a3  jz      short loc_1400216AA
0x1400216a5  mov     rax, rbx
0x1400216a8  jmp     short loc_1400216BD
0x1400216aa  call    cs:__imp_W32GetSessionState
0x1400216b1  nop     dword ptr [rax+rax+00h]
0x1400216b6  mov     rax, [rax+48h]
0x1400216ba  add     rax, r15
0x1400216bd  cmp     qword ptr [rax+2E0h], 0
0x1400216c5  jz      short loc_1400216F8
0x1400216c7  test    rbx, rbx
0x1400216ca  jnz     short loc_1400216DF
0x1400216cc  call    cs:__imp_W32GetSessionState
0x1400216d3  nop     dword ptr [rax+rax+00h]
0x1400216d8  mov     rbx, [rax+48h]
0x1400216dc  add     rbx, r15
0x1400216df  mov     rax, [rbx+2E0h]
0x1400216e6  mov     r9d, r14d
0x1400216e9  mov     r8d, edi
0x1400216ec  mov     edx, esi
0x1400216ee  mov     rcx, rbp
0x1400216f1  call    _guard_dispatch_icall
0x1400216f6  jmp     short loc_140021727
0x1400216f8  test    rbx, rbx
0x1400216fb  jnz     short loc_140021710
0x1400216fd  call    cs:__imp_W32GetSessionState
0x140021704  nop     dword ptr [rax+rax+00h]
0x140021709  mov     rbx, [rax+48h]
0x14002170d  add     rbx, r15
0x140021710  mov     rax, [rbx+0F0h]
0x140021717  xor     r9d, r9d
0x14002171a  mov     r8d, edi
0x14002171d  mov     edx, esi
0x14002171f  mov     rcx, rbp
0x140021722  call    _guard_dispatch_icall
0x140021727  mov     rbx, [rsp+88h+var_50]
0x14002172c  mov     rcx, [rbx+8]
0x140021730  test    rcx, rcx
0x140021733  jz      short loc_140021749
0x140021735  add     rcx, 460h; struct _POINTER_INFO *
0x14002173c  mov     r9d, r14d; unsigned int
0x14002173f  mov     r8d, edi; int
0x140021742  mov     edx, esi; int
0x140021744  call    ?MovePointerInternal@@YAXPEAU_POINTER_INFO@@JJK@Z; MovePointerInternal(_POINTER_INFO *,long,long,ulong)
0x140021749  mov     rax, [rsp+88h+var_58]
0x14002174e  test    rax, rax
0x140021751  jz      short loc_140021767
0x140021753  cmp     [rsp+88h+var_40], 0
0x140021758  jz      short loc_140021767
0x14002175a  mov     ecx, 0BFFFh
0x14002175f  mov     [rax+10h], rbx
0x140021763  and     [rax+4Eh], cx
0x140021767  call    cs:__imp_W32GetSessionState
0x14002176e  nop     dword ptr [rax+rax+00h]
0x140021773  mov     rcx, [rax+48h]
0x140021777  mov     rcx, [rcx+0D10h]; hsem
0x14002177e  call    cs:__imp_EngReleaseSemaphore
0x140021785  nop     dword ptr [rax+rax+00h]
0x14002178a  mov     eax, 1
0x14002178f  add     rsp, 58h
0x140021793  pop     r15
0x140021795  pop     r14
0x140021797  pop     rdi
0x140021798  pop     rsi
0x140021799  pop     rbp
0x14002179a  pop     rbx
0x14002179b  retn
```
