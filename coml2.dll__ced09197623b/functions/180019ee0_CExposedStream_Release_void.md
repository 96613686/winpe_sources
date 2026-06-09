# CExposedStream::Release(void)

- ea: `0x180019ee0`
- end: `0x18001a27d`
- name: `?Release@CExposedStream@@UEAAKXZ`
- size: `925`
- prototype: `unsigned int __fastcall(CExposedStream *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004dfa0`
- `0x18004dfb0`
- `0x18004dfc0`

## callees

- `0x180018680`
- `0x180019ee0`
- `0x18001a290`
- `0x18001a510`
- `0x18001b1c0`
- `0x18001c268`
- `0x18001e0f8`
- `0x18002ea90`
- `0x180032538`
- `0x180061410`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001a146`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001a156`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001a146`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001a156`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a1be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a20f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a1be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a20f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a06e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a06e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a0a3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a0a3`

## pseudocode

```c
__int64 __fastcall CExposedStream::Release(CExposedStream *this)
{
  unsigned __int32 v2; // esi
  __int64 v3; // r14
  __int64 v4; // rdx
  int v5; // r8d
  __int64 v6; // rdi
  __int64 v7; // rax
  int v8; // ecx
  int v9; // r15d
  __int64 v10; // r13
  __int64 v11; // r14
  int v12; // eax
  _QWORD *v13; // rdx
  _QWORD *v14; // r8
  __int64 v15; // r12
  DWORD CurrentThreadId; // eax
  __int64 v17; // rcx
  bool v18; // zf
  __int64 v19; // rax
  CSmAllocator *TlsSmAllocator; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  int v24; // ecx
  int v25; // eax
  CSmAllocator *v26; // rax
  CSmAllocator *v27; // rax
  CSmAllocator *v28; // rax
  CSmAllocator *v29; // rax
  _QWORD *ReservedForOle; // [rsp+50h] [rbp+8h] BYREF

  if ( !this || !memcmp_0((char *)this + 64, &GUID_04a45d68_dba8_467d_9aed_e762432212f9, 0x10u) )
  {
    v2 = _InterlockedDecrement((volatile signed __int32 *)this + 32);
    if ( v2 )
      return v2;
    v3 = *((_QWORD *)this + 15);
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    if ( !ReservedForOle )
      InternalTlsAllocData(&ReservedForOle);
    if ( !ReservedForOle[1] )
    {
      v26 = (CSmAllocator *)HeapAlloc(g_hHeap, 0, 0x30u);
      if ( v26 )
      {
        v27 = CSmAllocator::CSmAllocator(v26);
        ReservedForOle[1] = v27;
        if ( v27 )
          goto LABEL_7;
      }
      else
      {
        ReservedForOle[1] = 0;
      }
      ReservedForOle[1] = &g_ErrorSmAllocator;
    }
LABEL_7:
    v4 = *(_QWORD *)(v3 + 96);
    v5 = *(_DWORD *)(v3 + 104);
    v6 = ReservedForOle[1];
    v7 = *(_QWORD *)(v3 + 88);
    *(_QWORD *)(v6 + 8) = v7;
    *(_QWORD *)(v6 + 16) = v4;
    if ( v7 )
      v8 = *(_DWORD *)(v7 + 16) - 24;
    else
      v8 = 0;
    *(_DWORD *)(v6 + 32) = v8;
    v9 = 0;
    *(_DWORD *)(v6 + 36) = v5;
    *(_QWORD *)NtCurrentTeb()->ReservedForOle = v4;
    v10 = *(_QWORD *)(v6 + 24);
    *(_QWORD *)(v6 + 24) = v3;
    v11 = *((_QWORD *)this + 15);
    if ( v11 )
    {
      v12 = CPerContext::TakeSem(*((CPerContext **)this + 15), v4);
      v13 = (_QWORD *)*((_QWORD *)this + 15);
      v9 = v12;
      v14 = (_QWORD *)*((_QWORD *)this + 14);
      v14[4] = v13[2];
      v14[5] = v13[3];
      v14[6] = v13[4];
    }
    v15 = *((_QWORD *)this + 6);
    CExposedStream::~CExposedStream(this);
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    if ( !ReservedForOle )
      InternalTlsAllocData(&ReservedForOle);
    if ( ReservedForOle[1] )
      goto LABEL_14;
    v28 = (CSmAllocator *)HeapAlloc(g_hHeap, 0, 0x30u);
    if ( v28 )
    {
      v29 = CSmAllocator::CSmAllocator(v28);
      ReservedForOle[1] = v29;
      if ( v29 )
      {
LABEL_14:
        (*(void (__fastcall **)(_QWORD, CExposedStream *))(*(_QWORD *)ReservedForOle[1] + 40LL))(
          ReservedForOle[1],
          this);
        if ( v11 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 56), 0xFFFFFFFF) == 1 )
          {
            if ( *(_QWORD *)(v11 + 16) )
              CPerContext::Close((CPerContext *)v11);
            CPerContext::~CPerContext((CPerContext *)v11);
            CMallocBased::operator delete((void *)v11);
            TlsSmAllocator = GetTlsSmAllocator();
            CSmAllocator::Uninit(TlsSmAllocator);
          }
          else if ( v9 >= 0 )
          {
            CurrentThreadId = GetCurrentThreadId();
            v17 = *(_QWORD *)(v11 + 112);
            if ( *(_DWORD *)(v17 + 8) == CurrentThreadId )
            {
              v18 = (*(_DWORD *)(v17 + 4))-- == 1;
              v19 = *(_QWORD *)(v11 + 112);
              if ( v18 )
              {
                *(_DWORD *)(v19 + 8) = 0;
                if ( _InterlockedDecrement(*(volatile signed __int32 **)(v11 + 112)) >= 0 )
                  SetEvent(*(HANDLE *)(v11 + 120));
              }
              else
              {
                _InterlockedDecrement((volatile signed __int32 *)v19);
              }
            }
          }
        }
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v10 )
        {
          v22 = *(_QWORD *)(v10 + 88);
          v23 = *(_QWORD *)(v10 + 96);
          v24 = *(_DWORD *)(v10 + 104);
          *(_QWORD *)(v6 + 8) = v22;
          *(_QWORD *)(v6 + 16) = v23;
          if ( v22 )
            v25 = *(_DWORD *)(v22 + 16) - 24;
          else
            v25 = 0;
          *(_DWORD *)(v6 + 32) = v25;
          *(_DWORD *)(v6 + 36) = v24;
          *(_QWORD *)NtCurrentTeb()->ReservedForOle = v23;
          *(_QWORD *)(v6 + 24) = v10;
        }
        else
        {
          *(_QWORD *)(v6 + 8) = 0;
          *(_QWORD *)(v6 + 16) = 0;
          *(_QWORD *)(v6 + 32) = 0;
          *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
          *(_QWORD *)(v6 + 24) = 0;
        }
        return v2;
      }
    }
    else
    {
      ReservedForOle[1] = 0;
    }
    ReservedForOle[1] = &g_ErrorSmAllocator;
    goto LABEL_14;
  }
  return 0;
}

```

## disassembly

```asm
0x180019ee0  push    rbx
0x180019ee2  sub     rsp, 40h
0x180019ee6  mov     rbx, rcx
0x180019ee9  test    rcx, rcx
0x180019eec  jz      short loc_180019F0C
0x180019eee  add     rcx, 40h ; '@'; Buf1
0x180019ef2  lea     rdx, _GUID_04a45d68_dba8_467d_9aed_e762432212f9; Buf2
0x180019ef9  mov     r8d, 10h; Size
0x180019eff  call    memcmp_0
0x180019f04  test    eax, eax
0x180019f06  jnz     loc_18001A132
0x180019f0c  mov     [rsp+48h+arg_8], rbp
0x180019f11  mov     ebp, 0FFFFFFFFh
0x180019f16  mov     [rsp+48h+arg_10], rsi
0x180019f1b  mov     esi, ebp
0x180019f1d  lock xadd [rbx+80h], esi
0x180019f25  sub     esi, 1
0x180019f28  jnz     loc_18001A120
0x180019f2e  mov     rax, gs:30h
0x180019f37  mov     [rsp+48h+arg_18], rdi
0x180019f3c  mov     [rsp+48h+var_10], r12
0x180019f41  mov     [rsp+48h+var_18], r13
0x180019f46  mov     rcx, [rax+1758h]
0x180019f4d  mov     [rsp+48h+var_20], r14
0x180019f52  mov     r14, [rbx+78h]
0x180019f56  mov     [rsp+48h+var_28], r15
0x180019f5b  mov     [rsp+48h+arg_0], rcx
0x180019f60  test    rcx, rcx
0x180019f63  jz      loc_18001A141
0x180019f69  mov     rax, [rsp+48h+arg_0]
0x180019f6e  lea     rdi, ?g_ErrorSmAllocator@@3VCErrorSmAllocator@@A; CErrorSmAllocator g_ErrorSmAllocator
0x180019f75  cmp     qword ptr [rax+8], 0
0x180019f7a  jz      loc_18001A1AF
0x180019f80  mov     rax, [rsp+48h+arg_0]
0x180019f85  mov     rdx, [r14+60h]; unsigned int
0x180019f89  mov     r8d, [r14+68h]
0x180019f8d  mov     rdi, [rax+8]
0x180019f91  mov     rax, [r14+58h]
0x180019f95  mov     [rdi+8], rax
0x180019f99  mov     [rdi+10h], rdx
0x180019f9d  test    rax, rax
0x180019fa0  jz      loc_18001A13A
0x180019fa6  mov     ecx, [rax+10h]
0x180019fa9  sub     ecx, 18h
0x180019fac  mov     [rdi+20h], ecx
0x180019faf  xor     r15d, r15d
0x180019fb2  mov     [rdi+24h], r8d
0x180019fb6  mov     rax, gs:30h
0x180019fbf  mov     rcx, [rax+1758h]
0x180019fc6  mov     [rcx], rdx
0x180019fc9  mov     r13, [rdi+18h]
0x180019fcd  mov     [rdi+18h], r14
0x180019fd1  mov     r14, [rbx+78h]
0x180019fd5  test    r14, r14
0x180019fd8  jz      short loc_18001A005
0x180019fda  mov     rcx, r14; this
0x180019fdd  call    ?TakeSem@CPerContext@@QEAAJK@Z; CPerContext::TakeSem(ulong)
0x180019fe2  mov     rdx, [rbx+78h]
0x180019fe6  mov     r15d, eax
0x180019fe9  mov     r8, [rbx+70h]
0x180019fed  mov     rcx, [rdx+10h]
0x180019ff1  mov     [r8+20h], rcx
0x180019ff5  mov     rcx, [rdx+18h]
0x180019ff9  mov     [r8+28h], rcx
0x180019ffd  mov     rcx, [rdx+20h]
0x18001a001  mov     [r8+30h], rcx
0x18001a005  mov     r12, [rbx+30h]
0x18001a009  mov     rcx, rbx; this
0x18001a00c  call    ??1CExposedStream@@QEAA@XZ; CExposedStream::~CExposedStream(void)
0x18001a011  mov     rcx, gs:30h
0x18001a01a  mov     rax, [rcx+1758h]
0x18001a021  mov     [rsp+48h+arg_0], rax
0x18001a026  test    rax, rax
0x18001a029  jz      loc_18001A151
0x18001a02f  mov     rax, [rsp+48h+arg_0]
0x18001a034  cmp     qword ptr [rax+8], 0
0x18001a039  jz      loc_18001A200
0x18001a03f  mov     rax, [rsp+48h+arg_0]
0x18001a044  mov     rdx, rbx
0x18001a047  mov     rcx, [rax+8]
0x18001a04b  mov     rax, [rcx]
0x18001a04e  mov     rax, [rax+28h]
0x18001a052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a057  test    r14, r14
0x18001a05a  jz      short loc_18001A0D3
0x18001a05c  mov     eax, ebp
0x18001a05e  lock xadd [r14+38h], eax
0x18001a064  cmp     eax, 1
0x18001a067  jz      short loc_18001A0AB
0x18001a069  test    r15d, r15d
0x18001a06c  js      short loc_18001A0D3
0x18001a06e  call    cs:__imp_GetCurrentThreadId
0x18001a074  mov     rcx, [r14+70h]
0x18001a078  cmp     [rcx+8], eax
0x18001a07b  jnz     short loc_18001A0D3
0x18001a07d  sub     dword ptr [rcx+4], 1
0x18001a081  mov     rax, [r14+70h]
0x18001a085  jnz     loc_18001A1A2
0x18001a08b  xor     r8d, r8d
0x18001a08e  mov     [rax+8], r8d
0x18001a092  mov     rax, [r14+70h]
0x18001a096  lock xadd [rax], ebp
0x18001a09a  cmp     ebp, 1
0x18001a09d  js      short loc_18001A0D6
0x18001a09f  mov     rcx, [r14+78h]; hEvent
0x18001a0a3  call    cs:__imp_SetEvent
0x18001a0a9  jmp     short loc_18001A0D3
0x18001a0ab  cmp     qword ptr [r14+10h], 0
0x18001a0b0  jnz     loc_18001A258
0x18001a0b6  mov     rcx, r14; this
0x18001a0b9  call    ??1CPerContext@@QEAA@XZ; CPerContext::~CPerContext(void)
0x18001a0be  mov     rcx, r14; void *
0x18001a0c1  call    ??3CMallocBased@@SAXPEAX@Z; CMallocBased::operator delete(void *)
0x18001a0c6  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001a0cb  mov     rcx, rax; this
0x18001a0ce  call    ?Uninit@CSmAllocator@@QEAAJXZ; CSmAllocator::Uninit(void)
0x18001a0d3  xor     r8d, r8d
0x18001a0d6  mov     r15, [rsp+48h+var_28]
0x18001a0db  mov     r14, [rsp+48h+var_20]
0x18001a0e0  test    r12, r12
0x18001a0e3  jnz     loc_18001A265
0x18001a0e9  mov     r12, [rsp+48h+var_10]
0x18001a0ee  test    r13, r13
0x18001a0f1  jnz     short loc_18001A161
0x18001a0f3  mov     [rdi+8], r8
0x18001a0f7  mov     [rdi+10h], r8
0x18001a0fb  mov     [rdi+20h], r13
0x18001a0ff  mov     rcx, gs:30h
0x18001a108  mov     rdx, [rcx+1758h]
0x18001a10f  mov     [rdx], r8
0x18001a112  mov     [rdi+18h], r8
0x18001a116  mov     rdi, [rsp+48h+arg_18]
0x18001a11b  mov     r13, [rsp+48h+var_18]
0x18001a120  mov     rbp, [rsp+48h+arg_8]
0x18001a125  mov     eax, esi
0x18001a127  mov     rsi, [rsp+48h+arg_10]
0x18001a12c  add     rsp, 40h
0x18001a130  pop     rbx
0x18001a131  retn
0x18001a132  xor     eax, eax
0x18001a134  add     rsp, 40h
0x18001a138  pop     rbx
0x18001a139  retn
0x18001a13a  xor     ecx, ecx
0x18001a13c  jmp     loc_180019FAC
0x18001a141  lea     rcx, [rsp+48h+arg_0]
0x18001a146  call    cs:__imp_InternalTlsAllocData
0x18001a14c  jmp     loc_180019F69
0x18001a151  lea     rcx, [rsp+48h+arg_0]
0x18001a156  call    cs:__imp_InternalTlsAllocData
0x18001a15c  jmp     loc_18001A02F
0x18001a161  mov     rax, [r13+58h]
0x18001a165  mov     rdx, [r13+60h]
0x18001a169  mov     ecx, [r13+68h]
0x18001a16d  mov     [rdi+8], rax
0x18001a171  mov     [rdi+10h], rdx
0x18001a175  test    rax, rax
0x18001a178  jz      short loc_18001A1AA
0x18001a17a  mov     eax, [rax+10h]
0x18001a17d  sub     eax, 18h
0x18001a180  mov     [rdi+20h], eax
0x18001a183  mov     [rdi+24h], ecx
0x18001a186  mov     rax, gs:30h
0x18001a18f  mov     rcx, [rax+1758h]
0x18001a196  mov     [rcx], rdx
0x18001a199  mov     [rdi+18h], r13
0x18001a19d  jmp     loc_18001A116
0x18001a1a2  lock dec dword ptr [rax]
0x18001a1a5  jmp     loc_18001A0D3
0x18001a1aa  mov     eax, r8d
0x18001a1ad  jmp     short loc_18001A180
0x18001a1af  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001a1b6  xor     edx, edx; dwFlags
0x18001a1b8  mov     r8d, 30h ; '0'; dwBytes
0x18001a1be  call    cs:__imp_HeapAlloc
0x18001a1c4  test    rax, rax
0x18001a1c7  jnz     short loc_18001A1D8
0x18001a1c9  mov     rax, [rsp+48h+arg_0]
0x18001a1ce  mov     qword ptr [rax+8], 0
0x18001a1d6  jmp     short loc_18001A1F2
0x18001a1d8  mov     rcx, rax; this
0x18001a1db  call    ??0CSmAllocator@@QEAA@XZ; CSmAllocator::CSmAllocator(void)
0x18001a1e0  mov     rcx, [rsp+48h+arg_0]
0x18001a1e5  mov     [rcx+8], rax
0x18001a1e9  test    rax, rax
0x18001a1ec  jnz     loc_180019F80
0x18001a1f2  mov     rax, [rsp+48h+arg_0]
0x18001a1f7  mov     [rax+8], rdi
0x18001a1fb  jmp     loc_180019F80
0x18001a200  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001a207  xor     edx, edx; dwFlags
0x18001a209  mov     r8d, 30h ; '0'; dwBytes
0x18001a20f  call    cs:__imp_HeapAlloc
0x18001a215  test    rax, rax
0x18001a218  jnz     short loc_18001A229
0x18001a21a  mov     rax, [rsp+48h+arg_0]
0x18001a21f  mov     qword ptr [rax+8], 0
0x18001a227  jmp     short loc_18001A243
0x18001a229  mov     rcx, rax; this
0x18001a22c  call    ??0CSmAllocator@@QEAA@XZ; CSmAllocator::CSmAllocator(void)
0x18001a231  mov     rcx, [rsp+48h+arg_0]
0x18001a236  mov     [rcx+8], rax
0x18001a23a  test    rax, rax
0x18001a23d  jnz     loc_18001A03F
0x18001a243  mov     rax, [rsp+48h+arg_0]
0x18001a248  lea     rcx, ?g_ErrorSmAllocator@@3VCErrorSmAllocator@@A; CErrorSmAllocator g_ErrorSmAllocator
0x18001a24f  mov     [rax+8], rcx
0x18001a253  jmp     loc_18001A03F
0x18001a258  mov     rcx, r14; this
0x18001a25b  call    ?Close@CPerContext@@QEAAXXZ; CPerContext::Close(void)
0x18001a260  jmp     loc_18001A0B6
0x18001a265  mov     rax, [r12]
0x18001a269  mov     rcx, r12
0x18001a26c  mov     rax, [rax+10h]
0x18001a270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a275  xor     r8d, r8d
0x18001a278  jmp     loc_18001A0E9
```
