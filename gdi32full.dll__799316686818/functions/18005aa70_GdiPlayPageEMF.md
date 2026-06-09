# GdiPlayPageEMF

- ea: `0x18005aa70`
- end: `0x18005aefe`
- name: `GdiPlayPageEMF`
- size: `1166`
- prototype: `BOOL __stdcall(HANDLE SpoolFileHandle, HANDLE hemf, RECT *prectDocument, RECT *prectBorder, RECT *prectClip)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180094b70`
- `0x180094ce0`

## callees

- `0x180028f18`
- `0x18005aa70`
- `0x18005af04`
- `0x18005b074`
- `0x180094584`
- `0x1800a3514`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ac92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ad84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ac92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ad84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ad41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aeba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ad41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aeba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ac07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ac07`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005ad01`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005ad01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ad62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ae2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ad62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ae2c`
- `ntdll!RtlFreeHeap` at `0x18005aeeb`
- `ntdll!RtlFreeHeap` at `0x18005aeeb`
- `ntdll!RtlAllocateHeap` at `0x18005abf2`
- `ntdll!RtlAllocateHeap` at `0x18005abf2`
- `ntdll!RtlDecodePointer` at `0x18005aaa5`
- `ntdll!RtlDecodePointer` at `0x18005aaa5`
- `win32u!NtGdiGetTransform` at `0x18005ab9c`
- `win32u!NtGdiGetTransform` at `0x18005ab9c`

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
0x18005aa70  mov     [rsp+arg_18], r9
0x18005aa75  mov     [rsp+arg_10], r8
0x18005aa7a  push    rbx
0x18005aa7b  push    rsi
0x18005aa7c  push    rdi
0x18005aa7d  push    r12
0x18005aa7f  push    r13
0x18005aa81  push    r14
0x18005aa83  push    r15
0x18005aa85  sub     rsp, 50h
0x18005aa89  mov     r14, r9
0x18005aa8c  mov     r15, r8
0x18005aa8f  mov     r13, rdx
0x18005aa92  mov     rdi, rcx
0x18005aa95  mov     [rsp+88h+hMem], 0
0x18005aa9e  mov     rcx, cs:fpSeekPrinter; Pointer
0x18005aaa5  call    cs:__imp_RtlDecodePointer
0x18005aaab  mov     r10, rax
0x18005aaae  mov     [rsp+88h+var_40], rax
0x18005aab3  cmp     dword ptr [rdi], 53504854h
0x18005aab9  jnz     short loc_18005AAC5
0x18005aabb  cmp     dword ptr [r13+0], 45464854h
0x18005aac3  jz      short loc_18005AAD3
0x18005aac5  xor     eax, eax
0x18005aac7  jmp     loc_18005ABAE
0x18005aacc  xor     eax, eax
0x18005aace  jmp     loc_18005ABAE
0x18005aad3  mov     eax, [r13+4]
0x18005aad7  test    eax, eax
0x18005aad9  jz      loc_18005AC0D
0x18005aadf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005aae3  cmp     qword ptr [r13+8], 0
0x18005aae8  jz      loc_18005AC11
0x18005aaee  mov     eax, [rdi+50h]
0x18005aaf1  cmp     [rdi+3Ch], eax
0x18005aaf4  jnb     loc_18005ABDC
0x18005aafa  mov     eax, [rdi+3Ch]
0x18005aafd  imul    rcx, rax, 58h ; 'X'
0x18005ab01  mov     rdx, [rdi+48h]
0x18005ab05  mov     rax, [r13+8]
0x18005ab09  mov     [rcx+rdx], rax
0x18005ab0d  mov     eax, [r13+10h]
0x18005ab11  mov     [rcx+rdx+54h], eax
0x18005ab15  mov     eax, [r13+4]
0x18005ab19  mov     [rcx+rdx+8], eax
0x18005ab1d  mov     eax, [r15+4]
0x18005ab21  mov     [rcx+rdx+38h], eax
0x18005ab25  mov     eax, [r15+0Ch]
0x18005ab29  mov     [rcx+rdx+40h], eax
0x18005ab2d  mov     eax, [r15]
0x18005ab30  mov     [rcx+rdx+34h], eax
0x18005ab34  mov     eax, [r15+8]
0x18005ab38  mov     [rcx+rdx+3Ch], eax
0x18005ab3c  test    r14, r14
0x18005ab3f  jz      short loc_18005ABBE
0x18005ab41  mov     eax, [r14+4]
0x18005ab45  mov     [rcx+rdx+48h], eax
0x18005ab49  mov     eax, [r14+0Ch]
0x18005ab4d  mov     [rcx+rdx+50h], eax
0x18005ab51  mov     eax, [r14]
0x18005ab54  mov     [rcx+rdx+44h], eax
0x18005ab58  mov     eax, [r14+8]
0x18005ab5c  mov     [rcx+rdx+4Ch], eax
0x18005ab60  mov     r8, [rsp+88h+prectClip]
0x18005ab68  test    r8, r8
0x18005ab6b  jz      short loc_18005ABCE
0x18005ab6d  mov     eax, [r8+4]
0x18005ab71  mov     [rcx+rdx+28h], eax
0x18005ab75  mov     eax, [r8+0Ch]
0x18005ab79  mov     [rcx+rdx+30h], eax
0x18005ab7d  mov     eax, [r8]
0x18005ab80  mov     [rcx+rdx+24h], eax
0x18005ab84  mov     esi, [r8+8]
0x18005ab88  mov     [rcx+rdx+2Ch], esi
0x18005ab8c  lea     r8, [rdx+0Ch]
0x18005ab90  add     r8, rcx
0x18005ab93  mov     edx, 203h
0x18005ab98  mov     rcx, [rdi+8]
0x18005ab9c  call    cs:__imp_NtGdiGetTransform
0x18005aba2  test    eax, eax
0x18005aba4  jz      short loc_18005AC0D
0x18005aba6  inc     dword ptr [rdi+3Ch]
0x18005aba9  mov     eax, 1
0x18005abae  add     rsp, 50h
0x18005abb2  pop     r15
0x18005abb4  pop     r14
0x18005abb6  pop     r13
0x18005abb8  pop     r12
0x18005abba  pop     rdi
0x18005abbb  pop     rsi
0x18005abbc  pop     rbx
0x18005abbd  retn
0x18005abbe  mov     [rcx+rdx+48h], esi
0x18005abc2  mov     [rcx+rdx+50h], esi
0x18005abc6  mov     [rcx+rdx+44h], esi
0x18005abca  mov     eax, esi
0x18005abcc  jmp     short loc_18005AB5C
0x18005abce  mov     [rcx+rdx+28h], esi
0x18005abd2  mov     [rcx+rdx+30h], esi
0x18005abd6  mov     [rcx+rdx+24h], esi
0x18005abda  jmp     short loc_18005AB88
0x18005abdc  lea     ecx, [rax+20h]
0x18005abdf  imul    r8, rcx, 58h ; 'X'; Size
0x18005abe3  mov     rcx, gs:60h
0x18005abec  xor     edx, edx; Flags
0x18005abee  mov     rcx, [rcx+30h]; HeapHandle
0x18005abf2  call    cs:__imp_RtlAllocateHeap
0x18005abf8  mov     rbx, rax
0x18005abfb  test    rax, rax
0x18005abfe  jnz     loc_18005AEC5
0x18005ac04  lea     ecx, [rax+8]; dwErrCode
0x18005ac07  call    cs:__imp_SetLastError
0x18005ac0d  xor     eax, eax
0x18005ac0f  jmp     short loc_18005ABAE
0x18005ac11  mov     r14, rsi
0x18005ac14  xor     r12d, r12d
0x18005ac17  xor     r15d, r15d
0x18005ac1a  dec     eax
0x18005ac1c  lea     rax, [rax+rax*4]
0x18005ac20  mov     rbx, [rdi+30h]
0x18005ac24  mov     ecx, [rbx+rax*8+18h]
0x18005ac28  mov     dword ptr [rsp+88h+uBytes], ecx
0x18005ac2f  mov     rbx, [rbx+rax*8]
0x18005ac33  cmp     [rdi+64h], r12d
0x18005ac37  jnz     loc_18005AE37
0x18005ac3d  test    r15, r15
0x18005ac40  jnz     loc_18005ADE9
0x18005ac46  cmp     ecx, 100000h
0x18005ac4c  jbe     loc_18005AD6E
0x18005ac52  mov     [rdi+64h], r12d
0x18005ac56  call    CreateTempSpoolFile
0x18005ac5b  mov     r14, rax
0x18005ac5e  cmp     rax, rsi
0x18005ac61  jz      loc_18005AD6E
0x18005ac67  mov     dword ptr [rsp+88h+lpOverlapped], r12d
0x18005ac6c  xor     r9d, r9d
0x18005ac6f  xor     r8d, r8d
0x18005ac72  mov     rdx, rbx
0x18005ac75  mov     rcx, [rdi+10h]
0x18005ac79  mov     rax, [rsp+88h+var_40]
0x18005ac7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac83  test    eax, eax
0x18005ac85  jz      loc_18005AD47
0x18005ac8b  mov     edx, 10000h; uBytes
0x18005ac90  xor     ecx, ecx; uFlags
0x18005ac92  call    cs:__imp_LocalAlloc
0x18005ac98  mov     rcx, rax
0x18005ac9b  mov     [rsp+88h+lpBuffer], rax
0x18005aca0  test    rax, rax
0x18005aca3  jz      loc_18005AD47
0x18005aca9  mov     eax, dword ptr [rsp+88h+uBytes]
0x18005acb0  sub     eax, r12d
0x18005acb3  mov     edx, 10000h
0x18005acb8  cmp     eax, edx
0x18005acba  cmova   eax, edx
0x18005acbd  mov     [rsp+88h+nNumberOfBytesToWrite], eax
0x18005acc1  mov     [rsp+88h+NumberOfBytesWritten], 0
0x18005accc  mov     r8d, eax; unsigned int
0x18005accf  mov     rdx, rcx; unsigned __int8 *
0x18005acd2  mov     rcx, [rdi+10h]; void *
0x18005acd6  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005acdb  test    eax, eax
0x18005acdd  jz      loc_18005AE06
0x18005ace3  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x18005acec  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005acf4  mov     r8d, [rsp+88h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18005acf9  mov     rdx, [rsp+88h+lpBuffer]; lpBuffer
0x18005acfe  mov     rcx, r14; hFile
0x18005ad01  call    cs:__imp_WriteFile
0x18005ad07  test    eax, eax
0x18005ad09  jz      loc_18005AE06
0x18005ad0f  mov     eax, [rsp+88h+NumberOfBytesWritten]
0x18005ad16  cmp     eax, [rsp+88h+nNumberOfBytesToWrite]
0x18005ad1a  jnz     loc_18005AE06
0x18005ad20  add     r12d, eax
0x18005ad23  mov     eax, dword ptr [rsp+88h+uBytes]
0x18005ad2a  cmp     r12d, eax
0x18005ad2d  jb      loc_18005AE90
0x18005ad33  cmp     r12d, eax
0x18005ad36  jz      loc_18005AE9A
0x18005ad3c  mov     rcx, [rsp+88h+lpBuffer]; hMem
0x18005ad41  call    cs:__imp_LocalFree
0x18005ad47  mov     [rsp+88h+hMem], 0
0x18005ad50  mov     r12d, 1
0x18005ad56  test    r15, r15
0x18005ad59  jnz     loc_18005ADE9
0x18005ad5f  mov     rcx, r14; hObject
0x18005ad62  call    cs:__imp_CloseHandle
0x18005ad68  test    eax, eax
0x18005ad6a  cmovnz  r14, rsi
0x18005ad6e  test    r15, r15
0x18005ad71  jnz     short loc_18005ADE9
0x18005ad73  mov     [rdi+64h], r15d
0x18005ad77  mov     r12d, dword ptr [rsp+88h+uBytes]
0x18005ad7f  mov     edx, r12d; uBytes
0x18005ad82  xor     ecx, ecx; uFlags
0x18005ad84  call    cs:__imp_LocalAlloc
0x18005ad8a  mov     [rsp+88h+hMem], rax
0x18005ad8f  test    rax, rax
0x18005ad92  jz      short loc_18005ADDE
0x18005ad94  mov     dword ptr [rsp+88h+lpOverlapped], r15d
0x18005ad99  xor     r9d, r9d
0x18005ad9c  xor     r8d, r8d
0x18005ad9f  mov     rdx, rbx
0x18005ada2  mov     rcx, [rdi+10h]
0x18005ada6  mov     rax, [rsp+88h+var_40]
0x18005adab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005adb0  test    eax, eax
0x18005adb2  jz      short loc_18005ADDE
0x18005adb4  mov     r8d, r12d; unsigned int
0x18005adb7  mov     rdx, [rsp+88h+hMem]; unsigned __int8 *
0x18005adbc  mov     rcx, [rdi+10h]; void *
0x18005adc0  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005adc5  test    eax, eax
0x18005adc7  jz      short loc_18005ADDE
0x18005adc9  xor     r9d, r9d
0x18005adcc  xor     r8d, r8d
0x18005adcf  xor     edx, edx
0x18005add1  mov     rcx, [rsp+88h+hMem]; unsigned int *
0x18005add6  call    SetEnhMetaFileBitsAlt
0x18005addb  mov     r15, rax
0x18005adde  mov     r12d, 1
0x18005ade4  test    r15, r15
0x18005ade7  jz      short loc_18005AE12
0x18005ade9  mov     [r13+8], r15
0x18005aded  mov     [r13+10h], r12d
0x18005adf1  mov     r14, [rsp+88h+arg_18]
0x18005adf9  mov     r15, [rsp+88h+arg_10]
0x18005ae01  jmp     loc_18005AAEE
0x18005ae06  mov     eax, dword ptr [rsp+88h+uBytes]
0x18005ae0d  jmp     loc_18005AD33
0x18005ae12  mov     rcx, [rsp+88h+hMem]; hMem
0x18005ae17  test    rcx, rcx
0x18005ae1a  jnz     loc_18005AEB1
0x18005ae20  cmp     r14, rsi
0x18005ae23  jz      loc_18005AC0D
0x18005ae29  mov     rcx, r14; hObject
0x18005ae2c  call    cs:__imp_CloseHandle
0x18005ae32  jmp     loc_18005AC0D
0x18005ae37  mov     dword ptr [rsp+88h+lpOverlapped], r12d
0x18005ae3c  xor     r9d, r9d
0x18005ae3f  xor     r8d, r8d
0x18005ae42  mov     rdx, rbx
0x18005ae45  mov     rcx, [rdi+10h]
0x18005ae49  mov     rax, r10
0x18005ae4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae51  test    eax, eax
0x18005ae53  jz      short loc_18005AE84
0x18005ae55  mov     r8d, dword ptr [rsp+88h+uBytes]; unsigned int
0x18005ae5d  lea     rdx, [rsp+88h+hMem]; unsigned __int8 **
0x18005ae62  mov     rcx, [rdi+10h]; void *
0x18005ae66  call    ?MemMapReadPrinter@@YAHPEAXPEAPEAEK@Z; MemMapReadPrinter(void *,uchar * *,ulong)
0x18005ae6b  test    eax, eax
0x18005ae6d  jz      short loc_18005AE84
0x18005ae6f  xor     r9d, r9d
0x18005ae72  xor     r8d, r8d
0x18005ae75  xor     edx, edx
0x18005ae77  mov     rcx, [rsp+88h+hMem]; unsigned int *
0x18005ae7c  call    SetEnhMetaFileBitsAlt
0x18005ae81  mov     r15, rax
0x18005ae84  mov     ecx, dword ptr [rsp+88h+uBytes]
0x18005ae8b  jmp     loc_18005AC3D
0x18005ae90  mov     rcx, [rsp+88h+lpBuffer]
0x18005ae95  jmp     loc_18005ACB0
0x18005ae9a  xor     r9d, r9d
0x18005ae9d  mov     r8, r14
0x18005aea0  xor     edx, edx
0x18005aea2  xor     ecx, ecx; unsigned int *
0x18005aea4  call    SetEnhMetaFileBitsAlt
0x18005aea9  mov     r15, rax
0x18005aeac  jmp     loc_18005AD3C
0x18005aeb1  test    r12d, r12d
0x18005aeb4  jz      loc_18005AE20
0x18005aeba  call    cs:__imp_LocalFree
0x18005aec0  jmp     loc_18005AE20
0x18005aec5  mov     ecx, [rdi+50h]
0x18005aec8  imul    r8, rcx, 58h ; 'X'; Size
0x18005aecc  mov     rdx, [rdi+48h]; Src
0x18005aed0  mov     rcx, rbx; void *
0x18005aed3  call    memcpy_0
0x18005aed8  mov     rcx, gs:60h
0x18005aee1  mov     r8, [rdi+48h]; P
0x18005aee5  xor     edx, edx; Flags
0x18005aee7  mov     rcx, [rcx+30h]; HeapHandle
0x18005aeeb  call    cs:__imp_RtlFreeHeap
0x18005aef1  mov     [rdi+48h], rbx
0x18005aef5  add     dword ptr [rdi+50h], 20h ; ' '
0x18005aef9  jmp     loc_18005AAFA
```
