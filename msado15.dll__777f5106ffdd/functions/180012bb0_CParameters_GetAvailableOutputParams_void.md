# CParameters::GetAvailableOutputParams(void)

- ea: `0x180012bb0`
- end: `0x180012f65`
- name: `?GetAvailableOutputParams@CParameters@@QEAAJXZ`
- size: `949`
- prototype: `__int64 __fastcall(CParameters *__hidden this)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x180011d7c`
- `0x180012824`
- `0x18003fbd0`
- `0x18005cee0`
- `0x180079720`
- `0x18007fb40`

## callees

- `0x180011334`
- `0x180012bb0`
- `0x180047a50`
- `0x18006a22c`
- `0x18007e404`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x180012c78`
- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x180012c78`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x180012cad`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x180012cad`

## pseudocode

```c
__int64 __fastcall CParameters::GetAvailableOutputParams(CParameters *this)
{
  CParameters *v1; // rdx
  char *v2; // r8
  CParameter *v3; // r14
  unsigned int v5; // ebx
  char *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rdi
  __int64 v9; // r12
  unsigned int v10; // r13d
  unsigned int i; // ebp
  unsigned int v12; // r15d
  bool v13; // al
  CCollectionList *v14; // rcx
  bool v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int BidObjectID; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  __int64 v23; // [rsp+20h] [rbp-48h]
  __int64 v24; // [rsp+28h] [rbp-40h]
  int v25; // [rsp+70h] [rbp+8h] BYREF
  void *v26; // [rsp+78h] [rbp+10h] BYREF

  v1 = (CParameters *)*((_QWORD *)this + 7);
  v2 = (char *)this + 24;
  v3 = 0;
  v5 = 0;
  if ( (CParameters *)((char *)this + 24) != v1 )
  {
    v25 = 0;
    v6 = (char *)v1 - 32;
    if ( !v1 )
      v6 = 0;
    if ( v6 )
    {
      v7 = *((_QWORD *)v6 + 15);
      if ( v7 )
      {
        v8 = *(_QWORD *)(v7 + 152);
        if ( v8 )
        {
          if ( *(_QWORD *)(v8 + 8) && (*(_BYTE *)(v8 + 16) || *(_QWORD *)(v8 + 24)) )
          {
            v9 = 0;
            v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 248LL))(v2);
            for ( i = 0; ; ++i )
            {
              if ( i >= v10 )
              {
                CExecInfo::Init((CExecInfo *)v8);
                return v5;
              }
              v26 = 0;
              v12 = 1;
              v13 = CReaderWriterLock3AR::ReadOrWriteLock((CParameters *)((char *)this + 96));
              v14 = (CCollectionList *)*((_QWORD *)this + 11);
              v15 = v13;
              if ( v14 )
              {
                v16 = CCollectionList::LookUpByIndex(v14, i, &v26);
                v3 = (CParameter *)v26;
                v12 = v16;
              }
              CReaderWriterLock3AR::ReadOrWriteUnlock((CParameters *)((char *)this + 96), v15);
              if ( v12 )
                break;
              if ( v3 )
                v3 = (CParameter *)((char *)v3 - 24);
              v5 = (*(__int64 (__fastcall **)(CParameter *, int *))(*(_QWORD *)v3 + 120LL))(v3, &v25);
              if ( (v5 & 0x80000000) != 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) == -1 )
                  {
                    bidTraceW(
                      off_18012A1D0[0],
                      2934793,
                      L"<CParameters::GetAvailableOutputParams|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                      v5,
                      2866);
                  }
                  else
                  {
                    BidObjectID = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
                    bidTraceW(
                      off_18012A1D0[0],
                      2934793,
                      L"<CParameters::GetAvailableOutputParams|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                      BidObjectID,
                      v5,
                      2866);
                  }
                }
                return v5;
              }
              if ( (v25 & 2) != 0 || v25 == 4 )
              {
                v5 = CParameter::SetValue(v3, (struct FIELDBUFFER *)(v9 + *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL)));
                if ( (v5 & 0x80000000) != 0 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) == -1 )
                    {
                      bidTraceW(
                        off_18012A1D0[0],
                        2940937,
                        L"<CParameters::GetAvailableOutputParams|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                        v5,
                        2872);
                    }
                    else
                    {
                      v17 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
                      bidTraceW(
                        off_18012A1D0[0],
                        2940937,
                        L"<CParameters::GetAvailableOutputParams|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                        v17,
                        v5,
                        2872);
                    }
                  }
                  return v5;
                }
              }
              v9 += *((_QWORD *)v3 + 27) + 16LL;
              v3 = 0;
            }
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) == -1 )
              {
                bidTraceW(
                  off_18012A1D0[0],
                  3698697,
                  L"<CParameters::GetParameter|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                  v12,
                  3612);
              }
              else
              {
                v19 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
                bidTraceW(
                  off_18012A1D0[0],
                  3698697,
                  L"<CParameters::GetParameter|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                  v19,
                  v12,
                  3612);
              }
            }
            v5 = -2147024809;
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_18012A448[0] )
              {
                v20 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
                LODWORD(v23) = -2147024809;
                bidTraceW(off_18012A1D0[0], 3707904, off_18012A448[0], v20, v23);
              }
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) == -1 )
                {
                  LODWORD(v23) = 2864;
                  bidTraceW(
                    off_18012A1D0[0],
                    2932745,
                    L"<CParameters::GetAvailableOutputParams|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                    2147942487LL,
                    v23);
                }
                else
                {
                  v21 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
                  LODWORD(v24) = 2864;
                  LODWORD(v23) = -2147024809;
                  bidTraceW(
                    off_18012A1D0[0],
                    2932745,
                    L"<CParameters::GetAvailableOutputParams|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                    v21,
                    v23,
                    v24);
                }
              }
            }
          }
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180012bb0  push    rbx
0x180012bb2  push    rsi
0x180012bb3  push    r14
0x180012bb5  sub     rsp, 50h
0x180012bb9  mov     rdx, [rcx+38h]
0x180012bbd  lea     r8, [rcx+18h]
0x180012bc1  xor     r14d, r14d
0x180012bc4  mov     rsi, rcx
0x180012bc7  mov     ebx, r14d
0x180012bca  cmp     r8, rdx
0x180012bcd  jz      loc_180012F59
0x180012bd3  test    rdx, rdx
0x180012bd6  mov     [rsp+68h+arg_0], r14d
0x180012bdb  lea     rcx, [rdx-20h]
0x180012bdf  cmovz   rcx, r14
0x180012be3  test    rcx, rcx
0x180012be6  jz      loc_180012F59
0x180012bec  mov     [rsp+68h+var_20], rdi
0x180012bf1  mov     rdi, [rcx+78h]
0x180012bf5  test    rdi, rdi
0x180012bf8  jz      loc_180012F54
0x180012bfe  mov     rdi, [rdi+98h]
0x180012c05  test    rdi, rdi
0x180012c08  jz      loc_180012F54
0x180012c0e  cmp     [rdi+8], rbx
0x180012c12  jz      loc_180012F54
0x180012c18  cmp     [rdi+10h], bl
0x180012c1b  jnz     short loc_180012C27
0x180012c1d  cmp     [rdi+18h], rbx
0x180012c21  jz      loc_180012F54
0x180012c27  mov     rax, [r8]
0x180012c2a  mov     rcx, r8
0x180012c2d  mov     [rsp+68h+arg_10], rbp
0x180012c35  mov     [rsp+68h+var_28], r12
0x180012c3a  mov     r12, r14
0x180012c3d  mov     [rsp+68h+var_30], r13
0x180012c42  mov     rax, [rax+0F8h]
0x180012c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c4e  mov     r13d, eax
0x180012c51  mov     [rsp+68h+var_38], r15
0x180012c56  mov     ebp, r14d
0x180012c59  nop     dword ptr [rax+00000000h]
0x180012c60  cmp     ebp, r13d
0x180012c63  jnb     loc_180012F35
0x180012c69  lea     rcx, [rsi+60h]
0x180012c6d  mov     [rsp+68h+arg_8], r14
0x180012c72  mov     r15d, 1
0x180012c78  call    cs:__imp_?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ; CReaderWriterLock3AR::ReadOrWriteLock(void)
0x180012c7f  nop     dword ptr [rax+rax+00h]
0x180012c84  mov     rcx, [rsi+58h]; this
0x180012c88  movzx   r9d, al
0x180012c8c  test    rcx, rcx
0x180012c8f  jz      short loc_180012CA5
0x180012c91  mov     edx, ebp; unsigned __int64
0x180012c93  lea     r8, [rsp+68h+arg_8]; void **
0x180012c98  call    ?LookUpByIndex@CCollectionList@@QEAAJ_KPEAPEAX@Z; CCollectionList::LookUpByIndex(unsigned __int64,void * *)
0x180012c9d  mov     r14, [rsp+68h+arg_8]
0x180012ca2  mov     r15d, eax
0x180012ca5  movzx   edx, r9b
0x180012ca9  lea     rcx, [rsi+60h]
0x180012cad  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z; CReaderWriterLock3AR::ReadOrWriteUnlock(bool)
0x180012cb4  nop     dword ptr [rax+rax+00h]
0x180012cb9  test    r15d, r15d
0x180012cbc  jnz     loc_180012E14
0x180012cc2  test    r14, r14
0x180012cc5  jz      short loc_180012CCB
0x180012cc7  add     r14, 0FFFFFFFFFFFFFFE8h
0x180012ccb  mov     rax, [r14]
0x180012cce  lea     rdx, [rsp+68h+arg_0]
0x180012cd3  mov     rcx, r14
0x180012cd6  mov     rax, [rax+78h]
0x180012cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cdf  mov     ebx, eax
0x180012ce1  test    eax, eax
0x180012ce3  js      loc_180012D9C
0x180012ce9  mov     eax, [rsp+68h+arg_0]
0x180012ced  test    al, 2
0x180012cef  jnz     short loc_180012CF6
0x180012cf1  cmp     eax, 4
0x180012cf4  jnz     short loc_180012D0F
0x180012cf6  mov     rax, [rdi+8]
0x180012cfa  mov     rcx, r14; this
0x180012cfd  mov     rdx, [rax+8]
0x180012d01  add     rdx, r12; struct FIELDBUFFER *
0x180012d04  call    ?SetValue@CParameter@@QEAAJAEAVFIELDBUFFER@@@Z; CParameter::SetValue(FIELDBUFFER &)
0x180012d09  mov     ebx, eax
0x180012d0b  test    eax, eax
0x180012d0d  js      short loc_180012D24
0x180012d0f  add     r12, 10h
0x180012d13  inc     ebp
0x180012d15  add     r12, [r14+0D8h]
0x180012d1c  xor     r14d, r14d
0x180012d1f  jmp     loc_180012C60
0x180012d24  test    byte ptr cs:_bidGblFlags, 2
0x180012d2b  jz      loc_180012F3D
0x180012d31  lea     rcx, [rsi+70h]; this
0x180012d35  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012d3a  cmp     eax, 0FFFFFFFFh
0x180012d3d  jz      short loc_180012D74
0x180012d3f  lea     rcx, [rsi+70h]; this
0x180012d43  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012d48  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012d4f  lea     r8, aCparametersGet_13; "<CParameters::GetAvailableOutputParams|"...
0x180012d56  mov     r9d, eax
0x180012d59  mov     dword ptr [rsp+68h+var_40], 0B38h
0x180012d61  mov     edx, 2CE009h
0x180012d66  mov     dword ptr [rsp+68h+var_48], ebx
0x180012d6a  call    _bidTraceW
0x180012d6f  jmp     loc_180012F3D
0x180012d74  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012d7b  lea     r8, aCparametersGet_12; "<CParameters::GetAvailableOutputParams|"...
0x180012d82  mov     r9d, ebx
0x180012d85  mov     dword ptr [rsp+68h+var_48], 0B38h
0x180012d8d  mov     edx, 2CE009h
0x180012d92  call    _bidTraceW
0x180012d97  jmp     loc_180012F3D
0x180012d9c  test    byte ptr cs:_bidGblFlags, 2
0x180012da3  jz      loc_180012F3D
0x180012da9  lea     rcx, [rsi+70h]; this
0x180012dad  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012db2  cmp     eax, 0FFFFFFFFh
0x180012db5  jz      short loc_180012DEC
0x180012db7  lea     rcx, [rsi+70h]; this
0x180012dbb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012dc0  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012dc7  lea     r8, aCparametersGet_13; "<CParameters::GetAvailableOutputParams|"...
0x180012dce  mov     r9d, eax
0x180012dd1  mov     dword ptr [rsp+68h+var_40], 0B32h
0x180012dd9  mov     edx, 2CC809h
0x180012dde  mov     dword ptr [rsp+68h+var_48], ebx
0x180012de2  call    _bidTraceW
0x180012de7  jmp     loc_180012F3D
0x180012dec  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012df3  lea     r8, aCparametersGet_12; "<CParameters::GetAvailableOutputParams|"...
0x180012dfa  mov     r9d, ebx
0x180012dfd  mov     dword ptr [rsp+68h+var_48], 0B32h
0x180012e05  mov     edx, 2CC809h
0x180012e0a  call    _bidTraceW
0x180012e0f  jmp     loc_180012F3D
0x180012e14  test    byte ptr cs:_bidGblFlags, 2
0x180012e1b  jz      short loc_180012E81
0x180012e1d  lea     rcx, [rsi+70h]; this
0x180012e21  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012e26  cmp     eax, 0FFFFFFFFh
0x180012e29  jz      short loc_180012E5E
0x180012e2b  lea     rcx, [rsi+70h]; this
0x180012e2f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012e34  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012e3b  lea     r8, aCparametersGet_2; "<CParameters::GetParameter|ADO|ERR> %u#"...
0x180012e42  mov     r9d, eax
0x180012e45  mov     dword ptr [rsp+68h+var_40], 0E1Ch
0x180012e4d  mov     edx, 387009h
0x180012e52  mov     dword ptr [rsp+68h+var_48], r15d
0x180012e57  call    _bidTraceW
0x180012e5c  jmp     short loc_180012E81
0x180012e5e  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012e65  lea     r8, aCparametersGet_4; "<CParameters::GetParameter|ADO|ERR> 0x%"...
0x180012e6c  mov     r9d, r15d
0x180012e6f  mov     dword ptr [rsp+68h+var_48], 0E1Ch
0x180012e77  mov     edx, 387009h
0x180012e7c  call    _bidTraceW
0x180012e81  test    byte ptr cs:_bidGblFlags, 2
0x180012e88  mov     ebx, 80070057h
0x180012e8d  jz      loc_180012F3D
0x180012e93  mov     rax, cs:off_18012A448; "<CParameters::GetParameter|API|ADO|RET>"...
0x180012e9a  test    rax, rax
0x180012e9d  jz      short loc_180012EC7
0x180012e9f  lea     rcx, [rsi+70h]; this
0x180012ea3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012ea8  mov     r8, cs:off_18012A448; "<CParameters::GetParameter|API|ADO|RET>"...
0x180012eaf  mov     r9d, eax
0x180012eb2  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012eb9  mov     edx, 389400h
0x180012ebe  mov     dword ptr [rsp+68h+var_48], ebx
0x180012ec2  call    _bidTraceW
0x180012ec7  test    byte ptr cs:_bidGblFlags, 2
0x180012ece  jz      short loc_180012F3D
0x180012ed0  lea     rcx, [rsi+70h]; this
0x180012ed4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012ed9  cmp     eax, 0FFFFFFFFh
0x180012edc  jz      short loc_180012F10
0x180012ede  lea     rcx, [rsi+70h]; this
0x180012ee2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012ee7  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012eee  lea     r8, aCparametersGet_13; "<CParameters::GetAvailableOutputParams|"...
0x180012ef5  mov     r9d, eax
0x180012ef8  mov     dword ptr [rsp+68h+var_40], 0B30h
0x180012f00  mov     edx, 2CC009h
0x180012f05  mov     dword ptr [rsp+68h+var_48], ebx
0x180012f09  call    _bidTraceW
0x180012f0e  jmp     short loc_180012F3D
0x180012f10  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012f17  lea     r8, aCparametersGet_12; "<CParameters::GetAvailableOutputParams|"...
0x180012f1e  mov     r9d, ebx
0x180012f21  mov     dword ptr [rsp+68h+var_48], 0B30h
0x180012f29  mov     edx, 2CC009h
0x180012f2e  call    _bidTraceW
0x180012f33  jmp     short loc_180012F3D
0x180012f35  mov     rcx, rdi; this
0x180012f38  call    ?Init@CExecInfo@@QEAAXXZ; CExecInfo::Init(void)
0x180012f3d  mov     r15, [rsp+68h+var_38]
0x180012f42  mov     r12, [rsp+68h+var_28]
0x180012f47  mov     rbp, [rsp+68h+arg_10]
0x180012f4f  mov     r13, [rsp+68h+var_30]
0x180012f54  mov     rdi, [rsp+68h+var_20]
0x180012f59  mov     eax, ebx
0x180012f5b  add     rsp, 50h
0x180012f5f  pop     r14
0x180012f61  pop     rsi
0x180012f62  pop     rbx
0x180012f63  retn
```
