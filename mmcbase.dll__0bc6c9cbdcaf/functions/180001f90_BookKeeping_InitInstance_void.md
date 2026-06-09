# BookKeeping::InitInstance(void)

- ea: `0x180001f90`
- end: `0x1800022e9`
- name: `?InitInstance@BookKeeping@@SAJXZ`
- size: `857`
- prototype: `__int64(void)`
- caller_count: `10`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001230`
- `0x1800018b8`
- `0x180001c00`
- `0x18000d2e0`
- `0x18000d550`
- `0x18000d5f0`
- `0x18000d7e4`
- `0x18000dd40`
- `0x18000e360`
- `0x18000e3f0`

## callees

- `0x180001f90`
- `0x1800023e0`
- `0x1800052dc`
- `0x180005890`
- `0x1800064b4`
- `0x180007310`
- `0x180008630`
- `0x18000d034`
- `0x18000d08c`
- `0x18000edf8`
- `0x18000ef5c`
- `0x1800113b4`
- `0x18001984c`
- `0x180019ba0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002046`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002046`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 BookKeeping::InitInstance(void)
{
  int Instance; // ebx
  __int64 v1; // rcx
  int v2; // r11d
  CHeapFactory *v3; // rcx
  unsigned int v4; // r8d
  CHeapFactory *v5; // rcx
  LKRhash::CLKRLinearHashTable *v6; // rbx
  unsigned int v7; // r8d
  __int64 v8; // rcx
  __int64 v9; // rdx
  struct SnapinCLSIDTable *v10; // rax
  struct CSnapinThreadTable **v11; // rcx
  struct SnapinCLSIDTable *v12; // rbx
  SnapinOwnerTable *v13; // rcx
  SnapinOwnerTable *v14; // rcx
  CHeapFactory *v15; // rcx
  unsigned int v16; // r8d
  LKRhash::CLKRLinearHashTable *v17; // rax
  __int64 v18; // rdx
  WCHAR *v19; // r8
  LKRhash::CLKRLinearHashTable *v20; // rbx
  unsigned int v22; // [rsp+48h] [rbp+7h]
  bool v23; // [rsp+50h] [rbp+Fh]
  bool v24; // [rsp+58h] [rbp+17h]
  struct CLKRhashAllocator *v25; // [rsp+60h] [rbp+1Fh]
  void **v26; // [rsp+68h] [rbp+27h] BYREF
  unsigned __int16 *v27; // [rsp+70h] [rbp+2Fh]
  __int64 v28; // [rsp+78h] [rbp+37h]
  int v29; // [rsp+80h] [rbp+3Fh]
  LKRhash::CLKRLinearHashTable *v30; // [rsp+A8h] [rbp+67h] BYREF

  Instance = 0;
  if ( BookKeeping::s_initLock
    || _InterlockedCompareExchange((volatile signed __int32 *)&BookKeeping::s_initLock, GetCurrentThreadId(), 0) )
  {
    CSmallSpinLock::_LockSpin((CSmallSpinLock *)&BookKeeping::s_initLock);
  }
  if ( !BookKeeping::s_fInitialized )
  {
    v26 = &CStr::`vftable';
    v27 = (unsigned __int16 *)&CStr::s_rgwchEmptyStringBuffer;
    v28 = 0;
    v29 = 0;
    if ( (int)CStr::LoadStringW((CStr *)&v26, mmcerror::SC::s_hInst, 0x2EF1u) >= 0 )
    {
      v2 = StringCchCopyW(&qword_18002C4B8, 0x80u, v27);
      v1 = 0x80000000LL;
      if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147024774 )
        dword_18002CBE0 = GetTickCount();
    }
    SnapinRecord::InitializeDummySnapin((SnapinRecord *)v1);
    v6 = (LKRhash::CLKRLinearHashTable *)CHeapFactory::Alloc(v3, 0xB0u, v4);
    v30 = v6;
    if ( v6 )
      LKRhash::CLKRLinearHashTable::CLKRLinearHashTable(
        v6,
        "number",
        LKRhash::CTypedHashTable<SnapinInterfaceTable,InterfaceRecord,void *,LKRhash::CLKRLinearHashTable>::_ExtractKey,
        LKRhash::CTypedHashTable<SnapinInterfaceTable,InterfaceRecord,void *,LKRhash::CLKRLinearHashTable>::_CalcKeyHash,
        LKRhash::CTypedHashTable<SnapinInterfaceTable,InterfaceRecord,void *,LKRhash::CLKRLinearHashTable>::_EqualKeys,
        (void (*)(const void *, int))CObject::AssertValid,
        4.0,
        3u,
        v22,
        v23,
        v24,
        v25);
    else
      v6 = 0;
    BookKeeping::s_pInterfaceTable = v6;
    if ( v6 )
    {
      v10 = (struct SnapinCLSIDTable *)CHeapFactory::Alloc(v5, 0xB0u, v7);
      v12 = v10;
      v30 = v10;
      if ( v10 )
        LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>(v10);
      else
        v12 = 0;
      BookKeeping::s_pSnapinTable = v12;
      if ( v12 )
      {
        Instance = CSnapinThreadTable::CreateInstance(v11);
        if ( Instance >= 0 )
        {
          Instance = SnapinOwnerTable::AddSnapin(v13, (struct SnapinRecord *)&BookKeeping::s_unknownSnapin, (int *)&v30);
          if ( Instance >= 0 )
          {
            Instance = SnapinOwnerTable::AddSnapin(v14, (struct SnapinRecord *)&BookKeeping::s_dummySnapin, (int *)&v30);
            if ( Instance >= 0 )
            {
              v17 = (LKRhash::CLKRLinearHashTable *)CHeapFactory::Alloc(v15, 0xB0u, v16);
              v20 = v17;
              v30 = v17;
              if ( v17 )
                LKRhash::CTypedHashTable<ItemHandleTable,ItemHandle,void *,LKRhash::CLKRLinearHashTable>::CTypedHashTable<ItemHandleTable,ItemHandle,void *,LKRhash::CLKRLinearHashTable>(v17);
              else
                v20 = 0;
              BookKeeping::s_pItemHandleTable = v20;
              if ( v20 )
              {
                Instance = ResourceCache::LoadResources(mmcerror::SC::s_hInst, v18, v19);
                if ( Instance >= 0 )
                  goto LABEL_47;
                v8 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
                  goto LABEL_47;
                v9 = 16;
              }
              else
              {
                Instance = -2147024882;
                v8 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
                  goto LABEL_47;
                v9 = 15;
              }
            }
            else
            {
              v8 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
                goto LABEL_47;
              v9 = 14;
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
              goto LABEL_47;
            v9 = 13;
          }
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
            goto LABEL_47;
          v9 = 12;
        }
      }
      else
      {
        Instance = -2147024882;
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
          goto LABEL_47;
        v9 = 11;
      }
    }
    else
    {
      Instance = -2147024882;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
        goto LABEL_47;
      v9 = 10;
    }
    WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids, (unsigned int)Instance);
LABEL_47:
    v26 = &CStr::`vftable';
    CStr::Empty((CStr *)&v26);
  }
  BookKeeping::s_fInitialized = Instance >= 0;
  _InterlockedExchange((volatile __int32 *)&BookKeeping::s_initLock, 0);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180001f90  mov     rax, rsp
0x180001f93  mov     [rax+10h], rbx
0x180001f97  mov     [rax+18h], rdi
0x180001f9b  push    rbp
0x180001f9c  lea     rbp, [rax-5Fh]
0x180001fa0  sub     rsp, 90h
0x180001fa7  movaps  xmmword ptr [rax-18h], xmm6
0x180001fab  xor     ebx, ebx
0x180001fad  mov     eax, cs:?s_initLock@BookKeeping@@0VCSmallSpinLock@@A; CSmallSpinLock BookKeeping::s_initLock
0x180001fb3  test    eax, eax
0x180001fb5  jnz     short loc_180001FCB
0x180001fb7  call    cs:__imp_GetCurrentThreadId
0x180001fbd  mov     ecx, eax
0x180001fbf  xor     eax, eax
0x180001fc1  lock cmpxchg cs:?s_initLock@BookKeeping@@0VCSmallSpinLock@@A, ecx; CSmallSpinLock BookKeeping::s_initLock
0x180001fc9  jz      short loc_180001FD7
0x180001fcb  lea     rcx, ?s_initLock@BookKeeping@@0VCSmallSpinLock@@A; this
0x180001fd2  call    ?_LockSpin@CSmallSpinLock@@AEAAXXZ; CSmallSpinLock::_LockSpin(void)
0x180001fd7  cmp     cs:?s_fInitialized@BookKeeping@@0_NA, bl; bool BookKeeping::s_fInitialized
0x180001fdd  jnz     loc_1800022B8
0x180001fe3  lea     rdi, ??_7CStr@@6B@; const CStr::`vftable'
0x180001fea  mov     [rbp+57h+var_30], rdi
0x180001fee  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180001ff5  mov     [rbp+57h+var_28], rax
0x180001ff9  mov     [rbp+57h+var_20], rbx
0x180001ffd  mov     [rbp+57h+var_18], ebx
0x180002000  mov     r8d, 2EF1h; uID
0x180002006  mov     rdx, cs:?s_hInst@SC@mmcerror@@0PEAUHINSTANCE__@@EA; hInstance
0x18000200d  lea     rcx, [rbp+57h+var_30]; this
0x180002011  call    ?LoadStringW@CStr@@QEAAJPEAUHINSTANCE__@@I@Z; CStr::LoadStringW(HINSTANCE__ *,uint)
0x180002016  test    eax, eax
0x180002018  js      short loc_180002052
0x18000201a  mov     r8, [rbp+57h+var_28]; unsigned __int16 *
0x18000201e  mov     edx, 80h; unsigned __int64
0x180002023  lea     rcx, qword_18002C4B8; unsigned __int16 *
0x18000202a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000202f  mov     r11d, eax
0x180002032  mov     ecx, 80000000h
0x180002037  add     eax, ecx
0x180002039  test    ecx, eax
0x18000203b  jnz     short loc_180002046
0x18000203d  cmp     r11d, 8007007Ah
0x180002044  jnz     short loc_180002052
0x180002046  call    cs:__imp_GetTickCount
0x18000204c  mov     cs:dword_18002CBE0, eax
0x180002052  call    ?InitializeDummySnapin@SnapinRecord@@QEAAJXZ; SnapinRecord::InitializeDummySnapin(void)
0x180002057  mov     edx, 0B0h; unsigned __int64
0x18000205c  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x180002061  mov     rbx, rax
0x180002064  mov     [rbp+57h+arg_0], rax
0x180002068  movsd   xmm6, cs:__real@4010000000000000
0x180002070  test    rax, rax
0x180002073  jz      short loc_1800020BA
0x180002075  mov     [rsp+90h+var_58], 3; unsigned int
0x18000207d  movsd   [rsp+90h+var_60], xmm6; double
0x180002083  lea     rax, ?AssertValid@CObject@@UEBAXXZ; CObject::AssertValid(void)
0x18000208a  mov     [rsp+90h+var_68], rax; void (*)(const void *, int)
0x18000208f  lea     rax, ?_EqualKeys@?$CTypedHashTable@VSnapinInterfaceTable@@VInterfaceRecord@@PEAXVCLKRLinearHashTable@LKRhash@@@LKRhash@@CA_N_K0@Z; LKRhash::CTypedHashTable<SnapinInterfaceTable,InterfaceRecord,void *,LKRhash::CLKRLinearHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180002096  mov     [rsp+90h+var_70], rax; bool (*)(unsigned __int64, unsigned __int64)
0x18000209b  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VSnapinInterfaceTable@@VInterfaceRecord@@PEAXVCLKRLinearHashTable@LKRhash@@@LKRhash@@CAK_K@Z; unsigned int (*)(unsigned __int64)
0x1800020a2  lea     r8, ?_ExtractKey@?$CTypedHashTable@VSnapinInterfaceTable@@VInterfaceRecord@@PEAXVCLKRLinearHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; unsigned __int64 (*)(const void *)
0x1800020a9  lea     rdx, aNumber; "number"
0x1800020b0  mov     rcx, rbx; this
0x1800020b3  call    ??0CLKRLinearHashTable@LKRhash@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N7PEAVCLKRhashAllocator@@@Z; LKRhash::CLKRLinearHashTable::CLKRLinearHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool,bool,CLKRhashAllocator *)
0x1800020b8  jmp     short loc_1800020BC
0x1800020ba  xor     ebx, ebx
0x1800020bc  mov     cs:?s_pInterfaceTable@BookKeeping@@0PEAVSnapinInterfaceTable@@EA, rbx; SnapinInterfaceTable * BookKeeping::s_pInterfaceTable
0x1800020c3  test    rbx, rbx
0x1800020c6  jnz     short loc_1800020F8
0x1800020c8  mov     ebx, 8007000Eh
0x1800020cd  lea     rax, WPP_GLOBAL_Control
0x1800020d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020db  cmp     rcx, rax
0x1800020de  jz      loc_1800022AB
0x1800020e4  cmp     byte ptr [rcx+19h], 2
0x1800020e8  jb      loc_1800022AB
0x1800020ee  mov     edx, 0Ah
0x1800020f3  jmp     loc_180002297
0x1800020f8  mov     edx, 0B0h; unsigned __int64
0x1800020fd  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x180002102  mov     rbx, rax
0x180002105  mov     [rbp+57h+arg_0], rax
0x180002109  test    rax, rax
0x18000210c  jz      short loc_18000211B
0x18000210e  movaps  xmm2, xmm6
0x180002111  mov     rcx, rax
0x180002114  call    ??0?$CTypedHashTable@VSnapinCLSIDTable@@VSnapinRecord@@PEBVCStr@@VCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA@PEBDNKK_N1PEAVCLKRhashAllocator@@@Z; LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>(char const *,double,ulong,ulong,bool,bool,CLKRhashAllocator *)
0x180002119  jmp     short loc_18000211D
0x18000211b  xor     ebx, ebx
0x18000211d  mov     cs:?s_pSnapinTable@BookKeeping@@0PEAVSnapinCLSIDTable@@EA, rbx; SnapinCLSIDTable * BookKeeping::s_pSnapinTable
0x180002124  test    rbx, rbx
0x180002127  jnz     short loc_180002159
0x180002129  mov     ebx, 8007000Eh
0x18000212e  lea     rax, WPP_GLOBAL_Control
0x180002135  mov     rcx, cs:WPP_GLOBAL_Control
0x18000213c  cmp     rcx, rax
0x18000213f  jz      loc_1800022AB
0x180002145  cmp     byte ptr [rcx+19h], 2
0x180002149  jb      loc_1800022AB
0x18000214f  mov     edx, 0Bh
0x180002154  jmp     loc_180002297
0x180002159  call    ?CreateInstance@CSnapinThreadTable@@SAJPEAPEAV1@@Z; CSnapinThreadTable::CreateInstance(CSnapinThreadTable * *)
0x18000215e  mov     ebx, eax
0x180002160  test    eax, eax
0x180002162  jns     short loc_18000218F
0x180002164  lea     rax, WPP_GLOBAL_Control
0x18000216b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002172  cmp     rcx, rax
0x180002175  jz      loc_1800022AB
0x18000217b  cmp     byte ptr [rcx+19h], 2
0x18000217f  jb      loc_1800022AB
0x180002185  mov     edx, 0Ch
0x18000218a  jmp     loc_180002297
0x18000218f  lea     r8, [rbp+57h+arg_0]; int *
0x180002193  lea     rdx, ?s_unknownSnapin@BookKeeping@@0VSnapinRecord@@A; struct SnapinRecord *
0x18000219a  call    ?AddSnapin@SnapinOwnerTable@@QEAAJPEAVSnapinRecord@@AEAH@Z; SnapinOwnerTable::AddSnapin(SnapinRecord *,int &)
0x18000219f  mov     ebx, eax
0x1800021a1  test    eax, eax
0x1800021a3  jns     short loc_1800021D0
0x1800021a5  lea     rax, WPP_GLOBAL_Control
0x1800021ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021b3  cmp     rcx, rax
0x1800021b6  jz      loc_1800022AB
0x1800021bc  cmp     byte ptr [rcx+19h], 2
0x1800021c0  jb      loc_1800022AB
0x1800021c6  mov     edx, 0Dh
0x1800021cb  jmp     loc_180002297
0x1800021d0  lea     r8, [rbp+57h+arg_0]; int *
0x1800021d4  lea     rdx, ?s_dummySnapin@BookKeeping@@0VSnapinRecord@@A; struct SnapinRecord *
0x1800021db  call    ?AddSnapin@SnapinOwnerTable@@QEAAJPEAVSnapinRecord@@AEAH@Z; SnapinOwnerTable::AddSnapin(SnapinRecord *,int &)
0x1800021e0  mov     ebx, eax
0x1800021e2  test    eax, eax
0x1800021e4  jns     short loc_180002211
0x1800021e6  lea     rax, WPP_GLOBAL_Control
0x1800021ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021f4  cmp     rcx, rax
0x1800021f7  jz      loc_1800022AB
0x1800021fd  cmp     byte ptr [rcx+19h], 2
0x180002201  jb      loc_1800022AB
0x180002207  mov     edx, 0Eh
0x18000220c  jmp     loc_180002297
0x180002211  mov     edx, 0B0h; unsigned __int64
0x180002216  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x18000221b  mov     rbx, rax
0x18000221e  mov     [rbp+57h+arg_0], rax
0x180002222  test    rax, rax
0x180002225  jz      short loc_180002234
0x180002227  movaps  xmm2, xmm6
0x18000222a  mov     rcx, rax
0x18000222d  call    ??0?$CTypedHashTable@VItemHandleTable@@VItemHandle@@PEAXVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA@PEBDNKK_N1PEAVCLKRhashAllocator@@@Z; LKRhash::CTypedHashTable<ItemHandleTable,ItemHandle,void *,LKRhash::CLKRLinearHashTable>::CTypedHashTable<ItemHandleTable,ItemHandle,void *,LKRhash::CLKRLinearHashTable>(char const *,double,ulong,ulong,bool,bool,CLKRhashAllocator *)
0x180002232  jmp     short loc_180002236
0x180002234  xor     ebx, ebx
0x180002236  mov     cs:?s_pItemHandleTable@BookKeeping@@0PEAVItemHandleTable@@EA, rbx; ItemHandleTable * BookKeeping::s_pItemHandleTable
0x18000223d  test    rbx, rbx
0x180002240  jnz     short loc_180002267
0x180002242  mov     ebx, 8007000Eh
0x180002247  lea     rax, WPP_GLOBAL_Control
0x18000224e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002255  cmp     rcx, rax
0x180002258  jz      short loc_1800022AB
0x18000225a  cmp     byte ptr [rcx+19h], 2
0x18000225e  jb      short loc_1800022AB
0x180002260  mov     edx, 0Fh
0x180002265  jmp     short loc_180002297
0x180002267  mov     rcx, cs:?s_hInst@SC@mmcerror@@0PEAUHINSTANCE__@@EA; hModule
0x18000226e  call    ?LoadResources@ResourceCache@@SAJPEAUHINSTANCE__@@@Z; ResourceCache::LoadResources(HINSTANCE__ *)
0x180002273  mov     ebx, eax
0x180002275  test    eax, eax
0x180002277  jns     short loc_1800022AB
0x180002279  lea     rax, WPP_GLOBAL_Control
0x180002280  mov     rcx, cs:WPP_GLOBAL_Control
0x180002287  cmp     rcx, rax
0x18000228a  jz      short loc_1800022AB
0x18000228c  cmp     byte ptr [rcx+19h], 2
0x180002290  jb      short loc_1800022AB
0x180002292  mov     edx, 10h
0x180002297  mov     r9d, ebx
0x18000229a  lea     r8, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids
0x1800022a1  mov     rcx, [rcx+10h]
0x1800022a5  call    WPP_SF_d
0x1800022aa  nop
0x1800022ab  mov     [rbp+57h+var_30], rdi
0x1800022af  lea     rcx, [rbp+57h+var_30]; this
0x1800022b3  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x1800022b8  mov     eax, ebx
0x1800022ba  shr     eax, 1Fh
0x1800022bd  xor     al, 1
0x1800022bf  mov     cs:?s_fInitialized@BookKeeping@@0_NA, al; bool BookKeeping::s_fInitialized
0x1800022c5  xor     eax, eax
0x1800022c7  xchg    eax, cs:?s_initLock@BookKeeping@@0VCSmallSpinLock@@A; CSmallSpinLock BookKeeping::s_initLock
0x1800022cd  mov     eax, ebx
0x1800022cf  lea     r11, [rsp+90h+var_s0]
0x1800022d7  mov     rbx, [r11+18h]
0x1800022db  mov     rdi, [r11+20h]
0x1800022df  movaps  xmm6, xmmword ptr [r11-10h]
0x1800022e4  mov     rsp, r11
0x1800022e7  pop     rbp
0x1800022e8  retn
```
