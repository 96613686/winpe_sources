# PrjfGetContextFileObject

- ea: `0x140002b50`
- end: `0x140002d93`
- name: `PrjfGetContextFileObject`
- size: `579`
- prototype: `char __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64 *, PFLT_CONTEXT *)`
- caller_count: `17`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002d9c`
- `0x1400047cc`
- `0x140006c28`
- `0x140007cec`
- `0x140022320`
- `0x14002a260`
- `0x14002b0d0`
- `0x14002b640`
- `0x14002ba10`
- `0x14002d12c`
- `0x14002d988`
- `0x14003005c`
- `0x1400349fc`
- `0x14003df88`
- `0x140041e28`
- `0x140043844`
- `0x140043d88`

## callees

- `0x140002b50`
- `0x14000b1a0`
- `0x14000b1d0`
- `0x14000d5e8`

## import_xrefs

- `FLTMGR!FltGetFileContext` at `0x140002c46`
- `FLTMGR!FltGetFileContext` at `0x140002c46`
- `FLTMGR!FltGetStreamContext` at `0x140002b94`
- `FLTMGR!FltGetStreamContext` at `0x140002b94`
- `FLTMGR!FltReleaseContext` at `0x140002d31`
- `FLTMGR!FltReleaseContext` at `0x140002d4a`
- `FLTMGR!FltReleaseContext` at `0x140002d31`
- `FLTMGR!FltReleaseContext` at `0x140002d4a`

## pseudocode

```c
char __fastcall PrjfGetContextFileObject(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 *a3,
        PFLT_CONTEXT *a4)
{
  char v8; // di
  NTSTATUS StreamContext; // eax
  __int64 v10; // rdx
  int v11; // r8d
  __int64 v12; // rcx
  int v13; // r8d
  PFLT_CONTEXT v14; // rax
  PFLT_CONTEXT v15; // rcx
  __int64 v16; // rax
  PFLT_CONTEXT Context; // [rsp+90h] [rbp+18h] BYREF
  PFLT_CONTEXT v19; // [rsp+98h] [rbp+20h] BYREF

  *a3 = 0;
  Context = 0;
  v19 = 0;
  *a4 = 0;
  v8 = 0;
  StreamContext = FltGetStreamContext(Instance, FileObject, &v19);
  if ( StreamContext != -1073741275 && StreamContext != -1073741637 )
  {
    if ( StreamContext >= 0 )
    {
      if ( FltGetFileContext(Instance, FileObject, &Context) >= 0 )
      {
        v14 = Context;
        if ( *((_BYTE *)Context + 281) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v10);
          v14 = Context;
        }
        *a3 = (__int64)v14;
        v8 = 1;
        *a4 = v19;
        Context = 0;
        v19 = 0;
      }
      else
      {
        if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 2;
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdd(521, v10, v13, *((_QWORD *)WPP_GLOBAL_Control + 8));
        }
        MicrosoftTelemetryAssertTriggeredMsgKM("Have stream context but no file context.");
      }
    }
    else
    {
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 2;
      if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdd(521, v10, v11, *((_QWORD *)WPP_GLOBAL_Control + 8));
      }
    }
  }
  if ( v19 )
    FltReleaseContext(v19);
  v15 = Context;
  if ( Context )
    FltReleaseContext(Context);
  v16 = *a3;
  if ( v8 )
  {
    if ( !v16 || !*a4 )
LABEL_25:
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v15, v10);
  }
  else if ( v16 || *a4 )
  {
    goto LABEL_25;
  }
  return v8;
}

```

## disassembly

```asm
0x140002b50  mov     rax, rsp
0x140002b53  mov     [rax+8], rbx
0x140002b57  mov     [rax+10h], rbp
0x140002b5b  push    rsi
0x140002b5c  push    rdi
0x140002b5d  push    r14
0x140002b5f  sub     rsp, 60h
0x140002b63  mov     rsi, r8
0x140002b66  mov     qword ptr [r8], 0
0x140002b6d  lea     r8, [rax+20h]; Context
0x140002b71  mov     qword ptr [rax+18h], 0
0x140002b79  mov     rbx, r9
0x140002b7c  mov     qword ptr [rax+20h], 0
0x140002b84  mov     rbp, rdx
0x140002b87  mov     qword ptr [r9], 0
0x140002b8e  mov     r14, rcx
0x140002b91  xor     dil, dil
0x140002b94  call    cs:__imp_FltGetStreamContext
0x140002b9b  nop     dword ptr [rax+rax+00h]
0x140002ba0  mov     r9d, eax
0x140002ba3  cmp     eax, 0C0000225h
0x140002ba8  jz      loc_140002D24
0x140002bae  cmp     eax, 0C00000BBh
0x140002bb3  jz      loc_140002D24
0x140002bb9  test    eax, eax
0x140002bbb  jns     short loc_140002C38
0x140002bbd  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140002bc3  lea     rax, WPP_RECORDER_INITIALIZED
0x140002bca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002bd1  setnz   r8b
0x140002bd5  and     dl, 2
0x140002bd8  jnz     short loc_140002BE3
0x140002bda  test    r8b, r8b
0x140002bdd  jz      loc_140002D24
0x140002be3  mov     eax, [rbp+50h]
0x140002be6  mov     ecx, 209h
0x140002beb  mov     [rsp+78h+var_20], eax
0x140002bef  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140002bf6  mov     [rsp+78h+var_28], r9d
0x140002bfb  mov     r9, cs:WPP_GLOBAL_Control
0x140002c02  mov     [rsp+78h+var_30], 335h
0x140002c0a  mov     [rsp+78h+var_38], rax
0x140002c0f  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140002c16  mov     [rsp+78h+var_40], rax
0x140002c1b  mov     r9, [r9+40h]
0x140002c1f  mov     [rsp+78h+var_48], 14h
0x140002c26  mov     [rsp+78h+var_50], 9
0x140002c2e  call    WPP_RECORDER_AND_TRACE_SF_sDdd
0x140002c33  jmp     loc_140002D24
0x140002c38  lea     r8, [rsp+78h+Context]; Context
0x140002c40  mov     rdx, rbp; FileObject
0x140002c43  mov     rcx, r14; Instance
0x140002c46  call    cs:__imp_FltGetFileContext
0x140002c4d  nop     dword ptr [rax+rax+00h]
0x140002c52  mov     r9d, eax
0x140002c55  test    eax, eax
0x140002c57  jns     loc_140002CDD
0x140002c5d  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140002c63  lea     rax, WPP_RECORDER_INITIALIZED
0x140002c6a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002c71  setnz   r8b
0x140002c75  and     dl, 2
0x140002c78  jnz     short loc_140002C7F
0x140002c7a  test    r8b, r8b
0x140002c7d  jz      short loc_140002CCF
0x140002c7f  mov     eax, [rbp+50h]
0x140002c82  mov     ecx, 209h
0x140002c87  mov     [rsp+78h+var_20], eax
0x140002c8b  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140002c92  mov     [rsp+78h+var_28], r9d
0x140002c97  mov     r9, cs:WPP_GLOBAL_Control
0x140002c9e  mov     [rsp+78h+var_30], 345h
0x140002ca6  mov     [rsp+78h+var_38], rax
0x140002cab  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140002cb2  mov     [rsp+78h+var_40], rax
0x140002cb7  mov     r9, [r9+40h]
0x140002cbb  mov     [rsp+78h+var_48], 15h
0x140002cc2  mov     [rsp+78h+var_50], 9
0x140002cca  call    WPP_RECORDER_AND_TRACE_SF_sDdd
0x140002ccf  lea     rcx, aHaveStreamCont; "Have stream context but no file context"...
0x140002cd6  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140002cdb  jmp     short loc_140002D24
0x140002cdd  mov     rax, [rsp+78h+Context]
0x140002ce5  cmp     [rax+119h], dil
0x140002cec  jz      short loc_140002CFB
0x140002cee  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140002cf3  mov     rax, [rsp+78h+Context]
0x140002cfb  mov     [rsi], rax
0x140002cfe  mov     dil, 1
0x140002d01  mov     rax, [rsp+78h+arg_18]
0x140002d09  mov     [rbx], rax
0x140002d0c  mov     [rsp+78h+Context], 0
0x140002d18  mov     [rsp+78h+arg_18], 0
0x140002d24  mov     rcx, [rsp+78h+arg_18]; Context
0x140002d2c  test    rcx, rcx
0x140002d2f  jz      short loc_140002D3D
0x140002d31  call    cs:__imp_FltReleaseContext
0x140002d38  nop     dword ptr [rax+rax+00h]
0x140002d3d  mov     rcx, [rsp+78h+Context]; Context
0x140002d45  test    rcx, rcx
0x140002d48  jz      short loc_140002D56
0x140002d4a  call    cs:__imp_FltReleaseContext
0x140002d51  nop     dword ptr [rax+rax+00h]
0x140002d56  mov     rax, [rsi]
0x140002d59  test    dil, dil
0x140002d5c  jz      short loc_140002D6B
0x140002d5e  test    rax, rax
0x140002d61  jz      short loc_140002D75
0x140002d63  cmp     qword ptr [rbx], 0
0x140002d67  jnz     short loc_140002D7A
0x140002d69  jmp     short loc_140002D75
0x140002d6b  test    rax, rax
0x140002d6e  jnz     short loc_140002D75
0x140002d70  cmp     [rbx], rax
0x140002d73  jz      short loc_140002D7A
0x140002d75  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140002d7a  lea     r11, [rsp+78h+var_18]
0x140002d7f  mov     al, dil
0x140002d82  mov     rbx, [r11+20h]
0x140002d86  mov     rbp, [r11+28h]
0x140002d8a  mov     rsp, r11
0x140002d8d  pop     r14
0x140002d8f  pop     rdi
0x140002d90  pop     rsi
0x140002d91  retn
```
