# FveWorkerForwardProgress

- ea: `0x1400dce00`
- end: `0x1400dd013`
- name: `FveWorkerForwardProgress`
- size: `531`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400219a0`
- `0x14002a6e0`
- `0x14002c600`
- `0x1400dce00`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400dcffd`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400dcffd`
- `ntoskrnl!KeReleaseMutex` at `0x1400dcea5`
- `ntoskrnl!KeReleaseMutex` at `0x1400dcfef`
- `ntoskrnl!KeReleaseMutex` at `0x1400dcea5`
- `ntoskrnl!KeReleaseMutex` at `0x1400dcfef`
- `ntoskrnl!KeSetPriorityThread` at `0x1400dcede`
- `ntoskrnl!KeSetPriorityThread` at `0x1400dcede`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1400dcf30`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1400dcf30`
- `ntoskrnl!KeSetEvent` at `0x1400dce40`
- `ntoskrnl!KeSetEvent` at `0x1400dce40`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400dce29`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400dcefe`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400dce29`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400dcefe`
- `ntoskrnl!KeBugCheckEx` at `0x1400dcfa9`
- `ntoskrnl!KeBugCheckEx` at `0x1400dcfd9`
- `ntoskrnl!KeBugCheckEx` at `0x1400dcfa9`
- `ntoskrnl!KeBugCheckEx` at `0x1400dcfd9`

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
0x1400dce00  push    rbx
0x1400dce02  push    rbp
0x1400dce03  push    rsi
0x1400dce04  push    rdi
0x1400dce05  sub     rsp, 38h
0x1400dce09  mov     rdi, rcx
0x1400dce0c  mov     [rsp+58h+Timeout], 0; Timeout
0x1400dce15  mov     rcx, [rcx+10h]
0x1400dce19  mov     esi, 128h
0x1400dce1e  add     rcx, rsi; Object
0x1400dce21  xor     r9d, r9d; Alertable
0x1400dce24  xor     r8d, r8d; WaitMode
0x1400dce27  xor     edx, edx; WaitReason
0x1400dce29  call    cs:__imp_KeWaitForSingleObject
0x1400dce30  nop     dword ptr [rax+rax+00h]
0x1400dce35  lea     rcx, [rdi+28h]; Event
0x1400dce39  xor     r8d, r8d; Wait
0x1400dce3c  xor     edx, edx; Increment
0x1400dce3e  mov     ebx, eax
0x1400dce40  call    cs:__imp_KeSetEvent
0x1400dce47  nop     dword ptr [rax+rax+00h]
0x1400dce4c  test    ebx, ebx
0x1400dce4e  js      loc_1400DCFFB
0x1400dce54  mov     rax, [rdi+10h]
0x1400dce58  mov     rcx, [rax+0F0h]
0x1400dce5f  mov     eax, [rdi+20h]
0x1400dce62  mov     rdx, [rdi+10h]
0x1400dce66  cmp     byte ptr [rax+rcx], 0
0x1400dce6a  jnz     loc_1400DCFE6
0x1400dce70  lea     rax, [rdx+0F8h]
0x1400dce77  mov     rcx, [rax+8]
0x1400dce7b  cmp     [rcx], rax
0x1400dce7e  jnz     loc_1400DCFB6
0x1400dce84  mov     [rdi+8], rcx
0x1400dce88  xor     edx, edx; Wait
0x1400dce8a  mov     [rdi], rax
0x1400dce8d  mov     [rcx], rdi
0x1400dce90  mov     [rax+8], rdi
0x1400dce94  mov     rax, [rdi+10h]
0x1400dce98  inc     dword ptr [rax+0ECh]
0x1400dce9e  mov     rcx, [rdi+10h]
0x1400dcea2  add     rcx, rsi; Mutex
0x1400dcea5  call    cs:__imp_KeReleaseMutex
0x1400dceac  nop     dword ptr [rax+rax+00h]
0x1400dceb1  mov     esi, [rdi+20h]
0x1400dceb4  mov     edx, 12h; Priority
0x1400dceb9  mov     rax, [rdi+10h]
0x1400dcebd  mov     ebp, esi
0x1400dcebf  mov     rcx, gs:188h; Thread
0x1400dcec8  shl     rbp, 4
0x1400dcecc  shl     rsi, 5
0x1400dced0  add     rbp, [rax+110h]
0x1400dced7  add     rsi, [rax+118h]
0x1400dcede  call    cs:__imp_KeSetPriorityThread
0x1400dcee5  nop     dword ptr [rax+rax+00h]
0x1400dceea  xor     r9d, r9d; Alertable
0x1400dceed  mov     [rsp+58h+Timeout], 0; Timeout
0x1400dcef6  xor     r8d, r8d; WaitMode
0x1400dcef9  xor     edx, edx; WaitReason
0x1400dcefb  mov     rcx, rsi; Object
0x1400dcefe  call    cs:__imp_KeWaitForSingleObject
0x1400dcf05  nop     dword ptr [rax+rax+00h]
0x1400dcf0a  mov     rax, [rdi+10h]
0x1400dcf0e  mov     edx, [rdi+20h]
0x1400dcf11  mov     rcx, [rax+0F0h]
0x1400dcf18  cmp     byte ptr [rcx+rdx], 0
0x1400dcf1c  jnz     loc_1400DCFFB
0x1400dcf22  mov     rbx, [rdi+10h]
0x1400dcf26  mov     rcx, rbp; ListHead
0x1400dcf29  lea     rdx, [rbx+120h]; Lock
0x1400dcf30  call    cs:__imp_ExInterlockedRemoveHeadList
0x1400dcf37  nop     dword ptr [rax+rax+00h]
0x1400dcf3c  test    rax, rax
0x1400dcf3f  jz      short loc_1400DCFBD
0x1400dcf41  lea     rbx, [rax-0A8h]
0x1400dcf48  test    rbx, rbx
0x1400dcf4b  jz      short loc_1400DCF91
0x1400dcf4d  cmp     qword ptr [rbx+10h], 0
0x1400dcf52  jz      short loc_1400DCF91
0x1400dcf54  mov     rcx, rbx; BugCheckParameter2
0x1400dcf57  mov     [rbx+8], rbx
0x1400dcf5b  mov     [rbx], rbx
0x1400dcf5e  call    FveWorkerWorkStart
0x1400dcf63  mov     rax, [rbx+10h]
0x1400dcf67  mov     rdx, rbx
0x1400dcf6a  mov     byte ptr [rbx+60h], 1
0x1400dcf6e  mov     rcx, [rdi+10h]
0x1400dcf72  call    _guard_dispatch_icall
0x1400dcf77  mov     byte ptr [rbx+60h], 0
0x1400dcf7b  mov     rdx, rbx; BugCheckParameter2
0x1400dcf7e  mov     rcx, [rdi+10h]; Context
0x1400dcf82  call    FveWorkerWorkComplete
0x1400dcf87  test    al, al
0x1400dcf89  jz      loc_1400DCEEA
0x1400dcf8f  jmp     short loc_1400DCF63
0x1400dcf91  xor     r9d, r9d; BugCheckParameter3
0x1400dcf94  mov     [rsp+58h+Timeout], 0; BugCheckParameter4
0x1400dcf9d  mov     r8, rbx; BugCheckParameter2
0x1400dcfa0  mov     ecx, 120h; BugCheckCode
0x1400dcfa5  lea     edx, [r9+2]; BugCheckParameter1
0x1400dcfa9  call    cs:__imp_KeBugCheckEx
0x1400dcfb6  mov     ecx, 3
0x1400dcfbb  int     29h; Win8: RtlFailFast(ecx)
0x1400dcfbd  xor     r9d, r9d; BugCheckParameter3
0x1400dcfc0  mov     [rsp+58h+Timeout], 0; BugCheckParameter4
0x1400dcfc9  lea     r8, [rbx+0E0h]; BugCheckParameter2
0x1400dcfd0  mov     ecx, 120h; BugCheckCode
0x1400dcfd5  lea     edx, [r9+3]; BugCheckParameter1
0x1400dcfd9  call    cs:__imp_KeBugCheckEx
0x1400dcfe6  lea     rcx, [rdx+128h]; Mutex
0x1400dcfed  xor     edx, edx; Wait
0x1400dcfef  call    cs:__imp_KeReleaseMutex
0x1400dcff6  nop     dword ptr [rax+rax+00h]
0x1400dcffb  xor     ecx, ecx; ExitStatus
0x1400dcffd  call    cs:__imp_PsTerminateSystemThread
0x1400dd004  nop     dword ptr [rax+rax+00h]
0x1400dd009  add     rsp, 38h
0x1400dd00d  pop     rdi
0x1400dd00e  pop     rsi
0x1400dd00f  pop     rbp
0x1400dd010  pop     rbx
0x1400dd011  retn
```
