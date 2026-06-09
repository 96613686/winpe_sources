# FveWorkerForwardProgress

- ea: `0x1400dfd00`
- end: `0x1400dff13`
- name: `FveWorkerForwardProgress`
- size: `531`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140022cd0`
- `0x14002b6e0`
- `0x14002d600`
- `0x1400dfd00`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400dfefd`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400dfefd`
- `ntoskrnl!KeReleaseMutex` at `0x1400dfda5`
- `ntoskrnl!KeReleaseMutex` at `0x1400dfeef`
- `ntoskrnl!KeReleaseMutex` at `0x1400dfda5`
- `ntoskrnl!KeReleaseMutex` at `0x1400dfeef`
- `ntoskrnl!KeSetPriorityThread` at `0x1400dfdde`
- `ntoskrnl!KeSetPriorityThread` at `0x1400dfdde`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1400dfe30`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1400dfe30`
- `ntoskrnl!KeSetEvent` at `0x1400dfd40`
- `ntoskrnl!KeSetEvent` at `0x1400dfd40`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400dfd29`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400dfdfe`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400dfd29`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400dfdfe`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfea9`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfed9`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfea9`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfed9`

## pseudocode

```c
void __fastcall FveWorkerForwardProgress(char *StartContext)
{
  NTSTATUS v2; // ebx
  __int64 v3; // rdx
  _QWORD *v4; // rcx
  __int64 v5; // rax
  struct _LIST_ENTRY *v6; // rbp
  void *v7; // rsi
  __int64 v8; // rbx
  PLIST_ENTRY v9; // rax
  ULONG_PTR p_Blink; // rbx
  void (__fastcall *v11)(_QWORD, ULONG_PTR); // rax

  v2 = KeWaitForSingleObject((PVOID)(*((_QWORD *)StartContext + 2) + 296LL), Executive, 0, 0, 0);
  KeSetEvent((PRKEVENT)(StartContext + 40), 0, 0);
  if ( v2 >= 0 )
  {
    v3 = *((_QWORD *)StartContext + 2);
    if ( *(_BYTE *)(*((unsigned int *)StartContext + 8) + *(_QWORD *)(v3 + 240)) )
    {
      KeReleaseMutex((PRKMUTEX)(v3 + 296), 0);
    }
    else
    {
      v4 = *(_QWORD **)(v3 + 256);
      if ( *v4 != v3 + 248 )
        __fastfail(3u);
      *((_QWORD *)StartContext + 1) = v4;
      *(_QWORD *)StartContext = v3 + 248;
      *v4 = StartContext;
      *(_QWORD *)(v3 + 256) = StartContext;
      ++*(_DWORD *)(*((_QWORD *)StartContext + 2) + 236LL);
      KeReleaseMutex((PRKMUTEX)(*((_QWORD *)StartContext + 2) + 296LL), 0);
      v5 = *((_QWORD *)StartContext + 2);
      v6 = (struct _LIST_ENTRY *)(*(_QWORD *)(v5 + 272) + 16LL * *((unsigned int *)StartContext + 8));
      v7 = (void *)(*(_QWORD *)(v5 + 280) + 32LL * *((unsigned int *)StartContext + 8));
      KeSetPriorityThread(KeGetCurrentThread(), 18);
      while ( 1 )
      {
        KeWaitForSingleObject(v7, Executive, 0, 0, 0);
        if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)StartContext + 2) + 240LL) + *((unsigned int *)StartContext + 8)) )
          break;
        v8 = *((_QWORD *)StartContext + 2);
        v9 = ExInterlockedRemoveHeadList(v6, (PKSPIN_LOCK)(v8 + 288));
        if ( !v9 )
          KeBugCheckEx(0x120u, 3u, v8 + 224, 0, 0);
        p_Blink = (ULONG_PTR)&v9[-11].Blink;
        if ( v9 == (PLIST_ENTRY)168 || !*(_QWORD *)(p_Blink + 16) )
          KeBugCheckEx(0x120u, 2u, (ULONG_PTR)&v9[-11].Blink, 0, 0);
        *(_QWORD *)(p_Blink + 8) = p_Blink;
        *(_QWORD *)p_Blink = p_Blink;
        FveWorkerWorkStart((ULONG_PTR)&v9[-11].Blink);
        do
        {
          v11 = *(void (__fastcall **)(_QWORD, ULONG_PTR))(p_Blink + 16);
          *(_BYTE *)(p_Blink + 96) = 1;
          v11(*((_QWORD *)StartContext + 2), p_Blink);
          *(_BYTE *)(p_Blink + 96) = 0;
        }
        while ( FveWorkerWorkComplete(*((PVOID *)StartContext + 2), p_Blink) );
      }
    }
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x1400dfd00  push    rbx
0x1400dfd02  push    rbp
0x1400dfd03  push    rsi
0x1400dfd04  push    rdi
0x1400dfd05  sub     rsp, 38h
0x1400dfd09  mov     rdi, rcx
0x1400dfd0c  mov     [rsp+58h+Timeout], 0; Timeout
0x1400dfd15  mov     rcx, [rcx+10h]
0x1400dfd19  mov     esi, 128h
0x1400dfd1e  add     rcx, rsi; Object
0x1400dfd21  xor     r9d, r9d; Alertable
0x1400dfd24  xor     r8d, r8d; WaitMode
0x1400dfd27  xor     edx, edx; WaitReason
0x1400dfd29  call    cs:__imp_KeWaitForSingleObject
0x1400dfd30  nop     dword ptr [rax+rax+00h]
0x1400dfd35  lea     rcx, [rdi+28h]; Event
0x1400dfd39  xor     r8d, r8d; Wait
0x1400dfd3c  xor     edx, edx; Increment
0x1400dfd3e  mov     ebx, eax
0x1400dfd40  call    cs:__imp_KeSetEvent
0x1400dfd47  nop     dword ptr [rax+rax+00h]
0x1400dfd4c  test    ebx, ebx
0x1400dfd4e  js      loc_1400DFEFB
0x1400dfd54  mov     rax, [rdi+10h]
0x1400dfd58  mov     rcx, [rax+0F0h]
0x1400dfd5f  mov     eax, [rdi+20h]
0x1400dfd62  mov     rdx, [rdi+10h]
0x1400dfd66  cmp     byte ptr [rax+rcx], 0
0x1400dfd6a  jnz     loc_1400DFEE6
0x1400dfd70  lea     rax, [rdx+0F8h]
0x1400dfd77  mov     rcx, [rax+8]
0x1400dfd7b  cmp     [rcx], rax
0x1400dfd7e  jnz     loc_1400DFEB6
0x1400dfd84  mov     [rdi+8], rcx
0x1400dfd88  xor     edx, edx; Wait
0x1400dfd8a  mov     [rdi], rax
0x1400dfd8d  mov     [rcx], rdi
0x1400dfd90  mov     [rax+8], rdi
0x1400dfd94  mov     rax, [rdi+10h]
0x1400dfd98  inc     dword ptr [rax+0ECh]
0x1400dfd9e  mov     rcx, [rdi+10h]
0x1400dfda2  add     rcx, rsi; Mutex
0x1400dfda5  call    cs:__imp_KeReleaseMutex
0x1400dfdac  nop     dword ptr [rax+rax+00h]
0x1400dfdb1  mov     esi, [rdi+20h]
0x1400dfdb4  mov     edx, 12h; Priority
0x1400dfdb9  mov     rax, [rdi+10h]
0x1400dfdbd  mov     ebp, esi
0x1400dfdbf  mov     rcx, gs:188h; Thread
0x1400dfdc8  shl     rbp, 4
0x1400dfdcc  shl     rsi, 5
0x1400dfdd0  add     rbp, [rax+110h]
0x1400dfdd7  add     rsi, [rax+118h]
0x1400dfdde  call    cs:__imp_KeSetPriorityThread
0x1400dfde5  nop     dword ptr [rax+rax+00h]
0x1400dfdea  xor     r9d, r9d; Alertable
0x1400dfded  mov     [rsp+58h+Timeout], 0; Timeout
0x1400dfdf6  xor     r8d, r8d; WaitMode
0x1400dfdf9  xor     edx, edx; WaitReason
0x1400dfdfb  mov     rcx, rsi; Object
0x1400dfdfe  call    cs:__imp_KeWaitForSingleObject
0x1400dfe05  nop     dword ptr [rax+rax+00h]
0x1400dfe0a  mov     rax, [rdi+10h]
0x1400dfe0e  mov     edx, [rdi+20h]
0x1400dfe11  mov     rcx, [rax+0F0h]
0x1400dfe18  cmp     byte ptr [rcx+rdx], 0
0x1400dfe1c  jnz     loc_1400DFEFB
0x1400dfe22  mov     rbx, [rdi+10h]
0x1400dfe26  mov     rcx, rbp; ListHead
0x1400dfe29  lea     rdx, [rbx+120h]; Lock
0x1400dfe30  call    cs:__imp_ExInterlockedRemoveHeadList
0x1400dfe37  nop     dword ptr [rax+rax+00h]
0x1400dfe3c  test    rax, rax
0x1400dfe3f  jz      short loc_1400DFEBD
0x1400dfe41  lea     rbx, [rax-0A8h]
0x1400dfe48  test    rbx, rbx
0x1400dfe4b  jz      short loc_1400DFE91
0x1400dfe4d  cmp     qword ptr [rbx+10h], 0
0x1400dfe52  jz      short loc_1400DFE91
0x1400dfe54  mov     rcx, rbx; BugCheckParameter2
0x1400dfe57  mov     [rbx+8], rbx
0x1400dfe5b  mov     [rbx], rbx
0x1400dfe5e  call    FveWorkerWorkStart
0x1400dfe63  mov     rax, [rbx+10h]
0x1400dfe67  mov     rdx, rbx
0x1400dfe6a  mov     byte ptr [rbx+60h], 1
0x1400dfe6e  mov     rcx, [rdi+10h]
0x1400dfe72  call    _guard_dispatch_icall
0x1400dfe77  mov     byte ptr [rbx+60h], 0
0x1400dfe7b  mov     rdx, rbx; BugCheckParameter2
0x1400dfe7e  mov     rcx, [rdi+10h]; Context
0x1400dfe82  call    FveWorkerWorkComplete
0x1400dfe87  test    al, al
0x1400dfe89  jz      loc_1400DFDEA
0x1400dfe8f  jmp     short loc_1400DFE63
0x1400dfe91  xor     r9d, r9d; BugCheckParameter3
0x1400dfe94  mov     [rsp+58h+Timeout], 0; BugCheckParameter4
0x1400dfe9d  mov     r8, rbx; BugCheckParameter2
0x1400dfea0  mov     ecx, 120h; BugCheckCode
0x1400dfea5  lea     edx, [r9+2]; BugCheckParameter1
0x1400dfea9  call    cs:__imp_KeBugCheckEx
0x1400dfeb6  mov     ecx, 3
0x1400dfebb  int     29h; Win8: RtlFailFast(ecx)
0x1400dfebd  xor     r9d, r9d; BugCheckParameter3
0x1400dfec0  mov     [rsp+58h+Timeout], 0; BugCheckParameter4
0x1400dfec9  lea     r8, [rbx+0E0h]; BugCheckParameter2
0x1400dfed0  mov     ecx, 120h; BugCheckCode
0x1400dfed5  lea     edx, [r9+3]; BugCheckParameter1
0x1400dfed9  call    cs:__imp_KeBugCheckEx
0x1400dfee6  lea     rcx, [rdx+128h]; Mutex
0x1400dfeed  xor     edx, edx; Wait
0x1400dfeef  call    cs:__imp_KeReleaseMutex
0x1400dfef6  nop     dword ptr [rax+rax+00h]
0x1400dfefb  xor     ecx, ecx; ExitStatus
0x1400dfefd  call    cs:__imp_PsTerminateSystemThread
0x1400dff04  nop     dword ptr [rax+rax+00h]
0x1400dff09  add     rsp, 38h
0x1400dff0d  pop     rdi
0x1400dff0e  pop     rsi
0x1400dff0f  pop     rbp
0x1400dff10  pop     rbx
0x1400dff11  retn
```
