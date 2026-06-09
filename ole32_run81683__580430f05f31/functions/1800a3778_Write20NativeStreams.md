# Write20NativeStreams

- ea: `0x1800a3778`
- end: `0x1800a39bb`
- name: `Write20NativeStreams`
- size: `579`
- prototype: `HRESULT __fastcall(IStorage *pstg, const CGenericObject *genobj)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800a1474`

## callees

- `0x180009374`
- `0x1800a3778`
- `0x1800a4afc`
- `0x1800a4d70`
- `0x1800a6c2c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a3960`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a3960`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a38ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a38ee`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800a3930`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800a3930`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800a37b3`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800a37b3`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x1800a37c7`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x1800a37c7`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x1800a37ff`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x1800a37ff`

## pseudocode

```c
__int64 __fastcall Write20NativeStreams(IStorage *pstg, const CGenericObject *genobj)
{
  int v4; // ebx
  IStorage *v6; // rdx
  int v7; // r8d
  unsigned int v8; // r9d
  void *m_pv; // rsi
  wchar_t *m_szItem; // rcx
  unsigned int v11; // ebx
  char *v12; // rsi
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
      m_pv = genobj->m_dataNative.m_pv;
      cb = 0;
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
      v12 = (char *)HeapAlloc(g_hHeap, 0, 2LL * v11);
      if ( !v12 )
      {
LABEL_7:
        v4 = -2147024882;
        goto LABEL_18;
      }
      v13 = genobj->m_szItem;
      fDefUsed = 0;
      if ( !WideCharToMultiByte(0, 0, v13, v11, v12, 2 * v11, 0, &fDefUsed) || fDefUsed )
        v4 = -2147467259;
      else
        v4 = StSave10ItemName(pstg, v12);
      HeapFree(g_hHeap, 0, v12);
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
0x1800a3778  mov     [rsp-28h+arg_0], rbx
0x1800a377d  push    rbp
0x1800a377e  push    rsi
0x1800a377f  push    rdi
0x1800a3780  push    r14
0x1800a3782  push    r15
0x1800a3784  mov     rbp, rsp
0x1800a3787  sub     rsp, 50h
0x1800a378b  mov     rdi, genobj
0x1800a378e  mov     [rbp+plkbyt], 0
0x1800a3796  mov     r14, pstg
0x1800a3799  mov     [rbp+pstgNative], 0
0x1800a37a1  lea     r8, [rbp+plkbyt]; pplkbyt
0x1800a37a5  mov     [rbp+pstmNative], 0
0x1800a37ad  xor     edx, edx; fDeleteOnRelease
0x1800a37af  mov     pstg, [rdi+48h]; hGlobal
0x1800a37b3  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800a37b9  mov     ebx, eax
0x1800a37bb  test    eax, eax
0x1800a37bd  js      loc_1800A3966
0x1800a37c3  mov     pstg, [rbp+plkbyt]; plkbyt
0x1800a37c7  call    cs:__imp_StgIsStorageILockBytes
0x1800a37cd  xor     ecx, ecx
0x1800a37cf  test    eax, eax
0x1800a37d1  setz    cl
0x1800a37d4  test    ecx, ecx
0x1800a37d6  jz      short loc_1800A3846
0x1800a37d8  cmp     ecx, 1
0x1800a37db  jnz     loc_1800A3966
0x1800a37e1  lea     rax, [rbp+pstgNative]
0x1800a37e5  xor     r9d, r9d; snbExclude
0x1800a37e8  lea     r8d, [pstg+11h]; grfMode
0x1800a37ec  mov     [rsp+50h+ppstgOpen], rax; ppstgOpen
0x1800a37f1  mov     pstg, [rbp+plkbyt]; plkbyt
0x1800a37f5  xor     edx, edx; pstgPriority
0x1800a37f7  mov     [rsp+50h+reserved], 0; reserved
0x1800a37ff  call    cs:__imp_StgOpenStorageOnILockBytes
0x1800a3805  mov     ebx, eax
0x1800a3807  test    eax, eax
0x1800a3809  js      loc_1800A3966
0x1800a380f  mov     pstg, [rbp+pstgNative]; pstgSrc
0x1800a3813  call    UtDoStreamOperation
0x1800a3818  mov     ebx, eax
0x1800a381a  test    eax, eax
0x1800a381c  js      loc_1800A3966
0x1800a3822  mov     pstg, [rbp+pstgNative]
0x1800a3826  xor     r9d, r9d
0x1800a3829  xor     r8d, r8d
0x1800a382c  mov     qword ptr [rsp+50h+reserved], r14
0x1800a3831  xor     edx, edx
0x1800a3833  mov     rax, [pstg]
0x1800a3836  mov     rax, [rax+38h]
0x1800a383a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a383f  mov     ebx, eax
0x1800a3841  jmp     loc_1800A3966
0x1800a3846  mov     rsi, [rdi+40h]
0x1800a384a  mov     [rbp+cb], 0
0x1800a3851  test    rsi, rsi
0x1800a3854  jnz     short loc_1800A3860
0x1800a3856  mov     ebx, 8007000Eh
0x1800a385b  jmp     loc_1800A3966
0x1800a3860  lea     r8, [rbp+pstmNative]; ppstm
0x1800a3864  mov     pstg, r14; pstg
0x1800a3867  lea     genobj, szName; pwcsName
0x1800a386e  call    OpenOrCreateStream
0x1800a3873  mov     ebx, eax
0x1800a3875  test    eax, eax
0x1800a3877  js      loc_1800A3966
0x1800a387d  mov     pstg, [rbp+pstmNative]
0x1800a3881  lea     r9, [rbp+cb]
0x1800a3885  mov     r8d, 4
0x1800a388b  lea     genobj, [rdi+38h]
0x1800a388f  mov     rax, [pstg]
0x1800a3892  mov     rax, [rax+20h]
0x1800a3896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a389b  mov     ebx, eax
0x1800a389d  test    eax, eax
0x1800a389f  js      loc_1800A3966
0x1800a38a5  mov     pstg, [rbp+pstmNative]
0x1800a38a9  lea     r9, [rbp+cb]
0x1800a38ad  mov     r8d, [rdi+38h]
0x1800a38b1  mov     genobj, rsi
0x1800a38b4  mov     rax, [pstg]
0x1800a38b7  mov     rax, [rax+20h]
0x1800a38bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a38c0  mov     ebx, eax
0x1800a38c2  test    eax, eax
0x1800a38c4  js      loc_1800A3966
0x1800a38ca  mov     pstg, [rdi+70h]; string
0x1800a38ce  test    pstg, pstg
0x1800a38d1  jz      loc_1800A3966
0x1800a38d7  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800a38dc  mov     pstg, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800a38e3  xor     edx, edx; dwFlags
0x1800a38e5  lea     ebx, [rax+1]
0x1800a38e8  mov     r8d, ebx
0x1800a38eb  add     r8, r8; dwBytes
0x1800a38ee  call    cs:__imp_HeapAlloc
0x1800a38f4  mov     rsi, rax
0x1800a38f7  test    rax, rax
0x1800a38fa  jz      loc_1800A3856
0x1800a3900  mov     r8, [rdi+70h]; lpWideCharStr
0x1800a3904  lea     pstg, [rbp+fDefUsed]
0x1800a3908  mov     [rsp+50h+lpUsedDefaultChar], pstg; lpUsedDefaultChar
0x1800a390d  lea     eax, [rbx+rbx]
0x1800a3910  mov     [rsp+50h+lpDefaultChar], 0; lpDefaultChar
0x1800a3919  mov     r9d, ebx; cchWideChar
0x1800a391c  mov     dword ptr [rsp+50h+ppstgOpen], eax; cbMultiByte
0x1800a3920  xor     edx, edx; dwFlags
0x1800a3922  xor     ecx, ecx; CodePage
0x1800a3924  mov     qword ptr [rsp+50h+reserved], rsi; lpMultiByteStr
0x1800a3929  mov     [rbp+fDefUsed], 0
0x1800a3930  call    cs:__imp_WideCharToMultiByte
0x1800a3936  test    eax, eax
0x1800a3938  jz      short loc_1800A394F
0x1800a393a  cmp     [rbp+fDefUsed], 0
0x1800a393e  jnz     short loc_1800A394F
0x1800a3940  mov     genobj, rsi; szItemNameAnsi
0x1800a3943  mov     pstg, r14; pstg
0x1800a3946  call    ?StSave10ItemName@@YAJPEAUIStorage@@PEBD@Z; StSave10ItemName(IStorage *,char const *)
0x1800a394b  mov     ebx, eax
0x1800a394d  jmp     short loc_1800A3954
0x1800a394f  mov     ebx, 80004005h
0x1800a3954  mov     pstg, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800a395b  mov     r8, rsi; lpMem
0x1800a395e  xor     edx, edx; dwFlags
0x1800a3960  call    cs:__imp_HeapFree
0x1800a3966  mov     pstg, [rbp+plkbyt]
0x1800a396a  test    pstg, pstg
0x1800a396d  jz      short loc_1800A397B
0x1800a396f  mov     rax, [pstg]
0x1800a3972  mov     rax, [rax+10h]
0x1800a3976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a397b  mov     pstg, [rbp+pstgNative]
0x1800a397f  test    pstg, pstg
0x1800a3982  jz      short loc_1800A3990
0x1800a3984  mov     rax, [pstg]
0x1800a3987  mov     rax, [rax+10h]
0x1800a398b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3990  mov     pstg, [rbp+pstmNative]
0x1800a3994  test    pstg, pstg
0x1800a3997  jz      short loc_1800A39A5
0x1800a3999  mov     rax, [pstg]
0x1800a399c  mov     rax, [rax+10h]
0x1800a39a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a39a5  mov     eax, ebx
0x1800a39a7  mov     rbx, [rsp+50h+arg_0]
0x1800a39af  add     rsp, 50h
0x1800a39b3  pop     r15
0x1800a39b5  pop     r14
0x1800a39b7  pop     rdi
0x1800a39b8  pop     rsi
0x1800a39b9  pop     rbp
0x1800a39ba  retn
```
