# CRsetField::~CRsetField(void)

- ea: `0x180047afc`
- end: `0x180047d08`
- name: `??1CRsetField@@UEAA@XZ`
- size: `524`
- prototype: `void __fastcall(CRsetField *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180047a7c`
- `0x180093ec8`

## callees

- `0x180047afc`
- `0x1800d0010`

## import_xrefs

- `MSDART!??1CReaderWriterLock3AR@@QEAA@XZ` at `0x180047b51`
- `MSDART!??1CReaderWriterLock3AR@@QEAA@XZ` at `0x180047b51`
- `MSDART!MpHeapFree` at `0x180047bf8`
- `MSDART!MpHeapFree` at `0x180047bf8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRsetField::~CRsetField(CRsetField *this)
{
  char *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  int v5; // edx
  __int64 v6; // rdx
  __int64 v7; // rcx
  char *v8; // rcx

  *((_QWORD *)this + 41) = &CADOStackComObject<CFldProperties>::`vftable'{for `ADOIDispatchImpl<ADOProperties>'};
  *((_QWORD *)this + 42) = &CADOStackComObject<CFldProperties>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_IADOProperties>'};
  v2 = (char *)this + 344;
  *((_QWORD *)this + 43) = &CADOStackComObject<CFldProperties>::`vftable'{for `CStdCollection'};
  *((_DWORD *)this + 88) = 1;
  _InterlockedDecrement(&dword_180122C88);
  CReaderWriterLock3AR::~CReaderWriterLock3AR((CRsetField *)((char *)this + 416));
  *(_QWORD *)v2 = &CStdContainedObject::`vftable';
  if ( _InterlockedExchange((volatile __int32 *)v2 + 14, 0) == 1 )
  {
    *((_DWORD *)v2 + 12) = 1;
    v8 = (char *)*((_QWORD *)v2 + 4);
    if ( v2 == v8 )
      v8 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  *(_QWORD *)v2 = &CStdComObjectRoot::`vftable';
  v3 = *((_QWORD *)v2 + 5);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)v2 + 5) = 0;
  }
  *((_QWORD *)this + 39) = &CRsetField::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 80) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180121278)(
      bidID,
      `CRsetField::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_304[0],
      7,
      *((int *)this + 80),
      0);
  *((_DWORD *)this + 80) = 0;
  v4 = *((_QWORD *)this + 21);
  if ( v4 )
  {
    v5 = *((_DWORD *)this + 44) & 2;
    if ( (*((_DWORD *)this + 44) & 1) != 0 )
    {
      if ( v5
        || (*(int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)g_pStaticGlobals + 10) + 32LL))(
             *((_QWORD *)g_pStaticGlobals + 10),
             *((unsigned int *)this + 42)) >= 0 )
      {
        *((_DWORD *)this + 42) = 0;
      }
    }
    else
    {
      if ( !v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *((_QWORD *)this + 21) = 0;
    }
  }
  if ( (*((_BYTE *)this + 96) & 2) != 0 )
  {
    v6 = *((_QWORD *)this + 11);
    if ( v6 )
      MpHeapFree(g_hHeapHandle, v6);
    *((_QWORD *)this + 11) = 0;
  }
  *((_QWORD *)this + 1) = &CStdComObjectRoot::`vftable';
  v7 = *((_QWORD *)this + 6);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 6) = 0;
  }
}

```

## disassembly

```asm
0x180047afc  mov     [rsp+arg_0], rbx
0x180047b01  mov     [rsp+arg_8], rdi
0x180047b06  push    r14
0x180047b08  sub     rsp, 30h
0x180047b0c  mov     rbx, rcx
0x180047b0f  lea     rax, ??_7?$CADOStackComObject@VCFldProperties@@@@6B?$ADOIDispatchImpl@UADOProperties@@@@@; const CADOStackComObject<CFldProperties>::`vftable'{for `ADOIDispatchImpl<ADOProperties>'}
0x180047b16  mov     [rcx+148h], rax
0x180047b1d  lea     rax, ??_7?$CADOStackComObject@VCFldProperties@@@@6B?$ISupportErrorInfoImpl@$1?IID_IADOProperties@@3U_GUID@@B@ATL@@@; const CADOStackComObject<CFldProperties>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_IADOProperties>'}
0x180047b24  mov     [rcx+150h], rax
0x180047b2b  lea     rdi, [rcx+158h]
0x180047b32  lea     rax, ??_7?$CADOStackComObject@VCFldProperties@@@@6BCStdCollection@@@; const CADOStackComObject<CFldProperties>::`vftable'{for `CStdCollection'}
0x180047b39  mov     [rdi], rax
0x180047b3c  mov     dword ptr [rcx+160h], 1
0x180047b46  lock dec cs:dword_180122C88
0x180047b4d  lea     rcx, [rdi+48h]
0x180047b51  call    cs:__imp_??1CReaderWriterLock3AR@@QEAA@XZ; CReaderWriterLock3AR::~CReaderWriterLock3AR(void)
0x180047b58  nop     dword ptr [rax+rax+00h]
0x180047b5d  nop
0x180047b5e  lea     rax, ??_7CStdContainedObject@@6B@; const CStdContainedObject::`vftable'
0x180047b65  mov     [rdi], rax
0x180047b68  xor     eax, eax
0x180047b6a  xchg    eax, [rdi+38h]
0x180047b6d  cmp     eax, 1
0x180047b70  jz      loc_180047C71
0x180047b76  lea     r14, ??_7CStdComObjectRoot@@6B@; const CStdComObjectRoot::`vftable'
0x180047b7d  mov     [rdi], r14
0x180047b80  mov     rcx, [rdi+28h]
0x180047b84  test    rcx, rcx
0x180047b87  jnz     loc_180047C96
0x180047b8d  lea     rax, ??_7CNotUpdt_BidGeneric@CRsetField@@6B@; const CRsetField::CNotUpdt_BidGeneric::`vftable'
0x180047b94  mov     [rbx+138h], rax
0x180047b9b  movsxd  rcx, dword ptr [rbx+140h]
0x180047ba2  test    ecx, ecx
0x180047ba4  jnz     loc_180047CAF
0x180047baa  mov     dword ptr [rbx+140h], 0
0x180047bb4  mov     rcx, [rbx+0A8h]
0x180047bbb  test    rcx, rcx
0x180047bbe  jz      short loc_180047BE2
0x180047bc0  mov     eax, [rbx+0B0h]
0x180047bc6  mov     edx, eax
0x180047bc8  and     edx, 2
0x180047bcb  test    al, 1
0x180047bcd  jnz     short loc_180047C2F
0x180047bcf  test    edx, edx
0x180047bd1  jz      loc_180047C60
0x180047bd7  mov     qword ptr [rbx+0A8h], 0
0x180047be2  test    byte ptr [rbx+60h], 2
0x180047be6  jz      short loc_180047C0C
0x180047be8  mov     rdx, [rbx+58h]
0x180047bec  test    rdx, rdx
0x180047bef  jz      short loc_180047C04
0x180047bf1  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180047bf8  call    cs:__imp_MpHeapFree
0x180047bff  nop     dword ptr [rax+rax+00h]
0x180047c04  mov     qword ptr [rbx+58h], 0
0x180047c0c  mov     [rbx+8], r14
0x180047c10  mov     rcx, [rbx+30h]
0x180047c14  test    rcx, rcx
0x180047c17  jnz     loc_180047CEE
0x180047c1d  mov     rbx, [rsp+38h+arg_0]
0x180047c22  mov     rdi, [rsp+38h+arg_8]
0x180047c27  add     rsp, 30h
0x180047c2b  pop     r14
0x180047c2d  retn
0x180047c2f  test    edx, edx
0x180047c31  jnz     short loc_180047C54
0x180047c33  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180047c3a  mov     rcx, [rax+50h]
0x180047c3e  mov     rax, [rcx]
0x180047c41  mov     edx, [rbx+0A8h]
0x180047c47  mov     rax, [rax+20h]
0x180047c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c50  test    eax, eax
0x180047c52  js      short loc_180047BE2
0x180047c54  mov     dword ptr [rbx+0A8h], 0
0x180047c5e  jmp     short loc_180047BE2
0x180047c60  mov     rax, [rcx]
0x180047c63  mov     rax, [rax+10h]
0x180047c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c6c  jmp     loc_180047BD7
0x180047c71  mov     dword ptr [rdi+30h], 1
0x180047c78  mov     rcx, [rdi+20h]
0x180047c7c  xor     eax, eax
0x180047c7e  cmp     rdi, rcx
0x180047c81  cmovz   rcx, rax
0x180047c85  mov     rax, [rcx]
0x180047c88  mov     rax, [rax+10h]
0x180047c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c91  jmp     loc_180047B76
0x180047c96  mov     rax, [rcx]
0x180047c99  mov     rax, [rax+10h]
0x180047c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ca2  mov     qword ptr [rdi+28h], 0
0x180047caa  jmp     loc_180047B8D
0x180047caf  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180047cb7  jz      loc_180047BAA
0x180047cbd  mov     rax, cs:off_180121278
0x180047cc4  mov     r9, rcx
0x180047cc7  mov     [rsp+38h+var_18], 0
0x180047cd0  mov     r8d, 7
0x180047cd6  mov     rdx, cs:?_bidPtrSA_053_304@?6??BidRecycleID@CNotUpdt_BidGeneric@CRsetField@@AEAAHXZ@4REBGEB; ushort const * const `CRsetField::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_304
0x180047cdd  mov     rcx, cs:_bidID
0x180047ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ce9  jmp     loc_180047BAA
0x180047cee  mov     rax, [rcx]
0x180047cf1  mov     rax, [rax+10h]
0x180047cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cfa  mov     qword ptr [rbx+30h], 0
0x180047d02  jmp     loc_180047C1D
```
