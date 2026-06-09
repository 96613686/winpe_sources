# CscDclMRxDeleteItem

- ea: `0x14004b610`
- end: `0x14004b92c`
- name: `CscDclMRxDeleteItem`
- size: `796`
- prototype: `__int64 __fastcall(__int64, char, int *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x14007ae70`

## callees

- `0x1400017c0`
- `0x140003a00`
- `0x14000e100`
- `0x14000f8b0`
- `0x140012cb0`
- `0x140019204`
- `0x14001a548`
- `0x14001d200`
- `0x140023464`
- `0x14002f010`
- `0x14002f440`
- `0x14004b610`
- `0x140086870`

## import_xrefs

- `rdbss!RxScavengeRelatedFobxs` at `0x14004b87b`
- `rdbss!RxScavengeRelatedFobxs` at `0x14004b87b`
- `rdbss!RxScavengeRelatedClosePendingFobxs` at `0x14004b85b`
- `rdbss!RxScavengeRelatedClosePendingFobxs` at `0x14004b85b`

## pseudocode

```c
__int64 __fastcall CscDclMRxDeleteItem(__int64 a1, char a2, int *a3, int *a4)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  __int64 v8; // r13
  int v9; // r15d
  int StoreEntry; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // ecx
  int v14; // r9d
  __int64 v15; // rdx
  __int64 v16; // rsi
  int v17; // ecx
  __int64 v18; // rdx
  int v19; // r8d
  __int64 v20; // rsi
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // rdx
  char v26; // [rsp+40h] [rbp-99h] BYREF
  char v27[3]; // [rsp+41h] [rbp-98h] BYREF
  int v28; // [rsp+44h] [rbp-95h] BYREF
  __int64 v29; // [rsp+48h] [rbp-91h] BYREF
  __int64 v30; // [rsp+50h] [rbp-89h]
  int *v31; // [rsp+58h] [rbp-81h]
  int *v32; // [rsp+60h] [rbp-79h]
  __int128 v33; // [rsp+68h] [rbp-71h] BYREF
  __int128 v34; // [rsp+78h] [rbp-61h]
  __int128 v35; // [rsp+90h] [rbp-49h] BYREF
  _DWORD v36[20]; // [rsp+A0h] [rbp-39h] BYREF

  v4 = *(_QWORD *)(a1 + 64);
  v5 = *(_QWORD *)(a1 + 56);
  v31 = a3;
  v32 = a4;
  v8 = *(_QWORD *)(v4 + 32);
  v30 = v5;
  v29 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  memset(v36, 0, sizeof(v36));
  v26 = 0;
  v9 = 0;
  StoreEntry = CscDclMRx_GetStoreEntry(&v29, v8);
  if ( StoreEntry < 0 )
  {
    v13 = 1617;
LABEL_33:
    v19 = 1;
    goto LABEL_34;
  }
  CscGetContexts(a1, &v33, v11, v12);
  LOBYTE(v14) = 1;
  CscUpdateAndCaptureConnectionStateEx(v5, v8, a1, v14, (__int64)&v35, 1);
  if ( (BYTE1(v35) & 0x40) != 0 )
  {
    StoreEntry = CscDetermineAbortStatus(&v35);
    v13 = 1626;
    goto LABEL_28;
  }
  LOBYTE(v15) = 1;
  if ( !(unsigned __int8)_CscObtainFcbMostlyExclusive(a1, v15) )
  {
    StoreEntry = -1073741757;
    v13 = 1636;
    goto LABEL_33;
  }
  v16 = v34;
  if ( (*(_DWORD *)(v34 + 32) & 0x10028) == 0 || (v35 & 0x10) == 0 )
  {
    v13 = 1659;
    goto LABEL_32;
  }
  StoreEntry = CscStoreQueryInformationEntryEx(v29, 0, (unsigned int)v36, 0, (__int64)&v26, 0, 0);
  if ( StoreEntry < 0 )
  {
    v13 = 1669;
    goto LABEL_33;
  }
  v17 = v36[0];
  if ( (v36[0] & 0x80407) != 0 && (*(_DWORD *)(v16 + 24) & 0x800) == 0 )
  {
    v18 = *(_QWORD *)(v8 + 40) + 112LL;
    v28 = 0;
    StoreEntry = CscStoreQueryExplicitAccessEntry(v29, v18, &v28);
    if ( StoreEntry < 0 )
    {
      v13 = 1693;
      goto LABEL_33;
    }
    if ( (v28 & 0x10002) == 0 )
    {
      v13 = 1698;
LABEL_32:
      StoreEntry = -1073741790;
      goto LABEL_33;
    }
    v17 = v36[0];
  }
  if ( !v26 )
  {
    if ( (v17 & 0x80417) != 0 )
    {
      v19 = 2;
      if ( (a2 & 2) == 0 )
      {
        StoreEntry = -1073741823;
        v13 = 1717;
        goto LABEL_34;
      }
    }
    v20 = *((_QWORD *)&v33 + 1);
    if ( (*(_DWORD *)(*((_QWORD *)&v33 + 1) + 4LL) & 0x80u) != 0 && (a2 & 4) != 0 )
    {
      StoreEntry = -1073741823;
      v13 = 1725;
      v19 = 3;
      goto LABEL_34;
    }
    v27[0] = 1;
    StoreEntry = CscStoreSetInformationEntry(v29, 0, 0, 0, 0, v27, 0);
    if ( StoreEntry < 0 )
    {
      v13 = 1741;
      goto LABEL_33;
    }
    *(_DWORD *)(v20 + 4) &= ~0x80u;
    LOBYTE(v21) = 1;
    CscDclMRx_Synchronize(a1, 0, v21);
    LOBYTE(v22) = 1;
    RxScavengeRelatedClosePendingFobxs(*(_QWORD *)(a1 + 80), v30, v22);
    RxScavengeRelatedFobxs(*(PFCB *)(a1 + 80));
    LOBYTE(v23) = 1;
    LOBYTE(v24) = 1;
    CscDclMRx_Synchronize(a1, v24, v23);
  }
  v13 = 0;
  v9 = 1;
LABEL_28:
  v19 = 0;
  if ( StoreEntry < 0 )
    goto LABEL_33;
LABEL_34:
  *v31 = v9;
  *v32 = v19;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_DDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      35,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      (unsigned int)StoreEntry,
      v9,
      v19,
      v13);
  return (unsigned int)StoreEntry;
}

```

## disassembly

```asm
0x14004b610  push    rbp
0x14004b612  push    rbx
0x14004b613  push    rsi
0x14004b614  push    rdi
0x14004b615  push    r12
0x14004b617  push    r13
0x14004b619  push    r15
0x14004b61b  lea     rbp, [rsp-27h]
0x14004b620  sub     rsp, 100h
0x14004b627  mov     rax, cs:__security_cookie
0x14004b62e  xor     rax, rsp
0x14004b631  mov     [rbp+57h+var_40], rax
0x14004b635  mov     rax, [rcx+40h]
0x14004b639  xorps   xmm0, xmm0
0x14004b63c  mov     rsi, [rcx+38h]
0x14004b640  mov     r12d, edx
0x14004b643  xor     edx, edx; Val
0x14004b645  mov     [rsp+130h+var_D8], r8
0x14004b64a  mov     rdi, rcx
0x14004b64d  mov     [rbp+57h+var_D0], r9
0x14004b651  mov     r13, [rax+20h]
0x14004b655  lea     rcx, [rbp+57h+var_90]; void *
0x14004b659  mov     [rsp+130h+var_E0], rsi
0x14004b65e  lea     r8d, [rdx+50h]; Size
0x14004b662  mov     [rsp+130h+var_E8], 0
0x14004b66b  movups  [rbp+57h+var_C8], xmm0
0x14004b66f  movups  [rbp+57h+var_B8], xmm0
0x14004b673  movups  [rbp+57h+var_A0], xmm0
0x14004b677  call    memset
0x14004b67c  mov     rdx, r13
0x14004b67f  mov     [rsp+130h+var_F0], 0
0x14004b684  lea     rcx, [rsp+130h+var_E8]
0x14004b689  xor     r15d, r15d
0x14004b68c  call    CscDclMRx_GetStoreEntry
0x14004b691  mov     ebx, eax
0x14004b693  test    eax, eax
0x14004b695  jns     short loc_14004B6A1
0x14004b697  mov     ecx, 651h
0x14004b69c  jmp     loc_14004B8B5
0x14004b6a1  lea     rdx, [rbp+57h+var_C8]
0x14004b6a5  mov     rcx, rdi
0x14004b6a8  call    CscGetContexts
0x14004b6ad  lea     rax, [rbp+57h+var_A0]
0x14004b6b1  mov     byte ptr [rsp+130h+var_108], 1
0x14004b6b6  mov     r9b, 1
0x14004b6b9  mov     [rsp+130h+var_110], rax
0x14004b6be  mov     r8, rdi
0x14004b6c1  mov     rdx, r13
0x14004b6c4  mov     rcx, rsi
0x14004b6c7  call    CscUpdateAndCaptureConnectionStateEx
0x14004b6cc  test    byte ptr [rbp+57h+var_A0+1], 40h
0x14004b6d0  jz      short loc_14004B6E7
0x14004b6d2  lea     rcx, [rbp+57h+var_A0]
0x14004b6d6  call    CscDetermineAbortStatus
0x14004b6db  mov     ebx, eax
0x14004b6dd  mov     ecx, 65Ah
0x14004b6e2  jmp     loc_14004B89B
0x14004b6e7  mov     r8b, 1
0x14004b6ea  mov     rcx, rdi
0x14004b6ed  mov     dl, r8b
0x14004b6f0  call    __CscObtainFcbMostlyExclusive
0x14004b6f5  test    al, al
0x14004b6f7  jnz     short loc_14004B708
0x14004b6f9  mov     ebx, 0C0000043h
0x14004b6fe  mov     ecx, 664h
0x14004b703  jmp     loc_14004B8B5
0x14004b708  mov     rsi, qword ptr [rbp+57h+var_B8]
0x14004b70c  test    dword ptr [rsi+20h], 10028h
0x14004b713  jz      loc_14004B8AB
0x14004b719  test    byte ptr [rbp+57h+var_A0], 10h
0x14004b71d  jz      loc_14004B8AB
0x14004b723  mov     rcx, [rsp+130h+var_E8]
0x14004b728  lea     rax, [rsp+130h+var_F0]
0x14004b72d  mov     [rsp+130h+var_100], r15
0x14004b732  lea     r8, [rbp+57h+var_90]
0x14004b736  mov     [rsp+130h+var_108], r15
0x14004b73b  xor     r9d, r9d
0x14004b73e  xor     edx, edx
0x14004b740  mov     [rsp+130h+var_110], rax
0x14004b745  call    CscStoreQueryInformationEntryEx
0x14004b74a  mov     ebx, eax
0x14004b74c  test    eax, eax
0x14004b74e  jns     short loc_14004B75A
0x14004b750  mov     ecx, 685h
0x14004b755  jmp     loc_14004B8B5
0x14004b75a  mov     ecx, [rbp+57h+var_90]
0x14004b75d  test    ecx, 80407h
0x14004b763  jz      short loc_14004B7B1
0x14004b765  test    dword ptr [rsi+18h], 800h
0x14004b76c  jnz     short loc_14004B7B1
0x14004b76e  mov     rdx, [r13+28h]
0x14004b772  lea     r8, [rsp+130h+var_EC]
0x14004b777  mov     rcx, [rsp+130h+var_E8]
0x14004b77c  add     rdx, 70h ; 'p'
0x14004b780  mov     [rsp+130h+var_EC], r15d
0x14004b785  call    CscStoreQueryExplicitAccessEntry
0x14004b78a  mov     ebx, eax
0x14004b78c  test    eax, eax
0x14004b78e  jns     short loc_14004B79A
0x14004b790  mov     ecx, 69Dh
0x14004b795  jmp     loc_14004B8B5
0x14004b79a  test    [rsp+130h+var_EC], 10002h
0x14004b7a2  jnz     short loc_14004B7AE
0x14004b7a4  mov     ecx, 6A2h
0x14004b7a9  jmp     loc_14004B8B0
0x14004b7ae  mov     ecx, [rbp+57h+var_90]
0x14004b7b1  cmp     [rsp+130h+var_F0], r15b
0x14004b7b6  jnz     loc_14004B895
0x14004b7bc  test    ecx, 80417h
0x14004b7c2  jz      short loc_14004B7DE
0x14004b7c4  mov     r8d, 2
0x14004b7ca  test    r8b, r12b
0x14004b7cd  jnz     short loc_14004B7DE
0x14004b7cf  mov     ebx, 0C0000001h
0x14004b7d4  mov     ecx, 6B5h
0x14004b7d9  jmp     loc_14004B8BB
0x14004b7de  mov     rsi, qword ptr [rbp+57h+var_C8+8]
0x14004b7e2  mov     eax, [rsi+4]
0x14004b7e5  test    al, al
0x14004b7e7  jns     short loc_14004B804
0x14004b7e9  test    r12b, 4
0x14004b7ed  jz      short loc_14004B804
0x14004b7ef  mov     ebx, 0C0000001h
0x14004b7f4  mov     ecx, 6BDh
0x14004b7f9  mov     r8d, 3
0x14004b7ff  jmp     loc_14004B8BB
0x14004b804  mov     rcx, [rsp+130h+var_E8]
0x14004b809  lea     rax, [rsp+130h+var_EF]
0x14004b80e  mov     [rsp+130h+var_100], r15
0x14004b813  xor     r9d, r9d
0x14004b816  mov     [rsp+130h+var_108], rax
0x14004b81b  xor     r8d, r8d
0x14004b81e  xor     edx, edx
0x14004b820  mov     [rsp+130h+var_110], r15
0x14004b825  mov     [rsp+130h+var_EF], 1
0x14004b82a  call    CscStoreSetInformationEntry
0x14004b82f  mov     ebx, eax
0x14004b831  test    eax, eax
0x14004b833  js      short loc_14004B8A4
0x14004b835  btr     dword ptr [rsi+4], 7
0x14004b83a  mov     r8b, 1
0x14004b83d  xor     edx, edx
0x14004b83f  mov     rcx, rdi
0x14004b842  call    CscDclMRx_Synchronize
0x14004b847  mov     rdx, [rsp+130h+var_E0]
0x14004b84c  mov     r9b, 1
0x14004b84f  mov     rcx, [rdi+50h]
0x14004b853  mov     r8b, r9b
0x14004b856  mov     [rsp+130h+var_110], r15
0x14004b85b  call    cs:__imp_RxScavengeRelatedClosePendingFobxs
0x14004b862  nop     dword ptr [rax+rax+00h]
0x14004b867  mov     rdx, [rsp+130h+var_E0]
0x14004b86c  mov     r9b, 1
0x14004b86f  mov     rcx, [rdi+50h]; Fcb
0x14004b873  mov     r8b, r9b
0x14004b876  mov     [rsp+130h+var_110], r15
0x14004b87b  call    cs:__imp_RxScavengeRelatedFobxs
0x14004b882  nop     dword ptr [rax+rax+00h]
0x14004b887  mov     r8b, 1
0x14004b88a  mov     rcx, rdi
0x14004b88d  mov     dl, r8b
0x14004b890  call    CscDclMRx_Synchronize
0x14004b895  xor     ecx, ecx
0x14004b897  lea     r15d, [rcx+1]
0x14004b89b  xor     r8d, r8d
0x14004b89e  test    ebx, ebx
0x14004b8a0  jns     short loc_14004B8BB
0x14004b8a2  jmp     short loc_14004B8B5
0x14004b8a4  mov     ecx, 6CDh
0x14004b8a9  jmp     short loc_14004B8B5
0x14004b8ab  mov     ecx, 67Bh
0x14004b8b0  mov     ebx, 0C0000022h
0x14004b8b5  mov     r8d, 1
0x14004b8bb  mov     rax, [rsp+130h+var_D8]
0x14004b8c0  mov     [rax], r15d
0x14004b8c3  mov     rax, [rbp+57h+var_D0]
0x14004b8c7  mov     [rax], r8d
0x14004b8ca  mov     r10, cs:WPP_GLOBAL_Control
0x14004b8d1  lea     rax, WPP_GLOBAL_Control
0x14004b8d8  cmp     r10, rax
0x14004b8db  jz      short loc_14004B90B
0x14004b8dd  mov     eax, [r10+2Ch]
0x14004b8e1  test    al, 40h
0x14004b8e3  jz      short loc_14004B90B
0x14004b8e5  mov     dword ptr [rsp+130h+var_100], ecx
0x14004b8e9  mov     edx, 23h ; '#'
0x14004b8ee  mov     rcx, [r10+18h]
0x14004b8f2  mov     r9d, ebx
0x14004b8f5  mov     dword ptr [rsp+130h+var_108], r8d
0x14004b8fa  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004b901  mov     dword ptr [rsp+130h+var_110], r15d
0x14004b906  call    WPP_SF_DDDD
0x14004b90b  mov     eax, ebx
0x14004b90d  mov     rcx, [rbp+57h+var_40]
0x14004b911  xor     rcx, rsp; StackCookie
0x14004b914  call    __security_check_cookie
0x14004b919  add     rsp, 100h
0x14004b920  pop     r15
0x14004b922  pop     r13
0x14004b924  pop     r12
0x14004b926  pop     rdi
0x14004b927  pop     rsi
0x14004b928  pop     rbx
0x14004b929  pop     rbp
0x14004b92a  retn
```
