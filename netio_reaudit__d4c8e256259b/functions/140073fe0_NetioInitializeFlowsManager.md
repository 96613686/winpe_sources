# NetioInitializeFlowsManager

- ea: `0x140073fe0`
- end: `0x14007418b`
- name: `NetioInitializeFlowsManager`
- size: `427`
- prototype: `__int64 __fastcall(PVOID DeferredContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14003e850`
- `0x14003ed58`
- `0x1400426c8`
- `0x140073fe0`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x140074076`
- `ntoskrnl!RtlDeleteHashTable` at `0x140074076`
- `ntoskrnl!KeInitializeDpc` at `0x14007411f`
- `ntoskrnl!KeInitializeDpc` at `0x14007415c`
- `ntoskrnl!KeInitializeDpc` at `0x14007411f`
- `ntoskrnl!KeInitializeDpc` at `0x14007415c`
- `ntoskrnl!RtlCreateHashTable` at `0x14007400e`
- `ntoskrnl!RtlCreateHashTable` at `0x14007400e`
- `ntoskrnl!KeInitializeTimerEx` at `0x140074102`
- `ntoskrnl!KeInitializeTimerEx` at `0x140074102`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400740d2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400740e9`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400740d2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400740e9`

## pseudocode

```c
__int64 __fastcall NetioInitializeFlowsManager(char *DeferredContext)
{
  struct _RTL_DYNAMIC_HASH_TABLE *v1; // rbx
  unsigned int v3; // eax
  ULONG v4; // edx
  __int64 result; // rax
  unsigned int v6; // ecx
  int v7; // eax
  __int64 LookasideList; // rax
  __int64 v9; // rax
  int v10; // [rsp+20h] [rbp-38h]
  int v11; // [rsp+20h] [rbp-38h]
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+60h] [rbp+8h] BYREF

  v1 = (struct _RTL_DYNAMIC_HASH_TABLE *)(DeferredContext + 16);
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)(DeferredContext + 16);
  v3 = 2;
  v4 = 0;
  do
  {
    ++v4;
    v3 >>= 1;
  }
  while ( v3 );
  *((_DWORD *)DeferredContext + 14) = v4;
  if ( !RtlCreateHashTable(&HashTable, v4, 0) )
    return 3221225473LL;
  v6 = 1;
  v7 = 0;
  do
  {
    ++v7;
    v6 >>= 1;
  }
  while ( v6 );
  *((_DWORD *)DeferredContext + 22) = v7;
  *((_QWORD *)DeferredContext + 10) = 0;
  LookasideList = PplCreateLookasideList(0, v10, 0xF0u, 0x6634764Eu, 0, 0x6634764Eu);
  *((_QWORD *)DeferredContext + 236) = LookasideList;
  if ( !LookasideList )
    goto LABEL_8;
  v9 = PplCreateLookasideList(0, v11, 0x108u, 0x6636764Eu, 0, 0x6636764Eu);
  *((_QWORD *)DeferredContext + 237) = v9;
  if ( !v9 )
  {
    PplDestroyLookasideList(*((PVOID *)DeferredContext + 236), 0x6634764Eu);
LABEL_8:
    RtlDeleteHashTable(v1);
    return 3221225495LL;
  }
  KeInitializeSpinLock((PKSPIN_LOCK)DeferredContext);
  *((_DWORD *)DeferredContext + 2) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)DeferredContext + 8);
  *((_DWORD *)DeferredContext + 18) = 0;
  KeInitializeTimerEx((PKTIMER)(DeferredContext + 96), NotificationTimer);
  KeInitializeDpc((PRKDPC)(DeferredContext + 160), NetioFlowsManagerTimerCallback, DeferredContext);
  RtlInitializeTimerWheel(DeferredContext + 296, 0);
  KeInitializeDpc((PRKDPC)(DeferredContext + 224), NetioFlowsManagerTimerCallback, DeferredContext);
  result = 0;
  *((_QWORD *)DeferredContext + 238) = 0;
  *((_DWORD *)DeferredContext + 478) = 0;
  return result;
}

```

## disassembly

```asm
0x140073fe0  mov     [rsp+arg_8], rbx
0x140073fe5  push    rdi
0x140073fe6  sub     rsp, 50h
0x140073fea  lea     rbx, [rcx+10h]
0x140073fee  mov     rdi, rcx
0x140073ff1  mov     [rsp+58h+HashTable], rbx
0x140073ff6  mov     eax, 2
0x140073ffb  xor     edx, edx
0x140073ffd  inc     edx; Shift
0x140073fff  shr     eax, 1
0x140074001  jnz     short loc_140073FFD
0x140074003  mov     [rcx+38h], edx
0x140074006  xor     r8d, r8d; Flags
0x140074009  lea     rcx, [rsp+58h+HashTable]; HashTable
0x14007400e  call    cs:__imp_RtlCreateHashTable
0x140074015  nop     dword ptr [rax+rax+00h]
0x14007401a  test    al, al
0x14007401c  jnz     short loc_140074028
0x14007401e  mov     eax, 0C0000001h
0x140074023  jmp     loc_14007417F
0x140074028  mov     ecx, 1
0x14007402d  xor     eax, eax
0x14007402f  inc     eax
0x140074031  shr     ecx, 1
0x140074033  jnz     short loc_14007402F
0x140074035  mov     [rsp+58h+var_18], 6634764Eh; ULONG
0x14007403d  xor     ecx, ecx; int
0x14007403f  mov     [rdi+58h], eax
0x140074042  xor     eax, eax
0x140074044  mov     [rsp+58h+var_20], ax; __int16
0x140074049  mov     [rsp+58h+var_28], 6634764Eh; ULONG
0x140074051  mov     [rsp+58h+var_30], 0F0h; SIZE_T
0x14007405a  mov     qword ptr [rdi+50h], 0
0x140074062  call    PplCreateLookasideList
0x140074067  mov     [rdi+760h], rax
0x14007406e  test    rax, rax
0x140074071  jnz     short loc_14007408C
0x140074073  mov     rcx, rbx; HashTable
0x140074076  call    cs:__imp_RtlDeleteHashTable
0x14007407d  nop     dword ptr [rax+rax+00h]
0x140074082  mov     eax, 0C0000017h
0x140074087  jmp     loc_14007417F
0x14007408c  mov     ecx, 6636764Eh
0x140074091  xor     eax, eax
0x140074093  mov     [rsp+58h+var_18], ecx; ULONG
0x140074097  mov     [rsp+58h+var_20], ax; __int16
0x14007409c  mov     [rsp+58h+var_28], ecx; ULONG
0x1400740a0  xor     ecx, ecx; int
0x1400740a2  mov     [rsp+58h+var_30], 108h; SIZE_T
0x1400740ab  call    PplCreateLookasideList
0x1400740b0  mov     [rdi+768h], rax
0x1400740b7  test    rax, rax
0x1400740ba  jnz     short loc_1400740CF
0x1400740bc  mov     rcx, [rdi+760h]; P
0x1400740c3  mov     edx, 6634764Eh; Tag
0x1400740c8  call    PplDestroyLookasideList
0x1400740cd  jmp     short loc_140074073
0x1400740cf  mov     rcx, rdi; SpinLock
0x1400740d2  call    cs:__imp_KeInitializeSpinLock
0x1400740d9  nop     dword ptr [rax+rax+00h]
0x1400740de  lea     rcx, [rdi+40h]; SpinLock
0x1400740e2  mov     dword ptr [rdi+8], 0
0x1400740e9  call    cs:__imp_KeInitializeSpinLock
0x1400740f0  nop     dword ptr [rax+rax+00h]
0x1400740f5  lea     rcx, [rdi+60h]; Timer
0x1400740f9  mov     dword ptr [rdi+48h], 0
0x140074100  xor     edx, edx; Type
0x140074102  call    cs:__imp_KeInitializeTimerEx
0x140074109  nop     dword ptr [rax+rax+00h]
0x14007410e  lea     rcx, [rdi+0A0h]; Dpc
0x140074115  mov     r8, rdi; DeferredContext
0x140074118  lea     rdx, NetioFlowsManagerTimerCallback; DeferredRoutine
0x14007411f  call    cs:__imp_KeInitializeDpc
0x140074126  nop     dword ptr [rax+rax+00h]
0x14007412b  mov     edx, 40h ; '@'
0x140074130  mov     [rsp+58h+var_38], 0; int
0x140074138  lea     rcx, [rdi+128h]; void *
0x14007413f  lea     r9d, [rdx-3Fh]
0x140074143  mov     r8d, r9d
0x140074146  call    RtlInitializeTimerWheel
0x14007414b  lea     rcx, [rdi+0E0h]; Dpc
0x140074152  mov     r8, rdi; DeferredContext
0x140074155  lea     rdx, NetioFlowsManagerTimerCallback; DeferredRoutine
0x14007415c  call    cs:__imp_KeInitializeDpc
0x140074163  nop     dword ptr [rax+rax+00h]
0x140074168  xor     eax, eax
0x14007416a  mov     qword ptr [rdi+770h], 0
0x140074175  mov     dword ptr [rdi+778h], 0
0x14007417f  mov     rbx, [rsp+58h+arg_8]
0x140074184  add     rsp, 50h
0x140074188  pop     rdi
0x140074189  retn
```
