# QueryDosDeviceW

- ea: `0x1800b9940`
- end: `0x1800ba26e`
- name: `QueryDosDeviceW`
- size: `2350`
- prototype: `DWORD __stdcall(LPCWSTR lpDeviceName, LPWSTR lpTargetPath, DWORD ucchMax)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007fdc0`

## callees

- `0x18004b9d0`
- `0x1800b9940`
- `0x1800ba274`
- `0x180194eb9`
- `0x180194ee9`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800b99b7`
- `ntdll!RtlInitUnicodeString` at `0x1800b9a4c`
- `ntdll!RtlInitUnicodeString` at `0x1800b9e2a`
- `ntdll!RtlInitUnicodeString` at `0x1800b99b7`
- `ntdll!RtlInitUnicodeString` at `0x1800b9a4c`
- `ntdll!RtlInitUnicodeString` at `0x1800b9e2a`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1800b9aac`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1800b9aac`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800b9b1f`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800b9b1f`
- `ntdll!NtClose` at `0x1800b9b39`
- `ntdll!NtClose` at `0x1800b9fad`
- `ntdll!NtClose` at `0x1800ba205`
- `ntdll!NtClose` at `0x180197102`
- `ntdll!NtClose` at `0x1800b9b39`
- `ntdll!NtClose` at `0x1800b9fad`
- `ntdll!NtClose` at `0x1800ba205`
- `ntdll!NtClose` at `0x180197102`
- `ntdll!RtlFreeHeap` at `0x1800b9f59`
- `ntdll!RtlFreeHeap` at `0x1800ba150`
- `ntdll!RtlFreeHeap` at `0x1800ba255`
- `ntdll!RtlFreeHeap` at `0x180197127`
- `ntdll!RtlFreeHeap` at `0x1800b9f59`
- `ntdll!RtlFreeHeap` at `0x1800ba150`
- `ntdll!RtlFreeHeap` at `0x1800ba255`
- `ntdll!RtlFreeHeap` at `0x180197127`
- `ntdll!NtOpenDirectoryObject` at `0x1800b9a0f`
- `ntdll!NtOpenDirectoryObject` at `0x1800b9e86`
- `ntdll!NtOpenDirectoryObject` at `0x1800b9a0f`
- `ntdll!NtOpenDirectoryObject` at `0x1800b9e86`
- `ntdll!NtQueryDirectoryObject` at `0x1800b9f22`
- `ntdll!NtQueryDirectoryObject` at `0x1800ba11d`
- `ntdll!NtQueryDirectoryObject` at `0x1800b9f22`
- `ntdll!NtQueryDirectoryObject` at `0x1800ba11d`
- `ntdll!RtlCompareMemory` at `0x1800b9bc4`
- `ntdll!RtlCompareMemory` at `0x1800b9d31`
- `ntdll!RtlCompareMemory` at `0x1800b9bc4`
- `ntdll!RtlCompareMemory` at `0x1800b9d31`
- `ntdll!RtlAllocateHeap` at `0x1800b9ede`
- `ntdll!RtlAllocateHeap` at `0x1800ba0d7`
- `ntdll!RtlAllocateHeap` at `0x1800b9ede`
- `ntdll!RtlAllocateHeap` at `0x1800ba0d7`

## string_xrefs

- `0x1800b9bda`: `SymbolicLink`
- `0x1800b9d47`: `SymbolicLink`

## pseudocode

```c
DWORD __stdcall QueryDosDeviceW(LPCWSTR lpDeviceName, LPWSTR lpTargetPath, DWORD ucchMax)
{
  unsigned __int16 *Heap; // r14
  NTSTATUS v7; // eax
  NTSTATUS v8; // esi
  DWORD v9; // edi
  __int64 v10; // rdi
  unsigned __int16 *v11; // rbx
  size_t v12; // r8
  int v13; // edx
  WCHAR *v14; // rcx
  DWORD v15; // ebx
  int i; // eax
  NTSTATUS v17; // eax
  ULONG Size; // [rsp+48h] [rbp-F0h]
  ULONG DataWritten; // [rsp+50h] [rbp-E8h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-E0h] BYREF
  int v22; // [rsp+60h] [rbp-D8h]
  unsigned __int16 *v23; // [rsp+68h] [rbp-D0h]
  ULONG Context; // [rsp+70h] [rbp-C8h] BYREF
  unsigned __int16 *v25; // [rsp+78h] [rbp-C0h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-B8h] BYREF
  HANDLE SymbolicLinkHandle; // [rsp+98h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-98h] BYREF
  size_t v29; // [rsp+D0h] [rbp-68h]
  LPWSTR v30; // [rsp+D8h] [rbp-60h]
  __int128 Source1; // [rsp+E8h] [rbp-50h] BYREF
  __int128 v32; // [rsp+F8h] [rbp-40h]
  int v33; // [rsp+158h] [rbp+20h]

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  Heap = 0;
  FileHandle = 0;
  SymbolicLinkHandle = 0;
  Context = 0;
  DataWritten = 0;
  Source1 = 0;
  v32 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\??");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenDirectoryObject(&FileHandle, 1u, &ObjectAttributes);
  v8 = v7;
  if ( v7 < 0 )
  {
    BaseSetLastNTError((unsigned int)v7);
    return 0;
  }
  v30 = lpTargetPath;
  v9 = 0;
  v23 = 0;
  if ( !lpDeviceName )
  {
    if ( *(_BYTE *)(BaseStaticServerData + 2508) == 1 )
      v8 = IsGlobalDeviceMap(FileHandle);
    v22 = 0;
    Source1 = 0;
    v32 = 0;
    if ( ucchMax > 0x7FFFFFFF )
    {
      Size = -1;
      v15 = -1;
    }
    else
    {
      Size = 2 * ucchMax;
      v15 = 2 * ucchMax;
    }
    for ( i = 0; ; LOWORD(i) = v33 + 1 )
    {
      v33 = i;
      Heap = 0;
      v23 = 0;
      if ( (unsigned __int16)i >= 3u )
        goto LABEL_24;
      Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v15);
      v23 = Heap;
      if ( !Heap )
      {
        v8 = -1073741670;
        goto LABEL_52;
      }
      v17 = NtQueryDirectoryObject(FileHandle, Heap, Size, 0, 1u, &Context, &DataWritten);
      v8 = v17;
      if ( v17 < 0 )
        break;
      if ( v17 != 261 )
      {
        v11 = Heap;
        v25 = Heap;
        while ( RtlCompareMemory(&Source1, v11, 0x20u) != 32 )
        {
          if ( !wcscmp_0(*((const wchar_t **)v11 + 3), L"SymbolicLink") )
          {
            if ( v9 > ucchMax )
              goto LABEL_14;
            v12 = *v11;
            v29 = v12 >> 1;
            if ( (unsigned int)(v12 >> 1) > ucchMax - v9 || ucchMax - v9 - (unsigned int)(v12 >> 1) < 2 )
              goto LABEL_14;
            memcpy_0(lpTargetPath, *((const void **)v11 + 1), v12);
            v13 = v29;
            v14 = &lpTargetPath[(unsigned int)v29];
            *v14 = 0;
            lpTargetPath = v14 + 1;
            v9 += v13 + 1;
            ++v22;
          }
          v11 += 16;
          v25 = v11;
        }
LABEL_24:
        if ( v8 == 261 )
          goto LABEL_14;
        goto LABEL_25;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      Heap = 0;
      v23 = 0;
      if ( v15 == -1 )
        goto LABEL_24;
      if ( ~v15 < v15 )
      {
        Size = -1;
        v15 = -1;
      }
      else
      {
        Size = 2 * v15;
        v15 *= 2;
      }
      HIWORD(i) = HIWORD(v33);
    }
    if ( v17 != -2147483622 )
      goto LABEL_52;
    v8 = 0;
LABEL_25:
    if ( *(_BYTE *)(BaseStaticServerData + 2508) == 1 && v8 < 0 || v8 < 0 )
      goto LABEL_52;
    if ( !v9 )
    {
      if ( !ucchMax )
        goto LABEL_14;
      *lpTargetPath++ = 0;
      v9 = 1;
    }
    if ( v9 < ucchMax )
    {
      *lpTargetPath = 0;
      ++v9;
      goto LABEL_52;
    }
    goto LABEL_14;
  }
  RtlInitUnicodeString(&DestinationString, lpDeviceName);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = FileHandle;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
  if ( v8 < 0 )
    goto LABEL_52;
  DestinationString.Buffer = lpTargetPath;
  DestinationString.Length = 0;
  if ( ucchMax > 0x7FFFFFFF || 2 * ucchMax > 0xFFFF )
    DestinationString.MaximumLength = -1;
  else
    DestinationString.MaximumLength = 2 * ucchMax;
  DataWritten = 0;
  v8 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &DestinationString, &DataWritten);
  NtClose(SymbolicLinkHandle);
  if ( v8 < 0 )
    goto LABEL_52;
  v10 = DataWritten >> 1;
  if ( !(DataWritten >> 1) || lpTargetPath[(unsigned int)(v10 - 1)] )
  {
    if ( (unsigned int)v10 >= ucchMax )
      goto LABEL_13;
    lpTargetPath[v10] = 0;
    v10 = (unsigned int)(v10 + 1);
  }
  if ( (unsigned int)v10 >= ucchMax )
  {
LABEL_13:
    v9 = 0;
LABEL_14:
    v8 = -1073741789;
    goto LABEL_52;
  }
  lpTargetPath[v10] = 0;
  v9 = v10 + 1;
LABEL_52:
  if ( FileHandle )
    NtClose(FileHandle);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v8 < 0 )
  {
    v9 = 0;
    BaseSetLastNTError((unsigned int)v8);
  }
  return v9;
}

```

## disassembly

```asm
0x1800b9940  mov     r11, rsp
0x1800b9943  mov     [r11+8], rbx
0x1800b9947  mov     [r11+18h], rsi
0x1800b994b  push    rdi
0x1800b994c  push    r12
0x1800b994e  push    r13
0x1800b9950  push    r14
0x1800b9952  push    r15
0x1800b9954  sub     rsp, 110h
0x1800b995b  mov     r12d, r8d
0x1800b995e  mov     r15, rdx
0x1800b9961  mov     rbx, rcx
0x1800b9964  xorps   xmm0, xmm0
0x1800b9967  movups  xmmword ptr [rsp+138h+DestinationString.Length], xmm0
0x1800b996f  xor     eax, eax
0x1800b9971  movups  xmmword ptr [rsp+138h+ObjectAttributes.Length], xmm0
0x1800b9979  movups  xmmword ptr [rsp+138h+ObjectAttributes.ObjectName], xmm0
0x1800b9981  movups  xmmword ptr [r11-7Ch], xmm0
0x1800b9986  xor     r14d, r14d
0x1800b9989  mov     [rsp+138h+FileHandle], r14
0x1800b998e  mov     [r11-0A0h], r14
0x1800b9995  mov     [rsp+138h+var_C8], r14d
0x1800b999a  mov     [rsp+138h+DataWritten], r14d
0x1800b999f  movups  xmmword ptr [r11-50h], xmm0
0x1800b99a4  movups  xmmword ptr [r11-40h], xmm0
0x1800b99a9  lea     rdx, asc_1802A2A08; "\\??"
0x1800b99b0  lea     rcx, [r11-0B8h]; DestinationString
0x1800b99b7  call    cs:__imp_RtlInitUnicodeString
0x1800b99be  nop     dword ptr [rax+rax+00h]
0x1800b99c3  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x1800b99ce  mov     [rsp+138h+ObjectAttributes.RootDirectory], r14
0x1800b99d6  mov     [rsp+138h+ObjectAttributes.Attributes], 40h ; '@'
0x1800b99e1  lea     rax, [rsp+138h+DestinationString]
0x1800b99e9  mov     [rsp+138h+ObjectAttributes.ObjectName], rax
0x1800b99f1  xorps   xmm0, xmm0
0x1800b99f4  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b99fd  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x1800b9a05  mov     edx, 1; DesiredAccess
0x1800b9a0a  lea     rcx, [rsp+138h+FileHandle]; FileHandle
0x1800b9a0f  call    cs:__imp_NtOpenDirectoryObject
0x1800b9a16  nop     dword ptr [rax+rax+00h]
0x1800b9a1b  mov     esi, eax
0x1800b9a1d  test    eax, eax
0x1800b9a1f  js      loc_1800BA263
0x1800b9a25  xor     r13b, r13b
0x1800b9a28  mov     [rsp+138h+var_60], r15
0x1800b9a30  mov     edi, r14d
0x1800b9a33  mov     [rsp+138h+var_D0], r14
0x1800b9a38  test    rbx, rbx
0x1800b9a3b  jz      loc_1800BA02B
0x1800b9a41  mov     rdx, rbx; SourceString
0x1800b9a44  lea     rcx, [rsp+138h+DestinationString]; DestinationString
0x1800b9a4c  call    cs:__imp_RtlInitUnicodeString
0x1800b9a53  nop     dword ptr [rax+rax+00h]
0x1800b9a58  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x1800b9a63  mov     rax, [rsp+138h+FileHandle]
0x1800b9a68  mov     [rsp+138h+ObjectAttributes.RootDirectory], rax
0x1800b9a70  mov     [rsp+138h+ObjectAttributes.Attributes], 40h ; '@'
0x1800b9a7b  lea     rax, [rsp+138h+DestinationString]
0x1800b9a83  mov     [rsp+138h+ObjectAttributes.ObjectName], rax
0x1800b9a8b  xorps   xmm0, xmm0
0x1800b9a8e  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b9a97  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x1800b9a9f  mov     edx, 1; DesiredAccess
0x1800b9aa4  lea     rcx, [rsp+138h+SymbolicLinkHandle]; SymbolicLinkHandle
0x1800b9aac  call    cs:__imp_NtOpenSymbolicLinkObject
0x1800b9ab3  nop     dword ptr [rax+rax+00h]
0x1800b9ab8  mov     esi, eax
0x1800b9aba  mov     [rsp+138h+var_F8], eax
0x1800b9abe  test    eax, eax
0x1800b9ac0  js      loc_1800BA1FB
0x1800b9ac6  mov     [rsp+138h+DestinationString.Buffer], r15
0x1800b9ace  xor     eax, eax
0x1800b9ad0  mov     [rsp+138h+DestinationString.Length], ax
0x1800b9ad8  mov     ecx, 0FFFFh
0x1800b9add  cmp     r12d, 7FFFFFFFh
0x1800b9ae4  ja      loc_1800BA1C0
0x1800b9aea  lea     eax, [r12+r12]
0x1800b9aee  mov     dword ptr [rsp+138h+Size], eax
0x1800b9af2  cmp     eax, ecx
0x1800b9af4  ja      loc_1800BA1C8
0x1800b9afa  mov     [rsp+138h+DestinationString.MaximumLength], ax
0x1800b9b02  mov     [rsp+138h+DataWritten], 0
0x1800b9b0a  lea     r8, [rsp+138h+DataWritten]; DataWritten
0x1800b9b0f  lea     rdx, [rsp+138h+DestinationString]; LinkTarget
0x1800b9b17  mov     rcx, [rsp+138h+SymbolicLinkHandle]; SymLinkObjHandle
0x1800b9b1f  call    cs:__imp_NtQuerySymbolicLinkObject
0x1800b9b26  nop     dword ptr [rax+rax+00h]
0x1800b9b2b  mov     esi, eax
0x1800b9b2d  mov     [rsp+138h+var_F8], eax
0x1800b9b31  mov     rcx, [rsp+138h+SymbolicLinkHandle]; Handle
0x1800b9b39  call    cs:__imp_NtClose
0x1800b9b40  nop     dword ptr [rax+rax+00h]
0x1800b9b45  test    esi, esi
0x1800b9b47  js      loc_1800BA1FB
0x1800b9b4d  mov     edi, [rsp+138h+DataWritten]
0x1800b9b51  shr     edi, 1
0x1800b9b53  mov     dword ptr [rsp+138h+Size+4], edi
0x1800b9b57  jz      short loc_1800B9B7B
0x1800b9b59  lea     eax, [rdi-1]
0x1800b9b5c  cmp     word ptr [r15+rax*2], 0
0x1800b9b62  jnz     short loc_1800B9B7B
0x1800b9b64  cmp     edi, r12d
0x1800b9b67  jnb     short loc_1800B9B80
0x1800b9b69  xor     eax, eax
0x1800b9b6b  mov     [r15+rdi*2], ax
0x1800b9b70  inc     edi
0x1800b9b72  mov     dword ptr [rsp+138h+Size+4], edi
0x1800b9b76  jmp     loc_1800BA1FB
0x1800b9b7b  cmp     edi, r12d
0x1800b9b7e  jb      short loc_1800B9B94
0x1800b9b80  xor     edi, edi
0x1800b9b82  mov     dword ptr [rsp+138h+Size+4], edi
0x1800b9b86  mov     esi, 0C0000023h
0x1800b9b8b  mov     [rsp+138h+var_F8], esi
0x1800b9b8f  jmp     loc_1800BA1FB
0x1800b9b94  xor     eax, eax
0x1800b9b96  mov     [r15+rdi*2], ax
0x1800b9b9b  inc     edi
0x1800b9b9d  mov     dword ptr [rsp+138h+Size+4], edi
0x1800b9ba1  jmp     short loc_1800B9B64
0x1800b9ba3  mov     r13, r14
0x1800b9ba6  mov     [rsp+138h+var_C0], r14
0x1800b9bab  mov     rbx, [rsp+138h+var_60]
0x1800b9bb3  mov     r8d, 20h ; ' '; Length
0x1800b9bb9  mov     rdx, r13; Source2
0x1800b9bbc  lea     rcx, [rsp+138h+Source1]; Source1
0x1800b9bc4  call    cs:__imp_RtlCompareMemory
0x1800b9bcb  nop     dword ptr [rax+rax+00h]
0x1800b9bd0  cmp     rax, 20h ; ' '
0x1800b9bd4  jz      loc_1800B9FC7
0x1800b9bda  lea     rdx, aSymboliclink; "SymbolicLink"
0x1800b9be1  mov     rcx, [r13+18h]; String1
0x1800b9be5  call    wcscmp_0
0x1800b9bea  test    eax, eax
0x1800b9bec  jnz     loc_1800B9D05
0x1800b9bf2  mov     rcx, rbx
0x1800b9bf5  mov     [rsp+138h+var_58], rbx
0x1800b9bfd  mov     r11, [r13+8]
0x1800b9c01  xor     r10d, r10d
0x1800b9c04  mov     [rsp+138h+var_A8], r10d
0x1800b9c0c  test    r11, r11
0x1800b9c0f  jz      loc_1800B9D05
0x1800b9c15  test    rbx, rbx
0x1800b9c18  jz      loc_1800B9D05
0x1800b9c1e  mov     [rsp+138h+var_F4], r10b
0x1800b9c23  cmp     r10d, [rsp+138h+var_D8]
0x1800b9c28  jnb     short loc_1800B9C90
0x1800b9c2a  mov     rax, r11
0x1800b9c2d  mov     r9, rcx
0x1800b9c30  sub     r9, r11
0x1800b9c33  nop     dword ptr [rax+00h]
0x1800b9c37  nop     word ptr [rax+rax+00000000h]
0x1800b9c40  movzx   r8d, word ptr [rax]
0x1800b9c44  movzx   edx, word ptr [rax+r9]
0x1800b9c49  sub     r8d, edx
0x1800b9c4c  jnz     short loc_1800B9C56
0x1800b9c4e  add     rax, 2
0x1800b9c52  test    edx, edx
0x1800b9c54  jnz     short loc_1800B9C40
0x1800b9c56  test    r8d, r8d
0x1800b9c59  jz      short loc_1800B9C88
0x1800b9c5b  inc     r10d
0x1800b9c5e  mov     [rsp+138h+var_A8], r10d
0x1800b9c66  nop     word ptr [rax+rax+00000000h]
0x1800b9c70  movzx   eax, word ptr [rcx]
0x1800b9c73  add     rcx, 2
0x1800b9c77  mov     [rsp+138h+var_58], rcx
0x1800b9c7f  test    ax, ax
0x1800b9c82  jz      short loc_1800B9C86
0x1800b9c84  jmp     short loc_1800B9C70
0x1800b9c86  jmp     short loc_1800B9C23
0x1800b9c88  lea     rax, [rsp+138h+var_F4]
0x1800b9c8d  mov     byte ptr [rax], 1
0x1800b9c90  cmp     [rsp+138h+var_F4], 0
0x1800b9c95  jnz     short loc_1800B9D05
0x1800b9c97  cmp     edi, r12d
0x1800b9c9a  ja      loc_1800B9B86
0x1800b9ca0  movzx   r8d, word ptr [r13+0]; Size
0x1800b9ca5  mov     r13d, r8d
0x1800b9ca8  shr     r13, 1
0x1800b9cab  mov     eax, r12d
0x1800b9cae  sub     eax, edi
0x1800b9cb0  cmp     r13d, eax
0x1800b9cb3  ja      loc_1800B9B86
0x1800b9cb9  sub     eax, r13d
0x1800b9cbc  cmp     eax, 2
0x1800b9cbf  jb      loc_1800B9B86
0x1800b9cc5  mov     rdx, [rsp+138h+var_C0]
0x1800b9cca  mov     rdx, [rdx+8]; Src
0x1800b9cce  mov     rcx, r15; void *
0x1800b9cd1  call    memcpy_0
0x1800b9cd6  mov     eax, r13d
0x1800b9cd9  lea     rcx, [r15+rax*2]
0x1800b9cdd  mov     [rsp+138h+arg_8], rcx
0x1800b9ce5  xor     eax, eax
0x1800b9ce7  mov     [rcx], ax
0x1800b9cea  lea     r15, [rcx+2]
0x1800b9cee  mov     [rsp+138h+arg_8], r15
0x1800b9cf6  inc     r13d
0x1800b9cf9  add     edi, r13d
0x1800b9cfc  mov     dword ptr [rsp+138h+Size+4], edi
0x1800b9d00  mov     r13, [rsp+138h+var_C0]
0x1800b9d05  add     r13, 20h ; ' '
0x1800b9d09  mov     [rsp+138h+var_C0], r13
0x1800b9d0e  jmp     loc_1800B9BB3
0x1800b9d13  mov     rbx, r14
0x1800b9d16  mov     [rsp+138h+var_C0], rbx
0x1800b9d1b  nop     dword ptr [rax+rax+00h]
0x1800b9d20  mov     r8d, 20h ; ' '; Length
0x1800b9d26  mov     rdx, rbx; Source2
0x1800b9d29  lea     rcx, [rsp+138h+Source1]; Source1
0x1800b9d31  call    cs:__imp_RtlCompareMemory
0x1800b9d38  nop     dword ptr [rax+rax+00h]
0x1800b9d3d  cmp     rax, 20h ; ' '
0x1800b9d41  jz      loc_1800B9DDB
0x1800b9d47  lea     rdx, aSymboliclink; "SymbolicLink"
0x1800b9d4e  mov     rcx, [rbx+18h]; String1
0x1800b9d52  call    wcscmp_0
0x1800b9d57  test    eax, eax
0x1800b9d59  jnz     short loc_1800B9DCD
0x1800b9d5b  cmp     edi, r12d
0x1800b9d5e  ja      loc_1800B9B86
0x1800b9d64  movzx   r8d, word ptr [rbx]; Size
0x1800b9d68  mov     ecx, r8d
0x1800b9d6b  shr     rcx, 1
0x1800b9d6e  mov     [rsp+138h+var_68], rcx
0x1800b9d76  mov     eax, r12d
0x1800b9d79  sub     eax, edi
0x1800b9d7b  cmp     ecx, eax
0x1800b9d7d  ja      loc_1800B9B86
0x1800b9d83  sub     eax, ecx
0x1800b9d85  cmp     eax, 2
0x1800b9d88  jb      loc_1800B9B86
0x1800b9d8e  mov     rdx, [rbx+8]; Src
0x1800b9d92  mov     rcx, r15; void *
0x1800b9d95  call    memcpy_0
0x1800b9d9a  mov     rdx, [rsp+138h+var_68]
0x1800b9da2  mov     eax, edx
0x1800b9da4  lea     rcx, [r15+rax*2]
0x1800b9da8  mov     [rsp+138h+arg_8], rcx
0x1800b9db0  xor     eax, eax
0x1800b9db2  mov     [rcx], ax
0x1800b9db5  lea     r15, [rcx+2]
0x1800b9db9  mov     [rsp+138h+arg_8], r15
0x1800b9dc1  inc     edi
0x1800b9dc3  add     edi, edx
0x1800b9dc5  mov     dword ptr [rsp+138h+Size+4], edi
0x1800b9dc9  inc     [rsp+138h+var_D8]
0x1800b9dcd  add     rbx, 20h ; ' '
0x1800b9dd1  mov     [rsp+138h+var_C0], rbx
0x1800b9dd6  jmp     loc_1800B9D20
0x1800b9ddb  cmp     esi, 105h
0x1800b9de1  jz      loc_1800B9B86
0x1800b9de7  mov     rax, cs:BaseStaticServerData
0x1800b9dee  cmp     byte ptr [rax+9CCh], 1
0x1800b9df5  jnz     loc_1800B9FD3
0x1800b9dfb  test    esi, esi
0x1800b9dfd  js      loc_1800BA1FB
0x1800b9e03  cmp     r13b, 1
0x1800b9e07  jnz     loc_1800B9FD3
0x1800b9e0d  mov     rcx, [rsp+138h+FileHandle]; Handle
0x1800b9e12  test    rcx, rcx
0x1800b9e15  jnz     loc_1800B9FAD
0x1800b9e1b  lea     rdx, aGlobal_0; "\\GLOBAL??"
0x1800b9e22  lea     rcx, [rsp+138h+DestinationString]; DestinationString
0x1800b9e2a  call    cs:__imp_RtlInitUnicodeString
0x1800b9e31  nop     dword ptr [rax+rax+00h]
0x1800b9e36  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x1800b9e41  mov     [rsp+138h+ObjectAttributes.RootDirectory], 0
0x1800b9e4d  mov     [rsp+138h+ObjectAttributes.Attributes], 40h ; '@'
0x1800b9e58  lea     rax, [rsp+138h+DestinationString]
0x1800b9e60  mov     [rsp+138h+ObjectAttributes.ObjectName], rax
0x1800b9e68  xorps   xmm0, xmm0
0x1800b9e6b  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b9e74  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x1800b9e7c  mov     edx, 1; DesiredAccess
0x1800b9e81  lea     rcx, [rsp+138h+FileHandle]; FileHandle
0x1800b9e86  call    cs:__imp_NtOpenDirectoryObject
0x1800b9e8d  nop     dword ptr [rax+rax+00h]
0x1800b9e92  mov     esi, eax
0x1800b9e94  mov     [rsp+138h+var_F8], eax
0x1800b9e98  test    eax, eax
0x1800b9e9a  js      loc_1800B9F95
0x1800b9ea0  mov     r13d, [rsp+138h+arg_18]
0x1800b9ea8  nop     dword ptr [rax+rax+00000000h]
0x1800b9eb0  cmp     r13w, 3
0x1800b9eb5  jnb     loc_1800B9FC7
0x1800b9ebb  test    r14, r14
0x1800b9ebe  jnz     loc_1800B9F8C
0x1800b9ec4  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800b9eca  mov     ebx, dword ptr [rsp+138h+Size]
0x1800b9ece  mov     r8d, ebx; Size
0x1800b9ed1  mov     rcx, gs:60h
0x1800b9eda  mov     rcx, [rcx+30h]; HeapHandle
0x1800b9ede  call    cs:__imp_RtlAllocateHeap
0x1800b9ee5  nop     dword ptr [rax+rax+00h]
0x1800b9eea  mov     r14, rax
0x1800b9eed  mov     [rsp+138h+var_D0], rax
0x1800b9ef2  test    rax, rax
  ... truncated ...
```
