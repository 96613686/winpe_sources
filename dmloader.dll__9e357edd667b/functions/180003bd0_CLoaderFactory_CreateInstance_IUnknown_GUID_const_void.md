# CLoaderFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003bd0`
- end: `0x180003c75`
- name: `?CreateInstance@CLoaderFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `165`
- prototype: `int(CLoaderFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800019a0`
- `0x180003bd0`
- `0x180007f28`
- `0x180007fcc`
- `0x180008e90`
- `0x1800093e0`
- `0x1800094c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003c04`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003c04`

## pseudocode

```c
__int64 __fastcall CLoaderFactory::CreateInstance(
        CLoaderFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  CLoader *v7; // rax
  CLoader *v8; // rdi
  int Interface; // ebx

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  try
  {
    v7 = (CLoader *)malloc(0x280u);
    if ( v7 )
      v8 = CLoader::CLoader(v7);
    else
      v8 = 0;
  }
  catch ( ... )
  {
    return 2147942414LL;
  }
  if ( !v8 )
    return 2147942414LL;
  Interface = CLoader::Init(v8);
  if ( Interface >= 0 )
  {
    Interface = CLoader::QueryInterface(v8, a3, a4);
    CLoader::Release(v8);
  }
  else
  {
    CLoader::~CLoader(v8);
    operator delete(v8);
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180003bd0  push    rbx
0x180003bd2  push    rsi
0x180003bd3  push    rdi
0x180003bd4  push    r14
0x180003bd6  sub     rsp, 38h
0x180003bda  mov     rsi, r9
0x180003bdd  mov     r14, r8
0x180003be0  test    r9, r9
0x180003be3  jnz     short loc_180003BEC
0x180003be5  mov     eax, 80004003h
0x180003bea  jmp     short loc_180003C6B
0x180003bec  mov     qword ptr [r9], 0
0x180003bf3  test    rdx, rdx
0x180003bf6  jz      short loc_180003BFF
0x180003bf8  mov     eax, 80040110h
0x180003bfd  jmp     short loc_180003C6B
0x180003bff  mov     ecx, 280h; Size
0x180003c04  call    cs:__imp_malloc
0x180003c0a  test    rax, rax
0x180003c0d  jz      short loc_180003C1C
0x180003c0f  mov     rcx, rax; this
0x180003c12  call    ??0CLoader@@QEAA@XZ; CLoader::CLoader(void)
0x180003c17  mov     rdi, rax
0x180003c1a  jmp     short loc_180003C1E
0x180003c1c  xor     edi, edi
0x180003c1e  mov     [rsp+58h+var_38], rdi
0x180003c23  test    rdi, rdi
0x180003c26  jz      short loc_180003C66
0x180003c28  mov     rcx, rdi; this
0x180003c2b  call    ?Init@CLoader@@QEAAJXZ; CLoader::Init(void)
0x180003c30  mov     ebx, eax
0x180003c32  mov     rcx, rdi; this
0x180003c35  test    eax, eax
0x180003c37  jns     short loc_180003C4F
0x180003c39  call    ??1CLoader@@QEAA@XZ; CLoader::~CLoader(void)
0x180003c3e  mov     edx, 280h; unsigned __int64
0x180003c43  mov     rcx, rdi; void *
0x180003c46  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003c4b  mov     eax, ebx
0x180003c4d  jmp     short loc_180003C6B
0x180003c4f  mov     r8, rsi; void **
0x180003c52  mov     rdx, r14; struct _GUID *
0x180003c55  call    ?QueryInterface@CLoader@@UEAAJAEBU_GUID@@PEAPEAX@Z; CLoader::QueryInterface(_GUID const &,void * *)
0x180003c5a  mov     ebx, eax
0x180003c5c  mov     rcx, rdi; this
0x180003c5f  call    ?Release@CLoader@@UEAAKXZ; CLoader::Release(void)
0x180003c64  jmp     short loc_180003C4B
0x180003c66  mov     eax, 8007000Eh
0x180003c6b  add     rsp, 38h
0x180003c6f  pop     r14
0x180003c71  pop     rdi
0x180003c72  pop     rsi
0x180003c73  pop     rbx
0x180003c74  retn
```
