# GetDllDirectoryA

- ea: `0x18005e2c0`
- end: `0x18005e3f2`
- name: `GetDllDirectoryA`
- size: `306`
- prototype: `DWORD __stdcall(DWORD nBufferLength, LPSTR lpBuffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000f920`
- `0x18005e2c0`
- `0x18007c010`

## import_xrefs

- `ntdll!LdrGetDllDirectory` at `0x18005e2f1`
- `ntdll!LdrGetDllDirectory` at `0x18005e357`
- `ntdll!LdrGetDllDirectory` at `0x18005e2f1`
- `ntdll!LdrGetDllDirectory` at `0x18005e357`
- `ntdll!RtlSetLastWin32Error` at `0x18005e30b`
- `ntdll!RtlSetLastWin32Error` at `0x18005e30b`
- `ntdll!RtlInitUnicodeString` at `0x18005e2e7`
- `ntdll!RtlInitUnicodeString` at `0x18005e2e7`
- `ntdll!RtlFreeHeap` at `0x18005e377`
- `ntdll!RtlFreeHeap` at `0x18005e377`
- `ntdll!RtlAllocateHeap` at `0x18005e33b`
- `ntdll!RtlAllocateHeap` at `0x18005e33b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005e322`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005e322`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18005e399`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18005e399`
- `KERNELBASE!GetUnicodeStringToEightBitSizeRoutine` at `0x18005e3cd`
- `KERNELBASE!GetUnicodeStringToEightBitSizeRoutine` at `0x18005e3cd`

## pseudocode

```c
DWORD __stdcall GetDllDirectoryA(DWORD nBufferLength, LPSTR lpBuffer)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  USHORT Length; // r14
  ULONG *GlobalData; // rax
  __int64 (__fastcall *UnicodeStringToEightBitStringRoutine)(__int128 *, struct _UNICODE_STRING *, _QWORD); // rax
  int v12; // eax
  __int64 (__fastcall *UnicodeStringToEightBitSizeRoutine)(struct _UNICODE_STRING *); // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-20h] BYREF
  __int128 v15; // [rsp+30h] [rbp-10h] BYREF

  v15 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  LdrGetDllDirectory(&DestinationString);
  Length = DestinationString.Length;
  if ( DestinationString.Length == 2 )
  {
    if ( !nBufferLength )
      return 1;
    RtlSetLastWin32Error(0);
    *lpBuffer = 0;
  }
  else
  {
    while ( 1 )
    {
      GlobalData = (ULONG *)KernelBaseGetGlobalData(v5, v4, v6, v7);
      DestinationString.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, Length);
      if ( !DestinationString.Buffer )
      {
        v12 = -1073741801;
        goto LABEL_13;
      }
      DestinationString.MaximumLength = Length;
      DestinationString.Length = 0;
      if ( (unsigned int)LdrGetDllDirectory(&DestinationString) != -1073741789 )
        break;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
      Length = DestinationString.Length;
    }
    *((_QWORD *)&v15 + 1) = lpBuffer;
    WORD1(v15) = nBufferLength;
    if ( nBufferLength > 0xFFFE )
      WORD1(v15) = -2;
    UnicodeStringToEightBitStringRoutine = (__int64 (__fastcall *)(__int128 *, struct _UNICODE_STRING *, _QWORD))GetUnicodeStringToEightBitStringRoutine();
    v12 = UnicodeStringToEightBitStringRoutine(&v15, &DestinationString, 0);
    if ( v12 >= 0 )
      return (unsigned __int16)v15 - 1;
LABEL_13:
    if ( nBufferLength )
      *lpBuffer = 0;
    if ( v12 == -2147483643 )
    {
      UnicodeStringToEightBitSizeRoutine = (__int64 (__fastcall *)(struct _UNICODE_STRING *))GetUnicodeStringToEightBitSizeRoutine();
      return UnicodeStringToEightBitSizeRoutine(&DestinationString);
    }
    BaseSetLastNTError((unsigned int)v12);
  }
  return 0;
}

```

## disassembly

```asm
0x18005e2c0  push    rbp
0x18005e2c2  push    rbx
0x18005e2c3  push    rsi
0x18005e2c4  push    rdi
0x18005e2c5  push    r14
0x18005e2c7  mov     rbp, rsp
0x18005e2ca  sub     rsp, 40h
0x18005e2ce  mov     rsi, rdx
0x18005e2d1  mov     edi, ecx
0x18005e2d3  xorps   xmm0, xmm0
0x18005e2d6  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005e2da  xorps   xmm1, xmm1
0x18005e2dd  xor     edx, edx; SourceString
0x18005e2df  movups  [rbp+var_10], xmm0
0x18005e2e3  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x18005e2e7  call    cs:__imp_RtlInitUnicodeString
0x18005e2ed  lea     rcx, [rbp+DestinationString]
0x18005e2f1  call    cs:__imp_LdrGetDllDirectory
0x18005e2f7  movzx   r14d, [rbp+DestinationString.Length]
0x18005e2fc  xor     ebx, ebx
0x18005e2fe  cmp     r14w, 2
0x18005e303  jnz     short loc_18005E322
0x18005e305  test    edi, edi
0x18005e307  jz      short loc_18005E318
0x18005e309  xor     ecx, ecx; LastError
0x18005e30b  call    cs:__imp_RtlSetLastWin32Error
0x18005e311  mov     [rsi], bl
0x18005e313  jmp     loc_18005E3E5
0x18005e318  mov     eax, 1
0x18005e31d  jmp     loc_18005E3E7
0x18005e322  call    cs:__imp_KernelBaseGetGlobalData
0x18005e328  mov     rcx, gs:60h
0x18005e331  movzx   r8d, r14w; Size
0x18005e335  mov     edx, [rax]; Flags
0x18005e337  mov     rcx, [rcx+30h]; HeapHandle
0x18005e33b  call    cs:__imp_RtlAllocateHeap
0x18005e341  mov     [rbp+DestinationString.Buffer], rax
0x18005e345  test    rax, rax
0x18005e348  jz      short loc_18005E3BB
0x18005e34a  lea     rcx, [rbp+DestinationString]
0x18005e34e  mov     [rbp+DestinationString.MaximumLength], r14w
0x18005e353  mov     [rbp+DestinationString.Length], bx
0x18005e357  call    cs:__imp_LdrGetDllDirectory
0x18005e35d  cmp     eax, 0C0000023h
0x18005e362  jnz     short loc_18005E384
0x18005e364  mov     rcx, gs:60h
0x18005e36d  xor     edx, edx; Flags
0x18005e36f  mov     r8, [rbp+DestinationString.Buffer]; P
0x18005e373  mov     rcx, [rcx+30h]; HeapHandle
0x18005e377  call    cs:__imp_RtlFreeHeap
0x18005e37d  movzx   r14d, [rbp+DestinationString.Length]
0x18005e382  jmp     short loc_18005E322
0x18005e384  mov     eax, 0FFFEh
0x18005e389  mov     qword ptr [rbp+var_10+8], rsi
0x18005e38d  mov     word ptr [rbp+var_10+2], di
0x18005e391  cmp     edi, eax
0x18005e393  jbe     short loc_18005E399
0x18005e395  mov     word ptr [rbp+var_10+2], ax
0x18005e399  call    cs:__imp_GetUnicodeStringToEightBitStringRoutine
0x18005e39f  xor     r8d, r8d
0x18005e3a2  lea     rdx, [rbp+DestinationString]
0x18005e3a6  lea     rcx, [rbp+var_10]
0x18005e3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3af  test    eax, eax
0x18005e3b1  js      short loc_18005E3C0
0x18005e3b3  movzx   eax, word ptr [rbp+var_10]
0x18005e3b7  dec     eax
0x18005e3b9  jmp     short loc_18005E3E7
0x18005e3bb  mov     eax, 0C0000017h
0x18005e3c0  test    edi, edi
0x18005e3c2  jz      short loc_18005E3C6
0x18005e3c4  mov     [rsi], bl
0x18005e3c6  cmp     eax, 80000005h
0x18005e3cb  jnz     short loc_18005E3DE
0x18005e3cd  call    cs:__imp_GetUnicodeStringToEightBitSizeRoutine
0x18005e3d3  lea     rcx, [rbp+DestinationString]
0x18005e3d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3dc  jmp     short loc_18005E3E7
0x18005e3de  mov     ecx, eax
0x18005e3e0  call    BaseSetLastNTError
0x18005e3e5  xor     eax, eax
0x18005e3e7  add     rsp, 40h
0x18005e3eb  pop     r14
0x18005e3ed  pop     rdi
0x18005e3ee  pop     rsi
0x18005e3ef  pop     rbx
0x18005e3f0  pop     rbp
0x18005e3f1  retn
```
