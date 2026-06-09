# CMDCOM::~CMDCOM(void)

- ea: `0x180015b44`
- end: `0x180015bae`
- name: `??1CMDCOM@@UEAA@XZ`
- size: `106`
- prototype: `void __fastcall(CMDCOM *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800158d0`
- `0x180015bc0`

## callees

- `0x180015b44`
- `0x180026b94`
- `0x180031010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180015b86`
- `KERNEL32!DeleteCriticalSection` at `0x180015b86`

## pseudocode

```c
void __fastcall CMDCOM::~CMDCOM(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 i; // rdi
  __int64 v3; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CMDCOM::`vftable';
  for ( i = 0; i != 2; ++i )
  {
    v3 = *(&this->SpinCount + i);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  if ( LODWORD(this[1].SpinCount) )
  {
    DeleteCriticalSection(this + 2);
    LODWORD(this[1].SpinCount) = 0;
  }
  TerminateOneTimeGlobals();
  *(_QWORD *)&this->LockCount = &CMDCOM::CImpIConnectionPointContainer::`vftable';
}

```

## disassembly

```asm
0x180015b44  mov     [rsp+arg_0], rbx
0x180015b49  push    rdi
0x180015b4a  sub     rsp, 20h
0x180015b4e  lea     rax, ??_7CMDCOM@@6B@; const CMDCOM::`vftable'
0x180015b55  mov     rbx, rcx
0x180015b58  mov     [rcx], rax
0x180015b5b  xor     edi, edi
0x180015b5d  mov     rcx, [rbx+rdi*8+20h]
0x180015b62  test    rcx, rcx
0x180015b65  jz      short loc_180015B73
0x180015b67  mov     rax, [rcx]
0x180015b6a  mov     rax, [rax+10h]
0x180015b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b73  inc     rdi
0x180015b76  cmp     rdi, 2
0x180015b7a  jnz     short loc_180015B5D
0x180015b7c  cmp     dword ptr [rbx+48h], 0
0x180015b80  jz      short loc_180015B93
0x180015b82  lea     rcx, [rbx+50h]; lpCriticalSection
0x180015b86  call    cs:__imp_DeleteCriticalSection
0x180015b8c  mov     dword ptr [rbx+48h], 0
0x180015b93  call    ?TerminateOneTimeGlobals@@YAXXZ; TerminateOneTimeGlobals(void)
0x180015b98  lea     rax, ??_7CImpIConnectionPointContainer@CMDCOM@@6B@; const CMDCOM::CImpIConnectionPointContainer::`vftable'
0x180015b9f  mov     [rbx+8], rax
0x180015ba3  mov     rbx, [rsp+28h+arg_0]
0x180015ba8  add     rsp, 20h
0x180015bac  pop     rdi
0x180015bad  retn
```
