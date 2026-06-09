# GetVolumePathNameA

- ea: `0x18000bc30`
- end: `0x18000bd78`
- name: `GetVolumePathNameA`
- size: `328`
- prototype: `BOOL __stdcall(LPCSTR lpszFileName, LPSTR lpszVolumePathName, DWORD cchBufferLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000bc30`
- `0x18000d6c0`
- `0x18000f920`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000bd65`
- `ntdll!RtlFreeUnicodeString` at `0x18007aada`
- `ntdll!RtlFreeUnicodeString` at `0x18000bd65`
- `ntdll!RtlFreeUnicodeString` at `0x18007aada`
- `ntdll!RtlSetLastWin32Error` at `0x18000bcbd`
- `ntdll!RtlSetLastWin32Error` at `0x18000bcbd`
- `ntdll!RtlInitUnicodeString` at `0x18000bcf5`
- `ntdll!RtlInitUnicodeString` at `0x18000bcf5`
- `ntdll!RtlFreeHeap` at `0x18000bd5a`
- `ntdll!RtlFreeHeap` at `0x18007aacf`
- `ntdll!RtlFreeHeap` at `0x18000bd5a`
- `ntdll!RtlFreeHeap` at `0x18007aacf`
- `ntdll!RtlAllocateHeap` at `0x18000bcaa`
- `ntdll!RtlAllocateHeap` at `0x18000bcaa`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000bc92`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000bc92`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18000bcfb`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18000bcfb`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18000bcdb`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18000bcdb`

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
0x18000bc30  mov     rax, rsp
0x18000bc33  mov     [rax+8], rbx
0x18000bc37  push    rdi
0x18000bc38  sub     rsp, 60h
0x18000bc3c  mov     edi, r8d
0x18000bc3f  mov     rbx, rdx
0x18000bc42  xorps   xmm0, xmm0
0x18000bc45  movups  xmmword ptr [rax-20h], xmm0
0x18000bc49  xorps   xmm1, xmm1
0x18000bc4c  movups  xmmword ptr [rax-30h], xmm1
0x18000bc50  movups  xmmword ptr [rax-40h], xmm0
0x18000bc54  mov     rdx, rcx
0x18000bc57  lea     rcx, [rax-20h]
0x18000bc5b  call    Basep8BitStringToDynamicUnicodeString
0x18000bc60  test    eax, eax
0x18000bc62  jz      loc_18000BD6D
0x18000bc68  mov     [rsp+68h+var_28], rbx
0x18000bc6d  lea     eax, [rdi-1]
0x18000bc70  mov     [rsp+68h+var_30], ax
0x18000bc75  mov     [rsp+68h+var_2E], di
0x18000bc7a  mov     [rsp+68h+DestinationString.Buffer], 0
0x18000bc83  xor     eax, eax
0x18000bc85  mov     dword ptr [rsp+68h+DestinationString.Length], eax
0x18000bc89  movzx   eax, di
0x18000bc8c  add     ax, ax
0x18000bc8f  movzx   ebx, ax
0x18000bc92  call    cs:__imp_KernelBaseGetGlobalData
0x18000bc98  mov     r8d, ebx; Size
0x18000bc9b  mov     rcx, gs:60h
0x18000bca4  mov     edx, [rax]; Flags
0x18000bca6  mov     rcx, [rcx+30h]; HeapHandle
0x18000bcaa  call    cs:__imp_RtlAllocateHeap
0x18000bcb0  mov     [rsp+68h+DestinationString.Buffer], rax
0x18000bcb5  test    rax, rax
0x18000bcb8  jnz     short loc_18000BCCB
0x18000bcba  lea     ecx, [rax+8]; LastError
0x18000bcbd  call    cs:__imp_RtlSetLastWin32Error
0x18000bcc3  xor     ebx, ebx
0x18000bcc5  mov     [rsp+68h+var_48], ebx
0x18000bcc9  jmp     short loc_18000BD3E
0x18000bccb  mov     [rsp+68h+DestinationString.MaximumLength], bx
0x18000bcd0  mov     r8d, edi; cchBufferLength
0x18000bcd3  mov     rdx, rax; lpszVolumePathName
0x18000bcd6  mov     rcx, [rsp+68h+UnicodeString.Buffer]; lpszFileName
0x18000bcdb  call    cs:__imp_GetVolumePathNameW
0x18000bce1  mov     ebx, eax
0x18000bce3  mov     [rsp+68h+var_48], eax
0x18000bce7  test    eax, eax
0x18000bce9  jz      short loc_18000BD3E
0x18000bceb  mov     rdx, [rsp+68h+DestinationString.Buffer]; SourceString
0x18000bcf0  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18000bcf5  call    cs:__imp_RtlInitUnicodeString
0x18000bcfb  call    cs:__imp_GetUnicodeStringToEightBitStringRoutine
0x18000bd01  xor     r8d, r8d
0x18000bd04  lea     rdx, [rsp+68h+DestinationString]
0x18000bd09  lea     rcx, [rsp+68h+var_30]
0x18000bd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd13  test    eax, eax
0x18000bd15  jns     short loc_18000BD20
0x18000bd17  mov     ecx, eax
0x18000bd19  call    BaseSetLastNTError
0x18000bd1e  jmp     short loc_18000BCC3
0x18000bd20  movzx   eax, [rsp+68h+var_30]
0x18000bd25  cmp     eax, edi
0x18000bd27  jb      short loc_18000BD30
0x18000bd29  mov     ecx, 80000005h
0x18000bd2e  jmp     short loc_18000BD19
0x18000bd30  movzx   ecx, [rsp+68h+var_30]
0x18000bd35  mov     rax, [rsp+68h+var_28]
0x18000bd3a  mov     byte ptr [rcx+rax], 0
0x18000bd3e  cmp     [rsp+68h+DestinationString.Buffer], 0
0x18000bd44  jz      short loc_18000BD60
0x18000bd46  mov     rcx, gs:60h
0x18000bd4f  mov     r8, [rsp+68h+DestinationString.Buffer]; P
0x18000bd54  xor     edx, edx; Flags
0x18000bd56  mov     rcx, [rcx+30h]; HeapHandle
0x18000bd5a  call    cs:__imp_RtlFreeHeap
0x18000bd60  lea     rcx, [rsp+68h+UnicodeString]; UnicodeString
0x18000bd65  call    cs:__imp_RtlFreeUnicodeString
0x18000bd6b  mov     eax, ebx
0x18000bd6d  mov     rbx, [rsp+68h+arg_0]
0x18000bd72  add     rsp, 60h
0x18000bd76  pop     rdi
0x18000bd77  retn
0x18007aaac  push    rbp
0x18007aaae  sub     rsp, 20h
0x18007aab2  mov     rbp, rdx
0x18007aab5  cmp     qword ptr [rbp+30h], 0
0x18007aaba  jz      short loc_18007AAD6
0x18007aabc  mov     rcx, gs:60h
0x18007aac5  mov     r8, [rbp+30h]; P
0x18007aac9  xor     edx, edx; Flags
0x18007aacb  mov     rcx, [rcx+30h]; HeapHandle
0x18007aacf  call    cs:__imp_RtlFreeHeap
0x18007aad5  nop
0x18007aad6  lea     rcx, [rbp+48h]; UnicodeString
0x18007aada  call    cs:__imp_RtlFreeUnicodeString
0x18007aae0  nop
0x18007aae1  add     rsp, 20h
0x18007aae5  pop     rbp
0x18007aae6  retn
```
