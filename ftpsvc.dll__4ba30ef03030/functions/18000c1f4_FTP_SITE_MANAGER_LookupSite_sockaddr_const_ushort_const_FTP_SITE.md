# FTP_SITE_MANAGER::LookupSite(sockaddr const *,ushort const *,FTP_SITE * *)

- ea: `0x18000c1f4`
- end: `0x18000c3c2`
- name: `?LookupSite@FTP_SITE_MANAGER@@QEAAJPEBUsockaddr@@PEBGPEAPEAVFTP_SITE@@@Z`
- size: `462`
- prototype: `int(FTP_SITE_MANAGER *__hidden this, const struct sockaddr *, const unsigned __int16 *, struct FTP_SITE **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x1800041f0`
- `0x18000c420`

## callees

- `0x180001250`
- `0x18000c1f4`
- `0x18002aac4`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c2d5`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c31e`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c2d5`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c31e`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000c38a`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000c38a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000c28a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000c2b3`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000c28a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000c2b3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c245`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c245`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c304`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c342`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c304`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c342`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c380`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c39e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c380`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c39e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_SITE_MANAGER::LookupSite(
        FTP_SITE_MANAGER *this,
        struct sockaddr *a2,
        const unsigned __int16 *a3,
        struct FTP_SITE **a4)
{
  signed int v8; // edi
  int Key; // eax
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rax
  struct FTP_SITE *v12; // rdi
  __int64 v13; // rax
  unsigned int v15; // [rsp+20h] [rbp-E0h] BYREF
  void *Block; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v17[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v19[64]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(v19, 0, sizeof(v19));
  STRU::STRU((STRU *)v17, v19, 0x40u);
  v15 = 0;
  v8 = BuildNormalizedBinding(a2, a3, (struct STRU *)v17, &v15);
  if ( v8 < 0 )
    goto LABEL_19;
  Block = 0;
  if ( !(unsigned int)CLKRHashTable::FindKey((char *)this + 88, v18, &Block) )
  {
    v10 = (volatile signed __int32 *)Block;
    goto LABEL_11;
  }
  Block = 0;
  Key = CLKRHashTable::FindKey((char *)this + 88, v18 + 2LL * v15, &Block);
  v10 = (volatile signed __int32 *)Block;
  if ( !Key )
  {
LABEL_11:
    v12 = 0;
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v10 + 2));
    v13 = *((_QWORD *)v10 + 25);
    if ( v13 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 176));
      v12 = (struct FTP_SITE *)*((_QWORD *)v10 + 25);
    }
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v10 + 2));
    if ( v12 )
    {
      *a4 = v12;
      v8 = 0;
    }
    else
    {
      v8 = -2147023834;
    }
    goto LABEL_16;
  }
  if ( *((_DWORD *)this + 41) )
  {
    CReaderWriterLock3::ReadLock((FTP_SITE_MANAGER *)((char *)this + 176));
    v11 = *((_QWORD *)this + 21);
    if ( v11 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 176));
      *a4 = (struct FTP_SITE *)*((_QWORD *)this + 21);
      v8 = 0;
    }
    else
    {
      v8 = -2147023834;
    }
    CReaderWriterLock3::ReadUnlock((FTP_SITE_MANAGER *)((char *)this + 176));
  }
  else
  {
    v8 = -2147467259;
  }
LABEL_16:
  if ( v10 && _InterlockedExchangeAdd(v10 + 1, 0xFFFFFFFF) == 1 )
  {
    *v10 = 1684173926;
    *((_QWORD *)v10 + 25) = 0;
    STRU::~STRU((void *)(v10 + 4));
    CReaderWriterLock3::~CReaderWriterLock3((CReaderWriterLock3 *)(v10 + 2));
    operator delete((void *)v10);
  }
LABEL_19:
  STRU::~STRU(v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c1f4  push    rbp
0x18000c1f6  push    rbx
0x18000c1f7  push    rsi
0x18000c1f8  push    rdi
0x18000c1f9  push    r14
0x18000c1fb  push    r15
0x18000c1fd  lea     rbp, [rsp-8]
0x18000c202  sub     rsp, 108h
0x18000c209  mov     rax, cs:__security_cookie
0x18000c210  xor     rax, rsp
0x18000c213  mov     [rbp+30h+var_40], rax
0x18000c217  mov     r15, r9
0x18000c21a  mov     rdi, r8
0x18000c21d  mov     rbx, rdx
0x18000c220  mov     rsi, rcx
0x18000c223  xor     edx, edx; Val
0x18000c225  mov     r8d, 80h; Size
0x18000c22b  lea     rcx, [rsp+130h+var_C0]; void *
0x18000c230  call    memset_0
0x18000c235  mov     r8d, 40h ; '@'
0x18000c23b  lea     rdx, [rsp+130h+var_C0]
0x18000c240  lea     rcx, [rsp+130h+var_100]
0x18000c245  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000c24b  nop
0x18000c24c  mov     [rsp+130h+var_110], 0
0x18000c254  lea     r9, [rsp+130h+var_110]; unsigned int *
0x18000c259  lea     r8, [rsp+130h+var_100]; struct STRU *
0x18000c25e  mov     rdx, rdi; unsigned __int16 *
0x18000c261  mov     rcx, rbx; pSockaddr
0x18000c264  call    ?BuildNormalizedBinding@@YAJPEBUsockaddr@@PEBGPEAVSTRU@@PEAK@Z; BuildNormalizedBinding(sockaddr const *,ushort const *,STRU *,ulong *)
0x18000c269  mov     edi, eax
0x18000c26b  test    eax, eax
0x18000c26d  js      loc_18000C399
0x18000c273  mov     [rsp+130h+Block], 0
0x18000c27c  lea     r8, [rsp+130h+Block]
0x18000c281  mov     rdx, [rsp+130h+var_E0]
0x18000c286  lea     rcx, [rsi+58h]
0x18000c28a  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000c290  test    eax, eax
0x18000c292  jz      short loc_18000C313
0x18000c294  mov     [rsp+130h+Block], 0
0x18000c29d  mov     edx, [rsp+130h+var_110]
0x18000c2a1  mov     rax, [rsp+130h+var_E0]
0x18000c2a6  lea     rdx, [rax+rdx*2]
0x18000c2aa  lea     r8, [rsp+130h+Block]
0x18000c2af  lea     rcx, [rsi+58h]
0x18000c2b3  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000c2b9  mov     rbx, [rsp+130h+Block]
0x18000c2be  test    eax, eax
0x18000c2c0  jz      short loc_18000C318
0x18000c2c2  cmp     dword ptr [rsi+0A4h], 0
0x18000c2c9  jz      short loc_18000C30C
0x18000c2cb  lea     r14, [rsi+0B0h]
0x18000c2d2  mov     rcx, r14
0x18000c2d5  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000c2db  mov     rax, [rsi+0A8h]
0x18000c2e2  test    rax, rax
0x18000c2e5  jz      short loc_18000C2FC
0x18000c2e7  lock inc dword ptr [rax+0B0h]
0x18000c2ee  mov     rax, [rsi+0A8h]
0x18000c2f5  mov     [r15], rax
0x18000c2f8  xor     edi, edi
0x18000c2fa  jmp     short loc_18000C301
0x18000c2fc  mov     edi, 80070426h
0x18000c301  mov     rcx, r14
0x18000c304  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000c30a  jmp     short loc_18000C359
0x18000c30c  mov     edi, 80004005h
0x18000c311  jmp     short loc_18000C359
0x18000c313  mov     rbx, [rsp+130h+Block]
0x18000c318  xor     edi, edi
0x18000c31a  lea     rcx, [rbx+8]
0x18000c31e  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000c324  mov     rax, [rbx+0C8h]
0x18000c32b  test    rax, rax
0x18000c32e  jz      short loc_18000C33E
0x18000c330  lock inc dword ptr [rax+0B0h]
0x18000c337  mov     rdi, [rbx+0C8h]
0x18000c33e  lea     rcx, [rbx+8]
0x18000c342  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000c348  test    rdi, rdi
0x18000c34b  jz      short loc_18000C354
0x18000c34d  mov     [r15], rdi
0x18000c350  xor     edi, edi
0x18000c352  jmp     short loc_18000C359
0x18000c354  mov     edi, 80070426h
0x18000c359  test    rbx, rbx
0x18000c35c  jz      short loc_18000C399
0x18000c35e  or      eax, 0FFFFFFFFh
0x18000c361  lock xadd [rbx+4], eax
0x18000c366  cmp     eax, 1
0x18000c369  jnz     short loc_18000C399
0x18000c36b  mov     dword ptr [rbx], 64627466h
0x18000c371  mov     qword ptr [rbx+0C8h], 0
0x18000c37c  lea     rcx, [rbx+10h]
0x18000c380  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c386  lea     rcx, [rbx+8]
0x18000c38a  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000c390  mov     rcx, rbx; Block
0x18000c393  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c398  nop
0x18000c399  lea     rcx, [rsp+130h+var_100]
0x18000c39e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c3a4  mov     eax, edi
0x18000c3a6  mov     rcx, [rbp+30h+var_40]
0x18000c3aa  xor     rcx, rsp; StackCookie
0x18000c3ad  call    __security_check_cookie
0x18000c3b2  add     rsp, 108h
0x18000c3b9  pop     r15
0x18000c3bb  pop     r14
0x18000c3bd  pop     rdi
0x18000c3be  pop     rsi
0x18000c3bf  pop     rbx
0x18000c3c0  pop     rbp
0x18000c3c1  retn
```
