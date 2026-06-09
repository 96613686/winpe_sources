# AslRegistryGetString

- ea: `0x180066fec`
- end: `0x1800671af`
- name: `AslRegistryGetString`
- size: `451`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800671b8`
- `0x18006b3a0`
- `0x18007298c`

## callees

- `0x180066c10`
- `0x180066fec`
- `0x1800680ac`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x180067042`
- `ntdll!ZwQueryValueKey` at `0x180067101`
- `ntdll!ZwQueryValueKey` at `0x180067042`
- `ntdll!ZwQueryValueKey` at `0x180067101`
- `ntdll!RtlAllocateHeap` at `0x1800670aa`
- `ntdll!RtlAllocateHeap` at `0x1800670aa`
- `ntdll!RtlFreeHeap` at `0x18006719d`
- `ntdll!RtlFreeHeap` at `0x18006719d`
- `ntdll!RtlInitUnicodeString` at `0x18006701b`
- `ntdll!RtlInitUnicodeString` at `0x18006701b`

## string_xrefs

- `0x180067074`: `AslRegistryGetString`
- `0x1800670c5`: `AslRegistryGetString`
- `0x180067133`: `AslRegistryGetString`
- `0x180067176`: `AslRegistryGetString`

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
0x180066fec  push    rbx
0x180066fee  push    rsi
0x180066fef  push    rdi
0x180066ff0  push    r14
0x180066ff2  sub     rsp, 48h
0x180066ff6  mov     rsi, rdx
0x180066ff9  mov     qword ptr [rcx], 0
0x180067000  mov     r14, rcx
0x180067003  mov     [rsp+68h+arg_0], 0
0x18006700b  xorps   xmm0, xmm0
0x18006700e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180067013  mov     rdx, r8; SourceString
0x180067016  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18006701b  call    cs:__imp_RtlInitUnicodeString
0x180067021  xor     r9d, r9d; KeyValueInformation
0x180067024  lea     rax, [rsp+68h+arg_0]
0x180067029  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18006702e  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x180067033  mov     rcx, rsi; KeyHandle
0x180067036  mov     dword ptr [rsp+68h+Length], 0; Length
0x18006703e  lea     r8d, [r9+2]; KeyValueInformationClass
0x180067042  call    cs:__imp_ZwQueryValueKey
0x180067048  mov     ebx, eax
0x18006704a  cmp     eax, 80000005h
0x18006704f  jz      short loc_18006708A
0x180067051  cmp     eax, 0C0000023h
0x180067056  jz      short loc_18006708A
0x180067058  cmp     eax, 0C0000034h
0x18006705d  jz      loc_1800671A3
0x180067063  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18006706a  mov     dword ptr [rsp+68h+Length], eax
0x18006706e  mov     r8d, 536h
0x180067074  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18006707b  mov     ecx, 1
0x180067080  call    AslLogCallPrintf
0x180067085  jmp     loc_1800671A3
0x18006708a  mov     eax, [rsp+68h+arg_0]
0x18006708e  mov     edx, 8; Flags
0x180067093  add     eax, 2
0x180067096  mov     [rsp+68h+arg_0], eax
0x18006709a  mov     rcx, gs:60h
0x1800670a3  mov     r8d, eax; Size
0x1800670a6  mov     rcx, [rcx+30h]; HeapHandle
0x1800670aa  call    cs:__imp_RtlAllocateHeap
0x1800670b0  mov     rdi, rax
0x1800670b3  test    rax, rax
0x1800670b6  jnz     short loc_1800670DE
0x1800670b8  lea     r9, aOutOfMemory_0; "Out of memory"
0x1800670bf  mov     r8d, 544h
0x1800670c5  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x1800670cc  mov     ebx, 0C0000017h
0x1800670d1  lea     ecx, [rax+1]
0x1800670d4  call    AslLogCallPrintf
0x1800670d9  jmp     loc_1800671A3
0x1800670de  lea     rax, [rsp+68h+arg_0]
0x1800670e3  mov     r9, rdi; KeyValueInformation
0x1800670e6  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1800670eb  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1800670f0  mov     eax, [rsp+68h+arg_0]
0x1800670f4  mov     r8d, 2; KeyValueInformationClass
0x1800670fa  mov     rcx, rsi; KeyHandle
0x1800670fd  mov     dword ptr [rsp+68h+Length], eax; Length
0x180067101  call    cs:__imp_ZwQueryValueKey
0x180067107  mov     ebx, eax
0x180067109  test    eax, eax
0x18006710b  jns     short loc_18006711C
0x18006710d  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180067114  mov     r8d, 550h
0x18006711a  jmp     short loc_180067176
0x18006711c  mov     eax, [rdi+4]
0x18006711f  dec     eax
0x180067121  cmp     eax, 1
0x180067124  jbe     short loc_18006714B
0x180067126  lea     r9, aInvalidValueTy; "Invalid value type"
0x18006712d  mov     r8d, 558h
0x180067133  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18006713a  mov     ecx, 1
0x18006713f  call    AslLogCallPrintf
0x180067144  mov     ebx, 0C0000024h
0x180067149  jmp     short loc_18006718B
0x18006714b  mov     ecx, [rdi+8]
0x18006714e  lea     rdx, [rdi+0Ch]
0x180067152  shr     rcx, 1
0x180067155  xor     eax, eax
0x180067157  mov     [rdx+rcx*2], ax
0x18006715b  mov     rcx, r14
0x18006715e  call    AslStringDuplicate
0x180067163  mov     ebx, eax
0x180067165  test    eax, eax
0x180067167  jns     short loc_18006718B
0x180067169  lea     r9, aOutOfMemoryX_0; "Out of memory [%x]"
0x180067170  mov     r8d, 562h
0x180067176  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x18006717d  mov     dword ptr [rsp+68h+Length], eax
0x180067181  mov     ecx, 1
0x180067186  call    AslLogCallPrintf
0x18006718b  mov     rcx, gs:60h
0x180067194  mov     r8, rdi; P
0x180067197  xor     edx, edx; Flags
0x180067199  mov     rcx, [rcx+30h]; HeapHandle
0x18006719d  call    cs:__imp_RtlFreeHeap
0x1800671a3  mov     eax, ebx
0x1800671a5  add     rsp, 48h
0x1800671a9  pop     r14
0x1800671ab  pop     rdi
0x1800671ac  pop     rsi
0x1800671ad  pop     rbx
0x1800671ae  retn
```
