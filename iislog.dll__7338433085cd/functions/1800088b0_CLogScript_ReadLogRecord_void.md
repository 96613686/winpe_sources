# CLogScript::ReadLogRecord(void)

- ea: `0x1800088b0`
- end: `0x180008943`
- name: `?ReadLogRecord@CLogScript@@UEAAJXZ`
- size: `147`
- prototype: `__int64 __fastcall(CLogScript *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800088b0`
- `0x18000894c`
- `0x180010010`

## import_xrefs

- `msvcrt!fopen` at `0x1800088dc`
- `msvcrt!fopen` at `0x1800088dc`
- `KERNEL32!EnterCriticalSection` at `0x1800088c4`
- `KERNEL32!EnterCriticalSection` at `0x1800088c4`
- `KERNEL32!LeaveCriticalSection` at `0x180008930`
- `KERNEL32!LeaveCriticalSection` at `0x180008930`

## pseudocode

```c
__int64 __fastcall CLogScript::ReadLogRecord(const char **this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  CLogScript *v3; // rcx
  FILE *v4; // rax
  int v6; // eax
  unsigned int v7; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)(this + 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 1));
  if ( !this[6] )
  {
    v4 = fopen(this[11], "r");
    this[6] = (const char *)v4;
    if ( !v4 )
      return 2147500037LL;
  }
  CLogScript::ResetInetLogLine(v3, (struct _INETLOGLINE *)(this + 14));
  v6 = (*((__int64 (__fastcall **)(const char **, const char *, char *, const char *, _DWORD))*this + 34))(
         this,
         this[6],
         (char *)this + 112,
         this[143],
         *((_DWORD *)this + 288));
  v7 = 0;
  if ( v6 < 0 )
    v7 = v6;
  LeaveCriticalSection(v1);
  return v7;
}

```

## disassembly

```asm
0x1800088b0  mov     [rsp+arg_0], rbx
0x1800088b5  push    rdi
0x1800088b6  sub     rsp, 30h
0x1800088ba  lea     rdi, [rcx+8]
0x1800088be  mov     rbx, rcx
0x1800088c1  mov     rcx, rdi; lpCriticalSection
0x1800088c4  call    cs:__imp_EnterCriticalSection
0x1800088ca  cmp     qword ptr [rbx+30h], 0
0x1800088cf  jnz     short loc_1800088F2
0x1800088d1  mov     rcx, [rbx+58h]; FileName
0x1800088d5  lea     rdx, Mode; "r"
0x1800088dc  call    cs:__imp_fopen
0x1800088e2  mov     [rbx+30h], rax
0x1800088e6  test    rax, rax
0x1800088e9  jnz     short loc_1800088F2
0x1800088eb  mov     eax, 80004005h
0x1800088f0  jmp     short loc_180008938
0x1800088f2  lea     rdx, [rbx+70h]; struct _INETLOGLINE *
0x1800088f6  call    ?ResetInetLogLine@CLogScript@@AEAAXAEAU_INETLOGLINE@@@Z; CLogScript::ResetInetLogLine(_INETLOGLINE &)
0x1800088fb  mov     rdx, [rbx]
0x1800088fe  lea     r8, [rbx+70h]
0x180008902  mov     r9, [rbx+478h]
0x180008909  mov     rcx, rbx
0x18000890c  mov     rax, [rdx+110h]
0x180008913  mov     edx, [rbx+480h]
0x180008919  mov     [rsp+38h+var_18], edx
0x18000891d  mov     rdx, [rbx+30h]
0x180008921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008926  xor     ebx, ebx
0x180008928  mov     rcx, rdi; lpCriticalSection
0x18000892b  test    eax, eax
0x18000892d  cmovs   ebx, eax
0x180008930  call    cs:__imp_LeaveCriticalSection
0x180008936  mov     eax, ebx
0x180008938  mov     rbx, [rsp+38h+arg_0]
0x18000893d  add     rsp, 30h
0x180008941  pop     rdi
0x180008942  retn
```
