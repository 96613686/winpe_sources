# WorkItems::~WorkItems(void)

- ea: `0x18001a66c`
- end: `0x18001a6cd`
- name: `??1WorkItems@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(PTP_CLEANUP_GROUP *this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013dc8`
- `0x18001a8f0`

## callees

- `0x18000c308`
- `0x18001a66c`
- `0x18001a6d4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001a6ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001a6ba`

## pseudocode

```c
void __fastcall WorkItems::~WorkItems(PTP_CLEANUP_GROUP *this)
{
  if ( *this )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids, this);
    }
    CloseThreadpoolCleanupGroupMembers(*this, 0, 0);
  }
  WorkItems::Close((WorkItems *)this);
}

```

## disassembly

```asm
0x18001a66c  push    rbx
0x18001a66e  sub     rsp, 20h
0x18001a672  cmp     qword ptr [rcx], 0
0x18001a676  mov     rbx, rcx
0x18001a679  jz      short loc_18001A6C0
0x18001a67b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a682  lea     rax, WPP_GLOBAL_Control
0x18001a689  cmp     rcx, rax
0x18001a68c  jz      short loc_18001A6B2
0x18001a68e  cmp     byte ptr [rcx+19h], 3
0x18001a692  jb      short loc_18001A6B2
0x18001a694  test    byte ptr [rcx+1Ch], 1
0x18001a698  jz      short loc_18001A6B2
0x18001a69a  mov     rcx, [rcx+10h]
0x18001a69e  lea     r8, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids
0x18001a6a5  mov     edx, 0Dh
0x18001a6aa  mov     r9, rbx
0x18001a6ad  call    WPP_SF_q
0x18001a6b2  mov     rcx, [rbx]; ptpcg
0x18001a6b5  xor     r8d, r8d; pvCleanupContext
0x18001a6b8  xor     edx, edx; fCancelPendingCallbacks
0x18001a6ba  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001a6c0  mov     rcx, rbx; this
0x18001a6c3  add     rsp, 20h
0x18001a6c7  pop     rbx
0x18001a6c8  jmp     ?Close@WorkItems@@QEAAXXZ; WorkItems::Close(void)
```
