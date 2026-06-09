# CKSThunkDriver::IsDeviceFilterable(_DEVICE_OBJECT *,long &)

- ea: `0x14000a770`
- end: `0x14000a852`
- name: `?IsDeviceFilterable@CKSThunkDriver@@EEAA_NPEAU_DEVICE_OBJECT@@AEAJ@Z`
- size: `226`
- prototype: `bool(CKSThunkDriver *__hidden this, struct _DEVICE_OBJECT *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140003770`
- `0x14000a770`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000a7ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a7ce`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14000a7a3`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14000a7a3`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000a809`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a7df`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a7df`
- `ntoskrnl!ZwClose` at `0x14000a81d`
- `ntoskrnl!ZwClose` at `0x14000a81d`

## string_xrefs

- `0x14000a7ba`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
bool __fastcall CKSThunkDriver::IsDeviceFilterable(CKSThunkDriver *this, struct _DEVICE_OBJECT *a2, int *a3)
{
  NTSTATUS v5; // eax
  HANDLE v6; // rbx
  __int64 (__fastcall *SystemRoutineAddress)(__int64, HANDLE, __int64 *, CKSThunkDriver *, _QWORD); // rax
  int v8; // eax
  HANDLE v9; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp+18h] BYREF

  Handle = 0;
  v5 = IoOpenDeviceRegistryKey(a2, 2u, 0x20019u, &Handle);
  *a3 = v5;
  if ( v5 >= 0 )
  {
    v6 = Handle;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = (__int64 (__fastcall *)(__int64, HANDLE, __int64 *, CKSThunkDriver *, _QWORD))MmGetSystemRoutineAddress(&DestinationString);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = (__int64 (__fastcall *)(__int64, HANDLE, __int64 *, CKSThunkDriver *, _QWORD))RtlQueryRegistryValues;
    v8 = SystemRoutineAddress(0x40000000, v6, &qword_140007000, this, 0);
    v9 = Handle;
    *a3 = v8;
    ZwClose(v9);
  }
  if ( *a3 != -1073741772 )
    return *a3 >= 0;
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x14000a770  mov     r11, rsp
0x14000a773  mov     [r11+8], rbx
0x14000a777  mov     [r11+10h], rsi
0x14000a77b  push    rdi
0x14000a77c  sub     rsp, 40h
0x14000a780  mov     rax, rdx
0x14000a783  mov     qword ptr [r11+18h], 0
0x14000a78b  mov     rdi, r8
0x14000a78e  lea     r9, [r11+18h]; DeviceRegKey
0x14000a792  mov     rsi, rcx
0x14000a795  mov     edx, 2; DevInstKeyType
0x14000a79a  mov     rcx, rax; DeviceObject
0x14000a79d  mov     r8d, 20019h; DesiredAccess
0x14000a7a3  call    cs:__imp_IoOpenDeviceRegistryKey
0x14000a7aa  nop     dword ptr [rax+rax+00h]
0x14000a7af  mov     [rdi], eax
0x14000a7b1  test    eax, eax
0x14000a7b3  js      short loc_14000A829
0x14000a7b5  mov     rbx, [rsp+48h+Handle]
0x14000a7ba  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x14000a7c1  xorps   xmm0, xmm0
0x14000a7c4  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14000a7c9  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x14000a7ce  call    cs:__imp_RtlInitUnicodeString
0x14000a7d5  nop     dword ptr [rax+rax+00h]
0x14000a7da  lea     rcx, [rsp+48h+DestinationString]; SystemRoutineName
0x14000a7df  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a7e6  nop     dword ptr [rax+rax+00h]
0x14000a7eb  mov     r9, rsi
0x14000a7ee  mov     [rsp+48h+var_28], 0
0x14000a7f7  test    rax, rax
0x14000a7fa  lea     r8, qword_140007000
0x14000a801  mov     rdx, rbx
0x14000a804  mov     ecx, 40000000h
0x14000a809  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000a811  call    _guard_dispatch_icall
0x14000a816  mov     rcx, [rsp+48h+Handle]; Handle
0x14000a81b  mov     [rdi], eax
0x14000a81d  call    cs:__imp_ZwClose
0x14000a824  nop     dword ptr [rax+rax+00h]
0x14000a829  mov     eax, [rdi]
0x14000a82b  cmp     eax, 0C0000034h
0x14000a830  jz      short loc_14000A839
0x14000a832  shr     eax, 1Fh
0x14000a835  xor     al, 1
0x14000a837  jmp     short loc_14000A841
0x14000a839  mov     dword ptr [rdi], 0
0x14000a83f  xor     al, al
0x14000a841  mov     rbx, [rsp+48h+arg_0]
0x14000a846  mov     rsi, [rsp+48h+arg_8]
0x14000a84b  add     rsp, 40h
0x14000a84f  pop     rdi
0x14000a850  retn
```
