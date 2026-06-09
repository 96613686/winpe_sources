# InitStorageHelper(uchar *,ulong,IIS_CRYPTO_STORAGE * *)

- ea: `0x18001f8e4`
- end: `0x18001fa4f`
- name: `?InitStorageHelper@@YAJPEAEKPEAPEAVIIS_CRYPTO_STORAGE@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct IIS_CRYPTO_STORAGE **)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000ab6c`
- `0x18001f2c8`
- `0x18001f720`
- `0x180021330`

## callees

- `0x1800089c8`
- `0x180009bd0`
- `0x180014bb8`
- `0x18001f8e4`
- `0x1800292d0`
- `0x180029cf8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001f9fc`
- `ole32!CoTaskMemFree` at `0x18001f9fc`
- `IisRTL!PuDbgPrintW` at `0x18001f9df`
- `IisRTL!PuDbgPrintW` at `0x18001fa3a`
- `IisRTL!PuDbgPrintW` at `0x18001f9df`
- `IisRTL!PuDbgPrintW` at `0x18001fa3a`

## pseudocode

```c
__int64 __fastcall InitStorageHelper(unsigned __int8 *a1, int a2, struct IIS_CRYPTO_STORAGE **a3)
{
  int v4; // eax
  unsigned int v5; // edi
  IIS_CRYPTO_STORAGE *v6; // rax
  struct _IIS_CRYPTO_BLOB *v7; // rsi
  IIS_CRYPTO_STORAGE *v8; // rbx
  int CryptoProvider; // eax
  unsigned int v10; // edx
  int v11; // r8d
  int v12; // eax
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  pv = 0;
  v4 = IISCryptoCloneBlobFromRawData(&pv, a1, a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = (IIS_CRYPTO_STORAGE *)operator new(0x30u);
    v7 = (struct _IIS_CRYPTO_BLOB *)pv;
    v8 = v6;
    if ( v6 )
    {
      *((_QWORD *)v6 + 1) = 0;
      *((_DWORD *)v6 + 4) = 0;
      *((_QWORD *)v6 + 3) = 0;
      *((_QWORD *)v6 + 4) = 0;
      *(_QWORD *)v6 = &IIS_CRYPTO_STORAGE::`vftable';
      *((_QWORD *)v6 + 5) = 0;
      pv = 0;
      CryptoProvider = GetCryptoProvider((unsigned __int64 *)&pv);
      v5 = CryptoProvider;
      if ( CryptoProvider < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            1953,
            "InitStorageHelper",
            L"[InitStorageHelper] GetCryptoProvider failed with hr = 0x%x. (Crypto problem)\n",
            CryptoProvider);
      }
      else
      {
        v12 = IIS_CRYPTO_STORAGE::Initialize(v8, v7, v11, (unsigned __int64)pv);
        v5 = v12;
        if ( v12 >= 0 )
        {
LABEL_12:
          *(_BYTE *)v7 = 88;
          CoTaskMemFree(v7);
          goto LABEL_15;
        }
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            1947,
            "InitStorageHelper",
            L"[InitStorageHelper] IIS_CRYPTO_STORAGE::Initialize faile with hr = 0x%x.\n",
            v12);
      }
      IIS_CRYPTO_STORAGE::`scalar deleting destructor'(v8, v10);
    }
    else
    {
      v5 = -2147024882;
    }
    v8 = 0;
    goto LABEL_12;
  }
  v8 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      1968,
      "InitStorageHelper",
      L"[InitStorageHelper] IISCryptoCloneBlobFromRawData failed with hr = 0x%x. (Crypto problem).\n",
      v4);
LABEL_15:
  *a3 = v8;
  return v5;
}

```

## disassembly

```asm
0x18001f8e4  push    rbx
0x18001f8e6  push    rsi
0x18001f8e7  push    rdi
0x18001f8e8  push    r14
0x18001f8ea  sub     rsp, 38h
0x18001f8ee  mov     r14, r8
0x18001f8f1  mov     [rsp+58h+pv], 0
0x18001f8fa  mov     r8d, edx
0x18001f8fd  mov     rdx, rcx
0x18001f900  lea     rcx, [rsp+58h+pv]
0x18001f905  call    IISCryptoCloneBlobFromRawData
0x18001f90a  mov     edi, eax
0x18001f90c  test    eax, eax
0x18001f90e  js      loc_18001FA04
0x18001f914  mov     ecx, 30h ; '0'; Size
0x18001f919  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f91e  mov     rsi, [rsp+58h+pv]
0x18001f923  mov     rbx, rax
0x18001f926  test    rax, rax
0x18001f929  jz      loc_18001F9EF
0x18001f92f  mov     qword ptr [rax+8], 0
0x18001f937  lea     rcx, [rsp+58h+pv]; unsigned __int64 *
0x18001f93c  mov     dword ptr [rax+10h], 0
0x18001f943  mov     qword ptr [rax+18h], 0
0x18001f94b  mov     qword ptr [rax+20h], 0
0x18001f953  lea     rax, ??_7IIS_CRYPTO_STORAGE@@6B@; const IIS_CRYPTO_STORAGE::`vftable'
0x18001f95a  mov     [rbx], rax
0x18001f95d  mov     qword ptr [rbx+28h], 0
0x18001f965  mov     [rsp+58h+pv], 0
0x18001f96e  call    ?GetCryptoProvider@@YAJPEA_K@Z; GetCryptoProvider(unsigned __int64 *)
0x18001f973  mov     edi, eax
0x18001f975  test    eax, eax
0x18001f977  js      short loc_18001F9AB
0x18001f979  mov     r9, [rsp+58h+pv]; unsigned __int64
0x18001f97e  mov     rdx, rsi; struct _IIS_CRYPTO_BLOB *
0x18001f981  mov     rcx, rbx; this
0x18001f984  call    ?Initialize@IIS_CRYPTO_STORAGE@@QEAAJPEFAU_IIS_CRYPTO_BLOB@@H_K@Z; IIS_CRYPTO_STORAGE::Initialize(_IIS_CRYPTO_BLOB *,int,unsigned __int64)
0x18001f989  mov     edi, eax
0x18001f98b  test    eax, eax
0x18001f98d  jns     short loc_18001F9F6
0x18001f98f  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f996  jz      short loc_18001F9E5
0x18001f998  mov     [rsp+58h+var_30], eax
0x18001f99c  mov     r8d, 79Bh
0x18001f9a2  lea     rax, aInitstoragehel; "[InitStorageHelper] IIS_CRYPTO_STORAGE:"...
0x18001f9a9  jmp     short loc_18001F9C5
0x18001f9ab  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f9b2  jz      short loc_18001F9E5
0x18001f9b4  mov     [rsp+58h+var_30], eax
0x18001f9b8  mov     r8d, 7A1h
0x18001f9be  lea     rax, aInitstoragehel_0; "[InitStorageHelper] GetCryptoProvider f"...
0x18001f9c5  mov     rcx, cs:g_pDebug
0x18001f9cc  lea     r9, aInitstoragehel_3; "InitStorageHelper"
0x18001f9d3  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001f9da  mov     [rsp+58h+var_38], rax
0x18001f9df  call    cs:__imp_PuDbgPrintW
0x18001f9e5  mov     rcx, rbx; this
0x18001f9e8  call    ??_GIIS_CRYPTO_STORAGE@@QEAAPEAXI@Z; IIS_CRYPTO_STORAGE::`scalar deleting destructor'(uint)
0x18001f9ed  jmp     short loc_18001F9F4
0x18001f9ef  mov     edi, 8007000Eh
0x18001f9f4  xor     ebx, ebx
0x18001f9f6  mov     rcx, rsi; pv
0x18001f9f9  mov     byte ptr [rsi], 58h ; 'X'
0x18001f9fc  call    cs:__imp_CoTaskMemFree
0x18001fa02  jmp     short loc_18001FA40
0x18001fa04  xor     ebx, ebx
0x18001fa06  test    byte ptr cs:g_dwDebugFlags, 3
0x18001fa0d  jz      short loc_18001FA40
0x18001fa0f  mov     rcx, cs:g_pDebug
0x18001fa16  lea     r9, aInitstoragehel_3; "InitStorageHelper"
0x18001fa1d  mov     [rsp+58h+var_30], eax
0x18001fa21  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001fa28  lea     rax, aInitstoragehel_2; "[InitStorageHelper] IISCryptoCloneBlobF"...
0x18001fa2f  mov     r8d, 7B0h
0x18001fa35  mov     [rsp+58h+var_38], rax
0x18001fa3a  call    cs:__imp_PuDbgPrintW
0x18001fa40  mov     [r14], rbx
0x18001fa43  mov     eax, edi
0x18001fa45  add     rsp, 38h
0x18001fa49  pop     r14
0x18001fa4b  pop     rdi
0x18001fa4c  pop     rsi
0x18001fa4d  pop     rbx
0x18001fa4e  retn
```
