# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002254`
- end: `0x1800022f0`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002470`
- `0x180005b1c`
- `0x180005e3c`

## callees

- `0x180002254`
- `0x1800039cc`

## import_xrefs

- `msvcrt!free` at `0x1800022b5`
- `msvcrt!free` at `0x1800022cb`
- `msvcrt!free` at `0x1800022b5`
- `msvcrt!free` at `0x1800022cb`
- `KERNEL32!EnterCriticalSection` at `0x180002277`
- `KERNEL32!EnterCriticalSection` at `0x180002277`
- `KERNEL32!LeaveCriticalSection` at `0x18000228c`
- `KERNEL32!LeaveCriticalSection` at `0x18000228c`
- `KERNEL32!DeleteCriticalSection` at `0x18000229f`
- `KERNEL32!DeleteCriticalSection` at `0x18000229f`

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
0x180002254  mov     [rsp+arg_0], rbx
0x180002259  mov     [rsp+arg_8], rsi
0x18000225e  push    rdi
0x18000225f  sub     rsp, 20h
0x180002263  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000226a  mov     rbx, rcx
0x18000226d  lea     rsi, [rcx+20h]
0x180002271  mov     [rcx], rax
0x180002274  mov     rcx, rsi; lpCriticalSection
0x180002277  call    cs:__imp_EnterCriticalSection
0x18000227d  lea     rdi, [rbx+8]
0x180002281  mov     rcx, rdi; this
0x180002284  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002289  mov     rcx, rsi; lpCriticalSection
0x18000228c  call    cs:__imp_LeaveCriticalSection
0x180002292  cmp     byte ptr [rsi+28h], 0
0x180002296  jz      short loc_1800022A5
0x180002298  mov     rcx, rsi; lpCriticalSection
0x18000229b  mov     byte ptr [rsi+28h], 0
0x18000229f  call    cs:__imp_DeleteCriticalSection
0x1800022a5  mov     rcx, rdi; this
0x1800022a8  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800022ad  mov     rcx, [rdi]; Block
0x1800022b0  test    rcx, rcx
0x1800022b3  jz      short loc_1800022C2
0x1800022b5  call    cs:__imp_free
0x1800022bb  mov     qword ptr [rdi], 0
0x1800022c2  mov     rcx, [rbx+10h]; Block
0x1800022c6  test    rcx, rcx
0x1800022c9  jz      short loc_1800022D9
0x1800022cb  call    cs:__imp_free
0x1800022d1  mov     qword ptr [rbx+10h], 0
0x1800022d9  mov     rsi, [rsp+28h+arg_8]
0x1800022de  mov     dword ptr [rbx+18h], 0
0x1800022e5  mov     rbx, [rsp+28h+arg_0]
0x1800022ea  add     rsp, 20h
0x1800022ee  pop     rdi
0x1800022ef  retn
```
