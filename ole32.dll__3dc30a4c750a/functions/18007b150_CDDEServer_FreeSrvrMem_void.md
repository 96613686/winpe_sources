# CDDEServer::FreeSrvrMem(void)

- ea: `0x18007b150`
- end: `0x18007b1f0`
- name: `?FreeSrvrMem@CDDEServer@@AEAAJXZ`
- size: `160`
- prototype: `HRESULT __fastcall(CDDEServer *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18007b868`

## callees

- `0x180052760`
- `0x18007b150`
- `0x18007dad4`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!LocalLock` at `0x18007b192`
- `KERNELBASE!LocalLock` at `0x18007b192`
- `KERNELBASE!LocalUnlock` at `0x18007b1a8`
- `KERNELBASE!LocalUnlock` at `0x18007b1a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007b1b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007b1b1`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007b167`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007b1d2`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007b167`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007b1d2`

## pseudocode

```c
__int64 __fastcall CDDEServer::FreeSrvrMem(CDDEServer *this)
{
  ATOM m_aExe; // cx
  IClassFactory *m_pClassFactory; // rcx
  void *m_hcli; // rdi
  void *v5; // rsi
  void **v6; // rax
  ATOM m_aClass; // cx

  m_aExe = this->m_aExe;
  if ( m_aExe )
    GlobalDeleteAtom(m_aExe);
  m_pClassFactory = this->m_pClassFactory;
  if ( m_pClassFactory )
  {
    ((void (__fastcall *)(IClassFactory *))m_pClassFactory->lpVtbl->Release)(m_pClassFactory);
    this->m_pClassFactory = 0;
  }
  m_hcli = this->m_hcli;
  while ( m_hcli )
  {
    v5 = m_hcli;
    v6 = (void **)LocalLock(m_hcli);
    if ( v6 )
      m_hcli = *v6;
    else
      m_hcli = 0;
    LocalUnlock(v5);
    LocalFree(v5);
  }
  DestroyDdeSrvrWindow(this->m_hwnd, this->m_aClass);
  m_aClass = this->m_aClass;
  if ( m_aClass )
    GlobalDeleteAtom(m_aClass);
  operator delete(this, 0x80u);
  return 0;
}

```

## disassembly

```asm
0x18007b150  push    rbx
0x18007b152  push    rbp
0x18007b153  push    rsi
0x18007b154  push    rdi
0x18007b155  sub     rsp, 28h
0x18007b159  mov     rbx, this
0x18007b15c  xor     ebp, ebp
0x18007b15e  movzx   ecx, word ptr [this+78h]; nAtom
0x18007b162  test    cx, cx
0x18007b165  jz      short loc_18007B16D
0x18007b167  call    cs:__imp_GlobalDeleteAtom
0x18007b16d  mov     this, [rbx+18h]
0x18007b171  test    this, this
0x18007b174  jz      short loc_18007B186
0x18007b176  mov     rax, [this]
0x18007b179  mov     rax, [rax+10h]
0x18007b17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b182  mov     [rbx+18h], rbp
0x18007b186  mov     rdi, [rbx+58h]
0x18007b18a  jmp     short loc_18007B1B7
0x18007b18c  mov     this, rdi; hMem
0x18007b18f  mov     rsi, rdi
0x18007b192  call    cs:__imp_LocalLock
0x18007b198  test    rax, rax
0x18007b19b  jz      short loc_18007B1A2
0x18007b19d  mov     rdi, [rax]
0x18007b1a0  jmp     short loc_18007B1A5
0x18007b1a2  mov     rdi, rbp
0x18007b1a5  mov     this, rsi; hMem
0x18007b1a8  call    cs:__imp_LocalUnlock
0x18007b1ae  mov     this, rsi; hMem
0x18007b1b1  call    cs:__imp_LocalFree
0x18007b1b7  test    rdi, rdi
0x18007b1ba  jnz     short loc_18007B18C
0x18007b1bc  movzx   edx, word ptr [rbx+74h]; aClass
0x18007b1c0  mov     this, [rbx+50h]; hwnd
0x18007b1c4  call    ?DestroyDdeSrvrWindow@@YAJPEAUHWND__@@G@Z; DestroyDdeSrvrWindow(HWND__ *,ushort)
0x18007b1c9  movzx   ecx, word ptr [rbx+74h]; nAtom
0x18007b1cd  test    cx, cx
0x18007b1d0  jz      short loc_18007B1D8
0x18007b1d2  call    cs:__imp_GlobalDeleteAtom
0x18007b1d8  mov     edx, 80h; __formal
0x18007b1dd  mov     this, rbx; block
0x18007b1e0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007b1e5  xor     eax, eax
0x18007b1e7  add     rsp, 28h
0x18007b1eb  pop     rdi
0x18007b1ec  pop     rsi
0x18007b1ed  pop     rbp
0x18007b1ee  pop     rbx
0x18007b1ef  retn
```
