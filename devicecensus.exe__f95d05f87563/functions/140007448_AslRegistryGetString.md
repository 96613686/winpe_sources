# AslRegistryGetString

- ea: `0x140007448`
- end: `0x14000760b`
- name: `AslRegistryGetString`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD *, void *, const WCHAR *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140007614`
- `0x140008c40`
- `0x140009c7c`

## callees

- `0x140007074`
- `0x140007448`
- `0x1400097d4`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x14000749e`
- `ntdll!ZwQueryValueKey` at `0x14000755d`
- `ntdll!ZwQueryValueKey` at `0x14000749e`
- `ntdll!ZwQueryValueKey` at `0x14000755d`
- `ntdll!RtlFreeHeap` at `0x1400075f9`
- `ntdll!RtlFreeHeap` at `0x1400075f9`
- `ntdll!RtlAllocateHeap` at `0x140007506`
- `ntdll!RtlAllocateHeap` at `0x140007506`
- `ntdll!RtlInitUnicodeString` at `0x140007477`
- `ntdll!RtlInitUnicodeString` at `0x140007477`

## string_xrefs

- `0x1400074d0`: `AslRegistryGetString`
- `0x140007521`: `AslRegistryGetString`
- `0x14000758f`: `AslRegistryGetString`
- `0x1400075d2`: `AslRegistryGetString`

## pseudocode

```c
__int64 __fastcall AslRegistryGetString(_QWORD *a1, void *a2, const WCHAR *a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  _DWORD *Heap; // rax
  _DWORD *v8; // rdi
  NTSTATUS v9; // eax
  const char *v10; // r9
  __int64 v11; // r8
  __int64 Length; // [rsp+20h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF

  *a1 = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a3);
  v5 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
  v6 = v5;
  if ( v5 == -2147483643 || v5 == -1073741789 )
  {
    ResultLength += 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
    v8 = Heap;
    if ( !Heap )
    {
      v6 = -1073741801;
      AslLogCallPrintf(1, "AslRegistryGetString", 1348, "Out of memory");
      return v6;
    }
    v9 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, Heap, ResultLength, &ResultLength);
    v6 = v9;
    if ( v9 < 0 )
    {
      v10 = "Failed to query key value [%x]";
      v11 = 1360;
LABEL_13:
      LODWORD(Length) = v9;
      AslLogCallPrintf(1, "AslRegistryGetString", v11, v10, Length);
      goto LABEL_14;
    }
    if ( (unsigned int)(v8[1] - 1) <= 1 )
    {
      *((_WORD *)v8 + ((unsigned __int64)(unsigned int)v8[2] >> 1) + 6) = 0;
      v9 = AslStringDuplicate(a1, v8 + 3);
      v6 = v9;
      if ( v9 < 0 )
      {
        v10 = "Out of memory [%x]";
        v11 = 1378;
        goto LABEL_13;
      }
    }
    else
    {
      AslLogCallPrintf(1, "AslRegistryGetString", 1368, "Invalid value type");
      v6 = -1073741788;
    }
LABEL_14:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    return v6;
  }
  if ( v5 != -1073741772 )
    AslLogCallPrintf(1, "AslRegistryGetString", 1334, "Failed to query key value [%x]", v5);
  return v6;
}

```

## disassembly

```asm
0x140007448  push    rbx
0x14000744a  push    rsi
0x14000744b  push    rdi
0x14000744c  push    r14
0x14000744e  sub     rsp, 48h
0x140007452  mov     rsi, rdx
0x140007455  mov     qword ptr [rcx], 0
0x14000745c  mov     r14, rcx
0x14000745f  mov     [rsp+68h+arg_0], 0
0x140007467  xorps   xmm0, xmm0
0x14000746a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14000746f  mov     rdx, r8; SourceString
0x140007472  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140007477  call    cs:__imp_RtlInitUnicodeString
0x14000747d  xor     r9d, r9d; KeyValueInformation
0x140007480  lea     rax, [rsp+68h+arg_0]
0x140007485  mov     [rsp+68h+ResultLength], rax; ResultLength
0x14000748a  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14000748f  mov     rcx, rsi; KeyHandle
0x140007492  mov     dword ptr [rsp+68h+Length], 0; Length
0x14000749a  lea     r8d, [r9+2]; KeyValueInformationClass
0x14000749e  call    cs:__imp_ZwQueryValueKey
0x1400074a4  mov     ebx, eax
0x1400074a6  cmp     eax, 80000005h
0x1400074ab  jz      short loc_1400074E6
0x1400074ad  cmp     eax, 0C0000023h
0x1400074b2  jz      short loc_1400074E6
0x1400074b4  cmp     eax, 0C0000034h
0x1400074b9  jz      loc_1400075FF
0x1400074bf  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x1400074c6  mov     dword ptr [rsp+68h+Length], eax
0x1400074ca  mov     r8d, 536h
0x1400074d0  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x1400074d7  mov     ecx, 1
0x1400074dc  call    AslLogCallPrintf
0x1400074e1  jmp     loc_1400075FF
0x1400074e6  mov     eax, [rsp+68h+arg_0]
0x1400074ea  mov     edx, 8; Flags
0x1400074ef  add     eax, 2
0x1400074f2  mov     [rsp+68h+arg_0], eax
0x1400074f6  mov     rcx, gs:60h
0x1400074ff  mov     r8d, eax; Size
0x140007502  mov     rcx, [rcx+30h]; HeapHandle
0x140007506  call    cs:__imp_RtlAllocateHeap
0x14000750c  mov     rdi, rax
0x14000750f  test    rax, rax
0x140007512  jnz     short loc_14000753A
0x140007514  lea     r9, aOutOfMemory; "Out of memory"
0x14000751b  mov     r8d, 544h
0x140007521  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x140007528  mov     ebx, 0C0000017h
0x14000752d  lea     ecx, [rax+1]
0x140007530  call    AslLogCallPrintf
0x140007535  jmp     loc_1400075FF
0x14000753a  lea     rax, [rsp+68h+arg_0]
0x14000753f  mov     r9, rdi; KeyValueInformation
0x140007542  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140007547  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14000754c  mov     eax, [rsp+68h+arg_0]
0x140007550  mov     r8d, 2; KeyValueInformationClass
0x140007556  mov     rcx, rsi; KeyHandle
0x140007559  mov     dword ptr [rsp+68h+Length], eax; Length
0x14000755d  call    cs:__imp_ZwQueryValueKey
0x140007563  mov     ebx, eax
0x140007565  test    eax, eax
0x140007567  jns     short loc_140007578
0x140007569  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x140007570  mov     r8d, 550h
0x140007576  jmp     short loc_1400075D2
0x140007578  mov     eax, [rdi+4]
0x14000757b  dec     eax
0x14000757d  cmp     eax, 1
0x140007580  jbe     short loc_1400075A7
0x140007582  lea     r9, aInvalidValueTy; "Invalid value type"
0x140007589  mov     r8d, 558h
0x14000758f  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x140007596  mov     ecx, 1
0x14000759b  call    AslLogCallPrintf
0x1400075a0  mov     ebx, 0C0000024h
0x1400075a5  jmp     short loc_1400075E7
0x1400075a7  mov     ecx, [rdi+8]
0x1400075aa  lea     rdx, [rdi+0Ch]
0x1400075ae  shr     rcx, 1
0x1400075b1  xor     eax, eax
0x1400075b3  mov     [rdx+rcx*2], ax
0x1400075b7  mov     rcx, r14
0x1400075ba  call    AslStringDuplicate
0x1400075bf  mov     ebx, eax
0x1400075c1  test    eax, eax
0x1400075c3  jns     short loc_1400075E7
0x1400075c5  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x1400075cc  mov     r8d, 562h
0x1400075d2  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x1400075d9  mov     dword ptr [rsp+68h+Length], eax
0x1400075dd  mov     ecx, 1
0x1400075e2  call    AslLogCallPrintf
0x1400075e7  mov     rcx, gs:60h
0x1400075f0  mov     r8, rdi; P
0x1400075f3  xor     edx, edx; Flags
0x1400075f5  mov     rcx, [rcx+30h]; HeapHandle
0x1400075f9  call    cs:__imp_RtlFreeHeap
0x1400075ff  mov     eax, ebx
0x140007601  add     rsp, 48h
0x140007605  pop     r14
0x140007607  pop     rdi
0x140007608  pop     rsi
0x140007609  pop     rbx
0x14000760a  retn
```
