# ATL::CRegObject::~CRegObject(void)

- ea: `0x180003018`
- end: `0x1800030b4`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037f0`
- `0x18000a7ac`
- `0x18000aacc`

## callees

- `0x180003018`
- `0x180004ab8`

## import_xrefs

- `msvcrt!free` at `0x180003079`
- `msvcrt!free` at `0x18000308f`
- `msvcrt!free` at `0x180003079`
- `msvcrt!free` at `0x18000308f`
- `KERNEL32!EnterCriticalSection` at `0x18000303b`
- `KERNEL32!EnterCriticalSection` at `0x18000303b`
- `KERNEL32!LeaveCriticalSection` at `0x180003050`
- `KERNEL32!LeaveCriticalSection` at `0x180003050`
- `KERNEL32!DeleteCriticalSection` at `0x180003063`
- `KERNEL32!DeleteCriticalSection` at `0x180003063`

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
0x180003018  mov     [rsp+arg_0], rbx
0x18000301d  mov     [rsp+arg_8], rsi
0x180003022  push    rdi
0x180003023  sub     rsp, 20h
0x180003027  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000302e  mov     rbx, rcx
0x180003031  lea     rsi, [rcx+20h]
0x180003035  mov     [rcx], rax
0x180003038  mov     rcx, rsi; lpCriticalSection
0x18000303b  call    cs:__imp_EnterCriticalSection
0x180003041  lea     rdi, [rbx+8]
0x180003045  mov     rcx, rdi; this
0x180003048  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000304d  mov     rcx, rsi; lpCriticalSection
0x180003050  call    cs:__imp_LeaveCriticalSection
0x180003056  cmp     byte ptr [rsi+28h], 0
0x18000305a  jz      short loc_180003069
0x18000305c  mov     rcx, rsi; lpCriticalSection
0x18000305f  mov     byte ptr [rsi+28h], 0
0x180003063  call    cs:__imp_DeleteCriticalSection
0x180003069  mov     rcx, rdi; this
0x18000306c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003071  mov     rcx, [rdi]; Block
0x180003074  test    rcx, rcx
0x180003077  jz      short loc_180003086
0x180003079  call    cs:__imp_free
0x18000307f  mov     qword ptr [rdi], 0
0x180003086  mov     rcx, [rbx+10h]; Block
0x18000308a  test    rcx, rcx
0x18000308d  jz      short loc_18000309D
0x18000308f  call    cs:__imp_free
0x180003095  mov     qword ptr [rbx+10h], 0
0x18000309d  mov     rsi, [rsp+28h+arg_8]
0x1800030a2  mov     dword ptr [rbx+18h], 0
0x1800030a9  mov     rbx, [rsp+28h+arg_0]
0x1800030ae  add     rsp, 20h
0x1800030b2  pop     rdi
0x1800030b3  retn
```
