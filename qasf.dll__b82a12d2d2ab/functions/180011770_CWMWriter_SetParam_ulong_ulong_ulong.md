# CWMWriter::SetParam(ulong,ulong,ulong)

- ea: `0x180011770`
- end: `0x180011818`
- name: `?SetParam@CWMWriter@@UEAAJKKK@Z`
- size: `168`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011770`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800117ad`
- `KERNEL32!EnterCriticalSection` at `0x1800117d2`
- `KERNEL32!EnterCriticalSection` at `0x1800117f3`
- `KERNEL32!EnterCriticalSection` at `0x1800117ad`
- `KERNEL32!EnterCriticalSection` at `0x1800117d2`
- `KERNEL32!EnterCriticalSection` at `0x1800117f3`
- `KERNEL32!LeaveCriticalSection` at `0x1800117bc`
- `KERNEL32!LeaveCriticalSection` at `0x180011800`
- `KERNEL32!LeaveCriticalSection` at `0x1800117bc`
- `KERNEL32!LeaveCriticalSection` at `0x180011800`

## pseudocode

```c
__int64 __fastcall CWMWriter::SetParam(CWMWriter *this, int a2, int a3, int a4)
{
  int v6; // edx
  int v7; // edx
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rcx

  if ( a4 )
    return 2147942487LL;
  if ( *((_DWORD *)this - 28) )
    return 2147746343LL;
  v6 = a2 - 1;
  if ( !v6 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    *((_DWORD *)this + 17) = a3;
    goto LABEL_13;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    (*(void (__fastcall **)(CWMWriter *))(*(_QWORD *)this + 112LL))(this);
    *((_DWORD *)this + 61) = a3;
LABEL_13:
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
    goto LABEL_14;
  }
  if ( v7 != 1 )
    return 2147942487LL;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v10 = v9;
  if ( *((_DWORD *)this - 28) )
  {
    LeaveCriticalSection(v9);
    return 2147746343LL;
  }
  *((_DWORD *)this + 20) = a3;
LABEL_14:
  LeaveCriticalSection(v10);
  return 0;
}

```

## disassembly

```asm
0x180011770  mov     [rsp+arg_0], rbx
0x180011775  mov     [rsp+arg_8], rsi
0x18001177a  push    rdi
0x18001177b  sub     rsp, 20h
0x18001177f  mov     esi, r8d
0x180011782  mov     rdi, rcx
0x180011785  test    r9d, r9d
0x180011788  jnz     short loc_18001179F
0x18001178a  cmp     [rcx-70h], r9d
0x18001178e  jnz     short loc_1800117C2
0x180011790  sub     edx, 1
0x180011793  jz      short loc_1800117EF
0x180011795  sub     edx, 1
0x180011798  jz      short loc_1800117CE
0x18001179a  cmp     edx, 1
0x18001179d  jz      short loc_1800117A6
0x18001179f  mov     eax, 80070057h
0x1800117a4  jmp     short loc_180011808
0x1800117a6  lea     rbx, [rcx+58h]
0x1800117aa  mov     rcx, rbx; lpCriticalSection
0x1800117ad  call    cs:__imp_EnterCriticalSection
0x1800117b3  cmp     dword ptr [rdi-70h], 0
0x1800117b7  mov     rcx, rbx; lpCriticalSection
0x1800117ba  jz      short loc_1800117C9
0x1800117bc  call    cs:__imp_LeaveCriticalSection
0x1800117c2  mov     eax, 80040227h
0x1800117c7  jmp     short loc_180011808
0x1800117c9  mov     [rdi+50h], esi
0x1800117cc  jmp     short loc_180011800
0x1800117ce  add     rcx, 58h ; 'X'; lpCriticalSection
0x1800117d2  call    cs:__imp_EnterCriticalSection
0x1800117d8  mov     rax, [rdi]
0x1800117db  mov     rcx, rdi
0x1800117de  mov     rax, [rax+70h]
0x1800117e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117e7  mov     [rdi+0F4h], esi
0x1800117ed  jmp     short loc_1800117FC
0x1800117ef  add     rcx, 58h ; 'X'; lpCriticalSection
0x1800117f3  call    cs:__imp_EnterCriticalSection
0x1800117f9  mov     [rdi+44h], esi
0x1800117fc  lea     rcx, [rdi+58h]; lpCriticalSection
0x180011800  call    cs:__imp_LeaveCriticalSection
0x180011806  xor     eax, eax
0x180011808  mov     rbx, [rsp+28h+arg_0]
0x18001180d  mov     rsi, [rsp+28h+arg_8]
0x180011812  add     rsp, 20h
0x180011816  pop     rdi
0x180011817  retn
```
