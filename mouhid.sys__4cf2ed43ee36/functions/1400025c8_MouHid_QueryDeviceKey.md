# MouHid_QueryDeviceKey

- ea: `0x1400025c8`
- end: `0x1400026c8`
- name: `MouHid_QueryDeviceKey`
- size: `256`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001960`

## callees

- `0x1400025c8`
- `0x140004ec0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140002664`
- `ntoskrnl!ZwQueryValueKey` at `0x140002664`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000269b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000269b`
- `ntoskrnl!ExAllocatePool2` at `0x14000262d`
- `ntoskrnl!ExAllocatePool2` at `0x14000262d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400025f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400025f4`

## pseudocode

```c
__int64 __fastcall MouHid_QueryDeviceKey(HANDLE KeyHandle, const WCHAR *a2, void *a3)
{
  unsigned int *Pool2; // rbx
  NTSTATUS v6; // edi
  unsigned int v7; // eax
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  ULONG Length; // [rsp+68h] [rbp+20h] BYREF

  Length = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  if ( (unsigned int)ValueName.MaximumLength + 28 < (unsigned int)ValueName.MaximumLength + 24 )
    return 3221225621LL;
  Length = ValueName.MaximumLength + 28;
  Pool2 = (unsigned int *)ExAllocatePool2(256, Length, 1215655757);
  if ( Pool2 )
  {
    v6 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, Pool2, Length, &Length);
    if ( v6 >= 0 )
    {
      v7 = Pool2[3];
      if ( v7 > 4 )
        v6 = -1073741789;
      else
        memmove(a3, (char *)Pool2 + Pool2[2], v7);
    }
    ExFreePoolWithTag(Pool2, 0);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400025c8  mov     rax, rsp
0x1400025cb  mov     [rax+8], rbx
0x1400025cf  mov     [rax+10h], rsi
0x1400025d3  mov     [rax+20h], r9d
0x1400025d7  push    rdi
0x1400025d8  sub     rsp, 40h
0x1400025dc  mov     rdi, rcx
0x1400025df  mov     dword ptr [rax+20h], 0
0x1400025e6  xorps   xmm0, xmm0
0x1400025e9  lea     rcx, [rax-18h]; DestinationString
0x1400025ed  movups  xmmword ptr [rax-18h], xmm0
0x1400025f1  mov     rsi, r8
0x1400025f4  call    cs:__imp_RtlInitUnicodeString
0x1400025fb  nop     dword ptr [rax+rax+00h]
0x140002600  movzx   edx, [rsp+48h+ValueName.MaximumLength]
0x140002605  add     edx, 18h
0x140002608  cmp     edx, 18h
0x14000260b  jb      loc_1400026B2
0x140002611  lea     eax, [rdx+4]
0x140002614  cmp     eax, edx
0x140002616  jb      loc_1400026B2
0x14000261c  mov     edx, eax
0x14000261e  mov     ecx, 100h
0x140002623  mov     r8d, 48756F4Dh
0x140002629  mov     [rsp+48h+arg_18], eax
0x14000262d  call    cs:__imp_ExAllocatePool2
0x140002634  nop     dword ptr [rax+rax+00h]
0x140002639  mov     rbx, rax
0x14000263c  test    rax, rax
0x14000263f  jz      short loc_1400026A9
0x140002641  mov     ecx, [rsp+48h+arg_18]
0x140002645  lea     rax, [rsp+48h+arg_18]
0x14000264a  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14000264f  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140002654  mov     [rsp+48h+Length], ecx; Length
0x140002658  mov     r9, rbx; KeyValueInformation
0x14000265b  mov     rcx, rdi; KeyHandle
0x14000265e  mov     r8d, 1; KeyValueInformationClass
0x140002664  call    cs:__imp_ZwQueryValueKey
0x14000266b  nop     dword ptr [rax+rax+00h]
0x140002670  mov     edi, eax
0x140002672  test    eax, eax
0x140002674  js      short loc_140002696
0x140002676  mov     eax, [rbx+0Ch]
0x140002679  cmp     eax, 4
0x14000267c  ja      short loc_140002691
0x14000267e  mov     edx, [rbx+8]
0x140002681  mov     r8d, eax; Size
0x140002684  add     rdx, rbx; Src
0x140002687  mov     rcx, rsi; void *
0x14000268a  call    memmove
0x14000268f  jmp     short loc_140002696
0x140002691  mov     edi, 0C0000023h
0x140002696  xor     edx, edx; Tag
0x140002698  mov     rcx, rbx; P
0x14000269b  call    cs:__imp_ExFreePoolWithTag
0x1400026a2  nop     dword ptr [rax+rax+00h]
0x1400026a7  jmp     short loc_1400026AE
0x1400026a9  mov     edi, 0C0000017h
0x1400026ae  mov     eax, edi
0x1400026b0  jmp     short loc_1400026B7
0x1400026b2  mov     eax, 0C0000095h
0x1400026b7  mov     rbx, [rsp+48h+arg_0]
0x1400026bc  mov     rsi, [rsp+48h+arg_8]
0x1400026c1  add     rsp, 40h
0x1400026c5  pop     rdi
0x1400026c6  retn
```
