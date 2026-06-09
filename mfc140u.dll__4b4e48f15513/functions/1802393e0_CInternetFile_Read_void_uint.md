# CInternetFile::Read(void *,uint)

- ea: `0x1802393e0`
- end: `0x1802396a5`
- name: `?Read@CInternetFile@@UEAAIPEAXI@Z`
- size: `709`
- prototype: `unsigned int __fastcall(CInternetFile *this, void *lpBuf, unsigned int nCount)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180231d70`
- `0x1802393e0`
- `0x18023c2f0`

## import_xrefs

- `VCRUNTIME140!memset` at `0x1802394d4`
- `VCRUNTIME140!memset` at `0x180239590`
- `VCRUNTIME140!memset` at `0x1802395f8`
- `VCRUNTIME140!memset` at `0x180239687`
- `VCRUNTIME140!memset` at `0x1802394d4`
- `VCRUNTIME140!memset` at `0x180239590`
- `VCRUNTIME140!memset` at `0x1802395f8`
- `VCRUNTIME140!memset` at `0x180239687`
- `VCRUNTIME140!memcpy` at `0x18023949d`
- `VCRUNTIME140!memcpy` at `0x180239561`
- `VCRUNTIME140!memcpy` at `0x1802395e1`
- `VCRUNTIME140!memcpy` at `0x180239627`
- `VCRUNTIME140!memcpy` at `0x18023949d`
- `VCRUNTIME140!memcpy` at `0x180239561`
- `VCRUNTIME140!memcpy` at `0x1802395e1`
- `VCRUNTIME140!memcpy` at `0x180239627`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18023967b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180239699`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18023967b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180239699`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802394ec`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18023953d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18023966f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18023968d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802394ec`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18023953d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18023966f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18023968d`
- `WININET!InternetReadFile` at `0x180239427`
- `WININET!InternetReadFile` at `0x1802394bc`
- `WININET!InternetReadFile` at `0x180239578`
- `WININET!InternetReadFile` at `0x180239427`
- `WININET!InternetReadFile` at `0x1802394bc`
- `WININET!InternetReadFile` at `0x180239578`

## pseudocode

```c
__int64 __fastcall CInternetFile::Read(CInternetFile *this, char *lpBuf, unsigned int nCount)
{
  unsigned __int64 v4; // rdi
  void *m_hFile; // rcx
  unsigned __int8 *m_pbReadBuffer; // r9
  __int64 v9; // r12
  signed int v10; // eax
  unsigned __int8 *v11; // r15
  void *v12; // rcx
  __int64 m_nReadBufferPos; // rcx
  unsigned int m_nReadBufferBytes; // edx
  int v15; // edx
  unsigned __int8 *v16; // rbp
  bool v17; // cf
  unsigned __int8 *v18; // r15
  unsigned int v19; // eax
  size_t v20; // rbp
  char *v21; // rcx
  unsigned __int8 *v22; // rdx
  unsigned int dwBytes; // [rsp+50h] [rbp+8h] BYREF
  unsigned int dwRead; // [rsp+68h] [rbp+20h] BYREF

  v4 = nCount;
  if ( !this->m_bReadMode || (m_hFile = this->m_hFile) == 0 )
    AfxThrowInternetException(this->m_dwContext, 6u);
  m_pbReadBuffer = this->m_pbReadBuffer;
  if ( m_pbReadBuffer )
  {
    if ( nCount >= this->m_nReadBufferSize )
    {
      v9 = 0;
      v10 = this->m_nReadBufferBytes - this->m_nReadBufferPos;
      if ( v10 >= 0 )
        v9 = (unsigned int)v10;
      if ( (unsigned int)v9 <= nCount )
      {
        v11 = &m_pbReadBuffer[this->m_nReadBufferPos];
        if ( !(_DWORD)v9 )
        {
LABEL_15:
          v12 = this->m_hFile;
          this->m_nReadBufferPos = this->m_nReadBufferSize;
          if ( !InternetReadFile(v12, &lpBuf[v9], v4 - v9, &dwBytes) )
            AfxThrowInternetException(this->m_dwContext, 0);
          LODWORD(v4) = dwBytes;
          goto LABEL_42;
        }
        if ( lpBuf )
        {
          if ( v11 && nCount >= (unsigned __int64)(unsigned int)v9 )
          {
            memcpy(lpBuf, &m_pbReadBuffer[this->m_nReadBufferPos], (unsigned int)v9);
            goto LABEL_15;
          }
          memset(lpBuf, 0, nCount);
          if ( v11 )
          {
            if ( v4 >= (unsigned int)v9 )
              goto LABEL_64;
            *_errno() = 34;
LABEL_63:
            _invalid_parameter_noinfo();
LABEL_64:
            AfxThrowInvalidArgException();
          }
        }
LABEL_62:
        *_errno() = 22;
        goto LABEL_63;
      }
      return 0;
    }
    m_nReadBufferPos = this->m_nReadBufferPos;
    m_nReadBufferBytes = this->m_nReadBufferBytes;
    if ( (unsigned int)m_nReadBufferPos + nCount < m_nReadBufferBytes )
    {
      v22 = &m_pbReadBuffer[m_nReadBufferPos];
      if ( nCount )
      {
        if ( !lpBuf )
          goto LABEL_62;
        if ( !v22 )
        {
          memset(lpBuf, 0, nCount);
          goto LABEL_62;
        }
        memcpy(lpBuf, v22, nCount);
      }
      this->m_nReadBufferPos += v4;
      return (unsigned int)v4;
    }
    v15 = m_nReadBufferBytes - m_nReadBufferPos;
    v9 = 0;
    if ( v15 >= 0 )
      v9 = (unsigned int)v15;
    if ( (unsigned int)v9 > nCount )
      return 0;
    v16 = &m_pbReadBuffer[m_nReadBufferPos];
    if ( (_DWORD)v9 )
    {
      if ( !lpBuf )
      {
LABEL_26:
        *_errno() = 22;
        goto LABEL_59;
      }
      if ( !v16 || nCount < (unsigned __int64)(unsigned int)v9 )
      {
        memset(lpBuf, 0, nCount);
        if ( !v16 )
          goto LABEL_26;
        v17 = v4 < (unsigned int)v9;
        goto LABEL_57;
      }
      memcpy(lpBuf, &m_pbReadBuffer[m_nReadBufferPos], (unsigned int)v9);
    }
    if ( !InternetReadFile(this->m_hFile, this->m_pbReadBuffer, this->m_nReadBufferSize, &dwRead) )
      AfxThrowInternetException(this->m_dwContext, 0);
    v18 = this->m_pbReadBuffer;
    v19 = v4 - v9;
    v20 = (unsigned int)(v4 - v9);
    if ( (int)v4 - (int)v9 >= dwRead )
      v19 = dwRead;
    this->m_nReadBufferBytes = dwRead;
    v4 = v19;
    v21 = &lpBuf[v9];
    dwRead = v19;
    if ( !v19 )
      goto LABEL_41;
    if ( !v21 )
      goto LABEL_26;
    if ( v18 && v20 >= v19 )
    {
      memcpy(v21, v18, v19);
      LODWORD(v4) = dwRead;
LABEL_41:
      this->m_nReadBufferPos = v4;
LABEL_42:
      LODWORD(v4) = v9 + v4;
      return (unsigned int)v4;
    }
    memset(v21, 0, v20);
    if ( !v18 )
      goto LABEL_26;
    v17 = v20 < v4;
LABEL_57:
    if ( !v17 )
      goto LABEL_60;
    *_errno() = 34;
LABEL_59:
    _invalid_parameter_noinfo();
LABEL_60:
    AfxThrowInvalidArgException();
  }
  if ( !InternetReadFile(m_hFile, lpBuf, nCount, &dwBytes) )
    AfxThrowInternetException(this->m_dwContext, 0);
  return dwBytes;
}

```

## disassembly

```asm
0x1802393e0  mov     [rsp+arg_8], rbx
0x1802393e5  mov     [rsp+arg_10], rbp
0x1802393ea  push    rsi
0x1802393eb  push    rdi
0x1802393ec  push    r12
0x1802393ee  push    r14
0x1802393f0  push    r15
0x1802393f2  sub     rsp, 20h
0x1802393f6  cmp     dword ptr [this+38h], 0
0x1802393fa  mov     rsi, lpBuf
0x1802393fd  mov     edi, nCount
0x180239400  mov     rbx, this
0x180239403  jz      loc_180239637
0x180239409  mov     this, [this+30h]; hFile
0x18023940d  test    this, this
0x180239410  jz      loc_180239637
0x180239416  mov     r9, [rbx+70h]
0x18023941a  test    r9, r9
0x18023941d  jnz     short loc_180239450
0x18023941f  lea     r9, [rsp+48h+dwBytes]; lpdwNumberOfBytesRead
0x180239424  mov     nCount, edi; dwNumberOfBytesToRead
0x180239427  call    cs:__imp_InternetReadFile
0x18023942d  test    eax, eax
0x18023942f  jz      loc_180239646
0x180239435  mov     eax, [rsp+48h+dwBytes]
0x180239439  mov     rbx, [rsp+48h+arg_8]
0x18023943e  mov     rbp, [rsp+48h+arg_10]
0x180239443  add     rsp, 20h
0x180239447  pop     r15
0x180239449  pop     r14
0x18023944b  pop     r12
0x18023944d  pop     rdi
0x18023944e  pop     rsi
0x18023944f  retn
0x180239450  cmp     edi, [rbx+68h]
0x180239453  jb      loc_180239506
0x180239459  mov     eax, [rbx+78h]
0x18023945c  mov     r12d, 0
0x180239462  sub     eax, [rbx+6Ch]
0x180239465  cmovns  r12d, eax
0x180239469  cmp     r12d, edi
0x18023946c  ja      loc_180239608
0x180239472  mov     r15d, [rbx+6Ch]
0x180239476  add     r15, r9
0x180239479  mov     r14d, r12d
0x18023947c  test    r12d, r12d
0x18023947f  jz      short loc_1802394A3
0x180239481  test    rsi, rsi
0x180239484  jz      loc_18023968D
0x18023948a  test    r15, r15
0x18023948d  jz      short loc_1802394CC
0x18023948f  cmp     rdi, r14
0x180239492  jb      short loc_1802394CC
0x180239494  mov     nCount, r14d; Size
0x180239497  mov     lpBuf, r15; Src
0x18023949a  mov     this, rsi; void *
0x18023949d  call    cs:__imp_memcpy
0x1802394a3  mov     eax, [rbx+68h]
0x1802394a6  lea     lpBuf, [r12+rsi]; lpBuffer
0x1802394aa  mov     this, [rbx+30h]; hFile
0x1802394ae  lea     r9, [rsp+48h+dwBytes]; lpdwNumberOfBytesRead
0x1802394b3  sub     edi, r12d
0x1802394b6  mov     [rbx+6Ch], eax
0x1802394b9  mov     nCount, edi; dwNumberOfBytesToRead
0x1802394bc  call    cs:__imp_InternetReadFile
0x1802394c2  test    eax, eax
0x1802394c4  jz      loc_180239652
0x1802394ca  jmp     short loc_1802394FD
0x1802394cc  mov     r8, rdi; Size
0x1802394cf  xor     edx, edx; Val
0x1802394d1  mov     this, rsi; void *
0x1802394d4  call    cs:__imp_memset
0x1802394da  test    r15, r15
0x1802394dd  jz      loc_18023968D
0x1802394e3  cmp     rdi, r14
0x1802394e6  jnb     loc_18023969F
0x1802394ec  call    cs:__imp__errno
0x1802394f2  mov     dword ptr [rax], 22h ; '"'
0x1802394f8  jmp     loc_180239699
0x1802394fd  mov     edi, [rsp+48h+dwBytes]
0x180239501  jmp     loc_1802395EE
0x180239506  mov     ecx, [rbx+6Ch]
0x180239509  mov     edx, [rbx+78h]
0x18023950c  lea     eax, [this+rdi]
0x18023950f  cmp     eax, edx
0x180239511  jb      loc_18023960F
0x180239517  sub     edx, ecx
0x180239519  mov     r12d, 0
0x18023951f  cmovns  r12d, edx
0x180239523  cmp     r12d, edi
0x180239526  ja      loc_180239608
0x18023952c  mov     r14d, r12d
0x18023952f  lea     rbp, [r9+this]
0x180239533  test    r12d, r12d
0x180239536  jz      short loc_180239567
0x180239538  test    rsi, rsi
0x18023953b  jnz     short loc_18023954E
0x18023953d  call    cs:__imp__errno
0x180239543  mov     dword ptr [rax], 16h
0x180239549  jmp     loc_18023967B
0x18023954e  test    rbp, rbp
0x180239551  jz      short loc_180239588
0x180239553  cmp     rdi, r14
0x180239556  jb      short loc_180239588
0x180239558  mov     r8, r14; Size
0x18023955b  mov     lpBuf, rbp; Src
0x18023955e  mov     this, rsi; void *
0x180239561  call    cs:__imp_memcpy
0x180239567  mov     nCount, [rbx+68h]; dwNumberOfBytesToRead
0x18023956b  lea     r9, [rsp+48h+dwRead]; lpdwNumberOfBytesRead
0x180239570  mov     lpBuf, [rbx+70h]; lpBuffer
0x180239574  mov     this, [rbx+30h]; hFile
0x180239578  call    cs:__imp_InternetReadFile
0x18023957e  test    eax, eax
0x180239580  jz      loc_18023965E
0x180239586  jmp     short loc_1802395A3
0x180239588  mov     r8, rdi; Size
0x18023958b  xor     edx, edx; Val
0x18023958d  mov     this, rsi; void *
0x180239590  call    cs:__imp_memset
0x180239596  test    rbp, rbp
0x180239599  jz      short loc_18023953D
0x18023959b  cmp     rdi, r14
0x18023959e  jmp     loc_18023966D
0x1802395a3  mov     ecx, [rsp+48h+dwRead]
0x1802395a7  sub     edi, r12d
0x1802395aa  mov     r15, [rbx+70h]
0x1802395ae  cmp     edi, ecx
0x1802395b0  mov     eax, edi
0x1802395b2  mov     ebp, edi
0x1802395b4  cmovnb  eax, ecx
0x1802395b7  mov     [rbx+78h], ecx
0x1802395ba  mov     edi, eax
0x1802395bc  lea     this, [r12+rsi]; void *
0x1802395c0  mov     [rsp+48h+dwRead], edi
0x1802395c4  test    eax, eax
0x1802395c6  jz      short loc_1802395EB
0x1802395c8  test    this, this
0x1802395cb  jz      loc_18023953D
0x1802395d1  test    r15, r15
0x1802395d4  jz      short loc_1802395F3
0x1802395d6  cmp     rbp, rdi
0x1802395d9  jb      short loc_1802395F3
0x1802395db  mov     nCount, edi; Size
0x1802395de  mov     lpBuf, r15; Src
0x1802395e1  call    cs:__imp_memcpy
0x1802395e7  mov     edi, [rsp+48h+dwRead]
0x1802395eb  mov     [rbx+6Ch], edi
0x1802395ee  add     edi, r12d
0x1802395f1  jmp     short loc_180239630
0x1802395f3  mov     r8, rbp; Size
0x1802395f6  xor     edx, edx; Val
0x1802395f8  call    cs:__imp_memset
0x1802395fe  test    r15, r15
0x180239601  jnz     short loc_18023966A
0x180239603  jmp     loc_18023953D
0x180239608  xor     eax, eax
0x18023960a  jmp     loc_180239439
0x18023960f  lea     lpBuf, [r9+this]; Val
0x180239613  mov     r8, rdi; Size
0x180239616  test    edi, edi
0x180239618  jz      short loc_18023962D
0x18023961a  test    rsi, rsi
0x18023961d  jz      short loc_18023968D
0x18023961f  mov     this, rsi; void *
0x180239622  test    lpBuf, lpBuf
0x180239625  jz      short loc_180239687
0x180239627  call    cs:__imp_memcpy
0x18023962d  add     [rbx+6Ch], edi
0x180239630  mov     eax, edi
0x180239632  jmp     loc_180239439
0x180239637  mov     this, [rbx+40h]; dwContext
0x18023963b  mov     edx, 6; dwError
0x180239640  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x180239646  mov     this, [rbx+40h]; dwContext
0x18023964a  xor     edx, edx; dwError
0x18023964c  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x180239652  mov     this, [rbx+40h]; dwContext
0x180239656  xor     edx, edx; dwError
0x180239658  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x18023965e  mov     this, [rbx+40h]; dwContext
0x180239662  xor     edx, edx; dwError
0x180239664  call    ?AfxThrowInternetException@@YAX_KK@Z; AfxThrowInternetException(unsigned __int64,ulong)
0x18023966a  cmp     rbp, rdi
0x18023966d  jnb     short loc_180239681
0x18023966f  call    cs:__imp__errno
0x180239675  mov     dword ptr [rax], 22h ; '"'
0x18023967b  call    cs:__imp__invalid_parameter_noinfo
0x180239681  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180239687  call    cs:__imp_memset
0x18023968d  call    cs:__imp__errno
0x180239693  mov     dword ptr [rax], 16h
0x180239699  call    cs:__imp__invalid_parameter_noinfo
0x18023969f  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
