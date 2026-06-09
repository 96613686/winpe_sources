# ATL::CRegObject::~CRegObject(void)

- ea: `0x180004220`
- end: `0x1800042bc`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004350`
- `0x180006c60`

## callees

- `0x180004220`
- `0x1800056b0`

## import_xrefs

- `msvcrt!free` at `0x180004281`
- `msvcrt!free` at `0x180004297`
- `msvcrt!free` at `0x180004281`
- `msvcrt!free` at `0x180004297`
- `KERNEL32!EnterCriticalSection` at `0x180004243`
- `KERNEL32!EnterCriticalSection` at `0x180004243`
- `KERNEL32!DeleteCriticalSection` at `0x18000426b`
- `KERNEL32!DeleteCriticalSection` at `0x18000426b`
- `KERNEL32!LeaveCriticalSection` at `0x180004258`
- `KERNEL32!LeaveCriticalSection` at `0x180004258`

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
0x180004220  mov     [rsp+arg_0], rbx
0x180004225  mov     [rsp+arg_8], rsi
0x18000422a  push    rdi
0x18000422b  sub     rsp, 20h
0x18000422f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180004236  mov     rbx, rcx
0x180004239  lea     rsi, [rcx+20h]
0x18000423d  mov     [rcx], rax
0x180004240  mov     rcx, rsi; lpCriticalSection
0x180004243  call    cs:__imp_EnterCriticalSection
0x180004249  lea     rdi, [rbx+8]
0x18000424d  mov     rcx, rdi; this
0x180004250  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180004255  mov     rcx, rsi; lpCriticalSection
0x180004258  call    cs:__imp_LeaveCriticalSection
0x18000425e  cmp     byte ptr [rsi+28h], 0
0x180004262  jz      short loc_180004271
0x180004264  mov     rcx, rsi; lpCriticalSection
0x180004267  mov     byte ptr [rsi+28h], 0
0x18000426b  call    cs:__imp_DeleteCriticalSection
0x180004271  mov     rcx, rdi; this
0x180004274  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180004279  mov     rcx, [rdi]; Block
0x18000427c  test    rcx, rcx
0x18000427f  jz      short loc_18000428E
0x180004281  call    cs:__imp_free
0x180004287  mov     qword ptr [rdi], 0
0x18000428e  mov     rcx, [rbx+10h]; Block
0x180004292  test    rcx, rcx
0x180004295  jz      short loc_1800042A5
0x180004297  call    cs:__imp_free
0x18000429d  mov     qword ptr [rbx+10h], 0
0x1800042a5  mov     rsi, [rsp+28h+arg_8]
0x1800042aa  mov     dword ptr [rbx+18h], 0
0x1800042b1  mov     rbx, [rsp+28h+arg_0]
0x1800042b6  add     rsp, 20h
0x1800042ba  pop     rdi
0x1800042bb  retn
```
