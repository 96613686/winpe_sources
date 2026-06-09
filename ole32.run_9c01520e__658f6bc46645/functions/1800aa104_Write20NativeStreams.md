# Write20NativeStreams

- ea: `0x1800aa104`
- end: `0x1800aa357`
- name: `Write20NativeStreams`
- size: `595`
- prototype: `__int64 __fastcall(IStorage *pstg, const CGenericObject *genobj)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800a758c`

## callees

- `0x1800077fc`
- `0x1800aa104`
- `0x1800ab800`
- `0x1800aba70`
- `0x1800adda4`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa2f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa2f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa27d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa27d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800aa2bf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800aa2bf`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800aa136`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800aa136`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x1800aa150`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x1800aa150`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x1800aa18b`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x1800aa18b`

## pseudocode

```c
__int64 __fastcall Write20NativeStreams(IStorage *pstg, const CGenericObject *genobj)
{
  HRESULT v4; // ebx
  IStorage *v6; // rdx
  int v7; // r8d
  unsigned int v8; // r9d
  void *m_pv; // rsi
  wchar_t *m_szItem; // rcx
  unsigned int v11; // ebx
  char *lpMultiByteStr; // rsi
  wchar_t *v13; // r8
  IStorage *pstgNative; // [rsp+40h] [rbp-10h] BYREF
  IStream *pstmNative; // [rsp+48h] [rbp-8h] BYREF
  unsigned int cb; // [rsp+88h] [rbp+38h] BYREF
  int fDefUsed; // [rsp+90h] [rbp+40h] BYREF
  ILockBytes *plkbyt; // [rsp+98h] [rbp+48h] BYREF

  plkbyt = 0;
  pstgNative = 0;
  pstmNative = 0;
  v4 = CreateILockBytesOnHGlobal(genobj->m_dataNative.m_h, 0, &plkbyt);
  if ( v4 >= 0 )
  {
    if ( StgIsStorageILockBytes(plkbyt) )
    {
      cb = 0;
      m_pv = genobj->m_dataNative.m_pv;
      if ( !m_pv )
        goto LABEL_7;
      v4 = OpenOrCreateStream(pstg, &szName, &pstmNative);
      if ( v4 < 0 )
        goto LABEL_18;
      v4 = ((__int64 (__fastcall *)(IStream *, CData *, __int64, unsigned int *))pstmNative->lpVtbl->Write)(
             pstmNative,
             &genobj->m_dataNative,
             4,
             &cb);
      if ( v4 < 0 )
        goto LABEL_18;
      v4 = ((__int64 (__fastcall *)(IStream *, void *, _QWORD, unsigned int *))pstmNative->lpVtbl->Write)(
             pstmNative,
             m_pv,
             genobj->m_dataNative.m_cbSize,
             &cb);
      if ( v4 < 0 )
        goto LABEL_18;
      m_szItem = genobj->m_szItem;
      if ( !m_szItem )
        goto LABEL_18;
      v11 = safe_lstrlenW(m_szItem) + 1;
      lpMultiByteStr = (char *)HeapAlloc(g_hHeap, 0, 2LL * v11);
      if ( !lpMultiByteStr )
      {
LABEL_7:
        v4 = -2147024882;
        goto LABEL_18;
      }
      v13 = genobj->m_szItem;
      fDefUsed = 0;
      if ( !WideCharToMultiByte(0, 0, v13, v11, lpMultiByteStr, 2 * v11, 0, &fDefUsed) || fDefUsed )
        v4 = -2147467259;
      else
        v4 = StSave10ItemName(pstg, lpMultiByteStr);
      HeapFree(g_hHeap, 0, lpMultiByteStr);
    }
    else
    {
      v4 = StgOpenStorageOnILockBytes(plkbyt, 0, 0x12u, 0, 0, &pstgNative);
      if ( v4 >= 0 )
      {
        v4 = UtDoStreamOperation(pstgNative, v6, v7, v8);
        if ( v4 >= 0 )
          v4 = ((__int64 (__fastcall *)(IStorage *, _QWORD, _QWORD, _QWORD, IStorage *))pstgNative->lpVtbl->CopyTo)(
                 pstgNative,
                 0,
                 0,
                 0,
                 pstg);
      }
    }
  }
LABEL_18:
  if ( plkbyt )
    ((void (__fastcall *)(ILockBytes *))plkbyt->lpVtbl->Release)(plkbyt);
  if ( pstgNative )
    ((void (__fastcall *)(IStorage *))pstgNative->lpVtbl->Release)(pstgNative);
  if ( pstmNative )
    ((void (__fastcall *)(IStream *))pstmNative->lpVtbl->Release)(pstmNative);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800aa104  mov     [rsp-28h+arg_0], rbx
0x1800aa109  push    rbp
0x1800aa10a  push    rsi
0x1800aa10b  push    rdi
0x1800aa10c  push    r14
0x1800aa10e  push    r15
0x1800aa110  mov     rbp, rsp
0x1800aa113  sub     rsp, 50h
0x1800aa117  and     [rbp+plkbyt], 0
0x1800aa11c  lea     r8, [rbp+plkbyt]; pplkbyt
0x1800aa120  and     [rbp+pstgNative], 0
0x1800aa125  mov     rdi, genobj
0x1800aa128  and     [rbp+pstmNative], 0
0x1800aa12d  mov     r14, pstg
0x1800aa130  xor     edx, edx; fDeleteOnRelease
0x1800aa132  mov     pstg, [rdi+48h]; hGlobal
0x1800aa136  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800aa13d  nop     dword ptr [rax+rax+00h]
0x1800aa142  mov     ebx, eax
0x1800aa144  test    eax, eax
0x1800aa146  js      loc_1800AA301
0x1800aa14c  mov     pstg, [rbp+plkbyt]; plkbyt
0x1800aa150  call    cs:__imp_StgIsStorageILockBytes
0x1800aa157  nop     dword ptr [rax+rax+00h]
0x1800aa15c  xor     ecx, ecx
0x1800aa15e  test    eax, eax
0x1800aa160  setz    cl
0x1800aa163  test    ecx, ecx
0x1800aa165  jz      short loc_1800AA1D8
0x1800aa167  cmp     ecx, 1
0x1800aa16a  jnz     loc_1800AA301
0x1800aa170  lea     rax, [rbp+pstgNative]
0x1800aa174  xor     r9d, r9d; snbExclude
0x1800aa177  lea     r8d, [pstg+11h]; grfMode
0x1800aa17b  mov     [rsp+50h+ppstgOpen], rax; ppstgOpen
0x1800aa180  mov     pstg, [rbp+plkbyt]; plkbyt
0x1800aa184  xor     edx, edx; pstgPriority
0x1800aa186  and     dword ptr [rsp+50h+lpMultiByteStr], 0
0x1800aa18b  call    cs:__imp_StgOpenStorageOnILockBytes
0x1800aa192  nop     dword ptr [rax+rax+00h]
0x1800aa197  mov     ebx, eax
0x1800aa199  test    eax, eax
0x1800aa19b  js      loc_1800AA301
0x1800aa1a1  mov     pstg, [rbp+pstgNative]; pstgSrc
0x1800aa1a5  call    UtDoStreamOperation
0x1800aa1aa  mov     ebx, eax
0x1800aa1ac  test    eax, eax
0x1800aa1ae  js      loc_1800AA301
0x1800aa1b4  mov     pstg, [rbp+pstgNative]
0x1800aa1b8  xor     r9d, r9d
0x1800aa1bb  xor     r8d, r8d
0x1800aa1be  mov     [rsp+50h+lpMultiByteStr], r14
0x1800aa1c3  xor     edx, edx
0x1800aa1c5  mov     rax, [pstg]
0x1800aa1c8  mov     rax, [rax+38h]
0x1800aa1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa1d1  mov     ebx, eax
0x1800aa1d3  jmp     loc_1800AA301
0x1800aa1d8  and     [rbp+cb], 0
0x1800aa1dc  mov     rsi, [rdi+40h]
0x1800aa1e0  test    rsi, rsi
0x1800aa1e3  jnz     short loc_1800AA1EF
0x1800aa1e5  mov     ebx, 8007000Eh
0x1800aa1ea  jmp     loc_1800AA301
0x1800aa1ef  lea     r8, [rbp+pstmNative]; ppstm
0x1800aa1f3  mov     pstg, r14; pstg
0x1800aa1f6  lea     genobj, szName; pwcsName
0x1800aa1fd  call    OpenOrCreateStream
0x1800aa202  mov     ebx, eax
0x1800aa204  test    eax, eax
0x1800aa206  js      loc_1800AA301
0x1800aa20c  mov     pstg, [rbp+pstmNative]
0x1800aa210  lea     r9, [rbp+cb]
0x1800aa214  mov     r8d, 4
0x1800aa21a  lea     genobj, [rdi+38h]
0x1800aa21e  mov     rax, [pstg]
0x1800aa221  mov     rax, [rax+20h]
0x1800aa225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa22a  mov     ebx, eax
0x1800aa22c  test    eax, eax
0x1800aa22e  js      loc_1800AA301
0x1800aa234  mov     pstg, [rbp+pstmNative]
0x1800aa238  lea     r9, [rbp+cb]
0x1800aa23c  mov     r8d, [rdi+38h]
0x1800aa240  mov     genobj, rsi
0x1800aa243  mov     rax, [pstg]
0x1800aa246  mov     rax, [rax+20h]
0x1800aa24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa24f  mov     ebx, eax
0x1800aa251  test    eax, eax
0x1800aa253  js      loc_1800AA301
0x1800aa259  mov     pstg, [rdi+70h]; string
0x1800aa25d  test    pstg, pstg
0x1800aa260  jz      loc_1800AA301
0x1800aa266  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800aa26b  mov     pstg, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800aa272  xor     edx, edx; dwFlags
0x1800aa274  lea     ebx, [rax+1]
0x1800aa277  mov     r8d, ebx
0x1800aa27a  add     r8, r8; dwBytes
0x1800aa27d  call    cs:__imp_HeapAlloc
0x1800aa284  nop     dword ptr [rax+rax+00h]
0x1800aa289  mov     rsi, rax
0x1800aa28c  test    rax, rax
0x1800aa28f  jz      loc_1800AA1E5
0x1800aa295  mov     r8, [rdi+70h]; lpWideCharStr
0x1800aa299  lea     pstg, [rbp+fDefUsed]
0x1800aa29d  and     [rbp+fDefUsed], 0
0x1800aa2a1  lea     eax, [rbx+rbx]
0x1800aa2a4  mov     [rsp+50h+lpUsedDefaultChar], pstg; lpUsedDefaultChar
0x1800aa2a9  mov     r9d, ebx; cchWideChar
0x1800aa2ac  and     [rsp+50h+var_20], 0
0x1800aa2b2  xor     edx, edx; dwFlags
0x1800aa2b4  mov     dword ptr [rsp+50h+ppstgOpen], eax; cbMultiByte
0x1800aa2b8  xor     ecx, ecx; CodePage
0x1800aa2ba  mov     [rsp+50h+lpMultiByteStr], rsi; lpMultiByteStr
0x1800aa2bf  call    cs:__imp_WideCharToMultiByte
0x1800aa2c6  nop     dword ptr [rax+rax+00h]
0x1800aa2cb  test    eax, eax
0x1800aa2cd  jz      short loc_1800AA2E4
0x1800aa2cf  cmp     [rbp+fDefUsed], 0
0x1800aa2d3  jnz     short loc_1800AA2E4
0x1800aa2d5  mov     genobj, rsi; szItemNameAnsi
0x1800aa2d8  mov     pstg, r14; pstg
0x1800aa2db  call    ?StSave10ItemName@@YAJPEAUIStorage@@PEBD@Z; StSave10ItemName(IStorage *,char const *)
0x1800aa2e0  mov     ebx, eax
0x1800aa2e2  jmp     short loc_1800AA2E9
0x1800aa2e4  mov     ebx, 80004005h
0x1800aa2e9  mov     pstg, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800aa2f0  mov     r8, rsi; lpMem
0x1800aa2f3  xor     edx, edx; dwFlags
0x1800aa2f5  call    cs:__imp_HeapFree
0x1800aa2fc  nop     dword ptr [rax+rax+00h]
0x1800aa301  mov     pstg, [rbp+plkbyt]
0x1800aa305  test    pstg, pstg
0x1800aa308  jz      short loc_1800AA316
0x1800aa30a  mov     rax, [pstg]
0x1800aa30d  mov     rax, [rax+10h]
0x1800aa311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa316  mov     pstg, [rbp+pstgNative]
0x1800aa31a  test    pstg, pstg
0x1800aa31d  jz      short loc_1800AA32B
0x1800aa31f  mov     rax, [pstg]
0x1800aa322  mov     rax, [rax+10h]
0x1800aa326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa32b  mov     pstg, [rbp+pstmNative]
0x1800aa32f  test    pstg, pstg
0x1800aa332  jz      short loc_1800AA340
0x1800aa334  mov     rax, [pstg]
0x1800aa337  mov     rax, [rax+10h]
0x1800aa33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa340  mov     eax, ebx
0x1800aa342  mov     rbx, [rsp+50h+arg_0]
0x1800aa34a  add     rsp, 50h
0x1800aa34e  pop     r15
0x1800aa350  pop     r14
0x1800aa352  pop     rdi
0x1800aa353  pop     rsi
0x1800aa354  pop     rbp
0x1800aa355  retn
```
