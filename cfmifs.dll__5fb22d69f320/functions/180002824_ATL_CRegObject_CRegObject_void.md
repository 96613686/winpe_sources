# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002824`
- end: `0x1800028c0`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800029b0`
- `0x18000547c`
- `0x18000579c`

## callees

- `0x180002824`
- `0x1800039a4`

## import_xrefs

- `msvcrt!free` at `0x180002885`
- `msvcrt!free` at `0x18000289b`
- `msvcrt!free` at `0x180002885`
- `msvcrt!free` at `0x18000289b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000285c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000285c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002847`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002847`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000286f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000286f`

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
0x180002824  mov     [rsp+arg_0], rbx
0x180002829  mov     [rsp+arg_8], rsi
0x18000282e  push    rdi
0x18000282f  sub     rsp, 20h
0x180002833  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000283a  mov     rbx, rcx
0x18000283d  lea     rsi, [rcx+20h]
0x180002841  mov     [rcx], rax
0x180002844  mov     rcx, rsi; lpCriticalSection
0x180002847  call    cs:__imp_EnterCriticalSection
0x18000284d  lea     rdi, [rbx+8]
0x180002851  mov     rcx, rdi; this
0x180002854  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002859  mov     rcx, rsi; lpCriticalSection
0x18000285c  call    cs:__imp_LeaveCriticalSection
0x180002862  cmp     byte ptr [rsi+28h], 0
0x180002866  jz      short loc_180002875
0x180002868  mov     rcx, rsi; lpCriticalSection
0x18000286b  mov     byte ptr [rsi+28h], 0
0x18000286f  call    cs:__imp_DeleteCriticalSection
0x180002875  mov     rcx, rdi; this
0x180002878  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000287d  mov     rcx, [rdi]; Block
0x180002880  test    rcx, rcx
0x180002883  jz      short loc_180002892
0x180002885  call    cs:__imp_free
0x18000288b  mov     qword ptr [rdi], 0
0x180002892  mov     rcx, [rbx+10h]; Block
0x180002896  test    rcx, rcx
0x180002899  jz      short loc_1800028A9
0x18000289b  call    cs:__imp_free
0x1800028a1  mov     qword ptr [rbx+10h], 0
0x1800028a9  mov     rsi, [rsp+28h+arg_8]
0x1800028ae  mov     dword ptr [rbx+18h], 0
0x1800028b5  mov     rbx, [rsp+28h+arg_0]
0x1800028ba  add     rsp, 20h
0x1800028be  pop     rdi
0x1800028bf  retn
```
