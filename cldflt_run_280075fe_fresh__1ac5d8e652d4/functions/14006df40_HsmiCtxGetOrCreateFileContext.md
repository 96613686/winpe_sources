# HsmiCtxGetOrCreateFileContext

- ea: `0x14006df40`
- end: `0x14006e18d`
- name: `HsmiCtxGetOrCreateFileContext`
- size: `589`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context, PFILE_OBJECT FileObject)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14005191c`
- `0x140059648`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000ac28`
- `0x14006df40`
- `0x14006e194`

## import_xrefs

- `FLTMGR!FltGetFileContext` at `0x14006df76`
- `FLTMGR!FltGetFileContext` at `0x14006df76`
- `FLTMGR!FltSetFileContext` at `0x14006dfdc`
- `FLTMGR!FltSetFileContext` at `0x14006dfdc`
- `FLTMGR!FltReleaseContext` at `0x14006e07f`
- `FLTMGR!FltReleaseContext` at `0x14006e17c`
- `FLTMGR!FltReleaseContext` at `0x14006e07f`
- `FLTMGR!FltReleaseContext` at `0x14006e17c`

## pseudocode

```c
__int64 __fastcall HsmiCtxGetOrCreateFileContext(
        PFLT_INSTANCE *Context,
        PFILE_OBJECT FileObject,
        __int64 a3,
        _QWORD *a4)
{
  NTSTATUS FileContext; // ebx
  PFLT_CONTEXT v8; // rax
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  PFLT_CONTEXT Contexta; // [rsp+70h] [rbp+30h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+88h] [rbp+48h] BYREF

  Contexta = 0;
  *a4 = 0;
  FileContext = FltGetFileContext(Context[4], FileObject, &Contexta);
  HsmDbgBreakOnStatus((unsigned int)FileContext);
  if ( FileContext >= 0 )
    goto LABEL_6;
  if ( FileContext != -1073741275 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_8;
    }
    v11 = 20;
LABEL_24:
    WPP_SF_qqd(
      v10->AttachedDevice,
      v11,
      WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
      Context,
      FileObject,
      FileContext);
    goto LABEL_8;
  }
  OldContext = 0;
  FileContext = HsmiCtxCreateFileContext(Context, FileObject);
  HsmDbgBreakOnStatus((unsigned int)FileContext);
  if ( FileContext < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_8;
    }
    v11 = 17;
    goto LABEL_24;
  }
  FileContext = FltSetFileContext(Context[4], FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, Contexta, &OldContext);
  HsmDbgBreakOnStatus((unsigned int)FileContext);
  if ( FileContext == -1071906814 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqiqd(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
        Context,
        FileObject,
        Contexta,
        OldContext,
        -1071906814);
    }
    FltReleaseContext(Contexta);
    v8 = OldContext;
    FileContext = 0;
    goto LABEL_7;
  }
  if ( FileContext >= 0 )
  {
LABEL_6:
    v8 = Contexta;
LABEL_7:
    *a4 = v8;
    Contexta = 0;
    goto LABEL_8;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
      Context,
      FileObject,
      Contexta,
      FileContext);
  }
  FileContext = -1073741757;
  HsmDbgBreakOnStatus(3221225539LL);
LABEL_8:
  if ( Contexta )
    FltReleaseContext(Contexta);
  return (unsigned int)FileContext;
}

```

## disassembly

```asm
0x14006df40  mov     [rsp-28h+arg_8], rbx
0x14006df45  push    rbp
0x14006df46  push    rsi
0x14006df47  push    rdi
0x14006df48  push    r14
0x14006df4a  push    r15
0x14006df4c  mov     rbp, rsp
0x14006df4f  sub     rsp, 40h
0x14006df53  mov     r15, r8
0x14006df56  mov     [rbp+Context], 0
0x14006df5e  mov     rsi, rcx
0x14006df61  mov     qword ptr [r9], 0
0x14006df68  mov     rcx, [rcx+20h]; Instance
0x14006df6c  lea     r8, [rbp+Context]; Context
0x14006df70  mov     r14, r9
0x14006df73  mov     rdi, rdx
0x14006df76  call    cs:__imp_FltGetFileContext
0x14006df7d  nop     dword ptr [rax+rax+00h]
0x14006df82  mov     ecx, eax
0x14006df84  mov     ebx, eax
0x14006df86  call    HsmDbgBreakOnStatus
0x14006df8b  test    ebx, ebx
0x14006df8d  jns     short loc_14006E004
0x14006df8f  cmp     ebx, 0C0000225h
0x14006df95  jnz     loc_14006E096
0x14006df9b  lea     r9, [rbp+Context]
0x14006df9f  mov     [rbp+arg_18], 0
0x14006dfa7  mov     r8, r15
0x14006dfaa  mov     rdx, rdi; FileObject
0x14006dfad  mov     rcx, rsi; Context
0x14006dfb0  call    HsmiCtxCreateFileContext
0x14006dfb5  mov     ecx, eax
0x14006dfb7  mov     ebx, eax
0x14006dfb9  call    HsmDbgBreakOnStatus
0x14006dfbe  test    ebx, ebx
0x14006dfc0  js      short loc_14006E034
0x14006dfc2  mov     r9, [rbp+Context]; NewContext
0x14006dfc6  lea     rax, [rbp+arg_18]
0x14006dfca  mov     rcx, [rsi+20h]; Instance
0x14006dfce  mov     r8d, 1; Operation
0x14006dfd4  mov     rdx, rdi; FileObject
0x14006dfd7  mov     [rsp+40h+OldContext], rax; OldContext
0x14006dfdc  call    cs:__imp_FltSetFileContext
0x14006dfe3  nop     dword ptr [rax+rax+00h]
0x14006dfe8  mov     ecx, eax
0x14006dfea  mov     ebx, eax
0x14006dfec  call    HsmDbgBreakOnStatus
0x14006dff1  mov     r8d, 0C01C0002h
0x14006dff7  cmp     ebx, r8d
0x14006dffa  jz      short loc_14006E05B
0x14006dffc  test    ebx, ebx
0x14006dffe  js      loc_14006E121
0x14006e004  mov     rax, [rbp+Context]
0x14006e008  mov     [r14], rax
0x14006e00b  mov     [rbp+Context], 0
0x14006e013  mov     rcx, [rbp+Context]; Context
0x14006e017  test    rcx, rcx
0x14006e01a  jnz     loc_14006E17C
0x14006e020  mov     eax, ebx
0x14006e022  mov     rbx, [rsp+40h+arg_8]
0x14006e027  add     rsp, 40h
0x14006e02b  pop     r15
0x14006e02d  pop     r14
0x14006e02f  pop     rdi
0x14006e030  pop     rsi
0x14006e031  pop     rbp
0x14006e032  retn
0x14006e034  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e03b  lea     rax, WPP_GLOBAL_Control
0x14006e042  cmp     rcx, rax
0x14006e045  jz      short loc_14006E013
0x14006e047  mov     eax, [rcx+2Ch]
0x14006e04a  test    al, 1
0x14006e04c  jz      short loc_14006E013
0x14006e04e  cmp     byte ptr [rcx+29h], 2
0x14006e052  jb      short loc_14006E013
0x14006e054  mov     edx, 11h
0x14006e059  jmp     short loc_14006E0C7
0x14006e05b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e062  lea     rax, WPP_GLOBAL_Control
0x14006e069  cmp     rcx, rax
0x14006e06c  jz      short loc_14006E07B
0x14006e06e  mov     eax, [rcx+2Ch]
0x14006e071  test    al, 1
0x14006e073  jz      short loc_14006E07B
0x14006e075  cmp     byte ptr [rcx+29h], 4
0x14006e079  jnb     short loc_14006E0E8
0x14006e07b  mov     rcx, [rbp+Context]; Context
0x14006e07f  call    cs:__imp_FltReleaseContext
0x14006e086  nop     dword ptr [rax+rax+00h]
0x14006e08b  mov     rax, [rbp+arg_18]
0x14006e08f  xor     ebx, ebx
0x14006e091  jmp     loc_14006E008
0x14006e096  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e09d  lea     rax, WPP_GLOBAL_Control
0x14006e0a4  cmp     rcx, rax
0x14006e0a7  jz      loc_14006E013
0x14006e0ad  mov     eax, [rcx+2Ch]
0x14006e0b0  test    al, 1
0x14006e0b2  jz      loc_14006E013
0x14006e0b8  cmp     byte ptr [rcx+29h], 3
0x14006e0bc  jb      loc_14006E013
0x14006e0c2  mov     edx, 14h
0x14006e0c7  mov     rcx, [rcx+18h]
0x14006e0cb  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006e0d2  mov     dword ptr [rsp+40h+var_18], ebx
0x14006e0d6  mov     r9, rsi
0x14006e0d9  mov     [rsp+40h+OldContext], rdi
0x14006e0de  call    WPP_SF_qqd
0x14006e0e3  jmp     loc_14006E013
0x14006e0e8  mov     rax, [rbp+arg_18]
0x14006e0ec  mov     edx, 12h
0x14006e0f1  mov     rcx, [rcx+18h]
0x14006e0f5  mov     r9, rsi
0x14006e0f8  mov     [rsp+40h+var_8], r8d
0x14006e0fd  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006e104  mov     [rsp+40h+var_10], rax
0x14006e109  mov     rax, [rbp+Context]
0x14006e10d  mov     [rsp+40h+var_18], rax
0x14006e112  mov     [rsp+40h+OldContext], rdi
0x14006e117  call    WPP_SF_qqiqd
0x14006e11c  jmp     loc_14006E07B
0x14006e121  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e128  lea     rax, WPP_GLOBAL_Control
0x14006e12f  cmp     rcx, rax
0x14006e132  jz      short loc_14006E16B
0x14006e134  mov     eax, [rcx+2Ch]
0x14006e137  test    al, 1
0x14006e139  jz      short loc_14006E16B
0x14006e13b  cmp     byte ptr [rcx+29h], 2
0x14006e13f  jb      short loc_14006E16B
0x14006e141  mov     rax, [rbp+Context]
0x14006e145  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006e14c  mov     rcx, [rcx+18h]
0x14006e150  mov     edx, 13h
0x14006e155  mov     dword ptr [rsp+40h+var_10], ebx
0x14006e159  mov     r9, rsi
0x14006e15c  mov     [rsp+40h+var_18], rax
0x14006e161  mov     [rsp+40h+OldContext], rdi
0x14006e166  call    WPP_SF_qqqd
0x14006e16b  mov     ebx, 0C0000043h
0x14006e170  mov     ecx, ebx
0x14006e172  call    HsmDbgBreakOnStatus
0x14006e177  jmp     loc_14006E013
0x14006e17c  call    cs:__imp_FltReleaseContext
0x14006e183  nop     dword ptr [rax+rax+00h]
0x14006e188  jmp     loc_14006E020
```
