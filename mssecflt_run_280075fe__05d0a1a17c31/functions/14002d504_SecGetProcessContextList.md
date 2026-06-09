# SecGetProcessContextList

- ea: `0x14002d504`
- end: `0x14002d71d`
- name: `SecGetProcessContextList`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002f0fc`

## callees

- `0x140006754`
- `0x140006b6c`
- `0x140011650`
- `0x140021100`
- `0x140021280`
- `0x14002c47c`
- `0x14002c6b0`
- `0x14002d504`
- `0x14002e16c`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14002d574`
- `ntoskrnl!KeClearEvent` at `0x14002d574`
- `ntoskrnl!KeSetEvent` at `0x14002d6a6`
- `ntoskrnl!KeSetEvent` at `0x14002d6a6`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002d5ef`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002d5ef`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d5bc`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d6e3`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d5bc`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d6e3`

## pseudocode

```c
__int64 __fastcall SecGetProcessContextList(struct _SLIST_ENTRY ***a1, char a2)
{
  struct _SLIST_ENTRY *v2; // rdi
  struct _SLIST_ENTRY **v3; // rbx
  struct _SLIST_ENTRY *v4; // rsi
  int RunningProcesses; // r14d
  __int64 v8; // r14
  struct _SLIST_ENTRY *v9; // rcx
  PSLIST_ENTRY v10; // rax
  PSLIST_ENTRY v12; // [rsp+20h] [rbp-30h] BYREF
  struct _SLIST_ENTRY *v13; // [rsp+28h] [rbp-28h] BYREF
  PVOID Object; // [rsp+30h] [rbp-20h] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v16; // [rsp+40h] [rbp-10h] BYREF

  v2 = 0;
  v3 = 0;
  v15 = 0;
  v4 = 0;
  v16 = 0;
  v13 = 0;
  v12 = 0;
  Object = 0;
  _InterlockedIncrement((volatile signed __int32 *)SecProcessTable + 90);
  KeClearEvent((PRKEVENT)SecProcessTable + 14);
  RunningProcesses = MpGetRunningProcesses(&v15, &v16);
  if ( RunningProcesses >= 0 )
  {
    v8 = 0;
    if ( v16 )
    {
      while ( 1 )
      {
        if ( !*(_QWORD *)(v15 + 8 * v8) )
          goto LABEL_16;
        if ( Object )
        {
          ObfDereferenceObject(Object);
          Object = 0;
        }
        if ( v2 )
        {
          SecReleaseProcessContext(v2);
          v2 = 0;
          v12 = 0;
        }
        if ( PsLookupProcessByProcessId(*(HANDLE *)(v15 + 8 * v8), (PEPROCESS *)&Object) < 0 )
          goto LABEL_16;
        if ( (int)SecGetProcessContextByObject(Object, &v12) < 0
          && (!a2
           || (int)SecCreateProcessContext(*(struct _SLIST_ENTRY **)(v15 + 8 * v8), (struct _KPROCESS *)Object, 0, &v12) < 0) )
        {
          goto LABEL_15;
        }
        if ( (int)SecAllocateProcessContextListEntry(&v13) < 0 )
          break;
        v9 = v13;
        v2 = 0;
        v10 = v12;
        v4 = 0;
        v12 = 0;
        v13 = 0;
        v9[1].Next = v10;
        *((_QWORD *)&v9->Next + 1) = v3;
        v3 = &v9->Next + 1;
LABEL_16:
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= v16 )
          goto LABEL_17;
      }
      v4 = v13;
LABEL_15:
      v2 = v12;
      goto LABEL_16;
    }
LABEL_17:
    *a1 = v3;
    RunningProcesses = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)SecProcessTable + 90, 0xFFFFFFFF) == 1 )
    KeSetEvent((PRKEVENT)SecProcessTable + 14, 0, 0);
  if ( v15 )
    MpDeleteRunningProcesses();
  if ( v2 )
    SecReleaseProcessContext(v2);
  if ( v4 )
    SecReleaseProcessContextListEntry(v4);
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)RunningProcesses;
}

```

## disassembly

```asm
0x14002d504  mov     [rsp-28h+arg_8], rbx
0x14002d509  mov     [rsp-28h+arg_10], rsi
0x14002d50e  mov     [rsp-28h+arg_18], rdi
0x14002d513  push    rbp
0x14002d514  push    r12
0x14002d516  push    r13
0x14002d518  push    r14
0x14002d51a  push    r15
0x14002d51c  mov     rbp, rsp
0x14002d51f  sub     rsp, 50h
0x14002d523  mov     rax, cs:__security_cookie
0x14002d52a  xor     rax, rsp
0x14002d52d  mov     [rbp+var_8], rax
0x14002d531  mov     rax, cs:SecProcessTable
0x14002d538  xor     edi, edi
0x14002d53a  xor     ebx, ebx
0x14002d53c  mov     [rbp+var_18], 0
0x14002d544  xor     esi, esi
0x14002d546  mov     [rbp+var_10], 0
0x14002d54d  mov     [rbp+var_28], rsi
0x14002d551  mov     r13b, dl
0x14002d554  mov     r12, rcx
0x14002d557  mov     [rbp+var_30], rdi
0x14002d55b  mov     [rbp+Object], rbx
0x14002d55f  lock inc dword ptr [rax+168h]
0x14002d566  mov     rcx, cs:SecProcessTable
0x14002d56d  add     rcx, 150h; Event
0x14002d574  call    cs:__imp_KeClearEvent
0x14002d57b  nop     dword ptr [rax+rax+00h]
0x14002d580  lea     rdx, [rbp+var_10]
0x14002d584  lea     rcx, [rbp+var_18]
0x14002d588  call    MpGetRunningProcesses
0x14002d58d  mov     r14d, eax
0x14002d590  test    eax, eax
0x14002d592  js      loc_14002D67C
0x14002d598  xor     r14d, r14d
0x14002d59b  cmp     [rbp+var_10], ebx
0x14002d59e  jbe     loc_14002D675
0x14002d5a4  mov     rax, [rbp+var_18]
0x14002d5a8  cmp     qword ptr [rax+r14*8], 0
0x14002d5ad  jz      loc_14002D668
0x14002d5b3  mov     rcx, [rbp+Object]; Object
0x14002d5b7  test    rcx, rcx
0x14002d5ba  jz      short loc_14002D5D0
0x14002d5bc  call    cs:__imp_ObfDereferenceObject
0x14002d5c3  nop     dword ptr [rax+rax+00h]
0x14002d5c8  mov     [rbp+Object], 0
0x14002d5d0  test    rdi, rdi
0x14002d5d3  jz      short loc_14002D5E3
0x14002d5d5  mov     rcx, rdi; ListEntry
0x14002d5d8  call    SecReleaseProcessContext
0x14002d5dd  xor     edi, edi
0x14002d5df  mov     [rbp+var_30], rdi
0x14002d5e3  mov     rcx, [rbp+var_18]
0x14002d5e7  lea     rdx, [rbp+Object]; Process
0x14002d5eb  mov     rcx, [rcx+r14*8]; ProcessId
0x14002d5ef  call    cs:__imp_PsLookupProcessByProcessId
0x14002d5f6  nop     dword ptr [rax+rax+00h]
0x14002d5fb  test    eax, eax
0x14002d5fd  js      short loc_14002D668
0x14002d5ff  mov     rcx, [rbp+Object]
0x14002d603  lea     rdx, [rbp+var_30]
0x14002d607  call    SecGetProcessContextByObject
0x14002d60c  test    eax, eax
0x14002d60e  jns     short loc_14002D631
0x14002d610  test    r13b, r13b
0x14002d613  jz      short loc_14002D664
0x14002d615  mov     rcx, [rbp+var_18]
0x14002d619  lea     r9, [rbp+var_30]
0x14002d61d  mov     rdx, [rbp+Object]
0x14002d621  xor     r8d, r8d
0x14002d624  mov     rcx, [rcx+r14*8]
0x14002d628  call    SecCreateProcessContext
0x14002d62d  test    eax, eax
0x14002d62f  js      short loc_14002D664
0x14002d631  lea     rcx, [rbp+var_28]
0x14002d635  call    SecAllocateProcessContextListEntry
0x14002d63a  test    eax, eax
0x14002d63c  js      short loc_14002D660
0x14002d63e  mov     rcx, [rbp+var_28]
0x14002d642  xor     edi, edi
0x14002d644  mov     rax, [rbp+var_30]
0x14002d648  xor     esi, esi
0x14002d64a  mov     [rbp+var_30], rdi
0x14002d64e  mov     [rbp+var_28], rsi
0x14002d652  mov     [rcx+10h], rax
0x14002d656  mov     [rcx+8], rbx
0x14002d65a  lea     rbx, [rcx+8]
0x14002d65e  jmp     short loc_14002D668
0x14002d660  mov     rsi, [rbp+var_28]
0x14002d664  mov     rdi, [rbp+var_30]
0x14002d668  inc     r14d
0x14002d66b  cmp     r14d, [rbp+var_10]
0x14002d66f  jb      loc_14002D5A4
0x14002d675  mov     [r12], rbx
0x14002d679  xor     r14d, r14d
0x14002d67c  mov     rcx, cs:SecProcessTable
0x14002d683  or      eax, 0FFFFFFFFh
0x14002d686  lock xadd [rcx+168h], eax
0x14002d68e  cmp     eax, 1
0x14002d691  jnz     short loc_14002D6B2
0x14002d693  mov     rcx, cs:SecProcessTable
0x14002d69a  xor     r8d, r8d; Wait
0x14002d69d  add     rcx, 150h; Event
0x14002d6a4  xor     edx, edx; Increment
0x14002d6a6  call    cs:__imp_KeSetEvent
0x14002d6ad  nop     dword ptr [rax+rax+00h]
0x14002d6b2  mov     rcx, [rbp+var_18]
0x14002d6b6  test    rcx, rcx
0x14002d6b9  jz      short loc_14002D6C0
0x14002d6bb  call    MpDeleteRunningProcesses
0x14002d6c0  test    rdi, rdi
0x14002d6c3  jz      short loc_14002D6CD
0x14002d6c5  mov     rcx, rdi; ListEntry
0x14002d6c8  call    SecReleaseProcessContext
0x14002d6cd  test    rsi, rsi
0x14002d6d0  jz      short loc_14002D6DA
0x14002d6d2  mov     rcx, rsi; ListEntry
0x14002d6d5  call    SecReleaseProcessContextListEntry
0x14002d6da  mov     rcx, [rbp+Object]; Object
0x14002d6de  test    rcx, rcx
0x14002d6e1  jz      short loc_14002D6EF
0x14002d6e3  call    cs:__imp_ObfDereferenceObject
0x14002d6ea  nop     dword ptr [rax+rax+00h]
0x14002d6ef  mov     eax, r14d
0x14002d6f2  mov     rcx, [rbp+var_8]
0x14002d6f6  xor     rcx, rsp; StackCookie
0x14002d6f9  call    __security_check_cookie
0x14002d6fe  lea     r11, [rsp+50h+var_s0]
0x14002d703  mov     rbx, [r11+38h]
0x14002d707  mov     rsi, [r11+40h]
0x14002d70b  mov     rdi, [r11+48h]
0x14002d70f  mov     rsp, r11
0x14002d712  pop     r15
0x14002d714  pop     r14
0x14002d716  pop     r13
0x14002d718  pop     r12
0x14002d71a  pop     rbp
0x14002d71b  retn
```
