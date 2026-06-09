# CThrottledTelemetryLogger::OnEvent(ThrottledEventData const &)

- ea: `0x1800b8b64`
- end: `0x1800b8f5e`
- name: `?OnEvent@CThrottledTelemetryLogger@@QEAAXAEBUThrottledEventData@@@Z`
- size: `1018`
- prototype: `void __fastcall(CThrottledTelemetryLogger *__hidden this, const struct ThrottledEventData *)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x1800b14c4`
- `0x1800b1dd0`

## callees

- `0x1800095a0`
- `0x18000f014`
- `0x18001ec40`
- `0x18001ee94`
- `0x18001ffd4`
- `0x180049d80`
- `0x1800a91e0`
- `0x1800a93e4`
- `0x1800b8b64`
- `0x1800b9e14`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`
- `0x180108ed0`
- `0x180109290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8f2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8f2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8ba6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8ba6`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800b8cd4`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800b8f04`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800b8cd4`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800b8f04`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800b8d2d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800b8eb9`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800b8d2d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800b8eb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CThrottledTelemetryLogger::OnEvent(RTL_SRWLOCK *this, const struct ThrottledEventData *a2)
{
  RTL_SRWLOCK *v4; // r12
  __int64 v5; // rcx
  RTL_SRWLOCK v6; // r15
  __int64 v7; // rbx
  __int64 Ptr; // rdi
  __int64 *v9; // rax
  RTL_SRWLOCK *v10; // rdi
  struct _TP_TIMER *v11; // rcx
  unsigned __int64 v12; // rbx
  _QWORD *v13; // rbx
  signed __int64 v14; // rbx
  __m128i v15; // xmm1
  __int64 v16; // rdx
  __int64 *v17; // rax
  __int64 v18; // rcx
  void (__fastcall ***v19)(_QWORD, __int64); // r8
  __int64 v20; // rax
  _QWORD *v21; // rax
  unsigned __int64 v22; // rax
  unsigned __int64 *v23; // rdx
  struct _TP_TIMER *v24; // rcx
  __int128 v25; // [rsp+20h] [rbp-99h] BYREF
  _QWORD v26[5]; // [rsp+30h] [rbp-89h] BYREF
  __int128 v27; // [rsp+58h] [rbp-61h]
  _QWORD v28[2]; // [rsp+70h] [rbp-49h] BYREF
  __int128 v29; // [rsp+80h] [rbp-39h]
  __m128i v30; // [rsp+90h] [rbp-29h]
  _QWORD *v31; // [rsp+A8h] [rbp-11h]
  __int128 v32; // [rsp+B0h] [rbp-9h] BYREF
  __m128i si128; // [rsp+C0h] [rbp+7h]

  v4 = this + 2;
  v27 = (unsigned __int64)&this[2];
  AcquireSRWLockExclusive(this + 2);
  BYTE8(v27) = 1;
  (*(void (__fastcall **)(const struct ThrottledEventData *, __int128 *))(*(_QWORD *)a2 + 8LL))(a2, &v32);
  v6.Ptr = this->Ptr;
  v7 = *((_QWORD *)this->Ptr + 1);
  *(_OWORD *)v26 = (unsigned __int64)v7;
  Ptr = (__int64)v6.Ptr;
  while ( !*(_BYTE *)(v7 + 25) )
  {
    v26[0] = v7;
    LOBYTE(v5) = std::less<std::string>::operator()(v5, v7 + 32, &v32);
    if ( (_BYTE)v5 )
    {
      LODWORD(v26[1]) = 0;
    }
    else
    {
      LODWORD(v26[1]) = 1;
      Ptr = v7;
    }
    v9 = (__int64 *)(v7 + 16);
    if ( !(_BYTE)v5 )
      v9 = (__int64 *)v7;
    v7 = *v9;
  }
  if ( *(_BYTE *)(Ptr + 25) || (unsigned __int8)std::less<std::string>::operator()(v5, &v32, Ptr + 32) )
  {
    if ( this[1].Ptr == (PVOID)0x186186186186186LL )
      std::_Throw_tree_length_error();
    *(_QWORD *)&v25 = this;
    v10 = (RTL_SRWLOCK *)operator new(0xA8u);
    std::string::string(&v10[4], &v32);
    memset(&v10[8], 0, 0x68u);
    v10->Ptr = v6.Ptr;
    v10[1].Ptr = v6.Ptr;
    v10[2].Ptr = v6.Ptr;
    LOWORD(v10[3].Ptr) = 0;
    *((_QWORD *)&v25 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,CThrottledTelemetryLogger::EventInfo>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,CThrottledTelemetryLogger::EventInfo>,void *>>>(&v25);
    v25 = *(_OWORD *)v26;
    Ptr = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<CSwarmConn>>>>::_Insert_node(
            this,
            &v25,
            v10);
  }
  v11 = *(struct _TP_TIMER **)(Ptr + 152);
  if ( v11 && IsThreadpoolTimerSet(v11) )
  {
    (*(void (__fastcall **)(_QWORD, const struct ThrottledEventData *))(**(_QWORD **)(Ptr + 160) + 56LL))(
      *(_QWORD *)(Ptr + 160),
      a2);
  }
  else
  {
    v12 = (__int64)(*(_QWORD *)(Ptr + 72) - *(_QWORD *)(Ptr + 64)) >> 3;
    if ( v12 >= (*(unsigned int (__fastcall **)(const struct ThrottledEventData *))(*(_QWORD *)a2 + 16LL))(a2) )
    {
      v13 = *(_QWORD **)(Ptr + 64);
      *(_QWORD *)&v25 = 0;
      GetSystemTimePreciseAsFileTime(&v25);
      v14 = (unsigned int)v25 + ((unsigned __int64)DWORD1(v25) << 32) - *v13 - 116444736000000000LL;
      if ( v14 >= 10000LL
                * *(_QWORD *)(*(__int64 (__fastcall **)(const struct ThrottledEventData *, __int128 *))(*(_QWORD *)a2 + 24LL))(
                               a2,
                               &v25) )
      {
        memmove(
          *(void **)(Ptr + 64),
          (const void *)(*(_QWORD *)(Ptr + 64) + 8LL),
          *(_QWORD *)(Ptr + 72) - (*(_QWORD *)(Ptr + 64) + 8LL));
        *(_QWORD *)(Ptr + 72) -= 8LL;
      }
      else
      {
        if ( !*(_QWORD *)(Ptr + 152) )
        {
          v26[0] = this;
          *(_OWORD *)&v26[1] = v32;
          v15 = si128;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOBYTE(v32) = 0;
          v28[0] = std::X$$V::Z::_Func_impl_no_alloc<`CThrottledTelemetryLogger::OnEvent'::`15'::_lambda_1_,AXAEBUThrottledEventData * const>::`vftable';
          v28[1] = this;
          v29 = *(_OWORD *)&v26[1];
          v30 = v15;
          *(__m128i *)&v26[3] = si128;
          LOBYTE(v26[1]) = 0;
          v31 = v28;
          CTpTimer::Create((_QWORD *)(Ptr + 88), v28);
          if ( v31 )
          {
            LOBYTE(v16) = v31 != v28;
            (*(void (__fastcall **)(_QWORD *, __int64))(*v31 + 32LL))(v31, v16);
            v31 = 0;
          }
          std::string::~string(&v26[1]);
        }
        v17 = (__int64 *)(*(__int64 (__fastcall **)(const struct ThrottledEventData *, __int128 *))(*(_QWORD *)a2 + 40LL))(
                           a2,
                           &v25);
        v18 = *v17;
        *v17 = 0;
        v19 = *(void (__fastcall ****)(_QWORD, __int64))(Ptr + 160);
        *(_QWORD *)(Ptr + 160) = v18;
        if ( v19 )
          (**v19)(v19, 1);
        if ( (_QWORD)v25 )
          (**(void (__fastcall ***)(_QWORD, __int64))v25)(v25, 1);
        *(_BYTE *)(*(_QWORD *)(Ptr + 160) + 12LL) = 1;
        v20 = *(_QWORD *)(Ptr + 64);
        if ( v20 != *(_QWORD *)(Ptr + 72) )
          *(_QWORD *)(Ptr + 72) = v20;
        v21 = (_QWORD *)(*(__int64 (__fastcall **)(const struct ThrottledEventData *, __int128 *))(*(_QWORD *)a2 + 32LL))(
                          a2,
                          &v25);
        CTpTimer::_Set(Ptr + 88, *v21);
      }
    }
  }
  *(_QWORD *)&v25 = 0;
  GetSystemTimePreciseAsFileTime(&v25);
  v22 = (unsigned int)v25 + ((unsigned __int64)DWORD1(v25) << 32) - 116444736000000000LL;
  *(_QWORD *)&v25 = v22;
  v23 = *(unsigned __int64 **)(Ptr + 72);
  if ( v23 == *(unsigned __int64 **)(Ptr + 80) )
  {
    std::vector<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::_Emplace_reallocate<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
      Ptr + 64,
      v23,
      &v25);
  }
  else
  {
    *v23 = v22;
    *(_QWORD *)(Ptr + 72) += 8LL;
  }
  v24 = *(struct _TP_TIMER **)(Ptr + 152);
  if ( !v24 || !IsThreadpoolTimerSet(v24) )
    (*(void (__fastcall **)(const struct ThrottledEventData *))(*(_QWORD *)a2 + 48LL))(a2);
  std::string::~string(&v32);
  ReleaseSRWLockExclusive(v4);
}

```

## disassembly

```asm
0x1800b8b64  mov     [rsp-8+arg_10], rbx
0x1800b8b69  push    rbp
0x1800b8b6a  push    rsi
0x1800b8b6b  push    rdi
0x1800b8b6c  push    r12
0x1800b8b6e  push    r13
0x1800b8b70  push    r14
0x1800b8b72  push    r15
0x1800b8b74  lea     rbp, [rsp-27h]
0x1800b8b79  sub     rsp, 0E0h
0x1800b8b80  mov     rax, cs:__security_cookie
0x1800b8b87  xor     rax, rsp
0x1800b8b8a  mov     [rbp+57h+var_40], rax
0x1800b8b8e  mov     rsi, rdx
0x1800b8b91  mov     r14, rcx
0x1800b8b94  xorps   xmm0, xmm0
0x1800b8b97  movups  [rbp+57h+var_B8], xmm0
0x1800b8b9b  lea     r12, [rcx+10h]
0x1800b8b9f  mov     qword ptr [rbp+57h+var_B8], r12
0x1800b8ba3  mov     rcx, r12; SRWLock
0x1800b8ba6  call    cs:__imp_AcquireSRWLockExclusive
0x1800b8bac  mov     byte ptr [rbp+57h+var_B8+8], 1
0x1800b8bb0  mov     rax, [rsi]
0x1800b8bb3  lea     rdx, [rbp+57h+var_60]
0x1800b8bb7  mov     rcx, rsi
0x1800b8bba  mov     rax, [rax+8]
0x1800b8bbe  call    _guard_dispatch_icall
0x1800b8bc3  nop
0x1800b8bc4  mov     r15, [r14]
0x1800b8bc7  mov     rbx, [r15+8]
0x1800b8bcb  mov     qword ptr [rsp+110h+var_E0], rbx
0x1800b8bd0  xor     r13d, r13d
0x1800b8bd3  mov     qword ptr [rsp+110h+var_E0+8], r13
0x1800b8bd8  mov     rdi, r15
0x1800b8bdb  jmp     short loc_1800B8C14
0x1800b8bdd  mov     qword ptr [rsp+110h+var_E0], rbx
0x1800b8be2  lea     rdx, [rbx+20h]
0x1800b8be6  lea     r8, [rbp+57h+var_60]
0x1800b8bea  call    ??R?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEBA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@0@Z; std::less<std::string>::operator()(std::string const &,std::string const &)
0x1800b8bef  mov     cl, al
0x1800b8bf1  test    al, al
0x1800b8bf3  jz      short loc_1800B8BFC
0x1800b8bf5  mov     dword ptr [rsp+110h+var_E0+8], r13d
0x1800b8bfa  jmp     short loc_1800B8C07
0x1800b8bfc  mov     dword ptr [rsp+110h+var_E0+8], 1
0x1800b8c04  mov     rdi, rbx
0x1800b8c07  lea     rax, [rbx+10h]
0x1800b8c0b  test    cl, cl
0x1800b8c0d  cmovz   rax, rbx
0x1800b8c11  mov     rbx, [rax]
0x1800b8c14  cmp     [rbx+19h], r13b
0x1800b8c18  jz      short loc_1800B8BDD
0x1800b8c1a  cmp     [rdi+19h], r13b
0x1800b8c1e  jnz     short loc_1800B8C35
0x1800b8c20  lea     r8, [rdi+20h]
0x1800b8c24  lea     rdx, [rbp+57h+var_60]
0x1800b8c28  call    ??R?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEBA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@0@Z; std::less<std::string>::operator()(std::string const &,std::string const &)
0x1800b8c2d  test    al, al
0x1800b8c2f  jz      loc_1800B8CBE
0x1800b8c35  mov     rax, 186186186186186h
0x1800b8c3f  cmp     [r14+8], rax
0x1800b8c43  jz      loc_1800B8F58
0x1800b8c49  mov     qword ptr [rsp+110h+var_F0], r14
0x1800b8c4e  mov     qword ptr [rsp+110h+var_F0+8], r13
0x1800b8c53  mov     ecx, 0A8h; Size
0x1800b8c58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b8c5d  mov     rdi, rax
0x1800b8c60  mov     qword ptr [rsp+110h+var_F0+8], rax
0x1800b8c65  lea     rdx, [rbp+57h+var_60]
0x1800b8c69  lea     rcx, [rax+20h]
0x1800b8c6d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800b8c72  lea     rcx, [rdi+40h]; void *
0x1800b8c76  xor     edx, edx; Val
0x1800b8c78  lea     r8d, [rdx+68h]; Size
0x1800b8c7c  call    memset
0x1800b8c81  mov     [rdi], r15
0x1800b8c84  mov     [rdi+8], r15
0x1800b8c88  mov     [rdi+10h], r15
0x1800b8c8c  mov     [rdi+18h], r13w
0x1800b8c91  mov     qword ptr [rsp+110h+var_F0+8], r13
0x1800b8c96  lea     rcx, [rsp+110h+var_F0]
0x1800b8c9b  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEventInfo@CThrottledTelemetryLogger@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,CThrottledTelemetryLogger::EventInfo>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,CThrottledTelemetryLogger::EventInfo>,void *>>>(void)
0x1800b8ca0  movups  xmm0, xmmword ptr [rsp+110h+var_E0]
0x1800b8ca5  movdqu  [rsp+110h+var_F0], xmm0
0x1800b8cab  mov     r8, rdi
0x1800b8cae  lea     rdx, [rsp+110h+var_F0]
0x1800b8cb3  mov     rcx, r14
0x1800b8cb6  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VCSwarmConn@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VCSwarmConn@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VCSwarmConn@@@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<CSwarmConn>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::shared_ptr<CSwarmConn>>,void *> *>,std::_Tree_node<std::pair<std::string const,std::shared_ptr<CSwarmConn>>,void *> * const)
0x1800b8cbb  mov     rdi, rax
0x1800b8cbe  mov     rcx, [rdi+98h]; pti
0x1800b8cc5  mov     r15, 0FE624E212AC18000h
0x1800b8ccf  test    rcx, rcx
0x1800b8cd2  jz      short loc_1800B8CF9
0x1800b8cd4  call    cs:__imp_IsThreadpoolTimerSet
0x1800b8cda  test    eax, eax
0x1800b8cdc  jz      short loc_1800B8CF9
0x1800b8cde  mov     rcx, [rdi+0A0h]
0x1800b8ce5  mov     rax, [rcx]
0x1800b8ce8  mov     rdx, rsi
0x1800b8ceb  mov     rax, [rax+38h]
0x1800b8cef  call    _guard_dispatch_icall
0x1800b8cf4  jmp     loc_1800B8EAF
0x1800b8cf9  mov     rbx, [rdi+48h]
0x1800b8cfd  sub     rbx, [rdi+40h]
0x1800b8d01  sar     rbx, 3
0x1800b8d05  mov     rax, [rsi]
0x1800b8d08  mov     rcx, rsi
0x1800b8d0b  mov     rax, [rax+10h]
0x1800b8d0f  call    _guard_dispatch_icall
0x1800b8d14  mov     eax, eax
0x1800b8d16  cmp     rbx, rax
0x1800b8d19  jb      loc_1800B8EAF
0x1800b8d1f  mov     rbx, [rdi+40h]
0x1800b8d23  mov     qword ptr [rsp+110h+var_F0], r13
0x1800b8d28  lea     rcx, [rsp+110h+var_F0]
0x1800b8d2d  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800b8d33  mov     eax, dword ptr [rsp+110h+var_F0+4]
0x1800b8d37  shl     rax, 20h
0x1800b8d3b  sub     rax, [rbx]
0x1800b8d3e  mov     ecx, dword ptr [rsp+110h+var_F0]
0x1800b8d42  lea     rbx, [r15+rax]
0x1800b8d46  add     rbx, rcx
0x1800b8d49  mov     rax, [rsi]
0x1800b8d4c  lea     rdx, [rsp+110h+var_F0]
0x1800b8d51  mov     rcx, rsi
0x1800b8d54  mov     rax, [rax+18h]
0x1800b8d58  call    _guard_dispatch_icall
0x1800b8d5d  imul    rcx, [rax], 2710h
0x1800b8d64  cmp     rbx, rcx
0x1800b8d67  jge     loc_1800B8E96
0x1800b8d6d  cmp     [rdi+98h], r13
0x1800b8d74  jnz     loc_1800B8E01
0x1800b8d7a  lea     rcx, [rdi+58h]; pv
0x1800b8d7e  mov     qword ptr [rsp+110h+var_E0], r14
0x1800b8d83  movups  xmm2, [rbp+57h+var_60]
0x1800b8d87  movups  xmmword ptr [rsp+110h+var_E0+8], xmm2
0x1800b8d8c  movups  xmm1, [rbp+57h+var_50]
0x1800b8d90  movdqa  xmm3, cs:__xmm@000000000000000f0000000000000000
0x1800b8d98  movdqu  [rbp+57h+var_50], xmm3
0x1800b8d9d  mov     byte ptr [rbp+57h+var_60], r13b
0x1800b8da1  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?P@??OnEvent@CThrottledTelemetryLogger@@QEAAXAEBUThrottledEventData@@@Z@X$$V@std@@6B@; const std::_Func_impl_no_alloc<`CThrottledTelemetryLogger::OnEvent(ThrottledEventData const &)'::`15'::_lambda_1_,void,>::`vftable'
0x1800b8da8  mov     [rbp+57h+var_A0], rax
0x1800b8dac  mov     [rbp+57h+var_98], r14
0x1800b8db0  movaps  [rbp+57h+var_90], xmm2
0x1800b8db4  movaps  [rbp+57h+var_80], xmm1
0x1800b8db8  movdqu  [rbp+57h+var_C8], xmm3
0x1800b8dbd  mov     [rsp+110h+var_E0+8], r13b
0x1800b8dc2  lea     rax, [rbp+57h+var_A0]
0x1800b8dc6  mov     [rbp+57h+var_68], rax
0x1800b8dca  lea     rdx, [rbp+57h+var_A0]
0x1800b8dce  call    ?Create@CTpTimer@@QEAAX$$QEAV?$function@$$A6AXXZ@std@@@Z; CTpTimer::Create(std::function<void (void)> &&)
0x1800b8dd3  nop
0x1800b8dd4  mov     rcx, [rbp+57h+var_68]
0x1800b8dd8  test    rcx, rcx
0x1800b8ddb  jz      short loc_1800B8DF7
0x1800b8ddd  lea     rax, [rbp+57h+var_A0]
0x1800b8de1  cmp     rcx, rax
0x1800b8de4  setnz   dl
0x1800b8de7  mov     rax, [rcx]
0x1800b8dea  mov     rax, [rax+20h]
0x1800b8dee  call    _guard_dispatch_icall
0x1800b8df3  mov     [rbp+57h+var_68], r13
0x1800b8df7  lea     rcx, [rsp+110h+var_E0+8]; void *
0x1800b8dfc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800b8e01  mov     rax, [rsi]
0x1800b8e04  lea     rdx, [rsp+110h+var_F0]
0x1800b8e09  mov     rcx, rsi
0x1800b8e0c  mov     rax, [rax+28h]
0x1800b8e10  call    _guard_dispatch_icall
0x1800b8e15  mov     rcx, [rax]
0x1800b8e18  mov     [rax], r13
0x1800b8e1b  mov     r8, [rdi+0A0h]
0x1800b8e22  mov     [rdi+0A0h], rcx
0x1800b8e29  test    r8, r8
0x1800b8e2c  jz      short loc_1800B8E41
0x1800b8e2e  mov     rax, [r8]
0x1800b8e31  mov     edx, 1
0x1800b8e36  mov     rcx, r8
0x1800b8e39  mov     rax, [rax]
0x1800b8e3c  call    _guard_dispatch_icall
0x1800b8e41  mov     rcx, qword ptr [rsp+110h+var_F0]
0x1800b8e46  test    rcx, rcx
0x1800b8e49  jz      short loc_1800B8E5B
0x1800b8e4b  mov     rax, [rcx]
0x1800b8e4e  mov     edx, 1
0x1800b8e53  mov     rax, [rax]
0x1800b8e56  call    _guard_dispatch_icall
0x1800b8e5b  mov     rax, [rdi+0A0h]
0x1800b8e62  mov     byte ptr [rax+0Ch], 1
0x1800b8e66  mov     rax, [rdi+40h]
0x1800b8e6a  cmp     rax, [rdi+48h]
0x1800b8e6e  jz      short loc_1800B8E74
0x1800b8e70  mov     [rdi+48h], rax
0x1800b8e74  mov     rax, [rsi]
0x1800b8e77  lea     rdx, [rsp+110h+var_F0]
0x1800b8e7c  mov     rcx, rsi
0x1800b8e7f  mov     rax, [rax+20h]
0x1800b8e83  call    _guard_dispatch_icall
0x1800b8e88  lea     rcx, [rdi+58h]
0x1800b8e8c  mov     rdx, [rax]
0x1800b8e8f  call    ?_Set@CTpTimer@@AEAAXV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z; CTpTimer::_Set(std::chrono::duration<__int64,std::ratio<1,1000>>)
0x1800b8e94  jmp     short loc_1800B8EAF
0x1800b8e96  mov     rcx, [rdi+40h]; void *
0x1800b8e9a  lea     rdx, [rcx+8]; Src
0x1800b8e9e  mov     r8, [rdi+48h]
0x1800b8ea2  sub     r8, rdx; Size
0x1800b8ea5  call    memmove
0x1800b8eaa  add     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFF8h
0x1800b8eaf  mov     qword ptr [rsp+110h+var_F0], r13
0x1800b8eb4  lea     rcx, [rsp+110h+var_F0]
0x1800b8eb9  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800b8ebf  mov     eax, dword ptr [rsp+110h+var_F0+4]
0x1800b8ec3  shl     rax, 20h
0x1800b8ec7  mov     ecx, dword ptr [rsp+110h+var_F0]
0x1800b8ecb  add     rax, r15
0x1800b8ece  add     rax, rcx
0x1800b8ed1  mov     qword ptr [rsp+110h+var_F0], rax
0x1800b8ed6  mov     rdx, [rdi+48h]
0x1800b8eda  cmp     rdx, [rdi+50h]
0x1800b8ede  jz      short loc_1800B8EEA
0x1800b8ee0  mov     [rdx], rax
0x1800b8ee3  add     qword ptr [rdi+48h], 8
0x1800b8ee8  jmp     short loc_1800B8EF8
0x1800b8eea  lea     r8, [rsp+110h+var_F0]
0x1800b8eef  lea     rcx, [rdi+40h]
0x1800b8ef3  call    ??$_Emplace_reallocate@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@?$vector@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@V?$allocator@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@3@@std@@AEAAPEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@1@QEAV231@$$QEAV231@@Z; std::vector<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::_Emplace_reallocate<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> * const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> &&)
0x1800b8ef8  mov     rcx, [rdi+98h]; pti
0x1800b8eff  test    rcx, rcx
0x1800b8f02  jz      short loc_1800B8F0E
0x1800b8f04  call    cs:__imp_IsThreadpoolTimerSet
0x1800b8f0a  test    eax, eax
0x1800b8f0c  jnz     short loc_1800B8F1E
0x1800b8f0e  mov     rax, [rsi]
0x1800b8f11  mov     rcx, rsi
0x1800b8f14  mov     rax, [rax+30h]
0x1800b8f18  call    _guard_dispatch_icall
0x1800b8f1d  nop
0x1800b8f1e  lea     rcx, [rbp+57h+var_60]; void *
0x1800b8f22  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800b8f27  nop
0x1800b8f28  mov     rcx, r12; SRWLock
0x1800b8f2b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8f31  mov     rcx, [rbp+57h+var_40]
0x1800b8f35  xor     rcx, rsp; StackCookie
0x1800b8f38  call    __security_check_cookie
0x1800b8f3d  mov     rbx, [rsp+110h+arg_10]
0x1800b8f45  add     rsp, 0E0h
0x1800b8f4c  pop     r15
0x1800b8f4e  pop     r14
0x1800b8f50  pop     r13
0x1800b8f52  pop     r12
0x1800b8f54  pop     rdi
0x1800b8f55  pop     rsi
0x1800b8f56  pop     rbp
0x1800b8f57  retn
0x1800b8f58  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
