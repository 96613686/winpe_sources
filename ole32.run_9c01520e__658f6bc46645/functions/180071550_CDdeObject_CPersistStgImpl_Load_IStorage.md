# CDdeObject::CPersistStgImpl::Load(IStorage *)

- ea: `0x180071550`
- end: `0x1800717e9`
- name: `?Load@CPersistStgImpl@CDdeObject@@UEAAJPEAUIStorage@@@Z`
- size: `665`
- prototype: `HRESULT __fastcall(CDdeObject::CPersistStgImpl *this, IStorage *pstg)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003df18`
- `0x18004508c`
- `0x180046460`
- `0x18006f184`
- `0x18006f260`
- `0x18006fae0`
- `0x18006ff94`
- `0x18007053c`
- `0x18007091c`
- `0x180071550`
- `0x1800ab608`
- `0x1800abbb8`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x1800715f4`
- `KERNELBASE!GlobalFree` at `0x18007167d`
- `KERNELBASE!GlobalFree` at `0x1800715f4`
- `KERNELBASE!GlobalFree` at `0x18007167d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800716a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800716a5`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007171a`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007171a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007173c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007173c`

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
      goto $errRtn_50;
    }
    v5 = CStmBufRead::Read(&StmRead, v7, szItemName.Data1);
    if ( v5 < 0 )
      goto $errRtn_50;
    m_hNative = this->m_pDdeObject->m_hNative;
    if ( m_hNative )
      GlobalFree(m_hNative);
    this->m_pDdeObject->m_hNative = wNewHandle(v8, szItemName.Data1);
    GlobalUnlock(hDdePoke);
    v5 = CDdeObject::PostSysCommand(this->m_pDdeObject, v12, "StdEditDocument", 0, 1);
    if ( v5 < 0 )
      goto $errRtn_50;
    if ( !CStmBufRead::OpenStream(&StmReadItem, pstg, &word_1800EC7C0) )
    {
      *(_QWORD *)&szItemName.Data1 = 0;
      v5 = ReadStringStreamA(&StmReadItem, (LPVOID *)&szItemName);
      if ( v5 )
      {
$errRtn_50:
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
    goto $errRtn_50;
  }
  return result;
}

```

## disassembly

```asm
0x180071550  mov     [rsp-8+arg_10], rbx
0x180071555  push    rbp
0x180071556  push    rsi
0x180071557  push    rdi
0x180071558  push    r12
0x18007155a  push    r13
0x18007155c  lea     rbp, [rsp-1A0h]
0x180071564  sub     rsp, 2A0h
0x18007156b  mov     rax, cs:__security_cookie
0x180071572  xor     rax, rsp
0x180071575  mov     [rbp+1C0h+var_30], rax
0x18007157c  xor     r13d, r13d
0x18007157f  lea     r8, szName; pwcsName
0x180071586  mov     rdi, this
0x180071589  mov     [rsp+2C0h+hDdePoke], r13
0x18007158e  lea     this, [rsp+2C0h+StmRead]; this
0x180071593  mov     dword ptr [rsp+2C0h+szItemName], r13d
0x180071598  mov     [rsp+2C0h+StmRead.m_pStm], r13
0x18007159d  mov     rsi, pstg
0x1800715a0  mov     [rbp+1C0h+StmReadItem.m_pStm], r13
0x1800715a4  call    ?OpenStream@CStmBufRead@@QEAAJPEAUIStorage@@PEBG@Z; CStmBufRead::OpenStream(IStorage *,ushort const *)
0x1800715a9  test    eax, eax
0x1800715ab  js      short loc_18007162A
0x1800715ad  lea     r8d, [r13+4]; cBuf
0x1800715b1  lea     pstg, [rsp+2C0h+szItemName]; pBuf
0x1800715b6  lea     this, [rsp+2C0h+StmRead]; this
0x1800715bb  call    ?Read@CStmBufRead@@QEAAJPEAXK@Z; CStmBufRead::Read(void *,ulong)
0x1800715c0  mov     ebx, eax
0x1800715c2  test    eax, eax
0x1800715c4  js      short loc_180071600
0x1800715c6  movzx   edx, cs:?g_cfNative@@3GA; cfFormat
0x1800715cd  lea     r8, [rsp+2C0h+hDdePoke]; phDdePoke
0x1800715d2  mov     ecx, dword ptr [rsp+2C0h+szItemName]; dwSize
0x1800715d6  call    ?wAllocDdePokeBlock@@YAPEADKGPEAPEAX@Z; wAllocDdePokeBlock(ulong,ushort,void * *)
0x1800715db  mov     r12, rax
0x1800715de  test    rax, rax
0x1800715e1  jnz     short loc_180071651
0x1800715e3  mov     ebx, 8007000Eh
0x1800715e8  cmp     [rsp+2C0h+hDdePoke], r13
0x1800715ed  jz      short loc_180071600
0x1800715ef  mov     this, [rsp+2C0h+hDdePoke]; hMem
0x1800715f4  call    cs:__imp_GlobalFree
0x1800715fb  nop     dword ptr [rax+rax+00h]
0x180071600  mov     this, [rdi+8]; this
0x180071604  mov     pstg, [this+158h]; pChannel
0x18007160b  test    pstg, pstg
0x18007160e  jz      short $LExit
0x180071610  call    ?TermConv@CDdeObject@@AEAAJPEAVDDE_CHANNEL@@H@Z; CDdeObject::TermConv(DDE_CHANNEL *,int)
0x180071615  lea     this, [rbp+1C0h+StmReadItem]; initializedElement
0x180071619  call    ?Release@CStmBufRead@@QEAAXXZ; CStmBufRead::Release(void)
0x18007161e  lea     this, [rsp+2C0h+StmRead]; initializedElement
0x180071623  call    ?Release@CStmBufRead@@QEAAXXZ; CStmBufRead::Release(void)
0x180071628  mov     eax, ebx
0x18007162a  mov     this, [rbp+1C0h+var_30]
0x180071631  xor     this, rsp; StackCookie
0x180071634  call    __security_check_cookie
0x180071639  mov     rbx, [rsp+2C0h+arg_10]
0x180071641  add     rsp, 2A0h
0x180071648  pop     r13
0x18007164a  pop     r12
0x18007164c  pop     rdi
0x18007164d  pop     rsi
0x18007164e  pop     rbp
0x18007164f  retn
0x180071651  mov     r8d, dword ptr [rsp+2C0h+szItemName]; cBuf
0x180071656  lea     this, [rsp+2C0h+StmRead]; this
0x18007165b  mov     pstg, r12; pBuf
0x18007165e  call    ?Read@CStmBufRead@@QEAAJPEAXK@Z; CStmBufRead::Read(void *,ulong)
0x180071663  mov     ebx, eax
0x180071665  test    eax, eax
0x180071667  js      $errRtn_50
0x18007166d  mov     rax, [rdi+8]
0x180071671  mov     this, [rax+0C0h]; hMem
0x180071678  test    this, this
0x18007167b  jz      short loc_180071689
0x18007167d  call    cs:__imp_GlobalFree
0x180071684  nop     dword ptr [rax+rax+00h]
0x180071689  mov     edx, dword ptr [rsp+2C0h+szItemName]; cb
0x18007168d  mov     this, r12; lpstr
0x180071690  call    ?wNewHandle@@YAPEAXPEADK@Z; wNewHandle(char *,ulong)
0x180071695  mov     this, [rdi+8]
0x180071699  mov     [this+0C0h], rax
0x1800716a0  mov     this, [rsp+2C0h+hDdePoke]; hMem
0x1800716a5  call    cs:__imp_GlobalUnlock
0x1800716ac  nop     dword ptr [rax+rax+00h]
0x1800716b1  mov     this, [rdi+8]; this
0x1800716b5  lea     r8, achStdEditDocument; "StdEditDocument"
0x1800716bc  xor     r9d, r9d; fWait
0x1800716bf  mov     [rsp+2C0h+pChannel], 1; pChannel
0x1800716c7  call    ?PostSysCommand@CDdeObject@@AEAAJPEAVDDE_CHANNEL@@PEBDHH@Z; CDdeObject::PostSysCommand(DDE_CHANNEL *,char const *,int,int)
0x1800716cc  mov     ebx, eax
0x1800716ce  test    eax, eax
0x1800716d0  js      $errRtn_50
0x1800716d6  lea     r8, word_1800EC7C0; pwcsName
0x1800716dd  mov     pstg, rsi; pstg
0x1800716e0  lea     this, [rbp+1C0h+StmReadItem]; this
0x1800716e4  call    ?OpenStream@CStmBufRead@@QEAAJPEAUIStorage@@PEBG@Z; CStmBufRead::OpenStream(IStorage *,ushort const *)
0x1800716e9  test    eax, eax
0x1800716eb  jnz     short loc_180071748
0x1800716ed  lea     pstg, [rsp+2C0h+szItemName]; ppsz
0x1800716f2  mov     qword ptr [rsp+2C0h+szItemName], r13
0x1800716f7  lea     this, [rbp+1C0h+StmReadItem]; StmRead
0x1800716fb  call    ReadStringStreamA
0x180071700  mov     ebx, eax
0x180071702  test    eax, eax
0x180071704  jnz     $errRtn_50
0x18007170a  mov     rbx, [rdi+8]
0x18007170e  movzx   ecx, word ptr [rbx+96h]; nAtom
0x180071715  test    cx, cx
0x180071718  jz      short loc_180071726
0x18007171a  call    cs:__imp_GlobalDeleteAtom
0x180071721  nop     dword ptr [rax+rax+00h]
0x180071726  mov     this, qword ptr [rsp+2C0h+szItemName]; sz
0x18007172b  call    ?wGlobalAddAtomA@@YAGPEBD@Z; wGlobalAddAtomA(char const *)
0x180071730  mov     this, qword ptr [rsp+2C0h+szItemName]; pv
0x180071735  mov     [rbx+96h], ax
0x18007173c  call    cs:__imp_CoTaskMemFree
0x180071743  nop     dword ptr [rax+rax+00h]
0x180071748  mov     this, [rdi+8]
0x18007174c  lea     r8, GUID_NULL
0x180071753  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007175a  add     this, 48h ; 'H'
0x18007175e  lea     pstg, [rsp+2C0h+szItemName]
0x180071763  movdqu  [rsp+2C0h+szItemName], xmm0
0x180071769  mov     rax, [this]
0x18007176c  mov     rax, [rax+58h]
0x180071770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071775  mov     ebx, eax
0x180071777  test    eax, eax
0x180071779  js      $errRtn_50
0x18007177f  mov     this, [rdi+8]; this
0x180071783  mov     r8, [rsp+2C0h+hDdePoke]; hDdePoke
0x180071788  movzx   edx, word ptr [this+96h]; aItem
0x18007178f  call    ?Poke@CDdeObject@@AEAAJGPEAX@Z; CDdeObject::Poke(ushort,void *)
0x180071794  mov     this, [rdi+8]; this
0x180071798  mov     pstg, [this+150h]; pChannel
0x18007179f  call    ?TermConv@CDdeObject@@AEAAJPEAVDDE_CHANNEL@@H@Z; CDdeObject::TermConv(DDE_CHANNEL *,int)
0x1800717a4  mov     ebx, eax
0x1800717a6  test    eax, eax
0x1800717a8  jnz     $errRtn_50
0x1800717ae  mov     rax, [rdi+8]
0x1800717b2  mov     this, [rax+0B0h]
0x1800717b9  test    this, this
0x1800717bc  jz      short loc_1800717CA
0x1800717be  mov     rax, [this]
0x1800717c1  mov     rax, [rax+10h]
0x1800717c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800717ca  mov     rax, [rdi+8]
0x1800717ce  mov     this, rsi
0x1800717d1  mov     [rax+0B0h], rsi
0x1800717d8  mov     rax, [rsi]
0x1800717db  mov     rax, [rax+8]
0x1800717df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800717e4  jmp     $LExit
```
