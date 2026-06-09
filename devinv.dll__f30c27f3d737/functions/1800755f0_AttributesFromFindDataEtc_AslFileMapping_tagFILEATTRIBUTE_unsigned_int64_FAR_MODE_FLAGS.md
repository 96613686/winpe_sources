# _AttributesFromFindDataEtc(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800755f0`
- end: `0x180075b15`
- name: `?_AttributesFromFindDataEtc@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `1317`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180005e40`
- `0x180006e94`
- `0x180006ec4`
- `0x180066c10`
- `0x1800755f0`
- `0x180077fbc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800756d3`
- `ntdll!RtlAllocateHeap` at `0x1800756d3`
- `ntdll!RtlFreeHeap` at `0x18007576c`
- `ntdll!RtlFreeHeap` at `0x18007576c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075664`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180075655`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180075655`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180075ae3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180075ae3`

## string_xrefs

- `0x1800756f7`: `_SetFileAttributeValue`
- `0x180075743`: `_SetFileAttributeValue`
- `0x180075884`: `_SetFileAttributeValue`
- `0x180075985`: `_SetFileAttributeValue`
- `0x180075a94`: `_SetFileAttributeValue`
- `0x180075731`: `Failed to copy attribute value (index %d) [%x]`
- `0x18007588b`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x18007598c`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x180075a7f`: `StringCbCopy failed to copy string attribute (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromFindDataEtc(LPCWSTR **a1, __int64 a2)
{
  unsigned int v4; // ebx
  HANDLE FirstFileW; // r12
  signed int LastError; // eax
  int v7; // edi
  __int64 v8; // r14
  wchar_t *Heap; // rax
  int v10; // eax
  void *v11; // r8
  __int64 v12; // r15
  int v13; // r10d
  __int64 v14; // rax
  unsigned __int16 *v15; // rcx
  __int64 v16; // rdx
  _WORD *v17; // r8
  _WORD *v18; // rcx
  int v19; // r10d
  __int64 v20; // rax
  unsigned __int16 *v21; // rcx
  __int64 v22; // rdx
  _WORD *v23; // r8
  _WORD *v24; // rcx
  int v25; // esi
  unsigned __int16 *v26; // rax
  _WORD *v27; // rdi
  _WORD *v28; // r10
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v31[8]; // [rsp+280h] [rbp+180h] BYREF
  __int128 v32; // [rsp+290h] [rbp+190h]
  __int64 v33; // [rsp+2A0h] [rbp+1A0h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a2 )
    return (unsigned int)-2147024809;
  FirstFileW = FindFirstFileW(**a1, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    v7 = dword_180155384;
    v8 = 260;
    if ( (unsigned int)dword_180155384 <= 2 )
    {
      *(_DWORD *)a2 = *(_DWORD *)FindFileData.cFileName;
    }
    else if ( dword_180155384 == 3 )
    {
      *(_QWORD *)a2 = *(_QWORD *)FindFileData.cFileName;
    }
    else
    {
      if ( dword_180155384 != 4 )
        goto LABEL_20;
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20Au);
      *(_QWORD *)(a2 + 536) = Heap;
      if ( !Heap )
      {
        AslLogCallPrintf(1, "_SetFileAttributeValue", 3144, "Failed to alloc memory for string value (index %d)", 0);
        goto LABEL_20;
      }
      v10 = o_wmemcpy_s_0(Heap, 0x105u, FindFileData.cFileName, 0x104u);
      if ( v10 )
      {
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        AslLogCallPrintf(1, "_SetFileAttributeValue", 3156, "Failed to copy attribute value (index %d) [%x]", 0, v10);
        v11 = *(void **)(a2 + 536);
        if ( v11 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
          *(_QWORD *)(a2 + 536) = 0;
        }
LABEL_20:
        *(_OWORD *)v31 = 0;
        v33 = 0;
        v32 = 0;
        v12 = 20;
        if ( _StringFromFileTime(&FindFileData.ftCreationTime, v31) < 0 )
          goto LABEL_35;
        v13 = dword_1801554BC;
        if ( (unsigned int)dword_1801554BC <= 2 )
        {
          *(_DWORD *)(a2 + 7072) = *(_DWORD *)v31;
        }
        else if ( dword_1801554BC == 3 )
        {
          *(_QWORD *)(a2 + 7072) = *(_QWORD *)v31;
        }
        else
        {
          if ( dword_1801554BC != 4 )
            goto LABEL_35;
          v14 = 20;
          v15 = v31;
          v16 = 260;
          v17 = (_WORD *)(a2 + 7072);
          do
          {
            if ( !v14 )
              break;
            if ( !*v15 )
              break;
            *v17++ = *v15++;
            --v14;
            --v16;
          }
          while ( v16 );
          v18 = v17 - 1;
          if ( v16 )
            v18 = v17;
          *v18 = 0;
          if ( !v16 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              13,
              -2147024774);
            goto LABEL_35;
          }
        }
        *(_DWORD *)(a2 + 7592) = 13;
        *(_DWORD *)(a2 + 7596) = v13;
        *(_DWORD *)(a2 + 7600) = 1;
LABEL_35:
        if ( _StringFromFileTime(&FindFileData.ftLastWriteTime, v31) < 0 )
          goto LABEL_50;
        v19 = dword_1801554D4;
        if ( (unsigned int)dword_1801554D4 <= 2 )
        {
          *(_DWORD *)(a2 + 7616) = *(_DWORD *)v31;
        }
        else if ( dword_1801554D4 == 3 )
        {
          *(_QWORD *)(a2 + 7616) = *(_QWORD *)v31;
        }
        else
        {
          if ( dword_1801554D4 != 4 )
            goto LABEL_50;
          v20 = 20;
          v21 = v31;
          v22 = 260;
          v23 = (_WORD *)(a2 + 7616);
          do
          {
            if ( !v20 )
              break;
            if ( !*v21 )
              break;
            *v23++ = *v21++;
            --v20;
            --v22;
          }
          while ( v22 );
          v24 = v23 - 1;
          if ( v22 )
            v24 = v23;
          *v24 = 0;
          if ( !v22 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              14,
              -2147024774);
            goto LABEL_50;
          }
        }
        *(_DWORD *)(a2 + 8136) = 14;
        *(_DWORD *)(a2 + 8140) = v19;
        *(_DWORD *)(a2 + 8144) = 1;
LABEL_50:
        if ( _StringFromFileTime(&FindFileData.ftLastAccessTime, v31) >= 0 )
        {
          v25 = dword_1801554EC;
          if ( (unsigned int)dword_1801554EC <= 2 )
          {
            *(_DWORD *)(a2 + 8160) = *(_DWORD *)v31;
            goto LABEL_64;
          }
          if ( dword_1801554EC == 3 )
          {
            *(_QWORD *)(a2 + 8160) = *(_QWORD *)v31;
            goto LABEL_64;
          }
          if ( dword_1801554EC == 4 )
          {
            v26 = v31;
            v27 = (_WORD *)(a2 + 8160);
            do
            {
              if ( !v12 )
                break;
              if ( !*v26 )
                break;
              *v27++ = *v26++;
              --v12;
              --v8;
            }
            while ( v8 );
            v28 = v27 - 1;
            if ( v8 )
              v28 = v27;
            *v28 = 0;
            if ( !v8 )
            {
              AslLogCallPrintf(
                1,
                "_SetFileAttributeValue",
                3178,
                "StringCbCopy failed to copy string attribute (index %d) [%x]",
                15,
                -2147024774);
              goto LABEL_65;
            }
LABEL_64:
            *(_DWORD *)(a2 + 8680) = 15;
            *(_DWORD *)(a2 + 8684) = v25;
            *(_DWORD *)(a2 + 8688) = 1;
          }
        }
LABEL_65:
        v4 = 0;
        FindClose(FirstFileW);
        return v4;
      }
      *(_WORD *)(*(_QWORD *)(a2 + 536) + 520LL) = 0;
      *(_WORD *)a2 = 0;
    }
    *(_DWORD *)(a2 + 520) = 0;
    *(_DWORD *)(a2 + 524) = v7;
    *(_DWORD *)(a2 + 528) = 1;
    goto LABEL_20;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v4;
}

```

## disassembly

```asm
0x1800755f0  mov     [rsp-8+arg_10], rbx
0x1800755f5  push    rbp
0x1800755f6  push    rsi
0x1800755f7  push    rdi
0x1800755f8  push    r12
0x1800755fa  push    r13
0x1800755fc  push    r14
0x1800755fe  push    r15
0x180075600  lea     rbp, [rsp-1B0h]
0x180075608  sub     rsp, 2B0h
0x18007560f  mov     rax, cs:__security_cookie
0x180075616  xor     rax, rsp
0x180075619  mov     [rbp+1E0h+var_38], rax
0x180075620  mov     rbx, rdx
0x180075623  mov     rdi, rcx
0x180075626  xor     edx, edx; Val
0x180075628  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x18007562d  mov     r8d, 250h; Size
0x180075633  call    memset_0
0x180075638  xor     r13d, r13d
0x18007563b  test    rbx, rbx
0x18007563e  jnz     short loc_18007564A
0x180075640  mov     ebx, 80070057h
0x180075645  jmp     loc_180075AE9
0x18007564a  mov     rcx, [rdi]
0x18007564d  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x180075652  mov     rcx, [rcx]; lpFileName
0x180075655  call    cs:__imp_FindFirstFileW
0x18007565b  mov     r12, rax
0x18007565e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180075662  jnz     short loc_180075682
0x180075664  call    cs:__imp_GetLastError
0x18007566a  mov     ebx, eax
0x18007566c  test    eax, eax
0x18007566e  jle     loc_180075AE9
0x180075674  movzx   ebx, ax
0x180075677  or      ebx, 80070000h
0x18007567d  jmp     loc_180075AE9
0x180075682  mov     edi, cs:dword_180155384
0x180075688  mov     esi, 1
0x18007568d  mov     ecx, edi
0x18007568f  mov     r14d, 104h
0x180075695  test    edi, edi
0x180075697  jz      loc_18007579A
0x18007569d  sub     ecx, esi
0x18007569f  jz      loc_18007579A
0x1800756a5  sub     ecx, esi
0x1800756a7  jz      loc_18007579A
0x1800756ad  sub     ecx, esi
0x1800756af  jz      loc_180075790
0x1800756b5  cmp     ecx, esi
0x1800756b7  jnz     loc_1800757B3
0x1800756bd  mov     rcx, gs:60h
0x1800756c6  lea     edx, [rsi+7]; Flags
0x1800756c9  mov     r8d, 20Ah; Size
0x1800756cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800756d3  call    cs:__imp_RtlAllocateHeap
0x1800756d9  mov     [rbx+218h], rax
0x1800756e0  test    rax, rax
0x1800756e3  jnz     short loc_18007570A
0x1800756e5  lea     r9, aFailedToAllocM; "Failed to alloc memory for string value"...
0x1800756ec  mov     [rsp+2E0h+var_2C0], r13d
0x1800756f1  mov     r8d, 0C48h
0x1800756f7  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800756fe  mov     ecx, esi
0x180075700  call    AslLogCallPrintf
0x180075705  jmp     loc_1800757B3
0x18007570a  mov     r9, r14; N
0x18007570d  lea     r8, [rsp+2E0h+FindFileData.cFileName]; S2
0x180075712  mov     edx, 105h; N1
0x180075717  mov     rcx, rax; S1
0x18007571a  call    _o_wmemcpy_s_0
0x18007571f  test    eax, eax
0x180075721  jz      short loc_18007577B
0x180075723  jle     short loc_18007572D
0x180075725  movzx   eax, ax
0x180075728  or      eax, 80070000h
0x18007572d  mov     [rsp+2E0h+var_2B8], eax
0x180075731  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x180075738  mov     r8d, 0C54h
0x18007573e  mov     [rsp+2E0h+var_2C0], r13d
0x180075743  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x18007574a  mov     ecx, esi
0x18007574c  call    AslLogCallPrintf
0x180075751  mov     r8, [rbx+218h]; P
0x180075758  test    r8, r8
0x18007575b  jz      short loc_1800757B3
0x18007575d  mov     rcx, gs:60h
0x180075766  xor     edx, edx; Flags
0x180075768  mov     rcx, [rcx+30h]; HeapHandle
0x18007576c  call    cs:__imp_RtlFreeHeap
0x180075772  mov     [rbx+218h], r13
0x180075779  jmp     short loc_1800757B3
0x18007577b  mov     rcx, [rbx+218h]
0x180075782  mov     [rcx+208h], r13w
0x18007578a  mov     [rbx], r13w
0x18007578e  jmp     short loc_1800757A0
0x180075790  mov     rax, qword ptr [rsp+2E0h+FindFileData.cFileName]
0x180075795  mov     [rbx], rax
0x180075798  jmp     short loc_1800757A0
0x18007579a  mov     eax, dword ptr [rsp+2E0h+FindFileData.cFileName]
0x18007579e  mov     [rbx], eax
0x1800757a0  mov     [rbx+208h], r13d
0x1800757a7  mov     [rbx+20Ch], edi
0x1800757ad  mov     [rbx+210h], esi
0x1800757b3  xorps   xmm0, xmm0
0x1800757b6  lea     rdx, [rbp+1E0h+var_60]; unsigned __int16 *
0x1800757bd  xor     eax, eax
0x1800757bf  lea     rcx, [rsp+2E0h+FindFileData.ftCreationTime]; struct _FILETIME *
0x1800757c4  movups  xmmword ptr [rbp+1E0h+var_60], xmm0
0x1800757cb  mov     [rbp+1E0h+var_40], rax
0x1800757d2  movups  [rbp+1E0h+var_50], xmm0
0x1800757d9  call    ?_StringFromFileTime@@YAJQEAU_FILETIME@@PEAG@Z; _StringFromFileTime(_FILETIME * const,ushort *)
0x1800757de  mov     edi, 0C6Ah
0x1800757e3  mov     r15d, 14h
0x1800757e9  test    eax, eax
0x1800757eb  js      loc_1800758D9
0x1800757f1  mov     r10d, cs:dword_1801554BC
0x1800757f8  mov     ecx, r10d
0x1800757fb  test    r10d, r10d
0x1800757fe  jz      loc_1800758B6
0x180075804  sub     ecx, esi
0x180075806  jz      loc_1800758B6
0x18007580c  sub     ecx, esi
0x18007580e  jz      loc_1800758B6
0x180075814  sub     ecx, esi
0x180075816  jz      loc_1800758A6
0x18007581c  cmp     ecx, esi
0x18007581e  jnz     loc_1800758D9
0x180075824  mov     eax, r15d
0x180075827  lea     rcx, [rbp+1E0h+var_60]
0x18007582e  mov     rdx, r14
0x180075831  lea     r8, [rbx+1BA0h]
0x180075838  test    rax, rax
0x18007583b  jz      short loc_18007585B
0x18007583d  movzx   r9d, word ptr [rcx]
0x180075841  test    r9w, r9w
0x180075845  jz      short loc_18007585B
0x180075847  mov     [r8], r9w
0x18007584b  add     rcx, 2
0x18007584f  add     r8, 2
0x180075853  sub     rax, rsi
0x180075856  sub     rdx, rsi
0x180075859  jnz     short loc_180075838
0x18007585b  mov     rax, rdx
0x18007585e  lea     rcx, [r8-2]
0x180075862  neg     rax
0x180075865  sbb     r9d, r9d
0x180075868  not     r9d
0x18007586b  and     r9d, 8007007Ah
0x180075872  test    rdx, rdx
0x180075875  cmovnz  rcx, r8
0x180075879  mov     [rcx], r13w
0x18007587d  jnz     short loc_1800758C2
0x18007587f  mov     [rsp+2E0h+var_2B8], r9d
0x180075884  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x18007588b  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x180075892  mov     [rsp+2E0h+var_2C0], 0Dh
0x18007589a  mov     r8, rdi
0x18007589d  mov     ecx, esi
0x18007589f  call    AslLogCallPrintf
0x1800758a4  jmp     short loc_1800758D9
0x1800758a6  mov     rax, qword ptr [rbp+1E0h+var_60]
0x1800758ad  mov     [rbx+1BA0h], rax
0x1800758b4  jmp     short loc_1800758C2
0x1800758b6  mov     eax, dword ptr [rbp+1E0h+var_60]
0x1800758bc  mov     [rbx+1BA0h], eax
0x1800758c2  mov     dword ptr [rbx+1DA8h], 0Dh
0x1800758cc  mov     [rbx+1DACh], r10d
0x1800758d3  mov     [rbx+1DB0h], esi
0x1800758d9  lea     rdx, [rbp+1E0h+var_60]; unsigned __int16 *
0x1800758e0  lea     rcx, [rsp+2E0h+FindFileData.ftLastWriteTime]; struct _FILETIME *
0x1800758e5  call    ?_StringFromFileTime@@YAJQEAU_FILETIME@@PEAG@Z; _StringFromFileTime(_FILETIME * const,ushort *)
0x1800758ea  test    eax, eax
0x1800758ec  js      loc_1800759DA
0x1800758f2  mov     r10d, cs:dword_1801554D4
0x1800758f9  mov     ecx, r10d
0x1800758fc  test    r10d, r10d
0x1800758ff  jz      loc_1800759B7
0x180075905  sub     ecx, esi
0x180075907  jz      loc_1800759B7
0x18007590d  sub     ecx, esi
0x18007590f  jz      loc_1800759B7
0x180075915  sub     ecx, esi
0x180075917  jz      loc_1800759A7
0x18007591d  cmp     ecx, esi
0x18007591f  jnz     loc_1800759DA
0x180075925  mov     rax, r15
0x180075928  lea     rcx, [rbp+1E0h+var_60]
0x18007592f  mov     rdx, r14
0x180075932  lea     r8, [rbx+1DC0h]
0x180075939  test    rax, rax
0x18007593c  jz      short loc_18007595C
0x18007593e  movzx   r9d, word ptr [rcx]
0x180075942  test    r9w, r9w
0x180075946  jz      short loc_18007595C
0x180075948  mov     [r8], r9w
0x18007594c  add     rcx, 2
0x180075950  add     r8, 2
0x180075954  sub     rax, rsi
0x180075957  sub     rdx, rsi
0x18007595a  jnz     short loc_180075939
0x18007595c  mov     rax, rdx
0x18007595f  lea     rcx, [r8-2]
0x180075963  neg     rax
0x180075966  sbb     r9d, r9d
0x180075969  not     r9d
0x18007596c  and     r9d, 8007007Ah
0x180075973  test    rdx, rdx
0x180075976  cmovnz  rcx, r8
0x18007597a  mov     [rcx], r13w
0x18007597e  jnz     short loc_1800759C3
0x180075980  mov     [rsp+2E0h+var_2B8], r9d
0x180075985  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x18007598c  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x180075993  mov     [rsp+2E0h+var_2C0], 0Eh
0x18007599b  mov     r8, rdi
0x18007599e  mov     ecx, esi
0x1800759a0  call    AslLogCallPrintf
0x1800759a5  jmp     short loc_1800759DA
0x1800759a7  mov     rax, qword ptr [rbp+1E0h+var_60]
0x1800759ae  mov     [rbx+1DC0h], rax
0x1800759b5  jmp     short loc_1800759C3
0x1800759b7  mov     eax, dword ptr [rbp+1E0h+var_60]
0x1800759bd  mov     [rbx+1DC0h], eax
0x1800759c3  mov     dword ptr [rbx+1FC8h], 0Eh
0x1800759cd  mov     [rbx+1FCCh], r10d
0x1800759d4  mov     [rbx+1FD0h], esi
0x1800759da  lea     rdx, [rbp+1E0h+var_60]; unsigned __int16 *
0x1800759e1  lea     rcx, [rsp+2E0h+FindFileData.ftLastAccessTime]; struct _FILETIME *
0x1800759e6  call    ?_StringFromFileTime@@YAJQEAU_FILETIME@@PEAG@Z; _StringFromFileTime(_FILETIME * const,ushort *)
0x1800759eb  test    eax, eax
0x1800759ed  js      loc_180075ADD
0x1800759f3  mov     esi, cs:dword_1801554EC
0x1800759f9  mov     ecx, esi
0x1800759fb  test    esi, esi
0x1800759fd  jz      loc_180075AB7
0x180075a03  sub     ecx, 1
0x180075a06  jz      loc_180075AB7
0x180075a0c  sub     ecx, 1
0x180075a0f  jz      loc_180075AB7
0x180075a15  sub     ecx, 1
0x180075a18  jz      loc_180075AA7
0x180075a1e  cmp     ecx, 1
0x180075a21  jnz     loc_180075ADD
0x180075a27  lea     rax, [rbp+1E0h+var_60]
0x180075a2e  lea     rdi, [rbx+1FE0h]
0x180075a35  test    r15, r15
0x180075a38  jz      short loc_180075A56
0x180075a3a  movzx   ecx, word ptr [rax]
0x180075a3d  test    cx, cx
0x180075a40  jz      short loc_180075A56
0x180075a42  mov     [rdi], cx
0x180075a45  add     rax, 2
0x180075a49  add     rdi, 2
0x180075a4d  dec     r15
0x180075a50  sub     r14, 1
0x180075a54  jnz     short loc_180075A35
0x180075a56  mov     rax, r14
0x180075a59  lea     r10, [rdi-2]
0x180075a5d  neg     rax
0x180075a60  sbb     r11d, r11d
0x180075a63  not     r11d
0x180075a66  and     r11d, 8007007Ah
0x180075a6d  test    r14, r14
0x180075a70  cmovnz  r10, rdi
0x180075a74  mov     [r10], r13w
0x180075a78  jnz     short loc_180075AC3
0x180075a7a  mov     [rsp+2E0h+var_2B8], r11d
0x180075a7f  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x180075a86  mov     r8d, 0C6Ah
0x180075a8c  mov     [rsp+2E0h+var_2C0], 0Fh
0x180075a94  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180075a9b  mov     ecx, 1
0x180075aa0  call    AslLogCallPrintf
0x180075aa5  jmp     short loc_180075ADD
0x180075aa7  mov     rax, qword ptr [rbp+1E0h+var_60]
0x180075aae  mov     [rbx+1FE0h], rax
0x180075ab5  jmp     short loc_180075AC3
0x180075ab7  mov     eax, dword ptr [rbp+1E0h+var_60]
0x180075abd  mov     [rbx+1FE0h], eax
0x180075ac3  mov     dword ptr [rbx+21E8h], 0Fh
0x180075acd  mov     [rbx+21ECh], esi
0x180075ad3  mov     dword ptr [rbx+21F0h], 1
0x180075add  mov     ebx, r13d
0x180075ae0  mov     rcx, r12; hFindFile
0x180075ae3  call    cs:__imp_FindClose
0x180075ae9  mov     eax, ebx
0x180075aeb  mov     rcx, [rbp+1E0h+var_38]
0x180075af2  xor     rcx, rsp; StackCookie
0x180075af5  call    __security_check_cookie
0x180075afa  mov     rbx, [rsp+2E0h+arg_10]
0x180075b02  add     rsp, 2B0h
0x180075b09  pop     r15
0x180075b0b  pop     r14
0x180075b0d  pop     r13
0x180075b0f  pop     r12
0x180075b11  pop     rdi
0x180075b12  pop     rsi
0x180075b13  pop     rbp
  ... truncated ...
```
