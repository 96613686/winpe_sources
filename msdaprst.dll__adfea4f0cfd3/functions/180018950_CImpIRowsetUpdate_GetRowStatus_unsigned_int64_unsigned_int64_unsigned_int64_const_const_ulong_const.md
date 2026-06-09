# CImpIRowsetUpdate::GetRowStatus(unsigned __int64,unsigned __int64,unsigned __int64 const * const,ulong * const)

- ea: `0x180018950`
- end: `0x180018bbf`
- name: `?GetRowStatus@CImpIRowsetUpdate@@UEAAJ_K0QEB_KQEAK@Z`
- size: `623`
- prototype: `__int64 __fastcall(CImpIRowsetUpdate *__hidden this, unsigned __int64, unsigned __int64, const unsigned __int64 *const, unsigned int *const)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800023c0`
- `0x180011788`
- `0x180016584`
- `0x180018950`
- `0x18001b008`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001899b`
- `KERNEL32!GetCurrentThreadId` at `0x18001899b`
- `KERNEL32!LeaveCriticalSection` at `0x1800189e0`
- `KERNEL32!LeaveCriticalSection` at `0x180018b98`
- `KERNEL32!LeaveCriticalSection` at `0x1800189e0`
- `KERNEL32!LeaveCriticalSection` at `0x180018b98`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800189b8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800189b8`
- `MSDART!UMSEnterCSWraper` at `0x180018985`
- `MSDART!UMSEnterCSWraper` at `0x180018985`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowsetUpdate::GetRowStatus(
        CImpIRowsetUpdate *this,
        __int64 a2,
        unsigned __int64 a3,
        const unsigned __int64 *const a4,
        unsigned int *const a5)
{
  __int64 v8; // rbx
  DWORD *v9; // rdi
  bool v10; // zf
  __int64 v11; // rcx
  unsigned int v13; // esi
  int v14; // r12d
  __int64 v15; // rbp
  int v16; // r9d
  __int64 v17; // r10
  int v18; // r11d
  unsigned int BidObjectID; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  wchar_t *v22; // r8
  char *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // [rsp+80h] [rbp+8h]

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  if ( !*(_DWORD *)(v8 + 12) )
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  SetErrorInfo(0, 0);
  if ( !a3 )
  {
    --*(_DWORD *)(v8 + 16);
    v10 = (*(_DWORD *)(v8 + 12))-- == 1;
    if ( v10 )
      *v9 = -1;
    v11 = *(_QWORD *)v8;
    --*(_DWORD *)(v11 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 8));
    return 0;
  }
  if ( a5 && a4 )
  {
    v13 = 0;
    v14 = 0;
    v26 = 0;
    v15 = 0;
    do
    {
      if ( (unsigned int)CBitArray::IsSlotSet(*(CBitArray **)(*((_QWORD *)this + 3) + 208LL), a4[v15]) )
      {
        v14 = 1;
        if ( (bidGblFlags & 2) != 0 && off_180049B30[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
          bidTraceW(off_1800492A8[0], 166912, off_180049B30[0], BidObjectID, v15);
          v18 = v26;
        }
        v20 = 16;
      }
      else
      {
        v18 = 1;
        v26 = 1;
        v20 = *(_DWORD *)((unsigned int)(*(_DWORD *)(v17 + 220) * v16) + *(_QWORD *)(v17 + 224) + 28LL);
      }
      a5[v15] = v20;
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < a3 );
    if ( !v14 )
      goto LABEL_27;
    if ( v18 )
    {
      v13 = 265946;
      if ( (bidGblFlags & 2) == 0 || !off_180049B28[0] )
        goto LABEL_27;
      v21 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
      v22 = off_180049B28[0];
      v23 = off_1800492A0[0];
      v24 = 209920;
    }
    else
    {
      v13 = -2147217887;
      if ( (bidGblFlags & 2) == 0 || !off_180049B20[0] )
        goto LABEL_27;
      v21 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
      v22 = off_180049B20[0];
      v23 = off_180049298[0];
      v24 = 215040;
    }
    bidTraceW(v23, v24, v22, v21, v13);
  }
  else
  {
    v13 = Exit(-2147024809, 0);
  }
LABEL_27:
  --*(_DWORD *)(v8 + 16);
  v10 = (*(_DWORD *)(v8 + 12))-- == 1;
  if ( v10 )
    *v9 = -1;
  v25 = *(_QWORD *)v8;
  --*(_DWORD *)(v25 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v25 + 8));
  return v13;
}

```

## disassembly

```asm
0x180018950  mov     [rsp+arg_8], rbx
0x180018955  mov     [rsp+arg_18], r9
0x18001895a  push    rbp
0x18001895b  push    rsi
0x18001895c  push    rdi
0x18001895d  push    r12
0x18001895f  push    r13
0x180018961  push    r14
0x180018963  push    r15
0x180018965  sub     rsp, 40h
0x180018969  mov     rsi, r9
0x18001896c  mov     r15, r8
0x18001896f  mov     r14, rcx
0x180018972  mov     rbx, [rcx+18h]
0x180018976  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18001897a  mov     [rsp+78h+arg_10], rbx
0x180018982  mov     rcx, rbx
0x180018985  call    cs:__imp_UMSEnterCSWraper
0x18001898c  nop     dword ptr [rax+rax+00h]
0x180018991  lea     rdi, [rbx+8]
0x180018995  cmp     dword ptr [rbx+0Ch], 0
0x180018999  jnz     short loc_1800189A9
0x18001899b  call    cs:__imp_GetCurrentThreadId
0x1800189a2  nop     dword ptr [rax+rax+00h]
0x1800189a7  mov     [rdi], eax
0x1800189a9  inc     dword ptr [rbx+0Ch]
0x1800189ac  inc     dword ptr [rbx+10h]
0x1800189af  mov     [rsp+78h+var_48], rbx
0x1800189b4  xor     edx, edx; perrinfo
0x1800189b6  xor     ecx, ecx; dwReserved
0x1800189b8  call    cs:__imp_SetErrorInfo
0x1800189bf  nop     dword ptr [rax+rax+00h]
0x1800189c4  test    r15, r15
0x1800189c7  jnz     short loc_1800189F3
0x1800189c9  or      edx, 0FFFFFFFFh
0x1800189cc  add     [rbx+10h], edx
0x1800189cf  add     [rbx+0Ch], edx
0x1800189d2  jnz     short loc_1800189D6
0x1800189d4  mov     [rdi], edx
0x1800189d6  mov     rcx, [rbx]
0x1800189d9  dec     dword ptr [rcx+30h]
0x1800189dc  add     rcx, 8; lpCriticalSection
0x1800189e0  call    cs:__imp_LeaveCriticalSection
0x1800189e7  nop     dword ptr [rax+rax+00h]
0x1800189ec  xor     eax, eax
0x1800189ee  jmp     loc_180018BA6
0x1800189f3  mov     r13, [rsp+78h+arg_20]
0x1800189fb  test    r13, r13
0x1800189fe  jz      loc_180018B73
0x180018a04  test    rsi, rsi
0x180018a07  jz      loc_180018B73
0x180018a0d  xor     esi, esi
0x180018a0f  xor     r12d, r12d
0x180018a12  xor     r11d, r11d
0x180018a15  mov     [rsp+78h+arg_0], r11d
0x180018a1d  xor     ebp, ebp
0x180018a1f  test    r15, r15
0x180018a22  jz      loc_180018B81
0x180018a28  mov     rbx, [rsp+78h+arg_18]
0x180018a30  mov     r10, [r14+18h]
0x180018a34  mov     r9d, [rbx+rbp*8]
0x180018a38  mov     edx, r9d; unsigned int
0x180018a3b  mov     rcx, [r10+0D0h]; this
0x180018a42  call    ?IsSlotSet@CBitArray@@QEAAJK@Z; CBitArray::IsSlotSet(ulong)
0x180018a47  test    eax, eax
0x180018a49  jz      short loc_180018AA1
0x180018a4b  mov     r12d, 1
0x180018a51  test    byte ptr cs:_bidGblFlags, 2
0x180018a58  jz      short loc_180018A9A
0x180018a5a  mov     rax, cs:off_180049B30; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x180018a61  test    rax, rax
0x180018a64  jz      short loc_180018A9A
0x180018a66  mov     rcx, [r14+18h]
0x180018a6a  add     rcx, 70h ; 'p'; this
0x180018a6e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180018a73  mov     r8, cs:off_180049B30; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x180018a7a  mov     rcx, cs:off_1800492A8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180018a81  mov     [rsp+78h+var_58], ebp
0x180018a85  mov     r9d, eax
0x180018a88  mov     edx, 28C00h
0x180018a8d  call    _bidTraceW
0x180018a92  mov     r11d, [rsp+78h+arg_0]
0x180018a9a  mov     eax, 10h
0x180018a9f  jmp     short loc_180018AC3
0x180018aa1  mov     r11d, 1
0x180018aa7  mov     [rsp+78h+arg_0], r11d
0x180018aaf  imul    r9d, [r10+0DCh]
0x180018ab7  mov     rax, [r10+0E0h]
0x180018abe  mov     eax, [r9+rax+1Ch]
0x180018ac3  mov     [r13+rbp*4+0], eax
0x180018ac8  inc     ebp
0x180018aca  mov     eax, ebp
0x180018acc  cmp     rax, r15
0x180018acf  jb      loc_180018A30
0x180018ad5  test    r12d, r12d
0x180018ad8  mov     rbx, [rsp+78h+arg_10]
0x180018ae0  jz      loc_180018B81
0x180018ae6  test    r11d, r11d
0x180018ae9  jz      short loc_180018B2B
0x180018aeb  mov     esi, 40EDAh
0x180018af0  test    byte ptr cs:_bidGblFlags, 2
0x180018af7  jz      loc_180018B81
0x180018afd  mov     rax, cs:off_180049B28; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x180018b04  test    rax, rax
0x180018b07  jz      short loc_180018B81
0x180018b09  mov     rcx, [r14+18h]
0x180018b0d  add     rcx, 70h ; 'p'; this
0x180018b11  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180018b16  mov     r8, cs:off_180049B28; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x180018b1d  mov     rcx, cs:off_1800492A0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180018b24  mov     edx, 33400h
0x180018b29  jmp     short loc_180018B65
0x180018b2b  mov     esi, 80040E21h
0x180018b30  test    byte ptr cs:_bidGblFlags, 2
0x180018b37  jz      short loc_180018B81
0x180018b39  mov     rax, cs:off_180049B20; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x180018b40  test    rax, rax
0x180018b43  jz      short loc_180018B81
0x180018b45  mov     rcx, [r14+18h]
0x180018b49  add     rcx, 70h ; 'p'; this
0x180018b4d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180018b52  mov     r8, cs:off_180049B20; "<CImpIRowsetUpdate::GetRowStatus|ERR|PE"...
0x180018b59  mov     rcx, cs:off_180049298; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180018b60  mov     edx, 34800h
0x180018b65  mov     [rsp+78h+var_58], esi
0x180018b69  mov     r9d, eax
0x180018b6c  call    _bidTraceW
0x180018b71  jmp     short loc_180018B81
0x180018b73  xor     edx, edx; unsigned int
0x180018b75  mov     ecx, 80070057h; int
0x180018b7a  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180018b7f  mov     esi, eax
0x180018b81  or      edx, 0FFFFFFFFh
0x180018b84  add     [rbx+10h], edx
0x180018b87  add     [rbx+0Ch], edx
0x180018b8a  jnz     short loc_180018B8E
0x180018b8c  mov     [rdi], edx
0x180018b8e  mov     rcx, [rbx]
0x180018b91  dec     dword ptr [rcx+30h]
0x180018b94  add     rcx, 8; lpCriticalSection
0x180018b98  call    cs:__imp_LeaveCriticalSection
0x180018b9f  nop     dword ptr [rax+rax+00h]
0x180018ba4  mov     eax, esi
0x180018ba6  mov     rbx, [rsp+78h+arg_8]
0x180018bae  add     rsp, 40h
0x180018bb2  pop     r15
0x180018bb4  pop     r14
0x180018bb6  pop     r13
0x180018bb8  pop     r12
0x180018bba  pop     rdi
0x180018bbb  pop     rsi
0x180018bbc  pop     rbp
0x180018bbd  retn
```
