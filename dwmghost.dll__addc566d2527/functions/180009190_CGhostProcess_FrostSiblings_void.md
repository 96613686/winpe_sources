# CGhostProcess::FrostSiblings(void)

- ea: `0x180009190`
- end: `0x1800091da`
- name: `?FrostSiblings@CGhostProcess@@QEAAHXZ`
- size: `74`
- prototype: `__int64 __fastcall(LPARAM lParam)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180006bb8`
- `0x180007190`
- `0x180007280`
- `0x1800072d0`
- `0x1800091e0`

## callees

- `0x180009190`
- `0x180009f60`
- `0x180009f70`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!EnumWindows` at `0x1800091bd`
- `ext-ms-win-ntuser-window-l1-1-0!EnumWindows` at `0x1800091bd`

## pseudocode

```c
__int64 __fastcall CGhostProcess::FrostSiblings(LPARAM lParam)
{
  CLock::Acquire((LPCRITICAL_SECTION)(lParam + 16));
  if ( !*(_DWORD *)(lParam + 68) )
  {
    *(_DWORD *)(lParam + 68) = 1;
    EnumWindows((WNDENUMPROC)CGhostProcess::s_FrostSiblingsEnumProc, lParam);
  }
  CLock::Release((LPCRITICAL_SECTION)(lParam + 16));
  return *(unsigned int *)(lParam + 68);
}

```

## disassembly

```asm
0x180009190  mov     [rsp+arg_0], rbx
0x180009195  push    rdi
0x180009196  sub     rsp, 20h
0x18000919a  mov     rbx, rcx
0x18000919d  add     rcx, 10h; lpCriticalSection
0x1800091a1  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x1800091a6  cmp     dword ptr [rbx+44h], 0
0x1800091aa  jnz     short loc_1800091C3
0x1800091ac  mov     rdx, rbx; lParam
0x1800091af  mov     dword ptr [rbx+44h], 1
0x1800091b6  lea     rcx, ?s_FrostSiblingsEnumProc@CGhostProcess@@CAHPEAUHWND__@@_J@Z; lpEnumFunc
0x1800091bd  call    cs:__imp_EnumWindows
0x1800091c3  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800091c7  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x1800091cc  mov     eax, [rbx+44h]
0x1800091cf  mov     rbx, [rsp+28h+arg_0]
0x1800091d4  add     rsp, 20h
0x1800091d8  pop     rdi
0x1800091d9  retn
```
