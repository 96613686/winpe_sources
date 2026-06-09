# RefCountMap<ushort *>::Increment(ushort *)

- ea: `0x18003e410`
- end: `0x18003e510`
- name: `?Increment@?$RefCountMap@PEAG@@QEAAJPEAG@Z`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003e400`

## callees

- `0x18000da6c`
- `0x18002387c`
- `0x18003e410`
- `0x18003e518`
- `0x18003e5e0`
- `0x180043bb4`
- `0x18009901c`
- `0x1800992c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e485`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e485`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003e4e5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003e501`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003e4e5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003e501`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RefCountMap<unsigned short *>::Increment(__int64 a1, __int64 a2)
{
  bool v2; // al
  union _RTL_RUN_ONCE *v3; // rbx
  __int64 v4; // rax
  __int64 result; // rax
  void *v6; // rax
  __int64 v7; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-28h] BYREF
  char v9; // [rsp+28h] [rbp-20h]
  _BYTE v10[24]; // [rsp+30h] [rbp-18h] BYREF
  LPINIT_ONCE lpInitOnce; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF
  void *v13; // [rsp+60h] [rbp+18h]

  v12 = a2;
  lpInitOnce = 0;
  v2 = InitOnceHolder::BeginInitialize((InitOnceHolder *)&lpInitOnce, &stru_1800C3368);
  try
  {
    if ( v2 )
    {
      v6 = operator new(0x10u);
      v7 = (__int64)v6;
      v13 = v6;
      if ( v6 )
      {
        std::_Compressed_pair<std::less<unsigned short *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<unsigned short * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,int>>>,1>,1>::_Compressed_pair<std::less<unsigned short *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<unsigned short * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,int>>>,1>,1>(v6);
        std::_Tree<std::_Tmap_traits<unsigned short *,int,std::less<unsigned short *>,throwingAllocator<std::pair<unsigned short * const,int>>,0>>::_Alloc_sentinel_and_proxy();
      }
      qword_1800C3360 = v7;
      if ( !v7 )
      {
        InitOnceHolder::~InitOnceHolder((InitOnceHolder *)&lpInitOnce);
        return 2147942414LL;
      }
      InitOnceComplete(lpInitOnce, 0, 0);
      v3 = 0;
      lpInitOnce = 0;
    }
    else
    {
      v3 = lpInitOnce;
    }
    lpCriticalSection = (LPCRITICAL_SECTION)BstrRefCounts;
    v9 = 0;
    ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
    v4 = std::map<unsigned short *,int,std::less<unsigned short *>,throwingAllocator<std::pair<unsigned short * const,int>>>::_Try_emplace<unsigned short * const &,>(
           qword_1800C3360,
           v10,
           &v12);
    ++*(_DWORD *)(*(_QWORD *)v4 + 40LL);
    if ( v9 )
      LeaveCriticalSection(lpCriticalSection);
    if ( v3 )
      InitOnceComplete(v3, 4u, 0);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18003e410  mov     rax, rsp
0x18003e413  mov     [rax+10h], rdx
0x18003e417  mov     [rax+8], rcx
0x18003e41b  push    rbx
0x18003e41c  sub     rsp, 40h
0x18003e420  mov     qword ptr [rax+8], 0
0x18003e428  lea     rdx, stru_1800C3368; union _RTL_RUN_ONCE *
0x18003e42f  lea     rcx, [rax+8]; this
0x18003e433  call    ?BeginInitialize@InitOnceHolder@@QEAA_NPEAT_RTL_RUN_ONCE@@@Z; InitOnceHolder::BeginInitialize(_RTL_RUN_ONCE *)
0x18003e438  test    al, al
0x18003e43a  jnz     short loc_18003E499
0x18003e43c  mov     rbx, [rsp+48h+lpInitOnce]
0x18003e441  lea     rax, ?BstrRefCounts@@3V?$RefCountMap@PEAG@@A; RefCountMap<ushort *> BstrRefCounts
0x18003e448  mov     [rsp+48h+lpCriticalSection], rax
0x18003e44d  mov     [rsp+48h+var_20], 0
0x18003e452  lea     rcx, [rsp+48h+lpCriticalSection]; this
0x18003e457  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x18003e45c  nop
0x18003e45d  lea     r8, [rsp+48h+arg_8]
0x18003e462  lea     rdx, [rsp+48h+var_18]
0x18003e467  mov     rcx, cs:qword_1800C3360
0x18003e46e  call    ??$_Try_emplace@AEBQEAG$$V@?$map@PEAGHU?$less@PEAG@std@@V?$throwingAllocator@U?$pair@QEAGH@std@@@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAGH@std@@PEAX@std@@_N@1@AEBQEAG@Z; std::map<ushort *,int,std::less<ushort *>,throwingAllocator<std::pair<ushort * const,int>>>::_Try_emplace<ushort * const &,>(ushort * const &)
0x18003e473  mov     rax, [rax]
0x18003e476  inc     dword ptr [rax+28h]
0x18003e479  cmp     [rsp+48h+var_20], 0
0x18003e47e  jz      short loc_18003E48C
0x18003e480  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x18003e485  call    cs:__imp_LeaveCriticalSection
0x18003e48b  nop
0x18003e48c  test    rbx, rbx
0x18003e48f  jnz     short loc_18003E4F7
0x18003e491  xor     eax, eax
0x18003e493  add     rsp, 40h
0x18003e497  pop     rbx
0x18003e498  retn
0x18003e499  mov     ecx, 10h; unsigned __int64
0x18003e49e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e4a3  mov     rbx, rax
0x18003e4a6  mov     [rsp+48h+arg_10], rax
0x18003e4ab  test    rbx, rbx
0x18003e4ae  jz      short loc_18003E4BE
0x18003e4b0  mov     rcx, rax
0x18003e4b3  call    ??$?0AEBU?$less@PEAG@std@@U_Zero_then_variadic_args_t@1@@?$_Compressed_pair@U?$less@PEAG@std@@V?$_Compressed_pair@V?$throwingAllocator@U?$_Tree_node@U?$pair@QEAGH@std@@PEAX@std@@@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGH@std@@@std@@@std@@$00@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@AEBU?$less@PEAG@1@$$QEAU_Zero_then_variadic_args_t@1@@Z; std::_Compressed_pair<std::less<ushort *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<ushort * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,int>>>,1>,1>::_Compressed_pair<std::less<ushort *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<ushort * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,int>>>,1>,1>(std::_One_then_variadic_args_t,std::less<ushort *> const &,std::_Zero_then_variadic_args_t &&)
0x18003e4b8  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEAGHU?$less@PEAG@std@@V?$throwingAllocator@U?$pair@QEAGH@std@@@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ushort *,int,std::less<ushort *>,throwingAllocator<std::pair<ushort * const,int>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18003e4bd  nop
0x18003e4be  mov     cs:qword_1800C3360, rbx
0x18003e4c5  test    rbx, rbx
0x18003e4c8  jnz     short loc_18003E4DB
0x18003e4ca  lea     rcx, [rsp+48h+lpInitOnce]; this
0x18003e4cf  call    ??1InitOnceHolder@@QEAA@XZ; InitOnceHolder::~InitOnceHolder(void)
0x18003e4d4  mov     eax, 8007000Eh
0x18003e4d9  jmp     short loc_18003E493
0x18003e4db  xor     r8d, r8d; lpContext
0x18003e4de  xor     edx, edx; dwFlags
0x18003e4e0  mov     rcx, [rsp+48h+lpInitOnce]; lpInitOnce
0x18003e4e5  call    cs:__imp_InitOnceComplete
0x18003e4eb  xor     ebx, ebx
0x18003e4ed  mov     [rsp+48h+lpInitOnce], rbx
0x18003e4f2  jmp     loc_18003E441
0x18003e4f7  xor     r8d, r8d; lpContext
0x18003e4fa  lea     edx, [r8+4]; dwFlags
0x18003e4fe  mov     rcx, rbx; lpInitOnce
0x18003e501  call    cs:__imp_InitOnceComplete
0x18003e507  jmp     short loc_18003E491
0x18003e509  mov     eax, 8007000Eh
0x18003e50e  jmp     short loc_18003E493
```
