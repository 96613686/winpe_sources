# AslRegistryGetString

- ea: `0x18000e71c`
- end: `0x18000e8df`
- name: `AslRegistryGetString`
- size: `451`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b8e8`
- `0x18000e8e8`
- `0x180015b58`

## callees

- `0x18000e240`
- `0x18000e71c`
- `0x18000eef4`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x18000e772`
- `ntdll!ZwQueryValueKey` at `0x18000e831`
- `ntdll!ZwQueryValueKey` at `0x18000e772`
- `ntdll!ZwQueryValueKey` at `0x18000e831`
- `ntdll!RtlFreeHeap` at `0x18000e8cd`
- `ntdll!RtlFreeHeap` at `0x18000e8cd`
- `ntdll!RtlAllocateHeap` at `0x18000e7da`
- `ntdll!RtlAllocateHeap` at `0x18000e7da`
- `ntdll!RtlInitUnicodeString` at `0x18000e74b`
- `ntdll!RtlInitUnicodeString` at `0x18000e74b`

## string_xrefs

- `0x18000e7a4`: `AslRegistryGetString`
- `0x18000e7f5`: `AslRegistryGetString`
- `0x18000e863`: `AslRegistryGetString`
- `0x18000e8a6`: `AslRegistryGetString`

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
0x18000e71c  push    rbx
0x18000e71e  push    rsi
0x18000e71f  push    rdi
0x18000e720  push    r14
0x18000e722  sub     rsp, 48h
0x18000e726  mov     rsi, rdx
0x18000e729  mov     qword ptr [rcx], 0
0x18000e730  mov     r14, rcx
0x18000e733  mov     [rsp+68h+arg_0], 0
0x18000e73b  xorps   xmm0, xmm0
0x18000e73e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18000e743  mov     rdx, r8; SourceString
0x18000e746  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18000e74b  call    cs:__imp_RtlInitUnicodeString
0x18000e751  xor     r9d, r9d; KeyValueInformation
0x18000e754  lea     rax, [rsp+68h+arg_0]
0x18000e759  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18000e75e  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x18000e763  mov     rcx, rsi; KeyHandle
0x18000e766  mov     dword ptr [rsp+68h+Length], 0; Length
0x18000e76e  lea     r8d, [r9+2]; KeyValueInformationClass
0x18000e772  call    cs:__imp_ZwQueryValueKey
0x18000e778  mov     ebx, eax
0x18000e77a  cmp     eax, 80000005h
0x18000e77f  jz      short loc_18000E7BA
0x18000e781  cmp     eax, 0C0000023h
0x18000e786  jz      short loc_18000E7BA
0x18000e788  cmp     eax, 0C0000034h
0x18000e78d  jz      loc_18000E8D3
0x18000e793  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18000e79a  mov     dword ptr [rsp+68h+Length], eax
0x18000e79e  mov     r8d, 536h
0x18000e7a4  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18000e7ab  mov     ecx, 1
0x18000e7b0  call    AslLogCallPrintf
0x18000e7b5  jmp     loc_18000E8D3
0x18000e7ba  mov     eax, [rsp+68h+arg_0]
0x18000e7be  mov     edx, 8; Flags
0x18000e7c3  add     eax, 2
0x18000e7c6  mov     [rsp+68h+arg_0], eax
0x18000e7ca  mov     rcx, gs:60h
0x18000e7d3  mov     r8d, eax; Size
0x18000e7d6  mov     rcx, [rcx+30h]; HeapHandle
0x18000e7da  call    cs:__imp_RtlAllocateHeap
0x18000e7e0  mov     rdi, rax
0x18000e7e3  test    rax, rax
0x18000e7e6  jnz     short loc_18000E80E
0x18000e7e8  lea     r9, aOutOfMemory; "Out of memory"
0x18000e7ef  mov     r8d, 544h
0x18000e7f5  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18000e7fc  mov     ebx, 0C0000017h
0x18000e801  lea     ecx, [rax+1]
0x18000e804  call    AslLogCallPrintf
0x18000e809  jmp     loc_18000E8D3
0x18000e80e  lea     rax, [rsp+68h+arg_0]
0x18000e813  mov     r9, rdi; KeyValueInformation
0x18000e816  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18000e81b  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x18000e820  mov     eax, [rsp+68h+arg_0]
0x18000e824  mov     r8d, 2; KeyValueInformationClass
0x18000e82a  mov     rcx, rsi; KeyHandle
0x18000e82d  mov     dword ptr [rsp+68h+Length], eax; Length
0x18000e831  call    cs:__imp_ZwQueryValueKey
0x18000e837  mov     ebx, eax
0x18000e839  test    eax, eax
0x18000e83b  jns     short loc_18000E84C
0x18000e83d  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18000e844  mov     r8d, 550h
0x18000e84a  jmp     short loc_18000E8A6
0x18000e84c  mov     eax, [rdi+4]
0x18000e84f  dec     eax
0x18000e851  cmp     eax, 1
0x18000e854  jbe     short loc_18000E87B
0x18000e856  lea     r9, aInvalidValueTy; "Invalid value type"
0x18000e85d  mov     r8d, 558h
0x18000e863  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18000e86a  mov     ecx, 1
0x18000e86f  call    AslLogCallPrintf
0x18000e874  mov     ebx, 0C0000024h
0x18000e879  jmp     short loc_18000E8BB
0x18000e87b  mov     ecx, [rdi+8]
0x18000e87e  lea     rdx, [rdi+0Ch]
0x18000e882  shr     rcx, 1
0x18000e885  xor     eax, eax
0x18000e887  mov     [rdx+rcx*2], ax
0x18000e88b  mov     rcx, r14
0x18000e88e  call    AslStringDuplicate
0x18000e893  mov     ebx, eax
0x18000e895  test    eax, eax
0x18000e897  jns     short loc_18000E8BB
0x18000e899  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x18000e8a0  mov     r8d, 562h
0x18000e8a6  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18000e8ad  mov     dword ptr [rsp+68h+Length], eax
0x18000e8b1  mov     ecx, 1
0x18000e8b6  call    AslLogCallPrintf
0x18000e8bb  mov     rcx, gs:60h
0x18000e8c4  mov     r8, rdi; P
0x18000e8c7  xor     edx, edx; Flags
0x18000e8c9  mov     rcx, [rcx+30h]; HeapHandle
0x18000e8cd  call    cs:__imp_RtlFreeHeap
0x18000e8d3  mov     eax, ebx
0x18000e8d5  add     rsp, 48h
0x18000e8d9  pop     r14
0x18000e8db  pop     rdi
0x18000e8dc  pop     rsi
0x18000e8dd  pop     rbx
0x18000e8de  retn
```
