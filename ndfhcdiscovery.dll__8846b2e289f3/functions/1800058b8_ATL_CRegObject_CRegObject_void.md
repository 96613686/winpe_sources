# ATL::CRegObject::~CRegObject(void)

- ea: `0x1800058b8`
- end: `0x180005973`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `187`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d60`
- `0x180009c78`

## callees

- `0x1800058b8`
- `0x180006914`

## import_xrefs

- `msvcrt!free` at `0x18000592b`
- `msvcrt!free` at `0x180005947`
- `msvcrt!free` at `0x18000592b`
- `msvcrt!free` at `0x180005947`
- `KERNEL32!DeleteCriticalSection` at `0x18000590f`
- `KERNEL32!DeleteCriticalSection` at `0x18000590f`
- `KERNEL32!EnterCriticalSection` at `0x1800058db`
- `KERNEL32!EnterCriticalSection` at `0x1800058db`
- `KERNEL32!LeaveCriticalSection` at `0x1800058f6`
- `KERNEL32!LeaveCriticalSection` at `0x1800058f6`

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
0x1800058b8  mov     [rsp+arg_0], rbx
0x1800058bd  mov     [rsp+arg_8], rsi
0x1800058c2  push    rdi
0x1800058c3  sub     rsp, 20h
0x1800058c7  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800058ce  mov     rbx, rcx
0x1800058d1  lea     rsi, [rcx+20h]
0x1800058d5  mov     [rcx], rax
0x1800058d8  mov     rcx, rsi; lpCriticalSection
0x1800058db  call    cs:__imp_EnterCriticalSection
0x1800058e2  nop     dword ptr [rax+rax+00h]
0x1800058e7  lea     rdi, [rbx+8]
0x1800058eb  mov     rcx, rdi; this
0x1800058ee  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800058f3  mov     rcx, rsi; lpCriticalSection
0x1800058f6  call    cs:__imp_LeaveCriticalSection
0x1800058fd  nop     dword ptr [rax+rax+00h]
0x180005902  cmp     byte ptr [rsi+28h], 0
0x180005906  jz      short loc_18000591B
0x180005908  mov     rcx, rsi; lpCriticalSection
0x18000590b  mov     byte ptr [rsi+28h], 0
0x18000590f  call    cs:__imp_DeleteCriticalSection
0x180005916  nop     dword ptr [rax+rax+00h]
0x18000591b  mov     rcx, rdi; this
0x18000591e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180005923  mov     rcx, [rdi]; Block
0x180005926  test    rcx, rcx
0x180005929  jz      short loc_18000593E
0x18000592b  call    cs:__imp_free
0x180005932  nop     dword ptr [rax+rax+00h]
0x180005937  mov     qword ptr [rdi], 0
0x18000593e  mov     rcx, [rbx+10h]; Block
0x180005942  test    rcx, rcx
0x180005945  jz      short loc_18000595B
0x180005947  call    cs:__imp_free
0x18000594e  nop     dword ptr [rax+rax+00h]
0x180005953  mov     qword ptr [rbx+10h], 0
0x18000595b  mov     rsi, [rsp+28h+arg_8]
0x180005960  mov     dword ptr [rbx+18h], 0
0x180005967  mov     rbx, [rsp+28h+arg_0]
0x18000596c  add     rsp, 20h
0x180005970  pop     rdi
0x180005971  retn
```
