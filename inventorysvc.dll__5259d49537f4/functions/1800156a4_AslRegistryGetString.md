# AslRegistryGetString

- ea: `0x1800156a4`
- end: `0x180015867`
- name: `AslRegistryGetString`
- size: `451`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180015870`
- `0x180016e90`
- `0x180017f84`

## callees

- `0x1800152d0`
- `0x1800156a4`
- `0x180017adc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180015855`
- `ntdll!RtlFreeHeap` at `0x180015855`
- `ntdll!RtlAllocateHeap` at `0x180015762`
- `ntdll!RtlAllocateHeap` at `0x180015762`
- `ntdll!RtlInitUnicodeString` at `0x1800156d3`
- `ntdll!RtlInitUnicodeString` at `0x1800156d3`
- `ntdll!ZwQueryValueKey` at `0x1800156fa`
- `ntdll!ZwQueryValueKey` at `0x1800157b9`
- `ntdll!ZwQueryValueKey` at `0x1800156fa`
- `ntdll!ZwQueryValueKey` at `0x1800157b9`

## string_xrefs

- `0x18001572c`: `AslRegistryGetString`
- `0x18001577d`: `AslRegistryGetString`
- `0x1800157eb`: `AslRegistryGetString`
- `0x18001582e`: `AslRegistryGetString`

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
0x1800156a4  push    rbx
0x1800156a6  push    rsi
0x1800156a7  push    rdi
0x1800156a8  push    r14
0x1800156aa  sub     rsp, 48h
0x1800156ae  mov     rsi, rdx
0x1800156b1  mov     qword ptr [rcx], 0
0x1800156b8  mov     r14, rcx
0x1800156bb  mov     [rsp+68h+arg_0], 0
0x1800156c3  xorps   xmm0, xmm0
0x1800156c6  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800156cb  mov     rdx, r8; SourceString
0x1800156ce  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800156d3  call    cs:__imp_RtlInitUnicodeString
0x1800156d9  xor     r9d, r9d; KeyValueInformation
0x1800156dc  lea     rax, [rsp+68h+arg_0]
0x1800156e1  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1800156e6  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1800156eb  mov     rcx, rsi; KeyHandle
0x1800156ee  mov     dword ptr [rsp+68h+Length], 0; Length
0x1800156f6  lea     r8d, [r9+2]; KeyValueInformationClass
0x1800156fa  call    cs:__imp_ZwQueryValueKey
0x180015700  mov     ebx, eax
0x180015702  cmp     eax, 80000005h
0x180015707  jz      short loc_180015742
0x180015709  cmp     eax, 0C0000023h
0x18001570e  jz      short loc_180015742
0x180015710  cmp     eax, 0C0000034h
0x180015715  jz      loc_18001585B
0x18001571b  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180015722  mov     dword ptr [rsp+68h+Length], eax
0x180015726  mov     r8d, 536h
0x18001572c  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180015733  mov     ecx, 1
0x180015738  call    AslLogCallPrintf
0x18001573d  jmp     loc_18001585B
0x180015742  mov     eax, [rsp+68h+arg_0]
0x180015746  mov     edx, 8; Flags
0x18001574b  add     eax, 2
0x18001574e  mov     [rsp+68h+arg_0], eax
0x180015752  mov     rcx, gs:60h
0x18001575b  mov     r8d, eax; Size
0x18001575e  mov     rcx, [rcx+30h]; HeapHandle
0x180015762  call    cs:__imp_RtlAllocateHeap
0x180015768  mov     rdi, rax
0x18001576b  test    rax, rax
0x18001576e  jnz     short loc_180015796
0x180015770  lea     r9, aOutOfMemory_0; "Out of memory"
0x180015777  mov     r8d, 544h
0x18001577d  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180015784  mov     ebx, 0C0000017h
0x180015789  lea     ecx, [rax+1]
0x18001578c  call    AslLogCallPrintf
0x180015791  jmp     loc_18001585B
0x180015796  lea     rax, [rsp+68h+arg_0]
0x18001579b  mov     r9, rdi; KeyValueInformation
0x18001579e  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1800157a3  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1800157a8  mov     eax, [rsp+68h+arg_0]
0x1800157ac  mov     r8d, 2; KeyValueInformationClass
0x1800157b2  mov     rcx, rsi; KeyHandle
0x1800157b5  mov     dword ptr [rsp+68h+Length], eax; Length
0x1800157b9  call    cs:__imp_ZwQueryValueKey
0x1800157bf  mov     ebx, eax
0x1800157c1  test    eax, eax
0x1800157c3  jns     short loc_1800157D4
0x1800157c5  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x1800157cc  mov     r8d, 550h
0x1800157d2  jmp     short loc_18001582E
0x1800157d4  mov     eax, [rdi+4]
0x1800157d7  dec     eax
0x1800157d9  cmp     eax, 1
0x1800157dc  jbe     short loc_180015803
0x1800157de  lea     r9, aInvalidValueTy; "Invalid value type"
0x1800157e5  mov     r8d, 558h
0x1800157eb  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x1800157f2  mov     ecx, 1
0x1800157f7  call    AslLogCallPrintf
0x1800157fc  mov     ebx, 0C0000024h
0x180015801  jmp     short loc_180015843
0x180015803  mov     ecx, [rdi+8]
0x180015806  lea     rdx, [rdi+0Ch]
0x18001580a  shr     rcx, 1
0x18001580d  xor     eax, eax
0x18001580f  mov     [rdx+rcx*2], ax
0x180015813  mov     rcx, r14
0x180015816  call    AslStringDuplicate
0x18001581b  mov     ebx, eax
0x18001581d  test    eax, eax
0x18001581f  jns     short loc_180015843
0x180015821  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x180015828  mov     r8d, 562h
0x18001582e  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180015835  mov     dword ptr [rsp+68h+Length], eax
0x180015839  mov     ecx, 1
0x18001583e  call    AslLogCallPrintf
0x180015843  mov     rcx, gs:60h
0x18001584c  mov     r8, rdi; P
0x18001584f  xor     edx, edx; Flags
0x180015851  mov     rcx, [rcx+30h]; HeapHandle
0x180015855  call    cs:__imp_RtlFreeHeap
0x18001585b  mov     eax, ebx
0x18001585d  add     rsp, 48h
0x180015861  pop     r14
0x180015863  pop     rdi
0x180015864  pop     rsi
0x180015865  pop     rbx
0x180015866  retn
```
