# COleScript::Close(void)

- ea: `0x180051820`
- end: `0x180051871`
- name: `?Close@COleScript@@UEAAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180051b10`

## callees

- `0x180019420`
- `0x180051820`
- `0x18007b384`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005184c`
- `KERNEL32!GetCurrentThreadId` at `0x18005184c`

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
0x180051820  mov     [rsp+arg_0], rbx
0x180051825  push    rdi
0x180051826  sub     rsp, 20h
0x18005182a  cmp     dword ptr [rcx+11Ch], 0
0x180051831  mov     rdi, rcx
0x180051834  jz      short loc_18005183D
0x180051836  mov     eax, 80004005h
0x18005183b  jmp     short loc_180051866
0x18005183d  cmp     dword ptr [rcx+104h], 0FFFFFFFFh
0x180051844  jz      short loc_18005185E
0x180051846  mov     ebx, [rcx+104h]
0x18005184c  call    cs:__imp_GetCurrentThreadId
0x180051852  cmp     ebx, eax
0x180051854  jz      short loc_18005185E
0x180051856  mov     rcx, rdi; this
0x180051859  call    ?LogTelemetryOnCloseMultithreading@COleScript@@QEAAXXZ; COleScript::LogTelemetryOnCloseMultithreading(void)
0x18005185e  mov     rcx, rdi; this
0x180051861  call    ?CloseInternal@COleScript@@QEAAJXZ; COleScript::CloseInternal(void)
0x180051866  mov     rbx, [rsp+28h+arg_0]
0x18005186b  add     rsp, 20h
0x18005186f  pop     rdi
0x180051870  retn
```
