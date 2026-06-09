# SdbpCheckMatchingRegistryValue

- ea: `0x18007f554`
- end: `0x18007f8f8`
- name: `SdbpCheckMatchingRegistryValue`
- size: `932`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, wchar_t *String1@<rdx>, int, __int64, void *Buf1, size_t Size, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18007f34c`
- `0x18008036c`

## callees

- `0x18001ef8c`
- `0x18001f138`
- `0x18001f31c`
- `0x18005e5fc`
- `0x180061d70`
- `0x180061d88`
- `0x18007f554`
- `0x180082745`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x18007f604`
- `ntdll!ZwQueryValueKey` at `0x18007f692`
- `ntdll!ZwQueryValueKey` at `0x18007f604`
- `ntdll!ZwQueryValueKey` at `0x18007f692`
- `ntdll!RtlInitUnicodeString` at `0x18007f5da`
- `ntdll!RtlInitUnicodeString` at `0x18007f5da`
- `ntdll!RtlAllocateHeap` at `0x18007f640`
- `ntdll!RtlAllocateHeap` at `0x18007f752`
- `ntdll!RtlAllocateHeap` at `0x18007f895`
- `ntdll!RtlAllocateHeap` at `0x18007f640`
- `ntdll!RtlAllocateHeap` at `0x18007f752`
- `ntdll!RtlAllocateHeap` at `0x18007f895`

## string_xrefs

- `0x18007f5a2`: `dbRegistryDefaultName`
- `0x18007f661`: `SdbpCheckMatchingRegistryValue`
- `0x18007f6b5`: `SdbpCheckMatchingRegistryValue`
- `0x18007f71a`: `Unknown registry value data type`
- `0x18007f6a5`: `Failed to read value`

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
  int v21; // r8d
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
  if ( wcsicmp_0(String1, L"dbRegistryDefaultName") )
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
    AslLogCallPrintf(1, (unsigned int)"SdbpCheckMatchingRegistryValue", 1249, (unsigned int)"Failed to allocate memory");
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
  AslLogCallPrintf(1, (unsigned int)"SdbpCheckMatchingRegistryValue", v21, (_DWORD)v20);
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
0x18007f554  mov     [rsp-38h+arg_0], rbx
0x18007f559  mov     [rsp-38h+arg_18], r9
0x18007f55e  push    rbp
0x18007f55f  push    rsi
0x18007f560  push    rdi
0x18007f561  push    r12
0x18007f563  push    r13
0x18007f565  push    r14
0x18007f567  push    r15
0x18007f569  mov     rbp, rsp
0x18007f56c  sub     rsp, 50h
0x18007f570  xor     eax, eax
0x18007f572  xorps   xmm0, xmm0
0x18007f575  mov     [rbp+SourceString], rax
0x18007f579  mov     r12d, r8d
0x18007f57c  mov     [rbp+arg_8], eax
0x18007f57f  mov     r14, rdx
0x18007f582  mov     r13, rcx
0x18007f585  mov     r15d, eax
0x18007f588  mov     esi, eax
0x18007f58a  mov     edi, eax
0x18007f58c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18007f590  test    rdx, rdx
0x18007f593  jz      loc_18007F7DD
0x18007f599  cmp     [rdx], ax
0x18007f59c  jz      loc_18007F7DD
0x18007f5a2  lea     rdx, aDbregistrydefa; "dbRegistryDefaultName"
0x18007f5a9  mov     rcx, r14; String1
0x18007f5ac  mov     ebx, eax
0x18007f5ae  call    _wcsicmp_0
0x18007f5b3  test    eax, eax
0x18007f5b5  jnz     short loc_18007F5BB
0x18007f5b7  xor     edx, edx
0x18007f5b9  jmp     short loc_18007F5D6
0x18007f5bb  mov     rdx, r14
0x18007f5be  lea     rcx, [rbp+SourceString]
0x18007f5c2  call    AslStringDuplicate
0x18007f5c7  mov     r15, [rbp+SourceString]
0x18007f5cb  test    eax, eax
0x18007f5cd  js      loc_18007F823
0x18007f5d3  mov     rdx, r15; SourceString
0x18007f5d6  lea     rcx, [rbp+DestinationString]; DestinationString
0x18007f5da  call    cs:__imp_RtlInitUnicodeString
0x18007f5e1  nop     dword ptr [rax+rax+00h]
0x18007f5e6  xor     r9d, r9d; KeyValueInformation
0x18007f5e9  lea     rax, [rbp+arg_8]
0x18007f5ed  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18007f5f2  lea     rdx, [rbp+DestinationString]; ValueName
0x18007f5f6  mov     rcx, r13; KeyHandle
0x18007f5f9  mov     [rsp+50h+Length], ebx; Length
0x18007f5fd  lea     r14d, [r9+1]
0x18007f601  mov     r8d, r14d; KeyValueInformationClass
0x18007f604  call    cs:__imp_ZwQueryValueKey
0x18007f60b  nop     dword ptr [rax+rax+00h]
0x18007f610  test    eax, eax
0x18007f612  jns     short loc_18007F62A
0x18007f614  cmp     eax, 80000005h
0x18007f619  jz      short loc_18007F62A
0x18007f61b  cmp     eax, 0C0000023h
0x18007f620  jz      short loc_18007F62A
0x18007f622  mov     ebx, r14d
0x18007f625  jmp     loc_18007F823
0x18007f62a  mov     rcx, gs:60h
0x18007f633  mov     edx, 8; Flags
0x18007f638  mov     r8d, [rbp+arg_8]; Size
0x18007f63c  mov     rcx, [rcx+30h]; HeapHandle
0x18007f640  call    cs:__imp_RtlAllocateHeap
0x18007f647  nop     dword ptr [rax+rax+00h]
0x18007f64c  mov     rdi, rax
0x18007f64f  test    rax, rax
0x18007f652  jnz     short loc_18007F675
0x18007f654  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x18007f65b  mov     r8d, 4E1h
0x18007f661  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x18007f668  mov     ecx, r14d
0x18007f66b  call    AslLogCallPrintf
0x18007f670  jmp     loc_18007F823
0x18007f675  lea     rax, [rbp+arg_8]
0x18007f679  mov     r9, rdi; KeyValueInformation
0x18007f67c  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18007f681  lea     rdx, [rbp+DestinationString]; ValueName
0x18007f685  mov     eax, [rbp+arg_8]
0x18007f688  mov     r8d, r14d; KeyValueInformationClass
0x18007f68b  mov     rcx, r13; KeyHandle
0x18007f68e  mov     [rsp+50h+Length], eax; Length
0x18007f692  call    cs:__imp_ZwQueryValueKey
0x18007f699  nop     dword ptr [rax+rax+00h]
0x18007f69e  xor     r13d, r13d
0x18007f6a1  test    eax, eax
0x18007f6a3  jns     short loc_18007F6C6
0x18007f6a5  lea     r9, aFailedToReadVa_0; "Failed to read value"
0x18007f6ac  mov     r8d, 4ECh
0x18007f6b2  mov     ecx, r14d
0x18007f6b5  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x18007f6bc  call    AslLogCallPrintf
0x18007f6c1  jmp     loc_18007F7F4
0x18007f6c6  test    r12d, r12d
0x18007f6c9  jnz     short loc_18007F6DD
0x18007f6cb  mov     rax, [rbp+arg_40]
0x18007f6d2  mov     [rax], r14d
0x18007f6d5  mov     ebx, r14d
0x18007f6d8  jmp     loc_18007F7F4
0x18007f6dd  mov     ecx, [rdi+4]
0x18007f6e0  cmp     ecx, r12d
0x18007f6e3  jnz     short loc_18007F6D5
0x18007f6e5  mov     r14d, [rdi+8]
0x18007f6e9  add     r14, rdi
0x18007f6ec  sub     ecx, 1
0x18007f6ef  jz      loc_18007F87B
0x18007f6f5  sub     ecx, 1
0x18007f6f8  jz      loc_18007F87B
0x18007f6fe  sub     ecx, 1
0x18007f701  jz      loc_18007F858
0x18007f707  sub     ecx, 1
0x18007f70a  jz      loc_18007F7D1
0x18007f710  sub     ecx, 3
0x18007f713  jz      short loc_18007F738
0x18007f715  cmp     ecx, 4
0x18007f718  jz      short loc_18007F72C
0x18007f71a  lea     r9, aUnknownRegistr; "Unknown registry value data type"
0x18007f721  mov     r8d, 574h
0x18007f727  jmp     loc_18007F8B6
0x18007f72c  mov     rax, [r14]
0x18007f72f  cmp     [rbp+arg_28], rax
0x18007f733  jmp     loc_18007F7D7
0x18007f738  mov     rcx, gs:60h
0x18007f741  mov     edx, 8; Flags
0x18007f746  mov     r8d, [rdi+0Ch]
0x18007f74a  add     r8, 2; Size
0x18007f74e  mov     rcx, [rcx+30h]; HeapHandle
0x18007f752  call    cs:__imp_RtlAllocateHeap
0x18007f759  nop     dword ptr [rax+rax+00h]
0x18007f75e  mov     rsi, rax
0x18007f761  test    rax, rax
0x18007f764  jnz     short loc_18007F771
0x18007f766  mov     r8d, 529h
0x18007f76c  jmp     loc_18007F8AF
0x18007f771  mov     r8d, [rdi+0Ch]; Size
0x18007f775  mov     rdx, r14; Src
0x18007f778  mov     rcx, rsi; void *
0x18007f77b  call    memmove_0
0x18007f780  mov     ecx, [rdi+0Ch]
0x18007f783  shr     rcx, 1
0x18007f786  mov     [rsi+rcx*2], r13w
0x18007f78b  mov     rcx, rsi
0x18007f78e  mov     eax, [rdi+0Ch]
0x18007f791  and     rax, 0FFFFFFFFFFFFFFFEh
0x18007f795  add     rax, rsi
0x18007f798  cmp     rsi, rax
0x18007f79b  jnb     loc_18007F8DA
0x18007f7a1  lea     rax, [rcx+2]
0x18007f7a5  cmp     [rcx], r13w
0x18007f7a9  jnz     short loc_18007F7BA
0x18007f7ab  cmp     [rax], r13w
0x18007f7af  jz      loc_18007F8DA
0x18007f7b5  mov     word ptr [rcx], 3Bh ; ';'
0x18007f7ba  mov     rcx, rax
0x18007f7bd  mov     eax, [rdi+0Ch]
0x18007f7c0  and     rax, 0FFFFFFFFFFFFFFFEh
0x18007f7c4  add     rax, rsi
0x18007f7c7  cmp     rcx, rax
0x18007f7ca  jb      short loc_18007F7A1
0x18007f7cc  jmp     loc_18007F8DA
0x18007f7d1  mov     eax, [r14]
0x18007f7d4  cmp     [rbp+arg_20], eax
0x18007f7d7  jnz     loc_18007F8EE
0x18007f7dd  mov     rax, [rbp+arg_40]
0x18007f7e4  mov     dword ptr [rax], 1
0x18007f7ea  mov     ebx, 1
0x18007f7ef  test    rdi, rdi
0x18007f7f2  jz      short loc_18007F809
0x18007f7f4  mov     rcx, gs:60h
0x18007f7fd  mov     rdx, rdi
0x18007f800  mov     rcx, [rcx+30h]
0x18007f804  call    AslFree
0x18007f809  test    rsi, rsi
0x18007f80c  jz      short loc_18007F823
0x18007f80e  mov     rcx, gs:60h
0x18007f817  mov     rdx, rsi
0x18007f81a  mov     rcx, [rcx+30h]
0x18007f81e  call    AslFree
0x18007f823  test    r15, r15
0x18007f826  jz      short loc_18007F83D
0x18007f828  mov     rcx, gs:60h
0x18007f831  mov     rdx, r15
0x18007f834  mov     rcx, [rcx+30h]
0x18007f838  call    AslFree
0x18007f83d  mov     eax, ebx
0x18007f83f  mov     rbx, [rsp+50h+arg_0]
0x18007f847  add     rsp, 50h
0x18007f84b  pop     r15
0x18007f84d  pop     r14
0x18007f84f  pop     r13
0x18007f851  pop     r12
0x18007f853  pop     rdi
0x18007f854  pop     rsi
0x18007f855  pop     rbp
0x18007f856  retn
0x18007f858  mov     eax, [rdi+0Ch]
0x18007f85b  mov     r8, [rbp+Size]; Size
0x18007f85f  cmp     r8, rax
0x18007f862  jnz     loc_18007F8EE
0x18007f868  mov     rcx, [rbp+Buf1]; Buf1
0x18007f86c  mov     rdx, r14; Buf2
0x18007f86f  call    memcmp_0
0x18007f874  test    eax, eax
0x18007f876  jmp     loc_18007F7D7
0x18007f87b  mov     rcx, gs:60h
0x18007f884  mov     edx, 8; Flags
0x18007f889  mov     r8d, [rdi+0Ch]
0x18007f88d  add     r8, 2; Size
0x18007f891  mov     rcx, [rcx+30h]; HeapHandle
0x18007f895  call    cs:__imp_RtlAllocateHeap
0x18007f89c  nop     dword ptr [rax+rax+00h]
0x18007f8a1  mov     rsi, rax
0x18007f8a4  test    rax, rax
0x18007f8a7  jnz     short loc_18007F8C0
0x18007f8a9  mov     r8d, 511h
0x18007f8af  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x18007f8b6  mov     ecx, 1
0x18007f8bb  jmp     loc_18007F6B5
0x18007f8c0  mov     r8d, [rdi+0Ch]; Size
0x18007f8c4  mov     rdx, r14; Src
0x18007f8c7  mov     rcx, rsi; void *
0x18007f8ca  call    memmove_0
0x18007f8cf  mov     ecx, [rdi+0Ch]
0x18007f8d2  shr     rcx, 1
0x18007f8d5  mov     [rsi+rcx*2], r13w
0x18007f8da  mov     rcx, [rbp+arg_18]
0x18007f8de  mov     rdx, rsi
0x18007f8e1  call    AslStringPatternMatchExW
0x18007f8e6  test    eax, eax
0x18007f8e8  jnz     loc_18007F7DD
0x18007f8ee  mov     ebx, 1
0x18007f8f3  jmp     loc_18007F7F4
```
