# ATL::CRegObject::~CRegObject(void)

- ea: `0x1800026bc`
- end: `0x180002758`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800027e0`
- `0x180004d04`

## callees

- `0x1800026bc`
- `0x180003774`

## import_xrefs

- `msvcrt!free` at `0x18000271d`
- `msvcrt!free` at `0x180002733`
- `msvcrt!free` at `0x18000271d`
- `msvcrt!free` at `0x180002733`
- `KERNEL32!EnterCriticalSection` at `0x1800026df`
- `KERNEL32!EnterCriticalSection` at `0x1800026df`
- `KERNEL32!LeaveCriticalSection` at `0x1800026f4`
- `KERNEL32!LeaveCriticalSection` at `0x1800026f4`
- `KERNEL32!DeleteCriticalSection` at `0x180002707`
- `KERNEL32!DeleteCriticalSection` at `0x180002707`

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
0x1800026bc  mov     [rsp+arg_0], rbx
0x1800026c1  mov     [rsp+arg_8], rsi
0x1800026c6  push    rdi
0x1800026c7  sub     rsp, 20h
0x1800026cb  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800026d2  mov     rbx, rcx
0x1800026d5  lea     rsi, [rcx+20h]
0x1800026d9  mov     [rcx], rax
0x1800026dc  mov     rcx, rsi; lpCriticalSection
0x1800026df  call    cs:__imp_EnterCriticalSection
0x1800026e5  lea     rdi, [rbx+8]
0x1800026e9  mov     rcx, rdi; this
0x1800026ec  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800026f1  mov     rcx, rsi; lpCriticalSection
0x1800026f4  call    cs:__imp_LeaveCriticalSection
0x1800026fa  cmp     byte ptr [rsi+28h], 0
0x1800026fe  jz      short loc_18000270D
0x180002700  mov     rcx, rsi; lpCriticalSection
0x180002703  mov     byte ptr [rsi+28h], 0
0x180002707  call    cs:__imp_DeleteCriticalSection
0x18000270d  mov     rcx, rdi; this
0x180002710  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002715  mov     rcx, [rdi]; Block
0x180002718  test    rcx, rcx
0x18000271b  jz      short loc_18000272A
0x18000271d  call    cs:__imp_free
0x180002723  mov     qword ptr [rdi], 0
0x18000272a  mov     rcx, [rbx+10h]; Block
0x18000272e  test    rcx, rcx
0x180002731  jz      short loc_180002741
0x180002733  call    cs:__imp_free
0x180002739  mov     qword ptr [rbx+10h], 0
0x180002741  mov     rsi, [rsp+28h+arg_8]
0x180002746  mov     dword ptr [rbx+18h], 0
0x18000274d  mov     rbx, [rsp+28h+arg_0]
0x180002752  add     rsp, 20h
0x180002756  pop     rdi
0x180002757  retn
```
