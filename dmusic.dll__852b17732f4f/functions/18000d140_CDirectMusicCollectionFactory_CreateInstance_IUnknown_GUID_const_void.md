# CDirectMusicCollectionFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000d140`
- end: `0x18000d1ce`
- name: `?CreateInstance@CDirectMusicCollectionFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `142`
- prototype: `int(CDirectMusicCollectionFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000b56c`
- `0x18000cb00`
- `0x18000cc10`
- `0x18000d140`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d179`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d179`

## pseudocode

```c
__int64 __fastcall CDirectMusicCollectionFactory::CreateInstance(
        CDirectMusicCollectionFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  CCollection *v7; // rax
  CCollection *v8; // rdi
  unsigned int Interface; // ebx

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v7 = (CCollection *)malloc(0x130u);
  if ( v7 )
    v8 = CCollection::CCollection(v7);
  else
    v8 = 0;
  if ( !v8 )
    return 2147942414LL;
  Interface = CCollection::QueryInterface(v8, a3, a4);
  CCollection::Release(v8);
  return Interface;
}

```

## disassembly

```asm
0x18000d140  mov     [rsp+arg_0], rbx
0x18000d145  mov     [rsp+arg_8], rsi
0x18000d14a  push    rdi
0x18000d14b  sub     rsp, 20h
0x18000d14f  mov     rbx, r9
0x18000d152  mov     rsi, r8
0x18000d155  test    r9, r9
0x18000d158  jnz     short loc_18000D161
0x18000d15a  mov     eax, 80004003h
0x18000d15f  jmp     short loc_18000D1BE
0x18000d161  mov     qword ptr [r9], 0
0x18000d168  test    rdx, rdx
0x18000d16b  jz      short loc_18000D174
0x18000d16d  mov     eax, 80040110h
0x18000d172  jmp     short loc_18000D1BE
0x18000d174  mov     ecx, 130h; Size
0x18000d179  call    cs:__imp_malloc
0x18000d17f  mov     [rsp+28h+arg_18], rax
0x18000d184  test    rax, rax
0x18000d187  jz      short loc_18000D196
0x18000d189  mov     rcx, rax; this
0x18000d18c  call    ??0CCollection@@QEAA@XZ; CCollection::CCollection(void)
0x18000d191  mov     rdi, rax
0x18000d194  jmp     short loc_18000D198
0x18000d196  xor     edi, edi
0x18000d198  test    rdi, rdi
0x18000d19b  jz      short loc_18000D1B9
0x18000d19d  mov     r8, rbx; void **
0x18000d1a0  mov     rdx, rsi; struct _GUID *
0x18000d1a3  mov     rcx, rdi; this
0x18000d1a6  call    ?QueryInterface@CCollection@@UEAAJAEBU_GUID@@PEAPEAX@Z; CCollection::QueryInterface(_GUID const &,void * *)
0x18000d1ab  mov     ebx, eax
0x18000d1ad  mov     rcx, rdi; this
0x18000d1b0  call    ?Release@CCollection@@UEAAKXZ; CCollection::Release(void)
0x18000d1b5  mov     eax, ebx
0x18000d1b7  jmp     short loc_18000D1BE
0x18000d1b9  mov     eax, 8007000Eh
0x18000d1be  mov     rbx, [rsp+28h+arg_0]
0x18000d1c3  mov     rsi, [rsp+28h+arg_8]
0x18000d1c8  add     rsp, 20h
0x18000d1cc  pop     rdi
0x18000d1cd  retn
```
