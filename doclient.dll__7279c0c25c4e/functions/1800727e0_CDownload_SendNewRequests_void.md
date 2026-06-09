# CDownload::_SendNewRequests(void)

- ea: `0x1800727e0`
- end: `0x180072b1c`
- name: `?_SendNewRequests@CDownload@@IEAAXXZ`
- size: `828`
- prototype: `void __fastcall(CDownload *__hidden this)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180072b30`
- `0x18007baec`
- `0x18007c080`

## callees

- `0x180009528`
- `0x1800095a0`
- `0x18001eeac`
- `0x18005589c`
- `0x180071c08`
- `0x1800727e0`
- `0x180072c7c`
- `0x1800738d4`
- `0x180079018`
- `0x1800790b4`
- `0x1800a1ea4`
- `0x1800c0014`
- `0x1800f82f0`
- `0x1800f8314`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072adb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072adb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180072845`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180072ae9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180072845`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180072ae9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDownload::_SendNewRequests(CDownload *this)
{
  char v2; // bl
  HANDLE CurrentThread; // rax
  __int64 v4; // r15
  _QWORD *v5; // rax
  __int64 v6; // r14
  _QWORD *v7; // rcx
  _QWORD *v8; // rdi
  int v9; // ecx
  int v10; // r13d
  unsigned int DataRate; // eax
  unsigned int v12; // r14d
  __int64 v13; // rdi
  unsigned int v14; // ecx
  unsigned int v15; // edx
  __int64 *v16; // r8
  __int64 *v17; // rax
  __int64 *v18; // rcx
  _QWORD *v19; // r10
  __int64 v20; // rax
  _QWORD **v21; // rcx
  __int64 v22; // rdx
  _QWORD **v23; // rcx
  _QWORD *v24; // rcx
  _QWORD *v25; // rdi
  HANDLE v26; // rax
  __int64 v27; // [rsp+50h] [rbp-21h] BYREF
  _BYTE v28[8]; // [rsp+58h] [rbp-19h] BYREF
  __int64 v29; // [rsp+60h] [rbp-11h] BYREF
  int v30; // [rsp+6Ch] [rbp-5h]
  _BYTE v31[8]; // [rsp+80h] [rbp+Fh] BYREF
  void *Block[2]; // [rsp+88h] [rbp+17h] BYREF
  __int64 v33; // [rsp+98h] [rbp+27h] BYREF

  v2 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 112LL) + 8LL) + 352LL) + 644LL);
  if ( v2 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 0x10000);
  }
  v4 = *(_QWORD *)(*((_QWORD *)this + 10) + 120LL);
  Block[1] = 0;
  v5 = std::_Allocate<16,std::_Default_allocate_traits>(0x38u);
  *v5 = v5;
  v5[1] = v5;
  Block[0] = v5;
  v31[0] = 0;
  v6 = *(_QWORD *)(*((_QWORD *)this + 10) + 80LL);
  *(_QWORD *)v5[1] = 0;
  v7 = (_QWORD *)*v5;
  if ( *v5 )
  {
    do
    {
      v8 = (_QWORD *)*v7;
      operator delete(v7);
      v7 = v8;
    }
    while ( v8 );
  }
  *(_QWORD *)Block[0] = Block[0];
  *((void **)Block[0] + 1) = Block[0];
  v9 = 0;
  Block[1] = 0;
  if ( *(_QWORD *)(v4 + 16) )
  {
    (*(void (__fastcall **)(_QWORD, __int64, CDownload *, void **, __int64, _BYTE *))(**(_QWORD **)(v4 + 88) + 8LL))(
      *(_QWORD *)(v4 + 88),
      v4,
      this,
      Block,
      v6,
      v31);
    v9 = (int)Block[1];
  }
  if ( v31[0] )
  {
    CDownloader::RequestWakeUpOnUrgentPiece(*((CDownloader **)this + 10), this);
  }
  else
  {
    v10 = v9 + *((_DWORD *)this + 4);
    DataRate = CRateTracker::GetDataRate((CDownload *)((char *)this + 24));
    v12 = 7168;
    if ( DataRate > 0x1C00 )
      v12 = DataRate;
    std::chrono::steady_clock::now(&v27);
    while ( Block[1] )
    {
      v13 = *(_QWORD *)Block[0] + 16LL;
      if ( *(_QWORD *)CDownload::_FindRequest(this, v28, v13) == *((_QWORD *)this + 1) )
      {
        v14 = *((_DWORD *)this + 38);
        if ( v14 < *(_DWORD *)(v13 + 16) * v10 / v12 )
          v14 = *(_DWORD *)(v13 + 16) * v10 / v12;
        *(_QWORD *)(v13 + 24) = v27 + 1000000000LL * v14;
        std::list<CRequestBlock>::push_back((char *)this + 8, v13);
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 17) + 136LL))(*((_QWORD *)this + 17), v13);
        v15 = *(_DWORD *)v13;
        v16 = *(__int64 **)(v4 + 8);
        v17 = (__int64 *)v16[1];
        v30 = 0;
        v18 = v16;
        while ( !*((_BYTE *)v17 + 25) )
        {
          if ( *((_DWORD *)v17 + 8) >= v15 )
            v18 = v17;
          else
            v17 += 2;
          v17 = (__int64 *)*v17;
        }
        if ( !*((_BYTE *)v18 + 25) && v15 >= *((_DWORD *)v18 + 8) && v18 != v16 )
        {
          v33 = 0;
          std::_Tree<std::_Tmap_traits<CRequest,unsigned int,std::less<CRequest>,std::allocator<std::pair<CRequest const,unsigned int>>,0>>::find(
            v18 + 8,
            &v33,
            v13);
          if ( v33 == *v19 )
            *(_DWORD *)std::map<CRequest,unsigned int>::operator[](v19, v13) = 1;
          else
            ++*(_DWORD *)(v33 + 56);
        }
      }
      else
      {
        v20 = CRequest::Log(v13, &v29);
        if ( *(_QWORD *)(v20 + 24) > 0xFu )
          v20 = *(_QWORD *)v20;
        LogMessage(3u, "CDownload::_SendNewRequests", 0x83u, "Discarding duplicate request %s", (const char *)v20);
        std::string::~string(&v29);
      }
      v21 = *(_QWORD ***)Block[0];
      v22 = **(_QWORD **)Block[0];
      --Block[1];
      *v21[1] = v22;
      *(_QWORD *)(v22 + 8) = v21[1];
      operator delete(v21);
    }
  }
  v23 = (_QWORD **)Block[0];
  **((_QWORD **)Block[0] + 1) = 0;
  v24 = *v23;
  if ( v24 )
  {
    do
    {
      v25 = (_QWORD *)*v24;
      operator delete(v24);
      v24 = v25;
    }
    while ( v25 );
  }
  operator delete(Block[0]);
  if ( v2 )
  {
    v26 = GetCurrentThread();
    SetThreadPriority(v26, 0x20000);
  }
}

```

## disassembly

```asm
0x1800727e0  mov     rax, rsp
0x1800727e3  mov     [rax+10h], rbx
0x1800727e7  mov     [rax+18h], rsi
0x1800727eb  mov     [rax+20h], rdi
0x1800727ef  push    rbp
0x1800727f0  push    r12
0x1800727f2  push    r13
0x1800727f4  push    r14
0x1800727f6  push    r15
0x1800727f8  lea     rbp, [rax-5Fh]
0x1800727fc  sub     rsp, 0A0h
0x180072803  mov     rax, cs:__security_cookie
0x18007280a  xor     rax, rsp
0x18007280d  mov     [rbp+57h+var_28], rax
0x180072811  mov     rsi, rcx
0x180072814  mov     rax, [rcx+50h]
0x180072818  mov     rcx, [rax+70h]
0x18007281c  mov     rax, [rcx+8]
0x180072820  mov     rbx, [rax+160h]
0x180072827  mov     bl, [rbx+284h]
0x18007282d  mov     [rbp+57h+var_80], bl
0x180072830  xor     r12d, r12d
0x180072833  test    bl, bl
0x180072835  jz      short loc_18007284C
0x180072837  call    cs:__imp_GetCurrentThread
0x18007283d  mov     rcx, rax; hThread
0x180072840  mov     edx, 10000h; nPriority
0x180072845  call    cs:__imp_SetThreadPriority
0x18007284b  nop
0x18007284c  mov     rax, [rsi+50h]
0x180072850  mov     r15, [rax+78h]
0x180072854  xorps   xmm0, xmm0
0x180072857  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18007285b  mov     [rbp+57h+Block], r12
0x18007285f  mov     [rbp+57h+Block+8], r12
0x180072863  mov     r13d, 38h ; '8'
0x180072869  mov     ecx, r13d
0x18007286c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180072871  mov     [rax], rax
0x180072874  mov     [rax+8], rax
0x180072878  mov     [rbp+57h+Block], rax
0x18007287c  mov     [rbp+57h+var_48], r12b
0x180072880  mov     rcx, [rsi+50h]
0x180072884  mov     r14, [rcx+50h]
0x180072888  mov     rcx, [rax+8]
0x18007288c  mov     [rcx], r12
0x18007288f  mov     rcx, [rax]; Block
0x180072892  test    rcx, rcx
0x180072895  jz      short loc_1800728AA
0x180072897  mov     rdi, [rcx]
0x18007289a  mov     rdx, r13
0x18007289d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800728a2  mov     rcx, rdi
0x1800728a5  test    rdi, rdi
0x1800728a8  jnz     short loc_180072897
0x1800728aa  mov     rax, [rbp+57h+Block]
0x1800728ae  mov     [rax], rax
0x1800728b1  mov     rax, [rbp+57h+Block]
0x1800728b5  mov     [rax+8], rax
0x1800728b9  mov     rcx, r12
0x1800728bc  mov     [rbp+57h+Block+8], rcx
0x1800728c0  cmp     [r15+10h], r12
0x1800728c4  jz      short loc_1800728F2
0x1800728c6  mov     rcx, [r15+58h]
0x1800728ca  mov     rax, [rcx]
0x1800728cd  lea     rdx, [rbp+57h+var_48]
0x1800728d1  mov     [rsp+0C0h+var_98], rdx
0x1800728d6  mov     [rsp+0C0h+var_A0], r14
0x1800728db  lea     r9, [rbp+57h+Block]
0x1800728df  mov     r8, rsi
0x1800728e2  mov     rdx, r15
0x1800728e5  mov     rax, [rax+8]
0x1800728e9  call    _guard_dispatch_icall
0x1800728ee  mov     rcx, [rbp+57h+Block+8]
0x1800728f2  cmp     [rbp+57h+var_48], r12b
0x1800728f6  jz      short loc_180072909
0x1800728f8  mov     rdx, rsi; struct CDownload *
0x1800728fb  mov     rcx, [rsi+50h]; this
0x1800728ff  call    ?RequestWakeUpOnUrgentPiece@CDownloader@@QEAAXPEAVCDownload@@@Z; CDownloader::RequestWakeUpOnUrgentPiece(CDownload *)
0x180072904  jmp     loc_180072AA4
0x180072909  mov     r13d, [rsi+10h]
0x18007290d  add     r13d, ecx
0x180072910  lea     rcx, [rsi+18h]; this
0x180072914  call    ?GetDataRate@CRateTracker@@QEBA_KXZ; CRateTracker::GetDataRate(void)
0x180072919  mov     r14d, 1C00h
0x18007291f  cmp     eax, r14d
0x180072922  cmova   r14d, eax
0x180072926  lea     rcx, [rbp+57h+var_78]
0x18007292a  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18007292f  cmp     [rbp+57h+Block+8], r12
0x180072933  jz      loc_180072A9E
0x180072939  mov     rax, [rbp+57h+Block]
0x18007293d  mov     rdi, [rax]
0x180072940  add     rdi, 10h
0x180072944  mov     r8, rdi
0x180072947  lea     rdx, [rbp+57h+var_70]
0x18007294b  mov     rcx, rsi
0x18007294e  call    ?_FindRequest@CDownload@@IEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@VCRequestBlock@@@std@@@std@@@std@@AEBVCRequest@@@Z; CDownload::_FindRequest(CRequest const &)
0x180072953  mov     rcx, [rsi+8]
0x180072957  cmp     [rax], rcx
0x18007295a  jnz     loc_180072A28
0x180072960  mov     eax, r13d
0x180072963  imul    eax, [rdi+10h]
0x180072967  xor     edx, edx
0x180072969  div     r14d
0x18007296c  mov     ecx, [rsi+98h]
0x180072972  cmp     ecx, eax
0x180072974  cmovb   ecx, eax
0x180072977  mov     eax, ecx
0x180072979  imul    rcx, rax, 3B9ACA00h
0x180072980  add     rcx, [rbp+57h+var_78]
0x180072984  mov     [rdi+18h], rcx
0x180072988  mov     rdx, rdi
0x18007298b  lea     rcx, [rsi+8]
0x18007298f  call    ?push_back@?$list@VCRequestBlock@@V?$allocator@VCRequestBlock@@@std@@@std@@QEAAXAEBVCRequestBlock@@@Z; std::list<CRequestBlock>::push_back(CRequestBlock const &)
0x180072994  mov     rcx, [rsi+88h]
0x18007299b  mov     rax, [rcx]
0x18007299e  mov     rdx, rdi
0x1800729a1  mov     rax, [rax+88h]
0x1800729a8  call    _guard_dispatch_icall
0x1800729ad  mov     edx, [rdi]
0x1800729af  mov     r8, [r15+8]
0x1800729b3  mov     rax, [r8+8]
0x1800729b7  xor     ecx, ecx
0x1800729b9  mov     [rbp+57h+var_5C], ecx
0x1800729bc  mov     rcx, r8
0x1800729bf  xor     r9d, r9d
0x1800729c2  jmp     short loc_1800729D5
0x1800729c4  cmp     [rax+20h], edx
0x1800729c7  jnb     short loc_1800729CF
0x1800729c9  add     rax, 10h
0x1800729cd  jmp     short loc_1800729D2
0x1800729cf  mov     rcx, rax
0x1800729d2  mov     rax, [rax]
0x1800729d5  cmp     [rax+19h], r9b
0x1800729d9  jz      short loc_1800729C4
0x1800729db  cmp     [rcx+19h], r9b
0x1800729df  jnz     loc_180072A69
0x1800729e5  cmp     edx, [rcx+20h]
0x1800729e8  jb      short loc_180072A69
0x1800729ea  cmp     rcx, r8
0x1800729ed  jz      short loc_180072A69
0x1800729ef  mov     [rbp+57h+var_30], r9
0x1800729f3  lea     r10, [rcx+40h]
0x1800729f7  mov     r8, rdi
0x1800729fa  lea     rdx, [rbp+57h+var_30]
0x1800729fe  mov     rcx, r10
0x180072a01  call    ?find@?$_Tree@V?$_Tmap_traits@VCRequest@@IU?$less@VCRequest@@@std@@V?$allocator@U?$pair@$$CBVCRequest@@I@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCRequest@@I@std@@@std@@@std@@@2@AEBVCRequest@@@Z; std::_Tree<std::_Tmap_traits<CRequest,uint,std::less<CRequest>,std::allocator<std::pair<CRequest const,uint>>,0>>::find(CRequest const &)
0x180072a06  mov     r8, [rbp+57h+var_30]
0x180072a0a  cmp     r8, [r10]
0x180072a0d  jz      short loc_180072A15
0x180072a0f  inc     dword ptr [r8+38h]
0x180072a13  jmp     short loc_180072A69
0x180072a15  mov     rdx, rdi
0x180072a18  mov     rcx, r10
0x180072a1b  call    ??A?$map@VCRequest@@IU?$less@VCRequest@@@std@@V?$allocator@U?$pair@$$CBVCRequest@@I@std@@@3@@std@@QEAAAEAIAEBVCRequest@@@Z; std::map<CRequest,uint>::operator[](CRequest const &)
0x180072a20  mov     dword ptr [rax], 1
0x180072a26  jmp     short loc_180072A69
0x180072a28  lea     rdx, [rbp+57h+var_68]
0x180072a2c  mov     rcx, rdi
0x180072a2f  call    ?Log@CRequest@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; CRequest::Log(void)
0x180072a34  cmp     qword ptr [rax+18h], 0Fh
0x180072a39  jbe     short loc_180072A3E
0x180072a3b  mov     rax, [rax]
0x180072a3e  mov     [rsp+0C0h+var_A0], rax
0x180072a43  lea     r9, aDiscardingDupl; "Discarding duplicate request %s"
0x180072a4a  mov     r8d, 83h; unsigned int
0x180072a50  lea     rdx, aCdownloadSendn; "CDownload::_SendNewRequests"
0x180072a57  lea     ecx, [r8-80h]; unsigned __int8
0x180072a5b  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180072a60  lea     rcx, [rbp+57h+var_68]; void *
0x180072a64  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180072a69  mov     rax, [rbp+57h+Block]
0x180072a6d  mov     rcx, [rax]; Block
0x180072a70  mov     rdx, [rcx]
0x180072a73  dec     [rbp+57h+Block+8]
0x180072a77  mov     rax, [rcx+8]
0x180072a7b  mov     [rax], rdx
0x180072a7e  mov     rax, [rcx+8]
0x180072a82  mov     [rdx+8], rax
0x180072a86  mov     edx, 38h ; '8'
0x180072a8b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180072a90  cmp     [rbp+57h+Block+8], 0
0x180072a95  jnz     loc_180072939
0x180072a9b  xor     r12d, r12d
0x180072a9e  mov     r13d, 38h ; '8'
0x180072aa4  mov     rcx, [rbp+57h+Block]
0x180072aa8  mov     rax, [rcx+8]
0x180072aac  mov     [rax], r12
0x180072aaf  mov     rcx, [rcx]; Block
0x180072ab2  test    rcx, rcx
0x180072ab5  jz      short loc_180072ACA
0x180072ab7  mov     rdi, [rcx]
0x180072aba  mov     rdx, r13
0x180072abd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180072ac2  mov     rcx, rdi
0x180072ac5  test    rdi, rdi
0x180072ac8  jnz     short loc_180072AB7
0x180072aca  mov     rdx, r13
0x180072acd  mov     rcx, [rbp+57h+Block]; Block
0x180072ad1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180072ad6  nop
0x180072ad7  test    bl, bl
0x180072ad9  jz      short loc_180072AEF
0x180072adb  call    cs:__imp_GetCurrentThread
0x180072ae1  mov     rcx, rax; hThread
0x180072ae4  mov     edx, 20000h; nPriority
0x180072ae9  call    cs:__imp_SetThreadPriority
0x180072aef  mov     rcx, [rbp+57h+var_28]
0x180072af3  xor     rcx, rsp; StackCookie
0x180072af6  call    __security_check_cookie
0x180072afb  lea     r11, [rsp+0C0h+var_20]
0x180072b03  mov     rbx, [r11+38h]
0x180072b07  mov     rsi, [r11+40h]
0x180072b0b  mov     rdi, [r11+48h]
0x180072b0f  mov     rsp, r11
0x180072b12  pop     r15
0x180072b14  pop     r14
0x180072b16  pop     r13
0x180072b18  pop     r12
0x180072b1a  pop     rbp
0x180072b1b  retn
```
