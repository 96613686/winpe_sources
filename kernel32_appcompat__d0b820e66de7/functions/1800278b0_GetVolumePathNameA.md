# GetVolumePathNameA

- ea: `0x1800278b0`
- end: `0x180027a2c`
- name: `GetVolumePathNameA`
- size: `380`
- prototype: `BOOL __stdcall(LPCSTR lpszFileName, LPSTR lpszVolumePathName, DWORD cchBufferLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ccf0`
- `0x1800278b0`
- `0x180028f60`
- `0x180084010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180027a12`
- `ntdll!RtlFreeUnicodeString` at `0x180082b66`
- `ntdll!RtlFreeUnicodeString` at `0x180027a12`
- `ntdll!RtlFreeUnicodeString` at `0x180082b66`
- `ntdll!RtlSetLastWin32Error` at `0x180027949`
- `ntdll!RtlSetLastWin32Error` at `0x180027949`
- `ntdll!RtlInitUnicodeString` at `0x180027990`
- `ntdll!RtlInitUnicodeString` at `0x180027990`
- `ntdll!RtlFreeHeap` at `0x180027a01`
- `ntdll!RtlFreeHeap` at `0x180082b55`
- `ntdll!RtlFreeHeap` at `0x180027a01`
- `ntdll!RtlFreeHeap` at `0x180082b55`
- `ntdll!RtlAllocateHeap` at `0x180027930`
- `ntdll!RtlAllocateHeap` at `0x180027930`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180027912`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180027912`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18002799c`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18002799c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180027970`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180027970`

## pseudocode

```c
BOOL __stdcall GetVolumePathNameA(LPCSTR lpszFileName, LPSTR lpszVolumePathName, DWORD cchBufferLength)
{
  BOOL result; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  ULONG *GlobalData; // rax
  WCHAR *Heap; // rax
  BOOL VolumePathNameW; // ebx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 (__fastcall *UnicodeStringToEightBitStringRoutine)(__int128 *, struct _UNICODE_STRING *, _QWORD); // rax
  int v16; // eax
  __int64 v17; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-40h] BYREF
  __int128 v19; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-20h] BYREF

  UnicodeString = 0;
  v19 = 0;
  DestinationString = 0;
  result = Basep8BitStringToDynamicUnicodeString(&UnicodeString, lpszFileName);
  if ( !result )
    return result;
  *((_QWORD *)&v19 + 1) = lpszVolumePathName;
  LOWORD(v19) = cchBufferLength - 1;
  WORD1(v19) = cchBufferLength;
  DestinationString.Buffer = 0;
  *(_DWORD *)&DestinationString.Length = 0;
  GlobalData = (ULONG *)KernelBaseGetGlobalData(v7, v6, v8, v9);
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, (unsigned __int16)(2 * cchBufferLength));
  DestinationString.Buffer = Heap;
  if ( Heap )
  {
    DestinationString.MaximumLength = 2 * cchBufferLength;
    VolumePathNameW = GetVolumePathNameW(UnicodeString.Buffer, Heap, cchBufferLength);
    if ( !VolumePathNameW )
      goto LABEL_12;
    RtlInitUnicodeString(&DestinationString, DestinationString.Buffer);
    UnicodeStringToEightBitStringRoutine = (__int64 (__fastcall *)(__int128 *, struct _UNICODE_STRING *, _QWORD))GetUnicodeStringToEightBitStringRoutine(v14, v13);
    v16 = UnicodeStringToEightBitStringRoutine(&v19, &DestinationString, 0);
    if ( v16 >= 0 )
    {
      if ( (unsigned __int16)v19 < cchBufferLength )
      {
        *(_BYTE *)((unsigned __int16)v19 + *((_QWORD *)&v19 + 1)) = 0;
        goto LABEL_12;
      }
      v17 = 2147483653LL;
    }
    else
    {
      v17 = (unsigned int)v16;
    }
    BaseSetLastNTError(v17);
  }
  else
  {
    RtlSetLastWin32Error(8u);
  }
  VolumePathNameW = 0;
LABEL_12:
  if ( DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  RtlFreeUnicodeString(&UnicodeString);
  return VolumePathNameW;
}

```

## disassembly

```asm
0x1800278b0  mov     rax, rsp
0x1800278b3  mov     [rax+8], rbx
0x1800278b7  push    rdi
0x1800278b8  sub     rsp, 60h
0x1800278bc  mov     edi, r8d
0x1800278bf  mov     rbx, rdx
0x1800278c2  xorps   xmm0, xmm0
0x1800278c5  movups  xmmword ptr [rax-20h], xmm0
0x1800278c9  xorps   xmm1, xmm1
0x1800278cc  movups  xmmword ptr [rax-30h], xmm1
0x1800278d0  movups  xmmword ptr [rax-40h], xmm0
0x1800278d4  mov     rdx, rcx
0x1800278d7  lea     rcx, [rax-20h]
0x1800278db  call    Basep8BitStringToDynamicUnicodeString
0x1800278e0  test    eax, eax
0x1800278e2  jz      loc_180027A20
0x1800278e8  mov     [rsp+68h+var_28], rbx
0x1800278ed  lea     eax, [rdi-1]
0x1800278f0  mov     [rsp+68h+var_30], ax
0x1800278f5  mov     [rsp+68h+var_2E], di
0x1800278fa  mov     [rsp+68h+DestinationString.Buffer], 0
0x180027903  xor     eax, eax
0x180027905  mov     dword ptr [rsp+68h+DestinationString.Length], eax
0x180027909  movzx   eax, di
0x18002790c  add     ax, ax
0x18002790f  movzx   ebx, ax
0x180027912  call    cs:__imp_KernelBaseGetGlobalData
0x180027919  nop     dword ptr [rax+rax+00h]
0x18002791e  mov     r8d, ebx; Size
0x180027921  mov     rcx, gs:60h
0x18002792a  mov     edx, [rax]; Flags
0x18002792c  mov     rcx, [rcx+30h]; HeapHandle
0x180027930  call    cs:__imp_RtlAllocateHeap
0x180027937  nop     dword ptr [rax+rax+00h]
0x18002793c  mov     [rsp+68h+DestinationString.Buffer], rax
0x180027941  test    rax, rax
0x180027944  jnz     short loc_180027960
0x180027946  lea     ecx, [rax+8]; LastError
0x180027949  call    cs:__imp_RtlSetLastWin32Error
0x180027950  nop     dword ptr [rax+rax+00h]
0x180027955  xor     ebx, ebx
0x180027957  mov     [rsp+68h+var_48], ebx
0x18002795b  jmp     loc_1800279E5
0x180027960  mov     [rsp+68h+DestinationString.MaximumLength], bx
0x180027965  mov     r8d, edi; cchBufferLength
0x180027968  mov     rdx, rax; lpszVolumePathName
0x18002796b  mov     rcx, [rsp+68h+UnicodeString.Buffer]; lpszFileName
0x180027970  call    cs:__imp_GetVolumePathNameW
0x180027977  nop     dword ptr [rax+rax+00h]
0x18002797c  mov     ebx, eax
0x18002797e  mov     [rsp+68h+var_48], eax
0x180027982  test    eax, eax
0x180027984  jz      short loc_1800279E5
0x180027986  mov     rdx, [rsp+68h+DestinationString.Buffer]; SourceString
0x18002798b  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180027990  call    cs:__imp_RtlInitUnicodeString
0x180027997  nop     dword ptr [rax+rax+00h]
0x18002799c  call    cs:__imp_GetUnicodeStringToEightBitStringRoutine
0x1800279a3  nop     dword ptr [rax+rax+00h]
0x1800279a8  xor     r8d, r8d
0x1800279ab  lea     rdx, [rsp+68h+DestinationString]
0x1800279b0  lea     rcx, [rsp+68h+var_30]
0x1800279b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279ba  test    eax, eax
0x1800279bc  jns     short loc_1800279C7
0x1800279be  mov     ecx, eax
0x1800279c0  call    BaseSetLastNTError
0x1800279c5  jmp     short loc_180027955
0x1800279c7  movzx   eax, [rsp+68h+var_30]
0x1800279cc  cmp     eax, edi
0x1800279ce  jb      short loc_1800279D7
0x1800279d0  mov     ecx, 80000005h
0x1800279d5  jmp     short loc_1800279C0
0x1800279d7  movzx   ecx, [rsp+68h+var_30]
0x1800279dc  mov     rax, [rsp+68h+var_28]
0x1800279e1  mov     byte ptr [rcx+rax], 0
0x1800279e5  cmp     [rsp+68h+DestinationString.Buffer], 0
0x1800279eb  jz      short loc_180027A0D
0x1800279ed  mov     rcx, gs:60h
0x1800279f6  mov     r8, [rsp+68h+DestinationString.Buffer]; P
0x1800279fb  xor     edx, edx; Flags
0x1800279fd  mov     rcx, [rcx+30h]; HeapHandle
0x180027a01  call    cs:__imp_RtlFreeHeap
0x180027a08  nop     dword ptr [rax+rax+00h]
0x180027a0d  lea     rcx, [rsp+68h+UnicodeString]; UnicodeString
0x180027a12  call    cs:__imp_RtlFreeUnicodeString
0x180027a19  nop     dword ptr [rax+rax+00h]
0x180027a1e  mov     eax, ebx
0x180027a20  mov     rbx, [rsp+68h+arg_0]
0x180027a25  add     rsp, 60h
0x180027a29  pop     rdi
0x180027a2a  retn
0x180082b32  push    rbp
0x180082b34  sub     rsp, 20h
0x180082b38  mov     rbp, rdx
0x180082b3b  cmp     qword ptr [rbp+30h], 0
0x180082b40  jz      short loc_180082B62
0x180082b42  mov     rcx, gs:60h
0x180082b4b  mov     r8, [rbp+30h]; P
0x180082b4f  xor     edx, edx; Flags
0x180082b51  mov     rcx, [rcx+30h]; HeapHandle
0x180082b55  call    cs:__imp_RtlFreeHeap
0x180082b5c  nop     dword ptr [rax+rax+00h]
0x180082b61  nop
0x180082b62  lea     rcx, [rbp+48h]; UnicodeString
0x180082b66  call    cs:__imp_RtlFreeUnicodeString
0x180082b6d  nop     dword ptr [rax+rax+00h]
0x180082b72  nop
0x180082b73  add     rsp, 20h
0x180082b77  pop     rbp
0x180082b78  retn
```
