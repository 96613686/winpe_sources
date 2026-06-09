# ReadKeyFromStore

- ea: `0x18000ed10`
- end: `0x18000f6a1`
- name: `ReadKeyFromStore`
- size: `2449`
- prototype: `__int64 __fastcall(__int64, int, _WORD *)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e1d4`
- `0x18000eb0c`

## callees

- `0x1800044d0`
- `0x18000464c`
- `0x1800062cc`
- `0x180007118`
- `0x180008840`
- `0x1800090c0`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x18000ed10`
- `0x180010530`
- `0x180010cc0`
- `0x180017a50`
- `0x18001e4cc`
- `0x1800204b4`
- `0x18002095c`
- `0x1800398b0`
- `0x180039bf0`
- `0x180062310`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000f13a`
- `ntdll!RtlFreeHeap` at `0x18000f13a`
- `ntdll!RtlAllocateHeap` at `0x18000edc6`
- `ntdll!RtlAllocateHeap` at `0x18000f094`
- `ntdll!RtlAllocateHeap` at `0x18000edc6`
- `ntdll!RtlAllocateHeap` at `0x18000f094`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f10e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f10e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000f236`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000f236`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000f0d1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000f0d1`

## string_xrefs

- `0x18000edfc`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000eed2`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000f4a2`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000f4bc`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall ReadKeyFromStore(__int64 a1, int a2, _WORD *a3)
{
  const wchar_t *v3; // r12
  __int64 v4; // rbx
  size_t v6; // r14
  __int64 v7; // r15
  __int64 v8; // rax
  bool v9; // zf
  struct _PEB *v10; // rcx
  size_t v11; // rsi
  __int64 v12; // r8
  _WORD *Heap; // rax
  int v14; // edx
  int v15; // r8d
  _WORD *v16; // r13
  unsigned int v17; // esi
  PVOID *v18; // rcx
  __int64 v19; // r12
  unsigned int v20; // eax
  _WORD *v21; // rdi
  char *v22; // rdi
  unsigned __int64 v23; // rcx
  int v24; // r9d
  const wchar_t *v25; // r8
  int v26; // r15d
  unsigned __int64 v27; // rdx
  __int64 v28; // r11
  unsigned __int64 v29; // rax
  BOOL v30; // edx
  unsigned int v31; // eax
  int v32; // edx
  int v33; // r8d
  PVOID *v34; // rcx
  unsigned int KeyFileNameWithoutMachineGuid; // eax
  __int64 v36; // rdx
  SIZE_T v37; // r8
  __int64 v38; // rbx
  const wchar_t *v39; // rax
  int v40; // edx
  size_t v41; // r8
  size_t v42; // rdx
  wchar_t *v43; // rcx
  size_t *v44; // r8
  DWORD FileSize; // eax
  int v46; // edx
  int v47; // r8d
  DWORD v48; // ebx
  _QWORD *v49; // rcx
  void *v51; // rax
  int v52; // edx
  int v53; // r8d
  void *v54; // r15
  __int64 v55; // rdx
  int v56; // r8d
  unsigned int v57; // eax
  int v58; // edx
  int v59; // r8d
  unsigned int v60; // esi
  int v61; // eax
  __int64 v62; // rdx
  wchar_t *cchToCopy; // [rsp+20h] [rbp-E0h]
  char v64; // [rsp+30h] [rbp-D0h]
  size_t v66; // [rsp+48h] [rbp-B8h] BYREF
  void *v67; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v69; // [rsp+60h] [rbp-A0h]
  wchar_t pszSrc[112]; // [rsp+70h] [rbp-90h] BYREF

  v3 = L"Keys\\";
  v4 = -1;
  v69 = a1;
  v6 = 10;
  v7 = *(_QWORD *)(a1 + 80);
  v66 = -1;
  NumberOfBytesRead = 0;
  LODWORD(v67) = 0;
  if ( !*(_DWORD *)(a1 + 32) )
  {
    v20 = IsThreadWellKnownSid(0, &v67);
    v17 = v20;
    if ( v20 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v15,
        (unsigned int)"Status",
        v20,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
        199);
      goto LABEL_100;
    }
    if ( (_DWORD)v67 )
    {
      v3 = L"SystemKeys\\";
      v6 = 22;
    }
  }
  v8 = -1;
  do
    v9 = a3[++v8] == 0;
  while ( !v9 );
  v10 = NtCurrentPeb();
  v11 = (unsigned int)(2 * v8);
  v12 = 4;
  if ( !v7 )
    v12 = 38;
  Heap = RtlAllocateHeap(v10->ProcessHeap, 0, v6 + v11 + v12);
  v16 = Heap;
  if ( Heap )
  {
    v67 = 0;
    memcpy_0(Heap, a3, v11);
    if ( v7 )
    {
      v21 = v16 + 1;
      *(_WORD *)((char *)v16 + v11) = asc_180069744[0];
    }
    else
    {
      v21 = v16 + 18;
      *(_OWORD *)((char *)v16 + v11) = *(_OWORD *)L"\\Microsoft\\Crypto\\";
      *(_OWORD *)((char *)v16 + v11 + 16) = *(_OWORD *)L"ft\\Crypto\\";
      *(_DWORD *)((char *)v16 + v11 + 32) = *(_DWORD *)L"o\\";
    }
    v22 = (char *)v21 + v11;
    memcpy_0(v22, v3, v6);
    v19 = v69;
    *(_WORD *)&v22[v6] = 0;
    v23 = -1;
    v24 = *(_DWORD *)(v19 + 528);
    v25 = *(const wchar_t **)(v19 + 8);
    do
      ++v23;
    while ( v25[v23] );
    if ( v23 == 69 )
      goto LABEL_24;
    if ( !v24 )
    {
      v26 = a2;
      goto LABEL_30;
    }
    if ( v23 != 102 )
    {
LABEL_24:
      v26 = a2;
      if ( v24 && !a2 )
        goto LABEL_30;
      if ( v23 == 69 || !v24 )
      {
LABEL_26:
        v27 = 0;
        v28 = 0x7E0000007E03FFLL;
        while ( v27 < v23 )
        {
          v29 = v25[v27];
          switch ( v27 )
          {
            case ' ':
              if ( (_WORD)v29 != 95 )
                goto LABEL_30;
              break;
            case ')':
            case '.':
            case '3':
            case '8':
              if ( (_WORD)v29 != 45 )
                goto LABEL_30;
              break;
            case 'E':
              if ( (_WORD)v29 != 95 && v24 && !v26 )
                goto LABEL_30;
              break;
            default:
              LOWORD(v29) = v29 - 48;
              if ( (unsigned __int16)v29 > 0x36u || !_bittest64(&v28, v29) )
                goto LABEL_30;
              break;
          }
          ++v27;
        }
        StringCchCopyW(pszSrc, 0x6Eu, v25);
        v60 = OpenFileInStorageArea(*(_DWORD *)(v19 + 32), 0x80000000, v16, pszSrc, &v66);
        if ( v60 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              (unsigned int)WPP_aa991306b93132f591cbba2128657ece_Traceguids,
              (_DWORD)v16,
              (__int64)pszSrc);
          DebugTraceError(v60, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 1124);
          v66 = -1;
        }
        else if ( v66 != -1 )
        {
          goto LABEL_44;
        }
LABEL_30:
        v30 = *(_DWORD *)(v19 + 528) && !v26 && !*(_DWORD *)(v19 + 32);
        v31 = AddMachineGuidAndAppContainerSidHashToContainerNameW(*(STRSAFE_PCNZWCH *)(v19 + 8), v30, pszSrc);
        v17 = v31;
        if ( v31 )
        {
          DebugTraceError(v31, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 1143);
LABEL_55:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
          goto LABEL_56;
        }
        v17 = OpenFileInStorageArea(*(_DWORD *)(v19 + 32), 0x80000000, v16, pszSrc, &v66);
        if ( v17 )
        {
          v34 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              (unsigned int)WPP_aa991306b93132f591cbba2128657ece_Traceguids,
              (_DWORD)v16,
              (__int64)pszSrc);
            v34 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( *(_DWORD *)(v19 + 32) )
          {
            if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 1) != 0 )
              WPP_SF_sDsd(
                (unsigned int)v34[2],
                v32,
                v33,
                (unsigned int)"Status",
                v17,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
                168);
            goto LABEL_51;
          }
          KeyFileNameWithoutMachineGuid = GetKeyFileNameWithoutMachineGuid(*(_QWORD *)(v19 + 8), pszSrc);
          v17 = KeyFileNameWithoutMachineGuid;
          if ( KeyFileNameWithoutMachineGuid )
          {
            DebugTraceError(
              KeyFileNameWithoutMachineGuid,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
              1170);
            goto LABEL_51;
          }
          cchToCopy = pszSrc;
          v17 = OpenNearestFileInStorageArea(*(unsigned int *)(v19 + 32), v36, v16, pszSrc);
          if ( v17 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                12,
                (unsigned int)WPP_aa991306b93132f591cbba2128657ece_Traceguids,
                (_DWORD)v16,
                (__int64)pszSrc);
            DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 1186);
            goto LABEL_51;
          }
        }
        do
LABEL_44:
          v9 = pszSrc[++v4] == 0;
        while ( !v9 );
        v37 = 2LL * (unsigned int)(v4 + 1);
        v38 = (unsigned int)(v4 + 1);
        v39 = (const wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
        *(_QWORD *)(v19 + 16) = v39;
        if ( !v39 )
        {
          v17 = -2146893810;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v40,
              v41,
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
              182);
          goto LABEL_51;
        }
        if ( StringValidateDestW(v39, (unsigned int)v38, v41) < 0 )
        {
          if ( v38 )
            *v43 = 0;
        }
        else
        {
          StringCopyWorkerW_0(v43, v42, v44, pszSrc, (size_t)cchToCopy);
        }
        FileSize = GetFileSize((HANDLE)v66, 0);
        v48 = FileSize;
        if ( FileSize == -1 || FileSize - 44 > 0xFFFFD4 )
        {
          v17 = -2146893798;
          v49 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_51;
          v64 = -62;
        }
        else
        {
          v51 = (void *)SafeAllocaAllocateFromHeap(FileSize);
          v67 = v51;
          v54 = v51;
          if ( !v51 )
          {
            v17 = -2146893810;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v52,
                v53,
                (unsigned int)"Status",
                14,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
                203);
            goto LABEL_51;
          }
          if ( !ReadFile((HANDLE)v66, v51, v48, &NumberOfBytesRead, 0) )
          {
            v17 = -2146893798;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v55,
                v56,
                (unsigned int)"Status",
                26,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
                214);
            KspCryptAuditKeyFileOperation(0, v55, v19, v16, *(_QWORD *)(v19 + 16), 2458, -2146893798);
            goto LABEL_51;
          }
          KspCryptAuditKeyFileOperation(1, v55, v19, v16, *(_QWORD *)(v19 + 16), 2458, 0);
          if ( NumberOfBytesRead == v48 )
          {
            v57 = KspValidateKeyFile(v54, v48);
            v17 = v57;
            if ( v57 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v58,
                  v59,
                  (unsigned int)"Status",
                  v57,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
                  0);
            }
            else
            {
              *(_QWORD *)(v19 + 224) = v54;
              *(_DWORD *)(v19 + 232) = v48;
              v67 = 0;
            }
            goto LABEL_51;
          }
          v17 = -2146893798;
          v49 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_51:
            if ( v66 != -1 )
              CloseHandle((HANDLE)v66);
            if ( v67 )
              MSCryptFree(v67);
            goto LABEL_55;
          }
          v64 = -15;
        }
        WPP_SF_sDsd(
          v49[2],
          v46,
          v47,
          (unsigned int)"Status",
          26,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
          v64);
        goto LABEL_51;
      }
    }
    else
    {
      v26 = a2;
    }
    if ( v26 )
      goto LABEL_30;
    goto LABEL_26;
  }
  v17 = -2146893810;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_9;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v14,
    v15,
    (unsigned int)"Status",
    14,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
    228);
LABEL_100:
  v18 = (PVOID *)WPP_GLOBAL_Control;
LABEL_9:
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
    WPP_SF_sDsd(
      (unsigned int)v18[2],
      v14,
      v15,
      (unsigned int)"Status",
      v17,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
      71);
  v19 = v69;
LABEL_56:
  if ( v17 == -2146893798 )
  {
    v61 = RemoveKeyFromStore(v19);
    v62 = *(_QWORD *)(v19 + 8);
    if ( v62 )
      EtwLogNCryptDeleteKey(*(_QWORD *)(v19 + 56), v62, *(_QWORD *)(v19 + 16), 0, 4, v61);
  }
  return v17;
}

```

## disassembly

```asm
0x18000ed10  mov     r11, rsp
0x18000ed13  push    rbp
0x18000ed14  push    rsi
0x18000ed15  push    r12
0x18000ed17  lea     rbp, [rsp-80h]
0x18000ed1c  sub     rsp, 180h
0x18000ed23  mov     rax, cs:__security_cookie
0x18000ed2a  xor     rax, rsp
0x18000ed2d  mov     [rbp+90h+var_40], rax
0x18000ed31  mov     [r11+10h], rbx
0x18000ed35  lea     r12, aKeys; "Keys\\"
0x18000ed3c  mov     [r11-20h], rdi
0x18000ed40  mov     rax, rcx
0x18000ed43  mov     [r11-28h], r13
0x18000ed47  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ed4e  mov     [r11-30h], r14
0x18000ed52  mov     rdi, r8
0x18000ed55  mov     [rsp+190h+var_130], rcx
0x18000ed5a  mov     r14d, 0Ah
0x18000ed60  xor     ecx, ecx
0x18000ed62  mov     [r11-38h], r15
0x18000ed66  mov     r15, [rax+50h]
0x18000ed6a  mov     [rsp+190h+var_150], edx
0x18000ed6e  mov     [rsp+190h+var_148], rbx
0x18000ed73  mov     [rsp+190h+NumberOfBytesRead], ecx
0x18000ed77  mov     dword ptr [rsp+190h+var_140], ecx
0x18000ed7b  cmp     [rax+20h], ecx
0x18000ed7e  jz      loc_18000EE1C
0x18000ed84  mov     rax, rbx
0x18000ed87  nop     word ptr [rax+rax+00000000h]
0x18000ed90  cmp     word ptr [rdi+rax*2+2], 0
0x18000ed96  lea     rax, [rax+1]
0x18000ed9a  jnz     short loc_18000ED90
0x18000ed9c  mov     rcx, gs:60h
0x18000eda5  lea     esi, [rax+rax]
0x18000eda8  mov     eax, 26h ; '&'
0x18000edad  test    r15, r15
0x18000edb0  mov     r8d, 4
0x18000edb6  cmovz   r8d, eax
0x18000edba  xor     edx, edx; Flags
0x18000edbc  mov     rcx, [rcx+30h]; HeapHandle
0x18000edc0  add     r8, rsi
0x18000edc3  add     r8, r14; Size
0x18000edc6  call    cs:__imp_RtlAllocateHeap
0x18000edcd  nop     dword ptr [rax+rax+00h]
0x18000edd2  mov     r13, rax
0x18000edd5  test    rax, rax
0x18000edd8  jnz     short loc_18000EE4C
0x18000edda  mov     esi, 8009000Eh
0x18000eddf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ede6  lea     r14, WPP_GLOBAL_Control
0x18000eded  cmp     rcx, r14
0x18000edf0  jz      short loc_18000EDFC
0x18000edf2  test    byte ptr [rcx+1Ch], 1
0x18000edf6  jnz     loc_18000F4B4
0x18000edfc  lea     rdi, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ee03  cmp     rcx, r14
0x18000ee06  jz      short loc_18000EE12
0x18000ee08  test    byte ptr [rcx+1Ch], 1
0x18000ee0c  jnz     loc_18000F4EC
0x18000ee12  mov     r12, [rsp+190h+var_130]
0x18000ee17  jmp     loc_18000F146
0x18000ee1c  lea     rdx, [rsp+190h+var_140]
0x18000ee21  call    IsThreadWellKnownSid
0x18000ee26  mov     esi, eax
0x18000ee28  test    eax, eax
0x18000ee2a  jnz     loc_18000F479
0x18000ee30  cmp     dword ptr [rsp+190h+var_140], eax
0x18000ee34  jz      loc_18000ED84
0x18000ee3a  lea     r12, aSystemkeys_0; "SystemKeys\\"
0x18000ee41  mov     r14d, 16h
0x18000ee47  jmp     loc_18000ED84
0x18000ee4c  mov     r8, rsi; Size
0x18000ee4f  mov     [rsp+190h+var_140], 0
0x18000ee58  mov     rdx, rdi; Src
0x18000ee5b  mov     rcx, r13; void *
0x18000ee5e  call    memcpy_0
0x18000ee63  test    r15, r15
0x18000ee66  jnz     loc_18000F371
0x18000ee6c  movups  xmm0, xmmword ptr cs:aMicrosoftCrypt; "\\Microsoft\\Crypto\\"
0x18000ee73  lea     rdi, [r13+24h]
0x18000ee77  movups  xmmword ptr [rsi+r13], xmm0
0x18000ee7c  movups  xmm1, xmmword ptr cs:aMicrosoftCrypt+10h; "ft\\Crypto\\"
0x18000ee83  movups  xmmword ptr [rsi+r13+10h], xmm1
0x18000ee89  mov     eax, dword ptr cs:aMicrosoftCrypt+20h; "o\\"
0x18000ee8f  mov     [rsi+r13+20h], eax
0x18000ee94  add     rdi, rsi
0x18000ee97  mov     r8, r14; Size
0x18000ee9a  mov     rcx, rdi; void *
0x18000ee9d  mov     rdx, r12; Src
0x18000eea0  call    memcpy_0
0x18000eea5  mov     r12, [rsp+190h+var_130]
0x18000eeaa  xor     eax, eax
0x18000eeac  mov     [r14+rdi], ax
0x18000eeb1  mov     rcx, rbx
0x18000eeb4  mov     r9d, [r12+210h]
0x18000eebc  mov     r8, [r12+8]; pszSrc
0x18000eec1  inc     rcx
0x18000eec4  cmp     [r8+rcx*2], ax
0x18000eec9  jnz     short loc_18000EEC1
0x18000eecb  lea     r14, WPP_GLOBAL_Control
0x18000eed2  lea     rdi, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eed9  cmp     rcx, 45h ; 'E'
0x18000eedd  jz      short loc_18000EEF8
0x18000eedf  test    r9d, r9d
0x18000eee2  jz      loc_18000F04F
0x18000eee8  cmp     rcx, 66h ; 'f'
0x18000eeec  jnz     short loc_18000EEF8
0x18000eeee  mov     r15d, [rsp+190h+var_150]
0x18000eef3  jmp     loc_18000F529
0x18000eef8  mov     r15d, [rsp+190h+var_150]
0x18000eefd  test    r9d, r9d
0x18000ef00  jnz     loc_18000F512
0x18000ef06  cmp     rcx, 45h ; 'E'
0x18000ef0a  jnz     loc_18000F520
0x18000ef10  xor     edx, edx
0x18000ef12  mov     esi, 2Dh ; '-'
0x18000ef17  mov     r11, 7E0000007E03FFh
0x18000ef21  mov     r10d, 5Fh ; '_'
0x18000ef27  cmp     rdx, rcx
0x18000ef2a  jnb     loc_18000F566
0x18000ef30  movzx   eax, word ptr [r8+rdx*2]
0x18000ef35  cmp     rdx, 20h ; ' '
0x18000ef39  jnz     loc_18000F31F
0x18000ef3f  cmp     r10w, ax
0x18000ef43  jz      loc_18000F369
0x18000ef49  cmp     dword ptr [r12+210h], 0
0x18000ef52  jnz     loc_18000F5F5
0x18000ef58  xor     edx, edx
0x18000ef5a  mov     rcx, [r12+8]; pszSrc
0x18000ef5f  lea     r8, [rsp+190h+pszSrc]
0x18000ef64  call    AddMachineGuidAndAppContainerSidHashToContainerNameW
0x18000ef69  mov     esi, eax
0x18000ef6b  test    eax, eax
0x18000ef6d  jnz     loc_18000F613
0x18000ef73  mov     ecx, [r12+20h]
0x18000ef78  lea     rax, [rsp+190h+var_148]
0x18000ef7d  lea     r9, [rsp+190h+pszSrc]
0x18000ef82  mov     [rsp+190h+cchToCopy], rax
0x18000ef87  mov     r8, r13
0x18000ef8a  mov     edx, 80000000h
0x18000ef8f  call    OpenFileInStorageArea
0x18000ef94  mov     esi, eax
0x18000ef96  test    eax, eax
0x18000ef98  jz      loc_18000F064
0x18000ef9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efa5  cmp     rcx, r14
0x18000efa8  jnz     loc_18000F408
0x18000efae  cmp     dword ptr [r12+20h], 0
0x18000efb4  jnz     loc_18000F3B5
0x18000efba  mov     rcx, [r12+8]
0x18000efbf  lea     rdx, [rsp+190h+pszSrc]
0x18000efc4  call    GetKeyFileNameWithoutMachineGuid
0x18000efc9  mov     esi, eax
0x18000efcb  test    eax, eax
0x18000efcd  jnz     loc_18000F62F
0x18000efd3  mov     ecx, [r12+20h]
0x18000efd8  lea     rax, [rsp+190h+var_148]
0x18000efdd  mov     qword ptr [rsp+190h+var_160], rax
0x18000efe2  lea     r9, [rsp+190h+pszSrc]
0x18000efe7  lea     rax, [rsp+190h+pszSrc]
0x18000efec  mov     r8, r13
0x18000efef  mov     [rsp+190h+cchToCopy], rax
0x18000eff4  call    OpenNearestFileInStorageArea
0x18000eff9  mov     esi, eax
0x18000effb  test    eax, eax
0x18000effd  jz      short loc_18000F064
0x18000efff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f006  cmp     rcx, r14
0x18000f009  jz      short loc_18000F033
0x18000f00b  test    byte ptr [rcx+1Ch], 1
0x18000f00f  jz      short loc_18000F033
0x18000f011  mov     rcx, [rcx+10h]
0x18000f015  lea     rax, [rsp+190h+pszSrc]
0x18000f01a  mov     edx, 0Ch
0x18000f01f  mov     [rsp+190h+cchToCopy], rax
0x18000f024  mov     r9, r13
0x18000f027  lea     r8, WPP_aa991306b93132f591cbba2128657ece_Traceguids
0x18000f02e  call    WPP_SF_SS
0x18000f033  mov     r9d, 4A2h
0x18000f039  lea     rdx, aStatus; "Status"
0x18000f040  mov     r8, rdi
0x18000f043  mov     ecx, esi
0x18000f045  call    DebugTraceError
0x18000f04a  jmp     loc_18000F103
0x18000f04f  mov     r15d, [rsp+190h+var_150]
0x18000f054  jmp     loc_18000EF49
0x18000f059  cmp     [rsp+190h+var_148], rbx
0x18000f05e  jz      loc_18000EF49
0x18000f064  lea     rax, [rsp+190h+pszSrc]
0x18000f069  nop     dword ptr [rax+00000000h]
0x18000f070  cmp     word ptr [rax+rbx*2+2], 0
0x18000f076  lea     rbx, [rbx+1]
0x18000f07a  jnz     short loc_18000F070
0x18000f07c  mov     rcx, gs:60h
0x18000f085  lea     eax, [rbx+1]
0x18000f088  lea     r8, [rax+rax]; Size
0x18000f08c  mov     ebx, eax
0x18000f08e  xor     edx, edx; Flags
0x18000f090  mov     rcx, [rcx+30h]; HeapHandle
0x18000f094  call    cs:__imp_RtlAllocateHeap
0x18000f09b  nop     dword ptr [rax+rax+00h]
0x18000f0a0  mov     [r12+10h], rax
0x18000f0a5  mov     rcx, rax; pszDest
0x18000f0a8  test    rax, rax
0x18000f0ab  jz      loc_18000F1BF
0x18000f0b1  mov     edx, ebx; cchDest
0x18000f0b3  call    StringValidateDestW
0x18000f0b8  test    eax, eax
0x18000f0ba  js      loc_18000F64B
0x18000f0c0  lea     r9, [rsp+190h+pszSrc]; pszSrc
0x18000f0c5  call    StringCopyWorkerW_0
0x18000f0ca  mov     rcx, [rsp+190h+var_148]; hFile
0x18000f0cf  xor     edx, edx; lpFileSizeHigh
0x18000f0d1  call    cs:__imp_GetFileSize
0x18000f0d8  nop     dword ptr [rax+rax+00h]
0x18000f0dd  mov     ebx, eax
0x18000f0df  cmp     eax, 0FFFFFFFFh
0x18000f0e2  jnz     loc_18000F1F5
0x18000f0e8  mov     esi, 8009001Ah
0x18000f0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0f4  cmp     rcx, r14
0x18000f0f7  jz      short loc_18000F103
0x18000f0f9  test    byte ptr [rcx+1Ch], 1
0x18000f0fd  jnz     loc_18000F195
0x18000f103  mov     rcx, [rsp+190h+var_148]; hObject
0x18000f108  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f10c  jz      short loc_18000F11A
0x18000f10e  call    cs:__imp_CloseHandle
0x18000f115  nop     dword ptr [rax+rax+00h]
0x18000f11a  mov     rcx, [rsp+190h+var_140]
0x18000f11f  test    rcx, rcx
0x18000f122  jnz     loc_18000F65E
0x18000f128  mov     rcx, gs:60h
0x18000f131  mov     r8, r13; P
0x18000f134  xor     edx, edx; Flags
0x18000f136  mov     rcx, [rcx+30h]; HeapHandle
0x18000f13a  call    cs:__imp_RtlFreeHeap
0x18000f141  nop     dword ptr [rax+rax+00h]
0x18000f146  mov     r15, [rsp+190h+var_30]
0x18000f14e  mov     r14, [rsp+190h+var_28]
0x18000f156  mov     r13, [rsp+190h+var_20]
0x18000f15e  mov     rdi, [rsp+190h+var_18]
0x18000f166  mov     rbx, [rsp+190h+arg_8]
0x18000f16e  cmp     esi, 8009001Ah
0x18000f174  jz      loc_18000F668
0x18000f17a  mov     eax, esi
0x18000f17c  mov     rcx, [rbp+90h+var_40]
0x18000f180  xor     rcx, rsp; StackCookie
0x18000f183  call    __security_check_cookie
0x18000f188  add     rsp, 180h
0x18000f18f  pop     r12
0x18000f191  pop     rsi
0x18000f192  pop     rbp
0x18000f193  retn
0x18000f195  mov     dword ptr [rsp+190h+var_160], 4C2h
0x18000f19d  mov     [rsp+190h+var_168], rdi
0x18000f1a2  mov     dword ptr [rsp+190h+cchToCopy], 8009001Ah
0x18000f1aa  mov     rcx, [rcx+10h]
0x18000f1ae  lea     r9, aStatus; "Status"
0x18000f1b5  call    WPP_SF_sDsd
0x18000f1ba  jmp     loc_18000F103
0x18000f1bf  mov     esi, 8009000Eh
0x18000f1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1cb  cmp     rcx, r14
0x18000f1ce  jz      loc_18000F103
0x18000f1d4  test    byte ptr [rcx+1Ch], 1
0x18000f1d8  jz      loc_18000F103
0x18000f1de  mov     dword ptr [rsp+190h+var_160], 4B6h
0x18000f1e6  mov     [rsp+190h+var_168], rdi
0x18000f1eb  mov     dword ptr [rsp+190h+cchToCopy], 8009000Eh
0x18000f1f3  jmp     short loc_18000F1AA
0x18000f1f5  lea     ecx, [rbx-2Ch]
0x18000f1f8  cmp     ecx, 0FFFFD4h
0x18000f1fe  ja      loc_18000F0E8
0x18000f204  mov     rcx, rbx
0x18000f207  call    SafeAllocaAllocateFromHeap
0x18000f20c  mov     [rsp+190h+var_140], rax
0x18000f211  mov     r15, rax
0x18000f214  test    rax, rax
0x18000f217  jz      loc_18000F440
0x18000f21d  mov     rcx, [rsp+190h+var_148]; hFile
0x18000f222  lea     r9, [rsp+190h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000f227  mov     r8d, ebx; nNumberOfBytesToRead
0x18000f22a  mov     [rsp+190h+cchToCopy], 0; lpOverlapped
0x18000f233  mov     rdx, rax; lpBuffer
0x18000f236  call    cs:__imp_ReadFile
0x18000f23d  nop     dword ptr [rax+rax+00h]
0x18000f242  test    eax, eax
0x18000f244  jz      loc_18000F2D8
0x18000f24a  mov     rax, [r12+10h]
0x18000f24f  mov     r9, r13
0x18000f252  mov     dword ptr [rsp+190h+var_160], 0
0x18000f25a  mov     r8, r12
0x18000f25d  mov     dword ptr [rsp+190h+var_168], 99Ah
0x18000f265  mov     ecx, 1
0x18000f26a  mov     [rsp+190h+cchToCopy], rax
0x18000f26f  call    KspCryptAuditKeyFileOperation
0x18000f274  cmp     [rsp+190h+NumberOfBytesRead], ebx
0x18000f278  jnz     short loc_18000F2AC
  ... truncated ...
```
