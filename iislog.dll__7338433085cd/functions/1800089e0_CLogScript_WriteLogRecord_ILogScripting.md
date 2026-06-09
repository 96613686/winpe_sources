# CLogScript::WriteLogRecord(ILogScripting *)

- ea: `0x1800089e0`
- end: `0x180008a77`
- name: `?WriteLogRecord@CLogScript@@UEAAJPEAUILogScripting@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(CLogScript *__hidden this, struct ILogScripting *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800089e0`
- `0x180010010`

## import_xrefs

- `msvcrt!fopen` at `0x180008a1c`
- `msvcrt!fopen` at `0x180008a1c`
- `KERNEL32!EnterCriticalSection` at `0x1800089fc`
- `KERNEL32!EnterCriticalSection` at `0x1800089fc`
- `KERNEL32!LeaveCriticalSection` at `0x180008a5f`
- `KERNEL32!LeaveCriticalSection` at `0x180008a5f`

## pseudocode

```c
__int64 __fastcall CLogScript::WriteLogRecord(CLogScript *this, struct ILogScripting *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v5; // r9
  FILE *v6; // rdx
  FILE *v7; // rax
  int v9; // eax
  unsigned int v10; // ebx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v6 = (FILE *)*((_QWORD *)this + 135);
  if ( v6 )
  {
    LOBYTE(v5) = 0;
  }
  else
  {
    v7 = fopen(*((const char **)this + 140), "w+");
    *((_QWORD *)this + 135) = v7;
    v6 = v7;
    if ( !v7 )
      return 2147500037LL;
    LOBYTE(v5) = 1;
  }
  v9 = (*(__int64 (__fastcall **)(CLogScript *, FILE *, struct ILogScripting *, __int64))(*(_QWORD *)this + 280LL))(
         this,
         v6,
         a2,
         v5);
  v10 = 0;
  if ( v9 < 0 )
    v10 = v9;
  LeaveCriticalSection(v2);
  return v10;
}

```

## disassembly

```asm
0x1800089e0  mov     [rsp+arg_0], rbx
0x1800089e5  mov     [rsp+arg_8], rsi
0x1800089ea  push    rdi
0x1800089eb  sub     rsp, 30h
0x1800089ef  lea     rdi, [rcx+8]
0x1800089f3  mov     rbx, rcx
0x1800089f6  mov     rcx, rdi; lpCriticalSection
0x1800089f9  mov     rsi, rdx
0x1800089fc  call    cs:__imp_EnterCriticalSection
0x180008a02  mov     rdx, [rbx+438h]
0x180008a09  test    rdx, rdx
0x180008a0c  jnz     short loc_180008A3D
0x180008a0e  mov     rcx, [rbx+460h]; FileName
0x180008a15  lea     rdx, aW; "w+"
0x180008a1c  call    cs:__imp_fopen
0x180008a22  mov     [rbx+438h], rax
0x180008a29  mov     rdx, rax
0x180008a2c  test    rax, rax
0x180008a2f  jnz     short loc_180008A38
0x180008a31  mov     eax, 80004005h
0x180008a36  jmp     short loc_180008A67
0x180008a38  mov     r9b, 1
0x180008a3b  jmp     short loc_180008A40
0x180008a3d  xor     r9b, r9b
0x180008a40  mov     rax, [rbx]
0x180008a43  mov     r8, rsi
0x180008a46  mov     rcx, rbx
0x180008a49  mov     rax, [rax+118h]
0x180008a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a55  xor     ebx, ebx
0x180008a57  mov     rcx, rdi; lpCriticalSection
0x180008a5a  test    eax, eax
0x180008a5c  cmovs   ebx, eax
0x180008a5f  call    cs:__imp_LeaveCriticalSection
0x180008a65  mov     eax, ebx
0x180008a67  mov     rbx, [rsp+38h+arg_0]
0x180008a6c  mov     rsi, [rsp+38h+arg_8]
0x180008a71  add     rsp, 30h
0x180008a75  pop     rdi
0x180008a76  retn
```
