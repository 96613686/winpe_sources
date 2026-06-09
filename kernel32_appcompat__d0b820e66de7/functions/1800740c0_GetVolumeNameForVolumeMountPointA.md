# GetVolumeNameForVolumeMountPointA

- ea: `0x1800740c0`
- end: `0x18007423c`
- name: `GetVolumeNameForVolumeMountPointA`
- size: `380`
- prototype: `BOOL __stdcall(LPCSTR lpszVolumeMountPoint, LPSTR lpszVolumeName, DWORD cchBufferLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000ccf0`
- `0x180028f60`
- `0x1800740c0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180074222`
- `ntdll!RtlFreeUnicodeString` at `0x180083c1d`
- `ntdll!RtlFreeUnicodeString` at `0x180074222`
- `ntdll!RtlFreeUnicodeString` at `0x180083c1d`
- `ntdll!RtlSetLastWin32Error` at `0x180074159`
- `ntdll!RtlSetLastWin32Error` at `0x180074159`
- `ntdll!RtlInitUnicodeString` at `0x1800741a0`
- `ntdll!RtlInitUnicodeString` at `0x1800741a0`
- `ntdll!RtlFreeHeap` at `0x180074211`
- `ntdll!RtlFreeHeap` at `0x180083c0c`
- `ntdll!RtlFreeHeap` at `0x180074211`
- `ntdll!RtlFreeHeap` at `0x180083c0c`
- `ntdll!RtlAllocateHeap` at `0x180074140`
- `ntdll!RtlAllocateHeap` at `0x180074140`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x180074180`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x180074180`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180074122`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180074122`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x1800741ac`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x1800741ac`

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
0x1800740c0  mov     rax, rsp
0x1800740c3  mov     [rax+8], rbx
0x1800740c7  push    rdi
0x1800740c8  sub     rsp, 60h
0x1800740cc  mov     edi, r8d
0x1800740cf  mov     rbx, rdx
0x1800740d2  xorps   xmm0, xmm0
0x1800740d5  movups  xmmword ptr [rax-20h], xmm0
0x1800740d9  xorps   xmm1, xmm1
0x1800740dc  movups  xmmword ptr [rax-30h], xmm1
0x1800740e0  movups  xmmword ptr [rax-40h], xmm0
0x1800740e4  mov     rdx, rcx
0x1800740e7  lea     rcx, [rax-20h]
0x1800740eb  call    Basep8BitStringToDynamicUnicodeString
0x1800740f0  test    eax, eax
0x1800740f2  jz      loc_180074230
0x1800740f8  mov     [rsp+68h+var_28], rbx
0x1800740fd  lea     eax, [rdi-1]
0x180074100  mov     [rsp+68h+var_30], ax
0x180074105  mov     [rsp+68h+var_2E], di
0x18007410a  mov     [rsp+68h+DestinationString.Buffer], 0
0x180074113  xor     eax, eax
0x180074115  mov     dword ptr [rsp+68h+DestinationString.Length], eax
0x180074119  movzx   eax, di
0x18007411c  add     ax, ax
0x18007411f  movzx   ebx, ax
0x180074122  call    cs:__imp_KernelBaseGetGlobalData
0x180074129  nop     dword ptr [rax+rax+00h]
0x18007412e  mov     r8d, ebx; Size
0x180074131  mov     rcx, gs:60h
0x18007413a  mov     edx, [rax]; Flags
0x18007413c  mov     rcx, [rcx+30h]; HeapHandle
0x180074140  call    cs:__imp_RtlAllocateHeap
0x180074147  nop     dword ptr [rax+rax+00h]
0x18007414c  mov     [rsp+68h+DestinationString.Buffer], rax
0x180074151  test    rax, rax
0x180074154  jnz     short loc_180074170
0x180074156  lea     ecx, [rax+8]; LastError
0x180074159  call    cs:__imp_RtlSetLastWin32Error
0x180074160  nop     dword ptr [rax+rax+00h]
0x180074165  xor     ebx, ebx
0x180074167  mov     [rsp+68h+var_48], ebx
0x18007416b  jmp     loc_1800741F5
0x180074170  mov     [rsp+68h+DestinationString.MaximumLength], bx
0x180074175  mov     r8d, edi; cchBufferLength
0x180074178  mov     rdx, rax; lpszVolumeName
0x18007417b  mov     rcx, [rsp+68h+UnicodeString.Buffer]; lpszVolumeMountPoint
0x180074180  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180074187  nop     dword ptr [rax+rax+00h]
0x18007418c  mov     ebx, eax
0x18007418e  mov     [rsp+68h+var_48], eax
0x180074192  test    eax, eax
0x180074194  jz      short loc_1800741F5
0x180074196  mov     rdx, [rsp+68h+DestinationString.Buffer]; SourceString
0x18007419b  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800741a0  call    cs:__imp_RtlInitUnicodeString
0x1800741a7  nop     dword ptr [rax+rax+00h]
0x1800741ac  call    cs:__imp_GetUnicodeStringToEightBitStringRoutine
0x1800741b3  nop     dword ptr [rax+rax+00h]
0x1800741b8  xor     r8d, r8d
0x1800741bb  lea     rdx, [rsp+68h+DestinationString]
0x1800741c0  lea     rcx, [rsp+68h+var_30]
0x1800741c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800741ca  test    eax, eax
0x1800741cc  jns     short loc_1800741D7
0x1800741ce  mov     ecx, eax
0x1800741d0  call    BaseSetLastNTError
0x1800741d5  jmp     short loc_180074165
0x1800741d7  movzx   eax, [rsp+68h+var_30]
0x1800741dc  cmp     eax, edi
0x1800741de  jb      short loc_1800741E7
0x1800741e0  mov     ecx, 80000005h
0x1800741e5  jmp     short loc_1800741D0
0x1800741e7  movzx   ecx, [rsp+68h+var_30]
0x1800741ec  mov     rax, [rsp+68h+var_28]
0x1800741f1  mov     byte ptr [rcx+rax], 0
0x1800741f5  cmp     [rsp+68h+DestinationString.Buffer], 0
0x1800741fb  jz      short loc_18007421D
0x1800741fd  mov     rcx, gs:60h
0x180074206  mov     r8, [rsp+68h+DestinationString.Buffer]; P
0x18007420b  xor     edx, edx; Flags
0x18007420d  mov     rcx, [rcx+30h]; HeapHandle
0x180074211  call    cs:__imp_RtlFreeHeap
0x180074218  nop     dword ptr [rax+rax+00h]
0x18007421d  lea     rcx, [rsp+68h+UnicodeString]; UnicodeString
0x180074222  call    cs:__imp_RtlFreeUnicodeString
0x180074229  nop     dword ptr [rax+rax+00h]
0x18007422e  mov     eax, ebx
0x180074230  mov     rbx, [rsp+68h+arg_0]
0x180074235  add     rsp, 60h
0x180074239  pop     rdi
0x18007423a  retn
0x180083be9  push    rbp
0x180083beb  sub     rsp, 20h
0x180083bef  mov     rbp, rdx
0x180083bf2  cmp     qword ptr [rbp+30h], 0
0x180083bf7  jz      short loc_180083C19
0x180083bf9  mov     rcx, gs:60h
0x180083c02  mov     r8, [rbp+30h]; P
0x180083c06  xor     edx, edx; Flags
0x180083c08  mov     rcx, [rcx+30h]; HeapHandle
0x180083c0c  call    cs:__imp_RtlFreeHeap
0x180083c13  nop     dword ptr [rax+rax+00h]
0x180083c18  nop
0x180083c19  lea     rcx, [rbp+48h]; UnicodeString
0x180083c1d  call    cs:__imp_RtlFreeUnicodeString
0x180083c24  nop     dword ptr [rax+rax+00h]
0x180083c29  nop
0x180083c2a  add     rsp, 20h
0x180083c2e  pop     rbp
0x180083c2f  retn
```
