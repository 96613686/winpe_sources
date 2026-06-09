# UfhShortcutListenerCreate(void * *,ulong (*)(void))

- ea: `0x1800f0fe0`
- end: `0x1800f111f`
- name: `?UfhShortcutListenerCreate@@YAKPEAPEAXP6AKXZ@Z`
- size: `319`
- prototype: `unsigned int __fastcall(void **, unsigned int (*)(void))`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b2d90`

## callees

- `0x180040fa8`
- `0x1800f0fe0`
- `0x1800f1128`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800f10a7`
- `ntdll!RtlFreeHeap` at `0x1800f10c4`
- `ntdll!RtlFreeHeap` at `0x1800f10a7`
- `ntdll!RtlFreeHeap` at `0x1800f10c4`
- `ntdll!RtlAllocateHeap` at `0x1800f102b`
- `ntdll!RtlAllocateHeap` at `0x1800f102b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f106e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f106e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f107c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f107c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800f1102`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800f1102`

## pseudocode

```c
__int64 __fastcall UfhShortcutListenerCreate(void **a1, unsigned int (*a2)(void))
{
  void *v3; // r14
  DWORD LastError; // ebx
  struct _ACL *v5; // rsi
  _QWORD *Heap; // rdi
  DWORD SecurityDescAllowAccessToWorld; // eax
  HANDLE v8; // rax
  HANDLE Thread; // rax
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-20h] BYREF
  struct _ACL *v12; // [rsp+88h] [rbp+38h] BYREF
  void *v13; // [rsp+90h] [rbp+40h] BYREF

  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v3 = 0;
  LastError = 8;
  v13 = 0;
  v5 = 0;
  v12 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20u);
  if ( Heap )
  {
    SecurityDescAllowAccessToWorld = UfhpUtilityAllocGetSecurityDescAllowAccessToWorld(&v13, &v12);
    v3 = v13;
    LastError = SecurityDescAllowAccessToWorld;
    if ( !SecurityDescAllowAccessToWorld )
    {
      EventAttributes.nLength = 24;
      EventAttributes.lpSecurityDescriptor = v13;
      EventAttributes.bInheritHandle = 0;
      v8 = CreateEventW(&EventAttributes, 0, 0, L"Global\\UFH_{DC27E4C7-C59E-4710-927B-9F9C958092B1}");
      *Heap = v8;
      if ( v8 )
      {
        Heap[2] = StartScreenFilter_NewShortcutCallback;
        Thread = CreateThread(0, 0, UfhpShortcutListenerThread, Heap, 0, 0);
        Heap[1] = Thread;
        if ( Thread )
        {
          *a1 = Heap;
          LastError = 0;
          goto LABEL_6;
        }
      }
      LastError = GetLastError();
    }
    UfhShortcutListenerDelete(Heap);
LABEL_6:
    v5 = v12;
  }
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  return LastError;
}

```

## disassembly

```asm
0x1800f0fe0  mov     [rsp-28h+arg_0], rbx
0x1800f0fe5  mov     [rsp-28h+arg_8], rdx
0x1800f0fea  push    rbp
0x1800f0feb  push    rsi
0x1800f0fec  push    rdi
0x1800f0fed  push    r14
0x1800f0fef  push    r15
0x1800f0ff1  mov     rbp, rsp
0x1800f0ff4  sub     rsp, 50h
0x1800f0ff8  xor     eax, eax
0x1800f0ffa  mov     r15, rcx
0x1800f0ffd  mov     qword ptr [rbp+EventAttributes.bInheritHandle], rax
0x1800f1001  xorps   xmm0, xmm0
0x1800f1004  movups  xmmword ptr [rbp+EventAttributes.nLength], xmm0
0x1800f1008  mov     rcx, gs:60h
0x1800f1011  xor     r14d, r14d
0x1800f1014  lea     ebx, [rax+8]
0x1800f1017  mov     [rbp+arg_10], r14
0x1800f101b  xor     esi, esi
0x1800f101d  mov     edx, ebx; Flags
0x1800f101f  mov     [rbp+arg_8], rsi
0x1800f1023  mov     rcx, [rcx+30h]; HeapHandle
0x1800f1027  lea     r8d, [r14+20h]; Size
0x1800f102b  call    cs:__imp_RtlAllocateHeap
0x1800f1031  mov     rdi, rax
0x1800f1034  test    rax, rax
0x1800f1037  jz      short loc_1800F1090
0x1800f1039  lea     rdx, [rbp+arg_8]; struct _ACL **
0x1800f103d  lea     rcx, [rbp+arg_10]; void **
0x1800f1041  call    ?UfhpUtilityAllocGetSecurityDescAllowAccessToWorld@@YAKPEAPEAXPEAPEAU_ACL@@@Z; UfhpUtilityAllocGetSecurityDescAllowAccessToWorld(void * *,_ACL * *)
0x1800f1046  mov     r14, [rbp+arg_10]
0x1800f104a  mov     ebx, eax
0x1800f104c  test    eax, eax
0x1800f104e  jnz     short loc_1800F1084
0x1800f1050  lea     r9, Name; "Global\\UFH_{DC27E4C7-C59E-4710-927B-9F"...
0x1800f1057  mov     [rbp+EventAttributes.nLength], 18h
0x1800f105e  xor     r8d, r8d; bInitialState
0x1800f1061  mov     [rbp+EventAttributes.lpSecurityDescriptor], r14
0x1800f1065  xor     edx, edx; bManualReset
0x1800f1067  mov     [rbp+EventAttributes.bInheritHandle], esi
0x1800f106a  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x1800f106e  call    cs:__imp_CreateEventW
0x1800f1074  mov     [rdi], rax
0x1800f1077  test    rax, rax
0x1800f107a  jnz     short loc_1800F10E0
0x1800f107c  call    cs:__imp_GetLastError
0x1800f1082  mov     ebx, eax
0x1800f1084  mov     rcx, rdi; void *
0x1800f1087  call    ?UfhShortcutListenerDelete@@YAXPEAX@Z; UfhShortcutListenerDelete(void *)
0x1800f108c  mov     rsi, [rbp+arg_8]
0x1800f1090  test    rsi, rsi
0x1800f1093  jz      short loc_1800F10AD
0x1800f1095  mov     rcx, gs:60h
0x1800f109e  mov     r8, rsi; P
0x1800f10a1  xor     edx, edx; Flags
0x1800f10a3  mov     rcx, [rcx+30h]; HeapHandle
0x1800f10a7  call    cs:__imp_RtlFreeHeap
0x1800f10ad  test    r14, r14
0x1800f10b0  jz      short loc_1800F10CA
0x1800f10b2  mov     rcx, gs:60h
0x1800f10bb  mov     r8, r14; P
0x1800f10be  xor     edx, edx; Flags
0x1800f10c0  mov     rcx, [rcx+30h]; HeapHandle
0x1800f10c4  call    cs:__imp_RtlFreeHeap
0x1800f10ca  mov     eax, ebx
0x1800f10cc  mov     rbx, [rsp+50h+arg_0]
0x1800f10d4  add     rsp, 50h
0x1800f10d8  pop     r15
0x1800f10da  pop     r14
0x1800f10dc  pop     rdi
0x1800f10dd  pop     rsi
0x1800f10de  pop     rbp
0x1800f10df  retn
0x1800f10e0  lea     rax, ?StartScreenFilter_NewShortcutCallback@@YAKXZ; StartScreenFilter_NewShortcutCallback(void)
0x1800f10e7  mov     [rsp+50h+lpThreadId], rsi; lpThreadId
0x1800f10ec  mov     r9, rdi; lpParameter
0x1800f10ef  mov     [rdi+10h], rax
0x1800f10f3  lea     r8, ?UfhpShortcutListenerThread@@YAKPEAX@Z; lpStartAddress
0x1800f10fa  mov     [rsp+50h+dwCreationFlags], esi; dwCreationFlags
0x1800f10fe  xor     edx, edx; dwStackSize
0x1800f1100  xor     ecx, ecx; lpThreadAttributes
0x1800f1102  call    cs:__imp_CreateThread
0x1800f1108  mov     [rdi+8], rax
0x1800f110c  test    rax, rax
0x1800f110f  jz      loc_1800F107C
0x1800f1115  mov     [r15], rdi
0x1800f1118  xor     ebx, ebx
0x1800f111a  jmp     loc_1800F108C
```
