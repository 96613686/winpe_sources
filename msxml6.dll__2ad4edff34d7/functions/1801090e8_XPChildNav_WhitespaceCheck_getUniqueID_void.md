# XPChildNav<WhitespaceCheck>::_getUniqueID(void)

- ea: `0x1801090e8`
- end: `0x180109250`
- name: `?_getUniqueID@?$XPChildNav@VWhitespaceCheck@@@@QEBAPEAVString@@XZ`
- size: `360`
- prototype: `String *__fastcall(XPChildNav<WhitespacePreserve> *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180109b30`

## callees

- `0x18003d048`
- `0x1800bc3b0`
- `0x1800cada0`
- `0x1801089d4`
- `0x180108a10`
- `0x1801090e8`
- `0x18011e5b4`
- `0x180188010`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18010913b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18010913b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18010915e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18010915e`

## pseudocode

```c
_CodebaseString *__fastcall XPChildNav<WhitespaceCheck>::_getUniqueID(XPChildNav<WhitespacePreserve> *this)
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
  return String::newString(buff, (unsigned int)(v16 + v15));
}

```

## disassembly

```asm
0x1801090e8  mov     [rsp-8+arg_8], rbx
0x1801090ed  push    rbp
0x1801090ee  lea     rbp, [rsp-20h]
0x1801090f3  sub     rsp, 120h
0x1801090fa  mov     rax, cs:__security_cookie
0x180109101  xor     rax, rsp
0x180109104  mov     [rbp+20h+var_10], rax
0x180109108  mov     rax, cs:sha2.m_bcrypt.m_handle
0x18010910f  xorps   xmm0, xmm0
0x180109112  mov     rbx, this
0x180109115  movups  xmmword ptr [rsp+120h+loc._doc], xmm0
0x18010911a  movups  xmmword ptr [rsp+120h+loc._ndSecondary], xmm0
0x18010911f  test    rax, rax
0x180109122  jnz     short loc_180109170
0x180109124  xor     r9d, r9d; dwFlags
0x180109127  mov     [rsp+120h+phAlgorithm], rax
0x18010912c  xor     r8d, r8d; pszImplementation
0x18010912f  lea     rdx, aSha256; "SHA256"
0x180109136  lea     this, [rsp+120h+phAlgorithm]; phAlgorithm
0x18010913b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180109141  test    eax, eax
0x180109143  js      short loc_180109168
0x180109145  mov     this, [rsp+120h+phAlgorithm]
0x18010914a  xor     eax, eax
0x18010914c  lock cmpxchg cs:sha2.m_bcrypt.m_handle, this
0x180109155  jz      short loc_180109170
0x180109157  mov     this, [rsp+120h+phAlgorithm]; hAlgorithm
0x18010915c  xor     edx, edx; dwFlags
0x18010915e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180109164  test    eax, eax
0x180109166  jns     short loc_180109170
0x180109168  mov     ecx, eax; hr
0x18010916a  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180109170  call    ?GenerateSalt@@YAJXZ; GenerateSalt(void)
0x180109175  test    eax, eax
0x180109177  jz      short loc_180109181
0x180109179  mov     ecx, eax; hr
0x18010917b  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180109181  mov     rax, [rbx]
0x180109184  lea     rdx, [rsp+120h+loc]
0x180109189  mov     this, rbx
0x18010918c  mov     rax, [rax+100h]
0x180109193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109198  mov     rax, qword ptr cs:salt
0x18010919f  lea     r8, [rsp+120h+nodeid]; input
0x1801091a4  mov     qword ptr [rsp+120h+nodeid._salt], rax
0x1801091a9  lea     rdx, [rsp+120h+digest]; result
0x1801091ae  mov     rax, [rsp+120h+loc._ndPrimary]
0x1801091b3  mov     [rsp+120h+nodeid._ndPrimary], rax
0x1801091b8  mov     rax, [rsp+120h+loc._ndSecondary]
0x1801091bd  mov     [rsp+120h+nodeid._ndSecondary], rax
0x1801091c2  call    ?Hash@SHA2@@QEBA?AUDigest@1@PEBXK@Z; SHA2::Hash(void const *,ulong)
0x1801091c7  mov     this, [rsp+120h+digest.q]; id
0x1801091cc  lea     rdx, [rbp+20h+buff+4]; buff
0x1801091d0  mov     dword ptr [rbp+20h+buff], 440049h
0x1801091d7  call    ?generateID@XUtility@@SAH_KPEAGH@Z; XUtility::generateID(unsigned __int64,ushort *,int)
0x1801091dc  mov     this, [rsp+120h+digest.q+8]; id
0x1801091e1  lea     rdx, [rbp+20h+buff]
0x1801091e5  lea     r9d, [rax+2]
0x1801091e9  movsxd  rax, r9d
0x1801091ec  lea     rdx, [rdx+rax*2]; buff
0x1801091f0  call    ?generateID@XUtility@@SAH_KPEAGH@Z; XUtility::generateID(unsigned __int64,ushort *,int)
0x1801091f5  mov     this, [rsp+120h+digest.q+10h]; id
0x1801091fa  lea     rdx, [rbp+20h+buff]
0x1801091fe  lea     r11d, [rax+r9]
0x180109202  movsxd  rax, r11d
0x180109205  lea     rdx, [rdx+rax*2]; buff
0x180109209  call    ?generateID@XUtility@@SAH_KPEAGH@Z; XUtility::generateID(unsigned __int64,ushort *,int)
0x18010920e  mov     this, [rbp+20h+digest.q+18h]; id
0x180109212  lea     rdx, [rbp+20h+buff]
0x180109216  lea     r9d, [rax+r11]
0x18010921a  movsxd  rax, r9d
0x18010921d  lea     rdx, [rdx+rax*2]; buff
0x180109221  call    ?generateID@XUtility@@SAH_KPEAGH@Z; XUtility::generateID(unsigned __int64,ushort *,int)
0x180109226  lea     this, [rbp+20h+buff]; c
0x18010922a  lea     edx, [r9+rax]; length
0x18010922e  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x180109233  mov     this, [rbp+20h+var_10]
0x180109237  xor     this, rsp; StackCookie
0x18010923a  call    __security_check_cookie
0x18010923f  mov     rbx, [rsp+120h+arg_8]
0x180109247  add     rsp, 120h
0x18010924e  pop     rbp
0x18010924f  retn
```
