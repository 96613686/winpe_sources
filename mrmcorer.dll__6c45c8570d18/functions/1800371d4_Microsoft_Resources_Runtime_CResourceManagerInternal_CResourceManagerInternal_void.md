# Microsoft::Resources::Runtime::CResourceManagerInternal::~CResourceManagerInternal(void)

- ea: `0x1800371d4`
- end: `0x18003738e`
- name: `??1CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAA@XZ`
- size: `442`
- prototype: `void __fastcall(Microsoft::Resources::Runtime::CResourceManagerInternal *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800371a8`

## callees

- `0x18002cfd0`
- `0x1800371d4`
- `0x180037394`
- `0x1800373cc`
- `0x1800373f8`
- `0x18003744c`
- `0x1800867dc`
- `0x180086800`
- `0x18008eb5c`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800372ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800372ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037314`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037374`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c22c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037314`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037374`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c22c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037322`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037382`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c22d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037322`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037382`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c22d5`

## pseudocode

```c
void __fastcall Microsoft::Resources::Runtime::CResourceManagerInternal::~CResourceManagerInternal(
        Microsoft::Resources::Runtime::CResourceManagerInternal *this,
        unsigned int a2)
{
  Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal *v3; // rcx
  _QWORD *Iterator; // rdi
  _QWORD *v5; // rax
  unsigned __int64 v6; // rcx
  _QWORD *v7; // rax
  unsigned int v8; // edx
  _QWORD *v9; // rdi
  _QWORD *v10; // rax
  unsigned __int64 v11; // rcx
  Microsoft::Resources::Runtime::CContext *v12; // rcx
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  void *v15; // rsi
  HANDLE ProcessHeap; // rax
  Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *v17; // rcx
  void *v18; // rsi
  HANDLE v19; // rax
  void *v20; // rsi
  HANDLE v21; // rax

  v3 = (Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal *)*((_QWORD *)this + 4);
  if ( v3 )
    Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal::`scalar deleting destructor'(v3, a2);
  *((_QWORD *)this + 4) = 0;
  Iterator = (_QWORD *)Microsoft::Resources::Runtime::MrtMap<unsigned short const *,Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *,Microsoft::Resources::Runtime::Equal<unsigned short const *>>::GetIterator((char *)this + 96);
  if ( Iterator )
  {
    while ( 1 )
    {
      v5 = (_QWORD *)*Iterator;
      v6 = Iterator[1] + 1LL;
      Iterator[1] = v6;
      if ( v6 >= v5[3] )
        break;
      v15 = *(void **)(*v5 + 16 * v6);
      if ( v15 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v15);
      }
      v17 = *(Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo **)(*(_QWORD *)*Iterator
                                                                                             + 16LL * Iterator[1]
                                                                                             + 8);
      if ( v17 )
        Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo::`scalar deleting destructor'(
          v17,
          2 * *((_DWORD *)Iterator + 2));
    }
    operator delete(Iterator);
  }
  v7 = operator new(0x10u, (const struct std::nothrow_t *)&byte_1800DE360);
  v9 = v7;
  if ( v7 )
  {
    *v7 = (char *)this + 136;
    v7[1] = -1;
    while ( 1 )
    {
      v10 = (_QWORD *)*v9;
      v11 = v9[1] + 1LL;
      v9[1] = v11;
      if ( v11 >= v10[3] )
        break;
      v18 = *(void **)(*v10 + 16 * v11);
      if ( v18 )
      {
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v18);
      }
      v20 = *(void **)(*(_QWORD *)*v9 + 16LL * v9[1] + 8);
      if ( v20 )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v20);
      }
    }
    operator delete(v9);
  }
  v12 = (Microsoft::Resources::Runtime::CContext *)*((_QWORD *)this + 11);
  if ( v12 )
    Microsoft::Resources::Runtime::CContext::`scalar deleting destructor'(v12, v8);
  v13 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 23);
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 10) = 1;
  if ( v13 )
    (**v13)(v13, 1);
  v14 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 22);
  *((_QWORD *)this + 23) = 0;
  if ( v14 )
    (**v14)(v14, 1);
  *((_QWORD *)this + 22) = 0;
  Microsoft::Resources::Runtime::MrtMap<unsigned short const *,unsigned short const *,Microsoft::Resources::Runtime::Equal<unsigned short const *>>::~MrtMap<unsigned short const *,unsigned short const *,Microsoft::Resources::Runtime::Equal<unsigned short const *>>((char *)this + 136);
  Microsoft::Resources::Runtime::MrtMap<unsigned short const *,unsigned short const *,Microsoft::Resources::Runtime::Equal<unsigned short const *>>::~MrtMap<unsigned short const *,unsigned short const *,Microsoft::Resources::Runtime::Equal<unsigned short const *>>((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  Microsoft::Resources::StringResult::~StringResult(this);
}

```

## disassembly

```asm
0x1800371d4  push    rbx
0x1800371d6  push    rbp
0x1800371d7  push    rsi
0x1800371d8  push    rdi
0x1800371d9  push    r14
0x1800371db  sub     rsp, 20h
0x1800371df  mov     rbx, rcx
0x1800371e2  mov     rcx, [rcx+20h]; this
0x1800371e6  test    rcx, rcx
0x1800371e9  jnz     loc_180037357
0x1800371ef  lea     rcx, [rbx+60h]
0x1800371f3  mov     qword ptr [rbx+20h], 0
0x1800371fb  call    ?GetIterator@?$MrtMap@PEBGPEAVCSchemaPriIndexInfo@CResourceManagerInternal@Runtime@Resources@Microsoft@@U?$Equal@PEBG@345@@Runtime@Resources@Microsoft@@QEAAPEAV?$MrtMapIterator@PEBGPEAVCSchemaPriIndexInfo@CResourceManagerInternal@Runtime@Resources@Microsoft@@@234@XZ; Microsoft::Resources::Runtime::MrtMap<ushort const *,Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *,Microsoft::Resources::Runtime::Equal<ushort const *>>::GetIterator(void)
0x180037200  mov     rdi, rax
0x180037203  test    rax, rax
0x180037206  jz      short loc_180037228
0x180037208  mov     rcx, [rdi+8]
0x18003720c  mov     rax, [rdi]
0x18003720f  inc     rcx
0x180037212  mov     [rdi+8], rcx
0x180037216  cmp     rcx, [rax+18h]
0x18003721a  jb      loc_180037305
0x180037220  mov     rcx, rdi; Block
0x180037223  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037228  lea     rdx, byte_1800DE360; struct std::nothrow_t *
0x18003722f  mov     ecx, 10h; unsigned __int64
0x180037234  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037239  lea     rbp, [rbx+88h]
0x180037240  mov     rdi, rax
0x180037243  test    rax, rax
0x180037246  jz      short loc_180037273
0x180037248  mov     [rax], rbp
0x18003724b  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180037253  mov     rcx, [rdi+8]
0x180037257  mov     rax, [rdi]
0x18003725a  inc     rcx
0x18003725d  mov     [rdi+8], rcx
0x180037261  cmp     rcx, [rax+18h]
0x180037265  jb      loc_180037361
0x18003726b  mov     rcx, rdi; Block
0x18003726e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037273  mov     rcx, [rbx+58h]; this
0x180037277  test    rcx, rcx
0x18003727a  jnz     loc_18003734D
0x180037280  mov     rcx, [rbx+0B8h]
0x180037287  mov     edi, 1
0x18003728c  mov     qword ptr [rbx+58h], 0
0x180037294  mov     [rbx+28h], edi
0x180037297  test    rcx, rcx
0x18003729a  jz      short loc_1800372A9
0x18003729c  mov     rax, [rcx]
0x18003729f  mov     edx, edi
0x1800372a1  mov     rax, [rax]
0x1800372a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372a9  mov     rcx, [rbx+0B0h]
0x1800372b0  mov     qword ptr [rbx+0B8h], 0
0x1800372bb  test    rcx, rcx
0x1800372be  jz      short loc_1800372CD
0x1800372c0  mov     rax, [rcx]
0x1800372c3  mov     edx, edi
0x1800372c5  mov     rax, [rax]
0x1800372c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372cd  mov     rcx, rbp
0x1800372d0  mov     qword ptr [rbx+0B0h], 0
0x1800372db  call    ??1?$MrtMap@PEBGPEBGU?$Equal@PEBG@Runtime@Resources@Microsoft@@@Runtime@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::Runtime::MrtMap<ushort const *,ushort const *,Microsoft::Resources::Runtime::Equal<ushort const *>>::~MrtMap<ushort const *,ushort const *,Microsoft::Resources::Runtime::Equal<ushort const *>>(void)
0x1800372e0  lea     rcx, [rbx+60h]
0x1800372e4  call    ??1?$MrtMap@PEBGPEBGU?$Equal@PEBG@Runtime@Resources@Microsoft@@@Runtime@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::Runtime::MrtMap<ushort const *,ushort const *,Microsoft::Resources::Runtime::Equal<ushort const *>>::~MrtMap<ushort const *,ushort const *,Microsoft::Resources::Runtime::Equal<ushort const *>>(void)
0x1800372e9  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800372ed  call    cs:__imp_DeleteCriticalSection
0x1800372f3  mov     rcx, rbx; this
0x1800372f6  add     rsp, 20h
0x1800372fa  pop     r14
0x1800372fc  pop     rdi
0x1800372fd  pop     rsi
0x1800372fe  pop     rbp
0x1800372ff  pop     rbx
0x180037300  jmp     ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180037305  mov     rax, [rax]
0x180037308  add     rcx, rcx
0x18003730b  mov     rsi, [rax+rcx*8]
0x18003730f  test    rsi, rsi
0x180037312  jz      short loc_180037328
0x180037314  call    cs:__imp_GetProcessHeap
0x18003731a  mov     r8, rsi; lpMem
0x18003731d  xor     edx, edx; dwFlags
0x18003731f  mov     rcx, rax; hHeap
0x180037322  call    cs:__imp_HeapFree
0x180037328  mov     rax, [rdi]
0x18003732b  mov     rdx, [rdi+8]
0x18003732f  add     rdx, rdx; unsigned int
0x180037332  mov     rcx, [rax]
0x180037335  mov     rcx, [rcx+rdx*8+8]; this
0x18003733a  test    rcx, rcx
0x18003733d  jz      loc_180037208
0x180037343  call    ??_GCSchemaPriIndexInfo@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo::`scalar deleting destructor'(uint)
0x180037348  jmp     loc_180037208
0x18003734d  call    ??_GCContext@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CContext::`scalar deleting destructor'(uint)
0x180037352  jmp     loc_180037280
0x180037357  call    ??_GCResourceReferenceHandlerInternal@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal::`scalar deleting destructor'(uint)
0x18003735c  jmp     loc_1800371EF
0x180037361  mov     rax, [rax]
0x180037364  add     rcx, rcx
0x180037367  mov     rsi, [rax+rcx*8]
0x18003736b  test    rsi, rsi
0x18003736e  jz      loc_1800C22AC
0x180037374  call    cs:__imp_GetProcessHeap
0x18003737a  mov     r8, rsi; lpMem
0x18003737d  xor     edx, edx; dwFlags
0x18003737f  mov     rcx, rax; hHeap
0x180037382  call    cs:__imp_HeapFree
0x180037388  nop
0x180037389  jmp     loc_1800C22AC
0x1800c22ac  mov     rax, [rdi]
0x1800c22af  mov     rdx, [rdi+8]
0x1800c22b3  add     rdx, rdx
0x1800c22b6  mov     rcx, [rax]
0x1800c22b9  mov     rsi, [rcx+rdx*8+8]
0x1800c22be  test    rsi, rsi
0x1800c22c1  jz      loc_180037253
0x1800c22c7  call    cs:__imp_GetProcessHeap
0x1800c22cd  mov     r8, rsi; lpMem
0x1800c22d0  xor     edx, edx; dwFlags
0x1800c22d2  mov     rcx, rax; hHeap
0x1800c22d5  call    cs:__imp_HeapFree
0x1800c22db  nop
0x1800c22dc  jmp     loc_180037253
```
