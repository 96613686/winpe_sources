# InitStorageHelper2(char *,uchar *,ulong,IIS_CRYPTO_STORAGE * *,int)

- ea: `0x18001f720`
- end: `0x18001f8dd`
- name: `?InitStorageHelper2@@YAJPEADPEAEKPEAPEAVIIS_CRYPTO_STORAGE@@H@Z`
- size: `445`
- prototype: `__int64 __fastcall(char *, unsigned __int8 *, unsigned int, struct IIS_CRYPTO_STORAGE **, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x18001f2c8`
- `0x180021330`

## callees

- `0x1800089c8`
- `0x180008a08`
- `0x180014af0`
- `0x18001f720`
- `0x18001f8e4`
- `0x180028f34`
- `0x180029090`
- `0x180029d74`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001f87d`
- `ole32!CoTaskMemFree` at `0x18001f87d`
- `IisRTL!PuDbgPrintW` at `0x18001f855`
- `IisRTL!PuDbgPrintW` at `0x18001f8bb`
- `IisRTL!PuDbgPrintW` at `0x18001f855`
- `IisRTL!PuDbgPrintW` at `0x18001f8bb`

## pseudocode

```c
__int64 __fastcall InitStorageHelper2(
        char *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        struct IIS_CRYPTO_STORAGE **a4,
        int a5)
{
  bool v5; // zf
  int v9; // eax
  unsigned int v10; // edi
  IIS_CRYPTO_STORAGE2 *v11; // rax
  struct _IIS_CRYPTO_BLOB *v12; // rsi
  IIS_CRYPTO_STORAGE2 *v13; // rbx
  int v14; // ebp
  int CryptoProvider2; // eax
  int v16; // eax
  LPVOID pv; // [rsp+68h] [rbp+10h] BYREF

  v5 = *(_DWORD *)a2 == 1649632073;
  pv = 0;
  if ( !v5 )
    return InitStorageHelper(a2, a3, a4);
  v9 = IISCryptoCloneBlobFromRawData2(&pv, a2, a3);
  v10 = v9;
  if ( v9 < 0 )
  {
    v13 = 0;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        2078,
        "InitStorageHelper2",
        L"[InitStorageHelper] IISCryptoCloneBlobFromRawData failed with hr = 0x%x. (Crypto problem).\n",
        v9);
    goto LABEL_17;
  }
  v11 = (IIS_CRYPTO_STORAGE2 *)operator new(0x30u);
  v12 = (struct _IIS_CRYPTO_BLOB *)pv;
  v13 = v11;
  if ( !v11 )
  {
    v10 = -2147024882;
    goto LABEL_13;
  }
  v14 = a5;
  *((_QWORD *)v11 + 1) = 0;
  *((_DWORD *)v11 + 4) = 0;
  *((_QWORD *)v11 + 3) = 0;
  *((_QWORD *)v11 + 4) = 0;
  *(_QWORD *)v11 = &IIS_CRYPTO_STORAGE2::`vftable';
  *((_QWORD *)v11 + 5) = 0;
  pv = 0;
  CryptoProvider2 = GetCryptoProvider2((unsigned __int64 *)&pv, v14);
  v10 = CryptoProvider2;
  if ( CryptoProvider2 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        2063,
        "InitStorageHelper2",
        L"[InitStorageHelper] GetCryptoProvider failed with hr = 0x%x. (Crypto problem)\n",
        CryptoProvider2);
    goto LABEL_11;
  }
  v16 = IIS_CRYPTO_STORAGE2::Initialize(v13, v12, a1, (unsigned __int64)pv, v14);
  v10 = v16;
  if ( v16 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        2057,
        "InitStorageHelper2",
        L"[InitStorageHelper2] IIS_CRYPTO_STORAGE::Initialize failed with hr = 0x%x.\n",
        v16);
LABEL_11:
    *(_QWORD *)v13 = &IIS_CRYPTO_STORAGE2::`vftable';
    IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE(v13);
    operator delete(v13);
LABEL_13:
    v13 = 0;
  }
  *(_BYTE *)v12 = 88;
  CoTaskMemFree(v12);
LABEL_17:
  *a4 = v13;
  return v10;
}

```

## disassembly

```asm
0x18001f720  mov     [rsp+arg_0], rbx
0x18001f725  mov     [rsp+arg_10], rbp
0x18001f72a  push    rsi
0x18001f72b  push    rdi
0x18001f72c  push    r13
0x18001f72e  push    r14
0x18001f730  push    r15
0x18001f732  sub     rsp, 30h
0x18001f736  cmp     dword ptr [rdx], 62536349h
0x18001f73c  mov     r14, r9
0x18001f73f  mov     r10d, r8d
0x18001f742  mov     [rsp+58h+pv], 0
0x18001f74b  mov     rax, rdx
0x18001f74e  mov     r15, rcx
0x18001f751  jz      short loc_18001F766
0x18001f753  mov     r8, r9; struct IIS_CRYPTO_STORAGE **
0x18001f756  mov     edx, r10d; unsigned int
0x18001f759  mov     rcx, rax; unsigned __int8 *
0x18001f75c  call    ?InitStorageHelper@@YAJPEAEKPEAPEAVIIS_CRYPTO_STORAGE@@@Z; InitStorageHelper(uchar *,ulong,IIS_CRYPTO_STORAGE * *)
0x18001f761  jmp     loc_18001F8C6
0x18001f766  lea     rcx, [rsp+58h+pv]
0x18001f76b  call    IISCryptoCloneBlobFromRawData2
0x18001f770  mov     edi, eax
0x18001f772  test    eax, eax
0x18001f774  js      loc_18001F885
0x18001f77a  mov     ecx, 30h ; '0'; Size
0x18001f77f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f784  mov     rsi, [rsp+58h+pv]
0x18001f789  mov     rbx, rax
0x18001f78c  test    rax, rax
0x18001f78f  jz      loc_18001F870
0x18001f795  mov     ebp, [rsp+58h+arg_20]
0x18001f79c  lea     r13, ??_7IIS_CRYPTO_STORAGE2@@6B@; const IIS_CRYPTO_STORAGE2::`vftable'
0x18001f7a3  mov     qword ptr [rax+8], 0
0x18001f7ab  lea     rcx, [rsp+58h+pv]; unsigned __int64 *
0x18001f7b0  mov     dword ptr [rax+10h], 0
0x18001f7b7  mov     edx, ebp; int
0x18001f7b9  mov     qword ptr [rax+18h], 0
0x18001f7c1  mov     qword ptr [rax+20h], 0
0x18001f7c9  mov     [rax], r13
0x18001f7cc  mov     qword ptr [rax+28h], 0
0x18001f7d4  mov     [rsp+58h+pv], 0
0x18001f7dd  call    ?GetCryptoProvider2@@YAJPEA_KH@Z; GetCryptoProvider2(unsigned __int64 *,int)
0x18001f7e2  mov     edi, eax
0x18001f7e4  test    eax, eax
0x18001f7e6  js      short loc_18001F821
0x18001f7e8  mov     r9, [rsp+58h+pv]; unsigned __int64
0x18001f7ed  mov     r8, r15; char *
0x18001f7f0  mov     rdx, rsi; struct _IIS_CRYPTO_BLOB *
0x18001f7f3  mov     [rsp+58h+var_38], ebp; int
0x18001f7f7  mov     rcx, rbx; this
0x18001f7fa  call    ?Initialize@IIS_CRYPTO_STORAGE2@@QEAAJPEFAU_IIS_CRYPTO_BLOB@@PEAD_KH@Z; IIS_CRYPTO_STORAGE2::Initialize(_IIS_CRYPTO_BLOB *,char *,unsigned __int64,int)
0x18001f7ff  mov     edi, eax
0x18001f801  test    eax, eax
0x18001f803  jns     short loc_18001F877
0x18001f805  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f80c  jz      short loc_18001F85B
0x18001f80e  mov     [rsp+58h+var_30], eax
0x18001f812  mov     r8d, 809h
0x18001f818  lea     rax, aInitstoragehel_1; "[InitStorageHelper2] IIS_CRYPTO_STORAGE"...
0x18001f81f  jmp     short loc_18001F83B
0x18001f821  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f828  jz      short loc_18001F85B
0x18001f82a  mov     [rsp+58h+var_30], eax
0x18001f82e  mov     r8d, 80Fh
0x18001f834  lea     rax, aInitstoragehel_0; "[InitStorageHelper] GetCryptoProvider f"...
0x18001f83b  mov     rcx, cs:g_pDebug
0x18001f842  lea     r9, aInitstoragehel_4; "InitStorageHelper2"
0x18001f849  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001f850  mov     qword ptr [rsp+58h+var_38], rax
0x18001f855  call    cs:__imp_PuDbgPrintW
0x18001f85b  mov     rcx, rbx; this
0x18001f85e  mov     [rbx], r13
0x18001f861  call    ??1IIS_CRYPTO_STORAGE@@QEAA@XZ; IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE(void)
0x18001f866  mov     rcx, rbx; Block
0x18001f869  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f86e  jmp     short loc_18001F875
0x18001f870  mov     edi, 8007000Eh
0x18001f875  xor     ebx, ebx
0x18001f877  mov     rcx, rsi; pv
0x18001f87a  mov     byte ptr [rsi], 58h ; 'X'
0x18001f87d  call    cs:__imp_CoTaskMemFree
0x18001f883  jmp     short loc_18001F8C1
0x18001f885  xor     ebx, ebx
0x18001f887  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f88e  jz      short loc_18001F8C1
0x18001f890  mov     rcx, cs:g_pDebug
0x18001f897  lea     r9, aInitstoragehel_4; "InitStorageHelper2"
0x18001f89e  mov     [rsp+58h+var_30], eax
0x18001f8a2  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001f8a9  lea     rax, aInitstoragehel_2; "[InitStorageHelper] IISCryptoCloneBlobF"...
0x18001f8b0  mov     r8d, 81Eh
0x18001f8b6  mov     qword ptr [rsp+58h+var_38], rax
0x18001f8bb  call    cs:__imp_PuDbgPrintW
0x18001f8c1  mov     [r14], rbx
0x18001f8c4  mov     eax, edi
0x18001f8c6  mov     rbx, [rsp+58h+arg_0]
0x18001f8cb  mov     rbp, [rsp+58h+arg_10]
0x18001f8d0  add     rsp, 30h
0x18001f8d4  pop     r15
0x18001f8d6  pop     r14
0x18001f8d8  pop     r13
0x18001f8da  pop     rdi
0x18001f8db  pop     rsi
0x18001f8dc  retn
```
