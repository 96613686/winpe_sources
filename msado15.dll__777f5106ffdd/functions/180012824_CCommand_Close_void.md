# CCommand::Close(void)

- ea: `0x180012824`
- end: `0x180012ba0`
- name: `?Close@CCommand@@QEAAJXZ`
- size: `892`
- prototype: `__int64 __fastcall(CCommand *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180001c98`
- `0x180011a60`
- `0x180011e40`

## callees

- `0x18000f7c0`
- `0x1800119e0`
- `0x180012824`
- `0x180012bb0`
- `0x180020fc0`
- `0x18006a22c`
- `0x18007dd20`
- `0x1800c8f34`
- `0x1800cdade`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x1800129ac`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x1800129ac`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180012a3c`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180012a3c`
- `KERNEL32!TlsSetValue` at `0x1800128a3`
- `KERNEL32!TlsSetValue` at `0x18001293e`
- `KERNEL32!TlsSetValue` at `0x1800128a3`
- `KERNEL32!TlsSetValue` at `0x18001293e`
- `KERNEL32!TlsGetValue` at `0x180012860`
- `KERNEL32!TlsGetValue` at `0x180012860`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180012a90`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180012a90`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCommand::Close(CCommand *this)
{
  char *v2; // r15
  unsigned __int64 v3; // rsi
  _DWORD *Value; // rax
  int AvailableOutputParams; // r14d
  signed __int64 v6; // rax
  CParamBuffer *v7; // rcx
  unsigned int v8; // ebx
  _DWORD *v10; // rax
  IErrorInfo *v11; // rdx
  char *v13; // r14
  __int64 v14; // rbx
  unsigned int v15; // r8d
  unsigned int i; // r8d
  __int64 v17; // rdx
  CCollectionMapEntry *v18; // rcx
  int v19; // ebx
  unsigned int v20; // edx
  __int64 v21; // rcx
  unsigned int BidObjectID; // eax
  _DWORD *TlsValue; // [rsp+30h] [rbp-38h] BYREF
  int v24; // [rsp+38h] [rbp-30h]
  __int64 v25; // [rsp+40h] [rbp-28h]
  int v26; // [rsp+48h] [rbp-20h]
  __int16 v27; // [rsp+4Ch] [rbp-1Ch]
  char v28; // [rsp+4Eh] [rbp-1Ah]
  unsigned __int64 v29; // [rsp+50h] [rbp-18h]
  int v30; // [rsp+58h] [rbp-10h]
  int v31; // [rsp+5Ch] [rbp-Ch]

  v2 = (char *)this + 32;
  v3 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  v29 = v3;
  v31 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v30 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v24 = 1;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  AvailableOutputParams = CParameters::GetAvailableOutputParams((CCommand *)((char *)this + 368));
  if ( AvailableOutputParams < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 480)) == -1 )
      {
        bidTraceW(
          off_18012A1D0[0],
          2893833,
          L"<CParameters::EmptyParameters|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)AvailableOutputParams,
          2826);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 480));
        bidTraceW(
          off_18012A1D0[0],
          2893833,
          L"<CParameters::EmptyParameters|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          BidObjectID,
          AvailableOutputParams,
          2826);
      }
    }
  }
  else if ( !*((_BYTE *)this + 496) )
  {
    CStdCollection::DestroyList((CCommand *)((char *)this + 392), 0);
    *((_DWORD *)this + 119) = 1;
  }
  v6 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 15, 0, *((_QWORD *)this + 15));
  if ( v6 )
  {
    (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v6 + 88LL))(v6);
    v13 = (char *)*((_QWORD *)v2 + 4);
    if ( v2 != v13 )
    {
      if ( v13 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13 + 8LL))(*((_QWORD *)v2 + 4));
        CReaderWriterLock3AR::WriteLock((CReaderWriterLock3AR *)(v13 + 584));
        (*(void (__fastcall **)(unsigned __int64, _QWORD))(*(_QWORD *)v3 + 152LL))(v3, 0);
        v14 = *((_QWORD *)v13 + 72);
        v15 = *(_DWORD *)(v14 + 16);
        if ( v15 )
        {
          v20 = 0;
          v21 = *(_QWORD *)(v14 + 8);
          while ( *(_QWORD *)(v21 + 8LL * v20) != v3 )
          {
            if ( ++v20 >= v15 )
              goto LABEL_19;
          }
          if ( v20 != v15 - 1 )
            memmove_0((void *)(v21 + 8LL * v20), (const void *)(v21 + 8LL * v20 + 8), 8LL * (~v20 + v15));
          --*(_DWORD *)(v14 + 16);
        }
LABEL_19:
        for ( i = 0; i < *(_DWORD *)(v14 + 24); ++i )
        {
          v17 = *(_QWORD *)(v14 + 32) + 8LL * i;
          v18 = *(CCollectionMapEntry **)v17;
          if ( *(_QWORD *)v17 )
          {
            while ( v18 )
            {
              if ( *((_QWORD *)v18 + 3) == v3 )
              {
                *(_QWORD *)v17 = *(_QWORD *)(*(_QWORD *)v17 + 40LL);
                CCollectionMapEntry::`scalar deleting destructor'(v18, v17);
                --*(_DWORD *)(v14 + 40);
                goto LABEL_26;
              }
              v17 = (__int64)v18 + 40;
              v18 = (CCollectionMapEntry *)*((_QWORD *)v18 + 5);
            }
          }
        }
LABEL_26:
        v19 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int64))(*((_QWORD *)v13 + 64) + 352LL))(
                (_QWORD *)v13 + 64,
                v3);
        CReaderWriterLock3AR::WriteUnlock((CReaderWriterLock3AR *)(v13 + 584));
        v30 = v19;
        if ( v19 < 0 )
          CContext::PushError((CContext *)&TlsValue);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
  }
  v7 = (CParamBuffer *)*((_QWORD *)this + 67);
  if ( v7 )
  {
    CParamBuffer::Release(v7);
    *((_QWORD *)this + 67) = 0;
  }
  *((_BYTE *)this + 528) = 1;
  v8 = v30;
  if ( TlsValue[2]-- == 1 )
  {
    v10 = TlsValue;
    v11 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v11 )
    {
      SetErrorInfo(0, v11);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v10 = TlsValue;
    }
    if ( *((_BYTE *)v10 + 30) )
    {
      *((_QWORD *)v10 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180012824  push    rbp
0x180012826  push    rbx
0x180012827  push    rsi
0x180012828  push    rdi
0x180012829  push    r12
0x18001282b  push    r13
0x18001282d  push    r14
0x18001282f  push    r15
0x180012831  mov     rbp, rsp
0x180012834  sub     rsp, 68h
0x180012838  mov     rdi, rcx
0x18001283b  lea     r15, [rcx+20h]
0x18001283f  mov     rax, rcx
0x180012842  neg     rax
0x180012845  sbb     rsi, rsi
0x180012848  and     rsi, r15
0x18001284b  mov     [rbp+var_18], rsi
0x18001284f  xor     r13d, r13d
0x180012852  mov     [rbp+var_C], r13d
0x180012856  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001285d  mov     ecx, [rcx+14h]; dwTlsIndex
0x180012860  call    cs:__imp_TlsGetValue
0x180012867  nop     dword ptr [rax+rax+00h]
0x18001286c  mov     [rbp+TlsValue], rax
0x180012870  mov     [rbp+var_10], r13d
0x180012874  test    rax, rax
0x180012877  jnz     loc_18001295F
0x18001287d  mov     [rbp+var_30], 1
0x180012884  mov     [rbp+var_28], r13
0x180012888  mov     [rbp+var_20], r13d
0x18001288c  mov     [rbp+var_1C], r13w
0x180012891  mov     [rbp+var_1A], r13b
0x180012895  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x180012899  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x1800128a0  mov     ecx, [rcx+14h]; dwTlsIndex
0x1800128a3  call    cs:__imp_TlsSetValue
0x1800128aa  nop     dword ptr [rax+rax+00h]
0x1800128af  lea     rax, [rbp+TlsValue]
0x1800128b3  mov     [rbp+TlsValue], rax
0x1800128b7  lea     rbx, [rdi+170h]
0x1800128be  mov     rcx, rbx; this
0x1800128c1  call    ?GetAvailableOutputParams@CParameters@@QEAAJXZ; CParameters::GetAvailableOutputParams(void)
0x1800128c6  mov     r14d, eax
0x1800128c9  test    eax, eax
0x1800128cb  js      loc_180012AB9
0x1800128d1  cmp     [rbx+80h], r13b
0x1800128d8  jz      loc_180012B32
0x1800128de  mov     rcx, r13
0x1800128e1  mov     rax, [rdi+78h]
0x1800128e5  lock cmpxchg [rdi+78h], rcx
0x1800128eb  mov     rdx, rax
0x1800128ee  test    rax, rax
0x1800128f1  jnz     short loc_180012967
0x1800128f3  mov     rcx, [rdi+218h]; this
0x1800128fa  test    rcx, rcx
0x1800128fd  jnz     loc_180012B7D
0x180012903  mov     byte ptr [rdi+210h], 1
0x18001290a  mov     ebx, [rbp+var_10]
0x18001290d  mov     rax, [rbp+TlsValue]
0x180012911  add     dword ptr [rax+8], 0FFFFFFFFh
0x180012915  jnz     short loc_18001294B
0x180012917  mov     rax, [rbp+TlsValue]
0x18001291b  mov     rdx, [rax+10h]; perrinfo
0x18001291f  test    rdx, rdx
0x180012922  jnz     loc_180012A8E
0x180012928  cmp     [rax+1Eh], r13b
0x18001292c  jnz     loc_180012B8E
0x180012932  xor     edx, edx; lpTlsValue
0x180012934  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001293b  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001293e  call    cs:__imp_TlsSetValue
0x180012945  nop     dword ptr [rax+rax+00h]
0x18001294a  nop
0x18001294b  mov     eax, ebx
0x18001294d  add     rsp, 68h
0x180012951  pop     r15
0x180012953  pop     r14
0x180012955  pop     r13
0x180012957  pop     r12
0x180012959  pop     rdi
0x18001295a  pop     rsi
0x18001295b  pop     rbx
0x18001295c  pop     rbp
0x18001295d  retn
0x18001295f  inc     dword ptr [rax+8]
0x180012962  jmp     loc_1800128B7
0x180012967  mov     rcx, [rax]
0x18001296a  mov     rax, [rcx+58h]
0x18001296e  mov     rcx, rdx
0x180012971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012976  mov     r14, [r15+20h]
0x18001297a  cmp     r15, r14
0x18001297d  jz      loc_1800128F3
0x180012983  test    r14, r14
0x180012986  jz      loc_1800128F3
0x18001298c  mov     rax, [r14]
0x18001298f  mov     rcx, r14
0x180012992  mov     rax, [rax+8]
0x180012996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001299b  lea     r15, [r14+200h]
0x1800129a2  lea     r12, [r14+248h]
0x1800129a9  mov     rcx, r12
0x1800129ac  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x1800129b3  nop     dword ptr [rax+rax+00h]
0x1800129b8  mov     rax, [rsi]
0x1800129bb  xor     edx, edx
0x1800129bd  mov     rcx, rsi
0x1800129c0  mov     rax, [rax+98h]
0x1800129c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129cc  mov     rbx, [r14+240h]
0x1800129d3  mov     r8d, [rbx+10h]
0x1800129d7  test    r8d, r8d
0x1800129da  jnz     loc_180012A6E
0x1800129e0  mov     r8d, r13d
0x1800129e3  cmp     r8d, [rbx+18h]
0x1800129e7  jnb     short loc_180012A22
0x1800129e9  mov     ecx, r8d
0x1800129ec  mov     rax, [rbx+20h]
0x1800129f0  lea     rdx, [rax+rcx*8]; unsigned int
0x1800129f4  mov     rcx, [rdx]; this
0x1800129f7  test    rcx, rcx
0x1800129fa  jnz     short loc_180012A01
0x1800129fc  inc     r8d
0x1800129ff  jmp     short loc_1800129E3
0x180012a01  test    rcx, rcx
0x180012a04  jz      short loc_1800129FC
0x180012a06  cmp     [rcx+18h], rsi
0x180012a0a  jnz     loc_180012B71
0x180012a10  mov     rax, [rdx]
0x180012a13  mov     r8, [rax+28h]
0x180012a17  mov     [rdx], r8
0x180012a1a  call    ??_GCCollectionMapEntry@@QEAAPEAXI@Z; CCollectionMapEntry::`scalar deleting destructor'(uint)
0x180012a1f  dec     dword ptr [rbx+28h]
0x180012a22  mov     rax, [r15]
0x180012a25  mov     rdx, rsi
0x180012a28  mov     rcx, r15
0x180012a2b  mov     rax, [rax+160h]
0x180012a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a37  mov     ebx, eax
0x180012a39  mov     rcx, r12
0x180012a3c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x180012a43  nop     dword ptr [rax+rax+00h]
0x180012a48  mov     [rbp+var_10], ebx
0x180012a4b  test    ebx, ebx
0x180012a4d  js      short loc_180012A63
0x180012a4f  mov     rax, [r14]
0x180012a52  mov     rcx, r14
0x180012a55  mov     rax, [rax+10h]
0x180012a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a5e  jmp     loc_1800128F3
0x180012a63  lea     rcx, [rbp+TlsValue]; this
0x180012a67  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180012a6c  jmp     short loc_180012A4F
0x180012a6e  mov     edx, r13d
0x180012a71  mov     rcx, [rbx+8]
0x180012a75  mov     eax, edx
0x180012a77  cmp     [rcx+rax*8], rsi
0x180012a7b  jz      loc_180012B49
0x180012a81  inc     edx
0x180012a83  cmp     edx, r8d
0x180012a86  jnb     loc_1800129E0
0x180012a8c  jmp     short loc_180012A75
0x180012a8e  xor     ecx, ecx; dwReserved
0x180012a90  call    cs:__imp_SetErrorInfo
0x180012a97  nop     dword ptr [rax+rax+00h]
0x180012a9c  mov     rax, [rbp+TlsValue]
0x180012aa0  mov     rcx, [rax+10h]
0x180012aa4  mov     rax, [rcx]
0x180012aa7  mov     rax, [rax+10h]
0x180012aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ab0  mov     rax, [rbp+TlsValue]
0x180012ab4  jmp     loc_180012928
0x180012ab9  test    byte ptr cs:_bidGblFlags, 2
0x180012ac0  jz      loc_1800128DE
0x180012ac6  lea     rcx, [rbx+70h]; this
0x180012aca  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012acf  cmp     eax, 0FFFFFFFFh
0x180012ad2  jz      short loc_180012B0A
0x180012ad4  lea     rcx, [rbx+70h]; this
0x180012ad8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012add  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012ae4  mov     [rsp+68h+var_40], 0B0Ah
0x180012aec  mov     [rsp+68h+var_48], r14d
0x180012af1  mov     r9d, eax
0x180012af4  lea     r8, aCparametersEmp; "<CParameters::EmptyParameters|ADO|ERR> "...
0x180012afb  mov     edx, 2C2809h
0x180012b00  call    _bidTraceW
0x180012b05  jmp     loc_1800128DE
0x180012b0a  mov     [rsp+68h+var_48], 0B0Ah
0x180012b12  mov     r9d, r14d
0x180012b15  lea     r8, aCparametersEmp_0; "<CParameters::EmptyParameters|ADO|ERR> "...
0x180012b1c  mov     edx, 2C2809h
0x180012b21  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012b28  call    _bidTraceW
0x180012b2d  jmp     loc_1800128DE
0x180012b32  lea     rcx, [rbx+18h]; this
0x180012b36  xor     edx, edx; struct CCollectionList *
0x180012b38  call    ?DestroyList@CStdCollection@@QEAAXPEAVCCollectionList@@@Z; CStdCollection::DestroyList(CCollectionList *)
0x180012b3d  mov     dword ptr [rbx+6Ch], 1
0x180012b44  jmp     loc_1800128DE
0x180012b49  lea     eax, [r8-1]
0x180012b4d  cmp     edx, eax
0x180012b4f  jz      short loc_180012B69
0x180012b51  mov     eax, edx
0x180012b53  lea     rcx, [rcx+rax*8]; void *
0x180012b57  not     edx
0x180012b59  add     r8d, edx
0x180012b5c  shl     r8, 3; Size
0x180012b60  lea     rdx, [rcx+8]; Src
0x180012b64  call    memmove_0
0x180012b69  dec     dword ptr [rbx+10h]
0x180012b6c  jmp     loc_1800129E0
0x180012b71  lea     rdx, [rcx+28h]
0x180012b75  mov     rcx, [rdx]
0x180012b78  jmp     loc_180012A01
0x180012b7d  call    ?Release@CParamBuffer@@QEAAKXZ; CParamBuffer::Release(void)
0x180012b82  mov     [rdi+218h], r13
0x180012b89  jmp     loc_180012903
0x180012b8e  mov     [rax+10h], r13
0x180012b92  mov     rcx, [rbp+TlsValue]
0x180012b96  mov     [rcx+18h], r13d
0x180012b9a  jmp     loc_18001294B
```
