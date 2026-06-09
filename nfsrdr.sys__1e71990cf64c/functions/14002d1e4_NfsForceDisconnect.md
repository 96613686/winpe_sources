# NfsForceDisconnect

- ea: `0x14002d1e4`
- end: `0x14002d2e1`
- name: `NfsForceDisconnect`
- size: `253`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140001760`
- `0x140009f60`
- `0x14000adb0`
- `0x140020c90`
- `0x140020fa8`
- `0x1400219e8`
- `0x1400235c0`
- `0x140023dd0`
- `0x140024720`
- `0x140024c60`
- `0x140033ee0`
- `0x140034e3c`

## callees

- `0x1400159cc`
- `0x14002d17c`
- `0x14002d1e4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002d277`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002d277`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d266`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d28e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d266`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d28e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002d23b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002d23b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002d22a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002d22a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d29a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d29a`

## pseudocode

```c
void __fastcall NfsForceDisconnect(__int64 a1, char a2)
{
  int v4; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, (__int64)WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(*(PERESOURCE *)a1, 1u);
  if ( *(_DWORD *)(a1 + 8) == 6 )
  {
    if ( a2 || (v4 = *(_DWORD *)(a1 + 12), v4 != 100003) && v4 != 100021 )
    {
      ExReleaseResourceLite(*(PERESOURCE *)a1);
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)a1, 1u);
      NfsDisconnectLockHeldExclusive(a1);
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)a1);
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xBu, (__int64)WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
}

```

## disassembly

```asm
0x14002d1e4  mov     [rsp+arg_0], rbx
0x14002d1e9  mov     [rsp+arg_8], rbp
0x14002d1ee  push    rdi
0x14002d1ef  sub     rsp, 20h
0x14002d1f3  mov     dil, dl
0x14002d1f6  mov     rbx, rcx
0x14002d1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d200  lea     rbp, WPP_GLOBAL_Control
0x14002d207  cmp     rcx, rbp
0x14002d20a  jz      short loc_14002D22A
0x14002d20c  test    dword ptr [rcx+2Ch], 8000h
0x14002d213  jz      short loc_14002D22A
0x14002d215  mov     rcx, [rcx+18h]
0x14002d219  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x14002d220  mov     edx, 0Ah
0x14002d225  call    WPP_SF_
0x14002d22a  call    cs:__imp_KeEnterCriticalRegion
0x14002d231  nop     dword ptr [rax+rax+00h]
0x14002d236  mov     rcx, [rbx]; Resource
0x14002d239  mov     dl, 1; Wait
0x14002d23b  call    cs:__imp_ExAcquireResourceSharedLite
0x14002d242  nop     dword ptr [rax+rax+00h]
0x14002d247  cmp     dword ptr [rbx+8], 6
0x14002d24b  jnz     short loc_14002D28B
0x14002d24d  test    dil, dil
0x14002d250  jnz     short loc_14002D263
0x14002d252  mov     eax, [rbx+0Ch]
0x14002d255  cmp     eax, 186A3h
0x14002d25a  jz      short loc_14002D28B
0x14002d25c  cmp     eax, 186B5h
0x14002d261  jz      short loc_14002D28B
0x14002d263  mov     rcx, [rbx]; Resource
0x14002d266  call    cs:__imp_ExReleaseResourceLite
0x14002d26d  nop     dword ptr [rax+rax+00h]
0x14002d272  mov     rcx, [rbx]; Resource
0x14002d275  mov     dl, 1; Wait
0x14002d277  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002d27e  nop     dword ptr [rax+rax+00h]
0x14002d283  mov     rcx, rbx
0x14002d286  call    NfsDisconnectLockHeldExclusive
0x14002d28b  mov     rcx, [rbx]; Resource
0x14002d28e  call    cs:__imp_ExReleaseResourceLite
0x14002d295  nop     dword ptr [rax+rax+00h]
0x14002d29a  call    cs:__imp_KeLeaveCriticalRegion
0x14002d2a1  nop     dword ptr [rax+rax+00h]
0x14002d2a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d2ad  cmp     rcx, rbp
0x14002d2b0  jz      short loc_14002D2D0
0x14002d2b2  test    dword ptr [rcx+2Ch], 8000h
0x14002d2b9  jz      short loc_14002D2D0
0x14002d2bb  mov     rcx, [rcx+18h]
0x14002d2bf  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x14002d2c6  mov     edx, 0Bh
0x14002d2cb  call    WPP_SF_
0x14002d2d0  mov     rbx, [rsp+28h+arg_0]
0x14002d2d5  mov     rbp, [rsp+28h+arg_8]
0x14002d2da  add     rsp, 20h
0x14002d2de  pop     rdi
0x14002d2df  retn
```
