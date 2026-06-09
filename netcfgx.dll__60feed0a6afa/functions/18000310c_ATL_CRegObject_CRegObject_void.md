# ATL::CRegObject::~CRegObject(void)

- ea: `0x18000310c`
- end: `0x1800031a8`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032e0`
- `0x180005d2c`
- `0x180006054`

## callees

- `0x18000310c`
- `0x180003ed8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000316d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003183`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000316d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003183`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003157`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003144`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003144`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000312f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000312f`

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
0x18000310c  mov     [rsp+arg_0], rbx
0x180003111  mov     [rsp+arg_8], rsi
0x180003116  push    rdi
0x180003117  sub     rsp, 20h
0x18000311b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180003122  mov     rbx, rcx
0x180003125  lea     rsi, [rcx+20h]
0x180003129  mov     [rcx], rax
0x18000312c  mov     rcx, rsi; lpCriticalSection
0x18000312f  call    cs:__imp_EnterCriticalSection
0x180003135  lea     rdi, [rbx+8]
0x180003139  mov     rcx, rdi; this
0x18000313c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003141  mov     rcx, rsi; lpCriticalSection
0x180003144  call    cs:__imp_LeaveCriticalSection
0x18000314a  cmp     byte ptr [rsi+28h], 0
0x18000314e  jz      short loc_18000315D
0x180003150  mov     rcx, rsi; lpCriticalSection
0x180003153  mov     byte ptr [rsi+28h], 0
0x180003157  call    cs:__imp_DeleteCriticalSection
0x18000315d  mov     rcx, rdi; this
0x180003160  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003165  mov     rcx, [rdi]; Block
0x180003168  test    rcx, rcx
0x18000316b  jz      short loc_18000317A
0x18000316d  call    cs:__imp_free
0x180003173  mov     qword ptr [rdi], 0
0x18000317a  mov     rcx, [rbx+10h]; Block
0x18000317e  test    rcx, rcx
0x180003181  jz      short loc_180003191
0x180003183  call    cs:__imp_free
0x180003189  mov     qword ptr [rbx+10h], 0
0x180003191  mov     rsi, [rsp+28h+arg_8]
0x180003196  mov     dword ptr [rbx+18h], 0
0x18000319d  mov     rbx, [rsp+28h+arg_0]
0x1800031a2  add     rsp, 20h
0x1800031a6  pop     rdi
0x1800031a7  retn
```
