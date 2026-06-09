# WorkItems::WorkItems(void)

- ea: `0x18001a5ac`
- end: `0x18001a665`
- name: `??0WorkItems@@QEAA@XZ`
- size: `185`
- prototype: `WorkItems *__fastcall(WorkItems *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ce20`
- `0x18000d230`

## callees

- `0x18000c308`
- `0x18001a5ac`
- `0x18001a6d4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001a638`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001a638`

## pseudocode

```c
WorkItems *__fastcall WorkItems::WorkItems(WorkItems *this)
{
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids, this);
  }
  *((_DWORD *)this + 2) = 3;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_DWORD *)this + 17) = 1;
  *((_DWORD *)this + 18) = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *(_QWORD *)this = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    *((_QWORD *)this + 3) = ThreadpoolCleanupGroup;
    *((_QWORD *)this + 4) = 0;
  }
  else
  {
    WorkItems::Close(this);
  }
  return this;
}

```

## disassembly

```asm
0x18001a5ac  push    rbx
0x18001a5ae  sub     rsp, 20h
0x18001a5b2  mov     rbx, rcx
0x18001a5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5bc  lea     rax, WPP_GLOBAL_Control
0x18001a5c3  cmp     rcx, rax
0x18001a5c6  jz      short loc_18001A5EC
0x18001a5c8  cmp     byte ptr [rcx+19h], 3
0x18001a5cc  jb      short loc_18001A5EC
0x18001a5ce  test    byte ptr [rcx+1Ch], 1
0x18001a5d2  jz      short loc_18001A5EC
0x18001a5d4  mov     rcx, [rcx+10h]
0x18001a5d8  lea     r8, WPP_f0d96dd7853034934bfbcbbd7dfb6684_Traceguids
0x18001a5df  mov     edx, 0Ah
0x18001a5e4  mov     r9, rbx
0x18001a5e7  call    WPP_SF_q
0x18001a5ec  mov     dword ptr [rbx+8], 3
0x18001a5f3  mov     qword ptr [rbx+10h], 0
0x18001a5fb  mov     qword ptr [rbx+18h], 0
0x18001a603  mov     qword ptr [rbx+20h], 0
0x18001a60b  mov     qword ptr [rbx+28h], 0
0x18001a613  mov     qword ptr [rbx+30h], 0
0x18001a61b  mov     qword ptr [rbx+38h], 0
0x18001a623  mov     dword ptr [rbx+40h], 0
0x18001a62a  mov     dword ptr [rbx+44h], 1
0x18001a631  mov     dword ptr [rbx+48h], 48h ; 'H'
0x18001a638  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001a63e  mov     [rbx], rax
0x18001a641  test    rax, rax
0x18001a644  jz      short loc_18001A654
0x18001a646  mov     [rbx+18h], rax
0x18001a64a  mov     qword ptr [rbx+20h], 0
0x18001a652  jmp     short loc_18001A65C
0x18001a654  mov     rcx, rbx; this
0x18001a657  call    ?Close@WorkItems@@QEAAXXZ; WorkItems::Close(void)
0x18001a65c  mov     rax, rbx
0x18001a65f  add     rsp, 20h
0x18001a663  pop     rbx
0x18001a664  retn
```
