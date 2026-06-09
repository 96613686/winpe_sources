# CompressedStreamDump::GetNumaNodeRelationship(std::vector<_NUMA_NODE_RELATIONSHIP,std::allocator<_NUMA_NODE_RELATIONSHIP>> &)

- ea: `0x180028284`
- end: `0x180028456`
- name: `?GetNumaNodeRelationship@CompressedStreamDump@@YAJAEAV?$vector@U_NUMA_NODE_RELATIONSHIP@@V?$allocator@U_NUMA_NODE_RELATIONSHIP@@@std@@@std@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001e8f0`

## callees

- `0x180001710`
- `0x180001b1c`
- `0x1800021f4`
- `0x18001d290`
- `0x18001f10c`
- `0x180027ee4`
- `0x18002803c`
- `0x180028284`
- `0x1800289b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002840a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002840a`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x1800282c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x18002838a`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x1800282c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x18002838a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CompressedStreamDump::GetNumaNodeRelationship(__int64 a1)
{
  DWORD v2; // eax
  unsigned int v3; // edi
  size_t v4; // rdi
  void *v5; // rax
  KAFFINITY v6; // rcx
  struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *v7; // rax
  struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *v8; // rbx
  __int64 i; // rbx
  PSYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX v10; // r14
  __m128d v11; // xmm2
  __int64 v12; // rdx
  DWORD LastError; // eax
  DWORD ReturnedLength; // [rsp+20h] [rbp-39h] BYREF
  PSYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX Buffer[2]; // [rsp+28h] [rbp-31h] BYREF
  char *v17; // [rsp+38h] [rbp-21h]
  _QWORD v18[2]; // [rsp+40h] [rbp-19h] BYREF
  __int128 v19; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v20[24]; // [rsp+60h] [rbp+7h]

  v18[1] = -2;
  ReturnedLength = 0;
  if ( GetLogicalProcessorInformationEx(RelationNumaNode, 0, &ReturnedLength) || GetLastError() == 122 )
  {
    v4 = ReturnedLength;
    *(_OWORD *)Buffer = 0;
    v17 = 0;
    if ( ReturnedLength )
    {
      if ( ReturnedLength < 0x1000uLL )
      {
        v7 = (struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *)operator new(ReturnedLength);
      }
      else
      {
        if ( (unsigned __int64)ReturnedLength + 39 < ReturnedLength )
          __scrt_throw_std_bad_array_new_length();
        v5 = operator new(ReturnedLength + 39LL);
        v6 = (KAFFINITY)v5;
        if ( !v5 )
          __fastfail(5u);
        v7 = (struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *)(((unsigned __int64)v5 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        v7[-1].Group.GroupInfo[0].ActiveProcessorMask = v6;
      }
      Buffer[0] = v7;
      v8 = (struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *)((char *)v7 + v4);
      v17 = (char *)v7 + v4;
      memset_0(v7, 0, v4);
      Buffer[1] = v8;
      v18[0] = 0;
      std::_Tidy_guard<std::vector<char>>::~_Tidy_guard<std::vector<char>>(v18);
    }
    if ( GetLogicalProcessorInformationEx(RelationNumaNode, Buffer[0], &ReturnedLength) )
    {
      v3 = 0;
      for ( i = 0; (unsigned int)i < ReturnedLength; i = (unsigned int)(*(ULONG *)((char *)&v10->Size + i) + i) )
      {
        v10 = Buffer[0];
        if ( *(KAFFINITY *)((char *)&Buffer[0]->Processor.GroupMask[0].Mask + i) )
        {
          v19 = 0;
          *(_OWORD *)v20 = 0;
          LODWORD(v19) = *(ULONG *)((char *)&Buffer[0]->NumaNode.NodeNumber + i);
          v11 = *(__m128d *)(&Buffer[0]->Group.GroupInfo[0].MaximumProcessorCount + i);
          *(__m128d *)&v20[8] = v11;
          v12 = *(_QWORD *)(a1 + 8);
          if ( v12 == *(_QWORD *)(a1 + 16) )
          {
            std::vector<_NUMA_NODE_RELATIONSHIP>::_Emplace_reallocate<_NUMA_NODE_RELATIONSHIP const &>(a1, v12, &v19);
          }
          else
          {
            *(_OWORD *)v12 = v19;
            *(_OWORD *)(v12 + 16) = *(_OWORD *)v20;
            *(_QWORD *)(v12 + 32) = *(_OWORD *)&_mm_unpackhi_pd(v11, v11);
            *(_QWORD *)(a1 + 8) += 40LL;
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      CompressedStreamDump::LogMessage(
        (CompressedStreamDump *)4,
        "GetLogicalProcessorInformationEx failed with error %u",
        (const char *)LastError);
      v3 = -2147467259;
    }
    std::vector<char>::~vector<char>(Buffer);
  }
  else
  {
    v2 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      "GetLogicalProcessorInformationEx-1 failed with error %u",
      (const char *)v2);
    return (unsigned int)-2147418113;
  }
  return v3;
}

```

## disassembly

```asm
0x180028284  push    rbp
0x180028286  push    rbx
0x180028287  push    rsi
0x180028288  push    rdi
0x180028289  push    r14
0x18002828b  push    r15
0x18002828d  lea     rbp, [rsp-2Fh]
0x180028292  sub     rsp, 88h
0x180028299  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x1800282a1  mov     rax, cs:__security_cookie
0x1800282a8  xor     rax, rsp
0x1800282ab  mov     [rbp+57h+var_38], rax
0x1800282af  mov     r15, rcx
0x1800282b2  mov     [rbp+57h+ReturnedLength], 0
0x1800282b9  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x1800282bd  xor     edx, edx; Buffer
0x1800282bf  lea     esi, [rdx+1]
0x1800282c2  mov     ecx, esi; RelationshipType
0x1800282c4  call    cs:__imp_GetLogicalProcessorInformationEx
0x1800282ca  test    eax, eax
0x1800282cc  jnz     short loc_1800282FB
0x1800282ce  call    cs:__imp_GetLastError
0x1800282d4  cmp     eax, 7Ah ; 'z'
0x1800282d7  jz      short loc_1800282FB
0x1800282d9  call    cs:__imp_GetLastError
0x1800282df  mov     r8d, eax; char *
0x1800282e2  lea     rdx, aGetlogicalproc_0; "GetLogicalProcessorInformationEx-1 fail"...
0x1800282e9  lea     ecx, [rsi+3]; this
0x1800282ec  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x1800282f1  mov     edi, 8000FFFFh
0x1800282f6  jmp     loc_180028432
0x1800282fb  mov     edi, [rbp+57h+ReturnedLength]
0x1800282fe  xorps   xmm0, xmm0
0x180028301  movdqu  xmmword ptr [rbp+57h+Buffer], xmm0
0x180028306  mov     [rbp+57h+var_78], 0
0x18002830e  test    rdi, rdi
0x180028311  jz      short loc_180028380
0x180028313  cmp     rdi, 1000h
0x18002831a  jb      short loc_180028349
0x18002831c  lea     rcx, [rdi+27h]; Size
0x180028320  cmp     rcx, rdi
0x180028323  jbe     loc_180028450
0x180028329  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002832e  mov     rcx, rax
0x180028331  test    rax, rax
0x180028334  jnz     short loc_18002833B
0x180028336  lea     ecx, [rax+5]
0x180028339  int     29h; Win8: RtlFailFast(ecx)
0x18002833b  add     rax, 27h ; '''
0x18002833f  and     rax, 0FFFFFFFFFFFFFFE0h
0x180028343  mov     [rax-8], rcx
0x180028347  jmp     short loc_180028351
0x180028349  mov     rcx, rdi; Size
0x18002834c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028351  mov     [rbp+57h+Buffer], rax
0x180028355  lea     rbx, [rdi+rax]
0x180028359  mov     [rbp+57h+var_78], rbx
0x18002835d  mov     r8, rdi; Size
0x180028360  xor     edx, edx; Val
0x180028362  mov     rcx, rax; void *
0x180028365  call    memset_0
0x18002836a  mov     [rbp+57h+Buffer+8], rbx
0x18002836e  mov     [rbp+57h+var_70], 0
0x180028376  lea     rcx, [rbp+57h+var_70]
0x18002837a  call    ??1?$_Tidy_guard@V?$vector@DV?$allocator@D@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<char>>::~_Tidy_guard<std::vector<char>>(void)
0x18002837f  nop
0x180028380  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x180028384  mov     rdx, [rbp+57h+Buffer]; Buffer
0x180028388  mov     ecx, esi; RelationshipType
0x18002838a  call    cs:__imp_GetLogicalProcessorInformationEx
0x180028390  test    eax, eax
0x180028392  jz      short loc_18002840A
0x180028394  xor     edi, edi
0x180028396  xor     ebx, ebx
0x180028398  cmp     [rbp+57h+ReturnedLength], ebx
0x18002839b  jbe     loc_180028429
0x1800283a1  mov     r14, [rbp+57h+Buffer]
0x1800283a5  cmp     [rbx+r14+20h], rdi
0x1800283aa  jz      short loc_1800283FE
0x1800283ac  xorps   xmm0, xmm0
0x1800283af  movups  [rbp+57h+var_60], xmm0
0x1800283b3  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800283b7  mov     eax, [rbx+r14+8]
0x1800283bc  mov     dword ptr [rbp+57h+var_60], eax
0x1800283bf  movups  xmm2, xmmword ptr [rbx+r14+20h]
0x1800283c5  movups  xmmword ptr [rbp+57h+var_50+8], xmm2
0x1800283c9  mov     rdx, [r15+8]
0x1800283cd  cmp     rdx, [r15+10h]
0x1800283d1  jz      short loc_1800283F2
0x1800283d3  movups  xmm0, [rbp+57h+var_60]
0x1800283d7  movups  xmmword ptr [rdx], xmm0
0x1800283da  movups  xmm1, xmmword ptr [rbp+57h+var_50]
0x1800283de  movups  xmmword ptr [rdx+10h], xmm1
0x1800283e2  unpckhpd xmm2, xmm2
0x1800283e6  movsd   qword ptr [rdx+20h], xmm2
0x1800283eb  add     qword ptr [r15+8], 28h ; '('
0x1800283f0  jmp     short loc_1800283FE
0x1800283f2  lea     r8, [rbp+57h+var_60]
0x1800283f6  mov     rcx, r15
0x1800283f9  call    ??$_Emplace_reallocate@AEBU_NUMA_NODE_RELATIONSHIP@@@?$vector@U_NUMA_NODE_RELATIONSHIP@@V?$allocator@U_NUMA_NODE_RELATIONSHIP@@@std@@@std@@AEAAPEAU_NUMA_NODE_RELATIONSHIP@@QEAU2@AEBU2@@Z; std::vector<_NUMA_NODE_RELATIONSHIP>::_Emplace_reallocate<_NUMA_NODE_RELATIONSHIP const &>(_NUMA_NODE_RELATIONSHIP * const,_NUMA_NODE_RELATIONSHIP const &)
0x1800283fe  add     ebx, [rbx+r14+4]
0x180028403  cmp     ebx, [rbp+57h+ReturnedLength]
0x180028406  jb      short loc_1800283A1
0x180028408  jmp     short loc_180028429
0x18002840a  call    cs:__imp_GetLastError
0x180028410  mov     r8d, eax; char *
0x180028413  lea     rdx, aGetlogicalproc; "GetLogicalProcessorInformationEx failed"...
0x18002841a  mov     ecx, 4; this
0x18002841f  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180028424  mov     edi, 80004005h
0x180028429  lea     rcx, [rbp+57h+Buffer]
0x18002842d  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180028432  mov     eax, edi
0x180028434  mov     rcx, [rbp+57h+var_38]
0x180028438  xor     rcx, rsp; StackCookie
0x18002843b  call    __security_check_cookie
0x180028440  add     rsp, 88h
0x180028447  pop     r15
0x180028449  pop     r14
0x18002844b  pop     rdi
0x18002844c  pop     rsi
0x18002844d  pop     rbx
0x18002844e  pop     rbp
0x18002844f  retn
0x180028450  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
