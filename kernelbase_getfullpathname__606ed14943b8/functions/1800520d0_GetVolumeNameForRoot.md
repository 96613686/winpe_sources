# GetVolumeNameForRoot

- ea: `0x1800520d0`
- end: `0x18005287f`
- name: `GetVolumeNameForRoot`
- size: `1967`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180050cc0`
- `0x180050eb0`

## callees

- `0x18004c490`
- `0x1800520d0`
- `0x1800533cc`
- `0x180053c30`
- `0x18013877c`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180052202`
- `ntdll!NtOpenFile` at `0x180052202`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18005212e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18005212e`
- `ntdll!RtlSetLastWin32Error` at `0x1800526c2`
- `ntdll!RtlSetLastWin32Error` at `0x1800526da`
- `ntdll!RtlSetLastWin32Error` at `0x18005271d`
- `ntdll!RtlSetLastWin32Error` at `0x180052753`
- `ntdll!RtlSetLastWin32Error` at `0x18005276b`
- `ntdll!RtlSetLastWin32Error` at `0x18005281f`
- `ntdll!RtlSetLastWin32Error` at `0x18005283c`
- `ntdll!RtlSetLastWin32Error` at `0x1800526c2`
- `ntdll!RtlSetLastWin32Error` at `0x1800526da`
- `ntdll!RtlSetLastWin32Error` at `0x18005271d`
- `ntdll!RtlSetLastWin32Error` at `0x180052753`
- `ntdll!RtlSetLastWin32Error` at `0x18005276b`
- `ntdll!RtlSetLastWin32Error` at `0x18005281f`
- `ntdll!RtlSetLastWin32Error` at `0x18005283c`
- `ntdll!RtlNtStatusToDosError` at `0x18005270f`
- `ntdll!RtlNtStatusToDosError` at `0x18005270f`
- `ntdll!NtClose` at `0x180052254`
- `ntdll!NtClose` at `0x180052254`
- `ntdll!RtlFreeHeap` at `0x180052274`
- `ntdll!RtlFreeHeap` at `0x18005236d`
- `ntdll!RtlFreeHeap` at `0x180052468`
- `ntdll!RtlFreeHeap` at `0x1800525e4`
- `ntdll!RtlFreeHeap` at `0x180052654`
- `ntdll!RtlFreeHeap` at `0x180052701`
- `ntdll!RtlFreeHeap` at `0x180052742`
- `ntdll!RtlFreeHeap` at `0x180052789`
- `ntdll!RtlFreeHeap` at `0x1800527b8`
- `ntdll!RtlFreeHeap` at `0x1800527d6`
- `ntdll!RtlFreeHeap` at `0x18005280e`
- `ntdll!RtlFreeHeap` at `0x180052869`
- `ntdll!RtlFreeHeap` at `0x180052274`
- `ntdll!RtlFreeHeap` at `0x18005236d`
- `ntdll!RtlFreeHeap` at `0x180052468`
- `ntdll!RtlFreeHeap` at `0x1800525e4`
- `ntdll!RtlFreeHeap` at `0x180052654`
- `ntdll!RtlFreeHeap` at `0x180052701`
- `ntdll!RtlFreeHeap` at `0x180052742`
- `ntdll!RtlFreeHeap` at `0x180052789`
- `ntdll!RtlFreeHeap` at `0x1800527b8`
- `ntdll!RtlFreeHeap` at `0x1800527d6`
- `ntdll!RtlFreeHeap` at `0x18005280e`
- `ntdll!RtlFreeHeap` at `0x180052869`
- `ntdll!toupper` at `0x18005219a`
- `ntdll!toupper` at `0x18005219a`
- `ntdll!RtlAllocateHeap` at `0x1800522b2`
- `ntdll!RtlAllocateHeap` at `0x180052314`
- `ntdll!RtlAllocateHeap` at `0x180052392`
- `ntdll!RtlAllocateHeap` at `0x180052676`
- `ntdll!RtlAllocateHeap` at `0x1800522b2`
- `ntdll!RtlAllocateHeap` at `0x180052314`
- `ntdll!RtlAllocateHeap` at `0x180052392`
- `ntdll!RtlAllocateHeap` at `0x180052676`

## string_xrefs

- `0x1800523d8`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall GetVolumeNameForRoot(const WCHAR *a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // r15
  USHORT Length; // cx
  PWSTR Buffer; // rdx
  WCHAR *v7; // r8
  unsigned __int64 v8; // rax
  int v9; // ebx
  BOOL v10; // ebx
  WCHAR *Heap; // rax
  _WORD *v12; // rax
  _WORD *v13; // rdi
  void *v14; // rcx
  unsigned int v15; // eax
  DWORD *v16; // rbx
  void *FileInternal; // rax
  BOOL i; // eax
  BOOL v19; // esi
  DWORD j; // edx
  __int16 v21; // r8
  __int64 v22; // rax
  __int16 v23; // cx
  DWORD v25; // esi
  PVOID v26; // rax
  ULONG v27; // eax
  ULONG v28; // ecx
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v33[4]; // [rsp+90h] [rbp-70h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-60h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  USHORT OutBuffer; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE Src[526]; // [rsp+C2h] [rbp-3Eh] BYREF

  v3 = a3;
  FileHandle = 0;
  NtPathName = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
  {
    RtlSetLastWin32Error(3u);
    return 0;
  }
  Length = NtPathName.Length;
  Buffer = NtPathName.Buffer;
  v7 = &NtPathName.Buffer[(unsigned __int64)NtPathName.Length >> 1];
  if ( *(v7 - 1) == 92 )
  {
    *(v7 - 1) = 0;
    Buffer = NtPathName.Buffer;
    Length = NtPathName.Length - 2;
    NtPathName.Length -= 2;
  }
  if ( Length >= 4u )
  {
    v8 = (unsigned __int64)Length >> 1;
    if ( Buffer[v8 - 1] == 58 )
      NtPathName.Buffer[((unsigned __int64)NtPathName.Length >> 1) - 2] = toupper(Buffer[v8 - 2]);
  }
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 0x10u);
  if ( v9 < 0 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    v27 = RtlNtStatusToDosError(v9);
    RtlSetLastWin32Error(v27);
    return 0;
  }
  v10 = DeviceIoControl(FileHandle, 0x4D0008u, 0, 0, &OutBuffer, 0x208u, &BytesReturned, 0);
  NtClose(FileHandle);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( !v10 )
    return 0;
  NtPathName.Length = OutBuffer;
  NtPathName.MaximumLength = OutBuffer + 2;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, (unsigned __int16)(OutBuffer + 2));
  NtPathName.Buffer = Heap;
  if ( !Heap )
  {
    RtlSetLastWin32Error(8u);
    return 0;
  }
  memcpy_0(Heap, Src, OutBuffer);
  NtPathName.Buffer[(unsigned __int64)NtPathName.Length >> 1] = 0;
  v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, NtPathName.Length + 24LL);
  v13 = v12;
  if ( v12 )
  {
    v14 = v12 + 12;
    *(_OWORD *)v12 = 0;
    *((_QWORD *)v12 + 2) = 0;
    *((_DWORD *)v12 + 4) = 24;
    v15 = NtPathName.Length;
    v13[10] = NtPathName.Length;
    memcpy_0(v14, NtPathName.Buffer, v15);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    v16 = (DWORD *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x20u);
    if ( v16 )
    {
      v33[0] = 32;
      *(_QWORD *)&v33[1] = 128;
      v33[3] = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
      FileInternal = (void *)CreateFileInternal(L"\\\\.\\MountPointManager", 0, 3u, 3, (__int64)v33, 1);
      if ( FileInternal == (void *)-1LL )
      {
        IsBrokeredCreateDirectoryWPresent();
        FileHandle = (HANDLE)-1LL;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
LABEL_52:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
        return 0;
      }
      else
      {
        FileHandle = FileInternal;
        for ( i = DeviceIoControl(FileInternal, 0x6D0008u, v13, NtPathName.Length + 24, v16, 0x20u, &BytesReturned, 0);
              ;
              i = DeviceIoControl(FileHandle, 0x6D0008u, v13, NtPathName.Length + 24, v26, v25, &BytesReturned, 0) )
        {
          v19 = i;
          if ( i || NtCurrentTeb()->LastErrorValue != 234 )
            break;
          v25 = *v16;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
          v26 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v25);
          v16 = (DWORD *)v26;
          if ( !v26 )
          {
            CloseHandle(FileHandle);
            RtlSetLastWin32Error(8u);
            goto LABEL_52;
          }
        }
        CloseHandle(FileHandle);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
        if ( v19 )
        {
          for ( j = 0; j < v16[1]; ++j )
          {
            v21 = v16[6 * j + 3];
            v22 = v16[6 * j + 2];
            if ( (v21 == 96 || v21 == 98 && *(_WORD *)((char *)v16 + v22 + 96) == 92)
              && *(_WORD *)((char *)v16 + v22) == 92 )
            {
              v23 = *(_WORD *)((char *)v16 + v22 + 2);
              if ( (v23 == 63 || v23 == 92)
                && *(_WORD *)((char *)v16 + v22 + 4) == 63
                && *(_WORD *)((char *)v16 + v22 + 6) == 92
                && *(_WORD *)((char *)v16 + v22 + 8) == 86
                && *(_WORD *)((char *)v16 + v22 + 10) == 111
                && *(_WORD *)((char *)v16 + v22 + 12) == 108
                && *(_WORD *)((char *)v16 + v22 + 14) == 117
                && *(_WORD *)((char *)v16 + v22 + 16) == 109
                && *(_WORD *)((char *)v16 + v22 + 18) == 101
                && *(_WORD *)((char *)v16 + v22 + 20) == 123
                && *(_WORD *)((char *)v16 + v22 + 38) == 45
                && *(_WORD *)((char *)v16 + v22 + 48) == 45
                && *(_WORD *)((char *)v16 + v22 + 58) == 45
                && *(_WORD *)((char *)v16 + v22 + 68) == 45
                && *(_WORD *)((char *)v16 + v22 + 94) == 125
                && v21 == 96
                && v23 == 63 )
              {
                if ( (unsigned __int64)(2 * v3) >= 0x64 )
                {
                  *(_OWORD *)a2 = *(_OWORD *)((char *)v16 + v22);
                  *(_OWORD *)(a2 + 16) = *(_OWORD *)((char *)v16 + v22 + 16);
                  *(_OWORD *)(a2 + 32) = *(_OWORD *)((char *)v16 + v22 + 32);
                  *(_OWORD *)(a2 + 48) = *(_OWORD *)((char *)v16 + v22 + 48);
                  *(_OWORD *)(a2 + 64) = *(_OWORD *)((char *)v16 + v22 + 64);
                  *(_OWORD *)(a2 + 80) = *(_OWORD *)((char *)v16 + v22 + 80);
                  *(_WORD *)(a2 + 2) = 92;
                  *(_DWORD *)(a2 + 96) = 92;
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
                  return 1;
                }
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
                v28 = 206;
                goto LABEL_49;
              }
            }
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
        v28 = 87;
LABEL_49:
        RtlSetLastWin32Error(v28);
        return 0;
      }
    }
    else
    {
      RtlSetLastWin32Error(8u);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
      return 0;
    }
  }
  else
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    RtlSetLastWin32Error(8u);
    return 0;
  }
}

```

## disassembly

```asm
0x1800520d0  push    rbp
0x1800520d2  push    r12
0x1800520d4  push    r14
0x1800520d6  push    r15
0x1800520d8  lea     rbp, [rsp-1E8h]
0x1800520e0  sub     rsp, 2E8h
0x1800520e7  mov     rax, cs:__security_cookie
0x1800520ee  xor     rax, rsp
0x1800520f1  mov     [rbp+200h+var_30], rax
0x1800520f8  xorps   xmm0, xmm0
0x1800520fb  mov     r15d, r8d
0x1800520fe  mov     r14, rdx
0x180052101  xor     r12d, r12d
0x180052104  movups  xmmword ptr [rsp+300h+ObjectAttributes.ObjectName], xmm0
0x180052109  xor     eax, eax
0x18005210b  mov     [rsp+300h+FileHandle], r12
0x180052110  xor     r9d, r9d; DirectoryInfo
0x180052113  lea     rdx, [rsp+300h+NtPathName]; NtPathName
0x180052118  xor     r8d, r8d; NtFileNamePart
0x18005211b  movups  xmmword ptr [rsp+300h+ObjectAttributes+1Ch], xmm0
0x180052120  movups  xmmword ptr [rsp+300h+NtPathName.Length], xmm0
0x180052125  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm0
0x18005212a  movups  xmmword ptr [rbp+200h+IoStatusBlock], xmm0
0x18005212e  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180052135  nop     dword ptr [rax+rax+00h]
0x18005213a  test    al, al
0x18005213c  jz      loc_1800526D5
0x180052142  movzx   ecx, [rsp+300h+NtPathName.Length]
0x180052147  mov     rdx, [rsp+300h+NtPathName.Buffer]
0x18005214c  mov     eax, ecx
0x18005214e  shr     rax, 1
0x180052151  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x180052157  mov     [rsp+300h+arg_10], rbx
0x18005215f  lea     r8, [rdx+rax*2]
0x180052163  jnz     short loc_180052181
0x180052165  mov     [r8-2], r12w
0x18005216a  mov     eax, 0FFFEh
0x18005216f  movzx   ecx, [rsp+300h+NtPathName.Length]
0x180052174  mov     rdx, [rsp+300h+NtPathName.Buffer]
0x180052179  add     cx, ax
0x18005217c  mov     [rsp+300h+NtPathName.Length], cx
0x180052181  cmp     cx, 4
0x180052185  jb      short loc_1800521B8
0x180052187  movzx   eax, cx
0x18005218a  shr     rax, 1
0x18005218d  cmp     word ptr [rdx+rax*2-2], 3Ah ; ':'
0x180052193  jnz     short loc_1800521B8
0x180052195  movzx   ecx, word ptr [rdx+rax*2-4]; C
0x18005219a  call    cs:__imp_toupper
0x1800521a1  nop     dword ptr [rax+rax+00h]
0x1800521a6  movzx   edx, [rsp+300h+NtPathName.Length]
0x1800521ab  mov     rcx, [rsp+300h+NtPathName.Buffer]
0x1800521b0  shr     rdx, 1
0x1800521b3  mov     [rcx+rdx*2-4], ax
0x1800521b8  lea     rax, [rsp+300h+NtPathName]
0x1800521bd  mov     [rsp+300h+OpenOptions], 10h; OpenOptions
0x1800521c5  xorps   xmm0, xmm0
0x1800521c8  mov     [rsp+300h+ObjectAttributes.ObjectName], rax
0x1800521cd  lea     r9, [rbp+200h+IoStatusBlock]; IoStatusBlock
0x1800521d1  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x1800521d9  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x1800521de  mov     [rsp+300h+ObjectAttributes.RootDirectory], r12
0x1800521e3  mov     edx, 100080h; DesiredAccess
0x1800521e8  mov     [rsp+300h+ObjectAttributes.Attributes], 40h ; '@'
0x1800521f0  lea     rcx, [rsp+300h+FileHandle]; FileHandle
0x1800521f5  mov     [rsp+300h+ShareAccess], 3; ShareAccess
0x1800521fd  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x180052202  call    cs:__imp_NtOpenFile
0x180052209  nop     dword ptr [rax+rax+00h]
0x18005220e  mov     ebx, eax
0x180052210  test    eax, eax
0x180052212  js      loc_1800526ED
0x180052218  mov     rcx, [rsp+300h+FileHandle]; hDevice
0x18005221d  lea     rax, [rsp+300h+BytesReturned]
0x180052222  mov     [rsp+300h+lpOverlapped], r12; lpOverlapped
0x180052227  xor     r9d, r9d; nInBufferSize
0x18005222a  mov     [rsp+300h+lpBytesReturned], rax; lpBytesReturned
0x18005222f  xor     r8d, r8d; lpInBuffer
0x180052232  lea     rax, [rbp+200h+OutBuffer]
0x180052236  mov     [rsp+300h+OpenOptions], 208h; nOutBufferSize
0x18005223e  mov     edx, 4D0008h; dwIoControlCode
0x180052243  mov     qword ptr [rsp+300h+ShareAccess], rax; lpOutBuffer
0x180052248  call    DeviceIoControl
0x18005224d  mov     rcx, [rsp+300h+FileHandle]; Handle
0x180052252  mov     ebx, eax
0x180052254  call    cs:__imp_NtClose
0x18005225b  nop     dword ptr [rax+rax+00h]
0x180052260  mov     rcx, gs:60h
0x180052269  xor     edx, edx; Flags
0x18005226b  mov     r8, [rsp+300h+NtPathName.Buffer]; P
0x180052270  mov     rcx, [rcx+30h]; HeapHandle
0x180052274  call    cs:__imp_RtlFreeHeap
0x18005227b  nop     dword ptr [rax+rax+00h]
0x180052280  test    ebx, ebx
0x180052282  jz      loc_1800526CE
0x180052288  movzx   eax, [rbp+200h+OutBuffer]
0x18005228c  mov     [rsp+300h+NtPathName.Length], ax
0x180052291  add     ax, 2
0x180052295  movzx   r8d, ax; Size
0x180052299  mov     [rsp+300h+NtPathName.MaximumLength], r8w
0x18005229f  mov     rcx, gs:60h
0x1800522a8  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800522ae  mov     rcx, [rcx+30h]; HeapHandle
0x1800522b2  call    cs:__imp_RtlAllocateHeap
0x1800522b9  nop     dword ptr [rax+rax+00h]
0x1800522be  mov     [rsp+300h+NtPathName.Buffer], rax
0x1800522c3  test    rax, rax
0x1800522c6  jz      loc_1800526BD
0x1800522cc  movzx   r8d, [rbp+200h+OutBuffer]; Size
0x1800522d1  lea     rdx, [rbp+200h+Src]; Src
0x1800522d5  mov     rcx, rax; void *
0x1800522d8  mov     [rsp+300h+var_20], rdi
0x1800522e0  call    memcpy_0
0x1800522e5  movzx   edx, [rsp+300h+NtPathName.Length]
0x1800522ea  mov     rax, [rsp+300h+NtPathName.Buffer]
0x1800522ef  shr     rdx, 1
0x1800522f2  mov     [rax+rdx*2], r12w
0x1800522f7  mov     rcx, gs:60h
0x180052300  movzx   r8d, [rsp+300h+NtPathName.Length]
0x180052306  mov     edx, cs:KernelBaseGlobalData; Flags
0x18005230c  add     r8, 18h; Size
0x180052310  mov     rcx, [rcx+30h]; HeapHandle
0x180052314  call    cs:__imp_RtlAllocateHeap
0x18005231b  nop     dword ptr [rax+rax+00h]
0x180052320  mov     rdi, rax
0x180052323  test    rax, rax
0x180052326  jz      loc_1800527FA
0x18005232c  xor     eax, eax
0x18005232e  lea     rcx, [rdi+18h]; void *
0x180052332  xorps   xmm0, xmm0
0x180052335  movups  xmmword ptr [rdi], xmm0
0x180052338  mov     [rdi+10h], rax
0x18005233c  mov     dword ptr [rdi+10h], 18h
0x180052343  movzx   eax, [rsp+300h+NtPathName.Length]
0x180052348  mov     [rdi+14h], ax
0x18005234c  mov     r8d, eax; Size
0x18005234f  mov     rdx, [rsp+300h+NtPathName.Buffer]; Src
0x180052354  call    memcpy_0
0x180052359  mov     rcx, gs:60h
0x180052362  xor     edx, edx; Flags
0x180052364  mov     r8, [rsp+300h+NtPathName.Buffer]; P
0x180052369  mov     rcx, [rcx+30h]; HeapHandle
0x18005236d  call    cs:__imp_RtlFreeHeap
0x180052374  nop     dword ptr [rax+rax+00h]
0x180052379  mov     rcx, gs:60h
0x180052382  mov     r8d, 20h ; ' '; Size
0x180052388  mov     edx, cs:KernelBaseGlobalData; Flags
0x18005238e  mov     rcx, [rcx+30h]; HeapHandle
0x180052392  call    cs:__imp_RtlAllocateHeap
0x180052399  nop     dword ptr [rax+rax+00h]
0x18005239e  mov     rbx, rax
0x1800523a1  test    rax, rax
0x1800523a4  jz      loc_180052766
0x1800523aa  movdqa  xmm0, cs:__xmm@ffffffffffffffff0000000000000000
0x1800523b2  lea     rax, [rbp+200h+var_270]
0x1800523b6  mov     r9d, 3
0x1800523bc  mov     [rsp+300h+OpenOptions], 1; int
0x1800523c4  mov     r8d, r9d
0x1800523c7  mov     [rsp+300h+arg_18], rsi
0x1800523cf  xor     edx, edx
0x1800523d1  mov     dword ptr [rbp+200h+var_270], 20h ; ' '
0x1800523d8  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x1800523df  mov     qword ptr [rbp+200h+var_270+4], 80h
0x1800523e7  mov     [rbp+200h+var_264], r12d
0x1800523eb  movdqu  [rbp+200h+var_260], xmm0
0x1800523f0  mov     qword ptr [rsp+300h+ShareAccess], rax; __int64
0x1800523f5  call    CreateFileInternal
0x1800523fa  mov     rsi, rax
0x1800523fd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180052401  jz      loc_18005279C
0x180052407  mov     [rsp+300h+lpOverlapped], r12; lpOverlapped
0x18005240c  mov     rcx, rsi; hDevice
0x18005240f  mov     [rsp+300h+FileHandle], rax
0x180052414  lea     rax, [rsp+300h+BytesReturned]
0x180052419  mov     [rsp+300h+lpBytesReturned], rax; lpBytesReturned
0x18005241e  mov     [rsp+300h+OpenOptions], 20h ; ' '; nOutBufferSize
0x180052426  movzx   r9d, [rsp+300h+NtPathName.Length]
0x18005242c  mov     r8, rdi; lpInBuffer
0x18005242f  add     r9d, 18h; nInBufferSize
0x180052433  mov     qword ptr [rsp+300h+ShareAccess], rbx; lpOutBuffer
0x180052438  mov     edx, 6D0008h; dwIoControlCode
0x18005243d  call    DeviceIoControl
0x180052442  mov     esi, eax
0x180052444  test    eax, eax
0x180052446  jz      loc_18005262C
0x18005244c  mov     rcx, [rsp+300h+FileHandle]; hObject
0x180052451  call    CloseHandle
0x180052456  mov     rcx, gs:60h
0x18005245f  mov     r8, rdi; P
0x180052462  xor     edx, edx; Flags
0x180052464  mov     rcx, [rcx+30h]; HeapHandle
0x180052468  call    cs:__imp_RtlFreeHeap
0x18005246f  nop     dword ptr [rax+rax+00h]
0x180052474  test    esi, esi
0x180052476  jz      loc_180052730
0x18005247c  mov     edx, r12d
0x18005247f  cmp     edx, [rbx+4]
0x180052482  jnb     loc_180052730
0x180052488  mov     eax, edx
0x18005248a  lea     rcx, [rax+rax*2]
0x18005248e  movzx   r8d, word ptr [rbx+rcx*8+0Ch]
0x180052494  mov     eax, [rbx+rcx*8+8]
0x180052498  cmp     r8w, 60h ; '`'
0x18005249d  jnz     loc_1800526AB
0x1800524a3  cmp     word ptr [rax+rbx], 5Ch ; '\'
0x1800524a8  jnz     loc_1800526B6
0x1800524ae  movzx   ecx, word ptr [rax+rbx+2]
0x1800524b3  cmp     cx, 3Fh ; '?'
0x1800524b7  jnz     loc_18005284D
0x1800524bd  cmp     word ptr [rax+rbx+4], 3Fh ; '?'
0x1800524c3  jnz     loc_1800526B6
0x1800524c9  cmp     word ptr [rax+rbx+6], 5Ch ; '\'
0x1800524cf  jnz     loc_1800526B6
0x1800524d5  cmp     word ptr [rax+rbx+8], 56h ; 'V'
0x1800524db  jnz     loc_1800526B6
0x1800524e1  cmp     word ptr [rax+rbx+0Ah], 6Fh ; 'o'
0x1800524e7  jnz     loc_1800526B6
0x1800524ed  cmp     word ptr [rax+rbx+0Ch], 6Ch ; 'l'
0x1800524f3  jnz     loc_1800526B6
0x1800524f9  cmp     word ptr [rax+rbx+0Eh], 75h ; 'u'
0x1800524ff  jnz     loc_1800526B6
0x180052505  cmp     word ptr [rax+rbx+10h], 6Dh ; 'm'
0x18005250b  jnz     loc_1800526B6
0x180052511  cmp     word ptr [rax+rbx+12h], 65h ; 'e'
0x180052517  jnz     loc_1800526B6
0x18005251d  cmp     word ptr [rax+rbx+14h], 7Bh ; '{'
0x180052523  jnz     loc_1800526B6
0x180052529  cmp     word ptr [rax+rbx+26h], 2Dh ; '-'
0x18005252f  jnz     loc_1800526B6
0x180052535  cmp     word ptr [rax+rbx+30h], 2Dh ; '-'
0x18005253b  jnz     loc_1800526B6
0x180052541  cmp     word ptr [rax+rbx+3Ah], 2Dh ; '-'
0x180052547  jnz     loc_1800526B6
0x18005254d  cmp     word ptr [rax+rbx+44h], 2Dh ; '-'
0x180052553  jnz     loc_1800526B6
0x180052559  cmp     word ptr [rax+rbx+5Eh], 7Dh ; '}'
0x18005255f  jnz     loc_1800526B6
0x180052565  cmp     r8w, 60h ; '`'
0x18005256a  jnz     loc_1800526B6
0x180052570  cmp     cx, 3Fh ; '?'
0x180052574  jnz     loc_1800526B6
0x18005257a  mov     rcx, r15
0x18005257d  xor     edx, edx; Flags
0x18005257f  add     rcx, rcx
0x180052582  mov     r8, rbx; P
0x180052585  cmp     rcx, 64h ; 'd'
0x180052589  jb      loc_18005285C
0x18005258f  movups  xmm0, xmmword ptr [rax+rbx]
0x180052593  mov     ecx, 5Ch ; '\'
0x180052598  movups  xmmword ptr [r14], xmm0
0x18005259c  movups  xmm1, xmmword ptr [rax+rbx+10h]
0x1800525a1  movups  xmmword ptr [r14+10h], xmm1
0x1800525a6  movups  xmm0, xmmword ptr [rax+rbx+20h]
0x1800525ab  movups  xmmword ptr [r14+20h], xmm0
0x1800525b0  movups  xmm1, xmmword ptr [rax+rbx+30h]
0x1800525b5  movups  xmmword ptr [r14+30h], xmm1
0x1800525ba  movups  xmm0, xmmword ptr [rax+rbx+40h]
0x1800525bf  movups  xmmword ptr [r14+40h], xmm0
0x1800525c4  movups  xmm1, xmmword ptr [rax+rbx+50h]
0x1800525c9  movups  xmmword ptr [r14+50h], xmm1
0x1800525ce  mov     [r14+2], cx
0x1800525d3  mov     [r14+60h], ecx
0x1800525d7  mov     rcx, gs:60h
0x1800525e0  mov     rcx, [rcx+30h]; HeapHandle
0x1800525e4  call    cs:__imp_RtlFreeHeap
0x1800525eb  nop     dword ptr [rax+rax+00h]
0x1800525f0  mov     eax, 1
0x1800525f5  mov     rsi, [rsp+300h+arg_18]
0x1800525fd  mov     rdi, [rsp+300h+var_20]
0x180052605  mov     rbx, [rsp+300h+arg_10]
0x18005260d  mov     rcx, [rbp+200h+var_30]
0x180052614  xor     rcx, rsp; StackCookie
0x180052617  call    __security_check_cookie
0x18005261c  add     rsp, 2E8h
0x180052623  pop     r15
0x180052625  pop     r14
0x180052627  pop     r12
0x180052629  pop     rbp
0x18005262a  retn
0x18005262c  mov     ecx, gs:68h
0x180052634  cmp     ecx, 0EAh
0x18005263a  jnz     loc_18005244C
0x180052640  mov     rcx, gs:60h
0x180052649  mov     r8, rbx; P
0x18005264c  mov     esi, [rbx]
0x18005264e  xor     edx, edx; Flags
0x180052650  mov     rcx, [rcx+30h]; HeapHandle
0x180052654  call    cs:__imp_RtlFreeHeap
0x18005265b  nop     dword ptr [rax+rax+00h]
0x180052660  mov     rcx, gs:60h
0x180052669  mov     r8d, esi; Size
0x18005266c  mov     edx, cs:KernelBaseGlobalData; Flags
0x180052672  mov     rcx, [rcx+30h]; HeapHandle
0x180052676  call    cs:__imp_RtlAllocateHeap
0x18005267d  nop     dword ptr [rax+rax+00h]
0x180052682  mov     rcx, [rsp+300h+FileHandle]; hObject
0x180052687  mov     rbx, rax
0x18005268a  test    rax, rax
0x18005268d  jz      loc_180052832
0x180052693  mov     [rsp+300h+lpOverlapped], r12
  ... truncated ...
```
