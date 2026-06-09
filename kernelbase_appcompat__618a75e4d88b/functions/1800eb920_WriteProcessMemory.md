# WriteProcessMemory

- ea: `0x1800eb920`
- end: `0x1800ebca4`
- name: `WriteProcessMemory`
- size: `900`
- prototype: `BOOL __stdcall(HANDLE hProcess, LPVOID lpBaseAddress, LPCVOID lpBuffer, SIZE_T nSize, SIZE_T *lpNumberOfBytesWritten)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18008c8cc`

## callees

- `0x18004b9d0`
- `0x1800eb920`

## import_xrefs

- `ntdll!NtClose` at `0x1800ebc93`
- `ntdll!NtClose` at `0x1800ebc93`
- `ntdll!NtQueryVirtualMemory` at `0x1800eb9d6`
- `ntdll!NtQueryVirtualMemory` at `0x1800eb9d6`
- `ntdll!NtUnmapViewOfSection` at `0x1800ebc83`
- `ntdll!NtUnmapViewOfSection` at `0x1800ebc83`
- `ntdll!RtlOpenCrossProcessEmulatorWorkConnection` at `0x1800eb999`
- `ntdll!RtlOpenCrossProcessEmulatorWorkConnection` at `0x1800eb999`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800ebad2`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800ebbbf`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800ebbee`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800ebc27`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800ebc53`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800ebad2`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800ebbbf`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800ebbee`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800ebc27`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800ebc53`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800ebaed`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800ebbda`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800ebc09`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800ebc3f`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800ebc6e`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800ebaed`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800ebbda`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800ebc09`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800ebc3f`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800ebc6e`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a13b7`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a1407`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a144b`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a1498`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a14e8`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a13b7`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a1407`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a144b`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a1498`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a14e8`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a13d3`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a1423`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a1467`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a14b4`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a1504`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a13d3`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a1423`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a1467`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a14b4`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a1504`
- `ntdll!NtProtectVirtualMemory` at `0x1800ebaba`
- `ntdll!NtProtectVirtualMemory` at `0x1800ebb7b`
- `ntdll!NtProtectVirtualMemory` at `0x1800ebaba`
- `ntdll!NtProtectVirtualMemory` at `0x1800ebb7b`
- `ntdll!NtWriteVirtualMemory` at `0x1800eba13`
- `ntdll!NtWriteVirtualMemory` at `0x1800eba13`

## pseudocode

```c
BOOL __stdcall WriteProcessMemory(
        HANDLE hProcess,
        LPVOID lpBaseAddress,
        LPCVOID lpBuffer,
        SIZE_T nSize,
        SIZE_T *lpNumberOfBytesWritten)
{
  PVOID v7; // rdi
  char *v8; // rsi
  NTSTATUS v9; // ebx
  char v10; // r15
  ULONG v12; // r14d
  __int64 v13; // rax
  int v14; // eax
  ULONG v15; // r14d
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // [rsp+38h] [rbp-51h] BYREF
  SIZE_T NumberOfBytesToProtect; // [rsp+40h] [rbp-49h] BYREF
  PVOID v22; // [rsp+48h] [rbp-41h] BYREF
  ULONG OldAccessProtection; // [rsp+50h] [rbp-39h] BYREF
  PVOID BaseAddress; // [rsp+58h] [rbp-31h] BYREF
  ULONG_PTR NumberOfBytesWritten; // [rsp+60h] [rbp-29h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-21h] BYREF
  __int128 VirtualMemoryInformation; // [rsp+70h] [rbp-19h] BYREF
  __int128 v28; // [rsp+80h] [rbp-9h]
  __int128 v29; // [rsp+90h] [rbp+7h]

  OldAccessProtection = 0;
  BaseAddress = 0;
  NumberOfBytesToProtect = 0;
  NumberOfBytesWritten = 0;
  VirtualMemoryInformation = 0;
  v20 = 0;
  v28 = 0;
  Handle = 0;
  v29 = 0;
  v22 = 0;
  RtlOpenCrossProcessEmulatorWorkConnection(hProcess, &Handle, &v22);
  v7 = v22;
  if ( v22 )
    v8 = (char *)v22 + 8;
  else
    v8 = 0;
  v9 = NtQueryVirtualMemory(hProcess, lpBaseAddress, (MEMORY_INFORMATION_CLASS)8, &VirtualMemoryInformation, 0x30u, 0);
  if ( v9 < 0 )
  {
LABEL_10:
    if ( v22 )
    {
      NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v22);
      NtClose(Handle);
    }
    goto LABEL_12;
  }
  v10 = 0;
  if ( (BYTE4(v29) & 0xCC) != 0 )
    goto LABEL_5;
  if ( (BYTE4(v29) & 0x30) == 0 )
  {
LABEL_37:
    v9 = -1073741819;
    goto LABEL_10;
  }
  if ( DWORD2(v29) != 0x1000000 )
  {
    if ( DWORD2(v29) == 0x20000 )
    {
      v14 = 1610612800;
      goto LABEL_24;
    }
    goto LABEL_37;
  }
  v14 = 1610612864;
LABEL_24:
  v15 = v14 | DWORD1(v29) & 0xFFFFFFCF;
  BaseAddress = (PVOID)VirtualMemoryInformation;
  NumberOfBytesToProtect = ~((unsigned int)dword_1803AAE28 - 1LL)
                         & ((unsigned int)dword_1803AAE28
                          + ((unsigned __int64)lpBaseAddress & ((unsigned int)dword_1803AAE28 - 1LL))
                          + nSize
                          - 1);
  if ( NumberOfBytesToProtect > *((_QWORD *)&v28 + 1) )
    NumberOfBytesToProtect = *((_QWORD *)&v28 + 1);
  if ( v22 )
  {
    v16 = RtlWow64PopCrossProcessWorkFromFreeList(v7);
    if ( v16 )
    {
      *(_DWORD *)(v16 + 4) = 4;
      *(_QWORD *)(v16 + 8) = BaseAddress;
      *(_QWORD *)(v16 + 16) = NumberOfBytesToProtect;
      *(_DWORD *)(v16 + 24) = v15;
      RtlWow64PushCrossProcessWorkOntoWorkList(v8, v16, &v20);
      if ( v20 )
        RtlWow64PushCrossProcessWorkOntoFreeList(v7);
    }
    else
    {
      RtlWow64RequestCrossProcessHeavyFlush(v8);
    }
  }
  v9 = NtProtectVirtualMemory(hProcess, &BaseAddress, &NumberOfBytesToProtect, v15, &OldAccessProtection);
  if ( v22 )
  {
    v17 = RtlWow64PopCrossProcessWorkFromFreeList(v7);
    if ( v17 )
    {
      *(_DWORD *)(v17 + 4) = 5;
      *(_QWORD *)(v17 + 8) = BaseAddress;
      *(_QWORD *)(v17 + 16) = NumberOfBytesToProtect;
      *(_DWORD *)(v17 + 24) = v15;
      *(_DWORD *)(v17 + 28) = v9;
      RtlWow64PushCrossProcessWorkOntoWorkList(v8, v17, &v20);
      if ( v20 )
        RtlWow64PushCrossProcessWorkOntoFreeList(v7);
    }
    else
    {
      RtlWow64RequestCrossProcessHeavyFlush(v8);
    }
  }
  if ( v9 < 0 )
    goto LABEL_10;
  v10 = 1;
LABEL_5:
  v9 = NtWriteVirtualMemory(hProcess, lpBaseAddress, (PVOID)lpBuffer, nSize, &NumberOfBytesWritten);
  if ( lpNumberOfBytesWritten )
    *lpNumberOfBytesWritten = NumberOfBytesWritten;
  if ( v9 >= 0 && v22 )
  {
    v18 = RtlWow64PopCrossProcessWorkFromFreeList(v7);
    if ( v18 )
    {
      *(_DWORD *)(v18 + 4) = 6;
      *(_QWORD *)(v18 + 8) = lpBaseAddress;
      *(_QWORD *)(v18 + 16) = nSize;
      RtlWow64PushCrossProcessWorkOntoWorkList(v8, v18, &v20);
      if ( v20 )
        RtlWow64PushCrossProcessWorkOntoFreeList(v7);
    }
    else
    {
      RtlWow64RequestCrossProcessHeavyFlush(v8);
    }
  }
  if ( !v10 )
    goto LABEL_10;
  v12 = OldAccessProtection | 0x60000000;
  if ( (OldAccessProtection & 0xF0) == 0 )
    v12 = OldAccessProtection | 0x20000000;
  if ( v22 )
  {
    v19 = RtlWow64PopCrossProcessWorkFromFreeList(v7);
    if ( v19 )
    {
      *(_DWORD *)(v19 + 4) = 4;
      *(_QWORD *)(v19 + 8) = BaseAddress;
      *(_QWORD *)(v19 + 16) = NumberOfBytesToProtect;
      *(_DWORD *)(v19 + 24) = v12;
      RtlWow64PushCrossProcessWorkOntoWorkList(v8, v19, &v20);
      if ( v20 )
        RtlWow64PushCrossProcessWorkOntoFreeList(v7);
    }
    else
    {
      RtlWow64RequestCrossProcessHeavyFlush(v8);
    }
  }
  v9 = NtProtectVirtualMemory(hProcess, &BaseAddress, &NumberOfBytesToProtect, v12, &OldAccessProtection);
  if ( v22 )
  {
    v13 = RtlWow64PopCrossProcessWorkFromFreeList(v7);
    if ( v13 )
    {
      *(_DWORD *)(v13 + 4) = 5;
      *(_QWORD *)(v13 + 8) = BaseAddress;
      *(_QWORD *)(v13 + 16) = NumberOfBytesToProtect;
      *(_DWORD *)(v13 + 24) = v12;
      *(_DWORD *)(v13 + 28) = v9;
      RtlWow64PushCrossProcessWorkOntoWorkList(v8, v13, &v20);
      if ( v20 )
        RtlWow64PushCrossProcessWorkOntoFreeList(v7);
    }
    else
    {
      RtlWow64RequestCrossProcessHeavyFlush(v8);
    }
    goto LABEL_10;
  }
LABEL_12:
  if ( v9 >= 0 )
    return 1;
  BaseSetLastNTError((unsigned int)v9);
  return 0;
}

```

## disassembly

```asm
0x1800eb920  mov     rax, rsp
0x1800eb923  mov     [rax+8], rbx
0x1800eb927  mov     [rax+20h], r9
0x1800eb92b  mov     [rax+18h], r8
0x1800eb92f  push    rbp
0x1800eb930  push    rsi
0x1800eb931  push    rdi
0x1800eb932  push    r12
0x1800eb934  push    r13
0x1800eb936  push    r14
0x1800eb938  push    r15
0x1800eb93a  lea     rbp, [rax-57h]
0x1800eb93e  sub     rsp, 0A0h
0x1800eb945  xorps   xmm0, xmm0
0x1800eb948  mov     [rbp+4Fh+OldAccessProtection], 0
0x1800eb94f  mov     r13, rdx
0x1800eb952  mov     [rbp+4Fh+BaseAddress], 0
0x1800eb95a  lea     rdx, [rbp+4Fh+Handle]
0x1800eb95e  mov     [rbp+4Fh+NumberOfBytesToProtect], 0
0x1800eb966  lea     r8, [rbp+4Fh+var_90]
0x1800eb96a  mov     [rbp+4Fh+NumberOfBytesWritten], 0
0x1800eb972  movups  [rbp+4Fh+VirtualMemoryInformation], xmm0
0x1800eb976  mov     r12, rcx
0x1800eb979  mov     [rbp+4Fh+var_A0], 0
0x1800eb981  movups  [rbp+4Fh+var_58], xmm0
0x1800eb985  mov     [rbp+4Fh+Handle], 0
0x1800eb98d  movups  [rbp+4Fh+var_48], xmm0
0x1800eb991  mov     [rbp+4Fh+var_90], 0
0x1800eb999  call    cs:__imp_RtlOpenCrossProcessEmulatorWorkConnection
0x1800eb9a0  nop     dword ptr [rax+rax+00h]
0x1800eb9a5  mov     rdi, [rbp+4Fh+var_90]
0x1800eb9a9  test    rdi, rdi
0x1800eb9ac  jnz     loc_1800EBBA0
0x1800eb9b2  xor     esi, esi
0x1800eb9b4  mov     qword ptr [rsp+28h], 0; ResultLength
0x1800eb9bd  lea     r9, [rbp+4Fh+VirtualMemoryInformation]; VirtualMemoryInformation
0x1800eb9c1  mov     r8d, 8; VirtualMemoryInformationClass
0x1800eb9c7  mov     [rsp+0D0h+Length], 30h ; '0'; Length
0x1800eb9d0  mov     rdx, r13; Address
0x1800eb9d3  mov     rcx, r12; ProcessHandle
0x1800eb9d6  call    cs:__imp_NtQueryVirtualMemory
0x1800eb9dd  nop     dword ptr [rax+rax+00h]
0x1800eb9e2  mov     ebx, eax
0x1800eb9e4  test    eax, eax
0x1800eb9e6  js      short loc_1800EBA45
0x1800eb9e8  mov     r14d, dword ptr [rbp+4Fh+var_48+4]
0x1800eb9ec  xor     r15b, r15b
0x1800eb9ef  test    r14b, 0CCh
0x1800eb9f3  jz      loc_1800EBAFE
0x1800eb9f9  mov     r14, [rbp+4Fh+NumberOfBytesToWrite]
0x1800eb9fd  lea     rax, [rbp+4Fh+NumberOfBytesWritten]
0x1800eba01  mov     r8, [rbp+4Fh+Buffer]; Buffer
0x1800eba05  mov     r9, r14; NumberOfBytesToWrite
0x1800eba08  mov     rdx, r13; BaseAddress
0x1800eba0b  mov     [rsp+0D0h+Length], rax; NumberOfBytesWritten
0x1800eba10  mov     rcx, r12; ProcessHandle
0x1800eba13  call    cs:__imp_NtWriteVirtualMemory
0x1800eba1a  nop     dword ptr [rax+rax+00h]
0x1800eba1f  mov     rcx, [rbp+4Fh+lpNumberOfBytesWritten]
0x1800eba23  mov     ebx, eax
0x1800eba25  test    rcx, rcx
0x1800eba28  jz      short loc_1800EBA31
0x1800eba2a  mov     rax, [rbp+4Fh+NumberOfBytesWritten]
0x1800eba2e  mov     [rcx], rax
0x1800eba31  test    ebx, ebx
0x1800eba33  js      short loc_1800EBA40
0x1800eba35  cmp     [rbp+4Fh+var_90], 0
0x1800eba3a  jnz     loc_1800EBC24
0x1800eba40  test    r15b, r15b
0x1800eba43  jnz     short loc_1800EBA82
0x1800eba45  mov     rdx, [rbp+4Fh+var_90]; BaseAddress
0x1800eba49  test    rdx, rdx
0x1800eba4c  jnz     loc_1800EBC7F
0x1800eba52  test    ebx, ebx
0x1800eba54  js      short loc_1800EBA77
0x1800eba56  mov     eax, 1
0x1800eba5b  mov     rbx, [rsp+0D0h+arg_0]
0x1800eba63  add     rsp, 0A0h
0x1800eba6a  pop     r15
0x1800eba6c  pop     r14
0x1800eba6e  pop     r13
0x1800eba70  pop     r12
0x1800eba72  pop     rdi
0x1800eba73  pop     rsi
0x1800eba74  pop     rbp
0x1800eba75  retn
0x1800eba77  mov     ecx, ebx
0x1800eba79  call    BaseSetLastNTError
0x1800eba7e  xor     eax, eax
0x1800eba80  jmp     short loc_1800EBA5B
0x1800eba82  mov     ecx, [rbp+4Fh+OldAccessProtection]
0x1800eba85  bts     ecx, 1Dh
0x1800eba89  mov     r14d, ecx
0x1800eba8c  bts     r14d, 1Eh
0x1800eba91  test    cl, 0F0h
0x1800eba94  cmovz   r14d, ecx
0x1800eba98  cmp     [rbp+4Fh+var_90], 0
0x1800eba9d  jnz     loc_1800EBC50
0x1800ebaa3  lea     rax, [rbp+4Fh+OldAccessProtection]
0x1800ebaa7  mov     r9d, r14d; NewAccessProtection
0x1800ebaaa  lea     r8, [rbp+4Fh+NumberOfBytesToProtect]; NumberOfBytesToProtect
0x1800ebaae  mov     [rsp+0D0h+Length], rax; OldAccessProtection
0x1800ebab3  lea     rdx, [rbp+4Fh+BaseAddress]; BaseAddress
0x1800ebab7  mov     rcx, r12; ProcessHandle
0x1800ebaba  call    cs:__imp_NtProtectVirtualMemory
0x1800ebac1  nop     dword ptr [rax+rax+00h]
0x1800ebac6  cmp     [rbp+4Fh+var_90], 0
0x1800ebacb  mov     ebx, eax
0x1800ebacd  jz      short loc_1800EBA52
0x1800ebacf  mov     rcx, rdi
0x1800ebad2  call    cs:__imp_RtlWow64PopCrossProcessWorkFromFreeList
0x1800ebad9  nop     dword ptr [rax+rax+00h]
0x1800ebade  mov     rdx, rax
0x1800ebae1  mov     rcx, rsi
0x1800ebae4  test    rax, rax
0x1800ebae7  jnz     loc_1801A14C6
0x1800ebaed  call    cs:__imp_RtlWow64RequestCrossProcessHeavyFlush
0x1800ebaf4  nop     dword ptr [rax+rax+00h]
0x1800ebaf9  jmp     loc_1800EBA45
0x1800ebafe  test    r14b, 30h
0x1800ebb02  jz      loc_1800EBC1A
0x1800ebb08  cmp     dword ptr [rbp+4Fh+var_48+8], 1000000h
0x1800ebb0f  jnz     loc_1800EBBA9
0x1800ebb15  mov     eax, 60000080h
0x1800ebb1a  mov     ecx, cs:dword_1803AAE28
0x1800ebb20  and     r14d, 0FFFFFFCFh
0x1800ebb24  or      r14d, eax
0x1800ebb27  mov     rax, qword ptr [rbp+4Fh+VirtualMemoryInformation]
0x1800ebb2b  mov     [rbp+4Fh+BaseAddress], rax
0x1800ebb2f  lea     rdx, [rcx-1]
0x1800ebb33  mov     rax, rdx
0x1800ebb36  not     rdx
0x1800ebb39  and     rax, r13
0x1800ebb3c  add     rax, rcx
0x1800ebb3f  mov     rcx, [rbp+4Fh+NumberOfBytesToWrite]
0x1800ebb43  dec     rcx
0x1800ebb46  add     rcx, rax
0x1800ebb49  mov     rax, qword ptr [rbp+4Fh+var_58+8]
0x1800ebb4d  and     rcx, rdx
0x1800ebb50  mov     [rbp+4Fh+NumberOfBytesToProtect], rcx
0x1800ebb54  cmp     rcx, rax
0x1800ebb57  jbe     short loc_1800EBB5D
0x1800ebb59  mov     [rbp+4Fh+NumberOfBytesToProtect], rax
0x1800ebb5d  cmp     [rbp+4Fh+var_90], 0
0x1800ebb62  jnz     short loc_1800EBBBC
0x1800ebb64  lea     rax, [rbp+4Fh+OldAccessProtection]
0x1800ebb68  mov     r9d, r14d; NewAccessProtection
0x1800ebb6b  lea     r8, [rbp+4Fh+NumberOfBytesToProtect]; NumberOfBytesToProtect
0x1800ebb6f  mov     [rsp+0D0h+Length], rax; OldAccessProtection
0x1800ebb74  lea     rdx, [rbp+4Fh+BaseAddress]; BaseAddress
0x1800ebb78  mov     rcx, r12; ProcessHandle
0x1800ebb7b  call    cs:__imp_NtProtectVirtualMemory
0x1800ebb82  nop     dword ptr [rax+rax+00h]
0x1800ebb87  cmp     [rbp+4Fh+var_90], 0
0x1800ebb8c  mov     ebx, eax
0x1800ebb8e  jnz     short loc_1800EBBEB
0x1800ebb90  test    ebx, ebx
0x1800ebb92  js      loc_1800EBA45
0x1800ebb98  mov     r15b, 1
0x1800ebb9b  jmp     loc_1800EB9F9
0x1800ebba0  lea     rsi, [rdi+8]
0x1800ebba4  jmp     loc_1800EB9B4
0x1800ebba9  cmp     dword ptr [rbp+4Fh+var_48+8], 20000h
0x1800ebbb0  jnz     short loc_1800EBC1A
0x1800ebbb2  mov     eax, 60000040h
0x1800ebbb7  jmp     loc_1800EBB1A
0x1800ebbbc  mov     rcx, rdi
0x1800ebbbf  call    cs:__imp_RtlWow64PopCrossProcessWorkFromFreeList
0x1800ebbc6  nop     dword ptr [rax+rax+00h]
0x1800ebbcb  mov     rdx, rax
0x1800ebbce  mov     rcx, rsi
0x1800ebbd1  test    rax, rax
0x1800ebbd4  jnz     loc_1801A1398
0x1800ebbda  call    cs:__imp_RtlWow64RequestCrossProcessHeavyFlush
0x1800ebbe1  nop     dword ptr [rax+rax+00h]
0x1800ebbe6  jmp     loc_1800EBB64
0x1800ebbeb  mov     rcx, rdi
0x1800ebbee  call    cs:__imp_RtlWow64PopCrossProcessWorkFromFreeList
0x1800ebbf5  nop     dword ptr [rax+rax+00h]
0x1800ebbfa  mov     rdx, rax
0x1800ebbfd  mov     rcx, rsi
0x1800ebc00  test    rax, rax
0x1800ebc03  jnz     loc_1801A13E5
0x1800ebc09  call    cs:__imp_RtlWow64RequestCrossProcessHeavyFlush
0x1800ebc10  nop     dword ptr [rax+rax+00h]
0x1800ebc15  jmp     loc_1800EBB90
0x1800ebc1a  mov     ebx, 0C0000005h
0x1800ebc1f  jmp     loc_1800EBA45
0x1800ebc24  mov     rcx, rdi
0x1800ebc27  call    cs:__imp_RtlWow64PopCrossProcessWorkFromFreeList
0x1800ebc2e  nop     dword ptr [rax+rax+00h]
0x1800ebc33  mov     rcx, rsi
0x1800ebc36  test    rax, rax
0x1800ebc39  jnz     loc_1801A1435
0x1800ebc3f  call    cs:__imp_RtlWow64RequestCrossProcessHeavyFlush
0x1800ebc46  nop     dword ptr [rax+rax+00h]
0x1800ebc4b  jmp     loc_1800EBA40
0x1800ebc50  mov     rcx, rdi
0x1800ebc53  call    cs:__imp_RtlWow64PopCrossProcessWorkFromFreeList
0x1800ebc5a  nop     dword ptr [rax+rax+00h]
0x1800ebc5f  mov     rdx, rax
0x1800ebc62  mov     rcx, rsi
0x1800ebc65  test    rax, rax
0x1800ebc68  jnz     loc_1801A1479
0x1800ebc6e  call    cs:__imp_RtlWow64RequestCrossProcessHeavyFlush
0x1800ebc75  nop     dword ptr [rax+rax+00h]
0x1800ebc7a  jmp     loc_1800EBAA3
0x1800ebc7f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800ebc83  call    cs:__imp_NtUnmapViewOfSection
0x1800ebc8a  nop     dword ptr [rax+rax+00h]
0x1800ebc8f  mov     rcx, [rbp+4Fh+Handle]; Handle
0x1800ebc93  call    cs:__imp_NtClose
0x1800ebc9a  nop     dword ptr [rax+rax+00h]
0x1800ebc9f  jmp     loc_1800EBA52
0x1801a1398  mov     dword ptr [rax+4], 4
0x1801a139f  lea     r8, [rbp+4Fh+var_A0]
0x1801a13a3  mov     rax, [rbp+4Fh+BaseAddress]
0x1801a13a7  mov     [rdx+8], rax
0x1801a13ab  mov     rax, [rbp+4Fh+NumberOfBytesToProtect]
0x1801a13af  mov     [rdx+10h], rax
0x1801a13b3  mov     [rdx+18h], r14d
0x1801a13b7  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoWorkList
0x1801a13be  nop     dword ptr [rax+rax+00h]
0x1801a13c3  mov     rdx, [rbp+4Fh+var_A0]
0x1801a13c7  test    rdx, rdx
0x1801a13ca  jz      loc_1800EBB64
0x1801a13d0  mov     rcx, rdi
0x1801a13d3  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoFreeList
0x1801a13da  nop     dword ptr [rax+rax+00h]
0x1801a13df  nop
0x1801a13e0  jmp     loc_1800EBB64
0x1801a13e5  mov     dword ptr [rax+4], 5
0x1801a13ec  lea     r8, [rbp+4Fh+var_A0]
0x1801a13f0  mov     rax, [rbp+4Fh+BaseAddress]
0x1801a13f4  mov     [rdx+8], rax
0x1801a13f8  mov     rax, [rbp+4Fh+NumberOfBytesToProtect]
0x1801a13fc  mov     [rdx+10h], rax
0x1801a1400  mov     [rdx+18h], r14d
0x1801a1404  mov     [rdx+1Ch], ebx
0x1801a1407  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoWorkList
0x1801a140e  nop     dword ptr [rax+rax+00h]
0x1801a1413  mov     rdx, [rbp+4Fh+var_A0]
0x1801a1417  test    rdx, rdx
0x1801a141a  jz      loc_1800EBB90
0x1801a1420  mov     rcx, rdi
0x1801a1423  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoFreeList
0x1801a142a  nop     dword ptr [rax+rax+00h]
0x1801a142f  nop
0x1801a1430  jmp     loc_1800EBB90
0x1801a1435  lea     r8, [rbp+4Fh+var_A0]
0x1801a1439  mov     dword ptr [rax+4], 6
0x1801a1440  mov     rdx, rax
0x1801a1443  mov     [rax+8], r13
0x1801a1447  mov     [rax+10h], r14
0x1801a144b  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoWorkList
0x1801a1452  nop     dword ptr [rax+rax+00h]
0x1801a1457  mov     rdx, [rbp+4Fh+var_A0]
0x1801a145b  test    rdx, rdx
0x1801a145e  jz      loc_1800EBA40
0x1801a1464  mov     rcx, rdi
0x1801a1467  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoFreeList
0x1801a146e  nop     dword ptr [rax+rax+00h]
0x1801a1473  nop
0x1801a1474  jmp     loc_1800EBA40
0x1801a1479  mov     dword ptr [rax+4], 4
0x1801a1480  lea     r8, [rbp+4Fh+var_A0]
0x1801a1484  mov     rax, [rbp+4Fh+BaseAddress]
0x1801a1488  mov     [rdx+8], rax
0x1801a148c  mov     rax, [rbp+4Fh+NumberOfBytesToProtect]
0x1801a1490  mov     [rdx+10h], rax
0x1801a1494  mov     [rdx+18h], r14d
0x1801a1498  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoWorkList
0x1801a149f  nop     dword ptr [rax+rax+00h]
0x1801a14a4  mov     rdx, [rbp+4Fh+var_A0]
0x1801a14a8  test    rdx, rdx
0x1801a14ab  jz      loc_1800EBAA3
0x1801a14b1  mov     rcx, rdi
0x1801a14b4  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoFreeList
0x1801a14bb  nop     dword ptr [rax+rax+00h]
0x1801a14c0  nop
0x1801a14c1  jmp     loc_1800EBAA3
0x1801a14c6  mov     dword ptr [rax+4], 5
0x1801a14cd  lea     r8, [rbp+4Fh+var_A0]
0x1801a14d1  mov     rax, [rbp+4Fh+BaseAddress]
0x1801a14d5  mov     [rdx+8], rax
0x1801a14d9  mov     rax, [rbp+4Fh+NumberOfBytesToProtect]
0x1801a14dd  mov     [rdx+10h], rax
0x1801a14e1  mov     [rdx+18h], r14d
0x1801a14e5  mov     [rdx+1Ch], ebx
0x1801a14e8  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoWorkList
0x1801a14ef  nop     dword ptr [rax+rax+00h]
0x1801a14f4  mov     rdx, [rbp+4Fh+var_A0]
0x1801a14f8  test    rdx, rdx
0x1801a14fb  jz      loc_1800EBA45
0x1801a1501  mov     rcx, rdi
0x1801a1504  call    cs:__imp_RtlWow64PushCrossProcessWorkOntoFreeList
0x1801a150b  nop     dword ptr [rax+rax+00h]
0x1801a1510  nop
0x1801a1511  jmp     loc_1800EBA45
```
