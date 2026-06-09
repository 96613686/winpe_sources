# CAssociationCallback::OnRemoveCompleteCommon(int,long)

- ea: `0x140017f70`
- end: `0x140017fbe`
- name: `?OnRemoveCompleteCommon@CAssociationCallback@@IEAAJHJ@Z`
- size: `78`
- prototype: `__int64 __fastcall(void **this, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140017f60`
- `0x140017fd0`

## callees

- `0x14000bacc`
- `0x140017f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017fad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017fad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017f88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017f88`

## pseudocode

```c
__int64 __fastcall CAssociationCallback::OnRemoveCompleteCommon(void **this, int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)(this + 14);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 14));
  if ( *((_DWORD *)this + 26) )
    v7 = OnRemoveCompleteStub(a2, a3, this[4]);
  else
    v7 = -2140930029;
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x140017f70  push    rbx
0x140017f72  push    rbp
0x140017f73  push    rsi
0x140017f74  push    rdi
0x140017f75  sub     rsp, 28h
0x140017f79  lea     rdi, [rcx+70h]
0x140017f7d  mov     rbx, rcx
0x140017f80  mov     rcx, rdi; lpCriticalSection
0x140017f83  mov     esi, r8d
0x140017f86  mov     ebp, edx
0x140017f88  call    cs:__imp_EnterCriticalSection
0x140017f8e  cmp     dword ptr [rbx+68h], 0
0x140017f92  jz      short loc_140017FA5
0x140017f94  mov     r8, [rbx+20h]; void *
0x140017f98  mov     edx, esi; int
0x140017f9a  mov     ecx, ebp; int
0x140017f9c  call    ?OnRemoveCompleteStub@@YAJHJPEAX@Z; OnRemoveCompleteStub(int,long,void *)
0x140017fa1  mov     ebx, eax
0x140017fa3  jmp     short loc_140017FAA
0x140017fa5  mov     ebx, 80640013h
0x140017faa  mov     rcx, rdi; lpCriticalSection
0x140017fad  call    cs:__imp_LeaveCriticalSection
0x140017fb3  mov     eax, ebx
0x140017fb5  add     rsp, 28h
0x140017fb9  pop     rdi
0x140017fba  pop     rsi
0x140017fbb  pop     rbp
0x140017fbc  pop     rbx
0x140017fbd  retn
```
