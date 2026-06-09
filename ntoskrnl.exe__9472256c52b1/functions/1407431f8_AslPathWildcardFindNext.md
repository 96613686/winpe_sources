# AslPathWildcardFindNext

- ea: `0x1407431f8`
- end: `0x140743948`
- name: `AslPathWildcardFindNext`
- size: `1872`
- prototype: `__int64 __fastcall(wchar_t *, ULONGLONG, ULONGLONG *)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x14073a320`
- `0x14074209c`

## callees

- `0x140403380`
- `0x14043a410`
- `0x14045a2fc`
- `0x1406ce4ec`
- `0x1406dda80`
- `0x1406f6f80`
- `0x1406f7380`
- `0x1407431f8`
- `0x140743950`
- `0x140829754`
- `0x1408bf658`
- `0x1408c14bc`
- `0x1408c2f88`
- `0x140bb1320`
- `0x140bb19f0`

## string_xrefs

- `0x140743829`: `AslpPathWildcardPushNode failed [%x]`
- `0x1407434eb`: `AslpPathWildcardPeekNode failed [%x]`
- `0x1407438fb`: `AslpPathWildcardPeekNode failed [%x]`
- `0x1407434d3`: `AslpPathWildcardPeekNode`
- `0x1407438e7`: `AslpPathWildcardPeekNode`
- `0x1407434f8`: `AslpPathWildcardPopNode`
- `0x1407432f2`: `AslPathWildcardFindNext`
- `0x14074357a`: `AslPathWildcardFindNext`
- `0x140743599`: `AslPathWildcardFindNext`
- `0x14074380e`: `AslPathWildcardFindNext`
- `0x14074390f`: `AslPathWildcardFindNext`
- `0x14074358d`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x140743801`: `AslpPathWildcardAllocMatchNode failed [%x]`
- `0x140743569`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x140743863`: `RtlStringCbCopyNW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindNext(wchar_t *a1, ULONGLONG a2, ULONGLONG *a3)
{
  unsigned __int64 v5; // rcx
  __int16 *FileInformation; // r12
  NTSTATUS v7; // edi
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
  const char *v28; // r9
  int v29; // r8d
  const char *v30; // rdx
  NTSTATUS v31; // eax
  ULONGLONG v32; // rax
  ULONGLONG v33; // rcx
  ULONGLONG v34; // rdx
  ULONGLONG v35; // rcx
  int v36; // eax
  const wchar_t *v37; // r14
  bool v38; // zf
  int matched; // eax
  ULONGLONG v40; // r13
  unsigned __int64 v41; // r9
  __int64 v42; // r14
  ULONGLONG v43; // rdx
  ULONGLONG v44; // rcx
  __int64 v45; // r10
  ULONGLONG v46; // r14
  size_t v47; // rsi
  void *v48; // r15
  PVOID PoolWithTag; // rax
  void *v50; // rdi
  ULONGLONG v51; // rcx
  unsigned __int64 v52; // rdx
  const char *v53; // r9
  int v54; // r8d
  size_t v55; // rdx
  UNICODE_STRING DestinationString; // [rsp+68h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-9h] BYREF
  UNICODE_STRING v58; // [rsp+88h] [rbp+7h] BYREF
  __int128 v59; // [rsp+98h] [rbp+17h]
  ULONGLONG pullResult; // [rsp+F0h] [rbp+6Fh] BYREF
  ULONGLONG Size; // [rsp+F8h] [rbp+77h] BYREF

  pullResult = a2;
  if ( a3 == (ULONGLONG *)-1LL )
    return 2147483654LL;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 )
    return 3221225713LL;
  IoStatusBlock = 0;
  DestinationString = 0;
  v58 = 0;
  v59 = 0;
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
        (unsigned int)"RtlArrayGet failed to get the next node");
      v7 = -1073741595;
      v53 = "AslpPathWildcardPeekNode failed [%x]";
      v54 = 2498;
      goto LABEL_89;
    }
    if ( *((_QWORD *)v11 + 3) )
    {
      RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v11 + 2));
      v31 = ZwQueryDirectoryFile(
              *((HANDLE *)v11 + 3),
              0,
              0,
              0,
              &IoStatusBlock,
              FileInformation,
              0x268u,
              FileBothDirectoryInformation,
              1u,
              &DestinationString,
              0);
      if ( v31 < 0 )
      {
        if ( v31 != -2147483642 && v31 != -1073741809 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"AslPathWildcardFindNext",
            2527,
            (unsigned int)"NtQueryDirectoryFile failed to query next file [%x]");
          AslLogCallPrintf(
            2,
            (unsigned int)"AslPathWildcardFindNext",
            2528,
            (unsigned int)"FilePath: '%ws'  Pattern: '%ws'");
        }
        goto LABEL_42;
      }
      v36 = *((_DWORD *)FileInformation + 15);
      v37 = (const wchar_t *)(FileInformation + 47);
      if ( v36 == 4 )
      {
        if ( *v37 != 46 )
          goto LABEL_53;
        v38 = FileInformation[48] == 46;
LABEL_52:
        if ( !v38 )
          goto LABEL_53;
      }
      else
      {
        if ( v36 == 2 )
        {
          v37 = (const wchar_t *)(FileInformation + 47);
          v38 = FileInformation[47] == 46;
          goto LABEL_52;
        }
LABEL_53:
        matched = AslpPathWildcardAllocMatchNode(&v58, (PCUNICODE_STRING)v11, v37, FileInformation[30]);
        if ( matched == -1073741197 )
        {
          v7 = RtlStringCbCopyNW(a1, 0x208u, *((STRSAFE_PCNZWCH *)v11 + 1), *v11);
          if ( v7 >= 0 )
          {
            if ( *(_WORD *)(*((_QWORD *)v11 + 1) + 2 * ((unsigned __int64)*v11 >> 1) - 2) == 92
              || (v7 = RtlStringCbCatNW(a1, v55, L"\\", 2u), v7 >= 0) )
            {
              v7 = RtlStringCbCatNW(a1, v55, v37, *((unsigned int *)FileInformation + 15));
              if ( v7 >= 0 )
              {
                v7 = 0;
                goto LABEL_91;
              }
              v53 = "RtlStringCbCatNW failed [%x]";
              v54 = 2615;
            }
            else
            {
              v53 = "RtlStringCbCatNW failed [%x]";
              v54 = 2608;
            }
          }
          else
          {
            v53 = "RtlStringCbCopyNW failed [%x]";
            v54 = 2601;
          }
          goto LABEL_89;
        }
        if ( matched != -1073741565 && matched != -1073741638 )
        {
          if ( matched < 0 )
          {
            v28 = "AslpPathWildcardAllocMatchNode failed [%x]";
            v29 = 2585;
            v30 = "AslPathWildcardFindNext";
LABEL_77:
            AslLogCallPrintf(1, (_DWORD)v30, v29, (_DWORD)v28);
          }
          else
          {
            v40 = a3[4];
            v41 = a3[5];
            if ( v40 >= v41 )
            {
              if ( v40 + 1 <= v41 )
              {
                v7 = -1073741811;
LABEL_79:
                v53 = "AslpPathWildcardPushNode failed [%x]";
                v54 = 2577;
LABEL_89:
                AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindNext", v54, (_DWORD)v53);
                goto LABEL_91;
              }
              v42 = a3[6] - 1;
              if ( a3[6] + v40 < v40 + 1
                || (v43 = a3[3], v44 = a3[5], pullResult = 0, Size = 0, ULongLongMult(v44, v43, &pullResult) < 0)
                || (v46 = v45 & ~v42, ULongLongMult(v46, a3[3], &Size) < 0) )
              {
                v7 = -1073741675;
                goto LABEL_79;
              }
              v47 = Size;
              v48 = (void *)a3[7];
              PoolWithTag = ExAllocatePoolWithTag(PagedPool, Size, 0x72615452u);
              v50 = PoolWithTag;
              if ( v48 )
              {
                if ( !PoolWithTag )
                {
LABEL_74:
                  v7 = -1073741801;
                  goto LABEL_79;
                }
                memset_0(PoolWithTag, 0, v47);
                if ( pullResult < v47 )
                  v47 = pullResult;
                memmove(v50, v48, v47);
                ExFreePoolWithTag(v48, 0x72615452u);
              }
              else
              {
                if ( !PoolWithTag )
                  goto LABEL_74;
                memset_0(PoolWithTag, 0, v47);
              }
              a3[7] = (ULONGLONG)v50;
              a3[5] = v46;
            }
            v51 = a3[3];
            pullResult = 0;
            if ( ULongLongMult(v51, v40, &pullResult) < 0 || (v5 = a3[7], v52 = v5 + pullResult, v5 + pullResult < v5) )
            {
              v7 = -1073741675;
              goto LABEL_79;
            }
            *(UNICODE_STRING *)v52 = v58;
            *(_OWORD *)(v52 + 16) = v59;
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
        (unsigned int)"Node on the stack with invalid handle.");
LABEL_42:
      v32 = a3[4];
      if ( !v32 )
        goto LABEL_37;
      v33 = a3[3];
      pullResult = 0;
      if ( ULongLongMult(v33, v32 - 1, &pullResult) < 0
        || (v34 = a3[7], v35 = v34 + pullResult, v34 + pullResult < v34)
        || !v35 )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"AslpPathWildcardPeekNode",
          2079,
          (unsigned int)"RtlArrayGet failed to get the next node");
LABEL_37:
        v28 = "AslpPathWildcardPeekNode failed [%x]";
        v29 = 2106;
        v30 = "AslpPathWildcardPopNode";
        goto LABEL_77;
      }
      AslpPathWildcardFreeMatchNode(v35);
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
            v38 = v17 + v16 == 0;
            v18 = v17 + v16;
            Size = v18;
            if ( v38 )
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
  }
  v7 = -2147483642;
LABEL_91:
  AslFree(v5, FileInformation);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1407431f8  mov     rax, rsp
0x1407431fb  mov     [rax+20h], rbx
0x1407431ff  mov     [rax+10h], rdx
0x140743203  mov     [rax+8], rcx
0x140743207  push    rbp
0x140743208  push    rsi
0x140743209  push    rdi
0x14074320a  push    r12
0x14074320c  push    r13
0x14074320e  push    r14
0x140743210  push    r15
0x140743212  lea     rbp, [rax-5Fh]
0x140743216  sub     rsp, 0A0h
0x14074321d  mov     rbx, r8
0x140743220  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140743224  jnz     short loc_140743230
0x140743226  mov     eax, 80000006h
0x14074322b  jmp     loc_14074392C
0x140743230  test    rcx, rcx
0x140743233  jnz     short loc_14074323F
0x140743235  mov     eax, 0C00000EFh
0x14074323a  jmp     loc_14074392C
0x14074323f  test    rbx, rbx
0x140743242  jnz     short loc_14074324E
0x140743244  mov     eax, 0C00000F1h
0x140743249  jmp     loc_14074392C
0x14074324e  xorps   xmm0, xmm0
0x140743251  xorps   xmm1, xmm1
0x140743254  mov     edx, 268h
0x140743259  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14074325d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140743261  movups  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x140743265  movups  [rbp+57h+var_40], xmm0
0x140743269  call    AslAlloc
0x14074326e  mov     r12, rax
0x140743271  test    rax, rax
0x140743274  jnz     short loc_140743280
0x140743276  mov     edi, 0C0000017h
0x14074327b  jmp     loc_14074392A
0x140743280  mov     r13d, 1
0x140743286  mov     rax, [rbx+20h]
0x14074328a  cmp     rax, r13
0x14074328d  jb      loc_14074391D
0x140743293  lea     rdx, [rax-1]; ullMultiplier
0x140743297  cmp     rdx, rax
0x14074329a  jnb     loc_1407438DA
0x1407432a0  mov     rcx, [rbx+18h]; ullMultiplicand
0x1407432a4  lea     r8, [rbp+57h+pullResult]; pullResult
0x1407432a8  mov     [rbp+57h+pullResult], 0
0x1407432b0  call    ULongLongMult
0x1407432b5  test    eax, eax
0x1407432b7  js      loc_1407438DA
0x1407432bd  mov     rcx, [rbx+38h]
0x1407432c1  mov     rsi, [rbp+57h+pullResult]
0x1407432c5  add     rsi, rcx
0x1407432c8  cmp     rsi, rcx
0x1407432cb  jb      loc_1407438DA
0x1407432d1  test    rsi, rsi
0x1407432d4  jz      loc_1407438DA
0x1407432da  cmp     qword ptr [rsi+18h], 0
0x1407432df  jnz     loc_140743504
0x1407432e5  lea     r9, aNodeOnTheStack; "Node on the stack with invalid handle."
0x1407432ec  mov     r8d, 9C7h
0x1407432f2  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x1407432f9  mov     ecx, r13d
0x1407432fc  call    AslLogCallPrintf
0x140743301  jmp     loc_1407435B9
0x140743306  call    AslpPathWildcardFreeMatchNode
0x14074330b  mov     r10, [rbx+20h]
0x14074330f  lea     r9, [r10-1]
0x140743313  cmp     r9, r10
0x140743316  jnb     loc_140743286
0x14074331c  mov     rcx, [rbx+18h]; ullMultiplicand
0x140743320  lea     r8, [rbp+57h+pullResult]; pullResult
0x140743324  mov     rdx, r9; ullMultiplier
0x140743327  mov     [rbp+57h+pullResult], 0
0x14074332f  call    ULongLongMult
0x140743334  test    eax, eax
0x140743336  js      loc_140743286
0x14074333c  mov     rcx, [rbx+38h]
0x140743340  mov     rsi, [rbp+57h+pullResult]
0x140743344  add     rsi, rcx
0x140743347  cmp     rsi, rcx
0x14074334a  jb      loc_140743286
0x140743350  mov     rdi, [rbx+20h]
0x140743354  not     r9
0x140743357  add     rdi, r9
0x14074335a  mov     [rbp+57h+Size], rdi
0x14074335e  jz      short loc_1407433BB
0x140743360  mov     rdx, [rbx+18h]; ullMultiplier
0x140743364  lea     r8, [rbp+57h+Size]; pullResult
0x140743368  mov     rcx, rdi; ullMultiplicand
0x14074336b  call    ULongLongMult
0x140743370  test    eax, eax
0x140743372  js      loc_140743286
0x140743378  mov     rcx, [rbx+18h]; ullMultiplicand
0x14074337c  lea     r8, [rbp+57h+pullResult]; pullResult
0x140743380  mov     rdx, r10; ullMultiplier
0x140743383  mov     [rbp+57h+pullResult], 0
0x14074338b  call    ULongLongMult
0x140743390  test    eax, eax
0x140743392  js      loc_140743286
0x140743398  mov     rcx, [rbx+38h]
0x14074339c  mov     rdx, [rbp+57h+pullResult]
0x1407433a0  add     rdx, rcx; Src
0x1407433a3  cmp     rdx, rcx
0x1407433a6  jb      loc_140743286
0x1407433ac  mov     rdi, [rbp+57h+Size]
0x1407433b0  mov     rcx, rsi; void *
0x1407433b3  mov     r8, rdi; Size
0x1407433b6  call    memmove
0x1407433bb  mov     r8, [rbx+18h]; Size
0x1407433bf  lea     rcx, [rdi+rsi]; void *
0x1407433c3  xor     edx, edx; Val
0x1407433c5  call    memset_0
0x1407433ca  dec     qword ptr [rbx+20h]
0x1407433ce  mov     rcx, [rbx+20h]
0x1407433d2  cmp     rcx, 10h
0x1407433d6  jbe     loc_140743286
0x1407433dc  mov     rsi, [rbx+28h]
0x1407433e0  mov     rdx, [rbx+18h]; ullMultiplier
0x1407433e4  mov     rax, rsi
0x1407433e7  imul    rax, rdx
0x1407433eb  cmp     rax, 400h
0x1407433f1  jb      loc_140743286
0x1407433f7  mov     rax, rsi
0x1407433fa  shr     rax, 2
0x1407433fe  cmp     rcx, rax
0x140743401  jnb     loc_140743286
0x140743407  lea     r8, [rbp+57h+pullResult]; pullResult
0x14074340b  mov     [rbp+57h+pullResult], 0
0x140743413  mov     rcx, rsi; ullMultiplicand
0x140743416  mov     [rbp+57h+Size], 0
0x14074341e  call    ULongLongMult
0x140743423  test    eax, eax
0x140743425  js      loc_140743286
0x14074342b  mov     rdx, [rbx+18h]; ullMultiplier
0x14074342f  lea     r8, [rbp+57h+Size]; pullResult
0x140743433  shr     rsi, 1
0x140743436  mov     rcx, rsi; ullMultiplicand
0x140743439  call    ULongLongMult
0x14074343e  test    eax, eax
0x140743440  js      loc_140743286
0x140743446  mov     r14, [rbp+57h+Size]
0x14074344a  mov     r8d, 72615452h; Tag
0x140743450  mov     r15, [rbx+38h]
0x140743454  mov     rdx, r14; NumberOfBytes
0x140743457  mov     ecx, r13d; PoolType
0x14074345a  call    ExAllocatePoolWithTag
0x14074345f  mov     rdi, rax
0x140743462  test    r15, r15
0x140743465  jnz     short loc_14074347F
0x140743467  test    rax, rax
0x14074346a  jz      loc_140743286
0x140743470  mov     r8, r14; Size
0x140743473  xor     edx, edx; Val
0x140743475  mov     rcx, rax; void *
0x140743478  call    memset_0
0x14074347d  jmp     short loc_1407434B9
0x14074347f  test    rax, rax
0x140743482  jz      loc_140743286
0x140743488  mov     r8, r14; Size
0x14074348b  xor     edx, edx; Val
0x14074348d  mov     rcx, rdi; void *
0x140743490  call    memset_0
0x140743495  cmp     [rbp+57h+pullResult], r14
0x140743499  mov     rdx, r15; Src
0x14074349c  mov     rcx, rdi; void *
0x14074349f  cmovb   r14, [rbp+57h+pullResult]
0x1407434a4  mov     r8, r14; Size
0x1407434a7  call    memmove
0x1407434ac  mov     edx, 72615452h; Tag
0x1407434b1  mov     rcx, r15; P
0x1407434b4  call    ExFreePoolWithTag
0x1407434b9  mov     [rbx+38h], rdi
0x1407434bd  mov     [rbx+28h], rsi
0x1407434c1  jmp     loc_140743286
0x1407434c6  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x1407434cd  mov     r8d, 81Fh
0x1407434d3  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x1407434da  mov     ecx, r13d
0x1407434dd  mov     edi, 0C00000E5h
0x1407434e2  call    AslLogCallPrintf
0x1407434e7  mov     dword ptr [rsp+0D0h+IoStatusBlock], edi
0x1407434eb  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x1407434f2  mov     r8d, 83Ah
0x1407434f8  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x1407434ff  jmp     loc_140743815
0x140743504  mov     rdx, [rsi+10h]; SourceString
0x140743508  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14074350c  call    RtlInitUnicodeString
0x140743511  mov     rcx, [rsi+18h]; FileHandle
0x140743515  lea     rax, [rbp+57h+DestinationString]
0x140743519  mov     byte ptr [rsp+50h], 0; RestartScan
0x14074351e  xor     r9d, r9d; ApcContext
0x140743521  mov     [rsp+0D0h+FileName], rax; FileName
0x140743526  xor     r8d, r8d; ApcRoutine
0x140743529  mov     [rsp+0D0h+ReturnSingleEntry], r13b; ReturnSingleEntry
0x14074352e  lea     rax, [rbp+57h+var_60]
0x140743532  mov     [rsp+0D0h+FileInformationClass], 3; FileInformationClass
0x14074353a  xor     edx, edx; Event
0x14074353c  mov     [rsp+0D0h+Length], 268h; Length
0x140743544  mov     [rsp+0D0h+FileInformation], r12; FileInformation
0x140743549  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x14074354e  call    ZwQueryDirectoryFile
0x140743553  test    eax, eax
0x140743555  jns     loc_140743618
0x14074355b  cmp     eax, 80000006h
0x140743560  jz      short loc_1407435B9
0x140743562  cmp     eax, 0C000000Fh
0x140743567  jz      short loc_1407435B9
0x140743569  lea     r9, aNtquerydirecto_0; "NtQueryDirectoryFile failed to query ne"...
0x140743570  mov     dword ptr [rsp+0D0h+IoStatusBlock], eax
0x140743574  mov     r8d, 9DFh
0x14074357a  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x140743581  mov     ecx, r13d
0x140743584  call    AslLogCallPrintf
0x140743589  mov     rax, [rbp+57h+DestinationString.Buffer]
0x14074358d  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x140743594  mov     [rsp+0D0h+FileInformation], rax
0x140743599  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x1407435a0  mov     rax, [rsi+8]
0x1407435a4  mov     r8d, 9E0h
0x1407435aa  mov     ecx, 2
0x1407435af  mov     [rsp+0D0h+IoStatusBlock], rax
0x1407435b4  call    AslLogCallPrintf
0x1407435b9  mov     rax, [rbx+20h]
0x1407435bd  cmp     rax, r13
0x1407435c0  jnb     short loc_1407435CC
0x1407435c2  mov     edi, 8000001Ah
0x1407435c7  jmp     loc_1407434E7
0x1407435cc  lea     rdx, [rax-1]; ullMultiplier
0x1407435d0  cmp     rdx, rax
0x1407435d3  jnb     loc_1407434C6
0x1407435d9  mov     rcx, [rbx+18h]; ullMultiplicand
0x1407435dd  lea     r8, [rbp+57h+pullResult]; pullResult
0x1407435e1  mov     [rbp+57h+pullResult], 0
0x1407435e9  call    ULongLongMult
0x1407435ee  test    eax, eax
0x1407435f0  js      loc_1407434C6
0x1407435f6  mov     rdx, [rbx+38h]
0x1407435fa  mov     rcx, [rbp+57h+pullResult]
0x1407435fe  add     rcx, rdx
0x140743601  cmp     rcx, rdx
0x140743604  jb      loc_1407434C6
0x14074360a  test    rcx, rcx
0x14074360d  jnz     loc_140743306
0x140743613  jmp     loc_1407434C6
0x140743618  mov     eax, [r12+3Ch]
0x14074361d  lea     r14, [r12+5Eh]
0x140743622  cmp     eax, 4
0x140743625  jnz     short loc_140743637
0x140743627  cmp     word ptr [r14], 2Eh ; '.'
0x14074362c  jnz     short loc_14074364C
0x14074362e  cmp     word ptr [r12+60h], 2Eh ; '.'
0x140743635  jmp     short loc_140743646
0x140743637  cmp     eax, 2
0x14074363a  jnz     short loc_14074364C
0x14074363c  lea     r14, [r12+5Eh]
0x140743641  cmp     word ptr [r14], 2Eh ; '.'
0x140743646  jz      loc_140743286
0x14074364c  mov     r9d, [r12+38h]
0x140743651  lea     rcx, [rbp+57h+var_50]; DestinationString
0x140743655  movzx   eax, word ptr [r12+3Ch]
0x14074365b  mov     rdx, rsi; SourceString
0x14074365e  mov     r8, [rsi+10h]
0x140743662  shr     r9d, 4
0x140743666  mov     word ptr [rsp+0D0h+FileInformation], ax; __int16
0x14074366b  and     r9d, r13d
0x14074366e  mov     [rsp+0D0h+IoStatusBlock], r14; pszSrc
0x140743673  call    AslpPathWildcardAllocMatchNode
0x140743678  cmp     eax, 0C0000273h
0x14074367d  jz      loc_140743844
0x140743683  cmp     eax, 0C0000103h
0x140743688  jz      loc_140743286
0x14074368e  cmp     eax, 0C00000BAh
0x140743693  jz      loc_140743286
0x140743699  test    eax, eax
0x14074369b  js      loc_1407437FD
0x1407436a1  mov     r13, [rbx+20h]
0x1407436a5  mov     r9, [rbx+28h]
0x1407436a9  cmp     r13, r9
0x1407436ac  jb      loc_14074379C
0x1407436b2  lea     rcx, [r13+1]
0x1407436b6  cmp     rcx, r9
0x1407436b9  ja      short loc_1407436C5
0x1407436bb  mov     edi, 0C000000Dh
0x1407436c0  jmp     loc_1407437F2
0x1407436c5  mov     r14, [rbx+30h]
0x1407436c9  dec     r14
0x1407436cc  lea     r10, [r14+rcx]
0x1407436d0  cmp     r10, rcx
0x1407436d3  jb      loc_1407437ED
0x1407436d9  mov     rdx, [rbx+18h]; ullMultiplier
0x1407436dd  lea     r8, [rbp+57h+pullResult]; pullResult
0x1407436e1  mov     rcx, r9; ullMultiplicand
0x1407436e4  mov     [rbp+57h+pullResult], 0
0x1407436ec  mov     [rbp+57h+Size], 0
0x1407436f4  call    ULongLongMult
0x1407436f9  test    eax, eax
  ... truncated ...
```
