# CfReportSyncStatus

- ea: `0x1800078d0`
- end: `0x180007f29`
- name: `CfReportSyncStatus`
- size: `1625`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001aa0`
- `0x18000231e`
- `0x1800046bc`
- `0x1800078d0`
- `0x180010294`
- `0x180012054`
- `0x180012630`
- `0x180012c28`
- `0x18001d0ac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800079d4`
- `ntdll!RtlNtStatusToDosError` at `0x180007b49`
- `ntdll!RtlNtStatusToDosError` at `0x180007bdf`
- `ntdll!RtlNtStatusToDosError` at `0x180007c7c`
- `ntdll!RtlNtStatusToDosError` at `0x180007d25`
- `ntdll!RtlNtStatusToDosError` at `0x180007dff`
- `ntdll!RtlNtStatusToDosError` at `0x1800079d4`
- `ntdll!RtlNtStatusToDosError` at `0x180007b49`
- `ntdll!RtlNtStatusToDosError` at `0x180007bdf`
- `ntdll!RtlNtStatusToDosError` at `0x180007c7c`
- `ntdll!RtlNtStatusToDosError` at `0x180007d25`
- `ntdll!RtlNtStatusToDosError` at `0x180007dff`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007959`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007959`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ec5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ec5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007a8e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007a8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ed9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ed9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ef0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ef0`
- `FLTLIB!FilterSendMessage` at `0x180007e5a`
- `FLTLIB!FilterSendMessage` at `0x180007e5a`

## string_xrefs

- `0x180007c02`: `SetCldMsgCommand Failed`
- `0x1800079f4`: `CfpCreateFile Failed`
- `0x180007989`: `SyncRootPath Can't be NULL`

## pseudocode

```c
__int64 __fastcall CfReportSyncStatus(__int64 a1, char *a2)
{
  char *v2; // r15
  const WCHAR *v4; // rsi
  const WCHAR *v5; // r14
  _DWORD *v6; // rdi
  int SyncRootInfoByHandle; // ebx
  const wchar_t *v8; // rax
  __int64 v9; // rdx
  NTSTATUS v10; // eax
  signed int v11; // eax
  DWORD v12; // r12d
  HANDLE ProcessHeap; // rax
  NTSTATUS v14; // r15d
  NTSTATUS v15; // ecx
  __int64 v16; // rcx
  unsigned int v17; // ecx
  signed int v18; // eax
  NTSTATUS v19; // ecx
  __int64 v20; // rcx
  __int64 v21; // rax
  signed int v22; // eax
  NTSTATUS v23; // ecx
  __int64 v24; // rcx
  HANDLE v25; // rdx
  __int64 v26; // rax
  signed int v27; // eax
  NTSTATUS v28; // ecx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rax
  signed int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  size_t v35; // r8
  __int64 v36; // rcx
  char *v37; // rcx
  signed int v38; // eax
  HANDLE v39; // rax
  __int64 dwOutBufferSize; // [rsp+20h] [rbp-E0h]
  __int64 v42; // [rsp+30h] [rbp-D0h]
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  DWORD BytesReturned; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h]
  __int64 v47; // [rsp+70h] [rbp-90h]
  unsigned __int64 UnbiasedTime; // [rsp+78h] [rbp-88h] BYREF
  int v49; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v50; // [rsp+88h] [rbp-78h]
  __int64 v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  bool v53; // [rsp+A0h] [rbp-60h]
  _BYTE v54[4]; // [rsp+E0h] [rbp-20h] BYREF
  char v55; // [rsp+E4h] [rbp-1Ch] BYREF
  char v56; // [rsp+2E4h] [rbp+1E4h] BYREF

  v2 = a2;
  v47 = a1;
  hObject = (HANDLE)-1LL;
  UnbiasedTime = 0;
  memset_0(v54, 0, 0x404u);
  v46 = 0;
  BytesReturned = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  memset_0(&v49, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  SyncRootInfoByHandle = a1 == 0 ? 0x57 : 0;
  if ( !v47 )
    SyncRootInfoByHandle |= 0x80070000;
  if ( SyncRootInfoByHandle <= -1 )
  {
    v8 = L"SyncRootPath Can't be NULL";
    goto LABEL_90;
  }
  SyncRootInfoByHandle = GlobalPortInit(1);
  if ( SyncRootInfoByHandle <= -1 )
  {
    v8 = L"GlobalPortInit Failed";
    goto LABEL_90;
  }
  v10 = CfpCreateFile(v47, v9, 0, 7u, dwOutBufferSize, 0x21u, v42, &hObject);
  v11 = RtlNtStatusToDosError(v10);
  SyncRootInfoByHandle = v11;
  if ( v11 > 0 )
    SyncRootInfoByHandle = (unsigned __int16)v11 | 0x80070000;
  if ( SyncRootInfoByHandle <= -1 )
  {
    v8 = L"CfpCreateFile Failed";
    goto LABEL_90;
  }
  SyncRootInfoByHandle = CfpGetSyncRootInfoByHandle(hObject, 0);
  if ( SyncRootInfoByHandle <= -1 )
  {
    v8 = L"CfpGetSyncRootInfoByHandle Failed";
    goto LABEL_90;
  }
  v5 = (const WCHAR *)&v56;
  v4 = (const WCHAR *)&v55;
  v12 = 224;
  if ( (int)CfpGetSyncRootInfoByHandle(hObject, 0) < 0 )
  {
    v5 = 0;
    v4 = 0;
  }
  if ( v2 )
    v12 = *(_DWORD *)v2 + 224;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, v12);
  SyncRootInfoByHandle = v6 == 0 ? 8 : 0;
  if ( !v6 )
    SyncRootInfoByHandle |= 0x80070000;
  if ( SyncRootInfoByHandle > -1 )
  {
    *(_QWORD *)v6 = 1886219331;
    v6[2] = 200;
    v6[3] = 1507328;
    memset_0(v6 + 4, 0, 0xB8u);
    if ( v12 < 0x18 )
    {
      v14 = -1073741789;
LABEL_23:
      v15 = -1073741789;
      goto LABEL_28;
    }
    v14 = -1073741789;
    if ( *((_WORD *)v6 + 7) )
    {
      v16 = (unsigned int)v6[2];
      if ( ((v16 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 > v12 )
        goto LABEL_23;
      v17 = (v16 + 3) & 0xFFFFFFFC;
      v6[2] = v17;
      v6[5] = v17;
      v6[4] = 65543;
      *((_BYTE *)v6 + v17) = 1;
      ++v6[2];
      v15 = 0;
    }
    else
    {
      v15 = -1073741811;
    }
LABEL_28:
    v18 = RtlNtStatusToDosError(v15);
    SyncRootInfoByHandle = v18;
    if ( v18 > 0 )
      SyncRootInfoByHandle = (unsigned __int16)v18 | 0x80070000;
    if ( SyncRootInfoByHandle <= -1 )
    {
      v8 = L"SetVersion Failed";
      goto LABEL_89;
    }
    if ( v12 < 0x18 )
      goto LABEL_33;
    if ( *((_WORD *)v6 + 7) > 1u )
    {
      if ( v12 < 0x20 || (v20 = (unsigned int)v6[2], ((v20 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 > v12) )
      {
LABEL_33:
        v19 = -1073741789;
        goto LABEL_41;
      }
      v21 = ((_DWORD)v20 + 3) & 0xFFFFFFFC;
      v6[2] = v21;
      if ( *((_WORD *)v6 + 12) )
        *((_WORD *)v6 + 6) |= 1u;
      v6[6] = 131080;
      v19 = 0;
      v6[7] = v21;
      *(_WORD *)((char *)v6 + v21) = 7;
      v6[2] += 2;
    }
    else
    {
      v19 = -1073741811;
    }
LABEL_41:
    v22 = RtlNtStatusToDosError(v19);
    SyncRootInfoByHandle = v22;
    if ( v22 > 0 )
      SyncRootInfoByHandle = (unsigned __int16)v22 | 0x80070000;
    if ( SyncRootInfoByHandle <= -1 )
    {
      v8 = L"SetCldMsgCommand Failed";
      goto LABEL_89;
    }
    if ( v12 < 0x18 )
      goto LABEL_46;
    if ( *((_WORD *)v6 + 7) > 2u )
    {
      if ( v12 < 0x28 || (v24 = (unsigned int)v6[2], ((v24 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 > v12) )
      {
LABEL_46:
        v23 = -1073741789;
        goto LABEL_54;
      }
      v25 = hObject;
      v26 = ((_DWORD)v24 + 3) & 0xFFFFFFFC;
      v6[2] = v26;
      if ( *((_WORD *)v6 + 16) )
        *((_WORD *)v6 + 6) |= 1u;
      v6[8] = 524299;
      v23 = 0;
      v6[9] = v26;
      *(_QWORD *)((char *)v6 + v26) = v25;
      v6[2] += 8;
    }
    else
    {
      v23 = -1073741811;
    }
LABEL_54:
    v27 = RtlNtStatusToDosError(v23);
    SyncRootInfoByHandle = v27;
    if ( v27 > 0 )
      SyncRootInfoByHandle = (unsigned __int16)v27 | 0x80070000;
    if ( SyncRootInfoByHandle <= -1 )
    {
      v8 = L"SetCldDsMsgSyncRoot Failed";
      goto LABEL_89;
    }
    if ( v12 >= 0x18 )
    {
      if ( *((_WORD *)v6 + 7) <= 0x16u )
      {
        v28 = -1073741811;
        goto LABEL_67;
      }
      if ( v12 >= 0xC8 )
      {
        v29 = (unsigned int)v6[2];
        if ( ((v29 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= v12 )
        {
          v30 = v46;
          v31 = ((_DWORD)v29 + 3) & 0xFFFFFFFC;
          v6[2] = v31;
          if ( *((_WORD *)v6 + 96) )
            *((_WORD *)v6 + 6) |= 1u;
          v6[48] = 524294;
          v28 = 0;
          v6[49] = v31;
          *(_QWORD *)((char *)v6 + v31) = v30;
          v6[2] += 8;
          goto LABEL_67;
        }
      }
    }
    v28 = -1073741789;
LABEL_67:
    v32 = RtlNtStatusToDosError(v28);
    SyncRootInfoByHandle = v32;
    if ( v32 > 0 )
      SyncRootInfoByHandle = (unsigned __int16)v32 | 0x80070000;
    if ( SyncRootInfoByHandle
      && (TlmChk(v33, 4202, "CfReportSyncStatus", (unsigned int)SyncRootInfoByHandle), SyncRootInfoByHandle < 0) )
    {
      v8 = L"SetCldDsMsgSyncRootFileId Failed";
    }
    else
    {
      v52 = v46;
      if ( !a2 )
        goto LABEL_87;
      if ( v12 >= 0x18 )
      {
        if ( *((_WORD *)v6 + 7) > 9u )
        {
          if ( v12 >= 0x60 )
          {
            v34 = (unsigned int)v6[2];
            v35 = *(unsigned __int16 *)a2;
            if ( v35 + ((v34 + 3) & 0xFFFFFFFFFFFFFFFCuLL) <= v12 )
            {
              if ( *((_WORD *)v6 + 44) )
                *((_WORD *)v6 + 6) |= 1u;
              v36 = ((_DWORD)v34 + 3) & 0xFFFFFFFC;
              v6[2] = v36;
              v6[23] = v36;
              v37 = (char *)v6 + v36;
              *((_WORD *)v6 + 44) = 17;
              *((_WORD *)v6 + 45) = v35;
              if ( v37 != a2 )
                memcpy_0(v37, a2, v35);
              v14 = 0;
              v6[2] += *((unsigned __int16 *)v6 + 45);
            }
          }
        }
        else
        {
          v14 = -1073741811;
        }
      }
      v38 = RtlNtStatusToDosError(v14);
      SyncRootInfoByHandle = v38;
      if ( v38 > 0 )
        SyncRootInfoByHandle = (unsigned __int16)v38 | 0x80070000;
      if ( SyncRootInfoByHandle <= -1 )
      {
        v8 = L"SetCldDsMsgSyncStatus Failed";
      }
      else
      {
LABEL_87:
        v6[1] = 0;
        *((_WORD *)v6 + 6) &= ~2u;
        SyncRootInfoByHandle = FilterSendMessage(hPort, v6, v12, 0, 0, &BytesReturned);
        v8 = L"FilterSendMessage Failed";
        if ( SyncRootInfoByHandle > -1 )
          v8 = 0;
      }
    }
    goto LABEL_89;
  }
  v8 = L"HeapAlloc CldCmdReportStatus failed";
LABEL_89:
  v2 = a2;
LABEL_90:
  v50 = v8;
  v53 = v2 != 0;
  v51 = v47;
  TlmLogApiReliability(0x1Du, 0, v47, v4, v5, UnbiasedTime, &v49, SyncRootInfoByHandle);
  if ( v6 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v6);
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return (unsigned int)SyncRootInfoByHandle;
}

```

## disassembly

```asm
0x1800078d0  mov     [rsp-8+arg_10], rbx
0x1800078d5  push    rbp
0x1800078d6  push    rsi
0x1800078d7  push    rdi
0x1800078d8  push    r12
0x1800078da  push    r13
0x1800078dc  push    r14
0x1800078de  push    r15
0x1800078e0  lea     rbp, [rsp-400h]
0x1800078e8  sub     rsp, 500h
0x1800078ef  mov     rax, cs:__security_cookie
0x1800078f6  xor     rax, rsp
0x1800078f9  mov     [rbp+430h+var_40], rax
0x180007900  mov     r15, rdx
0x180007903  mov     [rsp+530h+Src], rdx
0x180007908  mov     rbx, rcx
0x18000790b  mov     [rsp+530h+var_4C0], rcx
0x180007910  xor     r13d, r13d
0x180007913  mov     [rsp+530h+hObject], 0FFFFFFFFFFFFFFFFh
0x18000791c  xor     edx, edx; Val
0x18000791e  mov     [rsp+530h+UnbiasedTime], r13
0x180007923  lea     rcx, [rbp+430h+var_450]; void *
0x180007927  mov     r8d, 404h; Size
0x18000792d  call    memset_0
0x180007932  xor     edx, edx; Val
0x180007934  mov     [rsp+530h+var_4C8], r13
0x180007939  lea     r8d, [r13+58h]; Size
0x18000793d  mov     [rsp+530h+BytesReturned], r13d
0x180007942  lea     rcx, [rbp+430h+var_4B0]; void *
0x180007946  mov     esi, r13d
0x180007949  mov     r14d, r13d
0x18000794c  mov     edi, r13d
0x18000794f  call    memset_0
0x180007954  lea     rcx, [rsp+530h+UnbiasedTime]; UnbiasedTime
0x180007959  call    cs:__imp_QueryUnbiasedInterruptTime
0x180007960  nop     dword ptr [rax+rax+00h]
0x180007965  mov     r12, [rsp+530h+var_4C0]
0x18000796a  mov     rax, rbx
0x18000796d  neg     rax
0x180007970  sbb     ebx, ebx
0x180007972  not     ebx
0x180007974  and     ebx, 57h
0x180007977  mov     eax, ebx
0x180007979  or      eax, 80070000h
0x18000797e  test    r12, r12
0x180007981  cmovz   ebx, eax
0x180007984  cmp     ebx, 0FFFFFFFFh
0x180007987  jg      short loc_180007995
0x180007989  lea     rax, aSyncrootpathCa_0; "SyncRootPath Can't be NULL"
0x180007990  jmp     loc_180007E7C
0x180007995  mov     cl, 1
0x180007997  call    GlobalPortInit
0x18000799c  mov     ebx, eax
0x18000799e  cmp     eax, 0FFFFFFFFh
0x1800079a1  jg      short loc_1800079AF
0x1800079a3  lea     rax, aGlobalportinit; "GlobalPortInit Failed"
0x1800079aa  jmp     loc_180007E7C
0x1800079af  lea     rax, [rsp+530h+hObject]
0x1800079b4  mov     r9d, 7
0x1800079ba  mov     [rsp+530h+var_4F8], rax
0x1800079bf  xor     r8d, r8d
0x1800079c2  mov     rcx, r12
0x1800079c5  mov     dword ptr [rsp+530h+lpBytesReturned], 21h ; '!'
0x1800079cd  call    CfpCreateFile
0x1800079d2  mov     ecx, eax; Status
0x1800079d4  call    cs:__imp_RtlNtStatusToDosError
0x1800079db  nop     dword ptr [rax+rax+00h]
0x1800079e0  mov     ebx, eax
0x1800079e2  test    eax, eax
0x1800079e4  jle     short loc_1800079EF
0x1800079e6  movzx   ebx, ax
0x1800079e9  or      ebx, 80070000h
0x1800079ef  cmp     ebx, 0FFFFFFFFh
0x1800079f2  jg      short loc_180007A00
0x1800079f4  lea     rax, aCfpcreatefileF; "CfpCreateFile Failed"
0x1800079fb  jmp     loc_180007E7C
0x180007a00  mov     rcx, [rsp+530h+hObject]; hFile
0x180007a05  lea     r8, [rsp+530h+var_4C8]
0x180007a0a  mov     r9d, 8
0x180007a10  mov     qword ptr [rsp+530h+dwOutBufferSize], r13; __int64
0x180007a15  xor     edx, edx
0x180007a17  call    CfpGetSyncRootInfoByHandle
0x180007a1c  mov     ebx, eax
0x180007a1e  cmp     eax, 0FFFFFFFFh
0x180007a21  jg      short loc_180007A2F
0x180007a23  lea     rax, aCfpgetsyncroot; "CfpGetSyncRootInfoByHandle Failed"
0x180007a2a  jmp     loc_180007E7C
0x180007a2f  mov     rcx, [rsp+530h+hObject]; hFile
0x180007a34  lea     r8, [rbp+430h+var_450]
0x180007a38  mov     r9d, 404h
0x180007a3e  mov     qword ptr [rsp+530h+dwOutBufferSize], r13; __int64
0x180007a43  mov     edx, 2
0x180007a48  call    CfpGetSyncRootInfoByHandle
0x180007a4d  test    eax, eax
0x180007a4f  lea     r14, [rbp+430h+var_24C]
0x180007a56  lea     rsi, [rbp+430h+var_44C]
0x180007a5a  mov     r12d, 0E0h
0x180007a60  cmovs   r14, r13
0x180007a64  cmovs   rsi, r13
0x180007a68  test    r15, r15
0x180007a6b  jz      short loc_180007A70
0x180007a6d  add     r12d, [r15]
0x180007a70  mov     r13d, r12d
0x180007a73  call    cs:__imp_GetProcessHeap
0x180007a7a  nop     dword ptr [rax+rax+00h]
0x180007a7f  mov     r15d, 8
0x180007a85  mov     r8d, r12d; dwBytes
0x180007a88  mov     rcx, rax; hHeap
0x180007a8b  mov     edx, r15d; dwFlags
0x180007a8e  call    cs:__imp_HeapAlloc
0x180007a95  nop     dword ptr [rax+rax+00h]
0x180007a9a  mov     rdi, rax
0x180007a9d  neg     rax
0x180007aa0  sbb     ebx, ebx
0x180007aa2  not     ebx
0x180007aa4  and     ebx, r15d
0x180007aa7  xor     r15d, r15d
0x180007aaa  mov     eax, ebx
0x180007aac  or      eax, 80070000h
0x180007ab1  test    rdi, rdi
0x180007ab4  cmovz   ebx, eax
0x180007ab7  cmp     ebx, 0FFFFFFFFh
0x180007aba  jg      short loc_180007AC8
0x180007abc  lea     rax, aHeapallocCldcm; "HeapAlloc CldCmdReportStatus failed"
0x180007ac3  jmp     loc_180007E77
0x180007ac8  xor     edx, edx; Val
0x180007aca  mov     qword ptr [rdi], 706D6C43h
0x180007ad1  mov     r8d, 0B8h; Size
0x180007ad7  mov     dword ptr [rdi+8], 0C8h
0x180007ade  lea     rcx, [rdi+10h]; void *
0x180007ae2  mov     dword ptr [rdi+0Ch], 170000h
0x180007ae9  call    memset_0
0x180007aee  cmp     r12d, 18h
0x180007af2  jnb     short loc_180007AFF
0x180007af4  mov     r15d, 0C0000023h
0x180007afa  mov     ecx, r15d
0x180007afd  jmp     short loc_180007B49
0x180007aff  mov     eax, r15d
0x180007b02  mov     r15d, 0C0000023h
0x180007b08  cmp     ax, [rdi+0Eh]
0x180007b0c  jb      short loc_180007B14
0x180007b0e  lea     ecx, [r15-16h]
0x180007b12  jmp     short loc_180007B49
0x180007b14  mov     ecx, [rdi+8]
0x180007b17  mov     edx, 1
0x180007b1c  lea     rax, [rcx+3]
0x180007b20  and     rax, 0FFFFFFFFFFFFFFFCh
0x180007b24  add     rax, rdx
0x180007b27  cmp     rax, r13
0x180007b2a  ja      short loc_180007AFA
0x180007b2c  lea     eax, [rcx+3]
0x180007b2f  and     eax, 0FFFFFFFCh
0x180007b32  mov     ecx, eax
0x180007b34  mov     [rdi+8], ecx
0x180007b37  mov     [rdi+14h], ecx
0x180007b3a  mov     dword ptr [rdi+10h], 10007h
0x180007b41  mov     [rax+rdi], dl
0x180007b44  add     [rdi+8], edx
0x180007b47  xor     ecx, ecx; Status
0x180007b49  call    cs:__imp_RtlNtStatusToDosError
0x180007b50  nop     dword ptr [rax+rax+00h]
0x180007b55  xor     edx, edx
0x180007b57  mov     ebx, eax
0x180007b59  test    eax, eax
0x180007b5b  jle     short loc_180007B66
0x180007b5d  movzx   ebx, ax
0x180007b60  or      ebx, 80070000h
0x180007b66  cmp     ebx, 0FFFFFFFFh
0x180007b69  jg      short loc_180007B77
0x180007b6b  lea     rax, aSetversionFail_0; "SetVersion Failed"
0x180007b72  jmp     loc_180007E77
0x180007b77  cmp     r12d, 18h
0x180007b7b  jnb     short loc_180007B82
0x180007b7d  mov     ecx, r15d
0x180007b80  jmp     short loc_180007BDF
0x180007b82  mov     r9d, 1
0x180007b88  cmp     r9w, [rdi+0Eh]
0x180007b8d  jb      short loc_180007B96
0x180007b8f  mov     ecx, 0C000000Dh
0x180007b94  jmp     short loc_180007BDF
0x180007b96  cmp     r12d, 20h ; ' '
0x180007b9a  jb      short loc_180007B7D
0x180007b9c  mov     ecx, [rdi+8]
0x180007b9f  mov     r8d, 2
0x180007ba5  lea     rax, [rcx+3]
0x180007ba9  and     rax, 0FFFFFFFFFFFFFFFCh
0x180007bad  add     rax, r8
0x180007bb0  cmp     rax, r13
0x180007bb3  ja      short loc_180007B7D
0x180007bb5  lea     eax, [rcx+3]
0x180007bb8  and     eax, 0FFFFFFFCh
0x180007bbb  mov     [rdi+8], eax
0x180007bbe  cmp     [rdi+18h], dx
0x180007bc2  jz      short loc_180007BC9
0x180007bc4  or      [rdi+0Ch], r9w
0x180007bc9  mov     dword ptr [rdi+18h], 20008h
0x180007bd0  mov     ecx, edx; Status
0x180007bd2  mov     [rdi+1Ch], eax
0x180007bd5  mov     word ptr [rax+rdi], 7
0x180007bdb  add     [rdi+8], r8d
0x180007bdf  call    cs:__imp_RtlNtStatusToDosError
0x180007be6  nop     dword ptr [rax+rax+00h]
0x180007beb  xor     r8d, r8d
0x180007bee  mov     ebx, eax
0x180007bf0  test    eax, eax
0x180007bf2  jle     short loc_180007BFD
0x180007bf4  movzx   ebx, ax
0x180007bf7  or      ebx, 80070000h
0x180007bfd  cmp     ebx, 0FFFFFFFFh
0x180007c00  jg      short loc_180007C0E
0x180007c02  lea     rax, aSetcldmsgcomma_0; "SetCldMsgCommand Failed"
0x180007c09  jmp     loc_180007E77
0x180007c0e  cmp     r12d, 18h
0x180007c12  jnb     short loc_180007C19
0x180007c14  mov     ecx, r15d
0x180007c17  jmp     short loc_180007C7C
0x180007c19  mov     eax, 2
0x180007c1e  cmp     ax, [rdi+0Eh]
0x180007c22  jb      short loc_180007C2B
0x180007c24  mov     ecx, 0C000000Dh
0x180007c29  jmp     short loc_180007C7C
0x180007c2b  cmp     r12d, 28h ; '('
0x180007c2f  jb      short loc_180007C14
0x180007c31  mov     ecx, [rdi+8]
0x180007c34  mov     r9d, 8
0x180007c3a  lea     rax, [rcx+3]
0x180007c3e  and     rax, 0FFFFFFFFFFFFFFFCh
0x180007c42  add     rax, r9
0x180007c45  cmp     rax, r13
0x180007c48  ja      short loc_180007C14
0x180007c4a  mov     rdx, [rsp+530h+hObject]
0x180007c4f  lea     eax, [rcx+3]
0x180007c52  and     eax, 0FFFFFFFCh
0x180007c55  mov     [rdi+8], eax
0x180007c58  cmp     [rdi+20h], r8w
0x180007c5d  jz      short loc_180007C67
0x180007c5f  lea     ecx, [r9-7]
0x180007c63  or      [rdi+0Ch], cx
0x180007c67  mov     dword ptr [rdi+20h], 8000Bh
0x180007c6e  mov     ecx, r8d; Status
0x180007c71  mov     [rdi+24h], eax
0x180007c74  mov     [rax+rdi], rdx
0x180007c78  add     [rdi+8], r9d
0x180007c7c  call    cs:__imp_RtlNtStatusToDosError
0x180007c83  nop     dword ptr [rax+rax+00h]
0x180007c88  xor     r8d, r8d
0x180007c8b  mov     ebx, eax
0x180007c8d  test    eax, eax
0x180007c8f  jle     short loc_180007C9A
0x180007c91  movzx   ebx, ax
0x180007c94  or      ebx, 80070000h
0x180007c9a  cmp     ebx, 0FFFFFFFFh
0x180007c9d  jg      short loc_180007CAB
0x180007c9f  lea     rax, aSetclddsmsgsyn_0; "SetCldDsMsgSyncRoot Failed"
0x180007ca6  jmp     loc_180007E77
0x180007cab  cmp     r12d, 18h
0x180007caf  jnb     short loc_180007CB6
0x180007cb1  mov     ecx, r15d
0x180007cb4  jmp     short loc_180007D25
0x180007cb6  mov     eax, 16h
0x180007cbb  cmp     ax, [rdi+0Eh]
0x180007cbf  jb      short loc_180007CC8
0x180007cc1  mov     ecx, 0C000000Dh
0x180007cc6  jmp     short loc_180007D25
0x180007cc8  cmp     r12d, 0C8h
0x180007ccf  jb      short loc_180007CB1
0x180007cd1  mov     ecx, [rdi+8]
0x180007cd4  mov     r9d, 8
0x180007cda  lea     rax, [rcx+3]
0x180007cde  and     rax, 0FFFFFFFFFFFFFFFCh
0x180007ce2  add     rax, r9
0x180007ce5  cmp     rax, r13
0x180007ce8  ja      short loc_180007CB1
0x180007cea  mov     rdx, [rsp+530h+var_4C8]
0x180007cef  lea     eax, [rcx+3]
0x180007cf2  and     eax, 0FFFFFFFCh
0x180007cf5  mov     [rdi+8], eax
0x180007cf8  cmp     [rdi+0C0h], r8w
0x180007d00  jz      short loc_180007D0A
0x180007d02  lea     ecx, [r9-7]
0x180007d06  or      [rdi+0Ch], cx
0x180007d0a  mov     dword ptr [rdi+0C0h], 80006h
0x180007d14  mov     ecx, r8d; Status
0x180007d17  mov     [rdi+0C4h], eax
0x180007d1d  mov     [rax+rdi], rdx
0x180007d21  add     [rdi+8], r9d
0x180007d25  call    cs:__imp_RtlNtStatusToDosError
0x180007d2c  nop     dword ptr [rax+rax+00h]
0x180007d31  xor     r9d, r9d
0x180007d34  mov     ebx, eax
0x180007d36  test    eax, eax
0x180007d38  jle     short loc_180007D43
0x180007d3a  movzx   ebx, ax
0x180007d3d  or      ebx, 80070000h
0x180007d43  test    ebx, ebx
0x180007d45  jz      short loc_180007D6E
0x180007d47  mov     r9d, ebx
0x180007d4a  lea     r8, aCfreportsyncst_0; "CfReportSyncStatus"
0x180007d51  mov     edx, 106Ah
0x180007d56  call    TlmChk
  ... truncated ...
```
