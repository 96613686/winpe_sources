# CPersistSession::OpenStreamFromURL(ushort *,IStream * *)

- ea: `0x180022d50`
- end: `0x180022fad`
- name: `?OpenStreamFromURL@CPersistSession@@AEAAJPEAGPEAPEAUIStream@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(CPersistSession *__hidden this, unsigned __int16 *, struct IStream **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022240`

## callees

- `0x180002770`
- `0x18001b008`
- `0x18002194c`
- `0x180021be8`
- `0x180022d50`
- `0x18002dca4`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPersistSession::OpenStreamFromURL(CPersistSession *this, unsigned __int16 *a2, struct IStream **a3)
{
  unsigned int v5; // esi
  int v6; // ebx
  CPersistSession *v7; // rbx
  CPersistSession *v8; // rcx
  signed int URLMonDLL; // edi
  int v10; // edi
  int v11; // ebx
  int v12; // ebx
  int v14; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+38h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-28h] BYREF
  CPersistSession *v17; // [rsp+70h] [rbp+8h] BYREF
  __int64 v18; // [rsp+88h] [rbp+20h] BYREF

  v17 = this;
  try
  {
    v5 = 0;
    v15 = 0;
    v18 = 0;
    v16 = 0;
    v17 = 0;
    v6 = ATL::CComObject<CBindingCallback>::CreateInstance(&v17);
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049C10[0] )
          bidTraceW(off_1800491F8[0], 303104, off_180049C10[0], (unsigned int)v6, 296);
      }
      ThrowHR(v6);
    }
    v7 = v17;
    (*(void (__fastcall **)(CPersistSession *))(*(_QWORD *)v17 + 8LL))(v17);
    *a3 = 0;
    URLMonDLL = CPersistSession::GetURLMonDLL(v8);
    if ( URLMonDLL < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049C08[0] )
        bidTraceW(off_1800491F8[0], 310272, off_180049C08[0], (unsigned int)URLMonDLL, 303);
      ThrowHR(URLMonDLL);
    }
    v10 = ((__int64 (__fastcall *)(_QWORD, unsigned __int16 *, __int64 *))CPersistSession::m_pCreateURLMoniker)(
            0,
            a2,
            &v15);
    if ( v10 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049C00[0] )
        bidTraceW(off_1800491F8[0], 313344, off_180049C00[0], (unsigned int)v10, 306);
      ThrowHR(v10);
    }
    v11 = ((__int64 (__fastcall *)(_QWORD, CPersistSession *, _QWORD, __int64 *))CPersistSession::m_pCreateAsyncBindCtx)(
            0,
            v7,
            0,
            &v18);
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049BF8[0] )
        bidTraceW(off_1800491F8[0], 316416, off_180049BF8[0], (unsigned int)v11, 309);
      ThrowHR(v11);
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *, struct IStream **))(*(_QWORD *)v15 + 72LL))(
            v15,
            v18,
            0,
            &IID_IStream,
            a3);
    if ( v12 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049BF0[0] )
        bidTraceW(off_1800491F8[0], 319488, off_180049BF0[0], (unsigned int)v12, 312);
      ThrowHR(v12);
    }
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v17);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v16);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v18);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v15);
  }
  catch ( long v14 )
  {
    LODWORD(v17) = v14;
    return (unsigned int)v17;
  }
  catch ( ... )
  {
    LODWORD(v17) = -2147467259;
    return (unsigned int)v17;
  }
  return v5;
}

```

## disassembly

```asm
0x180022d50  mov     rax, rsp
0x180022d53  mov     [rax+10h], rbx
0x180022d57  mov     [rax+18h], rsi
0x180022d5b  mov     [rax+8], rcx
0x180022d5f  push    rdi
0x180022d60  push    r14
0x180022d62  push    r15
0x180022d64  sub     rsp, 50h
0x180022d68  mov     r14, r8
0x180022d6b  mov     r15, rdx
0x180022d6e  xor     esi, esi
0x180022d70  mov     [rax-30h], rsi
0x180022d74  mov     [rax+20h], rsi
0x180022d78  mov     [rax-28h], rsi
0x180022d7c  mov     [rax+8], rsi
0x180022d80  lea     rcx, [rax+8]
0x180022d84  call    ?CreateInstance@?$CComObject@VCBindingCallback@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CBindingCallback>::CreateInstance(ATL::CComObject<CBindingCallback> * *)
0x180022d89  mov     ebx, eax
0x180022d8b  test    eax, eax
0x180022d8d  jns     short loc_180022DCE
0x180022d8f  test    byte ptr cs:_bidGblFlags, 2
0x180022d96  jz      short loc_180022DC7
0x180022d98  mov     rax, cs:off_180049C10; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022d9f  test    rax, rax
0x180022da2  jz      short loc_180022DC7
0x180022da4  mov     dword ptr [rsp+68h+var_48], 128h
0x180022dac  mov     r9d, ebx
0x180022daf  mov     r8, cs:off_180049C10; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022db6  mov     edx, 4A000h
0x180022dbb  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180022dc2  call    _bidTraceW
0x180022dc7  mov     ecx, ebx; int
0x180022dc9  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022dce  mov     rbx, [rsp+68h+arg_0]
0x180022dd3  mov     rax, [rbx]
0x180022dd6  mov     rcx, rbx
0x180022dd9  mov     rax, [rax+8]
0x180022ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022de2  mov     qword ptr [r14], 0
0x180022de9  call    ?GetURLMonDLL@CPersistSession@@AEAAJXZ; CPersistSession::GetURLMonDLL(void)
0x180022dee  mov     edi, eax
0x180022df0  test    eax, eax
0x180022df2  jns     short loc_180022E33
0x180022df4  test    byte ptr cs:_bidGblFlags, 2
0x180022dfb  jz      short loc_180022E2C
0x180022dfd  mov     rax, cs:off_180049C08; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022e04  test    rax, rax
0x180022e07  jz      short loc_180022E2C
0x180022e09  mov     dword ptr [rsp+68h+var_48], 12Fh
0x180022e11  mov     r9d, edi
0x180022e14  mov     r8, cs:off_180049C08; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022e1b  mov     edx, 4BC00h
0x180022e20  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180022e27  call    _bidTraceW
0x180022e2c  mov     ecx, edi; int
0x180022e2e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022e33  lea     r8, [rsp+68h+var_30]
0x180022e38  mov     rdx, r15
0x180022e3b  xor     ecx, ecx
0x180022e3d  mov     rax, cs:?m_pCreateURLMoniker@CPersistSession@@0P6AJPEAUIMoniker@@PEAGPEAPEAU2@@ZEA; long (*CPersistSession::m_pCreateURLMoniker)(IMoniker *,ushort *,IMoniker * *)
0x180022e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e49  mov     edi, eax
0x180022e4b  test    eax, eax
0x180022e4d  jns     short loc_180022E8E
0x180022e4f  test    byte ptr cs:_bidGblFlags, 2
0x180022e56  jz      short loc_180022E87
0x180022e58  mov     rax, cs:off_180049C00; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022e5f  test    rax, rax
0x180022e62  jz      short loc_180022E87
0x180022e64  mov     dword ptr [rsp+68h+var_48], 132h
0x180022e6c  mov     r9d, edi
0x180022e6f  mov     r8, cs:off_180049C00; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022e76  mov     edx, 4C800h
0x180022e7b  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180022e82  call    _bidTraceW
0x180022e87  mov     ecx, edi; int
0x180022e89  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022e8e  lea     r9, [rsp+68h+arg_18]
0x180022e96  xor     r8d, r8d
0x180022e99  mov     rdx, rbx
0x180022e9c  xor     ecx, ecx
0x180022e9e  mov     rax, cs:?m_pCreateAsyncBindCtx@CPersistSession@@0P6AJKPEAUIBindStatusCallback@@PEAUIEnumFORMATETC@@PEAPEAUIBindCtx@@@ZEA; long (*CPersistSession::m_pCreateAsyncBindCtx)(ulong,IBindStatusCallback *,IEnumFORMATETC *,IBindCtx * *)
0x180022ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022eaa  mov     ebx, eax
0x180022eac  test    eax, eax
0x180022eae  jns     short loc_180022EEF
0x180022eb0  test    byte ptr cs:_bidGblFlags, 2
0x180022eb7  jz      short loc_180022EE8
0x180022eb9  mov     rax, cs:off_180049BF8; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022ec0  test    rax, rax
0x180022ec3  jz      short loc_180022EE8
0x180022ec5  mov     dword ptr [rsp+68h+var_48], 135h
0x180022ecd  mov     r9d, ebx
0x180022ed0  mov     r8, cs:off_180049BF8; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022ed7  mov     edx, 4D400h
0x180022edc  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180022ee3  call    _bidTraceW
0x180022ee8  mov     ecx, ebx; int
0x180022eea  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022eef  mov     rcx, [rsp+68h+var_30]
0x180022ef4  mov     rax, [rcx]
0x180022ef7  mov     [rsp+68h+var_48], r14
0x180022efc  lea     r9, IID_IStream
0x180022f03  xor     r8d, r8d
0x180022f06  mov     rdx, [rsp+68h+arg_18]
0x180022f0e  mov     rax, [rax+48h]
0x180022f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f17  mov     ebx, eax
0x180022f19  test    eax, eax
0x180022f1b  jns     short loc_180022F5D
0x180022f1d  test    byte ptr cs:_bidGblFlags, 2
0x180022f24  jz      short loc_180022F55
0x180022f26  mov     rax, cs:off_180049BF0; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022f2d  test    rax, rax
0x180022f30  jz      short loc_180022F55
0x180022f32  mov     dword ptr [rsp+68h+var_48], 138h
0x180022f3a  mov     r9d, ebx
0x180022f3d  mov     r8, cs:off_180049BF0; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022f44  mov     edx, 4E000h
0x180022f49  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180022f50  call    _bidTraceW
0x180022f55  mov     ecx, ebx; int
0x180022f57  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022f5d  lea     rcx, [rsp+68h+arg_0]
0x180022f62  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022f67  nop
0x180022f68  lea     rcx, [rsp+68h+var_28]
0x180022f6d  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022f72  nop
0x180022f73  lea     rcx, [rsp+68h+arg_18]
0x180022f7b  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022f80  nop
0x180022f81  lea     rcx, [rsp+68h+var_30]
0x180022f86  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022f8b  nop
0x180022f8c  jmp     short loc_180022F94
0x180022f8e  jmp     short $+2
0x180022f90  mov     esi, dword ptr [rsp+68h+arg_0]
0x180022f94  mov     eax, esi
0x180022f96  lea     r11, [rsp+68h+var_18]
0x180022f9b  mov     rbx, [r11+28h]
0x180022f9f  mov     rsi, [r11+30h]
0x180022fa3  mov     rsp, r11
0x180022fa6  pop     r15
0x180022fa8  pop     r14
0x180022faa  pop     rdi
0x180022fab  retn
```
