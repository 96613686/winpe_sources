# FIStreamGet

- ea: `0x1400138d4`
- end: `0x140013bb1`
- name: `FIStreamGet`
- size: `733`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x140002a80`
- `0x140003140`
- `0x140013560`
- `0x140016bc0`
- `0x140017700`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x1400138d4`
- `0x140013bc0`
- `0x140014730`
- `0x140016494`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140013a93`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140013a93`
- `FLTMGR!FltSetStreamContext` at `0x140013a40`
- `FLTMGR!FltSetStreamContext` at `0x140013a40`
- `FLTMGR!FltGetStreamContext` at `0x140013923`
- `FLTMGR!FltGetStreamContext` at `0x140013923`
- `FLTMGR!FltReleaseContext` at `0x140013a7a`
- `FLTMGR!FltReleaseContext` at `0x140013af3`
- `FLTMGR!FltReleaseContext` at `0x140013b0b`
- `FLTMGR!FltReleaseContext` at `0x140013ba0`
- `FLTMGR!FltReleaseContext` at `0x140013a7a`
- `FLTMGR!FltReleaseContext` at `0x140013af3`
- `FLTMGR!FltReleaseContext` at `0x140013b0b`
- `FLTMGR!FltReleaseContext` at `0x140013ba0`

## pseudocode

```c
__int64 __fastcall FIStreamGet(__int64 a1, __int64 a2, PFLT_CONTEXT *a3, int *a4)
{
  int v8; // ebx
  struct _FILE_OBJECT *v9; // rdx
  struct _FLT_INSTANCE *v10; // rcx
  NTSTATUS StreamContext; // edi
  int v13; // eax
  _QWORD *v14; // rsi
  __int64 v15; // rdx
  __int64 v16; // rdi
  _QWORD *v17; // rdx
  _QWORD *v18; // rsi
  _QWORD *v19; // rax
  NTSTATUS v20; // eax
  PFLT_CONTEXT v21; // rax
  _QWORD *v22; // rcx
  PFLT_CONTEXT *v23; // rax
  PFLT_CONTEXT *v24; // rdx
  int v25; // eax
  __int64 v26; // rax
  PFLT_CONTEXT v27; // [rsp+30h] [rbp-10h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+38h] [rbp-8h] BYREF
  int v29; // [rsp+88h] [rbp+48h] BYREF
  PFLT_CONTEXT Context; // [rsp+98h] [rbp+58h] BYREF

  OldContext = 0;
  if ( a4 )
    v8 = *a4;
  else
    v8 = 0;
  v9 = *(struct _FILE_OBJECT **)(a2 + 16);
  v10 = *(struct _FLT_INSTANCE **)(a2 + 8);
  v27 = 0;
  Context = 0;
  StreamContext = FltGetStreamContext(v10, v9, &Context);
  if ( StreamContext >= 0 )
  {
    v8 |= 1u;
    *a3 = Context;
    goto LABEL_5;
  }
  if ( StreamContext == -1073741275 )
  {
    if ( (v8 & 0x10000) != 0 )
    {
      StreamContext = -1073741275;
    }
    else
    {
      v29 = 0;
      v13 = FIVolumeGet(a2, &v27, &v29);
      v14 = v27;
      StreamContext = v13;
      if ( v13 < 0 )
      {
        v25 = v8 | 2;
        if ( (v29 & 2) == 0 )
          v25 = v8;
        v8 = v25;
        goto LABEL_21;
      }
      if ( (v8 & 0x40000) == 0 && *((WCHAR **)v27 + 13) == FIUnknown )
        FIVolumeQueueQuery(a2, (__int64)v27);
      StreamContext = FIStreamCreate(&Context);
      if ( StreamContext < 0 )
      {
LABEL_21:
        if ( v14 )
          FltReleaseContext(v14);
        goto LABEL_23;
      }
      v15 = *(_QWORD *)(a2 + 16);
      *((_QWORD *)Context + 4) = *(_QWORD *)(v15 + 24);
      if ( !*(_QWORD *)(v15 + 32)
        || a1 && (v26 = *(_QWORD *)(a1 + 16), !*(_BYTE *)(v26 + 4)) && (*(_DWORD *)(v26 + 32) & 1) != 0 )
      {
        *((_DWORD *)Context + 14) |= 4u;
      }
      v16 = (__int64)(v14 + 3);
      *((_QWORD *)Context + 3) = v14;
      FILockExclusiveAcquire((__int64)(v14 + 3));
      v17 = (_QWORD *)v14[5];
      v18 = v14 + 4;
      if ( (_QWORD *)*v17 != v18 )
LABEL_17:
        __fastfail(3u);
      v19 = Context;
      *(_QWORD *)Context = v18;
      v19[1] = v17;
      *v17 = v19;
      v18[1] = v19;
      FILockExclusiveRelease(v16);
      v14 = 0;
      v20 = FltSetStreamContext(
              *(PFLT_INSTANCE *)(a2 + 8),
              *(PFILE_OBJECT *)(a2 + 16),
              FLT_SET_CONTEXT_KEEP_IF_EXISTS,
              Context,
              &OldContext);
      StreamContext = v20;
      if ( v20 >= 0 )
      {
        v21 = Context;
LABEL_20:
        *a3 = v21;
        StreamContext = 0;
        Context = 0;
        goto LABEL_21;
      }
      if ( v20 == -1071906814 )
      {
        ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)Context + 2);
        FILockExclusiveAcquire(*((_QWORD *)Context + 3) + 24LL);
        v22 = Context;
        v23 = *(PFLT_CONTEXT **)Context;
        if ( *(PFLT_CONTEXT *)Context != Context )
        {
          if ( v23[1] != Context )
            goto LABEL_17;
          v24 = (PFLT_CONTEXT *)*((_QWORD *)Context + 1);
          if ( *v24 != Context )
            goto LABEL_17;
          *v24 = v23;
          v23[1] = v24;
          v22 = Context;
        }
        FILockExclusiveRelease(v22[3] + 24LL);
        FltReleaseContext(*((PFLT_CONTEXT *)Context + 3));
        *((_QWORD *)Context + 3) = 0;
        FltReleaseContext(Context);
        v21 = OldContext;
        goto LABEL_20;
      }
    }
  }
  else
  {
    v8 |= 2u;
  }
LABEL_23:
  if ( Context )
    FltReleaseContext(Context);
LABEL_5:
  if ( a4 )
    *a4 = v8;
  return (unsigned int)StreamContext;
}

```

## disassembly

```asm
0x1400138d4  mov     [rsp-38h+arg_0], rbx
0x1400138d9  push    rbp
0x1400138da  push    rsi
0x1400138db  push    rdi
0x1400138dc  push    r12
0x1400138de  push    r13
0x1400138e0  push    r14
0x1400138e2  push    r15
0x1400138e4  mov     rbp, rsp
0x1400138e7  sub     rsp, 40h
0x1400138eb  mov     [rbp+var_8], 0
0x1400138f3  mov     r15, r9
0x1400138f6  mov     r12, r8
0x1400138f9  mov     r14, rdx
0x1400138fc  mov     r13, rcx
0x1400138ff  test    r9, r9
0x140013902  jz      short loc_140013963
0x140013904  mov     ebx, [r9]
0x140013907  mov     rdx, [rdx+10h]; FileObject
0x14001390b  lea     r8, [rbp+Context]; Context
0x14001390f  mov     rcx, [r14+8]; Instance
0x140013913  mov     [rbp+var_10], 0
0x14001391b  mov     [rbp+Context], 0
0x140013923  call    cs:__imp_FltGetStreamContext
0x14001392a  nop     dword ptr [rax+rax+00h]
0x14001392f  mov     edi, eax
0x140013931  test    eax, eax
0x140013933  js      short loc_140013967
0x140013935  mov     rcx, [rbp+Context]
0x140013939  or      ebx, 1
0x14001393c  mov     [r12], rcx
0x140013940  test    r15, r15
0x140013943  jz      short loc_140013948
0x140013945  mov     [r15], ebx
0x140013948  mov     rbx, [rsp+40h+arg_0]
0x140013950  mov     eax, edi
0x140013952  add     rsp, 40h
0x140013956  pop     r15
0x140013958  pop     r14
0x14001395a  pop     r13
0x14001395c  pop     r12
0x14001395e  pop     rdi
0x14001395f  pop     rsi
0x140013960  pop     rbp
0x140013961  retn
0x140013963  xor     ebx, ebx
0x140013965  jmp     short loc_140013907
0x140013967  mov     eax, 0C0000225h
0x14001396c  cmp     edi, eax
0x14001396e  jnz     loc_140013B20
0x140013974  bt      ebx, 10h
0x140013978  jb      loc_140013B28
0x14001397e  lea     r8, [rbp+arg_8]
0x140013982  mov     [rbp+arg_8], 0
0x140013989  lea     rdx, [rbp+var_10]
0x14001398d  mov     rcx, r14
0x140013990  call    FIVolumeGet
0x140013995  mov     rsi, [rbp+var_10]
0x140013999  mov     edi, eax
0x14001399b  test    eax, eax
0x14001399d  js      loc_140013B2F
0x1400139a3  bt      ebx, 12h
0x1400139a7  jnb     loc_140013B42
0x1400139ad  lea     rcx, [rbp+Context]
0x1400139b1  call    FIStreamCreate
0x1400139b6  mov     edi, eax
0x1400139b8  test    eax, eax
0x1400139ba  js      loc_140013A64
0x1400139c0  mov     rdx, [r14+10h]
0x1400139c4  mov     rax, [rbp+Context]
0x1400139c8  mov     rcx, [rdx+18h]
0x1400139cc  mov     [rax+20h], rcx
0x1400139d0  cmp     qword ptr [rdx+20h], 0
0x1400139d5  jnz     loc_140013B66
0x1400139db  mov     rax, [rbp+Context]
0x1400139df  or      dword ptr [rax+38h], 4
0x1400139e3  mov     rax, [rbp+Context]
0x1400139e7  lea     rdi, [rsi+18h]
0x1400139eb  mov     rcx, rdi
0x1400139ee  mov     [rax+18h], rsi
0x1400139f2  call    FILockExclusiveAcquire
0x1400139f7  mov     rdx, [rsi+28h]
0x1400139fb  add     rsi, 20h ; ' '
0x1400139ff  cmp     [rdx], rsi
0x140013a02  jz      short loc_140013A0B
0x140013a04  mov     ecx, 3
0x140013a09  int     29h; Win8: RtlFailFast(ecx)
0x140013a0b  mov     rax, [rbp+Context]
0x140013a0f  mov     rcx, rdi
0x140013a12  mov     [rax], rsi
0x140013a15  mov     [rax+8], rdx
0x140013a19  mov     [rdx], rax
0x140013a1c  mov     [rsi+8], rax
0x140013a20  call    FILockExclusiveRelease
0x140013a25  mov     r9, [rbp+Context]; NewContext
0x140013a29  lea     rax, [rbp+var_8]
0x140013a2d  mov     rdx, [r14+10h]; FileObject
0x140013a31  xor     esi, esi
0x140013a33  mov     rcx, [r14+8]; Instance
0x140013a37  mov     [rsp+40h+OldContext], rax; OldContext
0x140013a3c  lea     r8d, [rsi+1]; Operation
0x140013a40  call    cs:__imp_FltSetStreamContext
0x140013a47  nop     dword ptr [rax+rax+00h]
0x140013a4c  mov     edi, eax
0x140013a4e  test    eax, eax
0x140013a50  js      loc_140013B8D
0x140013a56  mov     rax, [rbp+Context]
0x140013a5a  mov     [r12], rax
0x140013a5e  xor     edi, edi
0x140013a60  mov     [rbp+Context], rsi
0x140013a64  test    rsi, rsi
0x140013a67  jnz     loc_140013B9D
0x140013a6d  mov     rcx, [rbp+Context]; Context
0x140013a71  test    rcx, rcx
0x140013a74  jz      loc_140013940
0x140013a7a  call    cs:__imp_FltReleaseContext
0x140013a81  nop     dword ptr [rax+rax+00h]
0x140013a86  jmp     loc_140013940
0x140013a8b  mov     rcx, [rbp+Context]
0x140013a8f  add     rcx, 10h; RunRef
0x140013a93  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140013a9a  nop     dword ptr [rax+rax+00h]
0x140013a9f  mov     rax, [rbp+Context]
0x140013aa3  mov     rcx, [rax+18h]
0x140013aa7  add     rcx, 18h
0x140013aab  call    FILockExclusiveAcquire
0x140013ab0  mov     rcx, [rbp+Context]
0x140013ab4  mov     rax, [rcx]
0x140013ab7  cmp     rax, rcx
0x140013aba  jz      short loc_140013ADE
0x140013abc  cmp     [rax+8], rcx
0x140013ac0  jnz     loc_140013A04
0x140013ac6  mov     rdx, [rcx+8]
0x140013aca  cmp     [rdx], rcx
0x140013acd  jnz     loc_140013A04
0x140013ad3  mov     [rdx], rax
0x140013ad6  mov     [rax+8], rdx
0x140013ada  mov     rcx, [rbp+Context]
0x140013ade  mov     rcx, [rcx+18h]
0x140013ae2  add     rcx, 18h
0x140013ae6  call    FILockExclusiveRelease
0x140013aeb  mov     rcx, [rbp+Context]
0x140013aef  mov     rcx, [rcx+18h]; Context
0x140013af3  call    cs:__imp_FltReleaseContext
0x140013afa  nop     dword ptr [rax+rax+00h]
0x140013aff  mov     rax, [rbp+Context]
0x140013b03  mov     [rax+18h], rsi
0x140013b07  mov     rcx, [rbp+Context]; Context
0x140013b0b  call    cs:__imp_FltReleaseContext
0x140013b12  nop     dword ptr [rax+rax+00h]
0x140013b17  mov     rax, [rbp+var_8]
0x140013b1b  jmp     loc_140013A5A
0x140013b20  or      ebx, 2
0x140013b23  jmp     loc_140013A6D
0x140013b28  mov     edi, eax
0x140013b2a  jmp     loc_140013A6D
0x140013b2f  mov     eax, ebx
0x140013b31  or      eax, 2
0x140013b34  test    byte ptr [rbp+arg_8], 2
0x140013b38  cmovz   eax, ebx
0x140013b3b  mov     ebx, eax
0x140013b3d  jmp     loc_140013A64
0x140013b42  mov     rax, [rsi+68h]
0x140013b46  lea     rcx, FIUnknown; "\\FI_UNKNOWN"
0x140013b4d  cmp     rax, rcx
0x140013b50  jnz     loc_1400139AD
0x140013b56  mov     rdx, rsi
0x140013b59  mov     rcx, r14
0x140013b5c  call    FIVolumeQueueQuery
0x140013b61  jmp     loc_1400139AD
0x140013b66  test    r13, r13
0x140013b69  jz      loc_1400139E3
0x140013b6f  mov     rax, [r13+10h]
0x140013b73  cmp     byte ptr [rax+4], 0
0x140013b77  jnz     loc_1400139E3
0x140013b7d  mov     eax, [rax+20h]
0x140013b80  test    al, 1
0x140013b82  jz      loc_1400139E3
0x140013b88  jmp     loc_1400139DB
0x140013b8d  cmp     eax, 0C01C0002h
0x140013b92  jnz     loc_140013A6D
0x140013b98  jmp     loc_140013A8B
0x140013b9d  mov     rcx, rsi; Context
0x140013ba0  call    cs:__imp_FltReleaseContext
0x140013ba7  nop     dword ptr [rax+rax+00h]
0x140013bac  jmp     loc_140013A6D
```
