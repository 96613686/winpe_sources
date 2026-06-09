# CArray<COwnerListFile>::~CArray<COwnerListFile>(void)

- ea: `0x180007700`
- end: `0x180007781`
- name: `??1?$CArray@VCOwnerListFile@@@@UEAA@XZ`
- size: `129`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007d70`
- `0x180009b34`
- `0x18000fc54`
- `0x180015560`
- `0x18001d38b`
- `0x18001d9ca`
- `0x18001df83`

## callees

- `0x180001534`
- `0x180007700`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007767`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007767`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000771e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000771e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000777a`

## pseudocode

```c
void __fastcall CArray<COwnerListFile>::~CArray<COwnerListFile>(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  void (__fastcall ***v3)(_QWORD, __int64); // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 32);
  *(_QWORD *)a1 = &CArray<CString>::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  v3 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 24);
  if ( v3 )
  {
    if ( *(v3 - 1) )
      (**v3)(v3, 3);
    else
      operator delete(v3 - 1, 8u);
  }
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
}

```

## disassembly

```asm
0x180007700  mov     [rsp+arg_0], rbx
0x180007705  push    rdi
0x180007706  sub     rsp, 20h
0x18000770a  lea     rax, ??_7?$CArray@VCString@@@@6B@; const CArray<CString>::`vftable'
0x180007711  mov     rbx, rcx
0x180007714  lea     rdi, [rcx+20h]
0x180007718  mov     [rcx], rax
0x18000771b  mov     rcx, rdi; lpCriticalSection
0x18000771e  call    cs:__imp_EnterCriticalSection
0x180007724  mov     rcx, [rbx+18h]
0x180007728  test    rcx, rcx
0x18000772b  jz      short loc_180007754
0x18000772d  cmp     qword ptr [rcx-8], 0
0x180007732  jz      short loc_180007746
0x180007734  mov     rax, [rcx]
0x180007737  mov     edx, 3
0x18000773c  mov     rax, [rax]
0x18000773f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007744  jmp     short loc_180007754
0x180007746  mov     edx, 8; unsigned __int64
0x18000774b  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18000774f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007754  mov     rcx, rdi; lpCriticalSection
0x180007757  mov     qword ptr [rbx+18h], 0
0x18000775f  mov     qword ptr [rbx+8], 0
0x180007767  call    cs:__imp_LeaveCriticalSection
0x18000776d  mov     rcx, rdi
0x180007770  mov     rbx, [rsp+28h+arg_0]
0x180007775  add     rsp, 20h
0x180007779  pop     rdi
0x18000777a  jmp     cs:__imp_DeleteCriticalSection
```
