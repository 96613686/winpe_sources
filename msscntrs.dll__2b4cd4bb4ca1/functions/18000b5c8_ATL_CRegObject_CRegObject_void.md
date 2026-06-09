# ATL::CRegObject::~CRegObject(void)

- ea: `0x18000b5c8`
- end: `0x18000b664`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b980`
- `0x18000ffec`
- `0x180010314`

## callees

- `0x18000b5c8`
- `0x18000c4b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b629`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b63f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b629`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b63f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b613`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b600`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b600`

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
0x18000b5c8  mov     [rsp+arg_0], rbx
0x18000b5cd  mov     [rsp+arg_8], rsi
0x18000b5d2  push    rdi
0x18000b5d3  sub     rsp, 20h
0x18000b5d7  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000b5de  mov     rbx, rcx
0x18000b5e1  lea     rsi, [rcx+20h]
0x18000b5e5  mov     [rcx], rax
0x18000b5e8  mov     rcx, rsi; lpCriticalSection
0x18000b5eb  call    cs:__imp_EnterCriticalSection
0x18000b5f1  lea     rdi, [rbx+8]
0x18000b5f5  mov     rcx, rdi; this
0x18000b5f8  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000b5fd  mov     rcx, rsi; lpCriticalSection
0x18000b600  call    cs:__imp_LeaveCriticalSection
0x18000b606  cmp     byte ptr [rsi+28h], 0
0x18000b60a  jz      short loc_18000B619
0x18000b60c  mov     rcx, rsi; lpCriticalSection
0x18000b60f  mov     byte ptr [rsi+28h], 0
0x18000b613  call    cs:__imp_DeleteCriticalSection
0x18000b619  mov     rcx, rdi; this
0x18000b61c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000b621  mov     rcx, [rdi]; Block
0x18000b624  test    rcx, rcx
0x18000b627  jz      short loc_18000B636
0x18000b629  call    cs:__imp_free
0x18000b62f  mov     qword ptr [rdi], 0
0x18000b636  mov     rcx, [rbx+10h]; Block
0x18000b63a  test    rcx, rcx
0x18000b63d  jz      short loc_18000B64D
0x18000b63f  call    cs:__imp_free
0x18000b645  mov     qword ptr [rbx+10h], 0
0x18000b64d  mov     rsi, [rsp+28h+arg_8]
0x18000b652  mov     dword ptr [rbx+18h], 0
0x18000b659  mov     rbx, [rsp+28h+arg_0]
0x18000b65e  add     rsp, 20h
0x18000b662  pop     rdi
0x18000b663  retn
```
