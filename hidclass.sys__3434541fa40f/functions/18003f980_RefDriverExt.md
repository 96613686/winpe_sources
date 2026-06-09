# RefDriverExt

- ea: `0x18003f980`
- end: `0x18003f9f7`
- name: `RefDriverExt`
- size: `119`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18003a590`
- `0x18003b69c`
- `0x18003f634`
- `0x18003f830`

## callees

- `0x18001d4d4`
- `0x18003f980`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x18003f996`
- `ntoskrnl!ExAcquireFastMutex` at `0x18003f996`
- `ntoskrnl!ExReleaseFastMutex` at `0x18003f9d0`
- `ntoskrnl!ExReleaseFastMutex` at `0x18003f9d0`

## pseudocode

```c
_VPB **__fastcall RefDriverExt(_VPB *a1)
{
  _VPB **p_Vpb; // rbx
  struct _DEVICE_OBJECT *p_Queue; // rdx

  p_Vpb = 0;
  ExAcquireFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  p_Queue = (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue;
  while ( 1 )
  {
    p_Queue = *(struct _DEVICE_OBJECT **)&p_Queue->Type;
    if ( p_Queue == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue )
      break;
    if ( p_Queue[-1].Vpb == a1 )
    {
      ++*((_DWORD *)&p_Queue[-1].Reserved + 2);
      p_Vpb = &p_Queue[-1].Vpb;
      break;
    }
  }
  ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  if ( !p_Vpb )
    TraceLoggingRefDriverExtFailed();
  return p_Vpb;
}

```

## disassembly

```asm
0x18003f980  mov     [rsp+arg_0], rbx
0x18003f985  push    rdi
0x18003f986  sub     rsp, 20h
0x18003f98a  mov     rdi, rcx
0x18003f98d  xor     ebx, ebx
0x18003f98f  lea     rcx, WPP_MAIN_CB.Queue+10h; FastMutex
0x18003f996  call    cs:__imp_ExAcquireFastMutex
0x18003f99d  nop     dword ptr [rax+rax+00h]
0x18003f9a2  lea     rcx, WPP_MAIN_CB.Queue
0x18003f9a9  mov     rdx, rcx
0x18003f9ac  mov     rdx, [rdx]
0x18003f9af  cmp     rdx, rcx
0x18003f9b2  jz      short loc_18003F9C9
0x18003f9b4  lea     rax, [rdx-118h]
0x18003f9bb  cmp     [rax], rdi
0x18003f9be  jnz     short loc_18003F9AC
0x18003f9c0  inc     dword ptr [rax+110h]
0x18003f9c6  mov     rbx, rax
0x18003f9c9  lea     rcx, WPP_MAIN_CB.Queue+10h; FastMutex
0x18003f9d0  call    cs:__imp_ExReleaseFastMutex
0x18003f9d7  nop     dword ptr [rax+rax+00h]
0x18003f9dc  test    rbx, rbx
0x18003f9df  jz      short loc_18003F9F0
0x18003f9e1  mov     rax, rbx
0x18003f9e4  mov     rbx, [rsp+28h+arg_0]
0x18003f9e9  add     rsp, 20h
0x18003f9ed  pop     rdi
0x18003f9ee  retn
0x18003f9f0  call    TraceLoggingRefDriverExtFailed
0x18003f9f5  jmp     short loc_18003F9E1
```
