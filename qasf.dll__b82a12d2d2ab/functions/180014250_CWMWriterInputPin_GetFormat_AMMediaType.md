# CWMWriterInputPin::GetFormat(_AMMediaType * *)

- ea: `0x180014250`
- end: `0x180014371`
- name: `?GetFormat@CWMWriterInputPin@@UEAAJPEAPEAU_AMMediaType@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this, struct _AMMediaType **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x180001014`
- `0x180001460`
- `0x180007194`
- `0x180014250`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800142a5`
- `KERNEL32!EnterCriticalSection` at `0x1800142a5`
- `KERNEL32!LeaveCriticalSection` at `0x180014349`
- `KERNEL32!LeaveCriticalSection` at `0x180014349`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::GetFormat(CWMWriterInputPin *this, struct _AMMediaType **a2)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbp
  _QWORD *v6; // rax
  unsigned int v7; // edi
  struct _AMMediaType *v8; // rbx
  struct _AMMediaType *MediaType; // rax
  unsigned __int64 v10; // [rsp+20h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 17) )
    return 2147500037LL;
  v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 5);
  EnterCriticalSection(v5 + 6);
  v6 = (_QWORD *)*((_QWORD *)this + 17);
  LODWORD(v10) = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64 *))(*(_QWORD *)*v6 + 32LL))(*v6, 0, &v10);
  if ( (int)(v7 + 0x80000000) < 0 || v7 == -1072887855 )
  {
    v8 = (struct _AMMediaType *)operator new[]((unsigned int)v10);
    if ( v8 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, struct _AMMediaType *, unsigned __int64 *))(***((_QWORD ***)this + 17)
                                                                                        + 32LL))(
             **((_QWORD **)this + 17),
             v8,
             &v10);
      if ( v7 || (MediaType = CreateMediaType(v8), (*a2 = MediaType) != 0) )
      {
        operator delete(v8);
      }
      else
      {
        operator delete(v8);
        v7 = -2147024882;
      }
    }
  }
  LeaveCriticalSection(v5 + 6);
  return v7;
}

```

## disassembly

```asm
0x180014250  mov     [rsp+arg_10], rbx
0x180014255  mov     [rsp+arg_18], rbp
0x18001425a  push    rsi
0x18001425b  push    rdi
0x18001425c  push    r14
0x18001425e  sub     rsp, 30h
0x180014262  mov     rax, cs:__security_cookie
0x180014269  xor     rax, rsp
0x18001426c  mov     [rsp+48h+var_20], rax
0x180014271  mov     r14, rdx
0x180014274  mov     rsi, rcx
0x180014277  test    rdx, rdx
0x18001427a  jnz     short loc_180014286
0x18001427c  mov     eax, 80004003h
0x180014281  jmp     loc_180014351
0x180014286  cmp     qword ptr [rcx+88h], 0
0x18001428e  jnz     short loc_18001429A
0x180014290  mov     eax, 80004005h
0x180014295  jmp     loc_180014351
0x18001429a  mov     rbp, [rcx+28h]
0x18001429e  lea     rcx, [rbp+0F0h]; lpCriticalSection
0x1800142a5  call    cs:__imp_EnterCriticalSection
0x1800142ab  mov     rax, [rsi+88h]
0x1800142b2  lea     r8, [rsp+48h+var_28]
0x1800142b7  mov     dword ptr [rsp+48h+var_28], 0
0x1800142bf  xor     edx, edx
0x1800142c1  mov     rcx, [rax]
0x1800142c4  mov     rax, [rcx]
0x1800142c7  mov     rax, [rax+20h]
0x1800142cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142d0  mov     edi, eax
0x1800142d2  mov     eax, 80000000h
0x1800142d7  lea     ecx, [rdi+rax]
0x1800142da  test    eax, ecx
0x1800142dc  jnz     short loc_1800142E6
0x1800142de  cmp     edi, 0C00D07D1h
0x1800142e4  jnz     short loc_180014342
0x1800142e6  mov     ecx, dword ptr [rsp+48h+var_28]; unsigned __int64
0x1800142ea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800142ef  mov     rbx, rax
0x1800142f2  test    rax, rax
0x1800142f5  jz      short loc_180014342
0x1800142f7  mov     rcx, [rsi+88h]
0x1800142fe  lea     r8, [rsp+48h+var_28]
0x180014303  mov     rcx, [rcx]
0x180014306  mov     rdx, [rcx]
0x180014309  mov     rax, [rdx+20h]
0x18001430d  mov     rdx, rbx
0x180014310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014315  mov     edi, eax
0x180014317  test    eax, eax
0x180014319  jnz     short loc_18001433A
0x18001431b  mov     rcx, rbx; struct _AMMediaType *
0x18001431e  call    ?CreateMediaType@@YAPEAU_AMMediaType@@PEBU1@@Z; CreateMediaType(_AMMediaType const *)
0x180014323  mov     [r14], rax
0x180014326  test    rax, rax
0x180014329  jnz     short loc_18001433A
0x18001432b  mov     rcx, rbx; void *
0x18001432e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014333  mov     edi, 8007000Eh
0x180014338  jmp     short loc_180014342
0x18001433a  mov     rcx, rbx; void *
0x18001433d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014342  lea     rcx, [rbp+0F0h]; lpCriticalSection
0x180014349  call    cs:__imp_LeaveCriticalSection
0x18001434f  mov     eax, edi
0x180014351  mov     rcx, [rsp+48h+var_20]
0x180014356  xor     rcx, rsp; StackCookie
0x180014359  call    __security_check_cookie
0x18001435e  mov     rbx, [rsp+48h+arg_10]
0x180014363  mov     rbp, [rsp+48h+arg_18]
0x180014368  add     rsp, 30h
0x18001436c  pop     r14
0x18001436e  pop     rdi
0x18001436f  pop     rsi
0x180014370  retn
```
