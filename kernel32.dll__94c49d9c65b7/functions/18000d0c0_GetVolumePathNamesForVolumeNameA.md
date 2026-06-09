# GetVolumePathNamesForVolumeNameA

- ea: `0x18000d0c0`
- end: `0x18000d251`
- name: `GetVolumePathNamesForVolumeNameA`
- size: `401`
- prototype: `BOOL __stdcall(LPCSTR lpszVolumeName, LPCH lpszVolumePathNames, DWORD cchBufferLength, PDWORD lpcchReturnLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d0c0`
- `0x18000d6c0`
- `0x18000f920`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000d235`
- `ntdll!RtlFreeUnicodeString` at `0x18007ac92`
- `ntdll!RtlFreeUnicodeString` at `0x18000d235`
- `ntdll!RtlFreeUnicodeString` at `0x18007ac92`
- `ntdll!RtlSetLastWin32Error` at `0x18000d15b`
- `ntdll!RtlSetLastWin32Error` at `0x18000d15b`
- `ntdll!RtlFreeHeap` at `0x18000d22a`
- `ntdll!RtlFreeHeap` at `0x18007ac87`
- `ntdll!RtlFreeHeap` at `0x18000d22a`
- `ntdll!RtlFreeHeap` at `0x18007ac87`
- `ntdll!RtlAllocateHeap` at `0x18000d148`
- `ntdll!RtlAllocateHeap` at `0x18000d148`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000d12d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000d12d`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18000d19c`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18000d19c`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18000d183`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18000d183`

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
0x18000d0c0  mov     rax, rsp
0x18000d0c3  mov     [rax+8], rbx
0x18000d0c7  mov     [rax+10h], rsi
0x18000d0cb  push    rdi
0x18000d0cc  sub     rsp, 60h
0x18000d0d0  mov     rsi, r9
0x18000d0d3  mov     ebx, r8d
0x18000d0d6  mov     rdi, rdx
0x18000d0d9  xorps   xmm0, xmm0
0x18000d0dc  movups  xmmword ptr [rax-20h], xmm0
0x18000d0e0  xorps   xmm1, xmm1
0x18000d0e3  movups  xmmword ptr [rax-30h], xmm1
0x18000d0e7  movups  xmmword ptr [rax-40h], xmm0
0x18000d0eb  mov     dword ptr [rax-48h], 0
0x18000d0f2  mov     rdx, rcx
0x18000d0f5  lea     rcx, [rax-20h]
0x18000d0f9  call    Basep8BitStringToDynamicUnicodeString
0x18000d0fe  test    eax, eax
0x18000d100  jz      loc_18000D24D
0x18000d106  mov     [rsp+68h+var_28], rdi
0x18000d10b  mov     [rsp+68h+var_2E], bx
0x18000d110  mov     [rsp+68h+P], 0
0x18000d119  xor     eax, eax
0x18000d11b  mov     [rsp+68h+var_3E], ax
0x18000d120  movzx   edi, bx
0x18000d123  add     di, di
0x18000d126  mov     [rsp+68h+var_3E], di
0x18000d12b  jz      short loc_18000D16C
0x18000d12d  call    cs:__imp_KernelBaseGetGlobalData
0x18000d133  movzx   r8d, [rsp+68h+var_3E]; Size
0x18000d139  mov     rcx, gs:60h
0x18000d142  mov     edx, [rax]; Flags
0x18000d144  mov     rcx, [rcx+30h]; HeapHandle
0x18000d148  call    cs:__imp_RtlAllocateHeap
0x18000d14e  mov     [rsp+68h+P], rax
0x18000d153  test    rax, rax
0x18000d156  jnz     short loc_18000D173
0x18000d158  lea     ecx, [rax+8]; LastError
0x18000d15b  call    cs:__imp_RtlSetLastWin32Error
0x18000d161  xor     ebx, ebx
0x18000d163  mov     [rsp+68h+var_44], ebx
0x18000d167  jmp     loc_18000D20E
0x18000d16c  xor     eax, eax
0x18000d16e  mov     [rsp+68h+P], rax
0x18000d173  lea     r9, [rsp+68h+cchReturnLength]; lpcchReturnLength
0x18000d178  mov     r8d, ebx; cchBufferLength
0x18000d17b  mov     rdx, rax; lpszVolumePathNames
0x18000d17e  mov     rcx, [rsp+68h+UnicodeString.Buffer]; lpszVolumeName
0x18000d183  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18000d189  mov     ebx, eax
0x18000d18b  mov     [rsp+68h+var_44], eax
0x18000d18f  test    eax, eax
0x18000d191  jz      short loc_18000D1D2
0x18000d193  test    ebx, ebx
0x18000d195  jnz     short loc_18000D1F7
0x18000d197  mov     [rsp+68h+var_40], di
0x18000d19c  call    cs:__imp_GetUnicodeStringToEightBitStringRoutine
0x18000d1a2  xor     r8d, r8d
0x18000d1a5  lea     rdx, [rsp+68h+var_40]
0x18000d1aa  lea     rcx, [rsp+68h+var_30]
0x18000d1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1b4  mov     edx, 80000000h
0x18000d1b9  lea     ecx, [rax+rdx]
0x18000d1bc  test    edx, ecx
0x18000d1be  jz      short loc_18000D1E4
0x18000d1c0  test    rsi, rsi
0x18000d1c3  jz      short loc_18000D20E
0x18000d1c5  test    ebx, ebx
0x18000d1c7  jz      short loc_18000D206
0x18000d1c9  movzx   eax, [rsp+68h+var_30]
0x18000d1ce  mov     [rsi], eax
0x18000d1d0  jmp     short loc_18000D20E
0x18000d1d2  mov     ecx, gs:68h
0x18000d1da  cmp     ecx, 0EAh
0x18000d1e0  jnz     short loc_18000D20E
0x18000d1e2  jmp     short loc_18000D193
0x18000d1e4  cmp     eax, 80000005h
0x18000d1e9  jz      short loc_18000D1C0
0x18000d1eb  mov     ecx, eax
0x18000d1ed  call    BaseSetLastNTError
0x18000d1f2  jmp     loc_18000D161
0x18000d1f7  movzx   ecx, word ptr [rsp+68h+cchReturnLength]
0x18000d1fc  add     cx, cx
0x18000d1ff  mov     [rsp+68h+var_40], cx
0x18000d204  jmp     short loc_18000D19C
0x18000d206  mov     eax, [rsp+68h+cchReturnLength]
0x18000d20a  add     eax, eax
0x18000d20c  jmp     short loc_18000D1CE
0x18000d20e  cmp     [rsp+68h+P], 0
0x18000d214  jz      short loc_18000D230
0x18000d216  mov     rcx, gs:60h
0x18000d21f  mov     r8, [rsp+68h+P]; P
0x18000d224  xor     edx, edx; Flags
0x18000d226  mov     rcx, [rcx+30h]; HeapHandle
0x18000d22a  call    cs:__imp_RtlFreeHeap
0x18000d230  lea     rcx, [rsp+68h+UnicodeString]; UnicodeString
0x18000d235  call    cs:__imp_RtlFreeUnicodeString
0x18000d23b  mov     eax, ebx
0x18000d23d  mov     rbx, [rsp+68h+arg_0]
0x18000d242  mov     rsi, [rsp+68h+arg_8]
0x18000d247  add     rsp, 60h
0x18000d24b  pop     rdi
0x18000d24c  retn
0x18000d24d  xor     eax, eax
0x18000d24f  jmp     short loc_18000D23D
0x18007ac64  push    rbp
0x18007ac66  sub     rsp, 20h
0x18007ac6a  mov     rbp, rdx
0x18007ac6d  cmp     qword ptr [rbp+30h], 0
0x18007ac72  jz      short loc_18007AC8E
0x18007ac74  mov     rcx, gs:60h
0x18007ac7d  mov     r8, [rbp+30h]; P
0x18007ac81  xor     edx, edx; Flags
0x18007ac83  mov     rcx, [rcx+30h]; HeapHandle
0x18007ac87  call    cs:__imp_RtlFreeHeap
0x18007ac8d  nop
0x18007ac8e  lea     rcx, [rbp+48h]; UnicodeString
0x18007ac92  call    cs:__imp_RtlFreeUnicodeString
0x18007ac98  nop
0x18007ac99  add     rsp, 20h
0x18007ac9d  pop     rbp
0x18007ac9e  retn
```
