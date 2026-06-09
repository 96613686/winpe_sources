# SdbpCheckMatchingRegistryValue

- ea: `0x1800a97a4`
- end: `0x1800a9b23`
- name: `SdbpCheckMatchingRegistryValue`
- size: `895`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, wchar_t *String1@<rdx>, int, __int64, void *Buf1, size_t Size, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800a95bc`
- `0x1800aa07c`

## callees

- `0x180041774`
- `0x18004281c`
- `0x18006f39c`
- `0x180076e90`
- `0x180076efc`
- `0x180076f14`
- `0x1800a97a4`
- `0x1800c0a94`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800a982a`
- `ntdll!RtlInitUnicodeString` at `0x1800a982a`
- `ntdll!RtlAllocateHeap` at `0x1800a9884`
- `ntdll!RtlAllocateHeap` at `0x1800a998a`
- `ntdll!RtlAllocateHeap` at `0x1800a9ac6`
- `ntdll!RtlAllocateHeap` at `0x1800a9884`
- `ntdll!RtlAllocateHeap` at `0x1800a998a`
- `ntdll!RtlAllocateHeap` at `0x1800a9ac6`
- `ntdll!ZwQueryValueKey` at `0x1800a984e`
- `ntdll!ZwQueryValueKey` at `0x1800a98d0`
- `ntdll!ZwQueryValueKey` at `0x1800a984e`
- `ntdll!ZwQueryValueKey` at `0x1800a98d0`

## string_xrefs

- `0x1800a989f`: `SdbpCheckMatchingRegistryValue`
- `0x1800a98ed`: `SdbpCheckMatchingRegistryValue`
- `0x1800a97f2`: `dbRegistryDefaultName`
- `0x1800a98dd`: `Failed to read value`
- `0x1800a9952`: `Unknown registry value data type`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingRegistryValue(
        HANDLE KeyHandle,
        wchar_t *String1,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        void *Buf1,
        size_t Size,
        _DWORD *a9)
{
  PCWSTR v12; // r15
  _WORD *v13; // rsi
  _DWORD *v14; // rdi
  unsigned int v15; // ebx
  const WCHAR *v16; // rdx
  int v17; // eax
  NTSTATUS v18; // eax
  _DWORD *Heap; // rax
  const char *v20; // r9
  __int64 v21; // r8
  int v22; // ecx
  _DWORD *v23; // r14
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  bool v29; // zf
  _WORD *v30; // rax
  _WORD *i; // rcx
  _WORD *v33; // rax
  PCWSTR SourceString; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+48h] BYREF
  __int64 v37; // [rsp+A8h] [rbp+58h]

  v37 = a4;
  SourceString = 0;
  ResultLength = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  DestinationString = 0;
  if ( !String1 || !*String1 )
    goto LABEL_38;
  v15 = 0;
  if ( wcsicmp(String1, L"dbRegistryDefaultName") )
  {
    v17 = AslStringDuplicate(&SourceString, String1);
    v12 = SourceString;
    if ( v17 < 0 )
      goto LABEL_42;
    v16 = SourceString;
  }
  else
  {
    v16 = 0;
  }
  RtlInitUnicodeString(&DestinationString, v16);
  v18 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, 0, 0, &ResultLength);
  if ( v18 < 0 && v18 != -2147483643 && v18 != -1073741789 )
  {
    v15 = 1;
    goto LABEL_42;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
  v14 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbpCheckMatchingRegistryValue", 1249, "Failed to allocate memory");
    goto LABEL_42;
  }
  if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, Heap, ResultLength, &ResultLength) >= 0 )
  {
    if ( !a3 )
    {
      *a9 = 1;
LABEL_18:
      v15 = 1;
      goto LABEL_39;
    }
    v22 = v14[1];
    if ( v22 != a3 )
      goto LABEL_18;
    v23 = (_DWORD *)((char *)v14 + (unsigned int)v14[2]);
    v24 = v22 - 1;
    if ( v24 && (v25 = v24 - 1) != 0 )
    {
      v26 = v25 - 1;
      if ( !v26 )
      {
        if ( Size != v14[3] )
          goto LABEL_52;
        v29 = memcmp_0(Buf1, (char *)v14 + (unsigned int)v14[2], Size) == 0;
LABEL_37:
        if ( v29 )
          goto LABEL_38;
LABEL_52:
        v15 = 1;
        goto LABEL_39;
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
        v29 = a5 == *v23;
        goto LABEL_37;
      }
      v28 = v27 - 3;
      if ( v28 )
      {
        if ( v28 != 4 )
        {
          v20 = "Unknown registry value data type";
          v21 = 1396;
          goto LABEL_15;
        }
        v29 = a6 == *(_QWORD *)v23;
        goto LABEL_37;
      }
      v30 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v14[3] + 2LL);
      v13 = v30;
      if ( !v30 )
      {
        v21 = 1321;
LABEL_49:
        v20 = "Failed to allocate memory";
        goto LABEL_15;
      }
      memmove_0(v30, v23, (unsigned int)v14[3]);
      v13[(unsigned __int64)(unsigned int)v14[3] >> 1] = 0;
      for ( i = v13; i < (_WORD *)((char *)v13 + (v14[3] & 0xFFFFFFFE)); ++i )
      {
        if ( !*i )
        {
          if ( !i[1] )
            break;
          *i = 59;
        }
      }
    }
    else
    {
      v33 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v14[3] + 2LL);
      v13 = v33;
      if ( !v33 )
      {
        v21 = 1297;
        goto LABEL_49;
      }
      memmove_0(v33, v23, (unsigned int)v14[3]);
      v13[(unsigned __int64)(unsigned int)v14[3] >> 1] = 0;
    }
    if ( !(unsigned int)AslStringPatternMatchExW(v37, v13) )
      goto LABEL_52;
LABEL_38:
    *a9 = 1;
    v15 = 1;
    if ( !v14 )
      goto LABEL_40;
    goto LABEL_39;
  }
  v20 = "Failed to read value";
  v21 = 1260;
LABEL_15:
  AslLogCallPrintf(1, "SdbpCheckMatchingRegistryValue", v21, v20);
LABEL_39:
  AslFree(NtCurrentPeb()->ProcessHeap, v14);
LABEL_40:
  if ( v13 )
    AslFree(NtCurrentPeb()->ProcessHeap, v13);
LABEL_42:
  if ( v12 )
    AslFree(NtCurrentPeb()->ProcessHeap, v12);
  return v15;
}

```

## disassembly

```asm
0x1800a97a4  mov     [rsp-38h+arg_0], rbx
0x1800a97a9  mov     [rsp-38h+arg_18], r9
0x1800a97ae  push    rbp
0x1800a97af  push    rsi
0x1800a97b0  push    rdi
0x1800a97b1  push    r12
0x1800a97b3  push    r13
0x1800a97b5  push    r14
0x1800a97b7  push    r15
0x1800a97b9  mov     rbp, rsp
0x1800a97bc  sub     rsp, 50h
0x1800a97c0  xor     eax, eax
0x1800a97c2  xorps   xmm0, xmm0
0x1800a97c5  mov     [rbp+SourceString], rax
0x1800a97c9  mov     r12d, r8d
0x1800a97cc  mov     [rbp+arg_8], eax
0x1800a97cf  mov     r14, rdx
0x1800a97d2  mov     r13, rcx
0x1800a97d5  mov     r15d, eax
0x1800a97d8  mov     esi, eax
0x1800a97da  mov     edi, eax
0x1800a97dc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800a97e0  test    rdx, rdx
0x1800a97e3  jz      loc_1800A9A0F
0x1800a97e9  cmp     [rdx], ax
0x1800a97ec  jz      loc_1800A9A0F
0x1800a97f2  lea     rdx, aDbregistrydefa; "dbRegistryDefaultName"
0x1800a97f9  mov     rcx, r14; String1
0x1800a97fc  mov     ebx, eax
0x1800a97fe  call    _wcsicmp
0x1800a9803  test    eax, eax
0x1800a9805  jnz     short loc_1800A980B
0x1800a9807  xor     edx, edx
0x1800a9809  jmp     short loc_1800A9826
0x1800a980b  mov     rdx, r14
0x1800a980e  lea     rcx, [rbp+SourceString]
0x1800a9812  call    AslStringDuplicate
0x1800a9817  mov     r15, [rbp+SourceString]
0x1800a981b  test    eax, eax
0x1800a981d  js      loc_1800A9A55
0x1800a9823  mov     rdx, r15; SourceString
0x1800a9826  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800a982a  call    cs:__imp_RtlInitUnicodeString
0x1800a9830  xor     r9d, r9d; KeyValueInformation
0x1800a9833  lea     rax, [rbp+arg_8]
0x1800a9837  mov     [rsp+50h+ResultLength], rax; ResultLength
0x1800a983c  lea     rdx, [rbp+DestinationString]; ValueName
0x1800a9840  mov     rcx, r13; KeyHandle
0x1800a9843  mov     [rsp+50h+Length], ebx; Length
0x1800a9847  lea     r14d, [r9+1]
0x1800a984b  mov     r8d, r14d; KeyValueInformationClass
0x1800a984e  call    cs:__imp_ZwQueryValueKey
0x1800a9854  test    eax, eax
0x1800a9856  jns     short loc_1800A986E
0x1800a9858  cmp     eax, 80000005h
0x1800a985d  jz      short loc_1800A986E
0x1800a985f  cmp     eax, 0C0000023h
0x1800a9864  jz      short loc_1800A986E
0x1800a9866  mov     ebx, r14d
0x1800a9869  jmp     loc_1800A9A55
0x1800a986e  mov     rcx, gs:60h
0x1800a9877  mov     edx, 8; Flags
0x1800a987c  mov     r8d, [rbp+arg_8]; Size
0x1800a9880  mov     rcx, [rcx+30h]; HeapHandle
0x1800a9884  call    cs:__imp_RtlAllocateHeap
0x1800a988a  mov     rdi, rax
0x1800a988d  test    rax, rax
0x1800a9890  jnz     short loc_1800A98B3
0x1800a9892  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x1800a9899  mov     r8d, 4E1h
0x1800a989f  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x1800a98a6  mov     ecx, r14d
0x1800a98a9  call    AslLogCallPrintf
0x1800a98ae  jmp     loc_1800A9A55
0x1800a98b3  lea     rax, [rbp+arg_8]
0x1800a98b7  mov     r9, rdi; KeyValueInformation
0x1800a98ba  mov     [rsp+50h+ResultLength], rax; ResultLength
0x1800a98bf  lea     rdx, [rbp+DestinationString]; ValueName
0x1800a98c3  mov     eax, [rbp+arg_8]
0x1800a98c6  mov     r8d, r14d; KeyValueInformationClass
0x1800a98c9  mov     rcx, r13; KeyHandle
0x1800a98cc  mov     [rsp+50h+Length], eax; Length
0x1800a98d0  call    cs:__imp_ZwQueryValueKey
0x1800a98d6  xor     r13d, r13d
0x1800a98d9  test    eax, eax
0x1800a98db  jns     short loc_1800A98FE
0x1800a98dd  lea     r9, aFailedToReadVa_0; "Failed to read value"
0x1800a98e4  mov     r8d, 4ECh
0x1800a98ea  mov     ecx, r14d
0x1800a98ed  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x1800a98f4  call    AslLogCallPrintf
0x1800a98f9  jmp     loc_1800A9A26
0x1800a98fe  test    r12d, r12d
0x1800a9901  jnz     short loc_1800A9915
0x1800a9903  mov     rax, [rbp+arg_40]
0x1800a990a  mov     [rax], r14d
0x1800a990d  mov     ebx, r14d
0x1800a9910  jmp     loc_1800A9A26
0x1800a9915  mov     ecx, [rdi+4]
0x1800a9918  cmp     ecx, r12d
0x1800a991b  jnz     short loc_1800A990D
0x1800a991d  mov     r14d, [rdi+8]
0x1800a9921  add     r14, rdi
0x1800a9924  sub     ecx, 1
0x1800a9927  jz      loc_1800A9AAC
0x1800a992d  sub     ecx, 1
0x1800a9930  jz      loc_1800A9AAC
0x1800a9936  sub     ecx, 1
0x1800a9939  jz      loc_1800A9A89
0x1800a993f  sub     ecx, 1
0x1800a9942  jz      loc_1800A9A03
0x1800a9948  sub     ecx, 3
0x1800a994b  jz      short loc_1800A9970
0x1800a994d  cmp     ecx, 4
0x1800a9950  jz      short loc_1800A9964
0x1800a9952  lea     r9, aUnknownRegistr; "Unknown registry value data type"
0x1800a9959  mov     r8d, 574h
0x1800a995f  jmp     loc_1800A9AE1
0x1800a9964  mov     rax, [r14]
0x1800a9967  cmp     [rbp+arg_28], rax
0x1800a996b  jmp     loc_1800A9A09
0x1800a9970  mov     rcx, gs:60h
0x1800a9979  mov     edx, 8; Flags
0x1800a997e  mov     r8d, [rdi+0Ch]
0x1800a9982  add     r8, 2; Size
0x1800a9986  mov     rcx, [rcx+30h]; HeapHandle
0x1800a998a  call    cs:__imp_RtlAllocateHeap
0x1800a9990  mov     rsi, rax
0x1800a9993  test    rax, rax
0x1800a9996  jnz     short loc_1800A99A3
0x1800a9998  mov     r8d, 529h
0x1800a999e  jmp     loc_1800A9ADA
0x1800a99a3  mov     r8d, [rdi+0Ch]; Size
0x1800a99a7  mov     rdx, r14; Src
0x1800a99aa  mov     rcx, rsi; void *
0x1800a99ad  call    memmove_0
0x1800a99b2  mov     ecx, [rdi+0Ch]
0x1800a99b5  shr     rcx, 1
0x1800a99b8  mov     [rsi+rcx*2], r13w
0x1800a99bd  mov     rcx, rsi
0x1800a99c0  mov     eax, [rdi+0Ch]
0x1800a99c3  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800a99c7  add     rax, rsi
0x1800a99ca  cmp     rsi, rax
0x1800a99cd  jnb     loc_1800A9B05
0x1800a99d3  lea     rax, [rcx+2]
0x1800a99d7  cmp     [rcx], r13w
0x1800a99db  jnz     short loc_1800A99EC
0x1800a99dd  cmp     [rax], r13w
0x1800a99e1  jz      loc_1800A9B05
0x1800a99e7  mov     word ptr [rcx], 3Bh ; ';'
0x1800a99ec  mov     rcx, rax
0x1800a99ef  mov     eax, [rdi+0Ch]
0x1800a99f2  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800a99f6  add     rax, rsi
0x1800a99f9  cmp     rcx, rax
0x1800a99fc  jb      short loc_1800A99D3
0x1800a99fe  jmp     loc_1800A9B05
0x1800a9a03  mov     eax, [r14]
0x1800a9a06  cmp     [rbp+arg_20], eax
0x1800a9a09  jnz     loc_1800A9B19
0x1800a9a0f  mov     rax, [rbp+arg_40]
0x1800a9a16  mov     dword ptr [rax], 1
0x1800a9a1c  mov     ebx, 1
0x1800a9a21  test    rdi, rdi
0x1800a9a24  jz      short loc_1800A9A3B
0x1800a9a26  mov     rcx, gs:60h
0x1800a9a2f  mov     rdx, rdi
0x1800a9a32  mov     rcx, [rcx+30h]
0x1800a9a36  call    AslFree
0x1800a9a3b  test    rsi, rsi
0x1800a9a3e  jz      short loc_1800A9A55
0x1800a9a40  mov     rcx, gs:60h
0x1800a9a49  mov     rdx, rsi
0x1800a9a4c  mov     rcx, [rcx+30h]
0x1800a9a50  call    AslFree
0x1800a9a55  test    r15, r15
0x1800a9a58  jz      short loc_1800A9A6F
0x1800a9a5a  mov     rcx, gs:60h
0x1800a9a63  mov     rdx, r15
0x1800a9a66  mov     rcx, [rcx+30h]
0x1800a9a6a  call    AslFree
0x1800a9a6f  mov     eax, ebx
0x1800a9a71  mov     rbx, [rsp+50h+arg_0]
0x1800a9a79  add     rsp, 50h
0x1800a9a7d  pop     r15
0x1800a9a7f  pop     r14
0x1800a9a81  pop     r13
0x1800a9a83  pop     r12
0x1800a9a85  pop     rdi
0x1800a9a86  pop     rsi
0x1800a9a87  pop     rbp
0x1800a9a88  retn
0x1800a9a89  mov     eax, [rdi+0Ch]
0x1800a9a8c  mov     r8, [rbp+Size]; Size
0x1800a9a90  cmp     r8, rax
0x1800a9a93  jnz     loc_1800A9B19
0x1800a9a99  mov     rcx, [rbp+Buf1]; Buf1
0x1800a9a9d  mov     rdx, r14; Buf2
0x1800a9aa0  call    memcmp_0
0x1800a9aa5  test    eax, eax
0x1800a9aa7  jmp     loc_1800A9A09
0x1800a9aac  mov     rcx, gs:60h
0x1800a9ab5  mov     edx, 8; Flags
0x1800a9aba  mov     r8d, [rdi+0Ch]
0x1800a9abe  add     r8, 2; Size
0x1800a9ac2  mov     rcx, [rcx+30h]; HeapHandle
0x1800a9ac6  call    cs:__imp_RtlAllocateHeap
0x1800a9acc  mov     rsi, rax
0x1800a9acf  test    rax, rax
0x1800a9ad2  jnz     short loc_1800A9AEB
0x1800a9ad4  mov     r8d, 511h
0x1800a9ada  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x1800a9ae1  mov     ecx, 1
0x1800a9ae6  jmp     loc_1800A98ED
0x1800a9aeb  mov     r8d, [rdi+0Ch]; Size
0x1800a9aef  mov     rdx, r14; Src
0x1800a9af2  mov     rcx, rsi; void *
0x1800a9af5  call    memmove_0
0x1800a9afa  mov     ecx, [rdi+0Ch]
0x1800a9afd  shr     rcx, 1
0x1800a9b00  mov     [rsi+rcx*2], r13w
0x1800a9b05  mov     rcx, [rbp+arg_18]
0x1800a9b09  mov     rdx, rsi
0x1800a9b0c  call    AslStringPatternMatchExW
0x1800a9b11  test    eax, eax
0x1800a9b13  jnz     loc_1800A9A0F
0x1800a9b19  mov     ebx, 1
0x1800a9b1e  jmp     loc_1800A9A26
```
