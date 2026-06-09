# CRootCauseInfoCollector::GetRootCauseInfoList(tagRootCauseInfo *,int)

- ea: `0x180021a1c`
- end: `0x180021daf`
- name: `?GetRootCauseInfoList@CRootCauseInfoCollector@@QEAAJPEAUtagRootCauseInfo@@H@Z`
- size: `915`
- prototype: `__int64 __fastcall(struct ProblemInstance ****this, struct tagRootCauseInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180018ae4`

## callees

- `0x180005048`
- `0x180005c64`
- `0x180006fa0`
- `0x180007014`
- `0x180017b94`
- `0x1800218e8`
- `0x180021a1c`
- `0x1800220cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021acb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021acb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021bdf`

## pseudocode

```c
__int64 __fastcall CRootCauseInfoCollector::GetRootCauseInfoList(
        struct ProblemInstance ****this,
        struct tagRootCauseInfo *a2,
        unsigned int a3)
{
  int v3; // eax
  struct tagRootCauseInfo *v4; // rsi
  struct ProblemInstance ****v5; // r13
  unsigned __int64 v6; // r11
  struct ProblemInstance ***v7; // rdi
  int v8; // r12d
  struct ProblemInstance **v9; // r14
  const unsigned __int16 *v10; // r15
  int v11; // ebx
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  struct ProblemInstance *v14; // r11
  int v15; // edx
  USHORT v16; // r15
  __int64 *v17; // r13
  _QWORD *v18; // rax
  __int64 v19; // rcx
  __int64 i; // rcx
  SIZE_T v21; // rbx
  RepairInfoEx *v22; // rax
  _QWORD *v24; // rbx
  const unsigned __int16 *v25; // r8
  USHORT j; // r12
  __int64 v27; // rdx
  int v28; // r13d
  __int64 v29; // rcx
  _QWORD *k; // rax
  struct tagRootCauseInfo *v31; // [rsp+20h] [rbp-E8h] BYREF
  __int64 v32; // [rsp+28h] [rbp-E0h]
  struct ProblemInstance **v33; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v34; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C8h] BYREF
  struct tagRepairInfo v36; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-48h]
  int v39; // [rsp+118h] [rbp+10h]
  unsigned __int64 v41; // [rsp+128h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = this;
  v31 = a2;
  v32 = a3;
  v6 = 0;
  v7 = *this;
  v8 = 0;
  while ( 1 )
  {
    v39 = v8;
    if ( v7 == v5[1] || v8 >= v3 )
      break;
    v9 = *v7;
    v33 = *v7;
    if ( !v4 || (v10 = (const unsigned __int16 *)*((_QWORD *)*v9 + 10)) == 0 )
    {
      v11 = -2147024809;
      goto LABEL_52;
    }
    v41 = v6;
    v11 = StringCchLengthW(v10, 0xFFFEu, &v41);
    if ( v11 < 0 )
      goto LABEL_52;
    v12 = v41;
    v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v41 + 2);
    v4->pwszDescription = v13;
    if ( !v13 )
    {
      v11 = -2147024882;
      goto LABEL_52;
    }
    v11 = StringCchCopyW(v13, v12 + 1, v10);
    if ( v11 < 0 )
      goto LABEL_52;
    v4->rootCauseID = (GUID)*((_OWORD *)*v9 + 16);
    v4->rootCauseFlags = (unsigned int)v14;
    v15 = (int)v14;
    if ( v9[7] == v14 )
    {
      v4->rootCauseFlags = 1;
      v15 = 1;
    }
    if ( *((_DWORD *)*v9 + 24) == 10 )
    {
      v15 |= 2u;
      v4->rootCauseFlags = v15;
    }
    if ( *(_DWORD *)(*((_QWORD *)*v9 + 9) + 24LL) == (_DWORD)v14 )
      v4->rootCauseFlags = v15 | 4;
    GetAdapterGUID(*v9, &v4->networkInterfaceID);
    v16 = 0;
    v17 = (__int64 *)(v5 + 3);
    v41 = (unsigned __int64)v17;
    v18 = (_QWORD *)*std::_Tree<std::_Tmap_traits<ProblemNode *,tagRepairInfoEx,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,tagRepairInfoEx>>,1>>::find(
                       v17,
                       &v34,
                       (unsigned __int64 *)&v33);
    while ( v18 != (_QWORD *)*v17 && (struct ProblemInstance **)v18[4] == v9 && v16 != 0xFFFF )
    {
      ++v16;
      if ( *((_BYTE *)v18 + 25) == (_BYTE)v6 )
      {
        v19 = v18[2];
        if ( *(_BYTE *)(v19 + 25) == (_BYTE)v6 )
        {
          v18 = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>>::_Min((_QWORD *)v19);
        }
        else
        {
          for ( i = v18[1]; *(_BYTE *)(i + 25) == (_BYTE)v6 && v18 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
            v18 = (_QWORD *)i;
          v18 = (_QWORD *)i;
        }
      }
    }
    if ( v16 )
    {
      v21 = 120LL * v16;
      v22 = (RepairInfoEx *)CoTaskMemAlloc(v21);
      v4->pRepairs = v22;
      if ( !v22 )
      {
        TNDFDeallocator<tagRootCauseInfo *,&void FreeRootCauseInfos(tagRootCauseInfo *,unsigned long,int)>::~TNDFDeallocator<tagRootCauseInfo *,&void FreeRootCauseInfos(tagRootCauseInfo *,unsigned long,int)>(&v31);
        return 2147942414LL;
      }
      for ( ; v21; --v21 )
      {
        LOBYTE(v22->repair.guid.Data1) = 0;
        v22 = (RepairInfoEx *)((char *)v22 + 1);
      }
      v24 = (_QWORD *)*std::_Tree<std::_Tmap_traits<ProblemNode *,tagRepairInfoEx,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,tagRepairInfoEx>>,1>>::find(
                         v17,
                         &v35,
                         (unsigned __int64 *)&v33);
      for ( j = v6; v24 != (_QWORD *)*v17 && (struct ProblemInstance **)v24[4] == v9 && j < v16; ++j )
      {
        v36 = *(struct tagRepairInfo *)(v24 + 5);
        v37 = v24[19];
        v27 = j;
        v4->pRepairs[v27].repairRank = v37;
        v28 = CopyRepairInfo(&v4->pRepairs[v27].repair, &v36, v25);
        v6 = 0;
        if ( v28 < 0 )
        {
          TNDFDeallocator<tagRootCauseInfo *,&void FreeRootCauseInfos(tagRootCauseInfo *,unsigned long,int)>::~TNDFDeallocator<tagRootCauseInfo *,&void FreeRootCauseInfos(tagRootCauseInfo *,unsigned long,int)>(&v31);
          return (unsigned int)v28;
        }
        v17 = (__int64 *)v41;
        if ( !*((_BYTE *)v24 + 25) )
        {
          v29 = v24[2];
          if ( *(_BYTE *)(v29 + 25) )
          {
            for ( k = (_QWORD *)v24[1]; !*((_BYTE *)k + 25) && v24 == (_QWORD *)k[2]; k = (_QWORD *)k[1] )
              v24 = k;
          }
          else
          {
            k = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>>::_Min((_QWORD *)v29);
          }
          v24 = k;
        }
      }
      v4->repairCount = v16;
      v8 = v39;
    }
    ++v4;
    ++v8;
    ++v7;
    v5 = this;
    v3 = a3;
  }
  v31 = (struct tagRootCauseInfo *)v6;
  v32 = 0;
  v11 = v6;
LABEL_52:
  TNDFDeallocator<tagRootCauseInfo *,&void FreeRootCauseInfos(tagRootCauseInfo *,unsigned long,int)>::~TNDFDeallocator<tagRootCauseInfo *,&void FreeRootCauseInfos(tagRootCauseInfo *,unsigned long,int)>(&v31);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180021a1c  mov     [rsp+arg_10], r8d
0x180021a21  mov     [rsp+arg_0], rcx
0x180021a26  push    rbx
0x180021a27  push    rsi
0x180021a28  push    rdi
0x180021a29  push    r12
0x180021a2b  push    r13
0x180021a2d  push    r14
0x180021a2f  push    r15
0x180021a31  sub     rsp, 0D0h
0x180021a38  mov     eax, r8d
0x180021a3b  mov     rsi, rdx
0x180021a3e  mov     r13, rcx
0x180021a41  mov     [rsp+108h+var_E8], rdx
0x180021a46  mov     dword ptr [rsp+108h+var_E0], eax
0x180021a4a  xor     r11d, r11d
0x180021a4d  mov     dword ptr [rsp+108h+var_E0+4], r11d
0x180021a52  mov     rdi, [rcx]
0x180021a55  mov     r12d, r11d
0x180021a58  mov     [rsp+108h+arg_8], r12d
0x180021a60  cmp     rdi, [r13+8]
0x180021a64  jz      loc_180021D7E
0x180021a6a  cmp     r12d, eax
0x180021a6d  jge     loc_180021D7E
0x180021a73  mov     r14, [rdi]
0x180021a76  mov     [rsp+108h+var_D8], r14
0x180021a7b  test    rsi, rsi
0x180021a7e  jz      loc_180021D77
0x180021a84  mov     rax, [r14]
0x180021a87  mov     r15, [rax+50h]
0x180021a8b  test    r15, r15
0x180021a8e  jz      loc_180021D77
0x180021a94  mov     [rsp+108h+arg_18], r11
0x180021a9c  lea     r8, [rsp+108h+arg_18]; unsigned __int64 *
0x180021aa4  mov     edx, 0FFFEh; unsigned __int64
0x180021aa9  mov     rcx, r15; unsigned __int16 *
0x180021aac  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180021ab1  mov     ebx, eax
0x180021ab3  test    eax, eax
0x180021ab5  js      loc_180021D8F
0x180021abb  mov     rbx, [rsp+108h+arg_18]
0x180021ac3  lea     rcx, ds:2[rbx*2]; cb
0x180021acb  call    cs:__imp_CoTaskMemAlloc
0x180021ad1  mov     [rsi], rax
0x180021ad4  xor     r11d, r11d
0x180021ad7  test    rax, rax
0x180021ada  jnz     short loc_180021AE6
0x180021adc  mov     ebx, 8007000Eh
0x180021ae1  jmp     loc_180021D8F
0x180021ae6  lea     rdx, [rbx+1]; unsigned __int64
0x180021aea  mov     r8, r15; unsigned __int16 *
0x180021aed  mov     rcx, rax; unsigned __int16 *
0x180021af0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021af5  mov     ebx, eax
0x180021af7  test    eax, eax
0x180021af9  js      loc_180021D8F
0x180021aff  mov     rax, [r14]
0x180021b02  movups  xmm0, xmmword ptr [rax+100h]
0x180021b09  movdqu  xmmword ptr [rsi+8], xmm0
0x180021b0e  mov     [rsi+18h], r11d
0x180021b12  mov     edx, r11d
0x180021b15  mov     ebx, 1
0x180021b1a  cmp     [r14+38h], r11
0x180021b1e  jnz     short loc_180021B25
0x180021b20  mov     [rsi+18h], ebx
0x180021b23  mov     edx, ebx
0x180021b25  mov     rax, [r14]
0x180021b28  cmp     dword ptr [rax+60h], 0Ah
0x180021b2c  jnz     short loc_180021B34
0x180021b2e  or      edx, 2
0x180021b31  mov     [rsi+18h], edx
0x180021b34  mov     rax, [r14]
0x180021b37  mov     rcx, [rax+48h]
0x180021b3b  cmp     [rcx+18h], r11d
0x180021b3f  jnz     short loc_180021B47
0x180021b41  or      edx, 4
0x180021b44  mov     [rsi+18h], edx
0x180021b47  lea     rdx, [rsi+1Ch]; struct _GUID *
0x180021b4b  mov     rcx, [r14]; struct ProblemInstance *
0x180021b4e  call    ?GetAdapterGUID@@YAHPEAVProblemInstance@@PEAU_GUID@@@Z; GetAdapterGUID(ProblemInstance *,_GUID *)
0x180021b53  xor     r11d, r11d
0x180021b56  mov     r15d, r11d
0x180021b59  add     r13, 18h
0x180021b5d  mov     [rsp+108h+arg_18], r13
0x180021b65  lea     r8, [rsp+108h+var_D8]
0x180021b6a  lea     rdx, [rsp+108h+var_D0]
0x180021b6f  mov     rcx, r13
0x180021b72  call    ?find@?$_Tree@V?$_Tmap_traits@PEAVProblemNode@@UtagRepairInfoEx@@U?$less@PEAVProblemNode@@@std@@V?$allocator@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@@4@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@@std@@@std@@@2@AEBQEAVProblemNode@@@Z; std::_Tree<std::_Tmap_traits<ProblemNode *,tagRepairInfoEx,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,tagRepairInfoEx>>,1>>::find(ProblemNode * const &)
0x180021b77  mov     rax, [rax]
0x180021b7a  cmp     rax, [r13+0]
0x180021b7e  jz      short loc_180021BCA
0x180021b80  cmp     [rax+20h], r14
0x180021b84  jnz     short loc_180021BCA
0x180021b86  mov     ecx, 0FFFFh
0x180021b8b  cmp     r15w, cx
0x180021b8f  jnb     short loc_180021BCA
0x180021b91  add     r15w, bx
0x180021b95  cmp     [rax+19h], r11b
0x180021b99  jnz     short loc_180021B7A
0x180021b9b  mov     rcx, [rax+10h]
0x180021b9f  cmp     [rcx+19h], r11b
0x180021ba3  jnz     short loc_180021BAC
0x180021ba5  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>,void *> *)
0x180021baa  jmp     short loc_180021B7A
0x180021bac  mov     rcx, [rax+8]
0x180021bb0  jmp     short loc_180021BBF
0x180021bb2  cmp     rax, [rcx+10h]
0x180021bb6  jnz     short loc_180021BC5
0x180021bb8  mov     rax, rcx
0x180021bbb  mov     rcx, [rcx+8]
0x180021bbf  cmp     [rcx+19h], r11b
0x180021bc3  jz      short loc_180021BB2
0x180021bc5  mov     rax, rcx
0x180021bc8  jmp     short loc_180021B7A
0x180021bca  test    r15w, r15w
0x180021bce  jz      loc_180021D4A
0x180021bd4  movzx   eax, r15w
0x180021bd8  imul    rbx, rax, 78h ; 'x'
0x180021bdc  mov     rcx, rbx; cb
0x180021bdf  call    cs:__imp_CoTaskMemAlloc
0x180021be5  mov     [rsi+30h], rax
0x180021be9  xor     r11d, r11d
0x180021bec  test    rax, rax
0x180021bef  jnz     short loc_180021C05
0x180021bf1  lea     rcx, [rsp+108h+var_E8]
0x180021bf6  call    ??1?$TNDFDeallocator@PEAUtagRootCauseInfo@@$1?FreeRootCauseInfos@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagRootCauseInfo *,&FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)>::~TNDFDeallocator<tagRootCauseInfo *,&FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)>(void)
0x180021bfb  mov     eax, 8007000Eh
0x180021c00  jmp     loc_180021D9B
0x180021c05  test    rbx, rbx
0x180021c08  jz      short loc_180021C1A
0x180021c0a  mov     ecx, 1
0x180021c0f  mov     [rax], r11b
0x180021c12  add     rax, rcx
0x180021c15  sub     rbx, rcx
0x180021c18  jnz     short loc_180021C0F
0x180021c1a  lea     r8, [rsp+108h+var_D8]
0x180021c1f  lea     rdx, [rsp+108h+var_C8]
0x180021c24  mov     rcx, r13
0x180021c27  call    ?find@?$_Tree@V?$_Tmap_traits@PEAVProblemNode@@UtagRepairInfoEx@@U?$less@PEAVProblemNode@@@std@@V?$allocator@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@@4@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@@std@@@std@@@2@AEBQEAVProblemNode@@@Z; std::_Tree<std::_Tmap_traits<ProblemNode *,tagRepairInfoEx,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,tagRepairInfoEx>>,1>>::find(ProblemNode * const &)
0x180021c2c  mov     rbx, [rax]
0x180021c2f  mov     r12d, r11d
0x180021c32  cmp     rbx, [r13+0]
0x180021c36  jz      loc_180021D3D
0x180021c3c  cmp     [rbx+20h], r14
0x180021c40  jnz     loc_180021D3D
0x180021c46  cmp     r12w, r15w
0x180021c4a  jnb     loc_180021D3D
0x180021c50  movups  xmm0, xmmword ptr [rbx+28h]
0x180021c54  movaps  xmmword ptr [rsp+108h+var_B8.guid.Data1], xmm0
0x180021c59  movups  xmm1, xmmword ptr [rbx+38h]
0x180021c5d  movaps  xmmword ptr [rsp+108h+var_B8.pwszClassName], xmm1
0x180021c62  movups  xmm0, xmmword ptr [rbx+48h]
0x180021c66  movaps  xmmword ptr [rsp+108h+var_B8.sidType], xmm0
0x180021c6b  movups  xmm1, xmmword ptr [rbx+58h]
0x180021c6f  movaps  xmmword ptr [rsp+108h+var_B8.risk], xmm1
0x180021c77  movups  xmm0, xmmword ptr [rbx+68h]
0x180021c7b  movaps  xmmword ptr [rsp+108h+var_B8.UiInfo.8], xmm0
0x180021c83  movups  xmm1, xmmword ptr [rbx+78h]
0x180021c87  movaps  xmmword ptr [rsp+108h+var_B8.UiInfo.8+10h], xmm1
0x180021c8f  movups  xmm0, xmmword ptr [rbx+88h]
0x180021c96  movaps  xmmword ptr [rsp+108h+var_B8.UiInfo.8+20h], xmm0
0x180021c9e  movsd   xmm1, qword ptr [rbx+98h]
0x180021ca6  movsd   [rsp+108h+var_48], xmm1
0x180021caf  movzx   eax, r12w
0x180021cb3  imul    rdx, rax, 78h ; 'x'
0x180021cb7  mov     rcx, [rsi+30h]
0x180021cbb  movzx   eax, word ptr [rsp+108h+var_48]
0x180021cc3  mov     [rdx+rcx+70h], ax
0x180021cc8  mov     rcx, [rsi+30h]
0x180021ccc  add     rcx, rdx; struct tagRepairInfo *
0x180021ccf  lea     rdx, [rsp+108h+var_B8]; struct tagRepairInfo *
0x180021cd4  call    ?CopyRepairInfo@@YAJPEAUtagRepairInfo@@PEBU1@@Z; CopyRepairInfo(tagRepairInfo *,tagRepairInfo const *)
0x180021cd9  mov     r13d, eax
0x180021cdc  xor     r11d, r11d
0x180021cdf  test    eax, eax
0x180021ce1  jns     short loc_180021CF5
0x180021ce3  lea     rcx, [rsp+108h+var_E8]
0x180021ce8  call    ??1?$TNDFDeallocator@PEAUtagRootCauseInfo@@$1?FreeRootCauseInfos@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagRootCauseInfo *,&FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)>::~TNDFDeallocator<tagRootCauseInfo *,&FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)>(void)
0x180021ced  mov     eax, r13d
0x180021cf0  jmp     loc_180021D9B
0x180021cf5  inc     r12w
0x180021cf9  cmp     [rbx+19h], r11b
0x180021cfd  mov     r13, [rsp+108h+arg_18]
0x180021d05  jnz     loc_180021C32
0x180021d0b  mov     rcx, [rbx+10h]
0x180021d0f  cmp     [rcx+19h], r11b
0x180021d13  jnz     short loc_180021D22
0x180021d15  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>,void *> *)
0x180021d1a  mov     rbx, rax
0x180021d1d  jmp     loc_180021C32
0x180021d22  mov     rax, [rbx+8]
0x180021d26  jmp     short loc_180021D35
0x180021d28  cmp     rbx, [rax+10h]
0x180021d2c  jnz     short loc_180021D1A
0x180021d2e  mov     rbx, rax
0x180021d31  mov     rax, [rax+8]
0x180021d35  cmp     [rax+19h], r11b
0x180021d39  jz      short loc_180021D28
0x180021d3b  jmp     short loc_180021D1A
0x180021d3d  mov     [rsi+38h], r15w
0x180021d42  mov     r12d, [rsp+108h+arg_8]
0x180021d4a  add     rsi, 40h ; '@'
0x180021d4e  inc     r12d
0x180021d51  add     rdi, 8
0x180021d55  mov     r13, [rsp+108h+arg_0]
0x180021d5d  mov     eax, [rsp+108h+arg_10]
0x180021d64  jmp     loc_180021A58
0x180021d69  mov     ebx, 80004005h
0x180021d6e  jmp     short loc_180021D75
0x180021d70  mov     ebx, 8007000Eh
0x180021d75  jmp     short loc_180021D8F
0x180021d77  mov     ebx, 80070057h
0x180021d7c  jmp     short loc_180021D8F
0x180021d7e  mov     [rsp+108h+var_E8], r11
0x180021d83  mov     [rsp+108h+var_E0], 0
0x180021d8c  mov     ebx, r11d
0x180021d8f  lea     rcx, [rsp+108h+var_E8]
0x180021d94  call    ??1?$TNDFDeallocator@PEAUtagRootCauseInfo@@$1?FreeRootCauseInfos@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagRootCauseInfo *,&FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)>::~TNDFDeallocator<tagRootCauseInfo *,&FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)>(void)
0x180021d99  mov     eax, ebx
0x180021d9b  add     rsp, 0D0h
0x180021da2  pop     r15
0x180021da4  pop     r14
0x180021da6  pop     r13
0x180021da8  pop     r12
0x180021daa  pop     rdi
0x180021dab  pop     rsi
0x180021dac  pop     rbx
0x180021dad  retn
```
