# ATL::CRegObject::~CRegObject(void)

- ea: `0x18000d860`
- end: `0x18000d8fc`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000db70`
- `0x18001217c`
- `0x18001249c`

## callees

- `0x18000d860`
- `0x18000f2a4`

## import_xrefs

- `msvcrt!free` at `0x18000d8c1`
- `msvcrt!free` at `0x18000d8d7`
- `msvcrt!free` at `0x18000d8c1`
- `msvcrt!free` at `0x18000d8d7`
- `KERNEL32!EnterCriticalSection` at `0x18000d883`
- `KERNEL32!EnterCriticalSection` at `0x18000d883`
- `KERNEL32!LeaveCriticalSection` at `0x18000d898`
- `KERNEL32!LeaveCriticalSection` at `0x18000d898`
- `KERNEL32!DeleteCriticalSection` at `0x18000d8ab`
- `KERNEL32!DeleteCriticalSection` at `0x18000d8ab`

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
0x18000d860  mov     [rsp+arg_0], rbx
0x18000d865  mov     [rsp+arg_8], rsi
0x18000d86a  push    rdi
0x18000d86b  sub     rsp, 20h
0x18000d86f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000d876  mov     rbx, rcx
0x18000d879  lea     rsi, [rcx+20h]
0x18000d87d  mov     [rcx], rax
0x18000d880  mov     rcx, rsi; lpCriticalSection
0x18000d883  call    cs:__imp_EnterCriticalSection
0x18000d889  lea     rdi, [rbx+8]
0x18000d88d  mov     rcx, rdi; this
0x18000d890  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000d895  mov     rcx, rsi; lpCriticalSection
0x18000d898  call    cs:__imp_LeaveCriticalSection
0x18000d89e  cmp     byte ptr [rsi+28h], 0
0x18000d8a2  jz      short loc_18000D8B1
0x18000d8a4  mov     rcx, rsi; lpCriticalSection
0x18000d8a7  mov     byte ptr [rsi+28h], 0
0x18000d8ab  call    cs:__imp_DeleteCriticalSection
0x18000d8b1  mov     rcx, rdi; this
0x18000d8b4  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000d8b9  mov     rcx, [rdi]; Block
0x18000d8bc  test    rcx, rcx
0x18000d8bf  jz      short loc_18000D8CE
0x18000d8c1  call    cs:__imp_free
0x18000d8c7  mov     qword ptr [rdi], 0
0x18000d8ce  mov     rcx, [rbx+10h]; Block
0x18000d8d2  test    rcx, rcx
0x18000d8d5  jz      short loc_18000D8E5
0x18000d8d7  call    cs:__imp_free
0x18000d8dd  mov     qword ptr [rbx+10h], 0
0x18000d8e5  mov     rsi, [rsp+28h+arg_8]
0x18000d8ea  mov     dword ptr [rbx+18h], 0
0x18000d8f1  mov     rbx, [rsp+28h+arg_0]
0x18000d8f6  add     rsp, 20h
0x18000d8fa  pop     rdi
0x18000d8fb  retn
```
