# Read20NativeStreams

- ea: `0x1800a2e4c`
- end: `0x1800a3081`
- name: `Read20NativeStreams`
- size: `565`
- prototype: `__int64 __fastcall(IStorage *pstg, CData *pdata)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004f258`

## callees

- `0x18000b2d4`
- `0x180052390`
- `0x180053014`
- `0x1800a2640`
- `0x1800a2e4c`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800a2f01`
- `KERNELBASE!GlobalAlloc` at `0x1800a2f01`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a2f21`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a3008`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a2f21`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a3008`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x1800a2ff8`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x1800a2ff8`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800a2f69`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800a2f69`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800a2f89`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800a2f89`

## pseudocode

```c
__int64 __fastcall Read20NativeStreams(IStorage *pstg, CData *pdata)
{
  HRESULT HGlobalFromILockBytes; // ebx
  unsigned __int64 m_cbSize; // rbx
  HGLOBAL v6; // rax
  void *v7; // rax
  ILockBytes *v8; // rcx
  void *v9; // rax
  int v10; // ecx
  unsigned int cbRead; // [rsp+30h] [rbp-39h] BYREF
  ILockBytes *plkbyt; // [rsp+38h] [rbp-31h] BYREF
  IStream *pstm; // [rsp+40h] [rbp-29h] BYREF
  IStorage *pstgNative; // [rsp+48h] [rbp-21h] BYREF
  tagSTATSTG statstg; // [rsp+50h] [rbp-19h] BYREF

  pstm = 0;
  plkbyt = 0;
  pstgNative = 0;
  if ( OpenStream(pstg, (wchar_t *)&szName, &pstm) )
  {
    HGlobalFromILockBytes = CreateILockBytesOnHGlobal(0, 0, &plkbyt);
    if ( HGlobalFromILockBytes >= 0 )
    {
      HGlobalFromILockBytes = StgCreateDocfileOnILockBytes(plkbyt, 0x1012u, 0, &pstgNative);
      if ( HGlobalFromILockBytes >= 0 )
      {
        HGlobalFromILockBytes = ((__int64 (__fastcall *)(IStorage *, _QWORD, _QWORD, _QWORD, IStorage *))pstg->lpVtbl->CopyTo)(
                                  pstg,
                                  0,
                                  0,
                                  0,
                                  pstgNative);
        if ( HGlobalFromILockBytes >= 0 )
        {
          memset_0(&statstg, 0, sizeof(statstg));
          HGlobalFromILockBytes = ((__int64 (__fastcall *)(ILockBytes *, tagSTATSTG *, _QWORD))plkbyt->lpVtbl[3].QueryInterface)(
                                    plkbyt,
                                    &statstg,
                                    0);
          if ( HGlobalFromILockBytes >= 0 )
          {
            v8 = plkbyt;
            pdata->m_cbSize = statstg.cbSize.LowPart;
            HGlobalFromILockBytes = GetHGlobalFromILockBytes(v8, &pdata->m_h);
            if ( HGlobalFromILockBytes >= 0 )
            {
              v9 = GlobalLock(pdata->m_h);
              v10 = HGlobalFromILockBytes;
              pdata->m_pv = v9;
              if ( !v9 )
                v10 = -2147024882;
              HGlobalFromILockBytes = v10;
            }
          }
        }
      }
    }
  }
  else
  {
    cbRead = 0;
    HGlobalFromILockBytes = ((__int64 (__fastcall *)(IStream *, CData *, __int64, unsigned int *))pstm->lpVtbl->Read)(
                              pstm,
                              pdata,
                              4,
                              &cbRead);
    if ( HGlobalFromILockBytes < 0 )
      goto LABEL_22;
    if ( cbRead != 4 )
      goto LABEL_4;
    m_cbSize = pdata->m_cbSize;
    if ( m_cbSize >= GetSafeAllocSize() )
      v6 = 0;
    else
      v6 = GlobalAlloc(2u, (unsigned int)m_cbSize);
    pdata->m_h = v6;
    if ( v6 && (v7 = GlobalLock(v6), (pdata->m_pv = v7) != 0) )
    {
      HGlobalFromILockBytes = ((__int64 (__fastcall *)(IStream *, void *, _QWORD, unsigned int *))pstm->lpVtbl->Read)(
                                pstm,
                                v7,
                                pdata->m_cbSize,
                                &cbRead);
      if ( HGlobalFromILockBytes >= 0 && pdata->m_cbSize != cbRead )
LABEL_4:
        HGlobalFromILockBytes = -2147287010;
    }
    else
    {
      HGlobalFromILockBytes = -2147024882;
    }
  }
LABEL_22:
  if ( pstm )
    ((void (__fastcall *)(IStream *))pstm->lpVtbl->Release)(pstm);
  if ( plkbyt )
    ((void (__fastcall *)(ILockBytes *))plkbyt->lpVtbl->Release)(plkbyt);
  if ( pstgNative )
    ((void (__fastcall *)(IStorage *))pstgNative->lpVtbl->Release)(pstgNative);
  return (unsigned int)HGlobalFromILockBytes;
}

```

## disassembly

```asm
0x1800a2e4c  mov     [rsp-8+arg_10], rbx
0x1800a2e51  push    rbp
0x1800a2e52  push    rsi
0x1800a2e53  push    rdi
0x1800a2e54  lea     rbp, [rsp-47h]
0x1800a2e59  sub     rsp, 0B0h
0x1800a2e60  mov     rax, cs:__security_cookie
0x1800a2e67  xor     rax, rsp
0x1800a2e6a  mov     [rbp+57h+var_20], rax
0x1800a2e6e  mov     rdi, pdata
0x1800a2e71  mov     [rbp+57h+pstm], 0
0x1800a2e79  lea     pdata, szName; szName
0x1800a2e80  mov     [rbp+57h+plkbyt], 0
0x1800a2e88  lea     r8, [rbp+57h+pstm]; ppstm
0x1800a2e8c  mov     [rbp+57h+pstgNative], 0
0x1800a2e94  mov     rsi, pstg
0x1800a2e97  xor     ebx, ebx
0x1800a2e99  call    OpenStream
0x1800a2e9e  xor     ecx, ecx
0x1800a2ea0  test    eax, eax
0x1800a2ea2  setz    cl
0x1800a2ea5  test    ecx, ecx
0x1800a2ea7  jz      loc_1800A2F61
0x1800a2ead  cmp     ecx, 1
0x1800a2eb0  jnz     loc_1800A3021
0x1800a2eb6  mov     pstg, [rbp+57h+pstm]
0x1800a2eba  lea     r9, [rbp+57h+cbRead]
0x1800a2ebe  mov     [rbp+57h+cbRead], ebx
0x1800a2ec1  lea     r8d, [rbx+4]
0x1800a2ec5  mov     pdata, rdi
0x1800a2ec8  mov     rax, [pstg]
0x1800a2ecb  mov     rax, [rax+18h]
0x1800a2ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2ed4  mov     ebx, eax
0x1800a2ed6  test    eax, eax
0x1800a2ed8  js      loc_1800A3021
0x1800a2ede  cmp     [rbp+57h+cbRead], 4
0x1800a2ee2  jz      short loc_1800A2EEE
0x1800a2ee4  mov     ebx, 8003001Eh
0x1800a2ee9  jmp     loc_1800A3021
0x1800a2eee  mov     ebx, [rdi]
0x1800a2ef0  call    GetSafeAllocSize
0x1800a2ef5  cmp     rbx, rax
0x1800a2ef8  jnb     short loc_1800A2F09
0x1800a2efa  mov     edx, ebx; dwBytes
0x1800a2efc  mov     ecx, 2; uFlags
0x1800a2f01  call    cs:__imp_GlobalAlloc
0x1800a2f07  jmp     short loc_1800A2F0B
0x1800a2f09  xor     eax, eax
0x1800a2f0b  mov     [rdi+10h], rax
0x1800a2f0f  test    rax, rax
0x1800a2f12  jnz     short loc_1800A2F1E
0x1800a2f14  mov     ebx, 8007000Eh
0x1800a2f19  jmp     loc_1800A3021
0x1800a2f1e  mov     pstg, rax; hMem
0x1800a2f21  call    cs:__imp_GlobalLock
0x1800a2f27  mov     [rdi+8], rax
0x1800a2f2b  mov     pdata, rax
0x1800a2f2e  test    rax, rax
0x1800a2f31  jz      short loc_1800A2F14
0x1800a2f33  mov     pstg, [rbp+57h+pstm]
0x1800a2f37  lea     r9, [rbp+57h+cbRead]
0x1800a2f3b  mov     r8d, [rdi]
0x1800a2f3e  mov     rax, [pstg]
0x1800a2f41  mov     rax, [rax+18h]
0x1800a2f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f4a  mov     ebx, eax
0x1800a2f4c  test    eax, eax
0x1800a2f4e  js      loc_1800A3021
0x1800a2f54  mov     eax, [rbp+57h+cbRead]
0x1800a2f57  cmp     [rdi], eax
0x1800a2f59  jz      loc_1800A3021
0x1800a2f5f  jmp     short loc_1800A2EE4
0x1800a2f61  lea     r8, [rbp+57h+plkbyt]; pplkbyt
0x1800a2f65  xor     edx, edx; fDeleteOnRelease
0x1800a2f67  xor     ecx, ecx; hGlobal
0x1800a2f69  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800a2f6f  mov     ebx, eax
0x1800a2f71  test    eax, eax
0x1800a2f73  js      loc_1800A3021
0x1800a2f79  mov     pstg, [rbp+57h+plkbyt]; plkbyt
0x1800a2f7d  lea     r9, [rbp+57h+pstgNative]; ppstgOpen
0x1800a2f81  xor     r8d, r8d; reserved
0x1800a2f84  mov     edx, 1012h; grfMode
0x1800a2f89  call    cs:__imp_StgCreateDocfileOnILockBytes
0x1800a2f8f  mov     ebx, eax
0x1800a2f91  test    eax, eax
0x1800a2f93  js      loc_1800A3021
0x1800a2f99  mov     pdata, [rbp+57h+pstgNative]
0x1800a2f9d  xor     r9d, r9d
0x1800a2fa0  mov     rax, [rsi]
0x1800a2fa3  xor     r8d, r8d
0x1800a2fa6  mov     [rsp+0C0h+var_A0], pdata
0x1800a2fab  mov     pstg, rsi
0x1800a2fae  xor     edx, edx
0x1800a2fb0  mov     rax, [rax+38h]
0x1800a2fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2fb9  mov     ebx, eax
0x1800a2fbb  test    eax, eax
0x1800a2fbd  js      short loc_1800A3021
0x1800a2fbf  xor     edx, edx; Val
0x1800a2fc1  lea     pstg, [rbp+57h+statstg]; void *
0x1800a2fc5  lea     r8d, [pdata+50h]; Size
0x1800a2fc9  call    memset_0
0x1800a2fce  mov     pstg, [rbp+57h+plkbyt]
0x1800a2fd2  lea     pdata, [rbp+57h+statstg]
0x1800a2fd6  xor     r8d, r8d
0x1800a2fd9  mov     rax, [pstg]
0x1800a2fdc  mov     rax, [rax+48h]
0x1800a2fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2fe5  mov     ebx, eax
0x1800a2fe7  test    eax, eax
0x1800a2fe9  js      short loc_1800A3021
0x1800a2feb  mov     eax, dword ptr [rbp+57h+statstg.cbSize]
0x1800a2fee  lea     pdata, [rdi+10h]; phglobal
0x1800a2ff2  mov     pstg, [rbp+57h+plkbyt]; plkbyt
0x1800a2ff6  mov     [rdi], eax
0x1800a2ff8  call    cs:__imp_GetHGlobalFromILockBytes
0x1800a2ffe  mov     ebx, eax
0x1800a3000  test    eax, eax
0x1800a3002  js      short loc_1800A3021
0x1800a3004  mov     pstg, [rdi+10h]; hMem
0x1800a3008  call    cs:__imp_GlobalLock
0x1800a300e  mov     ecx, ebx
0x1800a3010  mov     ebx, 8007000Eh
0x1800a3015  test    rax, rax
0x1800a3018  mov     [rdi+8], rax
0x1800a301c  cmovz   ecx, ebx
0x1800a301f  mov     ebx, ecx
0x1800a3021  mov     pstg, [rbp+57h+pstm]
0x1800a3025  test    pstg, pstg
0x1800a3028  jz      short loc_1800A3036
0x1800a302a  mov     rax, [pstg]
0x1800a302d  mov     rax, [rax+10h]
0x1800a3031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3036  mov     pstg, [rbp+57h+plkbyt]
0x1800a303a  test    pstg, pstg
0x1800a303d  jz      short loc_1800A304B
0x1800a303f  mov     rax, [pstg]
0x1800a3042  mov     rax, [rax+10h]
0x1800a3046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a304b  mov     pstg, [rbp+57h+pstgNative]
0x1800a304f  test    pstg, pstg
0x1800a3052  jz      short loc_1800A3060
0x1800a3054  mov     rax, [pstg]
0x1800a3057  mov     rax, [rax+10h]
0x1800a305b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3060  mov     eax, ebx
0x1800a3062  mov     pstg, [rbp+57h+var_20]
0x1800a3066  xor     pstg, rsp; StackCookie
0x1800a3069  call    __security_check_cookie
0x1800a306e  mov     rbx, [rsp+0C0h+arg_10]
0x1800a3076  add     rsp, 0B0h
0x1800a307d  pop     rdi
0x1800a307e  pop     rsi
0x1800a307f  pop     rbp
0x1800a3080  retn
```
