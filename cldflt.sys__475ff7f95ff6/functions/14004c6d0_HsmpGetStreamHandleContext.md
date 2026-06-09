# HsmpGetStreamHandleContext

- ea: `0x14004c6d0`
- end: `0x14004c784`
- name: `HsmpGetStreamHandleContext`
- size: `180`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e40`
- `0x1400021e0`
- `0x140009240`
- `0x1400092c0`
- `0x140034010`
- `0x1400451d0`
- `0x14004ba24`
- `0x14004c1b0`
- `0x140051da0`
- `0x1400521f0`
- `0x14005c9e0`
- `0x1400626b4`
- `0x14006486c`
- `0x140080390`

## callees

- `0x140006f40`
- `0x14004c6d0`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x14004c6f7`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004c6f7`
- `FLTMGR!FltDeleteContext` at `0x14004c76f`
- `FLTMGR!FltDeleteContext` at `0x14004c76f`
- `FLTMGR!FltGetRequestorProcess` at `0x14004c72e`
- `FLTMGR!FltGetRequestorProcess` at `0x14004c72e`
- `FLTMGR!FltReleaseContext` at `0x14004c74b`
- `FLTMGR!FltReleaseContext` at `0x14004c74b`

## pseudocode

```c
PFLT_CONTEXT __fastcall HsmpGetStreamHandleContext(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject)
{
  PFLT_CONTEXT v5; // rcx
  __int64 v6; // rdx
  PEPROCESS RequestorProcess; // rax
  PFLT_CONTEXT Context; // [rsp+48h] [rbp+20h] BYREF

  Context = 0;
  FltGetStreamHandleContext(Instance, FileObject, &Context);
  v5 = Context;
  if ( !Context )
    return Context;
  v6 = *((_QWORD *)Context + 2);
  if ( (*(_DWORD *)(v6 + 28) & 1) == 0 )
  {
    if ( Context )
    {
      FltDeleteContext(Context);
      goto LABEL_6;
    }
    return Context;
  }
  if ( *(PFLT_INSTANCE *)(*(_QWORD *)(*(_QWORD *)(v6 + 16) + 16LL) + 32LL) != Instance )
  {
LABEL_7:
    FltReleaseContext(v5);
    return 0;
  }
  if ( !CallbackData )
    return Context;
  RequestorProcess = FltGetRequestorProcess(CallbackData);
  if ( (unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
  {
LABEL_6:
    v5 = Context;
    goto LABEL_7;
  }
  return Context;
}

```

## disassembly

```asm
0x14004c6d0  mov     [rsp+arg_0], rbx
0x14004c6d5  push    rdi
0x14004c6d6  sub     rsp, 20h
0x14004c6da  mov     rax, r8
0x14004c6dd  mov     [rsp+28h+Context], 0
0x14004c6e6  mov     rbx, rdx
0x14004c6e9  lea     r8, [rsp+28h+Context]; Context
0x14004c6ee  mov     rdi, rcx
0x14004c6f1  mov     rdx, rax; FileObject
0x14004c6f4  mov     rcx, rbx; Instance
0x14004c6f7  call    cs:__imp_FltGetStreamHandleContext
0x14004c6fe  nop     dword ptr [rax+rax+00h]
0x14004c703  mov     rcx, [rsp+28h+Context]; Context
0x14004c708  test    rcx, rcx
0x14004c70b  jz      short loc_14004C765
0x14004c70d  mov     rdx, [rcx+10h]
0x14004c711  mov     eax, [rdx+1Ch]
0x14004c714  test    al, 1
0x14004c716  jz      short loc_14004C76A
0x14004c718  mov     rax, [rdx+10h]
0x14004c71c  mov     rdx, [rax+10h]
0x14004c720  cmp     [rdx+20h], rbx
0x14004c724  jnz     short loc_14004C74B
0x14004c726  test    rdi, rdi
0x14004c729  jz      short loc_14004C765
0x14004c72b  mov     rcx, rdi; CallbackData
0x14004c72e  call    cs:__imp_FltGetRequestorProcess
0x14004c735  nop     dword ptr [rax+rax+00h]
0x14004c73a  mov     rcx, rax
0x14004c73d  call    HsmOsIsPassThroughModeEnabled
0x14004c742  test    al, al
0x14004c744  jz      short loc_14004C77D
0x14004c746  mov     rcx, [rsp+28h+Context]; Context
0x14004c74b  call    cs:__imp_FltReleaseContext
0x14004c752  nop     dword ptr [rax+rax+00h]
0x14004c757  xor     eax, eax
0x14004c759  mov     rbx, [rsp+28h+arg_0]
0x14004c75e  add     rsp, 20h
0x14004c762  pop     rdi
0x14004c763  retn
0x14004c765  mov     rax, rcx
0x14004c768  jmp     short loc_14004C759
0x14004c76a  test    rcx, rcx
0x14004c76d  jz      short loc_14004C765
0x14004c76f  call    cs:__imp_FltDeleteContext
0x14004c776  nop     dword ptr [rax+rax+00h]
0x14004c77b  jmp     short loc_14004C746
0x14004c77d  mov     rax, [rsp+28h+Context]
0x14004c782  jmp     short loc_14004C759
```
