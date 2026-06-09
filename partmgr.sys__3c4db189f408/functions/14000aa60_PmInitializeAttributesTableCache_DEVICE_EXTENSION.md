# PmInitializeAttributesTableCache(_DEVICE_EXTENSION *)

- ea: `0x14000aa60`
- end: `0x14000ab34`
- name: `?PmInitializeAttributesTableCache@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007674`

## callees

- `0x14000aa60`
- `0x14001fda0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab15`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab15`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aafd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aafd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aad6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aad6`

## string_xrefs

- `0x14000aa87`: `AttributesTableCache`

## pseudocode

```c
__int64 __fastcall PmInitializeAttributesTableCache(struct _DEVICE_EXTENSION *a1)
{
  int DeviceParameterBinary; // edi
  __int64 v3; // rax
  KIRQL v4; // al
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF
  PVOID P; // [rsp+40h] [rbp+18h] BYREF

  P = 0;
  v6 = 0;
  DeviceParameterBinary = PmGetDeviceParameterBinary(a1, L"AttributesTableCache", &P, &v6);
  if ( DeviceParameterBinary >= 0 )
  {
    if ( v6 >= 0x18 )
    {
      v3 = *(_QWORD *)P - *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1;
      if ( *(_QWORD *)P == *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1 )
        v3 = *((_QWORD *)P + 1) - *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
      if ( v3 )
      {
        DeviceParameterBinary = -1073739509;
      }
      else
      {
        v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
        *((_QWORD *)a1 + 141) = P;
        P = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v4);
      }
    }
    else
    {
      DeviceParameterBinary = -1073741820;
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)DeviceParameterBinary;
}

```

## disassembly

```asm
0x14000aa60  mov     rax, rsp
0x14000aa63  mov     [rax+8], rbx
0x14000aa67  mov     [rax+20h], rsi
0x14000aa6b  push    rdi
0x14000aa6c  sub     rsp, 20h
0x14000aa70  lea     r9, [rax+10h]; unsigned int *
0x14000aa74  mov     qword ptr [rax+18h], 0
0x14000aa7c  lea     r8, [rax+18h]; void **
0x14000aa80  mov     dword ptr [rax+10h], 0
0x14000aa87  lea     rdx, aAttributestabl; "AttributesTableCache"
0x14000aa8e  mov     rsi, rcx
0x14000aa91  call    ?PmGetDeviceParameterBinary@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAPEAXPEAK@Z; PmGetDeviceParameterBinary(_DEVICE_EXTENSION *,ushort *,void * *,ulong *)
0x14000aa96  mov     edi, eax
0x14000aa98  test    eax, eax
0x14000aa9a  js      short loc_14000AB09
0x14000aa9c  cmp     [rsp+28h+arg_8], 18h
0x14000aaa1  jnb     short loc_14000AAAA
0x14000aaa3  mov     edi, 0C0000004h
0x14000aaa8  jmp     short loc_14000AB09
0x14000aaaa  mov     rcx, [rsp+28h+P]
0x14000aaaf  mov     rax, [rcx]
0x14000aab2  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x14000aab9  jnz     short loc_14000AAC6
0x14000aabb  mov     rax, [rcx+8]
0x14000aabf  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x14000aac6  test    rax, rax
0x14000aac9  jz      short loc_14000AAD2
0x14000aacb  mov     edi, 0C000090Bh
0x14000aad0  jmp     short loc_14000AB09
0x14000aad2  lea     rcx, [rsi+70h]; SpinLock
0x14000aad6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000aadd  nop     dword ptr [rax+rax+00h]
0x14000aae2  mov     rdx, [rsp+28h+P]
0x14000aae7  lea     rcx, [rsi+70h]; SpinLock
0x14000aaeb  mov     [rsi+468h], rdx
0x14000aaf2  mov     dl, al; NewIrql
0x14000aaf4  mov     [rsp+28h+P], 0
0x14000aafd  call    cs:__imp_KeReleaseSpinLock
0x14000ab04  nop     dword ptr [rax+rax+00h]
0x14000ab09  mov     rcx, [rsp+28h+P]; P
0x14000ab0e  test    rcx, rcx
0x14000ab11  jz      short loc_14000AB21
0x14000ab13  xor     edx, edx; Tag
0x14000ab15  call    cs:__imp_ExFreePoolWithTag
0x14000ab1c  nop     dword ptr [rax+rax+00h]
0x14000ab21  mov     rbx, [rsp+28h+arg_0]
0x14000ab26  mov     eax, edi
0x14000ab28  mov     rsi, [rsp+28h+arg_18]
0x14000ab2d  add     rsp, 20h
0x14000ab31  pop     rdi
0x14000ab32  retn
```
