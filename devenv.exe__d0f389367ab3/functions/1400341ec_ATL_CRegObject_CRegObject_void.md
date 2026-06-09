# ATL::CRegObject::~CRegObject(void)

- ea: `0x1400341ec`
- end: `0x140034276`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `138`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140033d78`
- `0x1400340e0`
- `0x14003639c`

## callees

- `0x140034114`
- `0x1400341ec`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14003422f`
- `KERNEL32!DeleteCriticalSection` at `0x14003422f`
- `KERNEL32!EnterCriticalSection` at `0x14003420a`
- `KERNEL32!EnterCriticalSection` at `0x14003420a`
- `KERNEL32!LeaveCriticalSection` at `0x14003421c`
- `KERNEL32!LeaveCriticalSection` at `0x14003421c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140034248`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14003425c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140034248`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14003425c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  LeaveCriticalSection(v2);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    free(v3);
    *((_QWORD *)this + 1) = 0;
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
0x1400341ec  mov     [rsp+arg_0], rbx
0x1400341f1  push    rdi
0x1400341f2  sub     rsp, 20h
0x1400341f6  mov     rbx, rcx
0x1400341f9  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x140034200  mov     [rcx], rax
0x140034203  lea     rdi, [rcx+20h]
0x140034207  mov     rcx, rdi; lpCriticalSection
0x14003420a  call    cs:__imp_EnterCriticalSection
0x140034210  lea     rcx, [rbx+8]; this
0x140034214  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140034219  mov     rcx, rdi; lpCriticalSection
0x14003421c  call    cs:__imp_LeaveCriticalSection
0x140034222  cmp     byte ptr [rdi+28h], 0
0x140034226  jz      short loc_140034236
0x140034228  mov     byte ptr [rdi+28h], 0
0x14003422c  mov     rcx, rdi; lpCriticalSection
0x14003422f  call    cs:__imp_DeleteCriticalSection
0x140034235  nop
0x140034236  lea     rcx, [rbx+8]; this
0x14003423a  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x14003423f  mov     rcx, [rbx+8]; Block
0x140034243  test    rcx, rcx
0x140034246  jz      short loc_140034253
0x140034248  call    cs:__imp_free
0x14003424e  and     qword ptr [rbx+8], 0
0x140034253  mov     rcx, [rbx+10h]; Block
0x140034257  test    rcx, rcx
0x14003425a  jz      short loc_140034267
0x14003425c  call    cs:__imp_free
0x140034262  and     qword ptr [rbx+10h], 0
0x140034267  and     dword ptr [rbx+18h], 0
0x14003426b  mov     rbx, [rsp+28h+arg_0]
0x140034270  add     rsp, 20h
0x140034274  pop     rdi
0x140034275  retn
```
