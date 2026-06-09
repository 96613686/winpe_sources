# DockCache::DisconnectedDock(_DOCK_PROFILE const *)

- ea: `0x180011b30`
- end: `0x180011c26`
- name: `?DisconnectedDock@DockCache@@QEAAJPEBU_DOCK_PROFILE@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct _DOCK_PROFILE *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800117c0`

## callees

- `0x180011acc`
- `0x180011b30`
- `0x18001262c`
- `0x180013598`
- `0x180013ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011b4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c0e`

## pseudocode

```c
__int64 __fastcall DockCache::DisconnectedDock(LPCRITICAL_SECTION lpCriticalSection, const struct _DOCK_PROFILE *a2)
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
          74,
          v4,
          (_DWORD)lpCriticalSection,
          (_DWORD)i,
          (__int64)a2 + 528);
      }
      Dock::Disconnected(i);
      v6 = 0;
      goto LABEL_15;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q_MAC_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, v4, (_DWORD)lpCriticalSection, (__int64)a2 + 528);
  }
  v6 = -2147023728;
LABEL_15:
  LeaveCriticalSection(lpCriticalSection);
  return v6;
}

```

## disassembly

```asm
0x180011b30  mov     [rsp+arg_8], rbx
0x180011b35  mov     [rsp+arg_10], rsi
0x180011b3a  push    rdi
0x180011b3b  sub     rsp, 40h
0x180011b3f  mov     rsi, rdx
0x180011b42  mov     rdi, rcx
0x180011b45  mov     [rsp+48h+arg_0], rcx
0x180011b4a  call    cs:__imp_EnterCriticalSection
0x180011b50  nop
0x180011b51  mov     rbx, [rdi+28h]
0x180011b55  cmp     rbx, [rdi+30h]
0x180011b59  jz      short loc_180011BC5
0x180011b5b  mov     rdx, rsi; struct _DOCK_PROFILE *
0x180011b5e  mov     rcx, rbx; this
0x180011b61  call    ?MatchByHardwareAddress@Dock@@QEBA_NPEBU_DOCK_PROFILE@@@Z; Dock::MatchByHardwareAddress(_DOCK_PROFILE const *)
0x180011b66  test    al, al
0x180011b68  jnz     short loc_180011B73
0x180011b6a  add     rbx, 0B78h
0x180011b71  jmp     short loc_180011B55
0x180011b73  lea     rax, WPP_GLOBAL_Control
0x180011b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b81  cmp     rcx, rax
0x180011b84  jz      short loc_180011BB9
0x180011b86  cmp     byte ptr [rcx+19h], 3
0x180011b8a  jb      short loc_180011BB9
0x180011b8c  test    byte ptr [rcx+1Ch], 1
0x180011b90  jz      short loc_180011BB9
0x180011b92  lea     rax, [rsi+210h]
0x180011b99  mov     edx, 4Ah ; 'J'
0x180011b9e  mov     [rsp+48h+var_18], rsi
0x180011ba3  mov     [rsp+48h+var_20], rax
0x180011ba8  mov     [rsp+48h+var_28], rbx
0x180011bad  mov     r9, rdi
0x180011bb0  mov     rcx, [rcx+10h]
0x180011bb4  call    WPP_SF_qq_MAC_q
0x180011bb9  mov     rcx, rbx; this
0x180011bbc  call    ?Disconnected@Dock@@QEAAXXZ; Dock::Disconnected(void)
0x180011bc1  xor     ebx, ebx
0x180011bc3  jmp     short loc_180011C0B
0x180011bc5  lea     rax, WPP_GLOBAL_Control
0x180011bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bd3  cmp     rcx, rax
0x180011bd6  jz      short loc_180011C06
0x180011bd8  cmp     byte ptr [rcx+19h], 3
0x180011bdc  jb      short loc_180011C06
0x180011bde  test    byte ptr [rcx+1Ch], 1
0x180011be2  jz      short loc_180011C06
0x180011be4  lea     rax, [rsi+210h]
0x180011beb  mov     edx, 4Bh ; 'K'
0x180011bf0  mov     [rsp+48h+var_20], rsi
0x180011bf5  mov     [rsp+48h+var_28], rax
0x180011bfa  mov     r9, rdi
0x180011bfd  mov     rcx, [rcx+10h]
0x180011c01  call    WPP_SF_q_MAC_q
0x180011c06  mov     ebx, 80070490h
0x180011c0b  mov     rcx, rdi; lpCriticalSection
0x180011c0e  call    cs:__imp_LeaveCriticalSection
0x180011c14  mov     eax, ebx
0x180011c16  mov     rbx, [rsp+48h+arg_8]
0x180011c1b  mov     rsi, [rsp+48h+arg_10]
0x180011c20  add     rsp, 40h
0x180011c24  pop     rdi
0x180011c25  retn
```
