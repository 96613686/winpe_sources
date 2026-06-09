# PrjfSetPlaceHolderFlagsSynchronized

- ea: `0x14003df88`
- end: `0x14003e0cf`
- name: `PrjfSetPlaceHolderFlagsSynchronized`
- size: `327`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400081f0`
- `0x140022320`
- `0x140023d68`
- `0x14002c98c`
- `0x140036f10`

## callees

- `0x140002b50`
- `0x14000b1d0`
- `0x140029214`
- `0x14003dd88`
- `0x14003df88`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14003e029`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14003e029`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003e055`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003e055`
- `FLTMGR!FltReleaseContext` at `0x14003e09b`
- `FLTMGR!FltReleaseContext` at `0x14003e0af`
- `FLTMGR!FltReleaseContext` at `0x14003e09b`
- `FLTMGR!FltReleaseContext` at `0x14003e0af`

## pseudocode

```c
__int64 __fastcall PrjfSetPlaceHolderFlagsSynchronized(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        unsigned int a4)
{
  unsigned int v8; // edi
  char ContextFileObject; // al
  _DWORD *v10; // rsi
  struct _EX_RUNDOWN_REF *v11; // rbx
  unsigned int v12; // eax
  char v14; // [rsp+20h] [rbp-78h]
  char v15; // [rsp+20h] [rbp-78h]
  PFLT_CONTEXT v16; // [rsp+40h] [rbp-58h] BYREF
  PFLT_CONTEXT Context[10]; // [rsp+48h] [rbp-50h] BYREF

  v8 = 0;
  Context[0] = 0;
  v16 = 0;
  ContextFileObject = PrjfGetContextFileObject(Instance, FileObject, (__int64 *)Context, &v16);
  v10 = v16;
  v11 = (struct _EX_RUNDOWN_REF *)Context[0];
  if ( ContextFileObject )
  {
    if ( !Context[0] )
      goto LABEL_16;
    if ( *((_DWORD *)Context[0] + 16) != 3 )
    {
      if ( !*((_QWORD *)Context[0] + 9) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      if ( (a4 & *(_DWORD *)(v11[9].Count + 12)) == 0 )
      {
        if ( *v10 == 1 )
        {
          v14 = 1;
          v12 = PrjfSetPlaceHolderFlags(Instance, FileObject, v11, a4, v14);
        }
        else
        {
          if ( LODWORD(v11[8].Count) == 3 )
            goto LABEL_14;
          if ( ExAcquireRundownProtection(v11 + 10) )
          {
            v15 = 1;
            v8 = PrjfSetPlaceHolderFlags(Instance, FileObject, v11, a4, v15);
            ExReleaseRundownProtection(v11 + 10);
            goto LABEL_14;
          }
          v12 = PrjfExpandAndWait(CallbackData, Instance, (__int64)FileObject, (__int64)v11, 3, 1, 8u, 0);
        }
        v8 = v12;
      }
    }
  }
LABEL_14:
  if ( v11 )
    FltReleaseContext(v11);
LABEL_16:
  if ( v10 )
    FltReleaseContext(v10);
  return v8;
}

```

## disassembly

```asm
0x14003df88  mov     rax, rsp
0x14003df8b  push    rbx
0x14003df8c  push    rbp
0x14003df8d  push    rsi
0x14003df8e  push    rdi
0x14003df8f  push    r12
0x14003df91  push    r13
0x14003df93  push    r14
0x14003df95  push    r15
0x14003df97  sub     rsp, 58h
0x14003df9b  mov     r14, r8
0x14003df9e  mov     r15, rdx
0x14003dfa1  mov     r12d, r9d
0x14003dfa4  lea     r8, [rax-50h]
0x14003dfa8  mov     r13, rcx
0x14003dfab  lea     r9, [rax-58h]
0x14003dfaf  xor     edi, edi
0x14003dfb1  mov     rdx, r14; FileObject
0x14003dfb4  mov     rcx, r15; Instance
0x14003dfb7  mov     [rax-50h], rdi
0x14003dfbb  mov     [rax-58h], rdi
0x14003dfbf  call    PrjfGetContextFileObject
0x14003dfc4  mov     rsi, [rsp+98h+var_58]
0x14003dfc9  mov     rbx, [rsp+98h+Context]
0x14003dfce  test    al, al
0x14003dfd0  jz      loc_14003E093
0x14003dfd6  test    rbx, rbx
0x14003dfd9  jz      loc_14003E0A7
0x14003dfdf  cmp     dword ptr [rbx+40h], 3
0x14003dfe3  jz      loc_14003E093
0x14003dfe9  cmp     [rbx+48h], rdi
0x14003dfed  jnz     short loc_14003DFF4
0x14003dfef  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003dff4  mov     rax, [rbx+48h]
0x14003dff8  test    [rax+0Ch], r12d
0x14003dffc  jnz     loc_14003E093
0x14003e002  cmp     dword ptr [rsi], 1
0x14003e005  jnz     short loc_14003E01F
0x14003e007  mov     r9d, r12d
0x14003e00a  mov     [rsp+98h+var_78], 1
0x14003e00f  mov     r8, rbx
0x14003e012  mov     rdx, r14
0x14003e015  mov     rcx, r15
0x14003e018  call    PrjfSetPlaceHolderFlags
0x14003e01d  jmp     short loc_14003E091
0x14003e01f  cmp     dword ptr [rbx+40h], 3
0x14003e023  jz      short loc_14003E093
0x14003e025  lea     rcx, [rbx+50h]; RunRef
0x14003e029  call    cs:__imp_ExAcquireRundownProtection
0x14003e030  nop     dword ptr [rax+rax+00h]
0x14003e035  test    al, al
0x14003e037  jz      short loc_14003E063
0x14003e039  mov     r9d, r12d
0x14003e03c  mov     [rsp+98h+var_78], 1
0x14003e041  mov     r8, rbx
0x14003e044  mov     rdx, r14
0x14003e047  mov     rcx, r15
0x14003e04a  call    PrjfSetPlaceHolderFlags
0x14003e04f  lea     rcx, [rbx+50h]; RunRef
0x14003e053  mov     edi, eax
0x14003e055  call    cs:__imp_ExReleaseRundownProtection
0x14003e05c  nop     dword ptr [rax+rax+00h]
0x14003e061  jmp     short loc_14003E093
0x14003e063  mov     [rsp+98h+var_60], dil; char
0x14003e068  mov     r9, rbx
0x14003e06b  mov     [rsp+98h+var_68], 8; int
0x14003e073  mov     r8, r14
0x14003e076  mov     [rsp+98h+var_70], 1; int
0x14003e07e  mov     rdx, r15
0x14003e081  mov     rcx, r13; CallbackData
0x14003e084  mov     dword ptr [rsp+98h+var_78], 3; int
0x14003e08c  call    PrjfExpandAndWait
0x14003e091  mov     edi, eax
0x14003e093  test    rbx, rbx
0x14003e096  jz      short loc_14003E0A7
0x14003e098  mov     rcx, rbx; Context
0x14003e09b  call    cs:__imp_FltReleaseContext
0x14003e0a2  nop     dword ptr [rax+rax+00h]
0x14003e0a7  test    rsi, rsi
0x14003e0aa  jz      short loc_14003E0BB
0x14003e0ac  mov     rcx, rsi; Context
0x14003e0af  call    cs:__imp_FltReleaseContext
0x14003e0b6  nop     dword ptr [rax+rax+00h]
0x14003e0bb  mov     eax, edi
0x14003e0bd  add     rsp, 58h
0x14003e0c1  pop     r15
0x14003e0c3  pop     r14
0x14003e0c5  pop     r13
0x14003e0c7  pop     r12
0x14003e0c9  pop     rdi
0x14003e0ca  pop     rsi
0x14003e0cb  pop     rbp
0x14003e0cc  pop     rbx
0x14003e0cd  retn
```
