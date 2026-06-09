# CImpIRowset::AddRefRows(unsigned __int64,unsigned __int64 const * const,ulong * const,ulong * const)

- ea: `0x180017a60`
- end: `0x180017d28`
- name: `?AddRefRows@CImpIRowset@@UEAAJ_KQEB_KQEAK2@Z`
- size: `712`
- prototype: `__int64 __fastcall(CImpIRowset *__hidden this, unsigned __int64, const unsigned __int64 *const, unsigned int *const, unsigned int *const)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800023c0`
- `0x180011788`
- `0x180016584`
- `0x180017a60`
- `0x18001b008`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180017ab4`
- `KERNEL32!GetCurrentThreadId` at `0x180017ab4`
- `KERNEL32!LeaveCriticalSection` at `0x180017b18`
- `KERNEL32!LeaveCriticalSection` at `0x180017c90`
- `KERNEL32!LeaveCriticalSection` at `0x180017d08`
- `KERNEL32!LeaveCriticalSection` at `0x180017b18`
- `KERNEL32!LeaveCriticalSection` at `0x180017c90`
- `KERNEL32!LeaveCriticalSection` at `0x180017d08`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180017adb`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180017adb`
- `MSDART!UMSEnterCSWraper` at `0x180017a96`
- `MSDART!UMSEnterCSWraper` at `0x180017a96`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CImpIRowset::AddRefRows(
        CImpIRowset *this,
        unsigned __int64 a2,
        const unsigned __int64 *const a3,
        unsigned int *const a4,
        unsigned int *const a5)
{
  __int64 v8; // rbx
  DWORD *v9; // rdi
  unsigned int v10; // esi
  bool v11; // zf
  __int64 v12; // rcx
  int v14; // r15d
  __int64 v15; // r14
  __int64 v16; // r13
  int v17; // r10d
  int v18; // r11d
  unsigned int BidObjectID; // eax
  __int64 v20; // r10
  __int64 v21; // r8
  unsigned int v22; // edi
  unsigned int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // rcx
  DWORD *v27; // [rsp+90h] [rbp+8h]

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  v27 = (DWORD *)(v8 + 8);
  if ( *(_DWORD *)(v8 + 12) )
    v27 = (DWORD *)(v8 + 8);
  else
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  SetErrorInfo(0, 0);
  if ( !a2 || a3 )
  {
    v14 = 0;
    v15 = 0;
    if ( !a2 )
      goto LABEL_35;
    do
    {
      v16 = *((_QWORD *)this + 3);
      if ( (unsigned int)CBitArray::IsSlotSet(*(CBitArray **)(v16 + 208), a3[v15]) )
      {
        if ( a5 )
          a5[v15] = 12;
        if ( (bidGblFlags & 2) != 0 && off_180049AE8[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180049260[0], 483328, off_180049AE8[0], BidObjectID, v15);
        }
        v18 = 1;
      }
      else
      {
        v20 = (unsigned int)(*(_DWORD *)(v16 + 220) * v17);
        v21 = *(_QWORD *)(v16 + 224);
        ++*(_DWORD *)(v20 + v21);
        ++*(_DWORD *)(*((_QWORD *)this + 3) + 264LL);
        if ( a4 )
          a4[v15] = *(_DWORD *)(v20 + v21);
        if ( a5 )
          a5[v15] = 0;
        v14 = 1;
      }
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < a2 );
    v9 = v27;
    if ( v18 )
    {
      if ( v14 )
      {
        v22 = 265946;
        if ( (bidGblFlags & 2) != 0 && off_180049AE0[0] )
        {
          v23 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180049258[0], 510976, off_180049AE0[0], v23, 265946);
        }
      }
      else
      {
        if ( (bidGblFlags & 2) != 0 && off_180049AD8[0] )
        {
          v25 = CBidGenericBase::GetBidObjectID((CImpIRowset *)((char *)this + 32));
          bidTraceW(off_180049250[0], 516096, off_180049AD8[0], v25, -2147217887);
        }
        v22 = Exit(-2147217887, 0);
      }
      --*(_DWORD *)(v8 + 16);
      v11 = (*(_DWORD *)(v8 + 12))-- == 1;
      if ( v11 )
        *(_DWORD *)(v8 + 8) = -1;
      v24 = *(_QWORD *)v8;
      --*(_DWORD *)(v24 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 8));
      return v22;
    }
    else
    {
LABEL_35:
      --*(_DWORD *)(v8 + 16);
      v11 = (*(_DWORD *)(v8 + 12))-- == 1;
      if ( v11 )
        *v9 = -1;
      v26 = *(_QWORD *)v8;
      --*(_DWORD *)(v26 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v26 + 8));
      return 0;
    }
  }
  else
  {
    v10 = Exit(-2147024809, 0);
    --*(_DWORD *)(v8 + 16);
    v11 = (*(_DWORD *)(v8 + 12))-- == 1;
    if ( v11 )
      *v9 = -1;
    v12 = *(_QWORD *)v8;
    --*(_DWORD *)(v12 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
    return v10;
  }
}

```

## disassembly

```asm
0x180017a60  mov     [rsp+arg_18], r9
0x180017a65  mov     [rsp+arg_10], r8
0x180017a6a  push    rbx
0x180017a6b  push    rbp
0x180017a6c  push    rsi
0x180017a6d  push    rdi
0x180017a6e  push    r12
0x180017a70  push    r13
0x180017a72  push    r14
0x180017a74  push    r15
0x180017a76  sub     rsp, 48h
0x180017a7a  mov     rsi, r8
0x180017a7d  mov     r12, rdx
0x180017a80  mov     rbp, rcx
0x180017a83  mov     rbx, [rcx+18h]
0x180017a87  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180017a8b  mov     [rsp+88h+arg_8], rbx
0x180017a93  mov     rcx, rbx
0x180017a96  call    cs:__imp_UMSEnterCSWraper
0x180017a9d  nop     dword ptr [rax+rax+00h]
0x180017aa2  lea     rdi, [rbx+8]
0x180017aa6  mov     [rsp+88h+arg_0], rdi
0x180017aae  cmp     dword ptr [rbx+0Ch], 0
0x180017ab2  jnz     short loc_180017AC4
0x180017ab4  call    cs:__imp_GetCurrentThreadId
0x180017abb  nop     dword ptr [rax+rax+00h]
0x180017ac0  mov     [rdi], eax
0x180017ac2  jmp     short loc_180017ACC
0x180017ac4  mov     [rsp+88h+arg_0], rdi
0x180017acc  inc     dword ptr [rbx+0Ch]
0x180017acf  inc     dword ptr [rbx+10h]
0x180017ad2  mov     [rsp+88h+var_58], rbx
0x180017ad7  xor     edx, edx; perrinfo
0x180017ad9  xor     ecx, ecx; dwReserved
0x180017adb  call    cs:__imp_SetErrorInfo
0x180017ae2  nop     dword ptr [rax+rax+00h]
0x180017ae7  test    r12, r12
0x180017aea  jz      short loc_180017B2B
0x180017aec  test    rsi, rsi
0x180017aef  jnz     short loc_180017B2B
0x180017af1  xor     edx, edx; unsigned int
0x180017af3  mov     ecx, 80070057h; int
0x180017af8  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180017afd  mov     esi, eax
0x180017aff  dec     dword ptr [rbx+10h]
0x180017b02  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x180017b06  jnz     short loc_180017B0E
0x180017b08  mov     dword ptr [rdi], 0FFFFFFFFh
0x180017b0e  mov     rcx, [rbx]
0x180017b11  dec     dword ptr [rcx+30h]
0x180017b14  add     rcx, 8; lpCriticalSection
0x180017b18  call    cs:__imp_LeaveCriticalSection
0x180017b1f  nop     dword ptr [rax+rax+00h]
0x180017b24  mov     eax, esi
0x180017b26  jmp     loc_180017D16
0x180017b2b  mov     rsi, [rsp+88h+arg_20]
0x180017b33  xor     r11d, r11d
0x180017b36  xor     r15d, r15d
0x180017b39  xor     r14d, r14d
0x180017b3c  test    r12, r12
0x180017b3f  jz      loc_180017CEF
0x180017b45  mov     rbx, [rsp+88h+arg_10]
0x180017b4d  mov     rdi, [rsp+88h+arg_18]
0x180017b55  mov     r13, [rbp+18h]
0x180017b59  mov     r10d, [rbx+r14*8]
0x180017b5d  mov     edx, r10d; unsigned int
0x180017b60  mov     rcx, [r13+0D0h]; this
0x180017b67  call    ?IsSlotSet@CBitArray@@QEAAJK@Z; CBitArray::IsSlotSet(ulong)
0x180017b6c  test    eax, eax
0x180017b6e  jz      short loc_180017BC3
0x180017b70  test    rsi, rsi
0x180017b73  jz      short loc_180017B7D
0x180017b75  mov     dword ptr [rsi+r14*4], 0Ch
0x180017b7d  test    byte ptr cs:_bidGblFlags, 2
0x180017b84  jz      short loc_180017BBB
0x180017b86  mov     rax, cs:off_180049AE8; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x180017b8d  test    rax, rax
0x180017b90  jz      short loc_180017BBB
0x180017b92  lea     rcx, [rbp+20h]; this
0x180017b96  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017b9b  mov     r8, cs:off_180049AE8; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x180017ba2  mov     rcx, cs:off_180049260; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017ba9  mov     [rsp+88h+var_68], r14d
0x180017bae  mov     r9d, eax
0x180017bb1  mov     edx, 76000h
0x180017bb6  call    _bidTraceW
0x180017bbb  mov     r11d, 1
0x180017bc1  jmp     short loc_180017C06
0x180017bc3  imul    r10d, [r13+0DCh]
0x180017bcb  mov     r8, [r13+0E0h]
0x180017bd2  inc     dword ptr [r10+r8]
0x180017bd6  mov     rax, [rbp+18h]
0x180017bda  inc     dword ptr [rax+108h]
0x180017be0  lea     rcx, ds:0[r14*4]
0x180017be8  test    rdi, rdi
0x180017beb  jz      short loc_180017BF4
0x180017bed  mov     eax, [r10+r8]
0x180017bf1  mov     [rdi+rcx], eax
0x180017bf4  test    rsi, rsi
0x180017bf7  jz      short loc_180017C00
0x180017bf9  mov     dword ptr [rsi+rcx], 0
0x180017c00  mov     r15d, 1
0x180017c06  inc     r14d
0x180017c09  mov     eax, r14d
0x180017c0c  cmp     rax, r12
0x180017c0f  jb      loc_180017B55
0x180017c15  test    r11d, r11d
0x180017c18  mov     rbx, [rsp+88h+arg_8]
0x180017c20  mov     rdi, [rsp+88h+arg_0]
0x180017c28  jz      loc_180017CEF
0x180017c2e  test    r15d, r15d
0x180017c31  jz      short loc_180017CA0
0x180017c33  mov     edi, 40EDAh
0x180017c38  test    byte ptr cs:_bidGblFlags, 2
0x180017c3f  jz      short loc_180017C76
0x180017c41  mov     rax, cs:off_180049AE0; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x180017c48  test    rax, rax
0x180017c4b  jz      short loc_180017C76
0x180017c4d  lea     rcx, [rbp+20h]; this
0x180017c51  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017c56  mov     r8, cs:off_180049AE0; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x180017c5d  mov     rcx, cs:off_180049258; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017c64  mov     [rsp+88h+var_68], edi
0x180017c68  mov     r9d, eax
0x180017c6b  mov     edx, 7CC00h
0x180017c70  call    _bidTraceW
0x180017c75  nop
0x180017c76  dec     dword ptr [rbx+10h]
0x180017c79  sub     dword ptr [rbx+0Ch], 1
0x180017c7d  jnz     short loc_180017C86
0x180017c7f  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x180017c86  mov     rcx, [rbx]
0x180017c89  dec     dword ptr [rcx+30h]
0x180017c8c  add     rcx, 8; lpCriticalSection
0x180017c90  call    cs:__imp_LeaveCriticalSection
0x180017c97  nop     dword ptr [rax+rax+00h]
0x180017c9c  mov     eax, edi
0x180017c9e  jmp     short loc_180017D16
0x180017ca0  mov     edi, 80040E21h
0x180017ca5  test    byte ptr cs:_bidGblFlags, 2
0x180017cac  jz      short loc_180017CE2
0x180017cae  mov     rax, cs:off_180049AD8; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x180017cb5  test    rax, rax
0x180017cb8  jz      short loc_180017CE2
0x180017cba  lea     rcx, [rbp+20h]; this
0x180017cbe  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180017cc3  mov     r8, cs:off_180049AD8; "<CImpIRowset::AddRefRows|ERR|PERSIST> %"...
0x180017cca  mov     rcx, cs:off_180049250; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180017cd1  mov     [rsp+88h+var_68], edi
0x180017cd5  mov     r9d, eax
0x180017cd8  mov     edx, 7E000h
0x180017cdd  call    _bidTraceW
0x180017ce2  xor     edx, edx; unsigned int
0x180017ce4  mov     ecx, edi; int
0x180017ce6  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180017ceb  mov     edi, eax
0x180017ced  jmp     short loc_180017C76
0x180017cef  dec     dword ptr [rbx+10h]
0x180017cf2  sub     dword ptr [rbx+0Ch], 1
0x180017cf6  jnz     short loc_180017CFE
0x180017cf8  mov     dword ptr [rdi], 0FFFFFFFFh
0x180017cfe  mov     rcx, [rbx]
0x180017d01  dec     dword ptr [rcx+30h]
0x180017d04  add     rcx, 8; lpCriticalSection
0x180017d08  call    cs:__imp_LeaveCriticalSection
0x180017d0f  nop     dword ptr [rax+rax+00h]
0x180017d14  xor     eax, eax
0x180017d16  add     rsp, 48h
0x180017d1a  pop     r15
0x180017d1c  pop     r14
0x180017d1e  pop     r13
0x180017d20  pop     r12
0x180017d22  pop     rdi
0x180017d23  pop     rsi
0x180017d24  pop     rbp
0x180017d25  pop     rbx
0x180017d26  retn
```
