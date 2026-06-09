# FTInstanceTeardownStart

- ea: `0x14000d700`
- end: `0x14000d805`
- name: `FTInstanceTeardownStart`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000d700`

## import_xrefs

- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14000d747`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14000d747`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7f0`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d75a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d75a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d795`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d795`
- `FLTMGR!FltReleaseContext` at `0x14000d7ab`
- `FLTMGR!FltReleaseContext` at `0x14000d7ab`
- `FLTMGR!FltGetVolumeContext` at `0x14000d726`
- `FLTMGR!FltGetVolumeContext` at `0x14000d726`
- `FLTMGR!FltObjectDereference` at `0x14000d7c3`
- `FLTMGR!FltObjectDereference` at `0x14000d7c3`

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
0x14000d700  mov     [rsp+arg_8], rbx
0x14000d705  push    rdi
0x14000d706  sub     rsp, 20h
0x14000d70a  mov     rdx, [rcx+10h]; Volume
0x14000d70e  lea     r8, [rsp+28h+Context]; Context
0x14000d713  mov     rdi, rcx
0x14000d716  mov     [rsp+28h+Context], 0
0x14000d71f  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000d726  call    cs:__imp_FltGetVolumeContext
0x14000d72d  nop     dword ptr [rax+rax+00h]
0x14000d732  test    eax, eax
0x14000d734  js      short loc_14000D753
0x14000d736  mov     rax, [rsp+28h+Context]
0x14000d73b  mov     rcx, [rax+1E8h]; NotificationEntry
0x14000d742  test    rcx, rcx
0x14000d745  jz      short loc_14000D753
0x14000d747  call    cs:__imp_IoUnregisterPlugPlayNotification
0x14000d74e  nop     dword ptr [rax+rax+00h]
0x14000d753  lea     rcx, FastMutex; FastMutex
0x14000d75a  call    cs:__imp_ExAcquireFastMutex
0x14000d761  nop     dword ptr [rax+rax+00h]
0x14000d766  mov     rbx, cs:P
0x14000d76d  lea     rdx, P
0x14000d774  cmp     rbx, rdx
0x14000d777  jz      short loc_14000D78E
0x14000d779  mov     rax, [rdi+10h]
0x14000d77d  mov     rcx, [rbx+10h]; FltObject
0x14000d781  cmp     rcx, rax
0x14000d784  jz      short loc_14000D7C3
0x14000d786  mov     rbx, [rbx]
0x14000d789  cmp     rbx, rdx
0x14000d78c  jnz     short loc_14000D77D
0x14000d78e  lea     rcx, FastMutex; FastMutex
0x14000d795  call    cs:__imp_ExReleaseFastMutex
0x14000d79c  nop     dword ptr [rax+rax+00h]
0x14000d7a1  mov     rcx, [rsp+28h+Context]; Context
0x14000d7a6  test    rcx, rcx
0x14000d7a9  jz      short loc_14000D7B7
0x14000d7ab  call    cs:__imp_FltReleaseContext
0x14000d7b2  nop     dword ptr [rax+rax+00h]
0x14000d7b7  mov     rbx, [rsp+28h+arg_8]
0x14000d7bc  add     rsp, 20h
0x14000d7c0  pop     rdi
0x14000d7c1  retn
0x14000d7c3  call    cs:__imp_FltObjectDereference
0x14000d7ca  nop     dword ptr [rax+rax+00h]
0x14000d7cf  mov     rcx, [rbx]
0x14000d7d2  cmp     [rcx+8], rbx
0x14000d7d6  jnz     short loc_14000D7FE
0x14000d7d8  mov     rax, [rbx+8]
0x14000d7dc  cmp     [rax], rbx
0x14000d7df  jnz     short loc_14000D7FE
0x14000d7e1  mov     [rax], rcx
0x14000d7e4  mov     edx, 72744C46h; Tag
0x14000d7e9  mov     [rcx+8], rax
0x14000d7ed  mov     rcx, rbx; P
0x14000d7f0  call    cs:__imp_ExFreePoolWithTag
0x14000d7f7  nop     dword ptr [rax+rax+00h]
0x14000d7fc  jmp     short loc_14000D78E
0x14000d7fe  mov     ecx, 3
0x14000d803  int     29h; Win8: RtlFailFast(ecx)
```
