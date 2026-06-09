# ATL::CRegObject::~CRegObject(void)

- ea: `0x140005c40`
- end: `0x140005cfb`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `187`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140005e10`
- `0x140008460`
- `0x14000878c`

## callees

- `0x140005c40`
- `0x140006968`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005cb3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005ccf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005cb3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005ccf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005c97`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005c97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005c63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005c63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005c7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005c7e`

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
0x140005c40  mov     [rsp+arg_0], rbx
0x140005c45  mov     [rsp+arg_8], rsi
0x140005c4a  push    rdi
0x140005c4b  sub     rsp, 20h
0x140005c4f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x140005c56  mov     rbx, rcx
0x140005c59  lea     rsi, [rcx+20h]
0x140005c5d  mov     [rcx], rax
0x140005c60  mov     rcx, rsi; lpCriticalSection
0x140005c63  call    cs:__imp_EnterCriticalSection
0x140005c6a  nop     dword ptr [rax+rax+00h]
0x140005c6f  lea     rdi, [rbx+8]
0x140005c73  mov     rcx, rdi; this
0x140005c76  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140005c7b  mov     rcx, rsi; lpCriticalSection
0x140005c7e  call    cs:__imp_LeaveCriticalSection
0x140005c85  nop     dword ptr [rax+rax+00h]
0x140005c8a  cmp     byte ptr [rsi+28h], 0
0x140005c8e  jz      short loc_140005CA3
0x140005c90  mov     rcx, rsi; lpCriticalSection
0x140005c93  mov     byte ptr [rsi+28h], 0
0x140005c97  call    cs:__imp_DeleteCriticalSection
0x140005c9e  nop     dword ptr [rax+rax+00h]
0x140005ca3  mov     rcx, rdi; this
0x140005ca6  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140005cab  mov     rcx, [rdi]; Block
0x140005cae  test    rcx, rcx
0x140005cb1  jz      short loc_140005CC6
0x140005cb3  call    cs:__imp_free
0x140005cba  nop     dword ptr [rax+rax+00h]
0x140005cbf  mov     qword ptr [rdi], 0
0x140005cc6  mov     rcx, [rbx+10h]; Block
0x140005cca  test    rcx, rcx
0x140005ccd  jz      short loc_140005CE3
0x140005ccf  call    cs:__imp_free
0x140005cd6  nop     dword ptr [rax+rax+00h]
0x140005cdb  mov     qword ptr [rbx+10h], 0
0x140005ce3  mov     rsi, [rsp+28h+arg_8]
0x140005ce8  mov     dword ptr [rbx+18h], 0
0x140005cef  mov     rbx, [rsp+28h+arg_0]
0x140005cf4  add     rsp, 20h
0x140005cf8  pop     rdi
0x140005cf9  retn
```
