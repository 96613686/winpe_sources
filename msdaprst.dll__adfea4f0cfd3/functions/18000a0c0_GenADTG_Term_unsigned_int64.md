# GenADTG::Term(unsigned __int64)

- ea: `0x18000a0c0`
- end: `0x18000a2fa`
- name: `?Term@GenADTG@@QEAAX_K@Z`
- size: `570`
- prototype: `void __fastcall(GenADTG *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800076c0`
- `0x18000a0c0`

## callees

- `0x180002770`
- `0x1800075fc`
- `0x18000a0c0`
- `0x18001b008`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000a185`
- `ole32!CoTaskMemFree` at `0x18000a195`
- `ole32!CoTaskMemFree` at `0x18000a185`
- `ole32!CoTaskMemFree` at `0x18000a195`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000a0f4`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000a0f4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000a2c2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000a2c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GenADTG::Term(GenADTG *this, __int64 a2)
{
  unsigned int *v4; // r9
  HRESULT ErrorInfo; // r15d
  __int64 v6; // rbx
  int v7; // eax
  int v8; // ebx
  __int64 i; // rbx
  __int64 v10; // rdx
  int v11; // esi
  __int64 v12; // [rsp+70h] [rbp+38h] BYREF
  __int64 v13; // [rsp+78h] [rbp+40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+80h] [rbp+48h] BYREF
  __int64 v15; // [rsp+88h] [rbp+50h] BYREF

  v15 = 0;
  pperrinfo = 0;
  v13 = 0;
  ErrorInfo = GetErrorInfo(0, &pperrinfo);
  v6 = *((_QWORD *)this + 37);
  if ( a2 )
  {
    v12 = 0;
    (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
      *((_QWORD *)this + 3),
      &IID_IChapteredRowset,
      &v12);
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, a2, 0);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v12);
  }
  while ( v6 )
  {
    GenADTG::Term(*(GenADTG **)v6, *(_QWORD *)(v6 + 8));
    v6 = *(_QWORD *)(v6 + 16);
  }
  GenADTG::ReleaseHRows(this, *((_QWORD *)this + 13), *((unsigned __int64 **)this + 14), v4);
  *((_QWORD *)this + 13) = 0;
  CoTaskMemFree(*((LPVOID *)this + 14));
  CoTaskMemFree(*((LPVOID *)this + 15));
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IRowsetNotifyEnable,
         &v13) >= 0 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 24LL))(v13, 1);
  v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IAccessor,
         &v15);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_1800495C0[0] )
        bidTraceW(off_1800491C0[0], 613376, off_1800495C0[0], (unsigned int)v7, 599);
    }
    ThrowHR(v8);
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 20); i = (unsigned int)(i + 1) )
  {
    v10 = *(_QWORD *)(*((_QWORD *)this + 9) + 8 * i);
    if ( v10 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v15 + 48LL))(v15, v10, 0);
      if ( v11 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800495B8[0] )
          bidTraceW(off_1800491C0[0], 622592, off_1800495B8[0], (unsigned int)v11, 608);
        ThrowHR(v11);
      }
      *(_QWORD *)(*((_QWORD *)this + 9) + 8 * i) = 0;
    }
  }
  if ( !ErrorInfo )
    SetErrorInfo(0, pperrinfo);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v13);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v15);
}

```

## disassembly

```asm
0x18000a0c0  push    rbp
0x18000a0c2  push    rbx
0x18000a0c3  push    rsi
0x18000a0c4  push    rdi
0x18000a0c5  push    r14
0x18000a0c7  push    r15
0x18000a0c9  mov     rbp, rsp
0x18000a0cc  sub     rsp, 38h
0x18000a0d0  mov     rsi, rdx
0x18000a0d3  mov     rdi, rcx
0x18000a0d6  mov     [rbp+arg_18], 0
0x18000a0de  mov     [rbp+pperrinfo], 0
0x18000a0e6  mov     [rbp+arg_8], 0
0x18000a0ee  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000a0f2  xor     ecx, ecx; dwReserved
0x18000a0f4  call    cs:__imp_GetErrorInfo
0x18000a0fb  nop     dword ptr [rax+rax+00h]
0x18000a100  mov     r15d, eax
0x18000a103  mov     rbx, [rdi+128h]
0x18000a10a  test    rsi, rsi
0x18000a10d  jz      short loc_18000A168
0x18000a10f  mov     [rbp+arg_0], 0
0x18000a117  mov     rcx, [rdi+18h]
0x18000a11b  mov     rdx, [rcx]
0x18000a11e  mov     rax, [rdx]
0x18000a121  lea     r8, [rbp+arg_0]
0x18000a125  lea     rdx, IID_IChapteredRowset
0x18000a12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a131  mov     rcx, [rbp+arg_0]
0x18000a135  test    rcx, rcx
0x18000a138  jz      short loc_18000A14D
0x18000a13a  mov     rax, [rcx]
0x18000a13d  xor     r8d, r8d
0x18000a140  mov     rdx, rsi
0x18000a143  mov     rax, [rax+20h]
0x18000a147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a14c  nop
0x18000a14d  lea     rcx, [rbp+arg_0]
0x18000a151  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18000a156  jmp     short loc_18000A168
0x18000a158  mov     rdx, [rbx+8]; unsigned __int64
0x18000a15c  mov     rcx, [rbx]; this
0x18000a15f  call    ?Term@GenADTG@@QEAAX_K@Z; GenADTG::Term(unsigned __int64)
0x18000a164  mov     rbx, [rbx+10h]
0x18000a168  test    rbx, rbx
0x18000a16b  jnz     short loc_18000A158
0x18000a16d  mov     r8, [rdi+70h]; unsigned __int64 *
0x18000a171  mov     rdx, [rdi+68h]; unsigned __int64
0x18000a175  mov     rcx, rdi; this
0x18000a178  call    ?ReleaseHRows@GenADTG@@AEAAX_KPEA_KPEAK@Z; GenADTG::ReleaseHRows(unsigned __int64,unsigned __int64 *,ulong *)
0x18000a17d  mov     [rdi+68h], rbx
0x18000a181  mov     rcx, [rdi+70h]; pv
0x18000a185  call    cs:__imp_CoTaskMemFree
0x18000a18c  nop     dword ptr [rax+rax+00h]
0x18000a191  mov     rcx, [rdi+78h]; pv
0x18000a195  call    cs:__imp_CoTaskMemFree
0x18000a19c  nop     dword ptr [rax+rax+00h]
0x18000a1a1  mov     [rdi+70h], rbx
0x18000a1a5  mov     [rdi+78h], rbx
0x18000a1a9  mov     rcx, [rdi+18h]
0x18000a1ad  mov     rax, [rcx]
0x18000a1b0  lea     r8, [rbp+arg_8]
0x18000a1b4  lea     rdx, ?IID_IRowsetNotifyEnable@@3U_GUID@@B; _GUID const IID_IRowsetNotifyEnable
0x18000a1bb  mov     rax, [rax]
0x18000a1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c3  test    eax, eax
0x18000a1c5  js      short loc_18000A1DA
0x18000a1c7  mov     rcx, [rbp+arg_8]
0x18000a1cb  mov     rax, [rcx]
0x18000a1ce  lea     edx, [rbx+1]
0x18000a1d1  mov     rax, [rax+18h]
0x18000a1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1da  mov     rcx, [rdi+18h]
0x18000a1de  mov     rax, [rcx]
0x18000a1e1  lea     r8, [rbp+arg_18]
0x18000a1e5  lea     rdx, IID_IAccessor
0x18000a1ec  mov     rax, [rax]
0x18000a1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1f4  mov     ebx, eax
0x18000a1f6  test    eax, eax
0x18000a1f8  jns     short loc_18000A23A
0x18000a1fa  test    byte ptr cs:_bidGblFlags, 2
0x18000a201  jz      short loc_18000A232
0x18000a203  mov     rcx, cs:off_1800495C0; "<GenADTG::Term|ADO|ERR>  HRESULT: 0x%08"...
0x18000a20a  test    rcx, rcx
0x18000a20d  jz      short loc_18000A232
0x18000a20f  mov     [rsp+38h+var_18], 257h
0x18000a217  mov     r9d, eax
0x18000a21a  mov     r8, cs:off_1800495C0; "<GenADTG::Term|ADO|ERR>  HRESULT: 0x%08"...
0x18000a221  mov     edx, 95C00h
0x18000a226  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000a22d  call    _bidTraceW
0x18000a232  mov     ecx, ebx; int
0x18000a234  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000a23a  xor     ebx, ebx
0x18000a23c  cmp     ebx, [rdi+50h]
0x18000a23f  jnb     short loc_18000A2B7
0x18000a241  mov     rax, [rdi+48h]
0x18000a245  mov     rdx, [rax+rbx*8]
0x18000a249  test    rdx, rdx
0x18000a24c  jz      short loc_18000A273
0x18000a24e  mov     rcx, [rbp+arg_18]
0x18000a252  mov     rax, [rcx]
0x18000a255  xor     r8d, r8d
0x18000a258  mov     rax, [rax+30h]
0x18000a25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a261  mov     esi, eax
0x18000a263  test    eax, eax
0x18000a265  js      short loc_18000A277
0x18000a267  mov     rax, [rdi+48h]
0x18000a26b  mov     qword ptr [rax+rbx*8], 0
0x18000a273  inc     ebx
0x18000a275  jmp     short loc_18000A23C
0x18000a277  test    byte ptr cs:_bidGblFlags, 2
0x18000a27e  jz      short loc_18000A2AF
0x18000a280  mov     rax, cs:off_1800495B8; "<GenADTG::Term|ADO|ERR>  HRESULT: 0x%08"...
0x18000a287  test    rax, rax
0x18000a28a  jz      short loc_18000A2AF
0x18000a28c  mov     [rsp+38h+var_18], 260h
0x18000a294  mov     r9d, esi
0x18000a297  mov     r8, cs:off_1800495B8; "<GenADTG::Term|ADO|ERR>  HRESULT: 0x%08"...
0x18000a29e  mov     edx, 98000h
0x18000a2a3  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000a2aa  call    _bidTraceW
0x18000a2af  mov     ecx, esi; int
0x18000a2b1  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000a2b7  test    r15d, r15d
0x18000a2ba  jnz     short loc_18000A2CF
0x18000a2bc  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000a2c0  xor     ecx, ecx; dwReserved
0x18000a2c2  call    cs:__imp_SetErrorInfo
0x18000a2c9  nop     dword ptr [rax+rax+00h]
0x18000a2ce  nop
0x18000a2cf  lea     rcx, [rbp+arg_8]
0x18000a2d3  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18000a2d8  nop
0x18000a2d9  lea     rcx, [rbp+pperrinfo]
0x18000a2dd  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18000a2e2  nop
0x18000a2e3  lea     rcx, [rbp+arg_18]
0x18000a2e7  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18000a2ec  add     rsp, 38h
0x18000a2f0  pop     r15
0x18000a2f2  pop     r14
0x18000a2f4  pop     rdi
0x18000a2f5  pop     rsi
0x18000a2f6  pop     rbx
0x18000a2f7  pop     rbp
0x18000a2f8  retn
```
