# DetachFromDrives

- ea: `0x14000b4a0`
- end: `0x14000b5f8`
- name: `DetachFromDrives`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b600`

## callees

- `0x14000b4a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b58a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b58a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b4ea`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b4ea`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b5c2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b5c2`
- `ntoskrnl!DbgPrintEx` at `0x14000b4c5`
- `ntoskrnl!DbgPrintEx` at `0x14000b53f`
- `ntoskrnl!DbgPrintEx` at `0x14000b5a3`
- `ntoskrnl!DbgPrintEx` at `0x14000b5d9`
- `ntoskrnl!DbgPrintEx` at `0x14000b4c5`
- `ntoskrnl!DbgPrintEx` at `0x14000b53f`
- `ntoskrnl!DbgPrintEx` at `0x14000b5a3`
- `ntoskrnl!DbgPrintEx` at `0x14000b5d9`
- `FLTMGR!FltDetachVolume` at `0x14000b524`
- `FLTMGR!FltDetachVolume` at `0x14000b524`
- `FLTMGR!FltObjectDereference` at `0x14000b54f`
- `FLTMGR!FltObjectDereference` at `0x14000b54f`

## pseudocode

```c
ULONG __fastcall DetachFromDrives(int a1)
{
  PVOID *v3; // rbx
  int v4; // r9d
  PVOID *v5; // r8
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rax
  PVOID *v9; // rcx

  DbgPrintEx(0x8Eu, 2u, "FileTrace!DetachFromDrives: Start, kept drives 0x%x\n", a1);
  if ( (a1 & 0x4000000) != 0 )
    return DbgPrintEx(0x8Eu, 2u, "\tNOTHING!!!\n");
  ExAcquireFastMutex(&FastMutex);
  v3 = (PVOID *)P;
  while ( v3 != &P )
  {
    v4 = *((_DWORD *)v3 + 6);
    if ( (v4 & a1) != 0 )
    {
      DbgPrintEx(0x8Eu, 2u, "\tKeeping attachment to 0x%x\n", v4);
      v3 = (PVOID *)*v3;
    }
    else
    {
      FltDetachVolume((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor, (PFLT_VOLUME)v3[2], 0);
      DbgPrintEx(0x8Eu, 2u, "\tDetaching from 0x%x\n", *((_DWORD *)v3 + 6));
      FltObjectDereference(v3[2]);
      v5 = (PVOID *)*v3;
      v6 = (_QWORD *)*((_QWORD *)*v3 + 1);
      v7 = *v6;
      if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v8 = (_QWORD *)v6[1], (_QWORD *)*v8 != v6) )
        __fastfail(3u);
      *v8 = v7;
      v9 = v3;
      *(_QWORD *)(v7 + 8) = v8;
      v3 = v5;
      ExFreePoolWithTag(v9, 0x72744C46u);
    }
  }
  ExReleaseFastMutex(&FastMutex);
  return DbgPrintEx(0x8Eu, 2u, "FileTrace!DetachFromDrives: END\n");
}

```

## disassembly

```asm
0x14000b4a0  push    rbx
0x14000b4a2  push    rbp
0x14000b4a3  push    rsi
0x14000b4a4  push    rdi
0x14000b4a5  push    r14
0x14000b4a7  sub     rsp, 20h
0x14000b4ab  mov     edi, ecx
0x14000b4ad  lea     r8, aFiletraceDetac_0; "FileTrace!DetachFromDrives: Start, kept"...
0x14000b4b4  mov     r9d, ecx
0x14000b4b7  mov     esi, 2
0x14000b4bc  mov     ebp, 8Eh
0x14000b4c1  mov     edx, esi; Level
0x14000b4c3  mov     ecx, ebp; ComponentId
0x14000b4c5  call    cs:__imp_DbgPrintEx
0x14000b4cc  nop     dword ptr [rax+rax+00h]
0x14000b4d1  bt      edi, 1Ah
0x14000b4d5  jnb     short loc_14000B4E3
0x14000b4d7  lea     r8, aNothing; "\tNOTHING!!!\n"
0x14000b4de  jmp     loc_14000B5D5
0x14000b4e3  lea     rcx, FastMutex; FastMutex
0x14000b4ea  call    cs:__imp_ExAcquireFastMutex
0x14000b4f1  nop     dword ptr [rax+rax+00h]
0x14000b4f6  mov     rbx, cs:P
0x14000b4fd  lea     r14, P
0x14000b504  jmp     loc_14000B5B2
0x14000b509  mov     r9d, [rbx+18h]
0x14000b50d  test    edi, r9d
0x14000b510  jnz     loc_14000B598
0x14000b516  mov     rdx, [rbx+10h]; Volume
0x14000b51a  xor     r8d, r8d; InstanceName
0x14000b51d  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000b524  call    cs:__imp_FltDetachVolume
0x14000b52b  nop     dword ptr [rax+rax+00h]
0x14000b530  mov     r9d, [rbx+18h]
0x14000b534  lea     r8, aDetachingFrom0; "\tDetaching from 0x%x\n"
0x14000b53b  mov     edx, esi; Level
0x14000b53d  mov     ecx, ebp; ComponentId
0x14000b53f  call    cs:__imp_DbgPrintEx
0x14000b546  nop     dword ptr [rax+rax+00h]
0x14000b54b  mov     rcx, [rbx+10h]; FltObject
0x14000b54f  call    cs:__imp_FltObjectDereference
0x14000b556  nop     dword ptr [rax+rax+00h]
0x14000b55b  mov     r8, [rbx]
0x14000b55e  mov     rcx, [r8+8]
0x14000b562  mov     rdx, [rcx]
0x14000b565  cmp     [rdx+8], rcx
0x14000b569  jnz     loc_14000B5F1
0x14000b56f  mov     rax, [rcx+8]
0x14000b573  cmp     [rax], rcx
0x14000b576  jnz     short loc_14000B5F1
0x14000b578  mov     [rax], rdx
0x14000b57b  mov     rcx, rbx; P
0x14000b57e  mov     [rdx+8], rax
0x14000b582  mov     rbx, r8
0x14000b585  mov     edx, 72744C46h; Tag
0x14000b58a  call    cs:__imp_ExFreePoolWithTag
0x14000b591  nop     dword ptr [rax+rax+00h]
0x14000b596  jmp     short loc_14000B5B2
0x14000b598  lea     r8, aKeepingAttachm; "\tKeeping attachment to 0x%x\n"
0x14000b59f  mov     edx, esi; Level
0x14000b5a1  mov     ecx, ebp; ComponentId
0x14000b5a3  call    cs:__imp_DbgPrintEx
0x14000b5aa  nop     dword ptr [rax+rax+00h]
0x14000b5af  mov     rbx, [rbx]
0x14000b5b2  cmp     rbx, r14
0x14000b5b5  jnz     loc_14000B509
0x14000b5bb  lea     rcx, FastMutex; FastMutex
0x14000b5c2  call    cs:__imp_ExReleaseFastMutex
0x14000b5c9  nop     dword ptr [rax+rax+00h]
0x14000b5ce  lea     r8, aFiletraceDetac; "FileTrace!DetachFromDrives: END\n"
0x14000b5d5  mov     edx, esi; Level
0x14000b5d7  mov     ecx, ebp; ComponentId
0x14000b5d9  call    cs:__imp_DbgPrintEx
0x14000b5e0  nop     dword ptr [rax+rax+00h]
0x14000b5e5  add     rsp, 20h
0x14000b5e9  pop     r14
0x14000b5eb  pop     rdi
0x14000b5ec  pop     rsi
0x14000b5ed  pop     rbp
0x14000b5ee  pop     rbx
0x14000b5ef  retn
0x14000b5f1  mov     ecx, 3
0x14000b5f6  int     29h; Win8: RtlFailFast(ecx)
```
