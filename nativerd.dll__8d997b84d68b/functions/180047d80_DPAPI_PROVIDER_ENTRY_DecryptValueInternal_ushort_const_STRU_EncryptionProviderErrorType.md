# DPAPI_PROVIDER_ENTRY::DecryptValueInternal(ushort const *,STRU *,EncryptionProviderErrorType *)

- ea: `0x180047d80`
- end: `0x180047fa5`
- name: `?DecryptValueInternal@DPAPI_PROVIDER_ENTRY@@UEAAJPEBGPEAVSTRU@@PEAW4EncryptionProviderErrorType@@@Z`
- size: `549`
- prototype: `__int64 __fastcall(DPAPI_PROVIDER_ENTRY *__hidden this, const unsigned __int16 *, struct STRU *, enum EncryptionProviderErrorType *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180047d80`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047e5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047f69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047f69`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180047e39`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180047e39`
- `iisutil!uudecode` at `0x180047e4f`
- `iisutil!uudecode` at `0x180047e4f`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180047e25`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180047e25`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180047f7e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180047f7e`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180047dc9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180047dc9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180047f74`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180047f74`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180047e8a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180047e8a`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180047de9`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180047de9`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180047f36`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180047f36`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180047e9c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180047eab`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180047ed0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180047e9c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180047eab`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180047ed0`
- `CRYPT32!CryptUnprotectData` at `0x180047f0f`
- `CRYPT32!CryptUnprotectData` at `0x180047f0f`

## pseudocode

```c
__int64 __fastcall DPAPI_PROVIDER_ENTRY::DecryptValueInternal(
        DPAPI_PROVIDER_ENTRY *this,
        const unsigned __int16 *a2,
        struct STRU *a3,
        enum EncryptionProviderErrorType *a4)
{
  signed int v8; // ebx
  char *Str; // rax
  signed int LastError; // eax
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  DATA_BLOB *v13; // r8
  BYTE *pbData; // rcx
  __int64 cbData; // rax
  DWORD v17; // [rsp+40h] [rbp-C0h] BYREF
  DATA_BLOB pDataOut; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h] BYREF
  DATA_BLOB pDataIn; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v21[48]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v22[56]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 v23[256]; // [rsp+E0h] [rbp-20h] BYREF
  char v24[256]; // [rsp+1E0h] [rbp+E0h] BYREF

  STRA::STRA((STRA *)v22, v24, 0x100u);
  memset_0(v23, 0, sizeof(v23));
  BUFFER::BUFFER((BUFFER *)v21, v23, 0x100u);
  v17 = 0;
  pDataIn = 0;
  pDataOut = 0;
  v19 = 0;
  if ( a2 && a3 )
  {
    v8 = STRA::CopyWTruncate((STRA *)v22, a2);
    if ( v8 >= 0 )
    {
      Str = STRA::QueryStr((STRA *)v22);
      if ( uudecode(Str, (struct BUFFER *)v21, &v17, 0) )
      {
        pDataIn.cbData = v17;
        pDataIn.pbData = (BYTE *)BUFFER::QueryPtr((BUFFER *)v21);
        if ( *STRU::QueryStr((DPAPI_PROVIDER_ENTRY *)((char *)this + 40)) )
        {
          v11 = STRU::QueryStr((DPAPI_PROVIDER_ENTRY *)((char *)this + 40));
          v12 = -1;
          do
            ++v12;
          while ( v11[v12] );
          LODWORD(v19) = 2 * v12 + 2;
          *((_QWORD *)&v19 + 1) = STRU::QueryStr((DPAPI_PROVIDER_ENTRY *)((char *)this + 40));
          v13 = (DATA_BLOB *)&v19;
        }
        else
        {
          v13 = 0;
        }
        if ( CryptUnprotectData(&pDataIn, 0, v13, 0, 0, *((_DWORD *)this + 24) != 0 ? 5 : 1, &pDataOut) )
        {
          v8 = STRU::Copy(a3, (const unsigned __int16 *)pDataOut.pbData, pDataOut.cbData >> 1);
        }
        else
        {
          *(_DWORD *)a4 = 12;
          v8 = -2147018895;
        }
      }
      else
      {
        *(_DWORD *)a4 = 3;
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
  pbData = pDataOut.pbData;
  if ( pDataOut.pbData )
  {
    cbData = pDataOut.cbData;
    if ( pDataOut.cbData )
    {
      do
      {
        *pbData++ = 0;
        --cbData;
      }
      while ( cbData );
      pbData = pDataOut.pbData;
    }
    LocalFree(pbData);
  }
  BUFFER::~BUFFER((BUFFER *)v21);
  STRA::~STRA((STRA *)v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180047d80  push    rbp
0x180047d82  push    rbx
0x180047d83  push    rsi
0x180047d84  push    rdi
0x180047d85  push    r14
0x180047d87  push    r15
0x180047d89  lea     rbp, [rsp-1F8h]
0x180047d91  sub     rsp, 2F8h
0x180047d98  mov     rax, cs:__security_cookie
0x180047d9f  xor     rax, rsp
0x180047da2  mov     [rbp+220h+var_40], rax
0x180047da9  mov     rsi, r8
0x180047dac  mov     rbx, rdx
0x180047daf  mov     r14, rcx
0x180047db2  lea     rdx, [rbp+220h+var_140]
0x180047db9  mov     r15d, 100h
0x180047dbf  lea     rcx, [rbp+220h+var_278]
0x180047dc3  mov     r8d, r15d
0x180047dc6  mov     rdi, r9
0x180047dc9  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180047dcf  mov     r8d, r15d; Size
0x180047dd2  lea     rcx, [rbp+220h+var_240]; void *
0x180047dd6  xor     edx, edx; Val
0x180047dd8  call    memset_0
0x180047ddd  mov     r8d, r15d
0x180047de0  lea     rdx, [rbp+220h+var_240]
0x180047de4  lea     rcx, [rsp+320h+var_2A8]
0x180047de9  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180047def  xor     r15d, r15d
0x180047df2  xorps   xmm0, xmm0
0x180047df5  mov     [rsp+320h+var_2E0], r15d
0x180047dfa  xorps   xmm1, xmm1
0x180047dfd  movups  xmmword ptr [rsp+320h+pDataIn.cbData], xmm0
0x180047e02  movups  xmmword ptr [rsp+320h+var_2D8.cbData], xmm1
0x180047e07  movups  [rsp+320h+var_2C8], xmm0
0x180047e0c  test    rbx, rbx
0x180047e0f  jz      loc_180047F40
0x180047e15  test    rsi, rsi
0x180047e18  jz      loc_180047F40
0x180047e1e  mov     rdx, rbx
0x180047e21  lea     rcx, [rbp+220h+var_278]
0x180047e25  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x180047e2b  mov     ebx, eax
0x180047e2d  test    eax, eax
0x180047e2f  js      loc_180047F45
0x180047e35  lea     rcx, [rbp+220h+var_278]
0x180047e39  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180047e3f  xor     r9d, r9d
0x180047e42  lea     r8, [rsp+320h+var_2E0]
0x180047e47  mov     rcx, rax
0x180047e4a  lea     rdx, [rsp+320h+var_2A8]
0x180047e4f  call    cs:__imp_?uudecode@@YAHPEADPEAVBUFFER@@PEAKH@Z; uudecode(char *,BUFFER *,ulong *,int)
0x180047e55  test    eax, eax
0x180047e57  jnz     short loc_180047E7D
0x180047e59  mov     dword ptr [rdi], 3
0x180047e5f  call    cs:__imp_GetLastError
0x180047e65  mov     ebx, eax
0x180047e67  test    eax, eax
0x180047e69  jle     loc_180047F45
0x180047e6f  movzx   ebx, ax
0x180047e72  or      ebx, 80070000h
0x180047e78  jmp     loc_180047F45
0x180047e7d  mov     eax, [rsp+320h+var_2E0]
0x180047e81  lea     rcx, [rsp+320h+var_2A8]
0x180047e86  mov     [rsp+320h+pDataIn.cbData], eax
0x180047e8a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180047e90  lea     rbx, [r14+28h]
0x180047e94  mov     [rsp+320h+pDataIn.pbData], rax
0x180047e99  mov     rcx, rbx
0x180047e9c  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180047ea2  cmp     [rax], r15w
0x180047ea6  jz      short loc_180047EE2
0x180047ea8  mov     rcx, rbx
0x180047eab  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180047eb1  mov     rcx, rax
0x180047eb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047eb8  inc     rax
0x180047ebb  cmp     [rcx+rax*2], r15w
0x180047ec0  jnz     short loc_180047EB8
0x180047ec2  lea     eax, ds:2[rax*2]
0x180047ec9  mov     rcx, rbx
0x180047ecc  mov     dword ptr [rsp+320h+var_2C8], eax
0x180047ed0  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180047ed6  mov     qword ptr [rsp+320h+var_2C8+8], rax
0x180047edb  lea     r8, [rsp+320h+var_2C8]
0x180047ee0  jmp     short loc_180047EE5
0x180047ee2  mov     r8, r15; pOptionalEntropy
0x180047ee5  mov     eax, [r14+60h]
0x180047ee9  neg     eax
0x180047eeb  lea     rax, [rsp+320h+var_2D8]
0x180047ef0  sbb     ecx, ecx
0x180047ef2  mov     [rsp+320h+pDataOut], rax; pDataOut
0x180047ef7  and     ecx, 4
0x180047efa  xor     r9d, r9d; pvReserved
0x180047efd  inc     ecx
0x180047eff  xor     edx, edx; ppszDataDescr
0x180047f01  mov     [rsp+320h+dwFlags], ecx; dwFlags
0x180047f05  lea     rcx, [rsp+320h+pDataIn]; pDataIn
0x180047f0a  mov     [rsp+320h+pPromptStruct], r15; pPromptStruct
0x180047f0f  call    cs:__imp_CryptUnprotectData
0x180047f15  test    eax, eax
0x180047f17  jnz     short loc_180047F26
0x180047f19  mov     dword ptr [rdi], 0Ch
0x180047f1f  mov     ebx, 80071771h
0x180047f24  jmp     short loc_180047F45
0x180047f26  mov     r8d, [rsp+320h+var_2D8.cbData]
0x180047f2b  mov     rcx, rsi
0x180047f2e  mov     rdx, [rsp+320h+var_2D8.pbData]
0x180047f33  shr     r8d, 1
0x180047f36  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180047f3c  mov     ebx, eax
0x180047f3e  jmp     short loc_180047F45
0x180047f40  mov     ebx, 80070057h
0x180047f45  mov     rcx, [rsp+320h+var_2D8.pbData]
0x180047f4a  test    rcx, rcx
0x180047f4d  jz      short loc_180047F6F
0x180047f4f  mov     eax, [rsp+320h+var_2D8.cbData]
0x180047f53  test    rax, rax
0x180047f56  jz      short loc_180047F69
0x180047f58  mov     [rcx], r15b
0x180047f5b  inc     rcx
0x180047f5e  sub     rax, 1
0x180047f62  jnz     short loc_180047F58
0x180047f64  mov     rcx, [rsp+320h+var_2D8.pbData]; hMem
0x180047f69  call    cs:__imp_LocalFree
0x180047f6f  lea     rcx, [rsp+320h+var_2A8]
0x180047f74  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180047f7a  lea     rcx, [rbp+220h+var_278]
0x180047f7e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180047f84  mov     eax, ebx
0x180047f86  mov     rcx, [rbp+220h+var_40]
0x180047f8d  xor     rcx, rsp; StackCookie
0x180047f90  call    __security_check_cookie
0x180047f95  add     rsp, 2F8h
0x180047f9c  pop     r15
0x180047f9e  pop     r14
0x180047fa0  pop     rdi
0x180047fa1  pop     rsi
0x180047fa2  pop     rbx
0x180047fa3  pop     rbp
0x180047fa4  retn
```
