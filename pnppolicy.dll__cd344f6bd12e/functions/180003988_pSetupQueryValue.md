# pSetupQueryValue

- ea: `0x180003988`
- end: `0x180003acd`
- name: `pSetupQueryValue`
- size: `325`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCWSTR SourceString@<rdx>, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800040d8`
- `0x180005018`
- `0x1800051f8`
- `0x1800054d4`
- `0x180006590`
- `0x180007548`
- `0x18000762c`

## callees

- `0x180003988`
- `0x18000a156`
- `0x18000a1a0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180003a35`
- `ntdll!NtQueryValueKey` at `0x180003a35`
- `ntdll!RtlInitUnicodeString` at `0x180003a10`
- `ntdll!RtlInitUnicodeString` at `0x180003a10`
- `ntdll!RtlNtStatusToDosError` at `0x180003a50`
- `ntdll!RtlNtStatusToDosError` at `0x180003a50`
- `KERNEL32!HeapFree` at `0x180003aa9`
- `KERNEL32!HeapFree` at `0x180003aa9`
- `KERNEL32!HeapAlloc` at `0x1800039e8`
- `KERNEL32!HeapAlloc` at `0x1800039e8`

## pseudocode

```c
__int64 __fastcall pSetupQueryValue(HANDLE KeyHandle, PCWSTR SourceString, _DWORD *a3, void *a4, unsigned int *a5)
{
  unsigned int v8; // r15d
  ULONG Length; // edi
  __int128 *v10; // rbx
  ULONG v11; // edi
  NTSTATUS v12; // eax
  unsigned int v13; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-60h] BYREF
  __int128 v17; // [rsp+48h] [rbp-50h] BYREF

  ResultLength = 0;
  v8 = (unsigned int)KeyHandle;
  DestinationString = 0;
  v17 = 0;
  if ( a4 )
  {
    Length = *a5 + 15;
    v10 = (__int128 *)HeapAlloc(hHeap, 0, Length);
    if ( !v10 )
      return 14;
  }
  else
  {
    v10 = &v17;
    Length = 16;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v12 = NtQueryValueKey((HANDLE)v8, &DestinationString, KeyValuePartialInformation, v10, Length, &ResultLength);
  if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147483643 )
  {
    v11 = 0;
    if ( a4 )
    {
      v13 = *((_DWORD *)v10 + 2);
      if ( *a5 < v13 )
        v11 = 122;
      else
        memcpy_0(a4, (char *)v10 + 12, v13);
    }
    *a5 = *((_DWORD *)v10 + 2);
    if ( a3 )
      *a3 = *((_DWORD *)v10 + 1);
  }
  else
  {
    v11 = RtlNtStatusToDosError(v12);
  }
  if ( v10 && v10 != &v17 )
    HeapFree(hHeap, 0, v10);
  return v11;
}

```

## disassembly

```asm
0x180003988  push    rbx
0x18000398a  push    rbp
0x18000398b  push    rsi
0x18000398c  push    rdi
0x18000398d  push    r12
0x18000398f  push    r14
0x180003991  push    r15
0x180003993  sub     rsp, 60h
0x180003997  mov     rax, cs:__security_cookie
0x18000399e  xor     rax, rsp
0x1800039a1  mov     [rsp+98h+var_40], rax
0x1800039a6  mov     rsi, [rsp+98h+arg_20]
0x1800039ae  xorps   xmm0, xmm0
0x1800039b1  mov     [rsp+98h+var_68], 0
0x1800039b9  xorps   xmm1, xmm1
0x1800039bc  mov     rbp, r9
0x1800039bf  mov     r14, r8
0x1800039c2  mov     r12, rdx
0x1800039c5  mov     r15, rcx
0x1800039c8  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x1800039cd  movups  [rsp+98h+var_50], xmm1
0x1800039d2  test    r9, r9
0x1800039d5  jz      short loc_1800039FE
0x1800039d7  mov     edi, [rsi]
0x1800039d9  xor     edx, edx; dwFlags
0x1800039db  mov     rcx, cs:hHeap; hHeap
0x1800039e2  add     edi, 0Fh
0x1800039e5  mov     r8d, edi; dwBytes
0x1800039e8  call    cs:__imp_HeapAlloc
0x1800039ee  mov     rbx, rax
0x1800039f1  test    rax, rax
0x1800039f4  jnz     short loc_180003A08
0x1800039f6  lea     edi, [rax+0Eh]
0x1800039f9  jmp     loc_180003AAF
0x1800039fe  lea     rbx, [rsp+98h+var_50]
0x180003a03  mov     edi, 10h
0x180003a08  mov     rdx, r12; SourceString
0x180003a0b  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x180003a10  call    cs:__imp_RtlInitUnicodeString
0x180003a16  lea     rax, [rsp+98h+var_68]
0x180003a1b  mov     ecx, r15d; KeyHandle
0x180003a1e  mov     [rsp+98h+ResultLength], rax; ResultLength
0x180003a23  lea     rdx, [rsp+98h+DestinationString]; ValueName
0x180003a28  mov     r9, rbx; KeyValueInformation
0x180003a2b  mov     [rsp+98h+Length], edi; Length
0x180003a2f  mov     r8d, 2; KeyValueInformationClass
0x180003a35  call    cs:__imp_NtQueryValueKey
0x180003a3b  mov     edx, 80000000h
0x180003a40  lea     ecx, [rax+rdx]
0x180003a43  test    edx, ecx
0x180003a45  jnz     short loc_180003A5A
0x180003a47  cmp     eax, 80000005h
0x180003a4c  jz      short loc_180003A5A
0x180003a4e  mov     ecx, eax; Status
0x180003a50  call    cs:__imp_RtlNtStatusToDosError
0x180003a56  mov     edi, eax
0x180003a58  jmp     short loc_180003A8E
0x180003a5a  xor     edi, edi
0x180003a5c  test    rbp, rbp
0x180003a5f  jz      short loc_180003A7E
0x180003a61  mov     eax, [rbx+8]
0x180003a64  cmp     [rsi], eax
0x180003a66  jb      short loc_180003A79
0x180003a68  mov     r8d, eax; Size
0x180003a6b  lea     rdx, [rbx+0Ch]; Src
0x180003a6f  mov     rcx, rbp; void *
0x180003a72  call    memcpy_0
0x180003a77  jmp     short loc_180003A7E
0x180003a79  mov     edi, 7Ah ; 'z'
0x180003a7e  mov     eax, [rbx+8]
0x180003a81  mov     [rsi], eax
0x180003a83  test    r14, r14
0x180003a86  jz      short loc_180003A8E
0x180003a88  mov     eax, [rbx+4]
0x180003a8b  mov     [r14], eax
0x180003a8e  test    rbx, rbx
0x180003a91  jz      short loc_180003AAF
0x180003a93  lea     rax, [rsp+98h+var_50]
0x180003a98  cmp     rbx, rax
0x180003a9b  jz      short loc_180003AAF
0x180003a9d  mov     rcx, cs:hHeap; hHeap
0x180003aa4  mov     r8, rbx; lpMem
0x180003aa7  xor     edx, edx; dwFlags
0x180003aa9  call    cs:__imp_HeapFree
0x180003aaf  mov     eax, edi
0x180003ab1  mov     rcx, [rsp+98h+var_40]
0x180003ab6  xor     rcx, rsp; StackCookie
0x180003ab9  call    __security_check_cookie
0x180003abe  add     rsp, 60h
0x180003ac2  pop     r15
0x180003ac4  pop     r14
0x180003ac6  pop     r12
0x180003ac8  pop     rdi
0x180003ac9  pop     rsi
0x180003aca  pop     rbp
0x180003acb  pop     rbx
0x180003acc  retn
```
