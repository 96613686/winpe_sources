# FatCommonLockControl

- ea: `0x140043c80`
- end: `0x140043e37`
- name: `FatCommonLockControl`
- size: `439`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400438e0`
- `0x140044460`

## callees

- `0x140007408`
- `0x140038eb4`
- `0x14003d880`
- `0x140043c80`
- `0x1400468c4`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x140043d6b`
- `ntoskrnl!FsRtlCheckOplock` at `0x140043d6b`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140043dbe`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140043dbe`
- `ntoskrnl!FsRtlAreThereWaitingFileLocks` at `0x140043d41`
- `ntoskrnl!FsRtlAreThereWaitingFileLocks` at `0x140043d41`
- `ntoskrnl!FsRtlProcessFileLock` at `0x140043d99`
- `ntoskrnl!FsRtlProcessFileLock` at `0x140043d99`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043e23`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f503`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043e23`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f503`

## pseudocode

```c
__int64 __fastcall FatCommonLockControl(PVOID Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v8; // r12d
  char v9; // r15
  __int64 v10; // rbx
  __int64 v11; // r9
  char v12; // di
  __int64 v13; // [rsp+88h] [rbp+10h] BYREF
  __int64 v14; // [rsp+90h] [rbp+18h] BYREF
  __int64 v15; // [rsp+98h] [rbp+20h] BYREF

  v15 = 0;
  v13 = 0;
  v14 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, &v15, &v13, &v14) != 2 )
  {
    FatCompleteRequest_Real(Entry, Irp, 3221225485LL, v6);
    return 3221225485LL;
  }
  v8 = 0;
  v9 = 0;
  v10 = v13;
  if ( !(unsigned __int8)FatAcquireSharedFcb(Entry, v13, v5, v6) )
    return FatFsdPostRequest(Entry, Irp);
  v12 = 1;
  if ( CurrentStackLocation->MinorFunction == 1 )
  {
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart >= *(_QWORD *)(v10 + 24) )
      goto LABEL_10;
    goto LABEL_9;
  }
  if ( (unsigned __int8)FsRtlAreThereWaitingFileLocks(v10 + 320) )
LABEL_9:
    v8 = FsRtlCheckOplock((POPLOCK)(v10 + 88), Irp, Entry, FatOplockComplete, 0);
LABEL_10:
  if ( v8 )
  {
    v9 = 1;
  }
  else
  {
    v8 = FsRtlProcessFileLock((PFILE_LOCK)(v10 + 320), Irp, 0);
    if ( *(_DWORD *)(v10 + 196) == 1 && *(_WORD *)v10 == 1282 && FsRtlOplockIsFastIoPossible((POPLOCK)(v10 + 88)) )
    {
      if ( *(_BYTE *)(v10 + 336)
        || *(_DWORD *)(*(_QWORD *)(v10 + 120) + 24LL)
        || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 200LL) & 0x4000) != 0
        || (*(_DWORD *)(v10 + 192) & 0x8000) != 0 )
      {
        v12 = 2;
      }
    }
    else
    {
      v12 = 0;
    }
    *(_BYTE *)(v10 + 5) = v12;
  }
  if ( !v9 )
    FatCompleteRequest_Real(Entry, 0, 0, v11);
  ExReleaseResourceLite(*(PERESOURCE *)(v10 + 8));
  return v8;
}

```

## disassembly

```asm
0x140043c80  mov     rax, rsp
0x140043c83  mov     [rax+8], rcx
0x140043c87  push    rbx
0x140043c88  push    rsi
0x140043c89  push    rdi
0x140043c8a  push    r12
0x140043c8c  push    r13
0x140043c8e  push    r14
0x140043c90  push    r15
0x140043c92  sub     rsp, 40h
0x140043c96  mov     rsi, rdx
0x140043c99  mov     r14, rcx
0x140043c9c  xor     edi, edi
0x140043c9e  mov     [rax+20h], rdi
0x140043ca2  mov     [rax+10h], rdi
0x140043ca6  mov     [rax+18h], rdi
0x140043caa  mov     r13, [rdx+0B8h]
0x140043cb1  lea     r9, [rax+18h]
0x140043cb5  lea     r8, [rax+10h]
0x140043cb9  lea     rdx, [rax+20h]
0x140043cbd  mov     rcx, [r13+30h]
0x140043cc1  call    FatDecodeFileObject
0x140043cc6  mov     rcx, r14; Entry
0x140043cc9  cmp     eax, 2
0x140043ccc  jz      short loc_140043CF1
0x140043cce  mov     ebx, 0C000000Dh
0x140043cd3  mov     r8d, ebx
0x140043cd6  mov     rdx, rsi; Irp
0x140043cd9  call    FatCompleteRequest_Real
0x140043cde  mov     eax, ebx
0x140043ce0  add     rsp, 40h
0x140043ce4  pop     r15
0x140043ce6  pop     r14
0x140043ce8  pop     r13
0x140043cea  pop     r12
0x140043cec  pop     rdi
0x140043ced  pop     rsi
0x140043cee  pop     rbx
0x140043cef  retn
0x140043cf1  mov     r12d, edi
0x140043cf4  mov     r15b, dil
0x140043cf7  mov     [rsp+78h+var_48], dil
0x140043cfc  mov     rbx, [rsp+78h+arg_8]
0x140043d04  mov     rdx, rbx
0x140043d07  call    FatAcquireSharedFcb
0x140043d0c  test    al, al
0x140043d0e  jnz     short loc_140043D1D
0x140043d10  mov     rdx, rsi; Context2
0x140043d13  mov     rcx, r14; Context1
0x140043d16  call    FatFsdPostRequest
0x140043d1b  jmp     short loc_140043CE0
0x140043d1d  mov     cl, [r13+1]
0x140043d21  mov     edi, 1
0x140043d26  cmp     cl, dil
0x140043d29  jnz     short loc_140043D3A
0x140043d2b  mov     rax, [rbx+18h]
0x140043d2f  cmp     [r13+18h], rax
0x140043d33  jb      short loc_140043D51
0x140043d35  cmp     cl, dil
0x140043d38  jz      short loc_140043D7A
0x140043d3a  lea     rcx, [rbx+140h]
0x140043d41  call    cs:__imp_FsRtlAreThereWaitingFileLocks
0x140043d48  nop     dword ptr [rax+rax+00h]
0x140043d4d  test    al, al
0x140043d4f  jz      short loc_140043D7A
0x140043d51  lea     rcx, [rbx+58h]; Oplock
0x140043d55  mov     [rsp+78h+PostIrpRoutine], 0; PostIrpRoutine
0x140043d5e  lea     r9, FatOplockComplete; CompletionRoutine
0x140043d65  mov     r8, r14; Context
0x140043d68  mov     rdx, rsi; Irp
0x140043d6b  call    cs:__imp_FsRtlCheckOplock
0x140043d72  nop     dword ptr [rax+rax+00h]
0x140043d77  mov     r12d, eax
0x140043d7a  test    r12d, r12d
0x140043d7d  jz      short loc_140043D8C
0x140043d7f  mov     r15b, dil
0x140043d82  mov     [rsp+78h+var_48], dil
0x140043d87  jmp     loc_140043E0D
0x140043d8c  lea     rcx, [rbx+140h]; FileLock
0x140043d93  xor     r8d, r8d; Context
0x140043d96  mov     rdx, rsi; Irp
0x140043d99  call    cs:__imp_FsRtlProcessFileLock
0x140043da0  nop     dword ptr [rax+rax+00h]
0x140043da5  mov     r12d, eax
0x140043da8  cmp     [rbx+0C4h], edi
0x140043dae  jnz     short loc_140043E07
0x140043db0  mov     eax, 502h
0x140043db5  cmp     [rbx], ax
0x140043db8  jnz     short loc_140043E07
0x140043dba  lea     rcx, [rbx+58h]; Oplock
0x140043dbe  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140043dc5  nop     dword ptr [rax+rax+00h]
0x140043dca  test    al, al
0x140043dcc  jz      short loc_140043E07
0x140043dce  cmp     byte ptr [rbx+150h], 0
0x140043dd5  jnz     short loc_140043E00
0x140043dd7  mov     rax, [rbx+78h]
0x140043ddb  cmp     dword ptr [rax+18h], 0
0x140043ddf  jnz     short loc_140043E00
0x140043de1  mov     rax, [rbx+0B8h]
0x140043de8  mov     ecx, [rax+0C8h]
0x140043dee  bt      ecx, 0Eh
0x140043df2  jb      short loc_140043E00
0x140043df4  test    dword ptr [rbx+0C0h], 8000h
0x140043dfe  jz      short loc_140043E09
0x140043e00  mov     edi, 2
0x140043e05  jmp     short loc_140043E09
0x140043e07  xor     edi, edi
0x140043e09  mov     [rbx+5], dil
0x140043e0d  test    r15b, r15b
0x140043e10  jnz     short loc_140043E1F
0x140043e12  xor     r8d, r8d
0x140043e15  xor     edx, edx; Irp
0x140043e17  mov     rcx, r14; Entry
0x140043e1a  call    FatCompleteRequest_Real
0x140043e1f  mov     rcx, [rbx+8]; Resource
0x140043e23  call    cs:__imp_ExReleaseResourceLite
0x140043e2a  nop     dword ptr [rax+rax+00h]
0x140043e2f  mov     eax, r12d
0x140043e32  jmp     loc_140043CE0
0x14005f4d1  push    rbp
0x14005f4d3  sub     rsp, 30h
0x14005f4d7  mov     rbp, rdx
0x14005f4da  movzx   eax, cl
0x14005f4dd  test    cl, cl
0x14005f4df  jnz     short loc_14005F4F8
0x14005f4e1  cmp     [rbp+30h], cl
0x14005f4e4  jnz     short loc_14005F4F8
0x14005f4e6  xor     r8d, r8d
0x14005f4e9  xor     edx, edx; Irp
0x14005f4eb  mov     rcx, [rbp+80h]; Entry
0x14005f4f2  call    FatCompleteRequest_Real
0x14005f4f7  nop
0x14005f4f8  mov     rcx, [rbp+88h]
0x14005f4ff  mov     rcx, [rcx+8]; Resource
0x14005f503  call    cs:__imp_ExReleaseResourceLite
0x14005f50a  nop     dword ptr [rax+rax+00h]
0x14005f50f  nop
0x14005f510  add     rsp, 30h
0x14005f514  pop     rbp
0x14005f515  retn
```
