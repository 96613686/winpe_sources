# AslPathWildcardFindNext

- ea: `0x14073ea34`
- end: `0x14073f184`
- name: `AslPathWildcardFindNext`
- size: `1872`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x140735b60`
- `0x14073d8dc`

## callees

- `0x1403f2d50`
- `0x140425870`
- `0x140446e5c`
- `0x1406cb88c`
- `0x1406daf30`
- `0x1406f4480`
- `0x1406f4880`
- `0x14073ea34`
- `0x14073f18c`
- `0x1408277e4`
- `0x140979890`
- `0x14097b68c`
- `0x14097d158`
- `0x140bae320`
- `0x140bae8e0`

## string_xrefs

- `0x14073f065`: `AslpPathWildcardPushNode failed [%x]`
- `0x14073ed27`: `AslpPathWildcardPeekNode failed [%x]`
- `0x14073f137`: `AslpPathWildcardPeekNode failed [%x]`
- `0x14073ed0f`: `AslpPathWildcardPeekNode`
- `0x14073f123`: `AslpPathWildcardPeekNode`
- `0x14073ed34`: `AslpPathWildcardPopNode`
- `0x14073eb2e`: `AslPathWildcardFindNext`
- `0x14073edb6`: `AslPathWildcardFindNext`
- `0x14073edd5`: `AslPathWildcardFindNext`
- `0x14073f04a`: `AslPathWildcardFindNext`
- `0x14073f14b`: `AslPathWildcardFindNext`
- `0x14073f03d`: `AslpPathWildcardAllocMatchNode failed [%x]`
- `0x14073edc9`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x14073eda5`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x14073f09f`: `RtlStringCbCopyNW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindNext(wchar_t *a1, ULONGLONG a2, ULONGLONG *a3)
{
  unsigned __int64 v5; // rcx
  __int16 *FileInformation; // r12
  unsigned int v7; // edi
  ULONGLONG v8; // rax
  ULONGLONG v9; // rcx
  ULONGLONG v10; // rcx
  unsigned __int16 *v11; // rsi
  ULONGLONG v12; // r10
  ULONGLONG v13; // rcx
  __int64 v14; // r9
  char *v15; // rsi
  ULONGLONG v16; // rdi
  __int64 v17; // r9
  ULONGLONG v18; // rdi
  ULONGLONG v19; // r10
  ULONGLONG v20; // rcx
  ULONGLONG v21; // rsi
  ULONGLONG v22; // rdx
  ULONGLONG v23; // rsi
  size_t v24; // r14
  void *v25; // r15
  PVOID v26; // rax
  void *v27; // rdi
  char v28; // di
  NTSTATUS v29; // eax
  ULONGLONG v30; // rax
  ULONGLONG v31; // rcx
  ULONGLONG v32; // rdx
  int v33; // eax
  const wchar_t *v34; // r14
  bool v35; // zf
  int matched; // eax
  ULONGLONG v37; // r13
  unsigned __int64 v38; // r9
  __int64 v39; // r14
  ULONGLONG v40; // rdx
  ULONGLONG v41; // rcx
  __int64 v42; // r10
  ULONGLONG v43; // r14
  size_t v44; // rsi
  void *v45; // r15
  PVOID PoolWithTag; // rax
  void *v47; // rdi
  ULONGLONG v48; // rcx
  unsigned __int64 v49; // rdx
  NTSTATUS v50; // eax
  const char *v51; // r9
  int v52; // r8d
  size_t v53; // rdx
  char IoStatusBlock; // [rsp+28h] [rbp-59h]
  UNICODE_STRING DestinationString; // [rsp+68h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK v56; // [rsp+78h] [rbp-9h] BYREF
  UNICODE_STRING v57; // [rsp+88h] [rbp+7h] BYREF
  __int128 v58; // [rsp+98h] [rbp+17h]
  ULONGLONG pullResult; // [rsp+F0h] [rbp+6Fh] BYREF
  ULONGLONG Size; // [rsp+F8h] [rbp+77h] BYREF

  pullResult = a2;
  if ( a3 == (ULONGLONG *)-1LL )
    return 2147483654LL;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 )
    return 3221225713LL;
  v56 = 0;
  DestinationString = 0;
  v57 = 0;
  v58 = 0;
  FileInformation = (__int16 *)AslAlloc(a1, 616);
  if ( !FileInformation )
    return (unsigned int)-1073741801;
  while ( 1 )
  {
    v8 = a3[4];
    if ( !v8 )
      break;
    v9 = a3[3];
    pullResult = 0;
    if ( ULongLongMult(v9, v8 - 1, &pullResult) < 0
      || (v10 = a3[7], v11 = (unsigned __int16 *)(v10 + pullResult), v10 + pullResult < v10)
      || !v11 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslpPathWildcardPeekNode",
        2079,
        (unsigned int)"RtlArrayGet failed to get the next node",
        IoStatusBlock);
      v7 = -1073741595;
      AslLogCallPrintf(
        1,
        (unsigned int)"AslPathWildcardFindNext",
        2498,
        (unsigned int)"AslpPathWildcardPeekNode failed [%x]",
        229);
      goto LABEL_92;
    }
    if ( *((_QWORD *)v11 + 3) )
    {
      RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v11 + 2));
      v29 = ZwQueryDirectoryFile(
              *((HANDLE *)v11 + 3),
              0,
              0,
              0,
              &v56,
              FileInformation,
              0x268u,
              FileBothDirectoryInformation,
              1u,
              &DestinationString,
              0);
      if ( v29 < 0 )
      {
        if ( v29 != -2147483642 && v29 != -1073741809 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"AslPathWildcardFindNext",
            2527,
            (unsigned int)"NtQueryDirectoryFile failed to query next file [%x]",
            v29);
          AslLogCallPrintf(
            2,
            (unsigned int)"AslPathWildcardFindNext",
            2528,
            (unsigned int)"FilePath: '%ws'  Pattern: '%ws'",
            *((_QWORD *)v11 + 1));
        }
        goto LABEL_42;
      }
      v33 = *((_DWORD *)FileInformation + 15);
      v34 = (const wchar_t *)(FileInformation + 47);
      if ( v33 == 4 )
      {
        if ( *v34 != 46 )
          goto LABEL_54;
        v35 = FileInformation[48] == 46;
      }
      else
      {
        if ( v33 != 2 )
          goto LABEL_54;
        v34 = (const wchar_t *)(FileInformation + 47);
        v35 = FileInformation[47] == 46;
      }
      if ( !v35 )
      {
LABEL_54:
        matched = AslpPathWildcardAllocMatchNode(&v57, (PCUNICODE_STRING)v11, v34, FileInformation[30]);
        if ( matched == -1073741197 )
        {
          v50 = RtlStringCbCopyNW(a1, 0x208u, *((STRSAFE_PCNZWCH *)v11 + 1), *v11);
          v7 = v50;
          if ( v50 >= 0 )
          {
            if ( *(_WORD *)(*((_QWORD *)v11 + 1) + 2 * ((unsigned __int64)*v11 >> 1) - 2) == 92
              || (v50 = RtlStringCbCatNW(a1, v53, L"\\", 2u), v7 = v50, v50 >= 0) )
            {
              v50 = RtlStringCbCatNW(a1, v53, v34, *((unsigned int *)FileInformation + 15));
              v7 = v50;
              if ( v50 >= 0 )
              {
                v7 = 0;
                goto LABEL_92;
              }
              v51 = "RtlStringCbCatNW failed [%x]";
              v52 = 2615;
            }
            else
            {
              v51 = "RtlStringCbCatNW failed [%x]";
              v52 = 2608;
            }
          }
          else
          {
            v51 = "RtlStringCbCopyNW failed [%x]";
            v52 = 2601;
          }
          goto LABEL_81;
        }
        if ( matched != -1073741565 && matched != -1073741638 )
        {
          if ( matched < 0 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"AslPathWildcardFindNext",
              2585,
              (unsigned int)"AslpPathWildcardAllocMatchNode failed [%x]",
              matched);
          }
          else
          {
            v37 = a3[4];
            v38 = a3[5];
            if ( v37 >= v38 )
            {
              if ( v37 + 1 <= v38 )
              {
                v7 = -1073741811;
                goto LABEL_77;
              }
              v39 = a3[6] - 1;
              if ( a3[6] + v37 < v37 + 1
                || (v40 = a3[3], v41 = a3[5], pullResult = 0, Size = 0, ULongLongMult(v41, v40, &pullResult) < 0)
                || (v43 = v42 & ~v39, ULongLongMult(v43, a3[3], &Size) < 0) )
              {
                v7 = -1073741675;
LABEL_77:
                LOBYTE(v50) = v7;
LABEL_80:
                v51 = "AslpPathWildcardPushNode failed [%x]";
                v52 = 2577;
LABEL_81:
                AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindNext", v52, (_DWORD)v51, v50);
                goto LABEL_92;
              }
              v44 = Size;
              v45 = (void *)a3[7];
              PoolWithTag = ExAllocatePoolWithTag(PagedPool, Size, 0x72615452u);
              v47 = PoolWithTag;
              if ( v45 )
              {
                if ( !PoolWithTag )
                {
LABEL_75:
                  v7 = -1073741801;
                  goto LABEL_77;
                }
                memset_0(PoolWithTag, 0, v44);
                if ( pullResult < v44 )
                  v44 = pullResult;
                memmove(v47, v45, v44);
                ExFreePoolWithTag(v45, 0x72615452u);
              }
              else
              {
                if ( !PoolWithTag )
                  goto LABEL_75;
                memset_0(PoolWithTag, 0, v44);
              }
              a3[7] = (ULONGLONG)v47;
              a3[5] = v43;
            }
            v48 = a3[3];
            pullResult = 0;
            if ( ULongLongMult(v48, v37, &pullResult) < 0 || (v5 = a3[7], v49 = v5 + pullResult, v5 + pullResult < v5) )
            {
              v7 = -1073741675;
              LOBYTE(v50) = -107;
              goto LABEL_80;
            }
            *(UNICODE_STRING *)v49 = v57;
            *(_OWORD *)(v49 + 16) = v58;
            ++a3[4];
          }
        }
      }
    }
    else
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslPathWildcardFindNext",
        2503,
        (unsigned int)"Node on the stack with invalid handle.",
        IoStatusBlock);
LABEL_42:
      v30 = a3[4];
      if ( v30 )
      {
        v31 = a3[3];
        pullResult = 0;
        if ( ULongLongMult(v31, v30 - 1, &pullResult) < 0
          || (v32 = a3[7], v32 + pullResult < v32)
          || !(v32 + pullResult) )
        {
          v28 = -27;
          AslLogCallPrintf(
            1,
            (unsigned int)"AslpPathWildcardPeekNode",
            2079,
            (unsigned int)"RtlArrayGet failed to get the next node",
            IoStatusBlock);
          goto LABEL_37;
        }
        AslpPathWildcardFreeMatchNode();
        v12 = a3[4];
        if ( v12 )
        {
          v13 = a3[3];
          pullResult = 0;
          if ( ULongLongMult(v13, v12 - 1, &pullResult) >= 0 )
          {
            v5 = a3[7];
            v15 = (char *)(v5 + pullResult);
            if ( v5 + pullResult >= v5 )
            {
              v16 = a3[4];
              v17 = ~v14;
              v35 = v17 + v16 == 0;
              v18 = v17 + v16;
              Size = v18;
              if ( v35 )
                goto LABEL_23;
              if ( ULongLongMult(v18, a3[3], &Size) >= 0 )
              {
                v20 = a3[3];
                pullResult = 0;
                if ( ULongLongMult(v20, v19, &pullResult) >= 0 )
                {
                  v5 = a3[7];
                  if ( v5 + pullResult >= v5 )
                  {
                    v18 = Size;
                    memmove(v15, (const void *)(v5 + pullResult), Size);
LABEL_23:
                    memset_0(&v15[v18], 0, a3[3]);
                    v5 = --a3[4];
                    if ( v5 > 0x10 )
                    {
                      v21 = a3[5];
                      v22 = a3[3];
                      if ( v22 * v21 >= 0x400 && v5 < v21 >> 2 )
                      {
                        pullResult = 0;
                        Size = 0;
                        if ( ULongLongMult(v21, v22, &pullResult) >= 0 )
                        {
                          v23 = v21 >> 1;
                          if ( ULongLongMult(v23, a3[3], &Size) >= 0 )
                          {
                            v24 = Size;
                            v25 = (void *)a3[7];
                            v26 = ExAllocatePoolWithTag(PagedPool, Size, 0x72615452u);
                            v27 = v26;
                            if ( v25 )
                            {
                              if ( v26 )
                              {
                                memset_0(v26, 0, v24);
                                if ( pullResult < v24 )
                                  v24 = pullResult;
                                memmove(v27, v25, v24);
                                ExFreePoolWithTag(v25, 0x72615452u);
LABEL_35:
                                a3[7] = (ULONGLONG)v27;
                                a3[5] = v23;
                              }
                            }
                            else if ( v26 )
                            {
                              memset_0(v26, 0, v24);
                              goto LABEL_35;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        v28 = 26;
LABEL_37:
        AslLogCallPrintf(
          1,
          (unsigned int)"AslpPathWildcardPopNode",
          2106,
          (unsigned int)"AslpPathWildcardPeekNode failed [%x]",
          v28);
      }
    }
  }
  v7 = -2147483642;
LABEL_92:
  AslFree(v5, FileInformation);
  return v7;
}

```

## disassembly

```asm
0x14073ea34  mov     rax, rsp
0x14073ea37  mov     [rax+20h], rbx
0x14073ea3b  mov     [rax+10h], rdx
0x14073ea3f  mov     [rax+8], rcx
0x14073ea43  push    rbp
0x14073ea44  push    rsi
0x14073ea45  push    rdi
0x14073ea46  push    r12
0x14073ea48  push    r13
0x14073ea4a  push    r14
0x14073ea4c  push    r15
0x14073ea4e  lea     rbp, [rax-5Fh]
0x14073ea52  sub     rsp, 0A0h
0x14073ea59  mov     rbx, r8
0x14073ea5c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14073ea60  jnz     short loc_14073EA6C
0x14073ea62  mov     eax, 80000006h
0x14073ea67  jmp     loc_14073F168
0x14073ea6c  test    rcx, rcx
0x14073ea6f  jnz     short loc_14073EA7B
0x14073ea71  mov     eax, 0C00000EFh
0x14073ea76  jmp     loc_14073F168
0x14073ea7b  test    rbx, rbx
0x14073ea7e  jnz     short loc_14073EA8A
0x14073ea80  mov     eax, 0C00000F1h
0x14073ea85  jmp     loc_14073F168
0x14073ea8a  xorps   xmm0, xmm0
0x14073ea8d  xorps   xmm1, xmm1
0x14073ea90  mov     edx, 268h
0x14073ea95  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14073ea99  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14073ea9d  movups  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x14073eaa1  movups  [rbp+57h+var_40], xmm0
0x14073eaa5  call    AslAlloc
0x14073eaaa  mov     r12, rax
0x14073eaad  test    rax, rax
0x14073eab0  jnz     short loc_14073EABC
0x14073eab2  mov     edi, 0C0000017h
0x14073eab7  jmp     loc_14073F166
0x14073eabc  mov     r13d, 1
0x14073eac2  mov     rax, [rbx+20h]
0x14073eac6  cmp     rax, r13
0x14073eac9  jb      loc_14073F159
0x14073eacf  lea     rdx, [rax-1]; ullMultiplier
0x14073ead3  cmp     rdx, rax
0x14073ead6  jnb     loc_14073F116
0x14073eadc  mov     rcx, [rbx+18h]; ullMultiplicand
0x14073eae0  lea     r8, [rbp+57h+pullResult]; pullResult
0x14073eae4  mov     [rbp+57h+pullResult], 0
0x14073eaec  call    ULongLongMult
0x14073eaf1  test    eax, eax
0x14073eaf3  js      loc_14073F116
0x14073eaf9  mov     rcx, [rbx+38h]
0x14073eafd  mov     rsi, [rbp+57h+pullResult]
0x14073eb01  add     rsi, rcx
0x14073eb04  cmp     rsi, rcx
0x14073eb07  jb      loc_14073F116
0x14073eb0d  test    rsi, rsi
0x14073eb10  jz      loc_14073F116
0x14073eb16  cmp     qword ptr [rsi+18h], 0
0x14073eb1b  jnz     loc_14073ED40
0x14073eb21  lea     r9, aNodeOnTheStack; "Node on the stack with invalid handle."
0x14073eb28  mov     r8d, 9C7h
0x14073eb2e  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x14073eb35  mov     ecx, r13d
0x14073eb38  call    AslLogCallPrintf
0x14073eb3d  jmp     loc_14073EDF5
0x14073eb42  call    AslpPathWildcardFreeMatchNode
0x14073eb47  mov     r10, [rbx+20h]
0x14073eb4b  lea     r9, [r10-1]
0x14073eb4f  cmp     r9, r10
0x14073eb52  jnb     loc_14073EAC2
0x14073eb58  mov     rcx, [rbx+18h]; ullMultiplicand
0x14073eb5c  lea     r8, [rbp+57h+pullResult]; pullResult
0x14073eb60  mov     rdx, r9; ullMultiplier
0x14073eb63  mov     [rbp+57h+pullResult], 0
0x14073eb6b  call    ULongLongMult
0x14073eb70  test    eax, eax
0x14073eb72  js      loc_14073EAC2
0x14073eb78  mov     rcx, [rbx+38h]
0x14073eb7c  mov     rsi, [rbp+57h+pullResult]
0x14073eb80  add     rsi, rcx
0x14073eb83  cmp     rsi, rcx
0x14073eb86  jb      loc_14073EAC2
0x14073eb8c  mov     rdi, [rbx+20h]
0x14073eb90  not     r9
0x14073eb93  add     rdi, r9
0x14073eb96  mov     [rbp+57h+Size], rdi
0x14073eb9a  jz      short loc_14073EBF7
0x14073eb9c  mov     rdx, [rbx+18h]; ullMultiplier
0x14073eba0  lea     r8, [rbp+57h+Size]; pullResult
0x14073eba4  mov     rcx, rdi; ullMultiplicand
0x14073eba7  call    ULongLongMult
0x14073ebac  test    eax, eax
0x14073ebae  js      loc_14073EAC2
0x14073ebb4  mov     rcx, [rbx+18h]; ullMultiplicand
0x14073ebb8  lea     r8, [rbp+57h+pullResult]; pullResult
0x14073ebbc  mov     rdx, r10; ullMultiplier
0x14073ebbf  mov     [rbp+57h+pullResult], 0
0x14073ebc7  call    ULongLongMult
0x14073ebcc  test    eax, eax
0x14073ebce  js      loc_14073EAC2
0x14073ebd4  mov     rcx, [rbx+38h]
0x14073ebd8  mov     rdx, [rbp+57h+pullResult]
0x14073ebdc  add     rdx, rcx; Src
0x14073ebdf  cmp     rdx, rcx
0x14073ebe2  jb      loc_14073EAC2
0x14073ebe8  mov     rdi, [rbp+57h+Size]
0x14073ebec  mov     rcx, rsi; void *
0x14073ebef  mov     r8, rdi; Size
0x14073ebf2  call    memmove
0x14073ebf7  mov     r8, [rbx+18h]; Size
0x14073ebfb  lea     rcx, [rdi+rsi]; void *
0x14073ebff  xor     edx, edx; Val
0x14073ec01  call    memset_0
0x14073ec06  dec     qword ptr [rbx+20h]
0x14073ec0a  mov     rcx, [rbx+20h]
0x14073ec0e  cmp     rcx, 10h
0x14073ec12  jbe     loc_14073EAC2
0x14073ec18  mov     rsi, [rbx+28h]
0x14073ec1c  mov     rdx, [rbx+18h]; ullMultiplier
0x14073ec20  mov     rax, rsi
0x14073ec23  imul    rax, rdx
0x14073ec27  cmp     rax, 400h
0x14073ec2d  jb      loc_14073EAC2
0x14073ec33  mov     rax, rsi
0x14073ec36  shr     rax, 2
0x14073ec3a  cmp     rcx, rax
0x14073ec3d  jnb     loc_14073EAC2
0x14073ec43  lea     r8, [rbp+57h+pullResult]; pullResult
0x14073ec47  mov     [rbp+57h+pullResult], 0
0x14073ec4f  mov     rcx, rsi; ullMultiplicand
0x14073ec52  mov     [rbp+57h+Size], 0
0x14073ec5a  call    ULongLongMult
0x14073ec5f  test    eax, eax
0x14073ec61  js      loc_14073EAC2
0x14073ec67  mov     rdx, [rbx+18h]; ullMultiplier
0x14073ec6b  lea     r8, [rbp+57h+Size]; pullResult
0x14073ec6f  shr     rsi, 1
0x14073ec72  mov     rcx, rsi; ullMultiplicand
0x14073ec75  call    ULongLongMult
0x14073ec7a  test    eax, eax
0x14073ec7c  js      loc_14073EAC2
0x14073ec82  mov     r14, [rbp+57h+Size]
0x14073ec86  mov     r8d, 72615452h; Tag
0x14073ec8c  mov     r15, [rbx+38h]
0x14073ec90  mov     rdx, r14; NumberOfBytes
0x14073ec93  mov     ecx, r13d; PoolType
0x14073ec96  call    ExAllocatePoolWithTag
0x14073ec9b  mov     rdi, rax
0x14073ec9e  test    r15, r15
0x14073eca1  jnz     short loc_14073ECBB
0x14073eca3  test    rax, rax
0x14073eca6  jz      loc_14073EAC2
0x14073ecac  mov     r8, r14; Size
0x14073ecaf  xor     edx, edx; Val
0x14073ecb1  mov     rcx, rax; void *
0x14073ecb4  call    memset_0
0x14073ecb9  jmp     short loc_14073ECF5
0x14073ecbb  test    rax, rax
0x14073ecbe  jz      loc_14073EAC2
0x14073ecc4  mov     r8, r14; Size
0x14073ecc7  xor     edx, edx; Val
0x14073ecc9  mov     rcx, rdi; void *
0x14073eccc  call    memset_0
0x14073ecd1  cmp     [rbp+57h+pullResult], r14
0x14073ecd5  mov     rdx, r15; Src
0x14073ecd8  mov     rcx, rdi; void *
0x14073ecdb  cmovb   r14, [rbp+57h+pullResult]
0x14073ece0  mov     r8, r14; Size
0x14073ece3  call    memmove
0x14073ece8  mov     edx, 72615452h; Tag
0x14073eced  mov     rcx, r15; P
0x14073ecf0  call    ExFreePoolWithTag
0x14073ecf5  mov     [rbx+38h], rdi
0x14073ecf9  mov     [rbx+28h], rsi
0x14073ecfd  jmp     loc_14073EAC2
0x14073ed02  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x14073ed09  mov     r8d, 81Fh
0x14073ed0f  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x14073ed16  mov     ecx, r13d
0x14073ed19  mov     edi, 0C00000E5h
0x14073ed1e  call    AslLogCallPrintf
0x14073ed23  mov     dword ptr [rsp+0D0h+IoStatusBlock], edi
0x14073ed27  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x14073ed2e  mov     r8d, 83Ah
0x14073ed34  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x14073ed3b  jmp     loc_14073F051
0x14073ed40  mov     rdx, [rsi+10h]; SourceString
0x14073ed44  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14073ed48  call    RtlInitUnicodeString
0x14073ed4d  mov     rcx, [rsi+18h]; FileHandle
0x14073ed51  lea     rax, [rbp+57h+DestinationString]
0x14073ed55  mov     byte ptr [rsp+50h], 0; RestartScan
0x14073ed5a  xor     r9d, r9d; ApcContext
0x14073ed5d  mov     [rsp+0D0h+FileName], rax; FileName
0x14073ed62  xor     r8d, r8d; ApcRoutine
0x14073ed65  mov     [rsp+0D0h+ReturnSingleEntry], r13b; ReturnSingleEntry
0x14073ed6a  lea     rax, [rbp+57h+var_60]
0x14073ed6e  mov     [rsp+0D0h+FileInformationClass], 3; FileInformationClass
0x14073ed76  xor     edx, edx; Event
0x14073ed78  mov     [rsp+0D0h+Length], 268h; Length
0x14073ed80  mov     [rsp+0D0h+FileInformation], r12; FileInformation
0x14073ed85  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x14073ed8a  call    ZwQueryDirectoryFile
0x14073ed8f  test    eax, eax
0x14073ed91  jns     loc_14073EE54
0x14073ed97  cmp     eax, 80000006h
0x14073ed9c  jz      short loc_14073EDF5
0x14073ed9e  cmp     eax, 0C000000Fh
0x14073eda3  jz      short loc_14073EDF5
0x14073eda5  lea     r9, aNtquerydirecto_0; "NtQueryDirectoryFile failed to query ne"...
0x14073edac  mov     dword ptr [rsp+0D0h+IoStatusBlock], eax
0x14073edb0  mov     r8d, 9DFh
0x14073edb6  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x14073edbd  mov     ecx, r13d
0x14073edc0  call    AslLogCallPrintf
0x14073edc5  mov     rax, [rbp+57h+DestinationString.Buffer]
0x14073edc9  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x14073edd0  mov     [rsp+0D0h+FileInformation], rax
0x14073edd5  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x14073eddc  mov     rax, [rsi+8]
0x14073ede0  mov     r8d, 9E0h
0x14073ede6  mov     ecx, 2
0x14073edeb  mov     [rsp+0D0h+IoStatusBlock], rax
0x14073edf0  call    AslLogCallPrintf
0x14073edf5  mov     rax, [rbx+20h]
0x14073edf9  cmp     rax, r13
0x14073edfc  jnb     short loc_14073EE08
0x14073edfe  mov     edi, 8000001Ah
0x14073ee03  jmp     loc_14073ED23
0x14073ee08  lea     rdx, [rax-1]; ullMultiplier
0x14073ee0c  cmp     rdx, rax
0x14073ee0f  jnb     loc_14073ED02
0x14073ee15  mov     rcx, [rbx+18h]; ullMultiplicand
0x14073ee19  lea     r8, [rbp+57h+pullResult]; pullResult
0x14073ee1d  mov     [rbp+57h+pullResult], 0
0x14073ee25  call    ULongLongMult
0x14073ee2a  test    eax, eax
0x14073ee2c  js      loc_14073ED02
0x14073ee32  mov     rdx, [rbx+38h]
0x14073ee36  mov     rcx, [rbp+57h+pullResult]
0x14073ee3a  add     rcx, rdx
0x14073ee3d  cmp     rcx, rdx
0x14073ee40  jb      loc_14073ED02
0x14073ee46  test    rcx, rcx
0x14073ee49  jnz     loc_14073EB42
0x14073ee4f  jmp     loc_14073ED02
0x14073ee54  mov     eax, [r12+3Ch]
0x14073ee59  lea     r14, [r12+5Eh]
0x14073ee5e  cmp     eax, 4
0x14073ee61  jnz     short loc_14073EE73
0x14073ee63  cmp     word ptr [r14], 2Eh ; '.'
0x14073ee68  jnz     short loc_14073EE88
0x14073ee6a  cmp     word ptr [r12+60h], 2Eh ; '.'
0x14073ee71  jmp     short loc_14073EE82
0x14073ee73  cmp     eax, 2
0x14073ee76  jnz     short loc_14073EE88
0x14073ee78  lea     r14, [r12+5Eh]
0x14073ee7d  cmp     word ptr [r14], 2Eh ; '.'
0x14073ee82  jz      loc_14073EAC2
0x14073ee88  mov     r9d, [r12+38h]
0x14073ee8d  lea     rcx, [rbp+57h+var_50]; DestinationString
0x14073ee91  movzx   eax, word ptr [r12+3Ch]
0x14073ee97  mov     rdx, rsi; SourceString
0x14073ee9a  mov     r8, [rsi+10h]
0x14073ee9e  shr     r9d, 4
0x14073eea2  mov     word ptr [rsp+0D0h+FileInformation], ax; __int16
0x14073eea7  and     r9d, r13d
0x14073eeaa  mov     [rsp+0D0h+IoStatusBlock], r14; pszSrc
0x14073eeaf  call    AslpPathWildcardAllocMatchNode
0x14073eeb4  cmp     eax, 0C0000273h
0x14073eeb9  jz      loc_14073F080
0x14073eebf  cmp     eax, 0C0000103h
0x14073eec4  jz      loc_14073EAC2
0x14073eeca  cmp     eax, 0C00000BAh
0x14073eecf  jz      loc_14073EAC2
0x14073eed5  test    eax, eax
0x14073eed7  js      loc_14073F039
0x14073eedd  mov     r13, [rbx+20h]
0x14073eee1  mov     r9, [rbx+28h]
0x14073eee5  cmp     r13, r9
0x14073eee8  jb      loc_14073EFD8
0x14073eeee  lea     rcx, [r13+1]
0x14073eef2  cmp     rcx, r9
0x14073eef5  ja      short loc_14073EF01
0x14073eef7  mov     edi, 0C000000Dh
0x14073eefc  jmp     loc_14073F02E
0x14073ef01  mov     r14, [rbx+30h]
0x14073ef05  dec     r14
0x14073ef08  lea     r10, [r14+rcx]
0x14073ef0c  cmp     r10, rcx
0x14073ef0f  jb      loc_14073F029
0x14073ef15  mov     rdx, [rbx+18h]; ullMultiplier
0x14073ef19  lea     r8, [rbp+57h+pullResult]; pullResult
0x14073ef1d  mov     rcx, r9; ullMultiplicand
0x14073ef20  mov     [rbp+57h+pullResult], 0
0x14073ef28  mov     [rbp+57h+Size], 0
0x14073ef30  call    ULongLongMult
0x14073ef35  test    eax, eax
  ... truncated ...
```
