# CompressedStreamDump::CompressedMemStream::Init(void)

- ea: `0x18001e8f0`
- end: `0x18001ec75`
- name: `?Init@CompressedMemStream@CompressedStreamDump@@QEAA_NXZ`
- size: `901`
- prototype: `char __fastcall(CompressedStreamDump::CompressedMemStream *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d6f4`

## callees

- `0x180001ae0`
- `0x180001b1c`
- `0x180003430`
- `0x180004560`
- `0x18001d290`
- `0x18001d638`
- `0x18001e8f0`
- `0x18001efac`
- `0x180027938`
- `0x180028284`
- `0x18002845c`
- `0x18002849c`
- `0x1800289b8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001e923`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001e923`

## pseudocode

```c
char __fastcall CompressedStreamDump::CompressedMemStream::Init(CompressedStreamDump::CompressedMemStream *this)
{
  unsigned int *v2; // r9
  unsigned __int64 dwAllocationGranularity; // r8
  __int64 v4; // rcx
  const char *v5; // rdx
  unsigned int v7; // ebx
  unsigned int v8; // r8d
  unsigned int v9; // ecx
  __int64 v10; // r8
  unsigned int v11; // r8d
  unsigned int v12; // eax
  int v13; // ecx
  char *v14; // rbx
  __int64 v15; // rcx
  unsigned int v16; // r8d
  CompressedStreamDump::DumpWriter *v17; // r14
  __int64 v18; // r12
  __int64 v19; // r15
  void *v20; // rax
  _QWORD *v21; // rbx
  __int64 i; // rbx
  __int64 v23; // r8
  __int64 v24; // rdx
  const char *v25; // r8
  struct _SYSTEM_INFO v26; // [rsp+38h] [rbp-50h] BYREF
  char *v27; // [rsp+90h] [rbp+8h] BYREF
  int v28; // [rsp+98h] [rbp+10h] BYREF

  memset(&v26, 0, sizeof(v26));
  GetSystemInfo(&v26);
  LODWORD(v27) = 0;
  v28 = 0;
  if ( CompressedStreamDump::GetSectorSize(*((HANDLE *)this + 3), &v28, (unsigned int *)&v27, v2) )
  {
    dwAllocationGranularity = (unsigned int)v27;
    if ( (unsigned int)v27 > v26.dwAllocationGranularity )
    {
      CompressedStreamDump::LogMessage(
        (CompressedStreamDump *)4,
        (int)"Logical sector size is greater than system allocation granularity. Can't continue.\n",
        (const char *)(unsigned int)v27);
      return 0;
    }
    v4 = 1;
    v5 = "Sector size is: %u bytes.\n";
  }
  else
  {
    dwAllocationGranularity = v26.dwAllocationGranularity;
    v4 = 2;
    v5 = "Failed to get phyical sector size. Use system allocation granularity size: %u bytes.\n";
  }
  *((_DWORD *)this + 10) = dwAllocationGranularity;
  CompressedStreamDump::LogMessage((CompressedStreamDump *)v4, (int)v5, (const char *)dwAllocationGranularity);
  v7 = *((_DWORD *)this + 4);
  v9 = CompressedStreamDump::GetPaddingBytes((CompressedStreamDump *)v7, *((unsigned int *)this + 10), v8) + v7;
  v10 = 0x4000000;
  if ( v9 <= 0x4000000 )
  {
    v10 = v9;
    if ( v9 < 0x100000 )
      v10 = 0x100000;
  }
  *((_DWORD *)this + 4) = v10;
  *((_DWORD *)this + 38) = v10;
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)1,
    (int)"MaxTransferSize size is: %u bytes.\n",
    (const char *)v10);
  v12 = *((_DWORD *)this + 3);
  if ( !v12 )
  {
    v12 = 4;
LABEL_12:
    v13 = v12;
    goto LABEL_13;
  }
  v13 = 128;
  if ( v12 <= 0x80 )
    goto LABEL_12;
LABEL_13:
  *((_DWORD *)this + 3) = v13;
  *((_QWORD *)this + 14) = *((_QWORD *)this + 4)
                         + CompressedStreamDump::GetPaddingBytes(
                             *((CompressedStreamDump **)this + 4),
                             *((unsigned int *)this + 10),
                             v11);
  v14 = (char *)operator new(0x38u);
  v27 = v14;
  v15 = *((_QWORD *)this + 14);
  *(_QWORD *)v14 = this;
  *((_QWORD *)v14 + 2) = 0;
  *((_QWORD *)v14 + 3) = -1;
  *((_QWORD *)v14 + 4) = 0;
  *((_DWORD *)v14 + 10) = 0;
  *((_QWORD *)v14 + 6) = v15;
  CompressedStreamDump::DumpWriter::Init((CompressedStreamDump::DumpWriter *)v14);
  v17 = (CompressedStreamDump::DumpWriter *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = v14;
  if ( v17 )
  {
    CompressedStreamDump::DumpWriter::~DumpWriter(v17);
    operator delete(v17, 0x38u);
  }
  *((_QWORD *)this + 20) = *((_QWORD *)this + 14);
  *((_QWORD *)this + 26) = CompressedStreamDump::GetPaddingBytes(
                             (CompressedStreamDump *)*((unsigned int *)this + 30),
                             *((unsigned int *)this + 10),
                             v16)
                         + *((_QWORD *)this + 14)
                         + *((unsigned int *)this + 30);
  v27 = (char *)*((unsigned int *)this + 26);
  if ( (unsigned __int64)v27 > (__int64)(*((_QWORD *)this + 12) - *((_QWORD *)this + 10)) >> 5 )
    std::vector<MemoryRegion>::_Reallocate<0>((char *)this + 80, &v27);
  v18 = *((_QWORD *)this + 39);
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)this + 41) - v18) >> 3) < 0x2800 )
  {
    v19 = *((_QWORD *)this + 40);
    v20 = operator new(0x64027u);
    if ( !v20 )
      __fastfail(5u);
    v21 = (_QWORD *)(((unsigned __int64)v20 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v21 - 1) = v20;
    memmove_0(v21, *((const void **)this + 39), *((_QWORD *)this + 40) - *((_QWORD *)this + 39));
    std::vector<MemoryBucket>::_Change_array(
      (char *)this + 312,
      v21,
      0xCCCCCCCCCCCCCCCDuLL * ((v19 - v18) >> 3),
      10240,
      -2);
  }
  if ( *((_QWORD *)this + 7) && *((_DWORD *)this + 16) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 16); i = (unsigned int)(i + 1) )
    {
      v23 = *((_QWORD *)this + 7) + 40 * i;
      if ( *(_QWORD *)(v23 + 24) )
      {
        v24 = *((_QWORD *)this + 46);
        if ( v24 == *((_QWORD *)this + 47) )
        {
          std::vector<_NUMA_NODE_RELATIONSHIP>::_Emplace_reallocate<_NUMA_NODE_RELATIONSHIP const &>();
        }
        else
        {
          *(_OWORD *)v24 = *(_OWORD *)v23;
          *(_OWORD *)(v24 + 16) = *(_OWORD *)(v23 + 16);
          *(_QWORD *)(v24 + 32) = *(_QWORD *)(v23 + 32);
          *((_QWORD *)this + 46) += 40LL;
        }
      }
    }
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)1,
      (int)"Number of NUMA nodes provided: %zu\n",
      (const char *)(0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 46) - *((_QWORD *)this + 45)) >> 3)));
  }
  else
  {
    CompressedStreamDump::GetNumaNodeRelationship((char *)this + 360);
    v25 = (const char *)(0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 46) - *((_QWORD *)this + 45)) >> 3));
    if ( v25 )
      CompressedStreamDump::LogMessage((CompressedStreamDump *)1, (int)"Number of NUMA nodes detected: %zu\n", v25);
    else
      CompressedStreamDump::LogMessage(
        (CompressedStreamDump *)2,
        (int)"NumaNodeInfoArray is empty after GetNumaNodeRelationship.\n",
        0);
  }
  return 1;
}

```

## disassembly

```asm
0x18001e8f0  mov     rax, rsp
0x18001e8f3  push    r12
0x18001e8f5  push    r14
0x18001e8f7  push    r15
0x18001e8f9  sub     rsp, 70h
0x18001e8fd  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x18001e905  mov     [rax+18h], rbx
0x18001e909  mov     [rax+20h], rdi
0x18001e90d  mov     rdi, rcx
0x18001e910  xorps   xmm0, xmm0
0x18001e913  movups  xmmword ptr [rax-50h], xmm0
0x18001e917  movups  xmmword ptr [rax-40h], xmm0
0x18001e91b  movups  xmmword ptr [rax-30h], xmm0
0x18001e91f  lea     rcx, [rax-50h]; lpSystemInfo
0x18001e923  call    cs:__imp_GetSystemInfo
0x18001e929  mov     dword ptr [rsp+88h+arg_0], 0
0x18001e934  mov     [rsp+88h+arg_8], 0
0x18001e93f  lea     r8, [rsp+88h+arg_0]; unsigned int *
0x18001e947  lea     rdx, [rsp+88h+arg_8]; void *
0x18001e94f  mov     rcx, [rdi+18h]; hFile
0x18001e953  call    ?GetSectorSize@CompressedStreamDump@@YA_NPEAXPEAK1@Z; CompressedStreamDump::GetSectorSize(void *,ulong *,ulong *)
0x18001e958  test    al, al
0x18001e95a  jnz     short loc_18001E96F
0x18001e95c  mov     r8d, [rsp+88h+var_28]
0x18001e961  mov     ecx, 2
0x18001e966  lea     rdx, aFailedToGetPhy; "Failed to get phyical sector size. Use "...
0x18001e96d  jmp     short loc_18001E9A2
0x18001e96f  mov     r8d, dword ptr [rsp+88h+arg_0]; char *
0x18001e977  cmp     r8d, [rsp+88h+var_28]
0x18001e97c  jbe     short loc_18001E996
0x18001e97e  lea     rdx, aLogicalSectorS; "Logical sector size is greater than sys"...
0x18001e985  mov     ecx, 4; this
0x18001e98a  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001e98f  xor     al, al
0x18001e991  jmp     loc_18001EC5C
0x18001e996  mov     ecx, 1; this
0x18001e99b  lea     rdx, aSectorSizeIsUB; "Sector size is: %u bytes.\n"
0x18001e9a2  mov     r12d, 28h ; '('
0x18001e9a8  mov     r15, rdi
0x18001e9ab  mov     [rdi+r12], r8d
0x18001e9af  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001e9b4  mov     ebx, [rdi+10h]
0x18001e9b7  mov     ecx, ebx; this
0x18001e9b9  mov     edx, [rdi+r12]; unsigned __int64
0x18001e9bd  call    ?GetPaddingBytes@CompressedStreamDump@@YAI_KI@Z; CompressedStreamDump::GetPaddingBytes(unsigned __int64,uint)
0x18001e9c2  lea     ecx, [rax+rbx]
0x18001e9c5  mov     r8d, 4000000h
0x18001e9cb  cmp     ecx, r8d
0x18001e9ce  ja      short loc_18001E9DE
0x18001e9d0  mov     r8d, ecx
0x18001e9d3  mov     eax, 100000h
0x18001e9d8  cmp     ecx, eax
0x18001e9da  cmovb   r8d, eax; char *
0x18001e9de  mov     [rdi+10h], r8d
0x18001e9e2  mov     [rdi+98h], r8d
0x18001e9e9  lea     rdx, aMaxtransfersiz; "MaxTransferSize size is: %u bytes.\n"
0x18001e9f0  mov     ecx, 1; this
0x18001e9f5  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001e9fa  mov     eax, [rdi+0Ch]
0x18001e9fd  test    eax, eax
0x18001e9ff  jnz     short loc_18001EA08
0x18001ea01  mov     eax, 4
0x18001ea06  jmp     short loc_18001EA1B
0x18001ea08  mov     ecx, 80h
0x18001ea0d  cmp     eax, ecx
0x18001ea0f  ja      short loc_18001EA1D
0x18001ea11  cmp     eax, 1
0x18001ea14  mov     ecx, 1
0x18001ea19  jb      short loc_18001EA1D
0x18001ea1b  mov     ecx, eax
0x18001ea1d  mov     [rdi+0Ch], ecx
0x18001ea20  mov     edx, [r15+r12]; unsigned __int64
0x18001ea24  mov     rcx, [rdi+20h]; this
0x18001ea28  call    ?GetPaddingBytes@CompressedStreamDump@@YAI_KI@Z; CompressedStreamDump::GetPaddingBytes(unsigned __int64,uint)
0x18001ea2d  mov     ecx, eax
0x18001ea2f  add     rcx, [rdi+20h]
0x18001ea33  mov     [rdi+70h], rcx
0x18001ea37  mov     ecx, 38h ; '8'; Size
0x18001ea3c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ea41  mov     rbx, rax
0x18001ea44  mov     [rsp+88h+arg_0], rax
0x18001ea4c  mov     rcx, [rdi+70h]
0x18001ea50  mov     [rax], rdi
0x18001ea53  mov     qword ptr [rax+10h], 0
0x18001ea5b  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18001ea63  mov     qword ptr [rax+20h], 0
0x18001ea6b  mov     dword ptr [rax+28h], 0
0x18001ea72  mov     [rax+30h], rcx
0x18001ea76  mov     rcx, rax; this
0x18001ea79  call    ?Init@DumpWriter@CompressedStreamDump@@QEAAXXZ; CompressedStreamDump::DumpWriter::Init(void)
0x18001ea7e  nop
0x18001ea7f  mov     r14, [rdi+48h]
0x18001ea83  mov     [rdi+48h], rbx
0x18001ea87  test    r14, r14
0x18001ea8a  jz      short loc_18001EAA1
0x18001ea8c  mov     rcx, r14; this
0x18001ea8f  call    ??1DumpWriter@CompressedStreamDump@@QEAA@XZ; CompressedStreamDump::DumpWriter::~DumpWriter(void)
0x18001ea94  mov     edx, 38h ; '8'; unsigned __int64
0x18001ea99  mov     rcx, r14; void *
0x18001ea9c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eaa1  mov     rax, [rdi+70h]
0x18001eaa5  mov     [rdi+0A0h], rax
0x18001eaac  mov     ecx, [rdi+78h]; this
0x18001eaaf  mov     edx, [r15+r12]; unsigned __int64
0x18001eab3  call    ?GetPaddingBytes@CompressedStreamDump@@YAI_KI@Z; CompressedStreamDump::GetPaddingBytes(unsigned __int64,uint)
0x18001eab8  mov     eax, eax
0x18001eaba  mov     ecx, [rdi+78h]
0x18001eabd  add     rcx, [rdi+70h]
0x18001eac1  add     rcx, rax
0x18001eac4  mov     [rdi+0D0h], rcx
0x18001eacb  lea     rcx, [rdi+50h]
0x18001eacf  mov     edx, [rdi+68h]
0x18001ead2  mov     [rsp+88h+arg_0], rdx
0x18001eada  mov     rax, [rcx+10h]
0x18001eade  sub     rax, [rcx]
0x18001eae1  sar     rax, 5
0x18001eae5  cmp     rdx, rax
0x18001eae8  jbe     short loc_18001EAF7
0x18001eaea  lea     rdx, [rsp+88h+arg_0]
0x18001eaf2  call    ??$_Reallocate@$0A@@?$vector@UMemoryRegion@@V?$allocator@UMemoryRegion@@@std@@@std@@AEAAXAEA_K@Z; std::vector<MemoryRegion>::_Reallocate<0>(unsigned __int64 &)
0x18001eaf7  lea     r14, [rdi+138h]
0x18001eafe  mov     r12, [r14]
0x18001eb01  mov     rax, [r14+10h]
0x18001eb05  sub     rax, r12
0x18001eb08  sar     rax, 3
0x18001eb0c  mov     r15, 0CCCCCCCCCCCCCCCDh
0x18001eb16  imul    rax, r15
0x18001eb1a  cmp     rax, 2800h
0x18001eb20  jnb     short loc_18001EB88
0x18001eb22  mov     r15, [r14+8]
0x18001eb26  mov     ecx, 64027h; Size
0x18001eb2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001eb30  test    rax, rax
0x18001eb33  jnz     short loc_18001EB3A
0x18001eb35  lea     ecx, [rax+5]
0x18001eb38  int     29h; Win8: RtlFailFast(ecx)
0x18001eb3a  lea     rbx, [rax+27h]
0x18001eb3e  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001eb42  mov     [rbx-8], rax
0x18001eb46  mov     r8, [r14+8]
0x18001eb4a  sub     r8, [r14]; Size
0x18001eb4d  mov     rdx, [r14]; Src
0x18001eb50  mov     rcx, rbx; void *
0x18001eb53  call    memmove_0
0x18001eb58  sub     r15, r12
0x18001eb5b  sar     r15, 3
0x18001eb5f  mov     r8, 0CCCCCCCCCCCCCCCDh
0x18001eb69  imul    r8, r15
0x18001eb6d  mov     r9d, 2800h
0x18001eb73  mov     rdx, rbx
0x18001eb76  mov     rcx, r14
0x18001eb79  call    ?_Change_array@?$vector@UMemoryBucket@@V?$allocator@UMemoryBucket@@@std@@@std@@AEAAXQEAUMemoryBucket@@_K1@Z; std::vector<MemoryBucket>::_Change_array(MemoryBucket * const,unsigned __int64,unsigned __int64)
0x18001eb7e  mov     r15, 0CCCCCCCCCCCCCCCDh
0x18001eb88  cmp     qword ptr [rdi+38h], 0
0x18001eb8d  jz      short loc_18001EC0A
0x18001eb8f  cmp     dword ptr [rdi+40h], 0
0x18001eb93  jz      short loc_18001EC0A
0x18001eb95  xor     ebx, ebx
0x18001eb97  cmp     ebx, [rdi+40h]
0x18001eb9a  jnb     short loc_18001EBEB
0x18001eb9c  lea     rcx, [rbx+rbx*4]
0x18001eba0  mov     rax, [rdi+38h]
0x18001eba4  lea     r8, [rax+rcx*8]
0x18001eba8  cmp     qword ptr [r8+18h], 0
0x18001ebad  jz      short loc_18001EBE7
0x18001ebaf  lea     rcx, [rdi+168h]
0x18001ebb6  mov     rdx, [rcx+8]
0x18001ebba  cmp     rdx, [rcx+10h]
0x18001ebbe  jz      short loc_18001EBE2
0x18001ebc0  movups  xmm0, xmmword ptr [r8]
0x18001ebc4  movups  xmmword ptr [rdx], xmm0
0x18001ebc7  movups  xmm1, xmmword ptr [r8+10h]
0x18001ebcc  movups  xmmword ptr [rdx+10h], xmm1
0x18001ebd0  movsd   xmm0, qword ptr [r8+20h]
0x18001ebd6  movsd   qword ptr [rdx+20h], xmm0
0x18001ebdb  add     qword ptr [rcx+8], 28h ; '('
0x18001ebe0  jmp     short loc_18001EBE7
0x18001ebe2  call    ??$_Emplace_reallocate@AEBU_NUMA_NODE_RELATIONSHIP@@@?$vector@U_NUMA_NODE_RELATIONSHIP@@V?$allocator@U_NUMA_NODE_RELATIONSHIP@@@std@@@std@@AEAAPEAU_NUMA_NODE_RELATIONSHIP@@QEAU2@AEBU2@@Z; std::vector<_NUMA_NODE_RELATIONSHIP>::_Emplace_reallocate<_NUMA_NODE_RELATIONSHIP const &>(_NUMA_NODE_RELATIONSHIP * const,_NUMA_NODE_RELATIONSHIP const &)
0x18001ebe7  inc     ebx
0x18001ebe9  jmp     short loc_18001EB97
0x18001ebeb  mov     r8, [rdi+170h]
0x18001ebf2  sub     r8, [rdi+168h]
0x18001ebf9  sar     r8, 3
0x18001ebfd  imul    r8, r15
0x18001ec01  lea     rdx, aNumberOfNumaNo; "Number of NUMA nodes provided: %zu\n"
0x18001ec08  jmp     short loc_18001EC38
0x18001ec0a  lea     rcx, [rdi+168h]
0x18001ec11  call    ?GetNumaNodeRelationship@CompressedStreamDump@@YAJAEAV?$vector@U_NUMA_NODE_RELATIONSHIP@@V?$allocator@U_NUMA_NODE_RELATIONSHIP@@@std@@@std@@@Z; CompressedStreamDump::GetNumaNodeRelationship(std::vector<_NUMA_NODE_RELATIONSHIP> &)
0x18001ec16  mov     r8, [rdi+170h]
0x18001ec1d  sub     r8, [rdi+168h]
0x18001ec24  sar     r8, 3
0x18001ec28  imul    r8, r15; char *
0x18001ec2c  test    r8, r8
0x18001ec2f  jz      short loc_18001EC44
0x18001ec31  lea     rdx, aNumberOfNumaNo_0; "Number of NUMA nodes detected: %zu\n"
0x18001ec38  mov     ecx, 1; this
0x18001ec3d  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001ec42  jmp     short loc_18001EC56
0x18001ec44  lea     rdx, aNumanodeinfoar; "NumaNodeInfoArray is empty after GetNum"...
0x18001ec4b  mov     ecx, 2; this
0x18001ec50  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001ec55  nop
0x18001ec56  mov     al, 1
0x18001ec58  jmp     short loc_18001EC5C
0x18001ec5a  xor     al, al
0x18001ec5c  lea     r11, [rsp+88h+var_18]
0x18001ec61  mov     rbx, [r11+30h]
0x18001ec65  mov     rdi, [r11+38h]
0x18001ec69  mov     rsp, r11
0x18001ec6c  pop     r15
0x18001ec6e  pop     r14
0x18001ec70  pop     r12
0x18001ec72  retn
0x18001ec73  jmp     short loc_18001EC5A
```
