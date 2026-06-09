# FsLibGroupSubExtentsByDanglingMdl

- ea: `0x140292d10`
- end: `0x140293440`
- name: `FsLibGroupSubExtentsByDanglingMdl`
- size: `1840`
- prototype: `__int64 __fastcall(const void *, __int64, __int64, unsigned int, __int64, __int64, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140055024`
- `0x14020f350`

## callees

- `0x14011af98`
- `0x140292d10`
- `0x14029a9b0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140292db1`
- `ntoskrnl!DbgPrintEx` at `0x140292e5a`
- `ntoskrnl!DbgPrintEx` at `0x140292ec6`
- `ntoskrnl!DbgPrintEx` at `0x140292f53`
- `ntoskrnl!DbgPrintEx` at `0x140292fdd`
- `ntoskrnl!DbgPrintEx` at `0x140293031`
- `ntoskrnl!DbgPrintEx` at `0x140293089`
- `ntoskrnl!DbgPrintEx` at `0x1402930b3`
- `ntoskrnl!DbgPrintEx` at `0x1402930f1`
- `ntoskrnl!DbgPrintEx` at `0x14029316e`
- `ntoskrnl!DbgPrintEx` at `0x1402931d4`
- `ntoskrnl!DbgPrintEx` at `0x14029322e`
- `ntoskrnl!DbgPrintEx` at `0x140293268`
- `ntoskrnl!DbgPrintEx` at `0x1402932d4`
- `ntoskrnl!DbgPrintEx` at `0x1402933c9`
- `ntoskrnl!DbgPrintEx` at `0x140292db1`
- `ntoskrnl!DbgPrintEx` at `0x140292e5a`
- `ntoskrnl!DbgPrintEx` at `0x140292ec6`
- `ntoskrnl!DbgPrintEx` at `0x140292f53`
- `ntoskrnl!DbgPrintEx` at `0x140292fdd`
- `ntoskrnl!DbgPrintEx` at `0x140293031`
- `ntoskrnl!DbgPrintEx` at `0x140293089`
- `ntoskrnl!DbgPrintEx` at `0x1402930b3`
- `ntoskrnl!DbgPrintEx` at `0x1402930f1`
- `ntoskrnl!DbgPrintEx` at `0x14029316e`
- `ntoskrnl!DbgPrintEx` at `0x1402931d4`
- `ntoskrnl!DbgPrintEx` at `0x14029322e`
- `ntoskrnl!DbgPrintEx` at `0x140293268`
- `ntoskrnl!DbgPrintEx` at `0x1402932d4`
- `ntoskrnl!DbgPrintEx` at `0x1402933c9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140293404`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bd9f9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140293404`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bd9f9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140292d87`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140292d87`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402933e9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402bd9dc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402933e9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402bd9dc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140292dd2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140292dd2`
- `ntoskrnl!FsRtlIsExtentDangling` at `0x140292fbd`
- `ntoskrnl!FsRtlIsExtentDangling` at `0x140292fbd`

## string_xrefs

- `0x140292da0`: `FsLibGroupSubExtentsByDanglingMdl: Failed to allocate ExtentsDescriptor from the lookaside list.\n`
- `0x140292deb`: `FsLibGroupSubExtentsByDanglingMdl: Failed to allocate DsmBuffer from the non-paged lookaside list.\n`
- `0x140293025`: `Case 1: Update SubExtentPageCount: %I64x, NextStartPage: %I64x\n`
- `0x1402930e5`: `Case 2: Update SubExtentClusterStart: %I64x\n`
- `0x14029325c`: `Case 4: Update SubExtentPageCount: %I64x, NextStartPage: %I64x\n`
- `0x140293222`: `Case 3: Update SubExtentClusterStart: %I64x, SubExtentPageCount: %I64x, NextStartPage: %I64x\n`

## pseudocode

```c
__int64 __fastcall FsLibGroupSubExtentsByDanglingMdl(
        const void *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        char *a7)
{
  unsigned __int64 v7; // r14
  unsigned int v10; // ebx
  unsigned __int64 v11; // r12
  PVOID v12; // r15
  _DWORD *v13; // r13
  unsigned __int64 v14; // r13
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  _QWORD *v17; // rcx
  int AddressRangesForSingleVolumeExtent; // eax
  __int64 i; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // r15
  unsigned __int64 v22; // rax
  __int64 v23; // r15
  __int64 v24; // r12
  int appended; // eax
  const CHAR *v26; // r8
  unsigned __int64 v27; // r8
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int v32; // eax
  int v34[2]; // [rsp+28h] [rbp-C0h]
  char v35; // [rsp+40h] [rbp-A8h]
  _DWORD *v36; // [rsp+48h] [rbp-A0h]
  PVOID v37; // [rsp+50h] [rbp-98h]
  unsigned __int64 v38; // [rsp+58h] [rbp-90h]
  int v39; // [rsp+60h] [rbp-88h]
  unsigned __int64 v40; // [rsp+68h] [rbp-80h]
  __int64 v41; // [rsp+70h] [rbp-78h]
  unsigned __int64 IsExtentDangling; // [rsp+70h] [rbp-78h]
  __int64 v43; // [rsp+78h] [rbp-70h]
  unsigned __int64 v44; // [rsp+80h] [rbp-68h]
  char v46; // [rsp+F8h] [rbp+10h]
  unsigned __int64 v47; // [rsp+F8h] [rbp+10h]
  unsigned __int64 v48; // [rsp+100h] [rbp+18h]

  v7 = a4;
  if ( a3 <= 0 )
    return 3221225485LL;
  v10 = -1073741823;
  v46 = 0;
  v11 = 0;
  v12 = 0;
  v48 = 0;
  v35 = 0;
  if ( !a5 && !a6 && !a7 )
    return 3221225485LL;
  v13 = ExAllocateFromPagedLookasideList(&FsLibExtentsDescriptorLookasideList);
  v36 = v13;
  if ( v13 )
  {
    v12 = ExAllocateFromNPagedLookasideList(&FsLibDsmBufferLookasideList);
    v37 = v12;
    if ( !v12 )
    {
      DbgPrintEx(
        0x9Au,
        2u,
        "FsLibGroupSubExtentsByDanglingMdl: Failed to allocate DsmBuffer from the non-paged lookaside list.\n");
      goto LABEL_7;
    }
    v14 = v7 >> 12;
    v15 = a2 * (v7 >> 12);
    v44 = v15;
    v16 = a3 * (v7 >> 12);
    v43 = v16;
    v17 = v36;
    while ( v16 > 0 )
    {
      *v17 = 65532;
      DbgPrintEx(
        0x9Au,
        2u,
        "FsLibGroupSubExtentsByDanglingMdl: StartingPageToQuery: 0x%llx, RemainingPagesToQuery: 0x%llx\n",
        v15,
        v16);
      AddressRangesForSingleVolumeExtent = FsLibGetAddressRangesForSingleVolumeExtent(
                                             a1,
                                             v44 << 12,
                                             v43 << 12,
                                             0x10000000,
                                             (__int64)v12,
                                             0x100000u,
                                             v36,
                                             0xFFFD0u);
      v10 = AddressRangesForSingleVolumeExtent;
      if ( AddressRangesForSingleVolumeExtent < 0 )
      {
        DbgPrintEx(
          0x9Au,
          2u,
          "FsLibGroupSubExtentsByDanglingMdl: FsLibGetAddressRangesForSingleVolumeExtent failed with 0x%08x\n",
          AddressRangesForSingleVolumeExtent);
        goto LABEL_59;
      }
      for ( i = 0; ; i = (unsigned int)(v39 + 1) )
      {
        v39 = i;
        v17 = v36;
        if ( (unsigned int)i >= v36[1] )
          break;
        v20 = 2 * i;
        v41 = *(_QWORD *)&v36[2 * v20 + 2];
        v21 = *(_QWORD *)&v36[2 * v20 + 4];
        v43 -= v21;
        v44 += v21;
        DbgPrintEx(0x9Au, 2u, "StartPage: %I64x, PageCount: %I64x, PagesToSkip: %I64x\n", v41, v21, v48);
        if ( v21 > v48 )
        {
          v22 = v48 + v41;
          v38 = v48 + v41;
          v23 = v21 - v48;
          v48 = 0;
          while ( 1 )
          {
            if ( !v23 )
              goto LABEL_46;
            v40 = v22;
            IsExtentDangling = FsRtlIsExtentDangling(v22, v23, 0);
            DbgPrintEx(0x9Au, 2u, "DanglingPage: %I64x\n", IsExtentDangling);
            if ( !v46 )
              goto LABEL_30;
            if ( IsExtentDangling - v38 >= v14 )
            {
              v24 = v11 / v14;
              if ( a5 )
              {
                appended = FsLibAppendExtent(a5, a2, v24);
                v10 = appended;
                if ( appended < 0 )
                {
                  v26 = "Case 2: FAILED to add to ExtentsWithDanglingMdl. StartCluster: %I64x, ClusterCount: %I64x, Status: %08x\n";
LABEL_26:
                  v34[0] = appended;
                  DbgPrintEx(0x9Au, 0, v26, a2, v24, *(_QWORD *)v34);
                  goto LABEL_27;
                }
              }
              DbgPrintEx(0x9Au, 2u, "Case 2: Found dangling MDL. StartCluster: %I64x, ClusterCount: %I64x\n", a2, v24);
              a2 += v24;
              v46 = 0;
              v11 = 0;
              DbgPrintEx(0x9Au, 2u, "Case 2: Update SubExtentClusterStart: %I64x\n", a2);
            }
            else
            {
              v11 += v14;
              v40 = v14 + v38;
              DbgPrintEx(0x9Au, 2u, "Case 1: Update SubExtentPageCount: %I64x, NextStartPage: %I64x\n", v11, v14 + v38);
            }
            if ( !v46 )
            {
LABEL_30:
              if ( IsExtentDangling >= v23 + v38 )
              {
                v11 += v23;
                v40 += v23;
                DbgPrintEx(0x9Au, 2u, "Case 4: Update SubExtentPageCount: %I64x, NextStartPage: %I64x\n", v11, v40);
              }
              else
              {
                v27 = v11 + IsExtentDangling - v38;
                v24 = v27 / v14;
                if ( !v35 )
                {
                  v35 = 1;
                  if ( !a5 && !a6 )
                  {
                    DbgPrintEx(
                      0x9Au,
                      0,
                      "Case 3: Found first dangling MDL.  Caller is not interested in sub extents that dangle or not. Dan"
                      "gling cluster: %I64x, Status: %08x\n",
                      v27 / v14 + a2,
                      v10);
                    goto LABEL_27;
                  }
                }
                v28 = v14 - v27 % v14;
                v47 = v28;
                if ( v24 > 0 )
                {
                  if ( a6 )
                  {
                    appended = FsLibAppendExtent(a6, a2, v24);
                    v10 = appended;
                    if ( appended < 0 )
                    {
                      v26 = "Case 3: FAILED to add to ExtentsWithoutDanglingMdl. StartCluster: %I64x, ClusterCount: %I64x"
                            ", Status: %08x\n";
                      goto LABEL_26;
                    }
                  }
                  DbgPrintEx(
                    0x9Au,
                    2u,
                    "Case 3: Non-dangling range: StartCluster: %I64x, ClusterCount: %I64x\n",
                    a2,
                    v24);
                  v28 = v47;
                }
                a2 += v24;
                v46 = 1;
                v11 = v7 >> 12;
                v40 = IsExtentDangling + v28;
                DbgPrintEx(
                  0x9Au,
                  2u,
                  "Case 3: Update SubExtentClusterStart: %I64x, SubExtentPageCount: %I64x, NextStartPage: %I64x\n",
                  a2,
                  v14,
                  IsExtentDangling + v28);
              }
            }
            v29 = v38;
            if ( v40 < v23 + v38 )
            {
              v23 += v38 - v40;
              v29 = v40;
              v38 = v40;
              v30 = v48;
            }
            else
            {
              v30 = v40 - v23 - v38;
              v48 = v30;
              v23 = 0;
            }
            DbgPrintEx(
              0x9Au,
              2u,
              "End of iteration. StartPage: %I64x, PageCount: %I64x, PagesToSkip: %I64x\n",
              v29,
              v23,
              v30);
            v22 = v38;
          }
        }
        v48 -= v21;
LABEL_46:
        ;
      }
      v12 = v37;
      v16 = v43;
      v15 = v44;
    }
    if ( v46 )
    {
      if ( a5 )
      {
        v31 = FsLibAppendExtent(a5, a2, v11 / v14);
        v10 = v31;
        if ( v31 < 0 )
        {
          v34[0] = v31;
          DbgPrintEx(
            0x9Au,
            0,
            "End: FAILED to add to ExtentsWithDanglingMdl. StartCluster: %I64x, ClusterCount: %I64x, Status: %08x\n",
            a2,
            v11 / v14,
            *(_QWORD *)v34);
LABEL_27:
          v12 = v37;
LABEL_59:
          v13 = v36;
          goto LABEL_60;
        }
        v12 = v37;
      }
      DbgPrintEx(0x9Au, 2u, "End: Dangling range: StartCluster: %I64x, ClusterCount: %I64x\n", a2, v11 / v14);
      goto LABEL_59;
    }
    if ( a6 )
    {
      v32 = FsLibAppendExtent(a6, a2, v11 / v14);
      v10 = v32;
      if ( v32 < 0 )
      {
        v34[0] = v32;
        DbgPrintEx(
          0x9Au,
          0,
          "End: FAILED to add to ExtentsWithoutDanglingMdl. StartCluster: %I64x, ClusterCount: %I64x, Status: %08x\n",
          a2,
          v11 / v14,
          *(_QWORD *)v34);
        goto LABEL_27;
      }
      v12 = v37;
    }
    DbgPrintEx(0x9Au, 2u, "End: Non-dangling range: StartCluster: %I64x, ClusterCount: %I64x\n", a2, v11 / v14);
    goto LABEL_59;
  }
  DbgPrintEx(
    0x9Au,
    2u,
    "FsLibGroupSubExtentsByDanglingMdl: Failed to allocate ExtentsDescriptor from the lookaside list.\n");
LABEL_7:
  v10 = -1073741670;
LABEL_60:
  if ( v13 )
    ExFreeToPagedLookasideList(&FsLibExtentsDescriptorLookasideList, v13);
  if ( v12 )
    ExFreeToNPagedLookasideList(&FsLibDsmBufferLookasideList, v12);
  if ( a7 )
    *a7 = v35;
  return v10;
}

```

## disassembly

```asm
0x140292d10  mov     r11, rsp
0x140292d13  mov     [r11+8], rcx
0x140292d17  push    rbx
0x140292d18  push    rsi
0x140292d19  push    rdi
0x140292d1a  push    r12
0x140292d1c  push    r13
0x140292d1e  push    r14
0x140292d20  push    r15
0x140292d22  sub     rsp, 0B0h
0x140292d29  mov     r14d, r9d
0x140292d2c  mov     rdi, r8
0x140292d2f  mov     rsi, rdx
0x140292d32  xor     eax, eax
0x140292d34  test    r8, r8
0x140292d37  jle     loc_140293427
0x140292d3d  mov     ebx, 0C0000001h
0x140292d42  mov     [r11+10h], al
0x140292d46  mov     r12d, eax
0x140292d49  mov     [rsp+0E8h+var_A0], rax
0x140292d4e  mov     r15d, eax
0x140292d51  mov     [rsp+0E8h+var_98], rax
0x140292d56  mov     [r11+18h], rax
0x140292d5a  mov     [rsp+0E8h+var_A8], al
0x140292d5e  cmp     [rsp+0E8h+arg_20], rax
0x140292d66  jnz     short loc_140292D80
0x140292d68  cmp     [rsp+0E8h+arg_28], rax
0x140292d70  jnz     short loc_140292D80
0x140292d72  cmp     [rsp+0E8h+arg_30], rax
0x140292d7a  jz      loc_140293427
0x140292d80  lea     rcx, FsLibExtentsDescriptorLookasideList; Lookaside
0x140292d87  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140292d8e  nop     dword ptr [rax+rax+00h]
0x140292d93  mov     r13, rax
0x140292d96  mov     [rsp+0E8h+var_A0], rax
0x140292d9b  test    rax, rax
0x140292d9e  jnz     short loc_140292DCB
0x140292da0  lea     r8, aFslibgroupsube_1; "FsLibGroupSubExtentsByDanglingMdl: Fail"...
0x140292da7  mov     edx, 2; Level
0x140292dac  mov     ecx, 9Ah; ComponentId
0x140292db1  call    cs:__imp_DbgPrintEx
0x140292db8  nop     dword ptr [rax+rax+00h]
0x140292dbd  mov     ebx, 0C000009Ah
0x140292dc2  mov     [rsp+0E8h+var_A4], ebx
0x140292dc6  jmp     loc_1402933DA
0x140292dcb  lea     rcx, FsLibDsmBufferLookasideList; Lookaside
0x140292dd2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140292dd9  nop     dword ptr [rax+rax+00h]
0x140292dde  mov     r15, rax
0x140292de1  mov     [rsp+0E8h+var_98], rax
0x140292de6  test    rax, rax
0x140292de9  jnz     short loc_140292DF4
0x140292deb  lea     r8, aFslibgroupsube_2; "FsLibGroupSubExtentsByDanglingMdl: Fail"...
0x140292df2  jmp     short loc_140292DA7
0x140292df4  mov     r13, r14
0x140292df7  shr     r13, 0Ch
0x140292dfb  mov     rdx, r13
0x140292dfe  imul    rdx, rsi
0x140292e02  mov     [rsp+0E8h+var_68], rdx
0x140292e0a  mov     [rsp+0E8h+var_48], rdx
0x140292e12  mov     rax, r13
0x140292e15  imul    rax, rdi
0x140292e19  mov     [rsp+0E8h+var_70], rax
0x140292e1e  mov     [rsp+0E8h+var_50], rax
0x140292e26  mov     edi, 9Ah
0x140292e2b  mov     r14d, 2
0x140292e31  mov     rcx, [rsp+0E8h+var_A0]
0x140292e36  test    rax, rax
0x140292e39  jle     loc_14029330C
0x140292e3f  mov     qword ptr [rcx], 0FFFCh
0x140292e46  mov     [rsp+0E8h+var_C8], rax
0x140292e4b  mov     r9, rdx
0x140292e4e  lea     r8, aFslibgroupsube; "FsLibGroupSubExtentsByDanglingMdl: Star"...
0x140292e55  mov     edx, r14d; Level
0x140292e58  mov     ecx, edi; ComponentId
0x140292e5a  call    cs:__imp_DbgPrintEx
0x140292e61  nop     dword ptr [rax+rax+00h]
0x140292e66  mov     r8, [rsp+0E8h+var_70]
0x140292e6b  shl     r8, 0Ch
0x140292e6f  mov     rdx, [rsp+0E8h+var_68]
0x140292e77  shl     rdx, 0Ch
0x140292e7b  mov     [rsp+0E8h+var_B0], 0FFFD0h; int
0x140292e83  mov     rax, [rsp+0E8h+var_A0]
0x140292e88  mov     [rsp+0E8h+var_B8], rax; __int64
0x140292e8d  mov     [rsp+0E8h+var_C0], 100000h; int
0x140292e95  mov     [rsp+0E8h+var_C8], r15; __int64
0x140292e9a  mov     r9d, 10000000h
0x140292ea0  mov     rcx, qword ptr [rsp+0E8h+arg_0]; int
0x140292ea8  call    FsLibGetAddressRangesForSingleVolumeExtent
0x140292ead  mov     ebx, eax
0x140292eaf  mov     [rsp+0E8h+var_A4], eax
0x140292eb3  test    eax, eax
0x140292eb5  jns     short loc_140292ED7
0x140292eb7  mov     r9d, eax
0x140292eba  lea     r8, aFslibgroupsube_0; "FsLibGroupSubExtentsByDanglingMdl: FsLi"...
0x140292ec1  mov     edx, r14d; Level
0x140292ec4  mov     ecx, edi; ComponentId
0x140292ec6  call    cs:__imp_DbgPrintEx
0x140292ecd  nop     dword ptr [rax+rax+00h]
0x140292ed2  jmp     loc_1402933D5
0x140292ed7  xor     eax, eax
0x140292ed9  mov     [rsp+0E8h+var_88], eax
0x140292edd  mov     rcx, [rsp+0E8h+var_A0]
0x140292ee2  cmp     eax, [rcx+4]
0x140292ee5  jnb     loc_1402932F5
0x140292eeb  add     rax, rax
0x140292eee  mov     rdx, [rcx+rax*8+8]
0x140292ef3  mov     [rsp+0E8h+var_78], rdx
0x140292ef8  mov     [rsp+0E8h+var_90], rdx
0x140292efd  mov     r15, [rcx+rax*8+10h]
0x140292f02  mov     rax, [rsp+0E8h+var_70]
0x140292f07  sub     rax, r15
0x140292f0a  mov     [rsp+0E8h+var_70], rax
0x140292f0f  mov     [rsp+0E8h+var_50], rax
0x140292f17  mov     rax, [rsp+0E8h+var_68]
0x140292f1f  add     rax, r15
0x140292f22  mov     [rsp+0E8h+var_68], rax
0x140292f2a  mov     [rsp+0E8h+var_48], rax
0x140292f32  mov     rax, [rsp+0E8h+arg_10]
0x140292f3a  mov     qword ptr [rsp+0E8h+var_C0], rax
0x140292f3f  mov     [rsp+0E8h+var_C8], r15
0x140292f44  mov     r9, rdx
0x140292f47  lea     r8, aStartpageI64xP; "StartPage: %I64x, PageCount: %I64x, Pag"...
0x140292f4e  mov     edx, r14d; Level
0x140292f51  mov     ecx, edi; ComponentId
0x140292f53  call    cs:__imp_DbgPrintEx
0x140292f5a  nop     dword ptr [rax+rax+00h]
0x140292f5f  mov     rcx, [rsp+0E8h+arg_10]
0x140292f67  cmp     r15, rcx
0x140292f6a  ja      short loc_140292F84
0x140292f6c  sub     rcx, r15
0x140292f6f  mov     [rsp+0E8h+arg_10], rcx
0x140292f77  mov     [rsp+0E8h+var_58], rcx
0x140292f7f  jmp     loc_1402932EA
0x140292f84  mov     rax, [rsp+0E8h+var_78]
0x140292f89  add     rax, rcx
0x140292f8c  mov     [rsp+0E8h+var_90], rax
0x140292f91  sub     r15, rcx
0x140292f94  xor     ecx, ecx
0x140292f96  mov     [rsp+0E8h+arg_10], rcx
0x140292f9e  mov     [rsp+0E8h+var_58], rcx
0x140292fa6  test    r15, r15
0x140292fa9  jz      loc_1402932EA
0x140292faf  mov     [rsp+0E8h+var_80], rax
0x140292fb4  xor     r8d, r8d
0x140292fb7  mov     rdx, r15
0x140292fba  mov     rcx, rax
0x140292fbd  call    cs:__imp_FsRtlIsExtentDangling
0x140292fc4  nop     dword ptr [rax+rax+00h]
0x140292fc9  mov     [rsp+0E8h+var_78], rax
0x140292fce  mov     r9, rax
0x140292fd1  lea     r8, aDanglingpageI6; "DanglingPage: %I64x\n"
0x140292fd8  mov     edx, r14d; Level
0x140292fdb  mov     ecx, edi; ComponentId
0x140292fdd  call    cs:__imp_DbgPrintEx
0x140292fe4  nop     dword ptr [rax+rax+00h]
0x140292fe9  mov     al, byte ptr [rsp+0E8h+arg_8]
0x140292ff0  test    al, al
0x140292ff2  jz      loc_14029310C
0x140292ff8  mov     rcx, [rsp+0E8h+var_78]
0x140292ffd  mov     rax, [rsp+0E8h+var_90]
0x140293002  sub     rcx, rax
0x140293005  cmp     rcx, r13
0x140293008  jnb     short loc_140293042
0x14029300a  add     r12, r13
0x14029300d  mov     [rsp+0E8h+var_60], r12
0x140293015  add     rax, r13
0x140293018  mov     [rsp+0E8h+var_80], rax
0x14029301d  mov     [rsp+0E8h+var_C8], rax
0x140293022  mov     r9, r12
0x140293025  lea     r8, aCase1UpdateSub; "Case 1: Update SubExtentPageCount: %I64"...
0x14029302c  mov     edx, r14d; Level
0x14029302f  mov     ecx, edi; ComponentId
0x140293031  call    cs:__imp_DbgPrintEx
0x140293038  nop     dword ptr [rax+rax+00h]
0x14029303d  jmp     loc_1402930FD
0x140293042  xor     edx, edx
0x140293044  mov     rax, r12
0x140293047  div     r13
0x14029304a  mov     r12, rax
0x14029304d  mov     rax, [rsp+0E8h+arg_20]
0x140293055  test    rax, rax
0x140293058  jz      short loc_14029309F
0x14029305a  mov     r8, r12
0x14029305d  mov     rdx, rsi
0x140293060  mov     rcx, rax
0x140293063  call    FsLibAppendExtent
0x140293068  mov     ebx, eax
0x14029306a  mov     [rsp+0E8h+var_A4], eax
0x14029306e  test    eax, eax
0x140293070  jns     short loc_14029309F
0x140293072  lea     r8, aCase2FailedToA; "Case 2: FAILED to add to ExtentsWithDan"...
0x140293079  mov     [rsp+0E8h+var_C0], eax
0x14029307d  mov     [rsp+0E8h+var_C8], r12
0x140293082  mov     r9, rsi
0x140293085  xor     edx, edx; Level
0x140293087  mov     ecx, edi; ComponentId
0x140293089  call    cs:__imp_DbgPrintEx
0x140293090  nop     dword ptr [rax+rax+00h]
0x140293095  mov     r15, [rsp+0E8h+var_98]
0x14029309a  jmp     loc_1402933D5
0x14029309f  mov     [rsp+0E8h+var_C8], r12
0x1402930a4  mov     r9, rsi
0x1402930a7  lea     r8, aCase2FoundDang; "Case 2: Found dangling MDL. StartCluste"...
0x1402930ae  mov     edx, r14d; Level
0x1402930b1  mov     ecx, edi; ComponentId
0x1402930b3  call    cs:__imp_DbgPrintEx
0x1402930ba  nop     dword ptr [rax+rax+00h]
0x1402930bf  add     rsi, r12
0x1402930c2  mov     [rsp+0E8h+var_40], rsi
0x1402930ca  xor     al, al
0x1402930cc  mov     byte ptr [rsp+0E8h+arg_8], al
0x1402930d3  mov     [rsp+0E8h+var_A7], al
0x1402930d7  xor     r12d, r12d
0x1402930da  mov     [rsp+0E8h+var_60], r12
0x1402930e2  mov     r9, rsi
0x1402930e5  lea     r8, aCase2UpdateSub; "Case 2: Update SubExtentClusterStart: %"...
0x1402930ec  mov     edx, r14d; Level
0x1402930ef  mov     ecx, edi; ComponentId
0x1402930f1  call    cs:__imp_DbgPrintEx
0x1402930f8  nop     dword ptr [rax+rax+00h]
0x1402930fd  mov     al, byte ptr [rsp+0E8h+arg_8]
0x140293104  test    al, al
0x140293106  jnz     loc_140293274
0x14029310c  mov     rcx, [rsp+0E8h+var_90]
0x140293111  lea     rax, [r15+rcx]
0x140293115  mov     rdx, [rsp+0E8h+var_78]
0x14029311a  cmp     rdx, rax
0x14029311d  jnb     loc_14029323C
0x140293123  mov     r8, rdx
0x140293126  sub     r8, rcx
0x140293129  add     r8, r12
0x14029312c  xor     edx, edx
0x14029312e  mov     rax, r8
0x140293131  div     r13
0x140293134  mov     r12, rax
0x140293137  mov     rcx, [rsp+0E8h+arg_28]
0x14029313f  cmp     [rsp+0E8h+var_A8], 0
0x140293144  jnz     short loc_14029317F
0x140293146  mov     [rsp+0E8h+var_A8], 1
0x14029314b  cmp     [rsp+0E8h+arg_20], 0
0x140293154  jnz     short loc_14029317F
0x140293156  test    rcx, rcx
0x140293159  jnz     short loc_14029317F
0x14029315b  lea     r9, [rax+rsi]
0x14029315f  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x140293163  lea     r8, aCase3FoundFirs; "Case 3: Found first dangling MDL.  Call"...
0x14029316a  xor     edx, edx; Level
0x14029316c  mov     ecx, edi; ComponentId
0x14029316e  call    cs:__imp_DbgPrintEx
0x140293175  nop     dword ptr [rax+rax+00h]
0x14029317a  jmp     loc_140293095
0x14029317f  xor     edx, edx
0x140293181  mov     rax, r8
0x140293184  div     r13
0x140293187  mov     rax, r13
0x14029318a  sub     rax, rdx
0x14029318d  mov     [rsp+0E8h+arg_8], rax
0x140293195  test    r12, r12
0x140293198  jle     short loc_1402931E8
0x14029319a  test    rcx, rcx
0x14029319d  jz      short loc_1402931C0
0x14029319f  mov     r8, r12
0x1402931a2  mov     rdx, rsi
0x1402931a5  call    FsLibAppendExtent
0x1402931aa  mov     ebx, eax
0x1402931ac  mov     [rsp+0E8h+var_A4], eax
0x1402931b0  test    eax, eax
0x1402931b2  jns     short loc_1402931C0
0x1402931b4  lea     r8, aCase3FailedToA; "Case 3: FAILED to add to ExtentsWithout"...
0x1402931bb  jmp     loc_140293079
0x1402931c0  mov     [rsp+0E8h+var_C8], r12
0x1402931c5  mov     r9, rsi
0x1402931c8  lea     r8, aCase3NonDangli; "Case 3: Non-dangling range: StartCluste"...
0x1402931cf  mov     edx, r14d; Level
0x1402931d2  mov     ecx, edi; ComponentId
0x1402931d4  call    cs:__imp_DbgPrintEx
0x1402931db  nop     dword ptr [rax+rax+00h]
0x1402931e0  mov     rax, [rsp+0E8h+arg_8]
0x1402931e8  add     rsi, r12
0x1402931eb  mov     [rsp+0E8h+var_40], rsi
0x1402931f3  mov     cl, 1
0x1402931f5  mov     byte ptr [rsp+0E8h+arg_8], cl
0x1402931fc  mov     [rsp+0E8h+var_A7], cl
0x140293200  mov     r12, r13
0x140293203  mov     [rsp+0E8h+var_60], r13
0x14029320b  add     rax, [rsp+0E8h+var_78]
0x140293210  mov     [rsp+0E8h+var_80], rax
0x140293215  mov     qword ptr [rsp+0E8h+var_C0], rax
0x14029321a  mov     [rsp+0E8h+var_C8], r13
0x14029321f  mov     r9, rsi
0x140293222  lea     r8, aCase3UpdateSub; "Case 3: Update SubExtentClusterStart: %"...
0x140293229  mov     edx, r14d; Level
0x14029322c  mov     ecx, edi; ComponentId
0x14029322e  call    cs:__imp_DbgPrintEx
0x140293235  nop     dword ptr [rax+rax+00h]
0x14029323a  jmp     short loc_140293274
0x14029323c  add     r12, r15
0x14029323f  mov     [rsp+0E8h+var_60], r12
0x140293247  mov     rax, [rsp+0E8h+var_80]
  ... truncated ...
```
