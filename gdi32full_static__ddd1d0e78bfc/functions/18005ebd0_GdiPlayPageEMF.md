# GdiPlayPageEMF

- ea: `0x18005ebd0`
- end: `0x18005f0ab`
- name: `GdiPlayPageEMF`
- size: `1243`
- prototype: `BOOL __stdcall(HANDLE SpoolFileHandle, HANDLE hemf, RECT *prectDocument, RECT *prectBorder, RECT *prectClip)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18009a9e0`
- `0x18009ab60`

## callees

- `0x18003261c`
- `0x18005ebd0`
- `0x18005f0b4`
- `0x18005f23c`
- `0x18009a394`
- `0x1800a68d4`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ee0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ef19`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ee0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ef19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eeca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f05b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eeca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f05b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ed7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ed7e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005ee84`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005ee84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005eef1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005efc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005eef1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005efc7`
- `ntdll!RtlFreeHeap` at `0x18005f092`
- `ntdll!RtlFreeHeap` at `0x18005f092`
- `ntdll!RtlAllocateHeap` at `0x18005ed63`
- `ntdll!RtlAllocateHeap` at `0x18005ed63`
- `ntdll!RtlDecodePointer` at `0x18005ec05`
- `ntdll!RtlDecodePointer` at `0x18005ec05`
- `win32u!NtGdiGetTransform` at `0x18005ed06`
- `win32u!NtGdiGetTransform` at `0x18005ed06`

## pseudocode

```c
BOOL __stdcall GdiPlayPageEMF(
        HANDLE SpoolFileHandle,
        HANDLE hemf,
        RECT *prectDocument,
        RECT *prectBorder,
        RECT *prectClip)
{
  RECT *v5; // r14
  RECT *v6; // r15
  PVOID v9; // r10
  int v11; // eax
  int v12; // esi
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  int right; // eax
  RECT *v17; // r8
  PVOID Heap; // rax
  PVOID v19; // rbx
  __int64 TempSpoolFile; // r14
  unsigned int v21; // r12d
  __int64 v22; // r15
  __int64 v23; // rax
  __int64 v24; // rbx
  unsigned int v25; // ecx
  __int64 v26; // rbx
  void *v27; // rcx
  unsigned int v28; // eax
  unsigned int v29; // eax
  DWORD nNumberOfBytesToWrite; // [rsp+30h] [rbp-58h]
  HLOCAL hMem; // [rsp+38h] [rbp-50h] BYREF
  LPCVOID lpBuffer; // [rsp+40h] [rbp-48h]
  unsigned int (__fastcall *v33)(_QWORD, __int64, _QWORD, _QWORD, _DWORD); // [rsp+48h] [rbp-40h]
  unsigned int uBytes; // [rsp+90h] [rbp+8h]
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp+10h] BYREF
  RECT *v36; // [rsp+A0h] [rbp+18h]
  RECT *v37; // [rsp+A8h] [rbp+20h]

  v37 = prectBorder;
  v36 = prectDocument;
  v5 = prectBorder;
  v6 = prectDocument;
  hMem = 0;
  v9 = RtlDecodePointer(fpSeekPrinter);
  v33 = (unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, _DWORD))v9;
  if ( *(_DWORD *)SpoolFileHandle != 1397770324 || *(_DWORD *)hemf != 1162233940 )
    return 0;
  v11 = *((_DWORD *)hemf + 1);
  if ( !v11 )
    return 0;
  v12 = -1;
  if ( !*((_QWORD *)hemf + 1) )
  {
    TempSpoolFile = -1;
    v21 = 0;
    v22 = 0;
    v23 = 5LL * (unsigned int)(v11 - 1);
    v24 = *((_QWORD *)SpoolFileHandle + 6);
    v25 = *(_DWORD *)(v24 + 8 * v23 + 24);
    uBytes = v25;
    v26 = *(_QWORD *)(v24 + 8 * v23);
    if ( *((_DWORD *)SpoolFileHandle + 25) )
    {
      if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, _DWORD))v9)(
             *((_QWORD *)SpoolFileHandle + 2),
             v26,
             0,
             0,
             0)
        && (unsigned int)MemMapReadPrinter(*((void **)SpoolFileHandle + 2), (unsigned __int8 **)&hMem, uBytes) )
      {
        v22 = SetEnhMetaFileBitsAlt((unsigned int *)hMem);
      }
      v25 = uBytes;
    }
    if ( !v22 )
    {
      if ( v25 <= 0x100000 )
        goto LABEL_37;
      *((_DWORD *)SpoolFileHandle + 25) = 0;
      TempSpoolFile = CreateTempSpoolFile();
      if ( TempSpoolFile == -1 )
        goto LABEL_37;
      if ( v33(*((_QWORD *)SpoolFileHandle + 2), v26, 0, 0, 0) )
      {
        v27 = LocalAlloc(0, 0x10000u);
        lpBuffer = v27;
        if ( v27 )
        {
          v28 = uBytes;
          while ( 1 )
          {
            v29 = v28 - v21;
            if ( v29 > 0x10000 )
              v29 = 0x10000;
            nNumberOfBytesToWrite = v29;
            NumberOfBytesWritten = 0;
            if ( !(unsigned int)MyReadPrinter(*((void **)SpoolFileHandle + 2), (unsigned __int8 *)v27, v29)
              || !WriteFile((HANDLE)TempSpoolFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
              || NumberOfBytesWritten != nNumberOfBytesToWrite )
            {
              break;
            }
            v21 += NumberOfBytesWritten;
            v28 = uBytes;
            if ( v21 >= uBytes )
              goto LABEL_31;
            v27 = (void *)lpBuffer;
          }
          v28 = uBytes;
LABEL_31:
          if ( v21 == v28 )
            v22 = SetEnhMetaFileBitsAlt(0);
          LocalFree((HLOCAL)lpBuffer);
        }
      }
      hMem = 0;
      v21 = 1;
      if ( !v22 )
      {
        if ( CloseHandle((HANDLE)TempSpoolFile) )
          TempSpoolFile = -1;
LABEL_37:
        *((_DWORD *)SpoolFileHandle + 25) = 0;
        hMem = LocalAlloc(0, uBytes);
        if ( hMem
          && v33(*((_QWORD *)SpoolFileHandle + 2), v26, 0, 0, 0)
          && (unsigned int)MyReadPrinter(*((void **)SpoolFileHandle + 2), (unsigned __int8 *)hMem, uBytes) )
        {
          v22 = SetEnhMetaFileBitsAlt((unsigned int *)hMem);
        }
        v21 = 1;
        if ( !v22 )
        {
          if ( hMem )
            LocalFree(hMem);
          if ( TempSpoolFile != -1 )
            CloseHandle((HANDLE)TempSpoolFile);
          return 0;
        }
      }
    }
    *((_QWORD *)hemf + 1) = v22;
    *((_DWORD *)hemf + 4) = v21;
    v5 = v37;
    v6 = v36;
  }
  v13 = *((_DWORD *)SpoolFileHandle + 20);
  if ( *((_DWORD *)SpoolFileHandle + 15) >= v13 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 88LL * (v13 + 32));
    v19 = Heap;
    if ( !Heap )
    {
      SetLastError(8u);
      return 0;
    }
    memcpy_0(Heap, *((const void **)SpoolFileHandle + 9), 88LL * *((unsigned int *)SpoolFileHandle + 20));
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)SpoolFileHandle + 9));
    *((_QWORD *)SpoolFileHandle + 9) = v19;
    *((_DWORD *)SpoolFileHandle + 20) += 32;
  }
  v14 = 88LL * *((unsigned int *)SpoolFileHandle + 15);
  v15 = *((_QWORD *)SpoolFileHandle + 9);
  *(_QWORD *)(v14 + v15) = *((_QWORD *)hemf + 1);
  *(_DWORD *)(v14 + v15 + 84) = *((_DWORD *)hemf + 4);
  *(_DWORD *)(v14 + v15 + 8) = *((_DWORD *)hemf + 1);
  *(_DWORD *)(v14 + v15 + 56) = v6->top;
  *(_DWORD *)(v14 + v15 + 64) = v6->bottom;
  *(_DWORD *)(v14 + v15 + 52) = v6->left;
  *(_DWORD *)(v14 + v15 + 60) = v6->right;
  if ( v5 )
  {
    *(_DWORD *)(v14 + v15 + 72) = v5->top;
    *(_DWORD *)(v14 + v15 + 80) = v5->bottom;
    *(_DWORD *)(v14 + v15 + 68) = v5->left;
    right = v5->right;
  }
  else
  {
    *(_DWORD *)(v14 + v15 + 72) = -1;
    *(_DWORD *)(v14 + v15 + 80) = -1;
    *(_DWORD *)(v14 + v15 + 68) = -1;
    right = -1;
  }
  *(_DWORD *)(v14 + v15 + 76) = right;
  v17 = prectClip;
  if ( prectClip )
  {
    *(_DWORD *)(v14 + v15 + 40) = prectClip->top;
    *(_DWORD *)(v14 + v15 + 48) = v17->bottom;
    *(_DWORD *)(v14 + v15 + 36) = v17->left;
    v12 = v17->right;
  }
  else
  {
    *(_DWORD *)(v14 + v15 + 40) = -1;
    *(_DWORD *)(v14 + v15 + 48) = -1;
    *(_DWORD *)(v14 + v15 + 36) = -1;
  }
  *(_DWORD *)(v14 + v15 + 44) = v12;
  if ( (unsigned int)NtGdiGetTransform(*((_QWORD *)SpoolFileHandle + 1), 515, v14 + v15 + 12) )
  {
    ++*((_DWORD *)SpoolFileHandle + 15);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18005ebd0  mov     [rsp+arg_18], r9
0x18005ebd5  mov     [rsp+arg_10], r8
0x18005ebda  push    rbx
0x18005ebdb  push    rsi
0x18005ebdc  push    rdi
0x18005ebdd  push    r12
0x18005ebdf  push    r13
0x18005ebe1  push    r14
0x18005ebe3  push    r15
0x18005ebe5  sub     rsp, 50h
0x18005ebe9  mov     r14, r9
0x18005ebec  mov     r15, r8
0x18005ebef  mov     r13, rdx
0x18005ebf2  mov     rdi, rcx
0x18005ebf5  mov     [rsp+88h+hMem], 0
0x18005ebfe  mov     rcx, cs:fpSeekPrinter; Pointer
0x18005ec05  call    cs:__imp_RtlDecodePointer
0x18005ec0c  nop     dword ptr [rax+rax+00h]
0x18005ec11  mov     r10, rax
0x18005ec14  mov     [rsp+88h+var_40], rax
0x18005ec19  cmp     dword ptr [rdi], 53504854h
0x18005ec1f  jnz     short loc_18005EC2B
0x18005ec21  cmp     dword ptr [r13+0], 45464854h
0x18005ec29  jz      short loc_18005EC39
0x18005ec2b  xor     eax, eax
0x18005ec2d  jmp     loc_18005ED1E
0x18005ec32  xor     eax, eax
0x18005ec34  jmp     loc_18005ED1E
0x18005ec39  mov     eax, [r13+4]
0x18005ec3d  test    eax, eax
0x18005ec3f  jz      loc_18005ED8A
0x18005ec45  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005ec49  cmp     qword ptr [r13+8], 0
0x18005ec4e  jz      loc_18005ED8E
0x18005ec54  mov     eax, [rdi+50h]
0x18005ec57  cmp     [rdi+3Ch], eax
0x18005ec5a  jnb     loc_18005ED4D
0x18005ec60  mov     eax, [rdi+3Ch]
0x18005ec63  imul    rcx, rax, 58h ; 'X'
0x18005ec67  mov     rdx, [rdi+48h]
0x18005ec6b  mov     rax, [r13+8]
0x18005ec6f  mov     [rcx+rdx], rax
0x18005ec73  mov     eax, [r13+10h]
0x18005ec77  mov     [rcx+rdx+54h], eax
0x18005ec7b  mov     eax, [r13+4]
0x18005ec7f  mov     [rcx+rdx+8], eax
0x18005ec83  mov     eax, [r15+4]
0x18005ec87  mov     [rcx+rdx+38h], eax
0x18005ec8b  mov     eax, [r15+0Ch]
0x18005ec8f  mov     [rcx+rdx+40h], eax
0x18005ec93  mov     eax, [r15]
0x18005ec96  mov     [rcx+rdx+34h], eax
0x18005ec9a  mov     eax, [r15+8]
0x18005ec9e  mov     [rcx+rdx+3Ch], eax
0x18005eca2  test    r14, r14
0x18005eca5  jz      loc_18005ED2F
0x18005ecab  mov     eax, [r14+4]
0x18005ecaf  mov     [rcx+rdx+48h], eax
0x18005ecb3  mov     eax, [r14+0Ch]
0x18005ecb7  mov     [rcx+rdx+50h], eax
0x18005ecbb  mov     eax, [r14]
0x18005ecbe  mov     [rcx+rdx+44h], eax
0x18005ecc2  mov     eax, [r14+8]
0x18005ecc6  mov     [rcx+rdx+4Ch], eax
0x18005ecca  mov     r8, [rsp+88h+prectClip]
0x18005ecd2  test    r8, r8
0x18005ecd5  jz      short loc_18005ED3F
0x18005ecd7  mov     eax, [r8+4]
0x18005ecdb  mov     [rcx+rdx+28h], eax
0x18005ecdf  mov     eax, [r8+0Ch]
0x18005ece3  mov     [rcx+rdx+30h], eax
0x18005ece7  mov     eax, [r8]
0x18005ecea  mov     [rcx+rdx+24h], eax
0x18005ecee  mov     esi, [r8+8]
0x18005ecf2  mov     [rcx+rdx+2Ch], esi
0x18005ecf6  lea     r8, [rdx+0Ch]
0x18005ecfa  add     r8, rcx
0x18005ecfd  mov     edx, 203h
0x18005ed02  mov     rcx, [rdi+8]
0x18005ed06  call    cs:__imp_NtGdiGetTransform
0x18005ed0d  nop     dword ptr [rax+rax+00h]
0x18005ed12  test    eax, eax
0x18005ed14  jz      short loc_18005ED8A
0x18005ed16  inc     dword ptr [rdi+3Ch]
0x18005ed19  mov     eax, 1
0x18005ed1e  add     rsp, 50h
0x18005ed22  pop     r15
0x18005ed24  pop     r14
0x18005ed26  pop     r13
0x18005ed28  pop     r12
0x18005ed2a  pop     rdi
0x18005ed2b  pop     rsi
0x18005ed2c  pop     rbx
0x18005ed2d  retn
0x18005ed2f  mov     [rcx+rdx+48h], esi
0x18005ed33  mov     [rcx+rdx+50h], esi
0x18005ed37  mov     [rcx+rdx+44h], esi
0x18005ed3b  mov     eax, esi
0x18005ed3d  jmp     short loc_18005ECC6
0x18005ed3f  mov     [rcx+rdx+28h], esi
0x18005ed43  mov     [rcx+rdx+30h], esi
0x18005ed47  mov     [rcx+rdx+24h], esi
0x18005ed4b  jmp     short loc_18005ECF2
0x18005ed4d  lea     ecx, [rax+20h]
0x18005ed50  imul    r8, rcx, 58h ; 'X'; Size
0x18005ed54  mov     rcx, gs:60h
0x18005ed5d  xor     edx, edx; Flags
0x18005ed5f  mov     rcx, [rcx+30h]; HeapHandle
0x18005ed63  call    cs:__imp_RtlAllocateHeap
0x18005ed6a  nop     dword ptr [rax+rax+00h]
0x18005ed6f  mov     rbx, rax
0x18005ed72  test    rax, rax
0x18005ed75  jnz     loc_18005F06C
0x18005ed7b  lea     ecx, [rax+8]; dwErrCode
0x18005ed7e  call    cs:__imp_SetLastError
0x18005ed85  nop     dword ptr [rax+rax+00h]
0x18005ed8a  xor     eax, eax
0x18005ed8c  jmp     short loc_18005ED1E
0x18005ed8e  mov     r14, rsi
0x18005ed91  xor     r12d, r12d
0x18005ed94  xor     r15d, r15d
0x18005ed97  dec     eax
0x18005ed99  lea     rax, [rax+rax*4]
0x18005ed9d  mov     rbx, [rdi+30h]
0x18005eda1  mov     ecx, [rbx+rax*8+18h]
0x18005eda5  mov     dword ptr [rsp+88h+uBytes], ecx
0x18005edac  mov     rbx, [rbx+rax*8]
0x18005edb0  cmp     [rdi+64h], r12d
0x18005edb4  jnz     loc_18005EFD8
0x18005edba  test    r15, r15
0x18005edbd  jnz     loc_18005EF84
0x18005edc3  cmp     ecx, 100000h
0x18005edc9  jbe     loc_18005EF03
0x18005edcf  mov     [rdi+64h], r12d
0x18005edd3  call    CreateTempSpoolFile
0x18005edd8  mov     r14, rax
0x18005eddb  cmp     rax, rsi
0x18005edde  jz      loc_18005EF03
0x18005ede4  mov     dword ptr [rsp+88h+lpOverlapped], r12d
0x18005ede9  xor     r9d, r9d
0x18005edec  xor     r8d, r8d
0x18005edef  mov     rdx, rbx
0x18005edf2  mov     rcx, [rdi+10h]
0x18005edf6  mov     rax, [rsp+88h+var_40]
0x18005edfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee00  test    eax, eax
0x18005ee02  jz      loc_18005EED6
0x18005ee08  mov     edx, 10000h; uBytes
0x18005ee0d  xor     ecx, ecx; uFlags
0x18005ee0f  call    cs:__imp_LocalAlloc
0x18005ee16  nop     dword ptr [rax+rax+00h]
0x18005ee1b  mov     rcx, rax
0x18005ee1e  mov     [rsp+88h+lpBuffer], rax
0x18005ee23  test    rax, rax
0x18005ee26  jz      loc_18005EED6
0x18005ee2c  mov     eax, dword ptr [rsp+88h+uBytes]
0x18005ee33  sub     eax, r12d
0x18005ee36  mov     edx, 10000h
0x18005ee3b  cmp     eax, edx
0x18005ee3d  cmova   eax, edx
0x18005ee40  mov     [rsp+88h+nNumberOfBytesToWrite], eax
0x18005ee44  mov     [rsp+88h+NumberOfBytesWritten], 0
0x18005ee4f  mov     r8d, eax; unsigned int
0x18005ee52  mov     rdx, rcx; unsigned __int8 *
0x18005ee55  mov     rcx, [rdi+10h]; void *
0x18005ee59  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005ee5e  test    eax, eax
0x18005ee60  jz      loc_18005EFA1
0x18005ee66  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x18005ee6f  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005ee77  mov     r8d, [rsp+88h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18005ee7c  mov     rdx, [rsp+88h+lpBuffer]; lpBuffer
0x18005ee81  mov     rcx, r14; hFile
0x18005ee84  call    cs:__imp_WriteFile
0x18005ee8b  nop     dword ptr [rax+rax+00h]
0x18005ee90  test    eax, eax
0x18005ee92  jz      loc_18005EFA1
0x18005ee98  mov     eax, [rsp+88h+NumberOfBytesWritten]
0x18005ee9f  cmp     eax, [rsp+88h+nNumberOfBytesToWrite]
0x18005eea3  jnz     loc_18005EFA1
0x18005eea9  add     r12d, eax
0x18005eeac  mov     eax, dword ptr [rsp+88h+uBytes]
0x18005eeb3  cmp     r12d, eax
0x18005eeb6  jb      loc_18005F031
0x18005eebc  cmp     r12d, eax
0x18005eebf  jz      loc_18005F03B
0x18005eec5  mov     rcx, [rsp+88h+lpBuffer]; hMem
0x18005eeca  call    cs:__imp_LocalFree
0x18005eed1  nop     dword ptr [rax+rax+00h]
0x18005eed6  mov     [rsp+88h+hMem], 0
0x18005eedf  mov     r12d, 1
0x18005eee5  test    r15, r15
0x18005eee8  jnz     loc_18005EF84
0x18005eeee  mov     rcx, r14; hObject
0x18005eef1  call    cs:__imp_CloseHandle
0x18005eef8  nop     dword ptr [rax+rax+00h]
0x18005eefd  test    eax, eax
0x18005eeff  cmovnz  r14, rsi
0x18005ef03  test    r15, r15
0x18005ef06  jnz     short loc_18005EF84
0x18005ef08  mov     [rdi+64h], r15d
0x18005ef0c  mov     r12d, dword ptr [rsp+88h+uBytes]
0x18005ef14  mov     edx, r12d; uBytes
0x18005ef17  xor     ecx, ecx; uFlags
0x18005ef19  call    cs:__imp_LocalAlloc
0x18005ef20  nop     dword ptr [rax+rax+00h]
0x18005ef25  mov     [rsp+88h+hMem], rax
0x18005ef2a  test    rax, rax
0x18005ef2d  jz      short loc_18005EF79
0x18005ef2f  mov     dword ptr [rsp+88h+lpOverlapped], r15d
0x18005ef34  xor     r9d, r9d
0x18005ef37  xor     r8d, r8d
0x18005ef3a  mov     rdx, rbx
0x18005ef3d  mov     rcx, [rdi+10h]
0x18005ef41  mov     rax, [rsp+88h+var_40]
0x18005ef46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef4b  test    eax, eax
0x18005ef4d  jz      short loc_18005EF79
0x18005ef4f  mov     r8d, r12d; unsigned int
0x18005ef52  mov     rdx, [rsp+88h+hMem]; unsigned __int8 *
0x18005ef57  mov     rcx, [rdi+10h]; void *
0x18005ef5b  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005ef60  test    eax, eax
0x18005ef62  jz      short loc_18005EF79
0x18005ef64  xor     r9d, r9d
0x18005ef67  xor     r8d, r8d
0x18005ef6a  xor     edx, edx
0x18005ef6c  mov     rcx, [rsp+88h+hMem]; unsigned int *
0x18005ef71  call    SetEnhMetaFileBitsAlt
0x18005ef76  mov     r15, rax
0x18005ef79  mov     r12d, 1
0x18005ef7f  test    r15, r15
0x18005ef82  jz      short loc_18005EFAD
0x18005ef84  mov     [r13+8], r15
0x18005ef88  mov     [r13+10h], r12d
0x18005ef8c  mov     r14, [rsp+88h+arg_18]
0x18005ef94  mov     r15, [rsp+88h+arg_10]
0x18005ef9c  jmp     loc_18005EC54
0x18005efa1  mov     eax, dword ptr [rsp+88h+uBytes]
0x18005efa8  jmp     loc_18005EEBC
0x18005efad  mov     rcx, [rsp+88h+hMem]; hMem
0x18005efb2  test    rcx, rcx
0x18005efb5  jnz     loc_18005F052
0x18005efbb  cmp     r14, rsi
0x18005efbe  jz      loc_18005ED8A
0x18005efc4  mov     rcx, r14; hObject
0x18005efc7  call    cs:__imp_CloseHandle
0x18005efce  nop     dword ptr [rax+rax+00h]
0x18005efd3  jmp     loc_18005ED8A
0x18005efd8  mov     dword ptr [rsp+88h+lpOverlapped], r12d
0x18005efdd  xor     r9d, r9d
0x18005efe0  xor     r8d, r8d
0x18005efe3  mov     rdx, rbx
0x18005efe6  mov     rcx, [rdi+10h]
0x18005efea  mov     rax, r10
0x18005efed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eff2  test    eax, eax
0x18005eff4  jz      short loc_18005F025
0x18005eff6  mov     r8d, dword ptr [rsp+88h+uBytes]; unsigned int
0x18005effe  lea     rdx, [rsp+88h+hMem]; unsigned __int8 **
0x18005f003  mov     rcx, [rdi+10h]; void *
0x18005f007  call    ?MemMapReadPrinter@@YAHPEAXPEAPEAEK@Z; MemMapReadPrinter(void *,uchar * *,ulong)
0x18005f00c  test    eax, eax
0x18005f00e  jz      short loc_18005F025
0x18005f010  xor     r9d, r9d
0x18005f013  xor     r8d, r8d
0x18005f016  xor     edx, edx
0x18005f018  mov     rcx, [rsp+88h+hMem]; unsigned int *
0x18005f01d  call    SetEnhMetaFileBitsAlt
0x18005f022  mov     r15, rax
0x18005f025  mov     ecx, dword ptr [rsp+88h+uBytes]
0x18005f02c  jmp     loc_18005EDBA
0x18005f031  mov     rcx, [rsp+88h+lpBuffer]
0x18005f036  jmp     loc_18005EE33
0x18005f03b  xor     r9d, r9d
0x18005f03e  mov     r8, r14
0x18005f041  xor     edx, edx
0x18005f043  xor     ecx, ecx; unsigned int *
0x18005f045  call    SetEnhMetaFileBitsAlt
0x18005f04a  mov     r15, rax
0x18005f04d  jmp     loc_18005EEC5
0x18005f052  test    r12d, r12d
0x18005f055  jz      loc_18005EFBB
0x18005f05b  call    cs:__imp_LocalFree
0x18005f062  nop     dword ptr [rax+rax+00h]
0x18005f067  jmp     loc_18005EFBB
0x18005f06c  mov     ecx, [rdi+50h]
0x18005f06f  imul    r8, rcx, 58h ; 'X'; Size
0x18005f073  mov     rdx, [rdi+48h]; Src
0x18005f077  mov     rcx, rbx; void *
0x18005f07a  call    memcpy_0
0x18005f07f  mov     rcx, gs:60h
0x18005f088  mov     r8, [rdi+48h]; P
0x18005f08c  xor     edx, edx; Flags
0x18005f08e  mov     rcx, [rcx+30h]; HeapHandle
0x18005f092  call    cs:__imp_RtlFreeHeap
0x18005f099  nop     dword ptr [rax+rax+00h]
0x18005f09e  mov     [rdi+48h], rbx
0x18005f0a2  add     dword ptr [rdi+50h], 20h ; ' '
0x18005f0a6  jmp     loc_18005EC60
  ... truncated ...
```
