# HsmpGetStreamContext

- ea: `0x140055370`
- end: `0x140055420`
- name: `HsmpGetStreamContext`
- size: `176`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400021e0`
- `0x1400431dc`
- `0x140043324`
- `0x140046cc0`
- `0x1400521f0`
- `0x140053800`
- `0x140055428`

## callees

- `0x140006f40`
- `0x140055370`

## import_xrefs

- `FLTMGR!FltGetStreamContext` at `0x140055397`
- `FLTMGR!FltGetStreamContext` at `0x140055397`
- `FLTMGR!FltDeleteContext` at `0x140055406`
- `FLTMGR!FltDeleteContext` at `0x140055406`
- `FLTMGR!FltGetRequestorProcess` at `0x1400553ca`
- `FLTMGR!FltGetRequestorProcess` at `0x1400553ca`
- `FLTMGR!FltReleaseContext` at `0x1400553e7`
- `FLTMGR!FltReleaseContext` at `0x1400553e7`

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
0x140055370  mov     [rsp+arg_0], rbx
0x140055375  push    rdi
0x140055376  sub     rsp, 20h
0x14005537a  mov     rax, r8
0x14005537d  mov     [rsp+28h+Context], 0
0x140055386  mov     rbx, rdx
0x140055389  lea     r8, [rsp+28h+Context]; Context
0x14005538e  mov     rdi, rcx
0x140055391  mov     rdx, rax; FileObject
0x140055394  mov     rcx, rbx; Instance
0x140055397  call    cs:__imp_FltGetStreamContext
0x14005539e  nop     dword ptr [rax+rax+00h]
0x1400553a3  mov     rcx, [rsp+28h+Context]; Context
0x1400553a8  test    rcx, rcx
0x1400553ab  jz      short loc_14005541B
0x1400553ad  mov     eax, [rcx+1Ch]
0x1400553b0  test    al, 1
0x1400553b2  jz      short loc_140055401
0x1400553b4  mov     rax, [rcx+10h]
0x1400553b8  mov     rdx, [rax+10h]
0x1400553bc  cmp     [rdx+20h], rbx
0x1400553c0  jnz     short loc_1400553E7
0x1400553c2  test    rdi, rdi
0x1400553c5  jz      short loc_14005541B
0x1400553c7  mov     rcx, rdi; CallbackData
0x1400553ca  call    cs:__imp_FltGetRequestorProcess
0x1400553d1  nop     dword ptr [rax+rax+00h]
0x1400553d6  mov     rcx, rax
0x1400553d9  call    HsmOsIsPassThroughModeEnabled
0x1400553de  test    al, al
0x1400553e0  jz      short loc_140055414
0x1400553e2  mov     rcx, [rsp+28h+Context]; Context
0x1400553e7  call    cs:__imp_FltReleaseContext
0x1400553ee  nop     dword ptr [rax+rax+00h]
0x1400553f3  xor     eax, eax
0x1400553f5  mov     rbx, [rsp+28h+arg_0]
0x1400553fa  add     rsp, 20h
0x1400553fe  pop     rdi
0x1400553ff  retn
0x140055401  test    rcx, rcx
0x140055404  jz      short loc_14005541B
0x140055406  call    cs:__imp_FltDeleteContext
0x14005540d  nop     dword ptr [rax+rax+00h]
0x140055412  jmp     short loc_1400553E2
0x140055414  mov     rax, [rsp+28h+Context]
0x140055419  jmp     short loc_1400553F5
0x14005541b  mov     rax, rcx
0x14005541e  jmp     short loc_1400553F5
```
