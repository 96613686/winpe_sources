# XPChildNav<WhitespaceCheck>::_getUniqueID(void)

- ea: `0x18010b7f0`
- end: `0x18010b965`
- name: `?_getUniqueID@?$XPChildNav@VWhitespaceCheck@@@@QEBAPEAVString@@XZ`
- size: `373`
- prototype: `String *__fastcall(XPChildNav<WhitespacePreserve> *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18010c250`

## callees

- `0x180030768`
- `0x1800bda08`
- `0x1800cc6c0`
- `0x18010b09c`
- `0x18010b0e4`
- `0x18010b7f0`
- `0x180120ff4`
- `0x18018c010`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18010b843`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18010b843`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18010b86c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18010b86c`

## pseudocode

```c
String *__fastcall XPChildNav<WhitespaceCheck>::_getUniqueID(XPChildNav<WhitespacePreserve> *this)
{
  NTSTATUS v2; // eax
  HRESULT Salt; // eax
  SHA2 *v4; // rcx
  unsigned int v5; // r9d
  int v6; // r8d
  int ID; // eax
  int v8; // r8d
  int v9; // eax
  int v10; // r9d
  int v11; // r8d
  int v12; // eax
  int v13; // r11d
  int v14; // r8d
  int v15; // eax
  int v16; // r9d
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+20h] [rbp-E0h] BYREF
  NodeID nodeid; // [rsp+28h] [rbp-D8h] BYREF
  NodeLocation loc; // [rsp+40h] [rbp-C0h] BYREF
  SHA2::Digest digest; // [rsp+68h] [rbp-98h] BYREF
  wchar_t buff[64]; // [rsp+90h] [rbp-70h] BYREF

  memset(&loc, 0, sizeof(loc));
  if ( !sha2.m_bcrypt.m_handle )
  {
    phAlgorithm = 0;
    v2 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
    if ( v2 < 0
      || _InterlockedCompareExchange64((volatile signed __int64 *)&sha2, (signed __int64)phAlgorithm, 0)
      && (v2 = BCryptCloseAlgorithmProvider(phAlgorithm, 0), v2 < 0) )
    {
      Exception::throwHR(v2);
    }
  }
  Salt = GenerateSalt();
  if ( Salt )
    Exception::throwHR(Salt);
  ((void (__fastcall *)(XPChildNav<WhitespacePreserve> *, NodeLocation *))this->_vtbl[1].fngetType)(this, &loc);
  nodeid._salt = salt;
  nodeid._ndPrimary = loc._ndPrimary;
  nodeid._ndSecondary = loc._ndSecondary;
  SHA2::Hash(v4, &digest, &nodeid, v5);
  *(_DWORD *)buff = 4456521;
  ID = XUtility::generateID(digest.q[0], &buff[2], v6);
  v9 = XUtility::generateID(digest.q[1], &buff[ID + 2], v8);
  v12 = XUtility::generateID(digest.q[2], &buff[v9 + v10], v11);
  v15 = XUtility::generateID(digest.q[3], &buff[v12 + v13], v14);
  return String::newString(buff, v16 + v15);
}

```

## disassembly

```asm
0x18010b7f0  mov     [rsp-8+arg_8], rbx
0x18010b7f5  push    rbp
0x18010b7f6  lea     rbp, [rsp-20h]
0x18010b7fb  sub     rsp, 120h
0x18010b802  mov     rax, cs:__security_cookie
0x18010b809  xor     rax, rsp
0x18010b80c  mov     [rbp+20h+var_10], rax
0x18010b810  mov     rax, cs:sha2.m_bcrypt.m_handle
0x18010b817  xorps   xmm0, xmm0
0x18010b81a  mov     rbx, this
0x18010b81d  movups  xmmword ptr [rsp+120h+loc._doc], xmm0
0x18010b822  movups  xmmword ptr [rsp+120h+loc._ndSecondary], xmm0
0x18010b827  test    rax, rax
0x18010b82a  jnz     short loc_18010B884
0x18010b82c  xor     r9d, r9d; dwFlags
0x18010b82f  mov     [rsp+120h+phAlgorithm], rax
0x18010b834  xor     r8d, r8d; pszImplementation
0x18010b837  lea     rdx, aSha256; "SHA256"
0x18010b83e  lea     this, [rsp+120h+phAlgorithm]; phAlgorithm
0x18010b843  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18010b84a  nop     dword ptr [rax+rax+00h]
0x18010b84f  test    eax, eax
0x18010b851  js      short loc_18010B87C
0x18010b853  mov     this, [rsp+120h+phAlgorithm]
0x18010b858  xor     eax, eax
0x18010b85a  lock cmpxchg cs:sha2.m_bcrypt.m_handle, this
0x18010b863  jz      short loc_18010B884
0x18010b865  mov     this, [rsp+120h+phAlgorithm]; hAlgorithm
0x18010b86a  xor     edx, edx; dwFlags
0x18010b86c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18010b873  nop     dword ptr [rax+rax+00h]
0x18010b878  test    eax, eax
0x18010b87a  jns     short loc_18010B884
0x18010b87c  mov     ecx, eax; hr
0x18010b87e  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18010b884  call    ?GenerateSalt@@YAJXZ; GenerateSalt(void)
0x18010b889  test    eax, eax
0x18010b88b  jz      short loc_18010B895
0x18010b88d  mov     ecx, eax; hr
0x18010b88f  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18010b895  mov     rax, [rbx]
0x18010b898  lea     rdx, [rsp+120h+loc]
0x18010b89d  mov     this, rbx
0x18010b8a0  mov     rax, [rax+100h]
0x18010b8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b8ac  mov     rax, qword ptr cs:salt
0x18010b8b3  lea     r8, [rsp+120h+nodeid]; input
0x18010b8b8  mov     qword ptr [rsp+120h+nodeid._salt], rax
0x18010b8bd  lea     rdx, [rsp+120h+digest]; result
0x18010b8c2  mov     rax, [rsp+120h+loc._ndPrimary]
0x18010b8c7  mov     [rsp+120h+nodeid._ndPrimary], rax
0x18010b8cc  mov     rax, [rsp+120h+loc._ndSecondary]
0x18010b8d1  mov     [rsp+120h+nodeid._ndSecondary], rax
0x18010b8d6  call    ?Hash@SHA2@@QEBA?AUDigest@1@PEBXK@Z; SHA2::Hash(void const *,ulong)
0x18010b8db  mov     this, [rsp+120h+digest.q]; id
0x18010b8e0  lea     rdx, [rbp+20h+buff+4]; buff
0x18010b8e4  mov     dword ptr [rbp+20h+buff], 440049h
0x18010b8eb  call    ?generateID@XUtility@@SAH_KPEAGH@Z; XUtility::generateID(unsigned __int64,ushort *,int)
0x18010b8f0  mov     this, [rsp+120h+digest.q+8]; id
0x18010b8f5  lea     rdx, [rbp+20h+buff]
0x18010b8f9  lea     r9d, [rax+2]
0x18010b8fd  movsxd  rax, r9d
0x18010b900  lea     rdx, [rdx+rax*2]; buff
0x18010b904  call    ?generateID@XUtility@@SAH_KPEAGH@Z; XUtility::generateID(unsigned __int64,ushort *,int)
0x18010b909  mov     this, [rsp+120h+digest.q+10h]; id
0x18010b90e  lea     rdx, [rbp+20h+buff]
0x18010b912  lea     r11d, [rax+r9]
0x18010b916  movsxd  rax, r11d
0x18010b919  lea     rdx, [rdx+rax*2]; buff
0x18010b91d  call    ?generateID@XUtility@@SAH_KPEAGH@Z; XUtility::generateID(unsigned __int64,ushort *,int)
0x18010b922  mov     this, [rbp+20h+digest.q+18h]; id
0x18010b926  lea     rdx, [rbp+20h+buff]
0x18010b92a  lea     r9d, [rax+r11]
0x18010b92e  movsxd  rax, r9d
0x18010b931  lea     rdx, [rdx+rax*2]; buff
0x18010b935  call    ?generateID@XUtility@@SAH_KPEAGH@Z; XUtility::generateID(unsigned __int64,ushort *,int)
0x18010b93a  lea     this, [rbp+20h+buff]; c
0x18010b93e  lea     edx, [r9+rax]; length
0x18010b942  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x18010b947  mov     this, [rbp+20h+var_10]
0x18010b94b  xor     this, rsp; StackCookie
0x18010b94e  call    __security_check_cookie
0x18010b953  mov     rbx, [rsp+120h+arg_8]
0x18010b95b  add     rsp, 120h
0x18010b962  pop     rbp
0x18010b963  retn
```
