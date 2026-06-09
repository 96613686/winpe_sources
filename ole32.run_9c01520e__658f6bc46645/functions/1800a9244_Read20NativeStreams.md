# Read20NativeStreams

- ea: `0x1800a9244`
- end: `0x1800a9498`
- name: `Read20NativeStreams`
- size: `596`
- prototype: `__int64 __fastcall(IStorage *pstg, CData *pdata)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800a9d28`

## callees

- `0x18000a574`
- `0x180046460`
- `0x180047484`
- `0x1800a8964`
- `0x1800a9244`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800a92f0`
- `KERNELBASE!GlobalAlloc` at `0x1800a92f0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a9316`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a9418`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a9316`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a9418`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x1800a9402`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x1800a9402`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800a9367`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800a9367`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800a938d`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800a938d`

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
0x1800a9244  mov     [rsp-8+arg_10], rbx
0x1800a9249  push    rbp
0x1800a924a  push    rsi
0x1800a924b  push    rdi
0x1800a924c  lea     rbp, [rsp-47h]
0x1800a9251  sub     rsp, 0B0h
0x1800a9258  mov     rax, cs:__security_cookie
0x1800a925f  xor     rax, rsp
0x1800a9262  mov     [rbp+57h+var_20], rax
0x1800a9266  and     [rbp+57h+pstm], 0
0x1800a926b  lea     r8, [rbp+57h+pstm]; ppstm
0x1800a926f  and     [rbp+57h+plkbyt], 0
0x1800a9274  mov     rdi, pdata
0x1800a9277  and     [rbp+57h+pstgNative], 0
0x1800a927c  lea     pdata, szName; szName
0x1800a9283  mov     rsi, pstg
0x1800a9286  xor     ebx, ebx
0x1800a9288  call    OpenStream
0x1800a928d  xor     ecx, ecx
0x1800a928f  test    eax, eax
0x1800a9291  setz    cl
0x1800a9294  test    ecx, ecx
0x1800a9296  jz      loc_1800A935F
0x1800a929c  cmp     ecx, 1
0x1800a929f  jnz     loc_1800A9437
0x1800a92a5  mov     pstg, [rbp+57h+pstm]
0x1800a92a9  lea     r9, [rbp+57h+cbRead]
0x1800a92ad  and     [rbp+57h+cbRead], ebx
0x1800a92b0  lea     r8d, [rbx+4]
0x1800a92b4  mov     pdata, rdi
0x1800a92b7  mov     rax, [pstg]
0x1800a92ba  mov     rax, [rax+18h]
0x1800a92be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a92c3  mov     ebx, eax
0x1800a92c5  test    eax, eax
0x1800a92c7  js      loc_1800A9437
0x1800a92cd  cmp     [rbp+57h+cbRead], 4
0x1800a92d1  jz      short loc_1800A92DD
0x1800a92d3  mov     ebx, 8003001Eh
0x1800a92d8  jmp     loc_1800A9437
0x1800a92dd  mov     ebx, [rdi]
0x1800a92df  call    GetSafeAllocSize
0x1800a92e4  cmp     rbx, rax
0x1800a92e7  jnb     short loc_1800A92FE
0x1800a92e9  mov     edx, ebx; dwBytes
0x1800a92eb  mov     ecx, 2; uFlags
0x1800a92f0  call    cs:__imp_GlobalAlloc
0x1800a92f7  nop     dword ptr [rax+rax+00h]
0x1800a92fc  jmp     short loc_1800A9300
0x1800a92fe  xor     eax, eax
0x1800a9300  mov     [rdi+10h], rax
0x1800a9304  test    rax, rax
0x1800a9307  jnz     short loc_1800A9313
0x1800a9309  mov     ebx, 8007000Eh
0x1800a930e  jmp     loc_1800A9437
0x1800a9313  mov     pstg, rax; hMem
0x1800a9316  call    cs:__imp_GlobalLock
0x1800a931d  nop     dword ptr [rax+rax+00h]
0x1800a9322  mov     [rdi+8], rax
0x1800a9326  mov     pdata, rax
0x1800a9329  test    rax, rax
0x1800a932c  jz      short loc_1800A9309
0x1800a932e  mov     pstg, [rbp+57h+pstm]
0x1800a9332  lea     r9, [rbp+57h+cbRead]
0x1800a9336  mov     r8d, [rdi]
0x1800a9339  mov     rax, [pstg]
0x1800a933c  mov     rax, [rax+18h]
0x1800a9340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9345  mov     ebx, eax
0x1800a9347  test    eax, eax
0x1800a9349  js      loc_1800A9437
0x1800a934f  mov     eax, [rbp+57h+cbRead]
0x1800a9352  cmp     [rdi], eax
0x1800a9354  jz      loc_1800A9437
0x1800a935a  jmp     loc_1800A92D3
0x1800a935f  lea     r8, [rbp+57h+plkbyt]; pplkbyt
0x1800a9363  xor     edx, edx; fDeleteOnRelease
0x1800a9365  xor     ecx, ecx; hGlobal
0x1800a9367  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800a936e  nop     dword ptr [rax+rax+00h]
0x1800a9373  mov     ebx, eax
0x1800a9375  test    eax, eax
0x1800a9377  js      loc_1800A9437
0x1800a937d  mov     pstg, [rbp+57h+plkbyt]; plkbyt
0x1800a9381  lea     r9, [rbp+57h+pstgNative]; ppstgOpen
0x1800a9385  xor     r8d, r8d; reserved
0x1800a9388  mov     edx, 1012h; grfMode
0x1800a938d  call    cs:__imp_StgCreateDocfileOnILockBytes
0x1800a9394  nop     dword ptr [rax+rax+00h]
0x1800a9399  mov     ebx, eax
0x1800a939b  test    eax, eax
0x1800a939d  js      loc_1800A9437
0x1800a93a3  mov     pdata, [rbp+57h+pstgNative]
0x1800a93a7  xor     r9d, r9d
0x1800a93aa  mov     rax, [rsi]
0x1800a93ad  xor     r8d, r8d
0x1800a93b0  mov     [rsp+0C0h+var_A0], pdata
0x1800a93b5  mov     pstg, rsi
0x1800a93b8  xor     edx, edx
0x1800a93ba  mov     rax, [rax+38h]
0x1800a93be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a93c3  mov     ebx, eax
0x1800a93c5  test    eax, eax
0x1800a93c7  js      short loc_1800A9437
0x1800a93c9  xor     edx, edx; Val
0x1800a93cb  lea     pstg, [rbp+57h+statstg]; void *
0x1800a93cf  lea     r8d, [pdata+50h]; Size
0x1800a93d3  call    memset_0
0x1800a93d8  mov     pstg, [rbp+57h+plkbyt]
0x1800a93dc  lea     pdata, [rbp+57h+statstg]
0x1800a93e0  xor     r8d, r8d
0x1800a93e3  mov     rax, [pstg]
0x1800a93e6  mov     rax, [rax+48h]
0x1800a93ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a93ef  mov     ebx, eax
0x1800a93f1  test    eax, eax
0x1800a93f3  js      short loc_1800A9437
0x1800a93f5  mov     eax, dword ptr [rbp+57h+statstg.cbSize]
0x1800a93f8  lea     pdata, [rdi+10h]; phglobal
0x1800a93fc  mov     pstg, [rbp+57h+plkbyt]; plkbyt
0x1800a9400  mov     [rdi], eax
0x1800a9402  call    cs:__imp_GetHGlobalFromILockBytes
0x1800a9409  nop     dword ptr [rax+rax+00h]
0x1800a940e  mov     ebx, eax
0x1800a9410  test    eax, eax
0x1800a9412  js      short loc_1800A9437
0x1800a9414  mov     pstg, [rdi+10h]; hMem
0x1800a9418  call    cs:__imp_GlobalLock
0x1800a941f  nop     dword ptr [rax+rax+00h]
0x1800a9424  mov     ecx, ebx
0x1800a9426  mov     ebx, 8007000Eh
0x1800a942b  test    rax, rax
0x1800a942e  mov     [rdi+8], rax
0x1800a9432  cmovz   ecx, ebx
0x1800a9435  mov     ebx, ecx
0x1800a9437  mov     pstg, [rbp+57h+pstm]
0x1800a943b  test    pstg, pstg
0x1800a943e  jz      short loc_1800A944C
0x1800a9440  mov     rax, [pstg]
0x1800a9443  mov     rax, [rax+10h]
0x1800a9447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a944c  mov     pstg, [rbp+57h+plkbyt]
0x1800a9450  test    pstg, pstg
0x1800a9453  jz      short loc_1800A9461
0x1800a9455  mov     rax, [pstg]
0x1800a9458  mov     rax, [rax+10h]
0x1800a945c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9461  mov     pstg, [rbp+57h+pstgNative]
0x1800a9465  test    pstg, pstg
0x1800a9468  jz      short loc_1800A9476
0x1800a946a  mov     rax, [pstg]
0x1800a946d  mov     rax, [rax+10h]
0x1800a9471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9476  mov     eax, ebx
0x1800a9478  mov     pstg, [rbp+57h+var_20]
0x1800a947c  xor     pstg, rsp; StackCookie
0x1800a947f  call    __security_check_cookie
0x1800a9484  mov     rbx, [rsp+0C0h+arg_10]
0x1800a948c  add     rsp, 0B0h
0x1800a9493  pop     rdi
0x1800a9494  pop     rsi
0x1800a9495  pop     rbp
0x1800a9496  retn
```
