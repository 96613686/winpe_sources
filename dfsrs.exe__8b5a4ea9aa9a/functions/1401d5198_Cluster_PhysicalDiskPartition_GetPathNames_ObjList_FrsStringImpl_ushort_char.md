# Cluster::PhysicalDiskPartition::GetPathNames(ObjList<FrsStringImpl<ushort,char>> &)

- ea: `0x1401d5198`
- end: `0x1401d543f`
- name: `?GetPathNames@PhysicalDiskPartition@Cluster@@QEBAPEAVFrsStatus@@AEAV?$ObjList@V?$FrsStringImpl@GD@@@@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140040f38`

## callees

- `0x14000ee94`
- `0x14001cfa0`
- `0x14002c548`
- `0x14004691c`
- `0x1401af7b0`
- `0x1401b3af8`
- `0x1401b9494`
- `0x1401c3480`
- `0x1401d1570`
- `0x1401d5198`
- `0x1401d7bfc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401d5242`
- `KERNEL32!GetCurrentThreadId` at `0x1401d52e6`
- `KERNEL32!GetCurrentThreadId` at `0x1401d5353`
- `KERNEL32!GetCurrentThreadId` at `0x1401d53e1`
- `KERNEL32!GetCurrentThreadId` at `0x1401d5242`
- `KERNEL32!GetCurrentThreadId` at `0x1401d52e6`
- `KERNEL32!GetCurrentThreadId` at `0x1401d5353`
- `KERNEL32!GetCurrentThreadId` at `0x1401d53e1`
- `CLUSAPI!ClusterResourceControl` at `0x1401d522d`
- `CLUSAPI!ClusterResourceControl` at `0x1401d52d3`
- `CLUSAPI!ClusterResourceControl` at `0x1401d522d`
- `CLUSAPI!ClusterResourceControl` at `0x1401d52d3`

## string_xrefs

- `0x1401d51e6`: `Cluster::PhysicalDiskPartition::GetPathNames`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Cluster::PhysicalDiskPartition::GetPathNames(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // r15
  const unsigned __int16 *v5; // rcx
  struct FrsStatus *v6; // rdi
  void *v7; // r14
  DWORD v8; // esi
  DWORD v9; // eax
  __int64 v10; // rcx
  _WORD *lpOutBuffer; // rsi
  unsigned __int64 v12; // rdx
  DWORD v13; // r14d
  DWORD v14; // eax
  __int64 v15; // rcx
  int v16; // r14d
  DWORD CurrentThreadId; // eax
  __int64 v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  unsigned __int64 v22; // [rsp+50h] [rbp-20h] BYREF
  struct _HCLUSTER *v23; // [rsp+58h] [rbp-18h] BYREF
  _WORD *v24; // [rsp+60h] [rbp-10h] BYREF
  DWORD BytesReturned; // [rsp+B8h] [rbp+48h] BYREF
  HRESOURCE hResource; // [rsp+C0h] [rbp+50h] BYREF
  char v27; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  v23 = 0;
  hResource = 0;
  v24 = 0;
  BytesReturned = 0;
  v4 = a2 + 8;
  std::vector<FrsStringImpl<unsigned short,char>>::clear(a2 + 8);
  v6 = Cluster::ClusterUtil::OpenClusterAndResource(
         v5,
         (const unsigned __int16 *)(*(_QWORD *)a1 + 18LL),
         &v23,
         &hResource);
  if ( !v6 )
  {
    v7 = (void *)(a1 + 1156);
    v8 = ClusterResourceControl(hResource, 0, 0x1000211u, (LPVOID)(a1 + 1156), 4u, 0, 0, &BytesReturned);
    if ( v8 == 234
      || (v9 = GetCurrentThreadId(),
          (v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                      v10,
                                      v8,
                                      0,
                                      1,
                                      "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                      "Cluster::PhysicalDiskPartition::GetPathNames",
                                      762,
                                      v9,
                                      0)) == 0) )
    {
      lpOutBuffer = operator_new(saturated_mul((unsigned __int64)BytesReturned >> 1, 2u));
      v24 = lpOutBuffer;
      v13 = ClusterResourceControl(hResource, 0, 0x1000211u, v7, 4u, lpOutBuffer, BytesReturned, 0);
      if ( !v13
        || (v14 = GetCurrentThreadId(),
            (v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v15,
                                        v13,
                                        0,
                                        1,
                                        "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                        "Cluster::PhysicalDiskPartition::GetPathNames",
                                        783,
                                        v14,
                                        0)) == 0) )
      {
        while ( lpOutBuffer )
        {
          if ( !*lpOutBuffer )
            break;
          v22 = 0;
          v16 = StringCchLengthW(lpOutBuffer, v12, &v22);
          if ( v16 < 0 )
          {
            CurrentThreadId = GetCurrentThreadId();
            v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                       v18,
                                       (unsigned int)v16,
                                       0,
                                       4,
                                       "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                       "Cluster::PhysicalDiskPartition::GetPathNames",
                                       816,
                                       CurrentThreadId,
                                       0);
            if ( v6 )
              break;
          }
          FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(&v27, lpOutBuffer);
          std::vector<FrsStringImpl<unsigned short,char>>::push_back(v4, &v27);
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v27);
          lpOutBuffer += v22 + 1;
        }
      }
    }
  }
  Cluster::ClusterUtil::CloseClusterAndResource(&v23, &hResource);
  if ( v6 )
  {
    std::vector<FrsStringImpl<unsigned short,char>>::clear(v4);
    v19 = GetCurrentThreadId();
    v3 = FrsStatusList::PushNewError(
           v20,
           *((unsigned int *)v6 + 1),
           *((unsigned int *)v6 + 2),
           *(unsigned int *)v6,
           "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
           "Cluster::PhysicalDiskPartition::GetPathNames",
           853,
           v19,
           v6);
  }
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v24);
  return v3;
}

```

## disassembly

```asm
0x1401d5198  mov     [rsp-38h+arg_0], rbx
0x1401d519d  push    rbp
0x1401d519e  push    rsi
0x1401d519f  push    rdi
0x1401d51a0  push    r12
0x1401d51a2  push    r13
0x1401d51a4  push    r14
0x1401d51a6  push    r15
0x1401d51a8  mov     rbp, rsp
0x1401d51ab  sub     rsp, 70h
0x1401d51af  mov     rsi, rcx
0x1401d51b2  xor     ebx, ebx
0x1401d51b4  mov     [rbp+var_18], rbx
0x1401d51b8  mov     [rbp+hResource], rbx
0x1401d51bc  mov     [rbp+var_10], rbx
0x1401d51c0  mov     [rbp+BytesReturned], ebx
0x1401d51c3  lea     r15, [rdx+8]
0x1401d51c7  mov     rcx, r15
0x1401d51ca  call    ?clear@?$vector@V?$FrsStringImpl@GD@@V?$allocator@V?$FrsStringImpl@GD@@@std@@@std@@QEAAXXZ; std::vector<FrsStringImpl<ushort,char>>::clear(void)
0x1401d51cf  mov     rdx, [rsi]
0x1401d51d2  add     rdx, 12h; unsigned __int16 *
0x1401d51d6  lea     r9, [rbp+hResource]; struct _HRESOURCE **
0x1401d51da  lea     r8, [rbp+var_18]; struct _HCLUSTER **
0x1401d51de  call    ?OpenClusterAndResource@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBG0AEAPEAU_HCLUSTER@@AEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::OpenClusterAndResource(ushort const *,ushort const *,_HCLUSTER * &,_HRESOURCE * &)
0x1401d51e3  mov     rdi, rax
0x1401d51e6  lea     r12, aClusterPhysica_1; "Cluster::PhysicalDiskPartition::GetPath"...
0x1401d51ed  lea     r13, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d51f4  test    rax, rax
0x1401d51f7  jnz     loc_1401D53C7
0x1401d51fd  lea     r14, [rsi+484h]
0x1401d5204  lea     rax, [rbp+BytesReturned]
0x1401d5208  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x1401d520d  mov     [rsp+70h+cbOutBufferSize], ebx; cbOutBufferSize
0x1401d5211  mov     [rsp+70h+lpOutBuffer], rbx; lpOutBuffer
0x1401d5216  mov     [rsp+70h+cbInBufferSize], 4; cbInBufferSize
0x1401d521e  mov     r9, r14; lpInBuffer
0x1401d5221  xor     edx, edx; hHostNode
0x1401d5223  mov     r8d, 1000211h; dwControlCode
0x1401d5229  mov     rcx, [rbp+hResource]; hResource
0x1401d522d  call    cs:__imp_ClusterResourceControl
0x1401d5234  nop     dword ptr [rax+rax+00h]
0x1401d5239  mov     esi, eax
0x1401d523b  cmp     eax, 0EAh
0x1401d5240  jz      short loc_1401D5283
0x1401d5242  call    cs:__imp_GetCurrentThreadId
0x1401d5249  nop     dword ptr [rax+rax+00h]
0x1401d524e  mov     [rsp+70h+var_30], rbx
0x1401d5253  mov     dword ptr [rsp+70h+lpBytesReturned], eax
0x1401d5257  mov     [rsp+70h+cbOutBufferSize], 2FAh
0x1401d525f  mov     [rsp+70h+lpOutBuffer], r12
0x1401d5264  mov     qword ptr [rsp+70h+cbInBufferSize], r13
0x1401d5269  lea     r9d, [rbx+1]
0x1401d526d  xor     r8d, r8d
0x1401d5270  mov     edx, esi
0x1401d5272  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d5277  mov     rdi, rax
0x1401d527a  test    rax, rax
0x1401d527d  jnz     loc_1401D53C7
0x1401d5283  mov     ecx, [rbp+BytesReturned]
0x1401d5286  shr     rcx, 1
0x1401d5289  mov     eax, 2
0x1401d528e  mul     rcx
0x1401d5291  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1401d5298  cmovo   rax, rcx
0x1401d529c  mov     rcx, rax; unsigned __int64
0x1401d529f  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401d52a4  mov     rsi, rax
0x1401d52a7  mov     [rbp+var_10], rax
0x1401d52ab  mov     [rsp+70h+lpBytesReturned], rbx; lpBytesReturned
0x1401d52b0  mov     edx, [rbp+BytesReturned]
0x1401d52b3  mov     [rsp+70h+cbOutBufferSize], edx; cbOutBufferSize
0x1401d52b7  mov     [rsp+70h+lpOutBuffer], rax; lpOutBuffer
0x1401d52bc  mov     [rsp+70h+cbInBufferSize], 4; cbInBufferSize
0x1401d52c4  mov     r9, r14; lpInBuffer
0x1401d52c7  xor     edx, edx; hHostNode
0x1401d52c9  mov     r8d, 1000211h; dwControlCode
0x1401d52cf  mov     rcx, [rbp+hResource]; hResource
0x1401d52d3  call    cs:__imp_ClusterResourceControl
0x1401d52da  nop     dword ptr [rax+rax+00h]
0x1401d52df  mov     r14d, eax
0x1401d52e2  test    eax, eax
0x1401d52e4  jz      short loc_1401D532A
0x1401d52e6  call    cs:__imp_GetCurrentThreadId
0x1401d52ed  nop     dword ptr [rax+rax+00h]
0x1401d52f2  mov     [rsp+70h+var_30], rbx
0x1401d52f7  mov     dword ptr [rsp+70h+lpBytesReturned], eax
0x1401d52fb  mov     [rsp+70h+cbOutBufferSize], 30Fh
0x1401d5303  mov     [rsp+70h+lpOutBuffer], r12
0x1401d5308  mov     qword ptr [rsp+70h+cbInBufferSize], r13
0x1401d530d  mov     r9d, 1
0x1401d5313  xor     r8d, r8d
0x1401d5316  mov     edx, r14d
0x1401d5319  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d531e  mov     rdi, rax
0x1401d5321  test    rax, rax
0x1401d5324  jnz     loc_1401D53C7
0x1401d532a  test    rsi, rsi
0x1401d532d  jz      loc_1401D53C7
0x1401d5333  cmp     [rsi], bx
0x1401d5336  jz      loc_1401D53C7
0x1401d533c  mov     [rbp+var_20], rbx
0x1401d5340  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1401d5344  mov     rcx, rsi; unsigned __int16 *
0x1401d5347  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1401d534c  mov     r14d, eax
0x1401d534f  test    eax, eax
0x1401d5351  jns     short loc_1401D5393
0x1401d5353  call    cs:__imp_GetCurrentThreadId
0x1401d535a  nop     dword ptr [rax+rax+00h]
0x1401d535f  mov     [rsp+70h+var_30], rbx
0x1401d5364  mov     dword ptr [rsp+70h+lpBytesReturned], eax
0x1401d5368  mov     [rsp+70h+cbOutBufferSize], 330h
0x1401d5370  mov     [rsp+70h+lpOutBuffer], r12
0x1401d5375  mov     qword ptr [rsp+70h+cbInBufferSize], r13
0x1401d537a  mov     r9d, 4
0x1401d5380  xor     r8d, r8d
0x1401d5383  mov     edx, r14d
0x1401d5386  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d538b  mov     rdi, rax
0x1401d538e  test    rax, rax
0x1401d5391  jnz     short loc_1401D53C7
0x1401d5393  mov     rdx, rsi
0x1401d5396  lea     rcx, [rbp+arg_18]
0x1401d539a  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1401d539f  nop
0x1401d53a0  lea     rdx, [rbp+arg_18]
0x1401d53a4  mov     rcx, r15
0x1401d53a7  call    ?push_back@?$vector@V?$FrsStringImpl@GD@@V?$allocator@V?$FrsStringImpl@GD@@@std@@@std@@QEAAXAEBV?$FrsStringImpl@GD@@@Z; std::vector<FrsStringImpl<ushort,char>>::push_back(FrsStringImpl<ushort,char> const &)
0x1401d53ac  nop
0x1401d53ad  lea     rcx, [rbp+arg_18]
0x1401d53b1  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d53b6  mov     rax, [rbp+var_20]
0x1401d53ba  lea     rsi, [rsi+rax*2]
0x1401d53be  add     rsi, 2
0x1401d53c2  jmp     loc_1401D532A
0x1401d53c7  lea     rdx, [rbp+hResource]; struct _HRESOURCE **
0x1401d53cb  lea     rcx, [rbp+var_18]; struct _HCLUSTER **
0x1401d53cf  call    ?CloseClusterAndResource@ClusterUtil@Cluster@@SAXAEAPEAU_HCLUSTER@@AEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::CloseClusterAndResource(_HCLUSTER * &,_HRESOURCE * &)
0x1401d53d4  test    rdi, rdi
0x1401d53d7  jz      short loc_1401D541A
0x1401d53d9  mov     rcx, r15
0x1401d53dc  call    ?clear@?$vector@V?$FrsStringImpl@GD@@V?$allocator@V?$FrsStringImpl@GD@@@std@@@std@@QEAAXXZ; std::vector<FrsStringImpl<ushort,char>>::clear(void)
0x1401d53e1  call    cs:__imp_GetCurrentThreadId
0x1401d53e8  nop     dword ptr [rax+rax+00h]
0x1401d53ed  mov     [rsp+70h+var_30], rdi
0x1401d53f2  mov     dword ptr [rsp+70h+lpBytesReturned], eax
0x1401d53f6  mov     [rsp+70h+cbOutBufferSize], 355h
0x1401d53fe  mov     [rsp+70h+lpOutBuffer], r12
0x1401d5403  mov     qword ptr [rsp+70h+cbInBufferSize], r13
0x1401d5408  mov     r9d, [rdi]
0x1401d540b  mov     r8d, [rdi+8]
0x1401d540f  mov     edx, [rdi+4]
0x1401d5412  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d5417  mov     rbx, rax
0x1401d541a  lea     rcx, [rbp+var_10]
0x1401d541e  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401d5423  mov     rax, rbx
0x1401d5426  mov     rbx, [rsp+70h+arg_0]
0x1401d542e  add     rsp, 70h
0x1401d5432  pop     r15
0x1401d5434  pop     r14
0x1401d5436  pop     r13
0x1401d5438  pop     r12
0x1401d543a  pop     rdi
0x1401d543b  pop     rsi
0x1401d543c  pop     rbp
0x1401d543d  retn
```
