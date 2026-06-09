# WfpMidlObjectShutdown

- ea: `0x1800036a4`
- end: `0x1800036fb`
- name: `WfpMidlObjectShutdown`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003170`
- `0x180003370`

## callees

- `0x1800036a4`
- `0x18001346a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800036d9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800036d9`
- `RPCRT4!MesHandleFree` at `0x1800036b4`
- `RPCRT4!MesHandleFree` at `0x1800036b4`

## pseudocode

```c
void *WfpMidlObjectShutdown()
{
  if ( Handle )
    MesHandleFree(Handle);
  if ( dword_18007C650 && dword_18007C648 )
    DeleteCriticalSection(&gWfpMidlObject);
  return memset_0(&gWfpMidlObject, 0, 0x40u);
}

```

## disassembly

```asm
0x1800036a4  sub     rsp, 28h
0x1800036a8  mov     rcx, cs:Handle; Handle
0x1800036af  test    rcx, rcx
0x1800036b2  jz      short loc_1800036C0
0x1800036b4  call    cs:__imp_MesHandleFree
0x1800036bb  nop     dword ptr [rax+rax+00h]
0x1800036c0  cmp     cs:dword_18007C650, 0
0x1800036c7  jz      short loc_1800036E5
0x1800036c9  cmp     cs:dword_18007C648, 0
0x1800036d0  jz      short loc_1800036E5
0x1800036d2  lea     rcx, gWfpMidlObject; lpCriticalSection
0x1800036d9  call    cs:__imp_DeleteCriticalSection
0x1800036e0  nop     dword ptr [rax+rax+00h]
0x1800036e5  xor     edx, edx; Val
0x1800036e7  lea     rcx, gWfpMidlObject; void *
0x1800036ee  lea     r8d, [rdx+40h]; Size
0x1800036f2  add     rsp, 28h
0x1800036f6  jmp     memset_0
```
