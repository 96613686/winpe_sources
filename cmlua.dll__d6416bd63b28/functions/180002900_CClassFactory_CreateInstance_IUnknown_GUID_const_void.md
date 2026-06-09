# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002900`
- end: `0x18000299b`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `155`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002900`
- `0x180006010`

## import_xrefs

- `cmutil!CmMalloc` at `0x180002930`
- `cmutil!CmMalloc` at `0x180002930`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  unsigned int v9; // ebx

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( a2 )
  {
    return (unsigned int)-2147221232;
  }
  else
  {
    v7 = CmMalloc(0x10u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 1;
      *(_QWORD *)v7 = &CCMLuaUtil::`vftable';
      _InterlockedIncrement(&dword_18000C6C0);
      v9 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v7)(v7, a3, a4);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180002900  mov     [rsp+arg_0], rbx
0x180002905  mov     [rsp+arg_8], rsi
0x18000290a  push    rdi
0x18000290b  sub     rsp, 20h
0x18000290f  mov     rbx, r9
0x180002912  mov     rsi, r8
0x180002915  test    r9, r9
0x180002918  jnz     short loc_180002921
0x18000291a  mov     eax, 80070057h
0x18000291f  jmp     short loc_18000298B
0x180002921  mov     qword ptr [r9], 0
0x180002928  test    rdx, rdx
0x18000292b  jnz     short loc_180002984
0x18000292d  lea     ecx, [rdx+10h]
0x180002930  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180002936  mov     rdi, rax
0x180002939  test    rax, rax
0x18000293c  jz      short loc_18000297D
0x18000293e  lea     rax, ??_7CCMLuaUtil@@6B@; const CCMLuaUtil::`vftable'
0x180002945  mov     dword ptr [rdi+8], 1
0x18000294c  mov     [rdi], rax
0x18000294f  lock inc cs:dword_18000C6C0
0x180002956  mov     rcx, [rdi]
0x180002959  mov     r8, rbx
0x18000295c  mov     rdx, rsi
0x18000295f  mov     rax, [rcx]
0x180002962  mov     rcx, rdi
0x180002965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000296a  mov     ebx, eax
0x18000296c  mov     rcx, rdi
0x18000296f  mov     rax, [rdi]
0x180002972  mov     rax, [rax+10h]
0x180002976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000297b  jmp     short loc_180002989
0x18000297d  mov     ebx, 8007000Eh
0x180002982  jmp     short loc_180002989
0x180002984  mov     ebx, 80040110h
0x180002989  mov     eax, ebx
0x18000298b  mov     rbx, [rsp+28h+arg_0]
0x180002990  mov     rsi, [rsp+28h+arg_8]
0x180002995  add     rsp, 20h
0x180002999  pop     rdi
0x18000299a  retn
```
