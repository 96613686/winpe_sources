# OpenFileInStorageArea

- ea: `0x180010530`
- end: `0x18001079c`
- name: `OpenFileInStorageArea`
- size: `620`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, _WORD *, _WORD *, _QWORD *)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000464c`
- `0x180005ab4`
- `0x18000ed10`
- `0x180029004`
- `0x1800362fc`
- `0x1800532a4`
- `0x18005a688`
- `0x18005d3f4`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x180010530`
- `0x1800107a4`
- `0x1800398b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800106d9`
- `ntdll!RtlFreeHeap` at `0x1800106d9`
- `ntdll!RtlAllocateHeap` at `0x1800105cb`
- `ntdll!RtlAllocateHeap` at `0x1800105cb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180010723`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180010723`

## string_xrefs

- `0x18001073a`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18001061c`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180010782`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`

## pseudocode

```c
__int64 __fastcall OpenFileInStorageArea(unsigned int a1, unsigned int a2, _WORD *a3, _WORD *a4, _QWORD *a5)
{
  __int64 v5; // r11
  int v7; // r14d
  int v8; // ebp
  unsigned int v9; // r13d
  __int64 v10; // rax
  size_t v11; // rbx
  unsigned int v12; // r15d
  char *Heap; // rax
  int v14; // edx
  int v15; // r8d
  char *v16; // rsi
  PVOID *v17; // rcx
  unsigned int v18; // ebx
  char *v19; // rdi
  __int64 v20; // rdi
  int v21; // r14d
  unsigned int File; // eax
  __int64 v24; // r9

  v5 = -1;
  *a5 = -1;
  v7 = (a2 & 0x40000000) != 0 ? 4 : 0;
  v8 = ((a2 & 0x40000000) != 0) + 3;
  v9 = 0;
  if ( (a2 & 0x40000000) == 0 )
    v9 = a2 >> 31;
  v10 = -1;
  do
    ++v10;
  while ( a3[v10] );
  v11 = (unsigned int)(2 * v10);
  do
    ++v5;
  while ( a4[v5] );
  v12 = 2 * v5;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(2 * v5 + v11) + 10LL);
  v16 = Heap;
  if ( Heap )
  {
    v19 = Heap + 8;
    *(_QWORD *)Heap = *(_QWORD *)L"\\\\?\\";
    *((_WORD *)Heap + 4) = asc_1800694F0[4];
    memcpy_0(Heap + 8, a3, v11);
    memcpy_0(&v19[v11], a4, v12 + 2LL);
    v20 = 0;
    v21 = v7 | 0x8000000;
    while ( 1 )
    {
      File = MyCreateFile(a1, v16, a2, v9, v8, v21, a5);
      v18 = File;
      if ( !File )
        break;
      if ( File != 32 )
      {
        if ( File - 2 <= 1 )
        {
          v18 = -2146893807;
          break;
        }
        if ( File == 5 )
        {
          v18 = -2146893808;
          v24 = 788;
        }
        else
        {
LABEL_25:
          v24 = 793;
        }
        DebugTraceError(v18, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", v24);
        break;
      }
      if ( (unsigned int)v20 >= 6 )
        goto LABEL_25;
      Sleep(*((_DWORD *)qword_18006EAF8 + v20));
      v20 = (unsigned int)(v20 + 1);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
  }
  else
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    v18 = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          v15,
          (unsigned int)"status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
          94);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          (unsigned int)v17[2],
          v14,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
          (unsigned int)"status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
          237);
    }
  }
  return v18;
}

```

## disassembly

```asm
0x180010530  mov     rax, rsp
0x180010533  mov     [rax+10h], rbx
0x180010537  mov     [rax+20h], r9
0x18001053b  mov     [rax+18h], r8
0x18001053f  mov     [rax+8], ecx
0x180010542  push    rbp
0x180010543  push    rsi
0x180010544  push    rdi
0x180010545  push    r12
0x180010547  push    r13
0x180010549  push    r14
0x18001054b  push    r15
0x18001054d  sub     rsp, 40h
0x180010551  mov     rax, [rsp+78h+arg_20]
0x180010559  or      r11, 0FFFFFFFFFFFFFFFFh
0x18001055d  mov     r10d, edx
0x180010560  mov     r12d, edx
0x180010563  and     r10d, 40000000h
0x18001056a  mov     [rax], r11
0x18001056d  mov     eax, r10d
0x180010570  neg     eax
0x180010572  mov     eax, r10d
0x180010575  sbb     r14d, r14d
0x180010578  and     r14d, 4
0x18001057c  neg     eax
0x18001057e  mov     eax, edx
0x180010580  sbb     ebp, ebp
0x180010582  shr     eax, 1Fh
0x180010585  neg     ebp
0x180010587  xor     edi, edi
0x180010589  add     ebp, 3
0x18001058c  mov     r13d, edi
0x18001058f  test    r10d, r10d
0x180010592  cmovz   r13d, eax
0x180010596  mov     rax, r11
0x180010599  inc     rax
0x18001059c  cmp     [r8+rax*2], di
0x1800105a1  jnz     short loc_180010599
0x1800105a3  lea     ebx, [rax+rax]
0x1800105a6  inc     r11
0x1800105a9  cmp     [r9+r11*2], di
0x1800105ae  jnz     short loc_1800105A6
0x1800105b0  mov     rcx, gs:60h
0x1800105b9  lea     r15d, [r11+r11]
0x1800105bd  lea     r8d, [r15+rbx]
0x1800105c1  xor     edx, edx; Flags
0x1800105c3  add     r8, 0Ah; Size
0x1800105c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800105cb  call    cs:__imp_RtlAllocateHeap
0x1800105d2  nop     dword ptr [rax+rax+00h]
0x1800105d7  mov     rsi, rax
0x1800105da  test    rax, rax
0x1800105dd  jnz     short loc_180010645
0x1800105df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105e6  lea     rdi, WPP_GLOBAL_Control
0x1800105ed  mov     ebx, 8009000Eh
0x1800105f2  cmp     rcx, rdi
0x1800105f5  jz      loc_1800106E5
0x1800105fb  test    byte ptr [rcx+1Ch], 1
0x1800105ff  jnz     loc_180010736
0x180010605  cmp     rcx, rdi
0x180010608  jz      loc_1800106E5
0x18001060e  test    byte ptr [rcx+1Ch], 1
0x180010612  jz      loc_1800106E5
0x180010618  mov     rcx, [rcx+10h]
0x18001061c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010623  mov     dword ptr [rsp+78h+var_48], 2EDh
0x18001062b  lea     r9, aStatus_0; "status"
0x180010632  mov     [rsp+78h+var_50], r8
0x180010637  mov     [rsp+78h+var_58], ebx
0x18001063b  call    WPP_SF_sDsd
0x180010640  jmp     loc_1800106E5
0x180010645  movsd   xmm0, qword ptr cs:asc_1800694F0; "\\\\?\\"
0x18001064d  lea     rdi, [rsi+8]
0x180010651  mov     rdx, [rsp+78h+Src]; Src
0x180010659  mov     r8, rbx; Size
0x18001065c  movsd   qword ptr [rax], xmm0
0x180010660  mov     rcx, rdi; void *
0x180010663  movzx   eax, word ptr cs:asc_1800694F0+8; ""
0x18001066a  mov     [rsi+8], ax
0x18001066e  call    memcpy_0
0x180010673  mov     rdx, [rsp+78h+arg_18]; Src
0x18001067b  lea     rcx, [rbx+rdi]; void *
0x18001067f  mov     r8d, r15d
0x180010682  add     r8, 2; Size
0x180010686  call    memcpy_0
0x18001068b  mov     r15d, [rsp+78h+arg_0]
0x180010693  xor     edi, edi
0x180010695  bts     r14d, 1Bh
0x18001069a  mov     rax, [rsp+78h+arg_20]
0x1800106a2  mov     r9d, r13d
0x1800106a5  mov     [rsp+78h+var_48], rax
0x1800106aa  mov     r8d, r12d
0x1800106ad  mov     dword ptr [rsp+78h+var_50], r14d
0x1800106b2  mov     rdx, rsi
0x1800106b5  mov     ecx, r15d
0x1800106b8  mov     [rsp+78h+var_58], ebp
0x1800106bc  call    MyCreateFile
0x1800106c1  mov     ebx, eax
0x1800106c3  test    eax, eax
0x1800106c5  jnz     short loc_180010700
0x1800106c7  mov     rcx, gs:60h
0x1800106d0  mov     r8, rsi; P
0x1800106d3  xor     edx, edx; Flags
0x1800106d5  mov     rcx, [rcx+30h]; HeapHandle
0x1800106d9  call    cs:__imp_RtlFreeHeap
0x1800106e0  nop     dword ptr [rax+rax+00h]
0x1800106e5  mov     eax, ebx
0x1800106e7  mov     rbx, [rsp+78h+arg_8]
0x1800106ef  add     rsp, 40h
0x1800106f3  pop     r15
0x1800106f5  pop     r14
0x1800106f7  pop     r13
0x1800106f9  pop     r12
0x1800106fb  pop     rdi
0x1800106fc  pop     rsi
0x1800106fd  pop     rbp
0x1800106fe  retn
0x180010700  cmp     ebx, 20h ; ' '
0x180010703  jz      short loc_180010714
0x180010705  add     eax, 0FFFFFFFEh
0x180010708  cmp     eax, 1
0x18001070b  ja      short loc_18001076A
0x18001070d  mov     ebx, 80090011h
0x180010712  jmp     short loc_1800106C7
0x180010714  cmp     edi, 6
0x180010717  jnb     short loc_18001077C
0x180010719  lea     rax, qword_18006EAF8
0x180010720  mov     ecx, [rax+rdi*4]; dwMilliseconds
0x180010723  call    cs:__imp_Sleep
0x18001072a  nop     dword ptr [rax+rax+00h]
0x18001072f  inc     edi
0x180010731  jmp     loc_18001069A
0x180010736  mov     rcx, [rcx+10h]
0x18001073a  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010741  mov     dword ptr [rsp+78h+var_48], 105Eh
0x180010749  lea     r9, aStatus_0; "status"
0x180010750  mov     [rsp+78h+var_50], rax
0x180010755  mov     [rsp+78h+var_58], ebx
0x180010759  call    WPP_SF_sDsd
0x18001075e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010765  jmp     loc_180010605
0x18001076a  cmp     ebx, 5
0x18001076d  jnz     short loc_18001077C
0x18001076f  mov     ebx, 80090010h
0x180010774  mov     r9d, 314h
0x18001077a  jmp     short loc_180010782
0x18001077c  mov     r9d, 319h
0x180010782  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010789  mov     ecx, ebx
0x18001078b  lea     rdx, aDwreturn; "dwReturn"
0x180010792  call    DebugTraceError
0x180010797  jmp     loc_1800106C7
```
