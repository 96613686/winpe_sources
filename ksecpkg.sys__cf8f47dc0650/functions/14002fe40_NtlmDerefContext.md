# NtlmDerefContext

- ea: `0x14002fe40`
- end: `0x14002ff2d`
- name: `NtlmDerefContext`
- size: `237`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140021020`
- `0x140021110`
- `0x1400214a0`
- `0x140023500`
- `0x140023580`
- `0x140026220`
- `0x140028320`
- `0x1400283e0`
- `0x1400284d0`
- `0x140030590`

## callees

- `0x140010240`
- `0x14002fe40`

## import_xrefs

- `ntoskrnl!ZwSetInformationObject` at `0x14002feeb`
- `ntoskrnl!ZwSetInformationObject` at `0x14002feeb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fe78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fec1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fe78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fec1`
- `ntoskrnl!ZwClose` at `0x14002fefb`
- `ntoskrnl!ZwClose` at `0x14002fefb`
- `ntoskrnl!ObfDereferenceObject` at `0x14002ff09`
- `ntoskrnl!ObfDereferenceObject` at `0x14002ff09`
- `cng!BCryptDestroyKey` at `0x14002fe96`
- `cng!BCryptDestroyKey` at `0x14002ff17`
- `cng!BCryptDestroyKey` at `0x14002fe96`
- `cng!BCryptDestroyKey` at `0x14002ff17`

## pseudocode

```c
void __fastcall NtlmDerefContext(PVOID P)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  char v7; // [rsp+30h] [rbp+8h] BYREF
  __int16 ObjectInformation; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  (*((void (__fastcall **)(PVOID, char *))LsaKernelFunctions + 5))(P, &v7);
  if ( v7 )
  {
    v2 = (void *)*((_QWORD *)P + 16);
    if ( v2 )
      ExFreePoolWithTag(v2, 0);
    v3 = (void *)*((_QWORD *)P + 7);
    if ( v3 )
    {
      ObjectInformation = 0;
      ZwSetInformationObject(v3, ObjectHandleFlagInformation, &ObjectInformation, 2u);
      ZwClose(*((HANDLE *)P + 7));
    }
    v4 = (void *)*((_QWORD *)P + 13);
    if ( v4 )
    {
      BCryptDestroyKey(v4);
      *((_QWORD *)P + 13) = 0;
    }
    v5 = (void *)*((_QWORD *)P + 14);
    if ( v5 )
    {
      BCryptDestroyKey(v5);
      *((_QWORD *)P + 14) = 0;
    }
    v6 = (void *)*((_QWORD *)P + 8);
    if ( v6 )
      ObfDereferenceObject(v6);
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14002fe40  push    rbx
0x14002fe42  sub     rsp, 20h
0x14002fe46  mov     rax, cs:?LsaKernelFunctions@@3PEAU_SECPKG_KERNEL_FUNCTIONS@@EA; _SECPKG_KERNEL_FUNCTIONS * LsaKernelFunctions
0x14002fe4d  lea     rdx, [rsp+28h+arg_0]
0x14002fe52  mov     rbx, rcx
0x14002fe55  mov     [rsp+28h+arg_0], 0
0x14002fe5a  mov     rax, [rax+28h]
0x14002fe5e  call    _guard_dispatch_icall
0x14002fe63  cmp     [rsp+28h+arg_0], 0
0x14002fe68  jz      short loc_14002FECD
0x14002fe6a  mov     rcx, [rbx+80h]; P
0x14002fe71  test    rcx, rcx
0x14002fe74  jz      short loc_14002FE84
0x14002fe76  xor     edx, edx; Tag
0x14002fe78  call    cs:__imp_ExFreePoolWithTag
0x14002fe7f  nop     dword ptr [rax+rax+00h]
0x14002fe84  mov     rcx, [rbx+38h]; ObjectHandle
0x14002fe88  test    rcx, rcx
0x14002fe8b  jnz     short loc_14002FED4
0x14002fe8d  mov     rcx, [rbx+68h]; hKey
0x14002fe91  test    rcx, rcx
0x14002fe94  jz      short loc_14002FEAA
0x14002fe96  call    cs:__imp_BCryptDestroyKey
0x14002fe9d  nop     dword ptr [rax+rax+00h]
0x14002fea2  mov     qword ptr [rbx+68h], 0
0x14002feaa  mov     rcx, [rbx+70h]; hKey
0x14002feae  test    rcx, rcx
0x14002feb1  jnz     short loc_14002FF17
0x14002feb3  mov     rcx, [rbx+40h]; Object
0x14002feb7  test    rcx, rcx
0x14002feba  jnz     short loc_14002FF09
0x14002febc  xor     edx, edx; Tag
0x14002febe  mov     rcx, rbx; P
0x14002fec1  call    cs:__imp_ExFreePoolWithTag
0x14002fec8  nop     dword ptr [rax+rax+00h]
0x14002fecd  add     rsp, 20h
0x14002fed1  pop     rbx
0x14002fed2  retn
0x14002fed4  mov     r9d, 2; Length
0x14002feda  mov     [rsp+28h+ObjectInformation], 0
0x14002fee1  lea     r8, [rsp+28h+ObjectInformation]; ObjectInformation
0x14002fee6  mov     edx, 4; ObjectInformationClass
0x14002feeb  call    cs:__imp_ZwSetInformationObject
0x14002fef2  nop     dword ptr [rax+rax+00h]
0x14002fef7  mov     rcx, [rbx+38h]; Handle
0x14002fefb  call    cs:__imp_ZwClose
0x14002ff02  nop     dword ptr [rax+rax+00h]
0x14002ff07  jmp     short loc_14002FE8D
0x14002ff09  call    cs:__imp_ObfDereferenceObject
0x14002ff10  nop     dword ptr [rax+rax+00h]
0x14002ff15  jmp     short loc_14002FEBC
0x14002ff17  call    cs:__imp_BCryptDestroyKey
0x14002ff1e  nop     dword ptr [rax+rax+00h]
0x14002ff23  mov     qword ptr [rbx+70h], 0
0x14002ff2b  jmp     short loc_14002FEB3
```
