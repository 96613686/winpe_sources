# CPnpNotification::FreeNotificationItem(_NOTIFICATION_ITEM *)

- ea: `0x18000c33c`
- end: `0x18000c47b`
- name: `?FreeNotificationItem@CPnpNotification@@IEAAXPEAU_NOTIFICATION_ITEM@@@Z`
- size: `319`
- prototype: `void(CPnpNotification *__hidden this, struct _NOTIFICATION_ITEM *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000bd8c`
- `0x18000ccec`
- `0x18000d16c`

## callees

- `0x1800019b0`
- `0x1800019bc`
- `0x180009970`
- `0x18000bce4`
- `0x18000c33c`
- `0x18000d2e4`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c3ab`
- `KERNEL32!GetLastError` at `0x18000c3ab`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000c3a1`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000c3a1`

## pseudocode

```c
void __fastcall CPnpNotification::FreeNotificationItem(CPnpNotification *this, struct _NOTIFICATION_ITEM *a2)
{
  _QWORD *v3; // rcx
  void *v4; // rdx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  void *v9; // r14
  __int64 v10; // rsi
  CChildDeviceInfo *i; // rdi

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v4 = (void *)*((_QWORD *)a2 + 4);
    if ( v4 )
    {
      if ( !DeleteTimerQueueTimer(0, v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      {
        GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2));
      }
    }
    v5 = (void *)*((_QWORD *)a2 + 2);
    if ( v5 )
      operator delete[](v5);
    v6 = (void *)*((_QWORD *)a2 + 3);
    if ( v6 )
      operator delete[](v6);
    v7 = *((_QWORD *)a2 + 5);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = *((_QWORD *)a2 + 9);
    if ( v8 )
    {
      v9 = (void *)(v8 - 8);
      v10 = *(_QWORD *)(v8 - 8);
      for ( i = (CChildDeviceInfo *)(v8 + 16 * v10); v10; --v10 )
      {
        i = (CChildDeviceInfo *)((char *)i - 16);
        CChildDeviceInfo::~CChildDeviceInfo(i);
      }
      operator delete[](v9);
    }
    operator delete(a2);
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && *((_BYTE *)v3 + 25) >= 4u )
    WPP_SF_sq(v3[2], 55, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
}

```

## disassembly

```asm
0x18000c33c  push    rbx
0x18000c33e  push    rbp
0x18000c33f  push    rsi
0x18000c340  push    rdi
0x18000c341  push    r12
0x18000c343  push    r14
0x18000c345  sub     rsp, 38h
0x18000c349  mov     rbx, rdx
0x18000c34c  mov     rbp, rcx
0x18000c34f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c356  lea     r12, WPP_GLOBAL_Control
0x18000c35d  cmp     rcx, r12
0x18000c360  jz      short loc_18000C389
0x18000c362  cmp     byte ptr [rcx+19h], 4
0x18000c366  jb      short loc_18000C389
0x18000c368  mov     rcx, [rcx+10h]
0x18000c36c  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c373  mov     edx, 35h ; '5'
0x18000c378  mov     [rsp+68h+var_48], rbp
0x18000c37d  call    WPP_SF_sq
0x18000c382  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c389  test    rbx, rbx
0x18000c38c  jz      loc_18000C449
0x18000c392  mov     rdx, [rbx+20h]; Timer
0x18000c396  test    rdx, rdx
0x18000c399  jz      short loc_18000C3D0
0x18000c39b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000c39f  xor     ecx, ecx; TimerQueue
0x18000c3a1  call    cs:__imp_DeleteTimerQueueTimer
0x18000c3a7  test    eax, eax
0x18000c3a9  jnz     short loc_18000C3D0
0x18000c3ab  call    cs:__imp_GetLastError
0x18000c3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3b8  cmp     rcx, r12
0x18000c3bb  jz      short loc_18000C3D0
0x18000c3bd  cmp     byte ptr [rcx+19h], 4
0x18000c3c1  jb      short loc_18000C3D0
0x18000c3c3  mov     rcx, [rcx+10h]
0x18000c3c7  mov     dword ptr [rsp+68h+var_48], eax
0x18000c3cb  call    WPP_SF_sD
0x18000c3d0  mov     rcx, [rbx+10h]; Block
0x18000c3d4  test    rcx, rcx
0x18000c3d7  jz      short loc_18000C3DE
0x18000c3d9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000c3de  mov     rcx, [rbx+18h]; Block
0x18000c3e2  test    rcx, rcx
0x18000c3e5  jz      short loc_18000C3EC
0x18000c3e7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000c3ec  mov     rcx, [rbx+28h]
0x18000c3f0  test    rcx, rcx
0x18000c3f3  jz      short loc_18000C401
0x18000c3f5  mov     rax, [rcx]
0x18000c3f8  mov     rax, [rax+10h]
0x18000c3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c401  mov     rax, [rbx+48h]
0x18000c405  test    rax, rax
0x18000c408  jz      short loc_18000C43A
0x18000c40a  lea     r14, [rax-8]
0x18000c40e  mov     rsi, [r14]
0x18000c411  mov     rdi, rsi
0x18000c414  shl     rdi, 4
0x18000c418  add     rdi, rax
0x18000c41b  test    rsi, rsi
0x18000c41e  jz      short loc_18000C432
0x18000c420  sub     rdi, 10h
0x18000c424  mov     rcx, rdi; this
0x18000c427  call    ??1CChildDeviceInfo@@QEAA@XZ; CChildDeviceInfo::~CChildDeviceInfo(void)
0x18000c42c  sub     rsi, 1
0x18000c430  jnz     short loc_18000C420
0x18000c432  mov     rcx, r14; Block
0x18000c435  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000c43a  mov     rcx, rbx; Block
0x18000c43d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c442  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c449  cmp     rcx, r12
0x18000c44c  jz      short loc_18000C46E
0x18000c44e  cmp     byte ptr [rcx+19h], 4
0x18000c452  jb      short loc_18000C46E
0x18000c454  mov     rcx, [rcx+10h]
0x18000c458  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000c45f  mov     edx, 37h ; '7'
0x18000c464  mov     [rsp+68h+var_48], rbp
0x18000c469  call    WPP_SF_sq
0x18000c46e  add     rsp, 38h
0x18000c472  pop     r14
0x18000c474  pop     r12
0x18000c476  pop     rdi
0x18000c477  pop     rsi
0x18000c478  pop     rbp
0x18000c479  pop     rbx
0x18000c47a  retn
```
