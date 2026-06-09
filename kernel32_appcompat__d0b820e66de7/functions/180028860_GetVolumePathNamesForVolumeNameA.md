# GetVolumePathNamesForVolumeNameA

- ea: `0x180028860`
- end: `0x180028a1c`
- name: `GetVolumePathNamesForVolumeNameA`
- size: `444`
- prototype: `BOOL __stdcall(LPCSTR lpszVolumeName, LPCH lpszVolumePathNames, DWORD cchBufferLength, PDWORD lpcchReturnLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ccf0`
- `0x180028860`
- `0x180028f60`
- `0x180084010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800289f9`
- `ntdll!RtlFreeUnicodeString` at `0x180082cfc`
- `ntdll!RtlFreeUnicodeString` at `0x1800289f9`
- `ntdll!RtlFreeUnicodeString` at `0x180082cfc`
- `ntdll!RtlSetLastWin32Error` at `0x180028907`
- `ntdll!RtlSetLastWin32Error` at `0x180028907`
- `ntdll!RtlFreeHeap` at `0x1800289e8`
- `ntdll!RtlFreeHeap` at `0x180082ceb`
- `ntdll!RtlFreeHeap` at `0x1800289e8`
- `ntdll!RtlFreeHeap` at `0x180082ceb`
- `ntdll!RtlAllocateHeap` at `0x1800288ee`
- `ntdll!RtlAllocateHeap` at `0x1800288ee`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800288cd`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800288cd`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180028954`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180028954`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180028935`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180028935`

## pseudocode

```c
BOOL __stdcall GetVolumePathNamesForVolumeNameA(
        LPCSTR lpszVolumeName,
        LPCH lpszVolumePathNames,
        DWORD cchBufferLength,
        PDWORD lpcchReturnLength)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int16 v11; // di
  ULONG *GlobalData; // rax
  WCHAR *Heap; // rax
  BOOL VolumePathNamesForVolumeNameW; // ebx
  __int64 (__fastcall *UnicodeStringToEightBitStringRoutine)(__int128 *, __int128 *, _QWORD); // rax
  unsigned int v16; // eax
  DWORD v17; // eax
  DWORD cchReturnLength; // [rsp+20h] [rbp-48h] BYREF
  BOOL v20; // [rsp+24h] [rbp-44h]
  __int128 v21; // [rsp+28h] [rbp-40h] BYREF
  __int128 v22; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-20h] BYREF

  UnicodeString = 0;
  v22 = 0;
  v21 = 0;
  cchReturnLength = 0;
  if ( !(unsigned int)Basep8BitStringToDynamicUnicodeString(&UnicodeString, lpszVolumeName) )
    return 0;
  *((_QWORD *)&v22 + 1) = lpszVolumePathNames;
  WORD1(v22) = cchBufferLength;
  *((_QWORD *)&v21 + 1) = 0;
  v11 = 2 * cchBufferLength;
  WORD1(v21) = 2 * cchBufferLength;
  if ( 2 * (_WORD)cchBufferLength )
  {
    GlobalData = (ULONG *)KernelBaseGetGlobalData(v8, v7, v9, v10);
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, WORD1(v21));
    *((_QWORD *)&v21 + 1) = Heap;
    if ( !Heap )
    {
      RtlSetLastWin32Error(8u);
LABEL_5:
      VolumePathNamesForVolumeNameW = 0;
      v20 = 0;
      goto LABEL_21;
    }
  }
  else
  {
    Heap = 0;
    *((_QWORD *)&v21 + 1) = 0;
  }
  VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(
                                    UnicodeString.Buffer,
                                    Heap,
                                    cchBufferLength,
                                    &cchReturnLength);
  v20 = VolumePathNamesForVolumeNameW;
  if ( VolumePathNamesForVolumeNameW || NtCurrentTeb()->LastErrorValue == 234 )
  {
    if ( VolumePathNamesForVolumeNameW )
      LOWORD(v21) = 2 * cchReturnLength;
    else
      LOWORD(v21) = v11;
    UnicodeStringToEightBitStringRoutine = (__int64 (__fastcall *)(__int128 *, __int128 *, _QWORD))GetUnicodeStringToEightBitStringRoutine();
    v16 = UnicodeStringToEightBitStringRoutine(&v22, &v21, 0);
    if ( (int)(v16 + 0x80000000) < 0 || v16 == -2147483643 )
    {
      if ( lpcchReturnLength )
      {
        if ( VolumePathNamesForVolumeNameW )
          v17 = (unsigned __int16)v22;
        else
          v17 = 2 * cchReturnLength;
        *lpcchReturnLength = v17;
      }
      goto LABEL_21;
    }
    BaseSetLastNTError(v16);
    goto LABEL_5;
  }
LABEL_21:
  if ( *((_QWORD *)&v21 + 1) )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)&v21 + 1));
  RtlFreeUnicodeString(&UnicodeString);
  return VolumePathNamesForVolumeNameW;
}

```

## disassembly

```asm
0x180028860  mov     rax, rsp
0x180028863  mov     [rax+8], rbx
0x180028867  mov     [rax+10h], rsi
0x18002886b  push    rdi
0x18002886c  sub     rsp, 60h
0x180028870  mov     rsi, r9
0x180028873  mov     ebx, r8d
0x180028876  mov     rdi, rdx
0x180028879  xorps   xmm0, xmm0
0x18002887c  movups  xmmword ptr [rax-20h], xmm0
0x180028880  xorps   xmm1, xmm1
0x180028883  movups  xmmword ptr [rax-30h], xmm1
0x180028887  movups  xmmword ptr [rax-40h], xmm0
0x18002888b  mov     dword ptr [rax-48h], 0
0x180028892  mov     rdx, rcx
0x180028895  lea     rcx, [rax-20h]
0x180028899  call    Basep8BitStringToDynamicUnicodeString
0x18002889e  test    eax, eax
0x1800288a0  jz      loc_180028A18
0x1800288a6  mov     [rsp+68h+var_28], rdi
0x1800288ab  mov     [rsp+68h+var_2E], bx
0x1800288b0  mov     [rsp+68h+P], 0
0x1800288b9  xor     eax, eax
0x1800288bb  mov     [rsp+68h+var_3E], ax
0x1800288c0  movzx   edi, bx
0x1800288c3  add     di, di
0x1800288c6  mov     [rsp+68h+var_3E], di
0x1800288cb  jz      short loc_18002891E
0x1800288cd  call    cs:__imp_KernelBaseGetGlobalData
0x1800288d4  nop     dword ptr [rax+rax+00h]
0x1800288d9  movzx   r8d, [rsp+68h+var_3E]; Size
0x1800288df  mov     rcx, gs:60h
0x1800288e8  mov     edx, [rax]; Flags
0x1800288ea  mov     rcx, [rcx+30h]; HeapHandle
0x1800288ee  call    cs:__imp_RtlAllocateHeap
0x1800288f5  nop     dword ptr [rax+rax+00h]
0x1800288fa  mov     [rsp+68h+P], rax
0x1800288ff  test    rax, rax
0x180028902  jnz     short loc_180028925
0x180028904  lea     ecx, [rax+8]; LastError
0x180028907  call    cs:__imp_RtlSetLastWin32Error
0x18002890e  nop     dword ptr [rax+rax+00h]
0x180028913  xor     ebx, ebx
0x180028915  mov     [rsp+68h+var_44], ebx
0x180028919  jmp     loc_1800289CC
0x18002891e  xor     eax, eax
0x180028920  mov     [rsp+68h+P], rax
0x180028925  lea     r9, [rsp+68h+cchReturnLength]; lpcchReturnLength
0x18002892a  mov     r8d, ebx; cchBufferLength
0x18002892d  mov     rdx, rax; lpszVolumePathNames
0x180028930  mov     rcx, [rsp+68h+UnicodeString.Buffer]; lpszVolumeName
0x180028935  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18002893c  nop     dword ptr [rax+rax+00h]
0x180028941  mov     ebx, eax
0x180028943  mov     [rsp+68h+var_44], eax
0x180028947  test    eax, eax
0x180028949  jz      short loc_180028990
0x18002894b  test    ebx, ebx
0x18002894d  jnz     short loc_1800289B5
0x18002894f  mov     [rsp+68h+var_40], di
0x180028954  call    cs:__imp_GetUnicodeStringToEightBitStringRoutine
0x18002895b  nop     dword ptr [rax+rax+00h]
0x180028960  xor     r8d, r8d
0x180028963  lea     rdx, [rsp+68h+var_40]
0x180028968  lea     rcx, [rsp+68h+var_30]
0x18002896d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028972  mov     edx, 80000000h
0x180028977  lea     ecx, [rax+rdx]
0x18002897a  test    edx, ecx
0x18002897c  jz      short loc_1800289A2
0x18002897e  test    rsi, rsi
0x180028981  jz      short loc_1800289CC
0x180028983  test    ebx, ebx
0x180028985  jz      short loc_1800289C4
0x180028987  movzx   eax, [rsp+68h+var_30]
0x18002898c  mov     [rsi], eax
0x18002898e  jmp     short loc_1800289CC
0x180028990  mov     ecx, gs:68h
0x180028998  cmp     ecx, 0EAh
0x18002899e  jnz     short loc_1800289CC
0x1800289a0  jmp     short loc_18002894B
0x1800289a2  cmp     eax, 80000005h
0x1800289a7  jz      short loc_18002897E
0x1800289a9  mov     ecx, eax
0x1800289ab  call    BaseSetLastNTError
0x1800289b0  jmp     loc_180028913
0x1800289b5  movzx   ecx, word ptr [rsp+68h+cchReturnLength]
0x1800289ba  add     cx, cx
0x1800289bd  mov     [rsp+68h+var_40], cx
0x1800289c2  jmp     short loc_180028954
0x1800289c4  mov     eax, [rsp+68h+cchReturnLength]
0x1800289c8  add     eax, eax
0x1800289ca  jmp     short loc_18002898C
0x1800289cc  cmp     [rsp+68h+P], 0
0x1800289d2  jz      short loc_1800289F4
0x1800289d4  mov     rcx, gs:60h
0x1800289dd  mov     r8, [rsp+68h+P]; P
0x1800289e2  xor     edx, edx; Flags
0x1800289e4  mov     rcx, [rcx+30h]; HeapHandle
0x1800289e8  call    cs:__imp_RtlFreeHeap
0x1800289ef  nop     dword ptr [rax+rax+00h]
0x1800289f4  lea     rcx, [rsp+68h+UnicodeString]; UnicodeString
0x1800289f9  call    cs:__imp_RtlFreeUnicodeString
0x180028a00  nop     dword ptr [rax+rax+00h]
0x180028a05  mov     eax, ebx
0x180028a07  mov     rbx, [rsp+68h+arg_0]
0x180028a0c  mov     rsi, [rsp+68h+arg_8]
0x180028a11  add     rsp, 60h
0x180028a15  pop     rdi
0x180028a16  retn
0x180028a18  xor     eax, eax
0x180028a1a  jmp     short loc_180028A07
0x180082cc8  push    rbp
0x180082cca  sub     rsp, 20h
0x180082cce  mov     rbp, rdx
0x180082cd1  cmp     qword ptr [rbp+30h], 0
0x180082cd6  jz      short loc_180082CF8
0x180082cd8  mov     rcx, gs:60h
0x180082ce1  mov     r8, [rbp+30h]; P
0x180082ce5  xor     edx, edx; Flags
0x180082ce7  mov     rcx, [rcx+30h]; HeapHandle
0x180082ceb  call    cs:__imp_RtlFreeHeap
0x180082cf2  nop     dword ptr [rax+rax+00h]
0x180082cf7  nop
0x180082cf8  lea     rcx, [rbp+48h]; UnicodeString
0x180082cfc  call    cs:__imp_RtlFreeUnicodeString
0x180082d03  nop     dword ptr [rax+rax+00h]
0x180082d08  nop
0x180082d09  add     rsp, 20h
0x180082d0d  pop     rbp
0x180082d0e  retn
```
