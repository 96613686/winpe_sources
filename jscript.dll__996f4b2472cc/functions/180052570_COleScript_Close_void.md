# COleScript::Close(void)

- ea: `0x180052570`
- end: `0x1800525c8`
- name: `?Close@COleScript@@UEAAJXZ`
- size: `88`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180052880`

## callees

- `0x18001643c`
- `0x180052570`
- `0x18007cba0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005259c`
- `KERNEL32!GetCurrentThreadId` at `0x18005259c`

## pseudocode

```c
__int64 __fastcall COleScript::Close(COleScript *this)
{
  int v3; // ebx

  if ( *((_DWORD *)this + 71) )
    return 2147500037LL;
  if ( *((_DWORD *)this + 65) != -1 )
  {
    v3 = *((_DWORD *)this + 65);
    if ( v3 != GetCurrentThreadId() )
      COleScript::LogTelemetryOnCloseMultithreading(this);
  }
  return COleScript::CloseInternal(this);
}

```

## disassembly

```asm
0x180052570  mov     [rsp+arg_0], rbx
0x180052575  push    rdi
0x180052576  sub     rsp, 20h
0x18005257a  cmp     dword ptr [rcx+11Ch], 0
0x180052581  mov     rdi, rcx
0x180052584  jz      short loc_18005258D
0x180052586  mov     eax, 80004005h
0x18005258b  jmp     short loc_1800525BC
0x18005258d  cmp     dword ptr [rcx+104h], 0FFFFFFFFh
0x180052594  jz      short loc_1800525B4
0x180052596  mov     ebx, [rcx+104h]
0x18005259c  call    cs:__imp_GetCurrentThreadId
0x1800525a3  nop     dword ptr [rax+rax+00h]
0x1800525a8  cmp     ebx, eax
0x1800525aa  jz      short loc_1800525B4
0x1800525ac  mov     rcx, rdi; this
0x1800525af  call    ?LogTelemetryOnCloseMultithreading@COleScript@@QEAAXXZ; COleScript::LogTelemetryOnCloseMultithreading(void)
0x1800525b4  mov     rcx, rdi; this
0x1800525b7  call    ?CloseInternal@COleScript@@QEAAJXZ; COleScript::CloseInternal(void)
0x1800525bc  mov     rbx, [rsp+28h+arg_0]
0x1800525c1  add     rsp, 20h
0x1800525c5  pop     rdi
0x1800525c6  retn
```
