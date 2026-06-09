# AslRegistryGetString

- ea: `0x180006c80`
- end: `0x180006e3c`
- name: `AslRegistryGetString`
- size: `444`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180005620`
- `0x18000a39c`
- `0x18000adf8`

## callees

- `0x180006880`
- `0x180006c80`
- `0x180007738`
- `0x18000a7c4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180006ca8`
- `ntdll!RtlInitUnicodeString` at `0x180006ca8`
- `ntdll!ZwQueryValueKey` at `0x180006ccd`
- `ntdll!ZwQueryValueKey` at `0x180006d94`
- `ntdll!ZwQueryValueKey` at `0x180006ccd`
- `ntdll!ZwQueryValueKey` at `0x180006d94`
- `ntdll!RtlAllocateHeap` at `0x180006d37`
- `ntdll!RtlAllocateHeap` at `0x180006d37`

## string_xrefs

- `0x180006cff`: `AslRegistryGetString`
- `0x180006d52`: `AslRegistryGetString`
- `0x180006dc6`: `AslRegistryGetString`
- `0x180006e07`: `AslRegistryGetString`

## pseudocode

```c
NTSTATUS __fastcall AslRegistryGetString(_QWORD *a1, void *a2, const WCHAR *a3)
{
  NTSTATUS result; // eax
  NTSTATUS v6; // ebx
  _WORD *Heap; // rax
  _WORD *v8; // rbx
  NTSTATUS v9; // eax
  int v10; // esi
  const char *v11; // r9
  __int64 v12; // r8
  __int64 Length; // [rsp+20h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF

  *a1 = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a3);
  result = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
  v6 = result;
  if ( result == -1073741789 || result == -2147483643 )
  {
    ResultLength += 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
    v8 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "AslRegistryGetString", 1348, "Out of memory");
      return -1073741801;
    }
    v9 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, Heap, ResultLength, &ResultLength);
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = "Failed to query key value [%x]";
      v12 = 1360;
LABEL_13:
      LODWORD(Length) = v9;
      AslLogCallPrintf(1, "AslRegistryGetString", v12, v11, Length);
      goto LABEL_14;
    }
    if ( (unsigned int)(*((_DWORD *)v8 + 1) - 1) <= 1 )
    {
      v8[((unsigned __int64)*((unsigned int *)v8 + 2) >> 1) + 6] = 0;
      v9 = AslStringDuplicate(a1);
      v10 = v9;
      if ( v9 < 0 )
      {
        v11 = "Out of memory [%x]";
        v12 = 1378;
        goto LABEL_13;
      }
    }
    else
    {
      AslLogCallPrintf(1, "AslRegistryGetString", 1368, "Invalid value type");
      v10 = -1073741788;
    }
LABEL_14:
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
    return v10;
  }
  if ( result != -1073741772 )
  {
    AslLogCallPrintf(1, "AslRegistryGetString", 1334, "Failed to query key value [%x]", result);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180006c80  push    rbx
0x180006c82  push    rbp
0x180006c83  push    rsi
0x180006c84  push    rdi
0x180006c85  sub     rsp, 48h
0x180006c89  xor     ebp, ebp
0x180006c8b  mov     rsi, rdx
0x180006c8e  mov     [rcx], rbp
0x180006c91  mov     rdi, rcx
0x180006c94  xorps   xmm0, xmm0
0x180006c97  mov     [rsp+68h+arg_0], ebp
0x180006c9b  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180006ca0  mov     rdx, r8; SourceString
0x180006ca3  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180006ca8  call    cs:__imp_RtlInitUnicodeString
0x180006cae  lea     rax, [rsp+68h+arg_0]
0x180006cb3  xor     r9d, r9d; KeyValueInformation
0x180006cb6  mov     [rsp+68h+ResultLength], rax; ResultLength
0x180006cbb  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x180006cc0  mov     r8d, 2; KeyValueInformationClass
0x180006cc6  mov     dword ptr [rsp+68h+Length], ebp; Length
0x180006cca  mov     rcx, rsi; KeyHandle
0x180006ccd  call    cs:__imp_ZwQueryValueKey
0x180006cd3  mov     ebx, eax
0x180006cd5  cmp     eax, 0C0000023h
0x180006cda  jz      short loc_180006D17
0x180006cdc  cmp     eax, 80000005h
0x180006ce1  jz      short loc_180006D17
0x180006ce3  cmp     eax, 0C0000034h
0x180006ce8  jz      loc_180006E33
0x180006cee  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180006cf5  mov     dword ptr [rsp+68h+Length], eax
0x180006cf9  mov     r8d, 536h
0x180006cff  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180006d06  mov     ecx, 1
0x180006d0b  call    AslLogCallPrintf
0x180006d10  mov     eax, ebx
0x180006d12  jmp     loc_180006E33
0x180006d17  mov     eax, [rsp+68h+arg_0]
0x180006d1b  mov     edx, 8; Flags
0x180006d20  add     eax, 2
0x180006d23  mov     [rsp+68h+arg_0], eax
0x180006d27  mov     rcx, gs:60h
0x180006d30  mov     r8d, eax; Size
0x180006d33  mov     rcx, [rcx+30h]; HeapHandle
0x180006d37  call    cs:__imp_RtlAllocateHeap
0x180006d3d  mov     rbx, rax
0x180006d40  test    rax, rax
0x180006d43  jnz     short loc_180006D71
0x180006d45  lea     r9, aOutOfMemory; "Out of memory"
0x180006d4c  mov     r8d, 544h
0x180006d52  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180006d59  mov     ecx, 1
0x180006d5e  call    AslLogCallPrintf
0x180006d63  mov     eax, 0C0000017h
0x180006d68  add     rsp, 48h
0x180006d6c  pop     rdi
0x180006d6d  pop     rsi
0x180006d6e  pop     rbp
0x180006d6f  pop     rbx
0x180006d70  retn
0x180006d71  lea     rax, [rsp+68h+arg_0]
0x180006d76  mov     r9, rbx; KeyValueInformation
0x180006d79  mov     [rsp+68h+ResultLength], rax; ResultLength
0x180006d7e  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x180006d83  mov     eax, [rsp+68h+arg_0]
0x180006d87  mov     r8d, 2; KeyValueInformationClass
0x180006d8d  mov     rcx, rsi; KeyHandle
0x180006d90  mov     dword ptr [rsp+68h+Length], eax; Length
0x180006d94  call    cs:__imp_ZwQueryValueKey
0x180006d9a  mov     esi, eax
0x180006d9c  test    eax, eax
0x180006d9e  jns     short loc_180006DAF
0x180006da0  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180006da7  mov     r8d, 550h
0x180006dad  jmp     short loc_180006E07
0x180006daf  mov     eax, [rbx+4]
0x180006db2  dec     eax
0x180006db4  cmp     eax, 1
0x180006db7  jbe     short loc_180006DDE
0x180006db9  lea     r9, aInvalidValueTy; "Invalid value type"
0x180006dc0  mov     r8d, 558h
0x180006dc6  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180006dcd  mov     ecx, 1
0x180006dd2  call    AslLogCallPrintf
0x180006dd7  mov     esi, 0C0000024h
0x180006ddc  jmp     short loc_180006E1C
0x180006dde  mov     ecx, [rbx+8]
0x180006de1  lea     rdx, [rbx+0Ch]
0x180006de5  shr     rcx, 1
0x180006de8  mov     [rdx+rcx*2], bp
0x180006dec  mov     rcx, rdi
0x180006def  call    AslStringDuplicate
0x180006df4  mov     esi, eax
0x180006df6  test    eax, eax
0x180006df8  jns     short loc_180006E1C
0x180006dfa  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x180006e01  mov     r8d, 562h
0x180006e07  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x180006e0e  mov     dword ptr [rsp+68h+Length], eax
0x180006e12  mov     ecx, 1
0x180006e17  call    AslLogCallPrintf
0x180006e1c  mov     rcx, gs:60h
0x180006e25  mov     rdx, rbx
0x180006e28  mov     rcx, [rcx+30h]
0x180006e2c  call    AslFree
0x180006e31  mov     eax, esi
0x180006e33  add     rsp, 48h
0x180006e37  pop     rdi
0x180006e38  pop     rsi
0x180006e39  pop     rbp
0x180006e3a  pop     rbx
0x180006e3b  retn
```
