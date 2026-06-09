# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002c04`
- end: `0x180002cbf`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `187`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d50`
- `0x18000596c`

## callees

- `0x180002c04`
- `0x1800041b4`

## import_xrefs

- `msvcrt!free` at `0x180002c77`
- `msvcrt!free` at `0x180002c93`
- `msvcrt!free` at `0x180002c77`
- `msvcrt!free` at `0x180002c93`
- `KERNEL32!LeaveCriticalSection` at `0x180002c42`
- `KERNEL32!LeaveCriticalSection` at `0x180002c42`
- `KERNEL32!EnterCriticalSection` at `0x180002c27`
- `KERNEL32!EnterCriticalSection` at `0x180002c27`
- `KERNEL32!DeleteCriticalSection` at `0x180002c5b`
- `KERNEL32!DeleteCriticalSection` at `0x180002c5b`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  void **v3; // rdi
  void *v4; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (void **)((char *)this + 8);
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  LeaveCriticalSection(v2);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  if ( *v3 )
  {
    free(*v3);
    *v3 = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x180002c04  mov     [rsp+arg_0], rbx
0x180002c09  mov     [rsp+arg_8], rsi
0x180002c0e  push    rdi
0x180002c0f  sub     rsp, 20h
0x180002c13  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180002c1a  mov     rbx, rcx
0x180002c1d  lea     rsi, [rcx+20h]
0x180002c21  mov     [rcx], rax
0x180002c24  mov     rcx, rsi; lpCriticalSection
0x180002c27  call    cs:__imp_EnterCriticalSection
0x180002c2e  nop     dword ptr [rax+rax+00h]
0x180002c33  lea     rdi, [rbx+8]
0x180002c37  mov     rcx, rdi; this
0x180002c3a  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002c3f  mov     rcx, rsi; lpCriticalSection
0x180002c42  call    cs:__imp_LeaveCriticalSection
0x180002c49  nop     dword ptr [rax+rax+00h]
0x180002c4e  cmp     byte ptr [rsi+28h], 0
0x180002c52  jz      short loc_180002C67
0x180002c54  mov     rcx, rsi; lpCriticalSection
0x180002c57  mov     byte ptr [rsi+28h], 0
0x180002c5b  call    cs:__imp_DeleteCriticalSection
0x180002c62  nop     dword ptr [rax+rax+00h]
0x180002c67  mov     rcx, rdi; this
0x180002c6a  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002c6f  mov     rcx, [rdi]; Block
0x180002c72  test    rcx, rcx
0x180002c75  jz      short loc_180002C8A
0x180002c77  call    cs:__imp_free
0x180002c7e  nop     dword ptr [rax+rax+00h]
0x180002c83  mov     qword ptr [rdi], 0
0x180002c8a  mov     rcx, [rbx+10h]; Block
0x180002c8e  test    rcx, rcx
0x180002c91  jz      short loc_180002CA7
0x180002c93  call    cs:__imp_free
0x180002c9a  nop     dword ptr [rax+rax+00h]
0x180002c9f  mov     qword ptr [rbx+10h], 0
0x180002ca7  mov     rsi, [rsp+28h+arg_8]
0x180002cac  mov     dword ptr [rbx+18h], 0
0x180002cb3  mov     rbx, [rsp+28h+arg_0]
0x180002cb8  add     rsp, 20h
0x180002cbc  pop     rdi
0x180002cbd  retn
```
