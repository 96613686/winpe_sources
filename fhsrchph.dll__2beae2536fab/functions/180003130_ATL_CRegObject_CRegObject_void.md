# ATL::CRegObject::~CRegObject(void)

- ea: `0x180003130`
- end: `0x1800031cc`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003390`
- `0x180006164`

## callees

- `0x180003130`
- `0x180003ed0`

## import_xrefs

- `msvcrt!free` at `0x180003191`
- `msvcrt!free` at `0x1800031a7`
- `msvcrt!free` at `0x180003191`
- `msvcrt!free` at `0x1800031a7`
- `KERNEL32!DeleteCriticalSection` at `0x18000317b`
- `KERNEL32!DeleteCriticalSection` at `0x18000317b`
- `KERNEL32!EnterCriticalSection` at `0x180003153`
- `KERNEL32!EnterCriticalSection` at `0x180003153`
- `KERNEL32!LeaveCriticalSection` at `0x180003168`
- `KERNEL32!LeaveCriticalSection` at `0x180003168`

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
0x180003130  mov     [rsp+arg_0], rbx
0x180003135  mov     [rsp+arg_8], rsi
0x18000313a  push    rdi
0x18000313b  sub     rsp, 20h
0x18000313f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180003146  mov     rbx, rcx
0x180003149  lea     rsi, [rcx+20h]
0x18000314d  mov     [rcx], rax
0x180003150  mov     rcx, rsi; lpCriticalSection
0x180003153  call    cs:__imp_EnterCriticalSection
0x180003159  lea     rdi, [rbx+8]
0x18000315d  mov     rcx, rdi; this
0x180003160  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003165  mov     rcx, rsi; lpCriticalSection
0x180003168  call    cs:__imp_LeaveCriticalSection
0x18000316e  cmp     byte ptr [rsi+28h], 0
0x180003172  jz      short loc_180003181
0x180003174  mov     rcx, rsi; lpCriticalSection
0x180003177  mov     byte ptr [rsi+28h], 0
0x18000317b  call    cs:__imp_DeleteCriticalSection
0x180003181  mov     rcx, rdi; this
0x180003184  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003189  mov     rcx, [rdi]; Block
0x18000318c  test    rcx, rcx
0x18000318f  jz      short loc_18000319E
0x180003191  call    cs:__imp_free
0x180003197  mov     qword ptr [rdi], 0
0x18000319e  mov     rcx, [rbx+10h]; Block
0x1800031a2  test    rcx, rcx
0x1800031a5  jz      short loc_1800031B5
0x1800031a7  call    cs:__imp_free
0x1800031ad  mov     qword ptr [rbx+10h], 0
0x1800031b5  mov     rsi, [rsp+28h+arg_8]
0x1800031ba  mov     dword ptr [rbx+18h], 0
0x1800031c1  mov     rbx, [rsp+28h+arg_0]
0x1800031c6  add     rsp, 20h
0x1800031ca  pop     rdi
0x1800031cb  retn
```
