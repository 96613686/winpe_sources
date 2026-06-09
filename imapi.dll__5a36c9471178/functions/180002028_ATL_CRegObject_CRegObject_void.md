# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002028`
- end: `0x1800020c4`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002140`
- `0x1800043dc`
- `0x1800093cc`

## callees

- `0x180002028`
- `0x180002aec`

## import_xrefs

- `msvcrt!free` at `0x180002089`
- `msvcrt!free` at `0x18000209f`
- `msvcrt!free` at `0x180002089`
- `msvcrt!free` at `0x18000209f`
- `KERNEL32!DeleteCriticalSection` at `0x180002073`
- `KERNEL32!DeleteCriticalSection` at `0x180002073`
- `KERNEL32!LeaveCriticalSection` at `0x180002060`
- `KERNEL32!LeaveCriticalSection` at `0x180002060`
- `KERNEL32!EnterCriticalSection` at `0x18000204b`
- `KERNEL32!EnterCriticalSection` at `0x18000204b`

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
0x180002028  mov     [rsp+arg_0], rbx
0x18000202d  mov     [rsp+arg_8], rsi
0x180002032  push    rdi
0x180002033  sub     rsp, 20h
0x180002037  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000203e  mov     rbx, rcx
0x180002041  lea     rsi, [rcx+20h]
0x180002045  mov     [rcx], rax
0x180002048  mov     rcx, rsi; lpCriticalSection
0x18000204b  call    cs:__imp_EnterCriticalSection
0x180002051  lea     rdi, [rbx+8]
0x180002055  mov     rcx, rdi; this
0x180002058  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000205d  mov     rcx, rsi; lpCriticalSection
0x180002060  call    cs:__imp_LeaveCriticalSection
0x180002066  cmp     byte ptr [rsi+28h], 0
0x18000206a  jz      short loc_180002079
0x18000206c  mov     rcx, rsi; lpCriticalSection
0x18000206f  mov     byte ptr [rsi+28h], 0
0x180002073  call    cs:__imp_DeleteCriticalSection
0x180002079  mov     rcx, rdi; this
0x18000207c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002081  mov     rcx, [rdi]; Block
0x180002084  test    rcx, rcx
0x180002087  jz      short loc_180002096
0x180002089  call    cs:__imp_free
0x18000208f  mov     qword ptr [rdi], 0
0x180002096  mov     rcx, [rbx+10h]; Block
0x18000209a  test    rcx, rcx
0x18000209d  jz      short loc_1800020AD
0x18000209f  call    cs:__imp_free
0x1800020a5  mov     qword ptr [rbx+10h], 0
0x1800020ad  mov     rsi, [rsp+28h+arg_8]
0x1800020b2  mov     dword ptr [rbx+18h], 0
0x1800020b9  mov     rbx, [rsp+28h+arg_0]
0x1800020be  add     rsp, 20h
0x1800020c2  pop     rdi
0x1800020c3  retn
```
