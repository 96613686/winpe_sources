# AES_PROVIDER_ENTRY::EncryptValueInternal(ushort const *,STRU *,EncryptionProviderErrorType *)

- ea: `0x1800493a0`
- end: `0x1800496d9`
- name: `?EncryptValueInternal@AES_PROVIDER_ENTRY@@UEAAJPEBGPEAVSTRU@@PEAW4EncryptionProviderErrorType@@@Z`
- size: `825`
- prototype: `int(AES_PROVIDER_ENTRY *__hidden this, const unsigned __int16 *, struct STRU *, enum EncryptionProviderErrorType *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800493a0`
- `0x180059bd2`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004949d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004949d`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180049685`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180049685`
- `iisutil!uuencode` at `0x18004964a`
- `iisutil!uuencode` at `0x18004964a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180049699`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800496a3`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800496ae`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180049699`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800496a3`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800496ae`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800494f3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049514`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004952e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800495ba`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800495c8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800495f3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049638`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049679`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800494f3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049514`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004952e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800495ba`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800495c8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800495f3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049638`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049679`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180049400`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180049425`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004944b`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180049400`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180049425`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004944b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800494e4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800495a7`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800494e4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800495a7`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800495e6`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180049663`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800495e6`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180049663`
- `CRYPTSP!CryptGenRandom` at `0x18004948d`
- `CRYPTSP!CryptGenRandom` at `0x180049505`
- `CRYPTSP!CryptGenRandom` at `0x180049541`
- `CRYPTSP!CryptGenRandom` at `0x18004948d`
- `CRYPTSP!CryptGenRandom` at `0x180049505`
- `CRYPTSP!CryptGenRandom` at `0x180049541`
- `CRYPTSP!CryptEncrypt` at `0x180049589`
- `CRYPTSP!CryptEncrypt` at `0x180049621`
- `CRYPTSP!CryptEncrypt` at `0x180049589`
- `CRYPTSP!CryptEncrypt` at `0x180049621`

## pseudocode

```c
__int64 __fastcall AES_PROVIDER_ENTRY::EncryptValueInternal(
        AES_PROVIDER_ENTRY *this,
        const unsigned __int16 *a2,
        struct STRU *a3,
        enum EncryptionProviderErrorType *a4)
{
  HCRYPTPROV v8; // rcx
  unsigned int v9; // ebx
  signed int LastError; // eax
  DWORD v11; // ebx
  __int64 v12; // rax
  size_t v13; // r14
  BYTE *Ptr; // rax
  char *v15; // rax
  BYTE *v16; // rax
  size_t v17; // r14
  HCRYPTKEY v18; // rcx
  bool v19; // cf
  const void *dwBufLen; // rbx
  void *v21; // rax
  BYTE *pbData; // rax
  DWORD v23; // ebx
  unsigned __int8 *v24; // rax
  const char *v25; // rax
  BYTE pbBuffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwDataLen; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v29[48]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v30[48]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v31[56]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 v32[256]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int8 v33[256]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int8 v34[256]; // [rsp+2E0h] [rbp+1E0h] BYREF

  pdwDataLen = 0;
  memset_0(v32, 0, sizeof(v32));
  BUFFER::BUFFER((BUFFER *)v30, v32, 0x100u);
  memset_0(v33, 0, sizeof(v33));
  BUFFER::BUFFER((BUFFER *)v31, v33, 0x100u);
  memset_0(v34, 0, sizeof(v34));
  BUFFER::BUFFER((BUFFER *)v29, v34, 0x100u);
  pbBuffer[0] = 0;
  if ( !a2 || !a3 )
  {
    v9 = -2147024809;
    goto LABEL_26;
  }
  v8 = *((_QWORD *)this + 5);
  if ( !v8 )
  {
    v9 = -2146893802;
    if ( *((int *)this + 15) < 0 )
      v9 = *((_DWORD *)this + 15);
    goto LABEL_26;
  }
  if ( !CryptGenRandom(v8, 1u, pbBuffer) )
    goto LABEL_8;
  v11 = pbBuffer[0] & 0xF;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  v13 = 2 * v12 + 2;
  if ( BUFFER::Resize((BUFFER *)v29, v13 + v11 + 4) )
  {
    Ptr = (BYTE *)BUFFER::QueryPtr((BUFFER *)v29);
    if ( !CryptGenRandom(*((_QWORD *)this + 5), 4u, Ptr)
      || (v15 = (char *)BUFFER::QueryPtr((BUFFER *)v29),
          memcpy_0(v15 + 4, a2, v13),
          v16 = (BYTE *)BUFFER::QueryPtr((BUFFER *)v29),
          !CryptGenRandom(*((_QWORD *)this + 5), v11, &v16[v13 + 4])) )
    {
LABEL_8:
      *(_DWORD *)a4 = 16;
      goto LABEL_9;
    }
    v17 = v11 + 4 + v13;
    v18 = *((_QWORD *)this + 6);
    v19 = *((_DWORD *)this + 14) != 0;
    pdwDataLen = v17;
    if ( !CryptEncrypt(v18, 0, 1, v19 ? 0x40 : 0, 0, &pdwDataLen, 0) )
      goto LABEL_17;
    if ( BUFFER::Resize((BUFFER *)v30, pdwDataLen) )
    {
      dwBufLen = BUFFER::QueryPtr((BUFFER *)v29);
      v21 = BUFFER::QueryPtr((BUFFER *)v30);
      memcpy_0(v21, dwBufLen, v17);
      pdwDataLen = v17;
      LODWORD(dwBufLen) = BUFFER::QuerySize((BUFFER *)v30);
      pbData = (BYTE *)BUFFER::QueryPtr((BUFFER *)v30);
      if ( CryptEncrypt(
             *((_QWORD *)this + 6),
             0,
             1,
             *((_DWORD *)this + 14) != 0 ? 0x40 : 0,
             pbData,
             &pdwDataLen,
             (DWORD)dwBufLen) )
      {
        v23 = pdwDataLen;
        v24 = (unsigned __int8 *)BUFFER::QueryPtr((BUFFER *)v30);
        if ( uuencode(v24, v23, (struct BUFFER *)v31, 0) )
        {
          if ( BUFFER::QuerySize((BUFFER *)v31) >= 8 )
          {
            v25 = (const char *)BUFFER::QueryPtr((BUFFER *)v31);
            v9 = STRU::CopyA(a3, v25);
          }
          else
          {
            v9 = -2147024883;
          }
          goto LABEL_26;
        }
        *(_DWORD *)a4 = 2;
        goto LABEL_9;
      }
LABEL_17:
      *(_DWORD *)a4 = 13;
    }
  }
LABEL_9:
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_26:
  BUFFER::~BUFFER((BUFFER *)v29);
  BUFFER::~BUFFER((BUFFER *)v31);
  BUFFER::~BUFFER((BUFFER *)v30);
  return v9;
}

```

## disassembly

```asm
0x1800493a0  push    rbp
0x1800493a2  push    rbx
0x1800493a3  push    rsi
0x1800493a4  push    rdi
0x1800493a5  push    r12
0x1800493a7  push    r13
0x1800493a9  push    r14
0x1800493ab  push    r15
0x1800493ad  lea     rbp, [rsp-2F8h]
0x1800493b5  sub     rsp, 3F8h
0x1800493bc  mov     rax, cs:__security_cookie
0x1800493c3  xor     rax, rsp
0x1800493c6  mov     [rbp+330h+var_50], rax
0x1800493cd  mov     r15, r8
0x1800493d0  mov     r12, rdx
0x1800493d3  mov     rsi, rcx
0x1800493d6  mov     ebx, 100h
0x1800493db  xor     r13d, r13d
0x1800493de  lea     rcx, [rbp+330h+var_350]; void *
0x1800493e2  mov     r8d, ebx; Size
0x1800493e5  mov     [rsp+430h+var_3EC], r13d
0x1800493ea  xor     edx, edx; Val
0x1800493ec  mov     rdi, r9
0x1800493ef  call    memset_0
0x1800493f4  mov     r8d, ebx
0x1800493f7  lea     rdx, [rbp+330h+var_350]
0x1800493fb  lea     rcx, [rsp+430h+var_3B8]
0x180049400  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180049406  mov     r8d, ebx; Size
0x180049409  lea     rcx, [rbp+330h+var_250]; void *
0x180049410  xor     edx, edx; Val
0x180049412  call    memset_0
0x180049417  mov     r8d, ebx
0x18004941a  lea     rdx, [rbp+330h+var_250]
0x180049421  lea     rcx, [rbp+330h+var_388]
0x180049425  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18004942b  mov     r8d, ebx; Size
0x18004942e  lea     rcx, [rbp+330h+var_150]; void *
0x180049435  xor     edx, edx; Val
0x180049437  call    memset_0
0x18004943c  mov     r8d, ebx
0x18004943f  lea     rdx, [rbp+330h+var_150]
0x180049446  lea     rcx, [rsp+430h+var_3E8]
0x18004944b  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180049451  mov     [rsp+430h+pbBuffer], r13b
0x180049456  test    r12, r12
0x180049459  jz      loc_18004968F
0x18004945f  test    r15, r15
0x180049462  jz      loc_18004968F
0x180049468  mov     rcx, [rsi+28h]; hProv
0x18004946c  test    rcx, rcx
0x18004946f  jnz     short loc_180049483
0x180049471  cmp     [rsi+3Ch], r13d
0x180049475  mov     ebx, 80090016h
0x18004947a  cmovl   ebx, [rsi+3Ch]
0x18004947e  jmp     loc_180049694
0x180049483  lea     r8, [rsp+430h+pbBuffer]; pbBuffer
0x180049488  mov     edx, 1; dwLen
0x18004948d  call    cs:__imp_CryptGenRandom
0x180049493  test    eax, eax
0x180049495  jnz     short loc_1800494BB
0x180049497  mov     dword ptr [rdi], 10h
0x18004949d  call    cs:__imp_GetLastError
0x1800494a3  mov     ebx, eax
0x1800494a5  test    eax, eax
0x1800494a7  jle     loc_180049694
0x1800494ad  movzx   ebx, ax
0x1800494b0  or      ebx, 80070000h
0x1800494b6  jmp     loc_180049694
0x1800494bb  movzx   ebx, [rsp+430h+pbBuffer]
0x1800494c0  and     ebx, 0Fh
0x1800494c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800494c7  inc     rax
0x1800494ca  cmp     [r12+rax*2], r13w
0x1800494cf  jnz     short loc_1800494C7
0x1800494d1  lea     r14, ds:2[rax*2]
0x1800494d9  lea     edx, [rbx+4]
0x1800494dc  add     edx, r14d
0x1800494df  lea     rcx, [rsp+430h+var_3E8]
0x1800494e4  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800494ea  test    al, al
0x1800494ec  jz      short loc_18004949D
0x1800494ee  lea     rcx, [rsp+430h+var_3E8]
0x1800494f3  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800494f9  mov     rcx, [rsi+28h]; hProv
0x1800494fd  mov     edx, 4; dwLen
0x180049502  mov     r8, rax; pbBuffer
0x180049505  call    cs:__imp_CryptGenRandom
0x18004950b  test    eax, eax
0x18004950d  jz      short loc_180049497
0x18004950f  lea     rcx, [rsp+430h+var_3E8]
0x180049514  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004951a  mov     r8, r14; Size
0x18004951d  mov     rdx, r12; Src
0x180049520  lea     rcx, [rax+4]; void *
0x180049524  call    memcpy_0
0x180049529  lea     rcx, [rsp+430h+var_3E8]
0x18004952e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180049534  mov     rcx, [rsi+28h]; hProv
0x180049538  mov     edx, ebx; dwLen
0x18004953a  lea     r8, [rax+4]
0x18004953e  add     r8, r14; pbBuffer
0x180049541  call    cs:__imp_CryptGenRandom
0x180049547  test    eax, eax
0x180049549  jz      loc_180049497
0x18004954f  mov     eax, [rsi+38h]
0x180049552  lea     ecx, [rbx+4]
0x180049555  add     r14, rcx
0x180049558  mov     [rsp+430h+dwBufLen], r13d; dwBufLen
0x18004955d  mov     rcx, [rsi+30h]; hKey
0x180049561  neg     eax
0x180049563  lea     rax, [rsp+430h+var_3EC]
0x180049568  mov     [rsp+430h+var_3EC], r14d
0x18004956d  sbb     r9d, r9d
0x180049570  mov     [rsp+430h+pdwDataLen], rax; pdwDataLen
0x180049575  mov     r12d, 1
0x18004957b  mov     [rsp+430h+pbData], r13; pbData
0x180049580  and     r9d, 40h; dwFlags
0x180049584  mov     r8d, r12d; Final
0x180049587  xor     edx, edx; hHash
0x180049589  call    cs:__imp_CryptEncrypt
0x18004958f  test    eax, eax
0x180049591  jnz     short loc_18004959E
0x180049593  mov     dword ptr [rdi], 0Dh
0x180049599  jmp     loc_18004949D
0x18004959e  mov     edx, [rsp+430h+var_3EC]
0x1800495a2  lea     rcx, [rsp+430h+var_3B8]
0x1800495a7  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800495ad  test    al, al
0x1800495af  jz      loc_18004949D
0x1800495b5  lea     rcx, [rsp+430h+var_3E8]
0x1800495ba  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800495c0  lea     rcx, [rsp+430h+var_3B8]
0x1800495c5  mov     rbx, rax
0x1800495c8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800495ce  mov     r8, r14; Size
0x1800495d1  mov     rdx, rbx; Src
0x1800495d4  mov     rcx, rax; void *
0x1800495d7  call    memcpy_0
0x1800495dc  lea     rcx, [rsp+430h+var_3B8]
0x1800495e1  mov     [rsp+430h+var_3EC], r14d
0x1800495e6  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800495ec  lea     rcx, [rsp+430h+var_3B8]
0x1800495f1  mov     ebx, eax
0x1800495f3  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800495f9  mov     ecx, [rsi+38h]
0x1800495fc  mov     r8d, r12d; Final
0x1800495ff  neg     ecx
0x180049601  mov     [rsp+430h+dwBufLen], ebx; dwBufLen
0x180049605  lea     rcx, [rsp+430h+var_3EC]
0x18004960a  sbb     r9d, r9d
0x18004960d  mov     [rsp+430h+pdwDataLen], rcx; pdwDataLen
0x180049612  mov     rcx, [rsi+30h]; hKey
0x180049616  and     r9d, 40h; dwFlags
0x18004961a  xor     edx, edx; hHash
0x18004961c  mov     [rsp+430h+pbData], rax; pbData
0x180049621  call    cs:__imp_CryptEncrypt
0x180049627  test    eax, eax
0x180049629  jz      loc_180049593
0x18004962f  mov     ebx, [rsp+430h+var_3EC]
0x180049633  lea     rcx, [rsp+430h+var_3B8]
0x180049638  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004963e  xor     r9d, r9d
0x180049641  lea     r8, [rbp+330h+var_388]
0x180049645  mov     rcx, rax
0x180049648  mov     edx, ebx
0x18004964a  call    cs:__imp_?uuencode@@YAHPEAEKPEAVBUFFER@@H@Z; uuencode(uchar *,ulong,BUFFER *,int)
0x180049650  test    eax, eax
0x180049652  jnz     short loc_18004965F
0x180049654  mov     dword ptr [rdi], 2
0x18004965a  jmp     loc_18004949D
0x18004965f  lea     rcx, [rbp+330h+var_388]
0x180049663  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180049669  cmp     eax, 8
0x18004966c  jnb     short loc_180049675
0x18004966e  mov     ebx, 8007000Dh
0x180049673  jmp     short loc_180049694
0x180049675  lea     rcx, [rbp+330h+var_388]
0x180049679  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004967f  mov     rdx, rax
0x180049682  mov     rcx, r15
0x180049685  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18004968b  mov     ebx, eax
0x18004968d  jmp     short loc_180049694
0x18004968f  mov     ebx, 80070057h
0x180049694  lea     rcx, [rsp+430h+var_3E8]
0x180049699  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004969f  lea     rcx, [rbp+330h+var_388]
0x1800496a3  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800496a9  lea     rcx, [rsp+430h+var_3B8]
0x1800496ae  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800496b4  mov     eax, ebx
0x1800496b6  mov     rcx, [rbp+330h+var_50]
0x1800496bd  xor     rcx, rsp; StackCookie
0x1800496c0  call    __security_check_cookie
0x1800496c5  add     rsp, 3F8h
0x1800496cc  pop     r15
0x1800496ce  pop     r14
0x1800496d0  pop     r13
0x1800496d2  pop     r12
0x1800496d4  pop     rdi
0x1800496d5  pop     rsi
0x1800496d6  pop     rbx
0x1800496d7  pop     rbp
0x1800496d8  retn
```
