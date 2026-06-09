# DisableSession

- ea: `0x14000b600`
- end: `0x14000b830`
- name: `DisableSession`
- size: `560`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000b4a0`
- `0x14000b600`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b80a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b80a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b691`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b691`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b712`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b7e2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b712`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b7e2`
- `ntoskrnl!DbgPrintEx` at `0x14000b646`
- `ntoskrnl!DbgPrintEx` at `0x14000b67d`
- `ntoskrnl!DbgPrintEx` at `0x14000b6f8`
- `ntoskrnl!DbgPrintEx` at `0x14000b72f`
- `ntoskrnl!DbgPrintEx` at `0x14000b7ad`
- `ntoskrnl!DbgPrintEx` at `0x14000b646`
- `ntoskrnl!DbgPrintEx` at `0x14000b67d`
- `ntoskrnl!DbgPrintEx` at `0x14000b6f8`
- `ntoskrnl!DbgPrintEx` at `0x14000b72f`
- `ntoskrnl!DbgPrintEx` at `0x14000b7ad`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000b81c`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000b81c`

## pseudocode

```c
void __fastcall DisableSession(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, _QWORD *Context)
{
  int i; // [rsp+20h] [rbp-28h]
  int j; // [rsp+20h] [rbp-28h]
  int v5; // [rsp+24h] [rbp-24h]
  unsigned int v6; // [rsp+28h] [rbp-20h]
  __int64 v7; // [rsp+30h] [rbp-18h]

  v5 = -1;
  LOWORD(v7) = 0;
  v6 = 0;
  DbgPrintEx(0x8Eu, 2u, "FileTrace!DisableSession: ");
  if ( Context )
  {
    v7 = *Context;
    DbgPrintEx(0x8Eu, 2u, "lh %I64X, ", *Context);
  }
  ExAcquireFastMutex(&SessionLock);
  for ( i = 0; i < 8; ++i )
  {
    if ( *((unsigned __int16 *)LogSessions + 20 * i) == (unsigned __int16)v7 )
    {
      v5 = i;
      DbgPrintEx(0x8Eu, 2u, "target session %d, ", i);
      goto LABEL_9;
    }
  }
  DbgPrintEx(0x8Eu, 2u, "target session %d, ", -1);
LABEL_9:
  if ( v5 >= 0 )
  {
    for ( j = 0; j < 8; ++j )
    {
      if ( j != v5 )
        v6 |= *((_DWORD *)LogSessions + 10 * j + 8);
    }
    DbgPrintEx(0x8Eu, 2u, "active session flags 0x%x\n", v6);
    memset((char *)LogSessions + 40 * v5, 0, 0x28u);
    ExReleaseFastMutex(&SessionLock);
    DetachFromDrives(v6);
  }
  else
  {
    ExReleaseFastMutex(&SessionLock);
    DbgPrintEx(0x8Eu, 2u, "SESSION NOT FOUND!\n");
  }
  if ( Context )
    ExFreePoolWithTag(Context, 0x72744C46u);
  FltFreeGenericWorkItem(FltWorkItem);
}

```

## disassembly

```asm
0x14000b600  mov     [rsp+P], r8
0x14000b605  mov     [rsp+arg_8], rdx
0x14000b60a  mov     [rsp+FltWorkItem], rcx
0x14000b60f  push    rdi
0x14000b610  sub     rsp, 40h
0x14000b614  mov     [rsp+48h+var_28], 0
0x14000b61c  mov     [rsp+48h+var_24], 0FFFFFFFFh
0x14000b624  mov     [rsp+48h+var_18], 0
0x14000b62d  mov     [rsp+48h+var_20], 0
0x14000b635  lea     r8, aFiletraceDisab; "FileTrace!DisableSession: "
0x14000b63c  mov     edx, 2; Level
0x14000b641  mov     ecx, 8Eh; ComponentId
0x14000b646  call    cs:__imp_DbgPrintEx
0x14000b64d  nop     dword ptr [rax+rax+00h]
0x14000b652  cmp     [rsp+48h+P], 0
0x14000b658  jz      short loc_14000B68A
0x14000b65a  mov     rax, [rsp+48h+P]
0x14000b65f  mov     rax, [rax]
0x14000b662  mov     [rsp+48h+var_18], rax
0x14000b667  mov     r9, [rsp+48h+var_18]
0x14000b66c  lea     r8, aLhI64x; "lh %I64X, "
0x14000b673  mov     edx, 2; Level
0x14000b678  mov     ecx, 8Eh; ComponentId
0x14000b67d  call    cs:__imp_DbgPrintEx
0x14000b684  nop     dword ptr [rax+rax+00h]
0x14000b689  nop
0x14000b68a  lea     rcx, SessionLock; FastMutex
0x14000b691  call    cs:__imp_ExAcquireFastMutex
0x14000b698  nop     dword ptr [rax+rax+00h]
0x14000b69d  nop
0x14000b69e  mov     [rsp+48h+var_28], 0
0x14000b6a6  jmp     short loc_14000B6B2
0x14000b6a8  mov     eax, [rsp+48h+var_28]
0x14000b6ac  inc     eax
0x14000b6ae  mov     [rsp+48h+var_28], eax
0x14000b6b2  cmp     [rsp+48h+var_28], 8
0x14000b6b7  jge     short loc_14000B6E2
0x14000b6b9  movsxd  rax, [rsp+48h+var_28]
0x14000b6be  imul    rax, 28h ; '('
0x14000b6c2  mov     rcx, cs:LogSessions
0x14000b6c9  movzx   eax, word ptr [rcx+rax]
0x14000b6cd  movzx   ecx, word ptr [rsp+48h+var_18]
0x14000b6d2  cmp     eax, ecx
0x14000b6d4  jnz     short loc_14000B6E0
0x14000b6d6  mov     eax, [rsp+48h+var_28]
0x14000b6da  mov     [rsp+48h+var_24], eax
0x14000b6de  jmp     short loc_14000B6E2
0x14000b6e0  jmp     short loc_14000B6A8
0x14000b6e2  mov     r9d, [rsp+48h+var_24]
0x14000b6e7  lea     r8, aTargetSessionD; "target session %d, "
0x14000b6ee  mov     edx, 2; Level
0x14000b6f3  mov     ecx, 8Eh; ComponentId
0x14000b6f8  call    cs:__imp_DbgPrintEx
0x14000b6ff  nop     dword ptr [rax+rax+00h]
0x14000b704  cmp     [rsp+48h+var_24], 0
0x14000b709  jge     short loc_14000B741
0x14000b70b  lea     rcx, SessionLock; FastMutex
0x14000b712  call    cs:__imp_ExReleaseFastMutex
0x14000b719  nop     dword ptr [rax+rax+00h]
0x14000b71e  lea     r8, aSessionNotFoun; "SESSION NOT FOUND!\n"
0x14000b725  mov     edx, 2; Level
0x14000b72a  mov     ecx, 8Eh; ComponentId
0x14000b72f  call    cs:__imp_DbgPrintEx
0x14000b736  nop     dword ptr [rax+rax+00h]
0x14000b73b  nop
0x14000b73c  jmp     loc_14000B7F8
0x14000b741  mov     [rsp+48h+var_28], 0
0x14000b749  jmp     short loc_14000B755
0x14000b74b  mov     eax, [rsp+48h+var_28]
0x14000b74f  inc     eax
0x14000b751  mov     [rsp+48h+var_28], eax
0x14000b755  cmp     [rsp+48h+var_28], 8
0x14000b75a  jge     short loc_14000B797
0x14000b75c  mov     eax, [rsp+48h+var_24]
0x14000b760  cmp     [rsp+48h+var_28], eax
0x14000b764  jz      short loc_14000B795
0x14000b766  movsxd  rax, [rsp+48h+var_28]
0x14000b76b  imul    rax, 28h ; '('
0x14000b76f  mov     rcx, cs:LogSessions
0x14000b776  add     rcx, rax
0x14000b779  mov     rax, rcx
0x14000b77c  mov     ecx, 4
0x14000b781  imul    rcx, 3
0x14000b785  mov     eax, [rax+rcx+14h]
0x14000b789  mov     ecx, [rsp+48h+var_20]
0x14000b78d  or      ecx, eax
0x14000b78f  mov     eax, ecx
0x14000b791  mov     [rsp+48h+var_20], eax
0x14000b795  jmp     short loc_14000B74B
0x14000b797  mov     r9d, [rsp+48h+var_20]
0x14000b79c  lea     r8, aActiveSessionF; "active session flags 0x%x\n"
0x14000b7a3  mov     edx, 2; Level
0x14000b7a8  mov     ecx, 8Eh; ComponentId
0x14000b7ad  call    cs:__imp_DbgPrintEx
0x14000b7b4  nop     dword ptr [rax+rax+00h]
0x14000b7b9  movsxd  rax, [rsp+48h+var_24]
0x14000b7be  imul    rax, 28h ; '('
0x14000b7c2  mov     rcx, cs:LogSessions
0x14000b7c9  add     rcx, rax
0x14000b7cc  mov     rax, rcx
0x14000b7cf  mov     rdi, rax
0x14000b7d2  xor     eax, eax
0x14000b7d4  mov     ecx, 28h ; '('
0x14000b7d9  rep stosb
0x14000b7db  lea     rcx, SessionLock; FastMutex
0x14000b7e2  call    cs:__imp_ExReleaseFastMutex
0x14000b7e9  nop     dword ptr [rax+rax+00h]
0x14000b7ee  mov     ecx, [rsp+48h+var_20]
0x14000b7f2  call    DetachFromDrives
0x14000b7f7  nop
0x14000b7f8  cmp     [rsp+48h+P], 0
0x14000b7fe  jz      short loc_14000B817
0x14000b800  mov     edx, 72744C46h; Tag
0x14000b805  mov     rcx, [rsp+48h+P]; P
0x14000b80a  call    cs:__imp_ExFreePoolWithTag
0x14000b811  nop     dword ptr [rax+rax+00h]
0x14000b816  nop
0x14000b817  mov     rcx, [rsp+48h+FltWorkItem]; FltWorkItem
0x14000b81c  call    cs:__imp_FltFreeGenericWorkItem
0x14000b823  nop     dword ptr [rax+rax+00h]
0x14000b828  nop
0x14000b829  add     rsp, 40h
0x14000b82d  pop     rdi
0x14000b82e  retn
```
