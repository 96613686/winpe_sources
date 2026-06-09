# CfGetPlaceholderRangeInfoForHydration

- ea: `0x18000f690`
- end: `0x18000fe8d`
- name: `CfGetPlaceholderRangeInfoForHydration`
- size: `2045`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000231e`
- `0x18000bb10`
- `0x18000c024`
- `0x18000f690`
- `0x180012c28`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000f800`
- `ntdll!RtlNtStatusToDosError` at `0x18000f897`
- `ntdll!RtlNtStatusToDosError` at `0x18000f92f`
- `ntdll!RtlNtStatusToDosError` at `0x18000f9c7`
- `ntdll!RtlNtStatusToDosError` at `0x18000fa5f`
- `ntdll!RtlNtStatusToDosError` at `0x18000fb03`
- `ntdll!RtlNtStatusToDosError` at `0x18000fba2`
- `ntdll!RtlNtStatusToDosError` at `0x18000fcc3`
- `ntdll!RtlNtStatusToDosError` at `0x18000fd6c`
- `ntdll!RtlNtStatusToDosError` at `0x18000f800`
- `ntdll!RtlNtStatusToDosError` at `0x18000f897`
- `ntdll!RtlNtStatusToDosError` at `0x18000f92f`
- `ntdll!RtlNtStatusToDosError` at `0x18000f9c7`
- `ntdll!RtlNtStatusToDosError` at `0x18000fa5f`
- `ntdll!RtlNtStatusToDosError` at `0x18000fb03`
- `ntdll!RtlNtStatusToDosError` at `0x18000fba2`
- `ntdll!RtlNtStatusToDosError` at `0x18000fcc3`
- `ntdll!RtlNtStatusToDosError` at `0x18000fd6c`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000f6d8`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000f6d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f726`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f726`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f744`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f744`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe69`
- `FLTLIB!FilterSendMessage` at `0x18000fdce`
- `FLTLIB!FilterSendMessage` at `0x18000fdce`

## string_xrefs

- `0x18000f8bd`: `SetCldMsgCommand failed`

## pseudocode

```c
__int64 __fastcall CfGetPlaceholderRangeInfoForHydration(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        _DWORD *a9)
{
  __int64 v12; // r13
  int v13; // r14d
  _DWORD *v14; // r15
  const wchar_t *v15; // rax
  HANDLE ProcessHeap; // rax
  NTSTATUS v17; // r12d
  NTSTATUS v18; // ecx
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // ecx
  signed int v22; // eax
  NTSTATUS v23; // ecx
  __int64 v24; // rcx
  __int64 v25; // rax
  signed int v26; // eax
  NTSTATUS v27; // ecx
  __int64 v28; // rcx
  __int64 v29; // rax
  signed int v30; // eax
  NTSTATUS v31; // ecx
  __int64 v32; // rcx
  __int64 v33; // rax
  signed int v34; // eax
  NTSTATUS v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // rax
  signed int v38; // eax
  NTSTATUS v39; // ecx
  __int64 v40; // rcx
  __int64 v41; // rax
  int v42; // ecx
  signed int v43; // eax
  NTSTATUS v44; // ecx
  __int64 v45; // rcx
  unsigned int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // rax
  signed int v49; // eax
  __int64 v50; // rcx
  unsigned int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rax
  NTSTATUS v54; // ecx
  __int64 v55; // rcx
  unsigned int v56; // eax
  __int64 v57; // rcx
  __int64 v58; // rax
  signed int v59; // eax
  __int64 v60; // rcx
  unsigned int v61; // eax
  __int64 v62; // rcx
  int v63; // eax
  signed int v64; // eax
  HANDLE v65; // rax
  int v67; // [rsp+40h] [rbp-61h] BYREF
  const wchar_t *v68; // [rsp+48h] [rbp-59h]
  __int64 v69; // [rsp+50h] [rbp-51h]
  __int64 v70; // [rsp+58h] [rbp-49h]
  __int64 v71; // [rsp+60h] [rbp-41h]
  int v72; // [rsp+68h] [rbp-39h]
  int OutBuffer; // [rsp+F0h] [rbp+4Fh] BYREF
  DWORD BytesReturned; // [rsp+F8h] [rbp+57h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+100h] [rbp+5Fh] BYREF
  int v76; // [rsp+108h] [rbp+67h]

  v76 = a4;
  BytesReturned = 0;
  OutBuffer = 0;
  memset_0(&v67, 0, 0x58u);
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v12 = CfpReferenceSyncRoot(a1);
  v13 = v12 == 0 ? 0x57 : 0;
  if ( !v12 )
    v13 |= 0x80070000;
  if ( v13 <= -1 )
  {
    v14 = 0;
    v15 = L"Syncroot not found with ConnectionKey";
    goto LABEL_115;
  }
  ProcessHeap = GetProcessHeap();
  v14 = HeapAlloc(ProcessHeap, 8u, 0x108u);
  v13 = v14 == 0 ? 8 : 0;
  if ( !v14 )
    v13 |= 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"Memory alloc failed for CldCmdPlaceholderRangeInfo";
    goto LABEL_115;
  }
  *(_QWORD *)v14 = 1886219331;
  v14[2] = 200;
  v14[3] = 1507328;
  memset_0(v14 + 4, 0, 0xB8u);
  v17 = -1073741811;
  if ( *((_WORD *)v14 + 7) )
  {
    v19 = (unsigned int)v14[2];
    if ( ((v19 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0x108 )
    {
      v21 = (v19 + 3) & 0xFFFFFFFC;
      v20 = v21;
      v14[2] = v21;
      v14[5] = v21;
      v18 = 0;
      v14[4] = 65543;
      *((_BYTE *)v14 + v20) = 1;
      ++v14[2];
    }
    else
    {
      v18 = -1073741789;
    }
  }
  else
  {
    v18 = -1073741811;
  }
  v22 = RtlNtStatusToDosError(v18);
  v13 = v22;
  if ( v22 > 0 )
    v13 = (unsigned __int16)v22 | 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"SetVersion failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) > 1u )
  {
    v24 = (unsigned int)v14[2];
    if ( ((v24 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0x108 )
    {
      v25 = ((_DWORD)v24 + 3) & 0xFFFFFFFC;
      v14[2] = v25;
      if ( *((_WORD *)v14 + 12) )
        *((_WORD *)v14 + 6) |= 1u;
      v14[6] = 131080;
      v23 = 0;
      v14[7] = v25;
      *(_WORD *)((char *)v14 + v25) = -12287;
      v14[2] += 2;
    }
    else
    {
      v23 = -1073741789;
    }
  }
  else
  {
    v23 = -1073741811;
  }
  v26 = RtlNtStatusToDosError(v23);
  v13 = v26;
  if ( v26 > 0 )
    v13 = (unsigned __int16)v26 | 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"SetCldMsgCommand failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) > 4u )
  {
    v28 = (unsigned int)v14[2];
    if ( ((v28 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x108 )
    {
      v29 = ((_DWORD)v28 + 3) & 0xFFFFFFFC;
      v14[2] = v29;
      if ( *((_WORD *)v14 + 24) )
        *((_WORD *)v14 + 6) |= 1u;
      v14[12] = 524294;
      v27 = 0;
      v14[13] = v29;
      *(_QWORD *)((char *)v14 + v29) = a1;
      v14[2] += 8;
    }
    else
    {
      v27 = -1073741789;
    }
  }
  else
  {
    v27 = -1073741811;
  }
  v30 = RtlNtStatusToDosError(v27);
  v13 = v30;
  if ( v30 > 0 )
    v13 = (unsigned __int16)v30 | 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"SetCldDsMsgSyncRootKey failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) > 7u )
  {
    v32 = (unsigned int)v14[2];
    if ( ((v32 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x108 )
    {
      v33 = ((_DWORD)v32 + 3) & 0xFFFFFFFC;
      v14[2] = v33;
      if ( *((_WORD *)v14 + 36) )
        *((_WORD *)v14 + 6) |= 1u;
      v14[18] = 524294;
      v31 = 0;
      v14[19] = v33;
      *(_QWORD *)((char *)v14 + v33) = a2;
      v14[2] += 8;
    }
    else
    {
      v31 = -1073741789;
    }
  }
  else
  {
    v31 = -1073741811;
  }
  v34 = RtlNtStatusToDosError(v31);
  v13 = v34;
  if ( v34 > 0 )
    v13 = (unsigned __int16)v34 | 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"SetCldDsMsgStreamKey Failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) > 0xDu )
  {
    v36 = (unsigned int)v14[2];
    if ( ((v36 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x108 )
    {
      v37 = ((_DWORD)v36 + 3) & 0xFFFFFFFC;
      v14[2] = v37;
      if ( *((_WORD *)v14 + 60) )
        *((_WORD *)v14 + 6) |= 1u;
      v14[30] = 524294;
      v35 = 0;
      v14[31] = v37;
      *(_QWORD *)((char *)v14 + v37) = a3;
      v14[2] += 8;
    }
    else
    {
      v35 = -1073741789;
    }
  }
  else
  {
    v35 = -1073741811;
  }
  v38 = RtlNtStatusToDosError(v35);
  v13 = v38;
  if ( v38 > 0 )
    v13 = (unsigned __int16)v38 | 0x80070000;
  if ( v13 <= -1 )
    goto LABEL_61;
  if ( *((_WORD *)v14 + 7) > 0xEu )
  {
    v40 = (unsigned int)v14[2];
    if ( ((v40 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0x108 )
    {
      v41 = ((_DWORD)v40 + 3) & 0xFFFFFFFC;
      v14[2] = v41;
      if ( *((_WORD *)v14 + 64) )
        *((_WORD *)v14 + 6) |= 1u;
      v42 = v76;
      v14[32] = 262154;
      v14[33] = v41;
      *(_DWORD *)((char *)v14 + v41) = v42;
      v39 = 0;
      v14[2] += 4;
    }
    else
    {
      v39 = -1073741789;
    }
  }
  else
  {
    v39 = -1073741811;
  }
  v43 = RtlNtStatusToDosError(v39);
  v13 = v43;
  if ( v43 > 0 )
    v13 = (unsigned __int16)v43 | 0x80070000;
  if ( v13 <= -1 )
  {
LABEL_61:
    v15 = L"SetCldDsMsgFileId Failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) > 0xFu )
  {
    v45 = (unsigned int)v14[2];
    if ( ((v45 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x108 )
    {
      v46 = (v45 + 3) & 0xFFFFFFFC;
      v14[2] = v46;
      if ( *((_WORD *)v14 + 68) )
        *((_WORD *)v14 + 6) |= 1u;
      v47 = v46;
      v14[35] = v46;
      v48 = a5;
      v14[34] = 524294;
      *(_QWORD *)((char *)v14 + v47) = v48;
      v44 = 0;
      v14[2] += 8;
    }
    else
    {
      v44 = -1073741789;
    }
  }
  else
  {
    v44 = -1073741811;
  }
  v49 = RtlNtStatusToDosError(v44);
  v13 = v49;
  if ( v49 > 0 )
    v13 = (unsigned __int16)v49 | 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"SetCldDsMsgStartingOffset Failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) <= 0x10u )
  {
    v13 = -1073741811;
LABEL_87:
    v15 = L"SetCldDsMsgRangeLength Failed";
    goto LABEL_115;
  }
  v50 = (unsigned int)v14[2];
  if ( ((v50 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 > 0x108 )
  {
    v13 = -1073741789;
    goto LABEL_87;
  }
  v51 = (v50 + 3) & 0xFFFFFFFC;
  v14[2] = v51;
  if ( *((_WORD *)v14 + 72) )
    *((_WORD *)v14 + 6) |= 1u;
  v14[37] = v51;
  v52 = v51;
  v53 = a6;
  v14[36] = 524294;
  *(_QWORD *)((char *)v14 + v52) = v53;
  v14[2] += 8;
  if ( *((_WORD *)v14 + 7) > 0x11u )
  {
    v55 = (unsigned int)v14[2];
    if ( ((v55 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x108 )
    {
      v56 = (v55 + 3) & 0xFFFFFFFC;
      v14[2] = v56;
      if ( *((_WORD *)v14 + 76) )
        *((_WORD *)v14 + 6) |= 1u;
      v57 = v56;
      v14[39] = v56;
      v58 = a7;
      v14[38] = 524299;
      *(_QWORD *)((char *)v14 + v57) = v58;
      v54 = 0;
      v14[2] += 8;
    }
    else
    {
      v54 = -1073741789;
    }
  }
  else
  {
    v54 = -1073741811;
  }
  v59 = RtlNtStatusToDosError(v54);
  v13 = v59;
  if ( v59 > 0 )
    v13 = (unsigned __int16)v59 | 0x80070000;
  if ( v13 > -1 )
  {
    if ( *((_WORD *)v14 + 7) > 0x12u )
    {
      v60 = (unsigned int)v14[2];
      if ( ((v60 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0x108 )
      {
        v61 = (v60 + 3) & 0xFFFFFFFC;
        v14[2] = v61;
        if ( *((_WORD *)v14 + 80) )
          *((_WORD *)v14 + 6) |= 1u;
        v14[41] = v61;
        v17 = 0;
        v62 = v61;
        v63 = a8;
        v14[40] = 262154;
        *(_DWORD *)((char *)v14 + v62) = v63;
        v14[2] += 4;
      }
      else
      {
        v17 = -1073741789;
      }
    }
    v64 = RtlNtStatusToDosError(v17);
    v13 = v64;
    if ( v64 > 0 )
      v13 = (unsigned __int16)v64 | 0x80070000;
    if ( v13 > -1 )
    {
      v14[1] = 0;
      *((_WORD *)v14 + 6) &= ~2u;
      v13 = FilterSendMessage(hPort, v14, 0x108u, &OutBuffer, 4u, &BytesReturned);
      if ( a9 )
        *a9 = OutBuffer;
      v15 = L"FilterSendMessage returned failure";
      if ( v13 > -1 )
        v15 = 0;
    }
    else
    {
      v15 = L"SetCldDsMsgInfoBufferLength Failed";
    }
  }
  else
  {
    v15 = L"SetCldDsMsgInfoBuffer Failed";
  }
LABEL_115:
  v68 = v15;
  v72 = v76;
  v69 = a1;
  v70 = a2;
  v71 = a3;
  TlmLogApiReliability(0x1Fu, 0, 0, 0, 0, UnbiasedTime, &v67, v13);
  if ( v12 )
    CfpReleaseSyncRoot(v12);
  if ( v14 )
  {
    v65 = GetProcessHeap();
    HeapFree(v65, 0, v14);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000f690  mov     [rsp-8+arg_18], r9d
0x18000f695  push    rbp
0x18000f696  push    rbx
0x18000f697  push    rsi
0x18000f698  push    rdi
0x18000f699  push    r12
0x18000f69b  push    r13
0x18000f69d  push    r14
0x18000f69f  push    r15
0x18000f6a1  lea     rbp, [rsp-7]
0x18000f6a6  sub     rsp, 0A8h
0x18000f6ad  xor     r14d, r14d
0x18000f6b0  mov     rdi, r8
0x18000f6b3  mov     rsi, rdx
0x18000f6b6  mov     [rbp+3Fh+BytesReturned], r14d
0x18000f6ba  mov     rbx, rcx
0x18000f6bd  mov     [rbp+3Fh+OutBuffer], r14d
0x18000f6c1  xor     edx, edx; Val
0x18000f6c3  lea     rcx, [rbp+3Fh+var_A0]; void *
0x18000f6c7  lea     r8d, [r14+58h]; Size
0x18000f6cb  call    memset_0
0x18000f6d0  lea     rcx, [rbp+3Fh+UnbiasedTime]; UnbiasedTime
0x18000f6d4  mov     [rbp+3Fh+UnbiasedTime], r14
0x18000f6d8  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000f6df  nop     dword ptr [rax+rax+00h]
0x18000f6e4  mov     rcx, rbx
0x18000f6e7  call    CfpReferenceSyncRoot
0x18000f6ec  mov     rcx, rax
0x18000f6ef  mov     r13, rax
0x18000f6f2  neg     rcx
0x18000f6f5  sbb     r14d, r14d
0x18000f6f8  xor     edx, edx
0x18000f6fa  not     r14d
0x18000f6fd  and     r14d, 57h
0x18000f701  mov     ecx, r14d
0x18000f704  or      ecx, 80070000h
0x18000f70a  test    rax, rax
0x18000f70d  cmovz   r14d, ecx
0x18000f711  cmp     r14d, 0FFFFFFFFh
0x18000f715  jg      short loc_18000F726
0x18000f717  mov     r15d, edx
0x18000f71a  lea     rax, aSyncrootNotFou_0; "Syncroot not found with ConnectionKey"
0x18000f721  jmp     loc_18000FDFF
0x18000f726  call    cs:__imp_GetProcessHeap
0x18000f72d  nop     dword ptr [rax+rax+00h]
0x18000f732  mov     r12d, 8
0x18000f738  mov     r8d, 108h; dwBytes
0x18000f73e  mov     rcx, rax; hHeap
0x18000f741  mov     edx, r12d; dwFlags
0x18000f744  call    cs:__imp_HeapAlloc
0x18000f74b  nop     dword ptr [rax+rax+00h]
0x18000f750  mov     r15, rax
0x18000f753  neg     rax
0x18000f756  sbb     r14d, r14d
0x18000f759  xor     edx, edx; Val
0x18000f75b  not     r14d
0x18000f75e  and     r14d, r12d
0x18000f761  mov     eax, r14d
0x18000f764  or      eax, 80070000h
0x18000f769  test    r15, r15
0x18000f76c  cmovz   r14d, eax
0x18000f770  cmp     r14d, 0FFFFFFFFh
0x18000f774  jg      short loc_18000F782
0x18000f776  lea     rax, aMemoryAllocFai; "Memory alloc failed for CldCmdPlacehold"...
0x18000f77d  jmp     loc_18000FDFF
0x18000f782  mov     r8d, 0B8h; Size
0x18000f788  mov     qword ptr [r15], 706D6C43h
0x18000f78f  lea     rcx, [r15+10h]; void *
0x18000f793  mov     dword ptr [r15+8], 0C8h
0x18000f79b  mov     dword ptr [r15+0Ch], 170000h
0x18000f7a3  call    memset_0
0x18000f7a8  xor     edx, edx
0x18000f7aa  mov     r12d, 0C000000Dh
0x18000f7b0  lea     r9d, [rdx+1]
0x18000f7b4  cmp     dx, [r15+0Eh]
0x18000f7b9  jb      short loc_18000F7C0
0x18000f7bb  mov     ecx, r12d
0x18000f7be  jmp     short loc_18000F800
0x18000f7c0  mov     ecx, [r15+8]
0x18000f7c4  lea     rax, [rcx+3]
0x18000f7c8  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000f7cc  add     rax, r9
0x18000f7cf  cmp     rax, 108h
0x18000f7d5  jbe     short loc_18000F7DE
0x18000f7d7  mov     ecx, 0C0000023h
0x18000f7dc  jmp     short loc_18000F800
0x18000f7de  lea     eax, [rcx+3]
0x18000f7e1  and     eax, 0FFFFFFFCh
0x18000f7e4  mov     ecx, eax
0x18000f7e6  mov     [r15+8], ecx
0x18000f7ea  mov     [r15+14h], ecx
0x18000f7ee  mov     ecx, edx; Status
0x18000f7f0  mov     dword ptr [r15+10h], 10007h
0x18000f7f8  mov     [rax+r15], r9b
0x18000f7fc  add     [r15+8], r9d
0x18000f800  call    cs:__imp_RtlNtStatusToDosError
0x18000f807  nop     dword ptr [rax+rax+00h]
0x18000f80c  xor     edx, edx
0x18000f80e  mov     r14d, eax
0x18000f811  test    eax, eax
0x18000f813  jle     short loc_18000F820
0x18000f815  movzx   r14d, ax
0x18000f819  or      r14d, 80070000h
0x18000f820  cmp     r14d, 0FFFFFFFFh
0x18000f824  jg      short loc_18000F832
0x18000f826  lea     rax, aSetversionFail; "SetVersion failed"
0x18000f82d  jmp     loc_18000FDFF
0x18000f832  mov     r9d, 1
0x18000f838  cmp     r9w, [r15+0Eh]
0x18000f83d  jb      short loc_18000F844
0x18000f83f  mov     ecx, r12d
0x18000f842  jmp     short loc_18000F897
0x18000f844  mov     ecx, [r15+8]
0x18000f848  mov     r8d, 2
0x18000f84e  lea     rax, [rcx+3]
0x18000f852  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000f856  add     rax, r8
0x18000f859  cmp     rax, 108h
0x18000f85f  jbe     short loc_18000F868
0x18000f861  mov     ecx, 0C0000023h
0x18000f866  jmp     short loc_18000F897
0x18000f868  lea     eax, [rcx+3]
0x18000f86b  and     eax, 0FFFFFFFCh
0x18000f86e  mov     [r15+8], eax
0x18000f872  cmp     [r15+18h], dx
0x18000f877  jz      short loc_18000F87E
0x18000f879  or      [r15+0Ch], r9w
0x18000f87e  mov     dword ptr [r15+18h], 20008h
0x18000f886  mov     ecx, edx; Status
0x18000f888  mov     [r15+1Ch], eax
0x18000f88c  mov     word ptr [rax+r15], 0D001h
0x18000f893  add     [r15+8], r8d
0x18000f897  call    cs:__imp_RtlNtStatusToDosError
0x18000f89e  nop     dword ptr [rax+rax+00h]
0x18000f8a3  xor     edx, edx
0x18000f8a5  mov     r14d, eax
0x18000f8a8  test    eax, eax
0x18000f8aa  jle     short loc_18000F8B7
0x18000f8ac  movzx   r14d, ax
0x18000f8b0  or      r14d, 80070000h
0x18000f8b7  cmp     r14d, 0FFFFFFFFh
0x18000f8bb  jg      short loc_18000F8C9
0x18000f8bd  lea     rax, aSetcldmsgcomma; "SetCldMsgCommand failed"
0x18000f8c4  jmp     loc_18000FDFF
0x18000f8c9  mov     eax, 4
0x18000f8ce  cmp     ax, [r15+0Eh]
0x18000f8d3  jb      short loc_18000F8DA
0x18000f8d5  mov     ecx, r12d
0x18000f8d8  jmp     short loc_18000F92F
0x18000f8da  mov     ecx, [r15+8]
0x18000f8de  mov     r8d, 8
0x18000f8e4  lea     rax, [rcx+3]
0x18000f8e8  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000f8ec  add     rax, r8
0x18000f8ef  cmp     rax, 108h
0x18000f8f5  jbe     short loc_18000F8FE
0x18000f8f7  mov     ecx, 0C0000023h
0x18000f8fc  jmp     short loc_18000F92F
0x18000f8fe  lea     eax, [rcx+3]
0x18000f901  and     eax, 0FFFFFFFCh
0x18000f904  mov     [r15+8], eax
0x18000f908  cmp     [r15+30h], dx
0x18000f90d  jz      short loc_18000F919
0x18000f90f  mov     ecx, 1
0x18000f914  or      [r15+0Ch], cx
0x18000f919  mov     dword ptr [r15+30h], 80006h
0x18000f921  mov     ecx, edx; Status
0x18000f923  mov     [r15+34h], eax
0x18000f927  mov     [rax+r15], rbx
0x18000f92b  add     [r15+8], r8d
0x18000f92f  call    cs:__imp_RtlNtStatusToDosError
0x18000f936  nop     dword ptr [rax+rax+00h]
0x18000f93b  xor     edx, edx
0x18000f93d  mov     r14d, eax
0x18000f940  test    eax, eax
0x18000f942  jle     short loc_18000F94F
0x18000f944  movzx   r14d, ax
0x18000f948  or      r14d, 80070000h
0x18000f94f  cmp     r14d, 0FFFFFFFFh
0x18000f953  jg      short loc_18000F961
0x18000f955  lea     rax, aSetclddsmsgsyn_2; "SetCldDsMsgSyncRootKey failed"
0x18000f95c  jmp     loc_18000FDFF
0x18000f961  mov     eax, 7
0x18000f966  cmp     ax, [r15+0Eh]
0x18000f96b  jb      short loc_18000F972
0x18000f96d  mov     ecx, r12d
0x18000f970  jmp     short loc_18000F9C7
0x18000f972  mov     ecx, [r15+8]
0x18000f976  mov     r8d, 8
0x18000f97c  lea     rax, [rcx+3]
0x18000f980  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000f984  add     rax, r8
0x18000f987  cmp     rax, 108h
0x18000f98d  jbe     short loc_18000F996
0x18000f98f  mov     ecx, 0C0000023h
0x18000f994  jmp     short loc_18000F9C7
0x18000f996  lea     eax, [rcx+3]
0x18000f999  and     eax, 0FFFFFFFCh
0x18000f99c  mov     [r15+8], eax
0x18000f9a0  cmp     [r15+48h], dx
0x18000f9a5  jz      short loc_18000F9B1
0x18000f9a7  mov     ecx, 1
0x18000f9ac  or      [r15+0Ch], cx
0x18000f9b1  mov     dword ptr [r15+48h], 80006h
0x18000f9b9  mov     ecx, edx; Status
0x18000f9bb  mov     [r15+4Ch], eax
0x18000f9bf  mov     [rax+r15], rsi
0x18000f9c3  add     [r15+8], r8d
0x18000f9c7  call    cs:__imp_RtlNtStatusToDosError
0x18000f9ce  nop     dword ptr [rax+rax+00h]
0x18000f9d3  xor     edx, edx
0x18000f9d5  mov     r14d, eax
0x18000f9d8  test    eax, eax
0x18000f9da  jle     short loc_18000F9E7
0x18000f9dc  movzx   r14d, ax
0x18000f9e0  or      r14d, 80070000h
0x18000f9e7  cmp     r14d, 0FFFFFFFFh
0x18000f9eb  jg      short loc_18000F9F9
0x18000f9ed  lea     rax, aSetclddsmsgstr; "SetCldDsMsgStreamKey Failed"
0x18000f9f4  jmp     loc_18000FDFF
0x18000f9f9  mov     eax, 0Dh
0x18000f9fe  cmp     ax, [r15+0Eh]
0x18000fa03  jb      short loc_18000FA0A
0x18000fa05  mov     ecx, r12d
0x18000fa08  jmp     short loc_18000FA5F
0x18000fa0a  mov     ecx, [r15+8]
0x18000fa0e  mov     r8d, 8
0x18000fa14  lea     rax, [rcx+3]
0x18000fa18  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000fa1c  add     rax, r8
0x18000fa1f  cmp     rax, 108h
0x18000fa25  jbe     short loc_18000FA2E
0x18000fa27  mov     ecx, 0C0000023h
0x18000fa2c  jmp     short loc_18000FA5F
0x18000fa2e  lea     eax, [rcx+3]
0x18000fa31  and     eax, 0FFFFFFFCh
0x18000fa34  mov     [r15+8], eax
0x18000fa38  cmp     [r15+78h], dx
0x18000fa3d  jz      short loc_18000FA49
0x18000fa3f  mov     ecx, 1
0x18000fa44  or      [r15+0Ch], cx
0x18000fa49  mov     dword ptr [r15+78h], 80006h
0x18000fa51  mov     ecx, edx; Status
0x18000fa53  mov     [r15+7Ch], eax
0x18000fa57  mov     [rax+r15], rdi
0x18000fa5b  add     [r15+8], r8d
0x18000fa5f  call    cs:__imp_RtlNtStatusToDosError
0x18000fa66  nop     dword ptr [rax+rax+00h]
0x18000fa6b  xor     edx, edx
0x18000fa6d  mov     r14d, eax
0x18000fa70  test    eax, eax
0x18000fa72  jle     short loc_18000FA7F
0x18000fa74  movzx   r14d, ax
0x18000fa78  or      r14d, 80070000h
0x18000fa7f  cmp     r14d, 0FFFFFFFFh
0x18000fa83  jg      short loc_18000FA91
0x18000fa85  lea     rax, aSetclddsmsgfil; "SetCldDsMsgFileId Failed"
0x18000fa8c  jmp     loc_18000FDFF
0x18000fa91  mov     eax, 0Eh
0x18000fa96  cmp     ax, [r15+0Eh]
0x18000fa9b  jb      short loc_18000FAA2
0x18000fa9d  mov     ecx, r12d
0x18000faa0  jmp     short loc_18000FB03
0x18000faa2  mov     ecx, [r15+8]
0x18000faa6  mov     r9d, 4
0x18000faac  lea     rax, [rcx+3]
0x18000fab0  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000fab4  add     rax, r9
0x18000fab7  cmp     rax, 108h
0x18000fabd  jbe     short loc_18000FAC6
0x18000fabf  mov     ecx, 0C0000023h
0x18000fac4  jmp     short loc_18000FB03
0x18000fac6  lea     eax, [rcx+3]
0x18000fac9  and     eax, 0FFFFFFFCh
0x18000facc  mov     [r15+8], eax
0x18000fad0  cmp     [r15+80h], dx
0x18000fad8  jz      short loc_18000FAE4
0x18000fada  mov     ecx, 1
0x18000fadf  or      [r15+0Ch], cx
0x18000fae4  mov     ecx, [rbp+3Fh+arg_18]
0x18000fae7  mov     dword ptr [r15+80h], 4000Ah
0x18000faf2  mov     [r15+84h], eax
0x18000faf9  mov     [rax+r15], ecx
0x18000fafd  mov     ecx, edx; Status
0x18000faff  add     [r15+8], r9d
0x18000fb03  call    cs:__imp_RtlNtStatusToDosError
0x18000fb0a  nop     dword ptr [rax+rax+00h]
0x18000fb0f  xor     edx, edx
0x18000fb11  mov     r14d, eax
0x18000fb14  test    eax, eax
0x18000fb16  jle     short loc_18000FB23
0x18000fb18  movzx   r14d, ax
0x18000fb1c  or      r14d, 80070000h
0x18000fb23  cmp     r14d, 0FFFFFFFFh
0x18000fb27  jle     loc_18000FA85
0x18000fb2d  mov     eax, 0Fh
0x18000fb32  cmp     ax, [r15+0Eh]
0x18000fb37  jb      short loc_18000FB3E
0x18000fb39  mov     ecx, r12d
0x18000fb3c  jmp     short loc_18000FBA2
  ... truncated ...
```
