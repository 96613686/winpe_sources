# SURFACCESS::Dispatch(void)

- ea: `0x140027c48`
- end: `0x140027c71`
- name: `?Dispatch@SURFACCESS@@QEAAPEAU_DDI_DISPATCH_TABLE@@XZ`
- size: `41`
- prototype: `struct _DDI_DISPATCH_TABLE *__fastcall(SURFACCESS *__hidden this)`
- caller_count: `22`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140025090`
- `0x1400255b0`
- `0x140025c90`
- `0x1400261a0`
- `0x1400267f0`
- `0x140026d40`
- `0x140027370`
- `0x140034a60`
- `0x140034b30`
- `0x1400355b0`
- `0x140035630`
- `0x1400357a0`
- `0x1400358d0`
- `0x1400359f0`
- `0x140035a90`
- `0x1400361e0`
- `0x1400363d0`
- `0x140036510`
- `0x1400365a0`
- `0x140036670`
- `0x140036830`
- `0x1400368b0`

## callees

- `0x140027c48`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x140027c55`
- `WIN32K!W32GetSessionState` at `0x140027c55`

## pseudocode

```c
struct _DDI_DISPATCH_TABLE *__fastcall SURFACCESS::Dispatch(SURFACCESS *this, __int64 a2)
{
  struct _DDI_DISPATCH_TABLE *result; // rax

  result = (struct _DDI_DISPATCH_TABLE *)*((_QWORD *)this + 2);
  if ( !result )
    return (struct _DDI_DISPATCH_TABLE *)(*(_QWORD *)(W32GetSessionState(this, a2) + 72) + 840LL);
  return result;
}

```

## disassembly

```asm
0x140027c48  sub     rsp, 28h
0x140027c4c  mov     rax, [rcx+10h]
0x140027c50  test    rax, rax
0x140027c53  jnz     short loc_140027C6B
0x140027c55  call    cs:__imp_W32GetSessionState
0x140027c5c  nop     dword ptr [rax+rax+00h]
0x140027c61  mov     rax, [rax+48h]
0x140027c65  add     rax, 348h
0x140027c6b  add     rsp, 28h
0x140027c6f  retn
```
