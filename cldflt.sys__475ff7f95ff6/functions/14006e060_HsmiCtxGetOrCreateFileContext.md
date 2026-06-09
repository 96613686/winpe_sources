# HsmiCtxGetOrCreateFileContext

- ea: `0x14006e060`
- end: `0x14006e2ad`
- name: `HsmiCtxGetOrCreateFileContext`
- size: `589`
- prototype: `__int64 __fastcall(PFLT_INSTANCE *Context, PFILE_OBJECT FileObject, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140051a3c`
- `0x140059768`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000ac28`
- `0x14006e060`
- `0x14006e2b4`

## import_xrefs

- `FLTMGR!FltGetFileContext` at `0x14006e096`
- `FLTMGR!FltGetFileContext` at `0x14006e096`
- `FLTMGR!FltSetFileContext` at `0x14006e0fc`
- `FLTMGR!FltSetFileContext` at `0x14006e0fc`
- `FLTMGR!FltReleaseContext` at `0x14006e19f`
- `FLTMGR!FltReleaseContext` at `0x14006e29c`
- `FLTMGR!FltReleaseContext` at `0x14006e19f`
- `FLTMGR!FltReleaseContext` at `0x14006e29c`

## pseudocode

```c
__int64 __fastcall HsmiCtxGetOrCreateFileContext(
        PFLT_INSTANCE *Context,
        PFILE_OBJECT FileObject,
        __int64 a3,
        _QWORD *a4)
{
  int FileContext; // ebx
  PFLT_CONTEXT v9; // rax
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  PFLT_CONTEXT Contexta; // [rsp+70h] [rbp+30h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+88h] [rbp+48h] BYREF

  Contexta = 0;
  *a4 = 0;
  FileContext = FltGetFileContext(Context[4], FileObject, &Contexta);
  HsmDbgBreakOnStatus(FileContext);
  if ( FileContext >= 0 )
    goto LABEL_6;
  if ( FileContext != -1073741275 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_8;
    }
    v12 = 20;
LABEL_24:
    WPP_SF_qqd(
      v11->AttachedDevice,
      v12,
      WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
      Context,
      FileObject,
      FileContext);
    goto LABEL_8;
  }
  OldContext = 0;
  FileContext = HsmiCtxCreateFileContext(Context, FileObject, a3, &Contexta);
  HsmDbgBreakOnStatus(FileContext);
  if ( FileContext < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_8;
    }
    v12 = 17;
    goto LABEL_24;
  }
  FileContext = FltSetFileContext(Context[4], FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, Contexta, &OldContext);
  HsmDbgBreakOnStatus(FileContext);
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
    v9 = OldContext;
    FileContext = 0;
    goto LABEL_7;
  }
  if ( FileContext >= 0 )
  {
LABEL_6:
    v9 = Contexta;
LABEL_7:
    *a4 = v9;
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
  HsmDbgBreakOnStatus(-1073741757);
LABEL_8:
  if ( Contexta )
    FltReleaseContext(Contexta);
  return (unsigned int)FileContext;
}

```

## disassembly

```asm
0x14006e060  mov     [rsp-28h+arg_8], rbx
0x14006e065  push    rbp
0x14006e066  push    rsi
0x14006e067  push    rdi
0x14006e068  push    r14
0x14006e06a  push    r15
0x14006e06c  mov     rbp, rsp
0x14006e06f  sub     rsp, 40h
0x14006e073  mov     r15, r8
0x14006e076  mov     [rbp+Context], 0
0x14006e07e  mov     rsi, rcx
0x14006e081  mov     qword ptr [r9], 0
0x14006e088  mov     rcx, [rcx+20h]; Instance
0x14006e08c  lea     r8, [rbp+Context]; Context
0x14006e090  mov     r14, r9
0x14006e093  mov     rdi, rdx
0x14006e096  call    cs:__imp_FltGetFileContext
0x14006e09d  nop     dword ptr [rax+rax+00h]
0x14006e0a2  mov     ecx, eax
0x14006e0a4  mov     ebx, eax
0x14006e0a6  call    HsmDbgBreakOnStatus
0x14006e0ab  test    ebx, ebx
0x14006e0ad  jns     short loc_14006E124
0x14006e0af  cmp     ebx, 0C0000225h
0x14006e0b5  jnz     loc_14006E1B6
0x14006e0bb  lea     r9, [rbp+Context]
0x14006e0bf  mov     [rbp+arg_18], 0
0x14006e0c7  mov     r8, r15
0x14006e0ca  mov     rdx, rdi; FileObject
0x14006e0cd  mov     rcx, rsi; Context
0x14006e0d0  call    HsmiCtxCreateFileContext
0x14006e0d5  mov     ecx, eax
0x14006e0d7  mov     ebx, eax
0x14006e0d9  call    HsmDbgBreakOnStatus
0x14006e0de  test    ebx, ebx
0x14006e0e0  js      short loc_14006E154
0x14006e0e2  mov     r9, [rbp+Context]; NewContext
0x14006e0e6  lea     rax, [rbp+arg_18]
0x14006e0ea  mov     rcx, [rsi+20h]; Instance
0x14006e0ee  mov     r8d, 1; Operation
0x14006e0f4  mov     rdx, rdi; FileObject
0x14006e0f7  mov     [rsp+40h+OldContext], rax; OldContext
0x14006e0fc  call    cs:__imp_FltSetFileContext
0x14006e103  nop     dword ptr [rax+rax+00h]
0x14006e108  mov     ecx, eax
0x14006e10a  mov     ebx, eax
0x14006e10c  call    HsmDbgBreakOnStatus
0x14006e111  mov     r8d, 0C01C0002h
0x14006e117  cmp     ebx, r8d
0x14006e11a  jz      short loc_14006E17B
0x14006e11c  test    ebx, ebx
0x14006e11e  js      loc_14006E241
0x14006e124  mov     rax, [rbp+Context]
0x14006e128  mov     [r14], rax
0x14006e12b  mov     [rbp+Context], 0
0x14006e133  mov     rcx, [rbp+Context]; Context
0x14006e137  test    rcx, rcx
0x14006e13a  jnz     loc_14006E29C
0x14006e140  mov     eax, ebx
0x14006e142  mov     rbx, [rsp+40h+arg_8]
0x14006e147  add     rsp, 40h
0x14006e14b  pop     r15
0x14006e14d  pop     r14
0x14006e14f  pop     rdi
0x14006e150  pop     rsi
0x14006e151  pop     rbp
0x14006e152  retn
0x14006e154  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e15b  lea     rax, WPP_GLOBAL_Control
0x14006e162  cmp     rcx, rax
0x14006e165  jz      short loc_14006E133
0x14006e167  mov     eax, [rcx+2Ch]
0x14006e16a  test    al, 1
0x14006e16c  jz      short loc_14006E133
0x14006e16e  cmp     byte ptr [rcx+29h], 2
0x14006e172  jb      short loc_14006E133
0x14006e174  mov     edx, 11h
0x14006e179  jmp     short loc_14006E1E7
0x14006e17b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e182  lea     rax, WPP_GLOBAL_Control
0x14006e189  cmp     rcx, rax
0x14006e18c  jz      short loc_14006E19B
0x14006e18e  mov     eax, [rcx+2Ch]
0x14006e191  test    al, 1
0x14006e193  jz      short loc_14006E19B
0x14006e195  cmp     byte ptr [rcx+29h], 4
0x14006e199  jnb     short loc_14006E208
0x14006e19b  mov     rcx, [rbp+Context]; Context
0x14006e19f  call    cs:__imp_FltReleaseContext
0x14006e1a6  nop     dword ptr [rax+rax+00h]
0x14006e1ab  mov     rax, [rbp+arg_18]
0x14006e1af  xor     ebx, ebx
0x14006e1b1  jmp     loc_14006E128
0x14006e1b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e1bd  lea     rax, WPP_GLOBAL_Control
0x14006e1c4  cmp     rcx, rax
0x14006e1c7  jz      loc_14006E133
0x14006e1cd  mov     eax, [rcx+2Ch]
0x14006e1d0  test    al, 1
0x14006e1d2  jz      loc_14006E133
0x14006e1d8  cmp     byte ptr [rcx+29h], 3
0x14006e1dc  jb      loc_14006E133
0x14006e1e2  mov     edx, 14h
0x14006e1e7  mov     rcx, [rcx+18h]
0x14006e1eb  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006e1f2  mov     dword ptr [rsp+40h+var_18], ebx
0x14006e1f6  mov     r9, rsi
0x14006e1f9  mov     [rsp+40h+OldContext], rdi
0x14006e1fe  call    WPP_SF_qqd
0x14006e203  jmp     loc_14006E133
0x14006e208  mov     rax, [rbp+arg_18]
0x14006e20c  mov     edx, 12h
0x14006e211  mov     rcx, [rcx+18h]
0x14006e215  mov     r9, rsi
0x14006e218  mov     [rsp+40h+var_8], r8d
0x14006e21d  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006e224  mov     [rsp+40h+var_10], rax
0x14006e229  mov     rax, [rbp+Context]
0x14006e22d  mov     [rsp+40h+var_18], rax
0x14006e232  mov     [rsp+40h+OldContext], rdi
0x14006e237  call    WPP_SF_qqiqd
0x14006e23c  jmp     loc_14006E19B
0x14006e241  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e248  lea     rax, WPP_GLOBAL_Control
0x14006e24f  cmp     rcx, rax
0x14006e252  jz      short loc_14006E28B
0x14006e254  mov     eax, [rcx+2Ch]
0x14006e257  test    al, 1
0x14006e259  jz      short loc_14006E28B
0x14006e25b  cmp     byte ptr [rcx+29h], 2
0x14006e25f  jb      short loc_14006E28B
0x14006e261  mov     rax, [rbp+Context]
0x14006e265  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006e26c  mov     rcx, [rcx+18h]
0x14006e270  mov     edx, 13h
0x14006e275  mov     dword ptr [rsp+40h+var_10], ebx
0x14006e279  mov     r9, rsi
0x14006e27c  mov     [rsp+40h+var_18], rax
0x14006e281  mov     [rsp+40h+OldContext], rdi
0x14006e286  call    WPP_SF_qqqd
0x14006e28b  mov     ebx, 0C0000043h
0x14006e290  mov     ecx, ebx
0x14006e292  call    HsmDbgBreakOnStatus
0x14006e297  jmp     loc_14006E133
0x14006e29c  call    cs:__imp_FltReleaseContext
0x14006e2a3  nop     dword ptr [rax+rax+00h]
0x14006e2a8  jmp     loc_14006E140
```
