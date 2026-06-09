# CDdeObject::CPersistStgImpl::Load(IStorage *)

- ea: `0x180078b70`
- end: `0x180078de6`
- name: `?Load@CPersistStgImpl@CDdeObject@@UEAAJPEAUIStorage@@@Z`
- size: `630`
- prototype: `HRESULT __fastcall(CDdeObject::CPersistStgImpl *this, IStorage *pstg)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180039eec`
- `0x1800428ec`
- `0x180052390`
- `0x180076b70`
- `0x180076c28`
- `0x180077458`
- `0x1800777d0`
- `0x180077cec`
- `0x18007800c`
- `0x180078b70`
- `0x1800a4940`
- `0x1800a4ea0`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x180078c14`
- `KERNELBASE!GlobalFree` at `0x180078c92`
- `KERNELBASE!GlobalFree` at `0x180078c14`
- `KERNELBASE!GlobalFree` at `0x180078c92`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180078cb4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180078cb4`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180078d23`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180078d23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078d3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078d3f`

## pseudocode

```c
HRESULT __fastcall CDdeObject::CPersistStgImpl::Load(CDdeObject::CPersistStgImpl *this, IStorage *pstg)
{
  HRESULT result; // eax
  HRESULT v5; // ebx
  int v6; // r8d
  char *v7; // rax
  char *v8; // r12
  CDdeObject *m_pDdeObject; // rcx
  DDE_CHANNEL *m_pDocChannel; // rdx
  void *m_hNative; // rcx
  DDE_CHANNEL *v12; // rdx
  CDdeObject *v13; // rbx
  ATOM m_aItem; // cx
  unsigned __int16 v15; // ax
  void *v16; // rcx
  CDdeObject::CProxyManagerImpl *p_m_ProxyMgr; // rcx
  int v18; // r8d
  IStorage *m_pstg; // rcx
  void *hDdePoke; // [rsp+30h] [rbp-D0h] BYREF
  GUID szItemName; // [rsp+40h] [rbp-C0h] BYREF
  CStmBufRead StmRead; // [rsp+50h] [rbp-B0h] BYREF
  CStmBufRead StmReadItem; // [rsp+170h] [rbp+70h] BYREF

  hDdePoke = 0;
  szItemName.Data1 = 0;
  StmRead.m_pStm = 0;
  StmReadItem.m_pStm = 0;
  result = CStmBufRead::OpenStream(&StmRead, pstg, &szName);
  if ( result >= 0 )
  {
    v5 = CStmBufRead::Read(&StmRead, &szItemName, 4u);
    if ( v5 < 0 )
    {
LABEL_7:
      m_pDdeObject = this->m_pDdeObject;
      m_pDocChannel = m_pDdeObject->m_pDocChannel;
      if ( m_pDocChannel )
        CDdeObject::TermConv(m_pDdeObject, m_pDocChannel, v6);
$LExit:
      CStmBufRead::Release((IInspectable **)&StmReadItem);
      CStmBufRead::Release((IInspectable **)&StmRead);
      return v5;
    }
    v7 = wAllocDdePokeBlock(szItemName.Data1, g_cfNative, &hDdePoke);
    v8 = v7;
    if ( !v7 )
    {
      v5 = -2147024882;
      goto $errRtn_84;
    }
    v5 = CStmBufRead::Read(&StmRead, v7, szItemName.Data1);
    if ( v5 < 0 )
      goto $errRtn_84;
    m_hNative = this->m_pDdeObject->m_hNative;
    if ( m_hNative )
      GlobalFree(m_hNative);
    this->m_pDdeObject->m_hNative = wNewHandle(v8, szItemName.Data1);
    GlobalUnlock(hDdePoke);
    v5 = CDdeObject::PostSysCommand(this->m_pDdeObject, v12, "StdEditDocument", 0, 1);
    if ( v5 < 0 )
      goto $errRtn_84;
    if ( !CStmBufRead::OpenStream(&StmReadItem, pstg, &word_1800E2350) )
    {
      *(_QWORD *)&szItemName.Data1 = 0;
      v5 = ReadStringStreamA(&StmReadItem, (LPVOID *)&szItemName);
      if ( v5 )
      {
$errRtn_84:
        if ( hDdePoke )
          GlobalFree(hDdePoke);
        goto LABEL_7;
      }
      v13 = this->m_pDdeObject;
      m_aItem = v13->m_aItem;
      if ( m_aItem )
        GlobalDeleteAtom(m_aItem);
      v15 = wGlobalAddAtomA(*(const char **)&szItemName.Data1);
      v16 = *(void **)&szItemName.Data1;
      v13->m_aItem = v15;
      CoTaskMemFree(v16);
    }
    p_m_ProxyMgr = &this->m_pDdeObject->m_ProxyMgr;
    szItemName = GUID_NULL;
    v5 = ((__int64 (__fastcall *)(CDdeObject::CProxyManagerImpl *, GUID *, GUID *))p_m_ProxyMgr->lpVtbl[3].Release)(
           p_m_ProxyMgr,
           &szItemName,
           &GUID_NULL);
    if ( v5 >= 0 )
    {
      CDdeObject::Poke(this->m_pDdeObject, this->m_pDdeObject->m_aItem, hDdePoke);
      v5 = CDdeObject::TermConv(this->m_pDdeObject, this->m_pDdeObject->m_pSysChannel, v18);
      if ( !v5 )
      {
        m_pstg = this->m_pDdeObject->m_pstg;
        if ( m_pstg )
          ((void (__fastcall *)(IStorage *))m_pstg->lpVtbl->Release)(m_pstg);
        this->m_pDdeObject->m_pstg = pstg;
        ((void (__fastcall *)(IStorage *))pstg->lpVtbl->AddRef)(pstg);
        goto $LExit;
      }
    }
    goto $errRtn_84;
  }
  return result;
}

```

## disassembly

```asm
0x180078b70  mov     [rsp-8+arg_10], rbx
0x180078b75  push    rbp
0x180078b76  push    rsi
0x180078b77  push    rdi
0x180078b78  push    r12
0x180078b7a  push    r13
0x180078b7c  lea     rbp, [rsp-1A0h]
0x180078b84  sub     rsp, 2A0h
0x180078b8b  mov     rax, cs:__security_cookie
0x180078b92  xor     rax, rsp
0x180078b95  mov     [rbp+1C0h+var_30], rax
0x180078b9c  xor     r13d, r13d
0x180078b9f  lea     r8, szName; pwcsName
0x180078ba6  mov     rdi, this
0x180078ba9  mov     [rsp+2C0h+hDdePoke], r13
0x180078bae  lea     this, [rsp+2C0h+StmRead]; this
0x180078bb3  mov     dword ptr [rsp+2C0h+szItemName], r13d
0x180078bb8  mov     [rsp+2C0h+StmRead.m_pStm], r13
0x180078bbd  mov     rsi, pstg
0x180078bc0  mov     [rbp+1C0h+StmReadItem.m_pStm], r13
0x180078bc4  call    ?OpenStream@CStmBufRead@@QEAAJPEAUIStorage@@PEBG@Z; CStmBufRead::OpenStream(IStorage *,ushort const *)
0x180078bc9  test    eax, eax
0x180078bcb  js      short loc_180078C44
0x180078bcd  lea     r8d, [r13+4]; cBuf
0x180078bd1  lea     pstg, [rsp+2C0h+szItemName]; pBuf
0x180078bd6  lea     this, [rsp+2C0h+StmRead]; this
0x180078bdb  call    ?Read@CStmBufRead@@QEAAJPEAXK@Z; CStmBufRead::Read(void *,ulong)
0x180078be0  mov     ebx, eax
0x180078be2  test    eax, eax
0x180078be4  js      short loc_180078C1A
0x180078be6  movzx   edx, cs:?g_cfNative@@3GA; cfFormat
0x180078bed  lea     r8, [rsp+2C0h+hDdePoke]; phDdePoke
0x180078bf2  mov     ecx, dword ptr [rsp+2C0h+szItemName]; dwSize
0x180078bf6  call    ?wAllocDdePokeBlock@@YAPEADKGPEAPEAX@Z; wAllocDdePokeBlock(ulong,ushort,void * *)
0x180078bfb  mov     r12, rax
0x180078bfe  test    rax, rax
0x180078c01  jnz     short loc_180078C6A
0x180078c03  mov     ebx, 8007000Eh
0x180078c08  cmp     [rsp+2C0h+hDdePoke], r13
0x180078c0d  jz      short loc_180078C1A
0x180078c0f  mov     this, [rsp+2C0h+hDdePoke]; hMem
0x180078c14  call    cs:__imp_GlobalFree
0x180078c1a  mov     this, [rdi+8]; this
0x180078c1e  mov     pstg, [this+158h]; pChannel
0x180078c25  test    pstg, pstg
0x180078c28  jz      short $LExit
0x180078c2a  call    ?TermConv@CDdeObject@@AEAAJPEAVDDE_CHANNEL@@H@Z; CDdeObject::TermConv(DDE_CHANNEL *,int)
0x180078c2f  lea     this, [rbp+1C0h+StmReadItem]; initializedElement
0x180078c33  call    ?Release@CStmBufRead@@QEAAXXZ; CStmBufRead::Release(void)
0x180078c38  lea     this, [rsp+2C0h+StmRead]; initializedElement
0x180078c3d  call    ?Release@CStmBufRead@@QEAAXXZ; CStmBufRead::Release(void)
0x180078c42  mov     eax, ebx
0x180078c44  mov     this, [rbp+1C0h+var_30]
0x180078c4b  xor     this, rsp; StackCookie
0x180078c4e  call    __security_check_cookie
0x180078c53  mov     rbx, [rsp+2C0h+arg_10]
0x180078c5b  add     rsp, 2A0h
0x180078c62  pop     r13
0x180078c64  pop     r12
0x180078c66  pop     rdi
0x180078c67  pop     rsi
0x180078c68  pop     rbp
0x180078c69  retn
0x180078c6a  mov     r8d, dword ptr [rsp+2C0h+szItemName]; cBuf
0x180078c6f  lea     this, [rsp+2C0h+StmRead]; this
0x180078c74  mov     pstg, r12; pBuf
0x180078c77  call    ?Read@CStmBufRead@@QEAAJPEAXK@Z; CStmBufRead::Read(void *,ulong)
0x180078c7c  mov     ebx, eax
0x180078c7e  test    eax, eax
0x180078c80  js      short $errRtn_84
0x180078c82  mov     rax, [rdi+8]
0x180078c86  mov     this, [rax+0C0h]; hMem
0x180078c8d  test    this, this
0x180078c90  jz      short loc_180078C98
0x180078c92  call    cs:__imp_GlobalFree
0x180078c98  mov     edx, dword ptr [rsp+2C0h+szItemName]; cb
0x180078c9c  mov     this, r12; lpstr
0x180078c9f  call    ?wNewHandle@@YAPEAXPEADK@Z; wNewHandle(char *,ulong)
0x180078ca4  mov     this, [rdi+8]
0x180078ca8  mov     [this+0C0h], rax
0x180078caf  mov     this, [rsp+2C0h+hDdePoke]; hMem
0x180078cb4  call    cs:__imp_GlobalUnlock
0x180078cba  mov     this, [rdi+8]; this
0x180078cbe  lea     r8, achStdEditDocument; "StdEditDocument"
0x180078cc5  xor     r9d, r9d; fWait
0x180078cc8  mov     [rsp+2C0h+pChannel], 1; pChannel
0x180078cd0  call    ?PostSysCommand@CDdeObject@@AEAAJPEAVDDE_CHANNEL@@PEBDHH@Z; CDdeObject::PostSysCommand(DDE_CHANNEL *,char const *,int,int)
0x180078cd5  mov     ebx, eax
0x180078cd7  test    eax, eax
0x180078cd9  js      $errRtn_84
0x180078cdf  lea     r8, word_1800E2350; pwcsName
0x180078ce6  mov     pstg, rsi; pstg
0x180078ce9  lea     this, [rbp+1C0h+StmReadItem]; this
0x180078ced  call    ?OpenStream@CStmBufRead@@QEAAJPEAUIStorage@@PEBG@Z; CStmBufRead::OpenStream(IStorage *,ushort const *)
0x180078cf2  test    eax, eax
0x180078cf4  jnz     short loc_180078D45
0x180078cf6  lea     pstg, [rsp+2C0h+szItemName]; ppsz
0x180078cfb  mov     qword ptr [rsp+2C0h+szItemName], r13
0x180078d00  lea     this, [rbp+1C0h+StmReadItem]; StmRead
0x180078d04  call    ReadStringStreamA
0x180078d09  mov     ebx, eax
0x180078d0b  test    eax, eax
0x180078d0d  jnz     $errRtn_84
0x180078d13  mov     rbx, [rdi+8]
0x180078d17  movzx   ecx, word ptr [rbx+96h]; nAtom
0x180078d1e  test    cx, cx
0x180078d21  jz      short loc_180078D29
0x180078d23  call    cs:__imp_GlobalDeleteAtom
0x180078d29  mov     this, qword ptr [rsp+2C0h+szItemName]; sz
0x180078d2e  call    ?wGlobalAddAtomA@@YAGPEBD@Z; wGlobalAddAtomA(char const *)
0x180078d33  mov     this, qword ptr [rsp+2C0h+szItemName]; pv
0x180078d38  mov     [rbx+96h], ax
0x180078d3f  call    cs:__imp_CoTaskMemFree
0x180078d45  mov     this, [rdi+8]
0x180078d49  lea     r8, GUID_NULL
0x180078d50  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180078d57  add     this, 48h ; 'H'
0x180078d5b  lea     pstg, [rsp+2C0h+szItemName]
0x180078d60  movdqu  [rsp+2C0h+szItemName], xmm0
0x180078d66  mov     rax, [this]
0x180078d69  mov     rax, [rax+58h]
0x180078d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d72  mov     ebx, eax
0x180078d74  test    eax, eax
0x180078d76  js      $errRtn_84
0x180078d7c  mov     this, [rdi+8]; this
0x180078d80  mov     r8, [rsp+2C0h+hDdePoke]; hDdePoke
0x180078d85  movzx   edx, word ptr [this+96h]; aItem
0x180078d8c  call    ?Poke@CDdeObject@@AEAAJGPEAX@Z; CDdeObject::Poke(ushort,void *)
0x180078d91  mov     this, [rdi+8]; this
0x180078d95  mov     pstg, [this+150h]; pChannel
0x180078d9c  call    ?TermConv@CDdeObject@@AEAAJPEAVDDE_CHANNEL@@H@Z; CDdeObject::TermConv(DDE_CHANNEL *,int)
0x180078da1  mov     ebx, eax
0x180078da3  test    eax, eax
0x180078da5  jnz     $errRtn_84
0x180078dab  mov     rax, [rdi+8]
0x180078daf  mov     this, [rax+0B0h]
0x180078db6  test    this, this
0x180078db9  jz      short loc_180078DC7
0x180078dbb  mov     rax, [this]
0x180078dbe  mov     rax, [rax+10h]
0x180078dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078dc7  mov     rax, [rdi+8]
0x180078dcb  mov     this, rsi
0x180078dce  mov     [rax+0B0h], rsi
0x180078dd5  mov     rax, [rsi]
0x180078dd8  mov     rax, [rax+8]
0x180078ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078de1  jmp     $LExit
```
