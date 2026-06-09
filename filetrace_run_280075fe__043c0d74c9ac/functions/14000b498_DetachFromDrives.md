# DetachFromDrives

- ea: `0x14000b498`
- end: `0x14000b5f0`
- name: `DetachFromDrives`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b600`

## callees

- `0x14000b498`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b582`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b582`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b4e2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b4e2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b5ba`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b5ba`
- `ntoskrnl!DbgPrintEx` at `0x14000b4bd`
- `ntoskrnl!DbgPrintEx` at `0x14000b537`
- `ntoskrnl!DbgPrintEx` at `0x14000b59b`
- `ntoskrnl!DbgPrintEx` at `0x14000b5d1`
- `ntoskrnl!DbgPrintEx` at `0x14000b4bd`
- `ntoskrnl!DbgPrintEx` at `0x14000b537`
- `ntoskrnl!DbgPrintEx` at `0x14000b59b`
- `ntoskrnl!DbgPrintEx` at `0x14000b5d1`
- `FLTMGR!FltDetachVolume` at `0x14000b51c`
- `FLTMGR!FltDetachVolume` at `0x14000b51c`
- `FLTMGR!FltObjectDereference` at `0x14000b547`
- `FLTMGR!FltObjectDereference` at `0x14000b547`

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
0x14000b498  push    rbx
0x14000b49a  push    rbp
0x14000b49b  push    rsi
0x14000b49c  push    rdi
0x14000b49d  push    r14
0x14000b49f  sub     rsp, 20h
0x14000b4a3  mov     edi, ecx
0x14000b4a5  lea     r8, aFiletraceDetac_0; "FileTrace!DetachFromDrives: Start, kept"...
0x14000b4ac  mov     r9d, ecx
0x14000b4af  mov     esi, 2
0x14000b4b4  mov     ebp, 8Eh
0x14000b4b9  mov     edx, esi; Level
0x14000b4bb  mov     ecx, ebp; ComponentId
0x14000b4bd  call    cs:__imp_DbgPrintEx
0x14000b4c4  nop     dword ptr [rax+rax+00h]
0x14000b4c9  bt      edi, 1Ah
0x14000b4cd  jnb     short loc_14000B4DB
0x14000b4cf  lea     r8, aNothing; "\tNOTHING!!!\n"
0x14000b4d6  jmp     loc_14000B5CD
0x14000b4db  lea     rcx, FastMutex; FastMutex
0x14000b4e2  call    cs:__imp_ExAcquireFastMutex
0x14000b4e9  nop     dword ptr [rax+rax+00h]
0x14000b4ee  mov     rbx, cs:P
0x14000b4f5  lea     r14, P
0x14000b4fc  jmp     loc_14000B5AA
0x14000b501  mov     r9d, [rbx+18h]
0x14000b505  test    edi, r9d
0x14000b508  jnz     loc_14000B590
0x14000b50e  mov     rdx, [rbx+10h]; Volume
0x14000b512  xor     r8d, r8d; InstanceName
0x14000b515  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000b51c  call    cs:__imp_FltDetachVolume
0x14000b523  nop     dword ptr [rax+rax+00h]
0x14000b528  mov     r9d, [rbx+18h]
0x14000b52c  lea     r8, aDetachingFrom0; "\tDetaching from 0x%x\n"
0x14000b533  mov     edx, esi; Level
0x14000b535  mov     ecx, ebp; ComponentId
0x14000b537  call    cs:__imp_DbgPrintEx
0x14000b53e  nop     dword ptr [rax+rax+00h]
0x14000b543  mov     rcx, [rbx+10h]; FltObject
0x14000b547  call    cs:__imp_FltObjectDereference
0x14000b54e  nop     dword ptr [rax+rax+00h]
0x14000b553  mov     r8, [rbx]
0x14000b556  mov     rcx, [r8+8]
0x14000b55a  mov     rdx, [rcx]
0x14000b55d  cmp     [rdx+8], rcx
0x14000b561  jnz     loc_14000B5E9
0x14000b567  mov     rax, [rcx+8]
0x14000b56b  cmp     [rax], rcx
0x14000b56e  jnz     short loc_14000B5E9
0x14000b570  mov     [rax], rdx
0x14000b573  mov     rcx, rbx; P
0x14000b576  mov     [rdx+8], rax
0x14000b57a  mov     rbx, r8
0x14000b57d  mov     edx, 72744C46h; Tag
0x14000b582  call    cs:__imp_ExFreePoolWithTag
0x14000b589  nop     dword ptr [rax+rax+00h]
0x14000b58e  jmp     short loc_14000B5AA
0x14000b590  lea     r8, aKeepingAttachm; "\tKeeping attachment to 0x%x\n"
0x14000b597  mov     edx, esi; Level
0x14000b599  mov     ecx, ebp; ComponentId
0x14000b59b  call    cs:__imp_DbgPrintEx
0x14000b5a2  nop     dword ptr [rax+rax+00h]
0x14000b5a7  mov     rbx, [rbx]
0x14000b5aa  cmp     rbx, r14
0x14000b5ad  jnz     loc_14000B501
0x14000b5b3  lea     rcx, FastMutex; FastMutex
0x14000b5ba  call    cs:__imp_ExReleaseFastMutex
0x14000b5c1  nop     dword ptr [rax+rax+00h]
0x14000b5c6  lea     r8, aFiletraceDetac; "FileTrace!DetachFromDrives: END\n"
0x14000b5cd  mov     edx, esi; Level
0x14000b5cf  mov     ecx, ebp; ComponentId
0x14000b5d1  call    cs:__imp_DbgPrintEx
0x14000b5d8  nop     dword ptr [rax+rax+00h]
0x14000b5dd  add     rsp, 20h
0x14000b5e1  pop     r14
0x14000b5e3  pop     rdi
0x14000b5e4  pop     rsi
0x14000b5e5  pop     rbp
0x14000b5e6  pop     rbx
0x14000b5e7  retn
0x14000b5e9  mov     ecx, 3
0x14000b5ee  int     29h; Win8: RtlFailFast(ecx)
```
