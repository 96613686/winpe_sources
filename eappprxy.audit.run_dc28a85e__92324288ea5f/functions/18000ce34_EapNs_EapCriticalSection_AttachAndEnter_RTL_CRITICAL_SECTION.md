# EapNs::EapCriticalSection::AttachAndEnter(_RTL_CRITICAL_SECTION *)

- ea: `0x18000ce34`
- end: `0x18000ce8b`
- name: `?AttachAndEnter@EapCriticalSection@EapNs@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z`
- size: `87`
- prototype: `void(EapNs::EapCriticalSection *__hidden this, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b8bc`
- `0x18000bd30`
- `0x18000bef4`
- `0x18000c280`
- `0x18000c720`
- `0x18000c7d0`
- `0x18000c88c`
- `0x18000cae8`

## callees

- `0x18000ce34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ce70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ce70`

## pseudocode

```c
void __fastcall EapNs::EapCriticalSection::AttachAndEnter(LPCRITICAL_SECTION *this, struct _RTL_CRITICAL_SECTION *a2)
{
  if ( *this && *this != a2 && *((_DWORD *)this + 2) )
  {
    do
      LeaveCriticalSection(*this);
    while ( (*((_DWORD *)this + 2))-- != 1 );
  }
  *this = a2;
  EnterCriticalSection(a2);
  ++*((_DWORD *)this + 2);
}

```

## disassembly

```asm
0x18000ce34  mov     [rsp+arg_0], rbx
0x18000ce39  push    rdi
0x18000ce3a  sub     rsp, 20h
0x18000ce3e  cmp     qword ptr [rcx], 0
0x18000ce42  mov     rdi, rdx
0x18000ce45  mov     rbx, rcx
0x18000ce48  jz      short loc_18000CE6A
0x18000ce4a  cmp     [rcx], rdx
0x18000ce4d  jz      short loc_18000CE6A
0x18000ce4f  cmp     dword ptr [rcx+8], 0
0x18000ce53  jbe     short loc_18000CE6A
0x18000ce55  mov     rcx, [rbx]; lpCriticalSection
0x18000ce58  call    cs:__imp_LeaveCriticalSection
0x18000ce5f  nop     dword ptr [rax+rax+00h]
0x18000ce64  sub     dword ptr [rbx+8], 1
0x18000ce68  jnz     short loc_18000CE55
0x18000ce6a  mov     rcx, rdi; lpCriticalSection
0x18000ce6d  mov     [rbx], rdi
0x18000ce70  call    cs:__imp_EnterCriticalSection
0x18000ce77  nop     dword ptr [rax+rax+00h]
0x18000ce7c  inc     dword ptr [rbx+8]
0x18000ce7f  mov     rbx, [rsp+28h+arg_0]
0x18000ce84  add     rsp, 20h
0x18000ce88  pop     rdi
0x18000ce89  retn
```
