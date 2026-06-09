# CSnapinThreadTable::FindThreads(int,BookKeeping::SnapinThreadFlags,ulong * *,ulong *)

- ea: `0x18000f43c`
- end: `0x18000f677`
- name: `?FindThreads@CSnapinThreadTable@@AEAAJHW4SnapinThreadFlags@BookKeeping@@PEAPEAKPEAK@Z`
- size: `571`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d550`
- `0x18000d5f0`

## callees

- `0x18000585c`
- `0x180008224`
- `0x18000bd34`
- `0x18000ed64`
- `0x18000f43c`
- `0x18000f680`
- `0x18000fbd4`
- `0x18000fc04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f5a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f5a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f508`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSnapinThreadTable::FindThreads(__int64 a1, int a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  volatile __int32 *v7; // r13
  _DWORD *v8; // rsi
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rdx
  _DWORD *v12; // rbx
  __int64 v13; // r14
  unsigned int v14; // r12d
  __int64 v15; // rcx
  _DWORD *v16; // rdi
  _BYTE v18[8]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v19; // [rsp+28h] [rbp-28h]
  __int16 v20; // [rsp+34h] [rbp-1Ch]
  _BYTE v21[8]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v22; // [rsp+40h] [rbp-10h]
  __int16 v23; // [rsp+4Ch] [rbp-4h]
  _DWORD *v24; // [rsp+90h] [rbp+40h] BYREF
  int v25; // [rsp+98h] [rbp+48h]

  v25 = a2;
  v24 = 0;
  v7 = (volatile __int32 *)(a1 + 176);
  CSmallSpinLock::WriteLock((CSmallSpinLock *)(a1 + 176));
  if ( a4 )
    *a4 = 0;
  v8 = a5;
  if ( a5 )
    *a5 = 0;
  if ( !a4 )
  {
    v9 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_33;
    v11 = 36;
    goto LABEL_9;
  }
  if ( !v8 )
  {
    v9 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_33;
    v11 = 37;
    goto LABEL_9;
  }
  v12 = CoTaskMemAlloc(0x10u);
  v24 = v12;
  if ( !v12 )
  {
    v9 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_33;
    v11 = 38;
LABEL_9:
    WPP_SF_(*(_QWORD *)(v10 + 16), v11, WPP_8949107765ef31f55290197bfd8c288d_Traceguids);
    goto LABEL_33;
  }
  v13 = 0;
  v14 = 4;
  LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::begin(a1, v18);
  LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::end(v15, v21);
  while ( 1 )
  {
    if ( v19 == v22 && v20 == v23 )
    {
      v9 = 0;
      *a4 = v12;
      v24 = 0;
      *v8 = v13;
      LKRhash::CLKRLinearHashTable_Iterator::_AddRef((LKRhash::CLKRLinearHashTable_Iterator *)v21, -1);
      LKRhash::CLKRLinearHashTable_Iterator::_AddRef((LKRhash::CLKRLinearHashTable_Iterator *)v18, -1);
      goto LABEL_33;
    }
    v16 = *(_DWORD **)(v19 + 8LL * v20 + 24);
    if ( v16[3] == 1 && (!v25 || v16[1] == v25) )
      break;
LABEL_27:
    LKRhash::CLKRLinearHashTable_Iterator::Increment((LKRhash::CLKRLinearHashTable_Iterator *)v18);
  }
  if ( (_DWORD)v13 != v14 || (a5 = v12, v14 *= 2, v12 = CoTaskMemRealloc(v12, 4LL * v14), (v24 = v12) != 0) )
  {
    v12[v13] = v16[2];
    v13 = (unsigned int)(v13 + 1);
    goto LABEL_27;
  }
  v9 = -2147024882;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 39, WPP_8949107765ef31f55290197bfd8c288d_Traceguids);
  v24 = a5;
  LKRhash::CLKRLinearHashTable_Iterator::_AddRef((LKRhash::CLKRLinearHashTable_Iterator *)v21, -1);
  LKRhash::CLKRLinearHashTable_Iterator::_AddRef((LKRhash::CLKRLinearHashTable_Iterator *)v18, -1);
LABEL_33:
  _InterlockedExchange(v7, 0);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v24);
  return v9;
}

```

## disassembly

```asm
0x18000f43c  mov     [rsp-38h+arg_10], rbx
0x18000f441  mov     [rsp-38h+arg_8], edx
0x18000f445  push    rbp
0x18000f446  push    rsi
0x18000f447  push    rdi
0x18000f448  push    r12
0x18000f44a  push    r13
0x18000f44c  push    r14
0x18000f44e  push    r15
0x18000f450  mov     rbp, rsp
0x18000f453  sub     rsp, 50h
0x18000f457  mov     r15, r9
0x18000f45a  mov     rdi, rcx
0x18000f45d  mov     [rbp+arg_0], 0
0x18000f465  lea     r13, [rcx+0B0h]
0x18000f46c  mov     rcx, r13; this
0x18000f46f  call    ?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x18000f474  test    r15, r15
0x18000f477  jz      short loc_18000F480
0x18000f479  mov     qword ptr [r15], 0
0x18000f480  mov     rsi, [rbp+arg_20]
0x18000f484  test    rsi, rsi
0x18000f487  jz      short loc_18000F48F
0x18000f489  mov     dword ptr [rsi], 0
0x18000f48f  test    r15, r15
0x18000f492  jnz     short loc_18000F4D3
0x18000f494  mov     edi, 80070057h
0x18000f499  lea     rax, WPP_GLOBAL_Control
0x18000f4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4a7  cmp     rcx, rax
0x18000f4aa  jz      loc_18000F64E
0x18000f4b0  cmp     byte ptr [rcx+19h], 2
0x18000f4b4  jb      loc_18000F64E
0x18000f4ba  lea     edx, [r15+24h]
0x18000f4be  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f4c5  mov     rcx, [rcx+10h]
0x18000f4c9  call    WPP_SF_
0x18000f4ce  jmp     loc_18000F64E
0x18000f4d3  test    rsi, rsi
0x18000f4d6  jnz     short loc_18000F503
0x18000f4d8  mov     edi, 80070057h
0x18000f4dd  lea     rax, WPP_GLOBAL_Control
0x18000f4e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4eb  cmp     rcx, rax
0x18000f4ee  jz      loc_18000F64E
0x18000f4f4  cmp     byte ptr [rcx+19h], 2
0x18000f4f8  jb      loc_18000F64E
0x18000f4fe  lea     edx, [rsi+25h]
0x18000f501  jmp     short loc_18000F4BE
0x18000f503  mov     ecx, 10h; cb
0x18000f508  call    cs:__imp_CoTaskMemAlloc
0x18000f50e  mov     rbx, rax
0x18000f511  mov     [rbp+arg_0], rax
0x18000f515  test    rax, rax
0x18000f518  jnz     short loc_18000F548
0x18000f51a  mov     edi, 8007000Eh
0x18000f51f  lea     rax, WPP_GLOBAL_Control
0x18000f526  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f52d  cmp     rcx, rax
0x18000f530  jz      loc_18000F64E
0x18000f536  cmp     byte ptr [rcx+19h], 2
0x18000f53a  jb      loc_18000F64E
0x18000f540  lea     edx, [rbx+26h]
0x18000f543  jmp     loc_18000F4BE
0x18000f548  xor     r14d, r14d
0x18000f54b  lea     r12d, [r14+4]
0x18000f54f  lea     rdx, [rbp+var_30]
0x18000f553  mov     rcx, rdi
0x18000f556  call    ?begin@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA?AViterator@12@XZ; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::begin(void)
0x18000f55b  nop
0x18000f55c  lea     rdx, [rbp+var_18]
0x18000f560  call    ?end@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA?AViterator@12@XZ; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::end(void)
0x18000f565  nop
0x18000f566  movsx   rax, [rbp+var_1C]
0x18000f56b  mov     rdi, [rbp+var_28]
0x18000f56f  cmp     rdi, [rbp+var_10]
0x18000f573  jnz     short loc_18000F57B
0x18000f575  cmp     ax, [rbp+var_4]
0x18000f579  jz      short loc_18000F5CF
0x18000f57b  mov     rdi, [rdi+rax*8+18h]
0x18000f580  cmp     dword ptr [rdi+0Ch], 1
0x18000f584  jnz     short loc_18000F5C4
0x18000f586  mov     eax, [rbp+arg_8]
0x18000f589  test    eax, eax
0x18000f58b  jz      short loc_18000F592
0x18000f58d  cmp     [rdi+4], eax
0x18000f590  jnz     short loc_18000F5C4
0x18000f592  cmp     r14d, r12d
0x18000f595  jnz     short loc_18000F5BA
0x18000f597  mov     [rbp+arg_20], rbx
0x18000f59b  add     r12d, r12d
0x18000f59e  mov     edx, r12d
0x18000f5a1  shl     rdx, 2; cb
0x18000f5a5  mov     rcx, rbx; pv
0x18000f5a8  call    cs:__imp_CoTaskMemRealloc
0x18000f5ae  mov     rbx, rax
0x18000f5b1  mov     [rbp+arg_0], rax
0x18000f5b5  test    rax, rax
0x18000f5b8  jz      short loc_18000F5F8
0x18000f5ba  mov     eax, [rdi+8]
0x18000f5bd  mov     [rbx+r14*4], eax
0x18000f5c1  inc     r14d
0x18000f5c4  lea     rcx, [rbp+var_30]; this
0x18000f5c8  call    ?Increment@CLKRLinearHashTable_Iterator@LKRhash@@QEAA_NXZ; LKRhash::CLKRLinearHashTable_Iterator::Increment(void)
0x18000f5cd  jmp     short loc_18000F566
0x18000f5cf  xor     edi, edi
0x18000f5d1  mov     [r15], rbx
0x18000f5d4  mov     [rbp+arg_0], rdi
0x18000f5d8  mov     [rsi], r14d
0x18000f5db  or      ebx, 0FFFFFFFFh
0x18000f5de  mov     edx, ebx; int
0x18000f5e0  lea     rcx, [rbp+var_18]; this
0x18000f5e4  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000f5e9  nop
0x18000f5ea  mov     edx, ebx; int
0x18000f5ec  lea     rcx, [rbp+var_30]; this
0x18000f5f0  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000f5f5  nop
0x18000f5f6  jmp     short loc_18000F64E
0x18000f5f8  mov     edi, 8007000Eh
0x18000f5fd  lea     rax, WPP_GLOBAL_Control
0x18000f604  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f60b  cmp     rcx, rax
0x18000f60e  jz      short loc_18000F62B
0x18000f610  cmp     byte ptr [rcx+19h], 2
0x18000f614  jb      short loc_18000F62B
0x18000f616  mov     edx, 27h ; '''
0x18000f61b  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f622  mov     rcx, [rcx+10h]
0x18000f626  call    WPP_SF_
0x18000f62b  mov     rax, [rbp+arg_20]
0x18000f62f  mov     [rbp+arg_0], rax
0x18000f633  or      ebx, 0FFFFFFFFh
0x18000f636  mov     edx, ebx; int
0x18000f638  lea     rcx, [rbp+var_18]; this
0x18000f63c  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000f641  nop
0x18000f642  mov     edx, ebx; int
0x18000f644  lea     rcx, [rbp+var_30]; this
0x18000f648  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000f64d  nop
0x18000f64e  xor     ecx, ecx
0x18000f650  xchg    ecx, [r13+0]
0x18000f654  lea     rcx, [rbp+arg_0]
0x18000f658  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000f65d  mov     eax, edi
0x18000f65f  mov     rbx, [rsp+50h+arg_10]
0x18000f667  add     rsp, 50h
0x18000f66b  pop     r15
0x18000f66d  pop     r14
0x18000f66f  pop     r13
0x18000f671  pop     r12
0x18000f673  pop     rdi
0x18000f674  pop     rsi
0x18000f675  pop     rbp
0x18000f676  retn
```
