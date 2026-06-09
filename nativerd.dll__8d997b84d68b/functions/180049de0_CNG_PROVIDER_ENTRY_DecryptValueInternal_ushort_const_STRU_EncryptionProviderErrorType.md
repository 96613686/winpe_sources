# CNG_PROVIDER_ENTRY::DecryptValueInternal(ushort const *,STRU *,EncryptionProviderErrorType *)

- ea: `0x180049de0`
- end: `0x18004a1e6`
- name: `?DecryptValueInternal@CNG_PROVIDER_ENTRY@@UEAAJPEBGPEAVSTRU@@PEAW4EncryptionProviderErrorType@@@Z`
- size: `1030`
- prototype: `__int64 __fastcall(CNG_PROVIDER_ENTRY *__hidden this, const unsigned __int16 *, struct STRU *, enum EncryptionProviderErrorType *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180049de0`
- `0x180059bc6`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049eec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049eec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a133`
- `bcrypt!BCryptDecrypt` at `0x180049f7b`
- `bcrypt!BCryptDecrypt` at `0x18004a076`
- `bcrypt!BCryptDecrypt` at `0x180049f7b`
- `bcrypt!BCryptDecrypt` at `0x18004a076`
- `iisutil!PuDbgPrintError` at `0x180049ff7`
- `iisutil!PuDbgPrintError` at `0x180049ff7`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180049ec4`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180049ec4`
- `iisutil!uudecode` at `0x180049eda`
- `iisutil!uudecode` at `0x180049eda`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180049eb0`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180049eb0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18004a1bb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18004a1bb`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180049e2c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180049e2c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a19c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a1a6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a1b1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a19c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a1a6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004a1b1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049f27`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049f41`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a00b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a021`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a037`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a099`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a0e1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a0ee`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a119`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a181`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049f27`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049f41`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a00b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a021`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a037`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a099`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a0e1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a0ee`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a119`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004a181`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180049e60`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180049e60`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180049e37`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180049e41`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180049e37`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180049e41`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180049fa0`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180049fa0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004a127`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004a127`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004a174`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18004a174`

## string_xrefs

- `0x180049fec`: `servercommon\inetsrv\iis\iisrearc\core\nativereader\dll\cngproviderentry.cxx`
- `0x18004a151`: `Failed to copy buffer to output string pstrDecryptedBlob.\n`

## pseudocode

```c
__int64 __fastcall CNG_PROVIDER_ENTRY::DecryptValueInternal(
        CNG_PROVIDER_ENTRY *this,
        const unsigned __int16 *a2,
        struct STRU *a3,
        enum EncryptionProviderErrorType *a4)
{
  int v8; // ebx
  char *Str; // rax
  signed int LastError; // eax
  ULONG cbIV; // esi
  __int64 v12; // r14
  UCHAR *pbIV; // rbx
  ULONG v14; // edi
  UCHAR *Ptr; // rax
  NTSTATUS v16; // ebx
  signed int v17; // eax
  const char *v18; // rax
  __int64 v19; // r8
  ULONG cbOutput; // r15d
  UCHAR *v21; // rax
  ULONG v22; // r14d
  UCHAR *pbOutput; // rsi
  UCHAR *v24; // rax
  ULONG v25; // edi
  UCHAR *v26; // rbx
  UCHAR *v27; // rax
  ULONG v28; // ebx
  __int64 (__fastcall *v29)(CNG_PROVIDER_ENTRY *, void *, _QWORD, _BYTE *, _DWORD); // rdi
  void *v30; // rax
  unsigned int v31; // edi
  __int64 v32; // rbx
  char *v33; // rbx
  const void *v34; // rax
  const unsigned __int16 *v35; // rax
  signed int v36; // eax
  __int64 Size; // rdi
  _BYTE *i; // rax
  ULONG pcbResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v41; // [rsp+54h] [rbp-ACh] BYREF
  ULONG v42; // [rsp+58h] [rbp-A8h]
  __int64 v43; // [rsp+60h] [rbp-A0h]
  STRU *v44; // [rsp+68h] [rbp-98h]
  _BYTE v45[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v46[48]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v47[48]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v48[56]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v49[2]; // [rsp+138h] [rbp+38h] BYREF
  char v50[256]; // [rsp+160h] [rbp+60h] BYREF

  v44 = a3;
  STRA::STRA((STRA *)v48, v50, 0x100u);
  BUFFER::BUFFER((BUFFER *)v45);
  BUFFER::BUFFER((BUFFER *)v46);
  memset(v49, 0, sizeof(v49));
  BUFFER::BUFFER((BUFFER *)v47, (unsigned __int8 *)v49, 0x20u);
  pcbResult = 0;
  v41 = 0;
  if ( !a2 || !a3 )
  {
    v8 = -2147024809;
    goto LABEL_30;
  }
  if ( !*((_QWORD *)this + 5) || !*((_QWORD *)this + 6) || !*((_DWORD *)this + 81) )
  {
    v8 = -2146893802;
    goto LABEL_30;
  }
  v8 = STRA::CopyWTruncate((STRA *)v48, a2);
  if ( v8 < 0 )
    goto LABEL_30;
  Str = STRA::QueryStr((STRA *)v48);
  if ( !uudecode(Str, (struct BUFFER *)v45, &v41, 0) )
  {
    *(_DWORD *)a4 = 3;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_30;
  }
  cbIV = *((_DWORD *)this + 80);
  v42 = cbIV + *((_DWORD *)this + 83);
  v12 = v42;
  pbIV = (UCHAR *)BUFFER::QueryPtr((BUFFER *)v45);
  v43 = v12;
  v14 = v41 - v12;
  Ptr = (UCHAR *)BUFFER::QueryPtr((BUFFER *)v45);
  v16 = BCryptDecrypt(*((BCRYPT_KEY_HANDLE *)this + 6), &Ptr[v12], v14, 0, pbIV, cbIV, 0, 0, &pcbResult, 1u);
  if ( v16 < 0 )
  {
LABEL_11:
    *(_DWORD *)a4 = 14;
    v8 = v16 | 0x10000000;
    goto LABEL_30;
  }
  if ( BUFFER::Resize((BUFFER *)v46, pcbResult) )
  {
    cbOutput = pcbResult;
    v21 = (UCHAR *)BUFFER::QueryPtr((BUFFER *)v46);
    v22 = *((_DWORD *)this + 80);
    pbOutput = v21;
    v24 = (UCHAR *)BUFFER::QueryPtr((BUFFER *)v45);
    v25 = v41 - v42;
    v26 = v24;
    v27 = (UCHAR *)BUFFER::QueryPtr((BUFFER *)v45);
    v16 = BCryptDecrypt(
            *((BCRYPT_KEY_HANDLE *)this + 6),
            &v27[v43],
            v25,
            0,
            v26,
            v22,
            pbOutput,
            cbOutput,
            &pcbResult,
            1u);
    if ( v16 < 0 )
      goto LABEL_11;
    v28 = pcbResult;
    v29 = *(__int64 (__fastcall **)(CNG_PROVIDER_ENTRY *, void *, _QWORD, _BYTE *, _DWORD))(*(_QWORD *)this + 48LL);
    v30 = BUFFER::QueryPtr((BUFFER *)v46);
    v8 = v29(this, v30, v28, v47, 0);
    if ( v8 < 0 )
    {
      *(_DWORD *)a4 = 17;
      goto LABEL_30;
    }
    v31 = *((_DWORD *)this + 83);
    v32 = *((unsigned int *)this + 80);
    v33 = (char *)BUFFER::QueryPtr((BUFFER *)v45) + v32;
    v34 = BUFFER::QueryPtr((BUFFER *)v47);
    if ( memcmp_0(v34, v33, v31) )
    {
      *(_DWORD *)a4 = 18;
      v8 = -2147467259;
      goto LABEL_30;
    }
    v35 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v46);
    v8 = STRU::Copy(v44, v35);
    if ( v8 < 0 )
    {
      v36 = GetLastError();
      v8 = v36;
      if ( v36 > 0 )
        v8 = (unsigned __int16)v36 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v18 = "Failed to copy buffer to output string pstrDecryptedBlob.\n";
        v19 = 379;
        goto LABEL_17;
      }
    }
  }
  else
  {
    v17 = GetLastError();
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v18 = "Failed to allocate buffDecryptedBlob buffer.\n";
      v19 = 326;
LABEL_17:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\nativereader\\dll\\cngproviderentry.cxx",
        v19,
        "CNG_PROVIDER_ENTRY::DecryptValueInternal",
        v8,
        v18);
    }
  }
LABEL_30:
  Size = BUFFER::QuerySize((BUFFER *)v45);
  for ( i = BUFFER::QueryPtr((BUFFER *)v45); Size; --Size )
    *i++ = 0;
  BUFFER::~BUFFER((BUFFER *)v47);
  BUFFER::~BUFFER((BUFFER *)v46);
  BUFFER::~BUFFER((BUFFER *)v45);
  STRA::~STRA((STRA *)v48);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180049de0  push    rbp
0x180049de2  push    rbx
0x180049de3  push    rsi
0x180049de4  push    rdi
0x180049de5  push    r12
0x180049de7  push    r13
0x180049de9  push    r14
0x180049deb  push    r15
0x180049ded  lea     rbp, [rsp-178h]
0x180049df5  sub     rsp, 278h
0x180049dfc  mov     rax, cs:__security_cookie
0x180049e03  xor     rax, rsp
0x180049e06  mov     [rbp+1B0h+var_50], rax
0x180049e0d  mov     rbx, r8
0x180049e10  mov     rdi, rdx
0x180049e13  mov     r12, rcx
0x180049e16  mov     [rsp+2B0h+var_248], rbx
0x180049e1b  mov     r8d, 100h
0x180049e21  lea     rdx, [rbp+1B0h+var_150]
0x180049e25  lea     rcx, [rbp+1B0h+var_1B0]
0x180049e29  mov     r13, r9
0x180049e2c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180049e32  lea     rcx, [rsp+2B0h+var_240]
0x180049e37  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180049e3d  lea     rcx, [rbp+1B0h+var_210]
0x180049e41  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180049e47  xorps   xmm0, xmm0
0x180049e4a  lea     rdx, [rbp+1B0h+var_178]
0x180049e4e  mov     r8d, 20h ; ' '
0x180049e54  lea     rcx, [rbp+1B0h+var_1E0]
0x180049e58  movups  [rbp+1B0h+var_178], xmm0
0x180049e5c  movups  [rbp+1B0h+var_168], xmm0
0x180049e60  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180049e66  xor     r15d, r15d
0x180049e69  mov     [rsp+2B0h+var_260], r15d
0x180049e6e  mov     [rsp+2B0h+var_25C], r15d
0x180049e73  test    rdi, rdi
0x180049e76  jz      loc_18004A16A
0x180049e7c  test    rbx, rbx
0x180049e7f  jz      loc_18004A16A
0x180049e85  cmp     [r12+28h], r15
0x180049e8a  jz      loc_18004A163
0x180049e90  cmp     [r12+30h], r15
0x180049e95  jz      loc_18004A163
0x180049e9b  cmp     [r12+144h], r15d
0x180049ea3  jz      loc_18004A163
0x180049ea9  mov     rdx, rdi
0x180049eac  lea     rcx, [rbp+1B0h+var_1B0]
0x180049eb0  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x180049eb6  mov     ebx, eax
0x180049eb8  test    eax, eax
0x180049eba  js      loc_18004A16F
0x180049ec0  lea     rcx, [rbp+1B0h+var_1B0]
0x180049ec4  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180049eca  xor     r9d, r9d
0x180049ecd  lea     r8, [rsp+2B0h+var_25C]
0x180049ed2  mov     rcx, rax
0x180049ed5  lea     rdx, [rsp+2B0h+var_240]
0x180049eda  call    cs:__imp_?uudecode@@YAHPEADPEAVBUFFER@@PEAKH@Z; uudecode(char *,BUFFER *,ulong *,int)
0x180049ee0  test    eax, eax
0x180049ee2  jnz     short loc_180049F0A
0x180049ee4  mov     dword ptr [r13+0], 3
0x180049eec  call    cs:__imp_GetLastError
0x180049ef2  mov     ebx, eax
0x180049ef4  test    eax, eax
0x180049ef6  jle     loc_18004A16F
0x180049efc  movzx   ebx, ax
0x180049eff  or      ebx, 80070000h
0x180049f05  jmp     loc_18004A16F
0x180049f0a  mov     r14d, [r12+14Ch]
0x180049f12  lea     rcx, [rsp+2B0h+var_240]
0x180049f17  mov     esi, [r12+140h]
0x180049f1f  add     r14d, esi
0x180049f22  mov     [rsp+2B0h+var_258], r14d
0x180049f27  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180049f2d  mov     edi, [rsp+2B0h+var_25C]
0x180049f31  lea     rcx, [rsp+2B0h+var_240]
0x180049f36  mov     rbx, rax
0x180049f39  mov     [rsp+2B0h+var_250], r14
0x180049f3e  sub     edi, r14d
0x180049f41  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180049f47  mov     rcx, [r12+30h]; hKey
0x180049f4c  xor     r9d, r9d; pPaddingInfo
0x180049f4f  mov     [rsp+2B0h+dwFlags], 1; dwFlags
0x180049f57  mov     r8d, edi; cbInput
0x180049f5a  lea     rdx, [rax+r14]; pbInput
0x180049f5e  lea     rax, [rsp+2B0h+var_260]
0x180049f63  mov     [rsp+2B0h+pcbResult], rax; pcbResult
0x180049f68  mov     [rsp+2B0h+cbOutput], r15d; cbOutput
0x180049f6d  mov     [rsp+2B0h+pbOutput], r15; pbOutput
0x180049f72  mov     [rsp+2B0h+cbIV], esi; cbIV
0x180049f76  mov     [rsp+2B0h+pbIV], rbx; pbIV
0x180049f7b  call    cs:__imp_BCryptDecrypt
0x180049f81  mov     ebx, eax
0x180049f83  test    eax, eax
0x180049f85  jns     short loc_180049F98
0x180049f87  mov     dword ptr [r13+0], 0Eh
0x180049f8f  bts     ebx, 1Ch
0x180049f93  jmp     loc_18004A16F
0x180049f98  mov     edx, [rsp+2B0h+var_260]
0x180049f9c  lea     rcx, [rbp+1B0h+var_210]
0x180049fa0  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180049fa6  test    al, al
0x180049fa8  jnz     short loc_18004A002
0x180049faa  call    cs:__imp_GetLastError
0x180049fb0  mov     ebx, eax
0x180049fb2  test    eax, eax
0x180049fb4  jle     short loc_180049FBF
0x180049fb6  movzx   ebx, ax
0x180049fb9  or      ebx, 80070000h
0x180049fbf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049fc6  jz      loc_18004A16F
0x180049fcc  lea     rax, aFailedToAlloca_1; "Failed to allocate buffDecryptedBlob bu"...
0x180049fd3  mov     r8d, 146h
0x180049fd9  mov     rcx, cs:g_pDebug
0x180049fe0  lea     r9, aCngProviderEnt; "CNG_PROVIDER_ENTRY::DecryptValueInterna"...
0x180049fe7  mov     qword ptr [rsp+2B0h+cbIV], rax
0x180049fec  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180049ff3  mov     dword ptr [rsp+2B0h+pbIV], ebx
0x180049ff7  call    cs:__imp_PuDbgPrintError
0x180049ffd  jmp     loc_18004A16F
0x18004a002  mov     r15d, [rsp+2B0h+var_260]
0x18004a007  lea     rcx, [rbp+1B0h+var_210]
0x18004a00b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a011  mov     r14d, [r12+140h]
0x18004a019  lea     rcx, [rsp+2B0h+var_240]
0x18004a01e  mov     rsi, rax
0x18004a021  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a027  mov     edi, [rsp+2B0h+var_25C]
0x18004a02b  lea     rcx, [rsp+2B0h+var_240]
0x18004a030  sub     edi, [rsp+2B0h+var_258]
0x18004a034  mov     rbx, rax
0x18004a037  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a03d  mov     rdx, [rsp+2B0h+var_250]
0x18004a042  xor     r9d, r9d; pPaddingInfo
0x18004a045  mov     rcx, [r12+30h]; hKey
0x18004a04a  add     rdx, rax; pbInput
0x18004a04d  mov     [rsp+2B0h+dwFlags], 1; dwFlags
0x18004a055  lea     rax, [rsp+2B0h+var_260]
0x18004a05a  mov     [rsp+2B0h+pcbResult], rax; pcbResult
0x18004a05f  mov     r8d, edi; cbInput
0x18004a062  mov     [rsp+2B0h+cbOutput], r15d; cbOutput
0x18004a067  mov     [rsp+2B0h+pbOutput], rsi; pbOutput
0x18004a06c  mov     [rsp+2B0h+cbIV], r14d; cbIV
0x18004a071  mov     [rsp+2B0h+pbIV], rbx; pbIV
0x18004a076  call    cs:__imp_BCryptDecrypt
0x18004a07c  xor     r15d, r15d
0x18004a07f  mov     ebx, eax
0x18004a081  test    eax, eax
0x18004a083  js      loc_180049F87
0x18004a089  mov     rax, [r12]
0x18004a08d  lea     rcx, [rbp+1B0h+var_210]
0x18004a091  mov     ebx, [rsp+2B0h+var_260]
0x18004a095  mov     rdi, [rax+30h]
0x18004a099  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a09f  lea     r9, [rbp+1B0h+var_1E0]
0x18004a0a3  mov     dword ptr [rsp+2B0h+pbIV], r15d
0x18004a0a8  mov     rdx, rax
0x18004a0ab  mov     r8d, ebx
0x18004a0ae  mov     rax, rdi
0x18004a0b1  mov     rcx, r12
0x18004a0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0b9  mov     ebx, eax
0x18004a0bb  test    eax, eax
0x18004a0bd  jns     short loc_18004A0CC
0x18004a0bf  mov     dword ptr [r13+0], 11h
0x18004a0c7  jmp     loc_18004A16F
0x18004a0cc  mov     edi, [r12+14Ch]
0x18004a0d4  lea     rcx, [rsp+2B0h+var_240]
0x18004a0d9  mov     ebx, [r12+140h]
0x18004a0e1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a0e7  lea     rcx, [rbp+1B0h+var_1E0]
0x18004a0eb  add     rbx, rax
0x18004a0ee  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a0f4  mov     r8d, edi; Size
0x18004a0f7  mov     rdx, rbx; Buf2
0x18004a0fa  mov     rcx, rax; Buf1
0x18004a0fd  call    memcmp_0
0x18004a102  test    eax, eax
0x18004a104  jz      short loc_18004A115
0x18004a106  mov     dword ptr [r13+0], 12h
0x18004a10e  mov     ebx, 80004005h
0x18004a113  jmp     short loc_18004A16F
0x18004a115  lea     rcx, [rbp+1B0h+var_210]
0x18004a119  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a11f  mov     rcx, [rsp+2B0h+var_248]
0x18004a124  mov     rdx, rax
0x18004a127  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004a12d  mov     ebx, eax
0x18004a12f  test    eax, eax
0x18004a131  jns     short loc_18004A16F
0x18004a133  call    cs:__imp_GetLastError
0x18004a139  mov     ebx, eax
0x18004a13b  test    eax, eax
0x18004a13d  jle     short loc_18004A148
0x18004a13f  movzx   ebx, ax
0x18004a142  or      ebx, 80070000h
0x18004a148  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a14f  jz      short loc_18004A16F
0x18004a151  lea     rax, aFailedToCopyBu; "Failed to copy buffer to output string "...
0x18004a158  mov     r8d, 17Bh
0x18004a15e  jmp     loc_180049FD9
0x18004a163  mov     ebx, 80090016h
0x18004a168  jmp     short loc_18004A16F
0x18004a16a  mov     ebx, 80070057h
0x18004a16f  lea     rcx, [rsp+2B0h+var_240]
0x18004a174  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18004a17a  lea     rcx, [rsp+2B0h+var_240]
0x18004a17f  mov     edi, eax
0x18004a181  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004a187  test    rdi, rdi
0x18004a18a  jz      short loc_18004A198
0x18004a18c  mov     [rax], r15b
0x18004a18f  inc     rax
0x18004a192  sub     rdi, 1
0x18004a196  jnz     short loc_18004A18C
0x18004a198  lea     rcx, [rbp+1B0h+var_1E0]
0x18004a19c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004a1a2  lea     rcx, [rbp+1B0h+var_210]
0x18004a1a6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004a1ac  lea     rcx, [rsp+2B0h+var_240]
0x18004a1b1  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18004a1b7  lea     rcx, [rbp+1B0h+var_1B0]
0x18004a1bb  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18004a1c1  mov     eax, ebx
0x18004a1c3  mov     rcx, [rbp+1B0h+var_50]
0x18004a1ca  xor     rcx, rsp; StackCookie
0x18004a1cd  call    __security_check_cookie
0x18004a1d2  add     rsp, 278h
0x18004a1d9  pop     r15
0x18004a1db  pop     r14
0x18004a1dd  pop     r13
0x18004a1df  pop     r12
0x18004a1e1  pop     rdi
0x18004a1e2  pop     rsi
0x18004a1e3  pop     rbx
0x18004a1e4  pop     rbp
0x18004a1e5  retn
```
