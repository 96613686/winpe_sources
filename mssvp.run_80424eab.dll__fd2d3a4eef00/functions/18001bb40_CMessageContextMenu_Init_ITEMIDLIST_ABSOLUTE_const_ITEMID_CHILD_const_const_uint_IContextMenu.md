# CMessageContextMenu::Init(_ITEMIDLIST_ABSOLUTE const *,_ITEMID_CHILD const * const *,uint,IContextMenu *)

- ea: `0x18001bb40`
- end: `0x18001bc1b`
- name: `?Init@CMessageContextMenu@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBQEFBU_ITEMID_CHILD@@IPEAUIContextMenu@@@Z`
- size: `219`
- prototype: `__int64 __usercall@<rax>(CMessageContextMenu *__hidden this@<rcx>, LPCITEMIDLIST pidl@<rdx>, const struct _ITEMID_CHILD *const *@<r8>, unsigned int@<r9d>, struct IContextMenu *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001bc30`
- `0x180020180`
- `0x180028eb0`

## callees

- `0x180006dcc`
- `0x18000be2c`
- `0x180019e18`
- `0x18001bb40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bba1`
- `api-ms-win-shell-namespace-l1-1-0!ILCloneFirst` at `0x18001bbd5`
- `api-ms-win-shell-namespace-l1-1-0!ILCloneFirst` at `0x18001bbd5`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001bb5d`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001bb5d`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x18001bb66`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x18001bb66`

## pseudocode

```c
__int64 __fastcall CMessageContextMenu::Init(
        CMessageContextMenu *this,
        LPCITEMIDLIST pidl,
        const struct _ITEMID_CHILD *const *a3,
        unsigned int a4,
        struct IUnknown *a5)
{
  LPITEMIDLIST v9; // rax
  unsigned int v10; // edi
  void *v11; // rax
  __int64 i; // rbp

  ILFree(*((LPITEMIDLIST *)this + 12));
  v9 = ILClone(pidl);
  *((_QWORD *)this + 12) = v9;
  if ( !v9 )
    goto LABEL_2;
  CMessageContextMenu::FreePidlTable(this);
  if ( is_mul_ok(a4 + 1, 8u) )
  {
    v11 = CoTaskMemAlloc(8LL * (a4 + 1));
    *((_QWORD *)this + 13) = v11;
    if ( !v11 )
    {
LABEL_2:
      v10 = -2147024882;
      goto LABEL_11;
    }
    memset_0(v11, 0, 8LL * (a4 + 1));
    v10 = 0;
    if ( *((_QWORD *)this + 13) )
    {
      for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
      {
        *(_QWORD *)(*((_QWORD *)this + 13) + 8 * i) = ILCloneFirst((LPCITEMIDLIST)a3[i]);
        if ( !*(_QWORD *)(*((_QWORD *)this + 13) + 8 * i) )
          goto LABEL_2;
      }
    }
  }
  else
  {
    v10 = -2147024362;
  }
LABEL_11:
  if ( *((struct IUnknown **)this + 11) != a5 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 11, a5);
  return v10;
}

```

## disassembly

```asm
0x18001bb40  push    rbx
0x18001bb42  push    rbp
0x18001bb43  push    rsi
0x18001bb44  push    rdi
0x18001bb45  push    r14
0x18001bb47  push    r15
0x18001bb49  sub     rsp, 28h
0x18001bb4d  mov     rsi, rcx
0x18001bb50  mov     r14d, r9d
0x18001bb53  mov     rcx, [rcx+60h]; pidl
0x18001bb57  mov     r15, r8
0x18001bb5a  mov     rbx, rdx
0x18001bb5d  call    cs:__imp_ILFree
0x18001bb63  mov     rcx, rbx; pidl
0x18001bb66  call    cs:__imp_ILClone
0x18001bb6c  mov     [rsi+60h], rax
0x18001bb70  test    rax, rax
0x18001bb73  jnz     short loc_18001BB7C
0x18001bb75  mov     edi, 8007000Eh
0x18001bb7a  jmp     short loc_18001BBF6
0x18001bb7c  mov     rcx, rsi; this
0x18001bb7f  call    ?FreePidlTable@CMessageContextMenu@@IEAAXXZ; CMessageContextMenu::FreePidlTable(void)
0x18001bb84  mov     eax, 8
0x18001bb89  mov     [rsp+58h+arg_0], 0
0x18001bb92  lea     ebx, [r14+1]
0x18001bb96  mul     rbx
0x18001bb99  test    rdx, rdx
0x18001bb9c  jnz     short loc_18001BBF1
0x18001bb9e  mov     rcx, rax; cb
0x18001bba1  call    cs:__imp_CoTaskMemAlloc
0x18001bba7  mov     [rsi+68h], rax
0x18001bbab  test    rax, rax
0x18001bbae  jz      short loc_18001BB75
0x18001bbb0  lea     r8, ds:0[rbx*8]; Size
0x18001bbb8  xor     edx, edx; Val
0x18001bbba  mov     rcx, rax; void *
0x18001bbbd  call    memset_0
0x18001bbc2  xor     edi, edi
0x18001bbc4  cmp     [rsi+68h], rdi
0x18001bbc8  jz      short loc_18001BBF6
0x18001bbca  xor     ebp, ebp
0x18001bbcc  cmp     ebp, r14d
0x18001bbcf  jnb     short loc_18001BBF6
0x18001bbd1  mov     rcx, [r15+rbp*8]; pidl
0x18001bbd5  call    cs:__imp_ILCloneFirst
0x18001bbdb  mov     rcx, [rsi+68h]
0x18001bbdf  mov     [rcx+rbp*8], rax
0x18001bbe3  mov     rax, [rsi+68h]
0x18001bbe7  cmp     [rax+rbp*8], rdi
0x18001bbeb  jz      short loc_18001BB75
0x18001bbed  inc     ebp
0x18001bbef  jmp     short loc_18001BBCC
0x18001bbf1  mov     edi, 80070216h
0x18001bbf6  mov     rdx, [rsp+58h+arg_20]; struct IUnknown *
0x18001bbfe  lea     rcx, [rsi+58h]; struct IUnknown **
0x18001bc02  cmp     [rcx], rdx
0x18001bc05  jz      short loc_18001BC0C
0x18001bc07  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001bc0c  mov     eax, edi
0x18001bc0e  add     rsp, 28h
0x18001bc12  pop     r15
0x18001bc14  pop     r14
0x18001bc16  pop     rdi
0x18001bc17  pop     rsi
0x18001bc18  pop     rbp
0x18001bc19  pop     rbx
0x18001bc1a  retn
```
