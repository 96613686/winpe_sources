# CFileListener::GetInMemoryFile(STRU *,ulong *,int *,int *,IIS_CRYPTO_STORAGE * *,_IIS_CRYPTO_BLOB * *)

- ea: `0x18000b3a0`
- end: `0x18000b4c8`
- name: `?GetInMemoryFile@CFileListener@@AEAAJPEAVSTRU@@PEAKPEAH2PEAPEAVIIS_CRYPTO_STORAGE@@PEAPEFAU_IIS_CRYPTO_BLOB@@@Z`
- size: `296`
- prototype: `int(CFileListener *__hidden this, struct STRU *, unsigned int *, int *, int *, struct IIS_CRYPTO_STORAGE **, struct _IIS_CRYPTO_BLOB **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d374`

## callees

- `0x180008a08`
- `0x180009bd0`
- `0x18000ab6c`
- `0x18000b3a0`
- `0x180023be0`

## import_xrefs

- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b479`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b479`

## pseudocode

```c
__int64 __fastcall CFileListener::GetInMemoryFile(
        CFileListener *this,
        struct STRU *a2,
        unsigned int *a3,
        int *a4,
        int *a5,
        struct IIS_CRYPTO_STORAGE **a6,
        struct _IIS_CRYPTO_BLOB **a7)
{
  IIS_CRYPTO_STORAGE *v7; // rbx
  struct _IIS_CRYPTO_BLOB *v8; // rsi
  struct IIS_CRYPTO_STORAGE **v12; // r14
  struct _IIS_CRYPTO_BLOB **v13; // r15
  int *v14; // rax
  unsigned __int16 *v15; // rdx
  int CryptoFromFile; // eax
  const unsigned __int16 *v17; // rcx
  int v18; // edi
  void *Block; // [rsp+30h] [rbp-48h] BYREF
  IIS_CRYPTO_STORAGE *v22; // [rsp+88h] [rbp+10h] BYREF

  v7 = 0;
  v8 = 0;
  v22 = 0;
  Block = 0;
  if ( a2 && a3 && a4 && (v12 = a6) != 0 && (v13 = a7) != 0 )
  {
    v14 = a5;
    v15 = (unsigned __int16 *)*((_QWORD *)this + 27);
    *a3 = 0;
    *a4 = 0;
    CryptoFromFile = CFileListener::GetCryptoFromFile(this, v15, &v22, (struct _IIS_CRYPTO_BLOB **)&Block, v14);
    v8 = (struct _IIS_CRYPTO_BLOB *)Block;
    v18 = CryptoFromFile;
    v7 = v22;
    if ( CryptoFromFile >= 0 )
    {
      v18 = SaveDataTo(v17, *((struct IMDCOM **)this + 71), v22, (struct _IIS_CRYPTO_BLOB *)Block, a3, a4);
      if ( v18 >= 0 )
      {
        v18 = STRU::Copy(a2, g_wszTempFileName);
        if ( v18 >= 0 )
        {
          *v13 = v8;
          v18 = 0;
          *v12 = v7;
          return (unsigned int)v18;
        }
      }
    }
  }
  else
  {
    v18 = -2147024809;
  }
  if ( v8 )
    operator delete(v8);
  if ( v7 )
    IIS_CRYPTO_STORAGE::`scalar deleting destructor'(v7, (unsigned int)a2);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18000b3a0  mov     r11, rsp
0x18000b3a3  mov     [r11+18h], rbx
0x18000b3a7  mov     [r11+8], rcx
0x18000b3ab  push    rbp
0x18000b3ac  push    rsi
0x18000b3ad  push    rdi
0x18000b3ae  push    r12
0x18000b3b0  push    r13
0x18000b3b2  push    r14
0x18000b3b4  push    r15
0x18000b3b6  sub     rsp, 40h
0x18000b3ba  xor     ebx, ebx
0x18000b3bc  xor     esi, esi
0x18000b3be  mov     [r11+10h], rbx
0x18000b3c2  mov     rbp, r9
0x18000b3c5  mov     [r11-48h], rsi
0x18000b3c9  mov     r12, r8
0x18000b3cc  mov     r13, rdx
0x18000b3cf  test    rdx, rdx
0x18000b3d2  jz      loc_18000B48F
0x18000b3d8  test    r8, r8
0x18000b3db  jz      loc_18000B48F
0x18000b3e1  test    r9, r9
0x18000b3e4  jz      loc_18000B48F
0x18000b3ea  mov     r14, [rsp+78h+arg_28]
0x18000b3f2  test    r14, r14
0x18000b3f5  jz      loc_18000B48F
0x18000b3fb  mov     r15, [rsp+78h+arg_30]
0x18000b403  test    r15, r15
0x18000b406  jz      loc_18000B48F
0x18000b40c  mov     rax, [rsp+78h+arg_20]
0x18000b414  mov     rdx, [rcx+0D8h]; unsigned __int16 *
0x18000b41b  mov     [r8], ebx
0x18000b41e  lea     r8, [r11+10h]; struct IIS_CRYPTO_STORAGE **
0x18000b422  mov     [r9], ebx
0x18000b425  lea     r9, [r11-48h]; struct _IIS_CRYPTO_BLOB **
0x18000b429  mov     [r11-58h], rax
0x18000b42d  call    ?GetCryptoFromFile@CFileListener@@AEAAJPEAGPEAPEAVIIS_CRYPTO_STORAGE@@PEAPEFAU_IIS_CRYPTO_BLOB@@PEAH@Z; CFileListener::GetCryptoFromFile(ushort *,IIS_CRYPTO_STORAGE * *,_IIS_CRYPTO_BLOB * *,int *)
0x18000b432  mov     rsi, [rsp+78h+Block]
0x18000b437  mov     edi, eax
0x18000b439  mov     rbx, [rsp+78h+arg_8]
0x18000b441  test    eax, eax
0x18000b443  js      short loc_18000B494
0x18000b445  mov     rdx, [rsp+78h+arg_0]
0x18000b44d  mov     r9, rsi; struct _IIS_CRYPTO_BLOB *
0x18000b450  mov     [rsp+78h+var_50], rbp; int *
0x18000b455  mov     r8, rbx; struct IIS_CRYPTO_STORAGE *
0x18000b458  mov     [rsp+78h+var_58], r12; unsigned int *
0x18000b45d  mov     rdx, [rdx+238h]; struct IMDCOM *
0x18000b464  call    ?SaveDataTo@@YAJPEBGPEAUIMDCOM@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@PEAKPEAH@Z; SaveDataTo(ushort const *,IMDCOM *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ulong *,int *)
0x18000b469  mov     edi, eax
0x18000b46b  test    eax, eax
0x18000b46d  js      short loc_18000B494
0x18000b46f  mov     rdx, cs:?g_wszTempFileName@@3PEAGEA; ushort * g_wszTempFileName
0x18000b476  mov     rcx, r13
0x18000b479  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b47f  mov     edi, eax
0x18000b481  test    eax, eax
0x18000b483  js      short loc_18000B494
0x18000b485  mov     [r15], rsi
0x18000b488  xor     edi, edi
0x18000b48a  mov     [r14], rbx
0x18000b48d  jmp     short loc_18000B4AE
0x18000b48f  mov     edi, 80070057h
0x18000b494  test    rsi, rsi
0x18000b497  jz      short loc_18000B4A1
0x18000b499  mov     rcx, rsi; Block
0x18000b49c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b4a1  test    rbx, rbx
0x18000b4a4  jz      short loc_18000B4AE
0x18000b4a6  mov     rcx, rbx; this
0x18000b4a9  call    ??_GIIS_CRYPTO_STORAGE@@QEAAPEAXI@Z; IIS_CRYPTO_STORAGE::`scalar deleting destructor'(uint)
0x18000b4ae  mov     rbx, [rsp+78h+arg_10]
0x18000b4b6  mov     eax, edi
0x18000b4b8  add     rsp, 40h
0x18000b4bc  pop     r15
0x18000b4be  pop     r14
0x18000b4c0  pop     r13
0x18000b4c2  pop     r12
0x18000b4c4  pop     rdi
0x18000b4c5  pop     rsi
0x18000b4c6  pop     rbp
0x18000b4c7  retn
```
