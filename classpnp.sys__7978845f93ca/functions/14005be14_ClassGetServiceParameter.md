# ClassGetServiceParameter

- ea: `0x14005be14`
- end: `0x14005bee6`
- name: `ClassGetServiceParameter`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14001f978`

## callees

- `0x14003e470`
- `0x14003e940`
- `0x14005be14`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14005be86`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005be86`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14005beb5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14005be96`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14005be96`

## string_xrefs

- `0x14005be56`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall ClassGetServiceParameter(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int64 v5; // rax
  __int64 v6; // rbx
  PVOID SystemRoutineAddress; // rax
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-29h] BYREF
  _QWORD v10[14]; // [rsp+48h] [rbp-19h] BYREF
  unsigned int v11; // [rsp+D0h] [rbp+6Fh] BYREF
  int v12; // [rsp+D4h] [rbp+73h]

  v12 = HIDWORD(a2);
  memset(v10, 0, sizeof(v10));
  v11 = 0;
  v10[2] = L"IdleClassSupported";
  LODWORD(v10[1]) = 292;
  v10[3] = &v11;
  v5 = *(_QWORD *)(a1 + 32);
  LODWORD(v10[4]) = 0x4000000;
  DestinationString = 0;
  v6 = *(_QWORD *)(v5 + 8);
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  result = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(0, v6, v10, 0, 0);
  if ( (int)result >= 0 )
  {
    result = v11;
    *a3 = v11;
  }
  return result;
}

```

## disassembly

```asm
0x14005be14  mov     rax, rsp
0x14005be17  mov     [rax+8], rbx
0x14005be1b  mov     [rax+18h], rdi
0x14005be1f  mov     [rax+10h], rdx
0x14005be23  push    rbp
0x14005be24  lea     rbp, [rax-5Fh]
0x14005be28  sub     rsp, 0B0h
0x14005be2f  xor     edx, edx; Val
0x14005be31  mov     rdi, r8
0x14005be34  mov     rbx, rcx
0x14005be37  lea     rcx, [rbp+57h+var_70]; void *
0x14005be3b  lea     r8d, [rdx+70h]; Size
0x14005be3f  call    memset
0x14005be44  lea     rax, aIdleclasssuppo; "IdleClassSupported"
0x14005be4b  mov     [rbp+57h+arg_8], 0
0x14005be52  mov     [rbp+57h+var_60], rax
0x14005be56  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x14005be5d  lea     rax, [rbp+57h+arg_8]
0x14005be61  mov     [rbp+57h+var_68], 124h
0x14005be68  mov     [rbp+57h+var_58], rax
0x14005be6c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005be70  mov     rax, [rbx+20h]
0x14005be74  xorps   xmm0, xmm0
0x14005be77  mov     [rbp+57h+var_50], 4000000h
0x14005be7e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005be82  mov     rbx, [rax+8]
0x14005be86  call    cs:__imp_RtlInitUnicodeString
0x14005be8d  nop     dword ptr [rax+rax+00h]
0x14005be92  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14005be96  call    cs:__imp_MmGetSystemRoutineAddress
0x14005be9d  nop     dword ptr [rax+rax+00h]
0x14005bea2  lea     r8, [rbp+57h+var_70]
0x14005bea6  mov     [rsp+0B0h+var_90], 0
0x14005beaf  test    rax, rax
0x14005beb2  mov     rdx, rbx
0x14005beb5  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14005bebd  xor     r9d, r9d
0x14005bec0  xor     ecx, ecx
0x14005bec2  call    _guard_dispatch_icall
0x14005bec7  test    eax, eax
0x14005bec9  js      short loc_14005BED0
0x14005becb  mov     eax, [rbp+57h+arg_8]
0x14005bece  mov     [rdi], eax
0x14005bed0  lea     r11, [rsp+0B0h+var_s0]
0x14005bed8  mov     rbx, [r11+10h]
0x14005bedc  mov     rdi, [r11+20h]
0x14005bee0  mov     rsp, r11
0x14005bee3  pop     rbp
0x14005bee4  retn
```
