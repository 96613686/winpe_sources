# CDDEServer::FreeSrvrMem(void)

- ea: `0x1800740a8`
- end: `0x18007417e`
- name: `?FreeSrvrMem@CDDEServer@@AEAAJXZ`
- size: `214`
- prototype: `HRESULT __fastcall(CDDEServer *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180074894`

## callees

- `0x180046854`
- `0x1800740a8`
- `0x180076de0`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!LocalLock` at `0x1800740fb`
- `KERNELBASE!LocalLock` at `0x1800740fb`
- `KERNELBASE!LocalUnlock` at `0x180074117`
- `KERNELBASE!LocalUnlock` at `0x180074117`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074126`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074126`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800740ca`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007414d`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800740ca`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007414d`

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
0x1800740a8  mov     [rsp+arg_0], rbx
0x1800740ad  mov     [rsp+arg_8], rbp
0x1800740b2  mov     [rsp+arg_10], rsi
0x1800740b7  push    rdi
0x1800740b8  sub     rsp, 20h
0x1800740bc  mov     rbx, this
0x1800740bf  xor     ebp, ebp
0x1800740c1  movzx   ecx, word ptr [this+78h]; nAtom
0x1800740c5  test    cx, cx
0x1800740c8  jz      short loc_1800740D6
0x1800740ca  call    cs:__imp_GlobalDeleteAtom
0x1800740d1  nop     dword ptr [rax+rax+00h]
0x1800740d6  mov     this, [rbx+18h]
0x1800740da  test    this, this
0x1800740dd  jz      short loc_1800740EF
0x1800740df  mov     rax, [this]
0x1800740e2  mov     rax, [rax+10h]
0x1800740e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800740eb  mov     [rbx+18h], rbp
0x1800740ef  mov     rdi, [rbx+58h]
0x1800740f3  jmp     short loc_180074132
0x1800740f5  mov     this, rdi; hMem
0x1800740f8  mov     rsi, rdi
0x1800740fb  call    cs:__imp_LocalLock
0x180074102  nop     dword ptr [rax+rax+00h]
0x180074107  test    rax, rax
0x18007410a  jz      short loc_180074111
0x18007410c  mov     rdi, [rax]
0x18007410f  jmp     short loc_180074114
0x180074111  mov     rdi, rbp
0x180074114  mov     this, rsi; hMem
0x180074117  call    cs:__imp_LocalUnlock
0x18007411e  nop     dword ptr [rax+rax+00h]
0x180074123  mov     this, rsi; hMem
0x180074126  call    cs:__imp_LocalFree
0x18007412d  nop     dword ptr [rax+rax+00h]
0x180074132  test    rdi, rdi
0x180074135  jnz     short loc_1800740F5
0x180074137  movzx   edx, word ptr [rbx+74h]; aClass
0x18007413b  mov     this, [rbx+50h]; hwnd
0x18007413f  call    ?DestroyDdeSrvrWindow@@YAJPEAUHWND__@@G@Z; DestroyDdeSrvrWindow(HWND__ *,ushort)
0x180074144  movzx   ecx, word ptr [rbx+74h]; nAtom
0x180074148  test    cx, cx
0x18007414b  jz      short loc_180074159
0x18007414d  call    cs:__imp_GlobalDeleteAtom
0x180074154  nop     dword ptr [rax+rax+00h]
0x180074159  mov     edx, 80h; __formal
0x18007415e  mov     this, rbx; block
0x180074161  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180074166  mov     rbx, [rsp+28h+arg_0]
0x18007416b  xor     eax, eax
0x18007416d  mov     rbp, [rsp+28h+arg_8]
0x180074172  mov     rsi, [rsp+28h+arg_10]
0x180074177  add     rsp, 20h
0x18007417b  pop     rdi
0x18007417c  retn
```
