# EventObjectCollection::~EventObjectCollection(void)

- ea: `0x18001f494`
- end: `0x18001f755`
- name: `??1EventObjectCollection@@AEAA@XZ`
- size: `705`
- prototype: `void __fastcall(EventObjectCollection *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180003df0`
- `0x18001f46c`

## callees

- `0x180003d54`
- `0x180012654`
- `0x18001f494`
- `0x18001f75c`
- `0x18001f778`
- `0x180026684`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f6f3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f6f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f6b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f6b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044bae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f6c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f6c8`

## string_xrefs

- `0x18001f67a`: `com\complus\src\events\tier1\enum.cpp`
- `0x18001f72d`: `com\complus\src\events\Shared\UTSem.h`

## pseudocode

```c
void __fastcall EventObjectCollection::~EventObjectCollection(EventObjectCollection *this)
{
  char *v2; // r15
  __int64 v3; // rcx
  _QWORD *v4; // rsi
  char *v5; // r14
  volatile signed __int32 *v6; // rdi
  unsigned __int16 *v7; // r12
  __int64 v8; // r13
  unsigned __int16 *i; // rdx
  __int64 v10; // r8
  unsigned __int16 *v11; // rcx
  unsigned __int16 *v12; // rax
  __int64 v13; // rdi
  signed __int32 v14; // eax
  bool v15; // zf
  void *v16; // rcx
  __int64 v17; // rcx

  *(_QWORD *)this = &EventObjectCollection::`vftable'{for `IEventObjectCollection'};
  *((_QWORD *)this + 1) = &EventObjectCollection::`vftable'{for `ICollectionNotify'};
  v2 = (char *)this + 104;
  if ( *((_DWORD *)this + 36) )
  {
    v3 = *((_QWORD *)this + 3);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    v4 = (_QWORD *)((char *)this + 56);
    v5 = (char *)this + 80;
    if ( !*((_DWORD *)v2 + 10) )
      InternalAssert(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x12Eu, 0x10u, L"m_fInitialized");
    EnterCriticalSection((LPCRITICAL_SECTION)v2);
LABEL_7:
    v6 = *(volatile signed __int32 **)v5;
    if ( v5 != (char *)this + 80 && _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 6, 0xFFFFFFFF) == 1 )
    {
      Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc::~Assoc(v5);
      *((_QWORD *)v5 + 2) = *((_QWORD *)this + 9);
      *((_QWORD *)this + 9) = v5;
    }
    while ( v6 != (volatile signed __int32 *)((char *)this + 80) )
    {
      if ( *((int *)v6 + 6) < 0 )
      {
        _InterlockedIncrement(v6 + 6);
        v5 = (char *)v6;
        v7 = (unsigned __int16 *)*((_QWORD *)v6 + 4);
        v8 = *((_QWORD *)v6 + 5);
        if ( !v8 )
          InternalError(L"com\\complus\\src\\events\\tier1\\enum.cpp", 0x1F1u, 0x80001203, 0x10u);
        i = v7;
        v10 = 19088743;
        while ( *i )
          v10 = *i++ + ((unsigned int)v10 >> 27) + 32 * (_DWORD)v10;
        if ( *v4 )
        {
          for ( i = (unsigned __int16 *)(*v4 + 8LL * ((unsigned int)v10 % *((_DWORD *)this + 16)));
                *(_QWORD *)i;
                i = (unsigned __int16 *)(*(_QWORD *)i + 16LL) )
          {
            v11 = v7;
            v12 = *(unsigned __int16 **)(*(_QWORD *)i + 32LL);
            if ( v12 == v7 )
            {
LABEL_23:
              v13 = *(_QWORD *)i;
              *(_QWORD *)i = *(_QWORD *)(*(_QWORD *)i + 16LL);
              v14 = *(_DWORD *)(v13 + 24);
              do
              {
                v15 = v14 == _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 24), v14 & 0x7FFFFFFF, v14);
                v14 = *(_DWORD *)(v13 + 24);
              }
              while ( !v15 );
              if ( !v14 )
              {
                Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc::`scalar deleting destructor'(
                  v13,
                  0);
                *(_QWORD *)(v13 + 16) = *((_QWORD *)this + 9);
                *((_QWORD *)this + 9) = v13;
              }
              --*((_DWORD *)this + 17);
              break;
            }
            if ( v12 && v7 )
            {
              while ( 1 )
              {
                v10 = *v12;
                if ( (_WORD)v10 != *v11 )
                  break;
                if ( !(_WORD)v10 )
                  goto LABEL_23;
                ++v12;
                ++v11;
              }
            }
          }
        }
        (*(void (__fastcall **)(__int64, unsigned __int16 *, __int64))(*(_QWORD *)v8 + 16LL))(v8, i, v10);
        CoTaskMemFree(v7);
        --*((_DWORD *)this + 24);
        goto LABEL_7;
      }
      v6 = *(volatile signed __int32 **)v6;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)v2);
    if ( *((_BYTE *)this + 32) )
    {
      v16 = (void *)*((_QWORD *)this + 5);
      if ( v16 )
        CoTaskMemFree(v16);
      v17 = *((_QWORD *)this + 6);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    _InterlockedDecrement(&g_tier1ActiveObjects);
  }
  else
  {
    v4 = (_QWORD *)((char *)this + 56);
  }
  if ( *((_DWORD *)v2 + 10) )
    DeleteCriticalSection((LPCRITICAL_SECTION)v2);
  Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::~Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>((__int64)v4);
}

```

## disassembly

```asm
0x18001f494  mov     [rsp+arg_8], rbx
0x18001f499  mov     [rsp+arg_10], rsi
0x18001f49e  mov     [rsp+arg_0], rcx
0x18001f4a3  push    rdi
0x18001f4a4  push    r12
0x18001f4a6  push    r13
0x18001f4a8  push    r14
0x18001f4aa  push    r15
0x18001f4ac  sub     rsp, 60h
0x18001f4b0  mov     rbx, rcx
0x18001f4b3  lea     rax, ??_7EventObjectCollection@@6BIEventObjectCollection@@@; const EventObjectCollection::`vftable'{for `IEventObjectCollection'}
0x18001f4ba  mov     [rcx], rax
0x18001f4bd  lea     rax, ??_7EventObjectCollection@@6BICollectionNotify@@@; const EventObjectCollection::`vftable'{for `ICollectionNotify'}
0x18001f4c4  mov     [rcx+8], rax
0x18001f4c8  lea     r15, [rcx+68h]
0x18001f4cc  xor     r12d, r12d
0x18001f4cf  cmp     [r15+28h], r12d
0x18001f4d3  jz      loc_18001F74F
0x18001f4d9  mov     rcx, [rcx+18h]
0x18001f4dd  test    rcx, rcx
0x18001f4e0  jnz     loc_18001F73E
0x18001f4e6  lea     rsi, [rbx+38h]
0x18001f4ea  lea     r14, [rsi+18h]
0x18001f4ee  cmp     [r15+28h], r12d
0x18001f4f2  jz      loc_18001F71B
0x18001f4f8  mov     rcx, r15; lpCriticalSection
0x18001f4fb  call    cs:__imp_EnterCriticalSection
0x18001f501  nop
0x18001f502  mov     rdi, [r14]
0x18001f505  mov     [rsp+88h+var_48], rdi
0x18001f50a  lea     rax, [rsi+18h]
0x18001f50e  cmp     r14, rax
0x18001f511  jz      short loc_18001F535
0x18001f513  or      eax, 0FFFFFFFFh
0x18001f516  lock xadd [r14+18h], eax
0x18001f51c  cmp     eax, 1
0x18001f51f  jnz     short loc_18001F535
0x18001f521  mov     rcx, r14
0x18001f524  call    ??1Assoc@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@QEAA@XZ; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc::~Assoc(void)
0x18001f529  mov     rax, [rsi+10h]
0x18001f52d  mov     [r14+10h], rax
0x18001f531  mov     [rsi+10h], r14
0x18001f535  lea     rax, [rsi+18h]
0x18001f539  cmp     rdi, rax
0x18001f53c  jz      loc_18001F68E
0x18001f542  mov     eax, [rdi+18h]
0x18001f545  test    eax, eax
0x18001f547  js      short loc_18001F553
0x18001f549  mov     rdi, [rdi]
0x18001f54c  mov     [rsp+88h+var_48], rdi
0x18001f551  jmp     short loc_18001F535
0x18001f553  lock inc dword ptr [rdi+18h]
0x18001f557  mov     r14, rdi
0x18001f55a  mov     [rsp+88h+var_30], rdi
0x18001f55f  mov     r12, [rdi+20h]
0x18001f563  mov     r13, [rdi+28h]
0x18001f567  xor     r10d, r10d
0x18001f56a  test    r13, r13
0x18001f56d  jz      loc_18001F669
0x18001f573  mov     [rsp+88h+var_68], r10
0x18001f578  mov     rdx, r12
0x18001f57b  mov     [rsp+88h+var_60], rdx
0x18001f580  mov     r8d, 1234567h
0x18001f586  cmp     [rdx], r10w
0x18001f58a  jz      short loc_18001F5AA
0x18001f58c  mov     ecx, r8d
0x18001f58f  shr     ecx, 1Bh
0x18001f592  shl     r8d, 5
0x18001f596  add     r8d, ecx
0x18001f599  movzx   eax, word ptr [rdx]
0x18001f59c  add     r8d, eax
0x18001f59f  add     rdx, 2
0x18001f5a3  mov     [rsp+88h+var_60], rdx
0x18001f5a8  jmp     short loc_18001F586
0x18001f5aa  mov     r9, [rsi]
0x18001f5ad  test    r9, r9
0x18001f5b0  jnz     short loc_18001F5D6
0x18001f5b2  mov     rax, [r13+0]
0x18001f5b6  mov     rcx, r13
0x18001f5b9  mov     rax, [rax+10h]
0x18001f5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5c2  mov     rcx, r12; pv
0x18001f5c5  call    cs:__imp_CoTaskMemFree
0x18001f5cb  dec     dword ptr [rbx+60h]
0x18001f5ce  xor     r12d, r12d
0x18001f5d1  jmp     loc_18001F502
0x18001f5d6  xor     edx, edx
0x18001f5d8  mov     eax, r8d
0x18001f5db  div     dword ptr [rbx+40h]
0x18001f5de  lea     rdx, [r9+rdx*8]
0x18001f5e2  mov     [rsp+88h+var_68], rdx
0x18001f5e7  mov     rax, [rdx]
0x18001f5ea  test    rax, rax
0x18001f5ed  jz      short loc_18001F5B2
0x18001f5ef  mov     rcx, r12
0x18001f5f2  mov     [rsp+88h+var_50], rcx
0x18001f5f7  mov     rax, [rax+20h]
0x18001f5fb  mov     [rsp+88h+var_58], rax
0x18001f600  cmp     rax, r12
0x18001f603  jnz     short loc_18001F62D
0x18001f605  mov     rdi, [rdx]
0x18001f608  mov     rax, [rdi+10h]
0x18001f60c  mov     [rdx], rax
0x18001f60f  mov     eax, [rdi+18h]
0x18001f612  mov     ecx, eax
0x18001f614  btr     ecx, 1Fh
0x18001f618  lock cmpxchg [rdi+18h], ecx
0x18001f61d  mov     eax, [rdi+18h]
0x18001f620  jz      short loc_18001F624
0x18001f622  jmp     short loc_18001F612
0x18001f624  test    eax, eax
0x18001f626  jz      short loc_18001F695
0x18001f628  dec     dword ptr [rbx+44h]
0x18001f62b  jmp     short loc_18001F5B2
0x18001f62d  test    rax, rax
0x18001f630  jz      short loc_18001F641
0x18001f632  test    r12, r12
0x18001f635  jz      short loc_18001F641
0x18001f637  movzx   r8d, word ptr [rax]
0x18001f63b  cmp     r8w, [rcx]
0x18001f63f  jz      short loc_18001F64F
0x18001f641  mov     rdx, [rdx]
0x18001f644  add     rdx, 10h
0x18001f648  mov     [rsp+88h+var_68], rdx
0x18001f64d  jmp     short loc_18001F5E7
0x18001f64f  test    r8w, r8w
0x18001f653  jz      short loc_18001F605
0x18001f655  add     rax, 2
0x18001f659  mov     [rsp+88h+var_58], rax
0x18001f65e  add     rcx, 2
0x18001f662  mov     [rsp+88h+var_50], rcx
0x18001f667  jmp     short loc_18001F637
0x18001f669  mov     edx, 1F1h; unsigned int
0x18001f66e  mov     r9d, 10h; unsigned __int16
0x18001f674  mov     r8d, 80001203h; unsigned int
0x18001f67a  lea     rcx, aComComplusSrcE_21; "com\\complus\\src\\events\\tier1\\enum."...
0x18001f681  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001f686  xor     r10d, r10d
0x18001f689  jmp     loc_18001F573
0x18001f68e  mov     [rsp+88h+var_30], rdi
0x18001f693  jmp     short loc_18001F6B0
0x18001f695  xor     edx, edx
0x18001f697  mov     rcx, rdi
0x18001f69a  call    ??_GAssoc@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@QEAAPEAXI@Z; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc::`scalar deleting destructor'(uint)
0x18001f69f  mov     rax, [rbx+48h]
0x18001f6a3  mov     [rdi+10h], rax
0x18001f6a7  mov     [rbx+48h], rdi
0x18001f6ab  jmp     loc_18001F628
0x18001f6b0  mov     rcx, r15; lpCriticalSection
0x18001f6b3  call    cs:__imp_LeaveCriticalSection
0x18001f6b9  cmp     [rbx+20h], r12b
0x18001f6bd  jz      short loc_18001F6E3
0x18001f6bf  mov     rcx, [rbx+28h]; pv
0x18001f6c3  test    rcx, rcx
0x18001f6c6  jz      short loc_18001F6CE
0x18001f6c8  call    cs:__imp_CoTaskMemFree
0x18001f6ce  mov     rcx, [rbx+30h]
0x18001f6d2  test    rcx, rcx
0x18001f6d5  jz      short loc_18001F6E3
0x18001f6d7  mov     rax, [rcx]
0x18001f6da  mov     rax, [rax+10h]
0x18001f6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6e3  lock dec cs:?g_tier1ActiveObjects@@3JA; long g_tier1ActiveObjects
0x18001f6ea  cmp     [r15+28h], r12d
0x18001f6ee  jz      short loc_18001F6F9
0x18001f6f0  mov     rcx, r15; lpCriticalSection
0x18001f6f3  call    cs:__imp_DeleteCriticalSection
0x18001f6f9  mov     rcx, rsi
0x18001f6fc  call    ??1?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@QEAA@XZ; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::~Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>(void)
0x18001f701  lea     r11, [rsp+88h+var_28]
0x18001f706  mov     rbx, [r11+38h]
0x18001f70a  mov     rsi, [r11+40h]
0x18001f70e  mov     rsp, r11
0x18001f711  pop     r15
0x18001f713  pop     r14
0x18001f715  pop     r13
0x18001f717  pop     r12
0x18001f719  pop     rdi
0x18001f71a  retn
0x18001f71b  mov     r8d, 10h; unsigned __int16
0x18001f721  lea     r9, aMFinitialized; "m_fInitialized"
0x18001f728  mov     edx, 12Eh; unsigned int
0x18001f72d  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x18001f734  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18001f739  jmp     loc_18001F4F8
0x18001f73e  mov     rax, [rcx]
0x18001f741  mov     rax, [rax+10h]
0x18001f745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f74a  jmp     loc_18001F4E6
0x18001f74f  lea     rsi, [rcx+38h]
0x18001f753  jmp     short loc_18001F6EA
0x180044b95  push    rbp
0x180044b97  sub     rsp, 20h
0x180044b9b  mov     rbp, rdx
0x180044b9e  mov     rcx, [rbp+90h]
0x180044ba5  add     rcx, 68h ; 'h'
0x180044ba9  add     rsp, 20h
0x180044bad  pop     rbp
0x180044bae  jmp     cs:__imp_LeaveCriticalSection
```
