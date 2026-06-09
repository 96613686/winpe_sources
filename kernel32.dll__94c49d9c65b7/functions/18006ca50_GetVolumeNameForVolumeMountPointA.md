# GetVolumeNameForVolumeMountPointA

- ea: `0x18006ca50`
- end: `0x18006cb98`
- name: `GetVolumeNameForVolumeMountPointA`
- size: `328`
- prototype: `BOOL __stdcall(LPCSTR lpszVolumeMountPoint, LPSTR lpszVolumeName, DWORD cchBufferLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000d6c0`
- `0x18000f920`
- `0x18006ca50`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18006cb85`
- `ntdll!RtlFreeUnicodeString` at `0x18007ba8e`
- `ntdll!RtlFreeUnicodeString` at `0x18006cb85`
- `ntdll!RtlFreeUnicodeString` at `0x18007ba8e`
- `ntdll!RtlSetLastWin32Error` at `0x18006cadd`
- `ntdll!RtlSetLastWin32Error` at `0x18006cadd`
- `ntdll!RtlInitUnicodeString` at `0x18006cb15`
- `ntdll!RtlInitUnicodeString` at `0x18006cb15`
- `ntdll!RtlFreeHeap` at `0x18006cb7a`
- `ntdll!RtlFreeHeap` at `0x18007ba83`
- `ntdll!RtlFreeHeap` at `0x18006cb7a`
- `ntdll!RtlFreeHeap` at `0x18007ba83`
- `ntdll!RtlAllocateHeap` at `0x18006caca`
- `ntdll!RtlAllocateHeap` at `0x18006caca`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x18006cafb`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x18006cafb`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006cab2`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006cab2`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18006cb1b`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18006cb1b`

## pseudocode

```c
BOOL __stdcall GetVolumeNameForVolumeMountPointA(
        LPCSTR lpszVolumeMountPoint,
        LPSTR lpszVolumeName,
        DWORD cchBufferLength)
{
  BOOL result; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  ULONG *GlobalData; // rax
  WCHAR *Heap; // rax
  BOOL VolumeNameForVolumeMountPointW; // ebx
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
  result = Basep8BitStringToDynamicUnicodeString(&UnicodeString, lpszVolumeMountPoint);
  if ( !result )
    return result;
  *((_QWORD *)&v19 + 1) = lpszVolumeName;
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
    VolumeNameForVolumeMountPointW = GetVolumeNameForVolumeMountPointW(UnicodeString.Buffer, Heap, cchBufferLength);
    if ( !VolumeNameForVolumeMountPointW )
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
  VolumeNameForVolumeMountPointW = 0;
LABEL_12:
  if ( DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  RtlFreeUnicodeString(&UnicodeString);
  return VolumeNameForVolumeMountPointW;
}

```

## disassembly

```asm
0x18006ca50  mov     rax, rsp
0x18006ca53  mov     [rax+8], rbx
0x18006ca57  push    rdi
0x18006ca58  sub     rsp, 60h
0x18006ca5c  mov     edi, r8d
0x18006ca5f  mov     rbx, rdx
0x18006ca62  xorps   xmm0, xmm0
0x18006ca65  movups  xmmword ptr [rax-20h], xmm0
0x18006ca69  xorps   xmm1, xmm1
0x18006ca6c  movups  xmmword ptr [rax-30h], xmm1
0x18006ca70  movups  xmmword ptr [rax-40h], xmm0
0x18006ca74  mov     rdx, rcx
0x18006ca77  lea     rcx, [rax-20h]
0x18006ca7b  call    Basep8BitStringToDynamicUnicodeString
0x18006ca80  test    eax, eax
0x18006ca82  jz      loc_18006CB8D
0x18006ca88  mov     [rsp+68h+var_28], rbx
0x18006ca8d  lea     eax, [rdi-1]
0x18006ca90  mov     [rsp+68h+var_30], ax
0x18006ca95  mov     [rsp+68h+var_2E], di
0x18006ca9a  mov     [rsp+68h+DestinationString.Buffer], 0
0x18006caa3  xor     eax, eax
0x18006caa5  mov     dword ptr [rsp+68h+DestinationString.Length], eax
0x18006caa9  movzx   eax, di
0x18006caac  add     ax, ax
0x18006caaf  movzx   ebx, ax
0x18006cab2  call    cs:__imp_KernelBaseGetGlobalData
0x18006cab8  mov     r8d, ebx; Size
0x18006cabb  mov     rcx, gs:60h
0x18006cac4  mov     edx, [rax]; Flags
0x18006cac6  mov     rcx, [rcx+30h]; HeapHandle
0x18006caca  call    cs:__imp_RtlAllocateHeap
0x18006cad0  mov     [rsp+68h+DestinationString.Buffer], rax
0x18006cad5  test    rax, rax
0x18006cad8  jnz     short loc_18006CAEB
0x18006cada  lea     ecx, [rax+8]; LastError
0x18006cadd  call    cs:__imp_RtlSetLastWin32Error
0x18006cae3  xor     ebx, ebx
0x18006cae5  mov     [rsp+68h+var_48], ebx
0x18006cae9  jmp     short loc_18006CB5E
0x18006caeb  mov     [rsp+68h+DestinationString.MaximumLength], bx
0x18006caf0  mov     r8d, edi; cchBufferLength
0x18006caf3  mov     rdx, rax; lpszVolumeName
0x18006caf6  mov     rcx, [rsp+68h+UnicodeString.Buffer]; lpszVolumeMountPoint
0x18006cafb  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18006cb01  mov     ebx, eax
0x18006cb03  mov     [rsp+68h+var_48], eax
0x18006cb07  test    eax, eax
0x18006cb09  jz      short loc_18006CB5E
0x18006cb0b  mov     rdx, [rsp+68h+DestinationString.Buffer]; SourceString
0x18006cb10  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18006cb15  call    cs:__imp_RtlInitUnicodeString
0x18006cb1b  call    cs:__imp_GetUnicodeStringToEightBitStringRoutine
0x18006cb21  xor     r8d, r8d
0x18006cb24  lea     rdx, [rsp+68h+DestinationString]
0x18006cb29  lea     rcx, [rsp+68h+var_30]
0x18006cb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb33  test    eax, eax
0x18006cb35  jns     short loc_18006CB40
0x18006cb37  mov     ecx, eax
0x18006cb39  call    BaseSetLastNTError
0x18006cb3e  jmp     short loc_18006CAE3
0x18006cb40  movzx   eax, [rsp+68h+var_30]
0x18006cb45  cmp     eax, edi
0x18006cb47  jb      short loc_18006CB50
0x18006cb49  mov     ecx, 80000005h
0x18006cb4e  jmp     short loc_18006CB39
0x18006cb50  movzx   ecx, [rsp+68h+var_30]
0x18006cb55  mov     rax, [rsp+68h+var_28]
0x18006cb5a  mov     byte ptr [rcx+rax], 0
0x18006cb5e  cmp     [rsp+68h+DestinationString.Buffer], 0
0x18006cb64  jz      short loc_18006CB80
0x18006cb66  mov     rcx, gs:60h
0x18006cb6f  mov     r8, [rsp+68h+DestinationString.Buffer]; P
0x18006cb74  xor     edx, edx; Flags
0x18006cb76  mov     rcx, [rcx+30h]; HeapHandle
0x18006cb7a  call    cs:__imp_RtlFreeHeap
0x18006cb80  lea     rcx, [rsp+68h+UnicodeString]; UnicodeString
0x18006cb85  call    cs:__imp_RtlFreeUnicodeString
0x18006cb8b  mov     eax, ebx
0x18006cb8d  mov     rbx, [rsp+68h+arg_0]
0x18006cb92  add     rsp, 60h
0x18006cb96  pop     rdi
0x18006cb97  retn
0x18007ba60  push    rbp
0x18007ba62  sub     rsp, 20h
0x18007ba66  mov     rbp, rdx
0x18007ba69  cmp     qword ptr [rbp+30h], 0
0x18007ba6e  jz      short loc_18007BA8A
0x18007ba70  mov     rcx, gs:60h
0x18007ba79  mov     r8, [rbp+30h]; P
0x18007ba7d  xor     edx, edx; Flags
0x18007ba7f  mov     rcx, [rcx+30h]; HeapHandle
0x18007ba83  call    cs:__imp_RtlFreeHeap
0x18007ba89  nop
0x18007ba8a  lea     rcx, [rbp+48h]; UnicodeString
0x18007ba8e  call    cs:__imp_RtlFreeUnicodeString
0x18007ba94  nop
0x18007ba95  add     rsp, 20h
0x18007ba99  pop     rbp
0x18007ba9a  retn
```
