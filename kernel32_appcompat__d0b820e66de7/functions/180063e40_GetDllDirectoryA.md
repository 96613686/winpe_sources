# GetDllDirectoryA

- ea: `0x180063e40`
- end: `0x180063fad`
- name: `GetDllDirectoryA`
- size: `365`
- prototype: `DWORD __stdcall(DWORD nBufferLength, LPSTR lpBuffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000ccf0`
- `0x180063e40`
- `0x180084010`

## import_xrefs

- `ntdll!LdrGetDllDirectory` at `0x180063e77`
- `ntdll!LdrGetDllDirectory` at `0x180063ef9`
- `ntdll!LdrGetDllDirectory` at `0x180063e77`
- `ntdll!LdrGetDllDirectory` at `0x180063ef9`
- `ntdll!RtlSetLastWin32Error` at `0x180063e97`
- `ntdll!RtlSetLastWin32Error` at `0x180063e97`
- `ntdll!RtlInitUnicodeString` at `0x180063e67`
- `ntdll!RtlInitUnicodeString` at `0x180063e67`
- `ntdll!RtlFreeHeap` at `0x180063f1f`
- `ntdll!RtlFreeHeap` at `0x180063f1f`
- `ntdll!RtlAllocateHeap` at `0x180063ed3`
- `ntdll!RtlAllocateHeap` at `0x180063ed3`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180063eb4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180063eb4`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180063f47`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180063f47`
- `KERNELBASE!GetUnicodeStringToEightBitSizeRoutine` at `0x180063f81`
- `KERNELBASE!GetUnicodeStringToEightBitSizeRoutine` at `0x180063f81`

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
0x180063e40  push    rbp
0x180063e42  push    rbx
0x180063e43  push    rsi
0x180063e44  push    rdi
0x180063e45  push    r14
0x180063e47  mov     rbp, rsp
0x180063e4a  sub     rsp, 40h
0x180063e4e  mov     rsi, rdx
0x180063e51  mov     edi, ecx
0x180063e53  xorps   xmm0, xmm0
0x180063e56  lea     rcx, [rbp+DestinationString]; DestinationString
0x180063e5a  xorps   xmm1, xmm1
0x180063e5d  xor     edx, edx; SourceString
0x180063e5f  movups  [rbp+var_10], xmm0
0x180063e63  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180063e67  call    cs:__imp_RtlInitUnicodeString
0x180063e6e  nop     dword ptr [rax+rax+00h]
0x180063e73  lea     rcx, [rbp+DestinationString]
0x180063e77  call    cs:__imp_LdrGetDllDirectory
0x180063e7e  nop     dword ptr [rax+rax+00h]
0x180063e83  movzx   r14d, [rbp+DestinationString.Length]
0x180063e88  xor     ebx, ebx
0x180063e8a  cmp     r14w, 2
0x180063e8f  jnz     short loc_180063EB4
0x180063e91  test    edi, edi
0x180063e93  jz      short loc_180063EAA
0x180063e95  xor     ecx, ecx; LastError
0x180063e97  call    cs:__imp_RtlSetLastWin32Error
0x180063e9e  nop     dword ptr [rax+rax+00h]
0x180063ea3  mov     [rsi], bl
0x180063ea5  jmp     loc_180063F9F
0x180063eaa  mov     eax, 1
0x180063eaf  jmp     loc_180063FA1
0x180063eb4  call    cs:__imp_KernelBaseGetGlobalData
0x180063ebb  nop     dword ptr [rax+rax+00h]
0x180063ec0  mov     rcx, gs:60h
0x180063ec9  movzx   r8d, r14w; Size
0x180063ecd  mov     edx, [rax]; Flags
0x180063ecf  mov     rcx, [rcx+30h]; HeapHandle
0x180063ed3  call    cs:__imp_RtlAllocateHeap
0x180063eda  nop     dword ptr [rax+rax+00h]
0x180063edf  mov     [rbp+DestinationString.Buffer], rax
0x180063ee3  test    rax, rax
0x180063ee6  jz      loc_180063F6F
0x180063eec  lea     rcx, [rbp+DestinationString]
0x180063ef0  mov     [rbp+DestinationString.MaximumLength], r14w
0x180063ef5  mov     [rbp+DestinationString.Length], bx
0x180063ef9  call    cs:__imp_LdrGetDllDirectory
0x180063f00  nop     dword ptr [rax+rax+00h]
0x180063f05  cmp     eax, 0C0000023h
0x180063f0a  jnz     short loc_180063F32
0x180063f0c  mov     rcx, gs:60h
0x180063f15  xor     edx, edx; Flags
0x180063f17  mov     r8, [rbp+DestinationString.Buffer]; P
0x180063f1b  mov     rcx, [rcx+30h]; HeapHandle
0x180063f1f  call    cs:__imp_RtlFreeHeap
0x180063f26  nop     dword ptr [rax+rax+00h]
0x180063f2b  movzx   r14d, [rbp+DestinationString.Length]
0x180063f30  jmp     short loc_180063EB4
0x180063f32  mov     eax, 0FFFEh
0x180063f37  mov     qword ptr [rbp+var_10+8], rsi
0x180063f3b  mov     word ptr [rbp+var_10+2], di
0x180063f3f  cmp     edi, eax
0x180063f41  jbe     short loc_180063F47
0x180063f43  mov     word ptr [rbp+var_10+2], ax
0x180063f47  call    cs:__imp_GetUnicodeStringToEightBitStringRoutine
0x180063f4e  nop     dword ptr [rax+rax+00h]
0x180063f53  xor     r8d, r8d
0x180063f56  lea     rdx, [rbp+DestinationString]
0x180063f5a  lea     rcx, [rbp+var_10]
0x180063f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f63  test    eax, eax
0x180063f65  js      short loc_180063F74
0x180063f67  movzx   eax, word ptr [rbp+var_10]
0x180063f6b  dec     eax
0x180063f6d  jmp     short loc_180063FA1
0x180063f6f  mov     eax, 0C0000017h
0x180063f74  test    edi, edi
0x180063f76  jz      short loc_180063F7A
0x180063f78  mov     [rsi], bl
0x180063f7a  cmp     eax, 80000005h
0x180063f7f  jnz     short loc_180063F98
0x180063f81  call    cs:__imp_GetUnicodeStringToEightBitSizeRoutine
0x180063f88  nop     dword ptr [rax+rax+00h]
0x180063f8d  lea     rcx, [rbp+DestinationString]
0x180063f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f96  jmp     short loc_180063FA1
0x180063f98  mov     ecx, eax
0x180063f9a  call    BaseSetLastNTError
0x180063f9f  xor     eax, eax
0x180063fa1  add     rsp, 40h
0x180063fa5  pop     r14
0x180063fa7  pop     rdi
0x180063fa8  pop     rsi
0x180063fa9  pop     rbx
0x180063faa  pop     rbp
0x180063fab  retn
```
