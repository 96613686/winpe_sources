# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002c28`
- end: `0x180002cc4`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d50`
- `0x180005620`

## callees

- `0x180002c28`
- `0x180004070`

## import_xrefs

- `msvcrt!free` at `0x180002c89`
- `msvcrt!free` at `0x180002c9f`
- `msvcrt!free` at `0x180002c89`
- `msvcrt!free` at `0x180002c9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c4b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002c73`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002c73`

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
0x180002c28  mov     [rsp+arg_0], rbx
0x180002c2d  mov     [rsp+arg_8], rsi
0x180002c32  push    rdi
0x180002c33  sub     rsp, 20h
0x180002c37  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180002c3e  mov     rbx, rcx
0x180002c41  lea     rsi, [rcx+20h]
0x180002c45  mov     [rcx], rax
0x180002c48  mov     rcx, rsi; lpCriticalSection
0x180002c4b  call    cs:__imp_EnterCriticalSection
0x180002c51  lea     rdi, [rbx+8]
0x180002c55  mov     rcx, rdi; this
0x180002c58  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002c5d  mov     rcx, rsi; lpCriticalSection
0x180002c60  call    cs:__imp_LeaveCriticalSection
0x180002c66  cmp     byte ptr [rsi+28h], 0
0x180002c6a  jz      short loc_180002C79
0x180002c6c  mov     rcx, rsi; lpCriticalSection
0x180002c6f  mov     byte ptr [rsi+28h], 0
0x180002c73  call    cs:__imp_DeleteCriticalSection
0x180002c79  mov     rcx, rdi; this
0x180002c7c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002c81  mov     rcx, [rdi]; Block
0x180002c84  test    rcx, rcx
0x180002c87  jz      short loc_180002C96
0x180002c89  call    cs:__imp_free
0x180002c8f  mov     qword ptr [rdi], 0
0x180002c96  mov     rcx, [rbx+10h]; Block
0x180002c9a  test    rcx, rcx
0x180002c9d  jz      short loc_180002CAD
0x180002c9f  call    cs:__imp_free
0x180002ca5  mov     qword ptr [rbx+10h], 0
0x180002cad  mov     rsi, [rsp+28h+arg_8]
0x180002cb2  mov     dword ptr [rbx+18h], 0
0x180002cb9  mov     rbx, [rsp+28h+arg_0]
0x180002cbe  add     rsp, 20h
0x180002cc2  pop     rdi
0x180002cc3  retn
```
