# AES_PROVIDER_ENTRY::DecryptValueInternal(ushort const *,STRU *,EncryptionProviderErrorType *)

- ea: `0x1800491b0`
- end: `0x18004938b`
- name: `?DecryptValueInternal@AES_PROVIDER_ENTRY@@UEAAJPEBGPEAVSTRU@@PEAW4EncryptionProviderErrorType@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(AES_PROVIDER_ENTRY *__hidden this, const unsigned __int16 *, struct STRU *, enum EncryptionProviderErrorType *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800491b0`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004926f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004926f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180049249`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180049249`
- `iisutil!uudecode` at `0x18004925f`
- `iisutil!uudecode` at `0x18004925f`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180049234`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180049234`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180049362`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180049362`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800491f6`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800491f6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180049357`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180049357`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049292`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800492e6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004930d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004933b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049292`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800492e6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004930d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004933b`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180049201`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180049201`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004931a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004931a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004932e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004932e`
- `CRYPTSP!CryptDecrypt` at `0x1800492bd`
- `CRYPTSP!CryptDecrypt` at `0x1800492bd`

## pseudocode

```c
__int64 __fastcall AES_PROVIDER_ENTRY::DecryptValueInternal(
        AES_PROVIDER_ENTRY *this,
        const unsigned __int16 *a2,
        struct STRU *a3,
        enum EncryptionProviderErrorType *a4)
{
  signed int v8; // ebx
  char *Str; // rax
  signed int LastError; // eax
  BYTE *pbData; // rax
  unsigned __int64 v12; // rbx
  _WORD *Ptr; // rax
  unsigned __int64 v14; // rbx
  const unsigned __int16 *v15; // rax
  __int64 Size; // rdi
  _BYTE *i; // rax
  DWORD pdwDataLen; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[48]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v21[56]; // [rsp+68h] [rbp-98h] BYREF
  char v22[256]; // [rsp+A0h] [rbp-60h] BYREF

  STRA::STRA((STRA *)v21, v22, 0x100u);
  BUFFER::BUFFER((BUFFER *)v20);
  pdwDataLen = 0;
  if ( !a2 || !a3 )
  {
    v8 = -2147024809;
    goto LABEL_20;
  }
  v8 = *((_DWORD *)this + 15);
  if ( v8 >= 0 )
  {
    v8 = STRA::CopyWTruncate((STRA *)v21, a2);
    if ( v8 >= 0 )
    {
      Str = STRA::QueryStr((STRA *)v21);
      if ( !uudecode(Str, (struct BUFFER *)v20, &pdwDataLen, 0) )
      {
        *(_DWORD *)a4 = 3;
        goto LABEL_7;
      }
      pbData = (BYTE *)BUFFER::QueryPtr((BUFFER *)v20);
      if ( !CryptDecrypt(*((_QWORD *)this + 6), 0, 1, *((_DWORD *)this + 14) != 0 ? 0x40 : 0, pbData, &pdwDataLen) )
      {
        *(_DWORD *)a4 = 14;
LABEL_7:
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_20;
      }
      if ( pdwDataLen < 4 )
        goto LABEL_12;
      v12 = pdwDataLen;
      Ptr = BUFFER::QueryPtr((BUFFER *)v20);
      v14 = v12 >> 1;
      if ( !v14 )
        goto LABEL_12;
      while ( *Ptr )
      {
        ++Ptr;
        if ( !--v14 )
          goto LABEL_12;
      }
      if ( Ptr )
      {
        v15 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v20);
        v8 = STRU::Copy(a3, v15 + 2);
      }
      else
      {
LABEL_12:
        v8 = -2147024883;
      }
    }
  }
LABEL_20:
  Size = BUFFER::QuerySize((BUFFER *)v20);
  for ( i = BUFFER::QueryPtr((BUFFER *)v20); Size; --Size )
    *i++ = 0;
  BUFFER::~BUFFER((BUFFER *)v20);
  STRA::~STRA((STRA *)v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800491b0  push    rbp
0x1800491b2  push    rbx
0x1800491b3  push    rsi
0x1800491b4  push    rdi
0x1800491b5  push    r12
0x1800491b7  push    r14
0x1800491b9  push    r15
0x1800491bb  lea     rbp, [rsp-0B0h]
0x1800491c3  sub     rsp, 1B0h
0x1800491ca  mov     rax, cs:__security_cookie
0x1800491d1  xor     rax, rsp
0x1800491d4  mov     [rbp+0E0h+var_40], rax
0x1800491db  mov     r14, r8
0x1800491de  mov     r15, rdx
0x1800491e1  mov     rsi, rcx
0x1800491e4  lea     rdx, [rbp+0E0h+var_140]
0x1800491e8  mov     r8d, 100h
0x1800491ee  lea     rcx, [rsp+1E0h+var_178]
0x1800491f3  mov     rdi, r9
0x1800491f6  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800491fc  lea     rcx, [rsp+1E0h+var_1A8]
0x180049201  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180049207  xor     r12d, r12d
0x18004920a  mov     [rsp+1E0h+var_1B0], r12d
0x18004920f  test    r15, r15
0x180049212  jz      loc_180049324
0x180049218  test    r14, r14
0x18004921b  jz      loc_180049324
0x180049221  mov     ebx, [rsi+3Ch]
0x180049224  test    ebx, ebx
0x180049226  js      loc_180049329
0x18004922c  mov     rdx, r15
0x18004922f  lea     rcx, [rsp+1E0h+var_178]
0x180049234  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x18004923a  mov     ebx, eax
0x18004923c  test    eax, eax
0x18004923e  js      loc_180049329
0x180049244  lea     rcx, [rsp+1E0h+var_178]
0x180049249  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18004924f  xor     r9d, r9d
0x180049252  lea     r8, [rsp+1E0h+var_1B0]
0x180049257  mov     rcx, rax
0x18004925a  lea     rdx, [rsp+1E0h+var_1A8]
0x18004925f  call    cs:__imp_?uudecode@@YAHPEADPEAVBUFFER@@PEAKH@Z; uudecode(char *,BUFFER *,ulong *,int)
0x180049265  test    eax, eax
0x180049267  jnz     short loc_18004928D
0x180049269  mov     dword ptr [rdi], 3
0x18004926f  call    cs:__imp_GetLastError
0x180049275  mov     ebx, eax
0x180049277  test    eax, eax
0x180049279  jle     loc_180049329
0x18004927f  movzx   ebx, ax
0x180049282  or      ebx, 80070000h
0x180049288  jmp     loc_180049329
0x18004928d  lea     rcx, [rsp+1E0h+var_1A8]
0x180049292  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180049298  mov     edx, [rsi+38h]
0x18004929b  lea     rcx, [rsp+1E0h+var_1B0]
0x1800492a0  neg     edx
0x1800492a2  mov     [rsp+1E0h+pdwDataLen], rcx; pdwDataLen
0x1800492a7  mov     rcx, [rsi+30h]; hKey
0x1800492ab  sbb     r9d, r9d
0x1800492ae  mov     [rsp+1E0h+pbData], rax; pbData
0x1800492b3  xor     edx, edx; hHash
0x1800492b5  and     r9d, 40h; dwFlags
0x1800492b9  lea     r8d, [rdx+1]; Final
0x1800492bd  call    cs:__imp_CryptDecrypt
0x1800492c3  test    eax, eax
0x1800492c5  jnz     short loc_1800492CF
0x1800492c7  mov     dword ptr [rdi], 0Eh
0x1800492cd  jmp     short loc_18004926F
0x1800492cf  cmp     [rsp+1E0h+var_1B0], 4
0x1800492d4  jnb     short loc_1800492DD
0x1800492d6  mov     ebx, 8007000Dh
0x1800492db  jmp     short loc_180049329
0x1800492dd  mov     ebx, [rsp+1E0h+var_1B0]
0x1800492e1  lea     rcx, [rsp+1E0h+var_1A8]
0x1800492e6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800492ec  shr     rbx, 1
0x1800492ef  jz      short loc_1800492D6
0x1800492f1  cmp     [rax], r12w
0x1800492f5  jz      short loc_180049303
0x1800492f7  add     rax, 2
0x1800492fb  sub     rbx, 1
0x1800492ff  jnz     short loc_1800492F1
0x180049301  jmp     short loc_1800492D6
0x180049303  test    rax, rax
0x180049306  jz      short loc_1800492D6
0x180049308  lea     rcx, [rsp+1E0h+var_1A8]
0x18004930d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180049313  mov     rcx, r14
0x180049316  lea     rdx, [rax+4]
0x18004931a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180049320  mov     ebx, eax
0x180049322  jmp     short loc_180049329
0x180049324  mov     ebx, 80070057h
0x180049329  lea     rcx, [rsp+1E0h+var_1A8]
0x18004932e  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180049334  lea     rcx, [rsp+1E0h+var_1A8]
0x180049339  mov     edi, eax
0x18004933b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180049341  test    rdi, rdi
0x180049344  jz      short loc_180049352
0x180049346  mov     [rax], r12b
0x180049349  inc     rax
0x18004934c  sub     rdi, 1
0x180049350  jnz     short loc_180049346
0x180049352  lea     rcx, [rsp+1E0h+var_1A8]
0x180049357  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004935d  lea     rcx, [rsp+1E0h+var_178]
0x180049362  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180049368  mov     eax, ebx
0x18004936a  mov     rcx, [rbp+0E0h+var_40]
0x180049371  xor     rcx, rsp; StackCookie
0x180049374  call    __security_check_cookie
0x180049379  add     rsp, 1B0h
0x180049380  pop     r15
0x180049382  pop     r14
0x180049384  pop     r12
0x180049386  pop     rdi
0x180049387  pop     rsi
0x180049388  pop     rbx
0x180049389  pop     rbp
0x18004938a  retn
```
