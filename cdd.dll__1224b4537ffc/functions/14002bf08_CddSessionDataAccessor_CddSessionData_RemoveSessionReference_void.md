# CddSessionDataAccessor<CddSessionData>::RemoveSessionReference(void)

- ea: `0x14002bf08`
- end: `0x14002bf51`
- name: `?RemoveSessionReference@?$CddSessionDataAccessor@UCddSessionData@@@@QEAAXXZ`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002c620`
- `0x140034f70`

## callees

- `0x14002bf08`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x14002bf0e`
- `WIN32K!W32GetSessionState` at `0x14002bf1d`
- `WIN32K!W32GetSessionState` at `0x14002bf0e`
- `WIN32K!W32GetSessionState` at `0x14002bf1d`
- `WIN32K!EngFreeMem` at `0x14002bf36`
- `WIN32K!EngFreeMem` at `0x14002bf36`

## pseudocode

```c
void __fastcall CddSessionDataAccessor<CddSessionData>::RemoveSessionReference(__int64 a1, __int64 a2)
{
  __int64 SessionState; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  _DWORD *v5; // rcx

  SessionState = W32GetSessionState(a1, a2);
  v5 = *(_DWORD **)(W32GetSessionState(v4, v3) + 72);
  if ( (*v5)-- == 1 )
  {
    EngFreeMem(*(PVOID *)(SessionState + 72));
    *(_QWORD *)(SessionState + 72) = 0;
  }
}

```

## disassembly

```asm
0x14002bf08  push    rbx
0x14002bf0a  sub     rsp, 20h
0x14002bf0e  call    cs:__imp_W32GetSessionState
0x14002bf15  nop     dword ptr [rax+rax+00h]
0x14002bf1a  mov     rbx, rax
0x14002bf1d  call    cs:__imp_W32GetSessionState
0x14002bf24  nop     dword ptr [rax+rax+00h]
0x14002bf29  mov     rcx, [rax+48h]
0x14002bf2d  add     dword ptr [rcx], 0FFFFFFFFh
0x14002bf30  jnz     short loc_14002BF4A
0x14002bf32  mov     rcx, [rbx+48h]; pv
0x14002bf36  call    cs:__imp_EngFreeMem
0x14002bf3d  nop     dword ptr [rax+rax+00h]
0x14002bf42  mov     qword ptr [rbx+48h], 0
0x14002bf4a  add     rsp, 20h
0x14002bf4e  pop     rbx
0x14002bf4f  retn
```
