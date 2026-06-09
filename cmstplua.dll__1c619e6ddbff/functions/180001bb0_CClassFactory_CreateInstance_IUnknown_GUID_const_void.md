# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001bb0`
- end: `0x180001c53`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `163`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001bb0`
- `0x180003010`

## import_xrefs

- `cmutil!CmMalloc` at `0x180001be0`
- `cmutil!CmMalloc` at `0x180001be0`

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
    v7 = CmMalloc(0x18u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 1;
      *(_QWORD *)v7 = &CCmstpLua::`vftable';
      _InterlockedIncrement(&dword_180006640);
      *((_QWORD *)v7 + 2) = 0;
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
0x180001bb0  mov     [rsp+arg_0], rbx
0x180001bb5  mov     [rsp+arg_8], rsi
0x180001bba  push    rdi
0x180001bbb  sub     rsp, 20h
0x180001bbf  mov     rbx, r9
0x180001bc2  mov     rsi, r8
0x180001bc5  test    r9, r9
0x180001bc8  jnz     short loc_180001BD1
0x180001bca  mov     eax, 80070057h
0x180001bcf  jmp     short loc_180001C43
0x180001bd1  mov     qword ptr [r9], 0
0x180001bd8  test    rdx, rdx
0x180001bdb  jnz     short loc_180001C3C
0x180001bdd  lea     ecx, [rdx+18h]
0x180001be0  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180001be6  mov     rdi, rax
0x180001be9  test    rax, rax
0x180001bec  jz      short loc_180001C35
0x180001bee  lea     rax, ??_7CCmstpLua@@6B@; const CCmstpLua::`vftable'
0x180001bf5  mov     dword ptr [rdi+8], 1
0x180001bfc  mov     [rdi], rax
0x180001bff  lock inc cs:dword_180006640
0x180001c06  mov     qword ptr [rdi+10h], 0
0x180001c0e  mov     r8, rbx
0x180001c11  mov     rcx, [rdi]
0x180001c14  mov     rdx, rsi
0x180001c17  mov     rax, [rcx]
0x180001c1a  mov     rcx, rdi
0x180001c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c22  mov     ebx, eax
0x180001c24  mov     rcx, rdi
0x180001c27  mov     rax, [rdi]
0x180001c2a  mov     rax, [rax+10h]
0x180001c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c33  jmp     short loc_180001C41
0x180001c35  mov     ebx, 8007000Eh
0x180001c3a  jmp     short loc_180001C41
0x180001c3c  mov     ebx, 80040110h
0x180001c41  mov     eax, ebx
0x180001c43  mov     rbx, [rsp+28h+arg_0]
0x180001c48  mov     rsi, [rsp+28h+arg_8]
0x180001c4d  add     rsp, 20h
0x180001c51  pop     rdi
0x180001c52  retn
```
