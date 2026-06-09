# sqlencrypt::SymmetricKeyCache::InsertKey(std::basic_string<uchar,std::char_traits<uchar>,std::allocator<uchar>> const &,std::shared_ptr<sqlencrypt::SecureCek> const &,ulong)

- ea: `0x100481650`
- end: `0x10048183c`
- name: `?InsertKey@SymmetricKeyCache@sqlencrypt@@QEAA_NAEBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@AEBV?$shared_ptr@USecureCek@sqlencrypt@@@4@K@Z`
- size: `492`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10047cc4c`
- `0x10047ddb8`

## callees

- `0x10040128c`
- `0x10044b8d8`
- `0x1004801e4`
- `0x1004805e8`
- `0x100480b0c`
- `0x100480c80`
- `0x100480ee8`
- `0x100481650`
- `0x1004819cc`
- `0x10054803b`
- `0x100548047`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1004816d0`
- `KERNEL32!CreateThread` at `0x1004816d0`
- `KERNEL32!SetEvent` at `0x1004817f6`
- `KERNEL32!SetEvent` at `0x1004817f6`
- `KERNEL32!GetLastError` at `0x1004816df`
- `KERNEL32!GetLastError` at `0x100481800`
- `KERNEL32!GetLastError` at `0x1004816df`
- `KERNEL32!GetLastError` at `0x100481800`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004817e0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004817e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall sqlencrypt::SymmetricKeyCache::InsertKey(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rdi
  __int64 v9; // rbx
  HANDLE Thread; // rax
  void *v11; // rax
  __int64 v12; // rsi
  __int64 perf_frequency_0; // rdi
  __int64 perf_counter_0; // rax
  void *v15; // rdx
  _BYTE v16[8]; // [rsp+38h] [rbp-29h] BYREF
  __int64 v17; // [rsp+40h] [rbp-21h]
  __int64 v18; // [rsp+48h] [rbp-19h]
  int v19; // [rsp+50h] [rbp-11h] BYREF
  char v20; // [rsp+58h] [rbp-9h]
  void *v21[2]; // [rsp+60h] [rbp-1h] BYREF
  __int128 v22; // [rsp+70h] [rbp+Fh]
  __int64 v23; // [rsp+80h] [rbp+1Fh] BYREF

  v18 = -2;
  v4 = a4;
  if ( !a4 )
    return 0;
  v9 = a1 + 64;
  v17 = a1 + 64;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 64) + 8LL))(a1 + 64);
  if ( !*(_BYTE *)(a1 + 57) )
  {
    Thread = CreateThread(0, 0, sqlencrypt::SymmetricKeyCache::Evict, (LPVOID)a1, 0, 0);
    *(_QWORD *)(a1 + 48) = Thread;
    if ( !Thread )
      GetLastError();
    *(_BYTE *)(a1 + 57) = 1;
  }
  v22 = 0;
  std::basic_string<unsigned char>::_Construct_lv_contents(v21, a2);
  std::shared_ptr<sqlencrypt::CipherInfoEntry>::shared_ptr<sqlencrypt::CipherInfoEntry>(&v23, a3);
  v11 = (void *)std::_Tree_comp_alloc<std::_Tmap_traits<std::basic_string<unsigned char>,std::shared_ptr<sqlencrypt::SecureCek>,std::less<std::basic_string<unsigned char>>,std::allocator<std::pair<std::basic_string<unsigned char> const,std::shared_ptr<sqlencrypt::SecureCek>>>,0>>::_Buynode<std::pair<std::basic_string<unsigned char>,std::shared_ptr<sqlencrypt::SecureCek>>>(
                  a1,
                  v21);
  std::_Tree<std::_Tmap_traits<std::basic_string<unsigned char>,std::shared_ptr<sqlencrypt::SecureCek>,std::less<std::basic_string<unsigned char>>,std::allocator<std::pair<std::basic_string<unsigned char> const,std::shared_ptr<sqlencrypt::SecureCek>>>,0>>::_Insert_nohint<std::pair<std::basic_string<unsigned char> const,std::shared_ptr<sqlencrypt::SecureCek>> &,std::_Tree_node<std::pair<std::basic_string<unsigned char> const,std::shared_ptr<sqlencrypt::SecureCek>>,void *> *>(
    a1,
    (int)&v19,
    0,
    (_DWORD)v11 + 32,
    v11);
  std::pair<std::basic_string<unsigned char> const,std::shared_ptr<sqlencrypt::SecureCek>>::~pair<std::basic_string<unsigned char> const,std::shared_ptr<sqlencrypt::SecureCek>>(v21);
  if ( v20 )
  {
    v22 = 0;
    std::basic_string<unsigned char>::_Construct_lv_contents(v21, a2);
    v12 = v4;
    perf_frequency_0 = Query_perf_frequency_0();
    perf_counter_0 = Query_perf_counter_0();
    v23 = 1000000000 * (perf_counter_0 % perf_frequency_0) / perf_frequency_0
        + 1000000000 * (v12 + perf_counter_0 / perf_frequency_0);
    std::vector<sqlencrypt::SymmetricKeyCache::KeyExpiry>::emplace_back<sqlencrypt::SymmetricKeyCache::KeyExpiry>(
      a1 + 16,
      v21);
    std::_Push_heap_unchecked<sqlencrypt::SymmetricKeyCache::KeyExpiry *,std::less<sqlencrypt::SymmetricKeyCache::KeyExpiry>>(
      *(_QWORD *)(a1 + 16),
      *(_QWORD *)(a1 + 24),
      v16);
    if ( *((_QWORD *)&v22 + 1) >= 0x10u )
    {
      v15 = v21[0];
      if ( (unsigned __int64)(*((_QWORD *)&v22 + 1) + 1LL) >= 0x1000 )
      {
        if ( ((__int64)v21[0] & 0x1F) != 0
          || (v15 = (void *)*((_QWORD *)v21[0] - 1), v15 >= v21[0])
          || (unsigned __int64)((char *)v21[0] - (char *)v15 - 8) > 0x1F )
        {
          _invalid_parameter_noinfo_noreturn();
        }
      }
      operator delete(v15);
    }
  }
  if ( !SetEvent(*(HANDLE *)(a1 + 136)) )
    GetLastError();
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
  return 1;
}

```

## disassembly

```asm
0x100481650  mov     rax, rsp
0x100481653  push    rbp
0x100481654  push    rsi
0x100481655  push    rdi
0x100481656  push    r14
0x100481658  push    r15
0x10048165a  lea     rbp, [rax-5Fh]
0x10048165e  sub     rsp, 90h
0x100481665  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x10048166d  mov     [rax+20h], rbx
0x100481671  mov     rax, cs:__security_cookie
0x100481678  xor     rax, rsp
0x10048167b  mov     [rbp+57h+var_28], rax
0x10048167f  mov     edi, r9d
0x100481682  mov     r15, r8
0x100481685  mov     rsi, rdx
0x100481688  mov     r14, rcx
0x10048168b  test    r9d, r9d
0x10048168e  jnz     short loc_100481697
0x100481690  xor     al, al
0x100481692  jmp     loc_100481819
0x100481697  lea     rbx, [rcx+40h]
0x10048169b  mov     [rbp+57h+var_78], rbx
0x10048169f  mov     rax, [rbx]
0x1004816a2  mov     rcx, rbx
0x1004816a5  mov     rax, [rax+8]
0x1004816a9  call    cs:__guard_dispatch_icall_fptr
0x1004816af  nop
0x1004816b0  cmp     byte ptr [r14+39h], 0
0x1004816b5  jnz     short loc_1004816EA
0x1004816b7  and     qword ptr [rsp+28h], 0
0x1004816bd  and     dword ptr [rsp+0B0h+var_90], 0
0x1004816c2  mov     r9, r14; lpParameter
0x1004816c5  lea     r8, ?Evict@SymmetricKeyCache@sqlencrypt@@CAKPEAX@Z; lpStartAddress
0x1004816cc  xor     edx, edx; dwStackSize
0x1004816ce  xor     ecx, ecx; lpThreadAttributes
0x1004816d0  call    cs:__imp_CreateThread
0x1004816d6  mov     [r14+30h], rax
0x1004816da  test    rax, rax
0x1004816dd  jnz     short loc_1004816E5
0x1004816df  call    cs:__imp_GetLastError
0x1004816e5  mov     byte ptr [r14+39h], 1
0x1004816ea  xorps   xmm0, xmm0
0x1004816ed  movdqu  [rbp+57h+var_48], xmm0
0x1004816f2  mov     rdx, rsi
0x1004816f5  lea     rcx, [rbp+57h+var_58]
0x1004816f9  call    ?_Construct_lv_contents@?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@QEAAXAEBV12@@Z; std::basic_string<uchar>::_Construct_lv_contents(std::basic_string<uchar> const &)
0x1004816fe  mov     rdx, r15
0x100481701  lea     rcx, [rbp+57h+var_38]
0x100481705  call    ??0?$shared_ptr@UCipherInfoEntry@sqlencrypt@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<sqlencrypt::CipherInfoEntry>::shared_ptr<sqlencrypt::CipherInfoEntry>(std::shared_ptr<sqlencrypt::CipherInfoEntry> const &)
0x10048170a  nop
0x10048170b  lea     rdx, [rbp+57h+var_58]
0x10048170f  mov     rcx, r14
0x100481712  call    ??$_Buynode@U?$pair@V?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@@?$_Tree_comp_alloc@V?$_Tmap_traits@V?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@U?$less@V?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@@2@$0A@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@PEAX@1@$$QEAU?$pair@V?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@1@@Z; std::_Tree_comp_alloc<std::_Tmap_traits<std::basic_string<uchar>,std::shared_ptr<sqlencrypt::SecureCek>,std::less<std::basic_string<uchar>>,std::allocator<std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>>>,0>>::_Buynode<std::pair<std::basic_string<uchar>,std::shared_ptr<sqlencrypt::SecureCek>>>(std::pair<std::basic_string<uchar>,std::shared_ptr<sqlencrypt::SecureCek>> &&)
0x100481717  lea     r9, [rax+20h]; int
0x10048171b  mov     [rsp+0B0h+var_90], rax; void *
0x100481720  xor     r8d, r8d; int
0x100481723  lea     rdx, [rbp+57h+var_68]; int
0x100481727  mov     rcx, r14; int
0x10048172a  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@U?$less@V?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<uchar>,std::shared_ptr<sqlencrypt::SecureCek>,std::less<std::basic_string<uchar>>,std::allocator<std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>>>,0>>::_Insert_nohint<std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>> &,std::_Tree_node<std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>>,void *> *>(bool,std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>> &,std::_Tree_node<std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>>,void *> *)
0x10048172f  nop
0x100481730  lea     rcx, [rbp+57h+var_58]
0x100481734  call    ??1?$pair@$$CBV?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@V?$shared_ptr@USecureCek@sqlencrypt@@@2@@std@@QEAA@XZ; std::pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>>::~pair<std::basic_string<uchar> const,std::shared_ptr<sqlencrypt::SecureCek>>(void)
0x100481739  cmp     [rbp+57h+var_60], 0
0x10048173d  jz      loc_1004817EF
0x100481743  xorps   xmm0, xmm0
0x100481746  movdqu  [rbp+57h+var_48], xmm0
0x10048174b  mov     rdx, rsi
0x10048174e  lea     rcx, [rbp+57h+var_58]
0x100481752  call    ?_Construct_lv_contents@?$basic_string@EU?$char_traits@E@std@@V?$allocator@E@2@@std@@QEAAXAEBV12@@Z; std::basic_string<uchar>::_Construct_lv_contents(std::basic_string<uchar> const &)
0x100481757  mov     rsi, rdi
0x10048175a  call    _Query_perf_frequency_0
0x10048175f  mov     rdi, rax
0x100481762  call    _Query_perf_counter_0
0x100481767  cqo
0x100481769  idiv    rdi
0x10048176c  lea     rcx, [rsi+rax]
0x100481770  imul    rax, rdx, 3B9ACA00h
0x100481777  cqo
0x100481779  idiv    rdi
0x10048177c  imul    rdx, rcx, 3B9ACA00h
0x100481783  add     rdx, rax
0x100481786  mov     [rbp+57h+var_38], rdx
0x10048178a  lea     rdx, [rbp+57h+var_58]
0x10048178e  lea     rcx, [r14+10h]
0x100481792  call    ??$emplace_back@UKeyExpiry@SymmetricKeyCache@sqlencrypt@@@?$vector@UKeyExpiry@SymmetricKeyCache@sqlencrypt@@V?$allocator@UKeyExpiry@SymmetricKeyCache@sqlencrypt@@@std@@@std@@QEAA?A_T$$QEAUKeyExpiry@SymmetricKeyCache@sqlencrypt@@@Z
0x100481797  lea     r8, [rbp+57h+var_80]
0x10048179b  mov     rdx, [r14+18h]
0x10048179f  mov     rcx, [r14+10h]
0x1004817a3  call    ??$_Push_heap_unchecked@PEAUKeyExpiry@SymmetricKeyCache@sqlencrypt@@U?$less@UKeyExpiry@SymmetricKeyCache@sqlencrypt@@@std@@@std@@YAXPEAUKeyExpiry@SymmetricKeyCache@sqlencrypt@@0AEAU?$less@UKeyExpiry@SymmetricKeyCache@sqlencrypt@@@0@@Z; std::_Push_heap_unchecked<sqlencrypt::SymmetricKeyCache::KeyExpiry *,std::less<sqlencrypt::SymmetricKeyCache::KeyExpiry>>(sqlencrypt::SymmetricKeyCache::KeyExpiry *,sqlencrypt::SymmetricKeyCache::KeyExpiry *,std::less<sqlencrypt::SymmetricKeyCache::KeyExpiry> &)
0x1004817a8  nop
0x1004817a9  mov     rax, qword ptr [rbp+57h+var_48+8]
0x1004817ad  cmp     rax, 10h
0x1004817b1  jb      short loc_1004817EF
0x1004817b3  inc     rax
0x1004817b6  mov     rdx, [rbp+57h+var_58]
0x1004817ba  mov     rcx, rdx
0x1004817bd  cmp     rax, 1000h
0x1004817c3  jb      short loc_1004817E7
0x1004817c5  test    cl, 1Fh
0x1004817c8  jnz     short loc_1004817E0
0x1004817ca  mov     rdx, [rdx-8]
0x1004817ce  cmp     rdx, rcx
0x1004817d1  jnb     short loc_1004817E0
0x1004817d3  sub     rcx, rdx
0x1004817d6  sub     rcx, 8
0x1004817da  cmp     rcx, 1Fh
0x1004817de  jbe     short loc_1004817E7
0x1004817e0  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1004817e7  mov     rcx, rdx; void *
0x1004817ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1004817ef  mov     rcx, [r14+88h]; hEvent
0x1004817f6  call    cs:__imp_SetEvent
0x1004817fc  test    eax, eax
0x1004817fe  jnz     short loc_100481807
0x100481800  call    cs:__imp_GetLastError
0x100481806  nop
0x100481807  mov     rcx, [rbx]
0x10048180a  mov     rax, [rcx+18h]
0x10048180e  mov     rcx, rbx
0x100481811  call    cs:__guard_dispatch_icall_fptr
0x100481817  mov     al, 1
0x100481819  mov     rcx, [rbp+57h+var_28]
0x10048181d  xor     rcx, rsp; StackCookie
0x100481820  call    __security_check_cookie
0x100481825  mov     rbx, [rsp+0B0h+arg_18]
0x10048182d  add     rsp, 90h
0x100481834  pop     r15
0x100481836  pop     r14
0x100481838  pop     rdi
0x100481839  pop     rsi
0x10048183a  pop     rbp
0x10048183b  retn
```
