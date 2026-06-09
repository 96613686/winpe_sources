# ATL::CRegObject::~CRegObject(void)

- ea: `0x14000c318`
- end: `0x14000c3b4`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c410`
- `0x14000e20c`
- `0x14000e534`

## callees

- `0x14000c318`
- `0x14000cc84`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000c33b`
- `KERNEL32!EnterCriticalSection` at `0x14000c33b`
- `KERNEL32!DeleteCriticalSection` at `0x14000c363`
- `KERNEL32!DeleteCriticalSection` at `0x14000c363`
- `KERNEL32!LeaveCriticalSection` at `0x14000c350`
- `KERNEL32!LeaveCriticalSection` at `0x14000c350`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c379`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c38f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c379`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c38f`

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
0x14000c318  mov     [rsp+arg_0], rbx
0x14000c31d  mov     [rsp+arg_8], rsi
0x14000c322  push    rdi
0x14000c323  sub     rsp, 20h
0x14000c327  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14000c32e  mov     rbx, rcx
0x14000c331  lea     rsi, [rcx+20h]
0x14000c335  mov     [rcx], rax
0x14000c338  mov     rcx, rsi; lpCriticalSection
0x14000c33b  call    cs:__imp_EnterCriticalSection
0x14000c341  lea     rdi, [rbx+8]
0x14000c345  mov     rcx, rdi; this
0x14000c348  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x14000c34d  mov     rcx, rsi; lpCriticalSection
0x14000c350  call    cs:__imp_LeaveCriticalSection
0x14000c356  cmp     byte ptr [rsi+28h], 0
0x14000c35a  jz      short loc_14000C369
0x14000c35c  mov     rcx, rsi; lpCriticalSection
0x14000c35f  mov     byte ptr [rsi+28h], 0
0x14000c363  call    cs:__imp_DeleteCriticalSection
0x14000c369  mov     rcx, rdi; this
0x14000c36c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x14000c371  mov     rcx, [rdi]; Block
0x14000c374  test    rcx, rcx
0x14000c377  jz      short loc_14000C386
0x14000c379  call    cs:__imp_free
0x14000c37f  mov     qword ptr [rdi], 0
0x14000c386  mov     rcx, [rbx+10h]; Block
0x14000c38a  test    rcx, rcx
0x14000c38d  jz      short loc_14000C39D
0x14000c38f  call    cs:__imp_free
0x14000c395  mov     qword ptr [rbx+10h], 0
0x14000c39d  mov     rsi, [rsp+28h+arg_8]
0x14000c3a2  mov     dword ptr [rbx+18h], 0
0x14000c3a9  mov     rbx, [rsp+28h+arg_0]
0x14000c3ae  add     rsp, 20h
0x14000c3b2  pop     rdi
0x14000c3b3  retn
```
