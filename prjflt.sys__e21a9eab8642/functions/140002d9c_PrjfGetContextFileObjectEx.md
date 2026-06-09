# PrjfGetContextFileObjectEx

- ea: `0x140002d9c`
- end: `0x140002f35`
- name: `PrjfGetContextFileObjectEx`
- size: `409`
- prototype: `char __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, _QWORD *, _QWORD *, PFLT_CONTEXT *Context)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005960`
- `0x140024b24`
- `0x1400280f0`
- `0x140029f60`
- `0x14002aecc`
- `0x14002d048`
- `0x140032db4`
- `0x14003cc14`
- `0x140040510`
- `0x140040670`

## callees

- `0x140002b50`
- `0x140002d9c`
- `0x14000b1d0`
- `0x14000d5e8`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x140002e25`
- `FLTMGR!FltGetStreamHandleContext` at `0x140002e25`
- `FLTMGR!FltReleaseContext` at `0x140002ed2`
- `FLTMGR!FltReleaseContext` at `0x140002ee6`
- `FLTMGR!FltReleaseContext` at `0x140002ed2`
- `FLTMGR!FltReleaseContext` at `0x140002ee6`

## pseudocode

```c
char __fastcall PrjfGetContextFileObjectEx(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        _QWORD *a3,
        _QWORD *a4,
        PFLT_CONTEXT *Context)
{
  __int64 v7; // rdx
  char ContextFileObject; // si
  __int64 v9; // r8

  *a3 = 0;
  *a4 = 0;
  *Context = 0;
  ContextFileObject = PrjfGetContextFileObject(Instance, FileObject);
  if ( ContextFileObject )
  {
    *a4 = 0;
    *a3 = 0;
  }
  else if ( *Context )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(0, v7, v9);
  }
  return ContextFileObject;
}

```

## disassembly

```asm
0x140002d9c  mov     rax, rsp
0x140002d9f  mov     [rax+8], rbx
0x140002da3  push    rbp
0x140002da4  push    rsi
0x140002da5  push    rdi
0x140002da6  push    r12
0x140002da8  push    r13
0x140002daa  push    r14
0x140002dac  push    r15
0x140002dae  sub     rsp, 60h
0x140002db2  mov     r14, [rsp+98h+Context]
0x140002dba  mov     r15, r9
0x140002dbd  mov     rbp, r8
0x140002dc0  mov     qword ptr [r8], 0
0x140002dc7  mov     qword ptr [r9], 0
0x140002dce  lea     r8, [rax+18h]
0x140002dd2  lea     r9, [rax+20h]
0x140002dd6  mov     qword ptr [rax+18h], 0
0x140002dde  mov     qword ptr [r14], 0
0x140002de5  mov     r13, rdx
0x140002de8  mov     r12, rcx
0x140002deb  mov     qword ptr [rax+20h], 0
0x140002df3  call    PrjfGetContextFileObject
0x140002df8  mov     rbx, [rsp+98h+arg_18]
0x140002e00  mov     sil, al
0x140002e03  test    al, al
0x140002e05  jz      loc_140002EC5
0x140002e0b  mov     rdi, [rsp+98h+arg_10]
0x140002e13  test    rbx, rbx
0x140002e16  jz      loc_140002F1E
0x140002e1c  mov     r8, r14; Context
0x140002e1f  mov     rdx, r13; FileObject
0x140002e22  mov     rcx, r12; Instance
0x140002e25  call    cs:__imp_FltGetStreamHandleContext
0x140002e2c  nop     dword ptr [rax+rax+00h]
0x140002e31  mov     r9d, eax
0x140002e34  mov     eax, 80000000h
0x140002e39  lea     ecx, [r9+rax]
0x140002e3d  test    eax, ecx
0x140002e3f  jnz     loc_140002F28
0x140002e45  cmp     r9d, 0C0000225h
0x140002e4c  jz      loc_140002F28
0x140002e52  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140002e58  lea     rax, WPP_RECORDER_INITIALIZED
0x140002e5f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002e66  setnz   r8b
0x140002e6a  and     dl, 2
0x140002e6d  jnz     short loc_140002E74
0x140002e6f  test    r8b, r8b
0x140002e72  jz      short loc_140002EC5
0x140002e74  mov     eax, [r13+50h]
0x140002e78  mov     ecx, 209h
0x140002e7d  mov     [rsp+98h+var_40], eax
0x140002e81  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140002e88  mov     [rsp+98h+var_48], r9d
0x140002e8d  mov     r9, cs:WPP_GLOBAL_Control
0x140002e94  mov     [rsp+98h+var_50], 3D6h
0x140002e9c  mov     [rsp+98h+var_58], rax
0x140002ea1  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140002ea8  mov     [rsp+98h+var_60], rax
0x140002ead  mov     r9, [r9+40h]
0x140002eb1  mov     [rsp+98h+var_68], 16h
0x140002eb8  mov     [rsp+98h+var_70], 9
0x140002ec0  call    WPP_RECORDER_AND_TRACE_SF_sDdd
0x140002ec5  mov     rcx, [rsp+98h+arg_10]; Context
0x140002ecd  test    rcx, rcx
0x140002ed0  jz      short loc_140002EDE
0x140002ed2  call    cs:__imp_FltReleaseContext
0x140002ed9  nop     dword ptr [rax+rax+00h]
0x140002ede  test    rbx, rbx
0x140002ee1  jz      short loc_140002EF2
0x140002ee3  mov     rcx, rbx; Context
0x140002ee6  call    cs:__imp_FltReleaseContext
0x140002eed  nop     dword ptr [rax+rax+00h]
0x140002ef2  test    sil, sil
0x140002ef5  jnz     short loc_140002F02
0x140002ef7  cmp     qword ptr [r14], 0
0x140002efb  jz      short loc_140002F02
0x140002efd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140002f02  mov     rbx, [rsp+98h+arg_0]
0x140002f0a  mov     al, sil
0x140002f0d  add     rsp, 60h
0x140002f11  pop     r15
0x140002f13  pop     r14
0x140002f15  pop     r13
0x140002f17  pop     r12
0x140002f19  pop     rdi
0x140002f1a  pop     rsi
0x140002f1b  pop     rbp
0x140002f1c  retn
0x140002f1e  test    rdi, rdi
0x140002f21  jz      short loc_140002F28
0x140002f23  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140002f28  xor     ecx, ecx
0x140002f2a  mov     [r15], rbx
0x140002f2d  xor     ebx, ebx
0x140002f2f  mov     [rbp+0], rdi
0x140002f33  jmp     short loc_140002ECD
```
