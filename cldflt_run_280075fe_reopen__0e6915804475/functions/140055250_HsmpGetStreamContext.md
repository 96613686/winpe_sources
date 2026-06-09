# HsmpGetStreamContext

- ea: `0x140055250`
- end: `0x140055300`
- name: `HsmpGetStreamContext`
- size: `176`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400021e0`
- `0x1400430ec`
- `0x140043234`
- `0x140046bd0`
- `0x1400520d0`
- `0x1400536e0`
- `0x140055308`

## callees

- `0x140006f40`
- `0x140055250`

## import_xrefs

- `FLTMGR!FltGetStreamContext` at `0x140055277`
- `FLTMGR!FltGetStreamContext` at `0x140055277`
- `FLTMGR!FltDeleteContext` at `0x1400552e6`
- `FLTMGR!FltDeleteContext` at `0x1400552e6`
- `FLTMGR!FltGetRequestorProcess` at `0x1400552aa`
- `FLTMGR!FltGetRequestorProcess` at `0x1400552aa`
- `FLTMGR!FltReleaseContext` at `0x1400552c7`
- `FLTMGR!FltReleaseContext` at `0x1400552c7`

## pseudocode

```c
PFLT_CONTEXT __fastcall HsmpGetStreamContext(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject)
{
  PFLT_CONTEXT v5; // rcx
  PEPROCESS RequestorProcess; // rax
  PFLT_CONTEXT Context; // [rsp+48h] [rbp+20h] BYREF

  Context = 0;
  FltGetStreamContext(Instance, FileObject, &Context);
  v5 = Context;
  if ( !Context )
    return Context;
  if ( (*((_DWORD *)Context + 7) & 1) == 0 )
  {
    if ( Context )
    {
      FltDeleteContext(Context);
      goto LABEL_6;
    }
    return Context;
  }
  if ( *(PFLT_INSTANCE *)(*(_QWORD *)(*((_QWORD *)Context + 2) + 16LL) + 32LL) != Instance )
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
0x140055250  mov     [rsp+arg_0], rbx
0x140055255  push    rdi
0x140055256  sub     rsp, 20h
0x14005525a  mov     rax, r8
0x14005525d  mov     [rsp+28h+Context], 0
0x140055266  mov     rbx, rdx
0x140055269  lea     r8, [rsp+28h+Context]; Context
0x14005526e  mov     rdi, rcx
0x140055271  mov     rdx, rax; FileObject
0x140055274  mov     rcx, rbx; Instance
0x140055277  call    cs:__imp_FltGetStreamContext
0x14005527e  nop     dword ptr [rax+rax+00h]
0x140055283  mov     rcx, [rsp+28h+Context]; Context
0x140055288  test    rcx, rcx
0x14005528b  jz      short loc_1400552FB
0x14005528d  mov     eax, [rcx+1Ch]
0x140055290  test    al, 1
0x140055292  jz      short loc_1400552E1
0x140055294  mov     rax, [rcx+10h]
0x140055298  mov     rdx, [rax+10h]
0x14005529c  cmp     [rdx+20h], rbx
0x1400552a0  jnz     short loc_1400552C7
0x1400552a2  test    rdi, rdi
0x1400552a5  jz      short loc_1400552FB
0x1400552a7  mov     rcx, rdi; CallbackData
0x1400552aa  call    cs:__imp_FltGetRequestorProcess
0x1400552b1  nop     dword ptr [rax+rax+00h]
0x1400552b6  mov     rcx, rax
0x1400552b9  call    HsmOsIsPassThroughModeEnabled
0x1400552be  test    al, al
0x1400552c0  jz      short loc_1400552F4
0x1400552c2  mov     rcx, [rsp+28h+Context]; Context
0x1400552c7  call    cs:__imp_FltReleaseContext
0x1400552ce  nop     dword ptr [rax+rax+00h]
0x1400552d3  xor     eax, eax
0x1400552d5  mov     rbx, [rsp+28h+arg_0]
0x1400552da  add     rsp, 20h
0x1400552de  pop     rdi
0x1400552df  retn
0x1400552e1  test    rcx, rcx
0x1400552e4  jz      short loc_1400552FB
0x1400552e6  call    cs:__imp_FltDeleteContext
0x1400552ed  nop     dword ptr [rax+rax+00h]
0x1400552f2  jmp     short loc_1400552C2
0x1400552f4  mov     rax, [rsp+28h+Context]
0x1400552f9  jmp     short loc_1400552D5
0x1400552fb  mov     rax, rcx
0x1400552fe  jmp     short loc_1400552D5
```
