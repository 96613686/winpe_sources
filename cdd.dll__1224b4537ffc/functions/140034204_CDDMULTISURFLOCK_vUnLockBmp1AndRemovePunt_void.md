# CDDMULTISURFLOCK::vUnLockBmp1AndRemovePunt(void)

- ea: `0x140034204`
- end: `0x14003424c`
- name: `?vUnLockBmp1AndRemovePunt@CDDMULTISURFLOCK@@QEAAXXZ`
- size: `72`
- prototype: `void __fastcall(CDDMULTISURFLOCK *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008da4`

## callees

- `0x1400224a0`
- `0x140034204`

## import_xrefs

- `WIN32K!EngReleaseSemaphore` at `0x140034232`
- `WIN32K!EngReleaseSemaphore` at `0x140034232`

## string_xrefs

- `0x14003421a`: `vUnLockBmp1AndRemovePunt: cddBmp1 == NULL\n`

## pseudocode

```c
void __fastcall CDDMULTISURFLOCK::vUnLockBmp1AndRemovePunt(CDDMULTISURFLOCK *this)
{
  if ( *(_QWORD *)this )
  {
    if ( !*((_QWORD *)this + 1) )
    {
      DbgLog("vUnLockBmp1AndRemovePunt: cddBmp1 == NULL\n");
      __debugbreak();
    }
    EngReleaseSemaphore(*(HSEMAPHORE *)(*((_QWORD *)this + 1) + 192LL));
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x140034204  push    rbx
0x140034206  sub     rsp, 20h
0x14003420a  cmp     qword ptr [rcx], 0
0x14003420e  mov     rbx, rcx
0x140034211  jz      short loc_140034245
0x140034213  cmp     qword ptr [rcx+8], 0
0x140034218  jnz     short loc_140034227
0x14003421a  lea     rcx, aVunlockbmp1and; "vUnLockBmp1AndRemovePunt: cddBmp1 == NU"...
0x140034221  call    ?DbgLog@@YAXPEBDZZ; DbgLog(char const *,...)
0x140034226  int     3; Trap to Debugger
0x140034227  mov     rcx, [rbx+8]
0x14003422b  mov     rcx, [rcx+0C0h]; hsem
0x140034232  call    cs:__imp_EngReleaseSemaphore
0x140034239  nop     dword ptr [rax+rax+00h]
0x14003423e  mov     qword ptr [rbx], 0
0x140034245  add     rsp, 20h
0x140034249  pop     rbx
0x14003424a  retn
```
