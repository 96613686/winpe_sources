# PrjfGetSetStreamHandleContext

- ea: `0x140021c5c`
- end: `0x140021f86`
- name: `PrjfGetSetStreamHandleContext`
- size: `810`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_CONTEXT Context@<r8>, char, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140002f3c`
- `0x14002a6b4`
- `0x14002aa24`
- `0x14002b640`

## callees

- `0x14000ba20`
- `0x14000be80`
- `0x14000d128`
- `0x140021c5c`
- `0x14003b380`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x140021e7e`
- `ntoskrnl!IoGetCurrentProcess` at `0x140021e7e`
- `ntoskrnl!ExUuidCreate` at `0x140021de3`
- `ntoskrnl!ExUuidCreate` at `0x140021de3`
- `ntoskrnl!KeInitializeEvent` at `0x140021da1`
- `ntoskrnl!KeInitializeEvent` at `0x140021da1`
- `FLTMGR!FltSetStreamHandleContext` at `0x140021f0b`
- `FLTMGR!FltSetStreamHandleContext` at `0x140021f0b`
- `FLTMGR!FltGetStreamHandleContext` at `0x140021cb3`
- `FLTMGR!FltGetStreamHandleContext` at `0x140021cb3`
- `FLTMGR!FltReferenceContext` at `0x140021db8`
- `FLTMGR!FltReferenceContext` at `0x140021db8`
- `FLTMGR!FltAllocateContext` at `0x140021ceb`
- `FLTMGR!FltAllocateContext` at `0x140021ceb`
- `FLTMGR!FltReleaseContext` at `0x140021f21`
- `FLTMGR!FltReleaseContext` at `0x140021f59`
- `FLTMGR!FltReleaseContext` at `0x140021f21`
- `FLTMGR!FltReleaseContext` at `0x140021f59`

## pseudocode

```c
__int64 __fastcall PrjfGetSetStreamHandleContext(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CONTEXT Context,
        _DWORD *a4,
        char a5,
        _QWORD *a6)
{
  NTSTATUS StreamHandleContext; // eax
  unsigned int v11; // ebx
  NTSTATUS v12; // eax
  int v13; // edx
  int v14; // r8d
  _QWORD *v15; // rax
  NTSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  struct _KPROCESS *CurrentProcess; // rax
  int inited; // eax
  int v21; // edx
  int v22; // r8d
  PFLT_CONTEXT v23; // rax
  PFLT_CONTEXT Contexta; // [rsp+60h] [rbp-19h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+68h] [rbp-11h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-9h] BYREF

  Contexta = 0;
  OldContext = 0;
  *a6 = 0;
  Uuid = 0;
  StreamHandleContext = FltGetStreamHandleContext(Instance, FileObject, &Contexta);
  v11 = StreamHandleContext;
  if ( StreamHandleContext == -1073741275 )
  {
    v12 = FltAllocateContext(Globals, 0x10u, 0x268u, (POOL_TYPE)512, &Contexta);
    v11 = v12;
    if ( v12 < 0 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = BYTE1(xmmword_14001A3D0) & 2;
        LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          521,
          v13,
          v14,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          9,
          30,
          (__int64)&WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          13,
          v12);
      }
      return v11;
    }
    memset(Contexta, 0, 0x268u);
    v15 = Contexta;
    *((_QWORD *)Contexta + 1) = Contexta;
    *v15 = v15;
    KeInitializeEvent((PRKEVENT)((char *)Contexta + 16), SynchronizationEvent, 1u);
    *((_QWORD *)Contexta + 6) = Context;
    FltReferenceContext(Context);
    if ( a5 )
      *((_DWORD *)Contexta + 10) |= 1u;
    if ( *a4 == 1 )
      *((_DWORD *)Contexta + 10) |= 0x18u;
    v16 = ExUuidCreate(&Uuid);
    v11 = v16;
    if ( v16 < 0 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = BYTE1(xmmword_14001A3D0) & 2;
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          521,
          v17,
          v18,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          9,
          31,
          (__int64)&WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          43,
          v16);
      }
      goto LABEL_25;
    }
    *(UUID *)((char *)Contexta + 56) = Uuid;
    CurrentProcess = IoGetCurrentProcess();
    inited = PrjfInitProcessInfo(CurrentProcess);
    v11 = inited;
    if ( inited < 0 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = BYTE1(xmmword_14001A3D0) & 2;
        LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          521,
          v21,
          v22,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          9,
          32,
          (__int64)&WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          59,
          inited);
      }
      goto LABEL_25;
    }
    v11 = FltSetStreamHandleContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, Contexta, &OldContext);
    if ( (v11 & 0x80000000) != 0 )
    {
      FltReleaseContext(Contexta);
      if ( v11 != -1071906814 )
        return v11;
      v23 = OldContext;
      v11 = 0;
      goto LABEL_24;
    }
  }
  else if ( StreamHandleContext < 0 )
  {
    goto LABEL_25;
  }
  v23 = Contexta;
LABEL_24:
  *a6 = v23;
  Contexta = 0;
LABEL_25:
  if ( Contexta )
    FltReleaseContext(Contexta);
  return v11;
}

```

## disassembly

```asm
0x140021c5c  push    rbp
0x140021c5e  push    rbx
0x140021c5f  push    rsi
0x140021c60  push    rdi
0x140021c61  push    r12
0x140021c63  push    r14
0x140021c65  push    r15
0x140021c67  lea     rbp, [rsp-17h]
0x140021c6c  sub     rsp, 90h
0x140021c73  mov     rax, cs:__security_cookie
0x140021c7a  xor     rax, rsp
0x140021c7d  mov     [rbp+47h+var_40], rax
0x140021c81  mov     rsi, [rbp+47h+arg_28]
0x140021c85  mov     r14, r8
0x140021c88  xorps   xmm0, xmm0
0x140021c8b  mov     [rbp+47h+Context], 0
0x140021c93  lea     r8, [rbp+47h+Context]; Context
0x140021c97  mov     [rbp+47h+OldContext], 0
0x140021c9f  mov     rdi, r9
0x140021ca2  mov     r12, rdx
0x140021ca5  mov     qword ptr [rsi], 0
0x140021cac  mov     r15, rcx
0x140021caf  movups  xmmword ptr [rbp+47h+Uuid.Data1], xmm0
0x140021cb3  call    cs:__imp_FltGetStreamHandleContext
0x140021cba  nop     dword ptr [rax+rax+00h]
0x140021cbf  mov     ebx, eax
0x140021cc1  cmp     eax, 0C0000225h
0x140021cc6  jnz     loc_140021F3D
0x140021ccc  mov     rcx, cs:Globals; Filter
0x140021cd3  lea     rax, [rbp+47h+Context]
0x140021cd7  mov     r9d, 200h; PoolType
0x140021cdd  mov     [rsp+0C0h+ReturnedContext], rax; ReturnedContext
0x140021ce2  mov     edx, 10h; ContextType
0x140021ce7  lea     r8d, [r9+68h]; ContextSize
0x140021ceb  call    cs:__imp_FltAllocateContext
0x140021cf2  nop     dword ptr [rax+rax+00h]
0x140021cf7  mov     ebx, eax
0x140021cf9  test    eax, eax
0x140021cfb  jns     short loc_140021D75
0x140021cfd  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140021d03  lea     rcx, WPP_RECORDER_INITIALIZED
0x140021d0a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140021d11  setnz   r8b
0x140021d15  and     dl, 2
0x140021d18  jnz     short loc_140021D23
0x140021d1a  test    r8b, r8b
0x140021d1d  jz      loc_140021F65
0x140021d23  mov     r9, cs:WPP_GLOBAL_Control
0x140021d2a  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140021d31  mov     [rsp+0C0h+var_70], ebx
0x140021d35  mov     ecx, 209h
0x140021d3a  mov     [rsp+0C0h+var_78], 60Dh
0x140021d42  mov     [rsp+0C0h+var_80], rax
0x140021d47  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140021d4e  mov     r9, [r9+40h]
0x140021d52  mov     [rsp+0C0h+var_88], rax
0x140021d57  mov     [rsp+0C0h+var_90], 1Eh
0x140021d5e  mov     [rsp+0C0h+var_98], 9
0x140021d66  mov     byte ptr [rsp+0C0h+ReturnedContext], 2
0x140021d6b  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140021d70  jmp     loc_140021F65
0x140021d75  mov     rcx, [rbp+47h+Context]; void *
0x140021d79  xor     edx, edx; Val
0x140021d7b  mov     r8d, 268h; Size
0x140021d81  call    memset
0x140021d86  mov     rax, [rbp+47h+Context]
0x140021d8a  mov     r8b, 1; State
0x140021d8d  mov     edx, 1; Type
0x140021d92  mov     [rax+8], rax
0x140021d96  mov     [rax], rax
0x140021d99  mov     rcx, [rbp+47h+Context]
0x140021d9d  add     rcx, 10h; Event
0x140021da1  call    cs:__imp_KeInitializeEvent
0x140021da8  nop     dword ptr [rax+rax+00h]
0x140021dad  mov     rax, [rbp+47h+Context]
0x140021db1  mov     rcx, r14; Context
0x140021db4  mov     [rax+30h], r14
0x140021db8  call    cs:__imp_FltReferenceContext
0x140021dbf  nop     dword ptr [rax+rax+00h]
0x140021dc4  cmp     [rbp+47h+arg_20], 0
0x140021dc8  jz      short loc_140021DD2
0x140021dca  mov     rax, [rbp+47h+Context]
0x140021dce  or      dword ptr [rax+28h], 1
0x140021dd2  cmp     dword ptr [rdi], 1
0x140021dd5  jnz     short loc_140021DDF
0x140021dd7  mov     rax, [rbp+47h+Context]
0x140021ddb  or      dword ptr [rax+28h], 18h
0x140021ddf  lea     rcx, [rbp+47h+Uuid]; Uuid
0x140021de3  call    cs:__imp_ExUuidCreate
0x140021dea  nop     dword ptr [rax+rax+00h]
0x140021def  mov     ebx, eax
0x140021df1  test    eax, eax
0x140021df3  jns     short loc_140021E6D
0x140021df5  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140021dfb  lea     rcx, WPP_RECORDER_INITIALIZED
0x140021e02  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140021e09  setnz   r8b
0x140021e0d  and     dl, 2
0x140021e10  jnz     short loc_140021E1B
0x140021e12  test    r8b, r8b
0x140021e15  jz      loc_140021F50
0x140021e1b  mov     [rsp+0C0h+var_70], eax
0x140021e1f  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140021e26  mov     [rsp+0C0h+var_78], 62Bh
0x140021e2e  mov     [rsp+0C0h+var_80], rax
0x140021e33  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140021e3a  mov     [rsp+0C0h+var_88], rax
0x140021e3f  mov     [rsp+0C0h+var_90], 1Fh
0x140021e46  mov     r9, cs:WPP_GLOBAL_Control
0x140021e4d  mov     ecx, 209h
0x140021e52  mov     [rsp+0C0h+var_98], 9
0x140021e5a  mov     byte ptr [rsp+0C0h+ReturnedContext], 2
0x140021e5f  mov     r9, [r9+40h]
0x140021e63  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140021e68  jmp     loc_140021F50
0x140021e6d  mov     rax, [rbp+47h+Context]
0x140021e71  movups  xmm0, xmmword ptr [rbp+47h+Uuid.Data1]
0x140021e75  movdqu  xmmword ptr [rax+38h], xmm0
0x140021e7a  mov     rbx, [rbp+47h+Context]
0x140021e7e  call    cs:__imp_IoGetCurrentProcess
0x140021e85  nop     dword ptr [rax+rax+00h]
0x140021e8a  mov     rcx, rax; Process
0x140021e8d  lea     rdx, [rbx+48h]
0x140021e91  call    PrjfInitProcessInfo
0x140021e96  mov     ebx, eax
0x140021e98  test    eax, eax
0x140021e9a  jns     short loc_140021EF2
0x140021e9c  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140021ea2  lea     rcx, WPP_RECORDER_INITIALIZED
0x140021ea9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140021eb0  setnz   r8b
0x140021eb4  and     dl, 2
0x140021eb7  jnz     short loc_140021EC2
0x140021eb9  test    r8b, r8b
0x140021ebc  jz      loc_140021F50
0x140021ec2  mov     [rsp+0C0h+var_70], eax
0x140021ec6  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140021ecd  mov     [rsp+0C0h+var_78], 63Bh
0x140021ed5  mov     [rsp+0C0h+var_80], rax
0x140021eda  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140021ee1  mov     [rsp+0C0h+var_88], rax
0x140021ee6  mov     [rsp+0C0h+var_90], 20h ; ' '
0x140021eed  jmp     loc_140021E46
0x140021ef2  mov     r9, [rbp+47h+Context]; NewContext
0x140021ef6  lea     rax, [rbp+47h+OldContext]
0x140021efa  mov     r8d, 1; Operation
0x140021f00  mov     [rsp+0C0h+ReturnedContext], rax; OldContext
0x140021f05  mov     rdx, r12; FileObject
0x140021f08  mov     rcx, r15; Instance
0x140021f0b  call    cs:__imp_FltSetStreamHandleContext
0x140021f12  nop     dword ptr [rax+rax+00h]
0x140021f17  mov     ebx, eax
0x140021f19  test    eax, eax
0x140021f1b  jns     short loc_140021F41
0x140021f1d  mov     rcx, [rbp+47h+Context]; Context
0x140021f21  call    cs:__imp_FltReleaseContext
0x140021f28  nop     dword ptr [rax+rax+00h]
0x140021f2d  cmp     ebx, 0C01C0002h
0x140021f33  jnz     short loc_140021F65
0x140021f35  mov     rax, [rbp+47h+OldContext]
0x140021f39  xor     ebx, ebx
0x140021f3b  jmp     short loc_140021F45
0x140021f3d  test    eax, eax
0x140021f3f  js      short loc_140021F50
0x140021f41  mov     rax, [rbp+47h+Context]
0x140021f45  mov     [rsi], rax
0x140021f48  mov     [rbp+47h+Context], 0
0x140021f50  mov     rcx, [rbp+47h+Context]; Context
0x140021f54  test    rcx, rcx
0x140021f57  jz      short loc_140021F65
0x140021f59  call    cs:__imp_FltReleaseContext
0x140021f60  nop     dword ptr [rax+rax+00h]
0x140021f65  mov     eax, ebx
0x140021f67  mov     rcx, [rbp+47h+var_40]
0x140021f6b  xor     rcx, rsp; StackCookie
0x140021f6e  call    __security_check_cookie
0x140021f73  add     rsp, 90h
0x140021f7a  pop     r15
0x140021f7c  pop     r14
0x140021f7e  pop     r12
0x140021f80  pop     rdi
0x140021f81  pop     rsi
0x140021f82  pop     rbx
0x140021f83  pop     rbp
0x140021f84  retn
```
