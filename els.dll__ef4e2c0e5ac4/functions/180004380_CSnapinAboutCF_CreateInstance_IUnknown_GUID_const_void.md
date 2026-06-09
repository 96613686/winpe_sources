# CSnapinAboutCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004380`
- end: `0x18000442a`
- name: `?CreateInstance@CSnapinAboutCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `170`
- prototype: `__int64 __fastcall(CSnapinAboutCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002928`
- `0x180004380`
- `0x18001435c`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CSnapinAboutCF::CreateInstance(
        CSnapinAboutCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rdi

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = operator new(0x10u);
      if ( v7 )
      {
        *(_QWORD *)v7 = &CSnapinAbout::`vftable';
        if ( !CDll::s_cObjs )
          InitGlobals();
        _InterlockedIncrement((volatile signed __int32 *)&CDll::s_cObjs);
        v7[3] = 1;
        v6 = (**(__int64 (__fastcall ***)(_DWORD *, const struct _GUID *, void **))v7)(v7, a3, a4);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180004380  mov     [rsp+arg_0], rbx
0x180004385  mov     [rsp+arg_8], rsi
0x18000438a  push    rdi
0x18000438b  sub     rsp, 20h
0x18000438f  mov     rbx, r9
0x180004392  mov     rsi, r8
0x180004395  test    r9, r9
0x180004398  jnz     short loc_1800043A1
0x18000439a  mov     ebx, 80070057h
0x18000439f  jmp     short loc_180004418
0x1800043a1  mov     qword ptr [r9], 0
0x1800043a8  test    rdx, rdx
0x1800043ab  jz      short loc_1800043B4
0x1800043ad  mov     ebx, 80040110h
0x1800043b2  jmp     short loc_180004418
0x1800043b4  mov     ecx, 10h; Size
0x1800043b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800043be  mov     rdi, rax
0x1800043c1  test    rax, rax
0x1800043c4  jz      short loc_180004413
0x1800043c6  lea     rax, ??_7CSnapinAbout@@6B@; const CSnapinAbout::`vftable'
0x1800043cd  mov     [rdi], rax
0x1800043d0  cmp     cs:?s_cObjs@CDll@@2KA, 0; ulong CDll::s_cObjs
0x1800043d7  jnz     short loc_1800043DE
0x1800043d9  call    ?InitGlobals@@YAXXZ; InitGlobals(void)
0x1800043de  lock inc cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x1800043e5  mov     dword ptr [rdi+0Ch], 1
0x1800043ec  mov     r8, rbx
0x1800043ef  mov     rax, [rdi]
0x1800043f2  mov     rdx, rsi
0x1800043f5  mov     rcx, rdi
0x1800043f8  mov     rax, [rax]
0x1800043fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004400  mov     rcx, [rdi]
0x180004403  mov     ebx, eax
0x180004405  mov     rax, [rcx+10h]
0x180004409  mov     rcx, rdi
0x18000440c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004411  jmp     short loc_180004418
0x180004413  mov     ebx, 8007000Eh
0x180004418  mov     rsi, [rsp+28h+arg_8]
0x18000441d  mov     eax, ebx
0x18000441f  mov     rbx, [rsp+28h+arg_0]
0x180004424  add     rsp, 20h
0x180004428  pop     rdi
0x180004429  retn
```
