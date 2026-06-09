# ATL::CRegObject::~CRegObject(void)

- ea: `0x1800023f8`
- end: `0x180002494`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800025a0`
- `0x180005074`

## callees

- `0x1800023f8`
- `0x1800030dc`

## import_xrefs

- `msvcrt!free` at `0x180002459`
- `msvcrt!free` at `0x18000246f`
- `msvcrt!free` at `0x180002459`
- `msvcrt!free` at `0x18000246f`
- `KERNEL32!EnterCriticalSection` at `0x18000241b`
- `KERNEL32!EnterCriticalSection` at `0x18000241b`
- `KERNEL32!LeaveCriticalSection` at `0x180002430`
- `KERNEL32!LeaveCriticalSection` at `0x180002430`
- `KERNEL32!DeleteCriticalSection` at `0x180002443`
- `KERNEL32!DeleteCriticalSection` at `0x180002443`

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
0x1800023f8  mov     [rsp+arg_0], rbx
0x1800023fd  mov     [rsp+arg_8], rsi
0x180002402  push    rdi
0x180002403  sub     rsp, 20h
0x180002407  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000240e  mov     rbx, rcx
0x180002411  lea     rsi, [rcx+20h]
0x180002415  mov     [rcx], rax
0x180002418  mov     rcx, rsi; lpCriticalSection
0x18000241b  call    cs:__imp_EnterCriticalSection
0x180002421  lea     rdi, [rbx+8]
0x180002425  mov     rcx, rdi; this
0x180002428  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000242d  mov     rcx, rsi; lpCriticalSection
0x180002430  call    cs:__imp_LeaveCriticalSection
0x180002436  cmp     byte ptr [rsi+28h], 0
0x18000243a  jz      short loc_180002449
0x18000243c  mov     rcx, rsi; lpCriticalSection
0x18000243f  mov     byte ptr [rsi+28h], 0
0x180002443  call    cs:__imp_DeleteCriticalSection
0x180002449  mov     rcx, rdi; this
0x18000244c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002451  mov     rcx, [rdi]; Block
0x180002454  test    rcx, rcx
0x180002457  jz      short loc_180002466
0x180002459  call    cs:__imp_free
0x18000245f  mov     qword ptr [rdi], 0
0x180002466  mov     rcx, [rbx+10h]; Block
0x18000246a  test    rcx, rcx
0x18000246d  jz      short loc_18000247D
0x18000246f  call    cs:__imp_free
0x180002475  mov     qword ptr [rbx+10h], 0
0x18000247d  mov     rsi, [rsp+28h+arg_8]
0x180002482  mov     dword ptr [rbx+18h], 0
0x180002489  mov     rbx, [rsp+28h+arg_0]
0x18000248e  add     rsp, 20h
0x180002492  pop     rdi
0x180002493  retn
```
