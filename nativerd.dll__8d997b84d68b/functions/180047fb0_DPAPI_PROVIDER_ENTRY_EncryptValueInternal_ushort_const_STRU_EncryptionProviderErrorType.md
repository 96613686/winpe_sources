# DPAPI_PROVIDER_ENTRY::EncryptValueInternal(ushort const *,STRU *,EncryptionProviderErrorType *)

- ea: `0x180047fb0`
- end: `0x180048197`
- name: `?EncryptValueInternal@DPAPI_PROVIDER_ENTRY@@UEAAJPEBGPEAVSTRU@@PEAW4EncryptionProviderErrorType@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(DPAPI_PROVIDER_ENTRY *__hidden this, const unsigned __int16 *, struct STRU *, enum EncryptionProviderErrorType *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180047fb0`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800480f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800480f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048157`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048157`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18004813e`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18004813e`
- `iisutil!uuencode` at `0x18004811b`
- `iisutil!uuencode` at `0x18004811b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18004816c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18004816c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180047ffc`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180047ffc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180048162`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180048162`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180048132`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180048132`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004801c`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004801c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180048053`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180048066`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18004808a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180048053`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180048066`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18004808a`
- `CRYPT32!CryptProtectData` at `0x1800480e3`
- `CRYPT32!CryptProtectData` at `0x1800480e3`

## pseudocode

```c
__int64 __fastcall DPAPI_PROVIDER_ENTRY::EncryptValueInternal(
        DPAPI_PROVIDER_ENTRY *this,
        BYTE *a2,
        struct STRU *a3,
        enum EncryptionProviderErrorType *a4)
{
  __int64 v8; // rbx
  const unsigned __int16 *Str; // rcx
  __int64 v10; // rax
  DATA_BLOB *v11; // r8
  signed int LastError; // eax
  unsigned int v13; // ebx
  const char *Ptr; // rax
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B0h] BYREF
  DATA_BLOB pDataIn; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v21[256]; // [rsp+E0h] [rbp-20h] BYREF
  char v22[256]; // [rsp+1E0h] [rbp+E0h] BYREF

  STRA::STRA((STRA *)v20, v22, 0x100u);
  memset_0(v21, 0, sizeof(v21));
  BUFFER::BUFFER((BUFFER *)v19, v21, 0x100u);
  pDataIn = 0;
  pDataOut = 0;
  v17 = 0;
  if ( a2 && a3 )
  {
    v8 = -1;
    if ( *STRU::QueryStr((DPAPI_PROVIDER_ENTRY *)((char *)this + 40)) )
    {
      Str = STRU::QueryStr((DPAPI_PROVIDER_ENTRY *)((char *)this + 40));
      v10 = -1;
      do
        ++v10;
      while ( Str[v10] );
      LODWORD(v17) = 2 * v10 + 2;
      *((_QWORD *)&v17 + 1) = STRU::QueryStr((DPAPI_PROVIDER_ENTRY *)((char *)this + 40));
      v11 = (DATA_BLOB *)&v17;
    }
    else
    {
      v11 = 0;
    }
    do
      ++v8;
    while ( *(_WORD *)&a2[2 * v8] );
    pDataIn.pbData = a2;
    pDataIn.cbData = 2 * v8 + 2;
    if ( CryptProtectData(&pDataIn, 0, v11, 0, 0, *((_DWORD *)this + 24) != 0 ? 5 : 1, &pDataOut) )
    {
      if ( uuencode(pDataOut.pbData, pDataOut.cbData, (struct BUFFER *)v19, 0) )
      {
        Ptr = (const char *)BUFFER::QueryPtr((BUFFER *)v19);
        v13 = STRU::CopyA(a3, Ptr);
        goto LABEL_17;
      }
      *(_DWORD *)a4 = 2;
    }
    else
    {
      *(_DWORD *)a4 = 11;
    }
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v13 = -2147024809;
  }
LABEL_17:
  if ( pDataOut.pbData )
    LocalFree(pDataOut.pbData);
  BUFFER::~BUFFER((BUFFER *)v19);
  STRA::~STRA((STRA *)v20);
  return v13;
}

```

## disassembly

```asm
0x180047fb0  push    rbp
0x180047fb2  push    rbx
0x180047fb3  push    rsi
0x180047fb4  push    rdi
0x180047fb5  push    r12
0x180047fb7  push    r13
0x180047fb9  push    r14
0x180047fbb  push    r15
0x180047fbd  lea     rbp, [rsp-1F8h]
0x180047fc5  sub     rsp, 2F8h
0x180047fcc  mov     rax, cs:__security_cookie
0x180047fd3  xor     rax, rsp
0x180047fd6  mov     [rbp+230h+var_50], rax
0x180047fdd  mov     r14, r8
0x180047fe0  mov     r15, rdx
0x180047fe3  mov     r13, rcx
0x180047fe6  lea     rdx, [rbp+230h+var_150]
0x180047fed  mov     ebx, 100h
0x180047ff2  lea     rcx, [rbp+230h+var_290]
0x180047ff6  mov     r8d, ebx
0x180047ff9  mov     rsi, r9
0x180047ffc  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180048002  mov     r8d, ebx; Size
0x180048005  lea     rcx, [rbp+230h+var_250]; void *
0x180048009  xor     edx, edx; Val
0x18004800b  call    memset_0
0x180048010  mov     r8d, ebx
0x180048013  lea     rdx, [rbp+230h+var_250]
0x180048017  lea     rcx, [rsp+330h+var_2C0]
0x18004801c  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180048022  xorps   xmm0, xmm0
0x180048025  xor     r12d, r12d
0x180048028  xorps   xmm1, xmm1
0x18004802b  movups  xmmword ptr [rsp+330h+pDataIn.cbData], xmm0
0x180048030  movups  xmmword ptr [rsp+330h+var_2F0.cbData], xmm1
0x180048035  movups  [rsp+330h+var_2E0], xmm0
0x18004803a  test    r15, r15
0x18004803d  jz      loc_180048148
0x180048043  test    r14, r14
0x180048046  jz      loc_180048148
0x18004804c  lea     rdi, [r13+28h]
0x180048050  mov     rcx, rdi
0x180048053  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180048059  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004805d  cmp     [rax], r12w
0x180048061  jz      short loc_18004809C
0x180048063  mov     rcx, rdi
0x180048066  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18004806c  mov     rcx, rax
0x18004806f  mov     rax, rbx
0x180048072  inc     rax
0x180048075  cmp     [rcx+rax*2], r12w
0x18004807a  jnz     short loc_180048072
0x18004807c  lea     eax, ds:2[rax*2]
0x180048083  mov     rcx, rdi
0x180048086  mov     dword ptr [rsp+330h+var_2E0], eax
0x18004808a  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180048090  mov     qword ptr [rsp+330h+var_2E0+8], rax
0x180048095  lea     r8, [rsp+330h+var_2E0]
0x18004809a  jmp     short loc_18004809F
0x18004809c  mov     r8, r12; pOptionalEntropy
0x18004809f  inc     rbx
0x1800480a2  cmp     [r15+rbx*2], r12w
0x1800480a7  jnz     short loc_18004809F
0x1800480a9  lea     eax, ds:2[rbx*2]
0x1800480b0  mov     [rsp+330h+pDataIn.pbData], r15
0x1800480b5  mov     [rsp+330h+pDataIn.cbData], eax
0x1800480b9  mov     eax, [r13+60h]
0x1800480bd  neg     eax
0x1800480bf  lea     rax, [rsp+330h+var_2F0]
0x1800480c4  sbb     ecx, ecx
0x1800480c6  mov     [rsp+330h+pDataOut], rax; pDataOut
0x1800480cb  and     ecx, 4
0x1800480ce  xor     r9d, r9d; pvReserved
0x1800480d1  inc     ecx
0x1800480d3  xor     edx, edx; szDataDescr
0x1800480d5  mov     [rsp+330h+dwFlags], ecx; dwFlags
0x1800480d9  lea     rcx, [rsp+330h+pDataIn]; pDataIn
0x1800480de  mov     [rsp+330h+pPromptStruct], r12; pPromptStruct
0x1800480e3  call    cs:__imp_CryptProtectData
0x1800480e9  test    eax, eax
0x1800480eb  jnz     short loc_18004810A
0x1800480ed  mov     dword ptr [rsi], 0Bh
0x1800480f3  call    cs:__imp_GetLastError
0x1800480f9  mov     ebx, eax
0x1800480fb  test    eax, eax
0x1800480fd  jle     short loc_18004814D
0x1800480ff  movzx   ebx, ax
0x180048102  or      ebx, 80070000h
0x180048108  jmp     short loc_18004814D
0x18004810a  mov     edx, [rsp+330h+var_2F0.cbData]
0x18004810e  lea     r8, [rsp+330h+var_2C0]
0x180048113  mov     rcx, [rsp+330h+var_2F0.pbData]
0x180048118  xor     r9d, r9d
0x18004811b  call    cs:__imp_?uuencode@@YAHPEAEKPEAVBUFFER@@H@Z; uuencode(uchar *,ulong,BUFFER *,int)
0x180048121  test    eax, eax
0x180048123  jnz     short loc_18004812D
0x180048125  mov     dword ptr [rsi], 2
0x18004812b  jmp     short loc_1800480F3
0x18004812d  lea     rcx, [rsp+330h+var_2C0]
0x180048132  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180048138  mov     rdx, rax
0x18004813b  mov     rcx, r14
0x18004813e  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180048144  mov     ebx, eax
0x180048146  jmp     short loc_18004814D
0x180048148  mov     ebx, 80070057h
0x18004814d  mov     rcx, [rsp+330h+var_2F0.pbData]; hMem
0x180048152  test    rcx, rcx
0x180048155  jz      short loc_18004815D
0x180048157  call    cs:__imp_LocalFree
0x18004815d  lea     rcx, [rsp+330h+var_2C0]
0x180048162  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180048168  lea     rcx, [rbp+230h+var_290]
0x18004816c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180048172  mov     eax, ebx
0x180048174  mov     rcx, [rbp+230h+var_50]
0x18004817b  xor     rcx, rsp; StackCookie
0x18004817e  call    __security_check_cookie
0x180048183  add     rsp, 2F8h
0x18004818a  pop     r15
0x18004818c  pop     r14
0x18004818e  pop     r13
0x180048190  pop     r12
0x180048192  pop     rdi
0x180048193  pop     rsi
0x180048194  pop     rbx
0x180048195  pop     rbp
0x180048196  retn
```
