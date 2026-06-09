# FTInstanceTeardownStart

- ea: `0x14000d740`
- end: `0x14000d845`
- name: `FTInstanceTeardownStart`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000d740`

## import_xrefs

- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14000d787`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14000d787`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d830`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d830`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d79a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d79a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d7d5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d7d5`
- `FLTMGR!FltReleaseContext` at `0x14000d7eb`
- `FLTMGR!FltReleaseContext` at `0x14000d7eb`
- `FLTMGR!FltGetVolumeContext` at `0x14000d766`
- `FLTMGR!FltGetVolumeContext` at `0x14000d766`
- `FLTMGR!FltObjectDereference` at `0x14000d803`
- `FLTMGR!FltObjectDereference` at `0x14000d803`

## pseudocode

```c
void __fastcall FTInstanceTeardownStart(__int64 a1)
{
  struct _FLT_VOLUME *v1; // rdx
  void *v3; // rcx
  PVOID *v4; // rbx
  PVOID v5; // rcx
  _QWORD *v6; // rcx
  PVOID *v7; // rax
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(struct _FLT_VOLUME **)(a1 + 16);
  Context = 0;
  if ( FltGetVolumeContext((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor, v1, &Context) >= 0 )
  {
    v3 = (void *)*((_QWORD *)Context + 61);
    if ( v3 )
      IoUnregisterPlugPlayNotification(v3);
  }
  ExAcquireFastMutex(&FastMutex);
  v4 = (PVOID *)P;
  if ( P != &P )
  {
    while ( 1 )
    {
      v5 = v4[2];
      if ( v5 == *(PVOID *)(a1 + 16) )
        break;
      v4 = (PVOID *)*v4;
      if ( v4 == &P )
        goto LABEL_7;
    }
    FltObjectDereference(v5);
    v6 = *v4;
    if ( *((PVOID **)*v4 + 1) != v4 || (v7 = (PVOID *)v4[1], *v7 != v4) )
      __fastfail(3u);
    *v7 = v6;
    v6[1] = v7;
    ExFreePoolWithTag(v4, 0x72744C46u);
  }
LABEL_7:
  ExReleaseFastMutex(&FastMutex);
  if ( Context )
    FltReleaseContext(Context);
}

```

## disassembly

```asm
0x14000d740  mov     [rsp+arg_8], rbx
0x14000d745  push    rdi
0x14000d746  sub     rsp, 20h
0x14000d74a  mov     rdx, [rcx+10h]; Volume
0x14000d74e  lea     r8, [rsp+28h+Context]; Context
0x14000d753  mov     rdi, rcx
0x14000d756  mov     [rsp+28h+Context], 0
0x14000d75f  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000d766  call    cs:__imp_FltGetVolumeContext
0x14000d76d  nop     dword ptr [rax+rax+00h]
0x14000d772  test    eax, eax
0x14000d774  js      short loc_14000D793
0x14000d776  mov     rax, [rsp+28h+Context]
0x14000d77b  mov     rcx, [rax+1E8h]; NotificationEntry
0x14000d782  test    rcx, rcx
0x14000d785  jz      short loc_14000D793
0x14000d787  call    cs:__imp_IoUnregisterPlugPlayNotification
0x14000d78e  nop     dword ptr [rax+rax+00h]
0x14000d793  lea     rcx, FastMutex; FastMutex
0x14000d79a  call    cs:__imp_ExAcquireFastMutex
0x14000d7a1  nop     dword ptr [rax+rax+00h]
0x14000d7a6  mov     rbx, cs:P
0x14000d7ad  lea     rdx, P
0x14000d7b4  cmp     rbx, rdx
0x14000d7b7  jz      short loc_14000D7CE
0x14000d7b9  mov     rax, [rdi+10h]
0x14000d7bd  mov     rcx, [rbx+10h]; FltObject
0x14000d7c1  cmp     rcx, rax
0x14000d7c4  jz      short loc_14000D803
0x14000d7c6  mov     rbx, [rbx]
0x14000d7c9  cmp     rbx, rdx
0x14000d7cc  jnz     short loc_14000D7BD
0x14000d7ce  lea     rcx, FastMutex; FastMutex
0x14000d7d5  call    cs:__imp_ExReleaseFastMutex
0x14000d7dc  nop     dword ptr [rax+rax+00h]
0x14000d7e1  mov     rcx, [rsp+28h+Context]; Context
0x14000d7e6  test    rcx, rcx
0x14000d7e9  jz      short loc_14000D7F7
0x14000d7eb  call    cs:__imp_FltReleaseContext
0x14000d7f2  nop     dword ptr [rax+rax+00h]
0x14000d7f7  mov     rbx, [rsp+28h+arg_8]
0x14000d7fc  add     rsp, 20h
0x14000d800  pop     rdi
0x14000d801  retn
0x14000d803  call    cs:__imp_FltObjectDereference
0x14000d80a  nop     dword ptr [rax+rax+00h]
0x14000d80f  mov     rcx, [rbx]
0x14000d812  cmp     [rcx+8], rbx
0x14000d816  jnz     short loc_14000D83E
0x14000d818  mov     rax, [rbx+8]
0x14000d81c  cmp     [rax], rbx
0x14000d81f  jnz     short loc_14000D83E
0x14000d821  mov     [rax], rcx
0x14000d824  mov     edx, 72744C46h; Tag
0x14000d829  mov     [rcx+8], rax
0x14000d82d  mov     rcx, rbx; P
0x14000d830  call    cs:__imp_ExFreePoolWithTag
0x14000d837  nop     dword ptr [rax+rax+00h]
0x14000d83c  jmp     short loc_14000D7CE
0x14000d83e  mov     ecx, 3
0x14000d843  int     29h; Win8: RtlFailFast(ecx)
```
