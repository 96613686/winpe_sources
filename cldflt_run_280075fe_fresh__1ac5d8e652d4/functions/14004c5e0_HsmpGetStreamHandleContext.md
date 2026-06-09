# HsmpGetStreamHandleContext

- ea: `0x14004c5e0`
- end: `0x14004c694`
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
- `0x1400450e0`
- `0x14004b934`
- `0x14004c0c0`
- `0x140051c80`
- `0x1400520d0`
- `0x14005c8c0`
- `0x140062594`
- `0x14006474c`
- `0x1400801f0`

## callees

- `0x140006f40`
- `0x14004c5e0`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x14004c607`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004c607`
- `FLTMGR!FltDeleteContext` at `0x14004c67f`
- `FLTMGR!FltDeleteContext` at `0x14004c67f`
- `FLTMGR!FltGetRequestorProcess` at `0x14004c63e`
- `FLTMGR!FltGetRequestorProcess` at `0x14004c63e`
- `FLTMGR!FltReleaseContext` at `0x14004c65b`
- `FLTMGR!FltReleaseContext` at `0x14004c65b`

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
0x14004c5e0  mov     [rsp+arg_0], rbx
0x14004c5e5  push    rdi
0x14004c5e6  sub     rsp, 20h
0x14004c5ea  mov     rax, r8
0x14004c5ed  mov     [rsp+28h+Context], 0
0x14004c5f6  mov     rbx, rdx
0x14004c5f9  lea     r8, [rsp+28h+Context]; Context
0x14004c5fe  mov     rdi, rcx
0x14004c601  mov     rdx, rax; FileObject
0x14004c604  mov     rcx, rbx; Instance
0x14004c607  call    cs:__imp_FltGetStreamHandleContext
0x14004c60e  nop     dword ptr [rax+rax+00h]
0x14004c613  mov     rcx, [rsp+28h+Context]; Context
0x14004c618  test    rcx, rcx
0x14004c61b  jz      short loc_14004C675
0x14004c61d  mov     rdx, [rcx+10h]
0x14004c621  mov     eax, [rdx+1Ch]
0x14004c624  test    al, 1
0x14004c626  jz      short loc_14004C67A
0x14004c628  mov     rax, [rdx+10h]
0x14004c62c  mov     rdx, [rax+10h]
0x14004c630  cmp     [rdx+20h], rbx
0x14004c634  jnz     short loc_14004C65B
0x14004c636  test    rdi, rdi
0x14004c639  jz      short loc_14004C675
0x14004c63b  mov     rcx, rdi; CallbackData
0x14004c63e  call    cs:__imp_FltGetRequestorProcess
0x14004c645  nop     dword ptr [rax+rax+00h]
0x14004c64a  mov     rcx, rax
0x14004c64d  call    HsmOsIsPassThroughModeEnabled
0x14004c652  test    al, al
0x14004c654  jz      short loc_14004C68D
0x14004c656  mov     rcx, [rsp+28h+Context]; Context
0x14004c65b  call    cs:__imp_FltReleaseContext
0x14004c662  nop     dword ptr [rax+rax+00h]
0x14004c667  xor     eax, eax
0x14004c669  mov     rbx, [rsp+28h+arg_0]
0x14004c66e  add     rsp, 20h
0x14004c672  pop     rdi
0x14004c673  retn
0x14004c675  mov     rax, rcx
0x14004c678  jmp     short loc_14004C669
0x14004c67a  test    rcx, rcx
0x14004c67d  jz      short loc_14004C675
0x14004c67f  call    cs:__imp_FltDeleteContext
0x14004c686  nop     dword ptr [rax+rax+00h]
0x14004c68b  jmp     short loc_14004C656
0x14004c68d  mov     rax, [rsp+28h+Context]
0x14004c692  jmp     short loc_14004C669
```
