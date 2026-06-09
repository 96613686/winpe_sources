# CfUpdatePlaceholder

- ea: `0x18000f100`
- end: `0x18000f538`
- name: `CfUpdatePlaceholder`
- size: `1080`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800118f4`

## callees

- `0x18000231e`
- `0x1800048bc`
- `0x180004d18`
- `0x180004d78`
- `0x18000f100`
- `0x180012c28`
- `0x18001cd74`
- `0x18001d0ac`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000f15a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000f15a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f29f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f501`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f29f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f501`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f2b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f2b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f515`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f515`

## string_xrefs

- `0x18000f17e`: `Failed IsDirectory check`
- `0x18000f211`: `Remove FileIdentity AND Non Null FileIdentity Not allowed`

## pseudocode

```c
__int64 __fastcall CfUpdatePlaceholder(
        unsigned __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4,
        void *Src,
        unsigned int a6,
        int a7,
        _QWORD *a8,
        struct _OVERLAPPED *a9)
{
  _DWORD *v9; // rsi
  char v12; // r12
  __int64 v13; // rdx
  int IsDirectory; // ebx
  const wchar_t *v15; // rcx
  __int64 v16; // rcx
  unsigned int v17; // edx
  int v18; // edi
  int v19; // eax
  int v20; // ecx
  unsigned int v21; // ebx
  HANDLE ProcessHeap; // rax
  int v23; // r8d
  char *v24; // r9
  size_t v25; // rbx
  HANDLE v26; // rax
  DWORD NumberOfBytesTransferred[2]; // [rsp+48h] [rbp-91h] BYREF
  __int64 v29; // [rsp+50h] [rbp-89h]
  __int64 v30; // [rsp+58h] [rbp-81h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+60h] [rbp-79h] BYREF
  size_t Size; // [rsp+68h] [rbp-71h]
  int v33; // [rsp+78h] [rbp-61h] BYREF
  const wchar_t *v34; // [rsp+80h] [rbp-59h]
  int v35; // [rsp+88h] [rbp-51h]
  char v36; // [rsp+8Ch] [rbp-4Dh]
  char v37; // [rsp+8Dh] [rbp-4Ch]
  char v38; // [rsp+8Eh] [rbp-4Bh]

  v9 = 0;
  NumberOfBytesTransferred[1] = 0;
  UnbiasedTime = 0;
  v30 = 0;
  LOBYTE(NumberOfBytesTransferred[0]) = 0;
  v12 = 0;
  memset_0(&v33, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  IsDirectory = CfpIsDirectory(a1, NumberOfBytesTransferred);
  if ( IsDirectory <= -1 )
  {
    v15 = L"Failed IsDirectory check";
    goto LABEL_75;
  }
  LOBYTE(v13) = LOBYTE(NumberOfBytesTransferred[0]) == 0;
  if ( !(unsigned __int8)CfpReferenceProtectedHandle(a1, v13) )
  {
    IsDirectory = -2147024890;
    v15 = L"Invalid Handle";
    goto LABEL_75;
  }
  v12 = 1;
  if ( (a7 & 8) != 0 && (a7 & 0x10) != 0 )
    IsDirectory = 87;
  else
    IsDirectory = 0;
  if ( IsDirectory )
    IsDirectory |= 0x80070000;
  if ( IsDirectory <= -1 )
  {
    v15 = L"Enable/Disable OnDemand Population Can't be ";
    goto LABEL_75;
  }
  if ( a3 && (a7 & 0x20) != 0 )
    IsDirectory = 87;
  else
    IsDirectory = 0;
  if ( IsDirectory )
    IsDirectory |= 0x80070000;
  if ( IsDirectory <= -1 )
  {
    v15 = L"Remove FileIdentity AND Non Null FileIdentity Not allowed";
    goto LABEL_75;
  }
  IsDirectory = 87;
  if ( (a7 & 0x42) != 0x42 )
    IsDirectory = 0;
  if ( IsDirectory )
    IsDirectory |= 0x80070000;
  if ( IsDirectory <= -1 )
  {
    v15 = L"Mark and Clear In Sync together not allowed";
    goto LABEL_75;
  }
  v16 = 0;
  v17 = a4 + 76;
  v18 = 4;
  Size = 16LL * a6;
  if ( (a7 & 4) == 0 )
    v16 = 16LL * a6;
  v19 = 152;
  v29 = 152;
  if ( (unsigned __int64)(a4 + 76) + v16 >= 0x98 )
  {
    v20 = 16 * a6;
    if ( (a7 & 4) != 0 )
      v20 = 0;
    v19 = v20 + v17;
    v29 = v20 + v17;
  }
  v21 = v19;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, v21);
  IsDirectory = v9 == 0 ? 8 : 0;
  if ( !v9 )
    IsDirectory |= 0x80070000;
  if ( IsDirectory <= -1 )
  {
    v15 = L"hsmOp Memory Allocation failed";
    goto LABEL_75;
  }
  v9[1] = -1073741821;
  v23 = 76;
  *v9 = -1879048166;
  v24 = (char *)(v9 + 19);
  v9[2] = 4;
  if ( (a7 & 8) != 0 )
  {
    v18 = 36;
  }
  else
  {
    if ( (a7 & 0x10) == 0 )
      goto LABEL_42;
    v18 = 68;
  }
  v9[2] = v18;
LABEL_42:
  if ( (a7 & 1) != 0 )
  {
    v18 |= 8u;
LABEL_46:
    v9[2] = v18;
    goto LABEL_47;
  }
  if ( (a7 & 2) != 0 )
  {
    v18 |= 1u;
    goto LABEL_46;
  }
LABEL_47:
  if ( (a7 & 0x40) != 0 )
  {
    v18 |= 0x100u;
    v9[2] = v18;
  }
  if ( (a7 & 0x20) != 0 )
  {
    v18 |= 0x80u;
    v9[2] = v18;
  }
  if ( (a7 & 0x80u) != 0 )
  {
    v18 |= 0x2000u;
    v9[2] = v18;
  }
  if ( (a7 & 0x100) != 0 )
  {
    v18 |= 0x10000u;
    v9[2] = v18;
  }
  if ( (a7 & 0x200) != 0 )
  {
    v18 |= 0x400u;
    v9[2] = v18;
  }
  if ( (a7 & 0x400) != 0 )
  {
    v18 |= 0x800000u;
    v9[2] = v18;
  }
  if ( (a7 & 4) != 0 )
  {
    v9[2] = v18 | 2;
  }
  else if ( Src && a6 )
  {
    v25 = Size;
    v9[17] = 76;
    v9[18] = (unsigned __int16)(16 * a6);
    memcpy_0(v9 + 19, Src, v25);
    v24 = (char *)v9 + v25 + 76;
    v23 = 16 * a6 + 76;
  }
  if ( a2 )
  {
    v9[14] = *(_DWORD *)(a2 + 32);
    *((_QWORD *)v9 + 3) = *(_QWORD *)(a2 + 40);
    *((_QWORD *)v9 + 4) = *(_QWORD *)a2;
    *((_QWORD *)v9 + 5) = *(_QWORD *)(a2 + 16);
    *((_QWORD *)v9 + 6) = *(_QWORD *)(a2 + 8);
    v36 = 1;
  }
  else
  {
    v9[2] |= 0x20000u;
  }
  if ( a8 )
  {
    *((_QWORD *)v9 + 2) = *a8;
    v37 = 1;
  }
  if ( a3 )
  {
    v9[15] = v23;
    v9[16] = a4;
    memcpy_0(v24, a3, a4);
    v38 = 1;
  }
  IsDirectory = IssueHsmControl(
                  a1,
                  v9,
                  v29,
                  (void *)((unsigned __int64)&v30 & -(__int64)(a8 != 0)),
                  a8 != 0 ? 8 : 0,
                  &NumberOfBytesTransferred[1],
                  a9);
  if ( IsDirectory > -1 )
  {
    v15 = 0;
    if ( a8 )
      *a8 = v30;
  }
  else
  {
    v15 = L"IssueHsmControl Failed";
  }
LABEL_75:
  v35 = a7;
  v34 = v15;
  TlmLogApiReliability(0x11u, a1, 0, 0, 0, UnbiasedTime, &v33, IsDirectory);
  if ( v12 )
    CfpReleaseProtectedHandle(a1);
  if ( v9 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v9);
  }
  return (unsigned int)IsDirectory;
}

```

## disassembly

```asm
0x18000f100  mov     rax, rsp
0x18000f103  mov     [rax+20h], r9d
0x18000f107  mov     [rax+18h], r8
0x18000f10b  mov     [rax+10h], rdx
0x18000f10f  mov     [rax+8], rcx
0x18000f113  push    rbp
0x18000f114  push    rbx
0x18000f115  push    rsi
0x18000f116  push    rdi
0x18000f117  push    r12
0x18000f119  push    r13
0x18000f11b  push    r14
0x18000f11d  push    r15
0x18000f11f  lea     rbp, [rax-47h]
0x18000f123  sub     rsp, 0D8h
0x18000f12a  xor     esi, esi
0x18000f12c  mov     rdi, r8
0x18000f12f  mov     rbx, rcx
0x18000f132  mov     [rsp+110h+NumberOfBytesTransferred+4], esi
0x18000f136  xor     edx, edx; Val
0x18000f138  mov     [rbp+3Fh+UnbiasedTime], rsi
0x18000f13c  lea     rcx, [rbp+3Fh+var_A0]; void *
0x18000f140  mov     [rsp+110h+var_C0], rsi
0x18000f145  lea     r8d, [rsi+58h]; Size
0x18000f149  mov     byte ptr [rsp+110h+NumberOfBytesTransferred], sil
0x18000f14e  xor     r12b, r12b
0x18000f151  call    memset_0
0x18000f156  lea     rcx, [rbp+3Fh+UnbiasedTime]; UnbiasedTime
0x18000f15a  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000f161  nop     dword ptr [rax+rax+00h]
0x18000f166  lea     rdx, [rsp+110h+NumberOfBytesTransferred]
0x18000f16b  mov     rcx, rbx
0x18000f16e  call    CfpIsDirectory
0x18000f173  mov     r14d, [rbp+3Fh+arg_30]
0x18000f177  mov     ebx, eax
0x18000f179  cmp     eax, 0FFFFFFFFh
0x18000f17c  jg      short loc_18000F18A
0x18000f17e  lea     rcx, aFailedIsdirect; "Failed IsDirectory check"
0x18000f185  jmp     loc_18000F4B1
0x18000f18a  cmp     byte ptr [rsp+110h+NumberOfBytesTransferred], sil
0x18000f18f  mov     rcx, [rbp+3Fh+hFile]
0x18000f193  setz    dl
0x18000f196  call    CfpReferenceProtectedHandle
0x18000f19b  test    al, al
0x18000f19d  jnz     short loc_18000F1B0
0x18000f19f  mov     ebx, 80070006h
0x18000f1a4  lea     rcx, aInvalidHandle; "Invalid Handle"
0x18000f1ab  jmp     loc_18000F4B1
0x18000f1b0  mov     r12d, 1
0x18000f1b6  mov     r15d, r14d
0x18000f1b9  lea     edx, [r12+56h]
0x18000f1be  and     r15d, 8
0x18000f1c2  jz      short loc_18000F1CE
0x18000f1c4  test    r14b, 10h
0x18000f1c8  jz      short loc_18000F1CE
0x18000f1ca  mov     ebx, edx
0x18000f1cc  jmp     short loc_18000F1D0
0x18000f1ce  xor     ebx, ebx
0x18000f1d0  mov     eax, ebx
0x18000f1d2  mov     r8d, 80070000h
0x18000f1d8  or      eax, r8d
0x18000f1db  test    ebx, ebx
0x18000f1dd  cmovnz  ebx, eax
0x18000f1e0  cmp     ebx, 0FFFFFFFFh
0x18000f1e3  jg      short loc_18000F1F1
0x18000f1e5  lea     rcx, aEnableDisableO; "Enable/Disable OnDemand Population Can'"...
0x18000f1ec  jmp     loc_18000F4B1
0x18000f1f1  test    rdi, rdi
0x18000f1f4  jz      short loc_18000F200
0x18000f1f6  test    r14b, 20h
0x18000f1fa  jz      short loc_18000F200
0x18000f1fc  mov     ebx, edx
0x18000f1fe  jmp     short loc_18000F202
0x18000f200  xor     ebx, ebx
0x18000f202  mov     eax, ebx
0x18000f204  or      eax, r8d
0x18000f207  test    ebx, ebx
0x18000f209  cmovnz  ebx, eax
0x18000f20c  cmp     ebx, 0FFFFFFFFh
0x18000f20f  jg      short loc_18000F21D
0x18000f211  lea     rcx, aRemoveFileiden; "Remove FileIdentity AND Non Null FileId"...
0x18000f218  jmp     loc_18000F4B1
0x18000f21d  xor     eax, eax
0x18000f21f  mov     cl, r14b
0x18000f222  and     cl, 42h
0x18000f225  mov     ebx, edx
0x18000f227  cmp     cl, 42h ; 'B'
0x18000f22a  cmovnz  ebx, eax
0x18000f22d  mov     eax, ebx
0x18000f22f  or      eax, r8d
0x18000f232  test    ebx, ebx
0x18000f234  cmovnz  ebx, eax
0x18000f237  cmp     ebx, 0FFFFFFFFh
0x18000f23a  jg      short loc_18000F248
0x18000f23c  lea     rcx, aMarkAndClearIn; "Mark and Clear In Sync together not all"...
0x18000f243  jmp     loc_18000F4B1
0x18000f248  mov     r13d, [rbp+3Fh+arg_28]
0x18000f24c  xor     ecx, ecx
0x18000f24e  mov     edx, dword ptr [rbp+3Fh+arg_18]
0x18000f251  mov     r9d, r13d
0x18000f254  shl     r9, 4
0x18000f258  add     edx, 4Ch ; 'L'
0x18000f25b  mov     eax, edx
0x18000f25d  mov     r8d, r14d
0x18000f260  mov     edi, 4
0x18000f265  mov     [rbp+3Fh+Size], r9
0x18000f269  and     r8d, edi
0x18000f26c  test    r8d, r8d
0x18000f26f  mov     [rbp+3Fh+arg_30], r8d
0x18000f273  cmovz   rcx, r9
0x18000f277  add     rcx, rax
0x18000f27a  mov     eax, 98h
0x18000f27f  mov     [rsp+110h+var_C8], rax
0x18000f284  cmp     rcx, rax
0x18000f287  jb      short loc_18000F29D
0x18000f289  xor     eax, eax
0x18000f28b  mov     rcx, r9
0x18000f28e  test    r8d, r8d
0x18000f291  cmovnz  rcx, rax
0x18000f295  lea     eax, [rcx+rdx]
0x18000f298  mov     [rsp+110h+var_C8], rax
0x18000f29d  mov     ebx, eax
0x18000f29f  call    cs:__imp_GetProcessHeap
0x18000f2a6  nop     dword ptr [rax+rax+00h]
0x18000f2ab  mov     r8d, ebx; dwBytes
0x18000f2ae  mov     edx, 8; dwFlags
0x18000f2b3  mov     rcx, rax; hHeap
0x18000f2b6  call    cs:__imp_HeapAlloc
0x18000f2bd  nop     dword ptr [rax+rax+00h]
0x18000f2c2  mov     rsi, rax
0x18000f2c5  neg     rax
0x18000f2c8  sbb     ebx, ebx
0x18000f2ca  not     ebx
0x18000f2cc  and     ebx, 8
0x18000f2cf  mov     eax, ebx
0x18000f2d1  or      eax, 80070000h
0x18000f2d6  test    rsi, rsi
0x18000f2d9  cmovz   ebx, eax
0x18000f2dc  cmp     ebx, 0FFFFFFFFh
0x18000f2df  jg      short loc_18000F2ED
0x18000f2e1  lea     rcx, aHsmopMemoryAll; "hsmOp Memory Allocation failed"
0x18000f2e8  jmp     loc_18000F4B1
0x18000f2ed  mov     dword ptr [rsi+4], 0C0000003h
0x18000f2f4  mov     r8d, 4Ch ; 'L'
0x18000f2fa  mov     dword ptr [rsi], 9000001Ah
0x18000f300  lea     r9, [rsi+4Ch]
0x18000f304  mov     [rsi+8], edi
0x18000f307  test    r15d, r15d
0x18000f30a  jz      short loc_18000F312
0x18000f30c  lea     edi, [r8-28h]
0x18000f310  jmp     short loc_18000F31D
0x18000f312  test    r14b, 10h
0x18000f316  jz      short loc_18000F320
0x18000f318  mov     edi, 44h ; 'D'
0x18000f31d  mov     [rsi+8], edi
0x18000f320  test    r12b, r14b
0x18000f323  jz      short loc_18000F32A
0x18000f325  or      edi, 8
0x18000f328  jmp     short loc_18000F333
0x18000f32a  test    r14b, 2
0x18000f32e  jz      short loc_18000F336
0x18000f330  or      edi, r12d
0x18000f333  mov     [rsi+8], edi
0x18000f336  mov     eax, 100h
0x18000f33b  test    r14b, 40h
0x18000f33f  jz      short loc_18000F346
0x18000f341  or      edi, eax
0x18000f343  mov     [rsi+8], edi
0x18000f346  test    r14b, 20h
0x18000f34a  jz      short loc_18000F353
0x18000f34c  bts     edi, 7
0x18000f350  mov     [rsi+8], edi
0x18000f353  test    r14b, r14b
0x18000f356  jns     short loc_18000F35F
0x18000f358  bts     edi, 0Dh
0x18000f35c  mov     [rsi+8], edi
0x18000f35f  test    eax, r14d
0x18000f362  jz      short loc_18000F36B
0x18000f364  bts     edi, 10h
0x18000f368  mov     [rsi+8], edi
0x18000f36b  mov     eax, 400h
0x18000f370  bt      r14d, 9
0x18000f375  jnb     short loc_18000F37C
0x18000f377  or      edi, eax
0x18000f379  mov     [rsi+8], edi
0x18000f37c  test    eax, r14d
0x18000f37f  jz      short loc_18000F388
0x18000f381  bts     edi, 17h
0x18000f385  mov     [rsi+8], edi
0x18000f388  cmp     [rbp+3Fh+arg_30], 0
0x18000f38c  jz      short loc_18000F396
0x18000f38e  or      edi, 2
0x18000f391  mov     [rsi+8], edi
0x18000f394  jmp     short loc_18000F3D9
0x18000f396  mov     rdx, [rbp+3Fh+Src]; Src
0x18000f39a  test    rdx, rdx
0x18000f39d  jz      short loc_18000F3D9
0x18000f39f  test    r13d, r13d
0x18000f3a2  jz      short loc_18000F3D9
0x18000f3a4  mov     rbx, [rbp+3Fh+Size]
0x18000f3a8  movzx   eax, r13w
0x18000f3ac  shl     ax, 4
0x18000f3b0  mov     rcx, r9; void *
0x18000f3b3  movzx   eax, ax
0x18000f3b6  mov     [rsi+44h], r8d
0x18000f3ba  mov     r8, rbx; Size
0x18000f3bd  mov     [rsi+48h], eax
0x18000f3c0  call    memcpy_0
0x18000f3c5  lea     r9, [rbx+4Ch]
0x18000f3c9  shl     r13d, 4
0x18000f3cd  add     r9, rsi
0x18000f3d0  mov     r8d, 4Ch ; 'L'
0x18000f3d6  add     r8d, r13d
0x18000f3d9  mov     rcx, [rbp+3Fh+arg_8]
0x18000f3dd  test    rcx, rcx
0x18000f3e0  jz      short loc_18000F40D
0x18000f3e2  mov     eax, [rcx+20h]
0x18000f3e5  mov     [rsi+38h], eax
0x18000f3e8  mov     rax, [rcx+28h]
0x18000f3ec  mov     [rsi+18h], rax
0x18000f3f0  mov     rax, [rcx]
0x18000f3f3  mov     [rsi+20h], rax
0x18000f3f7  mov     rax, [rcx+10h]
0x18000f3fb  mov     [rsi+28h], rax
0x18000f3ff  mov     rax, [rcx+8]
0x18000f403  mov     [rsi+30h], rax
0x18000f407  mov     [rbp+3Fh+var_8C], r12b
0x18000f40b  jmp     short loc_18000F412
0x18000f40d  bts     dword ptr [rsi+8], 11h
0x18000f412  mov     rdi, [rbp+3Fh+arg_38]
0x18000f419  test    rdi, rdi
0x18000f41c  jz      short loc_18000F429
0x18000f41e  mov     rax, [rdi]
0x18000f421  mov     [rsi+10h], rax
0x18000f425  mov     [rbp+3Fh+var_8B], r12b
0x18000f429  mov     rdx, [rbp+3Fh+arg_10]; Src
0x18000f42d  test    rdx, rdx
0x18000f430  jz      short loc_18000F44B
0x18000f432  mov     eax, dword ptr [rbp+3Fh+arg_18]
0x18000f435  mov     rcx, r9; void *
0x18000f438  mov     [rsi+3Ch], r8d
0x18000f43c  mov     r8d, eax; Size
0x18000f43f  mov     [rsi+40h], eax
0x18000f442  call    memcpy_0
0x18000f447  mov     [rbp+3Fh+var_8A], r12b
0x18000f44b  mov     r8d, dword ptr [rsp+110h+var_C8]
0x18000f450  mov     rax, rdi
0x18000f453  neg     rax
0x18000f456  mov     rdx, rsi
0x18000f459  mov     rax, rdi
0x18000f45c  sbb     ecx, ecx
0x18000f45e  and     ecx, 8
0x18000f461  neg     rax
0x18000f464  lea     rax, [rsp+110h+var_C0]
0x18000f469  sbb     r9, r9
0x18000f46c  and     r9, rax
0x18000f46f  mov     rax, [rbp+3Fh+arg_40]
0x18000f476  mov     [rsp+110h+var_E0], rax; __int64
0x18000f47b  lea     rax, [rsp+110h+NumberOfBytesTransferred+4]
0x18000f480  mov     [rsp+110h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18000f485  mov     [rsp+110h+var_F0], ecx; DWORD
0x18000f489  mov     rcx, [rbp+3Fh+hFile]; hFile
0x18000f48d  call    IssueHsmControl
0x18000f492  mov     ebx, eax
0x18000f494  cmp     eax, 0FFFFFFFFh
0x18000f497  jg      short loc_18000F4A2
0x18000f499  lea     rcx, aIssuehsmcontro; "IssueHsmControl Failed"
0x18000f4a0  jmp     short loc_18000F4B1
0x18000f4a2  xor     ecx, ecx
0x18000f4a4  test    rdi, rdi
0x18000f4a7  jz      short loc_18000F4B1
0x18000f4a9  mov     rax, [rsp+110h+var_C0]
0x18000f4ae  mov     [rdi], rax
0x18000f4b1  mov     dword ptr [rsp+110h+var_D8], ebx
0x18000f4b5  lea     rax, [rbp+3Fh+var_A0]
0x18000f4b9  mov     [rsp+110h+var_E0], rax
0x18000f4be  xor     r9d, r9d
0x18000f4c1  mov     rax, [rbp+3Fh+UnbiasedTime]
0x18000f4c5  xor     r8d, r8d
0x18000f4c8  mov     [rbp+3Fh+var_90], r14d
0x18000f4cc  mov     r14, [rbp+3Fh+hFile]
0x18000f4d0  mov     [rbp+3Fh+var_98], rcx
0x18000f4d4  mov     rdx, r14
0x18000f4d7  mov     [rsp+110h+lpNumberOfBytesTransferred], rax
0x18000f4dc  mov     ecx, 11h
0x18000f4e1  mov     qword ptr [rsp+110h+var_F0], 0
0x18000f4ea  call    TlmLogApiReliability
0x18000f4ef  test    r12b, r12b
0x18000f4f2  jz      short loc_18000F4FC
0x18000f4f4  mov     rcx, r14
0x18000f4f7  call    CfpReleaseProtectedHandle
0x18000f4fc  test    rsi, rsi
0x18000f4ff  jz      short loc_18000F521
0x18000f501  call    cs:__imp_GetProcessHeap
0x18000f508  nop     dword ptr [rax+rax+00h]
0x18000f50d  mov     r8, rsi; lpMem
0x18000f510  xor     edx, edx; dwFlags
0x18000f512  mov     rcx, rax; hHeap
0x18000f515  call    cs:__imp_HeapFree
0x18000f51c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
