# CfConvertToPlaceholder

- ea: `0x18000dfe0`
- end: `0x18000e245`
- name: `CfConvertToPlaceholder`
- size: `613`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000231e`
- `0x1800048bc`
- `0x180004d18`
- `0x180004d78`
- `0x18000dfe0`
- `0x180012c28`
- `0x18001cd74`
- `0x18001d0ac`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000e032`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000e032`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e09d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e207`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e09d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e207`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e0b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e0b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e21b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e21b`

## string_xrefs

- `0x18000e055`: `CfpIsDirectory Failed`

## pseudocode

```c
__int64 __fastcall CfConvertToPlaceholder(
        unsigned __int64 hFile,
        void *a2,
        unsigned int a3,
        int a4,
        _QWORD *a5,
        struct _OVERLAPPED *a6)
{
  size_t v6; // r15
  _DWORD *v9; // rbx
  char v10; // r12
  int IsDirectory; // eax
  __int64 v12; // rdx
  char v13; // r13
  int v14; // edi
  const wchar_t *v15; // rcx
  int v16; // eax
  unsigned int v17; // ebx
  HANDLE ProcessHeap; // rax
  int v19; // eax
  DWORD v20; // r8d
  _QWORD *v21; // r15
  HANDLE v22; // rax
  __int64 v24; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+48h] [rbp-51h] BYREF
  int v26; // [rsp+50h] [rbp-49h] BYREF
  const wchar_t *v27; // [rsp+58h] [rbp-41h]
  int v28; // [rsp+60h] [rbp-39h]
  char v29; // [rsp+64h] [rbp-35h]
  unsigned __int64 v30; // [rsp+68h] [rbp-31h]
  DWORD NumberOfBytesTransferred; // [rsp+F0h] [rbp+57h] BYREF
  void *Src; // [rsp+F8h] [rbp+5Fh]
  DWORD v33; // [rsp+108h] [rbp+6Fh] BYREF

  Src = a2;
  v6 = a3;
  NumberOfBytesTransferred = 0;
  v24 = 0;
  UnbiasedTime = 0;
  LOBYTE(v33) = 0;
  v9 = 0;
  v10 = 0;
  memset_0(&v26, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  IsDirectory = CfpIsDirectory(hFile, &v33);
  v13 = v33;
  v14 = IsDirectory;
  if ( IsDirectory > -1 )
  {
    LOBYTE(v12) = (_BYTE)v33 == 0;
    if ( (unsigned __int8)CfpReferenceProtectedHandle(hFile, v12) )
    {
      v16 = v6 + 20;
      v10 = 1;
      if ( (unsigned int)(v6 + 20) < 0x98 )
        v16 = 152;
      v33 = v16;
      v17 = v16;
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 0, v17);
      v14 = v9 == 0 ? 8 : 0;
      if ( !v9 )
        v14 |= 0x80070000;
      if ( v14 > -1 )
      {
        v9[1] = -1073741822;
        *v9 = -1879048166;
        v9[2] = 0;
        if ( (a4 & 1) != 0 )
        {
          v9[2] = 1;
          v19 = 1;
        }
        else
        {
          v19 = 0;
        }
        if ( (a4 & 2) != 0 )
        {
          v19 |= 2u;
          v9[2] = v19;
        }
        if ( (a4 & 4) != 0 )
        {
          v19 |= 0x20u;
          v9[2] = v19;
        }
        if ( (a4 & 8) != 0 )
        {
          v19 |= 0x400u;
          v9[2] = v19;
        }
        if ( (a4 & 0x10) != 0 )
          v9[2] = v19 | 0x1000000;
        memcpy_0(v9 + 5, Src, v6);
        v20 = v33;
        v9[4] = v6;
        v21 = a5;
        v14 = IssueHsmControl(
                hFile,
                v9,
                v20,
                (void *)((unsigned __int64)&v24 & -(__int64)(a5 != 0)),
                a5 != 0 ? 8 : 0,
                &NumberOfBytesTransferred,
                a6);
        if ( v14 > -1 )
        {
          v15 = 0;
          if ( v21 )
            *v21 = v24;
        }
        else
        {
          v15 = L"IssueHsmControl Failed";
        }
      }
      else
      {
        v15 = L"hsmOp Memory allocation Failed";
      }
    }
    else
    {
      v14 = -2147024890;
      v15 = L"Invalid File Handle";
    }
  }
  else
  {
    v15 = L"CfpIsDirectory Failed";
  }
  v27 = v15;
  v28 = a4;
  v29 = v13;
  v30 = hFile;
  TlmLogApiReliability(0x10u, hFile, 0, 0, 0, UnbiasedTime, &v26, v14);
  if ( v10 )
    CfpReleaseProtectedHandle(hFile);
  if ( v9 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v9);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000dfe0  mov     [rsp-8+arg_10], rbx
0x18000dfe5  mov     [rsp-8+Src], rdx
0x18000dfea  push    rbp
0x18000dfeb  push    rsi
0x18000dfec  push    rdi
0x18000dfed  push    r12
0x18000dfef  push    r13
0x18000dff1  push    r14
0x18000dff3  push    r15
0x18000dff5  lea     rbp, [rsp-17h]
0x18000dffa  sub     rsp, 0B0h
0x18000e001  xor     eax, eax
0x18000e003  mov     r15d, r8d
0x18000e006  mov     r14, rcx
0x18000e009  mov     [rbp+47h+NumberOfBytesTransferred], eax
0x18000e00c  xor     edx, edx; Val
0x18000e00e  mov     [rbp+47h+var_A0], rax
0x18000e012  lea     rcx, [rbp+47h+var_90]; void *
0x18000e016  mov     [rbp+47h+UnbiasedTime], rax
0x18000e01a  lea     r8d, [rax+58h]; Size
0x18000e01e  mov     byte ptr [rbp+47h+arg_18], al
0x18000e021  mov     esi, r9d
0x18000e024  mov     ebx, eax
0x18000e026  mov     r12b, al
0x18000e029  call    memset_0
0x18000e02e  lea     rcx, [rbp+47h+UnbiasedTime]; UnbiasedTime
0x18000e032  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000e039  nop     dword ptr [rax+rax+00h]
0x18000e03e  lea     rdx, [rbp+47h+arg_18]
0x18000e042  mov     rcx, r14
0x18000e045  call    CfpIsDirectory
0x18000e04a  mov     r13b, byte ptr [rbp+47h+arg_18]
0x18000e04e  mov     edi, eax
0x18000e050  cmp     eax, 0FFFFFFFFh
0x18000e053  jg      short loc_18000E061
0x18000e055  lea     rcx, aCfpisdirectory; "CfpIsDirectory Failed"
0x18000e05c  jmp     loc_18000E1B4
0x18000e061  test    r13b, r13b
0x18000e064  mov     rcx, r14
0x18000e067  setz    dl
0x18000e06a  call    CfpReferenceProtectedHandle
0x18000e06f  test    al, al
0x18000e071  jnz     short loc_18000E084
0x18000e073  mov     edi, 80070006h
0x18000e078  lea     rcx, aInvalidFileHan; "Invalid File Handle"
0x18000e07f  jmp     loc_18000E1B4
0x18000e084  lea     eax, [r15+14h]
0x18000e088  mov     ecx, 98h
0x18000e08d  cmp     eax, ecx
0x18000e08f  mov     r12d, 1
0x18000e095  cmovb   eax, ecx
0x18000e098  mov     [rbp+47h+arg_18], eax
0x18000e09b  mov     ebx, eax
0x18000e09d  call    cs:__imp_GetProcessHeap
0x18000e0a4  nop     dword ptr [rax+rax+00h]
0x18000e0a9  mov     r8d, ebx; dwBytes
0x18000e0ac  xor     edx, edx; dwFlags
0x18000e0ae  mov     rcx, rax; hHeap
0x18000e0b1  call    cs:__imp_HeapAlloc
0x18000e0b8  nop     dword ptr [rax+rax+00h]
0x18000e0bd  mov     rbx, rax
0x18000e0c0  neg     rax
0x18000e0c3  sbb     edi, edi
0x18000e0c5  not     edi
0x18000e0c7  and     edi, 8
0x18000e0ca  mov     eax, edi
0x18000e0cc  or      eax, 80070000h
0x18000e0d1  test    rbx, rbx
0x18000e0d4  cmovz   edi, eax
0x18000e0d7  cmp     edi, 0FFFFFFFFh
0x18000e0da  jg      short loc_18000E0E8
0x18000e0dc  lea     rcx, aHsmopMemoryAll_0; "hsmOp Memory allocation Failed"
0x18000e0e3  jmp     loc_18000E1B4
0x18000e0e8  mov     dword ptr [rbx+4], 0C0000002h
0x18000e0ef  mov     dword ptr [rbx], 9000001Ah
0x18000e0f5  mov     dword ptr [rbx+8], 0
0x18000e0fc  test    r12b, sil
0x18000e0ff  jnz     short loc_18000E105
0x18000e101  xor     eax, eax
0x18000e103  jmp     short loc_18000E10C
0x18000e105  mov     [rbx+8], r12d
0x18000e109  mov     eax, r12d
0x18000e10c  test    sil, 2
0x18000e110  jz      short loc_18000E118
0x18000e112  or      eax, 2
0x18000e115  mov     [rbx+8], eax
0x18000e118  test    sil, 4
0x18000e11c  jz      short loc_18000E124
0x18000e11e  or      eax, 20h
0x18000e121  mov     [rbx+8], eax
0x18000e124  test    sil, 8
0x18000e128  jz      short loc_18000E131
0x18000e12a  bts     eax, 0Ah
0x18000e12e  mov     [rbx+8], eax
0x18000e131  test    sil, 10h
0x18000e135  jz      short loc_18000E13E
0x18000e137  bts     eax, 18h
0x18000e13b  mov     [rbx+8], eax
0x18000e13e  mov     rdx, [rbp+47h+Src]; Src
0x18000e142  lea     rcx, [rbx+14h]; void *
0x18000e146  mov     r8, r15; Size
0x18000e149  call    memcpy_0
0x18000e14e  mov     r8d, [rbp+47h+arg_18]
0x18000e152  mov     rdx, rbx
0x18000e155  mov     [rbx+10h], r15d
0x18000e159  mov     r15, [rbp+47h+arg_20]
0x18000e15d  mov     rax, r15
0x18000e160  neg     rax
0x18000e163  mov     rax, r15
0x18000e166  sbb     ecx, ecx
0x18000e168  and     ecx, 8
0x18000e16b  neg     rax
0x18000e16e  lea     rax, [rbp+47h+var_A0]
0x18000e172  sbb     r9, r9
0x18000e175  and     r9, rax
0x18000e178  mov     rax, [rbp+47h+arg_28]
0x18000e17c  mov     [rsp+0E0h+var_B0], rax; __int64
0x18000e181  lea     rax, [rbp+47h+NumberOfBytesTransferred]
0x18000e185  mov     [rsp+0E0h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18000e18a  mov     [rsp+0E0h+var_C0], ecx; DWORD
0x18000e18e  mov     rcx, r14; hFile
0x18000e191  call    IssueHsmControl
0x18000e196  mov     edi, eax
0x18000e198  cmp     eax, 0FFFFFFFFh
0x18000e19b  jg      short loc_18000E1A6
0x18000e19d  lea     rcx, aIssuehsmcontro; "IssueHsmControl Failed"
0x18000e1a4  jmp     short loc_18000E1B4
0x18000e1a6  xor     ecx, ecx
0x18000e1a8  test    r15, r15
0x18000e1ab  jz      short loc_18000E1B4
0x18000e1ad  mov     rax, [rbp+47h+var_A0]
0x18000e1b1  mov     [r15], rax
0x18000e1b4  mov     [rsp+0E0h+var_A8], edi
0x18000e1b8  lea     rax, [rbp+47h+var_90]
0x18000e1bc  mov     [rsp+0E0h+var_B0], rax
0x18000e1c1  xor     r9d, r9d
0x18000e1c4  mov     rax, [rbp+47h+UnbiasedTime]
0x18000e1c8  xor     r8d, r8d
0x18000e1cb  mov     [rbp+47h+var_88], rcx
0x18000e1cf  mov     rdx, r14
0x18000e1d2  mov     [rsp+0E0h+lpNumberOfBytesTransferred], rax
0x18000e1d7  mov     ecx, 10h
0x18000e1dc  mov     qword ptr [rsp+0E0h+var_C0], 0
0x18000e1e5  mov     [rbp+47h+var_80], esi
0x18000e1e8  mov     [rbp+47h+var_7C], r13b
0x18000e1ec  mov     [rbp+47h+var_78], r14
0x18000e1f0  call    TlmLogApiReliability
0x18000e1f5  test    r12b, r12b
0x18000e1f8  jz      short loc_18000E202
0x18000e1fa  mov     rcx, r14
0x18000e1fd  call    CfpReleaseProtectedHandle
0x18000e202  test    rbx, rbx
0x18000e205  jz      short loc_18000E227
0x18000e207  call    cs:__imp_GetProcessHeap
0x18000e20e  nop     dword ptr [rax+rax+00h]
0x18000e213  mov     r8, rbx; lpMem
0x18000e216  xor     edx, edx; dwFlags
0x18000e218  mov     rcx, rax; hHeap
0x18000e21b  call    cs:__imp_HeapFree
0x18000e222  nop     dword ptr [rax+rax+00h]
0x18000e227  mov     rbx, [rsp+0E0h+arg_10]
0x18000e22f  mov     eax, edi
0x18000e231  add     rsp, 0B0h
0x18000e238  pop     r15
0x18000e23a  pop     r14
0x18000e23c  pop     r13
0x18000e23e  pop     r12
0x18000e240  pop     rdi
0x18000e241  pop     rsi
0x18000e242  pop     rbp
0x18000e243  retn
```
