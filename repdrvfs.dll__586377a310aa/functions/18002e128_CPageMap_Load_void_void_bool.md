# CPageMap::Load(void *,void *,bool)

- ea: `0x18002e128`
- end: `0x18002e5b2`
- name: `?Load@CPageMap@@QEAAKPEAX0_N@Z`
- size: `1162`
- prototype: `unsigned int __fastcall(CPageMap *__hidden this, HANDLE hFile, void *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002e830`

## callees

- `0x1800012b8`
- `0x18002496c`
- `0x18002e128`
- `0x18002e5b8`
- `0x18003085c`
- `0x1800308ec`
- `0x18003d184`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002e170`
- `wbemcomn!GetMemLogObject` at `0x18002e38f`
- `wbemcomn!GetMemLogObject` at `0x18002e3e9`
- `wbemcomn!GetMemLogObject` at `0x18002e448`
- `wbemcomn!GetMemLogObject` at `0x18002e4a2`
- `wbemcomn!GetMemLogObject` at `0x18002e506`
- `wbemcomn!GetMemLogObject` at `0x18002e551`
- `wbemcomn!GetMemLogObject` at `0x18002e170`
- `wbemcomn!GetMemLogObject` at `0x18002e38f`
- `wbemcomn!GetMemLogObject` at `0x18002e3e9`
- `wbemcomn!GetMemLogObject` at `0x18002e448`
- `wbemcomn!GetMemLogObject` at `0x18002e4a2`
- `wbemcomn!GetMemLogObject` at `0x18002e506`
- `wbemcomn!GetMemLogObject` at `0x18002e551`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e17e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e39d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e3f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e456`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e4b0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e514`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e55f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e17e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e39d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e3f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e456`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e4b0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e514`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e55f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e1d6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e20f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e258`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e2d1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e315`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e351`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e1d6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e20f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e258`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e2d1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e315`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e351`

## pseudocode

```c
unsigned int __fastcall CPageMap::Load(LPVOID *this, HANDLE hFile, void *a3, bool a4)
{
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v9; // rcx
  __int64 v10; // rdx
  LPVOID *v11; // r14
  _DWORD *i; // rax
  BOOL v13; // eax
  BOOL v14; // eax
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-48h] BYREF
  unsigned int Buffer; // [rsp+34h] [rbp-44h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-40h] BYREF
  _DWORD v27[15]; // [rsp+3Ch] [rbp-3Ch] BYREF

  v27[0] = 0;
  NumberOfBytesRead = 0;
  if ( CPageMap::LoadSignature((CPageMap *)this, hFile, a4) )
  {
    if ( !a4 )
      CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 1358);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 1358;
    }
    v10 = 16;
    goto LABEL_66;
  }
  if ( !ReadFile(hFile, this + 11, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 )
  {
    if ( !a4 )
      CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, 1358);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 1358;
    }
    v10 = 17;
LABEL_66:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 1358);
    return 1358;
  }
  Buffer = 0;
  if ( !ReadFile(hFile, &Buffer, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 )
  {
    if ( !a4 )
      CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, 1358);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 1358;
    }
    v10 = 18;
    goto LABEL_66;
  }
  try
  {
    v11 = this + 2;
    std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::resize(this + 2, Buffer);
  }
  catch ( CX_MemoryException )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 14);
    }
    return 14;
  }
  if ( !ReadFile(hFile, *v11, 24 * Buffer, &NumberOfBytesRead, 0) || NumberOfBytesRead != 24LL * Buffer )
  {
    if ( !a4 )
      CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, 1358);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 1358;
    }
    v10 = 20;
    goto LABEL_66;
  }
  for ( i = *v11; i != this[3]; i += 6 )
  {
    if ( i[4] != *((_DWORD *)this + 1) )
    {
      if ( !a4 )
        CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
      return 1358;
    }
  }
  v26 = 0;
  v13 = ReadFile(hFile, &v26, 4u, &NumberOfBytesRead, 0);
  if ( v13 && NumberOfBytesRead == 4 )
  {
    try
    {
      std::vector<unsigned long,wbem_allocator<unsigned long>>::resize(this + 5, v26);
      v14 = ReadFile(hFile, this[5], 4 * v26, &NumberOfBytesRead, 0);
    }
    catch ( CX_MemoryException )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, 14);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 14);
      }
      return 14;
    }
    if ( v14 && NumberOfBytesRead == 4LL * v26 )
    {
      if ( ReadFile(hFile, v27, 4u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 4 && v27[0] == 56506 )
        return ValidateMapFile((const struct CPageMap *)this, a3, a4);
      if ( !a4 )
        CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, 1358);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 24;
        goto LABEL_66;
      }
    }
    else
    {
      if ( !a4 )
        CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, 1358);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 23;
        goto LABEL_66;
      }
    }
  }
  else
  {
    if ( !a4 )
      CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, 1358);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 21;
      goto LABEL_66;
    }
  }
  return 1358;
}

```

## disassembly

```asm
0x18002e128  push    rbx
0x18002e12a  push    rsi
0x18002e12b  push    rdi
0x18002e12c  push    r12
0x18002e12e  push    r14
0x18002e130  push    r15
0x18002e132  sub     rsp, 48h
0x18002e136  mov     dil, r9b
0x18002e139  mov     r12, r8
0x18002e13c  mov     r15, rdx
0x18002e13f  mov     rsi, rcx
0x18002e142  mov     [rsp+78h+var_3C], 0
0x18002e14a  mov     [rsp+78h+NumberOfBytesRead], 0
0x18002e152  mov     r8b, r9b; bool
0x18002e155  call    ?LoadSignature@CPageMap@@QEAAKPEAX_N@Z; CPageMap::LoadSignature(void *,bool)
0x18002e15a  test    eax, eax
0x18002e15c  jz      short loc_18002E1B9
0x18002e15e  test    dil, dil
0x18002e161  jnz     short loc_18002E170
0x18002e163  xor     r8d, r8d; unsigned int
0x18002e166  xor     edx, edx; bool
0x18002e168  lea     ecx, [rdx+4]; int
0x18002e16b  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e170  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e176  mov     edx, 54Eh
0x18002e17b  mov     rcx, rax
0x18002e17e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e184  lea     rax, WPP_GLOBAL_Control
0x18002e18b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e192  cmp     rcx, rax
0x18002e195  jz      loc_18002E59F
0x18002e19b  test    byte ptr [rcx+1Ch], 1
0x18002e19f  jz      loc_18002E59F
0x18002e1a5  cmp     byte ptr [rcx+19h], 2
0x18002e1a9  jb      loc_18002E59F
0x18002e1af  mov     edx, 10h
0x18002e1b4  jmp     loc_18002E589
0x18002e1b9  lea     rdx, [rsi+58h]; lpBuffer
0x18002e1bd  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18002e1c6  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e1cb  mov     ebx, 4
0x18002e1d0  mov     r8d, ebx; nNumberOfBytesToRead
0x18002e1d3  mov     rcx, r15; hFile
0x18002e1d6  call    cs:__imp_ReadFile
0x18002e1dc  test    eax, eax
0x18002e1de  jz      loc_18002E540
0x18002e1e4  cmp     [rsp+78h+NumberOfBytesRead], ebx
0x18002e1e8  jnz     loc_18002E540
0x18002e1ee  mov     [rsp+78h+Buffer], 0
0x18002e1f6  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18002e1ff  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e204  mov     r8d, ebx; nNumberOfBytesToRead
0x18002e207  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x18002e20c  mov     rcx, r15; hFile
0x18002e20f  call    cs:__imp_ReadFile
0x18002e215  test    eax, eax
0x18002e217  jz      loc_18002E4F5
0x18002e21d  cmp     [rsp+78h+NumberOfBytesRead], ebx
0x18002e221  jnz     loc_18002E4F5
0x18002e227  lea     r14, [rsi+10h]
0x18002e22b  mov     edx, [rsp+78h+Buffer]
0x18002e22f  mov     rcx, r14
0x18002e232  call    ?resize@?$vector@UPageMapEntry@@V?$wbem_allocator@UPageMapEntry@@@@@std@@QEAAX_K@Z; std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::resize(unsigned __int64)
0x18002e237  nop
0x18002e238  mov     eax, [rsp+78h+Buffer]
0x18002e23c  lea     r8d, [rax+rax*2]
0x18002e240  shl     r8d, 3; nNumberOfBytesToRead
0x18002e244  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18002e24d  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e252  mov     rdx, [r14]; lpBuffer
0x18002e255  mov     rcx, r15; hFile
0x18002e258  call    cs:__imp_ReadFile
0x18002e25e  test    eax, eax
0x18002e260  jz      loc_18002E491
0x18002e266  mov     eax, [rsp+78h+Buffer]
0x18002e26a  lea     rcx, [rax+rax*2]
0x18002e26e  shl     rcx, 3
0x18002e272  mov     eax, [rsp+78h+NumberOfBytesRead]
0x18002e276  cmp     rax, rcx
0x18002e279  jnz     loc_18002E491
0x18002e27f  mov     rax, [r14]
0x18002e282  cmp     rax, [rsi+18h]
0x18002e286  jz      short loc_18002E2B0
0x18002e288  mov     ecx, [rsi+4]
0x18002e28b  cmp     [rax+10h], ecx
0x18002e28e  jnz     short loc_18002E296
0x18002e290  add     rax, 18h
0x18002e294  jmp     short loc_18002E282
0x18002e296  test    dil, dil
0x18002e299  jnz     loc_18002E59F
0x18002e29f  xor     r8d, r8d; unsigned int
0x18002e2a2  xor     edx, edx; bool
0x18002e2a4  mov     ecx, ebx; int
0x18002e2a6  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e2ab  jmp     loc_18002E59F
0x18002e2b0  mov     [rsp+78h+var_40], 0
0x18002e2b8  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18002e2c1  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e2c6  mov     r8d, ebx; nNumberOfBytesToRead
0x18002e2c9  lea     rdx, [rsp+78h+var_40]; lpBuffer
0x18002e2ce  mov     rcx, r15; hFile
0x18002e2d1  call    cs:__imp_ReadFile
0x18002e2d7  test    eax, eax
0x18002e2d9  jz      loc_18002E437
0x18002e2df  cmp     [rsp+78h+NumberOfBytesRead], ebx
0x18002e2e3  jnz     loc_18002E437
0x18002e2e9  mov     edx, [rsp+78h+var_40]
0x18002e2ed  lea     rcx, [rsi+28h]
0x18002e2f1  call    ?resize@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::resize(unsigned __int64)
0x18002e2f6  nop
0x18002e2f7  mov     r8d, [rsp+78h+var_40]
0x18002e2fc  shl     r8d, 2; nNumberOfBytesToRead
0x18002e300  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18002e309  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e30e  mov     rdx, [rsi+28h]; lpBuffer
0x18002e312  mov     rcx, r15; hFile
0x18002e315  call    cs:__imp_ReadFile
0x18002e31b  test    eax, eax
0x18002e31d  jz      loc_18002E3D8
0x18002e323  mov     ecx, [rsp+78h+var_40]
0x18002e327  shl     rcx, 2
0x18002e32b  mov     eax, [rsp+78h+NumberOfBytesRead]
0x18002e32f  cmp     rax, rcx
0x18002e332  jnz     loc_18002E3D8
0x18002e338  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18002e341  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e346  mov     r8d, ebx; nNumberOfBytesToRead
0x18002e349  lea     rdx, [rsp+78h+var_3C]; lpBuffer
0x18002e34e  mov     rcx, r15; hFile
0x18002e351  call    cs:__imp_ReadFile
0x18002e357  test    eax, eax
0x18002e359  jz      short loc_18002E37E
0x18002e35b  cmp     [rsp+78h+NumberOfBytesRead], ebx
0x18002e35f  jnz     short loc_18002E37E
0x18002e361  cmp     [rsp+78h+var_3C], 0DCBAh
0x18002e369  jnz     short loc_18002E37E
0x18002e36b  mov     r8b, dil; bool
0x18002e36e  mov     rdx, r12; void *
0x18002e371  mov     rcx, rsi; struct CPageMap *
0x18002e374  call    ?ValidateMapFile@@YAKAEBUCPageMap@@PEAX_N@Z; ValidateMapFile(CPageMap const &,void *,bool)
0x18002e379  jmp     loc_18002E5A4
0x18002e37e  test    dil, dil
0x18002e381  jnz     short loc_18002E38F
0x18002e383  xor     r8d, r8d; unsigned int
0x18002e386  xor     edx, edx; bool
0x18002e388  mov     ecx, ebx; int
0x18002e38a  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e38f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e395  mov     edx, 54Eh
0x18002e39a  mov     rcx, rax
0x18002e39d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e3a3  lea     rax, WPP_GLOBAL_Control
0x18002e3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3b1  cmp     rcx, rax
0x18002e3b4  jz      loc_18002E59F
0x18002e3ba  test    byte ptr [rcx+1Ch], 1
0x18002e3be  jz      loc_18002E59F
0x18002e3c4  cmp     byte ptr [rcx+19h], 2
0x18002e3c8  jb      loc_18002E59F
0x18002e3ce  mov     edx, 18h
0x18002e3d3  jmp     loc_18002E589
0x18002e3d8  test    dil, dil
0x18002e3db  jnz     short loc_18002E3E9
0x18002e3dd  xor     r8d, r8d; unsigned int
0x18002e3e0  xor     edx, edx; bool
0x18002e3e2  mov     ecx, ebx; int
0x18002e3e4  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e3e9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e3ef  mov     edx, 54Eh
0x18002e3f4  mov     rcx, rax
0x18002e3f7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e3fd  lea     rax, WPP_GLOBAL_Control
0x18002e404  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e40b  cmp     rcx, rax
0x18002e40e  jz      loc_18002E59F
0x18002e414  test    byte ptr [rcx+1Ch], 1
0x18002e418  jz      loc_18002E59F
0x18002e41e  cmp     byte ptr [rcx+19h], 2
0x18002e422  jb      loc_18002E59F
0x18002e428  mov     edx, 17h
0x18002e42d  jmp     loc_18002E589
0x18002e432  jmp     loc_18002E4EB
0x18002e437  test    dil, dil
0x18002e43a  jnz     short loc_18002E448
0x18002e43c  xor     r8d, r8d; unsigned int
0x18002e43f  xor     edx, edx; bool
0x18002e441  mov     ecx, ebx; int
0x18002e443  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e448  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e44e  mov     edx, 54Eh
0x18002e453  mov     rcx, rax
0x18002e456  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e45c  lea     rax, WPP_GLOBAL_Control
0x18002e463  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e46a  cmp     rcx, rax
0x18002e46d  jz      loc_18002E59F
0x18002e473  test    byte ptr [rcx+1Ch], 1
0x18002e477  jz      loc_18002E59F
0x18002e47d  cmp     byte ptr [rcx+19h], 2
0x18002e481  jb      loc_18002E59F
0x18002e487  mov     edx, 15h
0x18002e48c  jmp     loc_18002E589
0x18002e491  test    dil, dil
0x18002e494  jnz     short loc_18002E4A2
0x18002e496  xor     r8d, r8d; unsigned int
0x18002e499  xor     edx, edx; bool
0x18002e49b  mov     ecx, ebx; int
0x18002e49d  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e4a2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e4a8  mov     edx, 54Eh
0x18002e4ad  mov     rcx, rax
0x18002e4b0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e4b6  lea     rax, WPP_GLOBAL_Control
0x18002e4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e4c4  cmp     rcx, rax
0x18002e4c7  jz      loc_18002E59F
0x18002e4cd  test    byte ptr [rcx+1Ch], 1
0x18002e4d1  jz      loc_18002E59F
0x18002e4d7  cmp     byte ptr [rcx+19h], 2
0x18002e4db  jb      loc_18002E59F
0x18002e4e1  mov     edx, 14h
0x18002e4e6  jmp     loc_18002E589
0x18002e4eb  mov     eax, 0Eh
0x18002e4f0  jmp     loc_18002E5A4
0x18002e4f5  test    dil, dil
0x18002e4f8  jnz     short loc_18002E506
0x18002e4fa  xor     r8d, r8d; unsigned int
0x18002e4fd  xor     edx, edx; bool
0x18002e4ff  mov     ecx, ebx; int
0x18002e501  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e506  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e50c  mov     edx, 54Eh
0x18002e511  mov     rcx, rax
0x18002e514  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e51a  lea     rax, WPP_GLOBAL_Control
0x18002e521  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e528  cmp     rcx, rax
0x18002e52b  jz      short loc_18002E59F
0x18002e52d  test    byte ptr [rcx+1Ch], 1
0x18002e531  jz      short loc_18002E59F
0x18002e533  cmp     byte ptr [rcx+19h], 2
0x18002e537  jb      short loc_18002E59F
0x18002e539  mov     edx, 12h
0x18002e53e  jmp     short loc_18002E589
0x18002e540  test    dil, dil
0x18002e543  jnz     short loc_18002E551
0x18002e545  xor     r8d, r8d; unsigned int
0x18002e548  xor     edx, edx; bool
0x18002e54a  mov     ecx, ebx; int
0x18002e54c  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e551  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e557  mov     edx, 54Eh
0x18002e55c  mov     rcx, rax
0x18002e55f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e565  lea     rax, WPP_GLOBAL_Control
0x18002e56c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e573  cmp     rcx, rax
0x18002e576  jz      short loc_18002E59F
0x18002e578  test    byte ptr [rcx+1Ch], 1
0x18002e57c  jz      short loc_18002E59F
0x18002e57e  cmp     byte ptr [rcx+19h], 2
0x18002e582  jb      short loc_18002E59F
0x18002e584  mov     edx, 11h
0x18002e589  mov     r9d, 54Eh
0x18002e58f  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18002e596  mov     rcx, [rcx+10h]
0x18002e59a  call    WPP_SF_d
0x18002e59f  mov     eax, 54Eh
0x18002e5a4  add     rsp, 48h
0x18002e5a8  pop     r15
0x18002e5aa  pop     r14
0x18002e5ac  pop     r12
0x18002e5ae  pop     rdi
0x18002e5af  pop     rsi
0x18002e5b0  pop     rbx
0x18002e5b1  retn
```
