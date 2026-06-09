# DockCache::ConnectedDock(_DOCK_PROFILE const *)

- ea: `0x1800116c0`
- end: `0x1800117b9`
- name: `?ConnectedDock@DockCache@@QEAAJPEBU_DOCK_PROFILE@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct _DOCK_PROFILE *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800117c0`

## callees

- `0x180011470`
- `0x1800116c0`
- `0x18001262c`
- `0x180013598`
- `0x180013ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800116da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800116da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800117a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800117a1`

## pseudocode

```c
__int64 __fastcall DockCache::ConnectedDock(LPCRITICAL_SECTION lpCriticalSection, const struct _DOCK_PROFILE *a2)
{
  int v4; // r8d
  Dock *i; // rbx
  unsigned int v6; // ebx

  EnterCriticalSection(lpCriticalSection);
  for ( i = (Dock *)lpCriticalSection[1].DebugInfo;
        i != *(Dock **)&lpCriticalSection[1].LockCount;
        i = (Dock *)((char *)i + 2936) )
  {
    if ( Dock::MatchByHardwareAddress(i, a2) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qq_MAC_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          v4,
          (_DWORD)lpCriticalSection,
          (_DWORD)i,
          (__int64)a2 + 528);
      }
      Dock::Connected(i, a2);
      v6 = 0;
      goto LABEL_15;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q_MAC_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, v4, (_DWORD)lpCriticalSection, (__int64)a2 + 528);
  }
  v6 = -2147023728;
LABEL_15:
  LeaveCriticalSection(lpCriticalSection);
  return v6;
}

```

## disassembly

```asm
0x1800116c0  mov     [rsp+arg_8], rbx
0x1800116c5  mov     [rsp+arg_10], rsi
0x1800116ca  push    rdi
0x1800116cb  sub     rsp, 40h
0x1800116cf  mov     rsi, rdx
0x1800116d2  mov     rdi, rcx
0x1800116d5  mov     [rsp+48h+arg_0], rcx
0x1800116da  call    cs:__imp_EnterCriticalSection
0x1800116e0  nop
0x1800116e1  mov     rbx, [rdi+28h]
0x1800116e5  cmp     rbx, [rdi+30h]
0x1800116e9  jz      short loc_180011758
0x1800116eb  mov     rdx, rsi; struct _DOCK_PROFILE *
0x1800116ee  mov     rcx, rbx; this
0x1800116f1  call    ?MatchByHardwareAddress@Dock@@QEBA_NPEBU_DOCK_PROFILE@@@Z; Dock::MatchByHardwareAddress(_DOCK_PROFILE const *)
0x1800116f6  test    al, al
0x1800116f8  jnz     short loc_180011703
0x1800116fa  add     rbx, 0B78h
0x180011701  jmp     short loc_1800116E5
0x180011703  lea     rax, WPP_GLOBAL_Control
0x18001170a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011711  cmp     rcx, rax
0x180011714  jz      short loc_180011749
0x180011716  cmp     byte ptr [rcx+19h], 3
0x18001171a  jb      short loc_180011749
0x18001171c  test    byte ptr [rcx+1Ch], 1
0x180011720  jz      short loc_180011749
0x180011722  lea     rax, [rsi+210h]
0x180011729  mov     edx, 48h ; 'H'
0x18001172e  mov     [rsp+48h+var_18], rsi
0x180011733  mov     [rsp+48h+var_20], rax
0x180011738  mov     [rsp+48h+var_28], rbx
0x18001173d  mov     r9, rdi
0x180011740  mov     rcx, [rcx+10h]
0x180011744  call    WPP_SF_qq_MAC_q
0x180011749  mov     rdx, rsi; struct _DOCK_PROFILE *
0x18001174c  mov     rcx, rbx; this
0x18001174f  call    ?Connected@Dock@@QEAAXPEBU_DOCK_PROFILE@@@Z; Dock::Connected(_DOCK_PROFILE const *)
0x180011754  xor     ebx, ebx
0x180011756  jmp     short loc_18001179E
0x180011758  lea     rax, WPP_GLOBAL_Control
0x18001175f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011766  cmp     rcx, rax
0x180011769  jz      short loc_180011799
0x18001176b  cmp     byte ptr [rcx+19h], 3
0x18001176f  jb      short loc_180011799
0x180011771  test    byte ptr [rcx+1Ch], 1
0x180011775  jz      short loc_180011799
0x180011777  lea     rax, [rsi+210h]
0x18001177e  mov     edx, 49h ; 'I'
0x180011783  mov     [rsp+48h+var_20], rsi
0x180011788  mov     [rsp+48h+var_28], rax
0x18001178d  mov     r9, rdi
0x180011790  mov     rcx, [rcx+10h]
0x180011794  call    WPP_SF_q_MAC_q
0x180011799  mov     ebx, 80070490h
0x18001179e  mov     rcx, rdi; lpCriticalSection
0x1800117a1  call    cs:__imp_LeaveCriticalSection
0x1800117a7  mov     eax, ebx
0x1800117a9  mov     rbx, [rsp+48h+arg_8]
0x1800117ae  mov     rsi, [rsp+48h+arg_10]
0x1800117b3  add     rsp, 40h
0x1800117b7  pop     rdi
0x1800117b8  retn
```
