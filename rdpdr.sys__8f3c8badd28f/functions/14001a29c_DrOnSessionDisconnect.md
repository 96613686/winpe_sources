# DrOnSessionDisconnect

- ea: `0x14001a29c`
- end: `0x14001a413`
- name: `DrOnSessionDisconnect`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002acc0`

## callees

- `0x140003064`
- `0x14000324c`
- `0x140011c9c`
- `0x14001a29c`
- `0x14001dafc`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14001a2dc`
- `ntoskrnl!ProbeForRead` at `0x14001a2dc`
- `ntoskrnl!ProbeForWrite` at `0x14001a2f4`
- `ntoskrnl!ProbeForWrite` at `0x14001a2f4`

## pseudocode

```c
__int64 __fastcall DrOnSessionDisconnect(__int64 a1)
{
  volatile void *v2; // rsi
  _QWORD *v3; // rdi
  DrSessionManager *v4; // rcx
  _BYTE v6[40]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF

  memset(v6, 0, 32);
  v7 = 0;
  v2 = *(volatile void **)(a1 + 552);
  v3 = *(_QWORD **)(a1 + 560);
  ProbeForRead(v2, 0x20u, 1u);
  ProbeForWrite(v3, 8u, 1u);
  if ( *(_QWORD *)(a1 + 552) && *(_DWORD *)(a1 + 568) >= 0x20u && *(_DWORD *)(a1 + 572) >= 8u && *(_QWORD *)(a1 + 560) )
  {
    RtlCopyFromUser(v6, (void *)v2, 0x20u);
    DrSessionManager::OnDisconnect(v4, (struct tagCHANNEL_DISCONNECT_IN *)v6, (struct tagCHANNEL_DISCONNECT_OUT *)&v7);
    RtlWriteULong64ToUser(v3, v7);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14001a29c  mov     rax, rsp
0x14001a29f  mov     [rax+10h], rbx
0x14001a2a3  mov     [rax+18h], rsi
0x14001a2a7  push    rdi
0x14001a2a8  sub     rsp, 40h
0x14001a2ac  mov     rbx, rcx
0x14001a2af  xorps   xmm0, xmm0
0x14001a2b2  movups  xmmword ptr [rax-28h], xmm0
0x14001a2b6  movups  xmmword ptr [rax-18h], xmm0
0x14001a2ba  mov     qword ptr [rax+8], 0
0x14001a2c2  mov     rsi, [rcx+228h]
0x14001a2c9  mov     rdi, [rcx+230h]
0x14001a2d0  mov     edx, 20h ; ' '; Length
0x14001a2d5  lea     r8d, [rdx-1Fh]; Alignment
0x14001a2d9  mov     rcx, rsi; Address
0x14001a2dc  call    cs:__imp_ProbeForRead
0x14001a2e3  nop     dword ptr [rax+rax+00h]
0x14001a2e8  mov     edx, 8; Length
0x14001a2ed  lea     r8d, [rdx-7]; Alignment
0x14001a2f1  mov     rcx, rdi; Address
0x14001a2f4  call    cs:__imp_ProbeForWrite
0x14001a2fb  nop     dword ptr [rax+rax+00h]
0x14001a300  cmp     qword ptr [rbx+228h], 0
0x14001a308  jz      loc_14001A39B
0x14001a30e  cmp     dword ptr [rbx+238h], 20h ; ' '
0x14001a315  jb      loc_14001A39B
0x14001a31b  cmp     dword ptr [rbx+23Ch], 8
0x14001a322  jb      short loc_14001A39B
0x14001a324  cmp     qword ptr [rbx+230h], 0
0x14001a32c  jz      short loc_14001A39B
0x14001a32e  mov     r8d, 20h ; ' '; Size
0x14001a334  mov     rdx, rsi; Src
0x14001a337  lea     rcx, [rsp+48h+var_28]; void *
0x14001a33c  call    RtlCopyFromUser
0x14001a341  nop
0x14001a342  lea     r8, [rsp+48h+arg_0]; struct tagCHANNEL_DISCONNECT_OUT *
0x14001a347  lea     rdx, [rsp+48h+var_28]; struct tagCHANNEL_DISCONNECT_IN *
0x14001a34c  call    ?OnDisconnect@DrSessionManager@@QEAAXPEAUtagCHANNEL_DISCONNECT_IN@@PEAUtagCHANNEL_DISCONNECT_OUT@@@Z; DrSessionManager::OnDisconnect(tagCHANNEL_DISCONNECT_IN *,tagCHANNEL_DISCONNECT_OUT *)
0x14001a351  nop
0x14001a352  mov     rdx, [rsp+48h+arg_0]
0x14001a357  mov     rcx, rdi
0x14001a35a  call    RtlWriteULong64ToUser
0x14001a35f  nop
0x14001a360  xor     eax, eax
0x14001a362  jmp     loc_14001A402
0x14001a367  mov     ebx, eax
0x14001a369  lea     rax, WPP_GLOBAL_Control
0x14001a370  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a377  cmp     rcx, rax
0x14001a37a  jz      short loc_14001A397
0x14001a37c  cmp     byte ptr [rcx+29h], 4
0x14001a380  jb      short loc_14001A397
0x14001a382  mov     edx, 15h
0x14001a387  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a38e  mov     rcx, [rcx+18h]
0x14001a392  call    WPP_SF_
0x14001a397  mov     eax, ebx
0x14001a399  jmp     short loc_14001A402
0x14001a39b  lea     rax, WPP_GLOBAL_Control
0x14001a3a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a3a9  cmp     rcx, rax
0x14001a3ac  jz      short loc_14001A3C9
0x14001a3ae  cmp     byte ptr [rcx+29h], 2
0x14001a3b2  jb      short loc_14001A3C9
0x14001a3b4  mov     edx, 13h
0x14001a3b9  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a3c0  mov     rcx, [rcx+18h]
0x14001a3c4  call    WPP_SF_
0x14001a3c9  mov     eax, 0C000000Dh
0x14001a3ce  jmp     short loc_14001A402
0x14001a3d0  mov     ebx, eax
0x14001a3d2  lea     rax, WPP_GLOBAL_Control
0x14001a3d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a3e0  cmp     rcx, rax
0x14001a3e3  jz      short loc_14001A400
0x14001a3e5  cmp     byte ptr [rcx+29h], 4
0x14001a3e9  jb      short loc_14001A400
0x14001a3eb  mov     edx, 14h
0x14001a3f0  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a3f7  mov     rcx, [rcx+18h]
0x14001a3fb  call    WPP_SF_
0x14001a400  mov     eax, ebx
0x14001a402  mov     rbx, [rsp+48h+arg_8]
0x14001a407  mov     rsi, [rsp+48h+arg_10]
0x14001a40c  add     rsp, 40h
0x14001a410  pop     rdi
0x14001a411  retn
```
